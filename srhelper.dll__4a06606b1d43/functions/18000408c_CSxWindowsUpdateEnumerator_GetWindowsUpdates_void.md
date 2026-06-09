# CSxWindowsUpdateEnumerator::GetWindowsUpdates(void)

- ea: `0x18000408c`
- end: `0x1800044a5`
- name: `?GetWindowsUpdates@CSxWindowsUpdateEnumerator@@QEAAJXZ`
- size: `1049`
- prototype: `__int64 __fastcall(const unsigned __int16 **this)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x18000cc20`

## callees

- `0x180003ce0`
- `0x18000408c`
- `0x180004e20`
- `0x1800050dc`
- `0x180005478`
- `0x1800055a4`
- `0x180005c6c`
- `0x18000d348`
- `0x18000d43c`
- `0x180016010`

## import_xrefs

- `KERNEL32!GetSystemTimeAsFileTime` at `0x180004140`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1800043d0`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180004140`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1800043d0`
- `ole32!CoCreateInstance` at `0x180004163`
- `ole32!CoCreateInstance` at `0x180004163`
- `ole32!CoTaskMemFree` at `0x1800042d1`
- `ole32!CoTaskMemFree` at `0x180004410`
- `ole32!CoTaskMemFree` at `0x1800042d1`
- `ole32!CoTaskMemFree` at `0x180004410`

## string_xrefs

- `0x1800040df`: `CSxWindowsUpdateEnumerator::GetWindowsUpdates`

## pseudocode

```c
__int64 __fastcall CSxWindowsUpdateEnumerator::GetWindowsUpdates(const unsigned __int16 **this)
{
  __int16 v2; // ax
  const unsigned __int16 *v3; // r8
  int v4; // ecx
  int v5; // eax
  struct ICbsPackage *v6; // rcx
  __int64 v7; // rcx
  __int64 v8; // rcx
  LPVOID v9; // rcx
  __int64 v10; // rdx
  __int64 v11; // r8
  unsigned int v12; // ebx
  struct ICbsPackage *v14; // [rsp+30h] [rbp-59h] BYREF
  __int64 v15; // [rsp+38h] [rbp-51h] BYREF
  __int64 v16; // [rsp+40h] [rbp-49h] BYREF
  HRESULT CBSHives; // [rsp+48h] [rbp-41h] BYREF
  __int16 v18; // [rsp+4Ch] [rbp-3Dh]
  __int16 v19; // [rsp+4Eh] [rbp-3Bh]
  __int64 v20; // [rsp+80h] [rbp-9h] BYREF
  struct _FILETIME SystemTimeAsFileTime[2]; // [rsp+88h] [rbp-1h] BYREF
  int v22; // [rsp+F0h] [rbp+67h] BYREF
  int v23; // [rsp+F8h] [rbp+6Fh] BYREF
  LPVOID ppv; // [rsp+100h] [rbp+77h] BYREF
  LPVOID pv; // [rsp+108h] [rbp+7Fh] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_012e94a410f034635dd5ee797f3d6253_Traceguids);
  CSxFunctionTracer::CSxFunctionTracer(
    (CSxFunctionTracer *)&CBSHives,
    "CSxWindowsUpdateEnumerator::GetWindowsUpdates",
    584);
  ppv = 0;
  v20 = 0;
  v15 = 0;
  v14 = 0;
  v16 = 0;
  v22 = 0;
  pv = 0;
  SystemTimeAsFileTime[0] = 0;
  SystemTimeAsFileTime[1] = 0;
  if ( *((_DWORD *)this + 8) )
  {
    CBSHives = CSxWindowsUpdateEnumerator::_LoadCBSHives((CSxWindowsUpdateEnumerator *)this);
    v2 = 598;
    if ( CBSHives < 0 )
    {
LABEL_6:
      v19 = v2;
      goto LABEL_38;
    }
    v18 = 598;
  }
  GetSystemTimeAsFileTime(SystemTimeAsFileTime);
  CBSHives = CoCreateInstance(&CLSID_CbsSession, 0, 0x15u, &GUID_75207391_23f2_4396_85f0_8fdb879ed0ed, &ppv);
  v2 = 603;
  if ( CBSHives < 0 )
    goto LABEL_6;
  v3 = this[2];
  v18 = 603;
  CBSHives = (*(__int64 (__fastcall **)(LPVOID, __int64, const wchar_t *, unsigned __int64, const unsigned __int16 *))(*(_QWORD *)ppv + 24LL))(
               ppv,
               48,
               L"SPP",
               (unsigned __int64)L"T:" & -(__int64)(v3 != 0),
               v3);
  v2 = 612;
  if ( CBSHives < 0 )
    goto LABEL_6;
  v18 = 612;
  CBSHives = (*(__int64 (__fastcall **)(LPVOID, __int64, __int64 *))(*(_QWORD *)ppv + 56LL))(ppv, 16, &v20);
  v2 = 614;
  if ( CBSHives < 0 )
    goto LABEL_6;
  v18 = 614;
  v4 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *, int *))(*(_QWORD *)v20 + 24LL))(v20, 1, &v15, &v22);
  CBSHives = v4;
  v2 = 616;
  if ( v4 < 0 )
    goto LABEL_6;
  v18 = 616;
  while ( !v4 && v22 )
  {
    v23 = 0;
    CBSHives = (*(__int64 (__fastcall **)(LPVOID, _QWORD, __int64, _QWORD, __int64 *))(*(_QWORD *)ppv + 48LL))(
                 ppv,
                 0,
                 v15,
                 0,
                 &v16);
    v2 = 622;
    if ( CBSHives < 0 )
      goto LABEL_6;
    v18 = 622;
    CBSHives = (**(__int64 (__fastcall ***)(__int64, GUID *, struct ICbsPackage **))v16)(
                 v16,
                 &GUID_75207393_23f2_4396_85f0_8fdb879ed0ed,
                 &v14);
    if ( CBSHives < 0 )
    {
      v19 = 624;
      goto LABEL_38;
    }
    v18 = 624;
    CBSHives = CSxWindowsUpdateEnumerator::_IsWindowsUpdatePackage(v14, &v23);
    if ( CBSHives < 0 )
    {
      v19 = 626;
      goto LABEL_38;
    }
    v18 = 626;
    if ( v23 )
    {
      CoTaskMemFree(pv);
      pv = 0;
      CBSHives = CSxWindowsUpdateEnumerator::_GetPackageDisplayName(v14, (unsigned __int16 **)&pv);
      if ( CBSHives < 0 )
      {
        v19 = 634;
        goto LABEL_38;
      }
      v18 = 634;
      if ( pv )
      {
        v5 = ((__int64 (__fastcall *)(const unsigned __int16 *, __int64))this[5])(this[6], 2);
        CBSHives = v5;
        if ( v5 < 0 )
          goto LABEL_32;
        v18 = 641;
        if ( v5 == 1 )
        {
          CBSHives = -2147467260;
LABEL_32:
          v19 = 641;
          goto LABEL_38;
        }
      }
    }
    v6 = v14;
    if ( v14 )
    {
      v14 = 0;
      (*(void (__fastcall **)(struct ICbsPackage *))(*(_QWORD *)v6 + 16LL))(v6);
    }
    v7 = v16;
    if ( v16 )
    {
      v16 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
    }
    v8 = v15;
    if ( v15 )
    {
      v15 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
    }
    CBSHives = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *, int *))(*(_QWORD *)v20 + 24LL))(
                 v20,
                 1,
                 &v15,
                 &v22);
    v4 = CBSHives;
    if ( CBSHives < 0 )
    {
      v19 = 650;
      goto LABEL_38;
    }
    v18 = 650;
  }
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime[1]);
  xmmword_18001D980 = *(_OWORD *)&SystemTimeAsFileTime[0].dwLowDateTime;
LABEL_38:
  v9 = ppv;
  if ( ppv )
  {
    ppv = 0;
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v9 + 16LL))(v9);
  }
  CSxWindowsUpdateEnumerator::_UnloadCBSHives((CSxWindowsUpdateEnumerator *)this);
  CSxWindowsUpdateEnumerator::_CleanupOldHives(this[1]);
  CoTaskMemFree(pv);
  pv = 0;
  v12 = CBSHives;
  if ( v16 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
  if ( v14 )
    (*(void (__fastcall **)(struct ICbsPackage *))(*(_QWORD *)v14 + 16LL))(v14);
  if ( v15 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
  if ( v20 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&CBSHives, v10, v11);
  return v12;
}

```

## disassembly

```asm
0x18000408c  push    rbp
0x18000408e  push    rbx
0x18000408f  push    rsi
0x180004090  push    rdi
0x180004091  push    r12
0x180004093  push    r13
0x180004095  push    r14
0x180004097  push    r15
0x180004099  lea     rbp, [rsp-1Fh]
0x18000409e  sub     rsp, 0A8h
0x1800040a5  mov     rbx, rcx
0x1800040a8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800040af  lea     rax, WPP_GLOBAL_Control
0x1800040b6  cmp     rcx, rax
0x1800040b9  jz      short loc_1800040D9
0x1800040bb  test    dword ptr [rcx+1Ch], 20000000h
0x1800040c2  jz      short loc_1800040D9
0x1800040c4  mov     rcx, [rcx+10h]
0x1800040c8  lea     r8, WPP_012e94a410f034635dd5ee797f3d6253_Traceguids
0x1800040cf  mov     edx, 13h
0x1800040d4  call    WPP_SF_
0x1800040d9  mov     r8d, 248h; unsigned __int16
0x1800040df  lea     rdx, aCsxwindowsupda_0; "CSxWindowsUpdateEnumerator::GetWindowsU"...
0x1800040e6  lea     rcx, [rbp+57h+var_98]; this
0x1800040ea  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x1800040ef  xor     edi, edi
0x1800040f1  xor     eax, eax
0x1800040f3  mov     [rbp+57h+arg_10], rdi
0x1800040f7  mov     [rbp+57h+var_60], rdi
0x1800040fb  mov     [rbp+57h+var_A8], rdi
0x1800040ff  mov     [rbp+57h+var_B0], rdi
0x180004103  mov     [rbp+57h+var_A0], rdi
0x180004107  mov     [rbp+57h+arg_0], edi
0x18000410a  mov     [rbp+57h+pv], rdi
0x18000410e  mov     qword ptr [rbp+57h+SystemTimeAsFileTime.dwLowDateTime], rdi
0x180004112  mov     qword ptr [rbp+57h+SystemTimeAsFileTime.dwLowDateTime+8], rax
0x180004116  cmp     [rbx+20h], edi
0x180004119  jz      short loc_18000413C
0x18000411b  mov     rcx, rbx; this
0x18000411e  call    ?_LoadCBSHives@CSxWindowsUpdateEnumerator@@AEAAJXZ; CSxWindowsUpdateEnumerator::_LoadCBSHives(void)
0x180004123  mov     [rbp+57h+var_98], eax
0x180004126  test    eax, eax
0x180004128  mov     eax, 256h
0x18000412d  jns     short loc_180004138
0x18000412f  mov     [rbp+57h+var_92], ax
0x180004133  jmp     loc_1800043E2
0x180004138  mov     [rbp+57h+var_94], ax
0x18000413c  lea     rcx, [rbp+57h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180004140  call    cs:__imp_GetSystemTimeAsFileTime
0x180004146  xor     edx, edx; pUnkOuter
0x180004148  lea     rax, [rbp+57h+arg_10]
0x18000414c  lea     r9, _GUID_75207391_23f2_4396_85f0_8fdb879ed0ed; riid
0x180004153  mov     [rsp+0E0h+ppv], rax; ppv
0x180004158  lea     rcx, CLSID_CbsSession; rclsid
0x18000415f  lea     r8d, [rdx+15h]; dwClsContext
0x180004163  call    cs:__imp_CoCreateInstance
0x180004169  mov     [rbp+57h+var_98], eax
0x18000416c  test    eax, eax
0x18000416e  mov     eax, 25Bh
0x180004173  js      short loc_18000412F
0x180004175  mov     r8, [rbx+10h]
0x180004179  lea     r10, aT; "T:"
0x180004180  mov     rcx, [rbp+57h+arg_10]
0x180004184  mov     [rbp+57h+var_94], ax
0x180004188  mov     rax, r8
0x18000418b  neg     rax
0x18000418e  mov     [rsp+0E0h+ppv], r8
0x180004193  lea     r8, aSpp; "SPP"
0x18000419a  mov     rdx, [rcx]
0x18000419d  sbb     r9, r9
0x1800041a0  and     r9, r10
0x1800041a3  mov     rax, [rdx+18h]
0x1800041a7  mov     edx, 30h ; '0'
0x1800041ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800041b1  mov     [rbp+57h+var_98], eax
0x1800041b4  test    eax, eax
0x1800041b6  mov     eax, 264h
0x1800041bb  js      loc_18000412F
0x1800041c1  mov     rcx, [rbp+57h+arg_10]
0x1800041c5  lea     r8, [rbp+57h+var_60]
0x1800041c9  mov     [rbp+57h+var_94], ax
0x1800041cd  mov     edx, 10h
0x1800041d2  mov     rax, [rcx]
0x1800041d5  mov     rax, [rax+38h]
0x1800041d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800041de  mov     [rbp+57h+var_98], eax
0x1800041e1  test    eax, eax
0x1800041e3  mov     eax, 266h
0x1800041e8  js      loc_18000412F
0x1800041ee  mov     rcx, [rbp+57h+var_60]
0x1800041f2  lea     r9, [rbp+57h+arg_0]
0x1800041f6  mov     [rbp+57h+var_94], ax
0x1800041fa  lea     r8, [rbp+57h+var_A8]
0x1800041fe  mov     edx, 1
0x180004203  mov     rax, [rcx]
0x180004206  mov     rax, [rax+18h]
0x18000420a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000420f  mov     ecx, eax
0x180004211  mov     [rbp+57h+var_98], eax
0x180004214  test    eax, eax
0x180004216  mov     eax, 268h
0x18000421b  js      loc_18000412F
0x180004221  mov     [rbp+57h+var_94], ax
0x180004225  lea     esi, [rax+0Ah]
0x180004228  lea     r13d, [rax+8]
0x18000422c  lea     r14d, [rax+12h]
0x180004230  lea     r12d, [rax+19h]
0x180004234  lea     r15d, [rax+22h]
0x180004238  test    ecx, ecx
0x18000423a  jnz     loc_1800043CC
0x180004240  cmp     [rbp+57h+arg_0], edi
0x180004243  jbe     loc_1800043CC
0x180004249  mov     rcx, [rbp+57h+arg_10]
0x18000424d  lea     rdx, [rbp+57h+var_A0]
0x180004251  mov     r8, [rbp+57h+var_A8]
0x180004255  xor     r9d, r9d
0x180004258  mov     [rsp+0E0h+ppv], rdx
0x18000425d  xor     edx, edx
0x18000425f  mov     [rbp+57h+arg_8], edi
0x180004262  mov     rax, [rcx]
0x180004265  mov     rax, [rax+30h]
0x180004269  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000426e  mov     [rbp+57h+var_98], eax
0x180004271  test    eax, eax
0x180004273  mov     eax, 26Eh
0x180004278  js      loc_18000412F
0x18000427e  mov     rcx, [rbp+57h+var_A0]
0x180004282  lea     r8, [rbp+57h+var_B0]
0x180004286  mov     [rbp+57h+var_94], ax
0x18000428a  lea     rdx, _GUID_75207393_23f2_4396_85f0_8fdb879ed0ed
0x180004291  mov     rax, [rcx]
0x180004294  mov     rax, [rax]
0x180004297  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000429c  mov     [rbp+57h+var_98], eax
0x18000429f  test    eax, eax
0x1800042a1  js      loc_1800043C5
0x1800042a7  mov     rcx, [rbp+57h+var_B0]; struct ICbsPackage *
0x1800042ab  lea     rdx, [rbp+57h+arg_8]; int *
0x1800042af  mov     [rbp+57h+var_94], r13w
0x1800042b4  call    ?_IsWindowsUpdatePackage@CSxWindowsUpdateEnumerator@@CAJPEAUICbsPackage@@PEAH@Z; CSxWindowsUpdateEnumerator::_IsWindowsUpdatePackage(ICbsPackage *,int *)
0x1800042b9  mov     [rbp+57h+var_98], eax
0x1800042bc  test    eax, eax
0x1800042be  js      loc_1800043BF
0x1800042c4  mov     [rbp+57h+var_94], si
0x1800042c8  cmp     [rbp+57h+arg_8], edi
0x1800042cb  jz      short loc_180004328
0x1800042cd  mov     rcx, [rbp+57h+pv]; pv
0x1800042d1  call    cs:__imp_CoTaskMemFree
0x1800042d7  mov     rcx, [rbp+57h+var_B0]; struct ICbsPackage *
0x1800042db  lea     rdx, [rbp+57h+pv]; unsigned __int16 **
0x1800042df  mov     [rbp+57h+pv], rdi
0x1800042e3  call    ?_GetPackageDisplayName@CSxWindowsUpdateEnumerator@@CAJPEAUICbsPackage@@PEAPEAG@Z; CSxWindowsUpdateEnumerator::_GetPackageDisplayName(ICbsPackage *,ushort * *)
0x1800042e8  mov     [rbp+57h+var_98], eax
0x1800042eb  test    eax, eax
0x1800042ed  js      loc_1800043B1
0x1800042f3  mov     r8, [rbp+57h+pv]
0x1800042f7  mov     [rbp+57h+var_94], r14w
0x1800042fc  test    r8, r8
0x1800042ff  jz      short loc_180004328
0x180004301  mov     rcx, [rbx+30h]
0x180004305  mov     edx, 2
0x18000430a  mov     rax, [rbx+28h]
0x18000430e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004313  mov     [rbp+57h+var_98], eax
0x180004316  test    eax, eax
0x180004318  js      loc_1800043AA
0x18000431e  mov     [rbp+57h+var_94], r12w
0x180004323  cmp     eax, 1
0x180004326  jz      short loc_1800043A3
0x180004328  mov     rcx, [rbp+57h+var_B0]
0x18000432c  test    rcx, rcx
0x18000432f  jz      short loc_180004341
0x180004331  mov     [rbp+57h+var_B0], rdi
0x180004335  mov     rax, [rcx]
0x180004338  mov     rax, [rax+10h]
0x18000433c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004341  mov     rcx, [rbp+57h+var_A0]
0x180004345  test    rcx, rcx
0x180004348  jz      short loc_18000435A
0x18000434a  mov     [rbp+57h+var_A0], rdi
0x18000434e  mov     rax, [rcx]
0x180004351  mov     rax, [rax+10h]
0x180004355  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000435a  mov     rcx, [rbp+57h+var_A8]
0x18000435e  test    rcx, rcx
0x180004361  jz      short loc_180004373
0x180004363  mov     [rbp+57h+var_A8], rdi
0x180004367  mov     rax, [rcx]
0x18000436a  mov     rax, [rax+10h]
0x18000436e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004373  mov     rcx, [rbp+57h+var_60]
0x180004377  lea     r9, [rbp+57h+arg_0]
0x18000437b  lea     r8, [rbp+57h+var_A8]
0x18000437f  mov     edx, 1
0x180004384  mov     rax, [rcx]
0x180004387  mov     rax, [rax+18h]
0x18000438b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004390  mov     [rbp+57h+var_98], eax
0x180004393  mov     ecx, eax
0x180004395  test    eax, eax
0x180004397  js      short loc_1800043B8
0x180004399  mov     [rbp+57h+var_94], r15w
0x18000439e  jmp     loc_180004238
0x1800043a3  mov     [rbp+57h+var_98], 80004004h
0x1800043aa  mov     [rbp+57h+var_92], r12w
0x1800043af  jmp     short loc_1800043E2
0x1800043b1  mov     [rbp+57h+var_92], r14w
0x1800043b6  jmp     short loc_1800043E2
0x1800043b8  mov     [rbp+57h+var_92], r15w
0x1800043bd  jmp     short loc_1800043E2
0x1800043bf  mov     [rbp+57h+var_92], si
0x1800043c3  jmp     short loc_1800043E2
0x1800043c5  mov     [rbp+57h+var_92], r13w
0x1800043ca  jmp     short loc_1800043E2
0x1800043cc  lea     rcx, [rbp+57h+SystemTimeAsFileTime.dwLowDateTime+8]; lpSystemTimeAsFileTime
0x1800043d0  call    cs:__imp_GetSystemTimeAsFileTime
0x1800043d6  movups  xmm0, xmmword ptr [rbp+57h+SystemTimeAsFileTime.dwLowDateTime]
0x1800043da  movdqu  cs:xmmword_18001D980, xmm0
0x1800043e2  mov     rcx, [rbp+57h+arg_10]
0x1800043e6  test    rcx, rcx
0x1800043e9  jz      short loc_1800043FB
0x1800043eb  mov     [rbp+57h+arg_10], rdi
0x1800043ef  mov     rax, [rcx]
0x1800043f2  mov     rax, [rax+10h]
0x1800043f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800043fb  mov     rcx, rbx; this
0x1800043fe  call    ?_UnloadCBSHives@CSxWindowsUpdateEnumerator@@AEAAJXZ; CSxWindowsUpdateEnumerator::_UnloadCBSHives(void)
0x180004403  mov     rcx, [rbx+8]; unsigned __int16 *
0x180004407  call    ?_CleanupOldHives@CSxWindowsUpdateEnumerator@@CAJPEBG@Z; CSxWindowsUpdateEnumerator::_CleanupOldHives(ushort const *)
0x18000440c  mov     rcx, [rbp+57h+pv]; pv
0x180004410  call    cs:__imp_CoTaskMemFree
0x180004416  mov     [rbp+57h+pv], rdi
0x18000441a  mov     rcx, [rbp+57h+var_A0]
0x18000441e  mov     ebx, [rbp+57h+var_98]
0x180004421  test    rcx, rcx
0x180004424  jz      short loc_180004432
0x180004426  mov     rax, [rcx]
0x180004429  mov     rax, [rax+10h]
0x18000442d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004432  mov     rcx, [rbp+57h+var_B0]
0x180004436  test    rcx, rcx
0x180004439  jz      short loc_180004447
0x18000443b  mov     rax, [rcx]
0x18000443e  mov     rax, [rax+10h]
0x180004442  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004447  mov     rcx, [rbp+57h+var_A8]
0x18000444b  test    rcx, rcx
0x18000444e  jz      short loc_18000445C
0x180004450  mov     rax, [rcx]
0x180004453  mov     rax, [rax+10h]
0x180004457  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000445c  mov     rcx, [rbp+57h+var_60]
0x180004460  test    rcx, rcx
0x180004463  jz      short loc_180004471
0x180004465  mov     rax, [rcx]
0x180004468  mov     rax, [rax+10h]
0x18000446c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004471  mov     rcx, [rbp+57h+arg_10]
0x180004475  test    rcx, rcx
0x180004478  jz      short loc_180004486
0x18000447a  mov     rdx, [rcx]
0x18000447d  mov     rax, [rdx+10h]
0x180004481  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004486  lea     rcx, [rbp+57h+var_98]; this
0x18000448a  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18000448f  mov     eax, ebx
0x180004491  add     rsp, 0A8h
0x180004498  pop     r15
0x18000449a  pop     r14
0x18000449c  pop     r13
0x18000449e  pop     r12
0x1800044a0  pop     rdi
0x1800044a1  pop     rsi
0x1800044a2  pop     rbx
0x1800044a3  pop     rbp
0x1800044a4  retn
```
