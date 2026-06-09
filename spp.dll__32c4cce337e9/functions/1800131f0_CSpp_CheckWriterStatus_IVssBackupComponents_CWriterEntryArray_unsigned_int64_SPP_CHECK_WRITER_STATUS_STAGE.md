# CSpp::_CheckWriterStatus(IVssBackupComponents *,CWriterEntryArray *,unsigned __int64,_SPP_CHECK_WRITER_STATUS_STAGE)

- ea: `0x1800131f0`
- end: `0x1800137a0`
- name: `?_CheckWriterStatus@CSpp@@AEAAJPEAVIVssBackupComponents@@PEAVCWriterEntryArray@@_KW4_SPP_CHECK_WRITER_STATUS_STAGE@@@Z`
- size: `1456`
- prototype: `__int64 __fastcall(__int64, __int64 *, struct CWriterEntryArray *, unsigned __int64, int)`
- caller_count: `3`
- callee_count: `18`
- tags: `broker_com_uri`

## callers

- `0x1800049d0`
- `0x180005e10`
- `0x18001431c`

## callees

- `0x1800021f8`
- `0x18000232c`
- `0x180002bb8`
- `0x180011558`
- `0x1800123e4`
- `0x180012cac`
- `0x1800131f0`
- `0x18001b668`
- `0x18001b834`
- `0x180020710`
- `0x180020fc0`
- `0x1800216c8`
- `0x180025380`
- `0x1800268b4`
- `0x1800269ac`
- `0x180035b76`
- `0x180035bd0`
- `0x180037010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180013389`
- `OLEAUT32!__imp_SysFreeString` at `0x18001339c`
- `OLEAUT32!__imp_SysFreeString` at `0x18001375d`
- `OLEAUT32!__imp_SysFreeString` at `0x180013768`
- `OLEAUT32!__imp_SysFreeString` at `0x180013389`
- `OLEAUT32!__imp_SysFreeString` at `0x18001339c`
- `OLEAUT32!__imp_SysFreeString` at `0x18001375d`
- `OLEAUT32!__imp_SysFreeString` at `0x180013768`

## string_xrefs

- `0x18001325b`: `CSpp::_CheckWriterStatus`

## pseudocode

```c
__int64 __fastcall CSpp::_CheckWriterStatus(
        __int64 a1,
        __int64 *a2,
        struct CWriterEntryArray *a3,
        unsigned __int64 a4,
        int a5)
{
  unsigned int v9; // r15d
  __int16 v10; // ax
  CSpp *v11; // rcx
  int v12; // r12d
  int v13; // eax
  int v14; // ebx
  CSpp *v15; // rcx
  int IsRetryableError; // eax
  __int64 v17; // rcx
  bool v18; // zf
  __int64 v19; // r9
  struct _SPP_WRITER_ERROR_INFO *v20; // rax
  unsigned int v21; // ebx
  __int64 v22; // rdx
  __int64 v23; // r8
  char v25[4]; // [rsp+70h] [rbp-90h] BYREF
  char v26[4]; // [rsp+74h] [rbp-8Ch] BYREF
  BSTR v27; // [rsp+78h] [rbp-88h] BYREF
  enum _VSS_WRITER_STATE v28; // [rsp+80h] [rbp-80h] BYREF
  BSTR bstrString; // [rsp+88h] [rbp-78h] BYREF
  unsigned int v30; // [rsp+90h] [rbp-70h] BYREF
  int v31; // [rsp+98h] [rbp-68h] BYREF
  __int16 v32; // [rsp+9Ch] [rbp-64h]
  __int16 v33; // [rsp+9Eh] [rbp-62h]
  struct IUnknown *v34; // [rsp+D0h] [rbp-30h] BYREF
  unsigned int v35; // [rsp+D8h] [rbp-28h] BYREF
  struct IVssAsync *v36[2]; // [rsp+E0h] [rbp-20h] BYREF
  struct _GUID v37; // [rsp+F0h] [rbp-10h] BYREF
  struct _GUID v38; // [rsp+100h] [rbp+0h] BYREF
  GUID Buf1; // [rsp+110h] [rbp+10h] BYREF
  __int64 v40[2]; // [rsp+120h] [rbp+20h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 67, &WPP_c4639252eff5306510cbdeb3ef3cc4de_Traceguids, a2);
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v31, "CSpp::_CheckWriterStatus", 4716, 1);
  v9 = 0;
  v30 = 0;
  ATL::CComPtr<IVssBackupComponents>::CComPtr<IVssBackupComponents>(v36);
  v27 = 0;
  v28 = VSS_WS_UNKNOWN;
  *(GUID *)v40 = GUID_NULL;
  *(_DWORD *)v25 = 0;
  Buf1 = GUID_NULL;
  bstrString = 0;
  *(_DWORD *)v26 = 0;
  ATL::CComPtr<IVssBackupComponents>::CComPtr<IVssBackupComponents>(&v34);
  v35 = 0;
  if ( !a2 )
  {
    v21 = -2147024809;
    v33 = 4737;
    v31 = -2147024809;
    goto LABEL_55;
  }
  v32 = 4737;
  if ( !a3 && *(_BYTE *)(a1 + 40) && a5 != 3 )
  {
    v10 = 4738;
    v31 = -2147024809;
    goto LABEL_52;
  }
  v31 = 0;
  v32 = 4738;
  v31 = (*(__int64 (__fastcall **)(__int64 *, struct IVssAsync **))(*a2 + 128))(a2, v36);
  v10 = 4740;
  if ( v31 < 0 )
    goto LABEL_52;
  v32 = 4740;
  v31 = CSpp::_AsyncWaitWithTimeout(v11, v36[0], 0xFFFFFFFF, a4);
  v10 = 4741;
  if ( v31 < 0 )
    goto LABEL_52;
  v32 = 4741;
  v31 = (*(__int64 (__fastcall **)(__int64 *, unsigned int *))(*a2 + 136))(a2, &v30);
  v10 = 4743;
  if ( v31 < 0 )
    goto LABEL_52;
  v12 = 0;
  v32 = 4743;
  while ( v9 < v30 )
  {
    SysFreeString(bstrString);
    bstrString = 0;
    SysFreeString(v27);
    v27 = 0;
    ATL::CComPtr<IVssBackupComponentsEx3>::operator=(&v34);
    v13 = (*(__int64 (__fastcall **)(__int64 *, GUID *, struct IUnknown **))*a2)(
            a2,
            &GUID_c191bfbc_b602_4675_8bd1_67d642f529d5,
            &v34);
    if ( v13 != -2147467262 )
    {
      if ( v13 < 0 )
      {
        v31 = v13;
        v10 = 4763;
        goto LABEL_52;
      }
      v31 = ((__int64 (__fastcall *)(struct IUnknown *, _QWORD, __int64 *, GUID *, BSTR *, enum _VSS_WRITER_STATE *, char *, char *, BSTR *))v34->lpVtbl[20].QueryInterface)(
              v34,
              v9,
              v40,
              &Buf1,
              &v27,
              &v28,
              v25,
              v26,
              &bstrString);
      v10 = 4768;
      if ( v31 < 0 )
        goto LABEL_52;
      v32 = 4768;
      goto LABEL_22;
    }
    v31 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, __int64 *, GUID *, BSTR *, enum _VSS_WRITER_STATE *, char *))(*a2 + 152))(
            a2,
            v9,
            v40,
            &Buf1,
            &v27,
            &v28,
            v25);
    if ( v31 < 0 )
    {
      v33 = 4755;
      goto LABEL_53;
    }
    v32 = 4755;
    v14 = *(_DWORD *)v25;
    if ( *(int *)v25 >= 0 )
      goto LABEL_45;
    if ( !memcmp_0(&Buf1, &unk_18003B650, 0x10u) )
    {
      CSpp::_CheckAsrBackupErrorMsg(a1, a2, v27, a5);
LABEL_22:
      v14 = *(_DWORD *)v25;
    }
    if ( v14 >= 0 )
      goto LABEL_45;
    v15 = (CSpp *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000000) != 0 )
    {
      WPP_SF_S_guid__guid_DD(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)&Buf1, (__int64)v40, v14, v26[0]);
      v14 = *(_DWORD *)v25;
    }
    IsRetryableError = CSpp::_IsRetryableError(v15, &dword_18003BB60, 3u, v14);
    v31 = IsRetryableError;
    if ( IsRetryableError < 0 )
    {
      v10 = 4783;
      goto LABEL_52;
    }
    v17 = 4783;
    v32 = 4783;
    if ( IsRetryableError )
    {
      v18 = *(_DWORD *)(a1 + 120) == 4;
    }
    else
    {
      v18 = *(_DWORD *)(a1 + 120) == 4;
      if ( *(_DWORD *)(a1 + 120) < 4u )
      {
        Log_SPP_ERROR_WRITER(
          (struct CSxFunctionTracer *)&v31,
          0x4005u,
          0x12BCu,
          v27,
          bstrString,
          *(int *)v25,
          *(int *)v26);
        v12 = 1;
        goto LABEL_45;
      }
    }
    if ( v18 )
    {
      v17 = (__int64)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000000) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 69, &WPP_c4639252eff5306510cbdeb3ef3cc4de_Traceguids);
    }
    if ( a5 != 3 )
    {
      v19 = *(_QWORD *)(a1 + 32);
      v20 = *(struct _SPP_WRITER_ERROR_INFO **)(v19 + 8);
      LODWORD(v19) = *(_DWORD *)(v19 + 16);
      v37 = *(struct _GUID *)v40;
      v38 = Buf1;
      if ( !(unsigned int)CSpp::_IsWriterAlreadyInBadWritersList((CSpp *)v17, &v38, &v37, v19, v20, &v35) )
        Log_SPP_ERROR_WRITER(
          (struct CSxFunctionTracer *)&v31,
          0x4003u,
          0x12CEu,
          v27,
          bstrString,
          *(int *)v25,
          *(int *)v26);
    }
    if ( !*(_BYTE *)(a1 + 40) || a5 == 3 )
    {
      v31 = *(_DWORD *)v25;
      v10 = 4825;
      if ( *(int *)v25 < 0 )
        goto LABEL_52;
    }
    else
    {
      v38 = *(struct _GUID *)v40;
      v37 = Buf1;
      v31 = CSpp::_CacheBadWritersComponents(
              (CSpp *)a1,
              (struct IVssBackupComponents *)a2,
              a3,
              &v37,
              &v38,
              v27,
              *(unsigned int *)v25,
              *(int *)v26,
              v28,
              0,
              0,
              0,
              0);
      v10 = 4832;
      if ( v31 < 0 )
        goto LABEL_52;
      *(_BYTE *)(a1 + 41) = 1;
    }
    v32 = v10;
LABEL_45:
    ++v9;
  }
  v10 = 4838;
  if ( !v12 )
  {
    v31 = 0;
    v32 = 4838;
    goto LABEL_53;
  }
  v31 = -2147212301;
LABEL_52:
  v33 = v10;
LABEL_53:
  (*(void (__fastcall **)(__int64 *))(*a2 + 144))(a2);
  v21 = v31;
LABEL_55:
  ATL::CComPtr<IVssExamineWriterMetadata>::~CComPtr<IVssExamineWriterMetadata>();
  SysFreeString(bstrString);
  SysFreeString(v27);
  ATL::CComPtr<IVssExamineWriterMetadata>::~CComPtr<IVssExamineWriterMetadata>();
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v31, v22, v23);
  return v21;
}

```

## disassembly

```asm
0x1800131f0  push    rbp
0x1800131f2  push    rbx
0x1800131f3  push    rsi
0x1800131f4  push    rdi
0x1800131f5  push    r12
0x1800131f7  push    r13
0x1800131f9  push    r15
0x1800131fb  lea     rbp, [rsp-40h]
0x180013200  sub     rsp, 140h
0x180013207  mov     rax, cs:__security_cookie
0x18001320e  xor     rax, rsp
0x180013211  mov     [rbp+70h+var_40], rax
0x180013215  mov     rbx, r9
0x180013218  mov     r13, r8
0x18001321b  mov     rdi, rdx
0x18001321e  mov     rsi, rcx
0x180013221  mov     rcx, cs:WPP_GLOBAL_Control
0x180013228  lea     rax, WPP_GLOBAL_Control
0x18001322f  cmp     rcx, rax
0x180013232  jz      short loc_180013255
0x180013234  test    dword ptr [rcx+1Ch], 20000000h
0x18001323b  jz      short loc_180013255
0x18001323d  mov     rcx, [rcx+10h]
0x180013241  lea     r8, WPP_c4639252eff5306510cbdeb3ef3cc4de_Traceguids
0x180013248  mov     edx, 43h ; 'C'
0x18001324d  mov     r9, rdi
0x180013250  call    WPP_SF_q
0x180013255  mov     r9d, 1; unsigned __int16
0x18001325b  lea     rdx, aCsppCheckwrite; "CSpp::_CheckWriterStatus"
0x180013262  mov     r8d, 126Ch; unsigned __int16
0x180013268  lea     rcx, [rbp+70h+var_D8]; this
0x18001326c  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x180013271  xor     r15d, r15d
0x180013274  lea     rcx, [rbp+70h+var_90]
0x180013278  mov     [rbp+70h+var_E0], r15d
0x18001327c  call    ??0?$CComPtr@VIVssBackupComponents@@@ATL@@QEAA@H@Z; ATL::CComPtr<IVssBackupComponents>::CComPtr<IVssBackupComponents>(int)
0x180013281  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180013288  lea     rcx, [rbp+70h+var_A0]
0x18001328c  mov     [rsp+170h+var_F8], r15
0x180013291  mov     [rbp+70h+var_F0], r15d
0x180013295  movdqu  xmmword ptr [rbp+70h+var_50], xmm0
0x18001329a  mov     dword ptr [rsp+170h+var_100], r15d
0x18001329f  movdqu  [rbp+70h+Buf1], xmm0
0x1800132a4  mov     [rbp+70h+bstrString], r15
0x1800132a8  mov     dword ptr [rsp+170h+var_FC], r15d
0x1800132ad  call    ??0?$CComPtr@VIVssBackupComponents@@@ATL@@QEAA@H@Z; ATL::CComPtr<IVssBackupComponents>::CComPtr<IVssBackupComponents>(int)
0x1800132b2  mov     [rbp+70h+var_98], r15d
0x1800132b6  mov     eax, 1281h
0x1800132bb  test    rdi, rdi
0x1800132be  jz      loc_180013744
0x1800132c4  mov     [rbp+70h+var_D4], ax
0x1800132c8  test    r13, r13
0x1800132cb  jnz     short loc_1800132EE
0x1800132cd  cmp     [rsi+28h], r15b
0x1800132d1  jz      short loc_1800132EE
0x1800132d3  cmp     [rbp+70h+arg_20], 3
0x1800132da  jz      short loc_1800132EE
0x1800132dc  mov     ebx, 80070057h
0x1800132e1  mov     eax, 1282h
0x1800132e6  mov     [rbp+70h+var_D8], ebx
0x1800132e9  jmp     loc_180013729
0x1800132ee  mov     eax, 1282h
0x1800132f3  mov     [rbp+70h+var_D8], r15d
0x1800132f7  mov     [rbp+70h+var_D4], ax
0x1800132fb  lea     rdx, [rbp+70h+var_90]
0x1800132ff  mov     rax, [rdi]
0x180013302  mov     rcx, rdi
0x180013305  mov     rax, [rax+80h]
0x18001330c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013311  mov     [rbp+70h+var_D8], eax
0x180013314  test    eax, eax
0x180013316  mov     eax, 1284h
0x18001331b  js      loc_180013729
0x180013321  mov     rdx, [rbp+70h+var_90]; struct IVssAsync *
0x180013325  mov     r9, rbx; unsigned __int64
0x180013328  or      r8d, 0FFFFFFFFh; unsigned int
0x18001332c  mov     [rbp+70h+var_D4], ax
0x180013330  call    ?_AsyncWaitWithTimeout@CSpp@@AEAAJPEAUIVssAsync@@K_K@Z; CSpp::_AsyncWaitWithTimeout(IVssAsync *,ulong,unsigned __int64)
0x180013335  mov     [rbp+70h+var_D8], eax
0x180013338  test    eax, eax
0x18001333a  mov     eax, 1285h
0x18001333f  js      loc_180013729
0x180013345  mov     [rbp+70h+var_D4], ax
0x180013349  lea     rdx, [rbp+70h+var_E0]
0x18001334d  mov     rax, [rdi]
0x180013350  mov     rcx, rdi
0x180013353  mov     rax, [rax+88h]
0x18001335a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001335f  mov     [rbp+70h+var_D8], eax
0x180013362  test    eax, eax
0x180013364  mov     eax, 1287h
0x180013369  js      loc_180013729
0x18001336f  xor     r12d, r12d
0x180013372  mov     [rbp+70h+var_D4], ax
0x180013376  mov     ebx, 1293h
0x18001337b  cmp     r15d, [rbp+70h+var_E0]
0x18001337f  jnb     loc_18001370E
0x180013385  mov     rcx, [rbp+70h+bstrString]; bstrString
0x180013389  call    cs:__imp_SysFreeString
0x18001338f  mov     rcx, [rsp+170h+var_F8]; bstrString
0x180013394  mov     [rbp+70h+bstrString], 0
0x18001339c  call    cs:__imp_SysFreeString
0x1800133a2  lea     rcx, [rbp+70h+var_A0]
0x1800133a6  mov     [rsp+170h+var_F8], 0
0x1800133af  call    ??4?$CComPtr@VIVssBackupComponentsEx3@@@ATL@@QEAAPEAVIVssBackupComponentsEx3@@PEAV2@@Z; ATL::CComPtr<IVssBackupComponentsEx3>::operator=(IVssBackupComponentsEx3 *)
0x1800133b4  mov     rax, [rdi]
0x1800133b7  lea     r8, [rbp+70h+var_A0]
0x1800133bb  lea     rdx, _GUID_c191bfbc_b602_4675_8bd1_67d642f529d5
0x1800133c2  mov     rcx, rdi
0x1800133c5  mov     rax, [rax]
0x1800133c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800133cd  cmp     eax, 80004002h
0x1800133d2  jnz     loc_180013464
0x1800133d8  mov     rax, [rdi]
0x1800133db  lea     rcx, [rsp+170h+var_100]
0x1800133e0  mov     qword ptr [rsp+170h+var_140], rcx
0x1800133e5  lea     r9, [rbp+70h+Buf1]
0x1800133e9  lea     rcx, [rbp+70h+var_F0]
0x1800133ed  mov     edx, r15d
0x1800133f0  mov     [rsp+170h+var_148], rcx
0x1800133f5  lea     r8, [rbp+70h+var_50]
0x1800133f9  mov     rax, [rax+98h]
0x180013400  lea     rcx, [rsp+170h+var_F8]
0x180013405  mov     [rsp+170h+var_150], rcx
0x18001340a  mov     rcx, rdi
0x18001340d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013412  mov     [rbp+70h+var_D8], eax
0x180013415  test    eax, eax
0x180013417  js      loc_1800136F7
0x18001341d  mov     [rbp+70h+var_D4], bx
0x180013421  mov     ebx, dword ptr [rsp+170h+var_100]
0x180013425  test    ebx, ebx
0x180013427  jns     loc_1800136EF
0x18001342d  mov     r8d, 10h; Size
0x180013433  lea     rdx, unk_18003B650; Buf2
0x18001343a  lea     rcx, [rbp+70h+Buf1]; Buf1
0x18001343e  call    memcmp_0
0x180013443  test    eax, eax
0x180013445  jnz     loc_1800134D2
0x18001344b  mov     r9d, [rbp+70h+arg_20]
0x180013452  mov     rdx, rdi
0x180013455  mov     r8, [rsp+170h+var_F8]
0x18001345a  mov     rcx, rsi
0x18001345d  call    ?_CheckAsrBackupErrorMsg@CSpp@@AEAAJPEAVIVssBackupComponents@@PEBGW4_SPP_CHECK_WRITER_STATUS_STAGE@@@Z; CSpp::_CheckAsrBackupErrorMsg(IVssBackupComponents *,ushort const *,_SPP_CHECK_WRITER_STATUS_STAGE)
0x180013462  jmp     short loc_1800134CE
0x180013464  test    eax, eax
0x180013466  js      loc_180013704
0x18001346c  mov     rcx, [rbp+70h+var_A0]
0x180013470  lea     rdx, [rbp+70h+bstrString]
0x180013474  mov     qword ptr [rsp+170h+var_130], rdx
0x180013479  lea     r9, [rbp+70h+Buf1]
0x18001347d  lea     rdx, [rsp+170h+var_FC]
0x180013482  mov     qword ptr [rsp+170h+var_138], rdx
0x180013487  lea     r8, [rbp+70h+var_50]
0x18001348b  mov     rax, [rcx]
0x18001348e  lea     rdx, [rsp+170h+var_100]
0x180013493  mov     qword ptr [rsp+170h+var_140], rdx
0x180013498  lea     rdx, [rbp+70h+var_F0]
0x18001349c  mov     [rsp+170h+var_148], rdx
0x1800134a1  lea     rdx, [rsp+170h+var_F8]
0x1800134a6  mov     [rsp+170h+var_150], rdx
0x1800134ab  mov     edx, r15d
0x1800134ae  mov     rax, [rax+1E0h]
0x1800134b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800134ba  mov     [rbp+70h+var_D8], eax
0x1800134bd  test    eax, eax
0x1800134bf  mov     eax, 12A0h
0x1800134c4  js      loc_180013729
0x1800134ca  mov     [rbp+70h+var_D4], ax
0x1800134ce  mov     ebx, dword ptr [rsp+170h+var_100]
0x1800134d2  test    ebx, ebx
0x1800134d4  jns     loc_1800136EF
0x1800134da  mov     rcx, cs:WPP_GLOBAL_Control
0x1800134e1  lea     rax, WPP_GLOBAL_Control
0x1800134e8  cmp     rcx, rax
0x1800134eb  jz      short loc_180013526
0x1800134ed  test    dword ptr [rcx+1Ch], 8000000h
0x1800134f4  jz      short loc_180013526
0x1800134f6  mov     eax, dword ptr [rsp+170h+var_FC]
0x1800134fa  mov     r9, [rsp+170h+var_F8]
0x1800134ff  mov     rcx, [rcx+10h]; LoggerHandle
0x180013503  mov     dword ptr [rsp+170h+var_138], eax; char
0x180013507  lea     rax, [rbp+70h+var_50]
0x18001350b  mov     dword ptr [rsp+170h+var_140], ebx; char
0x18001350f  mov     [rsp+170h+var_148], rax; __int64
0x180013514  lea     rax, [rbp+70h+Buf1]
0x180013518  mov     [rsp+170h+var_150], rax; __int64
0x18001351d  call    WPP_SF_S_guid__guid_DD
0x180013522  mov     ebx, dword ptr [rsp+170h+var_100]
0x180013526  mov     r9d, ebx; int
0x180013529  lea     rdx, dword_18003BB60; int *
0x180013530  mov     r8d, 3; unsigned int
0x180013536  call    ?_IsRetryableError@CSpp@@AEAAJQEBJKJ@Z; CSpp::_IsRetryableError(long const * const,ulong,long)
0x18001353b  mov     [rbp+70h+var_D8], eax
0x18001353e  test    eax, eax
0x180013540  js      loc_1800136FD
0x180013546  mov     ecx, 12AFh
0x18001354b  mov     [rbp+70h+var_D4], cx
0x18001354f  jnz     short loc_180013592
0x180013551  cmp     dword ptr [rsi+78h], 4
0x180013555  jnb     short loc_180013596
0x180013557  mov     eax, dword ptr [rsp+170h+var_FC]
0x18001355b  lea     r8d, [rcx+0Dh]; unsigned int
0x18001355f  mov     r9, [rsp+170h+var_F8]; unsigned __int16 *
0x180013564  lea     rcx, [rbp+70h+var_D8]; this
0x180013568  mov     dword ptr [rsp+170h+var_140], eax; int
0x18001356c  mov     edx, 4005h; unsigned int
0x180013571  mov     eax, dword ptr [rsp+170h+var_100]
0x180013575  mov     dword ptr [rsp+170h+var_148], eax; int
0x180013579  mov     rax, [rbp+70h+bstrString]
0x18001357d  mov     [rsp+170h+var_150], rax; unsigned __int16 *
0x180013582  call    ?Log_SPP_ERROR_WRITER@@YAJPEAVCSxFunctionTracer@@KKPEBG1JJ@Z; Log_SPP_ERROR_WRITER(CSxFunctionTracer *,ulong,ulong,ushort const *,ushort const *,long,long)
0x180013587  mov     r12d, 1
0x18001358d  jmp     loc_1800136EF
0x180013592  cmp     dword ptr [rsi+78h], 4
0x180013596  jnz     short loc_1800135C9
0x180013598  mov     rcx, cs:WPP_GLOBAL_Control
0x18001359f  lea     rax, WPP_GLOBAL_Control
0x1800135a6  cmp     rcx, rax
0x1800135a9  jz      short loc_1800135C9
0x1800135ab  test    dword ptr [rcx+1Ch], 8000000h
0x1800135b2  jz      short loc_1800135C9
0x1800135b4  mov     rcx, [rcx+10h]
0x1800135b8  lea     r8, WPP_c4639252eff5306510cbdeb3ef3cc4de_Traceguids
0x1800135bf  mov     edx, 45h ; 'E'
0x1800135c4  call    WPP_SF_
0x1800135c9  cmp     [rbp+70h+arg_20], 3
0x1800135d0  jz      short loc_180013641
0x1800135d2  mov     r9, [rsi+20h]
0x1800135d6  lea     rax, [rbp+70h+var_98]
0x1800135da  movaps  xmm0, xmmword ptr [rbp+70h+var_50]
0x1800135de  lea     r8, [rbp+70h+var_80]; struct _GUID *
0x1800135e2  movaps  xmm1, [rbp+70h+Buf1]
0x1800135e6  lea     rdx, [rbp+70h+var_70]; struct _GUID *
0x1800135ea  mov     [rsp+170h+var_148], rax; unsigned int *
0x1800135ef  mov     rax, [r9+8]
0x1800135f3  mov     r9d, [r9+10h]; unsigned int
0x1800135f7  mov     [rsp+170h+var_150], rax; struct _SPP_WRITER_ERROR_INFO *
0x1800135fc  movdqa  xmmword ptr [rbp+70h+var_80.Data1], xmm0
0x180013601  movdqa  xmmword ptr [rbp+70h+var_70.Data1], xmm1
0x180013606  call    ?_IsWriterAlreadyInBadWritersList@CSpp@@AEAAHU_GUID@@0KPEAU_SPP_WRITER_ERROR_INFO@@PEAK@Z; CSpp::_IsWriterAlreadyInBadWritersList(_GUID,_GUID,ulong,_SPP_WRITER_ERROR_INFO *,ulong *)
0x18001360b  test    eax, eax
0x18001360d  jnz     short loc_180013641
0x18001360f  mov     eax, dword ptr [rsp+170h+var_FC]
0x180013613  lea     rcx, [rbp+70h+var_D8]; this
0x180013617  mov     r9, [rsp+170h+var_F8]; unsigned __int16 *
0x18001361c  mov     edx, 4003h; unsigned int
0x180013621  mov     dword ptr [rsp+170h+var_140], eax; int
0x180013625  mov     r8d, 12CEh; unsigned int
0x18001362b  mov     eax, dword ptr [rsp+170h+var_100]
0x18001362f  mov     dword ptr [rsp+170h+var_148], eax; int
0x180013633  mov     rax, [rbp+70h+bstrString]
0x180013637  mov     [rsp+170h+var_150], rax; unsigned __int16 *
0x18001363c  call    ?Log_SPP_ERROR_WRITER@@YAJPEAVCSxFunctionTracer@@KKPEBG1JJ@Z; Log_SPP_ERROR_WRITER(CSxFunctionTracer *,ulong,ulong,ushort const *,ushort const *,long,long)
0x180013641  cmp     byte ptr [rsi+28h], 0
0x180013645  jz      loc_1800136DB
0x18001364b  cmp     [rbp+70h+arg_20], 3
0x180013652  jz      loc_1800136DB
0x180013658  mov     eax, [rbp+70h+var_F0]
0x18001365b  lea     r9, [rbp+70h+var_80]; struct _GUID
0x18001365f  movaps  xmm0, xmmword ptr [rbp+70h+var_50]
0x180013663  mov     r8, r13; struct CWriterEntryArray *
0x180013666  movaps  xmm1, [rbp+70h+Buf1]
0x18001366a  mov     rdx, rdi; struct IVssBackupComponents *
0x18001366d  mov     [rsp+170h+var_110], 0; unsigned __int16 *
0x180013676  mov     rcx, rsi; this
0x180013679  mov     [rsp+170h+var_118], 0; int
0x180013681  mov     [rsp+170h+var_120], 0; unsigned __int16 *
0x18001368a  mov     [rsp+170h+var_128], 0; unsigned __int16 *
0x180013693  mov     [rsp+170h+var_130], eax; enum _VSS_WRITER_STATE
0x180013697  mov     eax, dword ptr [rsp+170h+var_FC]
0x18001369b  mov     dword ptr [rsp+170h+var_138], eax; int
0x18001369f  mov     eax, dword ptr [rsp+170h+var_100]
0x1800136a3  mov     dword ptr [rsp+170h+var_140], eax; int
0x1800136a7  mov     rax, [rsp+170h+var_F8]
0x1800136ac  mov     [rsp+170h+var_148], rax; unsigned __int16 *
0x1800136b1  lea     rax, [rbp+70h+var_70]
0x1800136b5  mov     [rsp+170h+var_150], rax; struct _GUID
0x1800136ba  movdqa  xmmword ptr [rbp+70h+var_70.Data1], xmm0
0x1800136bf  movdqa  xmmword ptr [rbp+70h+var_80.Data1], xmm1
0x1800136c4  call    ?_CacheBadWritersComponents@CSpp@@AEAAJPEAVIVssBackupComponents@@PEAVCWriterEntryArray@@U_GUID@@2PEBGJJW4_VSS_WRITER_STATE@@33J3@Z; CSpp::_CacheBadWritersComponents(IVssBackupComponents *,CWriterEntryArray *,_GUID,_GUID,ushort const *,long,long,_VSS_WRITER_STATE,ushort const *,ushort const *,long,ushort const *)
0x1800136c9  mov     [rbp+70h+var_D8], eax
0x1800136cc  test    eax, eax
0x1800136ce  mov     eax, 12E0h
0x1800136d3  js      short loc_180013729
0x1800136d5  mov     byte ptr [rsi+29h], 1
0x1800136d9  jmp     short loc_1800136EB
0x1800136db  mov     eax, dword ptr [rsp+170h+var_100]
0x1800136df  test    eax, eax
0x1800136e1  mov     [rbp+70h+var_D8], eax
0x1800136e4  mov     eax, 12D9h
0x1800136e9  js      short loc_180013729
0x1800136eb  mov     [rbp+70h+var_D4], ax
0x1800136ef  inc     r15d
0x1800136f2  jmp     loc_180013376
0x1800136f7  mov     [rbp+70h+var_D2], bx
0x1800136fb  jmp     short loc_18001372D
0x1800136fd  mov     eax, 12AFh
0x180013702  jmp     short loc_180013729
0x180013704  mov     [rbp+70h+var_D8], eax
  ... truncated ...
```
