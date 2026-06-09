# CTSThread::Initialize(void)

- ea: `0x18003b320`
- end: `0x18003b61a`
- name: `?Initialize@CTSThread@@UEAAJXZ`
- size: `762`
- prototype: `__int64 __fastcall(CTSThread *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x180037b30`

## callees

- `0x1800010b0`
- `0x18000adf8`
- `0x18000b98c`
- `0x18001b348`
- `0x18001bae0`
- `0x1800399f8`
- `0x180039b44`
- `0x180039c90`
- `0x18003b320`
- `0x18003ebcc`

## string_xrefs

- `0x18003b464`: `onecore\termsrv\rdpplatform\common\devplatform\platform\thread.cpp`
- `0x18003b38c`: `Failed to create thread signal event`
- `0x18003b51e`: `CTSSyncWaitResult::CreateInstancePool failed!`
- `0x18003b571`: `CTSMsg::CreateInstancePool failed!`
- `0x18003b5b8`: `CTSBufferResult::CreateInstancePool failed!`
- `0x18003b5ff`: `Failed to create ITSThreadInternal`

## pseudocode

```c
__int64 __fastcall CTSThread::Initialize(CTSThread *this)
{
  int Instance; // ebx
  int ActivityIdPrefix; // eax
  int v4; // edx
  const char *v5; // rcx
  __int64 v6; // r8
  __int64 v7; // rdx
  __int64 v8; // rdx
  __int64 v9; // rdx
  __int64 v10; // rcx
  int v11; // r8d
  int v12; // r9d
  __int64 v13; // rdx
  __int64 v14; // rcx
  __int64 v15; // rdx
  __int64 v16; // rcx
  __int64 v17; // rdx
  __int64 v18; // rcx
  const char *v20; // [rsp+50h] [rbp-28h] BYREF
  int v21; // [rsp+80h] [rbp+8h] BYREF
  int v22; // [rsp+88h] [rbp+10h] BYREF
  const char *v23; // [rsp+90h] [rbp+18h] BYREF
  const char *v24; // [rsp+98h] [rbp+20h] BYREF

  *((_QWORD *)this + 83) = 0;
  *((_QWORD *)this + 84) = -1;
  Instance = PAL_System_CondAlloc(1);
  if ( Instance >= 0 )
  {
    *((_QWORD *)this + 75) = 0;
    *((_QWORD *)this + 24) = (char *)this + 208;
    v6 = 0;
    *((_DWORD *)this + 50) = 8;
    *((_QWORD *)this + 26) = 0;
    do
    {
      v7 = v6 + 2 * v6 + 1;
      ++v6;
      v8 = *((_QWORD *)this + 24) + 8 * v7;
      *(_QWORD *)(v8 + 8) = *((_QWORD *)this + 23);
      *((_QWORD *)this + 23) = v8;
    }
    while ( v6 != 16 );
    *((_DWORD *)this + 32) = -1;
    if ( (unsigned int)CTSCriticalSection::Initialize((CTSThread *)((char *)this + 88)) )
    {
      Instance = CTSObjectPool<CTSSyncWaitResult>::CreateInstance(v10, v9, (char *)this + 640);
      if ( Instance >= 0 )
      {
        Instance = CTSObjectPool<CTSMsg>::CreateInstance(v14, v13, (char *)this + 648);
        if ( Instance >= 0 )
        {
          Instance = CTSObjectPool<CTSBufferResult>::CreateInstance(v16, v15, (char *)this + 656);
          if ( Instance >= 0 )
          {
            Instance = CTSThreadInternal_CreateInstance(v18, v17, (char *)this + 720);
            if ( Instance >= 0 )
            {
              *((_DWORD *)this + 5) |= 2u;
              return 0;
            }
            if ( *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 8) != 0
              && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 2u )
            {
              ActivityIdPrefix = RdpX_GetActivityIdPrefix();
              v4 = 22;
              v5 = "Failed to create ITSThreadInternal";
              goto LABEL_6;
            }
          }
          else if ( *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                 && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 8) != 0
                 && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 2u )
          {
            ActivityIdPrefix = RdpX_GetActivityIdPrefix();
            v4 = 21;
            v5 = "CTSBufferResult::CreateInstancePool failed!";
            goto LABEL_6;
          }
        }
        else if ( *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
               && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 8) != 0
               && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 2u )
        {
          ActivityIdPrefix = RdpX_GetActivityIdPrefix();
          v4 = 20;
          v5 = "CTSMsg::CreateInstancePool failed!";
          goto LABEL_6;
        }
      }
      else if ( *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
             && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 8) != 0
             && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 2u )
      {
        ActivityIdPrefix = RdpX_GetActivityIdPrefix();
        v4 = 19;
        v5 = "CTSSyncWaitResult::CreateInstancePool failed!";
        goto LABEL_6;
      }
    }
    else
    {
      if ( (unsigned int)dword_18005C008 > 2 )
      {
        v21 = 199;
        v23 = "Initialize";
        v22 = -2147467259;
        v24 = "onecore\\termsrv\\rdpplatform\\common\\devplatform\\platform\\thread.cpp";
        v20 = "Fail to init lock queue";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          v10,
          (unsigned int)byte_180055885,
          v11,
          v12,
          (__int64)&v20,
          (__int64)&v22,
          (__int64)&v24,
          (__int64)&v21,
          (__int64)&v23);
      }
      return (unsigned int)-2147024882;
    }
  }
  else if ( *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
         && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 8) != 0
         && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 2u )
  {
    ActivityIdPrefix = RdpX_GetActivityIdPrefix();
    v4 = 17;
    v5 = "Failed to create thread signal event";
LABEL_6:
    WPP_SF_DsD(
      *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL),
      v4,
      (unsigned int)&WPP_903e1551464439edae082eb88b6439cd_Traceguids,
      ActivityIdPrefix,
      (__int64)v5,
      Instance);
  }
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x18003b320  push    rbx
0x18003b322  push    rdi
0x18003b323  sub     rsp, 68h
0x18003b327  mov     rdi, rcx
0x18003b32a  mov     qword ptr [rcx+298h], 0
0x18003b335  lea     rdx, [rcx+2B0h]
0x18003b33c  mov     qword ptr [rcx+2A0h], 0FFFFFFFFFFFFFFFFh
0x18003b347  mov     ecx, 1; bManualReset
0x18003b34c  call    PAL_System_CondAlloc
0x18003b351  mov     ebx, eax
0x18003b353  test    eax, eax
0x18003b355  jns     short loc_18003B3BB
0x18003b357  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b35e  lea     rax, WPP_GLOBAL_Control
0x18003b365  cmp     rcx, rax
0x18003b368  jz      loc_18003B611
0x18003b36e  test    byte ptr [rcx+1Ch], 8
0x18003b372  jz      loc_18003B611
0x18003b378  cmp     byte ptr [rcx+19h], 2
0x18003b37c  jb      loc_18003B611
0x18003b382  call    RdpX_GetActivityIdPrefix
0x18003b387  mov     edx, 11h
0x18003b38c  lea     rcx, aFailedToCreate; "Failed to create thread signal event"
0x18003b393  mov     dword ptr [rsp+78h+var_50], ebx
0x18003b397  lea     r8, WPP_903e1551464439edae082eb88b6439cd_Traceguids
0x18003b39e  mov     [rsp+78h+var_58], rcx
0x18003b3a3  mov     r9d, eax
0x18003b3a6  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b3ad  mov     rcx, [rcx+10h]
0x18003b3b1  call    WPP_SF_DsD
0x18003b3b6  jmp     loc_18003B611
0x18003b3bb  lea     rax, [rdi+0D0h]
0x18003b3c2  mov     qword ptr [rdi+258h], 0
0x18003b3cd  mov     [rdi+0C0h], rax
0x18003b3d4  xor     r8d, r8d
0x18003b3d7  mov     dword ptr [rdi+0C8h], 8
0x18003b3e1  mov     qword ptr [rax], 0
0x18003b3e8  mov     rax, [rdi+0C0h]
0x18003b3ef  lea     rdx, ds:1[r8*2]
0x18003b3f7  add     rdx, r8
0x18003b3fa  inc     r8
0x18003b3fd  lea     rdx, [rax+rdx*8]
0x18003b401  mov     rax, [rdi+0B8h]
0x18003b408  mov     [rdx+8], rax
0x18003b40c  mov     [rdi+0B8h], rdx
0x18003b413  cmp     r8, 10h
0x18003b417  jnz     short loc_18003B3E8
0x18003b419  lea     rcx, [rdi+58h]; this
0x18003b41d  mov     dword ptr [rdi+80h], 0FFFFFFFFh
0x18003b427  call    ?Initialize@CTSCriticalSection@@QEAAHXZ; CTSCriticalSection::Initialize(void)
0x18003b42c  test    eax, eax
0x18003b42e  jnz     loc_18003B4D7
0x18003b434  mov     eax, cs:dword_18005C008
0x18003b43a  cmp     eax, 2
0x18003b43d  jbe     loc_18003B4CD
0x18003b443  lea     rax, aInitialize; "Initialize"
0x18003b44a  mov     [rsp+78h+arg_0], 0C7h
0x18003b455  mov     [rsp+78h+arg_10], rax
0x18003b45d  lea     rdx, byte_180055885
0x18003b464  lea     rax, aOnecoreTermsrv_3; "onecore\\termsrv\\rdpplatform\\common\\"...
0x18003b46b  mov     [rsp+78h+arg_8], 80004005h
0x18003b476  mov     [rsp+78h+arg_18], rax
0x18003b47e  lea     rax, aFailToInitLock; "Fail to init lock queue"
0x18003b485  mov     [rsp+78h+var_28], rax
0x18003b48a  lea     rax, [rsp+78h+arg_10]
0x18003b492  mov     [rsp+78h+var_38], rax
0x18003b497  lea     rax, [rsp+78h+arg_0]
0x18003b49f  mov     [rsp+78h+var_40], rax
0x18003b4a4  lea     rax, [rsp+78h+arg_18]
0x18003b4ac  mov     [rsp+78h+var_48], rax
0x18003b4b1  lea     rax, [rsp+78h+arg_8]
0x18003b4b9  mov     [rsp+78h+var_50], rax
0x18003b4be  lea     rax, [rsp+78h+var_28]
0x18003b4c3  mov     [rsp+78h+var_58], rax
0x18003b4c8  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18003b4cd  mov     ebx, 8007000Eh
0x18003b4d2  jmp     loc_18003B611
0x18003b4d7  lea     r8, [rdi+280h]
0x18003b4de  call    ?CreateInstance@?$CTSObjectPool@VCTSSyncWaitResult@@@@SAJIIPEAPEAV1@H@Z; CTSObjectPool<CTSSyncWaitResult>::CreateInstance(uint,uint,CTSObjectPool<CTSSyncWaitResult> * *,int)
0x18003b4e3  mov     ebx, eax
0x18003b4e5  test    eax, eax
0x18003b4e7  jns     short loc_18003B52A
0x18003b4e9  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b4f0  lea     rax, WPP_GLOBAL_Control
0x18003b4f7  cmp     rcx, rax
0x18003b4fa  jz      loc_18003B611
0x18003b500  test    byte ptr [rcx+1Ch], 8
0x18003b504  jz      loc_18003B611
0x18003b50a  cmp     byte ptr [rcx+19h], 2
0x18003b50e  jb      loc_18003B611
0x18003b514  call    RdpX_GetActivityIdPrefix
0x18003b519  mov     edx, 13h
0x18003b51e  lea     rcx, aCtssyncwaitres_0; "CTSSyncWaitResult::CreateInstancePool f"...
0x18003b525  jmp     loc_18003B393
0x18003b52a  lea     r8, [rdi+288h]
0x18003b531  call    ?CreateInstance@?$CTSObjectPool@VCTSMsg@@@@SAJIIPEAPEAV1@H@Z; CTSObjectPool<CTSMsg>::CreateInstance(uint,uint,CTSObjectPool<CTSMsg> * *,int)
0x18003b536  mov     ebx, eax
0x18003b538  test    eax, eax
0x18003b53a  jns     short loc_18003B57D
0x18003b53c  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b543  lea     rax, WPP_GLOBAL_Control
0x18003b54a  cmp     rcx, rax
0x18003b54d  jz      loc_18003B611
0x18003b553  test    byte ptr [rcx+1Ch], 8
0x18003b557  jz      loc_18003B611
0x18003b55d  cmp     byte ptr [rcx+19h], 2
0x18003b561  jb      loc_18003B611
0x18003b567  call    RdpX_GetActivityIdPrefix
0x18003b56c  mov     edx, 14h
0x18003b571  lea     rcx, aCtsmsgCreatein; "CTSMsg::CreateInstancePool failed!"
0x18003b578  jmp     loc_18003B393
0x18003b57d  lea     r8, [rdi+290h]
0x18003b584  call    ?CreateInstance@?$CTSObjectPool@VCTSBufferResult@@@@SAJIIPEAPEAV1@H@Z; CTSObjectPool<CTSBufferResult>::CreateInstance(uint,uint,CTSObjectPool<CTSBufferResult> * *,int)
0x18003b589  mov     ebx, eax
0x18003b58b  test    eax, eax
0x18003b58d  jns     short loc_18003B5C4
0x18003b58f  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b596  lea     rax, WPP_GLOBAL_Control
0x18003b59d  cmp     rcx, rax
0x18003b5a0  jz      short loc_18003B611
0x18003b5a2  test    byte ptr [rcx+1Ch], 8
0x18003b5a6  jz      short loc_18003B611
0x18003b5a8  cmp     byte ptr [rcx+19h], 2
0x18003b5ac  jb      short loc_18003B611
0x18003b5ae  call    RdpX_GetActivityIdPrefix
0x18003b5b3  mov     edx, 15h
0x18003b5b8  lea     rcx, aCtsbufferresul_1; "CTSBufferResult::CreateInstancePool fai"...
0x18003b5bf  jmp     loc_18003B393
0x18003b5c4  lea     r8, [rdi+2D0h]
0x18003b5cb  call    CTSThreadInternal_CreateInstance
0x18003b5d0  mov     ebx, eax
0x18003b5d2  test    eax, eax
0x18003b5d4  jns     short loc_18003B60B
0x18003b5d6  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b5dd  lea     rax, WPP_GLOBAL_Control
0x18003b5e4  cmp     rcx, rax
0x18003b5e7  jz      short loc_18003B611
0x18003b5e9  test    byte ptr [rcx+1Ch], 8
0x18003b5ed  jz      short loc_18003B611
0x18003b5ef  cmp     byte ptr [rcx+19h], 2
0x18003b5f3  jb      short loc_18003B611
0x18003b5f5  call    RdpX_GetActivityIdPrefix
0x18003b5fa  mov     edx, 16h
0x18003b5ff  lea     rcx, aFailedToCreate_4; "Failed to create ITSThreadInternal"
0x18003b606  jmp     loc_18003B393
0x18003b60b  or      dword ptr [rdi+14h], 2
0x18003b60f  xor     ebx, ebx
0x18003b611  mov     eax, ebx
0x18003b613  add     rsp, 68h
0x18003b617  pop     rdi
0x18003b618  pop     rbx
0x18003b619  retn
```
