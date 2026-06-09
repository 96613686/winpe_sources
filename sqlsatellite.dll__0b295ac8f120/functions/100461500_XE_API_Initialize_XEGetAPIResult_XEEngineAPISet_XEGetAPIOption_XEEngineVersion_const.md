# XE_API::Initialize(XEGetAPIResult (*)(XEEngineAPISet *,XEGetAPIOption),XEEngineVersion const &)

- ea: `0x100461500`
- end: `0x100461935`
- name: `?Initialize@XE_API@@SAHP6A?AW4XEGetAPIResult@@PEAUXEEngineAPISet@@W4XEGetAPIOption@@@ZAEBUXEEngineVersion@@@Z`
- size: `1077`
- prototype: `__int64 __fastcall(enum XEGetAPIResult (__high *)(struct XEEngineAPISet *, enum XEGetAPIOption), const struct XEEngineVersion *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x100404a00`

## callees

- `0x100461500`
- `0x100486af0`

## import_xrefs

- `KERNEL32!Module32NextW` at `0x10046167d`
- `KERNEL32!Module32NextW` at `0x100461706`
- `KERNEL32!Module32NextW` at `0x10046167d`
- `KERNEL32!Module32NextW` at `0x100461706`
- `KERNEL32!CreateToolhelp32Snapshot` at `0x10046165c`
- `KERNEL32!CreateToolhelp32Snapshot` at `0x10046165c`
- `KERNEL32!GetProcAddress` at `0x10046163d`
- `KERNEL32!GetProcAddress` at `0x1004616f4`
- `KERNEL32!GetProcAddress` at `0x100461735`
- `KERNEL32!GetProcAddress` at `0x10046163d`
- `KERNEL32!GetProcAddress` at `0x1004616f4`
- `KERNEL32!GetProcAddress` at `0x100461735`
- `KERNEL32!GetModuleHandleW` at `0x100461625`
- `KERNEL32!GetModuleHandleW` at `0x100461625`
- `KERNEL32!CloseHandle` at `0x10046171c`
- `KERNEL32!CloseHandle` at `0x10046171c`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1004616c8`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1004616df`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1004616c8`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1004616df`

## string_xrefs

- `0x10046160e`: `sqldk.dll`
- `0x1004615f2`: `xe.dll`
- `0x1004616d8`: `.dll.patch`

## pseudocode

```c
__int64 __fastcall XE_API::Initialize(
        __int64 (__fastcall *ProcAddress)(int *, __int64),
        const struct XEEngineVersion *a2)
{
  int v3; // r8d
  int v4; // ecx
  __int16 v5; // ax
  __int64 v6; // rdx
  LPCWSTR *v7; // rsi
  HMODULE hModule; // r14
  unsigned int v9; // edi
  HMODULE ModuleHandleW; // rax
  HMODULE v11; // rbx
  HANDLE Toolhelp32Snapshot; // rax
  void *v13; // rdi
  __int64 v14; // rax
  int v15; // eax
  const wchar_t *v16; // rbx
  __int128 *v17; // rax
  __int128 *v18; // rcx
  __int64 v19; // rdx
  __int64 v20; // r8
  __int128 v21; // xmm0
  __int128 v22; // xmm1
  __int128 *v23; // rax
  _OWORD *v24; // rcx
  __int128 v25; // xmm0
  bool v26; // zf
  int v27; // ett
  __int64 result; // rax
  __int128 *v29; // [rsp+20h] [rbp-E0h] BYREF
  __int128 *v30; // [rsp+28h] [rbp-D8h] BYREF
  __int64 v31; // [rsp+30h] [rbp-D0h] BYREF
  int v32; // [rsp+40h] [rbp-C0h] BYREF
  __int16 v33; // [rsp+44h] [rbp-BCh]
  __int16 v34; // [rsp+46h] [rbp-BAh]
  __int16 v35; // [rsp+48h] [rbp-B8h]
  __int128 **v36; // [rsp+50h] [rbp-B0h]
  __int16 v37; // [rsp+58h] [rbp-A8h]
  __int128 **v38; // [rsp+60h] [rbp-A0h]
  __int16 v39; // [rsp+68h] [rbp-98h]
  __int64 *v40; // [rsp+70h] [rbp-90h]
  MODULEENTRY32W me; // [rsp+80h] [rbp-80h] BYREF
  _QWORD v42[3]; // [rsp+4C0h] [rbp+3C0h] BYREF

  do
  {
    v3 = XE_API::sm_oti;
    v4 = XE_API::sm_oti + 1;
    if ( XE_API::sm_oti >= 0 )
      v4 = _InterlockedCompareExchange((volatile signed __int32 *)&XE_API::sm_oti, v4 | 0x80000000, XE_API::sm_oti);
    _mm_pause();
  }
  while ( v4 != v3 );
  if ( !v4 )
  {
    v33 = *(_WORD *)a2;
    v34 = *((_WORD *)a2 + 1);
    v35 = *((_WORD *)a2 + 2);
    v36 = &v29;
    v37 = *((_WORD *)a2 + 3);
    v38 = &v30;
    v5 = *((_WORD *)a2 + 4);
    v6 = 1;
    v39 = v5;
    v40 = &v31;
    v29 = 0;
    v30 = 0;
    v31 = 0;
    v32 = 56;
    if ( ProcAddress )
    {
LABEL_24:
      XE_API::sm_GetApiResult = ProcAddress(&v32, v6);
      if ( !XE_API::sm_GetApiResult )
      {
        v17 = v29;
        v18 = (__int128 *)&XE_API::sm_ClientAPI;
        v19 = 4;
        v20 = 4;
        do
        {
          v18 += 8;
          v21 = *v17;
          v17 += 8;
          *(v18 - 8) = v21;
          *(v18 - 7) = *(v17 - 7);
          *(v18 - 6) = *(v17 - 6);
          *(v18 - 5) = *(v17 - 5);
          *(v18 - 4) = *(v17 - 4);
          *(v18 - 3) = *(v17 - 3);
          *(v18 - 2) = *(v17 - 2);
          *(v18 - 1) = *(v17 - 1);
          --v20;
        }
        while ( v20 );
        *v18 = *v17;
        v18[1] = v17[1];
        v18[2] = v17[2];
        v22 = v17[3];
        v23 = v30;
        v18[3] = v22;
        v24 = &XE_API::sm_ServiceAPI;
        do
        {
          v24 += 8;
          v25 = *v23;
          v23 += 8;
          *(v24 - 8) = v25;
          *(v24 - 7) = *(v23 - 7);
          *(v24 - 6) = *(v23 - 6);
          *(v24 - 5) = *(v23 - 5);
          *(v24 - 4) = *(v23 - 4);
          *(v24 - 3) = *(v23 - 3);
          *(v24 - 2) = *(v23 - 2);
          *(v24 - 1) = *(v23 - 1);
          --v19;
        }
        while ( v19 );
        *v24 = *v23;
        v24[1] = v23[1];
        v24[2] = v23[2];
        v24[3] = v23[3];
        v24[4] = v23[4];
        v24[5] = v23[5];
        v24[6] = v23[6];
        *((_QWORD *)v24 + 14) = *((_QWORD *)v23 + 14);
        XE_API::sm_RegistrationAPI = *(_OWORD *)v31;
        xmmword_100516E48 = *(_OWORD *)(v31 + 16);
        qword_100516E58 = *(_QWORD *)(v31 + 32);
      }
    }
    else
    {
      v42[0] = 0;
      v42[1] = L"xe.dll";
      v7 = (LPCWSTR *)v42;
      hModule = 0;
      v42[2] = L"sqldk.dll";
      v9 = 0;
      while ( 1 )
      {
        ModuleHandleW = GetModuleHandleW(*v7);
        v11 = ModuleHandleW;
        if ( ModuleHandleW )
        {
          if ( GetProcAddress(ModuleHandleW, "XEGetEngine") )
            break;
        }
        ++v9;
        ++v7;
        if ( v9 >= 3 )
        {
          Toolhelp32Snapshot = CreateToolhelp32Snapshot(8u, 0);
          v13 = Toolhelp32Snapshot;
          if ( Toolhelp32Snapshot == (HANDLE)-1LL )
            goto LABEL_30;
          me.dwSize = 1080;
          if ( Module32NextW(Toolhelp32Snapshot, &me) )
          {
            while ( 1 )
            {
              v14 = -1;
              do
                ++v14;
              while ( me.szModule[v14] );
              v15 = v14 - 10;
              if ( v15 <= 0
                || (_mm_lfence(), v16 = &me.szModule[v15], _wcsicmp(L".exe.patch", v16))
                && (_mm_lfence(), _wcsicmp(L".dll.patch", v16)) )
              {
                if ( GetProcAddress(me.hModule, "XEGetEngine") )
                  break;
              }
              if ( !Module32NextW(v13, &me) )
                goto LABEL_21;
            }
            hModule = me.hModule;
          }
LABEL_21:
          v11 = hModule;
          CloseHandle(v13);
          if ( !hModule )
            goto LABEL_30;
          break;
        }
      }
      ProcAddress = (__int64 (__fastcall *)(int *, __int64))GetProcAddress(v11, "XEGetEngine");
      v6 = 0;
      if ( ProcAddress )
        goto LABEL_24;
      XE_API::sm_GetApiResult = 4;
    }
  }
  do
  {
LABEL_30:
    v27 = XE_API::sm_oti;
    v26 = v27 == _InterlockedCompareExchange(
                   (volatile signed __int32 *)&XE_API::sm_oti,
                   XE_API::sm_oti & 0x7FFFFFFF,
                   XE_API::sm_oti);
    _mm_pause();
  }
  while ( !v26 );
  if ( !qword_100516E68 )
    return 0;
  if ( !qword_1005170A8 )
    return 0;
  result = 1;
  if ( !qword_100516E40 )
    return 0;
  return result;
}

```

## disassembly

```asm
0x100461500  push    rbp
0x100461502  push    r15
0x100461504  lea     rbp, [rsp-3F8h]
0x10046150c  sub     rsp, 4F8h
0x100461513  mov     rax, cs:__security_cookie
0x10046151a  xor     rax, rsp
0x10046151d  mov     [rbp+400h+var_28], rax
0x100461524  mov     r9, rcx
0x100461527  nop     word ptr [rax+rax+00000000h]
0x100461530  mov     r8d, cs:?sm_oti@XE_API@@2VXE_OneTimeInit@@A; XE_OneTimeInit XE_API::sm_oti
0x100461537  lea     ecx, [r8+1]
0x10046153b  test    r8d, r8d
0x10046153e  js      short loc_100461553
0x100461540  or      ecx, 80000000h
0x100461546  mov     eax, r8d
0x100461549  lock cmpxchg cs:?sm_oti@XE_API@@2VXE_OneTimeInit@@A, ecx; XE_OneTimeInit XE_API::sm_oti
0x100461551  mov     ecx, eax
0x100461553  pause
0x100461555  cmp     ecx, r8d
0x100461558  jnz     short loc_100461530
0x10046155a  xor     r15d, r15d
0x10046155d  test    ecx, ecx
0x10046155f  jnz     loc_1004618E0
0x100461565  movzx   eax, word ptr [rdx]
0x100461568  mov     [rsp+500h+var_4BC], ax
0x10046156d  movzx   eax, word ptr [rdx+2]
0x100461571  mov     [rsp+500h+var_4BA], ax
0x100461576  movzx   eax, word ptr [rdx+4]
0x10046157a  mov     [rsp+500h+var_4B8], ax
0x10046157f  lea     rax, [rsp+500h+var_4E0]
0x100461584  mov     [rsp+500h+var_4B0], rax
0x100461589  movzx   eax, word ptr [rdx+6]
0x10046158d  mov     [rsp+500h+var_4A8], ax
0x100461592  lea     rax, [rsp+500h+var_4D8]
0x100461597  mov     [rsp+500h+arg_10], rbx
0x10046159f  mov     [rsp+500h+var_4A0], rax
0x1004615a4  movzx   eax, word ptr [rdx+8]
0x1004615a8  lea     edx, [rcx+1]
0x1004615ab  mov     [rsp+500h+var_10], rsi
0x1004615b3  mov     [rsp+500h+var_498], ax
0x1004615b8  lea     rax, [rsp+500h+var_4D0]
0x1004615bd  mov     [rsp+500h+var_18], rdi
0x1004615c5  mov     [rsp+500h+var_490], rax
0x1004615ca  mov     [rsp+500h+var_20], r14
0x1004615d2  mov     [rsp+500h+var_4E0], r15
0x1004615d7  mov     [rsp+500h+var_4D8], r15
0x1004615dc  mov     [rsp+500h+var_4D0], r15
0x1004615e1  mov     [rsp+500h+var_4C0], 38h ; '8'
0x1004615e9  test    r9, r9
0x1004615ec  jnz     loc_100461756
0x1004615f2  lea     rax, aXeDll; "xe.dll"
0x1004615f9  mov     [rbp+400h+var_40], r15
0x100461600  mov     [rbp+400h+var_38], rax
0x100461607  lea     rsi, [rbp+400h+var_40]
0x10046160e  lea     rax, aSqldkDll_0; "sqldk.dll"
0x100461615  mov     r14d, r15d
0x100461618  mov     [rbp+400h+var_30], rax
0x10046161f  mov     edi, r15d
0x100461622  mov     rcx, [rsi]; lpModuleName
0x100461625  call    cs:__imp_GetModuleHandleW
0x10046162b  mov     rbx, rax
0x10046162e  test    rax, rax
0x100461631  jz      short loc_10046164C
0x100461633  lea     rdx, ProcName; "XEGetEngine"
0x10046163a  mov     rcx, rax; hModule
0x10046163d  call    cs:__imp_GetProcAddress
0x100461643  test    rax, rax
0x100461646  jnz     loc_10046172B
0x10046164c  inc     edi
0x10046164e  add     rsi, 8
0x100461652  cmp     edi, 3
0x100461655  jb      short loc_100461622
0x100461657  xor     edx, edx; th32ProcessID
0x100461659  lea     ecx, [rdx+8]; dwFlags
0x10046165c  call    cs:__imp_CreateToolhelp32Snapshot
0x100461662  mov     rdi, rax
0x100461665  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x100461669  jz      loc_1004618B8
0x10046166f  lea     rdx, [rbp+400h+me]; lpme
0x100461673  mov     [rbp+400h+me.dwSize], 438h
0x10046167a  mov     rcx, rax; hSnapshot
0x10046167d  call    cs:__imp_Module32NextW
0x100461683  test    eax, eax
0x100461685  jz      loc_100461716
0x10046168b  nop     dword ptr [rax+rax+00h]
0x100461690  lea     rcx, [rbp+400h+me.szModule]
0x100461694  mov     rax, 0FFFFFFFFFFFFFFFFh
0x10046169b  nop     dword ptr [rax+rax+00h]
0x1004616a0  inc     rax
0x1004616a3  cmp     [rcx+rax*2], r14w
0x1004616a8  jnz     short loc_1004616A0
0x1004616aa  sub     eax, 0Ah
0x1004616ad  test    eax, eax
0x1004616af  jle     short loc_1004616E9
0x1004616b1  lfence
0x1004616b4  cdqe
0x1004616b6  lea     rbx, [rbp+400h+me.szModule]
0x1004616ba  lea     rcx, aExePatch; ".exe.patch"
0x1004616c1  lea     rbx, [rbx+rax*2]
0x1004616c5  mov     rdx, rbx; String2
0x1004616c8  call    cs:__imp__wcsicmp
0x1004616ce  test    eax, eax
0x1004616d0  jz      short loc_1004616FF
0x1004616d2  lfence
0x1004616d5  mov     rdx, rbx; String2
0x1004616d8  lea     rcx, aDllPatch; ".dll.patch"
0x1004616df  call    cs:__imp__wcsicmp
0x1004616e5  test    eax, eax
0x1004616e7  jz      short loc_1004616FF
0x1004616e9  mov     rcx, [rbp+400h+me.hModule]; hModule
0x1004616ed  lea     rdx, ProcName; "XEGetEngine"
0x1004616f4  call    cs:__imp_GetProcAddress
0x1004616fa  test    rax, rax
0x1004616fd  jnz     short loc_100461712
0x1004616ff  lea     rdx, [rbp+400h+me]; lpme
0x100461703  mov     rcx, rdi; hSnapshot
0x100461706  call    cs:__imp_Module32NextW
0x10046170c  test    eax, eax
0x10046170e  jnz     short loc_100461690
0x100461710  jmp     short loc_100461716
0x100461712  mov     r14, [rbp+400h+me.hModule]
0x100461716  mov     rcx, rdi; hObject
0x100461719  mov     rbx, r14
0x10046171c  call    cs:__imp_CloseHandle
0x100461722  test    r14, r14
0x100461725  jz      loc_1004618B8
0x10046172b  lea     rdx, ProcName; "XEGetEngine"
0x100461732  mov     rcx, rbx; hModule
0x100461735  call    cs:__imp_GetProcAddress
0x10046173b  mov     r9, rax
0x10046173e  mov     edx, r15d
0x100461741  test    rax, rax
0x100461744  jnz     short loc_100461756
0x100461746  mov     edx, 4
0x10046174b  mov     cs:?sm_GetApiResult@XE_API@@2W4XEGetAPIResult@@A, edx; XEGetAPIResult XE_API::sm_GetApiResult
0x100461751  jmp     loc_1004618B8
0x100461756  lea     rcx, [rsp+500h+var_4C0]
0x10046175b  call    r9
0x10046175e  mov     cs:?sm_GetApiResult@XE_API@@2W4XEGetAPIResult@@A, eax; XEGetAPIResult XE_API::sm_GetApiResult
0x100461764  test    eax, eax
0x100461766  jnz     loc_1004618B8
0x10046176c  mov     rax, [rsp+500h+var_4E0]
0x100461771  lea     rcx, ?sm_ClientAPI@XE_API@@2UXEEngineClientAPI@@A; XEEngineClientAPI XE_API::sm_ClientAPI
0x100461778  mov     edx, 4
0x10046177d  mov     r8d, edx
0x100461780  lea     rcx, [rcx+80h]
0x100461787  movups  xmm0, xmmword ptr [rax]
0x10046178a  lea     rax, [rax+80h]
0x100461791  movups  xmmword ptr [rcx-80h], xmm0
0x100461795  movups  xmm1, xmmword ptr [rax-70h]
0x100461799  movups  xmmword ptr [rcx-70h], xmm1
0x10046179d  movups  xmm0, xmmword ptr [rax-60h]
0x1004617a1  movups  xmmword ptr [rcx-60h], xmm0
0x1004617a5  movups  xmm1, xmmword ptr [rax-50h]
0x1004617a9  movups  xmmword ptr [rcx-50h], xmm1
0x1004617ad  movups  xmm0, xmmword ptr [rax-40h]
0x1004617b1  movups  xmmword ptr [rcx-40h], xmm0
0x1004617b5  movups  xmm1, xmmword ptr [rax-30h]
0x1004617b9  movups  xmmword ptr [rcx-30h], xmm1
0x1004617bd  movups  xmm0, xmmword ptr [rax-20h]
0x1004617c1  movups  xmmword ptr [rcx-20h], xmm0
0x1004617c5  movups  xmm1, xmmword ptr [rax-10h]
0x1004617c9  movups  xmmword ptr [rcx-10h], xmm1
0x1004617cd  sub     r8, 1
0x1004617d1  jnz     short loc_100461780
0x1004617d3  movups  xmm0, xmmword ptr [rax]
0x1004617d6  movups  xmmword ptr [rcx], xmm0
0x1004617d9  movups  xmm1, xmmword ptr [rax+10h]
0x1004617dd  movups  xmmword ptr [rcx+10h], xmm1
0x1004617e1  movups  xmm0, xmmword ptr [rax+20h]
0x1004617e5  movups  xmmword ptr [rcx+20h], xmm0
0x1004617e9  movups  xmm1, xmmword ptr [rax+30h]
0x1004617ed  mov     rax, [rsp+500h+var_4D8]
0x1004617f2  movups  xmmword ptr [rcx+30h], xmm1
0x1004617f6  lea     rcx, ?sm_ServiceAPI@XE_API@@2UXEEngineServicesAPI@@A; XEEngineServicesAPI XE_API::sm_ServiceAPI
0x1004617fd  nop     dword ptr [rax]
0x100461800  lea     rcx, [rcx+80h]
0x100461807  movups  xmm0, xmmword ptr [rax]
0x10046180a  lea     rax, [rax+80h]
0x100461811  movups  xmmword ptr [rcx-80h], xmm0
0x100461815  movups  xmm1, xmmword ptr [rax-70h]
0x100461819  movups  xmmword ptr [rcx-70h], xmm1
0x10046181d  movups  xmm0, xmmword ptr [rax-60h]
0x100461821  movups  xmmword ptr [rcx-60h], xmm0
0x100461825  movups  xmm1, xmmword ptr [rax-50h]
0x100461829  movups  xmmword ptr [rcx-50h], xmm1
0x10046182d  movups  xmm0, xmmword ptr [rax-40h]
0x100461831  movups  xmmword ptr [rcx-40h], xmm0
0x100461835  movups  xmm1, xmmword ptr [rax-30h]
0x100461839  movups  xmmword ptr [rcx-30h], xmm1
0x10046183d  movups  xmm0, xmmword ptr [rax-20h]
0x100461841  movups  xmmword ptr [rcx-20h], xmm0
0x100461845  movups  xmm1, xmmword ptr [rax-10h]
0x100461849  movups  xmmword ptr [rcx-10h], xmm1
0x10046184d  sub     rdx, 1
0x100461851  jnz     short loc_100461800
0x100461853  movups  xmm0, xmmword ptr [rax]
0x100461856  movups  xmmword ptr [rcx], xmm0
0x100461859  movups  xmm1, xmmword ptr [rax+10h]
0x10046185d  movups  xmmword ptr [rcx+10h], xmm1
0x100461861  movups  xmm0, xmmword ptr [rax+20h]
0x100461865  movups  xmmword ptr [rcx+20h], xmm0
0x100461869  movups  xmm1, xmmword ptr [rax+30h]
0x10046186d  movups  xmmword ptr [rcx+30h], xmm1
0x100461871  movups  xmm0, xmmword ptr [rax+40h]
0x100461875  movups  xmmword ptr [rcx+40h], xmm0
0x100461879  movups  xmm1, xmmword ptr [rax+50h]
0x10046187d  movups  xmmword ptr [rcx+50h], xmm1
0x100461881  movups  xmm0, xmmword ptr [rax+60h]
0x100461885  movups  xmmword ptr [rcx+60h], xmm0
0x100461889  mov     rax, [rax+70h]
0x10046188d  mov     [rcx+70h], rax
0x100461891  mov     rax, [rsp+500h+var_4D0]
0x100461896  movups  xmm0, xmmword ptr [rax]
0x100461899  movups  xmmword ptr cs:?sm_RegistrationAPI@XE_API@@2UXEEngineRegisterAPI@@A, xmm0; XEEngineRegisterAPI XE_API::sm_RegistrationAPI
0x1004618a0  movups  xmm1, xmmword ptr [rax+10h]
0x1004618a4  movups  cs:xmmword_100516E48, xmm1
0x1004618ab  movsd   xmm0, qword ptr [rax+20h]
0x1004618b0  movsd   cs:qword_100516E58, xmm0
0x1004618b8  mov     rdi, [rsp+500h+var_18]
0x1004618c0  mov     rsi, [rsp+500h+var_10]
0x1004618c8  mov     rbx, [rsp+500h+arg_10]
0x1004618d0  mov     r14, [rsp+500h+var_20]
0x1004618d8  nop     dword ptr [rax+rax+00000000h]
0x1004618e0  mov     eax, cs:?sm_oti@XE_API@@2VXE_OneTimeInit@@A; XE_OneTimeInit XE_API::sm_oti
0x1004618e6  mov     ecx, eax
0x1004618e8  btr     ecx, 1Fh
0x1004618ec  lock cmpxchg cs:?sm_oti@XE_API@@2VXE_OneTimeInit@@A, ecx; XE_OneTimeInit XE_API::sm_oti
0x1004618f4  pause
0x1004618f6  jnz     short loc_1004618E0
0x1004618f8  cmp     cs:qword_100516E68, r15
0x1004618ff  jz      short loc_100461918
0x100461901  cmp     cs:qword_1005170A8, r15
0x100461908  jz      short loc_100461918
0x10046190a  cmp     cs:qword_100516E40, r15
0x100461911  mov     eax, 1
0x100461916  jnz     short loc_10046191B
0x100461918  mov     eax, r15d
0x10046191b  mov     rcx, [rbp+400h+var_28]
0x100461922  xor     rcx, rsp; StackCookie
0x100461925  call    __security_check_cookie
0x10046192a  add     rsp, 4F8h
0x100461931  pop     r15
0x100461933  pop     rbp
0x100461934  retn
```
