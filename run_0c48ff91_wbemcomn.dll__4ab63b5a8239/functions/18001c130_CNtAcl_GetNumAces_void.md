# CNtAcl::GetNumAces(void)

- ea: `0x18001c130`
- end: `0x18001c1d0`
- name: `?GetNumAces@CNtAcl@@QEAAHXZ`
- size: `160`
- prototype: `__int64 __fastcall(CNtAcl *__hidden this)`
- caller_count: `4`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18001a650`
- `0x18001b490`
- `0x18001c030`
- `0x18003b210`

## callees

- `0x18001c130`
- `0x18001d19c`
- `0x180044310`
- `0x180047010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001c1a6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001c1a6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001c1bc`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001c1bc`

## string_xrefs

- `0x18001c1b5`: `GetAclInformation`

## pseudocode

```c
__int64 __fastcall CNtAcl::GetNumAces(CNtAcl *this)
{
  __int64 v1; // rbx
  FARPROC ProcAddress; // rax
  DWORD SecurityDll; // eax
  __int64 v5; // [rsp+30h] [rbp-28h] BYREF
  int v6; // [rsp+38h] [rbp-20h]

  v1 = *(_QWORD *)this;
  if ( !*(_QWORD *)this )
    return 0xFFFFFFFFLL;
  v5 = 0;
  v6 = 0;
  ProcAddress = (FARPROC)qword_1800703A0;
  if ( !qword_1800703A0 )
  {
    SecurityDll = DLpLoadSecurityDll();
    if ( SecurityDll )
    {
      SetLastError(SecurityDll);
      return 0xFFFFFFFFLL;
    }
    ProcAddress = GetProcAddress(g_hInstSecurityDLL, "GetAclInformation");
    qword_1800703A0 = (__int64)ProcAddress;
    if ( !ProcAddress )
      return 0xFFFFFFFFLL;
  }
  if ( ((unsigned int (__fastcall *)(__int64, __int64 *, __int64))ProcAddress)(v1, &v5, 12) )
    return (unsigned int)v5;
  return 0xFFFFFFFFLL;
}

```

## disassembly

```asm
0x18001c130  push    rbx
0x18001c132  sub     rsp, 50h
0x18001c136  mov     rax, cs:__security_cookie
0x18001c13d  xor     rax, rsp
0x18001c140  mov     [rsp+58h+var_18], rax
0x18001c145  mov     rbx, [rcx]
0x18001c148  test    rbx, rbx
0x18001c14b  jz      short loc_18001C196
0x18001c14d  xor     eax, eax
0x18001c14f  mov     [rsp+58h+var_28], rax
0x18001c154  mov     [rsp+58h+var_20], eax
0x18001c158  mov     rax, cs:qword_1800703A0
0x18001c15f  test    rax, rax
0x18001c162  jz      short loc_18001C19B
0x18001c164  mov     r9d, 2
0x18001c16a  lea     rdx, [rsp+58h+var_28]
0x18001c16f  mov     rcx, rbx
0x18001c172  lea     r8d, [r9+0Ah]
0x18001c176  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c17b  test    eax, eax
0x18001c17d  jz      short loc_18001C196
0x18001c17f  mov     eax, dword ptr [rsp+58h+var_28]
0x18001c183  mov     rcx, [rsp+58h+var_18]
0x18001c188  xor     rcx, rsp; StackCookie
0x18001c18b  call    __security_check_cookie
0x18001c190  add     rsp, 50h
0x18001c194  pop     rbx
0x18001c195  retn
0x18001c196  or      eax, 0FFFFFFFFh
0x18001c199  jmp     short loc_18001C183
0x18001c19b  call    ?DLpLoadSecurityDll@@YAKXZ; DLpLoadSecurityDll(void)
0x18001c1a0  test    eax, eax
0x18001c1a2  jz      short loc_18001C1AE
0x18001c1a4  mov     ecx, eax; dwErrCode
0x18001c1a6  call    cs:__imp_SetLastError
0x18001c1ac  jmp     short loc_18001C196
0x18001c1ae  mov     rcx, cs:?g_hInstSecurityDLL@@3PEAUHINSTANCE__@@EA; hModule
0x18001c1b5  lea     rdx, aGetaclinformat; "GetAclInformation"
0x18001c1bc  call    cs:__imp_GetProcAddress
0x18001c1c2  mov     cs:qword_1800703A0, rax
0x18001c1c9  test    rax, rax
0x18001c1cc  jz      short loc_18001C196
0x18001c1ce  jmp     short loc_18001C164
```
