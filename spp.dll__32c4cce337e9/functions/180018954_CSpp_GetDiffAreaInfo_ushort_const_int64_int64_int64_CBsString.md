# CSpp::_GetDiffAreaInfo(ushort const *,__int64 *,__int64 *,__int64 *,CBsString *)

- ea: `0x180018954`
- end: `0x180018caa`
- name: `?_GetDiffAreaInfo@CSpp@@CAJPEBGPEA_J11PEAVCBsString@@@Z`
- size: `854`
- prototype: `__int64 __fastcall(const unsigned __int16 *, __int64 *, __int64 *, unsigned __int16 **, struct CBsString *)`
- caller_count: `1`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000c910`

## callees

- `0x1800021f8`
- `0x18000232c`
- `0x180018954`
- `0x180020710`
- `0x180021614`
- `0x1800268b4`
- `0x1800269ac`
- `0x180034f3c`
- `0x18003532c`
- `0x1800353c4`
- `0x180035b00`
- `0x180037010`

## import_xrefs

- `VSSAPI!GetProviderMgmtInterfaceInternal` at `0x180018ad8`
- `VSSAPI!GetProviderMgmtInterfaceInternal` at `0x180018ad8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180018b2e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180018b3c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180018c55`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180018c63`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180018b2e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180018b3c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180018c55`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180018c63`

## pseudocode

```c
__int64 __fastcall CSpp::_GetDiffAreaInfo(
        const unsigned __int16 *a1,
        __int64 *a2,
        __int64 *a3,
        unsigned __int16 **a4,
        struct CBsString *a5)
{
  LPVOID *v9; // rax
  __int64 v10; // rcx
  CBsString *v11; // rbx
  __int16 v12; // ax
  unsigned __int16 v13; // dx
  int v14; // eax
  unsigned __int16 *v15; // r8
  const WCHAR *v16; // rdx
  __int16 v17; // ax
  unsigned int v18; // ebx
  __int64 v19; // rdx
  __int64 v20; // r8
  int ProviderMgmtInterfaceInternal; // [rsp+40h] [rbp-91h] BYREF
  __int16 v23; // [rsp+44h] [rbp-8Dh]
  __int16 v24; // [rsp+46h] [rbp-8Bh]
  __int64 v25; // [rsp+78h] [rbp-59h] BYREF
  __int64 v26; // [rsp+80h] [rbp-51h] BYREF
  LPVOID pv[2]; // [rsp+88h] [rbp-49h] BYREF
  unsigned __int16 *v28[2]; // [rsp+98h] [rbp-39h]
  __int128 v29; // [rsp+A8h] [rbp-29h]
  _QWORD v30[3]; // [rsp+B8h] [rbp-19h] BYREF
  GUID v31; // [rsp+D0h] [rbp-1h] BYREF
  __int128 v32[4]; // [rsp+E0h] [rbp+Fh] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 193, &WPP_c4639252eff5306510cbdeb3ef3cc4de_Traceguids);
  CSxFunctionTracer::CSxFunctionTracer(
    (CSxFunctionTracer *)&ProviderMgmtInterfaceInternal,
    "CSpp::_GetDiffAreaInfo",
    11344,
    1);
  ATL::CComPtr<IVssBackupComponents>::CComPtr<IVssBackupComponents>(&v26);
  ATL::CComPtr<IVssBackupComponents>::CComPtr<IVssBackupComponents>(&v25);
  v30[0] = &FileName;
  *(_OWORD *)pv = 0;
  v30[1] = 0;
  v9 = pv;
  *(_OWORD *)v28 = 0;
  v10 = 48;
  v29 = 0;
  do
  {
    *(_BYTE *)v9 = 0;
    v9 = (LPVOID *)((char *)v9 + 1);
    --v10;
  }
  while ( v10 );
  v11 = a5;
  v12 = 11352;
  if ( !a5 || (v23 = 11352, v12 = 11353, !a2) || (v23 = 11353, v12 = 11354, !a3) || (v23 = 11354, v12 = 11355, !a4) )
  {
    ProviderMgmtInterfaceInternal = -2147024809;
LABEL_30:
    v24 = v12;
    goto LABEL_31;
  }
  ProviderMgmtInterfaceInternal = 0;
  v23 = 11355;
  CBsString::Empty(a5);
  *a2 = 0;
  *a3 = 0;
  *a4 = 0;
  ProviderMgmtInterfaceInternal = CBsString::Set((CBsString *)v30, a1);
  v12 = 11363;
  if ( ProviderMgmtInterfaceInternal < 0 )
    goto LABEL_30;
  v23 = 11363;
  ProviderMgmtInterfaceInternal = CBsString::Trailing((CBsString *)v30, v13);
  v12 = 11364;
  if ( ProviderMgmtInterfaceInternal < 0 )
    goto LABEL_30;
  v23 = 11364;
  v31 = IID_IVssDifferentialSoftwareSnapshotMgmt2;
  v32[0] = xmmword_18003B620;
  ProviderMgmtInterfaceInternal = GetProviderMgmtInterfaceInternal(v32, &v31, &v26);
  v12 = 11368;
  if ( ProviderMgmtInterfaceInternal < 0 )
    goto LABEL_30;
  v23 = 11368;
  ProviderMgmtInterfaceInternal = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v26 + 48LL))(
                                    v26,
                                    v30[0],
                                    &v25);
  v12 = 11369;
  if ( ProviderMgmtInterfaceInternal < 0 )
    goto LABEL_30;
  v23 = 11369;
  while ( 1 )
  {
    LODWORD(a5) = 0;
    CoTaskMemFree(pv[1]);
    pv[1] = 0;
    CoTaskMemFree(v28[0]);
    LODWORD(a5) = 0;
    *(_OWORD *)pv = 0;
    *(_OWORD *)v28 = 0;
    v29 = 0;
    v14 = (*(__int64 (__fastcall **)(__int64, __int64, LPVOID *, struct CBsString **))(*(_QWORD *)v25 + 24LL))(
            v25,
            1,
            pv,
            &a5);
    ProviderMgmtInterfaceInternal = v14;
    if ( v14 < 0 )
      break;
    v23 = 11380;
    if ( v14 == 1 )
    {
      ProviderMgmtInterfaceInternal = 1;
      v17 = 11403;
LABEL_26:
      v23 = v17;
      goto LABEL_31;
    }
    if ( (_DWORD)a5 == 1 && LODWORD(pv[0]) == 3 )
    {
      ProviderMgmtInterfaceInternal = CBsString::Set(v11, v28[0]);
      v12 = 11388;
      if ( ProviderMgmtInterfaceInternal < 0 )
        goto LABEL_30;
      v15 = v28[1];
      v23 = 11388;
      *(_OWORD *)a3 = v29;
      *a4 = v15;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000000) != 0 )
      {
        v16 = &word_18003B6A0;
        if ( v28[0] )
          v16 = v28[0];
        WPP_SF_iiiS(*((_QWORD *)WPP_GLOBAL_Control + 2), (_DWORD)v16, (_DWORD)v15, *a2, *a3, (char)v15, (__int64)v16);
      }
      ProviderMgmtInterfaceInternal = 0;
      v17 = 11399;
      goto LABEL_26;
    }
  }
  v24 = 11380;
LABEL_31:
  CoTaskMemFree(pv[1]);
  pv[1] = 0;
  CoTaskMemFree(v28[0]);
  v28[0] = 0;
  v18 = ProviderMgmtInterfaceInternal;
  CBsString::_Release((CBsString *)v30);
  ATL::CComPtr<IVssExamineWriterMetadata>::~CComPtr<IVssExamineWriterMetadata>();
  ATL::CComPtr<IVssExamineWriterMetadata>::~CComPtr<IVssExamineWriterMetadata>();
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&ProviderMgmtInterfaceInternal, v19, v20);
  return v18;
}

```

## disassembly

```asm
0x180018954  push    rbp
0x180018956  push    rbx
0x180018957  push    rsi
0x180018958  push    rdi
0x180018959  push    r12
0x18001895b  push    r14
0x18001895d  push    r15
0x18001895f  lea     rbp, [rsp-1Fh]
0x180018964  sub     rsp, 0F0h
0x18001896b  mov     r14, r9
0x18001896e  mov     rdi, r8
0x180018971  mov     rsi, rdx
0x180018974  mov     r15, rcx
0x180018977  mov     rcx, cs:WPP_GLOBAL_Control
0x18001897e  lea     rax, WPP_GLOBAL_Control
0x180018985  cmp     rcx, rax
0x180018988  jz      short loc_1800189A8
0x18001898a  test    dword ptr [rcx+1Ch], 20000000h
0x180018991  jz      short loc_1800189A8
0x180018993  mov     rcx, [rcx+10h]
0x180018997  lea     r8, WPP_c4639252eff5306510cbdeb3ef3cc4de_Traceguids
0x18001899e  mov     edx, 0C1h
0x1800189a3  call    WPP_SF_
0x1800189a8  mov     r9d, 1; unsigned __int16
0x1800189ae  lea     rdx, aCsppGetdiffare; "CSpp::_GetDiffAreaInfo"
0x1800189b5  mov     r8d, 2C50h; unsigned __int16
0x1800189bb  lea     rcx, [rsp+120h+var_E0]; this
0x1800189c0  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x1800189c5  lea     rcx, [rbp+4Fh+var_A0]
0x1800189c9  call    ??0?$CComPtr@VIVssBackupComponents@@@ATL@@QEAA@H@Z; ATL::CComPtr<IVssBackupComponents>::CComPtr<IVssBackupComponents>(int)
0x1800189ce  lea     rcx, [rbp+4Fh+var_A8]
0x1800189d2  call    ??0?$CComPtr@VIVssBackupComponents@@@ATL@@QEAA@H@Z; ATL::CComPtr<IVssBackupComponents>::CComPtr<IVssBackupComponents>(int)
0x1800189d7  xorps   xmm0, xmm0
0x1800189da  lea     rax, FileName
0x1800189e1  xor     r12d, r12d
0x1800189e4  mov     [rbp+4Fh+var_68], rax
0x1800189e8  movups  xmmword ptr [rbp+4Fh+pv], xmm0
0x1800189ec  mov     [rbp+4Fh+var_60], r12
0x1800189f0  lea     rax, [rbp+4Fh+pv]
0x1800189f4  movups  xmmword ptr [rbp+4Fh+var_88], xmm0
0x1800189f8  lea     ecx, [r12+30h]
0x1800189fd  movups  [rbp+4Fh+var_78], xmm0
0x180018a01  mov     [rax], r12b
0x180018a04  inc     rax
0x180018a07  sub     rcx, 1
0x180018a0b  jnz     short loc_180018A01
0x180018a0d  mov     rbx, [rbp+4Fh+arg_20]
0x180018a11  mov     eax, 2C58h
0x180018a16  test    rbx, rbx
0x180018a19  jz      loc_180018C44
0x180018a1f  mov     [rsp+120h+var_DC], ax
0x180018a24  mov     eax, 2C59h
0x180018a29  test    rsi, rsi
0x180018a2c  jz      loc_180018C44
0x180018a32  mov     [rsp+120h+var_DC], ax
0x180018a37  mov     eax, 2C5Ah
0x180018a3c  test    rdi, rdi
0x180018a3f  jz      loc_180018C44
0x180018a45  mov     [rsp+120h+var_DC], ax
0x180018a4a  mov     eax, 2C5Bh
0x180018a4f  test    r14, r14
0x180018a52  jz      loc_180018C44
0x180018a58  mov     rcx, rbx; this
0x180018a5b  mov     [rsp+120h+var_E0], r12d
0x180018a60  mov     [rsp+120h+var_DC], ax
0x180018a65  call    ?Empty@CBsString@@QEAAXXZ; CBsString::Empty(void)
0x180018a6a  mov     [rsi], r12
0x180018a6d  lea     rcx, [rbp+4Fh+var_68]; this
0x180018a71  mov     [rdi], r12
0x180018a74  mov     rdx, r15; unsigned __int16 *
0x180018a77  mov     [r14], r12
0x180018a7a  call    ?Set@CBsString@@QEAAJPEBG@Z; CBsString::Set(ushort const *)
0x180018a7f  mov     [rsp+120h+var_E0], eax
0x180018a83  test    eax, eax
0x180018a85  mov     eax, 2C63h
0x180018a8a  js      loc_180018C4C
0x180018a90  lea     rcx, [rbp+4Fh+var_68]; this
0x180018a94  mov     [rsp+120h+var_DC], ax
0x180018a99  call    ?Trailing@CBsString@@QEAAJG@Z; CBsString::Trailing(ushort)
0x180018a9e  mov     [rsp+120h+var_E0], eax
0x180018aa2  test    eax, eax
0x180018aa4  mov     eax, 2C64h
0x180018aa9  js      loc_180018C4C
0x180018aaf  movups  xmm1, xmmword ptr cs:IID_IVssDifferentialSoftwareSnapshotMgmt2.Data1
0x180018ab6  lea     r8, [rbp+4Fh+var_A0]
0x180018aba  mov     [rsp+120h+var_DC], ax
0x180018abf  movups  xmm0, cs:xmmword_18003B620
0x180018ac6  lea     rdx, [rbp+4Fh+var_50]
0x180018aca  lea     rcx, [rbp+4Fh+var_40]
0x180018ace  movdqa  [rbp+4Fh+var_50], xmm1
0x180018ad3  movdqa  [rbp+4Fh+var_40], xmm0
0x180018ad8  call    cs:__imp_GetProviderMgmtInterfaceInternal
0x180018ade  mov     [rsp+120h+var_E0], eax
0x180018ae2  test    eax, eax
0x180018ae4  mov     eax, 2C68h
0x180018ae9  js      loc_180018C4C
0x180018aef  mov     rcx, [rbp+4Fh+var_A0]
0x180018af3  lea     r8, [rbp+4Fh+var_A8]
0x180018af7  mov     rdx, [rbp+4Fh+var_68]
0x180018afb  mov     [rsp+120h+var_DC], ax
0x180018b00  mov     rax, [rcx]
0x180018b03  mov     rax, [rax+30h]
0x180018b07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018b0c  mov     [rsp+120h+var_E0], eax
0x180018b10  test    eax, eax
0x180018b12  mov     eax, 2C69h
0x180018b17  js      loc_180018C4C
0x180018b1d  mov     [rsp+120h+var_DC], ax
0x180018b22  lea     r15d, [rax+0Bh]
0x180018b26  mov     rcx, [rbp+4Fh+pv+8]; pv
0x180018b2a  mov     dword ptr [rbp+4Fh+arg_20], r12d
0x180018b2e  call    cs:__imp_CoTaskMemFree
0x180018b34  mov     rcx, [rbp+4Fh+var_88]; pv
0x180018b38  mov     [rbp+4Fh+pv+8], r12
0x180018b3c  call    cs:__imp_CoTaskMemFree
0x180018b42  mov     rcx, [rbp+4Fh+var_A8]
0x180018b46  lea     r9, [rbp+4Fh+arg_20]
0x180018b4a  xorps   xmm0, xmm0
0x180018b4d  mov     dword ptr [rbp+4Fh+arg_20], r12d
0x180018b51  movups  xmmword ptr [rbp+4Fh+pv], xmm0
0x180018b55  lea     r8, [rbp+4Fh+pv]
0x180018b59  mov     edx, 1
0x180018b5e  movups  xmmword ptr [rbp+4Fh+var_88], xmm0
0x180018b62  movups  [rbp+4Fh+var_78], xmm0
0x180018b66  mov     rax, [rcx]
0x180018b69  mov     rax, [rax+18h]
0x180018b6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018b72  mov     [rsp+120h+var_E0], eax
0x180018b76  test    eax, eax
0x180018b78  js      loc_180018C3C
0x180018b7e  mov     [rsp+120h+var_DC], r15w
0x180018b84  cmp     eax, 1
0x180018b87  jz      loc_180018C2D
0x180018b8d  cmp     dword ptr [rbp+4Fh+arg_20], 1
0x180018b91  jnz     short loc_180018B26
0x180018b93  cmp     dword ptr [rbp+4Fh+pv], 3
0x180018b97  jnz     short loc_180018B26
0x180018b99  mov     rdx, [rbp+4Fh+var_88]; unsigned __int16 *
0x180018b9d  mov     rcx, rbx; this
0x180018ba0  call    ?Set@CBsString@@QEAAJPEBG@Z; CBsString::Set(ushort const *)
0x180018ba5  mov     [rsp+120h+var_E0], eax
0x180018ba9  test    eax, eax
0x180018bab  mov     eax, 2C7Ch
0x180018bb0  js      loc_180018C4C
0x180018bb6  mov     r8, [rbp+4Fh+var_88+8]
0x180018bba  mov     [rsp+120h+var_DC], ax
0x180018bbf  mov     rax, qword ptr [rbp+4Fh+var_78+8]
0x180018bc3  mov     [rsi], rax
0x180018bc6  mov     rax, qword ptr [rbp+4Fh+var_78]
0x180018bca  mov     [rdi], rax
0x180018bcd  mov     [r14], r8
0x180018bd0  mov     rcx, cs:WPP_GLOBAL_Control
0x180018bd7  lea     rax, WPP_GLOBAL_Control
0x180018bde  cmp     rcx, rax
0x180018be1  jz      short loc_180018C1C
0x180018be3  test    dword ptr [rcx+1Ch], 8000000h
0x180018bea  jz      short loc_180018C1C
0x180018bec  mov     rax, [rbp+4Fh+var_88]
0x180018bf0  lea     rdx, word_18003B6A0
0x180018bf7  mov     r9, [rsi]
0x180018bfa  test    rax, rax
0x180018bfd  mov     rcx, [rcx+10h]
0x180018c01  cmovnz  rdx, rax
0x180018c05  mov     rax, [rdi]
0x180018c08  mov     [rsp+120h+var_F0], rdx
0x180018c0d  mov     [rsp+120h+var_F8], r8
0x180018c12  mov     [rsp+120h+var_100], rax
0x180018c17  call    WPP_SF_iiiS
0x180018c1c  mov     [rsp+120h+var_E0], r12d
0x180018c21  mov     eax, 2C87h
0x180018c26  mov     [rsp+120h+var_DC], ax
0x180018c2b  jmp     short loc_180018C51
0x180018c2d  mov     [rsp+120h+var_E0], 1
0x180018c35  mov     eax, 2C8Bh
0x180018c3a  jmp     short loc_180018C26
0x180018c3c  mov     [rsp+120h+var_DA], r15w
0x180018c42  jmp     short loc_180018C51
0x180018c44  mov     [rsp+120h+var_E0], 80070057h
0x180018c4c  mov     [rsp+120h+var_DA], ax
0x180018c51  mov     rcx, [rbp+4Fh+pv+8]; pv
0x180018c55  call    cs:__imp_CoTaskMemFree
0x180018c5b  mov     rcx, [rbp+4Fh+var_88]; pv
0x180018c5f  mov     [rbp+4Fh+pv+8], r12
0x180018c63  call    cs:__imp_CoTaskMemFree
0x180018c69  mov     [rbp+4Fh+var_88], r12
0x180018c6d  mov     ebx, [rsp+120h+var_E0]
0x180018c71  lea     rcx, [rbp+4Fh+var_68]; this
0x180018c75  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x180018c7a  lea     rcx, [rbp+4Fh+var_A8]
0x180018c7e  call    ??1?$CComPtr@VIVssExamineWriterMetadata@@@ATL@@QEAA@XZ; ATL::CComPtr<IVssExamineWriterMetadata>::~CComPtr<IVssExamineWriterMetadata>(void)
0x180018c83  lea     rcx, [rbp+4Fh+var_A0]
0x180018c87  call    ??1?$CComPtr@VIVssExamineWriterMetadata@@@ATL@@QEAA@XZ; ATL::CComPtr<IVssExamineWriterMetadata>::~CComPtr<IVssExamineWriterMetadata>(void)
0x180018c8c  lea     rcx, [rsp+120h+var_E0]; this
0x180018c91  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x180018c96  mov     eax, ebx
0x180018c98  add     rsp, 0F0h
0x180018c9f  pop     r15
0x180018ca1  pop     r14
0x180018ca3  pop     r12
0x180018ca5  pop     rdi
0x180018ca6  pop     rsi
0x180018ca7  pop     rbx
0x180018ca8  pop     rbp
0x180018ca9  retn
```
