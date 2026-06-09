# CWbemNamespace::QueryObjectSink(long,IWbemObjectSink * *)

- ea: `0x18009fc70`
- end: `0x1800a009e`
- name: `?QueryObjectSink@CWbemNamespace@@UEAAJJPEAPEAUIWbemObjectSink@@@Z`
- size: `1070`
- prototype: `__int64 __fastcall(CWbemNamespace *__hidden this, int, struct IWbemObjectSink **)`
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x18000b104`
- `0x18000b140`
- `0x18001f6d0`
- `0x18003cfe0`
- `0x1800469a4`
- `0x180047ed0`
- `0x180065e88`
- `0x18007d990`
- `0x18009fc70`
- `0x1800da010`

## import_xrefs

- `wbemcomn!IsNtSetupRunning` at `0x18009fe6a`
- `wbemcomn!IsNtSetupRunning` at `0x18009fe6a`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18009ff00`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18009ff00`
- `wbemcomn!GetMemLogObject` at `0x18009fcc8`
- `wbemcomn!GetMemLogObject` at `0x18009fd18`
- `wbemcomn!GetMemLogObject` at `0x18009fd85`
- `wbemcomn!GetMemLogObject` at `0x18009fdd7`
- `wbemcomn!GetMemLogObject` at `0x18009fe15`
- `wbemcomn!GetMemLogObject` at `0x18009fead`
- `wbemcomn!GetMemLogObject` at `0x18009ff8e`
- `wbemcomn!GetMemLogObject` at `0x18009ffe7`
- `wbemcomn!GetMemLogObject` at `0x1800a004a`
- `wbemcomn!GetMemLogObject` at `0x18009fcc8`
- `wbemcomn!GetMemLogObject` at `0x18009fd18`
- `wbemcomn!GetMemLogObject` at `0x18009fd85`
- `wbemcomn!GetMemLogObject` at `0x18009fdd7`
- `wbemcomn!GetMemLogObject` at `0x18009fe15`
- `wbemcomn!GetMemLogObject` at `0x18009fead`
- `wbemcomn!GetMemLogObject` at `0x18009ff8e`
- `wbemcomn!GetMemLogObject` at `0x18009ffe7`
- `wbemcomn!GetMemLogObject` at `0x1800a004a`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18009fcd6`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18009fd23`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18009fd93`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18009fde5`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18009fe23`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18009feb8`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18009ff9e`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18009fff2`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800a005a`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18009fcd6`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18009fd23`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18009fd93`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18009fde5`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18009fe23`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18009feb8`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18009ff9e`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18009fff2`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800a005a`

## string_xrefs

- `0x18009fd6f`: `Write (QueryObjectSink)`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall CWbemNamespace::QueryObjectSink(CWbemNamespace *this, int a2, struct IWbemObjectSink **a3)
{
  CMemoryLog *MemLogObject; // rax
  CClientCnt *v7; // rcx
  __int64 v8; // rdx
  CWbemNamespace *v9; // rcx
  unsigned int v10; // ebx
  CMemoryLog *v11; // rax
  CClientCnt *v12; // rcx
  __int64 v13; // rdx
  __int64 v14; // r9
  CMemoryLog *v15; // rax
  CMemoryLog *v17; // rax
  CClientCnt *v18; // rcx
  __int64 v19; // rdx
  CMemoryLog *v20; // rax
  struct IWbemEventSubsystem_m4 *EssSink; // rbx
  CMemoryLog *v22; // rax
  _DWORD *v23; // rax
  __int64 v24; // rbx
  __int64 v25; // rcx
  CMemoryLog *v26; // rax
  CClientCnt *v27; // rcx
  __int64 v28; // rdx
  __int64 v29; // r9
  CMemoryLog *v30; // rax
  CMemoryLog *v31; // rax
  bool v32; // [rsp+28h] [rbp-60h]
  __int64 v33; // [rsp+40h] [rbp-48h] BYREF
  struct IWbemEventSubsystem_m4 *v34; // [rsp+48h] [rbp-40h] BYREF
  _DWORD *v35; // [rsp+A8h] [rbp+20h] BYREF

  if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 841, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids, this);
  }
  if ( (unsigned int)IsCallFromLowIntegrityClient() )
  {
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, -2147217405);
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return 2147749891LL;
    }
    v8 = 842;
LABEL_20:
    WPP_SF_d(*((_QWORD *)v7 + 2), v8, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids, 2147749891LL);
    return 2147749891LL;
  }
  v10 = CWbemNamespace::CheckNs(this);
  if ( (v10 & 0x80000000) != 0 )
  {
    v11 = GetMemLogObject();
    CMemoryLog::Write(v11, v10);
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return v10;
    }
    v13 = 843;
    v14 = v10;
    goto LABEL_65;
  }
  if ( !CWbemNamespace::InnerAllowedWithSD(
          v9,
          (CWbemNamespace *)((char *)this + 216),
          4u,
          L"Write (QueryObjectSink)",
          0,
          v32,
          1) )
  {
    v15 = GetMemLogObject();
    CMemoryLog::Write(v15, -2147217405);
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return 2147749891LL;
    }
    v8 = 844;
    goto LABEL_20;
  }
  if ( !a3 )
  {
    v17 = GetMemLogObject();
    CMemoryLog::Write(v17, -2147217400);
    v18 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return 2147749896LL;
    }
    v19 = 845;
LABEL_32:
    WPP_SF_d(*((_QWORD *)v18 + 2), v19, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids, 2147749896LL);
    return 2147749896LL;
  }
  *a3 = 0;
  if ( a2 )
  {
    v20 = GetMemLogObject();
    CMemoryLog::Write(v20, -2147217400);
    v18 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return 2147749896LL;
    }
    v19 = 846;
    goto LABEL_32;
  }
  EssSink = ConfigMgr::GetEssSink();
  if ( IsNtSetupRunning() || !EssSink )
  {
    v31 = GetMemLogObject();
    v10 = -2147217396;
    CMemoryLog::Write(v31, -2147217396);
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return v10;
    }
    v13 = 850;
    v14 = 2147749900LL;
LABEL_65:
    WPP_SF_d(*((_QWORD *)v12 + 2), v13, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids, v14);
    return v10;
  }
  v34 = EssSink;
  v33 = 0;
  v10 = (*(__int64 (__fastcall **)(struct IWbemEventSubsystem_m4 *, _QWORD, __int64 *))(*(_QWORD *)EssSink + 56LL))(
          EssSink,
          *((_QWORD *)this + 11),
          &v33);
  if ( (v10 & 0x80000000) != 0 )
  {
    v22 = GetMemLogObject();
    CMemoryLog::Write(v22, v10);
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 847, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids, v10);
    }
    goto LABEL_60;
  }
  v23 = CWin32DefaultArena::WbemMemAlloc(0x28u);
  v24 = (__int64)v23;
  v35 = v23;
  if ( v23 )
  {
    v25 = v33;
    *(_QWORD *)v23 = &CUnkBase<IWbemObjectSink,&_GUID const IID_IWbemObjectSink>::`vftable';
    v23[2] = 0;
    *((_QWORD *)v23 + 2) = 0;
    *(_QWORD *)v23 = &CSecureEssNamespaceSink::`vftable';
    *((_QWORD *)v23 + 3) = this;
    _InterlockedIncrement((volatile signed __int32 *)this + 6);
    *((_QWORD *)v23 + 4) = v25;
    if ( v25 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 8LL))(v25);
  }
  else
  {
    v24 = 0;
  }
  v35 = (_DWORD *)v24;
  if ( v24 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 8LL))(v24);
    v10 = (**(__int64 (__fastcall ***)(__int64, GUID *, struct IWbemObjectSink **))v24)(v24, &IID_IWbemObjectSink, a3);
    if ( (v10 & 0x80000000) != 0 )
    {
      v30 = GetMemLogObject();
      CMemoryLog::Write(v30, v10);
    }
    v27 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_59;
    }
    v28 = 849;
    v29 = v10;
  }
  else
  {
    v26 = GetMemLogObject();
    v10 = -2147217402;
    CMemoryLog::Write(v26, -2147217402);
    v27 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_59;
    }
    v28 = 848;
    v29 = 2147749894LL;
  }
  WPP_SF_d(*((_QWORD *)v27 + 2), v28, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids, v29);
LABEL_59:
  _com_ptr_t<_com_IIID<IWbemClassObject,&__s_GUID const _GUID_dc12a681_737f_11cf_884d_00aa004b2e24>>::_Release((__int64 *)&v35);
LABEL_60:
  _com_ptr_t<_com_IIID<IWbemClassObject,&__s_GUID const _GUID_dc12a681_737f_11cf_884d_00aa004b2e24>>::_Release(&v33);
  CReleaseMe::release((CReleaseMe *)&v34);
  return v10;
}

```

## disassembly

```asm
0x18009fc70  push    rbx
0x18009fc72  push    rbp
0x18009fc73  push    rsi
0x18009fc74  push    rdi
0x18009fc75  push    r12
0x18009fc77  push    r13
0x18009fc79  sub     rsp, 58h
0x18009fc7d  mov     rsi, r8
0x18009fc80  mov     ebp, edx
0x18009fc82  mov     rdi, rcx
0x18009fc85  lea     r12, WPP_GLOBAL_Control
0x18009fc8c  lea     r13, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids
0x18009fc93  mov     rcx, cs:WPP_GLOBAL_Control
0x18009fc9a  cmp     rcx, r12
0x18009fc9d  jz      short loc_18009FCBF
0x18009fc9f  test    byte ptr [rcx+1Ch], 1
0x18009fca3  jz      short loc_18009FCBF
0x18009fca5  cmp     byte ptr [rcx+19h], 5
0x18009fca9  jb      short loc_18009FCBF
0x18009fcab  mov     edx, 349h
0x18009fcb0  mov     r9, rdi
0x18009fcb3  mov     r8, r13
0x18009fcb6  mov     rcx, [rcx+10h]
0x18009fcba  call    WPP_SF_q
0x18009fcbf  call    ?IsCallFromLowIntegrityClient@@YAHXZ; IsCallFromLowIntegrityClient(void)
0x18009fcc4  test    eax, eax
0x18009fcc6  jz      short loc_18009FD0A
0x18009fcc8  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18009fcce  mov     edx, 80041003h
0x18009fcd3  mov     rcx, rax
0x18009fcd6  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18009fcdc  mov     rcx, cs:WPP_GLOBAL_Control
0x18009fce3  cmp     rcx, r12
0x18009fce6  jz      loc_18009FDC8
0x18009fcec  test    byte ptr [rcx+1Ch], 1
0x18009fcf0  jz      loc_18009FDC8
0x18009fcf6  cmp     byte ptr [rcx+19h], 2
0x18009fcfa  jb      loc_18009FDC8
0x18009fd00  mov     edx, 34Ah
0x18009fd05  jmp     loc_18009FDB6
0x18009fd0a  mov     rcx, rdi; this
0x18009fd0d  call    ?CheckNs@CWbemNamespace@@QEAAJXZ; CWbemNamespace::CheckNs(void)
0x18009fd12  mov     ebx, eax
0x18009fd14  test    eax, eax
0x18009fd16  jns     short loc_18009FD5A
0x18009fd18  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18009fd1e  mov     edx, ebx
0x18009fd20  mov     rcx, rax
0x18009fd23  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18009fd29  mov     rcx, cs:WPP_GLOBAL_Control
0x18009fd30  cmp     rcx, r12
0x18009fd33  jz      loc_1800A008F
0x18009fd39  test    byte ptr [rcx+1Ch], 1
0x18009fd3d  jz      loc_1800A008F
0x18009fd43  cmp     byte ptr [rcx+19h], 2
0x18009fd47  jb      loc_1800A008F
0x18009fd4d  mov     edx, 34Bh
0x18009fd52  mov     r9d, ebx
0x18009fd55  jmp     loc_1800A0083
0x18009fd5a  lea     rdx, [rdi+0D8h]; struct CNtSecurityDescriptor *
0x18009fd61  mov     [rsp+88h+var_58], 1; bool
0x18009fd66  mov     [rsp+88h+var_68], 0; unsigned __int16 *
0x18009fd6f  lea     r9, aWriteQueryobje; "Write (QueryObjectSink)"
0x18009fd76  mov     r8d, 4; unsigned int
0x18009fd7c  call    ?InnerAllowedWithSD@CWbemNamespace@@QEAA_NPEAVCNtSecurityDescriptor@@KPEBG1_N2@Z; CWbemNamespace::InnerAllowedWithSD(CNtSecurityDescriptor *,ulong,ushort const *,ushort const *,bool,bool)
0x18009fd81  test    al, al
0x18009fd83  jnz     short loc_18009FDD2
0x18009fd85  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18009fd8b  mov     edx, 80041003h
0x18009fd90  mov     rcx, rax
0x18009fd93  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18009fd99  mov     rcx, cs:WPP_GLOBAL_Control
0x18009fda0  cmp     rcx, r12
0x18009fda3  jz      short loc_18009FDC8
0x18009fda5  test    byte ptr [rcx+1Ch], 1
0x18009fda9  jz      short loc_18009FDC8
0x18009fdab  cmp     byte ptr [rcx+19h], 2
0x18009fdaf  jb      short loc_18009FDC8
0x18009fdb1  mov     edx, 34Ch
0x18009fdb6  mov     r9d, 80041003h
0x18009fdbc  mov     r8, r13
0x18009fdbf  mov     rcx, [rcx+10h]
0x18009fdc3  call    WPP_SF_d
0x18009fdc8  mov     eax, 80041003h
0x18009fdcd  jmp     loc_1800A0091
0x18009fdd2  test    rsi, rsi
0x18009fdd5  jnz     short loc_18009FE0A
0x18009fdd7  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18009fddd  mov     edx, 80041008h
0x18009fde2  mov     rcx, rax
0x18009fde5  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18009fdeb  mov     rcx, cs:WPP_GLOBAL_Control
0x18009fdf2  cmp     rcx, r12
0x18009fdf5  jz      short loc_18009FE58
0x18009fdf7  test    byte ptr [rcx+1Ch], 1
0x18009fdfb  jz      short loc_18009FE58
0x18009fdfd  cmp     byte ptr [rcx+19h], 2
0x18009fe01  jb      short loc_18009FE58
0x18009fe03  mov     edx, 34Dh
0x18009fe08  jmp     short loc_18009FE46
0x18009fe0a  mov     qword ptr [rsi], 0
0x18009fe11  test    ebp, ebp
0x18009fe13  jz      short loc_18009FE62
0x18009fe15  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18009fe1b  mov     edx, 80041008h
0x18009fe20  mov     rcx, rax
0x18009fe23  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18009fe29  mov     rcx, cs:WPP_GLOBAL_Control
0x18009fe30  cmp     rcx, r12
0x18009fe33  jz      short loc_18009FE58
0x18009fe35  test    byte ptr [rcx+1Ch], 1
0x18009fe39  jz      short loc_18009FE58
0x18009fe3b  cmp     byte ptr [rcx+19h], 2
0x18009fe3f  jb      short loc_18009FE58
0x18009fe41  mov     edx, 34Eh
0x18009fe46  mov     r9d, 80041008h
0x18009fe4c  mov     r8, r13
0x18009fe4f  mov     rcx, [rcx+10h]
0x18009fe53  call    WPP_SF_d
0x18009fe58  mov     eax, 80041008h
0x18009fe5d  jmp     loc_1800A0091
0x18009fe62  call    ?GetEssSink@ConfigMgr@@SAPEAUIWbemEventSubsystem_m4@@XZ; ConfigMgr::GetEssSink(void)
0x18009fe67  mov     rbx, rax
0x18009fe6a  call    cs:__imp_?IsNtSetupRunning@@YAHXZ; IsNtSetupRunning(void)
0x18009fe70  test    eax, eax
0x18009fe72  jnz     loc_1800A004A
0x18009fe78  test    rbx, rbx
0x18009fe7b  jz      loc_1800A004A
0x18009fe81  mov     [rsp+88h+var_40], rbx
0x18009fe86  mov     [rsp+88h+var_48], 0
0x18009fe8f  mov     rax, [rbx]
0x18009fe92  lea     r8, [rsp+88h+var_48]
0x18009fe97  mov     rdx, [rdi+58h]
0x18009fe9b  mov     rcx, rbx
0x18009fe9e  mov     rax, [rax+38h]
0x18009fea2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009fea7  mov     ebx, eax
0x18009fea9  test    eax, eax
0x18009feab  jns     short loc_18009FEFB
0x18009fead  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18009feb3  mov     edx, ebx
0x18009feb5  mov     rcx, rax
0x18009feb8  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18009febe  mov     rcx, cs:WPP_GLOBAL_Control
0x18009fec5  cmp     rcx, r12
0x18009fec8  jz      loc_1800A0033
0x18009fece  test    byte ptr [rcx+1Ch], 1
0x18009fed2  jz      loc_1800A0033
0x18009fed8  cmp     byte ptr [rcx+19h], 2
0x18009fedc  jb      loc_1800A0033
0x18009fee2  mov     edx, 34Fh
0x18009fee7  mov     r9d, ebx
0x18009feea  mov     r8, r13
0x18009feed  mov     rcx, [rcx+10h]
0x18009fef1  call    WPP_SF_d
0x18009fef6  jmp     loc_1800A0033
0x18009fefb  mov     ecx, 28h ; '('
0x18009ff00  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18009ff06  mov     rbx, rax
0x18009ff09  mov     [rsp+88h+arg_18], rax
0x18009ff11  test    rax, rax
0x18009ff14  jz      short loc_18009FF5E
0x18009ff16  mov     rcx, [rsp+88h+var_48]
0x18009ff1b  lea     rax, ??_7?$CUnkBase@UIWbemObjectSink@@$1?IID_IWbemObjectSink@@3U_GUID@@B@@6B@; const CUnkBase<IWbemObjectSink,&_GUID const IID_IWbemObjectSink>::`vftable'
0x18009ff22  mov     [rbx], rax
0x18009ff25  mov     dword ptr [rbx+8], 0
0x18009ff2c  mov     qword ptr [rbx+10h], 0
0x18009ff34  lea     rax, ??_7CSecureEssNamespaceSink@@6B@; const CSecureEssNamespaceSink::`vftable'
0x18009ff3b  mov     [rbx], rax
0x18009ff3e  mov     [rbx+18h], rdi
0x18009ff42  lock inc dword ptr [rdi+18h]
0x18009ff46  mov     [rbx+20h], rcx
0x18009ff4a  test    rcx, rcx
0x18009ff4d  jz      short loc_18009FF5C
0x18009ff4f  mov     rax, [rcx]
0x18009ff52  mov     rax, [rax+8]
0x18009ff56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009ff5b  nop
0x18009ff5c  jmp     short loc_18009FF60
0x18009ff5e  xor     ebx, ebx
0x18009ff60  mov     [rsp+88h+arg_18], 0
0x18009ff6c  mov     [rsp+88h+arg_18], rbx
0x18009ff74  test    rbx, rbx
0x18009ff77  jz      short loc_18009FF89
0x18009ff79  mov     rax, [rbx]
0x18009ff7c  mov     rcx, rbx
0x18009ff7f  mov     rax, [rax+8]
0x18009ff83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009ff88  nop
0x18009ff89  test    rbx, rbx
0x18009ff8c  jnz     short loc_18009FFC9
0x18009ff8e  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18009ff94  mov     ebx, 80041006h
0x18009ff99  mov     edx, ebx
0x18009ff9b  mov     rcx, rax
0x18009ff9e  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18009ffa4  mov     rcx, cs:WPP_GLOBAL_Control
0x18009ffab  cmp     rcx, r12
0x18009ffae  jz      short loc_1800A0025
0x18009ffb0  test    byte ptr [rcx+1Ch], 1
0x18009ffb4  jz      short loc_1800A0025
0x18009ffb6  cmp     byte ptr [rcx+19h], 2
0x18009ffba  jb      short loc_1800A0025
0x18009ffbc  mov     edx, 350h
0x18009ffc1  mov     r9d, 80041006h
0x18009ffc7  jmp     short loc_1800A0018
0x18009ffc9  mov     rax, [rbx]
0x18009ffcc  mov     r8, rsi
0x18009ffcf  lea     rdx, IID_IWbemObjectSink
0x18009ffd6  mov     rcx, rbx
0x18009ffd9  mov     rax, [rax]
0x18009ffdc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009ffe1  mov     ebx, eax
0x18009ffe3  test    eax, eax
0x18009ffe5  jns     short loc_18009FFF8
0x18009ffe7  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18009ffed  mov     edx, ebx
0x18009ffef  mov     rcx, rax
0x18009fff2  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18009fff8  mov     rcx, cs:WPP_GLOBAL_Control
0x18009ffff  cmp     rcx, r12
0x1800a0002  jz      short loc_1800A0025
0x1800a0004  test    byte ptr [rcx+1Ch], 1
0x1800a0008  jz      short loc_1800A0025
0x1800a000a  cmp     byte ptr [rcx+19h], 2
0x1800a000e  jb      short loc_1800A0025
0x1800a0010  mov     edx, 351h
0x1800a0015  mov     r9d, ebx
0x1800a0018  mov     r8, r13
0x1800a001b  mov     rcx, [rcx+10h]
0x1800a001f  call    WPP_SF_d
0x1800a0024  nop
0x1800a0025  lea     rcx, [rsp+88h+arg_18]
0x1800a002d  call    ?_Release@?$_com_ptr_t@V?$_com_IIID@UIWbemClassObject@@$1?_GUID_dc12a681_737f_11cf_884d_00aa004b2e24@@3U__s_GUID@@B@@@@AEAAXXZ; _com_ptr_t<_com_IIID<IWbemClassObject,&__s_GUID const _GUID_dc12a681_737f_11cf_884d_00aa004b2e24>>::_Release(void)
0x1800a0032  nop
0x1800a0033  lea     rcx, [rsp+88h+var_48]
0x1800a0038  call    ?_Release@?$_com_ptr_t@V?$_com_IIID@UIWbemClassObject@@$1?_GUID_dc12a681_737f_11cf_884d_00aa004b2e24@@3U__s_GUID@@B@@@@AEAAXXZ; _com_ptr_t<_com_IIID<IWbemClassObject,&__s_GUID const _GUID_dc12a681_737f_11cf_884d_00aa004b2e24>>::_Release(void)
0x1800a003d  nop
0x1800a003e  lea     rcx, [rsp+88h+var_40]; this
0x1800a0043  call    ?release@CReleaseMe@@QEAAXXZ; CReleaseMe::release(void)
0x1800a0048  jmp     short loc_1800A008F
0x1800a004a  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800a0050  mov     ebx, 8004100Ch
0x1800a0055  mov     edx, ebx
0x1800a0057  mov     rcx, rax
0x1800a005a  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800a0060  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a0067  cmp     rcx, r12
0x1800a006a  jz      short loc_1800A008F
0x1800a006c  test    byte ptr [rcx+1Ch], 1
0x1800a0070  jz      short loc_1800A008F
0x1800a0072  cmp     byte ptr [rcx+19h], 2
0x1800a0076  jb      short loc_1800A008F
0x1800a0078  mov     edx, 352h
0x1800a007d  mov     r9d, 8004100Ch
0x1800a0083  mov     r8, r13
0x1800a0086  mov     rcx, [rcx+10h]
0x1800a008a  call    WPP_SF_d
0x1800a008f  mov     eax, ebx
0x1800a0091  add     rsp, 58h
0x1800a0095  pop     r13
0x1800a0097  pop     r12
0x1800a0099  pop     rdi
0x1800a009a  pop     rsi
0x1800a009b  pop     rbp
0x1800a009c  pop     rbx
0x1800a009d  retn
```
