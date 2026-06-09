# IntfCreateContext(_GUID const &,ushort const *,ushort const *,_WLAN_INTERFACE_TYPE,void * *)

- ea: `0x18013aa70`
- end: `0x18013b0b3`
- name: `?IntfCreateContext@@YAKAEBU_GUID@@PEBG1W4_WLAN_INTERFACE_TYPE@@PEAPEAX@Z`
- size: `1603`
- prototype: `unsigned int __usercall@<eax>(const struct _GUID *@<rcx>, const unsigned __int16 *@<rdx>, const unsigned __int16 *@<r8>, enum _WLAN_INTERFACE_TYPE@<r9d>, void **)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x18011babc`

## callees

- `0x18000aa0c`
- `0x18000c5a0`
- `0x180011530`
- `0x180029ca0`
- `0x18002f450`
- `0x1800489a4`
- `0x1800a44c4`
- `0x180107330`
- `0x18013aa70`
- `0x180148900`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18013afb0`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18013afc9`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18013afb0`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18013afc9`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18013acff`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18013ad12`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18013acff`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18013ad12`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18013ad26`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18013ad8b`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18013adda`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18013ad26`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18013ad8b`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18013adda`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18013ab84`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18013ad38`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18013ad9d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18013adec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18013ab84`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18013ad38`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18013ad9d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18013adec`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18013b020`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18013b039`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18013b052`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18013b020`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18013b039`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18013b052`
- `MobileNetworking!HtNewHandle` at `0x18013ae46`
- `MobileNetworking!HtNewHandle` at `0x18013ae46`

## pseudocode

```c
__int64 __fastcall IntfCreateContext(
        const struct _GUID *a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        enum _WLAN_INTERFACE_TYPE a4,
        void **a5)
{
  char v8; // r12
  PVOID *v9; // rcx
  char *v10; // rbx
  DWORD LastError; // esi
  char *v12; // rax
  _QWORD *v13; // rcx
  __int64 v14; // rdx
  __int64 v15; // rsi
  __int64 v16; // rax
  unsigned __int16 *v17; // rax
  HANDLE EventW; // rax
  DWORD v19; // eax
  __int64 v20; // rdx
  HANDLE v21; // rax
  HANDLE v22; // rax
  __int64 v23; // rcx
  void *v24; // rcx
  void *v25; // rcx
  void *v26; // rcx
  char v28; // [rsp+31h] [rbp-37h]

  v28 = 0;
  v8 = 0;
  v9 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 37, &WPP_ddf81be17d3f38632d423248857aa840_Traceguids);
    v9 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( a5 )
  {
    if ( v9 != &WPP_GLOBAL_Control && *((_BYTE *)v9 + 105) >= 4u && (*((_BYTE *)v9 + 108) & 1) != 0 )
      WPP_SF_S_guid_d((TRACEHANDLE)v9[12], (__int64)a1, a4);
    v12 = (char *)AllocWLMem(0x1708u);
    v10 = v12;
    if ( !v12 )
    {
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || !*((_BYTE *)WPP_GLOBAL_Control + 105)
        || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) == 0 )
      {
        goto LABEL_21;
      }
      v14 = 40;
LABEL_20:
      WPP_SF_(v13[12], v14, &WPP_ddf81be17d3f38632d423248857aa840_Traceguids);
LABEL_21:
      LastError = GetLastError();
LABEL_22:
      v9 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_59;
    }
    memset_0(v12, 0, 0x1708u);
    *((_DWORD *)v10 + 806) = 4;
    *(struct _GUID *)(v10 + 8) = *a1;
    *((_OWORD *)v10 + 2) = *(_OWORD *)a2;
    *((_OWORD *)v10 + 3) = *((_OWORD *)a2 + 1);
    *((_OWORD *)v10 + 4) = *((_OWORD *)a2 + 2);
    *((_OWORD *)v10 + 5) = *((_OWORD *)a2 + 3);
    *((_OWORD *)v10 + 6) = *((_OWORD *)a2 + 4);
    *(_OWORD *)(v10 + 108) = *(_OWORD *)(a2 + 38);
    *((_DWORD *)v10 + 7) = a4;
    v15 = -1;
    v16 = -1;
    do
      ++v16;
    while ( a3[v16] );
    v17 = (unsigned __int16 *)AllocWLMem(2LL * (unsigned int)(v16 + 1));
    *((_QWORD *)v10 + 16) = v17;
    if ( !v17 )
    {
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || !*((_BYTE *)WPP_GLOBAL_Control + 105)
        || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) == 0 )
      {
        goto LABEL_21;
      }
      v14 = 41;
      goto LABEL_20;
    }
    do
      ++v15;
    while ( a3[v15] );
    if ( (int)StringCchCopyW(v17, (unsigned int)(v15 + 1), a3) < 0 )
    {
      v9 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 105)
        && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 42, &WPP_ddf81be17d3f38632d423248857aa840_Traceguids);
        v9 = (PVOID *)WPP_GLOBAL_Control;
      }
      LastError = 13;
      goto LABEL_60;
    }
    *((_QWORD *)v10 + 93) = v10 + 736;
    *((_QWORD *)v10 + 92) = v10 + 736;
    *((_QWORD *)v10 + 95) = v10 + 752;
    *((_QWORD *)v10 + 94) = v10 + 752;
    *((_QWORD *)v10 + 104) = v10 + 824;
    *((_QWORD *)v10 + 103) = v10 + 824;
    *((_QWORD *)v10 + 400) = v10 + 3192;
    *((_QWORD *)v10 + 399) = v10 + 3192;
    *((_QWORD *)v10 + 402) = v10 + 3208;
    *((_QWORD *)v10 + 401) = v10 + 3208;
    *((_QWORD *)v10 + 309) = v10 + 2464;
    *((_QWORD *)v10 + 308) = v10 + 2464;
    InitializeCriticalSection((LPCRITICAL_SECTION)(v10 + 144));
    v28 = 1;
    InitializeCriticalSection((LPCRITICAL_SECTION)(v10 + 2288));
    v8 = 1;
    EventW = CreateEventW(0, 0, 0, 0);
    *((_QWORD *)v10 + 33) = EventW;
    if ( EventW )
    {
      v21 = CreateEventW(0, 0, 0, 0);
      *((_QWORD *)v10 + 184) = v21;
      if ( v21 )
      {
        v22 = CreateEventW(0, 0, 0, 0);
        *((_QWORD *)v10 + 183) = v22;
        if ( v22 )
        {
          v19 = HtNewHandle(g_hHandleTable, v10, 1448036676, IntfDestroyContext, 1, v10);
          LastError = v19;
          if ( !v19 )
          {
            TrInitTraceHeader(1, 32, 50, v10 + 144, v10 + 3280);
            TrInitTraceHeader(4, 96, 10, v10 + 144, v10 + 3288);
            TrInitTraceHeader(2, 32, 50, v10 + 144, v10 + 3296);
            *a5 = *(void **)v10;
            goto LABEL_22;
          }
          v9 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && *((_BYTE *)WPP_GLOBAL_Control + 105)
            && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
          {
            v20 = 48;
            goto LABEL_42;
          }
        }
        else
        {
          v19 = GetLastError();
          LastError = v19;
          v9 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && *((_BYTE *)WPP_GLOBAL_Control + 105)
            && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
          {
            v20 = 47;
            goto LABEL_42;
          }
        }
      }
      else
      {
        v19 = GetLastError();
        LastError = v19;
        v9 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && *((_BYTE *)WPP_GLOBAL_Control + 105)
          && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
        {
          v20 = 46;
          goto LABEL_42;
        }
      }
    }
    else
    {
      v19 = GetLastError();
      LastError = v19;
      v9 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 105)
        && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
      {
        v20 = 45;
LABEL_42:
        WPP_SF_d(v9[12], v20, &WPP_ddf81be17d3f38632d423248857aa840_Traceguids, v19);
        goto LABEL_22;
      }
    }
LABEL_59:
    if ( !LastError )
      goto LABEL_74;
    goto LABEL_60;
  }
  v10 = 0;
  if ( v9 != &WPP_GLOBAL_Control && *((_BYTE *)v9 + 105) && (*((_BYTE *)v9 + 108) & 1) != 0 )
  {
    WPP_SF_(v9[12], 38, &WPP_ddf81be17d3f38632d423248857aa840_Traceguids);
    v9 = (PVOID *)WPP_GLOBAL_Control;
  }
  LastError = 87;
LABEL_60:
  if ( v28 )
  {
    DeleteCriticalSection((LPCRITICAL_SECTION)(v10 + 144));
    v9 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v8 )
  {
    DeleteCriticalSection((LPCRITICAL_SECTION)(v10 + 2288));
    v9 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v10 )
  {
    TrDeinitTraceHeader((struct _WLAN_TRACE_HEADER **)v10 + 410);
    TrDeinitTraceHeader((struct _WLAN_TRACE_HEADER **)v10 + 411);
    TrDeinitTraceHeader((struct _WLAN_TRACE_HEADER **)v10 + 412);
    v23 = *((_QWORD *)v10 + 16);
    if ( v23 )
      FreeWLMem(v23);
    v24 = (void *)*((_QWORD *)v10 + 183);
    if ( v24 )
    {
      CloseHandle(v24);
      *((_QWORD *)v10 + 183) = 0;
    }
    v25 = (void *)*((_QWORD *)v10 + 184);
    if ( v25 )
    {
      CloseHandle(v25);
      *((_QWORD *)v10 + 184) = 0;
    }
    v26 = (void *)*((_QWORD *)v10 + 33);
    if ( v26 )
    {
      CloseHandle(v26);
      *((_QWORD *)v10 + 33) = 0;
    }
    FreeWLMem(v10);
    v9 = (PVOID *)WPP_GLOBAL_Control;
  }
LABEL_74:
  if ( v9 != &WPP_GLOBAL_Control && *((_BYTE *)v9 + 105) >= 4u && (*((_BYTE *)v9 + 108) & 1) != 0 )
    WPP_SF_d(v9[12], 49, &WPP_ddf81be17d3f38632d423248857aa840_Traceguids, LastError);
  return LastError;
}

```

## disassembly

```asm
0x18013aa70  mov     [rsp+arg_0], rbx
0x18013aa75  mov     [rsp+arg_10], rsi
0x18013aa7a  mov     [rsp+arg_8], rdx
0x18013aa7f  push    rdi
0x18013aa80  push    r12
0x18013aa82  push    r13
0x18013aa84  push    r14
0x18013aa86  push    r15
0x18013aa88  sub     rsp, 40h
0x18013aa8c  mov     esi, r9d
0x18013aa8f  mov     r15, r8
0x18013aa92  mov     r13, rcx
0x18013aa95  xor     edi, edi
0x18013aa97  mov     [rsp+68h+var_37], dil
0x18013aa9c  mov     r12b, dil
0x18013aa9f  lea     r14, WPP_GLOBAL_Control
0x18013aaa6  mov     rcx, cs:WPP_GLOBAL_Control
0x18013aaad  cmp     rcx, r14
0x18013aab0  jz      short loc_18013AAD8
0x18013aab2  cmp     byte ptr [rcx+69h], 4
0x18013aab6  jb      short loc_18013AAD8
0x18013aab8  test    byte ptr [rcx+6Ch], 1
0x18013aabc  jz      short loc_18013AAD8
0x18013aabe  lea     edx, [rdi+25h]
0x18013aac1  lea     r8, WPP_ddf81be17d3f38632d423248857aa840_Traceguids
0x18013aac8  mov     rcx, [rcx+60h]
0x18013aacc  call    WPP_SF_
0x18013aad1  mov     rcx, cs:WPP_GLOBAL_Control
0x18013aad8  cmp     [rsp+68h+arg_20], rdi
0x18013aae0  jnz     short loc_18013AB1C
0x18013aae2  mov     rbx, rdi
0x18013aae5  cmp     rcx, r14
0x18013aae8  jz      short loc_18013AB12
0x18013aaea  cmp     byte ptr [rcx+69h], 1
0x18013aaee  jb      short loc_18013AB12
0x18013aaf0  test    byte ptr [rcx+6Ch], 1
0x18013aaf4  jz      short loc_18013AB12
0x18013aaf6  mov     edx, 26h ; '&'
0x18013aafb  lea     r8, WPP_ddf81be17d3f38632d423248857aa840_Traceguids
0x18013ab02  mov     rcx, [rcx+60h]
0x18013ab06  call    WPP_SF_
0x18013ab0b  mov     rcx, cs:WPP_GLOBAL_Control
0x18013ab12  mov     esi, 57h ; 'W'
0x18013ab17  jmp     loc_18013AFA2
0x18013ab1c  cmp     rcx, r14
0x18013ab1f  jz      short loc_18013AB42
0x18013ab21  cmp     byte ptr [rcx+69h], 4
0x18013ab25  jb      short loc_18013AB42
0x18013ab27  test    byte ptr [rcx+6Ch], 1
0x18013ab2b  jz      short loc_18013AB42
0x18013ab2d  mov     dword ptr [rsp+68h+var_40], esi; char
0x18013ab31  mov     [rsp+68h+var_48], r13; __int64
0x18013ab36  mov     r9, r15
0x18013ab39  mov     rcx, [rcx+60h]; LoggerHandle
0x18013ab3d  call    WPP_SF_S_guid_d
0x18013ab42  mov     ecx, 1708h; dwBytes
0x18013ab47  call    AllocWLMem
0x18013ab4c  mov     rbx, rax
0x18013ab4f  mov     [rsp+68h+var_30], rax
0x18013ab54  test    rax, rax
0x18013ab57  jnz     short loc_18013AB98
0x18013ab59  mov     rcx, cs:WPP_GLOBAL_Control
0x18013ab60  cmp     rcx, r14
0x18013ab63  jz      short loc_18013AB84
0x18013ab65  cmp     byte ptr [rcx+69h], 1
0x18013ab69  jb      short loc_18013AB84
0x18013ab6b  test    byte ptr [rcx+6Ch], 1
0x18013ab6f  jz      short loc_18013AB84
0x18013ab71  lea     edx, [rax+28h]
0x18013ab74  lea     r8, WPP_ddf81be17d3f38632d423248857aa840_Traceguids
0x18013ab7b  mov     rcx, [rcx+60h]
0x18013ab7f  call    WPP_SF_
0x18013ab84  call    cs:__imp_GetLastError
0x18013ab8a  mov     esi, eax
0x18013ab8c  mov     rcx, cs:WPP_GLOBAL_Control
0x18013ab93  jmp     loc_18013AF9A
0x18013ab98  xor     edx, edx; Val
0x18013ab9a  mov     r8d, 1708h; Size
0x18013aba0  mov     rcx, rbx; void *
0x18013aba3  call    memset_0
0x18013aba8  mov     dword ptr [rbx+0C98h], 4
0x18013abb2  movups  xmm0, xmmword ptr [r13+0]
0x18013abb7  movdqu  xmmword ptr [rbx+8], xmm0
0x18013abbc  mov     rax, [rsp+68h+arg_8]
0x18013abc1  movups  xmm0, xmmword ptr [rax]
0x18013abc4  movups  xmmword ptr [rbx+20h], xmm0
0x18013abc8  movups  xmm1, xmmword ptr [rax+10h]
0x18013abcc  movups  xmmword ptr [rbx+30h], xmm1
0x18013abd0  movups  xmm0, xmmword ptr [rax+20h]
0x18013abd4  movups  xmmword ptr [rbx+40h], xmm0
0x18013abd8  movups  xmm1, xmmword ptr [rax+30h]
0x18013abdc  movups  xmmword ptr [rbx+50h], xmm1
0x18013abe0  movups  xmm0, xmmword ptr [rax+40h]
0x18013abe4  movups  xmmword ptr [rbx+60h], xmm0
0x18013abe8  movups  xmm1, xmmword ptr [rax+4Ch]
0x18013abec  movups  xmmword ptr [rbx+6Ch], xmm1
0x18013abf0  mov     [rbx+1Ch], esi
0x18013abf3  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18013abf7  mov     rax, rsi
0x18013abfa  inc     rax
0x18013abfd  cmp     [r15+rax*2], di
0x18013ac02  jnz     short loc_18013ABFA
0x18013ac04  lea     ecx, [rax+1]
0x18013ac07  add     rcx, rcx; dwBytes
0x18013ac0a  call    AllocWLMem
0x18013ac0f  mov     rcx, rax; unsigned __int16 *
0x18013ac12  mov     [rbx+80h], rax
0x18013ac19  test    rax, rax
0x18013ac1c  jnz     short loc_18013AC4A
0x18013ac1e  mov     rcx, cs:WPP_GLOBAL_Control
0x18013ac25  cmp     rcx, r14
0x18013ac28  jz      loc_18013AB84
0x18013ac2e  cmp     byte ptr [rcx+69h], 1
0x18013ac32  jb      loc_18013AB84
0x18013ac38  test    byte ptr [rcx+6Ch], 1
0x18013ac3c  jz      loc_18013AB84
0x18013ac42  lea     edx, [rax+29h]
0x18013ac45  jmp     loc_18013AB74
0x18013ac4a  inc     rsi
0x18013ac4d  cmp     [r15+rsi*2], di
0x18013ac52  jnz     short loc_18013AC4A
0x18013ac54  lea     edx, [rsi+1]; unsigned __int64
0x18013ac57  mov     r8, r15; unsigned __int16 *
0x18013ac5a  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18013ac5f  test    eax, eax
0x18013ac61  jns     short loc_18013ACA1
0x18013ac63  mov     rcx, cs:WPP_GLOBAL_Control
0x18013ac6a  cmp     rcx, r14
0x18013ac6d  jz      short loc_18013AC97
0x18013ac6f  cmp     byte ptr [rcx+69h], 1
0x18013ac73  jb      short loc_18013AC97
0x18013ac75  test    byte ptr [rcx+6Ch], 1
0x18013ac79  jz      short loc_18013AC97
0x18013ac7b  mov     edx, 2Ah ; '*'
0x18013ac80  lea     r8, WPP_ddf81be17d3f38632d423248857aa840_Traceguids
0x18013ac87  mov     rcx, [rcx+60h]
0x18013ac8b  call    WPP_SF_
0x18013ac90  mov     rcx, cs:WPP_GLOBAL_Control
0x18013ac97  mov     esi, 0Dh
0x18013ac9c  jmp     loc_18013AFA2
0x18013aca1  lea     rax, [rbx+2E0h]
0x18013aca8  mov     [rax+8], rax
0x18013acac  mov     [rax], rax
0x18013acaf  lea     rax, [rbx+2F0h]
0x18013acb6  mov     [rax+8], rax
0x18013acba  mov     [rax], rax
0x18013acbd  lea     rax, [rbx+338h]
0x18013acc4  mov     [rax+8], rax
0x18013acc8  mov     [rax], rax
0x18013accb  lea     rax, [rbx+0C78h]
0x18013acd2  mov     [rax+8], rax
0x18013acd6  mov     [rax], rax
0x18013acd9  lea     rax, [rbx+0C88h]
0x18013ace0  mov     [rax+8], rax
0x18013ace4  mov     [rax], rax
0x18013ace7  lea     rax, [rbx+9A0h]
0x18013acee  mov     [rax+8], rax
0x18013acf2  mov     [rax], rax
0x18013acf5  lea     r15, [rbx+90h]
0x18013acfc  mov     rcx, r15; lpCriticalSection
0x18013acff  call    cs:__imp_InitializeCriticalSection
0x18013ad05  nop
0x18013ad06  mov     [rsp+68h+var_37], 1
0x18013ad0b  lea     rcx, [rbx+8F0h]; lpCriticalSection
0x18013ad12  call    cs:__imp_InitializeCriticalSection
0x18013ad18  nop
0x18013ad19  mov     r12b, 1
0x18013ad1c  xor     r9d, r9d; lpName
0x18013ad1f  xor     r8d, r8d; bInitialState
0x18013ad22  xor     edx, edx; bManualReset
0x18013ad24  xor     ecx, ecx; lpEventAttributes
0x18013ad26  call    cs:__imp_CreateEventW
0x18013ad2c  mov     [rbx+108h], rax
0x18013ad33  test    rax, rax
0x18013ad36  jnz     short loc_18013AD81
0x18013ad38  call    cs:__imp_GetLastError
0x18013ad3e  mov     esi, eax
0x18013ad40  mov     rcx, cs:WPP_GLOBAL_Control
0x18013ad47  cmp     rcx, r14
0x18013ad4a  jz      loc_18013AF9A
0x18013ad50  cmp     [rcx+69h], r12b
0x18013ad54  jb      loc_18013AF9A
0x18013ad5a  test    [rcx+6Ch], r12b
0x18013ad5e  jz      loc_18013AF9A
0x18013ad64  mov     edx, 2Dh ; '-'
0x18013ad69  mov     r9d, eax
0x18013ad6c  lea     r8, WPP_ddf81be17d3f38632d423248857aa840_Traceguids
0x18013ad73  mov     rcx, [rcx+60h]
0x18013ad77  call    WPP_SF_d
0x18013ad7c  jmp     loc_18013AB8C
0x18013ad81  xor     r9d, r9d; lpName
0x18013ad84  xor     r8d, r8d; bInitialState
0x18013ad87  xor     edx, edx; bManualReset
0x18013ad89  xor     ecx, ecx; lpEventAttributes
0x18013ad8b  call    cs:__imp_CreateEventW
0x18013ad91  mov     [rbx+5C0h], rax
0x18013ad98  test    rax, rax
0x18013ad9b  jnz     short loc_18013ADD0
0x18013ad9d  call    cs:__imp_GetLastError
0x18013ada3  mov     esi, eax
0x18013ada5  mov     rcx, cs:WPP_GLOBAL_Control
0x18013adac  cmp     rcx, r14
0x18013adaf  jz      loc_18013AF9A
0x18013adb5  cmp     [rcx+69h], r12b
0x18013adb9  jb      loc_18013AF9A
0x18013adbf  test    [rcx+6Ch], r12b
0x18013adc3  jz      loc_18013AF9A
0x18013adc9  mov     edx, 2Eh ; '.'
0x18013adce  jmp     short loc_18013AD69
0x18013add0  xor     r9d, r9d; lpName
0x18013add3  xor     r8d, r8d; bInitialState
0x18013add6  xor     edx, edx; bManualReset
0x18013add8  xor     ecx, ecx; lpEventAttributes
0x18013adda  call    cs:__imp_CreateEventW
0x18013ade0  mov     [rbx+5B8h], rax
0x18013ade7  test    rax, rax
0x18013adea  jnz     short loc_18013AE22
0x18013adec  call    cs:__imp_GetLastError
0x18013adf2  mov     esi, eax
0x18013adf4  mov     rcx, cs:WPP_GLOBAL_Control
0x18013adfb  cmp     rcx, r14
0x18013adfe  jz      loc_18013AF9A
0x18013ae04  cmp     [rcx+69h], r12b
0x18013ae08  jb      loc_18013AF9A
0x18013ae0e  test    [rcx+6Ch], r12b
0x18013ae12  jz      loc_18013AF9A
0x18013ae18  mov     edx, 2Fh ; '/'
0x18013ae1d  jmp     loc_18013AD69
0x18013ae22  mov     qword ptr [rsp+68h+var_40], rbx
0x18013ae27  mov     dword ptr [rsp+68h+var_48], 1
0x18013ae2f  lea     r9, ?IntfDestroyContext@@YAKPEAX@Z; IntfDestroyContext(void *)
0x18013ae36  mov     r8d, 564F4944h
0x18013ae3c  mov     rdx, rbx
0x18013ae3f  mov     rcx, cs:?g_hHandleTable@@3PEAXEA; void * g_hHandleTable
0x18013ae46  call    cs:__imp_HtNewHandle
0x18013ae4c  mov     esi, eax
0x18013ae4e  test    eax, eax
0x18013ae50  jz      short loc_18013AE80
0x18013ae52  mov     rcx, cs:WPP_GLOBAL_Control
0x18013ae59  cmp     rcx, r14
0x18013ae5c  jz      loc_18013AF9A
0x18013ae62  cmp     [rcx+69h], r12b
0x18013ae66  jb      loc_18013AF9A
0x18013ae6c  test    [rcx+6Ch], r12b
0x18013ae70  jz      loc_18013AF9A
0x18013ae76  mov     edx, 30h ; '0'
0x18013ae7b  jmp     loc_18013AD69
0x18013ae80  lea     rax, [rbx+0CD0h]
0x18013ae87  mov     [rsp+68h+var_48], rax
0x18013ae8c  mov     r9, r15
0x18013ae8f  mov     r8d, 32h ; '2'
0x18013ae95  lea     r13d, [r8-12h]
0x18013ae99  mov     edx, r13d
0x18013ae9c  lea     ecx, [r8-31h]
0x18013aea0  call    ?TrInitTraceHeader@@YAKW4_WLAN_TRACE_TYPE@@KKPEAU_RTL_CRITICAL_SECTION@@PEAPEAU_WLAN_TRACE_HEADER@@@Z; TrInitTraceHeader(_WLAN_TRACE_TYPE,ulong,ulong,_RTL_CRITICAL_SECTION *,_WLAN_TRACE_HEADER * *)
0x18013aea5  lea     rax, [rbx+0CD8h]
0x18013aeac  mov     [rsp+68h+var_48], rax
0x18013aeb1  mov     r9, r15
0x18013aeb4  lea     edx, [r13+40h]
0x18013aeb8  lea     ecx, [rdx-5Ch]
0x18013aebb  lea     r8d, [r13-16h]
0x18013aebf  call    ?TrInitTraceHeader@@YAKW4_WLAN_TRACE_TYPE@@KKPEAU_RTL_CRITICAL_SECTION@@PEAPEAU_WLAN_TRACE_HEADER@@@Z; TrInitTraceHeader(_WLAN_TRACE_TYPE,ulong,ulong,_RTL_CRITICAL_SECTION *,_WLAN_TRACE_HEADER * *)
0x18013aec4  lea     rax, [rbx+0CE0h]
0x18013aecb  mov     [rsp+68h+var_48], rax
0x18013aed0  mov     r9, r15
0x18013aed3  lea     r8d, [r13+12h]
0x18013aed7  mov     edx, r13d
0x18013aeda  lea     ecx, [r13-1Eh]
0x18013aede  call    ?TrInitTraceHeader@@YAKW4_WLAN_TRACE_TYPE@@KKPEAU_RTL_CRITICAL_SECTION@@PEAPEAU_WLAN_TRACE_HEADER@@@Z; TrInitTraceHeader(_WLAN_TRACE_TYPE,ulong,ulong,_RTL_CRITICAL_SECTION *,_WLAN_TRACE_HEADER * *)
0x18013aee3  mov     rax, [rbx]
0x18013aee6  mov     rcx, [rsp+68h+arg_20]
0x18013aeee  mov     [rcx], rax
0x18013aef1  jmp     loc_18013AB8C
0x18013aef6  mov     esi, eax
0x18013aef8  lea     rax, WPP_GLOBAL_Control
0x18013aeff  mov     rcx, cs:WPP_GLOBAL_Control
0x18013af06  cmp     rcx, rax
0x18013af09  jz      short loc_18013AF36
0x18013af0b  cmp     byte ptr [rcx+69h], 1
0x18013af0f  jb      short loc_18013AF36
0x18013af11  test    byte ptr [rcx+6Ch], 1
0x18013af15  jz      short loc_18013AF36
0x18013af17  mov     edx, 2Ch ; ','
0x18013af1c  mov     r9d, esi
0x18013af1f  lea     r8, WPP_ddf81be17d3f38632d423248857aa840_Traceguids
0x18013af26  mov     rcx, [rcx+60h]
0x18013af2a  call    WPP_SF_d
0x18013af2f  mov     rcx, cs:WPP_GLOBAL_Control
0x18013af36  xor     edi, edi
0x18013af38  lea     r14, WPP_GLOBAL_Control
0x18013af3f  mov     rbx, [rsp+68h+var_30]
0x18013af44  mov     r12b, dil
0x18013af47  jmp     short loc_18013AF9A
0x18013af49  mov     esi, eax
0x18013af4b  lea     rax, WPP_GLOBAL_Control
0x18013af52  mov     rcx, cs:WPP_GLOBAL_Control
0x18013af59  cmp     rcx, rax
0x18013af5c  jz      short loc_18013AF89
0x18013af5e  cmp     byte ptr [rcx+69h], 1
0x18013af62  jb      short loc_18013AF89
  ... truncated ...
```
