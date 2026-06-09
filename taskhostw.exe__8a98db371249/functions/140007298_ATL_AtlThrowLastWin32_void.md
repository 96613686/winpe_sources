# ATL::AtlThrowLastWin32(void)

- ea: `0x140007298`
- end: `0x1400072b6`
- name: `?AtlThrowLastWin32@ATL@@YAXXZ`
- size: `30`
- prototype: `void __noreturn(void)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x140001fb0`
- `0x1400022d0`
- `0x140002970`
- `0x1400068f0`
- `0x140009430`

## callees

- `0x140007298`
- `0x1400072bc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000729c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000729c`

## pseudocode

```c
void __noreturn ATL::AtlThrowLastWin32(void)
{
  signed int LastError; // eax

  LastError = GetLastError();
  if ( LastError > 0 )
    LastError = (unsigned __int16)LastError | 0x80070000;
  ATL::PrivateAtlThrow(LastError);
}

```

## disassembly

```asm
0x140007298  sub     rsp, 28h
0x14000729c  call    cs:__imp_GetLastError
0x1400072a2  test    eax, eax
0x1400072a4  jle     short loc_1400072AE
0x1400072a6  movzx   eax, ax
0x1400072a9  or      eax, 80070000h
0x1400072ae  mov     ecx, eax; int
0x1400072b0  call    ?PrivateAtlThrow@ATL@@YAXJ@Z; ATL::PrivateAtlThrow(long)
```
