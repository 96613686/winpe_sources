# EvtSubscribe

- ea: `0x18000d050`
- end: `0x18000d64a`
- name: `EvtSubscribe`
- size: `1530`
- prototype: `EVT_HANDLE __stdcall(EVT_HANDLE Session, HANDLE SignalEvent, LPCWSTR ChannelPath, LPCWSTR Query, EVT_HANDLE Bookmark, PVOID Context, EVT_SUBSCRIBE_CALLBACK Callback, DWORD Flags)`
- caller_count: `0`
- callee_count: `16`
- tags: `file_ops, loader_planting`

## callees

- `0x180006870`
- `0x180006aec`
- `0x180007010`
- `0x180007940`
- `0x18000a100`
- `0x18000c404`
- `0x18000d050`
- `0x18000dac0`
- `0x18000e248`
- `0x18000e778`
- `0x18000ec98`
- `0x18000ff68`
- `0x180021140`
- `0x1800216c4`
- `0x180023548`
- `0x180038fa4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d20b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d20b`

## pseudocode

```c
EVT_HANDLE __stdcall EvtSubscribe(
        EVT_HANDLE Session,
        HANDLE SignalEvent,
        LPCWSTR ChannelPath,
        LPCWSTR Query,
        EVT_HANDLE Bookmark,
        PVOID Context,
        EVT_SUBSCRIBE_CALLBACK Callback,
        DWORD Flags)
{
  __int64 v11; // rsi
  DWORD v12; // edi
  EVT_SUBSCRIBE_CALLBACK v13; // r12
  const wchar_t *v14; // r15
  __int64 v15; // rcx
  __int64 v16; // r9
  int v17; // r8d
  int v18; // ecx
  __int64 v19; // rcx
  unsigned int v20; // edi
  DWORD v21; // r14d
  RemotePushSubscription *v22; // rcx
  void *v23; // rdi
  unsigned int ReferencedObjectAs; // r14d
  wmi::RefBase *v26; // rbx
  __int64 v27; // rcx
  unsigned int v28; // edi
  RemotePullSubscription *v29; // rcx
  wmi::RefBase *v30; // [rsp+30h] [rbp-138h] BYREF
  wmi::RefBase *v31; // [rsp+38h] [rbp-130h] BYREF
  __int64 v32; // [rsp+40h] [rbp-128h] BYREF
  void *v33; // [rsp+48h] [rbp-120h]
  void *v34; // [rsp+50h] [rbp-118h] BYREF
  void *v35; // [rsp+58h] [rbp-110h]
  char v36; // [rsp+60h] [rbp-108h] BYREF
  _QWORD v37[3]; // [rsp+70h] [rbp-F8h] BYREF
  unsigned int v38; // [rsp+88h] [rbp-E0h]
  __int64 v39; // [rsp+8Ch] [rbp-DCh]
  char v40; // [rsp+94h] [rbp-D4h]
  _QWORD v41[3]; // [rsp+98h] [rbp-D0h] BYREF
  unsigned int v42; // [rsp+B0h] [rbp-B8h]
  __int64 v43; // [rsp+B4h] [rbp-B4h]
  char v44; // [rsp+BCh] [rbp-ACh]
  __int128 v45; // [rsp+C0h] [rbp-A8h] BYREF
  __int64 v46; // [rsp+D0h] [rbp-98h]
  unsigned int v47; // [rsp+D8h] [rbp-90h]
  int v48; // [rsp+DCh] [rbp-8Ch]
  int v49; // [rsp+E0h] [rbp-88h]
  __int128 pExceptionObject; // [rsp+E8h] [rbp-80h] BYREF
  __int64 v51; // [rsp+F8h] [rbp-70h]
  int v52; // [rsp+100h] [rbp-68h]
  int v53; // [rsp+104h] [rbp-64h]
  int v54; // [rsp+108h] [rbp-60h]
  __int128 v55; // [rsp+110h] [rbp-58h] BYREF
  __int64 v56; // [rsp+120h] [rbp-48h]
  int v57; // [rsp+128h] [rbp-40h]
  int v58; // [rsp+12Ch] [rbp-3Ch]
  int v59; // [rsp+130h] [rbp-38h]
  EvtException *v60; // [rsp+138h] [rbp-30h] BYREF
  HANDLE v61; // [rsp+178h] [rbp+10h] BYREF

  v61 = SignalEvent;
  v11 = 0;
  v32 = 0;
  v33 = 0;
  LastErrInfo::Reset((LastErrInfo *)Session);
  if ( __eh34_try(-1, 0) )
  {
    __eh34_scope_strut(0);
    v12 = Flags;
    if ( !Flags || (Flags & 0xFFFEEFFC) != 0 )
    {
      if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, WPP_6c6c805d13ef39f517b43cdeae326efa_Traceguids, 87);
      }
      v55 = 0;
      v56 = 0;
      v57 = 87;
      v58 = -1;
      v59 = 551;
      throw (EvtException *)&v55;
    }
    v13 = Callback;
    if ( Callback )
    {
      if ( SignalEvent )
        goto LABEL_41;
    }
    else if ( !SignalEvent )
    {
      goto LABEL_41;
    }
    if ( (Flags & 3) == 3 )
    {
      if ( Bookmark )
        goto LABEL_8;
    }
    else if ( !Bookmark )
    {
LABEL_8:
      v14 = L"*";
      if ( Query )
        v14 = Query;
      utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(&v34);
      if ( v17 == 3 )
      {
        v30 = 0;
        ReferencedObjectAs = ObjectTable::GetReferencedObjectAsType<BookmarkObject,void>(v15, v16, &v30);
        if ( ReferencedObjectAs )
        {
          if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_D(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              28,
              WPP_6c6c805d13ef39f517b43cdeae326efa_Traceguids,
              ReferencedObjectAs);
          }
          v45 = 0;
          v46 = 0;
          v47 = ReferencedObjectAs;
          v48 = -1;
          v49 = 580;
          throw (EvtException *)&v45;
        }
        v26 = v30;
        Bookmark::Render((char *)v30 + 64, &v34);
        if ( v26 )
          wmi::RefBase::Release(v26);
      }
      GetSession(&v31);
      if ( v13 )
      {
        v30 = 0;
        v19 = HandleTable::Emplace<RemotePushSubscription,wmi::AutoRef<Session> &,unsigned long (*&)(enum _EVT_SUBSCRIBE_NOTIFY_ACTION,void *,void *),void * &,unsigned long &>(
                v18,
                (int)&v30,
                (int)&v31,
                (int)&Callback,
                (__int64)&Context,
                (__int64)&Flags);
        if ( v19 )
        {
          *(_QWORD *)(v19 + 16) = v30;
          _InterlockedAdd((volatile signed __int32 *)(v19 + 8), 1u);
          _InterlockedAdd((volatile signed __int32 *)(v19 + 24), 1u);
          v11 = v19;
          v32 = v19;
          v30 = 0;
          EvtHandleRef::~EvtHandleRef((EvtHandleRef *)&v30);
          v20 = 0;
        }
        else
        {
          v20 = 14;
        }
        if ( (byte_18004B801 & 4) != 0 )
          McTemplateU0zz_EventWriteTransfer(v19, EVENT_PUSHSUB_CREATE, ChannelPath, v14);
        if ( v20 )
        {
          if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, WPP_6c6c805d13ef39f517b43cdeae326efa_Traceguids, v20);
          }
          v37[0] = &word_18004024A;
          v37[1] = 0;
          v37[2] = 0;
          v38 = v20;
          v39 = -1;
          v40 = 0;
          throw (EvtException *)v37;
        }
        v21 = 0;
        v22 = 0;
        if ( *(_BYTE *)(v11 + 28) == 2 )
          v22 = (RemotePushSubscription *)v11;
        RemotePushSubscription::Initialize(
          (Session **)v22,
          ChannelPath,
          v14,
          (const wchar_t *)((unsigned __int64)v34 & -(__int64)(v34 != v35)));
      }
      else
      {
        Flags = v12 | 0x10000000;
        v30 = 0;
        v27 = HandleTable::Emplace<RemotePullSubscription,wmi::AutoRef<Session> &,void * &,unsigned long>(
                v18,
                (int)&v30,
                (int)&v31,
                (int)&v61,
                (__int64)&Flags);
        if ( v27 )
        {
          *(_QWORD *)(v27 + 16) = v30;
          _InterlockedAdd((volatile signed __int32 *)(v27 + 8), 1u);
          _InterlockedAdd((volatile signed __int32 *)(v27 + 24), 1u);
          v11 = v27;
          v32 = v27;
          v30 = 0;
          EvtHandleRef::~EvtHandleRef((EvtHandleRef *)&v30);
          v28 = 0;
        }
        else
        {
          v28 = 14;
        }
        if ( (byte_18004B801 & 4) != 0 )
          McTemplateU0zz_EventWriteTransfer(v27, EVENT_PULLSUB_CREATE, ChannelPath, v14);
        if ( v28 )
        {
          if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, WPP_6c6c805d13ef39f517b43cdeae326efa_Traceguids, v28);
          }
          v41[0] = &word_18004024A;
          v41[1] = 0;
          v41[2] = 0;
          v42 = v28;
          v43 = -1;
          v44 = 0;
          throw (EvtException *)v41;
        }
        v21 = 0;
        v29 = 0;
        if ( *(_BYTE *)(v11 + 28) == 3 )
          v29 = (RemotePullSubscription *)v11;
        RemotePullSubscription::Initialize(
          v29,
          ChannelPath,
          v14,
          (const wchar_t *)((unsigned __int64)v34 & -(__int64)(v34 != v35)));
      }
      if ( v11 )
      {
        v23 = *(void **)(v11 + 16);
        v32 = 0;
        *(_BYTE *)(v11 + 29) = 1;
      }
      else
      {
        v23 = 0;
      }
      v33 = v23;
      if ( v31 )
        wmi::RefBase::Release(v31);
      v31 = 0;
      if ( v34 != &v36 )
        operator delete(v34);
      goto LABEL_71;
    }
LABEL_41:
    if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, WPP_6c6c805d13ef39f517b43cdeae326efa_Traceguids, 87);
    }
    pExceptionObject = 0;
    v51 = 0;
    v52 = 87;
    v53 = -1;
    v54 = 559;
    throw (EvtException *)&pExceptionObject;
  }
  if ( __eh34_catch(0) )
  {
    if ( __eh34_catch_type(0, &EvtException `RTTI Type Descriptor', &v60) )
    {
      Flags = *((_DWORD *)v60 + 6);
      v21 = Flags;
      v23 = v33;
      __eh34_try_continuation(0, &EvtException `RTTI Type Descriptor', &loc_18000D637);
    }
  }
LABEL_71:
  SetLastError(v21);
  EvtHandleRef::~EvtHandleRef((EvtHandleRef *)&v32);
  return v23;
}

```

## disassembly

```asm
0x18000d050  mov     rax, rsp
0x18000d053  mov     [rax+18h], rbx
0x18000d057  mov     [rax+20h], rsi
0x18000d05b  mov     [rax+10h], rdx
0x18000d05f  mov     [rax+8], rcx
0x18000d063  push    rdi
0x18000d064  push    r12
0x18000d066  push    r13
0x18000d068  push    r14
0x18000d06a  push    r15
0x18000d06c  sub     rsp, 140h
0x18000d073  mov     r14, r9
0x18000d076  mov     r13, r8
0x18000d079  mov     rbx, rdx
0x18000d07c  xor     r15d, r15d
0x18000d07f  mov     esi, r15d
0x18000d082  mov     [rsp+168h+var_128], r15
0x18000d087  mov     [rsp+168h+var_120], r15
0x18000d08c  call    ?Reset@LastErrInfo@@QEAAXXZ; LastErrInfo::Reset(void)
0x18000d091  mov     edi, [rsp+168h+Flags]
0x18000d098  test    edi, edi
0x18000d09a  jz      loc_18000D5B3
0x18000d0a0  test    edi, 0FFFEEFFCh
0x18000d0a6  jnz     loc_18000D5B3
0x18000d0ac  mov     r12, [rsp+168h+Callback]
0x18000d0b4  test    r12, r12
0x18000d0b7  jz      loc_18000D313
0x18000d0bd  test    rbx, rbx
0x18000d0c0  jnz     loc_18000D31C
0x18000d0c6  mov     r8d, edi
0x18000d0c9  and     r8d, 3
0x18000d0cd  mov     r9, [rsp+168h+Bookmark]
0x18000d0d5  cmp     r8d, 3
0x18000d0d9  jz      loc_18000D308
0x18000d0df  test    r9, r9
0x18000d0e2  jnz     loc_18000D31C
0x18000d0e8  lea     r15, asc_180040200; "*"
0x18000d0ef  test    r14, r14
0x18000d0f2  cmovnz  r15, r14
0x18000d0f6  lea     rcx, [rsp+168h+var_118]
0x18000d0fb  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x18000d100  nop
0x18000d101  cmp     r8d, 3
0x18000d105  jz      loc_18000D23C
0x18000d10b  mov     rdx, [rsp+168h+arg_0]
0x18000d113  lea     rcx, [rsp+168h+var_130]; void *
0x18000d118  call    ?GetSession@@YA?AV?$AutoRef@VSession@@@wmi@@PEAX@Z; GetSession(void *)
0x18000d11d  nop
0x18000d11e  lea     rax, [rsp+168h+Flags]
0x18000d126  lea     r8, [rsp+168h+var_130]
0x18000d12b  lea     rdx, [rsp+168h+var_138]
0x18000d130  test    r12, r12
0x18000d133  jz      loc_18000D287
0x18000d139  xor     r12d, r12d
0x18000d13c  mov     [rsp+168h+var_138], r12
0x18000d141  mov     [rsp+168h+var_140], rax
0x18000d146  lea     rax, [rsp+168h+Context]
0x18000d14e  mov     [rsp+168h+var_148], rax
0x18000d153  lea     r9, [rsp+168h+Callback]
0x18000d15b  call    ??$Emplace@VRemotePushSubscription@@AEAV?$AutoRef@VSession@@@wmi@@AEAP6AKW4_EVT_SUBSCRIBE_NOTIFY_ACTION@@PEAX1@ZAEAPEAXAEAK@HandleTable@@QEAAPEAVRemotePushSubscription@@AEAPEAXAEAV?$AutoRef@VSession@@@wmi@@AEAP6AKW4_EVT_SUBSCRIBE_NOTIFY_ACTION@@PEAX3@Z0AEAK@Z; HandleTable::Emplace<RemotePushSubscription,wmi::AutoRef<Session> &,ulong (*&)(_EVT_SUBSCRIBE_NOTIFY_ACTION,void *,void *),void * &,ulong &>(void * &,wmi::AutoRef<Session> &,ulong (*&)(_EVT_SUBSCRIBE_NOTIFY_ACTION,void *,void *),void * &,ulong &)
0x18000d160  mov     rcx, rax
0x18000d163  lea     ebx, [r12+1]
0x18000d168  test    rax, rax
0x18000d16b  jnz     loc_18000D401
0x18000d171  lea     edi, [rax+0Eh]
0x18000d174  test    cs:byte_18004B801, 4
0x18000d17b  jz      short loc_18000D18F
0x18000d17d  mov     r9, r15
0x18000d180  mov     r8, r13
0x18000d183  lea     rdx, EVENT_PUSHSUB_CREATE
0x18000d18a  call    McTemplateU0zz_EventWriteTransfer
0x18000d18f  test    edi, edi
0x18000d191  jnz     loc_18000D431
0x18000d197  mov     r14d, r12d
0x18000d19a  mov     rcx, r12
0x18000d19d  cmp     byte ptr [rsi+1Ch], 2
0x18000d1a1  cmovz   rcx, rsi; this
0x18000d1a5  mov     rax, [rsp+168h+var_110]
0x18000d1aa  sub     rax, [rsp+168h+var_118]
0x18000d1af  neg     rax
0x18000d1b2  sbb     r9, r9
0x18000d1b5  and     r9, [rsp+168h+var_118]; wchar_t *
0x18000d1ba  mov     r8, r15; wchar_t *
0x18000d1bd  mov     rdx, r13; wchar_t *
0x18000d1c0  call    ?Initialize@RemotePushSubscription@@QEAAXPEB_W00@Z; RemotePushSubscription::Initialize(wchar_t const *,wchar_t const *,wchar_t const *)
0x18000d1c5  test    rsi, rsi
0x18000d1c8  jz      loc_18000D577
0x18000d1ce  mov     rdi, [rsi+10h]
0x18000d1d2  mov     [rsp+168h+var_128], r12
0x18000d1d7  xchg    bl, [rsi+1Dh]
0x18000d1da  mov     [rsp+168h+var_120], rdi
0x18000d1df  mov     rcx, [rsp+168h+var_130]; this
0x18000d1e4  test    rcx, rcx
0x18000d1e7  jz      short loc_18000D1EE
0x18000d1e9  call    ?Release@RefBase@wmi@@QEAAKXZ; wmi::RefBase::Release(void)
0x18000d1ee  mov     [rsp+168h+var_130], r12
0x18000d1f3  lea     rax, [rsp+168h+var_108]
0x18000d1f8  mov     rcx, [rsp+168h+var_118]; void *
0x18000d1fd  cmp     rcx, rax
0x18000d200  jz      short loc_18000D208
0x18000d202  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000d207  nop
0x18000d208  mov     ecx, r14d; dwErrCode
0x18000d20b  call    cs:__imp_SetLastError
0x18000d211  nop
0x18000d212  lea     rcx, [rsp+168h+var_128]; this
0x18000d217  call    ??1EvtHandleRef@@QEAA@XZ; EvtHandleRef::~EvtHandleRef(void)
0x18000d21c  mov     rax, rdi
0x18000d21f  lea     r11, [rsp+168h+var_28]
0x18000d227  mov     rbx, [r11+40h]
0x18000d22b  mov     rsi, [r11+48h]
0x18000d22f  mov     rsp, r11
0x18000d232  pop     r15
0x18000d234  pop     r14
0x18000d236  pop     r13
0x18000d238  pop     r12
0x18000d23a  pop     rdi
0x18000d23b  retn
0x18000d23c  mov     [rsp+168h+var_138], 0
0x18000d245  lea     r8, [rsp+168h+var_138]
0x18000d24a  mov     rdx, r9
0x18000d24d  call    ??$GetReferencedObjectAsType@VBookmarkObject@@X@ObjectTable@@QEAAKPEAXAEAV?$AutoRef@VBookmarkObject@@@wmi@@@Z; ObjectTable::GetReferencedObjectAsType<BookmarkObject,void>(void *,wmi::AutoRef<BookmarkObject> &)
0x18000d252  mov     r14d, eax
0x18000d255  test    eax, eax
0x18000d257  jnz     loc_18000D37D
0x18000d25d  mov     rbx, [rsp+168h+var_138]
0x18000d262  lea     rcx, [rbx+40h]
0x18000d266  lea     rdx, [rsp+168h+var_118]
0x18000d26b  call    ?Render@Bookmark@@QEBAXAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; Bookmark::Render(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &)
0x18000d270  nop
0x18000d271  test    rbx, rbx
0x18000d274  jz      loc_18000D10B
0x18000d27a  mov     rcx, rbx; this
0x18000d27d  call    ?Release@RefBase@wmi@@QEAAKXZ; wmi::RefBase::Release(void)
0x18000d282  jmp     loc_18000D10B
0x18000d287  bts     edi, 1Ch
0x18000d28b  mov     [rsp+168h+Flags], edi
0x18000d292  xor     r12d, r12d
0x18000d295  mov     [rsp+168h+var_138], r12
0x18000d29a  mov     [rsp+168h+var_148], rax
0x18000d29f  lea     r9, [rsp+168h+arg_8]
0x18000d2a7  call    ??$Emplace@VRemotePullSubscription@@AEAV?$AutoRef@VSession@@@wmi@@AEAPEAXK@HandleTable@@QEAAPEAVRemotePullSubscription@@AEAPEAXAEAV?$AutoRef@VSession@@@wmi@@0$$QEAK@Z; HandleTable::Emplace<RemotePullSubscription,wmi::AutoRef<Session> &,void * &,ulong>(void * &,wmi::AutoRef<Session> &,void * &,ulong &&)
0x18000d2ac  mov     rcx, rax
0x18000d2af  lea     ebx, [r12+1]
0x18000d2b4  test    rax, rax
0x18000d2b7  jnz     loc_18000D4AC
0x18000d2bd  lea     edi, [rax+0Eh]
0x18000d2c0  test    cs:byte_18004B801, 4
0x18000d2c7  jnz     loc_18000D4DC
0x18000d2cd  test    edi, edi
0x18000d2cf  jnz     loc_18000D4F3
0x18000d2d5  mov     r14d, r12d
0x18000d2d8  mov     rcx, r12
0x18000d2db  cmp     byte ptr [rsi+1Ch], 3
0x18000d2df  cmovz   rcx, rsi; this
0x18000d2e3  mov     rax, [rsp+168h+var_110]
0x18000d2e8  sub     rax, [rsp+168h+var_118]
0x18000d2ed  neg     rax
0x18000d2f0  sbb     r9, r9
0x18000d2f3  and     r9, [rsp+168h+var_118]; wchar_t *
0x18000d2f8  mov     r8, r15; wchar_t *
0x18000d2fb  mov     rdx, r13; wchar_t *
0x18000d2fe  call    ?Initialize@RemotePullSubscription@@QEAAXPEB_W00@Z; RemotePullSubscription::Initialize(wchar_t const *,wchar_t const *,wchar_t const *)
0x18000d303  jmp     loc_18000D1C5
0x18000d308  test    r9, r9
0x18000d30b  jnz     loc_18000D0E8
0x18000d311  jmp     short loc_18000D31C
0x18000d313  test    rbx, rbx
0x18000d316  jnz     loc_18000D0C6
0x18000d31c  lea     rax, WPP_GLOBAL_Control
0x18000d323  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d32a  cmp     rcx, rax
0x18000d32d  jnz     loc_18000D57F
0x18000d333  xorps   xmm0, xmm0
0x18000d336  movdqu  [rsp+168h+pExceptionObject], xmm0
0x18000d33f  mov     [rsp+168h+var_70], r15
0x18000d347  mov     [rsp+168h+var_68], 57h ; 'W'
0x18000d352  mov     [rsp+168h+var_64], 0FFFFFFFFh
0x18000d35d  mov     [rsp+168h+var_60], 22Fh
0x18000d368  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x18000d36f  lea     rcx, [rsp+168h+pExceptionObject]; pExceptionObject
0x18000d377  call    _CxxThrowException_0
0x18000d37d  lea     rax, WPP_GLOBAL_Control
0x18000d384  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d38b  cmp     rcx, rax
0x18000d38e  jz      short loc_18000D3B6
0x18000d390  mov     ebx, 1
0x18000d395  test    [rcx+1Ch], bl
0x18000d398  jz      short loc_18000D3B6
0x18000d39a  cmp     byte ptr [rcx+19h], 2
0x18000d39e  jb      short loc_18000D3B6
0x18000d3a0  lea     edx, [rbx+1Bh]
0x18000d3a3  mov     r9d, r14d
0x18000d3a6  lea     r8, WPP_6c6c805d13ef39f517b43cdeae326efa_Traceguids
0x18000d3ad  mov     rcx, [rcx+10h]
0x18000d3b1  call    WPP_SF_D
0x18000d3b6  xorps   xmm0, xmm0
0x18000d3b9  movdqu  [rsp+168h+var_A8], xmm0
0x18000d3c2  mov     [rsp+168h+var_98], 0
0x18000d3ce  mov     [rsp+168h+var_90], r14d
0x18000d3d6  mov     [rsp+168h+var_8C], 0FFFFFFFFh
0x18000d3e1  mov     [rsp+168h+var_88], 244h
0x18000d3ec  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x18000d3f3  lea     rcx, [rsp+168h+var_A8]; pExceptionObject
0x18000d3fb  call    _CxxThrowException_0
0x18000d401  mov     rax, [rsp+168h+var_138]
0x18000d406  mov     [rcx+10h], rax
0x18000d40a  lock add [rcx+8], ebx
0x18000d40e  lock add [rcx+18h], ebx
0x18000d412  mov     rsi, rcx
0x18000d415  mov     [rsp+168h+var_128], rcx
0x18000d41a  mov     [rsp+168h+var_138], r12
0x18000d41f  lea     rcx, [rsp+168h+var_138]; this
0x18000d424  call    ??1EvtHandleRef@@QEAA@XZ; EvtHandleRef::~EvtHandleRef(void)
0x18000d429  mov     edi, r12d
0x18000d42c  jmp     loc_18000D174
0x18000d431  lea     rax, WPP_GLOBAL_Control
0x18000d438  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d43f  cmp     rcx, rax
0x18000d442  jz      short loc_18000D467
0x18000d444  test    [rcx+1Ch], bl
0x18000d447  jz      short loc_18000D467
0x18000d449  cmp     byte ptr [rcx+19h], 2
0x18000d44d  jb      short loc_18000D467
0x18000d44f  mov     edx, 1Dh
0x18000d454  mov     r9d, edi
0x18000d457  lea     r8, WPP_6c6c805d13ef39f517b43cdeae326efa_Traceguids
0x18000d45e  mov     rcx, [rcx+10h]
0x18000d462  call    WPP_SF_D
0x18000d467  lea     rax, word_18004024A
0x18000d46e  mov     [rsp+168h+var_F8], rax
0x18000d473  mov     [rsp+168h+var_F0], r12
0x18000d478  mov     [rsp+168h+var_E8], r12
0x18000d480  mov     [rsp+168h+var_E0], edi
0x18000d487  mov     [rsp+168h+var_DC], 0FFFFFFFFFFFFFFFFh
0x18000d493  mov     [rsp+168h+var_D4], r12b
0x18000d49b  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x18000d4a2  lea     rcx, [rsp+168h+var_F8]; pExceptionObject
0x18000d4a7  call    _CxxThrowException_0
0x18000d4ac  mov     rax, [rsp+168h+var_138]
0x18000d4b1  mov     [rcx+10h], rax
0x18000d4b5  lock add [rcx+8], ebx
0x18000d4b9  lock add [rcx+18h], ebx
0x18000d4bd  mov     rsi, rcx
0x18000d4c0  mov     [rsp+168h+var_128], rcx
0x18000d4c5  mov     [rsp+168h+var_138], r12
0x18000d4ca  lea     rcx, [rsp+168h+var_138]; this
0x18000d4cf  call    ??1EvtHandleRef@@QEAA@XZ; EvtHandleRef::~EvtHandleRef(void)
0x18000d4d4  mov     edi, r12d
0x18000d4d7  jmp     loc_18000D2C0
0x18000d4dc  mov     r9, r15
0x18000d4df  mov     r8, r13
0x18000d4e2  lea     rdx, EVENT_PULLSUB_CREATE
0x18000d4e9  call    McTemplateU0zz_EventWriteTransfer
0x18000d4ee  jmp     loc_18000D2CD
0x18000d4f3  lea     rax, WPP_GLOBAL_Control
0x18000d4fa  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d501  cmp     rcx, rax
0x18000d504  jz      short loc_18000D529
0x18000d506  test    [rcx+1Ch], bl
0x18000d509  jz      short loc_18000D529
0x18000d50b  cmp     byte ptr [rcx+19h], 2
0x18000d50f  jb      short loc_18000D529
0x18000d511  mov     edx, 1Eh
0x18000d516  mov     r9d, edi
0x18000d519  lea     r8, WPP_6c6c805d13ef39f517b43cdeae326efa_Traceguids
0x18000d520  mov     rcx, [rcx+10h]
0x18000d524  call    WPP_SF_D
0x18000d529  lea     rax, word_18004024A
0x18000d530  mov     [rsp+168h+var_D0], rax
0x18000d538  mov     [rsp+168h+var_C8], r12
0x18000d540  mov     [rsp+168h+var_C0], r12
0x18000d548  mov     [rsp+168h+var_B8], edi
0x18000d54f  mov     [rsp+168h+var_B4], 0FFFFFFFFFFFFFFFFh
0x18000d55b  mov     [rsp+168h+var_AC], r12b
0x18000d563  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x18000d56a  lea     rcx, [rsp+168h+var_D0]; pExceptionObject
0x18000d572  call    _CxxThrowException_0
0x18000d577  mov     rdi, r12
0x18000d57a  jmp     loc_18000D1DA
0x18000d57f  mov     ebx, 1
0x18000d584  test    [rcx+1Ch], bl
0x18000d587  jz      loc_18000D333
0x18000d58d  cmp     byte ptr [rcx+19h], 2
0x18000d591  jb      loc_18000D333
0x18000d597  lea     edx, [rbx+1Ah]
0x18000d59a  lea     r9d, [rbx+56h]
0x18000d59e  lea     r8, WPP_6c6c805d13ef39f517b43cdeae326efa_Traceguids
0x18000d5a5  mov     rcx, [rcx+10h]
0x18000d5a9  call    WPP_SF_D
0x18000d5ae  jmp     loc_18000D333
0x18000d5b3  lea     rax, WPP_GLOBAL_Control
0x18000d5ba  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d5c1  cmp     rcx, rax
0x18000d5c4  jz      short loc_18000D5ED
0x18000d5c6  mov     ebx, 1
0x18000d5cb  test    [rcx+1Ch], bl
0x18000d5ce  jz      short loc_18000D5ED
0x18000d5d0  cmp     byte ptr [rcx+19h], 2
0x18000d5d4  jb      short loc_18000D5ED
  ... truncated ...
```
