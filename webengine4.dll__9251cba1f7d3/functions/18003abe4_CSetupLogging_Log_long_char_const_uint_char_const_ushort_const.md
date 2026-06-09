# CSetupLogging::Log(long,char const *,uint,char const *,ushort const *)

- ea: `0x18003abe4`
- end: `0x18003acd1`
- name: `?Log@CSetupLogging@@SAXJPEBDI0PEBG@Z`
- size: `237`
- prototype: `void __fastcall(int, const char *, unsigned int, const char *, const unsigned __int16 *)`
- caller_count: `46`
- callee_count: `3`
- tags: `file_ops, installer_update`

## callers

- `0x18000d850`
- `0x180023c24`
- `0x180024d70`
- `0x1800251a8`
- `0x180033d68`
- `0x180036aa0`
- `0x180037324`
- `0x1800376f8`
- `0x18003785c`
- `0x180037b08`
- `0x180038250`
- `0x1800385e0`
- `0x180038808`
- `0x1800393c4`
- `0x1800397d4`
- `0x180039d9c`
- `0x18003a498`
- `0x18003a78c`
- `0x18003aba8`
- `0x18003abbc`
- `0x18003acd4`
- `0x18003b2c8`
- `0x18003ba0c`
- `0x18003c1e8`
- `0x18003c630`
- `0x18003c86c`
- `0x18003cbac`
- `0x18003ccd4`
- `0x18003dd70`
- `0x18003dfc0`
- `0x18003e2e8`
- `0x18003e494`
- `0x18003e744`
- `0x18003e808`
- `0x18003ea8c`
- `0x18003ef38`
- `0x18003f778`
- `0x18003f800`
- `0x18003ff7c`
- `0x1800400a8`
- `0x18004086c`
- `0x180041488`
- `0x180041724`
- `0x1800418cc`
- `0x180041e84`
- `0x180042f28`

## callees

- `0x18003abe4`
- `0x18003b35c`
- `0x18004d030`

## import_xrefs

- `KERNEL32!WriteFile` at `0x18003ac92`
- `KERNEL32!WriteFile` at `0x18003ac92`
- `KERNEL32!EnterCriticalSection` at `0x18003ac64`
- `KERNEL32!EnterCriticalSection` at `0x18003ac64`
- `KERNEL32!LeaveCriticalSection` at `0x18003acb3`
- `KERNEL32!LeaveCriticalSection` at `0x18003acb3`
- `KERNEL32!lstrlenA` at `0x18003ac6f`
- `KERNEL32!lstrlenA` at `0x18003ac6f`
- `KERNEL32!FlushFileBuffers` at `0x18003aca2`
- `KERNEL32!FlushFileBuffers` at `0x18003aca2`

## pseudocode

```c
void __fastcall CSetupLogging::Log(int a1, const char *a2, unsigned int a3, const char *a4, unsigned __int16 *a5)
{
  DWORD v5; // eax
  DWORD NumberOfBytesWritten; // [rsp+40h] [rbp-428h] BYREF
  CHAR String[1024]; // [rsp+50h] [rbp-418h] BYREF

  if ( CSetupLogging::g_pThis && *(_QWORD *)CSetupLogging::g_pThis && *((int *)CSetupLogging::g_pThis + 12) <= 20 )
  {
    NumberOfBytesWritten = 0;
    CSetupLogging::PrepareLogEntry(CSetupLogging::g_pThis, a1, a2, a3, a4, a5, String, 1024);
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)CSetupLogging::g_pThis + 8));
    v5 = lstrlenA(String);
    WriteFile(*(HANDLE *)CSetupLogging::g_pThis, String, v5, &NumberOfBytesWritten, 0);
    FlushFileBuffers(*(HANDLE *)CSetupLogging::g_pThis);
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)CSetupLogging::g_pThis + 8));
  }
}

```

## disassembly

```asm
0x18003abe4  sub     rsp, 468h
0x18003abeb  mov     rax, cs:__security_cookie
0x18003abf2  xor     rax, rsp
0x18003abf5  mov     [rsp+468h+var_18], rax
0x18003abfd  mov     r10, [rsp+468h+arg_20]
0x18003ac05  mov     eax, ecx
0x18003ac07  mov     rcx, cs:?g_pThis@CSetupLogging@@0PEAV1@EA; this
0x18003ac0e  test    rcx, rcx
0x18003ac11  jz      loc_18003ACB9
0x18003ac17  cmp     qword ptr [rcx], 0
0x18003ac1b  jz      loc_18003ACB9
0x18003ac21  cmp     dword ptr [rcx+30h], 14h
0x18003ac25  jg      loc_18003ACB9
0x18003ac2b  and     [rsp+468h+NumberOfBytesWritten], 0
0x18003ac30  lea     r11, [rsp+468h+String]
0x18003ac35  mov     [rsp+468h+var_430], 400h; int
0x18003ac3d  mov     [rsp+468h+var_438], r11; char *
0x18003ac42  mov     [rsp+468h+var_440], r10; unsigned __int16 *
0x18003ac47  mov     [rsp+468h+lpOverlapped], r9; char *
0x18003ac4c  mov     r9d, r8d; unsigned int
0x18003ac4f  mov     r8, rdx; char *
0x18003ac52  mov     edx, eax; int
0x18003ac54  call    ?PrepareLogEntry@CSetupLogging@@AEAAXJPEBDI0PEBGPEADH@Z; CSetupLogging::PrepareLogEntry(long,char const *,uint,char const *,ushort const *,char *,int)
0x18003ac59  mov     rcx, cs:?g_pThis@CSetupLogging@@0PEAV1@EA; CSetupLogging * CSetupLogging::g_pThis
0x18003ac60  add     rcx, 8; lpCriticalSection
0x18003ac64  call    cs:__imp_EnterCriticalSection
0x18003ac6a  lea     rcx, [rsp+468h+String]; lpString
0x18003ac6f  call    cs:__imp_lstrlenA
0x18003ac75  mov     rcx, cs:?g_pThis@CSetupLogging@@0PEAV1@EA; CSetupLogging * CSetupLogging::g_pThis
0x18003ac7c  lea     r9, [rsp+468h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18003ac81  and     [rsp+468h+lpOverlapped], 0
0x18003ac87  lea     rdx, [rsp+468h+String]; lpBuffer
0x18003ac8c  mov     r8d, eax; nNumberOfBytesToWrite
0x18003ac8f  mov     rcx, [rcx]; hFile
0x18003ac92  call    cs:__imp_WriteFile
0x18003ac98  mov     rcx, cs:?g_pThis@CSetupLogging@@0PEAV1@EA; CSetupLogging * CSetupLogging::g_pThis
0x18003ac9f  mov     rcx, [rcx]; hFile
0x18003aca2  call    cs:__imp_FlushFileBuffers
0x18003aca8  mov     rcx, cs:?g_pThis@CSetupLogging@@0PEAV1@EA; CSetupLogging * CSetupLogging::g_pThis
0x18003acaf  add     rcx, 8; lpCriticalSection
0x18003acb3  call    cs:__imp_LeaveCriticalSection
0x18003acb9  mov     rcx, [rsp+468h+var_18]
0x18003acc1  xor     rcx, rsp; StackCookie
0x18003acc4  call    __security_check_cookie
0x18003acc9  add     rsp, 468h
0x18003acd0  retn
```
