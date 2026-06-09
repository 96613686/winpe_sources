# CSpp::_GetSnapshotVolumeList(CSnapshotEntryArray *)

- ea: `0x18001a830`
- end: `0x18001ac3a`
- name: `?_GetSnapshotVolumeList@CSpp@@AEAAJPEAVCSnapshotEntryArray@@@Z`
- size: `1034`
- prototype: `__int64 __fastcall(CSpp *__hidden this, struct CSnapshotEntryArray *)`
- caller_count: `3`
- callee_count: `17`
- tags: `broker_com_uri`

## callers

- `0x180004ff0`
- `0x180005360`
- `0x1800084d0`

## callees

- `0x1800021f8`
- `0x18000232c`
- `0x18000406c`
- `0x1800072b8`
- `0x18000797c`
- `0x18000e208`
- `0x18001a830`
- `0x18001e2dc`
- `0x180020710`
- `0x1800268b4`
- `0x1800269ac`
- `0x18002daf0`
- `0x18003532c`
- `0x1800353c4`
- `0x180035b9a`
- `0x180035bd0`
- `0x180037010`

## import_xrefs

- `VSSAPI!VssFreeSnapshotPropertiesInternal` at `0x18001aa0b`
- `VSSAPI!VssFreeSnapshotPropertiesInternal` at `0x18001ab93`
- `VSSAPI!VssFreeSnapshotPropertiesInternal` at `0x18001aa0b`
- `VSSAPI!VssFreeSnapshotPropertiesInternal` at `0x18001ab93`
- `VSSAPI!CreateVssBackupComponentsInternal` at `0x18001a965`
- `VSSAPI!CreateVssBackupComponentsInternal` at `0x18001a965`

## pseudocode

```c
__int64 __fastcall CSpp::_GetSnapshotVolumeList(CSpp *this, struct CSnapshotEntryArray *a2)
{
  struct CSnapshotEntry *v4; // r14
  int v5; // r12d
  int v6; // edi
  __int64 v7; // rcx
  __int16 v8; // ax
  __int64 v9; // rdx
  CSpp *v10; // rcx
  __int64 v11; // rax
  int v12; // eax
  int v13; // eax
  bool v14; // sf
  unsigned __int16 v15; // dx
  __int64 v16; // rcx
  __int64 v17; // rdx
  __int64 v18; // r8
  int v20; // [rsp+30h] [rbp-D0h] BYREF
  struct IVssBackupComponents *v21; // [rsp+38h] [rbp-C8h] BYREF
  int v22; // [rsp+40h] [rbp-C0h] BYREF
  __int16 v23; // [rsp+44h] [rbp-BCh]
  __int16 v24; // [rsp+46h] [rbp-BAh]
  struct CSnapshotEntry *v25; // [rsp+78h] [rbp-88h] BYREF
  _QWORD v26[2]; // [rsp+80h] [rbp-80h] BYREF
  GUID v27; // [rsp+90h] [rbp-70h] BYREF
  int v28; // [rsp+A0h] [rbp-60h] BYREF
  _OWORD v29[2]; // [rsp+A8h] [rbp-58h] BYREF
  unsigned __int16 *v30; // [rsp+D0h] [rbp-30h]
  unsigned __int16 *v31; // [rsp+D8h] [rbp-28h]
  int v32; // [rsp+120h] [rbp+20h]

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 114, &WPP_c4639252eff5306510cbdeb3ef3cc4de_Traceguids);
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v22, "CSpp::_GetSnapshotVolumeList", 6447, 1);
  ATL::CComPtr<IVssBackupComponents>::CComPtr<IVssBackupComponents>(&v21);
  ATL::CComPtr<IVssBackupComponents>::CComPtr<IVssBackupComponents>(v26);
  v4 = 0;
  v25 = 0;
  v20 = 0;
  v5 = 0;
  memset_0(&v28, 0, 0x88u);
  if ( a2 )
  {
    v7 = *((_QWORD *)this + 13);
    v22 = 0;
    v23 = 6459;
    if ( v7 )
    {
      v27 = GUID_NULL;
      v6 = CSxDiagnostics::LogDiagnostic(v7, 2002, 0, 0, &v27);
      v22 = v6;
      v8 = 6463;
      if ( v6 < 0 )
        goto LABEL_8;
      v23 = 6463;
    }
    v5 = 1;
    CSxRefArray<CSnapshotEntryArray,CSnapshotEntry>::DeleteAll(a2);
    v6 = CreateVssBackupComponentsInternal(&v21, v9);
    v22 = v6;
    v8 = 6469;
    if ( v6 >= 0 )
    {
      v23 = 6469;
      v6 = (*(__int64 (__fastcall **)(struct IVssBackupComponents *, _QWORD))(*(_QWORD *)v21 + 40LL))(v21, 0);
      v22 = v6;
      v8 = 6470;
      if ( v6 >= 0 )
      {
        v23 = 6470;
        v6 = CSpp::_SetSnapshotContext(v10, v21, 0);
        v22 = v6;
        v8 = 6472;
        if ( v6 >= 0 )
        {
          v23 = 6472;
          v11 = *(_QWORD *)v21;
          v27 = GUID_NULL;
          v12 = (*(__int64 (__fastcall **)(struct IVssBackupComponents *, GUID *, __int64, __int64, _QWORD *))(v11 + 344))(
                  v21,
                  &v27,
                  1,
                  3,
                  v26);
          v6 = v12;
          if ( v12 < 0 )
          {
            if ( v12 == -2147212536 )
            {
LABEL_28:
              v6 = 0;
              v23 = 6526;
              goto LABEL_29;
            }
            v22 = v12;
            v8 = 6519;
          }
          else
          {
            while ( 1 )
            {
              VssFreeSnapshotPropertiesInternal(v29);
              memset_0(&v28, 0, 0x88u);
              v6 = (*(__int64 (__fastcall **)(_QWORD, __int64, int *, int *))(*(_QWORD *)v26[0] + 24LL))(
                     v26[0],
                     1,
                     &v28,
                     &v20);
              v22 = v6;
              v8 = 6481;
              if ( v6 < 0 )
                break;
              v23 = 6481;
              if ( v6 == 1 || v28 != 3 || v20 != 1 )
                goto LABEL_28;
              if ( v4 )
              {
                v25 = 0;
                CSppStringMapEntry::Release(v4);
              }
              v13 = CSnapshotEntry::CreateInstance(&v25);
              v4 = v25;
              v6 = v13;
              v22 = v13;
              v14 = v13 < 0;
              v8 = 6496;
              if ( v14 )
                break;
              v23 = 6496;
              v6 = CBsString::Set((struct CSnapshotEntry *)((char *)v25 + 8), v31);
              v22 = v6;
              v8 = 6497;
              if ( v6 < 0 )
                break;
              v23 = 6497;
              v6 = CBsString::Set((struct CSnapshotEntry *)((char *)v4 + 24), v30);
              v22 = v6;
              v8 = 6498;
              if ( v6 < 0 )
                break;
              v23 = 6498;
              v6 = CBsString::Trailing((struct CSnapshotEntry *)((char *)v4 + 24), v15);
              v22 = v6;
              v8 = 6500;
              if ( v6 < 0 )
                break;
              v23 = 6500;
              *(_OWORD *)((char *)v4 + 40) = v29[1];
              *(_OWORD *)((char *)v4 + 56) = v29[0];
              *((_DWORD *)v4 + 18) = v32;
              v6 = CSxRefArray<CSxVolumeInfoArray,CSxVolumeInfo>::Append(a2, v4);
              v22 = v6;
              v8 = 6505;
              if ( v6 < 0 )
                break;
              v23 = 6505;
            }
          }
        }
      }
    }
LABEL_8:
    v24 = v8;
    goto LABEL_30;
  }
  v6 = -2147024809;
  v24 = 6459;
LABEL_29:
  v22 = v6;
LABEL_30:
  if ( v28 == 3 )
  {
    VssFreeSnapshotPropertiesInternal(v29);
    memset_0(&v28, 0, 0x88u);
    v6 = v22;
  }
  if ( v5 )
  {
    v16 = *((_QWORD *)this + 13);
    if ( v16 )
    {
      v27 = GUID_NULL;
      CSxDiagnostics::LogDiagnostic(v16, 2002, 1, (unsigned int)v6, &v27);
      v6 = v22;
    }
  }
  if ( v4 )
    CSppStringMapEntry::Release(v4);
  ATL::CComPtr<IVssExamineWriterMetadata>::~CComPtr<IVssExamineWriterMetadata>();
  ATL::CComPtr<IVssExamineWriterMetadata>::~CComPtr<IVssExamineWriterMetadata>();
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v22, v17, v18);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18001a830  mov     [rsp-8+arg_10], rbx
0x18001a835  mov     [rsp-8+arg_18], rsi
0x18001a83a  push    rbp
0x18001a83b  push    rdi
0x18001a83c  push    r12
0x18001a83e  push    r14
0x18001a840  push    r15
0x18001a842  lea     rbp, [rsp-40h]
0x18001a847  sub     rsp, 140h
0x18001a84e  mov     rax, cs:__security_cookie
0x18001a855  xor     rax, rsp
0x18001a858  mov     [rbp+60h+var_30], rax
0x18001a85c  mov     r15, rdx
0x18001a85f  mov     rsi, rcx
0x18001a862  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a869  lea     rax, WPP_GLOBAL_Control
0x18001a870  cmp     rcx, rax
0x18001a873  jz      short loc_18001A893
0x18001a875  test    dword ptr [rcx+1Ch], 20000000h
0x18001a87c  jz      short loc_18001A893
0x18001a87e  mov     rcx, [rcx+10h]
0x18001a882  lea     r8, WPP_c4639252eff5306510cbdeb3ef3cc4de_Traceguids
0x18001a889  mov     edx, 72h ; 'r'
0x18001a88e  call    WPP_SF_
0x18001a893  mov     ebx, 1
0x18001a898  lea     rdx, aCsppGetsnapsho; "CSpp::_GetSnapshotVolumeList"
0x18001a89f  mov     r9d, ebx; unsigned __int16
0x18001a8a2  lea     rcx, [rsp+160h+var_120]; this
0x18001a8a7  mov     r8d, 192Fh; unsigned __int16
0x18001a8ad  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18001a8b2  lea     rcx, [rsp+160h+var_128]
0x18001a8b7  call    ??0?$CComPtr@VIVssBackupComponents@@@ATL@@QEAA@H@Z; ATL::CComPtr<IVssBackupComponents>::CComPtr<IVssBackupComponents>(int)
0x18001a8bc  lea     rcx, [rbp+60h+var_E0]
0x18001a8c0  call    ??0?$CComPtr@VIVssBackupComponents@@@ATL@@QEAA@H@Z; ATL::CComPtr<IVssBackupComponents>::CComPtr<IVssBackupComponents>(int)
0x18001a8c5  xor     r14d, r14d
0x18001a8c8  lea     rcx, [rbp+60h+var_C0]; void *
0x18001a8cc  xor     edx, edx; Val
0x18001a8ce  mov     [rsp+160h+var_E8], r14
0x18001a8d3  mov     r8d, 88h; Size
0x18001a8d9  mov     [rsp+160h+var_130], r14d
0x18001a8de  xor     r12d, r12d
0x18001a8e1  call    memset_0
0x18001a8e6  mov     eax, 193Bh
0x18001a8eb  test    r15, r15
0x18001a8ee  jnz     short loc_18001A8FF
0x18001a8f0  mov     edi, 80070057h
0x18001a8f5  mov     [rsp+160h+var_11A], ax
0x18001a8fa  jmp     loc_18001AB80
0x18001a8ff  mov     rcx, [rsi+68h]
0x18001a903  mov     [rsp+160h+var_120], r12d
0x18001a908  mov     [rsp+160h+var_11C], ax
0x18001a90d  test    rcx, rcx
0x18001a910  jz      short loc_18001A955
0x18001a912  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18001a919  lea     rax, [rbp+60h+var_D0]
0x18001a91d  xor     r9d, r9d
0x18001a920  xor     r8d, r8d
0x18001a923  mov     [rsp+160h+var_140], rax
0x18001a928  mov     edx, 7D2h
0x18001a92d  movdqu  [rbp+60h+var_D0], xmm0
0x18001a932  call    ?LogDiagnostic@CSxDiagnostics@@QEAAJW4SX_DIAG_OPERATION@@W4SX_DIAG_TYPE@@JU_GUID@@@Z; CSxDiagnostics::LogDiagnostic(SX_DIAG_OPERATION,SX_DIAG_TYPE,long,_GUID)
0x18001a937  mov     edi, eax
0x18001a939  mov     [rsp+160h+var_120], eax
0x18001a93d  test    eax, eax
0x18001a93f  mov     eax, 193Fh
0x18001a944  jns     short loc_18001A950
0x18001a946  mov     [rsp+160h+var_11A], ax
0x18001a94b  jmp     loc_18001AB84
0x18001a950  mov     [rsp+160h+var_11C], ax
0x18001a955  mov     rcx, r15
0x18001a958  mov     r12d, ebx
0x18001a95b  call    ?DeleteAll@?$CSxRefArray@VCSnapshotEntryArray@@VCSnapshotEntry@@@@QEAAXXZ; CSxRefArray<CSnapshotEntryArray,CSnapshotEntry>::DeleteAll(void)
0x18001a960  lea     rcx, [rsp+160h+var_128]
0x18001a965  call    cs:__imp_CreateVssBackupComponentsInternal
0x18001a96b  mov     edi, eax
0x18001a96d  mov     [rsp+160h+var_120], eax
0x18001a971  test    eax, eax
0x18001a973  mov     eax, 1945h
0x18001a978  js      short loc_18001A946
0x18001a97a  mov     rcx, [rsp+160h+var_128]
0x18001a97f  xor     edx, edx
0x18001a981  mov     [rsp+160h+var_11C], ax
0x18001a986  mov     rax, [rcx]
0x18001a989  mov     rax, [rax+28h]
0x18001a98d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a992  mov     edi, eax
0x18001a994  mov     [rsp+160h+var_120], eax
0x18001a998  test    eax, eax
0x18001a99a  mov     eax, 1946h
0x18001a99f  js      short loc_18001A946
0x18001a9a1  mov     rdx, [rsp+160h+var_128]; struct IVssBackupComponents *
0x18001a9a6  xor     r8d, r8d; unsigned int
0x18001a9a9  mov     [rsp+160h+var_11C], ax
0x18001a9ae  call    ?_SetSnapshotContext@CSpp@@AEAAJPEAVIVssBackupComponents@@K@Z; CSpp::_SetSnapshotContext(IVssBackupComponents *,ulong)
0x18001a9b3  mov     edi, eax
0x18001a9b5  mov     [rsp+160h+var_120], eax
0x18001a9b9  test    eax, eax
0x18001a9bb  mov     eax, 1948h
0x18001a9c0  js      short loc_18001A946
0x18001a9c2  mov     rcx, [rsp+160h+var_128]
0x18001a9c7  lea     rdx, [rbp+60h+var_E0]
0x18001a9cb  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18001a9d2  mov     [rsp+160h+var_11C], ax
0x18001a9d7  mov     r9d, 3
0x18001a9dd  mov     [rsp+160h+var_140], rdx
0x18001a9e2  mov     r8d, ebx
0x18001a9e5  mov     rax, [rcx]
0x18001a9e8  lea     rdx, [rbp+60h+var_D0]
0x18001a9ec  movdqu  [rbp+60h+var_D0], xmm0
0x18001a9f1  mov     rax, [rax+158h]
0x18001a9f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a9fd  mov     edi, eax
0x18001a9ff  test    eax, eax
0x18001aa01  js      loc_18001AB5F
0x18001aa07  lea     rcx, [rbp+60h+var_B8]
0x18001aa0b  call    cs:__imp_VssFreeSnapshotPropertiesInternal
0x18001aa11  xor     edx, edx; Val
0x18001aa13  lea     rcx, [rbp+60h+var_C0]; void *
0x18001aa17  mov     r8d, 88h; Size
0x18001aa1d  call    memset_0
0x18001aa22  mov     rcx, [rbp+60h+var_E0]
0x18001aa26  lea     r9, [rsp+160h+var_130]
0x18001aa2b  lea     r8, [rbp+60h+var_C0]
0x18001aa2f  mov     edx, ebx
0x18001aa31  mov     rax, [rcx]
0x18001aa34  mov     rax, [rax+18h]
0x18001aa38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001aa3d  mov     edi, eax
0x18001aa3f  mov     [rsp+160h+var_120], eax
0x18001aa43  test    eax, eax
0x18001aa45  mov     eax, 1951h
0x18001aa4a  js      loc_18001A946
0x18001aa50  mov     [rsp+160h+var_11C], ax
0x18001aa55  cmp     edi, ebx
0x18001aa57  jz      loc_18001AB74
0x18001aa5d  cmp     [rbp+60h+var_C0], 3
0x18001aa61  jnz     loc_18001AB74
0x18001aa67  cmp     [rsp+160h+var_130], ebx
0x18001aa6b  jnz     loc_18001AB74
0x18001aa71  test    r14, r14
0x18001aa74  jz      short loc_18001AA87
0x18001aa76  mov     rcx, r14; this
0x18001aa79  mov     [rsp+160h+var_E8], 0
0x18001aa82  call    ?Release@CSppStringMapEntry@@QEAAKXZ; CSppStringMapEntry::Release(void)
0x18001aa87  lea     rcx, [rsp+160h+var_E8]; struct CSnapshotEntry **
0x18001aa8c  call    ?CreateInstance@CSnapshotEntry@@SAJPEAPEAV1@@Z; CSnapshotEntry::CreateInstance(CSnapshotEntry * *)
0x18001aa91  mov     r14, [rsp+160h+var_E8]
0x18001aa96  mov     edi, eax
0x18001aa98  mov     [rsp+160h+var_120], eax
0x18001aa9c  test    eax, eax
0x18001aa9e  mov     eax, 1960h
0x18001aaa3  js      loc_18001A946
0x18001aaa9  mov     rdx, [rbp+60h+var_88]; unsigned __int16 *
0x18001aaad  lea     rcx, [r14+8]; this
0x18001aab1  mov     [rsp+160h+var_11C], ax
0x18001aab6  call    ?Set@CBsString@@QEAAJPEBG@Z; CBsString::Set(ushort const *)
0x18001aabb  mov     edi, eax
0x18001aabd  mov     [rsp+160h+var_120], eax
0x18001aac1  test    eax, eax
0x18001aac3  mov     eax, 1961h
0x18001aac8  js      loc_18001A946
0x18001aace  mov     rdx, [rbp+60h+var_90]; unsigned __int16 *
0x18001aad2  lea     rcx, [r14+18h]; this
0x18001aad6  mov     [rsp+160h+var_11C], ax
0x18001aadb  call    ?Set@CBsString@@QEAAJPEBG@Z; CBsString::Set(ushort const *)
0x18001aae0  mov     edi, eax
0x18001aae2  mov     [rsp+160h+var_120], eax
0x18001aae6  test    eax, eax
0x18001aae8  mov     eax, 1962h
0x18001aaed  js      loc_18001A946
0x18001aaf3  lea     rcx, [r14+18h]; this
0x18001aaf7  mov     [rsp+160h+var_11C], ax
0x18001aafc  call    ?Trailing@CBsString@@QEAAJG@Z; CBsString::Trailing(ushort)
0x18001ab01  mov     edi, eax
0x18001ab03  mov     [rsp+160h+var_120], eax
0x18001ab07  test    eax, eax
0x18001ab09  mov     eax, 1964h
0x18001ab0e  js      loc_18001A946
0x18001ab14  movups  xmm0, [rbp+60h+var_A8]
0x18001ab18  mov     [rsp+160h+var_11C], ax
0x18001ab1d  mov     rdx, r14
0x18001ab20  mov     rcx, r15
0x18001ab23  movdqu  xmmword ptr [r14+28h], xmm0
0x18001ab29  movups  xmm1, [rbp+60h+var_B8]
0x18001ab2d  movdqu  xmmword ptr [r14+38h], xmm1
0x18001ab33  mov     eax, [rbp+60h+var_40]
0x18001ab36  mov     [r14+48h], eax
0x18001ab3a  call    ?Append@?$CSxRefArray@VCSxVolumeInfoArray@@VCSxVolumeInfo@@@@QEAAJPEAVCSxVolumeInfo@@@Z; CSxRefArray<CSxVolumeInfoArray,CSxVolumeInfo>::Append(CSxVolumeInfo *)
0x18001ab3f  mov     edi, eax
0x18001ab41  mov     [rsp+160h+var_120], eax
0x18001ab45  test    eax, eax
0x18001ab47  mov     eax, 1969h
0x18001ab4c  js      loc_18001A946
0x18001ab52  mov     [rsp+160h+var_11C], ax
0x18001ab57  mov     ebx, r12d
0x18001ab5a  jmp     loc_18001AA07
0x18001ab5f  cmp     eax, 80042308h
0x18001ab64  jz      short loc_18001AB74
0x18001ab66  mov     [rsp+160h+var_120], eax
0x18001ab6a  mov     eax, 1977h
0x18001ab6f  jmp     loc_18001A946
0x18001ab74  mov     eax, 197Eh
0x18001ab79  xor     edi, edi
0x18001ab7b  mov     [rsp+160h+var_11C], ax
0x18001ab80  mov     [rsp+160h+var_120], edi
0x18001ab84  mov     ebx, 68h ; 'h'
0x18001ab89  cmp     [rbp+60h+var_C0], 3
0x18001ab8d  jnz     short loc_18001ABAC
0x18001ab8f  lea     rcx, [rbp+60h+var_B8]
0x18001ab93  call    cs:__imp_VssFreeSnapshotPropertiesInternal
0x18001ab99  xor     edx, edx; Val
0x18001ab9b  lea     r8d, [rbx+20h]; Size
0x18001ab9f  lea     rcx, [rbp+60h+var_C0]; void *
0x18001aba3  call    memset_0
0x18001aba8  mov     edi, [rsp+160h+var_120]
0x18001abac  test    r12d, r12d
0x18001abaf  jz      short loc_18001ABE6
0x18001abb1  mov     rcx, [rsi+rbx]
0x18001abb5  test    rcx, rcx
0x18001abb8  jz      short loc_18001ABE6
0x18001abba  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18001abc1  lea     rax, [rbp+60h+var_D0]
0x18001abc5  mov     r9d, edi
0x18001abc8  mov     edx, 7D2h
0x18001abcd  mov     [rsp+160h+var_140], rax
0x18001abd2  mov     r8d, 1
0x18001abd8  movdqu  [rbp+60h+var_D0], xmm0
0x18001abdd  call    ?LogDiagnostic@CSxDiagnostics@@QEAAJW4SX_DIAG_OPERATION@@W4SX_DIAG_TYPE@@JU_GUID@@@Z; CSxDiagnostics::LogDiagnostic(SX_DIAG_OPERATION,SX_DIAG_TYPE,long,_GUID)
0x18001abe2  mov     edi, [rsp+160h+var_120]
0x18001abe6  test    r14, r14
0x18001abe9  jz      short loc_18001ABF3
0x18001abeb  mov     rcx, r14; this
0x18001abee  call    ?Release@CSppStringMapEntry@@QEAAKXZ; CSppStringMapEntry::Release(void)
0x18001abf3  lea     rcx, [rbp+60h+var_E0]
0x18001abf7  call    ??1?$CComPtr@VIVssExamineWriterMetadata@@@ATL@@QEAA@XZ; ATL::CComPtr<IVssExamineWriterMetadata>::~CComPtr<IVssExamineWriterMetadata>(void)
0x18001abfc  lea     rcx, [rsp+160h+var_128]
0x18001ac01  call    ??1?$CComPtr@VIVssExamineWriterMetadata@@@ATL@@QEAA@XZ; ATL::CComPtr<IVssExamineWriterMetadata>::~CComPtr<IVssExamineWriterMetadata>(void)
0x18001ac06  lea     rcx, [rsp+160h+var_120]; this
0x18001ac0b  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18001ac10  mov     eax, edi
0x18001ac12  mov     rcx, [rbp+60h+var_30]
0x18001ac16  xor     rcx, rsp; StackCookie
0x18001ac19  call    __security_check_cookie
0x18001ac1e  lea     r11, [rsp+160h+var_20]
0x18001ac26  mov     rbx, [r11+40h]
0x18001ac2a  mov     rsi, [r11+48h]
0x18001ac2e  mov     rsp, r11
0x18001ac31  pop     r15
0x18001ac33  pop     r14
0x18001ac35  pop     r12
0x18001ac37  pop     rdi
0x18001ac38  pop     rbp
0x18001ac39  retn
```
