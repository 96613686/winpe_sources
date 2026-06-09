# Registry::GetStr(ushort const *,ushort * *)

- ea: `0x18000f670`
- end: `0x18000f88b`
- name: `?GetStr@Registry@@QEAAHPEBGPEAPEAG@Z`
- size: `539`
- prototype: `__int64 __fastcall(Registry *__hidden this, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x18000eed4`
- `0x180028590`
- `0x18002a710`

## callees

- `0x18000a290`
- `0x18000ab30`
- `0x18000f670`
- `0x1800101cc`
- `0x180047010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f837`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f878`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f837`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f878`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000f821`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000f862`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000f821`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000f862`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18000f791`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18000f7cd`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18000f791`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18000f7cd`

## pseudocode

```c
__int64 __fastcall Registry::GetStr(Registry *this, const unsigned __int16 *a2, unsigned __int16 **a3)
{
  __int64 v4; // rdi
  FARPROC ProcAddress; // rax
  int RegistryDll; // eax
  WCHAR *v9; // rdi
  FARPROC v10; // rax
  __int64 v11; // rsi
  int LastError; // eax
  DWORD v13; // eax
  DWORD v14; // ebx
  WCHAR *v15; // rax
  unsigned __int16 *v16; // rsi
  DWORD v17; // ebx
  unsigned __int16 *v19; // rcx
  WCHAR Dst; // [rsp+80h] [rbp+40h] BYREF
  unsigned int v21; // [rsp+90h] [rbp+50h] BYREF
  int v22; // [rsp+98h] [rbp+58h] BYREF

  *a3 = 0;
  v4 = *((_QWORD *)this + 1);
  v21 = 0;
  v22 = 0;
  if ( !v4 )
    return 1;
  ProcAddress = (FARPROC)qword_1800703F0;
  if ( !qword_1800703F0 )
  {
    RegistryDll = DLpLoadRegistryDll();
    if ( RegistryDll )
      goto LABEL_4;
    ProcAddress = GetProcAddress(g_hInstRegistryDLL, "RegQueryValueExW");
    qword_1800703F0 = (__int64)ProcAddress;
    if ( !ProcAddress )
    {
      RegistryDll = GetLastError();
      goto LABEL_4;
    }
  }
  RegistryDll = ((__int64 (__fastcall *)(__int64, const unsigned __int16 *, _QWORD, int *, _QWORD, unsigned int *))ProcAddress)(
                  v4,
                  a2,
                  0,
                  &v22,
                  0,
                  &v21);
LABEL_4:
  *((_DWORD *)this + 5) = RegistryDll;
  if ( RegistryDll )
    return 1;
  if ( (unsigned int)(v22 - 1) > 1 )
    return 1;
  v21 += 2;
  v9 = (WCHAR *)CWin32DefaultArena::WbemMemAlloc(saturated_mul(v21, 2u));
  if ( !v9 )
    return 1;
  v10 = (FARPROC)qword_1800703F0;
  v11 = *((_QWORD *)this + 1);
  if ( qword_1800703F0 )
    goto LABEL_8;
  LastError = DLpLoadRegistryDll();
  if ( !LastError )
  {
    v10 = GetProcAddress(g_hInstRegistryDLL, "RegQueryValueExW");
    qword_1800703F0 = (__int64)v10;
    if ( v10 )
    {
LABEL_8:
      LastError = ((__int64 (__fastcall *)(__int64, const unsigned __int16 *, _QWORD, int *, WCHAR *, unsigned int *))v10)(
                    v11,
                    a2,
                    0,
                    &v22,
                    v9,
                    &v21);
      goto LABEL_9;
    }
    LastError = GetLastError();
  }
LABEL_9:
  *((_DWORD *)this + 5) = LastError;
  if ( LastError )
    goto LABEL_15;
  v9[(unsigned __int64)v21 >> 1] = 0;
  if ( v22 != 2 )
  {
    v16 = v9;
    goto LABEL_14;
  }
  Dst = 0;
  v13 = ExpandEnvironmentStringsW(v9, &Dst, 1u) + 1;
  if ( v13
    && (v14 = v13 + 1, v15 = (WCHAR *)CWin32DefaultArena::WbemMemAlloc(saturated_mul(v13 + 1, 2u)), (v16 = v15) != 0) )
  {
    v17 = ExpandEnvironmentStringsW(v9, v15, v14);
    CMUILocale::_Free(v9);
    if ( v17 )
    {
LABEL_14:
      *a3 = v16;
      return 0;
    }
    v19 = v16;
  }
  else
  {
LABEL_15:
    v19 = v9;
  }
  CMUILocale::_Free(v19);
  return 1;
}

```

## disassembly

```asm
0x18000f670  push    rbp
0x18000f672  push    rbx
0x18000f673  push    rsi
0x18000f674  push    rdi
0x18000f675  push    r13
0x18000f677  push    r14
0x18000f679  push    r15
0x18000f67b  mov     rbp, rsp
0x18000f67e  sub     rsp, 40h
0x18000f682  mov     qword ptr [r8], 0
0x18000f689  mov     r14, r8
0x18000f68c  mov     rdi, [rcx+8]
0x18000f690  mov     r15, rdx
0x18000f693  mov     [rbp+arg_10], 0
0x18000f69a  mov     rbx, rcx
0x18000f69d  mov     [rbp+arg_18], 0
0x18000f6a4  mov     r13d, 1
0x18000f6aa  test    rdi, rdi
0x18000f6ad  jz      loc_18000F7F4
0x18000f6b3  mov     rax, cs:qword_1800703F0
0x18000f6ba  test    rax, rax
0x18000f6bd  jz      loc_18000F806
0x18000f6c3  lea     rcx, [rbp+arg_10]
0x18000f6c7  xor     r8d, r8d
0x18000f6ca  mov     [rsp+40h+var_18], rcx
0x18000f6cf  lea     r9, [rbp+arg_18]
0x18000f6d3  mov     rcx, rdi
0x18000f6d6  mov     [rsp+40h+var_20], 0
0x18000f6df  mov     rdx, r15
0x18000f6e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f6e7  mov     [rbx+14h], eax
0x18000f6ea  test    eax, eax
0x18000f6ec  jnz     loc_18000F7F4
0x18000f6f2  mov     eax, [rbp+arg_18]
0x18000f6f5  dec     eax
0x18000f6f7  cmp     eax, r13d
0x18000f6fa  ja      loc_18000F7F4
0x18000f700  mov     eax, [rbp+arg_10]
0x18000f703  add     eax, 2
0x18000f706  mov     ecx, eax
0x18000f708  mov     [rbp+arg_10], eax
0x18000f70b  mov     eax, 2
0x18000f710  mul     rcx
0x18000f713  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18000f71a  cmovb   rax, rcx
0x18000f71e  mov     rcx, rax; unsigned __int64
0x18000f721  call    ?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18000f726  mov     rdi, rax
0x18000f729  test    rax, rax
0x18000f72c  jz      loc_18000F7F4
0x18000f732  mov     rax, cs:qword_1800703F0
0x18000f739  mov     rsi, [rbx+8]
0x18000f73d  test    rax, rax
0x18000f740  jz      loc_18000F847
0x18000f746  lea     rcx, [rbp+arg_10]
0x18000f74a  xor     r8d, r8d
0x18000f74d  mov     [rsp+40h+var_18], rcx
0x18000f752  lea     r9, [rbp+arg_18]
0x18000f756  mov     rcx, rsi
0x18000f759  mov     [rsp+40h+var_20], rdi
0x18000f75e  mov     rdx, r15
0x18000f761  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f766  mov     [rbx+14h], eax
0x18000f769  test    eax, eax
0x18000f76b  jnz     short loc_18000F7EC
0x18000f76d  mov     ecx, [rbp+arg_10]
0x18000f770  shr     rcx, 1
0x18000f773  mov     [rdi+rcx*2], ax
0x18000f777  cmp     [rbp+arg_18], 2
0x18000f77b  jnz     loc_18000F842
0x18000f781  xor     ecx, ecx
0x18000f783  lea     rdx, [rbp+Dst]; lpDst
0x18000f787  mov     [rbp+Dst], cx
0x18000f78b  mov     r8d, r13d; nSize
0x18000f78e  mov     rcx, rdi; lpSrc
0x18000f791  call    cs:__imp_ExpandEnvironmentStringsW
0x18000f797  add     eax, r13d
0x18000f79a  jz      short loc_18000F7EC
0x18000f79c  lea     ebx, [rax+1]
0x18000f79f  mov     eax, 2
0x18000f7a4  mov     ecx, ebx
0x18000f7a6  mul     rcx
0x18000f7a9  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18000f7b0  cmovb   rax, rcx
0x18000f7b4  mov     rcx, rax; unsigned __int64
0x18000f7b7  call    ?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18000f7bc  mov     rsi, rax
0x18000f7bf  test    rax, rax
0x18000f7c2  jz      short loc_18000F7EC
0x18000f7c4  mov     r8d, ebx; nSize
0x18000f7c7  mov     rdx, rax; lpDst
0x18000f7ca  mov     rcx, rdi; lpSrc
0x18000f7cd  call    cs:__imp_ExpandEnvironmentStringsW
0x18000f7d3  mov     rcx, rdi; void *
0x18000f7d6  mov     ebx, eax
0x18000f7d8  call    ?_Free@CMUILocale@@SAHPEAX@Z; CMUILocale::_Free(void *)
0x18000f7dd  test    ebx, ebx
0x18000f7df  jz      loc_18000F883
0x18000f7e5  mov     [r14], rsi
0x18000f7e8  xor     eax, eax
0x18000f7ea  jmp     short loc_18000F7F7
0x18000f7ec  mov     rcx, rdi; void *
0x18000f7ef  call    ?_Free@CMUILocale@@SAHPEAX@Z; CMUILocale::_Free(void *)
0x18000f7f4  mov     eax, r13d
0x18000f7f7  add     rsp, 40h
0x18000f7fb  pop     r15
0x18000f7fd  pop     r14
0x18000f7ff  pop     r13
0x18000f801  pop     rdi
0x18000f802  pop     rsi
0x18000f803  pop     rbx
0x18000f804  pop     rbp
0x18000f805  retn
0x18000f806  call    ?DLpLoadRegistryDll@@YAKXZ; DLpLoadRegistryDll(void)
0x18000f80b  test    eax, eax
0x18000f80d  jnz     loc_18000F6E7
0x18000f813  mov     rcx, cs:?g_hInstRegistryDLL@@3PEAUHINSTANCE__@@EA; hModule
0x18000f81a  lea     rdx, aRegqueryvaluee; "RegQueryValueExW"
0x18000f821  call    cs:__imp_GetProcAddress
0x18000f827  mov     cs:qword_1800703F0, rax
0x18000f82e  test    rax, rax
0x18000f831  jnz     loc_18000F6C3
0x18000f837  call    cs:__imp_GetLastError
0x18000f83d  jmp     loc_18000F6E7
0x18000f842  mov     rsi, rdi
0x18000f845  jmp     short loc_18000F7E5
0x18000f847  call    ?DLpLoadRegistryDll@@YAKXZ; DLpLoadRegistryDll(void)
0x18000f84c  test    eax, eax
0x18000f84e  jnz     loc_18000F766
0x18000f854  mov     rcx, cs:?g_hInstRegistryDLL@@3PEAUHINSTANCE__@@EA; hModule
0x18000f85b  lea     rdx, aRegqueryvaluee; "RegQueryValueExW"
0x18000f862  call    cs:__imp_GetProcAddress
0x18000f868  mov     cs:qword_1800703F0, rax
0x18000f86f  test    rax, rax
0x18000f872  jnz     loc_18000F746
0x18000f878  call    cs:__imp_GetLastError
0x18000f87e  jmp     loc_18000F766
0x18000f883  mov     rcx, rsi
0x18000f886  jmp     loc_18000F7EF
```
