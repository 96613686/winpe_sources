# CTokenActivation::InitializeObject(void)

- ea: `0x180038f90`
- end: `0x180039391`
- name: `?InitializeObject@CTokenActivation@@QEAAJXZ`
- size: `1025`
- prototype: `__int64 __fastcall(CTokenActivation *__hidden this)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18001bbdc`

## callees

- `0x180003020`
- `0x180003520`
- `0x180003838`
- `0x180003ed8`
- `0x180004288`
- `0x180004520`
- `0x18001a134`
- `0x180020200`
- `0x1800236b4`
- `0x180038f90`
- `0x1800399c4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180039030`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003914c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800392ba`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800392eb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003931c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003934d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180039030`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003914c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800392ba`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800392eb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003931c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003934d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180039160`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800392cf`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180039300`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180039331`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180039362`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180039160`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800392cf`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180039300`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180039331`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180039362`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180039045`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180039045`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800390ce`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003913c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800390ce`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003913c`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800390b6`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800390b6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800390e3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800390e3`
- `SLC!SLOpen` at `0x18003917a`
- `SLC!SLOpen` at `0x18003917a`

## pseudocode

```c
__int64 __fastcall CTokenActivation::InitializeObject(CTokenActivation *this)
{
  _QWORD *v1; // rsi
  unsigned __int16 *v2; // r14
  int v4; // eax
  unsigned int v5; // edi
  char v6; // r15
  __int64 v7; // rcx
  HANDLE ProcessHeap; // rax
  _QWORD *v9; // rax
  _QWORD *v10; // rcx
  _QWORD *v11; // rax
  HANDLE EventW; // rax
  void *v13; // rcx
  HANDLE v14; // rdi
  signed int LastError; // eax
  _QWORD *v16; // rdi
  void *v17; // rcx
  HANDLE v18; // rax
  HRESULT v19; // eax
  int v20; // eax
  __int64 v21; // rcx
  int v22; // eax
  HANDLE v23; // rax
  unsigned __int16 *v24; // rbx
  HANDLE v25; // rax
  unsigned __int16 *v26; // rbx
  HANDLE v27; // rax
  unsigned __int16 *v28; // rbx
  HANDLE v29; // rax
  _QWORD *v31; // [rsp+20h] [rbp-39h] BYREF
  unsigned __int16 *v32; // [rsp+28h] [rbp-31h] BYREF
  unsigned __int16 *v33; // [rsp+30h] [rbp-29h] BYREF
  unsigned __int16 *v34; // [rsp+38h] [rbp-21h] BYREF
  unsigned __int16 *v35; // [rsp+40h] [rbp-19h] BYREF
  _QWORD *v36; // [rsp+48h] [rbp-11h] BYREF
  struct _tagSL_LICENSING_STATUS v37; // [rsp+50h] [rbp-9h] BYREF

  v1 = 0;
  v2 = 0;
  v36 = 0;
  v35 = 0;
  v34 = 0;
  v33 = 0;
  v32 = 0;
  if ( *((_DWORD *)this + 32) )
  {
    CRWLock2T<CEmptyType>::Done((char *)this + 24);
    *((_DWORD *)this + 32) = 0;
  }
  CArray<CDispatchImplT<IElevationConfig,&_GUID const IID_IElevationConfig,1,0,&_GUID const LIBID_SppComApiLib,1,0>::CTypeInfoItem,unsigned long,CAdaptorDefault,CPoliciesDefault>::SetSize(
    (char *)this + 8,
    0);
  v4 = CRWLock2T<CEmptyType>::Init((char *)this + 24);
  v5 = v4;
  v6 = 1;
  if ( v4 < 0
    || (*((_DWORD *)this + 32) = 1,
        v4 = CDispatchImplT<IOfflineActivationPhoneList,&_GUID const IID_IOfflineActivationPhoneList,1,0,&_GUID const LIBID_SppComApiLib,1,0>::AddTypeLib<1,0>(this),
        v5 = v4,
        v4 < 0) )
  {
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v4);
  }
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v5);
  if ( (v5 & 0x80000000) != 0 )
    goto LABEL_7;
  *((_DWORD *)this + 42) = 24;
  ProcessHeap = GetProcessHeap();
  v9 = HeapAlloc(ProcessHeap, 0, 0x10u);
  v10 = v9;
  if ( v9 )
  {
    *(_DWORD *)v9 = 1;
    v6 = 0;
    v9[1] = 0;
  }
  else
  {
    v10 = 0;
  }
  v11 = 0;
  if ( !v6 )
    v11 = v10;
  v31 = v11;
  if ( v11 )
  {
    v31 = 0;
    v5 = 0;
    v1 = v11;
    v36 = v11;
  }
  else
  {
    v5 = -2147024882;
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147942414LL);
  }
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v5);
  SP<CRefCountWrapper<DH_HANDLE>,SP_COM<CRefCountWrapper<DH_HANDLE>>>::~SP<CRefCountWrapper<DH_HANDLE>,SP_COM<CRefCountWrapper<DH_HANDLE>>>(&v31);
  if ( (v5 & 0x80000000) != 0 )
    goto LABEL_7;
  EventW = CreateEventW(0, 0, 0, 0);
  v13 = (void *)v1[1];
  v14 = EventW;
  if ( v13 )
    CloseHandle(v13);
  if ( !v14 )
  {
    v1[1] = 0;
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError )
    {
      if ( LastError > 0 )
        v5 = (unsigned __int16)LastError | 0x80070000;
    }
    else
    {
      v5 = -2147467259;
    }
    goto LABEL_7;
  }
  v1[1] = v14;
  v16 = (_QWORD *)*((_QWORD *)this + 19);
  v36 = 0;
  if ( v16 && _InterlockedExchangeAdd((volatile signed __int32 *)v16, 0xFFFFFFFF) == 1 )
  {
    v17 = (void *)v16[1];
    if ( v17 )
    {
      CloseHandle(v17);
      v16[1] = 0;
    }
    v18 = GetProcessHeap();
    HeapFree(v18, 0, v16);
  }
  *((_QWORD *)this + 19) = v1;
  v19 = SLOpen((HSLC *)this + 24);
  v5 = v19;
  if ( v19 < 0 )
  {
LABEL_46:
    v7 = (unsigned int)v19;
    goto LABEL_47;
  }
  memset(&v37, 0, sizeof(v37));
  LODWORD(v31) = 0;
  v20 = SPPGetWindowsLicenseStatus(&v37, (enum tagE_LICENSING_CHANNEL *)&v31, 0);
  v5 = v20;
  if ( v20 < 0 )
  {
    v21 = (unsigned int)v20;
LABEL_32:
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v21);
    goto LABEL_37;
  }
  if ( (_DWORD)v31 != 32 && (_DWORD)v31 != 2 )
  {
    v5 = -1073418209;
    v21 = 3221549087LL;
    goto LABEL_32;
  }
  *(SLID *)((char *)this + 200) = v37.SkuId;
LABEL_37:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v5);
  if ( (v5 & 0x80000000) != 0 )
  {
LABEL_7:
    v7 = v5;
LABEL_47:
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v7);
    goto LABEL_48;
  }
  v19 = STRAPI_LoadFromResource(0xABu, &v35);
  v5 = v19;
  if ( v19 < 0 )
    goto LABEL_46;
  v19 = STRAPI_LoadFromResource(0xACu, &v34);
  v5 = v19;
  if ( v19 < 0 )
    goto LABEL_46;
  v19 = STRAPI_LoadFromResource(0xADu, &v33);
  v5 = v19;
  if ( v19 < 0 )
    goto LABEL_46;
  v22 = STRAPI_LoadFromResource(0xAAu, &v32);
  v5 = v22;
  if ( v22 < 0 )
  {
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v22);
    v2 = v32;
    goto LABEL_48;
  }
  v2 = v32;
  v19 = STRAPI_FormatMsg((unsigned __int16 **)this + 32, v35, v32);
  v5 = v19;
  if ( v19 < 0 )
    goto LABEL_46;
  v19 = STRAPI_FormatMsg((unsigned __int16 **)this + 33, v34, v2);
  v5 = v19;
  if ( v19 < 0 )
    goto LABEL_46;
  v19 = STRAPI_FormatMsg((unsigned __int16 **)this + 34, v33, v2);
  v5 = v19;
  if ( v19 < 0 )
    goto LABEL_46;
LABEL_48:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v5);
  if ( v2 )
  {
    v23 = GetProcessHeap();
    HeapFree(v23, 0, v2 - 2);
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  v24 = v33;
  if ( v33 )
  {
    v25 = GetProcessHeap();
    HeapFree(v25, 0, v24 - 2);
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  v26 = v34;
  if ( v34 )
  {
    v27 = GetProcessHeap();
    HeapFree(v27, 0, v26 - 2);
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  v28 = v35;
  if ( v35 )
  {
    v29 = GetProcessHeap();
    HeapFree(v29, 0, v28 - 2);
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  SP<CRefCountWrapper<DH_HANDLE>,SP_COM<CRefCountWrapper<DH_HANDLE>>>::~SP<CRefCountWrapper<DH_HANDLE>,SP_COM<CRefCountWrapper<DH_HANDLE>>>(&v36);
  return v5;
}

```

## disassembly

```asm
0x180038f90  push    rbp
0x180038f92  push    rbx
0x180038f93  push    rsi
0x180038f94  push    rdi
0x180038f95  push    r14
0x180038f97  push    r15
0x180038f99  lea     rbp, [rsp-2Fh]
0x180038f9e  sub     rsp, 88h
0x180038fa5  xor     esi, esi
0x180038fa7  xor     r14d, r14d
0x180038faa  mov     rbx, rcx
0x180038fad  mov     [rbp+57h+var_68], rsi
0x180038fb1  mov     [rbp+57h+var_70], rsi
0x180038fb5  mov     [rbp+57h+var_78], rsi
0x180038fb9  mov     [rbp+57h+var_80], rsi
0x180038fbd  mov     [rbp+57h+var_88], r14
0x180038fc1  cmp     [rcx+80h], esi
0x180038fc7  jz      short loc_180038FD8
0x180038fc9  add     rcx, 18h
0x180038fcd  call    ?Done@?$CRWLock2T@VCEmptyType@@@@QEAAJXZ; CRWLock2T<CEmptyType>::Done(void)
0x180038fd2  mov     [rbx+80h], esi
0x180038fd8  lea     rcx, [rbx+8]
0x180038fdc  xor     edx, edx
0x180038fde  call    ?SetSize@?$CArray@UCTypeInfoItem@?$CDispatchImplT@UIElevationConfig@@$1?IID_IElevationConfig@@3U_GUID@@B$00$0A@$1?LIBID_SppComApiLib@@3U3@B$00$0A@@@KVCAdaptorDefault@@VCPoliciesDefault@@@@QEAAJH@Z; CArray<CDispatchImplT<IElevationConfig,&_GUID const IID_IElevationConfig,1,0,&_GUID const LIBID_SppComApiLib,1,0>::CTypeInfoItem,ulong,CAdaptorDefault,CPoliciesDefault>::SetSize(int)
0x180038fe3  lea     rcx, [rbx+18h]
0x180038fe7  call    ?Init@?$CRWLock2T@VCEmptyType@@@@QEAAJXZ; CRWLock2T<CEmptyType>::Init(void)
0x180038fec  mov     edi, eax
0x180038fee  mov     r15d, 1
0x180038ff4  test    eax, eax
0x180038ff6  js      short loc_18003900D
0x180038ff8  mov     rcx, rbx
0x180038ffb  mov     [rbx+80h], r15d
0x180039002  call    ??$AddTypeLib@$00$0A@@?$CDispatchImplT@UIOfflineActivationPhoneList@@$1?IID_IOfflineActivationPhoneList@@3U_GUID@@B$00$0A@$1?LIBID_SppComApiLib@@3U3@B$00$0A@@@IEAAJPEAX@Z; CDispatchImplT<IOfflineActivationPhoneList,&_GUID const IID_IOfflineActivationPhoneList,1,0,&_GUID const LIBID_SppComApiLib,1,0>::AddTypeLib<1,0>(void *)
0x180039007  mov     edi, eax
0x180039009  test    eax, eax
0x18003900b  jns     short loc_180039014
0x18003900d  mov     ecx, eax
0x18003900f  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180039014  mov     ecx, edi
0x180039016  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18003901b  test    edi, edi
0x18003901d  jns     short loc_180039026
0x18003901f  mov     ecx, edi
0x180039021  jmp     loc_1800392A9
0x180039026  mov     dword ptr [rbx+0A8h], 18h
0x180039030  call    cs:__imp_GetProcessHeap
0x180039037  nop     dword ptr [rax+rax+00h]
0x18003903c  xor     edx, edx; dwFlags
0x18003903e  mov     rcx, rax; hHeap
0x180039041  lea     r8d, [rdx+10h]; dwBytes
0x180039045  call    cs:__imp_HeapAlloc
0x18003904c  nop     dword ptr [rax+rax+00h]
0x180039051  mov     rcx, rax
0x180039054  test    rax, rax
0x180039057  jz      short loc_180039065
0x180039059  mov     [rax], r15d
0x18003905c  xor     r15b, r15b
0x18003905f  mov     [rax+8], rsi
0x180039063  jmp     short loc_180039067
0x180039065  xor     ecx, ecx
0x180039067  xor     eax, eax
0x180039069  test    r15b, r15b
0x18003906c  cmovz   rax, rcx
0x180039070  mov     [rbp+57h+var_90], rax
0x180039074  test    rax, rax
0x180039077  jnz     short loc_180039087
0x180039079  mov     edi, 8007000Eh
0x18003907e  mov     ecx, edi
0x180039080  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180039085  jmp     short loc_180039094
0x180039087  mov     [rbp+57h+var_90], rsi
0x18003908b  xor     edi, edi
0x18003908d  mov     rsi, rax
0x180039090  mov     [rbp+57h+var_68], rax
0x180039094  mov     ecx, edi
0x180039096  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18003909b  lea     rcx, [rbp+57h+var_90]
0x18003909f  call    ??1?$SP@V?$CRefCountWrapper@VDH_HANDLE@@@@V?$SP_COM@V?$CRefCountWrapper@VDH_HANDLE@@@@@@@@QEAA@XZ; SP<CRefCountWrapper<DH_HANDLE>,SP_COM<CRefCountWrapper<DH_HANDLE>>>::~SP<CRefCountWrapper<DH_HANDLE>,SP_COM<CRefCountWrapper<DH_HANDLE>>>(void)
0x1800390a4  test    edi, edi
0x1800390a6  js      loc_18003901F
0x1800390ac  xor     r9d, r9d; lpName
0x1800390af  xor     r8d, r8d; bInitialState
0x1800390b2  xor     edx, edx; bManualReset
0x1800390b4  xor     ecx, ecx; lpEventAttributes
0x1800390b6  call    cs:__imp_CreateEventW
0x1800390bd  nop     dword ptr [rax+rax+00h]
0x1800390c2  mov     rcx, [rsi+8]; hObject
0x1800390c6  mov     rdi, rax
0x1800390c9  test    rcx, rcx
0x1800390cc  jz      short loc_1800390DA
0x1800390ce  call    cs:__imp_CloseHandle
0x1800390d5  nop     dword ptr [rax+rax+00h]
0x1800390da  test    rdi, rdi
0x1800390dd  jnz     short loc_180039113
0x1800390df  mov     [rsi+8], r14
0x1800390e3  call    cs:__imp_GetLastError
0x1800390ea  nop     dword ptr [rax+rax+00h]
0x1800390ef  mov     edi, eax
0x1800390f1  test    eax, eax
0x1800390f3  jnz     short loc_1800390FF
0x1800390f5  mov     edi, 80004005h
0x1800390fa  jmp     loc_18003901F
0x1800390ff  jle     loc_18003901F
0x180039105  movzx   edi, ax
0x180039108  or      edi, 80070000h
0x18003910e  jmp     loc_18003901F
0x180039113  mov     [rsi+8], rdi
0x180039117  mov     rdi, [rbx+98h]
0x18003911e  mov     [rbp+57h+var_68], r14
0x180039122  test    rdi, rdi
0x180039125  jz      short loc_18003916C
0x180039127  or      eax, 0FFFFFFFFh
0x18003912a  lock xadd [rdi], eax
0x18003912e  cmp     eax, 1
0x180039131  jnz     short loc_18003916C
0x180039133  mov     rcx, [rdi+8]; hObject
0x180039137  test    rcx, rcx
0x18003913a  jz      short loc_18003914C
0x18003913c  call    cs:__imp_CloseHandle
0x180039143  nop     dword ptr [rax+rax+00h]
0x180039148  mov     [rdi+8], r14
0x18003914c  call    cs:__imp_GetProcessHeap
0x180039153  nop     dword ptr [rax+rax+00h]
0x180039158  mov     r8, rdi; lpMem
0x18003915b  xor     edx, edx; dwFlags
0x18003915d  mov     rcx, rax; hHeap
0x180039160  call    cs:__imp_HeapFree
0x180039167  nop     dword ptr [rax+rax+00h]
0x18003916c  lea     rcx, [rbx+0C0h]; phSLC
0x180039173  mov     [rbx+98h], rsi
0x18003917a  call    cs:__imp_SLOpen
0x180039181  nop     dword ptr [rax+rax+00h]
0x180039186  mov     edi, eax
0x180039188  test    eax, eax
0x18003918a  js      loc_1800392A7
0x180039190  xorps   xmm0, xmm0
0x180039193  lea     rdx, [rbp+57h+var_90]; enum tagE_LICENSING_CHANNEL *
0x180039197  xor     eax, eax
0x180039199  lea     rcx, [rbp+57h+var_60]; struct _tagSL_LICENSING_STATUS *
0x18003919d  xor     r8d, r8d; struct _SYSTEMTIME *
0x1800391a0  mov     [rbp+57h+var_60.qwValidityExpiration], rax
0x1800391a4  movups  xmmword ptr [rbp+57h+var_60.SkuId.Data1], xmm0
0x1800391a8  mov     dword ptr [rbp+57h+var_90], eax
0x1800391ab  movups  xmmword ptr [rbp+57h+var_60.eStatus], xmm0
0x1800391af  call    ?SPPGetWindowsLicenseStatus@@YAJPEAU_tagSL_LICENSING_STATUS@@PEAW4tagE_LICENSING_CHANNEL@@PEAU_SYSTEMTIME@@@Z; SPPGetWindowsLicenseStatus(_tagSL_LICENSING_STATUS *,tagE_LICENSING_CHANNEL *,_SYSTEMTIME *)
0x1800391b4  mov     edi, eax
0x1800391b6  test    eax, eax
0x1800391b8  jns     short loc_1800391C3
0x1800391ba  mov     ecx, eax
0x1800391bc  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x1800391c1  jmp     short loc_1800391E4
0x1800391c3  cmp     dword ptr [rbp+57h+var_90], 20h ; ' '
0x1800391c7  jz      short loc_1800391D8
0x1800391c9  cmp     dword ptr [rbp+57h+var_90], 2
0x1800391cd  jz      short loc_1800391D8
0x1800391cf  mov     edi, 0C004F01Fh
0x1800391d4  mov     ecx, edi
0x1800391d6  jmp     short loc_1800391BC
0x1800391d8  movups  xmm0, xmmword ptr [rbp+57h+var_60.SkuId.Data1]
0x1800391dc  movdqu  xmmword ptr [rbx+0C8h], xmm0
0x1800391e4  mov     ecx, edi
0x1800391e6  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x1800391eb  test    edi, edi
0x1800391ed  js      loc_18003901F
0x1800391f3  lea     rdx, [rbp+57h+var_70]; unsigned __int16 **
0x1800391f7  mov     ecx, 0ABh; unsigned int
0x1800391fc  call    ?STRAPI_LoadFromResource@@YAJIPEAPEAG@Z; STRAPI_LoadFromResource(uint,ushort * *)
0x180039201  mov     edi, eax
0x180039203  test    eax, eax
0x180039205  js      loc_1800392A7
0x18003920b  lea     rdx, [rbp+57h+var_78]; unsigned __int16 **
0x18003920f  mov     ecx, 0ACh; unsigned int
0x180039214  call    ?STRAPI_LoadFromResource@@YAJIPEAPEAG@Z; STRAPI_LoadFromResource(uint,ushort * *)
0x180039219  mov     edi, eax
0x18003921b  test    eax, eax
0x18003921d  js      loc_1800392A7
0x180039223  lea     rdx, [rbp+57h+var_80]; unsigned __int16 **
0x180039227  mov     ecx, 0ADh; unsigned int
0x18003922c  call    ?STRAPI_LoadFromResource@@YAJIPEAPEAG@Z; STRAPI_LoadFromResource(uint,ushort * *)
0x180039231  mov     edi, eax
0x180039233  test    eax, eax
0x180039235  js      short loc_1800392A7
0x180039237  lea     rdx, [rbp+57h+var_88]; unsigned __int16 **
0x18003923b  mov     ecx, 0AAh; unsigned int
0x180039240  call    ?STRAPI_LoadFromResource@@YAJIPEAPEAG@Z; STRAPI_LoadFromResource(uint,ushort * *)
0x180039245  mov     edi, eax
0x180039247  test    eax, eax
0x180039249  jns     short loc_180039258
0x18003924b  mov     ecx, eax
0x18003924d  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180039252  mov     r14, [rbp+57h+var_88]
0x180039256  jmp     short loc_1800392AE
0x180039258  mov     r14, [rbp+57h+var_88]
0x18003925c  lea     rcx, [rbx+100h]; unsigned __int16 **
0x180039263  mov     rdx, [rbp+57h+var_70]; unsigned __int16 *
0x180039267  mov     r8, r14
0x18003926a  call    ?STRAPI_FormatMsg@@YAJPEAPEAGPEBGZZ; STRAPI_FormatMsg(ushort * *,ushort const *,...)
0x18003926f  mov     edi, eax
0x180039271  test    eax, eax
0x180039273  js      short loc_1800392A7
0x180039275  mov     rdx, [rbp+57h+var_78]; unsigned __int16 *
0x180039279  lea     rcx, [rbx+108h]; unsigned __int16 **
0x180039280  mov     r8, r14
0x180039283  call    ?STRAPI_FormatMsg@@YAJPEAPEAGPEBGZZ; STRAPI_FormatMsg(ushort * *,ushort const *,...)
0x180039288  mov     edi, eax
0x18003928a  test    eax, eax
0x18003928c  js      short loc_1800392A7
0x18003928e  mov     rdx, [rbp+57h+var_80]; unsigned __int16 *
0x180039292  lea     rcx, [rbx+110h]; unsigned __int16 **
0x180039299  mov     r8, r14
0x18003929c  call    ?STRAPI_FormatMsg@@YAJPEAPEAGPEBGZZ; STRAPI_FormatMsg(ushort * *,ushort const *,...)
0x1800392a1  mov     edi, eax
0x1800392a3  test    eax, eax
0x1800392a5  jns     short loc_1800392AE
0x1800392a7  mov     ecx, eax
0x1800392a9  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x1800392ae  mov     ecx, edi
0x1800392b0  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x1800392b5  test    r14, r14
0x1800392b8  jz      short loc_1800392E2
0x1800392ba  call    cs:__imp_GetProcessHeap
0x1800392c1  nop     dword ptr [rax+rax+00h]
0x1800392c6  lea     r8, [r14-4]; lpMem
0x1800392ca  xor     edx, edx; dwFlags
0x1800392cc  mov     rcx, rax; hHeap
0x1800392cf  call    cs:__imp_HeapFree
0x1800392d6  nop     dword ptr [rax+rax+00h]
0x1800392db  xor     ecx, ecx
0x1800392dd  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x1800392e2  mov     rbx, [rbp+57h+var_80]
0x1800392e6  test    rbx, rbx
0x1800392e9  jz      short loc_180039313
0x1800392eb  call    cs:__imp_GetProcessHeap
0x1800392f2  nop     dword ptr [rax+rax+00h]
0x1800392f7  lea     r8, [rbx-4]; lpMem
0x1800392fb  xor     edx, edx; dwFlags
0x1800392fd  mov     rcx, rax; hHeap
0x180039300  call    cs:__imp_HeapFree
0x180039307  nop     dword ptr [rax+rax+00h]
0x18003930c  xor     ecx, ecx
0x18003930e  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180039313  mov     rbx, [rbp+57h+var_78]
0x180039317  test    rbx, rbx
0x18003931a  jz      short loc_180039344
0x18003931c  call    cs:__imp_GetProcessHeap
0x180039323  nop     dword ptr [rax+rax+00h]
0x180039328  lea     r8, [rbx-4]; lpMem
0x18003932c  xor     edx, edx; dwFlags
0x18003932e  mov     rcx, rax; hHeap
0x180039331  call    cs:__imp_HeapFree
0x180039338  nop     dword ptr [rax+rax+00h]
0x18003933d  xor     ecx, ecx
0x18003933f  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180039344  mov     rbx, [rbp+57h+var_70]
0x180039348  test    rbx, rbx
0x18003934b  jz      short loc_180039375
0x18003934d  call    cs:__imp_GetProcessHeap
0x180039354  nop     dword ptr [rax+rax+00h]
0x180039359  lea     r8, [rbx-4]; lpMem
0x18003935d  xor     edx, edx; dwFlags
0x18003935f  mov     rcx, rax; hHeap
0x180039362  call    cs:__imp_HeapFree
0x180039369  nop     dword ptr [rax+rax+00h]
0x18003936e  xor     ecx, ecx
0x180039370  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180039375  lea     rcx, [rbp+57h+var_68]
0x180039379  call    ??1?$SP@V?$CRefCountWrapper@VDH_HANDLE@@@@V?$SP_COM@V?$CRefCountWrapper@VDH_HANDLE@@@@@@@@QEAA@XZ; SP<CRefCountWrapper<DH_HANDLE>,SP_COM<CRefCountWrapper<DH_HANDLE>>>::~SP<CRefCountWrapper<DH_HANDLE>,SP_COM<CRefCountWrapper<DH_HANDLE>>>(void)
0x18003937e  mov     eax, edi
0x180039380  add     rsp, 88h
0x180039387  pop     r15
0x180039389  pop     r14
0x18003938b  pop     rdi
0x18003938c  pop     rsi
0x18003938d  pop     rbx
0x18003938e  pop     rbp
0x18003938f  retn
```
