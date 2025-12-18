# code_caver.wds

WinDbg script port of [code_caver.py](../code_caver.py) - no pykd dependency required.

## Usage
```
$$>a<path\to\code_caver.wds <start_addr> <end_addr>
```

Get module range with `lm m <module>`, then pass the addresses:
```
0:000> lm m kernel32
start    end        module name
77d10000 77da0000   kernel32

0:000> $$>a<C:\tools\code_caver.wds 77d10000 77da0000
```

## Notes

- Handles 64-bit addresses natively
- Detects all executable protection types (0x10, 0x20, 0x40, 0x80)
- Works with WinDbg classic