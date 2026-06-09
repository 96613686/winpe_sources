# KspCreateClaimInternal(unsigned __int64,unsigned __int64,unsigned __int64,ulong,_BCryptBufferDesc *,uchar *,ulong,ulong *,ulong)

- ea: `0x18001c818`
- end: `0x18001d029`
- name: `?KspCreateClaimInternal@@YAJ_K00KPEAU_BCryptBufferDesc@@PEAEKPEAKK@Z`
- size: `2065`
- prototype: `int(unsigned __int64, unsigned __int64, unsigned __int64, unsigned int, struct _BCryptBufferDesc *, unsigned __int8 *, unsigned int, unsigned int *, unsigned int)`
- caller_count: `1`
- callee_count: `18`
- tags: `broker_com_uri`

## callers

- `0x18002a9a0`

## callees

- `0x180001178`
- `0x1800011c4`
- `0x180001238`
- `0x18000a3c8`
- `0x18000a408`
- `0x18000d2a8`
- `0x18000d9d0`
- `0x180011fd8`
- `0x1800135dc`
- `0x180013aac`
- `0x180014648`
- `0x1800146c4`
- `0x1800156c4`
- `0x18001594c`
- `0x18001c818`
- `0x18003af5c`
- `0x18003c240`
- `0x18003d010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18001c8b0`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18001c8bd`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18001ca70`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18001c8b0`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18001c8bd`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18001ca70`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall KspCreateClaimInternal(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        unsigned int a4,
        struct _BCryptBufferDesc *a5,
        unsigned __int8 *a6,
        unsigned int a7,
        unsigned int *a8,
        char a9)
{
  unsigned int v9; // esi
  __int64 v13; // rdi
  __int64 v14; // rcx
  __int64 v15; // rcx
  unsigned int Handle; // ebx
  __int64 v17; // rsi
  __int64 v18; // rcx
  _QWORD *v19; // rax
  int v20; // edx
  _BYTE *v21; // rcx
  __int64 v22; // rax
  int v23; // ecx
  __int64 v25; // rcx
  _QWORD *v26; // rax
  int v27; // edx
  __int64 v28; // rcx
  __int64 v29; // rsi
  unsigned __int16 *v30; // rax
  __int64 v31; // rcx
  int v32; // edx
  int v33; // r8d
  __int64 v34; // r9
  _QWORD *v35; // rax
  __int64 v36; // rdx
  __int64 v37; // rcx
  PBCryptBuffer pBuffers; // rcx
  __int64 v39; // rax
  __int64 v40; // rcx
  __int64 v41; // rcx
  unsigned int v42; // [rsp+30h] [rbp-99h] BYREF
  __int64 v43; // [rsp+38h] [rbp-91h] BYREF
  void **v44; // [rsp+40h] [rbp-89h] BYREF
  __int64 v45; // [rsp+48h] [rbp-81h]
  __int128 v46; // [rsp+50h] [rbp-79h] BYREF
  void *Src[2]; // [rsp+60h] [rbp-69h]
  size_t Size; // [rsp+70h] [rbp-59h]
  __int64 v49; // [rsp+78h] [rbp-51h] BYREF
  __int64 v50; // [rsp+80h] [rbp-49h] BYREF
  _QWORD v51[2]; // [rsp+88h] [rbp-41h] BYREF
  void *v52; // [rsp+98h] [rbp-31h]
  GUID ActivityId; // [rsp+A0h] [rbp-29h] BYREF
  GUID v54; // [rsp+B0h] [rbp-19h] BYREF

  v9 = a4;
  v42 = a4;
  v52 = a6;
  v49 = 0;
  v50 = 0;
  v13 = 0;
  v43 = 0;
  v46 = 0;
  *(_OWORD *)Src = 0;
  Size = 0;
  v44 = &Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::`vftable';
  v45 = 0;
  v51[0] = &Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::`vftable';
  v51[1] = 0;
  ActivityId = 0;
  v54 = 0;
  EventActivityIdControl(5u, &ActivityId);
  EventActivityIdControl(1u, &v54);
  if ( (unsigned int)dword_18004B100 > 5 && (unsigned __int8)tlgKeywordOn() )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      v14,
      byte_1800454C9,
      &v54,
      &ActivityId);
  if ( a8 && a3 && a2 && v9 == 2 )
  {
    Handle = HtGetHandle(a1, 3, &v49);
    if ( Handle )
    {
      WppTraceIndent(v15, 2u);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          476,
          (unsigned int)&WPP_0b747ea9e75c324d6ca3a604f9d495cb_Traceguids,
          (_DWORD)WPP_pszIndent,
          Handle);
      }
      goto LABEL_20;
    }
    v17 = v49;
    Handle = KspEnterCriticalSection(v49 + 16);
    if ( Handle )
    {
      WppTraceIndent(v18, 2u);
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_19;
      }
      v20 = 477;
      goto LABEL_18;
    }
    Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::Attach(v51, v17 + 16);
    Handle = HtGetHandle(a2, 2, &v43);
    if ( Handle )
    {
      WppTraceIndent(v25, 2u);
      v26 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_37;
      }
      v27 = 478;
LABEL_36:
      WPP_SF_sd(
        v26[2],
        v27,
        (unsigned int)&WPP_0b747ea9e75c324d6ca3a604f9d495cb_Traceguids,
        (_DWORD)WPP_pszIndent,
        Handle);
LABEL_37:
      v13 = v43;
      goto LABEL_19;
    }
    Handle = HtGetHandle(a3, 2, &v50);
    if ( Handle )
    {
      WppTraceIndent(v28, 2u);
      v26 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_37;
      }
      v27 = 479;
      goto LABEL_36;
    }
    v13 = v43;
    if ( *(_DWORD *)(v43 + 1048) && (v29 = v50, *(_DWORD *)(v50 + 1048)) )
    {
      if ( !*(_DWORD *)(v50 + 1056) || !*(_DWORD *)(v43 + 1056) )
      {
        WppTraceIndent(v28, 2u);
        v34 = 2148073511LL;
        Handle = -2146893785;
        v35 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_19;
        }
        v36 = 481;
        goto LABEL_55;
      }
      v30 = (unsigned __int16 *)(*(_QWORD *)(v43 + 1088) + 32LL);
      v31 = *(_QWORD *)(v50 + 1088) - *(_QWORD *)(v43 + 1088);
      do
      {
        v32 = *(unsigned __int16 *)((char *)v30 + v31);
        v33 = *v30 - v32;
        if ( v33 )
          break;
        ++v30;
      }
      while ( v32 );
      if ( v33 )
      {
        WppTraceIndent(v31, 2u);
        v34 = 2148073511LL;
        Handle = -2146893785;
        v35 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_19;
        }
        v36 = 482;
        goto LABEL_55;
      }
      Handle = KsppBeginCardCall(v43 + 1072);
      if ( Handle )
      {
        WppTraceIndent(v37, 2u);
        v19 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_19;
        }
        v20 = 483;
        goto LABEL_18;
      }
      Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::Attach(&v44, *(_QWORD *)(v13 + 1088) + 624LL);
      Handle = KsppAuthenticateUser(v13 + 1072, 1, 0, *(_DWORD *)(v13 + 1112) | a9 & 0x40u);
      if ( Handle )
      {
        WppTraceIndent((__int64)pBuffers, 2u);
        v19 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_19;
        }
        v20 = 484;
        goto LABEL_18;
      }
      LODWORD(v46) = 1;
      BYTE4(v46) = *(_BYTE *)(v29 + 1068);
      BYTE5(v46) = *(_BYTE *)(v13 + 1068);
      *((_QWORD *)&v46 + 1) = 0;
      LODWORD(Src[0]) = 0;
      if ( a5 )
      {
        if ( a5->ulVersion )
        {
          WppTraceIndent((__int64)pBuffers, 2u);
          v34 = 2148073511LL;
          Handle = -2146893785;
          v35 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_19;
          }
          v36 = 485;
          goto LABEL_55;
        }
        if ( a5->cBuffers > 1 )
        {
          WppTraceIndent((__int64)pBuffers, 2u);
          v34 = 2148073511LL;
          Handle = -2146893785;
          v35 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_19;
          }
          v36 = 486;
          goto LABEL_55;
        }
        if ( a5->cBuffers == 1 )
        {
          pBuffers = a5->pBuffers;
          if ( pBuffers->BufferType != 49 )
          {
            WppTraceIndent((__int64)pBuffers, 2u);
            v34 = 2148073511LL;
            Handle = -2146893785;
            v35 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            {
              goto LABEL_19;
            }
            v36 = 487;
            goto LABEL_55;
          }
          LODWORD(Src[0]) = pBuffers->cbBuffer;
          *((_QWORD *)&v46 + 1) = pBuffers->pvBuffer;
        }
      }
      v39 = *(_QWORD *)(*(_QWORD *)(v13 + 1088) + 8LL);
      if ( *(_DWORD *)(v39 + 512) )
      {
        Handle = (*(__int64 (__fastcall **)(_QWORD, __int128 *))(v39 + 528))(
                   *(_QWORD *)(*(_QWORD *)(v13 + 1088) + 8LL),
                   &v46);
        if ( Handle )
        {
          WppTraceIndent(v40, 2u);
          v19 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_19;
          }
          v20 = 489;
        }
        else
        {
          Handle = KsppCopyData(Src[1], (unsigned int)Size, v52, a7, a8);
          if ( !Handle )
            goto LABEL_19;
          WppTraceIndent(v41, 2u);
          v19 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_19;
          }
          v20 = 490;
        }
LABEL_18:
        WPP_SF_sd(
          v19[2],
          v20,
          (unsigned int)&WPP_0b747ea9e75c324d6ca3a604f9d495cb_Traceguids,
          (_DWORD)WPP_pszIndent,
          Handle);
LABEL_19:
        v9 = v42;
        goto LABEL_20;
      }
      WppTraceIndent((__int64)pBuffers, 2u);
      Handle = -2146893783;
      v35 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_19;
      }
      v36 = 488;
    }
    else
    {
      WppTraceIndent(v28, 2u);
      Handle = -2146893813;
      v35 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_19;
      }
      v36 = 480;
    }
    v34 = Handle;
LABEL_55:
    WPP_SF_d(v35[2], v36, &WPP_0b747ea9e75c324d6ca3a604f9d495cb_Traceguids, v34);
    goto LABEL_19;
  }
  WppTraceIndent(v14, 2u);
  Handle = -2146893785;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 475, &WPP_0b747ea9e75c324d6ca3a604f9d495cb_Traceguids, 2148073511LL);
  }
LABEL_20:
  v21 = Src[1];
  if ( Src[1] )
  {
    v22 = (unsigned int)Size;
    if ( (_DWORD)Size )
    {
      do
      {
        *v21++ = 0;
        --v22;
      }
      while ( v22 );
      v21 = Src[1];
    }
    CspFreeH(v21);
  }
  if ( v45 )
  {
    v45 = 0;
    KsppEndCardCall(v13 + 1072);
  }
  if ( (unsigned int)dword_18004B100 > 5 && (unsigned __int8)tlgKeywordOn() )
  {
    v42 = Handle;
    LODWORD(v43) = v9;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      v23,
      (unsigned int)byte_180045599,
      (unsigned int)&v54,
      (unsigned int)&ActivityId,
      (__int64)&v43,
      (__int64)&v42);
  }
  EventActivityIdControl(2u, &ActivityId);
  v51[0] = &Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::`vftable';
  Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::Close(v51);
  v44 = &Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::`vftable';
  Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::Close(&v44);
  return Handle;
}

```

## disassembly

```asm
0x18001c818  mov     [rsp-8+arg_18], rbx
0x18001c81d  push    rbp
0x18001c81e  push    rsi
0x18001c81f  push    rdi
0x18001c820  push    r12
0x18001c822  push    r13
0x18001c824  push    r14
0x18001c826  push    r15
0x18001c828  lea     rbp, [rsp-7]
0x18001c82d  sub     rsp, 0D0h
0x18001c834  mov     rax, cs:__security_cookie
0x18001c83b  xor     rax, rsp
0x18001c83e  mov     [rbp+37h+var_40], rax
0x18001c842  mov     esi, r9d
0x18001c845  mov     [rsp+100h+var_D0], r9d
0x18001c84a  mov     r14, r8
0x18001c84d  mov     r12, rdx
0x18001c850  mov     rbx, rcx
0x18001c853  mov     r15, [rbp+37h+arg_20]
0x18001c857  mov     rax, [rbp+37h+arg_28]
0x18001c85b  mov     [rbp+37h+var_68], rax
0x18001c85f  mov     r13, [rbp+37h+arg_38]
0x18001c863  xor     ecx, ecx
0x18001c865  mov     [rbp+37h+var_88], rcx
0x18001c869  mov     [rbp+37h+var_80], rcx
0x18001c86d  mov     edi, ecx
0x18001c86f  mov     [rsp+100h+var_C8], rcx
0x18001c874  xorps   xmm0, xmm0
0x18001c877  xor     eax, eax
0x18001c879  movups  [rbp+37h+var_B0], xmm0
0x18001c87d  movups  xmmword ptr [rbp+37h+Src], xmm0
0x18001c881  mov     [rbp+37h+Size], rax
0x18001c885  lea     rax, ??_7?$HandleT@UCriticalSectionTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::`vftable'
0x18001c88c  mov     [rsp+100h+var_C0], rax
0x18001c891  mov     [rsp+100h+var_B8], rcx
0x18001c896  mov     [rbp+37h+var_78], rax
0x18001c89a  mov     [rbp+37h+var_70], rcx
0x18001c89e  movups  xmmword ptr [rbp+37h+ActivityId.Data1], xmm0
0x18001c8a2  xorps   xmm1, xmm1
0x18001c8a5  movups  xmmword ptr [rbp+37h+var_50.Data1], xmm1
0x18001c8a9  lea     rdx, [rbp+37h+ActivityId]; ActivityId
0x18001c8ad  lea     ecx, [rdi+5]; ControlCode
0x18001c8b0  call    cs:__imp_EventActivityIdControl
0x18001c8b6  lea     rdx, [rbp+37h+var_50]; ActivityId
0x18001c8ba  lea     ecx, [rdi+1]; ControlCode
0x18001c8bd  call    cs:__imp_EventActivityIdControl
0x18001c8c3  mov     eax, cs:dword_18004B100
0x18001c8c9  cmp     eax, 5
0x18001c8cc  jbe     short loc_18001C8EB
0x18001c8ce  call    _tlgKeywordOn
0x18001c8d3  test    al, al
0x18001c8d5  jz      short loc_18001C8EB
0x18001c8d7  lea     r9, [rbp+37h+ActivityId]
0x18001c8db  lea     r8, [rbp+37h+var_50]
0x18001c8df  lea     rdx, byte_1800454C9
0x18001c8e6  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x18001c8eb  test    r13, r13
0x18001c8ee  jz      loc_18001CFCC
0x18001c8f4  test    r14, r14
0x18001c8f7  jz      loc_18001CFCC
0x18001c8fd  test    r12, r12
0x18001c900  jz      loc_18001CFCC
0x18001c906  cmp     esi, 2
0x18001c909  jnz     loc_18001CFCC
0x18001c90f  lea     r8, [rbp+37h+var_88]
0x18001c913  lea     edx, [rsi+1]
0x18001c916  mov     rcx, rbx
0x18001c919  call    HtGetHandle
0x18001c91e  mov     ebx, eax
0x18001c920  test    eax, eax
0x18001c922  jz      short loc_18001C97C
0x18001c924  mov     r12d, esi
0x18001c927  mov     edx, r12d
0x18001c92a  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18001c92f  lea     rcx, WPP_GLOBAL_Control
0x18001c936  mov     rax, cs:WPP_GLOBAL_Control
0x18001c93d  cmp     rax, rcx
0x18001c940  jz      loc_18001C9E4
0x18001c946  test    byte ptr [rax+1Ch], 1
0x18001c94a  jz      loc_18001C9E4
0x18001c950  cmp     [rax+19h], r12b
0x18001c954  jb      loc_18001C9E4
0x18001c95a  mov     edx, 1DCh
0x18001c95f  mov     dword ptr [rsp+100h+var_E0], ebx
0x18001c963  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x18001c96a  lea     r8, WPP_0b747ea9e75c324d6ca3a604f9d495cb_Traceguids
0x18001c971  mov     rcx, [rax+10h]
0x18001c975  call    WPP_SF_sd
0x18001c97a  jmp     short loc_18001C9E4
0x18001c97c  mov     rsi, [rbp+37h+var_88]
0x18001c980  lea     rcx, [rsi+10h]
0x18001c984  call    KspEnterCriticalSection
0x18001c989  mov     ebx, eax
0x18001c98b  test    eax, eax
0x18001c98d  jz      loc_18001CAC4
0x18001c993  mov     r12d, 2
0x18001c999  mov     edx, r12d
0x18001c99c  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18001c9a1  lea     rcx, WPP_GLOBAL_Control
0x18001c9a8  mov     rax, cs:WPP_GLOBAL_Control
0x18001c9af  cmp     rax, rcx
0x18001c9b2  jz      short loc_18001C9E0
0x18001c9b4  test    byte ptr [rax+1Ch], 1
0x18001c9b8  jz      short loc_18001C9E0
0x18001c9ba  cmp     [rax+19h], r12b
0x18001c9be  jb      short loc_18001C9E0
0x18001c9c0  mov     edx, 1DDh
0x18001c9c5  mov     dword ptr [rsp+100h+var_E0], ebx
0x18001c9c9  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x18001c9d0  lea     r8, WPP_0b747ea9e75c324d6ca3a604f9d495cb_Traceguids
0x18001c9d7  mov     rcx, [rax+10h]
0x18001c9db  call    WPP_SF_sd
0x18001c9e0  mov     esi, [rsp+100h+var_D0]
0x18001c9e4  mov     rcx, [rbp+37h+Src+8]
0x18001c9e8  xor     r15d, r15d
0x18001c9eb  test    rcx, rcx
0x18001c9ee  jz      short loc_18001CA0D
0x18001c9f0  mov     eax, dword ptr [rbp+37h+Size]
0x18001c9f3  test    rax, rax
0x18001c9f6  jz      short loc_18001CA08
0x18001c9f8  mov     [rcx], r15b
0x18001c9fb  inc     rcx
0x18001c9fe  sub     rax, 1
0x18001ca02  jnz     short loc_18001C9F8
0x18001ca04  mov     rcx, [rbp+37h+Src+8]
0x18001ca08  call    CspFreeH
0x18001ca0d  cmp     [rsp+100h+var_B8], r15
0x18001ca12  jz      short loc_18001CA25
0x18001ca14  mov     [rsp+100h+var_B8], r15
0x18001ca19  lea     rcx, [rdi+430h]
0x18001ca20  call    KsppEndCardCall
0x18001ca25  mov     eax, cs:dword_18004B100
0x18001ca2b  cmp     eax, 5
0x18001ca2e  jbe     short loc_18001CA69
0x18001ca30  call    _tlgKeywordOn
0x18001ca35  test    al, al
0x18001ca37  jz      short loc_18001CA69
0x18001ca39  mov     [rsp+100h+var_D0], ebx
0x18001ca3d  mov     dword ptr [rsp+100h+var_C8], esi
0x18001ca41  lea     rax, [rsp+100h+var_D0]
0x18001ca46  mov     [rsp+100h+var_D8], rax
0x18001ca4b  lea     rax, [rsp+100h+var_C8]
0x18001ca50  mov     [rsp+100h+var_E0], rax
0x18001ca55  lea     r9, [rbp+37h+ActivityId]
0x18001ca59  lea     r8, [rbp+37h+var_50]
0x18001ca5d  lea     rdx, byte_180045599
0x18001ca64  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18001ca69  lea     rdx, [rbp+37h+ActivityId]; ActivityId
0x18001ca6d  mov     ecx, r12d; ControlCode
0x18001ca70  call    cs:__imp_EventActivityIdControl
0x18001ca76  nop
0x18001ca77  lea     rdi, ??_7?$HandleT@UCriticalSectionTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::`vftable'
0x18001ca7e  mov     [rbp+37h+var_78], rdi
0x18001ca82  lea     rcx, [rbp+37h+var_78]
0x18001ca86  call    ?Close@?$HandleT@UCriticalSectionTraits@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::Close(void)
0x18001ca8b  nop
0x18001ca8c  mov     [rsp+100h+var_C0], rdi
0x18001ca91  lea     rcx, [rsp+100h+var_C0]
0x18001ca96  call    ?Close@?$HandleT@UCriticalSectionTraits@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::Close(void)
0x18001ca9b  mov     eax, ebx
0x18001ca9d  mov     rcx, [rbp+37h+var_40]
0x18001caa1  xor     rcx, rsp; StackCookie
0x18001caa4  call    __security_check_cookie
0x18001caa9  mov     rbx, [rsp+100h+arg_18]
0x18001cab1  add     rsp, 0D0h
0x18001cab8  pop     r15
0x18001caba  pop     r14
0x18001cabc  pop     r13
0x18001cabe  pop     r12
0x18001cac0  pop     rdi
0x18001cac1  pop     rsi
0x18001cac2  pop     rbp
0x18001cac3  retn
0x18001cac4  lea     rdx, [rsi+10h]
0x18001cac8  lea     rcx, [rbp+37h+var_78]
0x18001cacc  call    ?Attach@?$HandleT@UCriticalSectionTraits@@@Wrappers@WRL@Microsoft@@QEAAXPEAU_RTL_CRITICAL_SECTION@@@Z; Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::Attach(_RTL_CRITICAL_SECTION *)
0x18001cad1  lea     r8, [rsp+100h+var_C8]
0x18001cad6  mov     edx, 2
0x18001cadb  mov     rcx, r12
0x18001cade  call    HtGetHandle
0x18001cae3  mov     ebx, eax
0x18001cae5  mov     r12d, 2
0x18001caeb  mov     edx, r12d
0x18001caee  test    eax, eax
0x18001caf0  jz      short loc_18001CB40
0x18001caf2  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18001caf7  lea     rcx, WPP_GLOBAL_Control
0x18001cafe  mov     rax, cs:WPP_GLOBAL_Control
0x18001cb05  cmp     rax, rcx
0x18001cb08  jz      short loc_18001CB36
0x18001cb0a  test    byte ptr [rax+1Ch], 1
0x18001cb0e  jz      short loc_18001CB36
0x18001cb10  cmp     [rax+19h], r12b
0x18001cb14  jb      short loc_18001CB36
0x18001cb16  mov     edx, 1DEh
0x18001cb1b  mov     dword ptr [rsp+100h+var_E0], ebx
0x18001cb1f  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x18001cb26  lea     r8, WPP_0b747ea9e75c324d6ca3a604f9d495cb_Traceguids
0x18001cb2d  mov     rcx, [rax+10h]
0x18001cb31  call    WPP_SF_sd
0x18001cb36  mov     rdi, [rsp+100h+var_C8]
0x18001cb3b  jmp     loc_18001C9E0
0x18001cb40  lea     r8, [rbp+37h+var_80]
0x18001cb44  mov     rcx, r14
0x18001cb47  call    HtGetHandle
0x18001cb4c  mov     ebx, eax
0x18001cb4e  xor     r9d, r9d
0x18001cb51  test    eax, eax
0x18001cb53  jz      short loc_18001CB83
0x18001cb55  mov     edx, r12d
0x18001cb58  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18001cb5d  lea     rcx, WPP_GLOBAL_Control
0x18001cb64  mov     rax, cs:WPP_GLOBAL_Control
0x18001cb6b  cmp     rax, rcx
0x18001cb6e  jz      short loc_18001CB36
0x18001cb70  test    byte ptr [rax+1Ch], 1
0x18001cb74  jz      short loc_18001CB36
0x18001cb76  cmp     [rax+19h], r12b
0x18001cb7a  jb      short loc_18001CB36
0x18001cb7c  mov     edx, 1DFh
0x18001cb81  jmp     short loc_18001CB1B
0x18001cb83  mov     rdi, [rsp+100h+var_C8]
0x18001cb88  cmp     [rdi+418h], r9d
0x18001cb8f  jz      loc_18001CF8A
0x18001cb95  mov     rsi, [rbp+37h+var_80]
0x18001cb99  cmp     [rsi+418h], r9d
0x18001cba0  jz      loc_18001CF8A
0x18001cba6  cmp     [rsi+420h], r9d
0x18001cbad  jz      loc_18001CF44
0x18001cbb3  cmp     [rdi+420h], r9d
0x18001cbba  jz      loc_18001CF44
0x18001cbc0  lea     r14, [rdi+430h]
0x18001cbc7  mov     rcx, [rsi+440h]
0x18001cbce  add     rcx, 20h ; ' '
0x18001cbd2  mov     rax, [r14+10h]
0x18001cbd6  add     rax, 20h ; ' '
0x18001cbda  sub     rcx, rax
0x18001cbdd  movzx   r8d, word ptr [rax]
0x18001cbe1  movzx   edx, word ptr [rax+rcx]
0x18001cbe5  sub     r8d, edx
0x18001cbe8  jnz     short loc_18001CBF1
0x18001cbea  add     rax, r12
0x18001cbed  test    edx, edx
0x18001cbef  jnz     short loc_18001CBDD
0x18001cbf1  test    r8d, r8d
0x18001cbf4  jz      short loc_18001CC4C
0x18001cbf6  mov     edx, r12d
0x18001cbf9  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18001cbfe  mov     r9d, 80090027h
0x18001cc04  mov     ebx, r9d
0x18001cc07  lea     rcx, WPP_GLOBAL_Control
0x18001cc0e  mov     rax, cs:WPP_GLOBAL_Control
0x18001cc15  cmp     rax, rcx
0x18001cc18  jz      loc_18001C9E0
0x18001cc1e  test    byte ptr [rax+1Ch], 1
0x18001cc22  jz      loc_18001C9E0
0x18001cc28  cmp     [rax+19h], r12b
0x18001cc2c  jb      loc_18001C9E0
0x18001cc32  mov     edx, 1E2h
0x18001cc37  lea     r8, WPP_0b747ea9e75c324d6ca3a604f9d495cb_Traceguids
0x18001cc3e  mov     rcx, [rax+10h]
0x18001cc42  call    WPP_SF_d
0x18001cc47  jmp     loc_18001C9E0
0x18001cc4c  mov     rcx, r14
0x18001cc4f  call    KsppBeginCardCall
0x18001cc54  mov     ebx, eax
0x18001cc56  test    eax, eax
0x18001cc58  jz      short loc_18001CC97
0x18001cc5a  mov     edx, r12d
0x18001cc5d  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18001cc62  lea     rcx, WPP_GLOBAL_Control
0x18001cc69  mov     rax, cs:WPP_GLOBAL_Control
0x18001cc70  cmp     rax, rcx
0x18001cc73  jz      loc_18001C9E0
0x18001cc79  test    byte ptr [rax+1Ch], 1
0x18001cc7d  jz      loc_18001C9E0
0x18001cc83  cmp     [rax+19h], r12b
0x18001cc87  jb      loc_18001C9E0
0x18001cc8d  mov     edx, 1E3h
0x18001cc92  jmp     loc_18001C9C5
0x18001cc97  mov     rdx, [rdi+440h]
0x18001cc9e  add     rdx, 270h
0x18001cca5  lea     rcx, [rsp+100h+var_C0]
0x18001ccaa  call    ?Attach@?$HandleT@UCriticalSectionTraits@@@Wrappers@WRL@Microsoft@@QEAAXPEAU_RTL_CRITICAL_SECTION@@@Z; Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::Attach(_RTL_CRITICAL_SECTION *)
0x18001ccaf  mov     r9d, [rbp+37h+arg_40]
0x18001ccb6  and     r9d, 40h
0x18001ccba  or      r9d, [rdi+458h]
0x18001ccc1  xor     r8d, r8d
0x18001ccc4  lea     edx, [r8+1]
0x18001ccc8  mov     rcx, r14
0x18001cccb  call    KsppAuthenticateUser
0x18001ccd0  mov     ebx, eax
0x18001ccd2  test    eax, eax
0x18001ccd4  jz      short loc_18001CD13
0x18001ccd6  mov     edx, r12d
0x18001ccd9  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18001ccde  lea     rcx, WPP_GLOBAL_Control
0x18001cce5  mov     rax, cs:WPP_GLOBAL_Control
0x18001ccec  cmp     rax, rcx
0x18001ccef  jz      loc_18001C9E0
  ... truncated ...
```
