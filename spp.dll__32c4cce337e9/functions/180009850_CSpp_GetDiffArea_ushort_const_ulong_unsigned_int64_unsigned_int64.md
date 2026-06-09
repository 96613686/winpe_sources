# CSpp::GetDiffArea(ushort const *,ulong *,unsigned __int64 *,unsigned __int64 *)

- ea: `0x180009850`
- end: `0x180009ba6`
- name: `?GetDiffArea@CSpp@@UEAAJPEBGPEAKPEA_K2@Z`
- size: `854`
- prototype: `int(CSpp *__hidden this, const unsigned __int16 *, unsigned int *, unsigned __int64 *, unsigned __int64 *)`
- caller_count: `0`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800021f8`
- `0x18000232c`
- `0x180009850`
- `0x180020710`
- `0x1800268b4`
- `0x1800269ac`
- `0x18002d6e8`
- `0x18003532c`
- `0x1800353c4`
- `0x180035b00`
- `0x180037010`

## import_xrefs

- `KERNEL32!GetDiskFreeSpaceExW` at `0x1800099c5`
- `KERNEL32!GetDiskFreeSpaceExW` at `0x1800099c5`
- `VSSAPI!GetProviderMgmtInterfaceInternal` at `0x180009a15`
- `VSSAPI!GetProviderMgmtInterfaceInternal` at `0x180009a15`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009a6d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009a7b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009b48`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009b56`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009a6d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009a7b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009b48`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009b56`

## pseudocode

```c
__int64 __fastcall CSpp::GetDiffArea(
        CSpp *this,
        const unsigned __int16 *a2,
        unsigned int *a3,
        unsigned __int64 *a4,
        unsigned __int64 *a5)
{
  unsigned __int64 *v8; // r14
  __int16 v9; // ax
  unsigned __int16 v10; // dx
  __int64 v11; // rcx
  unsigned __int64 v12; // rdi
  unsigned __int64 v13; // rbx
  unsigned __int64 v14; // rsi
  int v15; // eax
  ULONGLONG v16; // rdx
  unsigned int v17; // ebx
  __int64 v18; // rdx
  __int64 v19; // r8
  int ProviderMgmtInterfaceInternal; // [rsp+30h] [rbp-91h] BYREF
  __int16 v22; // [rsp+34h] [rbp-8Dh]
  __int16 v23; // [rsp+36h] [rbp-8Bh]
  __int64 v24; // [rsp+68h] [rbp-59h] BYREF
  LPCWSTR lpDirectoryName[2]; // [rsp+70h] [rbp-51h] BYREF
  union _ULARGE_INTEGER TotalNumberOfFreeBytes; // [rsp+80h] [rbp-41h] BYREF
  _ULARGE_INTEGER FreeBytesAvailableToCaller; // [rsp+88h] [rbp-39h] BYREF
  LPVOID pv[2]; // [rsp+90h] [rbp-31h] BYREF
  LPVOID v29[2]; // [rsp+A0h] [rbp-21h]
  __int128 v30; // [rsp+B0h] [rbp-11h]
  GUID v31; // [rsp+C0h] [rbp-1h] BYREF
  __int128 v32[4]; // [rsp+D0h] [rbp+Fh] BYREF
  int v33; // [rsp+128h] [rbp+67h] BYREF
  union _ULARGE_INTEGER TotalNumberOfBytes; // [rsp+130h] [rbp+6Fh] BYREF
  __int64 v35; // [rsp+138h] [rbp+77h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 201, &WPP_c4639252eff5306510cbdeb3ef3cc4de_Traceguids);
  CSxFunctionTracer::CSxFunctionTracer(
    (CSxFunctionTracer *)&ProviderMgmtInterfaceInternal,
    "CSpp::GetDiffArea",
    11679,
    1);
  ATL::CComPtr<IVssBackupComponents>::CComPtr<IVssBackupComponents>(&v24);
  ATL::CComPtr<IVssBackupComponents>::CComPtr<IVssBackupComponents>(&v35);
  lpDirectoryName[0] = &FileName;
  v33 = 0;
  FreeBytesAvailableToCaller.QuadPart = 0;
  TotalNumberOfBytes.QuadPart = 0;
  TotalNumberOfFreeBytes.QuadPart = 0;
  lpDirectoryName[1] = 0;
  *(_OWORD *)pv = 0;
  *(_OWORD *)v29 = 0;
  v30 = 0;
  if ( a3 )
    *a3 = 0;
  if ( a4 )
    *a4 = 0;
  v8 = a5;
  if ( a5 )
    *a5 = 0;
  v9 = 11701;
  if ( a2 && (v22 = 11701, v9 = 11702, a3) && (v22 = 11702, v9 = 11703, a4) && (v22 = 11703, v9 = 11704, v8) )
  {
    ProviderMgmtInterfaceInternal = 0;
    v22 = 11704;
    ProviderMgmtInterfaceInternal = CBsString::Set((CBsString *)lpDirectoryName, a2);
    v9 = 11706;
    if ( ProviderMgmtInterfaceInternal >= 0 )
    {
      v22 = 11706;
      ProviderMgmtInterfaceInternal = CBsString::Trailing((CBsString *)lpDirectoryName, v10);
      v9 = 11707;
      if ( ProviderMgmtInterfaceInternal >= 0 )
      {
        v22 = 11707;
        if ( GetDiskFreeSpaceExW(
               lpDirectoryName[0],
               &FreeBytesAvailableToCaller,
               &TotalNumberOfBytes,
               &TotalNumberOfFreeBytes) )
        {
          ProviderMgmtInterfaceInternal = 0;
          v31 = IID_IVssDifferentialSoftwareSnapshotMgmt2;
          v32[0] = xmmword_18003B620;
          v22 = 11712;
          ProviderMgmtInterfaceInternal = GetProviderMgmtInterfaceInternal(v32, &v31, &v24);
          v9 = 11716;
          if ( ProviderMgmtInterfaceInternal >= 0 )
          {
            v22 = 11716;
            ProviderMgmtInterfaceInternal = (*(__int64 (__fastcall **)(__int64, LPCWSTR, __int64 *))(*(_QWORD *)v24 + 48LL))(
                                              v24,
                                              lpDirectoryName[0],
                                              &v35);
            v9 = 11717;
            if ( ProviderMgmtInterfaceInternal >= 0 )
            {
              v12 = 0;
              v22 = 11717;
              v13 = 0;
              v14 = -1;
              while ( 1 )
              {
                CoTaskMemFree(pv[1]);
                pv[1] = 0;
                CoTaskMemFree(v29[0]);
                v33 = 0;
                *(_OWORD *)pv = 0;
                *(_OWORD *)v29 = 0;
                v30 = 0;
                v15 = (*(__int64 (__fastcall **)(__int64, __int64, LPVOID *, int *))(*(_QWORD *)v35 + 24LL))(
                        v35,
                        1,
                        pv,
                        &v33);
                ProviderMgmtInterfaceInternal = v15;
                if ( v15 < 0 )
                  break;
                v22 = 11730;
                if ( v15 == 1 )
                {
                  v14 = v12;
                  if ( v12 == -1 )
LABEL_28:
                    LODWORD(v16) = 100;
                  else
                    v16 = (1000 * v12 / TotalNumberOfBytes.QuadPart + 5) / 0xA;
                  *a3 = v16;
                  *a4 = v14;
                  *v8 = v13;
                  v22 = 11767;
                  ProviderMgmtInterfaceInternal = 0;
                  goto LABEL_34;
                }
                if ( v33 == 1 && LODWORD(pv[0]) == 3 )
                {
                  v13 += *((_QWORD *)&v30 + 1);
                  if ( v29[1] == (LPVOID)-1LL )
                    goto LABEL_28;
                  v12 += (unsigned __int64)v29[1];
                }
              }
              v9 = 11730;
            }
          }
        }
        else
        {
          ProviderMgmtInterfaceInternal = GetLastFailureAsHRESULT(v11);
          v9 = 11712;
        }
      }
    }
  }
  else
  {
    ProviderMgmtInterfaceInternal = -2147024809;
  }
  v23 = v9;
LABEL_34:
  CoTaskMemFree(pv[1]);
  pv[1] = 0;
  CoTaskMemFree(v29[0]);
  v29[0] = 0;
  v17 = ProviderMgmtInterfaceInternal;
  CBsString::_Release((unsigned __int16 **)lpDirectoryName);
  ATL::CComPtr<IVssExamineWriterMetadata>::~CComPtr<IVssExamineWriterMetadata>();
  ATL::CComPtr<IVssExamineWriterMetadata>::~CComPtr<IVssExamineWriterMetadata>();
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&ProviderMgmtInterfaceInternal, v18, v19);
  return v17;
}

```

## disassembly

```asm
0x180009850  mov     [rsp-8+arg_0], rbx
0x180009855  push    rbp
0x180009856  push    rsi
0x180009857  push    rdi
0x180009858  push    r12
0x18000985a  push    r13
0x18000985c  push    r14
0x18000985e  push    r15
0x180009860  lea     rbp, [rsp-1Fh]
0x180009865  sub     rsp, 0E0h
0x18000986c  mov     r15, r9
0x18000986f  mov     r12, r8
0x180009872  mov     rbx, rdx
0x180009875  mov     rcx, cs:WPP_GLOBAL_Control
0x18000987c  lea     rax, WPP_GLOBAL_Control
0x180009883  cmp     rcx, rax
0x180009886  jz      short loc_1800098A6
0x180009888  test    dword ptr [rcx+1Ch], 20000000h
0x18000988f  jz      short loc_1800098A6
0x180009891  mov     rcx, [rcx+10h]
0x180009895  lea     r8, WPP_c4639252eff5306510cbdeb3ef3cc4de_Traceguids
0x18000989c  mov     edx, 0C9h
0x1800098a1  call    WPP_SF_
0x1800098a6  mov     r9d, 1; unsigned __int16
0x1800098ac  lea     rdx, aCsppGetdiffare_0; "CSpp::GetDiffArea"
0x1800098b3  mov     r8d, 2D9Fh; unsigned __int16
0x1800098b9  lea     rcx, [rsp+110h+var_E0]; this
0x1800098be  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x1800098c3  lea     rcx, [rbp+4Fh+var_A8]
0x1800098c7  call    ??0?$CComPtr@VIVssBackupComponents@@@ATL@@QEAA@H@Z; ATL::CComPtr<IVssBackupComponents>::CComPtr<IVssBackupComponents>(int)
0x1800098cc  lea     rcx, [rbp+4Fh+arg_18]
0x1800098d0  call    ??0?$CComPtr@VIVssBackupComponents@@@ATL@@QEAA@H@Z; ATL::CComPtr<IVssBackupComponents>::CComPtr<IVssBackupComponents>(int)
0x1800098d5  xor     r13d, r13d
0x1800098d8  lea     rax, FileName
0x1800098df  mov     [rbp+4Fh+lpDirectoryName], rax
0x1800098e3  xorps   xmm0, xmm0
0x1800098e6  mov     [rbp+4Fh+arg_8], r13d
0x1800098ea  mov     qword ptr [rbp+4Fh+FreeBytesAvailableToCaller], r13
0x1800098ee  mov     qword ptr [rbp+4Fh+TotalNumberOfBytes], r13
0x1800098f2  mov     qword ptr [rbp+4Fh+TotalNumberOfFreeBytes], r13
0x1800098f6  mov     [rbp+4Fh+var_98], r13
0x1800098fa  movups  xmmword ptr [rbp+4Fh+pv], xmm0
0x1800098fe  movups  xmmword ptr [rbp+4Fh+var_70], xmm0
0x180009902  movups  [rbp+4Fh+var_60], xmm0
0x180009906  test    r12, r12
0x180009909  jz      short loc_18000990F
0x18000990b  mov     [r12], r13d
0x18000990f  test    r15, r15
0x180009912  jz      short loc_180009917
0x180009914  mov     [r15], r13
0x180009917  mov     r14, [rbp+4Fh+arg_20]
0x18000991b  test    r14, r14
0x18000991e  jz      short loc_180009923
0x180009920  mov     [r14], r13
0x180009923  mov     eax, 2DB5h
0x180009928  test    rbx, rbx
0x18000992b  jz      loc_180009B37
0x180009931  mov     [rsp+110h+var_DC], ax
0x180009936  mov     eax, 2DB6h
0x18000993b  test    r12, r12
0x18000993e  jz      loc_180009B37
0x180009944  mov     [rsp+110h+var_DC], ax
0x180009949  mov     eax, 2DB7h
0x18000994e  test    r15, r15
0x180009951  jz      loc_180009B37
0x180009957  mov     [rsp+110h+var_DC], ax
0x18000995c  mov     eax, 2DB8h
0x180009961  test    r14, r14
0x180009964  jz      loc_180009B37
0x18000996a  mov     rdx, rbx; unsigned __int16 *
0x18000996d  mov     [rsp+110h+var_E0], r13d
0x180009972  lea     rcx, [rbp+4Fh+lpDirectoryName]; this
0x180009976  mov     [rsp+110h+var_DC], ax
0x18000997b  call    ?Set@CBsString@@QEAAJPEBG@Z; CBsString::Set(ushort const *)
0x180009980  mov     [rsp+110h+var_E0], eax
0x180009984  test    eax, eax
0x180009986  mov     eax, 2DBAh
0x18000998b  js      loc_180009B3F
0x180009991  lea     rcx, [rbp+4Fh+lpDirectoryName]; this
0x180009995  mov     [rsp+110h+var_DC], ax
0x18000999a  call    ?Trailing@CBsString@@QEAAJG@Z; CBsString::Trailing(ushort)
0x18000999f  mov     [rsp+110h+var_E0], eax
0x1800099a3  test    eax, eax
0x1800099a5  mov     eax, 2DBBh
0x1800099aa  js      loc_180009B3F
0x1800099b0  mov     rcx, [rbp+4Fh+lpDirectoryName]; lpDirectoryName
0x1800099b4  lea     r9, [rbp+4Fh+TotalNumberOfFreeBytes]; lpTotalNumberOfFreeBytes
0x1800099b8  lea     r8, [rbp+4Fh+TotalNumberOfBytes]; lpTotalNumberOfBytes
0x1800099bc  mov     [rsp+110h+var_DC], ax
0x1800099c1  lea     rdx, [rbp+4Fh+FreeBytesAvailableToCaller]; lpFreeBytesAvailableToCaller
0x1800099c5  call    cs:__imp_GetDiskFreeSpaceExW
0x1800099cb  test    eax, eax
0x1800099cd  jnz     short loc_1800099E2
0x1800099cf  call    GetLastFailureAsHRESULT
0x1800099d4  mov     [rsp+110h+var_E0], eax
0x1800099d8  mov     eax, 2DC0h
0x1800099dd  jmp     loc_180009B3F
0x1800099e2  movups  xmm1, xmmword ptr cs:IID_IVssDifferentialSoftwareSnapshotMgmt2.Data1
0x1800099e9  mov     eax, 2DC0h
0x1800099ee  lea     r8, [rbp+4Fh+var_A8]
0x1800099f2  movups  xmm0, cs:xmmword_18003B620
0x1800099f9  lea     rdx, [rbp+4Fh+var_50]
0x1800099fd  mov     [rsp+110h+var_E0], r13d
0x180009a02  lea     rcx, [rbp+4Fh+var_40]
0x180009a06  movdqa  [rbp+4Fh+var_50], xmm1
0x180009a0b  movdqa  [rbp+4Fh+var_40], xmm0
0x180009a10  mov     [rsp+110h+var_DC], ax
0x180009a15  call    cs:__imp_GetProviderMgmtInterfaceInternal
0x180009a1b  mov     [rsp+110h+var_E0], eax
0x180009a1f  test    eax, eax
0x180009a21  mov     eax, 2DC4h
0x180009a26  js      loc_180009B3F
0x180009a2c  mov     rcx, [rbp+4Fh+var_A8]
0x180009a30  lea     r8, [rbp+4Fh+arg_18]
0x180009a34  mov     rdx, [rbp+4Fh+lpDirectoryName]
0x180009a38  mov     [rsp+110h+var_DC], ax
0x180009a3d  mov     rax, [rcx]
0x180009a40  mov     rax, [rax+30h]
0x180009a44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009a49  mov     [rsp+110h+var_E0], eax
0x180009a4d  test    eax, eax
0x180009a4f  mov     eax, 2DC5h
0x180009a54  js      loc_180009B3F
0x180009a5a  mov     rdi, r13
0x180009a5d  mov     [rsp+110h+var_DC], ax
0x180009a62  mov     rbx, r13
0x180009a65  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180009a69  mov     rcx, [rbp+4Fh+pv+8]; pv
0x180009a6d  call    cs:__imp_CoTaskMemFree
0x180009a73  mov     rcx, [rbp+4Fh+var_70]; pv
0x180009a77  mov     [rbp+4Fh+pv+8], r13
0x180009a7b  call    cs:__imp_CoTaskMemFree
0x180009a81  mov     rcx, [rbp+4Fh+arg_18]
0x180009a85  lea     r9, [rbp+4Fh+arg_8]
0x180009a89  xorps   xmm0, xmm0
0x180009a8c  mov     [rbp+4Fh+arg_8], r13d
0x180009a90  movups  xmmword ptr [rbp+4Fh+pv], xmm0
0x180009a94  lea     r8, [rbp+4Fh+pv]
0x180009a98  mov     edx, 1
0x180009a9d  movups  xmmword ptr [rbp+4Fh+var_70], xmm0
0x180009aa1  movups  [rbp+4Fh+var_60], xmm0
0x180009aa5  mov     rax, [rcx]
0x180009aa8  mov     rax, [rax+18h]
0x180009aac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009ab1  mov     [rsp+110h+var_E0], eax
0x180009ab5  test    eax, eax
0x180009ab7  js      short loc_180009B30
0x180009ab9  mov     ecx, 2DD2h
0x180009abe  mov     [rsp+110h+var_DC], cx
0x180009ac3  cmp     eax, 1
0x180009ac6  jz      short loc_180009AE4
0x180009ac8  cmp     [rbp+4Fh+arg_8], 1
0x180009acc  jnz     short loc_180009A69
0x180009ace  cmp     dword ptr [rbp+4Fh+pv], 3
0x180009ad2  jnz     short loc_180009A69
0x180009ad4  add     rbx, qword ptr [rbp+4Fh+var_60+8]
0x180009ad8  cmp     [rbp+4Fh+var_70+8], rsi
0x180009adc  jz      short loc_180009AEC
0x180009ade  add     rdi, [rbp+4Fh+var_70+8]
0x180009ae2  jmp     short loc_180009A69
0x180009ae4  cmp     rdi, rsi
0x180009ae7  mov     rsi, rdi
0x180009aea  jnz     short loc_180009AF3
0x180009aec  mov     edx, 64h ; 'd'
0x180009af1  jmp     short loc_180009B15
0x180009af3  xor     edx, edx
0x180009af5  imul    rax, rdi, 3E8h
0x180009afc  div     qword ptr [rbp+4Fh+TotalNumberOfBytes]
0x180009b00  lea     rcx, [rax+5]
0x180009b04  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180009b0e  mul     rcx
0x180009b11  shr     rdx, 3
0x180009b15  mov     [r12], edx
0x180009b19  mov     eax, 2DF7h
0x180009b1e  mov     [r15], rsi
0x180009b21  mov     [r14], rbx
0x180009b24  mov     [rsp+110h+var_DC], ax
0x180009b29  mov     [rsp+110h+var_E0], r13d
0x180009b2e  jmp     short loc_180009B44
0x180009b30  mov     eax, 2DD2h
0x180009b35  jmp     short loc_180009B3F
0x180009b37  mov     [rsp+110h+var_E0], 80070057h
0x180009b3f  mov     [rsp+110h+var_DA], ax
0x180009b44  mov     rcx, [rbp+4Fh+pv+8]; pv
0x180009b48  call    cs:__imp_CoTaskMemFree
0x180009b4e  mov     rcx, [rbp+4Fh+var_70]; pv
0x180009b52  mov     [rbp+4Fh+pv+8], r13
0x180009b56  call    cs:__imp_CoTaskMemFree
0x180009b5c  mov     [rbp+4Fh+var_70], r13
0x180009b60  mov     ebx, [rsp+110h+var_E0]
0x180009b64  lea     rcx, [rbp+4Fh+lpDirectoryName]; this
0x180009b68  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x180009b6d  lea     rcx, [rbp+4Fh+arg_18]
0x180009b71  call    ??1?$CComPtr@VIVssExamineWriterMetadata@@@ATL@@QEAA@XZ; ATL::CComPtr<IVssExamineWriterMetadata>::~CComPtr<IVssExamineWriterMetadata>(void)
0x180009b76  lea     rcx, [rbp+4Fh+var_A8]
0x180009b7a  call    ??1?$CComPtr@VIVssExamineWriterMetadata@@@ATL@@QEAA@XZ; ATL::CComPtr<IVssExamineWriterMetadata>::~CComPtr<IVssExamineWriterMetadata>(void)
0x180009b7f  lea     rcx, [rsp+110h+var_E0]; this
0x180009b84  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x180009b89  mov     eax, ebx
0x180009b8b  mov     rbx, [rsp+110h+arg_0]
0x180009b93  add     rsp, 0E0h
0x180009b9a  pop     r15
0x180009b9c  pop     r14
0x180009b9e  pop     r13
0x180009ba0  pop     r12
0x180009ba2  pop     rdi
0x180009ba3  pop     rsi
0x180009ba4  pop     rbp
0x180009ba5  retn
```
