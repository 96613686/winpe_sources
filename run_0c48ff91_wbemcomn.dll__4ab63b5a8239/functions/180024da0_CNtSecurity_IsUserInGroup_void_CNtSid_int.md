# CNtSecurity::IsUserInGroup(void *,CNtSid &,int *)

- ea: `0x180024da0`
- end: `0x180024e40`
- name: `?IsUserInGroup@CNtSecurity@@SAHPEAXAEAVCNtSid@@PEAH@Z`
- size: `160`
- prototype: `__int64 __fastcall(void *, struct CNtSid *, int *)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18001d19c`
- `0x180024da0`
- `0x180047010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180024e16`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180024e16`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180024e2c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180024e2c`

## string_xrefs

- `0x180024e25`: `CheckTokenMembership`

## pseudocode

```c
__int64 __fastcall CNtSecurity::IsUserInGroup(void *a1, struct CNtSid *a2, int *a3)
{
  FARPROC ProcAddress; // rax
  __int64 v6; // rsi
  DWORD SecurityDll; // eax
  int v9; // [rsp+30h] [rbp+8h] BYREF

  *a3 = 0;
  if ( !a1 )
    return 0;
  ProcAddress = (FARPROC)qword_180070320;
  v6 = *(_QWORD *)a2;
  v9 = 0;
  if ( !qword_180070320 )
  {
    SecurityDll = DLpLoadSecurityDll();
    if ( SecurityDll )
    {
      SetLastError(SecurityDll);
      return 0;
    }
    ProcAddress = GetProcAddress(g_hInstSecurityDLL, "CheckTokenMembership");
    qword_180070320 = (__int64)ProcAddress;
    if ( !ProcAddress )
      return 0;
  }
  if ( ((unsigned int (__fastcall *)(void *, __int64, int *))ProcAddress)(a1, v6, &v9) )
  {
    *a3 = v9;
    return 1;
  }
  return 0;
}

```

## disassembly

```asm
0x180024da0  mov     [rsp+arg_8], rbx
0x180024da5  mov     [rsp+arg_10], rsi
0x180024daa  push    rdi
0x180024dab  sub     rsp, 20h
0x180024daf  mov     dword ptr [r8], 0
0x180024db6  mov     rbx, r8
0x180024db9  mov     rdi, rcx
0x180024dbc  test    rcx, rcx
0x180024dbf  jz      short loc_180024E07
0x180024dc1  mov     rax, cs:qword_180070320
0x180024dc8  mov     rsi, [rdx]
0x180024dcb  mov     [rsp+28h+arg_0], 0
0x180024dd3  test    rax, rax
0x180024dd6  jz      short loc_180024E0B
0x180024dd8  lea     r8, [rsp+28h+arg_0]
0x180024ddd  mov     rdx, rsi
0x180024de0  mov     rcx, rdi
0x180024de3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024de8  test    eax, eax
0x180024dea  jz      short loc_180024E07
0x180024dec  mov     eax, [rsp+28h+arg_0]
0x180024df0  mov     [rbx], eax
0x180024df2  mov     eax, 1
0x180024df7  mov     rbx, [rsp+28h+arg_8]
0x180024dfc  mov     rsi, [rsp+28h+arg_10]
0x180024e01  add     rsp, 20h
0x180024e05  pop     rdi
0x180024e06  retn
0x180024e07  xor     eax, eax
0x180024e09  jmp     short loc_180024DF7
0x180024e0b  call    ?DLpLoadSecurityDll@@YAKXZ; DLpLoadSecurityDll(void)
0x180024e10  test    eax, eax
0x180024e12  jz      short loc_180024E1E
0x180024e14  mov     ecx, eax; dwErrCode
0x180024e16  call    cs:__imp_SetLastError
0x180024e1c  jmp     short loc_180024E07
0x180024e1e  mov     rcx, cs:?g_hInstSecurityDLL@@3PEAUHINSTANCE__@@EA; hModule
0x180024e25  lea     rdx, aChecktokenmemb; "CheckTokenMembership"
0x180024e2c  call    cs:__imp_GetProcAddress
0x180024e32  mov     cs:qword_180070320, rax
0x180024e39  test    rax, rax
0x180024e3c  jz      short loc_180024E07
0x180024e3e  jmp     short loc_180024DD8
```
