# _guard_dispatch_icall_nop

- ea: `0x140016a80`
- end: `0x140016a82`
- name: `_guard_dispatch_icall_nop`
- size: `2`
- prototype: ``
- caller_count: `18`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x140003670`
- `0x1400042e8`
- `0x14000457c`
- `0x1400046bc`
- `0x140004764`
- `0x140010fa8`
- `0x140012d04`
- `0x14001481c`
- `0x140015970`
- `0x140015c48`
- `0x140016338`
- `0x140016590`
- `0x1400165c4`
- `0x14001668c`
- `0x140016830`
- `0x140016ab0`
- `0x140025180`
- `0x140027008`

## pseudocode

```c
__int64 __fastcall guard_dispatch_icall_nop()
{
  __int64 (*v0)(void); // rax

  return v0();
}

```

## disassembly

```asm
0x140016a80  jmp     rax
```
