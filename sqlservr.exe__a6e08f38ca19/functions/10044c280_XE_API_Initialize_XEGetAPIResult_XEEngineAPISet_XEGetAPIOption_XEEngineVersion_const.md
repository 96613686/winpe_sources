# XE_API::Initialize(XEGetAPIResult (*)(XEEngineAPISet *,XEGetAPIOption),XEEngineVersion const &)

- ea: `0x10044c280`
- end: `0x10044c658`
- name: `?Initialize@XE_API@@SAHP6A?AW4XEGetAPIResult@@PEAUXEEngineAPISet@@W4XEGetAPIOption@@@ZAEBUXEEngineVersion@@@Z`
- size: `984`
- prototype: `__int64 __fastcall(enum XEGetAPIResult (__high *)(struct XEEngineAPISet *, enum XEGetAPIOption), const struct XEEngineVersion *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x100415b60`

## callees

- `0x100401580`
- `0x10044c280`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x10044c3bd`
- `KERNEL32!GetProcAddress` at `0x10044c474`
- `KERNEL32!GetProcAddress` at `0x10044c4b5`
- `KERNEL32!GetProcAddress` at `0x10044c3bd`
- `KERNEL32!GetProcAddress` at `0x10044c474`
- `KERNEL32!GetProcAddress` at `0x10044c4b5`
- `KERNEL32!GetModuleHandleW` at `0x10044c3a5`
- `KERNEL32!GetModuleHandleW` at `0x10044c3a5`
- `KERNEL32!CloseHandle` at `0x10044c49c`
- `KERNEL32!CloseHandle` at `0x10044c49c`
- `KERNEL32!CreateToolhelp32Snapshot` at `0x10044c3dc`
- `KERNEL32!CreateToolhelp32Snapshot` at `0x10044c3dc`
- `KERNEL32!Module32NextW` at `0x10044c3fd`
- `KERNEL32!Module32NextW` at `0x10044c486`
- `KERNEL32!Module32NextW` at `0x10044c3fd`
- `KERNEL32!Module32NextW` at `0x10044c486`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x10044c448`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x10044c45f`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x10044c448`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x10044c45f`

## string_xrefs

- `0x10044c38e`: `sqldk.dll`
- `0x10044c372`: `xe.dll`
- `0x10044c458`: `.dll.patch`

## pseudocode

```c
__int64 __fastcall XE_API::Initialize(
        __int64 (__fastcall *ProcAddress)(int *, __int64),
        const struct XEEngineVersion *a2)
{
  __int64 v2; // rdi
  __int64 v3; // rsi
  __int64 v4; // r14
  int v6; // r8d
  int v7; // ecx
  __int16 v8; // ax
  __int64 v9; // rdx
  LPCWSTR *v10; // rsi
  HMODULE hModule; // r14
  unsigned int i; // edi
  HMODULE ModuleHandleW; // rax
  HMODULE v14; // rbx
  HANDLE Toolhelp32Snapshot; // rax
  void *v16; // rdi
  __int64 v17; // rax
  int v18; // eax
  const wchar_t *v19; // rbx
  __int128 *v20; // rax
  __int128 *v21; // rcx
  __int64 v22; // rdx
  __int64 v23; // r8
  __int128 v24; // xmm0
  __int128 v25; // xmm1
  __int128 *v26; // rax
  _OWORD *v27; // rcx
  __int128 v28; // xmm0
  bool v29; // zf
  int v30; // ett
  __int64 result; // rax
  __int128 *v32; // [rsp+20h] [rbp-E0h] BYREF
  __int128 *v33; // [rsp+28h] [rbp-D8h] BYREF
  __int64 v34; // [rsp+30h] [rbp-D0h] BYREF
  int v35; // [rsp+40h] [rbp-C0h] BYREF
  __int16 v36; // [rsp+44h] [rbp-BCh]
  __int16 v37; // [rsp+46h] [rbp-BAh]
  __int16 v38; // [rsp+48h] [rbp-B8h]
  __int128 **v39; // [rsp+50h] [rbp-B0h]
  __int16 v40; // [rsp+58h] [rbp-A8h]
  __int128 **v41; // [rsp+60h] [rbp-A0h]
  __int16 v42; // [rsp+68h] [rbp-98h]
  __int64 *v43; // [rsp+70h] [rbp-90h]
  MODULEENTRY32W me; // [rsp+80h] [rbp-80h] BYREF
  _QWORD v45[8]; // [rsp+4C0h] [rbp+3C0h] BYREF

  do
  {
    v6 = XE_API::sm_oti;
    v7 = XE_API::sm_oti + 1;
    if ( XE_API::sm_oti >= 0 )
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)&XE_API::sm_oti, v7 | 0x80000000, XE_API::sm_oti);
    _mm_pause();
  }
  while ( v7 != v6 );
  if ( !v7 )
  {
    v36 = *(_WORD *)a2;
    v37 = *((_WORD *)a2 + 1);
    v38 = *((_WORD *)a2 + 2);
    v39 = &v32;
    v40 = *((_WORD *)a2 + 3);
    v41 = &v33;
    v8 = *((_WORD *)a2 + 4);
    v9 = 1;
    v45[6] = v3;
    v42 = v8;
    v45[5] = v2;
    v43 = &v34;
    v45[4] = v4;
    v32 = 0;
    v33 = 0;
    v34 = 0;
    v35 = 56;
    if ( !ProcAddress )
    {
      v45[0] = 0;
      v45[1] = L"xe.dll";
      v10 = (LPCWSTR *)v45;
      hModule = 0;
      v45[2] = L"sqldk.dll";
      for ( i = 0; i < 3; ++i )
      {
        ModuleHandleW = GetModuleHandleW(*v10);
        v14 = ModuleHandleW;
        if ( ModuleHandleW && GetProcAddress(ModuleHandleW, "XEGetEngine") )
          goto LABEL_22;
        ++v10;
      }
      Toolhelp32Snapshot = CreateToolhelp32Snapshot(8u, 0);
      v16 = Toolhelp32Snapshot;
      if ( Toolhelp32Snapshot == (HANDLE)-1LL )
        goto LABEL_30;
      me.dwSize = 1080;
      if ( Module32NextW(Toolhelp32Snapshot, &me) )
      {
        while ( 1 )
        {
          v17 = -1;
          do
            ++v17;
          while ( me.szModule[v17] );
          v18 = v17 - 10;
          if ( v18 <= 0
            || (_mm_lfence(), v19 = &me.szModule[v18], _wcsicmp(L".exe.patch", v19))
            && (_mm_lfence(), _wcsicmp(L".dll.patch", v19)) )
          {
            if ( GetProcAddress(me.hModule, "XEGetEngine") )
              break;
          }
          if ( !Module32NextW(v16, &me) )
            goto LABEL_21;
        }
        hModule = me.hModule;
      }
LABEL_21:
      v14 = hModule;
      CloseHandle(v16);
      if ( !hModule )
LABEL_30:
        JUMPOUT(0x10044C658LL);
LABEL_22:
      ProcAddress = (__int64 (__fastcall *)(int *, __int64))GetProcAddress(v14, "XEGetEngine");
      v9 = 0;
      if ( !ProcAddress )
      {
        XE_API::sm_GetApiResult = 4;
        goto LABEL_30;
      }
    }
    XE_API::sm_GetApiResult = ProcAddress(&v35, v9);
    if ( !XE_API::sm_GetApiResult )
    {
      v20 = v32;
      v21 = (__int128 *)&XE_API::sm_ClientAPI;
      v22 = 4;
      v23 = 4;
      do
      {
        v21 += 8;
        v24 = *v20;
        v20 += 8;
        *(v21 - 8) = v24;
        *(v21 - 7) = *(v20 - 7);
        *(v21 - 6) = *(v20 - 6);
        *(v21 - 5) = *(v20 - 5);
        *(v21 - 4) = *(v20 - 4);
        *(v21 - 3) = *(v20 - 3);
        *(v21 - 2) = *(v20 - 2);
        *(v21 - 1) = *(v20 - 1);
        --v23;
      }
      while ( v23 );
      *v21 = *v20;
      v21[1] = v20[1];
      v21[2] = v20[2];
      v25 = v20[3];
      v26 = v33;
      v21[3] = v25;
      v27 = &XE_API::sm_ServiceAPI;
      do
      {
        v27 += 8;
        v28 = *v26;
        v26 += 8;
        *(v27 - 8) = v28;
        *(v27 - 7) = *(v26 - 7);
        *(v27 - 6) = *(v26 - 6);
        *(v27 - 5) = *(v26 - 5);
        *(v27 - 4) = *(v26 - 4);
        *(v27 - 3) = *(v26 - 3);
        *(v27 - 2) = *(v26 - 2);
        *(v27 - 1) = *(v26 - 1);
        --v22;
      }
      while ( v22 );
      *v27 = *v26;
      v27[1] = v26[1];
      v27[2] = v26[2];
      v27[3] = v26[3];
      v27[4] = v26[4];
      v27[5] = v26[5];
      v27[6] = v26[6];
      *((_QWORD *)v27 + 14) = *((_QWORD *)v26 + 14);
      XE_API::sm_RegistrationAPI = *(_OWORD *)v34;
      xmmword_1004A99E0 = *(_OWORD *)(v34 + 16);
      qword_1004A99F0 = *(_QWORD *)(v34 + 32);
    }
    goto LABEL_30;
  }
  do
  {
    v30 = XE_API::sm_oti;
    v29 = v30 == _InterlockedCompareExchange(
                   (volatile signed __int32 *)&XE_API::sm_oti,
                   XE_API::sm_oti & 0x7FFFFFFF,
                   XE_API::sm_oti);
    _mm_pause();
  }
  while ( !v29 );
  if ( !qword_1004A9518 )
    return 0;
  if ( !qword_1004A9758 )
    return 0;
  result = 1;
  if ( !qword_1004A99D8 )
    return 0;
  return result;
}

```

## disassembly

```asm
0x10044c280  push    rbp
0x10044c282  push    r15
0x10044c284  lea     rbp, [rsp-3F8h]
0x10044c28c  sub     rsp, 4F8h
0x10044c293  mov     rax, cs:__security_cookie
0x10044c29a  xor     rax, rsp
0x10044c29d  mov     [rbp+400h+var_28], rax
0x10044c2a4  mov     r9, rcx
0x10044c2a7  nop     word ptr [rax+rax+00000000h]
0x10044c2b0  mov     r8d, cs:?sm_oti@XE_API@@2VXE_OneTimeInit@@A; XE_OneTimeInit XE_API::sm_oti
0x10044c2b7  lea     ecx, [r8+1]
0x10044c2bb  test    r8d, r8d
0x10044c2be  js      short loc_10044C2D3
0x10044c2c0  or      ecx, 80000000h
0x10044c2c6  mov     eax, r8d
0x10044c2c9  lock cmpxchg cs:?sm_oti@XE_API@@2VXE_OneTimeInit@@A, ecx; XE_OneTimeInit XE_API::sm_oti
0x10044c2d1  mov     ecx, eax
0x10044c2d3  pause
0x10044c2d5  cmp     ecx, r8d
0x10044c2d8  jnz     short loc_10044C2B0
0x10044c2da  xor     r15d, r15d
0x10044c2dd  test    ecx, ecx
0x10044c2df  jnz     loc_10044C660
0x10044c2e5  movzx   eax, word ptr [rdx]
0x10044c2e8  mov     [rsp+500h+var_4BC], ax
0x10044c2ed  movzx   eax, word ptr [rdx+2]
0x10044c2f1  mov     [rsp+500h+var_4BA], ax
0x10044c2f6  movzx   eax, word ptr [rdx+4]
0x10044c2fa  mov     [rsp+500h+var_4B8], ax
0x10044c2ff  lea     rax, [rsp+500h+var_4E0]
0x10044c304  mov     [rsp+500h+var_4B0], rax
0x10044c309  movzx   eax, word ptr [rdx+6]
0x10044c30d  mov     [rsp+500h+var_4A8], ax
0x10044c312  lea     rax, [rsp+500h+var_4D8]
0x10044c317  mov     [rsp+500h+arg_10], rbx
0x10044c31f  mov     [rsp+500h+var_4A0], rax
0x10044c324  movzx   eax, word ptr [rdx+8]
0x10044c328  lea     edx, [rcx+1]
0x10044c32b  mov     [rsp+500h+var_10], rsi
0x10044c333  mov     [rsp+500h+var_498], ax
0x10044c338  lea     rax, [rsp+500h+var_4D0]
0x10044c33d  mov     [rsp+500h+var_18], rdi
0x10044c345  mov     [rsp+500h+var_490], rax
0x10044c34a  mov     [rsp+500h+var_20], r14
0x10044c352  mov     [rsp+500h+var_4E0], r15
0x10044c357  mov     [rsp+500h+var_4D8], r15
0x10044c35c  mov     [rsp+500h+var_4D0], r15
0x10044c361  mov     [rsp+500h+var_4C0], 38h ; '8'
0x10044c369  test    r9, r9
0x10044c36c  jnz     loc_10044C4D6
0x10044c372  lea     rax, aXeDll; "xe.dll"
0x10044c379  mov     [rbp+400h+var_40], r15
0x10044c380  mov     [rbp+400h+var_38], rax
0x10044c387  lea     rsi, [rbp+400h+var_40]
0x10044c38e  lea     rax, aSqldkDll_0; "sqldk.dll"
0x10044c395  mov     r14d, r15d
0x10044c398  mov     [rbp+400h+var_30], rax
0x10044c39f  mov     edi, r15d
0x10044c3a2  mov     rcx, [rsi]; lpModuleName
0x10044c3a5  call    cs:__imp_GetModuleHandleW
0x10044c3ab  mov     rbx, rax
0x10044c3ae  test    rax, rax
0x10044c3b1  jz      short loc_10044C3CC
0x10044c3b3  lea     rdx, aXegetengine; "XEGetEngine"
0x10044c3ba  mov     rcx, rax; hModule
0x10044c3bd  call    cs:__imp_GetProcAddress
0x10044c3c3  test    rax, rax
0x10044c3c6  jnz     loc_10044C4AB
0x10044c3cc  inc     edi
0x10044c3ce  add     rsi, 8
0x10044c3d2  cmp     edi, 3
0x10044c3d5  jb      short loc_10044C3A2
0x10044c3d7  xor     edx, edx; th32ProcessID
0x10044c3d9  lea     ecx, [rdx+8]; dwFlags
0x10044c3dc  call    cs:__imp_CreateToolhelp32Snapshot
0x10044c3e2  mov     rdi, rax
0x10044c3e5  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x10044c3e9  jz      loc_10044C638
0x10044c3ef  lea     rdx, [rbp+400h+me]; lpme
0x10044c3f3  mov     [rbp+400h+me.dwSize], 438h
0x10044c3fa  mov     rcx, rax; hSnapshot
0x10044c3fd  call    cs:__imp_Module32NextW
0x10044c403  test    eax, eax
0x10044c405  jz      loc_10044C496
0x10044c40b  nop     dword ptr [rax+rax]
0x10044c40f  nop
0x10044c410  lea     rcx, [rbp+400h+me.szModule]
0x10044c414  mov     rax, 0FFFFFFFFFFFFFFFFh
0x10044c41b  nop     dword ptr [rax+rax+00h]
0x10044c420  inc     rax
0x10044c423  cmp     [rcx+rax*2], r14w
0x10044c428  jnz     short loc_10044C420
0x10044c42a  sub     eax, 0Ah
0x10044c42d  test    eax, eax
0x10044c42f  jle     short loc_10044C469
0x10044c431  lfence
0x10044c434  cdqe
0x10044c436  lea     rbx, [rbp+400h+me.szModule]
0x10044c43a  lea     rcx, aExePatch; ".exe.patch"
0x10044c441  lea     rbx, [rbx+rax*2]
0x10044c445  mov     rdx, rbx; String2
0x10044c448  call    cs:__imp__wcsicmp
0x10044c44e  test    eax, eax
0x10044c450  jz      short loc_10044C47F
0x10044c452  lfence
0x10044c455  mov     rdx, rbx; String2
0x10044c458  lea     rcx, aDllPatch; ".dll.patch"
0x10044c45f  call    cs:__imp__wcsicmp
0x10044c465  test    eax, eax
0x10044c467  jz      short loc_10044C47F
0x10044c469  mov     rcx, [rbp+400h+me.hModule]; hModule
0x10044c46d  lea     rdx, aXegetengine; "XEGetEngine"
0x10044c474  call    cs:__imp_GetProcAddress
0x10044c47a  test    rax, rax
0x10044c47d  jnz     short loc_10044C492
0x10044c47f  lea     rdx, [rbp+400h+me]; lpme
0x10044c483  mov     rcx, rdi; hSnapshot
0x10044c486  call    cs:__imp_Module32NextW
0x10044c48c  test    eax, eax
0x10044c48e  jnz     short loc_10044C410
0x10044c490  jmp     short loc_10044C496
0x10044c492  mov     r14, [rbp+400h+me.hModule]
0x10044c496  mov     rcx, rdi; hObject
0x10044c499  mov     rbx, r14
0x10044c49c  call    cs:__imp_CloseHandle
0x10044c4a2  test    r14, r14
0x10044c4a5  jz      loc_10044C638
0x10044c4ab  lea     rdx, aXegetengine; "XEGetEngine"
0x10044c4b2  mov     rcx, rbx; hModule
0x10044c4b5  call    cs:__imp_GetProcAddress
0x10044c4bb  mov     r9, rax
0x10044c4be  mov     edx, r15d
0x10044c4c1  test    rax, rax
0x10044c4c4  jnz     short loc_10044C4D6
0x10044c4c6  mov     edx, 4
0x10044c4cb  mov     cs:?sm_GetApiResult@XE_API@@2W4XEGetAPIResult@@A, edx; XEGetAPIResult XE_API::sm_GetApiResult
0x10044c4d1  jmp     loc_10044C638
0x10044c4d6  lea     rcx, [rsp+500h+var_4C0]
0x10044c4db  call    r9
0x10044c4de  mov     cs:?sm_GetApiResult@XE_API@@2W4XEGetAPIResult@@A, eax; XEGetAPIResult XE_API::sm_GetApiResult
0x10044c4e4  test    eax, eax
0x10044c4e6  jnz     loc_10044C638
0x10044c4ec  mov     rax, [rsp+500h+var_4E0]
0x10044c4f1  lea     rcx, ?sm_ClientAPI@XE_API@@2UXEEngineClientAPI@@A; XEEngineClientAPI XE_API::sm_ClientAPI
0x10044c4f8  mov     edx, 4
0x10044c4fd  mov     r8d, edx
0x10044c500  lea     rcx, [rcx+80h]
0x10044c507  movups  xmm0, xmmword ptr [rax]
0x10044c50a  lea     rax, [rax+80h]
0x10044c511  movups  xmmword ptr [rcx-80h], xmm0
0x10044c515  movups  xmm1, xmmword ptr [rax-70h]
0x10044c519  movups  xmmword ptr [rcx-70h], xmm1
0x10044c51d  movups  xmm0, xmmword ptr [rax-60h]
0x10044c521  movups  xmmword ptr [rcx-60h], xmm0
0x10044c525  movups  xmm1, xmmword ptr [rax-50h]
0x10044c529  movups  xmmword ptr [rcx-50h], xmm1
0x10044c52d  movups  xmm0, xmmword ptr [rax-40h]
0x10044c531  movups  xmmword ptr [rcx-40h], xmm0
0x10044c535  movups  xmm1, xmmword ptr [rax-30h]
0x10044c539  movups  xmmword ptr [rcx-30h], xmm1
0x10044c53d  movups  xmm0, xmmword ptr [rax-20h]
0x10044c541  movups  xmmword ptr [rcx-20h], xmm0
0x10044c545  movups  xmm1, xmmword ptr [rax-10h]
0x10044c549  movups  xmmword ptr [rcx-10h], xmm1
0x10044c54d  sub     r8, 1
0x10044c551  jnz     short loc_10044C500
0x10044c553  movups  xmm0, xmmword ptr [rax]
0x10044c556  movups  xmmword ptr [rcx], xmm0
0x10044c559  movups  xmm1, xmmword ptr [rax+10h]
0x10044c55d  movups  xmmword ptr [rcx+10h], xmm1
0x10044c561  movups  xmm0, xmmword ptr [rax+20h]
0x10044c565  movups  xmmword ptr [rcx+20h], xmm0
0x10044c569  movups  xmm1, xmmword ptr [rax+30h]
0x10044c56d  mov     rax, [rsp+500h+var_4D8]
0x10044c572  movups  xmmword ptr [rcx+30h], xmm1
0x10044c576  lea     rcx, ?sm_ServiceAPI@XE_API@@2UXEEngineServicesAPI@@A; XEEngineServicesAPI XE_API::sm_ServiceAPI
0x10044c57d  nop     dword ptr [rax]
0x10044c580  lea     rcx, [rcx+80h]
0x10044c587  movups  xmm0, xmmword ptr [rax]
0x10044c58a  lea     rax, [rax+80h]
0x10044c591  movups  xmmword ptr [rcx-80h], xmm0
0x10044c595  movups  xmm1, xmmword ptr [rax-70h]
0x10044c599  movups  xmmword ptr [rcx-70h], xmm1
0x10044c59d  movups  xmm0, xmmword ptr [rax-60h]
0x10044c5a1  movups  xmmword ptr [rcx-60h], xmm0
0x10044c5a5  movups  xmm1, xmmword ptr [rax-50h]
0x10044c5a9  movups  xmmword ptr [rcx-50h], xmm1
0x10044c5ad  movups  xmm0, xmmword ptr [rax-40h]
0x10044c5b1  movups  xmmword ptr [rcx-40h], xmm0
0x10044c5b5  movups  xmm1, xmmword ptr [rax-30h]
0x10044c5b9  movups  xmmword ptr [rcx-30h], xmm1
0x10044c5bd  movups  xmm0, xmmword ptr [rax-20h]
0x10044c5c1  movups  xmmword ptr [rcx-20h], xmm0
0x10044c5c5  movups  xmm1, xmmword ptr [rax-10h]
0x10044c5c9  movups  xmmword ptr [rcx-10h], xmm1
0x10044c5cd  sub     rdx, 1
0x10044c5d1  jnz     short loc_10044C580
0x10044c5d3  movups  xmm0, xmmword ptr [rax]
0x10044c5d6  movups  xmmword ptr [rcx], xmm0
0x10044c5d9  movups  xmm1, xmmword ptr [rax+10h]
0x10044c5dd  movups  xmmword ptr [rcx+10h], xmm1
0x10044c5e1  movups  xmm0, xmmword ptr [rax+20h]
0x10044c5e5  movups  xmmword ptr [rcx+20h], xmm0
0x10044c5e9  movups  xmm1, xmmword ptr [rax+30h]
0x10044c5ed  movups  xmmword ptr [rcx+30h], xmm1
0x10044c5f1  movups  xmm0, xmmword ptr [rax+40h]
0x10044c5f5  movups  xmmword ptr [rcx+40h], xmm0
0x10044c5f9  movups  xmm1, xmmword ptr [rax+50h]
0x10044c5fd  movups  xmmword ptr [rcx+50h], xmm1
0x10044c601  movups  xmm0, xmmword ptr [rax+60h]
0x10044c605  movups  xmmword ptr [rcx+60h], xmm0
0x10044c609  mov     rax, [rax+70h]
0x10044c60d  mov     [rcx+70h], rax
0x10044c611  mov     rax, [rsp+500h+var_4D0]
0x10044c616  movups  xmm0, xmmword ptr [rax]
0x10044c619  movups  xmmword ptr cs:?sm_RegistrationAPI@XE_API@@2UXEEngineRegisterAPI@@A, xmm0; XEEngineRegisterAPI XE_API::sm_RegistrationAPI
0x10044c620  movups  xmm1, xmmword ptr [rax+10h]
0x10044c624  movups  cs:xmmword_1004A99E0, xmm1
0x10044c62b  movsd   xmm0, qword ptr [rax+20h]
0x10044c630  movsd   cs:qword_1004A99F0, xmm0
0x10044c638  mov     rdi, [rsp+500h+var_18]
0x10044c640  mov     rsi, [rsp+500h+var_10]
0x10044c648  mov     rbx, [rsp+500h+arg_10]
0x10044c650  mov     r14, [rsp+500h+var_20]
0x10044c660  mov     eax, cs:?sm_oti@XE_API@@2VXE_OneTimeInit@@A; XE_OneTimeInit XE_API::sm_oti
0x10044c666  mov     ecx, eax
0x10044c668  btr     ecx, 1Fh
0x10044c66c  lock cmpxchg cs:?sm_oti@XE_API@@2VXE_OneTimeInit@@A, ecx; XE_OneTimeInit XE_API::sm_oti
0x10044c674  pause
0x10044c676  jnz     short loc_10044C660
0x10044c678  cmp     cs:qword_1004A9518, r15
0x10044c67f  jz      short loc_10044C698
0x10044c681  cmp     cs:qword_1004A9758, r15
0x10044c688  jz      short loc_10044C698
0x10044c68a  cmp     cs:qword_1004A99D8, r15
0x10044c691  mov     eax, 1
0x10044c696  jnz     short loc_10044C69B
0x10044c698  mov     eax, r15d
0x10044c69b  mov     rcx, [rbp+400h+var_28]
0x10044c6a2  xor     rcx, rsp; StackCookie
0x10044c6a5  call    __security_check_cookie
0x10044c6aa  add     rsp, 4F8h
0x10044c6b1  pop     r15
0x10044c6b3  pop     rbp
0x10044c6b4  retn
```
