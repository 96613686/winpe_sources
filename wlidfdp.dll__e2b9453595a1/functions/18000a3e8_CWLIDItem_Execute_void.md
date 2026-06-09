# CWLIDItem::Execute(void)

- ea: `0x18000a3e8`
- end: `0x18000a82f`
- name: `?Execute@CWLIDItem@@QEAAJXZ`
- size: `1095`
- prototype: `__int64 __fastcall(CWLIDItem *this, __int64, __int64, unsigned int)`
- caller_count: `1`
- callee_count: `17`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000bac0`

## callees

- `0x180003700`
- `0x180003728`
- `0x18000505c`
- `0x1800054dc`
- `0x180005d3c`
- `0x180008430`
- `0x180008edc`
- `0x18000a3e8`
- `0x18000de3c`
- `0x18000e1c0`
- `0x18000e500`
- `0x18000eff8`
- `0x18000f0e4`
- `0x18000f11c`
- `0x18000f230`
- `0x18000f4cc`
- `0x180012010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000a7e1`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000a7e1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a4be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a4be`
- `api-ms-win-security-base-l1-1-0!ImpersonateSelf` at `0x18000a4b4`
- `api-ms-win-security-base-l1-1-0!ImpersonateSelf` at `0x18000a4b4`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000a7f1`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000a7f1`

## string_xrefs

- `0x18000a505`: `WLIDCCreateContextEx returned PPCRL_NO_SUCH_HANDLE -- not a connected account?`

## pseudocode

```c
__int64 __fastcall CWLIDItem::Execute(CWLIDItem *this, __int64 a2, __int64 a3, unsigned int a4)
{
  unsigned __int64 v5; // rcx
  const unsigned __int16 *v6; // rdx
  const unsigned __int16 *v7; // rcx
  unsigned __int64 v8; // r8
  signed int LastError; // eax
  int v10; // eax
  unsigned int v11; // edx
  int v12; // esi
  unsigned __int8 v13; // dl
  PPTraceStatus *v14; // rcx
  bool v15; // cl
  unsigned __int8 v16; // dl
  PPTraceStatus *v17; // rcx
  bool v18; // cl
  const unsigned __int16 *String; // rax
  const unsigned __int16 *v20; // rax
  __int64 v21; // rdx
  unsigned int v22; // esi
  int v23; // eax
  unsigned int v24; // ebx
  struct IFunctionInstance **v26; // [rsp+20h] [rbp-B8h]
  struct IFunctionInstance **v27; // [rsp+20h] [rbp-B8h]
  struct IFunctionInstance **v28; // [rsp+20h] [rbp-B8h]
  struct IFunctionInstance *v29; // [rsp+30h] [rbp-A8h] BYREF
  void *Block; // [rsp+38h] [rbp-A0h] BYREF
  void **v31; // [rsp+40h] [rbp-98h] BYREF
  __int64 v32; // [rsp+48h] [rbp-90h]
  __int64 v33; // [rsp+50h] [rbp-88h]
  bool v34; // [rsp+58h] [rbp-80h]
  int v35; // [rsp+60h] [rbp-78h] BYREF
  _QWORD v36[4]; // [rsp+68h] [rbp-70h] BYREF
  CPassportException *v37; // [rsp+88h] [rbp-50h] BYREF
  ATL::CAtlException *v38; // [rsp+90h] [rbp-48h] BYREF
  const wil::ResultException *v39; // [rsp+98h] [rbp-40h] BYREF
  int v40; // [rsp+E0h] [rbp+8h] BYREF
  unsigned int v41; // [rsp+E8h] [rbp+10h] BYREF
  int v42; // [rsp+F0h] [rbp+18h]
  void *v43; // [rsp+F8h] [rbp+20h] BYREF

  v40 = 0;
  v41 = 0;
  v29 = 0;
  v42 = 0;
  v43 = 0;
  Block = 0;
  v36[0] = "CWLIDItem::Execute";
  v36[1] = &v40;
  v36[2] = 0;
  v36[3] = 0;
  MsaTracingInternal::TraceFunctionEnter(
    (MsaTracingInternal *)"\\wlidqueue.cpp",
    "CWLIDItem::Execute",
    (const char *)0x48,
    a4,
    (const unsigned __int16 *)v26);
  if ( !*((_QWORD *)this + 9) )
  {
    v40 = -2147024809;
    goto LABEL_45;
  }
  if ( *((_BYTE *)this + 96) )
  {
    TracePrintW(5u, "\\wlidqueue.cpp", 0x55u, L"Query has been cancelled, not executing.\n");
LABEL_5:
    v40 = 1;
    goto LABEL_45;
  }
  if ( !ImpersonateSelf(SecurityImpersonation) )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v40 = LastError;
    goto LABEL_45;
  }
  v42 = 1;
  v10 = WLIDCCreateContextEx(v7, v6, v8, &v43);
  if ( __eh34_try(-1, 0) )
  {
    __eh34_scope_strut(0);
    v12 = v10;
    v40 = v10;
    if ( v10 == -2147188724 )
    {
      TracePrintW(
        5u,
        "\\wlidqueue.cpp",
        0x75u,
        L"WLIDCCreateContextEx returned PPCRL_NO_SUCH_HANDLE -- not a connected account?");
      v40 = 0;
    }
    else
    {
      if ( v10 >= 0 )
      {
        v12 = WLIDCEnumerateUserAssociatedDevices(
                v43,
                v11,
                *((unsigned __int16 **)this + 11),
                &v41,
                (struct __MIDL_liveidsvc_0003 **)&Block);
        v40 = v12;
      }
      if ( v12 < 0 )
      {
        v18 = 0;
        if ( PPTraceShouldRedact() )
        {
          LOBYTE(v17) = 1;
          if ( PPTraceStatus::TraceOnFlag(v17, v16) )
            v18 = 1;
        }
        v32 = *((_QWORD *)this + 11);
        v33 = 0;
        v34 = v18;
        v31 = &PPRedactedStringW::`vftable';
        String = PPRedactedStringW::GetString((PPRedactedStringW *)&v31);
        TracePrintW(2u, "\\wlidqueue.cpp", 0x88u, L"Failed to enumerate devices for owner %ls. (0x%x)", String, v12);
        goto LABEL_26;
      }
    }
    v15 = 0;
    if ( PPTraceShouldRedact() )
    {
      LOBYTE(v14) = 1;
      if ( PPTraceStatus::TraceOnFlag(v14, v13) )
        v15 = 1;
    }
    v32 = *((_QWORD *)this + 11);
    v33 = 0;
    v34 = v15;
    v31 = &PPRedactedStringW::`vftable';
    v20 = PPRedactedStringW::GetString((PPRedactedStringW *)&v31);
    LODWORD(v27) = v41;
    TracePrintW(5u, "\\wlidqueue.cpp", 0x8Cu, L"Enumerated %u devices for owner %ls.", v27, v20);
LABEL_26:
    PPRedactedStringW::~PPRedactedStringW((PPRedactedStringW *)&v31);
  }
  if ( __eh34_catch(0) )
  {
    if ( __eh34_catch_type(0, &CPassportException `RTTI Type Descriptor', &v37) )
    {
      v5 = *((unsigned int *)v37 + 2);
      v40 = v5;
      if ( (v5 & 0x80000000) == 0LL )
        v40 = -2147418113;
      __eh34_try_continuation(0, &CPassportException `RTTI Type Descriptor', &loc_18000A7BE);
      goto LABEL_45;
    }
    if ( __eh34_catch_type(0, &ATL::CAtlException `RTTI Type Descriptor', &v38) )
    {
      v5 = *(unsigned int *)v38;
      v40 = v5;
      if ( (v5 & 0x80000000) == 0LL )
        v40 = -2147418113;
      __eh34_try_continuation(0, &ATL::CAtlException `RTTI Type Descriptor', &loc_18000A822);
      goto LABEL_45;
    }
    if ( __eh34_catch_type(0, &std::bad_alloc `RTTI Type Descriptor', 0) )
    {
      v40 = -2147024882;
      __eh34_try_continuation(0, &std::bad_alloc `RTTI Type Descriptor', &loc_18000A824);
      goto LABEL_45;
    }
    if ( __eh34_catch_type(0, &long `RTTI Type Descriptor', (long *)&v35) )
    {
      v40 = v35;
      if ( v35 >= 0 )
        v40 = -2147418113;
      __eh34_try_continuation(0, &long `RTTI Type Descriptor', &loc_18000A826);
      goto LABEL_45;
    }
    if ( __eh34_catch_type(0, &wil::ResultException `RTTI Type Descriptor', &v39) )
    {
      v5 = *((unsigned int *)v39 + 8);
      v40 = v5;
      if ( (v5 & 0x80000000) == 0LL )
        v40 = -2147418113;
      __eh34_try_continuation(0, &wil::ResultException `RTTI Type Descriptor', &loc_18000A7BE);
      goto LABEL_45;
    }
  }
  if ( *((_BYTE *)this + 96) )
  {
    TracePrintW(5u, "\\wlidqueue.cpp", 0x96u, L"Query has been cancelled, droping results.");
    goto LABEL_5;
  }
  CComCritSecLockWTry<CComAutoCriticalSectionWTry>::CComCritSecLockWTry<CComAutoCriticalSectionWTry>(
    (__int64)&v31,
    (struct _RTL_CRITICAL_SECTION *)((char *)this + 16));
  if ( *((_BYTE *)this + 96) )
  {
    TracePrintW(5u, "\\wlidqueue.cpp", 0xA6u, L"Query has been cancelled, droping results.");
    v40 = 1;
  }
  else
  {
    v21 = (unsigned int)v40;
    if ( v40 < 0 )
      goto LABEL_41;
    v22 = 0;
    if ( v41 )
    {
      while ( 1 )
      {
        v23 = CWLIDFDProv::BuildInstance(
                *((unsigned __int16 **)Block + 2 * v22),
                *((unsigned __int16 **)Block + 2 * v22 + 1),
                *((struct IFunctionDiscoveryProvider **)this + 10),
                *((struct IFunctionDiscoveryProviderFactory **)this + 8),
                &v29);
        v40 = v23;
        if ( v23 < 0 )
          break;
        (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD, struct IFunctionInstance *))(**((_QWORD **)this + 9) + 24LL))(
          *((_QWORD *)this + 9),
          0,
          0,
          v29);
        ATL::CComPtrBase<IFunctionInstance>::Release(&v29);
        if ( ++v22 >= v41 )
          goto LABEL_38;
      }
      LODWORD(v28) = v23;
      TracePrintW(2u, "\\wlidqueue.cpp", 0xC3u, L"Failed to build instance. (0x%x)", v28);
LABEL_38:
      v21 = (unsigned int)v40;
    }
    if ( (int)v21 < 0 )
    {
LABEL_41:
      if ( (_DWORD)v21 == -2147186655 || (_DWORD)v21 == -2147186459 )
      {
        v21 = 2147942486LL;
        v40 = -2147024810;
      }
      (*(void (__fastcall **)(_QWORD, __int64, _QWORD, const wchar_t *))(**((_QWORD **)this + 9) + 32LL))(
        *((_QWORD *)this + 9),
        v21,
        0,
        L"Provider\\Microsoft.WindowsLive.Devices");
    }
    (*(void (__fastcall **)(_QWORD, __int64, _QWORD, const wchar_t *))(**((_QWORD **)this + 9) + 40LL))(
      *((_QWORD *)this + 9),
      1000,
      0,
      L"Provider\\Microsoft.WindowsLive.Devices");
  }
  CComCritSecLockWTry<CComAutoCriticalSectionWTry>::~CComCritSecLockWTry<CComAutoCriticalSectionWTry>((__int64)&v31);
LABEL_45:
  if ( v43 )
    WLIDCDeleteContextEx(v5, &v43);
  if ( Block )
    free(Block);
  if ( v42 )
    RevertToSelf();
  v24 = v40;
  ((void (__fastcall *)(_QWORD *))CTraceFuncW<long>::~CTraceFuncW<long>)(v36);
  ATL::CComPtrBase<IFunctionInstanceCollection>::~CComPtrBase<IFunctionInstanceCollection>((__int64 *)&v29);
  return v24;
}

```

## disassembly

```asm
0x18000a3e8  mov     r11, rsp
0x18000a3eb  push    rbx
0x18000a3ec  push    rsi
0x18000a3ed  push    rdi
0x18000a3ee  push    r14
0x18000a3f0  sub     rsp, 0B8h
0x18000a3f7  mov     rdi, rcx
0x18000a3fa  mov     dword ptr [r11+8], 0
0x18000a402  mov     dword ptr [r11+10h], 0
0x18000a40a  mov     [rsp+0D8h+var_A8], 0
0x18000a413  mov     [rsp+0D8h+arg_10], 0
0x18000a41e  mov     qword ptr [r11+20h], 0
0x18000a426  mov     [rsp+0D8h+Block], 0
0x18000a42f  lea     rdx, aCwliditemExecu; "CWLIDItem::Execute"
0x18000a436  mov     [r11-70h], rdx
0x18000a43a  lea     rax, [r11+8]
0x18000a43e  mov     [r11-68h], rax
0x18000a442  mov     qword ptr [r11-60h], 0
0x18000a44a  mov     qword ptr [r11-58h], 0
0x18000a452  mov     r8d, 48h ; 'H'; char *
0x18000a458  lea     r14, aWlidqueueCpp; "\\wlidqueue.cpp"
0x18000a45f  mov     rcx, r14; this
0x18000a462  call    ?TraceFunctionEnter@MsaTracingInternal@@YAKPEBD0KPEBG@Z; MsaTracingInternal::TraceFunctionEnter(char const *,char const *,ulong,ushort const *)
0x18000a467  nop
0x18000a468  cmp     qword ptr [rdi+48h], 0
0x18000a46d  jnz     short loc_18000A47F
0x18000a46f  mov     [rsp+0D8h+arg_0], 80070057h
0x18000a47a  jmp     loc_18000A7BE
0x18000a47f  cmp     byte ptr [rdi+60h], 0
0x18000a483  jz      short loc_18000A4AF
0x18000a485  lea     r9, aQueryHasBeenCa; "Query has been cancelled, not executing"...
0x18000a48c  mov     r8d, 55h ; 'U'; unsigned int
0x18000a492  mov     rdx, r14; char *
0x18000a495  lea     ecx, [r8-50h]; unsigned __int8
0x18000a499  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18000a49e  mov     ebx, 1
0x18000a4a3  mov     [rsp+0D8h+arg_0], ebx
0x18000a4aa  jmp     loc_18000A7BE
0x18000a4af  mov     ecx, 2; ImpersonationLevel
0x18000a4b4  call    cs:__imp_ImpersonateSelf
0x18000a4ba  test    eax, eax
0x18000a4bc  jnz     short loc_18000A4DC
0x18000a4be  call    cs:__imp_GetLastError
0x18000a4c4  test    eax, eax
0x18000a4c6  jle     short loc_18000A4D0
0x18000a4c8  movzx   eax, ax
0x18000a4cb  or      eax, 80070000h
0x18000a4d0  mov     [rsp+0D8h+arg_0], eax
0x18000a4d7  jmp     loc_18000A7BE
0x18000a4dc  mov     ebx, 1
0x18000a4e1  mov     [rsp+0D8h+arg_10], ebx
0x18000a4e8  lea     r9, [rsp+0D8h+arg_18]; void **
0x18000a4f0  call    ?WLIDCCreateContextEx@@YAJPEBG0_KPEAPEAX@Z; WLIDCCreateContextEx(ushort const *,ushort const *,unsigned __int64,void * *)
0x18000a4f5  mov     esi, eax
0x18000a4f7  mov     [rsp+0D8h+arg_0], eax
0x18000a4fe  cmp     eax, 8004800Ch
0x18000a503  jnz     short loc_18000A549
0x18000a505  lea     r9, aWlidccreatecon_0; "WLIDCCreateContextEx returned PPCRL_NO_"...
0x18000a50c  lea     r8d, [rbx+74h]; unsigned int
0x18000a510  mov     rdx, r14; char *
0x18000a513  lea     ecx, [rbx+4]; unsigned __int8
0x18000a516  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18000a51b  mov     [rsp+0D8h+arg_0], 0
0x18000a526  call    ?PPTraceShouldRedact@@YA_NXZ; PPTraceShouldRedact(void)
0x18000a52b  test    al, al
0x18000a52d  jz      loc_18000A5E9
0x18000a533  mov     cl, bl; this
0x18000a535  call    ?TraceOnFlag@PPTraceStatus@@YA_NE@Z; PPTraceStatus::TraceOnFlag(uchar)
0x18000a53a  test    al, al
0x18000a53c  jz      loc_18000A5E9
0x18000a542  mov     cl, bl
0x18000a544  jmp     loc_18000A5EB
0x18000a549  test    eax, eax
0x18000a54b  js      short loc_18000A579
0x18000a54d  lea     rax, [rsp+0D8h+Block]
0x18000a552  mov     [rsp+0D8h+var_B8], rax; struct __MIDL_liveidsvc_0003 **
0x18000a557  lea     r9, [rsp+0D8h+arg_8]; unsigned int *
0x18000a55f  mov     r8, [rdi+58h]; unsigned __int16 *
0x18000a563  mov     rcx, [rsp+0D8h+arg_18]; void *
0x18000a56b  call    ?WLIDCEnumerateUserAssociatedDevices@@YAJQEAXKPEAGPEAKPEAPEAU__MIDL_liveidsvc_0003@@@Z; WLIDCEnumerateUserAssociatedDevices(void * const,ulong,ushort *,ulong *,__MIDL_liveidsvc_0003 * *)
0x18000a570  mov     esi, eax
0x18000a572  mov     [rsp+0D8h+arg_0], eax
0x18000a579  test    esi, esi
0x18000a57b  jns     short loc_18000A526
0x18000a57d  call    ?PPTraceShouldRedact@@YA_NXZ; PPTraceShouldRedact(void)
0x18000a582  test    al, al
0x18000a584  jz      short loc_18000A595
0x18000a586  mov     cl, bl; this
0x18000a588  call    ?TraceOnFlag@PPTraceStatus@@YA_NE@Z; PPTraceStatus::TraceOnFlag(uchar)
0x18000a58d  test    al, al
0x18000a58f  jz      short loc_18000A595
0x18000a591  mov     cl, bl
0x18000a593  jmp     short loc_18000A597
0x18000a595  xor     cl, cl
0x18000a597  mov     rax, [rdi+58h]
0x18000a59b  mov     [rsp+0D8h+var_90], rax
0x18000a5a0  mov     [rsp+0D8h+var_88], 0
0x18000a5a9  mov     [rsp+0D8h+var_80], cl
0x18000a5ad  lea     rax, ??_7PPRedactedStringW@@6B@; const PPRedactedStringW::`vftable'
0x18000a5b4  mov     [rsp+0D8h+var_98], rax
0x18000a5b9  lea     rcx, [rsp+0D8h+var_98]; this
0x18000a5be  call    ?GetString@PPRedactedStringW@@QEAAPEBGXZ; PPRedactedStringW::GetString(void)
0x18000a5c3  mov     dword ptr [rsp+0D8h+var_B0], esi
0x18000a5c7  mov     [rsp+0D8h+var_B8], rax
0x18000a5cc  lea     r9, aFailedToEnumer; "Failed to enumerate devices for owner %"...
0x18000a5d3  mov     r8d, 88h; unsigned int
0x18000a5d9  mov     rdx, r14; char *
0x18000a5dc  mov     ecx, 2; unsigned __int8
0x18000a5e1  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18000a5e6  nop
0x18000a5e7  jmp     short loc_18000A642
0x18000a5e9  xor     cl, cl
0x18000a5eb  mov     rax, [rdi+58h]
0x18000a5ef  mov     [rsp+0D8h+var_90], rax
0x18000a5f4  mov     [rsp+0D8h+var_88], 0
0x18000a5fd  mov     [rsp+0D8h+var_80], cl
0x18000a601  lea     rax, ??_7PPRedactedStringW@@6B@; const PPRedactedStringW::`vftable'
0x18000a608  mov     [rsp+0D8h+var_98], rax
0x18000a60d  lea     rcx, [rsp+0D8h+var_98]; this
0x18000a612  call    ?GetString@PPRedactedStringW@@QEAAPEBGXZ; PPRedactedStringW::GetString(void)
0x18000a617  mov     [rsp+0D8h+var_B0], rax
0x18000a61c  mov     eax, [rsp+0D8h+arg_8]
0x18000a623  mov     dword ptr [rsp+0D8h+var_B8], eax
0x18000a627  lea     r9, aEnumeratedUDev; "Enumerated %u devices for owner %ls."
0x18000a62e  mov     r8d, 8Ch; unsigned int
0x18000a634  mov     rdx, r14; char *
0x18000a637  mov     ecx, 5; unsigned __int8
0x18000a63c  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18000a641  nop
0x18000a642  lea     rcx, [rsp+0D8h+var_98]; this
0x18000a647  call    ??1PPRedactedStringW@@QEAA@XZ; PPRedactedStringW::~PPRedactedStringW(void)
0x18000a64c  nop
0x18000a64d  cmp     byte ptr [rdi+60h], 0
0x18000a651  jz      short loc_18000A672
0x18000a653  lea     r9, aQueryHasBeenCa_0; "Query has been cancelled, droping resul"...
0x18000a65a  mov     r8d, 96h; unsigned int
0x18000a660  mov     rdx, r14; char *
0x18000a663  mov     ecx, 5; unsigned __int8
0x18000a668  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18000a66d  jmp     loc_18000A4A3
0x18000a672  lea     rdx, [rdi+10h]
0x18000a676  lea     rcx, [rsp+0D8h+var_98]
0x18000a67b  call    ??0?$CComCritSecLockWTry@VCComAutoCriticalSectionWTry@@@@QEAA@AEAVCComAutoCriticalSectionWTry@@_N@Z; CComCritSecLockWTry<CComAutoCriticalSectionWTry>::CComCritSecLockWTry<CComAutoCriticalSectionWTry>(CComAutoCriticalSectionWTry &,bool)
0x18000a680  nop
0x18000a681  cmp     byte ptr [rdi+60h], 0
0x18000a685  jz      short loc_18000A6B7
0x18000a687  lea     r9, aQueryHasBeenCa_0; "Query has been cancelled, droping resul"...
0x18000a68e  mov     r8d, 0A6h; unsigned int
0x18000a694  mov     rdx, r14; char *
0x18000a697  mov     ecx, 5; unsigned __int8
0x18000a69c  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18000a6a1  mov     [rsp+0D8h+arg_0], ebx
0x18000a6a8  lea     rcx, [rsp+0D8h+var_98]
0x18000a6ad  call    ??1?$CComCritSecLockWTry@VCComAutoCriticalSectionWTry@@@@QEAA@XZ; CComCritSecLockWTry<CComAutoCriticalSectionWTry>::~CComCritSecLockWTry<CComAutoCriticalSectionWTry>(void)
0x18000a6b2  jmp     loc_18000A7BE
0x18000a6b7  mov     edx, [rsp+0D8h+arg_0]
0x18000a6be  test    edx, edx
0x18000a6c0  js      loc_18000A764
0x18000a6c6  xor     esi, esi
0x18000a6c8  cmp     [rsp+0D8h+arg_8], esi
0x18000a6cf  jbe     loc_18000A760
0x18000a6d5  mov     eax, esi
0x18000a6d7  add     rax, rax
0x18000a6da  mov     rcx, [rsp+0D8h+Block]
0x18000a6df  lea     rdx, [rsp+0D8h+var_A8]
0x18000a6e4  mov     [rsp+0D8h+var_B8], rdx; struct IFunctionInstance **
0x18000a6e9  mov     r9, [rdi+40h]; struct IFunctionDiscoveryProviderFactory *
0x18000a6ed  mov     r8, [rdi+50h]; struct IFunctionDiscoveryProvider *
0x18000a6f1  mov     rdx, [rcx+rax*8+8]; unsigned __int16 *
0x18000a6f6  mov     rcx, [rcx+rax*8]; Source
0x18000a6fa  call    ?BuildInstance@CWLIDFDProv@@SAJPEAG0PEAUIFunctionDiscoveryProvider@@PEAUIFunctionDiscoveryProviderFactory@@PEAPEAUIFunctionInstance@@@Z; CWLIDFDProv::BuildInstance(ushort *,ushort *,IFunctionDiscoveryProvider *,IFunctionDiscoveryProviderFactory *,IFunctionInstance * *)
0x18000a6ff  mov     [rsp+0D8h+arg_0], eax
0x18000a706  test    eax, eax
0x18000a708  js      short loc_18000A73B
0x18000a70a  mov     rcx, [rdi+48h]
0x18000a70e  mov     rax, [rcx]
0x18000a711  mov     r9, [rsp+0D8h+var_A8]
0x18000a716  xor     r8d, r8d
0x18000a719  xor     edx, edx
0x18000a71b  mov     rax, [rax+18h]
0x18000a71f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a724  lea     rcx, [rsp+0D8h+var_A8]
0x18000a729  call    ?Release@?$CComPtrBase@UIFunctionInstance@@@ATL@@QEAAXXZ; ATL::CComPtrBase<IFunctionInstance>::Release(void)
0x18000a72e  add     esi, ebx
0x18000a730  cmp     esi, [rsp+0D8h+arg_8]
0x18000a737  jb      short loc_18000A6D5
0x18000a739  jmp     short loc_18000A759
0x18000a73b  mov     dword ptr [rsp+0D8h+var_B8], eax
0x18000a73f  lea     r9, aFailedToBuildI; "Failed to build instance. (0x%x)"
0x18000a746  mov     r8d, 0C3h; unsigned int
0x18000a74c  mov     rdx, r14; char *
0x18000a74f  mov     ecx, 2; unsigned __int8
0x18000a754  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18000a759  mov     edx, [rsp+0D8h+arg_0]
0x18000a760  test    edx, edx
0x18000a762  jns     short loc_18000A79A
0x18000a764  cmp     edx, 80048821h
0x18000a76a  jz      short loc_18000A774
0x18000a76c  cmp     edx, 800488E5h
0x18000a772  jnz     short loc_18000A780
0x18000a774  mov     edx, 80070056h
0x18000a779  mov     [rsp+0D8h+arg_0], edx
0x18000a780  mov     rcx, [rdi+48h]
0x18000a784  mov     rax, [rcx]
0x18000a787  lea     r9, aProviderMicros; "Provider\\Microsoft.WindowsLive.Devices"
0x18000a78e  xor     r8d, r8d
0x18000a791  mov     rax, [rax+20h]
0x18000a795  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a79a  mov     rcx, [rdi+48h]
0x18000a79e  mov     rax, [rcx]
0x18000a7a1  lea     r9, aProviderMicros; "Provider\\Microsoft.WindowsLive.Devices"
0x18000a7a8  xor     r8d, r8d
0x18000a7ab  mov     edx, 3E8h
0x18000a7b0  mov     rax, [rax+28h]
0x18000a7b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a7b9  jmp     loc_18000A6A8
0x18000a7be  cmp     [rsp+0D8h+arg_18], 0
0x18000a7c7  jz      short loc_18000A7D7
0x18000a7c9  lea     rdx, [rsp+0D8h+arg_18]; void **
0x18000a7d1  call    ?WLIDCDeleteContextEx@@YAJ_KPEAPEAX@Z; WLIDCDeleteContextEx(unsigned __int64,void * *)
0x18000a7d6  nop
0x18000a7d7  mov     rcx, [rsp+0D8h+Block]; Block
0x18000a7dc  test    rcx, rcx
0x18000a7df  jz      short loc_18000A7E7
0x18000a7e1  call    cs:__imp_free
0x18000a7e7  cmp     [rsp+0D8h+arg_10], 0
0x18000a7ef  jz      short loc_18000A7F7
0x18000a7f1  call    cs:__imp_RevertToSelf
0x18000a7f7  mov     ebx, [rsp+0D8h+arg_0]
0x18000a7fe  lea     rcx, [rsp+0D8h+var_70]
0x18000a803  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x18000a808  nop
0x18000a809  lea     rcx, [rsp+0D8h+var_A8]
0x18000a80e  call    ??1?$CComPtrBase@UIFunctionInstanceCollection@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IFunctionInstanceCollection>::~CComPtrBase<IFunctionInstanceCollection>(void)
0x18000a813  mov     eax, ebx
0x18000a815  add     rsp, 0B8h
0x18000a81c  pop     r14
0x18000a81e  pop     rdi
0x18000a81f  pop     rsi
0x18000a820  pop     rbx
0x18000a821  retn
0x18000a822  jmp     short loc_18000A7BE
0x18000a824  jmp     short loc_18000A7BE
0x18000a826  jmp     short loc_18000A7BE
0x18000a828  jmp     short loc_18000A7D7
0x18000a82a  jmp     short loc_18000A7D7
0x18000a82c  jmp     short loc_18000A7D7
```
