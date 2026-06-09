# CWriterEntry::_Initialize(IVssExamineWriterMetadata *)

- ea: `0x180024b8c`
- end: `0x180025065`
- name: `?_Initialize@CWriterEntry@@QEAAJPEAVIVssExamineWriterMetadata@@@Z`
- size: `1241`
- prototype: `__int64 __fastcall(CWriterEntry *__hidden this, struct IVssExamineWriterMetadata *)`
- caller_count: `1`
- callee_count: `21`
- tags: `service_task, broker_com_uri`

## callers

- `0x180017960`

## callees

- `0x1800021f8`
- `0x18000232c`
- `0x18000406c`
- `0x180007344`
- `0x18000907c`
- `0x18000cbc0`
- `0x18000dce0`
- `0x18000e080`
- `0x180020710`
- `0x180023254`
- `0x1800236b8`
- `0x180023fc4`
- `0x180024b8c`
- `0x18002506c`
- `0x1800268b4`
- `0x1800269ac`
- `0x18003532c`
- `0x180035b76`
- `0x180035b82`
- `0x180035bd0`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180024fa6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180024fa6`
- `OLEAUT32!__imp_SysFreeString` at `0x180024f50`
- `OLEAUT32!__imp_SysFreeString` at `0x180024fe7`
- `OLEAUT32!__imp_SysFreeString` at `0x18002501b`
- `OLEAUT32!__imp_SysFreeString` at `0x180025023`
- `OLEAUT32!__imp_SysFreeString` at `0x18002502d`
- `OLEAUT32!__imp_SysFreeString` at `0x180024f50`
- `OLEAUT32!__imp_SysFreeString` at `0x180024fe7`
- `OLEAUT32!__imp_SysFreeString` at `0x18002501b`
- `OLEAUT32!__imp_SysFreeString` at `0x180025023`
- `OLEAUT32!__imp_SysFreeString` at `0x18002502d`

## string_xrefs

- `0x180024bf3`: `CWriterEntry::_Initialize`

## pseudocode

```c
__int64 __fastcall CWriterEntry::_Initialize(CWriterEntry *this, struct IVssExamineWriterMetadata *a2)
{
  struct CComponentEntry *v4; // rbx
  CComponentEntry *v5; // rdi
  __int16 v6; // ax
  CComponentEntryArray **v7; // rsi
  CComponentEntryArray *v8; // rcx
  CComponentEntryArray *v9; // rcx
  GUID v10; // xmm1
  int v11; // eax
  bool v12; // cf
  unsigned int i; // r15d
  unsigned int v14; // eax
  int v15; // eax
  bool v16; // sf
  const unsigned __int16 *v17; // rdx
  CComponentEntryArray *v18; // rcx
  unsigned int v19; // r12d
  int v20; // eax
  __int16 v21; // r10
  unsigned int v22; // r15d
  int v23; // eax
  int IsAncestorOf; // eax
  __int64 v25; // rax
  SIZE_T v26; // rsi
  void *v27; // rcx
  unsigned int v28; // esi
  __int64 v29; // rdx
  __int64 v30; // r8
  struct CComponentEntry *v32; // [rsp+40h] [rbp-89h] BYREF
  unsigned int v33; // [rsp+48h] [rbp-81h] BYREF
  BSTR bstrString; // [rsp+50h] [rbp-79h] BYREF
  int Instance; // [rsp+58h] [rbp-71h] BYREF
  __int16 v36; // [rsp+5Ch] [rbp-6Dh]
  __int16 v37; // [rsp+5Eh] [rbp-6Bh]
  int v38; // [rsp+90h] [rbp-39h] BYREF
  CComponentEntry *v39; // [rsp+98h] [rbp-31h] BYREF
  struct IVssWMComponent *v40; // [rsp+A0h] [rbp-29h] BYREF
  int v41; // [rsp+A8h] [rbp-21h] BYREF
  int v42; // [rsp+ACh] [rbp-1Dh] BYREF
  int v43; // [rsp+B0h] [rbp-19h] BYREF
  BSTR v44; // [rsp+B8h] [rbp-11h] BYREF
  __int64 v45; // [rsp+C0h] [rbp-9h] BYREF
  GUID Buf1; // [rsp+C8h] [rbp-1h] BYREF
  GUID v47; // [rsp+D8h] [rbp+Fh] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_42a92c2e2d463d75d3c9fac66a804989_Traceguids);
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&Instance, "CWriterEntry::_Initialize", 56, 1);
  v44 = 0;
  v38 = 0;
  v47 = GUID_NULL;
  v41 = 0;
  Buf1 = GUID_NULL;
  v43 = 0;
  v42 = 0;
  v33 = 0;
  ATL::CComPtr<IVssBackupComponents>::CComPtr<IVssBackupComponents>(&v45);
  ATL::CComPtr<IVssBackupComponents>::CComPtr<IVssBackupComponents>(&v40);
  v4 = 0;
  v5 = 0;
  v32 = 0;
  v39 = 0;
  bstrString = 0;
  v6 = 76;
  if ( !a2 )
  {
    Instance = -2147024809;
LABEL_6:
    v37 = v6;
    goto LABEL_48;
  }
  v7 = (CComponentEntryArray **)((char *)this + 64);
  Instance = 0;
  v8 = (CComponentEntryArray *)*((_QWORD *)this + 8);
  v36 = 76;
  if ( v8 )
  {
    *v7 = 0;
    CComponentEntryArray::Release(v8);
  }
  v9 = *v7;
  if ( *v7 )
  {
    *v7 = 0;
    CComponentEntryArray::Release(v9);
  }
  Instance = CSxVolumeInfoArray::CreateInstance((struct CSxVolumeInfoArray **)this + 8);
  v6 = 82;
  if ( Instance < 0 )
    goto LABEL_6;
  v36 = 82;
  Instance = (*(__int64 (__fastcall **)(struct IVssExamineWriterMetadata *, GUID *, GUID *, BSTR *, int *, int *))(*(_QWORD *)a2 + 24LL))(
               a2,
               &v47,
               &Buf1,
               &v44,
               &v38,
               &v41);
  v6 = 91;
  if ( Instance < 0 )
    goto LABEL_6;
  v36 = 91;
  Instance = CBsString::Set((CWriterEntry *)((char *)this + 8), v44);
  v6 = 96;
  if ( Instance < 0 )
    goto LABEL_6;
  v36 = 96;
  v10 = v47;
  v11 = v38 - 1;
  v12 = v38 == 1;
  *((GUID *)this + 2) = Buf1;
  *((_DWORD *)this + 19) = v12 || v11 == 1;
  *((GUID *)this + 3) = v10;
  *((_DWORD *)this + 20) = memcmp_0(&Buf1, &unk_18003C7A8, 0x10u) == 0;
  Instance = (*(__int64 (__fastcall **)(struct IVssExamineWriterMetadata *, int *, int *, unsigned int *))(*(_QWORD *)a2 + 32LL))(
               a2,
               &v43,
               &v42,
               &v33);
  v6 = 111;
  if ( Instance < 0 )
    goto LABEL_6;
  for ( i = 0; ; ++i )
  {
    v36 = v6;
    v14 = v33;
    if ( i >= v33 )
      break;
    ATL::CComPtrBase<IVssWMComponent>::Release(&v40);
    Instance = (*(__int64 (__fastcall **)(struct IVssExamineWriterMetadata *, _QWORD, struct IVssWMComponent **))(*(_QWORD *)a2 + 56LL))(
                 a2,
                 i,
                 &v40);
    v6 = 122;
    if ( Instance < 0 )
      goto LABEL_6;
    v36 = 122;
    if ( v4 )
    {
      v32 = 0;
      CComponentEntry::Release(v4);
    }
    v15 = CComponentEntry::CreateInstance(&v32);
    v4 = v32;
    v16 = v15 < 0;
    Instance = v15;
    v6 = 128;
    if ( v16 )
      goto LABEL_6;
    v17 = (const unsigned __int16 *)*((_QWORD *)this + 1);
    v36 = 128;
    Instance = CComponentEntry::_Initialize(v32, v17, v40);
    v6 = 130;
    if ( Instance < 0 )
      goto LABEL_6;
    v18 = *v7;
    v36 = 130;
    Instance = CSxRefArray<CSxVolumeInfoArray,CSxVolumeInfo>::Append(v18, v4);
    v6 = 131;
    if ( Instance < 0 )
      goto LABEL_6;
  }
  v19 = 0;
LABEL_25:
  if ( v19 >= v14 )
  {
    SysFreeString(bstrString);
    v25 = *(_QWORD *)a2;
    bstrString = 0;
    Instance = (*(__int64 (__fastcall **)(struct IVssExamineWriterMetadata *, BSTR *))(v25 + 96))(a2, &bstrString);
    v6 = 169;
    if ( Instance < 0 )
      goto LABEL_6;
    v36 = 169;
    if ( ATL::CComBSTR::Length((ATL::CComBSTR *)&bstrString) )
    {
      v26 = 2 * ATL::CComBSTR::Length((ATL::CComBSTR *)&bstrString) + 2;
      v27 = CoTaskMemAlloc(v26);
      *((_QWORD *)this + 3) = v27;
      v6 = 180;
      if ( !v27 )
      {
        Instance = -2147024882;
        goto LABEL_6;
      }
      Instance = 0;
      v36 = 180;
      memcpy_0(v27, bstrString, v26);
    }
  }
  else
  {
    if ( v4 )
    {
      v32 = 0;
      CComponentEntry::Release(v4);
    }
    v20 = CSxRefArray<CWriterEntryArray,CWriterEntry>::Get(*v7, v19, &v32);
    v4 = v32;
    Instance = v20;
    if ( v20 >= 0 )
    {
      v36 = v21;
      v22 = 0;
      *((_DWORD *)v32 + 25) = 1;
      while ( 1 )
      {
        v14 = v33;
        if ( v22 >= v33 )
        {
          ++v19;
          goto LABEL_25;
        }
        if ( v5 )
        {
          v39 = 0;
          CComponentEntry::Release(v5);
        }
        v23 = CSxRefArray<CWriterEntryArray,CWriterEntry>::Get(*v7, v22, &v39);
        v5 = v39;
        v16 = v23 < 0;
        Instance = v23;
        v6 = 149;
        if ( v16 )
          goto LABEL_6;
        v36 = 149;
        IsAncestorOf = CComponentEntry::_IsAncestorOf(v39, v4);
        Instance = IsAncestorOf;
        if ( IsAncestorOf < 0 )
          break;
        v36 = 151;
        if ( !IsAncestorOf && (*((_DWORD *)v4 + 23) || *((_DWORD *)v5 + 23)) )
          *((_DWORD *)v4 + 25) = 0;
        ++v22;
      }
      v6 = 151;
      goto LABEL_6;
    }
    v37 = v21;
  }
LABEL_48:
  v28 = Instance;
  SysFreeString(bstrString);
  if ( v5 )
    CComponentEntry::Release(v5);
  if ( v4 )
    CComponentEntry::Release(v4);
  ATL::CComPtr<IVssExamineWriterMetadata>::~CComPtr<IVssExamineWriterMetadata>();
  ATL::CComPtr<IVssExamineWriterMetadata>::~CComPtr<IVssExamineWriterMetadata>();
  SysFreeString(0);
  SysFreeString(0);
  SysFreeString(v44);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&Instance, v29, v30);
  return v28;
}

```

## disassembly

```asm
0x180024b8c  mov     [rsp-8+arg_10], rbx
0x180024b91  push    rbp
0x180024b92  push    rsi
0x180024b93  push    rdi
0x180024b94  push    r12
0x180024b96  push    r13
0x180024b98  push    r14
0x180024b9a  push    r15
0x180024b9c  lea     rbp, [rsp-27h]
0x180024ba1  sub     rsp, 0F0h
0x180024ba8  mov     rax, cs:__security_cookie
0x180024baf  xor     rax, rsp
0x180024bb2  mov     [rbp+57h+var_38], rax
0x180024bb6  mov     r14, rdx
0x180024bb9  mov     r13, rcx
0x180024bbc  mov     rcx, cs:WPP_GLOBAL_Control
0x180024bc3  lea     rax, WPP_GLOBAL_Control
0x180024bca  cmp     rcx, rax
0x180024bcd  jz      short loc_180024BED
0x180024bcf  test    dword ptr [rcx+1Ch], 20000000h
0x180024bd6  jz      short loc_180024BED
0x180024bd8  mov     rcx, [rcx+10h]
0x180024bdc  lea     r8, WPP_42a92c2e2d463d75d3c9fac66a804989_Traceguids
0x180024be3  mov     edx, 0Ah
0x180024be8  call    WPP_SF_
0x180024bed  mov     r9d, 1; unsigned __int16
0x180024bf3  lea     rdx, aCwriterentryIn; "CWriterEntry::_Initialize"
0x180024bfa  lea     rcx, [rbp+57h+var_C8]; this
0x180024bfe  lea     r8d, [r9+37h]; unsigned __int16
0x180024c02  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x180024c07  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180024c0e  lea     rcx, [rbp+57h+var_60]
0x180024c12  mov     [rbp+57h+var_68], 0
0x180024c1a  mov     [rbp+57h+var_90], 0
0x180024c21  movdqu  [rbp+57h+var_48], xmm0
0x180024c26  mov     [rbp+57h+var_78], 0
0x180024c2d  movdqu  [rbp+57h+Buf1], xmm0
0x180024c32  mov     [rbp+57h+var_70], 0
0x180024c39  mov     [rbp+57h+var_74], 0
0x180024c40  mov     [rsp+120h+var_D8], 0
0x180024c48  call    ??0?$CComPtr@VIVssBackupComponents@@@ATL@@QEAA@H@Z; ATL::CComPtr<IVssBackupComponents>::CComPtr<IVssBackupComponents>(int)
0x180024c4d  lea     rcx, [rbp+57h+var_80]
0x180024c51  call    ??0?$CComPtr@VIVssBackupComponents@@@ATL@@QEAA@H@Z; ATL::CComPtr<IVssBackupComponents>::CComPtr<IVssBackupComponents>(int)
0x180024c56  xor     ebx, ebx
0x180024c58  xor     edi, edi
0x180024c5a  mov     [rsp+120h+var_E0], rbx
0x180024c5f  mov     [rbp+57h+var_88], rdi
0x180024c63  mov     [rbp+57h+bstrString], rbx
0x180024c67  lea     eax, [rbx+4Ch]
0x180024c6a  test    r14, r14
0x180024c6d  jnz     short loc_180024C7F
0x180024c6f  mov     [rbp+57h+var_C8], 80070057h
0x180024c76  mov     [rbp+57h+var_C2], ax
0x180024c7a  jmp     loc_180024FE0
0x180024c7f  lea     rsi, [r13+40h]
0x180024c83  mov     [rbp+57h+var_C8], ebx
0x180024c86  mov     rcx, [rsi]; this
0x180024c89  mov     [rbp+57h+var_C4], ax
0x180024c8d  test    rcx, rcx
0x180024c90  jz      short loc_180024C9A
0x180024c92  mov     [rsi], rbx
0x180024c95  call    ?Release@CComponentEntryArray@@QEAAKXZ; CComponentEntryArray::Release(void)
0x180024c9a  mov     rcx, [rsi]; this
0x180024c9d  test    rcx, rcx
0x180024ca0  jz      short loc_180024CAA
0x180024ca2  mov     [rsi], rbx
0x180024ca5  call    ?Release@CComponentEntryArray@@QEAAKXZ; CComponentEntryArray::Release(void)
0x180024caa  mov     rcx, rsi; struct CSxVolumeInfoArray **
0x180024cad  call    ?CreateInstance@CSxVolumeInfoArray@@SAJPEAPEAV1@@Z; CSxVolumeInfoArray::CreateInstance(CSxVolumeInfoArray * *)
0x180024cb2  mov     [rbp+57h+var_C8], eax
0x180024cb5  test    eax, eax
0x180024cb7  mov     eax, 52h ; 'R'
0x180024cbc  js      short loc_180024C76
0x180024cbe  mov     [rbp+57h+var_C4], ax
0x180024cc2  lea     rcx, [rbp+57h+var_78]
0x180024cc6  mov     rax, [r14]
0x180024cc9  lea     r9, [rbp+57h+var_68]
0x180024ccd  mov     [rsp+120h+var_F8], rcx
0x180024cd2  lea     r8, [rbp+57h+Buf1]
0x180024cd6  lea     rcx, [rbp+57h+var_90]
0x180024cda  mov     [rsp+120h+var_100], rcx
0x180024cdf  lea     rdx, [rbp+57h+var_48]
0x180024ce3  mov     rax, [rax+18h]
0x180024ce7  mov     rcx, r14
0x180024cea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024cef  mov     [rbp+57h+var_C8], eax
0x180024cf2  test    eax, eax
0x180024cf4  mov     eax, 5Bh ; '['
0x180024cf9  js      loc_180024C76
0x180024cff  mov     rdx, [rbp+57h+var_68]; unsigned __int16 *
0x180024d03  lea     rcx, [r13+8]; this
0x180024d07  mov     [rbp+57h+var_C4], ax
0x180024d0b  call    ?Set@CBsString@@QEAAJPEBG@Z; CBsString::Set(ushort const *)
0x180024d10  mov     [rbp+57h+var_C8], eax
0x180024d13  test    eax, eax
0x180024d15  mov     eax, 60h ; '`'
0x180024d1a  js      loc_180024C76
0x180024d20  movups  xmm0, [rbp+57h+Buf1]
0x180024d24  xor     ecx, ecx
0x180024d26  mov     [rbp+57h+var_C4], ax
0x180024d2a  mov     eax, [rbp+57h+var_90]
0x180024d2d  lea     rdx, unk_18003C7A8; Buf2
0x180024d34  movups  xmm1, [rbp+57h+var_48]
0x180024d38  dec     eax
0x180024d3a  mov     r8d, 10h; Size
0x180024d40  cmp     eax, 1
0x180024d43  movdqu  xmmword ptr [r13+20h], xmm0
0x180024d49  setbe   cl
0x180024d4c  mov     [r13+4Ch], ecx
0x180024d50  lea     rcx, [rbp+57h+Buf1]; Buf1
0x180024d54  movdqu  xmmword ptr [r13+30h], xmm1
0x180024d5a  call    memcmp_0
0x180024d5f  xor     ecx, ecx
0x180024d61  lea     r9, [rsp+120h+var_D8]
0x180024d66  test    eax, eax
0x180024d68  lea     r8, [rbp+57h+var_74]
0x180024d6c  lea     rdx, [rbp+57h+var_70]
0x180024d70  setz    cl
0x180024d73  mov     [r13+50h], ecx
0x180024d77  mov     rcx, r14
0x180024d7a  mov     rax, [r14]
0x180024d7d  mov     rax, [rax+20h]
0x180024d81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024d86  mov     [rbp+57h+var_C8], eax
0x180024d89  test    eax, eax
0x180024d8b  mov     eax, 6Fh ; 'o'
0x180024d90  js      loc_180024C76
0x180024d96  xor     r15d, r15d
0x180024d99  mov     [rbp+57h+var_C4], ax
0x180024d9d  mov     eax, [rsp+120h+var_D8]
0x180024da1  cmp     r15d, eax
0x180024da4  jnb     loc_180024E59
0x180024daa  lea     rcx, [rbp+57h+var_80]
0x180024dae  call    ?Release@?$CComPtrBase@VIVssWMComponent@@@ATL@@QEAAXXZ; ATL::CComPtrBase<IVssWMComponent>::Release(void)
0x180024db3  mov     rax, [r14]
0x180024db6  lea     r8, [rbp+57h+var_80]
0x180024dba  mov     edx, r15d
0x180024dbd  mov     rcx, r14
0x180024dc0  mov     rax, [rax+38h]
0x180024dc4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024dc9  mov     [rbp+57h+var_C8], eax
0x180024dcc  test    eax, eax
0x180024dce  mov     eax, 7Ah ; 'z'
0x180024dd3  js      loc_180024C76
0x180024dd9  mov     [rbp+57h+var_C4], ax
0x180024ddd  test    rbx, rbx
0x180024de0  jz      short loc_180024DEF
0x180024de2  mov     rcx, rbx; this
0x180024de5  mov     [rsp+120h+var_E0], rdi
0x180024dea  call    ?Release@CComponentEntry@@QEAAKXZ; CComponentEntry::Release(void)
0x180024def  lea     rcx, [rsp+120h+var_E0]; struct CComponentEntry **
0x180024df4  call    ?CreateInstance@CComponentEntry@@SAJPEAPEAV1@@Z; CComponentEntry::CreateInstance(CComponentEntry * *)
0x180024df9  mov     rbx, [rsp+120h+var_E0]
0x180024dfe  test    eax, eax
0x180024e00  mov     [rbp+57h+var_C8], eax
0x180024e03  mov     eax, 80h
0x180024e08  js      loc_180024C76
0x180024e0e  mov     r8, [rbp+57h+var_80]; struct IVssWMComponent *
0x180024e12  mov     rcx, rbx; this
0x180024e15  mov     rdx, [r13+8]; unsigned __int16 *
0x180024e19  mov     [rbp+57h+var_C4], ax
0x180024e1d  call    ?_Initialize@CComponentEntry@@QEAAJPEBGPEAVIVssWMComponent@@@Z; CComponentEntry::_Initialize(ushort const *,IVssWMComponent *)
0x180024e22  mov     [rbp+57h+var_C8], eax
0x180024e25  test    eax, eax
0x180024e27  mov     eax, 82h
0x180024e2c  js      loc_180024C76
0x180024e32  mov     rcx, [rsi]
0x180024e35  mov     rdx, rbx
0x180024e38  mov     [rbp+57h+var_C4], ax
0x180024e3c  call    ?Append@?$CSxRefArray@VCSxVolumeInfoArray@@VCSxVolumeInfo@@@@QEAAJPEAVCSxVolumeInfo@@@Z; CSxRefArray<CSxVolumeInfoArray,CSxVolumeInfo>::Append(CSxVolumeInfo *)
0x180024e41  mov     [rbp+57h+var_C8], eax
0x180024e44  test    eax, eax
0x180024e46  mov     eax, 83h
0x180024e4b  js      loc_180024C76
0x180024e51  inc     r15d
0x180024e54  jmp     loc_180024D99
0x180024e59  xor     r12d, r12d
0x180024e5c  mov     r10d, 8Eh
0x180024e62  cmp     r12d, eax
0x180024e65  jnb     loc_180024F4C
0x180024e6b  test    rbx, rbx
0x180024e6e  jz      short loc_180024E87
0x180024e70  mov     rcx, rbx; this
0x180024e73  mov     [rsp+120h+var_E0], 0
0x180024e7c  call    ?Release@CComponentEntry@@QEAAKXZ; CComponentEntry::Release(void)
0x180024e81  mov     r10d, 8Eh
0x180024e87  mov     rcx, [rsi]
0x180024e8a  lea     r8, [rsp+120h+var_E0]
0x180024e8f  mov     edx, r12d
0x180024e92  call    ?Get@?$CSxRefArray@VCWriterEntryArray@@VCWriterEntry@@@@QEAAJKPEAPEAVCWriterEntry@@@Z; CSxRefArray<CWriterEntryArray,CWriterEntry>::Get(ulong,CWriterEntry * *)
0x180024e97  mov     rbx, [rsp+120h+var_E0]
0x180024e9c  mov     [rbp+57h+var_C8], eax
0x180024e9f  test    eax, eax
0x180024ea1  js      loc_180024F42
0x180024ea7  mov     [rbp+57h+var_C4], r10w
0x180024eac  xor     r15d, r15d
0x180024eaf  mov     dword ptr [rbx+64h], 1
0x180024eb6  mov     eax, [rsp+120h+var_D8]
0x180024eba  cmp     r15d, eax
0x180024ebd  jnb     short loc_180024F30
0x180024ebf  test    rdi, rdi
0x180024ec2  jz      short loc_180024ED4
0x180024ec4  mov     rcx, rdi; this
0x180024ec7  mov     [rbp+57h+var_88], 0
0x180024ecf  call    ?Release@CComponentEntry@@QEAAKXZ; CComponentEntry::Release(void)
0x180024ed4  mov     rcx, [rsi]
0x180024ed7  lea     r8, [rbp+57h+var_88]
0x180024edb  mov     edx, r15d
0x180024ede  call    ?Get@?$CSxRefArray@VCWriterEntryArray@@VCWriterEntry@@@@QEAAJKPEAPEAVCWriterEntry@@@Z; CSxRefArray<CWriterEntryArray,CWriterEntry>::Get(ulong,CWriterEntry * *)
0x180024ee3  mov     rdi, [rbp+57h+var_88]
0x180024ee7  test    eax, eax
0x180024ee9  mov     [rbp+57h+var_C8], eax
0x180024eec  mov     eax, 95h
0x180024ef1  js      loc_180024C76
0x180024ef7  mov     rdx, rbx; struct CComponentEntry *
0x180024efa  mov     [rbp+57h+var_C4], ax
0x180024efe  mov     rcx, rdi; this
0x180024f01  call    ?_IsAncestorOf@CComponentEntry@@QEAAJPEAV1@@Z; CComponentEntry::_IsAncestorOf(CComponentEntry *)
0x180024f06  mov     [rbp+57h+var_C8], eax
0x180024f09  test    eax, eax
0x180024f0b  js      short loc_180024F38
0x180024f0d  mov     ecx, 97h
0x180024f12  mov     [rbp+57h+var_C4], cx
0x180024f16  jnz     short loc_180024F2B
0x180024f18  cmp     dword ptr [rbx+5Ch], 0
0x180024f1c  jnz     short loc_180024F24
0x180024f1e  cmp     dword ptr [rdi+5Ch], 0
0x180024f22  jz      short loc_180024F2B
0x180024f24  mov     dword ptr [rbx+64h], 0
0x180024f2b  inc     r15d
0x180024f2e  jmp     short loc_180024EB6
0x180024f30  inc     r12d
0x180024f33  jmp     loc_180024E5C
0x180024f38  mov     eax, 97h
0x180024f3d  jmp     loc_180024C76
0x180024f42  mov     [rbp+57h+var_C2], r10w
0x180024f47  jmp     loc_180024FE0
0x180024f4c  mov     rcx, [rbp+57h+bstrString]; bstrString
0x180024f50  call    cs:__imp_SysFreeString
0x180024f56  mov     rax, [r14]
0x180024f59  lea     rdx, [rbp+57h+bstrString]
0x180024f5d  mov     rcx, r14
0x180024f60  mov     [rbp+57h+bstrString], 0
0x180024f68  mov     rax, [rax+60h]
0x180024f6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024f71  mov     [rbp+57h+var_C8], eax
0x180024f74  test    eax, eax
0x180024f76  mov     eax, 0A9h
0x180024f7b  js      loc_180024C76
0x180024f81  lea     rcx, [rbp+57h+bstrString]; this
0x180024f85  mov     [rbp+57h+var_C4], ax
0x180024f89  call    ?Length@CComBSTR@ATL@@QEBAIXZ; ATL::CComBSTR::Length(void)
0x180024f8e  test    eax, eax
0x180024f90  jz      short loc_180024FE0
0x180024f92  lea     rcx, [rbp+57h+bstrString]; this
0x180024f96  call    ?Length@CComBSTR@ATL@@QEBAIXZ; ATL::CComBSTR::Length(void)
0x180024f9b  lea     eax, ds:2[rax*2]
0x180024fa2  mov     ecx, eax; cb
0x180024fa4  mov     esi, eax
0x180024fa6  call    cs:__imp_CoTaskMemAlloc
0x180024fac  mov     rcx, rax; void *
0x180024faf  mov     [r13+18h], rax
0x180024fb3  test    rax, rax
0x180024fb6  mov     eax, 0B4h
0x180024fbb  jnz     short loc_180024FC9
0x180024fbd  mov     [rbp+57h+var_C8], 8007000Eh
0x180024fc4  jmp     loc_180024C76
0x180024fc9  mov     rdx, [rbp+57h+bstrString]; Src
0x180024fcd  mov     r8, rsi; Size
0x180024fd0  mov     [rbp+57h+var_C8], 0
0x180024fd7  mov     [rbp+57h+var_C4], ax
0x180024fdb  call    memcpy_0
0x180024fe0  mov     rcx, [rbp+57h+bstrString]; bstrString
0x180024fe4  mov     esi, [rbp+57h+var_C8]
0x180024fe7  call    cs:__imp_SysFreeString
0x180024fed  test    rdi, rdi
0x180024ff0  jz      short loc_180024FFA
0x180024ff2  mov     rcx, rdi; this
0x180024ff5  call    ?Release@CComponentEntry@@QEAAKXZ; CComponentEntry::Release(void)
0x180024ffa  test    rbx, rbx
0x180024ffd  jz      short loc_180025007
0x180024fff  mov     rcx, rbx; this
0x180025002  call    ?Release@CComponentEntry@@QEAAKXZ; CComponentEntry::Release(void)
0x180025007  lea     rcx, [rbp+57h+var_80]
0x18002500b  call    ??1?$CComPtr@VIVssExamineWriterMetadata@@@ATL@@QEAA@XZ; ATL::CComPtr<IVssExamineWriterMetadata>::~CComPtr<IVssExamineWriterMetadata>(void)
0x180025010  lea     rcx, [rbp+57h+var_60]
0x180025014  call    ??1?$CComPtr@VIVssExamineWriterMetadata@@@ATL@@QEAA@XZ; ATL::CComPtr<IVssExamineWriterMetadata>::~CComPtr<IVssExamineWriterMetadata>(void)
0x180025019  xor     ecx, ecx; bstrString
0x18002501b  call    cs:__imp_SysFreeString
0x180025021  xor     ecx, ecx; bstrString
0x180025023  call    cs:__imp_SysFreeString
0x180025029  mov     rcx, [rbp+57h+var_68]; bstrString
0x18002502d  call    cs:__imp_SysFreeString
0x180025033  lea     rcx, [rbp+57h+var_C8]; this
0x180025037  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18002503c  mov     eax, esi
0x18002503e  mov     rcx, [rbp+57h+var_38]
0x180025042  xor     rcx, rsp; StackCookie
0x180025045  call    __security_check_cookie
0x18002504a  mov     rbx, [rsp+120h+arg_10]
  ... truncated ...
```
