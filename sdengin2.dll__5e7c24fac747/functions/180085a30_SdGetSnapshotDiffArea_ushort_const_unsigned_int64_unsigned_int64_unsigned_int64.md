# SdGetSnapshotDiffArea(ushort const *,unsigned __int64 *,unsigned __int64 *,unsigned __int64 *)

- ea: `0x180085a30`
- end: `0x180085cc6`
- name: `?SdGetSnapshotDiffArea@@YAJPEBGPEA_K11@Z`
- size: `662`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int64 *, unsigned __int64 *, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18001e604`

## callees

- `0x180003430`
- `0x1800081d8`
- `0x18006fe84`
- `0x18006ff8c`
- `0x180079e1c`
- `0x180085a30`
- `0x18008f5d0`
- `0x18009a24c`
- `0x18009a3ac`
- `0x18009ae34`
- `0x1800cb010`

## import_xrefs

- `KERNEL32!GetDiskFreeSpaceExW` at `0x180085b53`
- `KERNEL32!GetDiskFreeSpaceExW` at `0x180085b53`
- `ole32!CoTaskMemFree` at `0x180085bed`
- `ole32!CoTaskMemFree` at `0x180085bfb`
- `ole32!CoTaskMemFree` at `0x180085c77`
- `ole32!CoTaskMemFree` at `0x180085c85`
- `ole32!CoTaskMemFree` at `0x180085bed`
- `ole32!CoTaskMemFree` at `0x180085bfb`
- `ole32!CoTaskMemFree` at `0x180085c77`
- `ole32!CoTaskMemFree` at `0x180085c85`
- `VSSAPI!GetProviderMgmtInterfaceInternal` at `0x180085b9c`
- `VSSAPI!GetProviderMgmtInterfaceInternal` at `0x180085b9c`

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
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_47d9d944255c365ef76b44a624e21031_Traceguids);
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&LastFailureAsHRESULT, "SdGetSnapshotDiffArea", 950, 1);
  ATL::CComPtr<ISdUniCursor>::CComPtr<ISdUniCursor>(&v23);
  ATL::CComPtr<ISdUniCursor>::CComPtr<ISdUniCursor>(&v25);
  lpDirectoryName[0] = (LPCWSTR)qword_1800E8530;
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
  v22[0] = xmmword_1800E6C08;
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
  ATL::CComPtr<IResolveSidToUserName>::~CComPtr<IResolveSidToUserName>();
  ATL::CComPtr<IResolveSidToUserName>::~CComPtr<IResolveSidToUserName>();
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&LastFailureAsHRESULT);
  return v10;
}

```

## disassembly

```asm
0x180085a30  mov     [rsp-8+arg_18], r9
0x180085a35  mov     [rsp-8+arg_10], r8
0x180085a3a  push    rbp
0x180085a3b  push    rbx
0x180085a3c  push    rsi
0x180085a3d  push    rdi
0x180085a3e  push    r14
0x180085a40  lea     rbp, [rsp-37h]
0x180085a45  sub     rsp, 0E0h
0x180085a4c  mov     rbx, rdx
0x180085a4f  mov     rdi, rcx
0x180085a52  mov     rcx, cs:WPP_GLOBAL_Control
0x180085a59  lea     rax, WPP_GLOBAL_Control
0x180085a60  cmp     rcx, rax
0x180085a63  jz      short loc_180085A83
0x180085a65  test    dword ptr [rcx+1Ch], 20000000h
0x180085a6c  jz      short loc_180085A83
0x180085a6e  mov     rcx, [rcx+10h]
0x180085a72  lea     r8, WPP_47d9d944255c365ef76b44a624e21031_Traceguids
0x180085a79  mov     edx, 0Ch
0x180085a7e  call    WPP_SF_
0x180085a83  mov     r9d, 1; unsigned __int16
0x180085a89  lea     rdx, aSdgetsnapshotd; "SdGetSnapshotDiffArea"
0x180085a90  mov     r8d, 3B6h; unsigned __int16
0x180085a96  lea     rcx, [rbp+57h+var_D0]; this
0x180085a9a  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x180085a9f  lea     rcx, [rbp+57h+arg_0]; void *
0x180085aa3  call    ??0?$CComPtr@UISdUniCursor@@@ATL@@QEAA@XZ; ATL::CComPtr<ISdUniCursor>::CComPtr<ISdUniCursor>(void)
0x180085aa8  lea     rcx, [rbp+57h+arg_10]; void *
0x180085aac  call    ??0?$CComPtr@UISdUniCursor@@@ATL@@QEAA@XZ; ATL::CComPtr<ISdUniCursor>::CComPtr<ISdUniCursor>(void)
0x180085ab1  xor     esi, esi
0x180085ab3  lea     rax, qword_1800E8530
0x180085aba  mov     [rbp+57h+lpDirectoryName], rax
0x180085abe  xorps   xmm0, xmm0
0x180085ac1  mov     dword ptr [rbp+57h+arg_18], esi
0x180085ac4  mov     qword ptr [rbp+57h+FreeBytesAvailableToCaller], rsi
0x180085ac8  mov     qword ptr [rbp+57h+TotalNumberOfBytes], rsi
0x180085acc  mov     qword ptr [rbp+57h+TotalNumberOfFreeBytes], rsi
0x180085ad0  mov     [rbp+57h+var_90], rsi
0x180085ad4  movups  xmmword ptr [rbp+57h+pv], xmm0
0x180085ad8  movups  xmmword ptr [rbp+57h+var_68], xmm0
0x180085adc  movups  [rbp+57h+var_58], xmm0
0x180085ae0  test    rbx, rbx
0x180085ae3  jz      short loc_180085AE8
0x180085ae5  mov     [rbx], rsi
0x180085ae8  mov     eax, 3CAh
0x180085aed  test    rdi, rdi
0x180085af0  jnz     short loc_180085B02
0x180085af2  mov     [rbp+57h+var_D0], 80070057h
0x180085af9  mov     [rbp+57h+var_CA], ax
0x180085afd  jmp     loc_180085C73
0x180085b02  mov     rdx, rdi; unsigned __int16 *
0x180085b05  mov     [rbp+57h+var_D0], esi
0x180085b08  lea     rcx, [rbp+57h+lpDirectoryName]; this
0x180085b0c  mov     [rbp+57h+var_CC], ax
0x180085b10  call    ?Set@CBsString@@QEAAJPEBG@Z; CBsString::Set(ushort const *)
0x180085b15  mov     [rbp+57h+var_D0], eax
0x180085b18  test    eax, eax
0x180085b1a  mov     eax, 3CCh
0x180085b1f  js      short loc_180085AF9
0x180085b21  mov     edx, 5Ch ; '\'; unsigned __int16
0x180085b26  mov     [rbp+57h+var_CC], ax
0x180085b2a  lea     rcx, [rbp+57h+lpDirectoryName]; this
0x180085b2e  call    ?Trailing@CBsString@@QEAAJG@Z; CBsString::Trailing(ushort)
0x180085b33  mov     [rbp+57h+var_D0], eax
0x180085b36  test    eax, eax
0x180085b38  mov     eax, 3CDh
0x180085b3d  js      short loc_180085AF9
0x180085b3f  mov     rcx, [rbp+57h+lpDirectoryName]; lpDirectoryName
0x180085b43  lea     r9, [rbp+57h+TotalNumberOfFreeBytes]; lpTotalNumberOfFreeBytes
0x180085b47  lea     r8, [rbp+57h+TotalNumberOfBytes]; lpTotalNumberOfBytes
0x180085b4b  mov     [rbp+57h+var_CC], ax
0x180085b4f  lea     rdx, [rbp+57h+FreeBytesAvailableToCaller]; lpFreeBytesAvailableToCaller
0x180085b53  call    cs:__imp_GetDiskFreeSpaceExW
0x180085b59  test    eax, eax
0x180085b5b  jnz     short loc_180085B6C
0x180085b5d  call    GetLastFailureAsHRESULT
0x180085b62  mov     [rbp+57h+var_D0], eax
0x180085b65  mov     eax, 3D2h
0x180085b6a  jmp     short loc_180085AF9
0x180085b6c  movups  xmm1, xmmword ptr cs:IID_IVssDifferentialSoftwareSnapshotMgmt2.Data1
0x180085b73  mov     eax, 3D2h
0x180085b78  lea     r8, [rbp+57h+arg_0]
0x180085b7c  movups  xmm0, cs:xmmword_1800E6C08
0x180085b83  lea     rdx, [rbp+57h+var_40]
0x180085b87  mov     [rbp+57h+var_D0], esi
0x180085b8a  lea     rcx, [rbp+57h+var_30]
0x180085b8e  movdqa  [rbp+57h+var_40], xmm1
0x180085b93  movdqa  [rbp+57h+var_30], xmm0
0x180085b98  mov     [rbp+57h+var_CC], ax
0x180085b9c  call    cs:__imp_GetProviderMgmtInterfaceInternal
0x180085ba2  mov     [rbp+57h+var_D0], eax
0x180085ba5  test    eax, eax
0x180085ba7  mov     eax, 3D6h
0x180085bac  js      loc_180085AF9
0x180085bb2  mov     rcx, [rbp+57h+arg_0]
0x180085bb6  lea     r8, [rbp+57h+arg_10]
0x180085bba  mov     rdx, [rbp+57h+lpDirectoryName]
0x180085bbe  mov     [rbp+57h+var_CC], ax
0x180085bc2  mov     rax, [rcx]
0x180085bc5  mov     rax, [rax+38h]
0x180085bc9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180085bce  mov     [rbp+57h+var_D0], eax
0x180085bd1  test    eax, eax
0x180085bd3  mov     eax, 3D7h
0x180085bd8  js      loc_180085AF9
0x180085bde  mov     rdi, rsi
0x180085be1  mov     [rbp+57h+var_CC], ax
0x180085be5  lea     r14d, [rax+0Dh]
0x180085be9  mov     rcx, [rbp+57h+pv+8]; pv
0x180085bed  call    cs:__imp_CoTaskMemFree
0x180085bf3  mov     rcx, [rbp+57h+var_68]; pv
0x180085bf7  mov     [rbp+57h+pv+8], rsi
0x180085bfb  call    cs:__imp_CoTaskMemFree
0x180085c01  mov     rcx, [rbp+57h+arg_10]
0x180085c05  lea     r9, [rbp+57h+arg_18]
0x180085c09  xorps   xmm0, xmm0
0x180085c0c  mov     dword ptr [rbp+57h+arg_18], esi
0x180085c0f  movups  xmmword ptr [rbp+57h+pv], xmm0
0x180085c13  lea     r8, [rbp+57h+pv]
0x180085c17  mov     edx, 1
0x180085c1c  movups  xmmword ptr [rbp+57h+var_68], xmm0
0x180085c20  movups  [rbp+57h+var_58], xmm0
0x180085c24  mov     rax, [rcx]
0x180085c27  mov     rax, [rax+18h]
0x180085c2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180085c30  mov     [rbp+57h+var_D0], eax
0x180085c33  test    eax, eax
0x180085c35  js      short loc_180085C6E
0x180085c37  mov     [rbp+57h+var_CC], r14w
0x180085c3c  cmp     eax, 1
0x180085c3f  jz      short loc_180085C58
0x180085c41  cmp     dword ptr [rbp+57h+arg_18], 1
0x180085c45  jnz     short loc_180085BE9
0x180085c47  cmp     dword ptr [rbp+57h+pv], 3
0x180085c4b  jnz     short loc_180085BE9
0x180085c4d  add     rdi, qword ptr [rbp+57h+var_58+8]
0x180085c51  cmp     [rbp+57h+var_68+8], 0FFFFFFFFFFFFFFFFh
0x180085c56  jnz     short loc_180085BE9
0x180085c58  test    rbx, rbx
0x180085c5b  jz      short loc_180085C60
0x180085c5d  mov     [rbx], rdi
0x180085c60  mov     eax, 407h
0x180085c65  mov     [rbp+57h+var_D0], esi
0x180085c68  mov     [rbp+57h+var_CC], ax
0x180085c6c  jmp     short loc_180085C73
0x180085c6e  mov     [rbp+57h+var_CA], r14w
0x180085c73  mov     rcx, [rbp+57h+pv+8]; pv
0x180085c77  call    cs:__imp_CoTaskMemFree
0x180085c7d  mov     rcx, [rbp+57h+var_68]; pv
0x180085c81  mov     [rbp+57h+pv+8], rsi
0x180085c85  call    cs:__imp_CoTaskMemFree
0x180085c8b  mov     [rbp+57h+var_68], rsi
0x180085c8f  mov     ebx, [rbp+57h+var_D0]
0x180085c92  lea     rcx, [rbp+57h+lpDirectoryName]; this
0x180085c96  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x180085c9b  lea     rcx, [rbp+57h+arg_10]
0x180085c9f  call    ??1?$CComPtr@UIResolveSidToUserName@@@ATL@@QEAA@XZ; ATL::CComPtr<IResolveSidToUserName>::~CComPtr<IResolveSidToUserName>(void)
0x180085ca4  lea     rcx, [rbp+57h+arg_0]
0x180085ca8  call    ??1?$CComPtr@UIResolveSidToUserName@@@ATL@@QEAA@XZ; ATL::CComPtr<IResolveSidToUserName>::~CComPtr<IResolveSidToUserName>(void)
0x180085cad  lea     rcx, [rbp+57h+var_D0]; this
0x180085cb1  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x180085cb6  mov     eax, ebx
0x180085cb8  add     rsp, 0E0h
0x180085cbf  pop     r14
0x180085cc1  pop     rdi
0x180085cc2  pop     rsi
0x180085cc3  pop     rbx
0x180085cc4  pop     rbp
0x180085cc5  retn
```
