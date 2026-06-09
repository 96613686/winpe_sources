# FetchWinErrorSymbolicName

- ea: `0x1800457fc`
- end: `0x180045823`
- name: `FetchWinErrorSymbolicName`
- size: `39`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path`

## callers

- `0x180043390`

## callees

- `0x180021c58`
- `0x1800457fc`

## import_xrefs

- `ext-ms-win-core-symbolicnames-l1-1-0!GetWinErrorSymbolicName` at `0x180045814`

## pseudocode

```c
__int64 __fastcall FetchWinErrorSymbolicName(__int64 a1, __int64 a2)
{
  unsigned int v2; // ebx

  v2 = a1;
  if ( (unsigned __int8)IsGetNetEventSymbolicNamePresent(a1, a2) )
    return GetWinErrorSymbolicName(v2);
  else
    return 0;
}

```

## disassembly

```asm
0x1800457fc  push    rbx
0x1800457fe  sub     rsp, 20h
0x180045802  mov     ebx, ecx
0x180045804  call    IsGetNetEventSymbolicNamePresent
0x180045809  test    al, al
0x18004580b  jz      short loc_18004581B
0x18004580d  mov     ecx, ebx
0x18004580f  add     rsp, 20h
0x180045813  pop     rbx
0x180045814  jmp     cs:__imp_GetWinErrorSymbolicName
0x18004581b  xor     eax, eax
0x18004581d  add     rsp, 20h
0x180045821  pop     rbx
0x180045822  retn
```
