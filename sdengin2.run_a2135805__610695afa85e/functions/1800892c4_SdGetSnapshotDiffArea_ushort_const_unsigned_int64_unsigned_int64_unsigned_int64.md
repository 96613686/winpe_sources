# SdGetSnapshotDiffArea(ushort const *,unsigned __int64 *,unsigned __int64 *,unsigned __int64 *)

- ea: `0x1800892c4`
- end: `0x18008957f`
- name: `?SdGetSnapshotDiffArea@@YAJPEBGPEA_K11@Z`
- size: `699`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int64 *, unsigned __int64 *, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18001f128`

## callees

- `0x180003520`
- `0x180008370`
- `0x180072e08`
- `0x180072f14`
- `0x18007d000`
- `0x1800892c4`
- `0x1800935fc`
- `0x18009e904`
- `0x18009ea6c`
- `0x18009f560`
- `0x1800d1010`

## import_xrefs

- `KERNEL32!GetDiskFreeSpaceExW` at `0x1800893e7`
- `KERNEL32!GetDiskFreeSpaceExW` at `0x1800893e7`
- `ole32!CoTaskMemFree` at `0x18008948d`
- `ole32!CoTaskMemFree` at `0x1800894a1`
- `ole32!CoTaskMemFree` at `0x180089523`
- `ole32!CoTaskMemFree` at `0x180089537`
- `ole32!CoTaskMemFree` at `0x18008948d`
- `ole32!CoTaskMemFree` at `0x1800894a1`
- `ole32!CoTaskMemFree` at `0x180089523`
- `ole32!CoTaskMemFree` at `0x180089537`
- `VSSAPI!GetProviderMgmtInterfaceInternal` at `0x180089436`
- `VSSAPI!GetProviderMgmtInterfaceInternal` at `0x180089436`

## pseudocode

```c
__int64 __fastcall SdGetSnapshotDiffArea(
        const unsigned __int16 *a1,
        unsigned __int64 *a2,
        unsigned __int64 *a3,
        unsigned __int64 *a4)
{
  __int16 v6; // ax
  __int64 v7; // rcx
  unsigned __int64 v8; // rdi
  int v9; // eax
  unsigned int v10; // ebx
  int LastFailureAsHRESULT; // [rsp+30h] [rbp-79h] BYREF
  __int16 v13; // [rsp+34h] [rbp-75h]
  __int16 v14; // [rsp+36h] [rbp-73h]
  LPCWSTR lpDirectoryName[2]; // [rsp+68h] [rbp-41h] BYREF
  union _ULARGE_INTEGER TotalNumberOfBytes; // [rsp+78h] [rbp-31h] BYREF
  union _ULARGE_INTEGER FreeBytesAvailableToCaller; // [rsp+80h] [rbp-29h] BYREF
  LPVOID pv[2]; // [rsp+88h] [rbp-21h] BYREF
  LPVOID v19[2]; // [rsp+98h] [rbp-11h]
  __int128 v20; // [rsp+A8h] [rbp-1h]
  GUID v21; // [rsp+C0h] [rbp+17h] BYREF
  __int128 v22[3]; // [rsp+D0h] [rbp+27h] BYREF
  __int64 v23; // [rsp+110h] [rbp+67h] BYREF
  union _ULARGE_INTEGER TotalNumberOfFreeBytes; // [rsp+118h] [rbp+6Fh] BYREF
  unsigned __int64 *v25; // [rsp+120h] [rbp+77h] BYREF
  unsigned __int64 *v26; // [rsp+128h] [rbp+7Fh] BYREF

  v26 = a4;
  v25 = a3;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_47d9d944255c365ef76b44a624e21031_Traceguids, a4);
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&LastFailureAsHRESULT, "SdGetSnapshotDiffArea", 0x3B6u, 1u);
  ATL::CComPtr<ISdUniCursor>::CComPtr<ISdUniCursor>(&v23);
  ATL::CComPtr<ISdUniCursor>::CComPtr<ISdUniCursor>(&v25);
  lpDirectoryName[0] = (LPCWSTR)qword_1800EE510;
  LODWORD(v26) = 0;
  FreeBytesAvailableToCaller.QuadPart = 0;
  TotalNumberOfBytes.QuadPart = 0;
  TotalNumberOfFreeBytes.QuadPart = 0;
  lpDirectoryName[1] = 0;
  *(_OWORD *)pv = 0;
  *(_OWORD *)v19 = 0;
  v20 = 0;
  if ( a2 )
    *a2 = 0;
  v6 = 970;
  if ( !a1 )
  {
    LastFailureAsHRESULT = -2147024809;
LABEL_8:
    v14 = v6;
    goto LABEL_25;
  }
  LastFailureAsHRESULT = 0;
  v13 = 970;
  LastFailureAsHRESULT = CBsString::Set((CBsString *)lpDirectoryName, a1);
  v6 = 972;
  if ( LastFailureAsHRESULT < 0 )
    goto LABEL_8;
  v13 = 972;
  LastFailureAsHRESULT = CBsString::Trailing((CBsString *)lpDirectoryName, 0x5Cu);
  v6 = 973;
  if ( LastFailureAsHRESULT < 0 )
    goto LABEL_8;
  v13 = 973;
  if ( !GetDiskFreeSpaceExW(
          lpDirectoryName[0],
          &FreeBytesAvailableToCaller,
          &TotalNumberOfBytes,
          &TotalNumberOfFreeBytes) )
  {
    LastFailureAsHRESULT = GetLastFailureAsHRESULT(v7);
    v6 = 978;
    goto LABEL_8;
  }
  LastFailureAsHRESULT = 0;
  v21 = IID_IVssDifferentialSoftwareSnapshotMgmt2;
  v22[0] = xmmword_1800ECBE8;
  v13 = 978;
  LastFailureAsHRESULT = GetProviderMgmtInterfaceInternal(v22, &v21, &v23);
  v6 = 982;
  if ( LastFailureAsHRESULT < 0 )
    goto LABEL_8;
  v13 = 982;
  LastFailureAsHRESULT = (*(__int64 (__fastcall **)(__int64, LPCWSTR, unsigned __int64 **))(*(_QWORD *)v23 + 56LL))(
                           v23,
                           lpDirectoryName[0],
                           &v25);
  v6 = 983;
  if ( LastFailureAsHRESULT < 0 )
    goto LABEL_8;
  v8 = 0;
  v13 = 983;
  while ( 1 )
  {
    CoTaskMemFree(pv[1]);
    pv[1] = 0;
    CoTaskMemFree(v19[0]);
    LODWORD(v26) = 0;
    *(_OWORD *)pv = 0;
    *(_OWORD *)v19 = 0;
    v20 = 0;
    v9 = (*(__int64 (__fastcall **)(unsigned __int64 *, __int64, LPVOID *, unsigned __int64 **))(*v25 + 24))(
           v25,
           1,
           pv,
           &v26);
    LastFailureAsHRESULT = v9;
    if ( v9 < 0 )
    {
      v14 = 996;
      goto LABEL_25;
    }
    v13 = 996;
    if ( v9 == 1 )
      break;
    if ( (_DWORD)v26 == 1 && LODWORD(pv[0]) == 3 )
    {
      v8 += *((_QWORD *)&v20 + 1);
      if ( v19[1] == (LPVOID)-1LL )
        break;
    }
  }
  if ( a2 )
    *a2 = v8;
  LastFailureAsHRESULT = 0;
  v13 = 1031;
LABEL_25:
  CoTaskMemFree(pv[1]);
  pv[1] = 0;
  CoTaskMemFree(v19[0]);
  v19[0] = 0;
  v10 = LastFailureAsHRESULT;
  CBsString::_Release((CBsString *)lpDirectoryName);
  ATL::CComPtr<IResolveSidToUserName>::~CComPtr<IResolveSidToUserName>(&v25);
  ATL::CComPtr<IResolveSidToUserName>::~CComPtr<IResolveSidToUserName>(&v23);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&LastFailureAsHRESULT);
  return v10;
}

```

## disassembly

```asm
0x1800892c4  mov     [rsp-8+arg_18], r9
0x1800892c9  mov     [rsp-8+arg_10], r8
0x1800892ce  push    rbp
0x1800892cf  push    rbx
0x1800892d0  push    rsi
0x1800892d1  push    rdi
0x1800892d2  push    r14
0x1800892d4  lea     rbp, [rsp-37h]
0x1800892d9  sub     rsp, 0E0h
0x1800892e0  mov     rbx, rdx
0x1800892e3  mov     rdi, rcx
0x1800892e6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800892ed  lea     rax, WPP_GLOBAL_Control
0x1800892f4  cmp     rcx, rax
0x1800892f7  jz      short loc_180089317
0x1800892f9  test    dword ptr [rcx+1Ch], 20000000h
0x180089300  jz      short loc_180089317
0x180089302  mov     rcx, [rcx+10h]
0x180089306  lea     r8, WPP_47d9d944255c365ef76b44a624e21031_Traceguids
0x18008930d  mov     edx, 0Ch
0x180089312  call    WPP_SF_
0x180089317  mov     r9d, 1; unsigned __int16
0x18008931d  lea     rdx, aSdgetsnapshotd; "SdGetSnapshotDiffArea"
0x180089324  mov     r8d, 3B6h; unsigned __int16
0x18008932a  lea     rcx, [rbp+57h+var_D0]; this
0x18008932e  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x180089333  lea     rcx, [rbp+57h+arg_0]; void *
0x180089337  call    ??0?$CComPtr@UISdUniCursor@@@ATL@@QEAA@XZ; ATL::CComPtr<ISdUniCursor>::CComPtr<ISdUniCursor>(void)
0x18008933c  lea     rcx, [rbp+57h+arg_10]; void *
0x180089340  call    ??0?$CComPtr@UISdUniCursor@@@ATL@@QEAA@XZ; ATL::CComPtr<ISdUniCursor>::CComPtr<ISdUniCursor>(void)
0x180089345  xor     esi, esi
0x180089347  lea     rax, qword_1800EE510
0x18008934e  mov     [rbp+57h+lpDirectoryName], rax
0x180089352  xorps   xmm0, xmm0
0x180089355  mov     dword ptr [rbp+57h+arg_18], esi
0x180089358  mov     qword ptr [rbp+57h+FreeBytesAvailableToCaller], rsi
0x18008935c  mov     qword ptr [rbp+57h+TotalNumberOfBytes], rsi
0x180089360  mov     qword ptr [rbp+57h+TotalNumberOfFreeBytes], rsi
0x180089364  mov     [rbp+57h+var_90], rsi
0x180089368  movups  xmmword ptr [rbp+57h+pv], xmm0
0x18008936c  movups  xmmword ptr [rbp+57h+var_68], xmm0
0x180089370  movups  [rbp+57h+var_58], xmm0
0x180089374  test    rbx, rbx
0x180089377  jz      short loc_18008937C
0x180089379  mov     [rbx], rsi
0x18008937c  mov     eax, 3CAh
0x180089381  test    rdi, rdi
0x180089384  jnz     short loc_180089396
0x180089386  mov     [rbp+57h+var_D0], 80070057h
0x18008938d  mov     [rbp+57h+var_CA], ax
0x180089391  jmp     loc_18008951F
0x180089396  mov     rdx, rdi; unsigned __int16 *
0x180089399  mov     [rbp+57h+var_D0], esi
0x18008939c  lea     rcx, [rbp+57h+lpDirectoryName]; this
0x1800893a0  mov     [rbp+57h+var_CC], ax
0x1800893a4  call    ?Set@CBsString@@QEAAJPEBG@Z; CBsString::Set(ushort const *)
0x1800893a9  mov     [rbp+57h+var_D0], eax
0x1800893ac  test    eax, eax
0x1800893ae  mov     eax, 3CCh
0x1800893b3  js      short loc_18008938D
0x1800893b5  mov     edx, 5Ch ; '\'; unsigned __int16
0x1800893ba  mov     [rbp+57h+var_CC], ax
0x1800893be  lea     rcx, [rbp+57h+lpDirectoryName]; this
0x1800893c2  call    ?Trailing@CBsString@@QEAAJG@Z; CBsString::Trailing(ushort)
0x1800893c7  mov     [rbp+57h+var_D0], eax
0x1800893ca  test    eax, eax
0x1800893cc  mov     eax, 3CDh
0x1800893d1  js      short loc_18008938D
0x1800893d3  mov     rcx, [rbp+57h+lpDirectoryName]; lpDirectoryName
0x1800893d7  lea     r9, [rbp+57h+TotalNumberOfFreeBytes]; lpTotalNumberOfFreeBytes
0x1800893db  lea     r8, [rbp+57h+TotalNumberOfBytes]; lpTotalNumberOfBytes
0x1800893df  mov     [rbp+57h+var_CC], ax
0x1800893e3  lea     rdx, [rbp+57h+FreeBytesAvailableToCaller]; lpFreeBytesAvailableToCaller
0x1800893e7  call    cs:__imp_GetDiskFreeSpaceExW
0x1800893ee  nop     dword ptr [rax+rax+00h]
0x1800893f3  test    eax, eax
0x1800893f5  jnz     short loc_180089406
0x1800893f7  call    GetLastFailureAsHRESULT
0x1800893fc  mov     [rbp+57h+var_D0], eax
0x1800893ff  mov     eax, 3D2h
0x180089404  jmp     short loc_18008938D
0x180089406  movups  xmm1, xmmword ptr cs:IID_IVssDifferentialSoftwareSnapshotMgmt2.Data1
0x18008940d  mov     eax, 3D2h
0x180089412  lea     r8, [rbp+57h+arg_0]
0x180089416  movups  xmm0, cs:xmmword_1800ECBE8
0x18008941d  lea     rdx, [rbp+57h+var_40]
0x180089421  mov     [rbp+57h+var_D0], esi
0x180089424  lea     rcx, [rbp+57h+var_30]
0x180089428  movdqa  [rbp+57h+var_40], xmm1
0x18008942d  movdqa  [rbp+57h+var_30], xmm0
0x180089432  mov     [rbp+57h+var_CC], ax
0x180089436  call    cs:__imp_GetProviderMgmtInterfaceInternal
0x18008943d  nop     dword ptr [rax+rax+00h]
0x180089442  mov     [rbp+57h+var_D0], eax
0x180089445  test    eax, eax
0x180089447  mov     eax, 3D6h
0x18008944c  js      loc_18008938D
0x180089452  mov     rcx, [rbp+57h+arg_0]
0x180089456  lea     r8, [rbp+57h+arg_10]
0x18008945a  mov     rdx, [rbp+57h+lpDirectoryName]
0x18008945e  mov     [rbp+57h+var_CC], ax
0x180089462  mov     rax, [rcx]
0x180089465  mov     rax, [rax+38h]
0x180089469  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008946e  mov     [rbp+57h+var_D0], eax
0x180089471  test    eax, eax
0x180089473  mov     eax, 3D7h
0x180089478  js      loc_18008938D
0x18008947e  mov     rdi, rsi
0x180089481  mov     [rbp+57h+var_CC], ax
0x180089485  lea     r14d, [rax+0Dh]
0x180089489  mov     rcx, [rbp+57h+pv+8]; pv
0x18008948d  call    cs:__imp_CoTaskMemFree
0x180089494  nop     dword ptr [rax+rax+00h]
0x180089499  mov     rcx, [rbp+57h+var_68]; pv
0x18008949d  mov     [rbp+57h+pv+8], rsi
0x1800894a1  call    cs:__imp_CoTaskMemFree
0x1800894a8  nop     dword ptr [rax+rax+00h]
0x1800894ad  mov     rcx, [rbp+57h+arg_10]
0x1800894b1  lea     r9, [rbp+57h+arg_18]
0x1800894b5  xorps   xmm0, xmm0
0x1800894b8  mov     dword ptr [rbp+57h+arg_18], esi
0x1800894bb  movups  xmmword ptr [rbp+57h+pv], xmm0
0x1800894bf  lea     r8, [rbp+57h+pv]
0x1800894c3  mov     edx, 1
0x1800894c8  movups  xmmword ptr [rbp+57h+var_68], xmm0
0x1800894cc  movups  [rbp+57h+var_58], xmm0
0x1800894d0  mov     rax, [rcx]
0x1800894d3  mov     rax, [rax+18h]
0x1800894d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800894dc  mov     [rbp+57h+var_D0], eax
0x1800894df  test    eax, eax
0x1800894e1  js      short loc_18008951A
0x1800894e3  mov     [rbp+57h+var_CC], r14w
0x1800894e8  cmp     eax, 1
0x1800894eb  jz      short loc_180089504
0x1800894ed  cmp     dword ptr [rbp+57h+arg_18], 1
0x1800894f1  jnz     short loc_180089489
0x1800894f3  cmp     dword ptr [rbp+57h+pv], 3
0x1800894f7  jnz     short loc_180089489
0x1800894f9  add     rdi, qword ptr [rbp+57h+var_58+8]
0x1800894fd  cmp     [rbp+57h+var_68+8], 0FFFFFFFFFFFFFFFFh
0x180089502  jnz     short loc_180089489
0x180089504  test    rbx, rbx
0x180089507  jz      short loc_18008950C
0x180089509  mov     [rbx], rdi
0x18008950c  mov     eax, 407h
0x180089511  mov     [rbp+57h+var_D0], esi
0x180089514  mov     [rbp+57h+var_CC], ax
0x180089518  jmp     short loc_18008951F
0x18008951a  mov     [rbp+57h+var_CA], r14w
0x18008951f  mov     rcx, [rbp+57h+pv+8]; pv
0x180089523  call    cs:__imp_CoTaskMemFree
0x18008952a  nop     dword ptr [rax+rax+00h]
0x18008952f  mov     rcx, [rbp+57h+var_68]; pv
0x180089533  mov     [rbp+57h+pv+8], rsi
0x180089537  call    cs:__imp_CoTaskMemFree
0x18008953e  nop     dword ptr [rax+rax+00h]
0x180089543  mov     [rbp+57h+var_68], rsi
0x180089547  mov     ebx, [rbp+57h+var_D0]
0x18008954a  lea     rcx, [rbp+57h+lpDirectoryName]; this
0x18008954e  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x180089553  lea     rcx, [rbp+57h+arg_10]
0x180089557  call    ??1?$CComPtr@UIResolveSidToUserName@@@ATL@@QEAA@XZ; ATL::CComPtr<IResolveSidToUserName>::~CComPtr<IResolveSidToUserName>(void)
0x18008955c  lea     rcx, [rbp+57h+arg_0]
0x180089560  call    ??1?$CComPtr@UIResolveSidToUserName@@@ATL@@QEAA@XZ; ATL::CComPtr<IResolveSidToUserName>::~CComPtr<IResolveSidToUserName>(void)
0x180089565  lea     rcx, [rbp+57h+var_D0]; this
0x180089569  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18008956e  mov     eax, ebx
0x180089570  add     rsp, 0E0h
0x180089577  pop     r14
0x180089579  pop     rdi
0x18008957a  pop     rsi
0x18008957b  pop     rbx
0x18008957c  pop     rbp
0x18008957d  retn
```
