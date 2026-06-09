# CEventDispatcher::CForwardSink::OnDesktopUnlock(__PTSSessInfo *,__MIDL___MIDL_itf_lsminterfacesdef_0000_0001_0001,__MIDL___MIDL_itf_lsminterfacesdef_0000_0001_0001)

- ea: `0x18001d000`
- end: `0x18001d717`
- name: `?OnDesktopUnlock@CForwardSink@CEventDispatcher@@UEAAJPEAU__PTSSessInfo@@W4__MIDL___MIDL_itf_lsminterfacesdef_0000_0001_0001@@1@Z`
- size: `1815`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `loader_planting, installer_update`

## callees

- `0x180009ee0`
- `0x18000a210`
- `0x18000eeb4`
- `0x180011b80`
- `0x18001d000`
- `0x1800321f0`
- `0x180033058`
- `0x1800be394`
- `0x1800c3400`
- `0x1800c4da0`
- `0x1800c8010`

## import_xrefs

- `ntdll!RtlReleaseResource` at `0x18001d302`
- `ntdll!RtlReleaseResource` at `0x18001d302`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001d194`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001d537`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001d6ec`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001d194`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001d537`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001d6ec`

## pseudocode

```c
__int64 __fastcall CEventDispatcher::CForwardSink::OnDesktopUnlock(_QWORD *a1, __int64 a2, signed int a3, int a4)
{
  int v4; // r14d
  _QWORD *v6; // rsi
  _QWORD *v7; // r12
  int v8; // ecx
  _QWORD **v9; // rdx
  _QWORD *i; // rax
  __int64 v11; // r14
  __int64 v12; // rcx
  unsigned __int64 v13; // rcx
  void *v14; // rsp
  void *v15; // rsp
  unsigned int v16; // r14d
  unsigned int v17; // esi
  _QWORD **v18; // rax
  _QWORD *v19; // rdi
  _QWORD *v20; // rcx
  unsigned int v21; // edi
  __int64 v22; // rsi
  unsigned int v23; // r12d
  __int64 v24; // rcx
  int v25; // eax
  __int64 v26; // rdx
  EVENT_DESCRIPTOR *p_EventDescriptor; // rdx
  int v28; // eax
  unsigned int v29; // edi
  _DWORD v31[2]; // [rsp+30h] [rbp+0h] BYREF
  unsigned int v32; // [rsp+38h] [rbp+8h]
  signed int v33; // [rsp+3Ch] [rbp+Ch]
  unsigned int v34; // [rsp+40h] [rbp+10h]
  unsigned int v35; // [rsp+48h] [rbp+18h]
  __int64 v36; // [rsp+50h] [rbp+20h] BYREF
  __int64 v37; // [rsp+58h] [rbp+28h] BYREF
  __int64 v38; // [rsp+60h] [rbp+30h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+68h] [rbp+38h] BYREF
  _QWORD *v40; // [rsp+78h] [rbp+48h] BYREF
  PRTL_RESOURCE Resource; // [rsp+80h] [rbp+50h] BYREF
  int v42; // [rsp+88h] [rbp+58h]
  __int64 v43; // [rsp+90h] [rbp+60h] BYREF
  EVENT_DESCRIPTOR v44; // [rsp+98h] [rbp+68h] BYREF
  _QWORD *v45; // [rsp+A8h] [rbp+78h]
  _DWORD *v46; // [rsp+B0h] [rbp+80h]
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+C0h] [rbp+90h] BYREF
  __int16 *v48; // [rsp+D0h] [rbp+A0h]
  int v49; // [rsp+D8h] [rbp+A8h]
  int v50; // [rsp+DCh] [rbp+ACh]
  const char *v51; // [rsp+E0h] [rbp+B0h]
  __int64 v52; // [rsp+E8h] [rbp+B8h]
  PRTL_RESOURCE *p_Resource; // [rsp+F0h] [rbp+C0h]
  __int64 v54; // [rsp+F8h] [rbp+C8h]
  EVENT_DESCRIPTOR *v55; // [rsp+100h] [rbp+D0h]
  __int64 v56; // [rsp+108h] [rbp+D8h]
  EVENT_DESCRIPTOR *v57; // [rsp+110h] [rbp+E0h]
  __int64 v58; // [rsp+118h] [rbp+E8h]
  PRTL_RESOURCE *v59; // [rsp+120h] [rbp+F0h]
  __int64 v60; // [rsp+128h] [rbp+F8h]
  __int64 *v61; // [rsp+130h] [rbp+100h]
  __int64 v62; // [rsp+138h] [rbp+108h]
  __int64 *v63; // [rsp+140h] [rbp+110h]
  __int64 v64; // [rsp+148h] [rbp+118h]

  v4 = a4;
  v32 = a4;
  v33 = a3;
  v6 = a1;
  v45 = a1;
  v37 = (__int64)a1;
  v38 = a2;
  v35 = a3;
  v31[0] = a4;
  if ( (unsigned int)dword_180128170 > 5 )
  {
    v40 = (_QWORD *)a4;
    v36 = a3;
    v43 = (__int64)a1;
    *(_QWORD *)&v44.Id = a2;
    Resource = (PRTL_RESOURCE)*(int *)(a2 + 24);
    v61 = (__int64 *)&v40;
    v62 = 8;
    v59 = (PRTL_RESOURCE *)&v36;
    v60 = 8;
    v57 = (EVENT_DESCRIPTOR *)&v43;
    v58 = 8;
    v55 = &v44;
    v56 = 8;
    p_Resource = &Resource;
    v54 = 8;
    v51 = "Dispatching event OnDesktopUnlock";
    v52 = 34;
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    *(_DWORD *)&EventDescriptor.Level = 5;
    EventDescriptor.Keyword = 0;
    UserData.Ptr = (ULONGLONG)off_180128178;
    UserData.Size = *(unsigned __int16 *)off_180128178;
    UserData.Reserved = 2;
    v48 = (__int16 *)qword_180115AD0;
    v49 = 73;
    v50 = 1;
    v34 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 8u, &UserData);
  }
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ITSNotifySinkEx>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ITSNotifySinkEx>::GetImpl'::`2'::impl) )
  {
    v7 = v6 + 1;
    v40 = v6 + 1;
    CAutoExclusiveLock::CAutoExclusiveLock((CAutoExclusiveLock *)&Resource, (struct CResource *)(v6[1] + 1608LL));
    v8 = 0;
    v9 = (_QWORD **)(v6[1] + 1592LL);
    for ( i = *v9; i != v9; i = (_QWORD *)*i )
      ++v8;
    v11 = (unsigned int)(8 * v8);
    LODWORD(v36) = 8 * v8;
    v34 = 8 * v8;
    v12 = v11 + 15;
    if ( v11 + 15 <= (unsigned __int64)(unsigned int)v11 )
      v12 = 0xFFFFFFFFFFFFFF0LL;
    v13 = v12 & 0xFFFFFFFFFFFFFFF0uLL;
    v14 = alloca(v13);
    v15 = alloca(v13);
    v46 = v31;
    if ( !v31 )
      goto LABEL_30;
    v16 = (unsigned int)v11 >> 3;
    v17 = 0;
    v18 = (_QWORD **)(*v7 + 1592LL);
    v19 = *v18;
    if ( *v18 != v18 )
    {
      do
      {
        if ( v17 >= v16 )
          break;
        v20 = v19 - 199;
        if ( !v19 )
          v20 = 0;
        *(_QWORD *)&v31[2 * v17] = v20;
        (*(void (__fastcall **)(_QWORD *))(*v20 + 8LL))(v20);
        ++v17;
        v19 = (_QWORD *)*v19;
      }
      while ( v19 != (_QWORD *)(*v7 + 1592LL) );
    }
    if ( v42 )
    {
      v42 = 0;
      if ( LODWORD(Resource[1].Lock.DebugInfo) )
        RtlReleaseResource(Resource);
    }
    v21 = 0;
    if ( !v16 )
    {
LABEL_30:
      CAutoSharedLock::~CAutoSharedLock((CAutoSharedLock *)&Resource);
      v6 = v45;
      v4 = v32;
      goto LABEL_31;
    }
    v22 = 0;
    v23 = v33;
    while ( 1 )
    {
      v24 = *(_QWORD *)(*(_QWORD *)&v31[2 * v22] + 1608LL);
      v25 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, _QWORD))(*(_QWORD *)v24 + 80LL))(v24, a2, v23, v32);
      v26 = (unsigned int)v25;
      if ( v25 != -2147023174 && v25 != -2147417848 )
        break;
      if ( (unsigned int)dword_180128170 > 3 )
      {
        v31[0] = v25;
        v37 = *(_QWORD *)(*(_QWORD *)&v31[2 * v22] + 1608LL);
        v55 = (EVENT_DESCRIPTOR *)v31;
        v56 = 4;
        p_Resource = (PRTL_RESOURCE *)&v37;
        v54 = 8;
        v51 = "Subscriber is no longer available";
        v52 = 34;
        *(_DWORD *)&v44.Id = 184549376;
        *(_DWORD *)&v44.Level = 3;
        v44.Keyword = 0;
        UserData.Ptr = (ULONGLONG)off_180128178;
        UserData.Size = *(unsigned __int16 *)off_180128178;
        UserData.Reserved = 2;
        v48 = &word_1801166FE;
        v49 = 47;
        v50 = 1;
        v35 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
        p_EventDescriptor = &v44;
LABEL_27:
        EventWriteTransfer(RegHandle, p_EventDescriptor, 0, 0, 5u, &UserData);
      }
LABEL_28:
      (*(void (__fastcall **)(_QWORD, __int64))(**(_QWORD **)&v31[2 * v22] + 16LL))(*(_QWORD *)&v31[2 * v22], v26);
      ++v21;
      ++v22;
      if ( v21 >= v16 )
      {
        v7 = v40;
        goto LABEL_30;
      }
    }
    if ( v25 >= 0 || (unsigned int)dword_180128170 <= 2 )
      goto LABEL_28;
    v38 = *(_QWORD *)(*(_QWORD *)&v31[2 * v22] + 1608LL);
    LODWORD(v36) = v25;
    v55 = (EVENT_DESCRIPTOR *)&v38;
    v56 = 8;
    p_Resource = (PRTL_RESOURCE *)&v36;
    v54 = 4;
    v51 = "OnDesktopUnlock failed";
    v52 = 23;
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    *(_DWORD *)&EventDescriptor.Level = 2;
    EventDescriptor.Keyword = 0;
    UserData.Ptr = (ULONGLONG)off_180128178;
    UserData.Size = *(unsigned __int16 *)off_180128178;
    UserData.Reserved = 2;
    v48 = (__int16 *)&dword_1801158FC;
    v49 = 47;
    v50 = 1;
    v31[0] = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    p_EventDescriptor = &EventDescriptor;
    goto LABEL_27;
  }
  CEventDispatcher::CForwardSink::DispatchEvent<__PTSSessInfo *,enum __MIDL___MIDL_itf_lsminterfacesdef_0000_0001_0001,enum __MIDL___MIDL_itf_lsminterfacesdef_0000_0001_0001>(
    (CEventDispatcher::CForwardSink *)v6,
    v4);
  v7 = v6 + 1;
LABEL_31:
  v28 = CEventDispatcher::TestForEvent(*v7, 14, a2);
  v29 = v28;
  if ( v28 < 0 && (unsigned int)dword_180128170 > 3 )
  {
    v38 = v4;
    v37 = v33;
    Resource = (PRTL_RESOURCE)v6;
    *(_QWORD *)&v44.Id = a2;
    v43 = *(int *)(a2 + 24);
    LODWORD(v36) = v28;
    v63 = &v38;
    v64 = 8;
    v61 = &v37;
    v62 = 8;
    v59 = &Resource;
    v60 = 8;
    v57 = &v44;
    v58 = 8;
    v55 = (EVENT_DESCRIPTOR *)&v43;
    v56 = 8;
    p_Resource = (PRTL_RESOURCE *)&v36;
    v54 = 4;
    v51 = "OnDesktopUnlock TestForEvent returned failure";
    v52 = 46;
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    *(_DWORD *)&EventDescriptor.Level = 3;
    EventDescriptor.Keyword = 0;
    UserData.Ptr = (ULONGLONG)off_180128178;
    UserData.Size = *(unsigned __int16 *)off_180128178;
    UserData.Reserved = 2;
    v48 = &word_18011659E;
    v49 = 78;
    v50 = 1;
    v31[0] = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 9u, &UserData);
  }
  return v29;
}

```

## disassembly

```asm
0x18001d000  push    rbp
0x18001d002  push    rbx
0x18001d003  push    rsi
0x18001d004  push    rdi
0x18001d005  push    r12
0x18001d007  push    r13
0x18001d009  push    r14
0x18001d00b  push    r15
0x18001d00d  sub     rsp, 168h
0x18001d014  lea     rbp, [rsp+30h]
0x18001d019  mov     rax, cs:__security_cookie
0x18001d020  xor     rax, rbp
0x18001d023  mov     [rbp+170h+var_50], rax
0x18001d02a  movsxd  r14, r9d
0x18001d02d  mov     [rbp+170h+var_168], r14d
0x18001d031  movsxd  rdi, r8d
0x18001d034  mov     [rbp+170h+var_164], edi
0x18001d037  mov     r13, rdx
0x18001d03a  mov     rsi, rcx
0x18001d03d  mov     [rbp+170h+var_F8], rcx
0x18001d041  mov     [rbp+170h+var_148], rcx
0x18001d045  mov     [rbp+170h+var_140], rdx
0x18001d049  mov     [rbp+170h+var_158], edi
0x18001d04c  mov     [rbp+170h+var_170], r14d
0x18001d050  mov     eax, cs:dword_180128170
0x18001d056  cmp     eax, 5
0x18001d059  jbe     loc_18001D19C
0x18001d05f  mov     [rbp+170h+var_128], r14
0x18001d063  mov     [rbp+170h+var_150], rdi
0x18001d067  mov     [rbp+170h+var_110], rcx
0x18001d06b  mov     qword ptr [rbp+170h+var_108.Id], rdx
0x18001d06f  movsxd  rax, dword ptr [rdx+18h]
0x18001d073  mov     [rbp+170h+Resource], rax
0x18001d077  lea     rax, [rbp+170h+var_128]
0x18001d07b  mov     [rbp+170h+var_70], rax
0x18001d082  mov     [rbp+170h+var_68], 8
0x18001d08d  xor     ebx, ebx
0x18001d08f  lea     rax, [rbp+170h+var_150]
0x18001d093  mov     [rbp+170h+var_80], rax
0x18001d09a  mov     [rbp+170h+var_78], 8
0x18001d0a5  lea     rax, [rbp+170h+var_110]
0x18001d0a9  mov     [rbp+170h+var_90], rax
0x18001d0b0  mov     [rbp+170h+var_88], 8
0x18001d0bb  lea     rax, [rbp+170h+var_108]
0x18001d0bf  mov     [rbp+170h+var_A0], rax
0x18001d0c6  mov     [rbp+170h+var_98], 8
0x18001d0d1  lea     rax, [rbp+170h+Resource]
0x18001d0d5  mov     [rbp+170h+var_B0], rax
0x18001d0dc  mov     [rbp+170h+var_A8], 8
0x18001d0e7  lea     rax, aDispatchingEve; "Dispatching event OnDesktopUnlock"
0x18001d0ee  mov     [rbp+170h+var_C0], rax
0x18001d0f5  mov     [rbp+170h+var_B8], 22h ; '"'
0x18001d100  mov     dword ptr [rbp+170h+EventDescriptor.Id], 0B000000h
0x18001d107  movzx   eax, cs:word_180115AC6
0x18001d10e  mov     dword ptr [rbp+170h+EventDescriptor.Level], eax
0x18001d111  mov     [rbp+170h+EventDescriptor.Keyword], rbx
0x18001d115  mov     rax, cs:off_180128178
0x18001d11c  mov     [rbp+170h+var_E0.Ptr], rax
0x18001d123  movzx   eax, word ptr [rax]
0x18001d126  mov     [rbp+170h+var_E0.Size], eax
0x18001d12c  mov     dword ptr [rbp+170h+var_E0.0Ch], 2
0x18001d136  lea     rax, qword_180115AD0
0x18001d13d  mov     [rbp+170h+var_D0], rax
0x18001d144  mov     [rbp+170h+var_C8], 49h ; 'I'
0x18001d14e  mov     [rbp+170h+var_C4], 1
0x18001d158  lea     rax, _TraceLoggingMetadataEnd
0x18001d15f  lea     r15, _TraceLoggingMetadata
0x18001d166  sub     eax, r15d
0x18001d169  mov     [rbp+170h+var_160], eax
0x18001d16c  mov     eax, [rbp+170h+var_160]
0x18001d16f  lea     rax, [rbp+170h+var_E0]
0x18001d176  mov     [rsp+1A0h+UserData], rax; UserData
0x18001d17b  mov     [rsp+1A0h+UserDataCount], 8; UserDataCount
0x18001d183  xor     r9d, r9d; RelatedActivityId
0x18001d186  xor     r8d, r8d; ActivityId
0x18001d189  lea     rdx, [rbp+170h+EventDescriptor]; EventDescriptor
0x18001d18d  mov     rcx, cs:RegHandle; RegHandle
0x18001d194  call    cs:__imp_EventWriteTransfer
0x18001d19a  jmp     short loc_18001D19E
0x18001d19c  xor     ebx, ebx
0x18001d19e  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ITSNotifySinkEx@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ITSNotifySinkEx@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ITSNotifySinkEx> `wil::Feature<__WilFeatureTraits_Feature_ITSNotifySinkEx>::GetImpl(void)'::`2'::impl
0x18001d1a5  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ITSNotifySinkEx@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ITSNotifySinkEx>::__private_IsEnabled(void)
0x18001d1aa  test    al, al
0x18001d1ac  jz      short loc_18001D1D1
0x18001d1ae  mov     [rsp+1A0h+UserDataCount], r14d; int
0x18001d1b3  mov     r9d, edi
0x18001d1b6  mov     r8, r13
0x18001d1b9  lea     rdx, ??_9ITSNotifySink@@$BFA@AA; [thunk]: ITSNotifySink::`vcall'{80,{flat}}
0x18001d1c0  mov     rcx, rsi; this
0x18001d1c3  call    ??$DispatchEvent@PEAU__PTSSessInfo@@W4__MIDL___MIDL_itf_lsminterfacesdef_0000_0001_0001@@W42@@CForwardSink@CEventDispatcher@@AEAAXU?$EvFunction@P8ITSNotifySink@@EAAJPEAU__PTSSessInfo@@W4__MIDL___MIDL_itf_lsminterfacesdef_0000_0001_0001@@1@Z@@PEAU__PTSSessInfo@@W4__MIDL___MIDL_itf_lsminterfacesdef_0000_0001_0001@@2@Z; CEventDispatcher::CForwardSink::DispatchEvent<__PTSSessInfo *,__MIDL___MIDL_itf_lsminterfacesdef_0000_0001_0001,__MIDL___MIDL_itf_lsminterfacesdef_0000_0001_0001>(EvFunction<long (ITSNotifySink::*)(__PTSSessInfo *,__MIDL___MIDL_itf_lsminterfacesdef_0000_0001_0001,__MIDL___MIDL_itf_lsminterfacesdef_0000_0001_0001)>,__PTSSessInfo *,__MIDL___MIDL_itf_lsminterfacesdef_0000_0001_0001,__MIDL___MIDL_itf_lsminterfacesdef_0000_0001_0001)
0x18001d1c8  lea     r12, [rsi+8]
0x18001d1cc  jmp     loc_18001D570
0x18001d1d1  lea     r12, [rsi+8]
0x18001d1d5  mov     [rbp+170h+var_128], r12
0x18001d1d9  mov     rdx, [r12]
0x18001d1dd  add     rdx, 648h; struct CResource *
0x18001d1e4  lea     rcx, [rbp+170h+Resource]; this
0x18001d1e8  call    ??0CAutoExclusiveLock@@QEAA@AEAVCResource@@@Z; CAutoExclusiveLock::CAutoExclusiveLock(CResource &)
0x18001d1ed  mov     ecx, ebx
0x18001d1ef  mov     rdx, [r12]
0x18001d1f3  add     rdx, 638h
0x18001d1fa  mov     rax, [rdx]
0x18001d1fd  cmp     rax, rdx
0x18001d200  jz      short loc_18001D20C
0x18001d202  inc     ecx
0x18001d204  mov     rax, [rax]
0x18001d207  cmp     rax, rdx
0x18001d20a  jnz     short loc_18001D202
0x18001d20c  lea     r14d, ds:0[rcx*8]
0x18001d214  mov     dword ptr [rbp+170h+var_150], r14d
0x18001d218  mov     [rbp+170h+var_160], r14d
0x18001d21c  mov     eax, r14d
0x18001d21f  lea     rcx, [r14+0Fh]
0x18001d223  cmp     rcx, rax
0x18001d226  ja      short loc_18001D232
0x18001d228  mov     rcx, 0FFFFFFFFFFFFFF0h
0x18001d232  and     rcx, 0FFFFFFFFFFFFFFF0h
0x18001d236  mov     rax, rcx
0x18001d239  call    _alloca_probe
0x18001d23e  sub     rsp, rcx
0x18001d241  lea     r15, [rsp+1A0h+var_170]
0x18001d246  mov     [rbp+170h+var_F0], r15
0x18001d24d  jmp     short loc_18001D295
0x18001d24f  call    _o__resetstkoflw_0
0x18001d254  xor     r15d, r15d
0x18001d257  mov     [rbp+170h+var_F0], r15
0x18001d25e  mov     r8d, [rbp+170h+var_160]
0x18001d262  lea     rdx, aAllocaFailedFo; "alloca failed for %d bytes"
0x18001d269  mov     ecx, 8; int
0x18001d26e  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18001d273  xor     ebx, ebx
0x18001d275  mov     r12, [rbp+170h+var_128]
0x18001d279  mov     rax, [rbp+170h+var_148]
0x18001d27d  mov     [rbp+170h+var_F8], rax
0x18001d281  mov     r13, [rbp+170h+var_140]
0x18001d285  mov     eax, [rbp+170h+var_158]
0x18001d288  mov     [rbp+170h+var_164], eax
0x18001d28b  mov     eax, [rbp+170h+var_170]
0x18001d28e  mov     [rbp+170h+var_168], eax
0x18001d291  mov     r14d, dword ptr [rbp+170h+var_150]
0x18001d295  test    r15, r15
0x18001d298  jz      loc_18001D55F
0x18001d29e  shr     r14d, 3
0x18001d2a2  mov     esi, ebx
0x18001d2a4  mov     rax, [r12]
0x18001d2a8  add     rax, 638h
0x18001d2ae  mov     rdi, [rax]
0x18001d2b1  cmp     rdi, rax
0x18001d2b4  jz      short loc_18001D2EF
0x18001d2b6  cmp     esi, r14d
0x18001d2b9  jnb     short loc_18001D2EF
0x18001d2bb  lea     rcx, [rdi-638h]
0x18001d2c2  test    rdi, rdi
0x18001d2c5  cmovz   rcx, rbx
0x18001d2c9  mov     eax, esi
0x18001d2cb  mov     [r15+rax*8], rcx
0x18001d2cf  mov     rax, [rcx]
0x18001d2d2  mov     rax, [rax+8]
0x18001d2d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d2db  inc     esi
0x18001d2dd  mov     rdi, [rdi]
0x18001d2e0  mov     rax, [r12]
0x18001d2e4  add     rax, 638h
0x18001d2ea  cmp     rdi, rax
0x18001d2ed  jnz     short loc_18001D2B6
0x18001d2ef  cmp     [rbp+170h+var_118], 0
0x18001d2f3  jz      short loc_18001D308
0x18001d2f5  mov     [rbp+170h+var_118], ebx
0x18001d2f8  mov     rcx, [rbp+170h+Resource]; Resource
0x18001d2fc  cmp     dword ptr [rcx+60h], 0
0x18001d300  jz      short loc_18001D308
0x18001d302  call    cs:__imp_RtlReleaseResource
0x18001d308  mov     edi, ebx
0x18001d30a  test    r14d, r14d
0x18001d30d  jz      loc_18001D55F
0x18001d313  mov     rsi, rbx
0x18001d316  mov     r12d, [rbp+170h+var_164]
0x18001d31a  nop     word ptr [rax+rax+00h]
0x18001d320  mov     rax, [r15+rsi*8]
0x18001d324  mov     rcx, [rax+648h]
0x18001d32b  mov     rax, [rcx]
0x18001d32e  mov     r9d, [rbp+170h+var_168]
0x18001d332  mov     r8d, r12d
0x18001d335  mov     rdx, r13
0x18001d338  mov     rax, [rax+50h]
0x18001d33c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d341  mov     edx, eax
0x18001d343  cmp     eax, 800706BAh
0x18001d348  jz      loc_18001D43E
0x18001d34e  cmp     eax, 80010108h
0x18001d353  jz      loc_18001D43E
0x18001d359  test    eax, eax
0x18001d35b  jns     loc_18001D53D
0x18001d361  mov     ecx, cs:dword_180128170
0x18001d367  cmp     ecx, 2
0x18001d36a  jbe     loc_18001D53D
0x18001d370  mov     rax, [r15+rsi*8]
0x18001d374  mov     rcx, [rax+648h]
0x18001d37b  mov     [rbp+170h+var_140], rcx
0x18001d37f  mov     dword ptr [rbp+170h+var_150], edx
0x18001d382  lea     rax, [rbp+170h+var_140]
0x18001d386  mov     [rbp+170h+var_A0], rax
0x18001d38d  mov     [rbp+170h+var_98], 8
0x18001d398  lea     rax, [rbp+170h+var_150]
0x18001d39c  mov     [rbp+170h+var_B0], rax
0x18001d3a3  mov     [rbp+170h+var_A8], 4
0x18001d3ae  lea     rax, aOndesktopunloc; "OnDesktopUnlock failed"
0x18001d3b5  mov     [rbp+170h+var_C0], rax
0x18001d3bc  mov     [rbp+170h+var_B8], 17h
0x18001d3c7  mov     dword ptr [rbp+170h+EventDescriptor.Id], 0B000000h
0x18001d3ce  movzx   eax, cs:word_1801158F2
0x18001d3d5  mov     dword ptr [rbp+170h+EventDescriptor.Level], eax
0x18001d3d8  mov     [rbp+170h+EventDescriptor.Keyword], rbx
0x18001d3dc  mov     rax, cs:off_180128178
0x18001d3e3  mov     [rbp+170h+var_E0.Ptr], rax
0x18001d3ea  movzx   eax, word ptr [rax]
0x18001d3ed  mov     [rbp+170h+var_E0.Size], eax
0x18001d3f3  mov     dword ptr [rbp+170h+var_E0.0Ch], 2
0x18001d3fd  lea     rax, dword_1801158FC
0x18001d404  mov     [rbp+170h+var_D0], rax
0x18001d40b  mov     [rbp+170h+var_C8], 2Fh ; '/'
0x18001d415  mov     [rbp+170h+var_C4], 1
0x18001d41f  lea     rax, _TraceLoggingMetadataEnd
0x18001d426  lea     rcx, _TraceLoggingMetadata
0x18001d42d  sub     eax, ecx
0x18001d42f  mov     [rbp+170h+var_170], eax
0x18001d432  mov     eax, [rbp+170h+var_170]
0x18001d435  lea     rdx, [rbp+170h+EventDescriptor]
0x18001d439  jmp     loc_18001D516
0x18001d43e  mov     eax, cs:dword_180128170
0x18001d444  cmp     eax, 3
0x18001d447  jbe     loc_18001D53D
0x18001d44d  mov     [rbp+170h+var_170], edx
0x18001d450  mov     rax, [r15+rsi*8]
0x18001d454  mov     rcx, [rax+648h]
0x18001d45b  mov     [rbp+170h+var_148], rcx
0x18001d45f  lea     rax, [rbp+170h+var_170]
0x18001d463  mov     [rbp+170h+var_A0], rax
0x18001d46a  mov     [rbp+170h+var_98], 4
0x18001d475  lea     rax, [rbp+170h+var_148]
0x18001d479  mov     [rbp+170h+var_B0], rax
0x18001d480  mov     [rbp+170h+var_A8], 8
0x18001d48b  lea     rax, aSubscriberIsNo; "Subscriber is no longer available"
0x18001d492  mov     [rbp+170h+var_C0], rax
0x18001d499  mov     [rbp+170h+var_B8], 22h ; '"'
0x18001d4a4  mov     dword ptr [rbp+170h+var_108.Id], 0B000000h
0x18001d4ab  movzx   eax, cs:word_1801166F4
0x18001d4b2  mov     dword ptr [rbp+170h+var_108.Level], eax
0x18001d4b5  mov     [rbp+170h+var_108.Keyword], rbx
0x18001d4b9  mov     rax, cs:off_180128178
0x18001d4c0  mov     [rbp+170h+var_E0.Ptr], rax
0x18001d4c7  movzx   eax, word ptr [rax]
0x18001d4ca  mov     [rbp+170h+var_E0.Size], eax
0x18001d4d0  mov     dword ptr [rbp+170h+var_E0.0Ch], 2
0x18001d4da  lea     rax, word_1801166FE
0x18001d4e1  mov     [rbp+170h+var_D0], rax
0x18001d4e8  mov     [rbp+170h+var_C8], 2Fh ; '/'
0x18001d4f2  mov     [rbp+170h+var_C4], 1
0x18001d4fc  lea     rax, _TraceLoggingMetadataEnd
0x18001d503  lea     rcx, _TraceLoggingMetadata
0x18001d50a  sub     eax, ecx
0x18001d50c  mov     [rbp+170h+var_158], eax
0x18001d50f  mov     eax, [rbp+170h+var_158]
0x18001d512  lea     rdx, [rbp+170h+var_108]; EventDescriptor
0x18001d516  lea     rax, [rbp+170h+var_E0]
0x18001d51d  mov     [rsp+1A0h+UserData], rax; UserData
0x18001d522  mov     [rsp+1A0h+UserDataCount], 5; UserDataCount
0x18001d52a  xor     r9d, r9d; RelatedActivityId
0x18001d52d  xor     r8d, r8d; ActivityId
0x18001d530  mov     rcx, cs:RegHandle; RegHandle
0x18001d537  call    cs:__imp_EventWriteTransfer
0x18001d53d  mov     rcx, [r15+rsi*8]
0x18001d541  mov     rax, [rcx]
0x18001d544  mov     rax, [rax+10h]
0x18001d548  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d54d  inc     edi
0x18001d54f  inc     rsi
0x18001d552  cmp     edi, r14d
0x18001d555  jb      loc_18001D320
0x18001d55b  mov     r12, [rbp+170h+var_128]
0x18001d55f  lea     rcx, [rbp+170h+Resource]; this
0x18001d563  call    ??1CAutoSharedLock@@QEAA@XZ; CAutoSharedLock::~CAutoSharedLock(void)
0x18001d568  mov     rsi, [rbp+170h+var_F8]
0x18001d56c  mov     r14d, [rbp+170h+var_168]
0x18001d570  mov     r8, r13
0x18001d573  mov     edx, 0Eh
0x18001d578  mov     rcx, [r12]
0x18001d57c  call    ?TestForEvent@CEventDispatcher@@AEAAJW4__MIDL___MIDL_itf_lsminterfacesdef_0000_0001_0002@@PEAU__PTSSessInfo@@@Z; CEventDispatcher::TestForEvent(__MIDL___MIDL_itf_lsminterfacesdef_0000_0001_0002,__PTSSessInfo *)
0x18001d581  mov     edi, eax
0x18001d583  test    eax, eax
0x18001d585  jns     loc_18001D6F2
0x18001d58b  mov     ecx, cs:dword_180128170
0x18001d591  cmp     ecx, 3
0x18001d594  jbe     loc_18001D6F2
0x18001d59a  movsxd  rcx, r14d
0x18001d59d  mov     [rbp+170h+var_140], rcx
0x18001d5a1  movsxd  rcx, [rbp+170h+var_164]
0x18001d5a5  mov     [rbp+170h+var_148], rcx
0x18001d5a9  mov     [rbp+170h+Resource], rsi
0x18001d5ad  mov     qword ptr [rbp+170h+var_108.Id], r13
  ... truncated ...
```
