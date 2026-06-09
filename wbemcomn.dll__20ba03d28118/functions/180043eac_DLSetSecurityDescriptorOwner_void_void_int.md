# DLSetSecurityDescriptorOwner(void *,void *,int)

- ea: `0x180043eac`
- end: `0x180043f24`
- name: `?DLSetSecurityDescriptorOwner@@YAHPEAX0H@Z`
- size: `120`
- prototype: `__int64 __fastcall(void *, void *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18001a730`

## callees

- `0x18001d19c`
- `0x180043eac`
- `0x180047010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180043eda`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180043eda`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180043ef0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180043ef0`

## string_xrefs

- `0x180043ee9`: `SetSecurityDescriptorOwner`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall DLSetSecurityDescriptorOwner(void *a1, void *a2)
{
  FARPROC ProcAddress; // rax
  unsigned int v5; // ebx
  DWORD SecurityDll; // eax

  ProcAddress = (FARPROC)qword_180070370;
  if ( qword_180070370 )
    return ((unsigned int (__fastcall *)(void *, void *, _QWORD))ProcAddress)(a1, a2, 0);
  v5 = 0;
  SecurityDll = DLpLoadSecurityDll();
  if ( !SecurityDll )
  {
    ProcAddress = GetProcAddress(g_hInstSecurityDLL, "SetSecurityDescriptorOwner");
    qword_180070370 = (__int64)ProcAddress;
    if ( !ProcAddress )
      return v5;
    return ((unsigned int (__fastcall *)(void *, void *, _QWORD))ProcAddress)(a1, a2, 0);
  }
  SetLastError(SecurityDll);
  return v5;
}

```

## disassembly

```asm
0x180043eac  mov     [rsp+arg_0], rbx
0x180043eb1  mov     [rsp+arg_8], rsi
0x180043eb6  push    rdi
0x180043eb7  sub     rsp, 20h
0x180043ebb  mov     rax, cs:qword_180070370
0x180043ec2  mov     rdi, rdx
0x180043ec5  mov     rsi, rcx
0x180043ec8  test    rax, rax
0x180043ecb  jnz     short loc_180043F02
0x180043ecd  xor     ebx, ebx
0x180043ecf  call    ?DLpLoadSecurityDll@@YAKXZ; DLpLoadSecurityDll(void)
0x180043ed4  test    eax, eax
0x180043ed6  jz      short loc_180043EE2
0x180043ed8  mov     ecx, eax; dwErrCode
0x180043eda  call    cs:__imp_SetLastError
0x180043ee0  jmp     short loc_180043F12
0x180043ee2  mov     rcx, cs:?g_hInstSecurityDLL@@3PEAUHINSTANCE__@@EA; hModule
0x180043ee9  lea     rdx, aSetsecuritydes_0; "SetSecurityDescriptorOwner"
0x180043ef0  call    cs:__imp_GetProcAddress
0x180043ef6  mov     cs:qword_180070370, rax
0x180043efd  test    rax, rax
0x180043f00  jz      short loc_180043F12
0x180043f02  xor     r8d, r8d
0x180043f05  mov     rdx, rdi
0x180043f08  mov     rcx, rsi
0x180043f0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043f10  mov     ebx, eax
0x180043f12  mov     rsi, [rsp+28h+arg_8]
0x180043f17  mov     eax, ebx
0x180043f19  mov     rbx, [rsp+28h+arg_0]
0x180043f1e  add     rsp, 20h
0x180043f22  pop     rdi
0x180043f23  retn
```
