# CollectorInitiatedSubscription::Activate(ushort const *,SubscriptionReadData const &)

- ea: `0x180009170`
- end: `0x1800099fb`
- name: `?Activate@CollectorInitiatedSubscription@@UEAAXPEBGAEBVSubscriptionReadData@@@Z`
- size: `2187`
- prototype: `void __fastcall(CollectorInitiatedSubscription *__hidden this, wchar_t *String1, const struct SubscriptionReadData *)`
- caller_count: `0`
- callee_count: `28`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000195c`
- `0x180002510`
- `0x1800032dc`
- `0x180003430`
- `0x180003810`
- `0x180003a50`
- `0x180003cc8`
- `0x180003d48`
- `0x18000526c`
- `0x1800062d4`
- `0x180006334`
- `0x18000669c`
- `0x180007844`
- `0x18000837c`
- `0x18000840c`
- `0x180008828`
- `0x180009170`
- `0x1800103b8`
- `0x180010f80`
- `0x1800113b4`
- `0x18001ddec`
- `0x18001de2c`
- `0x18001df44`
- `0x18001e10c`
- `0x18001e14c`
- `0x18001e734`
- `0x18001fe50`
- `0x180023010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x1800095f2`
- `msvcrt!_wcsicmp` at `0x1800095f2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800091c9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800091c9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800092b6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800092b6`

## string_xrefs

- `0x18000989e`: `admin\wmi\events\forwarding\collector\service\submgr.cpp`
- `0x180009996`: `admin\wmi\events\forwarding\collector\service\submgr.cpp`

## pseudocode

```c
void __fastcall CollectorInitiatedSubscription::Activate(
        CollectorInitiatedSubscription *this,
        wchar_t *String1,
        const struct SubscriptionReadData *a3)
{
  struct SubscriptionReadData *v3; // r12
  wchar_t *v4; // r13
  CollectorInitiatedSubscription *v5; // r15
  struct _RTL_CRITICAL_SECTION *v6; // rbx
  PVOID *v7; // rcx
  __int64 v8; // rdi
  __int64 v9; // rdx
  unsigned int v10; // edx
  __int64 v11; // r12
  _QWORD *v12; // r9
  _QWORD *v13; // r8
  _QWORD *v14; // r12
  __int64 v15; // rdx
  __int64 v16; // rdx
  unsigned __int64 i; // r12
  const wchar_t *v18; // rdx
  __int64 v19; // rax
  __int64 v20; // rcx
  const unsigned __int16 *v21; // r13
  const unsigned __int16 *v22; // rsi
  BoundSubscription *v23; // rax
  volatile signed __int32 *v24; // rdi
  __int64 v25; // rax
  _QWORD *v26; // rsi
  __int64 v27; // rdx
  __int64 v28; // rdx
  CollectorInitiatedSubscription *v29; // rdi
  const unsigned __int16 *v30; // r9
  const unsigned __int16 *v31; // rcx
  unsigned int v32; // ebx
  const unsigned __int16 *v33; // rcx
  __int64 v34; // rdx
  wmi::Exception *v35; // rbx
  _QWORD *v36; // rdx
  const unsigned __int16 *v37; // rdi
  unsigned int v38; // eax
  const unsigned __int16 *v39; // rcx
  int v40; // [rsp+30h] [rbp-288h]
  unsigned int v41; // [rsp+34h] [rbp-284h]
  unsigned __int64 v42; // [rsp+38h] [rbp-280h] BYREF
  struct SubscriptionReadData *v43; // [rsp+40h] [rbp-278h]
  CollectorInitiatedSubscription *v44; // [rsp+48h] [rbp-270h]
  unsigned __int16 *v45; // [rsp+50h] [rbp-268h]
  volatile signed __int32 *v46; // [rsp+58h] [rbp-260h]
  const unsigned __int16 *v47; // [rsp+60h] [rbp-258h]
  wchar_t *v48; // [rsp+68h] [rbp-250h]
  CollectorInitiatedSubscription *v49; // [rsp+70h] [rbp-248h]
  wchar_t *v50; // [rsp+78h] [rbp-240h]
  void *v51; // [rsp+80h] [rbp-238h] BYREF
  _BYTE *v52; // [rsp+88h] [rbp-230h] BYREF
  struct _RTL_CRITICAL_SECTION *v53; // [rsp+90h] [rbp-228h]
  struct SubscriptionReadData *v54; // [rsp+98h] [rbp-220h]
  __int128 v55; // [rsp+A0h] [rbp-218h] BYREF
  __int64 v56; // [rsp+B0h] [rbp-208h]
  void **pExceptionObject; // [rsp+B8h] [rbp-200h] BYREF
  char v58; // [rsp+C0h] [rbp-1F8h]
  const char *v59; // [rsp+C8h] [rbp-1F0h]
  __int64 v60; // [rsp+D0h] [rbp-1E8h]
  __int64 v61; // [rsp+D8h] [rbp-1E0h]
  unsigned int v62; // [rsp+E0h] [rbp-1D8h]
  int v63; // [rsp+E4h] [rbp-1D4h]
  int v64; // [rsp+E8h] [rbp-1D0h]
  void **v65; // [rsp+F0h] [rbp-1C8h] BYREF
  char v66; // [rsp+F8h] [rbp-1C0h]
  const char *v67; // [rsp+100h] [rbp-1B8h]
  __int64 v68; // [rsp+108h] [rbp-1B0h]
  __int64 v69; // [rsp+110h] [rbp-1A8h]
  int v70; // [rsp+118h] [rbp-1A0h]
  int v71; // [rsp+11Ch] [rbp-19Ch]
  int v72; // [rsp+120h] [rbp-198h]
  _BYTE v73[24]; // [rsp+130h] [rbp-188h] BYREF
  char v74[24]; // [rsp+148h] [rbp-170h] BYREF
  unsigned __int64 v75; // [rsp+160h] [rbp-158h]
  __int64 v76; // [rsp+168h] [rbp-150h]
  __int64 v77; // [rsp+170h] [rbp-148h]
  __int64 v78; // [rsp+180h] [rbp-138h]
  __int64 v79; // [rsp+188h] [rbp-130h]
  _QWORD v80[3]; // [rsp+198h] [rbp-120h] BYREF
  wmi::Exception *v81; // [rsp+1B0h] [rbp-108h] BYREF
  char v82[16]; // [rsp+1C0h] [rbp-F8h] BYREF
  _QWORD v83[2]; // [rsp+1D0h] [rbp-E8h] BYREF
  _QWORD *v84; // [rsp+1E0h] [rbp-D8h]
  unsigned __int64 v85; // [rsp+1E8h] [rbp-D0h]
  _QWORD v86[2]; // [rsp+1F0h] [rbp-C8h] BYREF
  __int128 *v87; // [rsp+200h] [rbp-B8h]
  unsigned __int64 v88; // [rsp+208h] [rbp-B0h]
  _QWORD v89[3]; // [rsp+210h] [rbp-A8h] BYREF
  unsigned __int64 v90; // [rsp+228h] [rbp-90h]
  unsigned __int16 *v91[3]; // [rsp+230h] [rbp-88h] BYREF
  unsigned __int64 v92; // [rsp+248h] [rbp-70h]
  _BYTE v93[32]; // [rsp+250h] [rbp-68h] BYREF

  v3 = a3;
  v43 = a3;
  v4 = String1;
  v48 = String1;
  v5 = this;
  v44 = this;
  v50 = String1;
  v54 = a3;
  v6 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 16);
  v53 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 16);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  v7 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 64);
    v7 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v4 && *v4 )
  {
    std::wstring::wstring(v89, v4);
    v8 = *(_QWORD *)std::_Tree<std::_Tmap_traits<std::wstring,wmi::AutoRef<BoundSubscription>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,wmi::AutoRef<BoundSubscription>>>,0>>::find(
                      (char *)v5 + 208,
                      &v52,
                      v89);
    LOBYTE(v9) = 1;
    std::wstring::_Tidy(v89, v9, 0);
    if ( v8 != *((_QWORD *)v5 + 26) )
    {
      v7 = (PVOID *)WPP_GLOBAL_Control;
LABEL_9:
      if ( v7 != &WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 0x10) != 0 && *((_BYTE *)v7 + 25) >= 4u )
        WPP_SF_S(v7[2], 65);
      goto LABEL_13;
    }
  }
  else if ( *((_QWORD *)v5 + 27) )
  {
    goto LABEL_9;
  }
  v49 = v5;
  v41 = 0;
  std::wstring::wstring(v91, &word_180026AD8);
  v40 = 0;
  v52 = (char *)v5 + 96;
  *((_BYTE *)v5 + 96) = 0;
  *((_QWORD *)v5 + 11) = 0;
  ReadMetadataProp(*(const struct tag_EcRpcMetadataPropertyList **)v3, v10, (struct _FILETIME *)v5 + 11);
  if ( !*((_QWORD *)v5 + 14) || !v4 || !*v4 )
  {
    v88 = 7;
    v87 = 0;
    LOWORD(v86[0]) = 0;
    v85 = 7;
    v84 = 0;
    LOWORD(v83[0]) = 0;
    SubscriptionReadData::GetLogFile(v3, v83);
    SubscriptionReadData::GetPublisherName(v3, v86);
    if ( !v87 && !v84 )
      std::wstring::assign(v83, L"ForwardedEvents");
    v11 = *(_QWORD *)(*((_QWORD *)v5 + 13) + 128LL);
    wmi::AutoRef<AbstractEventProcessor>::operator=((char *)v5 + 112);
    if ( v87 )
    {
      v12 = v86;
      if ( v88 >= 8 )
        v12 = (_QWORD *)v86[0];
    }
    else
    {
      v12 = 0;
    }
    if ( v84 )
    {
      v13 = v83;
      if ( v85 >= 8 )
        v13 = (_QWORD *)v83[0];
    }
    else
    {
      v13 = 0;
    }
    v14 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, unsigned __int64 *, _QWORD *, _QWORD *))(*(_QWORD *)v11 + 8LL))(
                      v11,
                      &v42,
                      v13,
                      v12);
    wmi::AutoRef<AbstractEventProcessor>::Release((char *)v5 + 112);
    *((_QWORD *)v5 + 14) = *v14;
    *v14 = 0;
    wmi::AutoRef<AbstractEventProcessor>::Release(&v42);
    LOBYTE(v15) = 1;
    std::wstring::_Tidy(v83, v15, 0);
    LOBYTE(v16) = 1;
    std::wstring::_Tidy(v86, v16, 0);
    v3 = v43;
  }
  _EventSources::_EventSources((_EventSources *)v73);
  SubscriptionReadData::GetEventSources(v3, (struct _EventSources *)v73);
  LOBYTE(v83[0]) = 0;
  v83[1] = ZeroStringVector;
  v84 = v80;
  v90 = 7;
  v89[2] = 0;
  LOWORD(v89[0]) = 0;
  v55 = 0;
  v56 = 0;
  SubscriptionReadData::GetCommonUserName(v3, v89);
  SubscriptionReadData::GetCommonPassword(v3, &v55);
  LOBYTE(v86[0]) = 0;
  v86[1] = ZeroPasswordString;
  v87 = &v55;
  if ( v75 != (v77 - v76) >> 5
    || v75 != (v79 - v78) >> 5
    || v75 != 0xAAAAAAAAAAAAAAABuLL * ((__int64)(v80[1] - v80[0]) >> 3) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 66, &WPP_311dc52e399f3c6238c54a9ac88e2061_Traceguids, 13);
    }
    v66 = 0;
    v67 = "admin\\wmi\\events\\forwarding\\collector\\service\\submgr.cpp";
    v68 = 0;
    v69 = 0;
    v70 = 13;
    v71 = -1;
    v72 = 2473;
    v65 = &wmi::GenericException::`vftable';
    throw (wmi::GenericException *)&v65;
  }
  for ( i = 0; ; ++i )
  {
    v42 = i;
    if ( i >= v75 )
      break;
    if ( !v4 || !*v4 )
      goto LABEL_40;
    v18 = (const wchar_t *)(v76 + 32 * i);
    if ( *((_QWORD *)v18 + 3) >= 8u )
      v18 = *(const wchar_t **)v18;
    if ( !_wcsicmp(v4, v18) )
    {
LABEL_40:
      v19 = std::vector<bool>::operator[](v74, v82, i);
      if ( ((1 << *(_QWORD *)(v19 + 8)) & **(_DWORD **)v19) != 0 )
      {
        v20 = 32 * i;
        v21 = (const unsigned __int16 *)(32 * i + v76);
        if ( *((_QWORD *)v21 + 3) >= 8u )
          v21 = *(const unsigned __int16 **)v21;
        v47 = v21;
        v22 = (const unsigned __int16 *)(v20 + v78);
        if ( *(_QWORD *)(v20 + v78 + 24) >= 8u )
          v22 = *(const unsigned __int16 **)v22;
        if ( v22 && *v22 )
        {
          v45 = *(unsigned __int16 **)(v80[0] + 24 * i);
        }
        else
        {
          v22 = (const unsigned __int16 *)v89;
          if ( v90 >= 8 )
            v22 = (const unsigned __int16 *)v89[0];
          v45 = (unsigned __int16 *)v55;
        }
        v23 = (BoundSubscription *)operator new(0x218u);
        v51 = v23;
        if ( v23 )
          v24 = (volatile signed __int32 *)BoundSubscription::BoundSubscription(v23, v5, v21);
        else
          v24 = 0;
        v46 = v24;
        v51 = (void *)v24;
        if ( v24 )
          _InterlockedIncrement(v24 + 2);
        if ( __eh34_try(0, 1) )
        {
          __eh34_scope_strut(1);
          BoundSubscription::Activate((BoundSubscription *)v24, v43, v22, v45);
          std::wstring::wstring(v93, v21);
          v25 = std::map<std::wstring,wmi::AutoRef<BoundSubscription>>::operator[]((char *)v5 + 208, v93);
          v26 = (_QWORD *)v25;
          if ( v24 )
            _InterlockedIncrement(v24 + 2);
          wmi::AutoRef<AbstractEventProcessor>::Release(v25);
          *v26 = v24;
          LOBYTE(v27) = 1;
          std::wstring::_Tidy(v93, v27, 0);
          v4 = v48;
        }
        if ( __eh34_catch(1) )
        {
          if ( __eh34_catch_type(1, &wmi::Exception `RTTI Type Descriptor', &v81) )
          {
            v35 = v81;
            v41 = (**(__int64 (__fastcall ***)(wmi::Exception *))v81)(v81);
            if ( v41 == *((_DWORD *)v46 + 45) )
            {
              v36 = v46 + 46;
              if ( *((_QWORD *)v46 + 26) >= 8u )
                v36 = (_QWORD *)*v36;
              std::wstring::assign(v91, v36);
            }
            v37 = (const unsigned __int16 *)v91;
            if ( v92 >= 8 )
              v37 = v91[0];
            v38 = (**(__int64 (__fastcall ***)(wmi::Exception *))v35)(v35);
            v39 = (const unsigned __int16 *)((char *)v44 + 56);
            if ( *((_QWORD *)v44 + 10) >= 8u )
              v39 = *(const unsigned __int16 **)v39;
            WriteSavedRunTimeStatus(v39, v47, v38, v37, 0, 1);
            v40 = 1;
            v6 = v53;
            i = v42;
            v5 = v44;
            v4 = v50;
            v48 = v50;
            v43 = v54;
            __eh34_try_continuation(1, &wmi::Exception `RTTI Type Descriptor', &loc_18000975C);
          }
        }
        wmi::AutoRef<AbstractEventProcessor>::Release(&v51);
      }
    }
  }
  wmi::ScopeGuardImpl1<void (*)(std::vector<std::vector<unsigned short>> *),std::vector<std::vector<unsigned short>> *>::~ScopeGuardImpl1<void (*)(std::vector<std::vector<unsigned short>> *),std::vector<std::vector<unsigned short>> *>(v86);
  std::vector<_WSMAN_OPTION>::~vector<_WSMAN_OPTION>(&v55);
  LOBYTE(v28) = 1;
  std::wstring::_Tidy(v89, v28, 0);
  wmi::ScopeGuardImpl1<void (*)(std::vector<std::vector<unsigned short>> *),std::vector<std::vector<unsigned short>> *>::~ScopeGuardImpl1<void (*)(std::vector<std::vector<unsigned short>> *),std::vector<std::vector<unsigned short>> *>(v83);
  _EventSources::~_EventSources((_EventSources *)v73);
  v29 = v49;
  if ( v40 && !*((_QWORD *)v49 + 27) )
  {
    v30 = (const unsigned __int16 *)v91;
    if ( v92 >= 8 )
      v30 = v91[0];
    v31 = (const unsigned __int16 *)((char *)v5 + 56);
    if ( *((_QWORD *)v5 + 10) >= 8u )
      v31 = *(const unsigned __int16 **)v31;
    v32 = v41;
    WriteSavedRunTimeStatus(v31, 0, v41, v30, 0, 1);
    if ( !v41 )
      v32 = 1287;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 67, &WPP_311dc52e399f3c6238c54a9ac88e2061_Traceguids, v32);
    }
    v58 = 0;
    v59 = "admin\\wmi\\events\\forwarding\\collector\\service\\submgr.cpp";
    v60 = 0;
    v61 = 0;
    v62 = v32;
    v63 = -1;
    v64 = 2546;
    pExceptionObject = &wmi::GenericException::`vftable';
    throw (wmi::GenericException *)&pExceptionObject;
  }
  v33 = (const unsigned __int16 *)((char *)v5 + 56);
  if ( *((_QWORD *)v5 + 10) >= 8u )
    v33 = *(const unsigned __int16 **)v33;
  WriteSavedRunTimeStatus(v33, 0, 0, &word_180026AD8, 0, 1);
  if ( *((_QWORD *)v29 + 27) )
    *v52 = 1;
  LOBYTE(v34) = 1;
  std::wstring::_Tidy(v91, v34, 0);
LABEL_13:
  LeaveCriticalSection(v6);
}

```

## disassembly

```asm
0x180009170  push    rbx
0x180009172  push    rsi
0x180009173  push    rdi
0x180009174  push    r12
0x180009176  push    r13
0x180009178  push    r14
0x18000917a  push    r15
0x18000917c  sub     rsp, 280h
0x180009183  mov     rax, cs:__security_cookie
0x18000918a  xor     rax, rsp
0x18000918d  mov     [rsp+2B8h+var_48], rax
0x180009195  mov     r12, r8
0x180009198  mov     [rsp+2B8h+var_278], r8
0x18000919d  mov     r13, rdx
0x1800091a0  mov     [rsp+2B8h+var_250], rdx
0x1800091a5  mov     r15, rcx
0x1800091a8  mov     [rsp+2B8h+var_270], rcx
0x1800091ad  mov     [rsp+2B8h+var_240], rdx
0x1800091b2  mov     [rsp+2B8h+var_220], r8
0x1800091ba  lea     rbx, [rcx+10h]
0x1800091be  mov     [rsp+2B8h+var_228], rbx
0x1800091c6  mov     rcx, rbx; lpCriticalSection
0x1800091c9  call    cs:__imp_EnterCriticalSection
0x1800091cf  nop
0x1800091d0  lea     rax, WPP_GLOBAL_Control
0x1800091d7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800091de  cmp     rcx, rax
0x1800091e1  jz      short loc_180009212
0x1800091e3  test    byte ptr [rcx+1Ch], 10h
0x1800091e7  jz      short loc_180009212
0x1800091e9  cmp     byte ptr [rcx+19h], 4
0x1800091ed  jb      short loc_180009212
0x1800091ef  lea     r9, [r15+38h]
0x1800091f3  cmp     qword ptr [r9+18h], 8
0x1800091f8  jb      short loc_1800091FD
0x1800091fa  mov     r9, [r9]
0x1800091fd  mov     edx, 40h ; '@'
0x180009202  mov     rcx, [rcx+10h]
0x180009206  call    WPP_SF_S
0x18000920b  mov     rcx, cs:WPP_GLOBAL_Control
0x180009212  xor     r14d, r14d
0x180009215  test    r13, r13
0x180009218  jz      loc_1800092DF
0x18000921e  cmp     [r13+0], r14w
0x180009223  jz      loc_1800092DF
0x180009229  mov     rdx, r13
0x18000922c  lea     rcx, [rsp+2B8h+var_A8]
0x180009234  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x180009239  lea     rsi, [r15+0D0h]
0x180009240  lea     r8, [rsp+2B8h+var_A8]
0x180009248  lea     rdx, [rsp+2B8h+var_230]
0x180009250  mov     rcx, rsi
0x180009253  call    ?find@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$AutoRef@VBoundSubscription@@@wmi@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$AutoRef@VBoundSubscription@@@wmi@@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$AutoRef@VBoundSubscription@@@wmi@@@std@@@std@@@std@@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Tree<std::_Tmap_traits<std::wstring,wmi::AutoRef<BoundSubscription>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,wmi::AutoRef<BoundSubscription>>>,0>>::find(std::wstring const &)
0x180009258  mov     rdi, [rax]
0x18000925b  xor     r8d, r8d
0x18000925e  mov     dl, 1
0x180009260  lea     rcx, [rsp+2B8h+var_A8]
0x180009268  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18000926d  cmp     rdi, [rsi]
0x180009270  setnz   al
0x180009273  test    al, al
0x180009275  jz      short loc_1800092E8
0x180009277  mov     rcx, cs:WPP_GLOBAL_Control
0x18000927e  lea     rax, WPP_GLOBAL_Control
0x180009285  cmp     rcx, rax
0x180009288  jz      short loc_1800092B3
0x18000928a  test    byte ptr [rcx+1Ch], 10h
0x18000928e  jz      short loc_1800092B3
0x180009290  cmp     byte ptr [rcx+19h], 4
0x180009294  jb      short loc_1800092B3
0x180009296  lea     r9, [r15+38h]
0x18000929a  cmp     qword ptr [r9+18h], 8
0x18000929f  jb      short loc_1800092A4
0x1800092a1  mov     r9, [r9]
0x1800092a4  mov     edx, 41h ; 'A'
0x1800092a9  mov     rcx, [rcx+10h]
0x1800092ad  call    WPP_SF_S
0x1800092b2  nop
0x1800092b3  mov     rcx, rbx; lpCriticalSection
0x1800092b6  call    cs:__imp_LeaveCriticalSection
0x1800092bc  mov     rcx, [rsp+2B8h+var_48]
0x1800092c4  xor     rcx, rsp; StackCookie
0x1800092c7  call    __security_check_cookie
0x1800092cc  add     rsp, 280h
0x1800092d3  pop     r15
0x1800092d5  pop     r14
0x1800092d7  pop     r13
0x1800092d9  pop     r12
0x1800092db  pop     rdi
0x1800092dc  pop     rsi
0x1800092dd  pop     rbx
0x1800092de  retn
0x1800092df  cmp     [r15+0D8h], r14
0x1800092e6  jnz     short loc_18000927E
0x1800092e8  mov     [rsp+2B8h+var_248], r15
0x1800092ed  mov     [rsp+2B8h+var_284], r14d
0x1800092f2  lea     rdx, word_180026AD8
0x1800092f9  lea     rcx, [rsp+2B8h+var_88]
0x180009301  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x180009306  nop
0x180009307  mov     [rsp+2B8h+var_288], r14d
0x18000930c  lea     rax, [r15+60h]
0x180009310  mov     [rsp+2B8h+var_230], rax
0x180009318  mov     [rax], r14b
0x18000931b  lea     r8, [r15+58h]; struct _FILETIME *
0x18000931f  mov     [r8], r14
0x180009322  mov     rcx, [r12]; struct tag_EcRpcMetadataPropertyList *
0x180009326  call    ?ReadMetadataProp@@YA_NAEBUtag_EcRpcMetadataPropertyList@@KAEAU_FILETIME@@@Z; ReadMetadataProp(tag_EcRpcMetadataPropertyList const &,ulong,_FILETIME &)
0x18000932b  lea     rsi, [r15+70h]
0x18000932f  cmp     [rsi], r14
0x180009332  jz      short loc_18000934A
0x180009334  test    r13, r13
0x180009337  jz      short loc_18000934A
0x180009339  cmp     [r13+0], r14w
0x18000933e  jz      short loc_18000934A
0x180009340  mov     edi, 7
0x180009345  jmp     loc_18000948E
0x18000934a  mov     edi, 7
0x18000934f  mov     [rsp+2B8h+var_B0], rdi
0x180009357  mov     [rsp+2B8h+var_B8], r14
0x18000935f  mov     word ptr [rsp+2B8h+var_C8], r14w
0x180009368  mov     [rsp+2B8h+var_D0], rdi
0x180009370  mov     [rsp+2B8h+var_D8], r14
0x180009378  mov     word ptr [rsp+2B8h+var_E8], r14w
0x180009381  lea     rdx, [rsp+2B8h+var_E8]
0x180009389  mov     rcx, r12
0x18000938c  call    ?GetLogFile@SubscriptionReadData@@QEBAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; SubscriptionReadData::GetLogFile(std::wstring &)
0x180009391  lea     rdx, [rsp+2B8h+var_C8]
0x180009399  mov     rcx, r12
0x18000939c  call    ?GetPublisherName@SubscriptionReadData@@QEBAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; SubscriptionReadData::GetPublisherName(std::wstring &)
0x1800093a1  cmp     [rsp+2B8h+var_B8], r14
0x1800093a9  jnz     short loc_1800093C9
0x1800093ab  cmp     [rsp+2B8h+var_D8], r14
0x1800093b3  jnz     short loc_1800093C9
0x1800093b5  lea     rdx, aForwardedevent; "ForwardedEvents"
0x1800093bc  lea     rcx, [rsp+2B8h+var_E8]
0x1800093c4  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::assign(ushort const *)
0x1800093c9  mov     rax, [r15+68h]
0x1800093cd  mov     r12, [rax+80h]
0x1800093d4  mov     rcx, rsi
0x1800093d7  call    ??4?$AutoRef@VAbstractEventProcessor@@@wmi@@QEAAAEAV01@PEAVAbstractEventProcessor@@@Z; wmi::AutoRef<AbstractEventProcessor>::operator=(AbstractEventProcessor *)
0x1800093dc  mov     rax, [r12]
0x1800093e0  cmp     [rsp+2B8h+var_B8], r14
0x1800093e8  jnz     short loc_1800093EF
0x1800093ea  mov     r9, r14
0x1800093ed  jmp     short loc_180009409
0x1800093ef  lea     r9, [rsp+2B8h+var_C8]
0x1800093f7  cmp     [rsp+2B8h+var_B0], 8
0x180009400  cmovnb  r9, [rsp+2B8h+var_C8]
0x180009409  cmp     [rsp+2B8h+var_D8], r14
0x180009411  jnz     short loc_180009418
0x180009413  mov     r8, r14
0x180009416  jmp     short loc_180009432
0x180009418  lea     r8, [rsp+2B8h+var_E8]
0x180009420  cmp     [rsp+2B8h+var_D0], 8
0x180009429  cmovnb  r8, [rsp+2B8h+var_E8]
0x180009432  lea     rdx, [rsp+2B8h+var_280]
0x180009437  mov     rcx, r12
0x18000943a  mov     rax, [rax+8]
0x18000943e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009443  mov     r12, rax
0x180009446  mov     rcx, rsi
0x180009449  call    ?Release@?$AutoRef@VAbstractEventProcessor@@@wmi@@QEAAXXZ; wmi::AutoRef<AbstractEventProcessor>::Release(void)
0x18000944e  mov     rcx, [r12]
0x180009452  mov     [rsi], rcx
0x180009455  mov     [r12], r14
0x180009459  lea     rcx, [rsp+2B8h+var_280]
0x18000945e  call    ?Release@?$AutoRef@VAbstractEventProcessor@@@wmi@@QEAAXXZ; wmi::AutoRef<AbstractEventProcessor>::Release(void)
0x180009463  nop
0x180009464  xor     r8d, r8d
0x180009467  mov     dl, 1
0x180009469  lea     rcx, [rsp+2B8h+var_E8]
0x180009471  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180009476  nop
0x180009477  xor     r8d, r8d
0x18000947a  mov     dl, 1
0x18000947c  lea     rcx, [rsp+2B8h+var_C8]
0x180009484  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180009489  mov     r12, [rsp+2B8h+var_278]
0x18000948e  lea     rcx, [rsp+2B8h+var_188]; this
0x180009496  call    ??0_EventSources@@QEAA@XZ; _EventSources::_EventSources(void)
0x18000949b  nop
0x18000949c  lea     rdx, [rsp+2B8h+var_188]; struct _EventSources *
0x1800094a4  mov     rcx, r12; this
0x1800094a7  call    ?GetEventSources@SubscriptionReadData@@QEBAXAEAU_EventSources@@@Z; SubscriptionReadData::GetEventSources(_EventSources &)
0x1800094ac  mov     byte ptr [rsp+2B8h+var_E8], r14b
0x1800094b4  lea     rax, ?ZeroStringVector@@YAXPEAV?$vector@V?$vector@GV?$allocator@G@std@@@std@@V?$allocator@V?$vector@GV?$allocator@G@std@@@std@@@2@@std@@@Z; ZeroStringVector(std::vector<std::vector<ushort>> *)
0x1800094bb  mov     [rsp+2B8h+var_E0], rax
0x1800094c3  lea     rax, [rsp+2B8h+var_120]
0x1800094cb  mov     [rsp+2B8h+var_D8], rax
0x1800094d3  mov     [rsp+2B8h+var_90], rdi
0x1800094db  mov     [rsp+2B8h+var_98], r14
0x1800094e3  mov     word ptr [rsp+2B8h+var_A8], r14w
0x1800094ec  xorps   xmm0, xmm0
0x1800094ef  movdqu  [rsp+2B8h+var_218], xmm0
0x1800094f8  mov     [rsp+2B8h+var_208], r14
0x180009500  lea     rdx, [rsp+2B8h+var_A8]
0x180009508  mov     rcx, r12
0x18000950b  call    ?GetCommonUserName@SubscriptionReadData@@QEBAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; SubscriptionReadData::GetCommonUserName(std::wstring &)
0x180009510  lea     rdx, [rsp+2B8h+var_218]
0x180009518  mov     rcx, r12
0x18000951b  call    ?GetCommonPassword@SubscriptionReadData@@QEBAXAEAV?$vector@GV?$allocator@G@std@@@std@@@Z; SubscriptionReadData::GetCommonPassword(std::vector<ushort> &)
0x180009520  mov     byte ptr [rsp+2B8h+var_C8], r14b
0x180009528  lea     rax, ?ZeroPasswordString@@YAXPEAV?$vector@GV?$allocator@G@std@@@std@@@Z; ZeroPasswordString(std::vector<ushort> *)
0x18000952f  mov     [rsp+2B8h+var_C0], rax
0x180009537  lea     rax, [rsp+2B8h+var_218]
0x18000953f  mov     [rsp+2B8h+var_B8], rax
0x180009547  mov     rcx, [rsp+2B8h+var_158]
0x18000954f  mov     rax, [rsp+2B8h+var_148]
0x180009557  sub     rax, [rsp+2B8h+var_150]
0x18000955f  sar     rax, 5
0x180009563  cmp     rcx, rax
0x180009566  jnz     loc_180009956
0x18000956c  mov     rax, [rsp+2B8h+var_130]
0x180009574  sub     rax, [rsp+2B8h+var_138]
0x18000957c  sar     rax, 5
0x180009580  cmp     rcx, rax
0x180009583  jnz     loc_180009956
0x180009589  mov     rax, [rsp+2B8h+var_118]
0x180009591  sub     rax, [rsp+2B8h+var_120]
0x180009599  sar     rax, 3
0x18000959d  mov     rdx, 0AAAAAAAAAAAAAAABh
0x1800095a7  imul    rax, rdx
0x1800095ab  cmp     rcx, rax
0x1800095ae  jnz     loc_180009956
0x1800095b4  mov     r12, r14
0x1800095b7  mov     [rsp+2B8h+var_280], r12
0x1800095bc  cmp     r12, [rsp+2B8h+var_158]
0x1800095c4  jnb     loc_1800097AD
0x1800095ca  test    r13, r13
0x1800095cd  jz      short loc_180009600
0x1800095cf  cmp     [r13+0], r14w
0x1800095d4  jz      short loc_180009600
0x1800095d6  mov     rdx, r12
0x1800095d9  shl     rdx, 5
0x1800095dd  add     rdx, [rsp+2B8h+var_150]
0x1800095e5  cmp     qword ptr [rdx+18h], 8
0x1800095ea  jb      short loc_1800095EF
0x1800095ec  mov     rdx, [rdx]; String2
0x1800095ef  mov     rcx, r13; String1
0x1800095f2  call    cs:__imp__wcsicmp
0x1800095f8  test    eax, eax
0x1800095fa  jnz     loc_1800097A5
0x180009600  mov     r8, r12
0x180009603  lea     rdx, [rsp+2B8h+var_F8]
0x18000960b  lea     rcx, [rsp+2B8h+var_170]
0x180009613  call    ??A?$vector@_NV?$allocator@_N@std@@@std@@QEAA?AV?$_Vb_reference@U?$_Wrap_alloc@V?$allocator@I@std@@@std@@@1@_K@Z; std::vector<bool>::operator[](unsigned __int64)
0x180009618  mov     rcx, [rax+8]
0x18000961c  mov     edx, 1
0x180009621  shl     edx, cl
0x180009623  mov     rax, [rax]
0x180009626  test    [rax], edx
0x180009628  jz      loc_1800097A5
0x18000962e  mov     rcx, r12
0x180009631  shl     rcx, 5
0x180009635  mov     r13, [rsp+2B8h+var_150]
0x18000963d  add     r13, rcx
0x180009640  cmp     qword ptr [r13+18h], 8
0x180009645  jb      short loc_18000964B
0x180009647  mov     r13, [r13+0]
0x18000964b  mov     [rsp+2B8h+var_258], r13
0x180009650  mov     rsi, [rsp+2B8h+var_138]
0x180009658  add     rsi, rcx
0x18000965b  cmp     qword ptr [rsi+18h], 8
0x180009660  jb      short loc_180009665
0x180009662  mov     rsi, [rsi]
0x180009665  test    rsi, rsi
0x180009668  jz      short loc_180009687
0x18000966a  cmp     [rsi], r14w
0x18000966e  jz      short loc_180009687
0x180009670  lea     rcx, [r12+r12*2]
0x180009674  mov     rax, [rsp+2B8h+var_120]
0x18000967c  mov     rdi, [rax+rcx*8]
0x180009680  mov     [rsp+2B8h+var_268], rdi
0x180009685  jmp     short loc_1800096AE
0x180009687  lea     rsi, [rsp+2B8h+var_A8]
0x18000968f  cmp     [rsp+2B8h+var_90], 8
0x180009698  cmovnb  rsi, [rsp+2B8h+var_A8]
0x1800096a1  mov     rax, qword ptr [rsp+2B8h+var_218]
0x1800096a9  mov     [rsp+2B8h+var_268], rax
0x1800096ae  mov     ecx, 218h; dwBytes
0x1800096b3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800096b8  mov     [rsp+2B8h+var_238], rax
0x1800096c0  test    rax, rax
0x1800096c3  jz      short loc_1800096D8
0x1800096c5  mov     r8, r13; unsigned __int16 *
0x1800096c8  mov     rdx, r15; struct Subscription *
0x1800096cb  mov     rcx, rax; this
0x1800096ce  call    ??0BoundSubscription@@QEAA@AEAVSubscription@@PEBG@Z; BoundSubscription::BoundSubscription(Subscription &,ushort const *)
0x1800096d3  mov     rdi, rax
0x1800096d6  jmp     short loc_1800096DB
0x1800096d8  mov     rdi, r14
0x1800096db  mov     [rsp+2B8h+var_260], rdi
0x1800096e0  mov     [rsp+2B8h+var_238], rdi
0x1800096e8  test    rdi, rdi
0x1800096eb  jz      short loc_1800096F1
0x1800096ed  lock inc dword ptr [rdi+8]
0x1800096f1  mov     r9, [rsp+2B8h+var_268]; unsigned __int16 *
0x1800096f6  mov     r8, rsi; unsigned __int16 *
0x1800096f9  mov     rdx, [rsp+2B8h+var_278]; struct SubscriptionReadData *
  ... truncated ...
```
