# WFDMgrInitialize(void * *)

- ea: `0x180187c78`
- end: `0x1801883e0`
- name: `?WFDMgrInitialize@@YAKPEAPEAX@Z`
- size: `1896`
- prototype: `unsigned int __fastcall(void **)`
- caller_count: `1`
- callee_count: `20`
- tags: `broker_com_uri`

## callers

- `0x180100294`

## callees

- `0x18000aa0c`
- `0x18000c5a0`
- `0x180011530`
- `0x18002f450`
- `0x18006bff0`
- `0x18007f934`
- `0x1800a84a0`
- `0x1800a94e0`
- `0x1800ab094`
- `0x1800cb7a8`
- `0x1800ce620`
- `0x1800da00c`
- `0x1800da634`
- `0x1800db1c0`
- `0x1800fe134`
- `0x180107330`
- `0x18016bff4`
- `0x18017a2e8`
- `0x18017f99c`
- `0x180187c78`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180188382`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180188382`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180187d8c`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180187d8c`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180187d9d`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180187de7`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180187e30`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180187e79`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180187d9d`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180187de7`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180187e30`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180187e79`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180188348`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180188357`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180188366`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180188375`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180188348`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180188357`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180188366`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180188375`
- `MobileNetworking!HtNewHandle` at `0x18018829d`
- `MobileNetworking!HtNewHandle` at `0x18018829d`

## pseudocode

```c
__int64 __fastcall WFDMgrInitialize(void **a1)
{
  PVOID *v2; // rcx
  unsigned int inited; // edi
  __int64 v4; // rdx
  char *v5; // rax
  char *v6; // rbx
  int v7; // r15d
  int v8; // r14d
  int v9; // ebp
  HANDLE EventW; // rax
  HANDLE v11; // rax
  HANDLE v12; // rax
  HANDLE v13; // rax
  _QWORD *v14; // rcx
  __int64 v15; // rdx
  __int64 v16; // rcx
  void *v17; // rax
  __int64 v18; // rdx
  __int64 v19; // rax
  unsigned int DefaultGOProfile; // eax
  void *v21; // rcx
  void *v22; // rcx
  void *v23; // rcx
  void *v24; // rcx
  void *v26; // [rsp+60h] [rbp+8h] BYREF

  v26 = 0;
  v2 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 190, &WPP_770d2a6ca85f3f6f822445dd5e88f798_Traceguids);
    v2 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( a1 )
  {
    *a1 = 0;
    v5 = (char *)AllocWLMem(0x3F0u);
    v6 = v5;
    if ( !v5 )
    {
      inited = 14;
      v2 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        return inited;
      if ( !*((_BYTE *)WPP_GLOBAL_Control + 105) || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) == 0 )
        goto LABEL_115;
      v4 = 192;
      goto LABEL_10;
    }
    v7 = 0;
    v8 = 0;
    v9 = 0;
    memset_0(v5, 0, 0x3F0u);
    InitializeCriticalSection((LPCRITICAL_SECTION)v6 + 6);
    EventW = CreateEventW(0, 1, 0, 0);
    *((_QWORD *)v6 + 1) = EventW;
    if ( !EventW
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 105)
      && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 193, &WPP_770d2a6ca85f3f6f822445dd5e88f798_Traceguids, 0);
    }
    v11 = CreateEventW(0, 1, 0, 0);
    *((_QWORD *)v6 + 2) = v11;
    if ( !v11
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 105)
      && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 194, &WPP_770d2a6ca85f3f6f822445dd5e88f798_Traceguids, 0);
    }
    v12 = CreateEventW(0, 0, 0, 0);
    *((_QWORD *)v6 + 3) = v12;
    if ( !v12
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 105)
      && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 195, &WPP_770d2a6ca85f3f6f822445dd5e88f798_Traceguids, 0);
    }
    v13 = CreateEventW(0, 0, 0, 0);
    *((_QWORD *)v6 + 117) = v13;
    if ( !v13
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 105)
      && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 196, &WPP_770d2a6ca85f3f6f822445dd5e88f798_Traceguids, 0);
    }
    inited = WFDMgrInitializeThreadpoolEnvironment((struct _WFD_MANAGER *)v6);
    if ( !inited )
    {
      v7 = 1;
      inited = WlanInitEventQueue(
                 (struct _WLAN_EVENT_QUEUE *)(v6 + 32),
                 (void (*)(struct _WLAN_COMMON_EVENT *))WFDProcessUpcallNotification,
                 (void (*)(struct _WLAN_COMMON_EVENT *))WFDFreeUpcallNotification,
                 0);
      if ( inited )
      {
        v14 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || !*((_BYTE *)WPP_GLOBAL_Control + 105)
          || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) == 0 )
        {
          goto LABEL_43;
        }
        v15 = 197;
        goto LABEL_42;
      }
      *((_QWORD *)v6 + 85) = v6 + 672;
      *((_QWORD *)v6 + 84) = v6 + 672;
      *((_QWORD *)v6 + 87) = v6 + 688;
      *((_QWORD *)v6 + 86) = v6 + 688;
      *((_QWORD *)v6 + 91) = v6 + 720;
      *((_QWORD *)v6 + 90) = v6 + 720;
      *((_QWORD *)v6 + 116) = v6 + 920;
      *((_QWORD *)v6 + 115) = v6 + 920;
      *((_DWORD *)v6 + 250) = 1;
      *((_QWORD *)v6 + 120) = 0;
      *((_DWORD *)v6 + 239) = 5;
      v17 = (void *)AllocWLMem(0x78u);
      *((_QWORD *)v6 + 29) = v17;
      if ( !v17 )
      {
        v2 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
          return inited;
        if ( !*((_BYTE *)WPP_GLOBAL_Control + 105) || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) == 0 )
          goto LABEL_115;
        v18 = 198;
LABEL_57:
        WPP_SF_d(v2[12], v18, &WPP_770d2a6ca85f3f6f822445dd5e88f798_Traceguids, 0);
        goto LABEL_114;
      }
      v8 = 1;
      memset_0(v17, 0, 0x78u);
      inited = WFDMgrSerializerCreateHandle(*((struct _WFD_MGR_API_SERIALIZER_STATE **)v6 + 29), &v26);
      if ( inited )
      {
        v14 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || !*((_BYTE *)WPP_GLOBAL_Control + 105)
          || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) == 0 )
        {
          goto LABEL_43;
        }
        v15 = 199;
        goto LABEL_42;
      }
      **((_QWORD **)v6 + 29) = v26;
      inited = WFDMgrSerializerInitializeContext(v26);
      if ( inited )
      {
        v14 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || !*((_BYTE *)WPP_GLOBAL_Control + 105)
          || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) == 0 )
        {
          goto LABEL_43;
        }
        v15 = 200;
        goto LABEL_42;
      }
      *((_QWORD *)v6 + 27) = v26;
      v9 = 1;
      inited = WFDMgrInitializeDiscoverySerializer((struct _WFD_MANAGER *)v6);
      if ( inited )
      {
        v14 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || !*((_BYTE *)WPP_GLOBAL_Control + 105)
          || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) == 0 )
        {
          goto LABEL_43;
        }
        v15 = 201;
        goto LABEL_42;
      }
      v19 = AllocWLMem(0xCu);
      *((_QWORD *)v6 + 111) = v19;
      if ( !v19 )
      {
        v2 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
          return inited;
        if ( !*((_BYTE *)WPP_GLOBAL_Control + 105) || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) == 0 )
          goto LABEL_115;
        v18 = 202;
        goto LABEL_57;
      }
      *(_QWORD *)v19 = 0;
      *(_DWORD *)(v19 + 8) = 0;
      inited = WFDMgrInitGracePeriodManager(v6);
      if ( inited )
      {
        v14 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || !*((_BYTE *)WPP_GLOBAL_Control + 105)
          || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) == 0 )
        {
          goto LABEL_43;
        }
        v15 = 203;
LABEL_42:
        WPP_SF_d(v14[12], v15, &WPP_770d2a6ca85f3f6f822445dd5e88f798_Traceguids, inited);
        goto LABEL_43;
      }
      DefaultGOProfile = WFDMgrLoadDefaultGOProfile((struct _WFD_PROFILE *)(v6 + 280));
      if ( DefaultGOProfile )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 3u
          && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 12),
            204,
            &WPP_770d2a6ca85f3f6f822445dd5e88f798_Traceguids,
            DefaultGOProfile);
        }
      }
      else
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 3u
          && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 205, &WPP_770d2a6ca85f3f6f822445dd5e88f798_Traceguids);
        }
        *((_DWORD *)v6 + 148) = 1;
      }
      g_WfdPassPhrase = 0;
      dword_1802A3284 = 0;
      memset_0(&dword_1802A3244, 0, 0x40u);
      inited = HtNewHandle(g_hHandleTable, v6, 287445282, WFDMgrOnReferenceCountReachedZero, 1, v6);
      if ( !inited )
      {
        WFDMgrTraceRefCount(*(void **)v6);
        *a1 = *(void **)v6;
        goto LABEL_114;
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 105)
        && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 206, &WPP_770d2a6ca85f3f6f822445dd5e88f798_Traceguids, inited);
      }
      WFDMgrDeinitGracePeriodManager((struct _WFD_MANAGER *)v6);
      v9 = 1;
    }
LABEL_43:
    if ( *((_QWORD *)v6 + 28) )
      WFDMgrCleanupDiscoverySerializer((struct _WFD_MANAGER *)v6, 0);
    v16 = *((_QWORD *)v6 + 111);
    if ( v16 )
      FreeWLMem(v16);
    if ( *((_QWORD *)v6 + 29) )
    {
      if ( v9 )
        WFDMgrSerializerFinalizeContext(*((void **)v6 + 27), 0);
      if ( v26 )
      {
        WFDMgrSerializerDereference(v26);
      }
      else
      {
        memset_0(*((void **)v6 + 29), 0, 0x78u);
        FreeWLMem(*((_QWORD *)v6 + 29));
      }
    }
    if ( v8 )
      WlanDeinitEventQueue((struct _WLAN_EVENT_QUEUE *)(v6 + 32));
    if ( v7 )
      WFDMgrDeinitializeThreadpoolEnvironment((struct _WFD_MANAGER *)v6);
    v21 = (void *)*((_QWORD *)v6 + 117);
    if ( v21 )
      CloseHandle(v21);
    v22 = (void *)*((_QWORD *)v6 + 3);
    if ( v22 )
      CloseHandle(v22);
    v23 = (void *)*((_QWORD *)v6 + 2);
    if ( v23 )
      CloseHandle(v23);
    v24 = (void *)*((_QWORD *)v6 + 1);
    if ( v24 )
      CloseHandle(v24);
    DeleteCriticalSection((LPCRITICAL_SECTION)v6 + 6);
    FreeWLMem(v6);
    goto LABEL_114;
  }
  inited = 87;
  if ( v2 == &WPP_GLOBAL_Control )
    return inited;
  if ( *((_BYTE *)v2 + 105) && (*((_BYTE *)v2 + 108) & 1) != 0 )
  {
    v4 = 191;
LABEL_10:
    WPP_SF_(v2[12], v4, &WPP_770d2a6ca85f3f6f822445dd5e88f798_Traceguids);
LABEL_114:
    v2 = (PVOID *)WPP_GLOBAL_Control;
  }
LABEL_115:
  if ( v2 != &WPP_GLOBAL_Control && *((_BYTE *)v2 + 105) >= 4u && (*((_BYTE *)v2 + 108) & 1) != 0 )
    WPP_SF_d(v2[12], 207, &WPP_770d2a6ca85f3f6f822445dd5e88f798_Traceguids, inited);
  return inited;
}

```

## disassembly

```asm
0x180187c78  mov     [rsp+arg_8], rbx
0x180187c7d  mov     [rsp+arg_10], rbp
0x180187c82  push    rsi
0x180187c83  push    rdi
0x180187c84  push    r12
0x180187c86  push    r14
0x180187c88  push    r15
0x180187c8a  sub     rsp, 30h
0x180187c8e  mov     rsi, rcx
0x180187c91  mov     [rsp+58h+arg_0], 0
0x180187c9a  mov     rcx, cs:WPP_GLOBAL_Control
0x180187ca1  lea     rdi, WPP_GLOBAL_Control
0x180187ca8  mov     r12d, 1
0x180187cae  cmp     rcx, rdi
0x180187cb1  jz      short loc_180187CDB
0x180187cb3  cmp     byte ptr [rcx+69h], 4
0x180187cb7  jb      short loc_180187CDB
0x180187cb9  test    [rcx+6Ch], r12b
0x180187cbd  jz      short loc_180187CDB
0x180187cbf  mov     rcx, [rcx+60h]
0x180187cc3  lea     r8, WPP_770d2a6ca85f3f6f822445dd5e88f798_Traceguids
0x180187cca  mov     edx, 0BEh
0x180187ccf  call    WPP_SF_
0x180187cd4  mov     rcx, cs:WPP_GLOBAL_Control
0x180187cdb  test    rsi, rsi
0x180187cde  jnz     short loc_180187D1F
0x180187ce0  lea     edi, [rsi+57h]
0x180187ce3  lea     rbp, WPP_GLOBAL_Control
0x180187cea  cmp     rcx, rbp
0x180187ced  jz      loc_1801883C7
0x180187cf3  cmp     [rcx+69h], r12b
0x180187cf7  jb      loc_18018839E
0x180187cfd  test    [rcx+6Ch], r12b
0x180187d01  jz      loc_18018839E
0x180187d07  lea     edx, [rdi+68h]
0x180187d0a  mov     rcx, [rcx+60h]
0x180187d0e  lea     r8, WPP_770d2a6ca85f3f6f822445dd5e88f798_Traceguids
0x180187d15  call    WPP_SF_
0x180187d1a  jmp     loc_180188397
0x180187d1f  mov     ecx, 3F0h; dwBytes
0x180187d24  mov     qword ptr [rsi], 0
0x180187d2b  call    AllocWLMem
0x180187d30  mov     rbx, rax
0x180187d33  test    rax, rax
0x180187d36  jnz     short loc_180187D6D
0x180187d38  lea     edi, [rax+0Eh]
0x180187d3b  mov     rcx, cs:WPP_GLOBAL_Control
0x180187d42  lea     rbp, WPP_GLOBAL_Control
0x180187d49  cmp     rcx, rbp
0x180187d4c  jz      loc_1801883C7
0x180187d52  cmp     [rcx+69h], r12b
0x180187d56  jb      loc_18018839E
0x180187d5c  test    [rcx+6Ch], r12b
0x180187d60  jz      loc_18018839E
0x180187d66  mov     edx, 0C0h
0x180187d6b  jmp     short loc_180187D0A
0x180187d6d  xor     edx, edx; Val
0x180187d6f  mov     r8d, 3F0h; Size
0x180187d75  mov     rcx, rbx; void *
0x180187d78  xor     r15d, r15d
0x180187d7b  xor     r14d, r14d
0x180187d7e  xor     ebp, ebp
0x180187d80  call    memset_0
0x180187d85  lea     rcx, [rbx+0F0h]; lpCriticalSection
0x180187d8c  call    cs:__imp_InitializeCriticalSection
0x180187d92  xor     r9d, r9d; lpName
0x180187d95  xor     r8d, r8d; bInitialState
0x180187d98  mov     edx, r12d; bManualReset
0x180187d9b  xor     ecx, ecx; lpEventAttributes
0x180187d9d  call    cs:__imp_CreateEventW
0x180187da3  mov     [rbx+8], rax
0x180187da7  test    rax, rax
0x180187daa  jnz     short loc_180187DDC
0x180187dac  mov     rcx, cs:WPP_GLOBAL_Control
0x180187db3  cmp     rcx, rdi
0x180187db6  jz      short loc_180187DDC
0x180187db8  cmp     [rcx+69h], r12b
0x180187dbc  jb      short loc_180187DDC
0x180187dbe  test    [rcx+6Ch], r12b
0x180187dc2  jz      short loc_180187DDC
0x180187dc4  mov     rcx, [rcx+60h]
0x180187dc8  lea     r8, WPP_770d2a6ca85f3f6f822445dd5e88f798_Traceguids
0x180187dcf  mov     edx, 0C1h
0x180187dd4  xor     r9d, r9d
0x180187dd7  call    WPP_SF_d
0x180187ddc  xor     r9d, r9d; lpName
0x180187ddf  xor     r8d, r8d; bInitialState
0x180187de2  mov     edx, r12d; bManualReset
0x180187de5  xor     ecx, ecx; lpEventAttributes
0x180187de7  call    cs:__imp_CreateEventW
0x180187ded  mov     [rbx+10h], rax
0x180187df1  test    rax, rax
0x180187df4  jnz     short loc_180187E26
0x180187df6  mov     rcx, cs:WPP_GLOBAL_Control
0x180187dfd  cmp     rcx, rdi
0x180187e00  jz      short loc_180187E26
0x180187e02  cmp     [rcx+69h], r12b
0x180187e06  jb      short loc_180187E26
0x180187e08  test    [rcx+6Ch], r12b
0x180187e0c  jz      short loc_180187E26
0x180187e0e  mov     rcx, [rcx+60h]
0x180187e12  lea     r8, WPP_770d2a6ca85f3f6f822445dd5e88f798_Traceguids
0x180187e19  mov     edx, 0C2h
0x180187e1e  xor     r9d, r9d
0x180187e21  call    WPP_SF_d
0x180187e26  xor     r9d, r9d; lpName
0x180187e29  xor     r8d, r8d; bInitialState
0x180187e2c  xor     edx, edx; bManualReset
0x180187e2e  xor     ecx, ecx; lpEventAttributes
0x180187e30  call    cs:__imp_CreateEventW
0x180187e36  mov     [rbx+18h], rax
0x180187e3a  test    rax, rax
0x180187e3d  jnz     short loc_180187E6F
0x180187e3f  mov     rcx, cs:WPP_GLOBAL_Control
0x180187e46  cmp     rcx, rdi
0x180187e49  jz      short loc_180187E6F
0x180187e4b  cmp     [rcx+69h], r12b
0x180187e4f  jb      short loc_180187E6F
0x180187e51  test    [rcx+6Ch], r12b
0x180187e55  jz      short loc_180187E6F
0x180187e57  mov     rcx, [rcx+60h]
0x180187e5b  lea     r8, WPP_770d2a6ca85f3f6f822445dd5e88f798_Traceguids
0x180187e62  mov     edx, 0C3h
0x180187e67  xor     r9d, r9d
0x180187e6a  call    WPP_SF_d
0x180187e6f  xor     r9d, r9d; lpName
0x180187e72  xor     r8d, r8d; bInitialState
0x180187e75  xor     edx, edx; bManualReset
0x180187e77  xor     ecx, ecx; lpEventAttributes
0x180187e79  call    cs:__imp_CreateEventW
0x180187e7f  mov     [rbx+3A8h], rax
0x180187e86  test    rax, rax
0x180187e89  jnz     short loc_180187EBB
0x180187e8b  mov     rcx, cs:WPP_GLOBAL_Control
0x180187e92  cmp     rcx, rdi
0x180187e95  jz      short loc_180187EBB
0x180187e97  cmp     [rcx+69h], r12b
0x180187e9b  jb      short loc_180187EBB
0x180187e9d  test    [rcx+6Ch], r12b
0x180187ea1  jz      short loc_180187EBB
0x180187ea3  mov     rcx, [rcx+60h]
0x180187ea7  lea     r8, WPP_770d2a6ca85f3f6f822445dd5e88f798_Traceguids
0x180187eae  mov     edx, 0C4h
0x180187eb3  xor     r9d, r9d
0x180187eb6  call    WPP_SF_d
0x180187ebb  mov     rcx, rbx; struct _WFD_MANAGER *
0x180187ebe  call    ?WFDMgrInitializeThreadpoolEnvironment@@YAKPEAU_WFD_MANAGER@@@Z; WFDMgrInitializeThreadpoolEnvironment(_WFD_MANAGER *)
0x180187ec3  mov     edi, eax
0x180187ec5  test    eax, eax
0x180187ec7  jnz     short loc_180187F27
0x180187ec9  lea     rcx, [rbx+20h]; struct _WLAN_EVENT_QUEUE *
0x180187ecd  xor     r9d, r9d; unsigned int *
0x180187ed0  lea     r8, ?WFDFreeUpcallNotification@@YAXPEAU_WLAN_COMMON_EVENT@@@Z; void (*)(struct _WLAN_COMMON_EVENT *)
0x180187ed7  mov     r15d, r12d
0x180187eda  lea     rdx, ?WFDProcessUpcallNotification@@YAXPEAU_WLAN_COMMON_EVENT@@@Z; void (*)(struct _WLAN_COMMON_EVENT *)
0x180187ee1  call    ?WlanInitEventQueue@@YAKPEAU_WLAN_EVENT_QUEUE@@P6AXPEAU_WLAN_COMMON_EVENT@@@Z2PEAK@Z; WlanInitEventQueue(_WLAN_EVENT_QUEUE *,void (*)(_WLAN_COMMON_EVENT *),void (*)(_WLAN_COMMON_EVENT *),ulong *)
0x180187ee6  mov     edi, eax
0x180187ee8  test    eax, eax
0x180187eea  jz      loc_180187F84
0x180187ef0  mov     rcx, cs:WPP_GLOBAL_Control
0x180187ef7  lea     rax, WPP_GLOBAL_Control
0x180187efe  cmp     rcx, rax
0x180187f01  jz      short loc_180187F27
0x180187f03  cmp     [rcx+69h], r12b
0x180187f07  jb      short loc_180187F27
0x180187f09  test    [rcx+6Ch], r12b
0x180187f0d  jz      short loc_180187F27
0x180187f0f  mov     edx, 0C5h
0x180187f14  mov     rcx, [rcx+60h]
0x180187f18  lea     r8, WPP_770d2a6ca85f3f6f822445dd5e88f798_Traceguids
0x180187f1f  mov     r9d, edi
0x180187f22  call    WPP_SF_d
0x180187f27  cmp     qword ptr [rbx+0E0h], 0
0x180187f2f  jz      short loc_180187F3B
0x180187f31  xor     edx, edx; unsigned __int8
0x180187f33  mov     rcx, rbx; struct _WFD_MANAGER *
0x180187f36  call    ?WFDMgrCleanupDiscoverySerializer@@YAXPEAU_WFD_MANAGER@@E@Z; WFDMgrCleanupDiscoverySerializer(_WFD_MANAGER *,uchar)
0x180187f3b  mov     rcx, [rbx+378h]
0x180187f42  test    rcx, rcx
0x180187f45  jz      short loc_180187F4C
0x180187f47  call    FreeWLMem
0x180187f4c  cmp     qword ptr [rbx+0E8h], 0
0x180187f54  jz      loc_180188321
0x180187f5a  test    ebp, ebp
0x180187f5c  jz      short loc_180187F6C
0x180187f5e  mov     rcx, [rbx+0D8h]; void *
0x180187f65  xor     edx, edx; void *
0x180187f67  call    ?WFDMgrSerializerFinalizeContext@@YAHPEAX0@Z; WFDMgrSerializerFinalizeContext(void *,void *)
0x180187f6c  mov     rcx, [rsp+58h+arg_0]; void *
0x180187f71  test    rcx, rcx
0x180187f74  jz      loc_180188303
0x180187f7a  call    ?WFDMgrSerializerDereference@@YAXPEAX@Z; WFDMgrSerializerDereference(void *)
0x180187f7f  jmp     loc_180188321
0x180187f84  lea     rax, [rbx+2A0h]
0x180187f8b  mov     ecx, 78h ; 'x'; dwBytes
0x180187f90  mov     [rax+8], rax
0x180187f94  mov     [rax], rax
0x180187f97  lea     rax, [rbx+2B0h]
0x180187f9e  mov     [rax+8], rax
0x180187fa2  mov     [rax], rax
0x180187fa5  lea     rax, [rbx+2D0h]
0x180187fac  mov     [rax+8], rax
0x180187fb0  mov     [rax], rax
0x180187fb3  lea     rax, [rbx+398h]
0x180187fba  mov     [rax+8], rax
0x180187fbe  mov     [rax], rax
0x180187fc1  mov     [rbx+3E8h], r12d
0x180187fc8  mov     [rbx+3C0h], rbp
0x180187fcf  mov     dword ptr [rbx+3BCh], 5
0x180187fd9  call    AllocWLMem
0x180187fde  mov     [rbx+0E8h], rax
0x180187fe5  test    rax, rax
0x180187fe8  jnz     short loc_180188032
0x180187fea  mov     rcx, cs:WPP_GLOBAL_Control
0x180187ff1  lea     rbp, WPP_GLOBAL_Control
0x180187ff8  cmp     rcx, rbp
0x180187ffb  jz      loc_1801883C7
0x180188001  cmp     [rcx+69h], r12b
0x180188005  jb      loc_18018839E
0x18018800b  test    [rcx+6Ch], r12b
0x18018800f  jz      loc_18018839E
0x180188015  mov     edx, 0C6h
0x18018801a  mov     rcx, [rcx+60h]
0x18018801e  lea     r8, WPP_770d2a6ca85f3f6f822445dd5e88f798_Traceguids
0x180188025  xor     r9d, r9d
0x180188028  call    WPP_SF_d
0x18018802d  jmp     loc_180188397
0x180188032  xor     edx, edx; Val
0x180188034  mov     rcx, rax; void *
0x180188037  mov     r14d, r12d
0x18018803a  lea     r8d, [rdx+78h]; Size
0x18018803e  call    memset_0
0x180188043  mov     rcx, [rbx+0E8h]; struct _WFD_MGR_API_SERIALIZER_STATE *
0x18018804a  lea     rdx, [rsp+58h+arg_0]; void **
0x18018804f  call    ?WFDMgrSerializerCreateHandle@@YAKPEAU_WFD_MGR_API_SERIALIZER_STATE@@PEAPEAX@Z; WFDMgrSerializerCreateHandle(_WFD_MGR_API_SERIALIZER_STATE *,void * *)
0x180188054  mov     edi, eax
0x180188056  test    eax, eax
0x180188058  jz      short loc_18018808F
0x18018805a  mov     rcx, cs:WPP_GLOBAL_Control
0x180188061  lea     rax, WPP_GLOBAL_Control
0x180188068  cmp     rcx, rax
0x18018806b  jz      loc_180187F27
0x180188071  cmp     [rcx+69h], r12b
0x180188075  jb      loc_180187F27
0x18018807b  test    [rcx+6Ch], r12b
0x18018807f  jz      loc_180187F27
0x180188085  mov     edx, 0C7h
0x18018808a  jmp     loc_180187F14
0x18018808f  mov     rcx, [rbx+0E8h]
0x180188096  mov     rax, [rsp+58h+arg_0]
0x18018809b  mov     [rcx], rax
0x18018809e  mov     rcx, [rsp+58h+arg_0]; void *
0x1801880a3  call    ?WFDMgrSerializerInitializeContext@@YAKPEAX@Z; WFDMgrSerializerInitializeContext(void *)
0x1801880a8  mov     edi, eax
0x1801880aa  test    eax, eax
0x1801880ac  jz      short loc_1801880E3
0x1801880ae  mov     rcx, cs:WPP_GLOBAL_Control
0x1801880b5  lea     rax, WPP_GLOBAL_Control
0x1801880bc  cmp     rcx, rax
0x1801880bf  jz      loc_180187F27
0x1801880c5  cmp     [rcx+69h], r12b
0x1801880c9  jb      loc_180187F27
0x1801880cf  test    [rcx+6Ch], r12b
0x1801880d3  jz      loc_180187F27
0x1801880d9  mov     edx, 0C8h
0x1801880de  jmp     loc_180187F14
0x1801880e3  mov     rax, [rsp+58h+arg_0]
0x1801880e8  mov     rcx, rbx; struct _WFD_MANAGER *
0x1801880eb  mov     [rbx+0D8h], rax
0x1801880f2  mov     ebp, r12d
0x1801880f5  call    ?WFDMgrInitializeDiscoverySerializer@@YAKPEAU_WFD_MANAGER@@@Z; WFDMgrInitializeDiscoverySerializer(_WFD_MANAGER *)
0x1801880fa  mov     edi, eax
0x1801880fc  test    eax, eax
0x1801880fe  jz      short loc_180188135
0x180188100  mov     rcx, cs:WPP_GLOBAL_Control
0x180188107  lea     rax, WPP_GLOBAL_Control
0x18018810e  cmp     rcx, rax
0x180188111  jz      loc_180187F27
0x180188117  cmp     [rcx+69h], r12b
0x18018811b  jb      loc_180187F27
0x180188121  test    [rcx+6Ch], r12b
0x180188125  jz      loc_180187F27
0x18018812b  mov     edx, 0C9h
0x180188130  jmp     loc_180187F14
0x180188135  mov     ecx, 0Ch; dwBytes
0x18018813a  call    AllocWLMem
0x18018813f  mov     [rbx+378h], rax
0x180188146  test    rax, rax
0x180188149  jnz     short loc_180188180
0x18018814b  mov     rcx, cs:WPP_GLOBAL_Control
0x180188152  lea     rbp, WPP_GLOBAL_Control
0x180188159  cmp     rcx, rbp
0x18018815c  jz      loc_1801883C7
0x180188162  cmp     [rcx+69h], r12b
0x180188166  jb      loc_18018839E
0x18018816c  test    [rcx+6Ch], r12b
0x180188170  jz      loc_18018839E
0x180188176  mov     edx, 0CAh
0x18018817b  jmp     loc_18018801A
0x180188180  xor     ecx, ecx
  ... truncated ...
```
