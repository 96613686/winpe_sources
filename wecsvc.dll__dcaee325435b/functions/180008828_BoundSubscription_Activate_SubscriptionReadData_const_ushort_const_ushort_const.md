# BoundSubscription::Activate(SubscriptionReadData const &,ushort const *,ushort const *)

- ea: `0x180008828`
- end: `0x18000915f`
- name: `?Activate@BoundSubscription@@QEAAXAEBVSubscriptionReadData@@PEBG1@Z`
- size: `2359`
- prototype: `void __fastcall(BoundSubscription *__hidden this, const struct SubscriptionReadData *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `27`
- tags: `service_task, broker_com_uri`

## callers

- `0x180009170`

## callees

- `0x18000195c`
- `0x1800032dc`
- `0x1800062d4`
- `0x180006334`
- `0x18000669c`
- `0x180007fec`
- `0x1800083e0`
- `0x180008828`
- `0x18000c724`
- `0x18000dc4c`
- `0x18000f7b0`
- `0x180010058`
- `0x1800103b8`
- `0x1800112e8`
- `0x180011878`
- `0x180013194`
- `0x18001de6c`
- `0x18001df04`
- `0x18001e08c`
- `0x18001e0cc`
- `0x18001e18c`
- `0x18001e1cc`
- `0x18001e20c`
- `0x18001e660`
- `0x18001e734`
- `0x18001f000`
- `0x18001fe50`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180008a24`
- `msvcrt!_wcsicmp` at `0x180008a24`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180008880`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180008880`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000908b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000908b`
- `WsmSvc!WSManCreateSessionInternal` at `0x180008e1c`
- `WsmSvc!WSManCreateSessionInternal` at `0x180008f18`
- `WsmSvc!WSManCreateSessionInternal` at `0x180008e1c`
- `WsmSvc!WSManCreateSessionInternal` at `0x180008f18`

## string_xrefs

- `0x180008abf`: `admin\wmi\events\forwarding\collector\service\submgr.cpp`
- `0x180008b61`: `admin\wmi\events\forwarding\collector\service\submgr.cpp`
- `0x180008c00`: `admin\wmi\events\forwarding\collector\service\submgr.cpp`
- `0x180008e93`: `admin\wmi\events\forwarding\collector\service\submgr.cpp`
- `0x180009113`: `admin\wmi\events\forwarding\collector\service\submgr.cpp`

## pseudocode

```c
void __fastcall BoundSubscription::Activate(
        BoundSubscription *this,
        const struct SubscriptionReadData *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4)
{
  struct _RTL_CRITICAL_SECTION *v8; // r13
  _QWORD *v9; // rcx
  _QWORD *v10; // r9
  _WORD *v11; // rcx
  const unsigned __int16 **v12; // rbx
  const unsigned __int16 *v13; // rdx
  const unsigned __int16 *v14; // rcx
  enum _EC_SUBSCRIPTION_DELIVERY_MODE DeliveryMode; // eax
  bool v16; // zf
  int v17; // eax
  BoundSubscription *v18; // rax
  const wchar_t *v19; // rcx
  _QWORD *v20; // r8
  _QWORD *v21; // r8
  _QWORD *v22; // rax
  WSMAN_SESSION_HANDLE *v23; // rbx
  int SessionInternal; // esi
  __int64 v25; // rdx
  unsigned int v26; // edx
  _WORD **v27; // rdx
  _WORD *v28; // rcx
  __int64 v29; // rdx
  __int64 v30; // rdx
  unsigned int v31; // ebx
  unsigned __int64 v32; // [rsp+20h] [rbp-E0h]
  unsigned int v33; // [rsp+40h] [rbp-C0h] BYREF
  bool v34; // [rsp+44h] [rbp-BCh] BYREF
  void **pExceptionObject; // [rsp+48h] [rbp-B8h] BYREF
  char v36; // [rsp+50h] [rbp-B0h]
  const char *v37; // [rsp+58h] [rbp-A8h]
  __int64 v38; // [rsp+60h] [rbp-A0h]
  __int64 v39; // [rsp+68h] [rbp-98h]
  int v40; // [rsp+70h] [rbp-90h]
  int v41; // [rsp+74h] [rbp-8Ch]
  int v42; // [rsp+78h] [rbp-88h]
  __int128 v43; // [rsp+80h] [rbp-80h] BYREF
  const unsigned __int16 *v44; // [rsp+90h] [rbp-70h]
  _BYTE v45[24]; // [rsp+98h] [rbp-68h] BYREF
  unsigned int v46[4]; // [rsp+B0h] [rbp-50h] BYREF
  struct WSMAN_OBJECT *v47; // [rsp+C0h] [rbp-40h]
  char v48[8]; // [rsp+C8h] [rbp-38h] BYREF
  void (__fastcall *v49)(struct BoundSubscription *, bool); // [rsp+D0h] [rbp-30h]
  BoundSubscription *v50; // [rsp+D8h] [rbp-28h]
  char v51; // [rsp+E0h] [rbp-20h]
  __int128 v52; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v53; // [rsp+F8h] [rbp-8h]
  char *v54; // [rsp+100h] [rbp+0h]
  _QWORD v55[2]; // [rsp+108h] [rbp+8h] BYREF
  __int64 v56; // [rsp+118h] [rbp+18h]
  unsigned __int64 v57; // [rsp+120h] [rbp+20h]
  _QWORD v58[3]; // [rsp+128h] [rbp+28h] BYREF
  unsigned __int64 v59; // [rsp+140h] [rbp+40h]
  _WORD v60[8]; // [rsp+148h] [rbp+48h] BYREF
  __int64 v61; // [rsp+158h] [rbp+58h]
  __int64 v62; // [rsp+160h] [rbp+60h]

  v48[0] = 0;
  v49 = MyInternalDeactivate;
  v50 = this;
  v51 = 1;
  v8 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 16);
  v54 = (char *)this + 16;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    v9 = (_QWORD *)((char *)this + 72);
    if ( *((_QWORD *)this + 12) >= 8u )
      v9 = (_QWORD *)*v9;
    v10 = (_QWORD *)(*((_QWORD *)this + 8) + 56LL);
    if ( *(_QWORD *)(*((_QWORD *)this + 8) + 80LL) >= 8u )
      v10 = (_QWORD *)*v10;
    WPP_SF_SSq(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      32,
      (_DWORD)WPP_GLOBAL_Control,
      (_DWORD)v10,
      (__int64)v9,
      (char)this);
  }
  *((_DWORD *)this + 45) = 0;
  if ( *((_QWORD *)this + 26) < 8u )
    v11 = (_WORD *)((char *)this + 184);
  else
    v11 = (_WORD *)*((_QWORD *)this + 23);
  *((_QWORD *)this + 25) = 0;
  *v11 = 0;
  v12 = (const unsigned __int16 **)((char *)this + 72);
  if ( *((_QWORD *)this + 12) < 8u )
    v13 = (const unsigned __int16 *)((char *)this + 72);
  else
    v13 = *v12;
  v14 = (const unsigned __int16 *)(*((_QWORD *)this + 8) + 56LL);
  if ( *(_QWORD *)(*((_QWORD *)this + 8) + 80LL) >= 8u )
    v14 = *(const unsigned __int16 **)v14;
  WriteSavedRunTimeStatus(v14, v13, 0, &word_180026AD8, 0, 1);
  *((_DWORD *)this + 96) = 513;
  DeliveryMode = SubscriptionReadData::GetDeliveryMode(a2);
  *((_DWORD *)this + 42) = DeliveryMode;
  v16 = DeliveryMode == EcDeliveryModePull;
  v17 = 128;
  if ( v16 )
    v17 = 16;
  *((_DWORD *)this + 96) |= v17;
  v59 = 7;
  v58[2] = 0;
  LOWORD(v58[0]) = 0;
  v33 = 0;
  ReadMetadataProp(*(const struct tag_EcRpcMetadataPropertyList **)a2, 0x15u, &v33);
  *(_OWORD *)v46 = 0;
  v47 = 0;
  v62 = 7;
  v61 = 0;
  v60[0] = 0;
  SubscriptionReadData::GetLocale(a2, v60);
  SubscriptionReadData::GetURI(a2, (char *)this + 136);
  v52 = 0;
  v53 = 0;
  InitWSManConnectionOptions(v60, &v52);
  if ( *((_QWORD *)this + 11) )
  {
    v18 = *((_QWORD *)this + 12) < 8u ? (BoundSubscription *)((char *)this + 72) : (BoundSubscription *)*v12;
    if ( *(_WORD *)v18 )
    {
      v19 = *((_QWORD *)this + 12) < 8u ? (const wchar_t *)((char *)this + 72) : *v12;
      if ( _wcsicmp(v19, L"localhost") )
      {
        std::wstring::operator=(v58, (char *)this + 72);
        v43 = 0;
        v44 = 0;
        if ( v33 )
        {
          switch ( v33 )
          {
            case 1u:
              if ( a3 && *a3 )
              {
                *((_QWORD *)&v43 + 1) = a3;
                v44 = a4;
              }
              LODWORD(v43) = 4;
LABEL_61:
              memset(v45, 0, sizeof(v45));
              v57 = 7;
              v56 = 0;
              LOWORD(v55[0]) = 0;
              SubscriptionReadData::GetTransportName(a2, v55);
              if ( v56 )
              {
                std::vector<unsigned short>::resize(v45, v56 + 20 + *((_QWORD *)this + 11));
                v33 = 0;
                ReadMetadataProp(*(const struct tag_EcRpcMetadataPropertyList **)a2, 0xCu, &v33);
                if ( v33 )
                {
                  v33 = 0;
                  ReadMetadataProp(*(const struct tag_EcRpcMetadataPropertyList **)a2, 0xCu, &v33);
                  if ( *((_QWORD *)this + 12) >= 8u )
                    v12 = (const unsigned __int16 **)*v12;
                  v21 = v55;
                  if ( v57 >= 8 )
                    v21 = (_QWORD *)v55[0];
                  LODWORD(v32) = v33;
                  StringPrintf(v45, L"%s://%s:%u", v21, v12, v32);
                }
                else
                {
                  if ( *((_QWORD *)this + 12) >= 8u )
                    v12 = (const unsigned __int16 **)*v12;
                  v20 = v55;
                  if ( v57 >= 8 )
                    v20 = (_QWORD *)v55[0];
                  StringPrintf(v45, L"%s://%s", v20, v12);
                }
              }
              else
              {
                v33 = 0;
                ReadMetadataProp(*(const struct tag_EcRpcMetadataPropertyList **)a2, 0xCu, &v33);
                if ( !v33 )
                {
LABEL_78:
                  v22 = v58;
                  if ( v59 >= 8 )
                    v22 = (_QWORD *)v58[0];
                  v23 = (WSMAN_SESSION_HANDLE *)((char *)this + 288);
                  SessionInternal = WSManCreateSessionInternal(
                                      v22,
                                      8,
                                      &v43,
                                      0,
                                      (unsigned __int64)&v52 & -(__int64)(v61 != 0),
                                      v46,
                                      (char *)this + 288,
                                      0);
                  LOBYTE(v25) = 1;
                  std::wstring::_Tidy(v55, v25, 0);
                  std::vector<_WSMAN_OPTION>::~vector<_WSMAN_OPTION>(v45);
                  goto LABEL_88;
                }
                std::vector<unsigned short>::resize(v45, *((_QWORD *)this + 11) + 20LL);
                v33 = 0;
                ReadMetadataProp(*(const struct tag_EcRpcMetadataPropertyList **)a2, 0xCu, &v33);
                if ( *((_QWORD *)this + 12) >= 8u )
                  v12 = (const unsigned __int16 **)*v12;
                StringPrintf(v45, L"%s:%u", v12, v33);
              }
              std::wstring::assign(v58, *(_QWORD *)v45);
              goto LABEL_78;
            case 2u:
              if ( !a3 || !*a3 )
              {
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                {
                  WPP_SF_D(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    34,
                    &WPP_311dc52e399f3c6238c54a9ac88e2061_Traceguids,
                    87);
                }
                v36 = 0;
                v37 = "admin\\wmi\\events\\forwarding\\collector\\service\\submgr.cpp";
                v38 = 0;
                v39 = 0;
                v40 = 87;
                v41 = -1;
                v42 = 1319;
                pExceptionObject = &wmi::GenericException::`vftable';
                throw (wmi::GenericException *)&pExceptionObject;
              }
              LODWORD(v43) = 2;
              break;
            case 3u:
              if ( !a3 || !*a3 )
              {
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                {
                  WPP_SF_D(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    35,
                    &WPP_311dc52e399f3c6238c54a9ac88e2061_Traceguids,
                    87);
                }
                v36 = 0;
                v37 = "admin\\wmi\\events\\forwarding\\collector\\service\\submgr.cpp";
                v38 = 0;
                v39 = 0;
                v40 = 87;
                v41 = -1;
                v42 = 1328;
                pExceptionObject = &wmi::GenericException::`vftable';
                throw (wmi::GenericException *)&pExceptionObject;
              }
              LODWORD(v43) = 8;
              break;
            case 4u:
              goto LABEL_61;
            default:
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, &WPP_311dc52e399f3c6238c54a9ac88e2061_Traceguids, 87);
              }
              v36 = 0;
              v37 = "admin\\wmi\\events\\forwarding\\collector\\service\\submgr.cpp";
              v38 = 0;
              v39 = 0;
              v40 = 87;
              v41 = -1;
              v42 = 1336;
              pExceptionObject = &wmi::GenericException::`vftable';
              throw (wmi::GenericException *)&pExceptionObject;
          }
        }
        else if ( !a3 || !*a3 )
        {
          goto LABEL_61;
        }
        *((_QWORD *)&v43 + 1) = a3;
        v44 = a4;
        goto LABEL_61;
      }
    }
  }
  if ( *((_DWORD *)this + 42) == 2 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, &WPP_311dc52e399f3c6238c54a9ac88e2061_Traceguids, 50);
    }
    v36 = 0;
    v37 = "admin\\wmi\\events\\forwarding\\collector\\service\\submgr.cpp";
    v38 = 0;
    v39 = 0;
    v40 = 50;
    v41 = -1;
    v42 = 1266;
    pExceptionObject = &wmi::GenericException::`vftable';
    throw (wmi::GenericException *)&pExceptionObject;
  }
  *(_QWORD *)v45 = 4;
  *(_OWORD *)&v45[8] = 0;
  v23 = (WSMAN_SESSION_HANDLE *)((char *)this + 288);
  SessionInternal = WSManCreateSessionInternal(0, 0, v45, 0, 0, v46, (char *)this + 288, 0);
LABEL_88:
  if ( !SessionInternal || !*v23 )
  {
    BoundSubscription::RecordLastError(this, v46[2], v47);
    v31 = v46[2];
    if ( !v46[2] )
      v31 = 1287;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 37, &WPP_311dc52e399f3c6238c54a9ac88e2061_Traceguids, v31);
    }
    v36 = 0;
    v37 = "admin\\wmi\\events\\forwarding\\collector\\service\\submgr.cpp";
    v38 = 0;
    v39 = 0;
    v40 = v31;
    v41 = -1;
    v42 = 1376;
    pExceptionObject = &wmi::GenericException::`vftable';
    throw (wmi::GenericException *)&pExceptionObject;
  }
  if ( v61 )
    SetWSManSessionOptionsLocales(*v23);
  SubscriptionReadData::GetDialect(a2, (char *)this + 432);
  SubscriptionReadData::GetQuery(a2, (char *)this + 464);
  *(_QWORD *)((char *)this + 500) = 0;
  ReadMetadataProp(*(const struct tag_EcRpcMetadataPropertyList **)a2, v26, (struct _FILETIME *)((char *)this + 500));
  v33 = 2;
  ReadMetadataProp(*(const struct tag_EcRpcMetadataPropertyList **)a2, 0x12u, &v33);
  *((_DWORD *)this + 43) = v33;
  v34 = 0;
  ReadMetadataProp(*(const struct tag_EcRpcMetadataPropertyList **)a2, 0x19u, &v34);
  *((_BYTE *)this + 176) = v34;
  *((_DWORD *)this + 97) = -1;
  v33 = -1;
  ReadMetadataProp(*(const struct tag_EcRpcMetadataPropertyList **)a2, 0xEu, &v33);
  *((_DWORD *)this + 98) = v33;
  v33 = 15000;
  ReadMetadataProp(*(const struct tag_EcRpcMetadataPropertyList **)a2, 0xFu, &v33);
  *((_DWORD *)this + 99) = v33;
  v33 = 900000;
  ReadMetadataProp(*(const struct tag_EcRpcMetadataPropertyList **)a2, 0x10u, &v33);
  *((_DWORD *)this + 124) = v33;
  v27 = (_WORD **)((char *)this + 400);
  if ( *((_QWORD *)this + 53) < 8u )
    v28 = (_WORD *)((char *)this + 400);
  else
    v28 = *v27;
  *((_QWORD *)this + 52) = 0;
  *v28 = 0;
  if ( *((_DWORD *)this + 42) == 2 )
    SubscriptionReadData::GetHostName(a2, v27);
  BoundSubscription::EnterSubscribingState(this);
  v48[0] = 1;
  LOBYTE(v29) = 1;
  std::wstring::_Tidy(v60, v29, 0);
  LOBYTE(v30) = 1;
  std::wstring::_Tidy(v58, v30, 0);
  LeaveCriticalSection(v8);
  wmi::ScopeGuardImpl2<void (*)(BoundSubscription *,bool),BoundSubscription *,bool>::~ScopeGuardImpl2<void (*)(BoundSubscription *,bool),BoundSubscription *,bool>(v48);
}

```

## disassembly

```asm
0x180008828  push    rbp
0x18000882a  push    rbx
0x18000882b  push    rsi
0x18000882c  push    rdi
0x18000882d  push    r12
0x18000882f  push    r13
0x180008831  push    r14
0x180008833  push    r15
0x180008835  lea     rbp, [rsp-78h]
0x18000883a  sub     rsp, 178h
0x180008841  mov     rax, cs:__security_cookie
0x180008848  xor     rax, rsp
0x18000884b  mov     [rbp+0B0h+var_48], rax
0x18000884f  mov     r12, r9
0x180008852  mov     rsi, r8
0x180008855  mov     r15, rdx
0x180008858  mov     rdi, rcx
0x18000885b  xor     r14d, r14d
0x18000885e  mov     [rbp+0B0h+var_E8], r14b
0x180008862  lea     rax, ?MyInternalDeactivate@@YAXPEAVBoundSubscription@@_N@Z; MyInternalDeactivate(BoundSubscription *,bool)
0x180008869  mov     [rbp+0B0h+var_E0], rax
0x18000886d  mov     [rbp+0B0h+var_D8], rcx
0x180008871  mov     [rbp+0B0h+var_D0], 1
0x180008875  lea     r13, [rcx+10h]
0x180008879  mov     [rbp+0B0h+var_B0], r13
0x18000887d  mov     rcx, r13; lpCriticalSection
0x180008880  call    cs:__imp_EnterCriticalSection
0x180008886  nop
0x180008887  lea     rax, WPP_GLOBAL_Control
0x18000888e  mov     r8, cs:WPP_GLOBAL_Control
0x180008895  cmp     r8, rax
0x180008898  jz      short loc_1800088E0
0x18000889a  test    byte ptr [r8+1Ch], 10h
0x18000889f  jz      short loc_1800088E0
0x1800088a1  cmp     byte ptr [r8+19h], 4
0x1800088a6  jb      short loc_1800088E0
0x1800088a8  lea     rcx, [rdi+48h]
0x1800088ac  cmp     qword ptr [rcx+18h], 8
0x1800088b1  jb      short loc_1800088B6
0x1800088b3  mov     rcx, [rcx]
0x1800088b6  mov     r9, [rdi+40h]
0x1800088ba  add     r9, 38h ; '8'
0x1800088be  cmp     qword ptr [r9+18h], 8
0x1800088c3  jb      short loc_1800088C8
0x1800088c5  mov     r9, [r9]
0x1800088c8  mov     edx, 20h ; ' '
0x1800088cd  mov     qword ptr [rsp+1B0h+var_188], rdi
0x1800088d2  mov     [rsp+1B0h+var_190], rcx
0x1800088d7  mov     rcx, [r8+10h]
0x1800088db  call    WPP_SF_SSq
0x1800088e0  mov     [rdi+0B4h], r14d
0x1800088e7  lea     rax, [rdi+0B8h]
0x1800088ee  cmp     qword ptr [rax+18h], 8
0x1800088f3  jb      short loc_1800088FA
0x1800088f5  mov     rcx, [rax]
0x1800088f8  jmp     short loc_1800088FD
0x1800088fa  mov     rcx, rax
0x1800088fd  mov     [rax+10h], r14
0x180008901  mov     [rcx], r14w
0x180008905  lea     rbx, [rdi+48h]
0x180008909  cmp     qword ptr [rbx+18h], 8
0x18000890e  jb      short loc_180008915
0x180008910  mov     rdx, [rbx]
0x180008913  jmp     short loc_180008918
0x180008915  mov     rdx, rbx; unsigned __int16 *
0x180008918  mov     rcx, [rdi+40h]
0x18000891c  add     rcx, 38h ; '8'
0x180008920  cmp     qword ptr [rcx+18h], 8
0x180008925  jb      short loc_18000892A
0x180008927  mov     rcx, [rcx]; unsigned __int16 *
0x18000892a  mov     [rsp+1B0h+var_188], 1; bool
0x18000892f  mov     [rsp+1B0h+var_190], r14; unsigned __int64
0x180008934  lea     r9, word_180026AD8; unsigned __int16 *
0x18000893b  xor     r8d, r8d; unsigned int
0x18000893e  call    ?WriteSavedRunTimeStatus@@YAXPEBG0K0_K_N@Z; WriteSavedRunTimeStatus(ushort const *,ushort const *,ulong,ushort const *,unsigned __int64,bool)
0x180008943  mov     dword ptr [rdi+180h], 201h
0x18000894d  mov     rcx, r15; this
0x180008950  call    ?GetDeliveryMode@SubscriptionReadData@@QEBA?AW4_EC_SUBSCRIPTION_DELIVERY_MODE@@XZ; SubscriptionReadData::GetDeliveryMode(void)
0x180008955  mov     [rdi+0A8h], eax
0x18000895b  cmp     eax, 1
0x18000895e  mov     eax, 80h
0x180008963  jnz     short loc_18000896A
0x180008965  mov     eax, 10h
0x18000896a  or      [rdi+180h], eax
0x180008970  mov     [rbp+0B0h+var_70], 7
0x180008978  mov     [rbp+0B0h+var_78], r14
0x18000897c  mov     word ptr [rbp+0B0h+var_88], r14w
0x180008981  mov     [rsp+1B0h+var_170], r14d
0x180008986  lea     r8, [rsp+1B0h+var_170]; unsigned int *
0x18000898b  mov     edx, 15h; unsigned int
0x180008990  mov     rcx, [r15]; struct tag_EcRpcMetadataPropertyList *
0x180008993  call    ?ReadMetadataProp@@YA_NAEBUtag_EcRpcMetadataPropertyList@@KAEAK@Z; ReadMetadataProp(tag_EcRpcMetadataPropertyList const &,ulong,ulong &)
0x180008998  xorps   xmm0, xmm0
0x18000899b  xor     eax, eax
0x18000899d  movups  xmmword ptr [rbp+0B0h+var_100], xmm0
0x1800089a1  mov     [rbp+0B0h+var_F0], rax
0x1800089a5  mov     [rbp+0B0h+var_50], 7
0x1800089ad  mov     [rbp+0B0h+var_58], r14
0x1800089b1  mov     [rbp+0B0h+var_68], r14w
0x1800089b6  lea     rdx, [rbp+0B0h+var_68]
0x1800089ba  mov     rcx, r15
0x1800089bd  call    ?GetLocale@SubscriptionReadData@@QEBAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; SubscriptionReadData::GetLocale(std::wstring &)
0x1800089c2  lea     rdx, [rdi+88h]
0x1800089c9  mov     rcx, r15
0x1800089cc  call    ?GetURI@SubscriptionReadData@@QEBAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; SubscriptionReadData::GetURI(std::wstring &)
0x1800089d1  xorps   xmm0, xmm0
0x1800089d4  xor     eax, eax
0x1800089d6  movups  [rbp+0B0h+var_C8], xmm0
0x1800089da  mov     [rbp+0B0h+var_B8], rax
0x1800089de  lea     rdx, [rbp+0B0h+var_C8]
0x1800089e2  lea     rcx, [rbp+0B0h+var_68]
0x1800089e6  call    ?InitWSManConnectionOptions@@YAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAU_WSMAN_CONNECTION_OPTIONS@@@Z; InitWSManConnectionOptions(std::wstring &,_WSMAN_CONNECTION_OPTIONS &)
0x1800089eb  cmp     [rdi+58h], r14
0x1800089ef  jz      loc_180008E41
0x1800089f5  cmp     qword ptr [rbx+18h], 8
0x1800089fa  jb      short loc_180008A01
0x1800089fc  mov     rax, [rbx]
0x1800089ff  jmp     short loc_180008A04
0x180008a01  mov     rax, rbx
0x180008a04  cmp     [rax], r14w
0x180008a08  jz      loc_180008E41
0x180008a0e  cmp     qword ptr [rbx+18h], 8
0x180008a13  jb      short loc_180008A1A
0x180008a15  mov     rcx, [rbx]
0x180008a18  jmp     short loc_180008A1D
0x180008a1a  mov     rcx, rbx; String1
0x180008a1d  lea     rdx, aLocalhost; "localhost"
0x180008a24  call    cs:__imp__wcsicmp
0x180008a2a  test    eax, eax
0x180008a2c  jz      loc_180008E41
0x180008a32  mov     rdx, rbx
0x180008a35  lea     rcx, [rbp+0B0h+var_88]
0x180008a39  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x180008a3e  xorps   xmm0, xmm0
0x180008a41  xor     eax, eax
0x180008a43  movups  [rbp+0B0h+var_130], xmm0
0x180008a47  mov     [rbp+0B0h+var_120], rax
0x180008a4b  mov     ecx, [rsp+1B0h+var_170]
0x180008a4f  xor     edx, edx
0x180008a51  lea     r14d, [rax+2]
0x180008a55  test    ecx, ecx
0x180008a57  jz      loc_180008C67
0x180008a5d  sub     ecx, 1
0x180008a60  jz      loc_180008C4C
0x180008a66  sub     ecx, 1
0x180008a69  jz      loc_180008BAD
0x180008a6f  sub     ecx, 1
0x180008a72  jz      loc_180008B0B
0x180008a78  cmp     ecx, 1
0x180008a7b  jz      loc_180008C79
0x180008a81  lea     ebx, [rax+57h]
0x180008a84  mov     rcx, cs:WPP_GLOBAL_Control
0x180008a8b  lea     rax, WPP_GLOBAL_Control
0x180008a92  cmp     rcx, rax
0x180008a95  jz      short loc_180008ABB
0x180008a97  test    byte ptr [rcx+1Ch], 10h
0x180008a9b  jz      short loc_180008ABB
0x180008a9d  cmp     [rcx+19h], r14b
0x180008aa1  jb      short loc_180008ABB
0x180008aa3  lea     edx, [rbx-33h]
0x180008aa6  mov     r9d, ebx
0x180008aa9  lea     r8, WPP_311dc52e399f3c6238c54a9ac88e2061_Traceguids
0x180008ab0  mov     rcx, [rcx+10h]
0x180008ab4  call    WPP_SF_D
0x180008ab9  xor     edx, edx
0x180008abb  mov     [rsp+1B0h+var_160], dl
0x180008abf  lea     rax, aAdminWmiEvents_8; "admin\\wmi\\events\\forwarding\\collect"...
0x180008ac6  mov     [rsp+1B0h+var_158], rax
0x180008acb  mov     [rsp+1B0h+var_150], rdx
0x180008ad0  mov     [rsp+1B0h+var_148], 0
0x180008ad9  mov     [rsp+1B0h+var_140], ebx
0x180008add  mov     [rsp+1B0h+var_13C], 0FFFFFFFFh
0x180008ae5  mov     [rsp+1B0h+var_138], 538h
0x180008aed  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x180008af4  mov     [rsp+1B0h+pExceptionObject], rax
0x180008af9  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x180008b00  lea     rcx, [rsp+1B0h+pExceptionObject]; pExceptionObject
0x180008b05  call    _CxxThrowException_0
0x180008b0b  test    rsi, rsi
0x180008b0e  jz      short loc_180008B21
0x180008b10  cmp     [rsi], dx
0x180008b13  jz      short loc_180008B21
0x180008b15  mov     dword ptr [rbp+0B0h+var_130], 8
0x180008b1c  jmp     loc_180008C71
0x180008b21  mov     ebx, 57h ; 'W'
0x180008b26  mov     rcx, cs:WPP_GLOBAL_Control
0x180008b2d  lea     rax, WPP_GLOBAL_Control
0x180008b34  cmp     rcx, rax
0x180008b37  jz      short loc_180008B5D
0x180008b39  test    byte ptr [rcx+1Ch], 10h
0x180008b3d  jz      short loc_180008B5D
0x180008b3f  cmp     [rcx+19h], r14b
0x180008b43  jb      short loc_180008B5D
0x180008b45  lea     edx, [rbx-34h]
0x180008b48  mov     r9d, ebx
0x180008b4b  lea     r8, WPP_311dc52e399f3c6238c54a9ac88e2061_Traceguids
0x180008b52  mov     rcx, [rcx+10h]
0x180008b56  call    WPP_SF_D
0x180008b5b  xor     edx, edx
0x180008b5d  mov     [rsp+1B0h+var_160], dl
0x180008b61  lea     rax, aAdminWmiEvents_8; "admin\\wmi\\events\\forwarding\\collect"...
0x180008b68  mov     [rsp+1B0h+var_158], rax
0x180008b6d  mov     [rsp+1B0h+var_150], rdx
0x180008b72  mov     [rsp+1B0h+var_148], 0
0x180008b7b  mov     [rsp+1B0h+var_140], ebx
0x180008b7f  mov     [rsp+1B0h+var_13C], 0FFFFFFFFh
0x180008b87  mov     [rsp+1B0h+var_138], 530h
0x180008b8f  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x180008b96  mov     [rsp+1B0h+pExceptionObject], rax
0x180008b9b  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x180008ba2  lea     rcx, [rsp+1B0h+pExceptionObject]; pExceptionObject
0x180008ba7  call    _CxxThrowException_0
0x180008bad  test    rsi, rsi
0x180008bb0  jz      short loc_180008BC0
0x180008bb2  cmp     [rsi], dx
0x180008bb5  jz      short loc_180008BC0
0x180008bb7  mov     dword ptr [rbp+0B0h+var_130], r14d
0x180008bbb  jmp     loc_180008C71
0x180008bc0  mov     ebx, 57h ; 'W'
0x180008bc5  mov     rcx, cs:WPP_GLOBAL_Control
0x180008bcc  lea     rax, WPP_GLOBAL_Control
0x180008bd3  cmp     rcx, rax
0x180008bd6  jz      short loc_180008BFC
0x180008bd8  test    byte ptr [rcx+1Ch], 10h
0x180008bdc  jz      short loc_180008BFC
0x180008bde  cmp     [rcx+19h], r14b
0x180008be2  jb      short loc_180008BFC
0x180008be4  lea     edx, [rbx-35h]
0x180008be7  mov     r9d, ebx
0x180008bea  lea     r8, WPP_311dc52e399f3c6238c54a9ac88e2061_Traceguids
0x180008bf1  mov     rcx, [rcx+10h]
0x180008bf5  call    WPP_SF_D
0x180008bfa  xor     edx, edx
0x180008bfc  mov     [rsp+1B0h+var_160], dl
0x180008c00  lea     rax, aAdminWmiEvents_8; "admin\\wmi\\events\\forwarding\\collect"...
0x180008c07  mov     [rsp+1B0h+var_158], rax
0x180008c0c  mov     [rsp+1B0h+var_150], rdx
0x180008c11  mov     [rsp+1B0h+var_148], 0
0x180008c1a  mov     [rsp+1B0h+var_140], ebx
0x180008c1e  mov     [rsp+1B0h+var_13C], 0FFFFFFFFh
0x180008c26  mov     [rsp+1B0h+var_138], 527h
0x180008c2e  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x180008c35  mov     [rsp+1B0h+pExceptionObject], rax
0x180008c3a  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x180008c41  lea     rcx, [rsp+1B0h+pExceptionObject]; pExceptionObject
0x180008c46  call    _CxxThrowException_0
0x180008c4c  test    rsi, rsi
0x180008c4f  jz      short loc_180008C5E
0x180008c51  cmp     [rsi], dx
0x180008c54  jz      short loc_180008C5E
0x180008c56  mov     qword ptr [rbp+0B0h+var_130+8], rsi
0x180008c5a  mov     [rbp+0B0h+var_120], r12
0x180008c5e  mov     dword ptr [rbp+0B0h+var_130], 4
0x180008c65  jmp     short loc_180008C79
0x180008c67  test    rsi, rsi
0x180008c6a  jz      short loc_180008C79
0x180008c6c  cmp     [rsi], dx
0x180008c6f  jz      short loc_180008C79
0x180008c71  mov     qword ptr [rbp+0B0h+var_130+8], rsi
0x180008c75  mov     [rbp+0B0h+var_120], r12
0x180008c79  movdqu  [rbp+0B0h+var_118], xmm0
0x180008c7e  xor     r12d, r12d
0x180008c81  mov     [rbp+0B0h+var_108], r12
0x180008c85  mov     [rbp+0B0h+var_90], 7
0x180008c8d  mov     [rbp+0B0h+var_98], r12
0x180008c91  mov     word ptr [rbp+0B0h+var_A8], r12w
0x180008c96  lea     rdx, [rbp+0B0h+var_A8]
0x180008c9a  mov     rcx, r15
0x180008c9d  call    ?GetTransportName@SubscriptionReadData@@QEBAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; SubscriptionReadData::GetTransportName(std::wstring &)
0x180008ca2  mov     rcx, [rbp+0B0h+var_98]
0x180008ca6  test    rcx, rcx
0x180008ca9  jz      loc_180008D5C
0x180008caf  mov     rdx, [rdi+58h]
0x180008cb3  add     rcx, 14h
0x180008cb7  add     rdx, rcx
0x180008cba  lea     rcx, [rbp+0B0h+var_118]
0x180008cbe  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x180008cc3  mov     [rsp+1B0h+var_170], r12d
0x180008cc8  lea     r8, [rsp+1B0h+var_170]; unsigned int *
0x180008ccd  lea     esi, [r12+0Ch]
0x180008cd2  mov     edx, esi; unsigned int
0x180008cd4  mov     rcx, [r15]; struct tag_EcRpcMetadataPropertyList *
0x180008cd7  call    ?ReadMetadataProp@@YA_NAEBUtag_EcRpcMetadataPropertyList@@KAEAK@Z; ReadMetadataProp(tag_EcRpcMetadataPropertyList const &,ulong,ulong &)
0x180008cdc  cmp     [rsp+1B0h+var_170], r12d
0x180008ce1  jnz     short loc_180008D13
0x180008ce3  cmp     qword ptr [rbx+18h], 8
0x180008ce8  jb      short loc_180008CED
0x180008cea  mov     rbx, [rbx]
0x180008ced  lea     r8, [rbp+0B0h+var_A8]
0x180008cf1  cmp     [rbp+0B0h+var_90], 8
0x180008cf6  cmovnb  r8, [rbp+0B0h+var_A8]
0x180008cfb  mov     r9, rbx
0x180008cfe  lea     rdx, aSS; "%s://%s"
0x180008d05  lea     rcx, [rbp+0B0h+var_118]
0x180008d09  call    ?StringPrintf@@YAJAEAV?$vector@GV?$allocator@G@std@@@std@@PEBGZZ; StringPrintf(std::vector<ushort> &,ushort const *,...)
0x180008d0e  jmp     loc_180008DC3
0x180008d13  mov     [rsp+1B0h+var_170], r12d
0x180008d18  lea     r8, [rsp+1B0h+var_170]; unsigned int *
0x180008d1d  mov     edx, esi; unsigned int
0x180008d1f  mov     rcx, [r15]; struct tag_EcRpcMetadataPropertyList *
  ... truncated ...
```
