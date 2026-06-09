# CEventDispatcher::CForwardSink::OnDesktopUnlock(__PTSSessInfo *,__MIDL___MIDL_itf_lsminterfacesdef_0000_0001_0001,__MIDL___MIDL_itf_lsminterfacesdef_0000_0001_0001)

- ea: `0x18001de40`
- end: `0x18001e574`
- name: `?OnDesktopUnlock@CForwardSink@CEventDispatcher@@UEAAJPEAU__PTSSessInfo@@W4__MIDL___MIDL_itf_lsminterfacesdef_0000_0001_0001@@1@Z`
- size: `1844`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `loader_planting, installer_update`

## callees

- `0x1800095a0`
- `0x180009940`
- `0x18000f054`
- `0x1800121d0`
- `0x18001de40`
- `0x180033f60`
- `0x180034df8`
- `0x1800c4328`
- `0x1800c9400`
- `0x1800cae70`
- `0x1800ce010`

## import_xrefs

- `ntdll!RtlReleaseResource` at `0x18001e150`
- `ntdll!RtlReleaseResource` at `0x18001e150`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001dfd4`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001e387`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001e542`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001dfd4`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001e387`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001e542`

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
  if ( (unsigned int)dword_18012E170 > 5 )
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
    UserData.Ptr = (ULONGLONG)off_18012E178;
    UserData.Size = *(unsigned __int16 *)off_18012E178;
    UserData.Reserved = 2;
    v48 = (__int16 *)qword_18011BB50;
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
      if ( (unsigned int)dword_18012E170 > 3 )
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
        UserData.Ptr = (ULONGLONG)off_18012E178;
        UserData.Size = *(unsigned __int16 *)off_18012E178;
        UserData.Reserved = 2;
        v48 = &word_18011C77E;
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
    if ( v25 >= 0 || (unsigned int)dword_18012E170 <= 2 )
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
    UserData.Ptr = (ULONGLONG)off_18012E178;
    UserData.Size = *(unsigned __int16 *)off_18012E178;
    UserData.Reserved = 2;
    v48 = (__int16 *)&dword_18011B97C;
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
  if ( v28 < 0 && (unsigned int)dword_18012E170 > 3 )
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
    UserData.Ptr = (ULONGLONG)off_18012E178;
    UserData.Size = *(unsigned __int16 *)off_18012E178;
    UserData.Reserved = 2;
    v48 = &word_18011C61E;
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
0x18001de40  push    rbp
0x18001de42  push    rbx
0x18001de43  push    rsi
0x18001de44  push    rdi
0x18001de45  push    r12
0x18001de47  push    r13
0x18001de49  push    r14
0x18001de4b  push    r15
0x18001de4d  sub     rsp, 168h
0x18001de54  lea     rbp, [rsp+30h]
0x18001de59  mov     rax, cs:__security_cookie
0x18001de60  xor     rax, rbp
0x18001de63  mov     [rbp+170h+var_50], rax
0x18001de6a  movsxd  r14, r9d
0x18001de6d  mov     [rbp+170h+var_168], r14d
0x18001de71  movsxd  rdi, r8d
0x18001de74  mov     [rbp+170h+var_164], edi
0x18001de77  mov     r13, rdx
0x18001de7a  mov     rsi, rcx
0x18001de7d  mov     [rbp+170h+var_F8], rcx
0x18001de81  mov     [rbp+170h+var_148], rcx
0x18001de85  mov     [rbp+170h+var_140], rdx
0x18001de89  mov     [rbp+170h+var_158], edi
0x18001de8c  mov     [rbp+170h+var_170], r14d
0x18001de90  mov     eax, cs:dword_18012E170
0x18001de96  cmp     eax, 5
0x18001de99  jbe     loc_18001DFE2
0x18001de9f  mov     [rbp+170h+var_128], r14
0x18001dea3  mov     [rbp+170h+var_150], rdi
0x18001dea7  mov     [rbp+170h+var_110], rcx
0x18001deab  mov     qword ptr [rbp+170h+var_108.Id], rdx
0x18001deaf  movsxd  rax, dword ptr [rdx+18h]
0x18001deb3  mov     [rbp+170h+Resource], rax
0x18001deb7  lea     rax, [rbp+170h+var_128]
0x18001debb  mov     [rbp+170h+var_70], rax
0x18001dec2  mov     [rbp+170h+var_68], 8
0x18001decd  xor     ebx, ebx
0x18001decf  lea     rax, [rbp+170h+var_150]
0x18001ded3  mov     [rbp+170h+var_80], rax
0x18001deda  mov     [rbp+170h+var_78], 8
0x18001dee5  lea     rax, [rbp+170h+var_110]
0x18001dee9  mov     [rbp+170h+var_90], rax
0x18001def0  mov     [rbp+170h+var_88], 8
0x18001defb  lea     rax, [rbp+170h+var_108]
0x18001deff  mov     [rbp+170h+var_A0], rax
0x18001df06  mov     [rbp+170h+var_98], 8
0x18001df11  lea     rax, [rbp+170h+Resource]
0x18001df15  mov     [rbp+170h+var_B0], rax
0x18001df1c  mov     [rbp+170h+var_A8], 8
0x18001df27  lea     rax, aDispatchingEve; "Dispatching event OnDesktopUnlock"
0x18001df2e  mov     [rbp+170h+var_C0], rax
0x18001df35  mov     [rbp+170h+var_B8], 22h ; '"'
0x18001df40  mov     dword ptr [rbp+170h+EventDescriptor.Id], 0B000000h
0x18001df47  movzx   eax, cs:word_18011BB46
0x18001df4e  mov     dword ptr [rbp+170h+EventDescriptor.Level], eax
0x18001df51  mov     [rbp+170h+EventDescriptor.Keyword], rbx
0x18001df55  mov     rax, cs:off_18012E178
0x18001df5c  mov     [rbp+170h+var_E0.Ptr], rax
0x18001df63  movzx   eax, word ptr [rax]
0x18001df66  mov     [rbp+170h+var_E0.Size], eax
0x18001df6c  mov     dword ptr [rbp+170h+var_E0.0Ch], 2
0x18001df76  lea     rax, qword_18011BB50
0x18001df7d  mov     [rbp+170h+var_D0], rax
0x18001df84  mov     [rbp+170h+var_C8], 49h ; 'I'
0x18001df8e  mov     [rbp+170h+var_C4], 1
0x18001df98  lea     rax, _TraceLoggingMetadataEnd
0x18001df9f  lea     r15, _TraceLoggingMetadata
0x18001dfa6  sub     eax, r15d
0x18001dfa9  mov     [rbp+170h+var_160], eax
0x18001dfac  mov     eax, [rbp+170h+var_160]
0x18001dfaf  lea     rax, [rbp+170h+var_E0]
0x18001dfb6  mov     [rsp+1A0h+UserData], rax; UserData
0x18001dfbb  mov     [rsp+1A0h+UserDataCount], 8; UserDataCount
0x18001dfc3  xor     r9d, r9d; RelatedActivityId
0x18001dfc6  xor     r8d, r8d; ActivityId
0x18001dfc9  lea     rdx, [rbp+170h+EventDescriptor]; EventDescriptor
0x18001dfcd  mov     rcx, cs:RegHandle; RegHandle
0x18001dfd4  call    cs:__imp_EventWriteTransfer
0x18001dfdb  nop     dword ptr [rax+rax+00h]
0x18001dfe0  jmp     short loc_18001DFE4
0x18001dfe2  xor     ebx, ebx
0x18001dfe4  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ITSNotifySinkEx@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ITSNotifySinkEx@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ITSNotifySinkEx> `wil::Feature<__WilFeatureTraits_Feature_ITSNotifySinkEx>::GetImpl(void)'::`2'::impl
0x18001dfeb  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ITSNotifySinkEx@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ITSNotifySinkEx>::__private_IsEnabled(void)
0x18001dff0  test    al, al
0x18001dff2  jz      short loc_18001E017
0x18001dff4  mov     [rsp+1A0h+UserDataCount], r14d; int
0x18001dff9  mov     r9d, edi
0x18001dffc  mov     r8, r13
0x18001dfff  lea     rdx, ??_9ITSNotifySink@@$BFA@AA; [thunk]: ITSNotifySink::`vcall'{80,{flat}}
0x18001e006  mov     rcx, rsi; this
0x18001e009  call    ??$DispatchEvent@PEAU__PTSSessInfo@@W4__MIDL___MIDL_itf_lsminterfacesdef_0000_0001_0001@@W42@@CForwardSink@CEventDispatcher@@AEAAXU?$EvFunction@P8ITSNotifySink@@EAAJPEAU__PTSSessInfo@@W4__MIDL___MIDL_itf_lsminterfacesdef_0000_0001_0001@@1@Z@@PEAU__PTSSessInfo@@W4__MIDL___MIDL_itf_lsminterfacesdef_0000_0001_0001@@2@Z; CEventDispatcher::CForwardSink::DispatchEvent<__PTSSessInfo *,__MIDL___MIDL_itf_lsminterfacesdef_0000_0001_0001,__MIDL___MIDL_itf_lsminterfacesdef_0000_0001_0001>(EvFunction<long (ITSNotifySink::*)(__PTSSessInfo *,__MIDL___MIDL_itf_lsminterfacesdef_0000_0001_0001,__MIDL___MIDL_itf_lsminterfacesdef_0000_0001_0001)>,__PTSSessInfo *,__MIDL___MIDL_itf_lsminterfacesdef_0000_0001_0001,__MIDL___MIDL_itf_lsminterfacesdef_0000_0001_0001)
0x18001e00e  lea     r12, [rsi+8]
0x18001e012  jmp     loc_18001E3C6
0x18001e017  lea     r12, [rsi+8]
0x18001e01b  mov     [rbp+170h+var_128], r12
0x18001e01f  mov     rdx, [r12]
0x18001e023  add     rdx, 648h; struct CResource *
0x18001e02a  lea     rcx, [rbp+170h+Resource]; this
0x18001e02e  call    ??0CAutoExclusiveLock@@QEAA@AEAVCResource@@@Z; CAutoExclusiveLock::CAutoExclusiveLock(CResource &)
0x18001e033  mov     ecx, ebx
0x18001e035  mov     rdx, [r12]
0x18001e039  add     rdx, 638h
0x18001e040  mov     rax, [rdx]
0x18001e043  cmp     rax, rdx
0x18001e046  jz      short loc_18001E05A
0x18001e048  nop     dword ptr [rax+rax+00000000h]
0x18001e050  inc     ecx
0x18001e052  mov     rax, [rax]
0x18001e055  cmp     rax, rdx
0x18001e058  jnz     short loc_18001E050
0x18001e05a  lea     r14d, ds:0[rcx*8]
0x18001e062  mov     dword ptr [rbp+170h+var_150], r14d
0x18001e066  mov     [rbp+170h+var_160], r14d
0x18001e06a  mov     eax, r14d
0x18001e06d  lea     rcx, [r14+0Fh]
0x18001e071  cmp     rcx, rax
0x18001e074  ja      short loc_18001E080
0x18001e076  mov     rcx, 0FFFFFFFFFFFFFF0h
0x18001e080  and     rcx, 0FFFFFFFFFFFFFFF0h
0x18001e084  mov     rax, rcx
0x18001e087  call    _alloca_probe
0x18001e08c  sub     rsp, rcx
0x18001e08f  lea     r15, [rsp+1A0h+var_170]
0x18001e094  mov     [rbp+170h+var_F0], r15
0x18001e09b  jmp     short loc_18001E0E3
0x18001e09d  call    _o__resetstkoflw_0
0x18001e0a2  xor     r15d, r15d
0x18001e0a5  mov     [rbp+170h+var_F0], r15
0x18001e0ac  mov     r8d, [rbp+170h+var_160]
0x18001e0b0  lea     rdx, aAllocaFailedFo; "alloca failed for %d bytes"
0x18001e0b7  mov     ecx, 8; int
0x18001e0bc  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18001e0c1  xor     ebx, ebx
0x18001e0c3  mov     r12, [rbp+170h+var_128]
0x18001e0c7  mov     rax, [rbp+170h+var_148]
0x18001e0cb  mov     [rbp+170h+var_F8], rax
0x18001e0cf  mov     r13, [rbp+170h+var_140]
0x18001e0d3  mov     eax, [rbp+170h+var_158]
0x18001e0d6  mov     [rbp+170h+var_164], eax
0x18001e0d9  mov     eax, [rbp+170h+var_170]
0x18001e0dc  mov     [rbp+170h+var_168], eax
0x18001e0df  mov     r14d, dword ptr [rbp+170h+var_150]
0x18001e0e3  test    r15, r15
0x18001e0e6  jz      loc_18001E3B5
0x18001e0ec  shr     r14d, 3
0x18001e0f0  mov     esi, ebx
0x18001e0f2  mov     rax, [r12]
0x18001e0f6  add     rax, 638h
0x18001e0fc  mov     rdi, [rax]
0x18001e0ff  cmp     rdi, rax
0x18001e102  jz      short loc_18001E13D
0x18001e104  cmp     esi, r14d
0x18001e107  jnb     short loc_18001E13D
0x18001e109  lea     rcx, [rdi-638h]
0x18001e110  test    rdi, rdi
0x18001e113  cmovz   rcx, rbx
0x18001e117  mov     eax, esi
0x18001e119  mov     [r15+rax*8], rcx
0x18001e11d  mov     rax, [rcx]
0x18001e120  mov     rax, [rax+8]
0x18001e124  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e129  inc     esi
0x18001e12b  mov     rdi, [rdi]
0x18001e12e  mov     rax, [r12]
0x18001e132  add     rax, 638h
0x18001e138  cmp     rdi, rax
0x18001e13b  jnz     short loc_18001E104
0x18001e13d  cmp     [rbp+170h+var_118], 0
0x18001e141  jz      short loc_18001E15C
0x18001e143  mov     [rbp+170h+var_118], ebx
0x18001e146  mov     rcx, [rbp+170h+Resource]; Resource
0x18001e14a  cmp     dword ptr [rcx+60h], 0
0x18001e14e  jz      short loc_18001E15C
0x18001e150  call    cs:__imp_RtlReleaseResource
0x18001e157  nop     dword ptr [rax+rax+00h]
0x18001e15c  mov     edi, ebx
0x18001e15e  test    r14d, r14d
0x18001e161  jz      loc_18001E3B5
0x18001e167  mov     rsi, rbx
0x18001e16a  mov     r12d, [rbp+170h+var_164]
0x18001e16e  xchg    ax, ax
0x18001e170  mov     rax, [r15+rsi*8]
0x18001e174  mov     rcx, [rax+648h]
0x18001e17b  mov     rax, [rcx]
0x18001e17e  mov     r9d, [rbp+170h+var_168]
0x18001e182  mov     r8d, r12d
0x18001e185  mov     rdx, r13
0x18001e188  mov     rax, [rax+50h]
0x18001e18c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e191  mov     edx, eax
0x18001e193  cmp     eax, 800706BAh
0x18001e198  jz      loc_18001E28E
0x18001e19e  cmp     eax, 80010108h
0x18001e1a3  jz      loc_18001E28E
0x18001e1a9  test    eax, eax
0x18001e1ab  jns     loc_18001E393
0x18001e1b1  mov     ecx, cs:dword_18012E170
0x18001e1b7  cmp     ecx, 2
0x18001e1ba  jbe     loc_18001E393
0x18001e1c0  mov     rax, [r15+rsi*8]
0x18001e1c4  mov     rcx, [rax+648h]
0x18001e1cb  mov     [rbp+170h+var_140], rcx
0x18001e1cf  mov     dword ptr [rbp+170h+var_150], edx
0x18001e1d2  lea     rax, [rbp+170h+var_140]
0x18001e1d6  mov     [rbp+170h+var_A0], rax
0x18001e1dd  mov     [rbp+170h+var_98], 8
0x18001e1e8  lea     rax, [rbp+170h+var_150]
0x18001e1ec  mov     [rbp+170h+var_B0], rax
0x18001e1f3  mov     [rbp+170h+var_A8], 4
0x18001e1fe  lea     rax, aOndesktopunloc; "OnDesktopUnlock failed"
0x18001e205  mov     [rbp+170h+var_C0], rax
0x18001e20c  mov     [rbp+170h+var_B8], 17h
0x18001e217  mov     dword ptr [rbp+170h+EventDescriptor.Id], 0B000000h
0x18001e21e  movzx   eax, cs:word_18011B972
0x18001e225  mov     dword ptr [rbp+170h+EventDescriptor.Level], eax
0x18001e228  mov     [rbp+170h+EventDescriptor.Keyword], rbx
0x18001e22c  mov     rax, cs:off_18012E178
0x18001e233  mov     [rbp+170h+var_E0.Ptr], rax
0x18001e23a  movzx   eax, word ptr [rax]
0x18001e23d  mov     [rbp+170h+var_E0.Size], eax
0x18001e243  mov     dword ptr [rbp+170h+var_E0.0Ch], 2
0x18001e24d  lea     rax, dword_18011B97C
0x18001e254  mov     [rbp+170h+var_D0], rax
0x18001e25b  mov     [rbp+170h+var_C8], 2Fh ; '/'
0x18001e265  mov     [rbp+170h+var_C4], 1
0x18001e26f  lea     rax, _TraceLoggingMetadataEnd
0x18001e276  lea     rcx, _TraceLoggingMetadata
0x18001e27d  sub     eax, ecx
0x18001e27f  mov     [rbp+170h+var_170], eax
0x18001e282  mov     eax, [rbp+170h+var_170]
0x18001e285  lea     rdx, [rbp+170h+EventDescriptor]
0x18001e289  jmp     loc_18001E366
0x18001e28e  mov     eax, cs:dword_18012E170
0x18001e294  cmp     eax, 3
0x18001e297  jbe     loc_18001E393
0x18001e29d  mov     [rbp+170h+var_170], edx
0x18001e2a0  mov     rax, [r15+rsi*8]
0x18001e2a4  mov     rcx, [rax+648h]
0x18001e2ab  mov     [rbp+170h+var_148], rcx
0x18001e2af  lea     rax, [rbp+170h+var_170]
0x18001e2b3  mov     [rbp+170h+var_A0], rax
0x18001e2ba  mov     [rbp+170h+var_98], 4
0x18001e2c5  lea     rax, [rbp+170h+var_148]
0x18001e2c9  mov     [rbp+170h+var_B0], rax
0x18001e2d0  mov     [rbp+170h+var_A8], 8
0x18001e2db  lea     rax, aSubscriberIsNo; "Subscriber is no longer available"
0x18001e2e2  mov     [rbp+170h+var_C0], rax
0x18001e2e9  mov     [rbp+170h+var_B8], 22h ; '"'
0x18001e2f4  mov     dword ptr [rbp+170h+var_108.Id], 0B000000h
0x18001e2fb  movzx   eax, cs:word_18011C774
0x18001e302  mov     dword ptr [rbp+170h+var_108.Level], eax
0x18001e305  mov     [rbp+170h+var_108.Keyword], rbx
0x18001e309  mov     rax, cs:off_18012E178
0x18001e310  mov     [rbp+170h+var_E0.Ptr], rax
0x18001e317  movzx   eax, word ptr [rax]
0x18001e31a  mov     [rbp+170h+var_E0.Size], eax
0x18001e320  mov     dword ptr [rbp+170h+var_E0.0Ch], 2
0x18001e32a  lea     rax, word_18011C77E
0x18001e331  mov     [rbp+170h+var_D0], rax
0x18001e338  mov     [rbp+170h+var_C8], 2Fh ; '/'
0x18001e342  mov     [rbp+170h+var_C4], 1
0x18001e34c  lea     rax, _TraceLoggingMetadataEnd
0x18001e353  lea     rcx, _TraceLoggingMetadata
0x18001e35a  sub     eax, ecx
0x18001e35c  mov     [rbp+170h+var_158], eax
0x18001e35f  mov     eax, [rbp+170h+var_158]
0x18001e362  lea     rdx, [rbp+170h+var_108]; EventDescriptor
0x18001e366  lea     rax, [rbp+170h+var_E0]
0x18001e36d  mov     [rsp+1A0h+UserData], rax; UserData
0x18001e372  mov     [rsp+1A0h+UserDataCount], 5; UserDataCount
0x18001e37a  xor     r9d, r9d; RelatedActivityId
0x18001e37d  xor     r8d, r8d; ActivityId
0x18001e380  mov     rcx, cs:RegHandle; RegHandle
0x18001e387  call    cs:__imp_EventWriteTransfer
0x18001e38e  nop     dword ptr [rax+rax+00h]
0x18001e393  mov     rcx, [r15+rsi*8]
0x18001e397  mov     rax, [rcx]
0x18001e39a  mov     rax, [rax+10h]
0x18001e39e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e3a3  inc     edi
0x18001e3a5  inc     rsi
0x18001e3a8  cmp     edi, r14d
0x18001e3ab  jb      loc_18001E170
0x18001e3b1  mov     r12, [rbp+170h+var_128]
0x18001e3b5  lea     rcx, [rbp+170h+Resource]; this
0x18001e3b9  call    ??1CAutoSharedLock@@QEAA@XZ; CAutoSharedLock::~CAutoSharedLock(void)
0x18001e3be  mov     rsi, [rbp+170h+var_F8]
0x18001e3c2  mov     r14d, [rbp+170h+var_168]
0x18001e3c6  mov     r8, r13
0x18001e3c9  mov     edx, 0Eh
0x18001e3ce  mov     rcx, [r12]
0x18001e3d2  call    ?TestForEvent@CEventDispatcher@@AEAAJW4__MIDL___MIDL_itf_lsminterfacesdef_0000_0001_0002@@PEAU__PTSSessInfo@@@Z; CEventDispatcher::TestForEvent(__MIDL___MIDL_itf_lsminterfacesdef_0000_0001_0002,__PTSSessInfo *)
0x18001e3d7  mov     edi, eax
0x18001e3d9  test    eax, eax
0x18001e3db  jns     loc_18001E54E
0x18001e3e1  mov     ecx, cs:dword_18012E170
0x18001e3e7  cmp     ecx, 3
0x18001e3ea  jbe     loc_18001E54E
0x18001e3f0  movsxd  rcx, r14d
0x18001e3f3  mov     [rbp+170h+var_140], rcx
  ... truncated ...
```
