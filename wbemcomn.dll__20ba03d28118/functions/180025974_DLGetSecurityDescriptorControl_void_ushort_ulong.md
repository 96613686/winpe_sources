# DLGetSecurityDescriptorControl(void *,ushort *,ulong *)

- ea: `0x180025974`
- end: `0x1800259e4`
- name: `?DLGetSecurityDescriptorControl@@YAHPEAXPEAGPEAK@Z`
- size: `112`
- prototype: `__int64 __fastcall(void *, unsigned __int16 *, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18003b580`

## callees

- `0x18001d19c`
- `0x180025974`
- `0x180047010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800259ba`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800259ba`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800259d0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800259d0`

## string_xrefs

- `0x1800259c9`: `GetSecurityDescriptorControl`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall DLGetSecurityDescriptorControl(void *a1, unsigned __int16 *a2, unsigned int *a3)
{
  FARPROC ProcAddress; // rax
  unsigned int v7; // ebx
  DWORD SecurityDll; // eax

  ProcAddress = (FARPROC)qword_180070340;
  if ( !qword_180070340 )
  {
    v7 = 0;
    SecurityDll = DLpLoadSecurityDll();
    if ( SecurityDll )
    {
      SetLastError(SecurityDll);
      return v7;
    }
    ProcAddress = GetProcAddress(g_hInstSecurityDLL, "GetSecurityDescriptorControl");
    qword_180070340 = (__int64)ProcAddress;
    if ( !ProcAddress )
      return v7;
  }
  return ((unsigned int (__fastcall *)(void *, unsigned __int16 *, unsigned int *))ProcAddress)(a1, a2, a3);
}

```

## disassembly

```asm
0x180025974  push    rbx
0x180025976  push    rbp
0x180025977  push    rsi
0x180025978  push    rdi
0x180025979  sub     rsp, 28h
0x18002597d  mov     rax, cs:qword_180070340
0x180025984  mov     rdi, r8
0x180025987  mov     rsi, rdx
0x18002598a  mov     rbp, rcx
0x18002598d  test    rax, rax
0x180025990  jz      short loc_1800259AD
0x180025992  mov     r8, rdi
0x180025995  mov     rdx, rsi
0x180025998  mov     rcx, rbp
0x18002599b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800259a0  mov     ebx, eax
0x1800259a2  mov     eax, ebx
0x1800259a4  add     rsp, 28h
0x1800259a8  pop     rdi
0x1800259a9  pop     rsi
0x1800259aa  pop     rbp
0x1800259ab  pop     rbx
0x1800259ac  retn
0x1800259ad  xor     ebx, ebx
0x1800259af  call    ?DLpLoadSecurityDll@@YAKXZ; DLpLoadSecurityDll(void)
0x1800259b4  test    eax, eax
0x1800259b6  jz      short loc_1800259C2
0x1800259b8  mov     ecx, eax; dwErrCode
0x1800259ba  call    cs:__imp_SetLastError
0x1800259c0  jmp     short loc_1800259A2
0x1800259c2  mov     rcx, cs:?g_hInstSecurityDLL@@3PEAUHINSTANCE__@@EA; hModule
0x1800259c9  lea     rdx, aGetsecuritydes_2; "GetSecurityDescriptorControl"
0x1800259d0  call    cs:__imp_GetProcAddress
0x1800259d6  mov     cs:qword_180070340, rax
0x1800259dd  test    rax, rax
0x1800259e0  jz      short loc_1800259A2
0x1800259e2  jmp     short loc_180025992
```
