# ScExtpRegisterTriggers(_SERVICE_TRIGGER_REGISTRATION *,ulong,int,_SERVICE_TRIGGER_CONTEXT *)

- ea: `0x14000f87c`
- end: `0x14000fe2c`
- name: `?ScExtpRegisterTriggers@@YAKPEAU_SERVICE_TRIGGER_REGISTRATION@@KHPEAU_SERVICE_TRIGGER_CONTEXT@@@Z`
- size: `1456`
- prototype: `unsigned int __fastcall(struct _SERVICE_TRIGGER_REGISTRATION *, unsigned int, int, struct _SERVICE_TRIGGER_CONTEXT *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x14000e290`

## callees

- `0x140001eec`
- `0x140003e54`
- `0x14000f87c`
- `0x14000fe9c`
- `0x140038698`
- `0x1400575b0`
- `0x140064a90`

## import_xrefs

- `RPCRT4!UuidCreate` at `0x14000fae5`
- `RPCRT4!UuidCreate` at `0x14000fae5`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x14000f915`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x14000f915`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14000fdfd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14000fdfd`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14000f993`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14000f993`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000fa66`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000fdd5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000fa66`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000fdd5`
- `EventAggregation!EaFreeAggregatedEventParameters` at `0x14000fa52`
- `EventAggregation!EaFreeAggregatedEventParameters` at `0x14000fde5`
- `EventAggregation!EaFreeAggregatedEventParameters` at `0x14000fa52`
- `EventAggregation!EaFreeAggregatedEventParameters` at `0x14000fde5`
- `EventAggregation!EaQueryAggregatedEventParameters` at `0x14000f9b0`
- `EventAggregation!EaQueryAggregatedEventParameters` at `0x14000f9b0`
- `EventAggregation!EACreateAggregateEvent` at `0x14000fba8`
- `EventAggregation!EACreateAggregateEvent` at `0x14000fba8`
- `EventAggregation!BriCreateBrokeredEvent` at `0x14000fabc`
- `EventAggregation!BriCreateBrokeredEvent` at `0x14000fabc`
- `EventAggregation!EaCreateAggregatedEvent` at `0x14000fa23`
- `EventAggregation!EaCreateAggregatedEvent` at `0x14000fa23`
- `DABAPI!DabRegisterTriggerConsumer` at `0x14000fb3a`
- `DABAPI!DabRegisterTriggerConsumer` at `0x14000fb3a`

## string_xrefs

- `0x14000f98c`: `System\CurrentControlSet\Control\ServiceAggregatedEvents`

## pseudocode

```c
__int64 __fastcall ScExtpRegisterTriggers(
        struct _SERVICE_TRIGGER_REGISTRATION *a1,
        unsigned int a2,
        int a3,
        struct _SERVICE_TRIGGER_CONTEXT *a4)
{
  unsigned int AggregatedEvent; // ebx
  unsigned __int16 v6; // r13
  int v8; // r12d
  _DWORD *v9; // rax
  _DWORD *v10; // rdi
  __int64 v11; // r14
  int v12; // ecx
  int v13; // ecx
  int v14; // ecx
  __int64 *v15; // r12
  __int64 v16; // r8
  int v17; // eax
  struct _SERVICE_TRIGGER_CONTEXT **v18; // rcx
  PRPC_ASYNC_STATE v19; // rcx
  int v20; // edx
  __int64 v21; // rcx
  __int64 v22; // r8
  __int64 v23; // r9
  PHKEY phkResult; // [rsp+20h] [rbp-E0h]
  __int64 v26; // [rsp+38h] [rbp-C8h]
  __int64 v27; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v28; // [rsp+58h] [rbp-A8h]
  __int64 v29; // [rsp+60h] [rbp-A0h]
  HKEY hKey; // [rsp+68h] [rbp-98h] BYREF
  __int64 v31; // [rsp+70h] [rbp-90h] BYREF
  __int128 v32; // [rsp+78h] [rbp-88h] BYREF
  __int128 v33; // [rsp+88h] [rbp-78h]
  __int128 v34; // [rsp+98h] [rbp-68h]
  __int64 v35; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v36; // [rsp+B0h] [rbp-50h] BYREF
  _OWORD v37[2]; // [rsp+B8h] [rbp-48h] BYREF
  __int128 v38; // [rsp+D8h] [rbp-28h]
  struct _SERVICE_TRIGGER_CONTEXT *v39; // [rsp+E8h] [rbp-18h]
  __int64 v40; // [rsp+F0h] [rbp-10h] BYREF
  UUID Uuid; // [rsp+F8h] [rbp-8h] BYREF
  _OWORD v42[2]; // [rsp+108h] [rbp+8h] BYREF

  LODWORD(v29) = a3;
  v28 = a2;
  AggregatedEvent = 0;
  v40 = 0;
  v6 = 0;
  v31 = 0;
  v39 = 0;
  hKey = 0;
  v8 = a3;
  v27 = 0;
  Uuid = 0;
  memset(v42, 0, sizeof(v42));
  v32 = 0;
  v33 = 0;
  v34 = 0;
  memset(v37, 0, sizeof(v37));
  v38 = 0;
  if ( !a2 )
  {
    v10 = 0;
    goto LABEL_53;
  }
  while ( 1 )
  {
    v9 = LocalAlloc(0x40u, 0x48u);
    v10 = v9;
    if ( !v9 )
    {
      AggregatedEvent = 14;
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control || (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) == 0 )
        goto LABEL_53;
      v20 = 48;
      goto LABEL_51;
    }
    v11 = 104LL * v6;
    v9[4] = *(_DWORD *)((char *)a1 + v11 + 4);
    v9[8] = *(_DWORD *)((char *)a1 + v11);
    v9[16] = *(_DWORD *)((char *)a1 + v11 + 96);
    v12 = *(_DWORD *)((char *)a1 + v11);
    v32 = 0;
    v33 = 0;
    v34 = 0;
    v13 = v12 - 1;
    if ( !v13 )
      break;
    v14 = v13 - 1;
    if ( !v14 )
    {
      LODWORD(phkResult) = v29 != 0;
      AggregatedEvent = BriCreateBrokeredEvent(
                          (char *)a1 + v11 + 24,
                          *(_QWORD *)((char *)a1 + v11 + 8),
                          *(_QWORD *)((char *)a1 + v11 + 16),
                          (char *)a1 + v11 + 40,
                          phkResult,
                          0,
                          &v40,
                          v42);
      if ( !AggregatedEvent )
      {
        *(_OWORD *)(v10 + 10) = *(_OWORD *)((char *)a1 + v11 + 24);
        *((_QWORD *)v10 + 7) = v40;
LABEL_17:
        v8 = v29;
        goto LABEL_18;
      }
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control || (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) == 0 )
        goto LABEL_53;
      v20 = 51;
LABEL_51:
      WPP_SF_Sd(
        v19->StubInfo,
        v20,
        (unsigned int)WPP_33ca3c9d568834eb2422a5f850c17021_Traceguids,
        *((_QWORD *)a4 + 3),
        AggregatedEvent);
      goto LABEL_53;
    }
    if ( v14 != 1 )
    {
      AggregatedEvent = 50;
      goto LABEL_53;
    }
    if ( !RegOpenKeyExW(
            HKEY_LOCAL_MACHINE,
            L"System\\CurrentControlSet\\Control\\ServiceAggregatedEvents",
            0,
            1u,
            &hKey) )
    {
      AggregatedEvent = EaQueryAggregatedEventParameters(hKey, *(_QWORD *)((char *)a1 + v11 + 24), &v27);
      if ( AggregatedEvent )
      {
        v19 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
          || (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) == 0 )
        {
          goto LABEL_53;
        }
        v20 = 52;
        goto LABEL_51;
      }
      *(_QWORD *)(v27 + 56) = *(_QWORD *)((char *)a1 + v11 + 8);
      *(_QWORD *)(v27 + 64) = *(_QWORD *)((char *)a1 + v11 + 16);
      LODWORD(v26) = v8 == 0 ? 2 : 0;
      AggregatedEvent = EaCreateAggregatedEvent(v27, v8 != 0, &ScExtpAggregateTriggerArrived, 0, 0, 0, a4, v26, v10 + 6);
      *(_QWORD *)(v27 + 56) = 0;
      *(_QWORD *)(v27 + 64) = 0;
      if ( AggregatedEvent )
      {
        v19 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
          || (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) == 0 )
        {
          goto LABEL_53;
        }
        v20 = 53;
        goto LABEL_51;
      }
      EaFreeAggregatedEventParameters(v27);
      v27 = 0;
      RegCloseKey(hKey);
      hKey = 0;
    }
LABEL_18:
    if ( *(_DWORD *)((char *)a1 + v11) != 3 )
    {
      *(_QWORD *)&v37[0] = v40;
      *(_QWORD *)&v38 = &ScExtpTriggerArrived;
      v17 = _mm_cvtsi128_si32((__m128i)0LL);
      memset((char *)v37 + 8, 0, 24);
      *((_QWORD *)&v38 + 1) = 0;
      if ( !v8 )
        v17 = 2;
      v39 = a4;
      DWORD2(v37[0]) = v17;
      AggregatedEvent = EACreateAggregateEvent(v37, v10 + 6);
      if ( AggregatedEvent )
      {
        v19 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
          || (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) == 0 )
        {
          goto LABEL_53;
        }
        v20 = 54;
        goto LABEL_51;
      }
    }
    v18 = (struct _SERVICE_TRIGGER_CONTEXT **)*((_QWORD *)a4 + 5);
    if ( *v18 != (struct _SERVICE_TRIGGER_CONTEXT *)((char *)a4 + 32) )
      __fastfail(3u);
    *(_QWORD *)v10 = (char *)a4 + 32;
    *((_QWORD *)v10 + 1) = v18;
    *v18 = (struct _SERVICE_TRIGGER_CONTEXT *)v10;
    *((_QWORD *)a4 + 5) = v10;
    v10 = 0;
    if ( ++v6 >= v28 )
      goto LABEL_53;
  }
  AggregatedEvent = UuidCreate(&Uuid);
  if ( AggregatedEvent )
  {
    v19 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control || (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) == 0 )
      goto LABEL_53;
    v20 = 49;
    goto LABEL_51;
  }
  *(_QWORD *)&v32 = &Uuid;
  v15 = (__int64 *)((char *)a1 + v11 + 24);
  *((_QWORD *)&v32 + 1) = *((_QWORD *)a4 + 3);
  DWORD1(v34) = 1;
  *((_QWORD *)&v34 + 1) = v15;
  if ( (_DWORD)v29 )
    LODWORD(v33) = v33 | 1;
  AggregatedEvent = DabRegisterTriggerConsumer(0xFFFF, 1, &v32, &v40, &v31);
  if ( !AggregatedEvent )
  {
    *((_QWORD *)v10 + 5) = v31;
    goto LABEL_17;
  }
  if ( (unsigned int)dword_1400BA2A0 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1400BA2A0, 0x200000000000LL, v16) )
  {
    v35 = *v15;
    v36 = *((_QWORD *)a4 + 3);
    v29 = 0x1000000;
    v28 = AggregatedEvent;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
      v21,
      (__int64)&word_1400AF8FE,
      v22,
      v23,
      &v36,
      &v35);
  }
  if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
    WPP_SF_SSD(
      WPP_GLOBAL_Control->StubInfo,
      50,
      (unsigned int)WPP_33ca3c9d568834eb2422a5f850c17021_Traceguids,
      *v15,
      *((_QWORD *)a4 + 3),
      AggregatedEvent);
LABEL_53:
  if ( hKey )
    RegCloseKey(hKey);
  if ( v27 )
    EaFreeAggregatedEventParameters(v27);
  if ( v10 )
  {
    ScExtpUnregisterTrigger((struct _SERVICE_TRIGGER_SUBSCRIPTION *)v10, 0);
    LocalFree(v10);
  }
  return AggregatedEvent;
}

```

## disassembly

```asm
0x14000f87c  mov     [rsp-8+arg_8], rbx
0x14000f881  push    rbp
0x14000f882  push    rsi
0x14000f883  push    rdi
0x14000f884  push    r12
0x14000f886  push    r13
0x14000f888  push    r14
0x14000f88a  push    r15
0x14000f88c  lea     rbp, [rsp-30h]
0x14000f891  sub     rsp, 130h
0x14000f898  mov     rax, cs:__security_cookie
0x14000f89f  xor     rax, rsp
0x14000f8a2  mov     [rbp+60h+var_38], rax
0x14000f8a6  xorps   xmm1, xmm1
0x14000f8a9  mov     dword ptr [rsp+160h+var_100], r8d
0x14000f8ae  xorps   xmm0, xmm0
0x14000f8b1  mov     [rsp+160h+var_108], edx
0x14000f8b5  xor     ebx, ebx
0x14000f8b7  mov     r15, rcx
0x14000f8ba  xor     ecx, ecx
0x14000f8bc  mov     [rbp+60h+var_70], rbx
0x14000f8c0  xor     r13d, r13d
0x14000f8c3  mov     [rsp+160h+var_F0], rbx
0x14000f8c8  mov     [rbp+60h+var_78], rcx
0x14000f8cc  mov     rsi, r9
0x14000f8cf  mov     [rsp+160h+hKey], rcx
0x14000f8d4  mov     r12d, r8d
0x14000f8d7  mov     [rsp+160h+var_110], rcx
0x14000f8dc  movups  xmmword ptr [rbp+60h+Uuid.Data1], xmm0
0x14000f8e0  movups  [rbp+60h+var_58], xmm1
0x14000f8e4  movups  [rbp+60h+var_48], xmm1
0x14000f8e8  movups  [rsp+160h+var_E8], xmm0
0x14000f8ed  movups  [rbp+60h+var_D8], xmm0
0x14000f8f1  movups  [rbp+60h+var_C8], xmm0
0x14000f8f5  movups  [rbp+60h+var_A8], xmm1
0x14000f8f9  movups  [rbp+60h+var_98], xmm1
0x14000f8fd  movups  [rbp+60h+var_88], xmm1
0x14000f901  test    edx, edx
0x14000f903  jz      loc_14000FDC9
0x14000f909  lea     r14d, [rbx+1]
0x14000f90d  mov     edx, 48h ; 'H'; uBytes
0x14000f912  lea     ecx, [rdx-8]; uFlags
0x14000f915  call    cs:__imp_LocalAlloc
0x14000f91b  mov     rdi, rax
0x14000f91e  test    rax, rax
0x14000f921  jz      loc_14000FD8E
0x14000f927  xorps   xmm0, xmm0
0x14000f92a  movzx   eax, r13w
0x14000f92e  imul    r14, rax, 68h ; 'h'
0x14000f932  mov     eax, [r14+r15+4]
0x14000f937  mov     [rdi+10h], eax
0x14000f93a  mov     eax, [r14+r15]
0x14000f93e  mov     [rdi+20h], eax
0x14000f941  mov     eax, [r14+r15+60h]
0x14000f946  mov     [rdi+40h], eax
0x14000f949  mov     ecx, [r14+r15]
0x14000f94d  movups  [rsp+160h+var_E8], xmm0
0x14000f952  movups  [rbp+60h+var_D8], xmm0
0x14000f956  movups  [rbp+60h+var_C8], xmm0
0x14000f95a  sub     ecx, 1
0x14000f95d  jz      loc_14000FAE1
0x14000f963  sub     ecx, 1
0x14000f966  jz      loc_14000FA7A
0x14000f96c  cmp     ecx, 1
0x14000f96f  jnz     loc_14000FC4A
0x14000f975  lea     rax, [rsp+160h+hKey]
0x14000f97a  mov     r9d, ecx; samDesired
0x14000f97d  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14000f984  mov     [rsp+160h+phkResult], rax; phkResult
0x14000f989  xor     r8d, r8d; ulOptions
0x14000f98c  lea     rdx, SubKey; "System\\CurrentControlSet\\Control\\Ser"...
0x14000f993  call    cs:__imp_RegOpenKeyExW
0x14000f999  test    eax, eax
0x14000f99b  jnz     loc_14000FB58
0x14000f9a1  mov     rdx, [r14+r15+18h]
0x14000f9a6  lea     r8, [rsp+160h+var_110]
0x14000f9ab  mov     rcx, [rsp+160h+hKey]
0x14000f9b0  call    cs:__imp_EaQueryAggregatedEventParameters
0x14000f9b6  mov     ebx, eax
0x14000f9b8  test    eax, eax
0x14000f9ba  jnz     loc_14000FC1F
0x14000f9c0  mov     rax, [rsp+160h+var_110]
0x14000f9c5  lea     r8, [rdi+18h]
0x14000f9c9  mov     rcx, [r14+r15+8]
0x14000f9ce  mov     [rsp+160h+var_120], r8
0x14000f9d3  lea     r8, ?ScExtpAggregateTriggerArrived@@YAXPEAXU_CBROKERED_EVENT_ID@@00KKPEAW4_BI_ACTIVATION_STATUS@@@Z; ScExtpAggregateTriggerArrived(void *,_CBROKERED_EVENT_ID,void *,void *,ulong,ulong,_BI_ACTIVATION_STATUS *)
0x14000f9da  mov     [rax+38h], rcx
0x14000f9de  mov     rcx, [r14+r15+10h]
0x14000f9e3  mov     rax, [rsp+160h+var_110]
0x14000f9e8  mov     [rax+40h], rcx
0x14000f9ec  mov     eax, r12d
0x14000f9ef  neg     eax
0x14000f9f1  sbb     ecx, ecx
0x14000f9f3  xor     edx, edx
0x14000f9f5  not     ecx
0x14000f9f7  and     ecx, 2
0x14000f9fa  mov     dword ptr [rsp+160h+var_128], ecx
0x14000f9fe  test    r12d, r12d
0x14000fa01  mov     rcx, [rsp+160h+var_110]
0x14000fa06  setnz   dl
0x14000fa09  mov     [rsp+160h+var_130], rsi
0x14000fa0e  xor     r9d, r9d
0x14000fa11  mov     [rsp+160h+var_138], 0
0x14000fa1a  mov     [rsp+160h+phkResult], 0
0x14000fa23  call    cs:__imp_EaCreateAggregatedEvent
0x14000fa29  mov     ebx, eax
0x14000fa2b  mov     rax, [rsp+160h+var_110]
0x14000fa30  mov     qword ptr [rax+38h], 0
0x14000fa38  mov     rax, [rsp+160h+var_110]
0x14000fa3d  mov     qword ptr [rax+40h], 0
0x14000fa45  test    ebx, ebx
0x14000fa47  jnz     loc_14000FBF4
0x14000fa4d  mov     rcx, [rsp+160h+var_110]
0x14000fa52  call    cs:__imp_EaFreeAggregatedEventParameters
0x14000fa58  mov     rcx, [rsp+160h+hKey]; hKey
0x14000fa5d  mov     [rsp+160h+var_110], 0
0x14000fa66  call    cs:__imp_RegCloseKey
0x14000fa6c  mov     [rsp+160h+hKey], 0
0x14000fa75  jmp     loc_14000FB58
0x14000fa7a  mov     r8, [r14+r15+10h]
0x14000fa7f  lea     rcx, [rbp+60h+var_58]
0x14000fa83  mov     rdx, [r14+r15+8]
0x14000fa88  lea     r12, [r14+r15]
0x14000fa8c  mov     [rsp+160h+var_128], rcx
0x14000fa91  lea     r9, [r15+28h]
0x14000fa95  xor     eax, eax
0x14000fa97  lea     rcx, [rbp+60h+var_70]
0x14000fa9b  cmp     dword ptr [rsp+160h+var_100], eax
0x14000fa9f  mov     [rsp+160h+var_130], rcx
0x14000faa4  lea     rcx, [r12+18h]
0x14000faa9  setnz   al
0x14000faac  mov     [rsp+160h+var_138], 0
0x14000fab5  add     r9, r14
0x14000fab8  mov     dword ptr [rsp+160h+phkResult], eax
0x14000fabc  call    cs:__imp_BriCreateBrokeredEvent
0x14000fac2  mov     ebx, eax
0x14000fac4  test    eax, eax
0x14000fac6  jnz     loc_14000FC54
0x14000facc  movups  xmm0, xmmword ptr [r12+18h]
0x14000fad2  movdqu  xmmword ptr [rdi+28h], xmm0
0x14000fad7  mov     rax, [rbp+60h+var_70]
0x14000fadb  mov     [rdi+38h], rax
0x14000fadf  jmp     short loc_14000FB53
0x14000fae1  lea     rcx, [rbp+60h+Uuid]; Uuid
0x14000fae5  call    cs:__imp_UuidCreate
0x14000faeb  mov     ebx, eax
0x14000faed  test    eax, eax
0x14000faef  jnz     loc_14000FD6E
0x14000faf5  lea     rax, [rbp+60h+Uuid]
0x14000faf9  lea     r12, [r15+18h]
0x14000fafd  mov     qword ptr [rsp+160h+var_E8], rax
0x14000fb02  mov     rax, [rsi+18h]
0x14000fb06  lea     ecx, [rbx+1]
0x14000fb09  add     r12, r14
0x14000fb0c  mov     qword ptr [rbp+60h+var_E8+8], rax
0x14000fb10  mov     dword ptr [rbp+60h+var_C8+4], ecx
0x14000fb13  mov     qword ptr [rbp+60h+var_C8+8], r12
0x14000fb17  cmp     dword ptr [rsp+160h+var_100], ebx
0x14000fb1b  jz      short loc_14000FB20
0x14000fb1d  or      dword ptr [rbp+60h+var_D8], ecx
0x14000fb20  lea     rax, [rsp+160h+var_F0]
0x14000fb25  mov     edx, ecx
0x14000fb27  mov     ecx, 0FFFFh
0x14000fb2c  mov     [rsp+160h+phkResult], rax
0x14000fb31  lea     r9, [rbp+60h+var_70]
0x14000fb35  lea     r8, [rsp+160h+var_E8]
0x14000fb3a  call    cs:__imp_DabRegisterTriggerConsumer
0x14000fb40  mov     ebx, eax
0x14000fb42  test    eax, eax
0x14000fb44  jnz     loc_14000FCB1
0x14000fb4a  mov     rax, [rsp+160h+var_F0]
0x14000fb4f  mov     [rdi+28h], rax
0x14000fb53  mov     r12d, dword ptr [rsp+160h+var_100]
0x14000fb58  cmp     dword ptr [r14+r15], 3
0x14000fb5d  jz      short loc_14000FBB8
0x14000fb5f  mov     rax, [rbp+60h+var_70]
0x14000fb63  lea     rdx, [rdi+18h]
0x14000fb67  mov     qword ptr [rbp+60h+var_A8], rax
0x14000fb6b  xorps   xmm0, xmm0
0x14000fb6e  lea     rax, ?ScExtpTriggerArrived@@YAXPEAXU_CBROKERED_EVENT_ID@@00K@Z; ScExtpTriggerArrived(void *,_CBROKERED_EVENT_ID,void *,void *,ulong)
0x14000fb75  mov     qword ptr [rbp+60h+var_98+8], 0
0x14000fb7d  mov     qword ptr [rbp+60h+var_88], rax
0x14000fb81  mov     ecx, 2
0x14000fb86  movd    eax, xmm0
0x14000fb8a  test    r12d, r12d
0x14000fb8d  movdqu  [rbp+60h+var_A8+8], xmm0
0x14000fb92  mov     qword ptr [rbp+60h+var_88+8], 0
0x14000fb9a  cmovz   eax, ecx
0x14000fb9d  mov     [rbp+60h+var_78], rsi
0x14000fba1  lea     rcx, [rbp+60h+var_A8]
0x14000fba5  mov     dword ptr [rbp+60h+var_A8+8], eax
0x14000fba8  call    cs:__imp_EACreateAggregateEvent
0x14000fbae  mov     ebx, eax
0x14000fbb0  test    eax, eax
0x14000fbb2  jnz     loc_14000FC7F
0x14000fbb8  lea     rax, [rsi+20h]
0x14000fbbc  mov     rcx, [rax+8]
0x14000fbc0  cmp     [rcx], rax
0x14000fbc3  jnz     loc_14000FCAA
0x14000fbc9  mov     [rdi], rax
0x14000fbcc  mov     [rdi+8], rcx
0x14000fbd0  mov     [rcx], rdi
0x14000fbd3  mov     [rax+8], rdi
0x14000fbd7  xor     edi, edi
0x14000fbd9  lea     r14d, [rdi+1]
0x14000fbdd  add     r13w, r14w
0x14000fbe1  movzx   eax, r13w
0x14000fbe5  cmp     eax, [rsp+160h+var_108]
0x14000fbe9  jb      loc_14000F90D
0x14000fbef  jmp     loc_14000FDCB
0x14000fbf4  mov     rcx, cs:WPP_GLOBAL_Control
0x14000fbfb  lea     rax, WPP_GLOBAL_Control
0x14000fc02  cmp     rcx, rax
0x14000fc05  jz      loc_14000FDCB
0x14000fc0b  test    byte ptr [rcx+1Ch], 1
0x14000fc0f  jz      loc_14000FDCB
0x14000fc15  mov     edx, 35h ; '5'
0x14000fc1a  jmp     loc_14000FDAF
0x14000fc1f  mov     rcx, cs:WPP_GLOBAL_Control
0x14000fc26  lea     rax, WPP_GLOBAL_Control
0x14000fc2d  cmp     rcx, rax
0x14000fc30  jz      loc_14000FDCB
0x14000fc36  test    byte ptr [rcx+1Ch], 1
0x14000fc3a  jz      loc_14000FDCB
0x14000fc40  mov     edx, 34h ; '4'
0x14000fc45  jmp     loc_14000FDAF
0x14000fc4a  mov     ebx, 32h ; '2'
0x14000fc4f  jmp     loc_14000FDCB
0x14000fc54  mov     rcx, cs:WPP_GLOBAL_Control
0x14000fc5b  lea     rax, WPP_GLOBAL_Control
0x14000fc62  cmp     rcx, rax
0x14000fc65  jz      loc_14000FDCB
0x14000fc6b  test    byte ptr [rcx+1Ch], 1
0x14000fc6f  jz      loc_14000FDCB
0x14000fc75  mov     edx, 33h ; '3'
0x14000fc7a  jmp     loc_14000FDAF
0x14000fc7f  mov     rcx, cs:WPP_GLOBAL_Control
0x14000fc86  lea     rax, WPP_GLOBAL_Control
0x14000fc8d  cmp     rcx, rax
0x14000fc90  jz      loc_14000FDCB
0x14000fc96  test    byte ptr [rcx+1Ch], 1
0x14000fc9a  jz      loc_14000FDCB
0x14000fca0  mov     edx, 36h ; '6'
0x14000fca5  jmp     loc_14000FDAF
0x14000fcaa  mov     ecx, 3
0x14000fcaf  int     29h; Win8: RtlFailFast(ecx)
0x14000fcb1  mov     eax, cs:dword_1400BA2A0
0x14000fcb7  cmp     eax, 5
0x14000fcba  jbe     short loc_14000FD25
0x14000fcbc  mov     rdx, 200000000000h
0x14000fcc6  lea     rcx, dword_1400BA2A0
0x14000fccd  call    _tlgKeywordOn
0x14000fcd2  test    al, al
0x14000fcd4  jz      short loc_14000FD25
0x14000fcd6  mov     rax, [r12]
0x14000fcda  lea     rdx, word_1400AF8FE
0x14000fce1  mov     [rbp+60h+var_B8], rax
0x14000fce5  mov     rax, [rsi+18h]
0x14000fce9  mov     [rbp+60h+var_B0], rax
0x14000fced  lea     rax, [rsp+160h+var_100]
0x14000fcf2  mov     [rsp+160h+var_128], rax
0x14000fcf7  lea     rax, [rsp+160h+var_108]
0x14000fcfc  mov     [rsp+160h+var_130], rax
0x14000fd01  lea     rax, [rbp+60h+var_B8]
0x14000fd05  mov     [rsp+160h+var_138], rax
0x14000fd0a  lea     rax, [rbp+60h+var_B0]
0x14000fd0e  mov     [rsp+160h+phkResult], rax
0x14000fd13  mov     [rsp+160h+var_100], 1000000h
0x14000fd1c  mov     [rsp+160h+var_108], ebx
0x14000fd20  call    ??$Write@U?$_tlgWrapSz@G@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x14000fd25  mov     rcx, cs:WPP_GLOBAL_Control
0x14000fd2c  lea     rax, WPP_GLOBAL_Control
0x14000fd33  cmp     rcx, rax
0x14000fd36  jz      loc_14000FDCB
0x14000fd3c  test    byte ptr [rcx+1Ch], 1
0x14000fd40  jz      loc_14000FDCB
0x14000fd46  mov     rax, [rsi+18h]
0x14000fd4a  lea     r8, WPP_33ca3c9d568834eb2422a5f850c17021_Traceguids
0x14000fd51  mov     r9, [r12]
0x14000fd55  mov     edx, 32h ; '2'
0x14000fd5a  mov     rcx, [rcx+10h]
0x14000fd5e  mov     dword ptr [rsp+160h+var_138], ebx
0x14000fd62  mov     [rsp+160h+phkResult], rax
0x14000fd67  call    WPP_SF_SSD
0x14000fd6c  jmp     short loc_14000FDCB
0x14000fd6e  mov     rcx, cs:WPP_GLOBAL_Control
0x14000fd75  lea     rax, WPP_GLOBAL_Control
0x14000fd7c  cmp     rcx, rax
0x14000fd7f  jz      short loc_14000FDCB
0x14000fd81  test    byte ptr [rcx+1Ch], 1
0x14000fd85  jz      short loc_14000FDCB
0x14000fd87  mov     edx, 31h ; '1'
0x14000fd8c  jmp     short loc_14000FDAF
0x14000fd8e  mov     ebx, 0Eh
0x14000fd93  mov     rcx, cs:WPP_GLOBAL_Control
0x14000fd9a  lea     rax, WPP_GLOBAL_Control
0x14000fda1  cmp     rcx, rax
0x14000fda4  jz      short loc_14000FDCB
0x14000fda6  test    [rcx+1Ch], r14b
0x14000fdaa  jz      short loc_14000FDCB
  ... truncated ...
```
