# XE_API::Initialize(XEGetAPIResult (*)(XEEngineAPISet *,XEGetAPIOption),XEEngineVersion const &)

- ea: `0x100442c50`
- end: `0x100443028`
- name: `?Initialize@XE_API@@SAHP6A?AW4XEGetAPIResult@@PEAUXEEngineAPISet@@W4XEGetAPIOption@@@ZAEBUXEEngineVersion@@@Z`
- size: `984`
- prototype: `__int64 __fastcall(enum XEGetAPIResult (__high *)(struct XEEngineAPISet *, enum XEGetAPIOption), const struct XEEngineVersion *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1005e3c00`

## callees

- `0x100403070`
- `0x100442c50`

## import_xrefs

- `KERNEL32!Module32NextW` at `0x100442dcd`
- `KERNEL32!Module32NextW` at `0x100442e56`
- `KERNEL32!Module32NextW` at `0x100442dcd`
- `KERNEL32!Module32NextW` at `0x100442e56`
- `KERNEL32!GetModuleHandleW` at `0x100442d75`
- `KERNEL32!GetModuleHandleW` at `0x100442d75`
- `KERNEL32!GetProcAddress` at `0x100442d8d`
- `KERNEL32!GetProcAddress` at `0x100442e44`
- `KERNEL32!GetProcAddress` at `0x100442e85`
- `KERNEL32!GetProcAddress` at `0x100442d8d`
- `KERNEL32!GetProcAddress` at `0x100442e44`
- `KERNEL32!GetProcAddress` at `0x100442e85`
- `KERNEL32!CloseHandle` at `0x100442e6c`
- `KERNEL32!CloseHandle` at `0x100442e6c`
- `KERNEL32!CreateToolhelp32Snapshot` at `0x100442dac`
- `KERNEL32!CreateToolhelp32Snapshot` at `0x100442dac`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x100442e18`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x100442e2f`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x100442e18`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x100442e2f`

## string_xrefs

- `0x100442d42`: `xe.dll`
- `0x100442d5e`: `sqldk.dll`
- `0x100442e28`: `.dll.patch`

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
        JUMPOUT(0x100443028LL);
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
      xmmword_100720ED0 = *(_OWORD *)(v34 + 16);
      qword_100720EE0 = *(_QWORD *)(v34 + 32);
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
  if ( !qword_100715148 )
    return 0;
  if ( !qword_100714EC8 )
    return 0;
  result = 1;
  if ( !qword_100720EC8 )
    return 0;
  return result;
}

```

## disassembly

```asm
0x100442c50  push    rbp
0x100442c52  push    r15
0x100442c54  lea     rbp, [rsp-3F8h]
0x100442c5c  sub     rsp, 4F8h
0x100442c63  mov     rax, cs:__security_cookie
0x100442c6a  xor     rax, rsp
0x100442c6d  mov     [rbp+400h+var_28], rax
0x100442c74  mov     r9, rcx
0x100442c77  nop     word ptr [rax+rax+00000000h]
0x100442c80  mov     r8d, cs:?sm_oti@XE_API@@2VXE_OneTimeInit@@A; XE_OneTimeInit XE_API::sm_oti
0x100442c87  lea     ecx, [r8+1]
0x100442c8b  test    r8d, r8d
0x100442c8e  js      short loc_100442CA3
0x100442c90  or      ecx, 80000000h
0x100442c96  mov     eax, r8d
0x100442c99  lock cmpxchg cs:?sm_oti@XE_API@@2VXE_OneTimeInit@@A, ecx; XE_OneTimeInit XE_API::sm_oti
0x100442ca1  mov     ecx, eax
0x100442ca3  pause
0x100442ca5  cmp     ecx, r8d
0x100442ca8  jnz     short loc_100442C80
0x100442caa  xor     r15d, r15d
0x100442cad  test    ecx, ecx
0x100442caf  jnz     loc_100443030
0x100442cb5  movzx   eax, word ptr [rdx]
0x100442cb8  mov     [rsp+500h+var_4BC], ax
0x100442cbd  movzx   eax, word ptr [rdx+2]
0x100442cc1  mov     [rsp+500h+var_4BA], ax
0x100442cc6  movzx   eax, word ptr [rdx+4]
0x100442cca  mov     [rsp+500h+var_4B8], ax
0x100442ccf  lea     rax, [rsp+500h+var_4E0]
0x100442cd4  mov     [rsp+500h+var_4B0], rax
0x100442cd9  movzx   eax, word ptr [rdx+6]
0x100442cdd  mov     [rsp+500h+var_4A8], ax
0x100442ce2  lea     rax, [rsp+500h+var_4D8]
0x100442ce7  mov     [rsp+500h+arg_10], rbx
0x100442cef  mov     [rsp+500h+var_4A0], rax
0x100442cf4  movzx   eax, word ptr [rdx+8]
0x100442cf8  lea     edx, [rcx+1]
0x100442cfb  mov     [rsp+500h+var_10], rsi
0x100442d03  mov     [rsp+500h+var_498], ax
0x100442d08  lea     rax, [rsp+500h+var_4D0]
0x100442d0d  mov     [rsp+500h+var_18], rdi
0x100442d15  mov     [rsp+500h+var_490], rax
0x100442d1a  mov     [rsp+500h+var_20], r14
0x100442d22  mov     [rsp+500h+var_4E0], r15
0x100442d27  mov     [rsp+500h+var_4D8], r15
0x100442d2c  mov     [rsp+500h+var_4D0], r15
0x100442d31  mov     [rsp+500h+var_4C0], 38h ; '8'
0x100442d39  test    r9, r9
0x100442d3c  jnz     loc_100442EA6
0x100442d42  lea     rax, aXeDll; "xe.dll"
0x100442d49  mov     [rbp+400h+var_40], r15
0x100442d50  mov     [rbp+400h+var_38], rax
0x100442d57  lea     rsi, [rbp+400h+var_40]
0x100442d5e  lea     rax, aSqldkDll_0; "sqldk.dll"
0x100442d65  mov     r14d, r15d
0x100442d68  mov     [rbp+400h+var_30], rax
0x100442d6f  mov     edi, r15d
0x100442d72  mov     rcx, [rsi]; lpModuleName
0x100442d75  call    cs:__imp_GetModuleHandleW
0x100442d7b  mov     rbx, rax
0x100442d7e  test    rax, rax
0x100442d81  jz      short loc_100442D9C
0x100442d83  lea     rdx, ProcName; "XEGetEngine"
0x100442d8a  mov     rcx, rax; hModule
0x100442d8d  call    cs:__imp_GetProcAddress
0x100442d93  test    rax, rax
0x100442d96  jnz     loc_100442E7B
0x100442d9c  inc     edi
0x100442d9e  add     rsi, 8
0x100442da2  cmp     edi, 3
0x100442da5  jb      short loc_100442D72
0x100442da7  xor     edx, edx; th32ProcessID
0x100442da9  lea     ecx, [rdx+8]; dwFlags
0x100442dac  call    cs:__imp_CreateToolhelp32Snapshot
0x100442db2  mov     rdi, rax
0x100442db5  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x100442db9  jz      loc_100443008
0x100442dbf  lea     rdx, [rbp+400h+me]; lpme
0x100442dc3  mov     [rbp+400h+me.dwSize], 438h
0x100442dca  mov     rcx, rax; hSnapshot
0x100442dcd  call    cs:__imp_Module32NextW
0x100442dd3  test    eax, eax
0x100442dd5  jz      loc_100442E66
0x100442ddb  nop     dword ptr [rax+rax]
0x100442ddf  nop
0x100442de0  lea     rcx, [rbp+400h+me.szModule]
0x100442de4  mov     rax, 0FFFFFFFFFFFFFFFFh
0x100442deb  nop     dword ptr [rax+rax+00h]
0x100442df0  inc     rax
0x100442df3  cmp     [rcx+rax*2], r14w
0x100442df8  jnz     short loc_100442DF0
0x100442dfa  sub     eax, 0Ah
0x100442dfd  test    eax, eax
0x100442dff  jle     short loc_100442E39
0x100442e01  lfence
0x100442e04  cdqe
0x100442e06  lea     rbx, [rbp+400h+me.szModule]
0x100442e0a  lea     rcx, aExePatch; ".exe.patch"
0x100442e11  lea     rbx, [rbx+rax*2]
0x100442e15  mov     rdx, rbx; String2
0x100442e18  call    cs:__imp__wcsicmp
0x100442e1e  test    eax, eax
0x100442e20  jz      short loc_100442E4F
0x100442e22  lfence
0x100442e25  mov     rdx, rbx; String2
0x100442e28  lea     rcx, aDllPatch; ".dll.patch"
0x100442e2f  call    cs:__imp__wcsicmp
0x100442e35  test    eax, eax
0x100442e37  jz      short loc_100442E4F
0x100442e39  mov     rcx, [rbp+400h+me.hModule]; hModule
0x100442e3d  lea     rdx, ProcName; "XEGetEngine"
0x100442e44  call    cs:__imp_GetProcAddress
0x100442e4a  test    rax, rax
0x100442e4d  jnz     short loc_100442E62
0x100442e4f  lea     rdx, [rbp+400h+me]; lpme
0x100442e53  mov     rcx, rdi; hSnapshot
0x100442e56  call    cs:__imp_Module32NextW
0x100442e5c  test    eax, eax
0x100442e5e  jnz     short loc_100442DE0
0x100442e60  jmp     short loc_100442E66
0x100442e62  mov     r14, [rbp+400h+me.hModule]
0x100442e66  mov     rcx, rdi; hObject
0x100442e69  mov     rbx, r14
0x100442e6c  call    cs:__imp_CloseHandle
0x100442e72  test    r14, r14
0x100442e75  jz      loc_100443008
0x100442e7b  lea     rdx, ProcName; "XEGetEngine"
0x100442e82  mov     rcx, rbx; hModule
0x100442e85  call    cs:__imp_GetProcAddress
0x100442e8b  mov     r9, rax
0x100442e8e  mov     edx, r15d
0x100442e91  test    rax, rax
0x100442e94  jnz     short loc_100442EA6
0x100442e96  mov     edx, 4
0x100442e9b  mov     cs:?sm_GetApiResult@XE_API@@2W4XEGetAPIResult@@A, edx; XEGetAPIResult XE_API::sm_GetApiResult
0x100442ea1  jmp     loc_100443008
0x100442ea6  lea     rcx, [rsp+500h+var_4C0]
0x100442eab  call    r9
0x100442eae  mov     cs:?sm_GetApiResult@XE_API@@2W4XEGetAPIResult@@A, eax; XEGetAPIResult XE_API::sm_GetApiResult
0x100442eb4  test    eax, eax
0x100442eb6  jnz     loc_100443008
0x100442ebc  mov     rax, [rsp+500h+var_4E0]
0x100442ec1  lea     rcx, ?sm_ClientAPI@XE_API@@2UXEEngineClientAPI@@A; XEEngineClientAPI XE_API::sm_ClientAPI
0x100442ec8  mov     edx, 4
0x100442ecd  mov     r8d, edx
0x100442ed0  lea     rcx, [rcx+80h]
0x100442ed7  movups  xmm0, xmmword ptr [rax]
0x100442eda  lea     rax, [rax+80h]
0x100442ee1  movups  xmmword ptr [rcx-80h], xmm0
0x100442ee5  movups  xmm1, xmmword ptr [rax-70h]
0x100442ee9  movups  xmmword ptr [rcx-70h], xmm1
0x100442eed  movups  xmm0, xmmword ptr [rax-60h]
0x100442ef1  movups  xmmword ptr [rcx-60h], xmm0
0x100442ef5  movups  xmm1, xmmword ptr [rax-50h]
0x100442ef9  movups  xmmword ptr [rcx-50h], xmm1
0x100442efd  movups  xmm0, xmmword ptr [rax-40h]
0x100442f01  movups  xmmword ptr [rcx-40h], xmm0
0x100442f05  movups  xmm1, xmmword ptr [rax-30h]
0x100442f09  movups  xmmword ptr [rcx-30h], xmm1
0x100442f0d  movups  xmm0, xmmword ptr [rax-20h]
0x100442f11  movups  xmmword ptr [rcx-20h], xmm0
0x100442f15  movups  xmm1, xmmword ptr [rax-10h]
0x100442f19  movups  xmmword ptr [rcx-10h], xmm1
0x100442f1d  sub     r8, 1
0x100442f21  jnz     short loc_100442ED0
0x100442f23  movups  xmm0, xmmword ptr [rax]
0x100442f26  movups  xmmword ptr [rcx], xmm0
0x100442f29  movups  xmm1, xmmword ptr [rax+10h]
0x100442f2d  movups  xmmword ptr [rcx+10h], xmm1
0x100442f31  movups  xmm0, xmmword ptr [rax+20h]
0x100442f35  movups  xmmword ptr [rcx+20h], xmm0
0x100442f39  movups  xmm1, xmmword ptr [rax+30h]
0x100442f3d  mov     rax, [rsp+500h+var_4D8]
0x100442f42  movups  xmmword ptr [rcx+30h], xmm1
0x100442f46  lea     rcx, ?sm_ServiceAPI@XE_API@@2UXEEngineServicesAPI@@A; XEEngineServicesAPI XE_API::sm_ServiceAPI
0x100442f4d  nop     dword ptr [rax]
0x100442f50  lea     rcx, [rcx+80h]
0x100442f57  movups  xmm0, xmmword ptr [rax]
0x100442f5a  lea     rax, [rax+80h]
0x100442f61  movups  xmmword ptr [rcx-80h], xmm0
0x100442f65  movups  xmm1, xmmword ptr [rax-70h]
0x100442f69  movups  xmmword ptr [rcx-70h], xmm1
0x100442f6d  movups  xmm0, xmmword ptr [rax-60h]
0x100442f71  movups  xmmword ptr [rcx-60h], xmm0
0x100442f75  movups  xmm1, xmmword ptr [rax-50h]
0x100442f79  movups  xmmword ptr [rcx-50h], xmm1
0x100442f7d  movups  xmm0, xmmword ptr [rax-40h]
0x100442f81  movups  xmmword ptr [rcx-40h], xmm0
0x100442f85  movups  xmm1, xmmword ptr [rax-30h]
0x100442f89  movups  xmmword ptr [rcx-30h], xmm1
0x100442f8d  movups  xmm0, xmmword ptr [rax-20h]
0x100442f91  movups  xmmword ptr [rcx-20h], xmm0
0x100442f95  movups  xmm1, xmmword ptr [rax-10h]
0x100442f99  movups  xmmword ptr [rcx-10h], xmm1
0x100442f9d  sub     rdx, 1
0x100442fa1  jnz     short loc_100442F50
0x100442fa3  movups  xmm0, xmmword ptr [rax]
0x100442fa6  movups  xmmword ptr [rcx], xmm0
0x100442fa9  movups  xmm1, xmmword ptr [rax+10h]
0x100442fad  movups  xmmword ptr [rcx+10h], xmm1
0x100442fb1  movups  xmm0, xmmword ptr [rax+20h]
0x100442fb5  movups  xmmword ptr [rcx+20h], xmm0
0x100442fb9  movups  xmm1, xmmword ptr [rax+30h]
0x100442fbd  movups  xmmword ptr [rcx+30h], xmm1
0x100442fc1  movups  xmm0, xmmword ptr [rax+40h]
0x100442fc5  movups  xmmword ptr [rcx+40h], xmm0
0x100442fc9  movups  xmm1, xmmword ptr [rax+50h]
0x100442fcd  movups  xmmword ptr [rcx+50h], xmm1
0x100442fd1  movups  xmm0, xmmword ptr [rax+60h]
0x100442fd5  movups  xmmword ptr [rcx+60h], xmm0
0x100442fd9  mov     rax, [rax+70h]
0x100442fdd  mov     [rcx+70h], rax
0x100442fe1  mov     rax, [rsp+500h+var_4D0]
0x100442fe6  movups  xmm0, xmmword ptr [rax]
0x100442fe9  movups  xmmword ptr cs:?sm_RegistrationAPI@XE_API@@2UXEEngineRegisterAPI@@A, xmm0; XEEngineRegisterAPI XE_API::sm_RegistrationAPI
0x100442ff0  movups  xmm1, xmmword ptr [rax+10h]
0x100442ff4  movups  cs:xmmword_100720ED0, xmm1
0x100442ffb  movsd   xmm0, qword ptr [rax+20h]
0x100443000  movsd   cs:qword_100720EE0, xmm0
0x100443008  mov     rdi, [rsp+500h+var_18]
0x100443010  mov     rsi, [rsp+500h+var_10]
0x100443018  mov     rbx, [rsp+500h+arg_10]
0x100443020  mov     r14, [rsp+500h+var_20]
0x100443030  mov     eax, cs:?sm_oti@XE_API@@2VXE_OneTimeInit@@A; XE_OneTimeInit XE_API::sm_oti
0x100443036  mov     ecx, eax
0x100443038  btr     ecx, 1Fh
0x10044303c  lock cmpxchg cs:?sm_oti@XE_API@@2VXE_OneTimeInit@@A, ecx; XE_OneTimeInit XE_API::sm_oti
0x100443044  pause
0x100443046  jnz     short loc_100443030
0x100443048  cmp     cs:qword_100715148, r15
0x10044304f  jz      short loc_100443068
0x100443051  cmp     cs:qword_100714EC8, r15
0x100443058  jz      short loc_100443068
0x10044305a  cmp     cs:qword_100720EC8, r15
0x100443061  mov     eax, 1
0x100443066  jnz     short loc_10044306B
0x100443068  mov     eax, r15d
0x10044306b  mov     rcx, [rbp+400h+var_28]
0x100443072  xor     rcx, rsp; StackCookie
0x100443075  call    __security_check_cookie
0x10044307a  add     rsp, 4F8h
0x100443081  pop     r15
0x100443083  pop     rbp
0x100443084  retn
```
