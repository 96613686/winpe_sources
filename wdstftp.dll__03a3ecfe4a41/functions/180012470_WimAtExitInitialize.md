# WimAtExitInitialize

- ea: `0x180012470`
- end: `0x1800124e3`
- name: `WimAtExitInitialize`
- size: `115`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update`

## callees

- `0x180012470`
- `0x1800219c4`
- `0x1800608a8`

## import_xrefs

- `KERNEL32!InitializeCriticalSection` at `0x18001247f`
- `KERNEL32!InitializeCriticalSection` at `0x18001247f`
- `KERNEL32!DeleteCriticalSection` at `0x1800124c3`
- `KERNEL32!DeleteCriticalSection` at `0x1800124c3`

## pseudocode

```c
__int64 WimAtExitInitialize()
{
  unsigned int v0; // ebx

  v0 = 0;
  InitializeCriticalSection(&stru_180077AA0);
  if ( atexit(WimAtExitDestroy) )
  {
    v0 = -2147024882;
    UtilReportError(
      (__int64)L"WimAtExitInitialize",
      (__int64)L"onecore\\base\\ntsetup\\opktools\\osimage\\lib\\utility\\utility.c",
      0x41u,
      -2147024882);
    DeleteCriticalSection(&stru_180077AA0);
  }
  else
  {
    dword_1800778F4 = 1;
  }
  return v0;
}

```

## disassembly

```asm
0x180012470  push    rbx
0x180012472  sub     rsp, 20h
0x180012476  lea     rcx, stru_180077AA0; lpCriticalSection
0x18001247d  xor     ebx, ebx
0x18001247f  call    cs:__imp_InitializeCriticalSection
0x180012486  nop     dword ptr [rax+rax+00h]
0x18001248b  lea     rcx, WimAtExitDestroy; void (__cdecl *)()
0x180012492  call    atexit
0x180012497  test    eax, eax
0x180012499  jz      short loc_1800124D1
0x18001249b  mov     ebx, 8007000Eh
0x1800124a0  lea     rdx, aOnecoreBaseNts_1; "onecore\\base\\ntsetup\\opktools\\osima"...
0x1800124a7  mov     r9d, ebx
0x1800124aa  lea     rcx, aWimatexitiniti; "WimAtExitInitialize"
0x1800124b1  mov     r8d, 41h ; 'A'
0x1800124b7  call    UtilReportError
0x1800124bc  lea     rcx, stru_180077AA0; lpCriticalSection
0x1800124c3  call    cs:__imp_DeleteCriticalSection
0x1800124ca  nop     dword ptr [rax+rax+00h]
0x1800124cf  jmp     short loc_1800124DB
0x1800124d1  mov     cs:dword_1800778F4, 1
0x1800124db  mov     eax, ebx
0x1800124dd  add     rsp, 20h
0x1800124e1  pop     rbx
0x1800124e2  retn
```
