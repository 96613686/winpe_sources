# UbpmTriggerConsumerConfigure

- ea: `0x18002d260`
- end: `0x18002d593`
- name: `UbpmTriggerConsumerConfigure`
- size: `819`
- prototype: `__int64 __fastcall(struct _UBPM_TRIGGER_CONSUMER_BLOCK *)`
- caller_count: `0`
- callee_count: `15`
- tags: `registry_config, loader_planting`

## callees

- `0x180002d30`
- `0x180008720`
- `0x180008920`
- `0x18000eb68`
- `0x1800101a0`
- `0x1800103c0`
- `0x180015b90`
- `0x18001af64`
- `0x18002b4a0`
- `0x18002c05c`
- `0x18002cff4`
- `0x18002d260`
- `0x180035184`
- `0x18004022e`
- `0x180040260`

## import_xrefs

- `ntdll!RtlReleaseSRWLockExclusive` at `0x18002d3a1`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18002d3e0`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18002d4ab`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18002d508`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18002d51f`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18002d3a1`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18002d3e0`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18002d4ab`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18002d508`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18002d51f`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002d540`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002d540`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18002d558`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18002d558`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x18002d4ca`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x18002d4ca`

## pseudocode

```c
__int64 __fastcall UbpmTriggerConsumerConfigure(struct _UBPM_TRIGGER_CONSUMER_BLOCK *a1, char *a2)
{
  unsigned int v4; // ebp
  char v5; // r15
  int v6; // r8d
  int v7; // r9d
  char *v8; // rbx
  __int64 v9; // rcx
  int v10; // eax
  unsigned int v11; // eax
  char *v12; // rcx
  PVOID *v13; // rcx
  const wchar_t *v14; // rax
  void *v15; // rax
  DWORD v16; // ebx
  char v18; // [rsp+40h] [rbp-D8h] BYREF
  bool v19[7]; // [rsp+41h] [rbp-D7h] BYREF
  void *v20; // [rsp+48h] [rbp-D0h] BYREF
  _BYTE v21[144]; // [rsp+50h] [rbp-C8h] BYREF

  memset_0(v21, 0, 0x88u);
  UbpmUtilsStartLockTracking((struct _CEM_LOCK_TRACKER *)v21);
  v4 = UbpmConsumerIncPendingActions((__int64)a1);
  if ( !v4 )
  {
    v5 = 0;
    UBPM_ACQUIRE_SRWLOCK_EXCLUSIVE((struct _UBPM_TRIGGER_CONSUMER_BLOCK *)((char *)a1 + 312));
    UBPM_ACQUIRE_SRWLOCK_EXCLUSIVE((struct _UBPM_TRIGGER_CONSUMER_BLOCK *)((char *)a1 + 48));
    v8 = (char *)a1 + 24;
    if ( (unsigned int)dword_18004F0F0 > 4 )
    {
      v9 = *(_QWORD *)v8;
      v18 = *a2;
      v19[0] = (*(_BYTE *)(v9 + 16) & 1) == 0;
      v20 = *(void **)(v9 + 8);
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>>(
        v9,
        (unsigned int)&word_180045EF6,
        v6,
        v7,
        (__int64)&v20,
        (__int64)v19,
        (__int64)&v18);
    }
    v10 = *(_DWORD *)(*(_QWORD *)v8 + 16LL) & 1;
    if ( *a2 )
    {
      if ( v10 )
      {
        v11 = UbpmConsumerEnable(a1);
        v4 = v11;
        if ( v11 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_Sd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              32,
              (unsigned int)&WPP_854cad5030553c91fcf88b43a20977bf_Traceguids,
              *(_QWORD *)(*(_QWORD *)v8 + 8LL),
              v11);
          *((_DWORD *)a1 + 14) = 0;
          RtlReleaseSRWLockExclusive((char *)a1 + 48);
          UbpmConsumerDisable(a1);
          v12 = (char *)a1 + 312;
          *((_DWORD *)a1 + 80) = 0;
LABEL_24:
          RtlReleaseSRWLockExclusive(v12);
          UbpmConsumerDecPendingActions((__int64)a1);
          goto LABEL_25;
        }
      }
    }
    else if ( !v10 )
    {
      v5 = 1;
      *(_DWORD *)(*(_QWORD *)v8 + 16LL) |= 1u;
    }
    *((_DWORD *)a1 + 14) = 0;
    RtlReleaseSRWLockExclusive((char *)a1 + 48);
    v13 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      v14 = L"ENABLED";
      if ( !*a2 )
        v14 = L"DISABLED";
      WPP_SF_SS(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        33,
        (unsigned int)&WPP_854cad5030553c91fcf88b43a20977bf_Traceguids,
        *(_QWORD *)(*(_QWORD *)v8 + 8LL),
        (__int64)v14);
      v13 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v5 )
    {
      if ( v13 != &WPP_GLOBAL_Control && (*((_BYTE *)v13 + 28) & 4) != 0 )
        WPP_SF_S(v13[2], 34, &WPP_854cad5030553c91fcf88b43a20977bf_Traceguids, *(_QWORD *)(*(_QWORD *)v8 + 8LL));
      UBPM_ACQUIRE_SRWLOCK_EXCLUSIVE((struct _UBPM_TRIGGER_CONSUMER_BLOCK *)((char *)a1 + 208));
      v15 = (void *)*((_QWORD *)a1 + 36);
      *((_BYTE *)a1 + 296) = 1;
      v20 = v15;
      *((_QWORD *)a1 + 36) = 0;
      *((_DWORD *)a1 + 54) = 0;
      RtlReleaseSRWLockExclusive((char *)a1 + 208);
      UbpmConsumerDisable(a1);
      CloseThreadpoolCleanupGroupMembers(*((PTP_CLEANUP_GROUP *)a1 + 14), 1, 0);
      UbpmUtilsFreeTimerContext(&v20, 0);
      UBPM_ACQUIRE_SRWLOCK_EXCLUSIVE((struct _UBPM_TRIGGER_CONSUMER_BLOCK *)((char *)a1 + 208));
      UbpmpDrainActionQueue(a1, 0, 0);
      *((_BYTE *)a1 + 296) = 0;
      *((_DWORD *)a1 + 54) = 0;
      RtlReleaseSRWLockExclusive((char *)a1 + 208);
    }
    *((_DWORD *)a1 + 80) = 0;
    v12 = (char *)a1 + 312;
    goto LABEL_24;
  }
LABEL_25:
  v16 = UbpmpLockTrackerId;
  if ( UbpmpLockTrackerId != -1 )
  {
    if ( *(_QWORD *)TlsGetValue(UbpmpLockTrackerId) )
      __int2c();
    TlsSetValue(v16, 0);
  }
  return v4;
}

```

## disassembly

```asm
0x18002d260  mov     [rsp+arg_8], rbx
0x18002d265  mov     [rsp+arg_10], rbp
0x18002d26a  push    rsi
0x18002d26b  push    rdi
0x18002d26c  push    r12
0x18002d26e  push    r14
0x18002d270  push    r15
0x18002d272  sub     rsp, 0F0h
0x18002d279  mov     rax, cs:__security_cookie
0x18002d280  xor     rax, rsp
0x18002d283  mov     [rsp+118h+var_38], rax
0x18002d28b  mov     r12, rdx
0x18002d28e  mov     rdi, rcx
0x18002d291  xor     edx, edx; Val
0x18002d293  lea     rcx, [rsp+118h+var_C8]; void *
0x18002d298  mov     r8d, 88h; Size
0x18002d29e  call    memset_0
0x18002d2a3  lea     rcx, [rsp+118h+var_C8]; lpTlsValue
0x18002d2a8  call    ?UbpmUtilsStartLockTracking@@YAXPEAU_CEM_LOCK_TRACKER@@@Z; UbpmUtilsStartLockTracking(_CEM_LOCK_TRACKER *)
0x18002d2ad  mov     rcx, rdi
0x18002d2b0  call    UbpmConsumerIncPendingActions
0x18002d2b5  mov     ebp, eax
0x18002d2b7  test    eax, eax
0x18002d2b9  jnz     loc_18002D533
0x18002d2bf  lea     r14, [rdi+138h]
0x18002d2c6  xor     r15b, r15b
0x18002d2c9  mov     rcx, r14; struct _UBPM_SRWLOCK *
0x18002d2cc  call    ?UBPM_ACQUIRE_SRWLOCK_EXCLUSIVE@@YAXAEAU_UBPM_SRWLOCK@@@Z; UBPM_ACQUIRE_SRWLOCK_EXCLUSIVE(_UBPM_SRWLOCK &)
0x18002d2d1  lea     rcx, [rdi+30h]; struct _UBPM_SRWLOCK *
0x18002d2d5  call    ?UBPM_ACQUIRE_SRWLOCK_EXCLUSIVE@@YAXAEAU_UBPM_SRWLOCK@@@Z; UBPM_ACQUIRE_SRWLOCK_EXCLUSIVE(_UBPM_SRWLOCK &)
0x18002d2da  mov     ecx, cs:dword_18004F0F0
0x18002d2e0  lea     rbx, [rdi+18h]
0x18002d2e4  cmp     ecx, 4
0x18002d2e7  jbe     short loc_18002D332
0x18002d2e9  mov     al, [r12]
0x18002d2ed  lea     rdx, word_180045EF6
0x18002d2f4  mov     rcx, [rbx]
0x18002d2f7  mov     [rsp+118h+var_D8], al
0x18002d2fb  mov     al, [rcx+10h]
0x18002d2fe  not     al
0x18002d300  and     al, 1
0x18002d302  mov     [rsp+118h+var_D7], al
0x18002d306  mov     rax, [rcx+8]
0x18002d30a  mov     [rsp+118h+var_D0], rax
0x18002d30f  lea     rax, [rsp+118h+var_D8]
0x18002d314  mov     [rsp+118h+var_E8], rax
0x18002d319  lea     rax, [rsp+118h+var_D7]
0x18002d31e  mov     [rsp+118h+var_F0], rax
0x18002d323  lea     rax, [rsp+118h+var_D0]
0x18002d328  mov     [rsp+118h+var_F8], rax
0x18002d32d  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$00@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$00@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<1> const &)
0x18002d332  mov     rdx, [rbx]
0x18002d335  mov     ecx, [rdx+10h]
0x18002d338  mov     eax, ecx
0x18002d33a  and     eax, 1
0x18002d33d  cmp     [r12], r15b
0x18002d341  jz      loc_18002D3C8
0x18002d347  test    eax, eax
0x18002d349  jz      loc_18002D3D5
0x18002d34f  mov     rcx, rdi; struct _UBPM_TRIGGER_CONSUMER_BLOCK *
0x18002d352  call    UbpmConsumerEnable
0x18002d357  mov     ebp, eax
0x18002d359  test    eax, eax
0x18002d35b  jz      short loc_18002D3D5
0x18002d35d  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d364  lea     rsi, WPP_GLOBAL_Control
0x18002d36b  cmp     rcx, rsi
0x18002d36e  jz      short loc_18002D396
0x18002d370  test    byte ptr [rcx+1Ch], 1
0x18002d374  jz      short loc_18002D396
0x18002d376  mov     r9, [rbx]
0x18002d379  lea     r8, WPP_854cad5030553c91fcf88b43a20977bf_Traceguids
0x18002d380  mov     rcx, [rcx+10h]
0x18002d384  mov     edx, 20h ; ' '
0x18002d389  mov     dword ptr [rsp+118h+var_F8], eax
0x18002d38d  mov     r9, [r9+8]
0x18002d391  call    WPP_SF_Sd
0x18002d396  lea     rcx, [rdi+30h]
0x18002d39a  mov     dword ptr [rcx+8], 0
0x18002d3a1  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18002d3a8  nop     dword ptr [rax+rax+00h]
0x18002d3ad  mov     rcx, rdi
0x18002d3b0  call    UbpmConsumerDisable
0x18002d3b5  lea     rcx, [rdi+138h]
0x18002d3bc  mov     dword ptr [rcx+8], 0
0x18002d3c3  jmp     loc_18002D51F
0x18002d3c8  test    eax, eax
0x18002d3ca  jnz     short loc_18002D3D5
0x18002d3cc  or      ecx, 1
0x18002d3cf  mov     r15b, 1
0x18002d3d2  mov     [rdx+10h], ecx
0x18002d3d5  lea     rcx, [rdi+30h]
0x18002d3d9  mov     dword ptr [rcx+8], 0
0x18002d3e0  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18002d3e7  nop     dword ptr [rax+rax+00h]
0x18002d3ec  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d3f3  lea     rsi, WPP_GLOBAL_Control
0x18002d3fa  cmp     rcx, rsi
0x18002d3fd  jz      short loc_18002D444
0x18002d3ff  test    byte ptr [rcx+1Ch], 4
0x18002d403  jz      short loc_18002D444
0x18002d405  mov     r9, [rbx]
0x18002d408  lea     rdx, aDisabled; "DISABLED"
0x18002d40f  cmp     byte ptr [r12], 0
0x18002d414  lea     rax, aEnabled; "ENABLED"
0x18002d41b  mov     rcx, [rcx+10h]
0x18002d41f  lea     r8, WPP_854cad5030553c91fcf88b43a20977bf_Traceguids
0x18002d426  cmovz   rax, rdx
0x18002d42a  mov     edx, 21h ; '!'
0x18002d42f  mov     r9, [r9+8]
0x18002d433  mov     [rsp+118h+var_F8], rax
0x18002d438  call    WPP_SF_SS
0x18002d43d  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d444  test    r15b, r15b
0x18002d447  jz      loc_18002D514
0x18002d44d  cmp     rcx, rsi
0x18002d450  jz      short loc_18002D474
0x18002d452  test    byte ptr [rcx+1Ch], 4
0x18002d456  jz      short loc_18002D474
0x18002d458  mov     r9, [rbx]
0x18002d45b  lea     r8, WPP_854cad5030553c91fcf88b43a20977bf_Traceguids
0x18002d462  mov     rcx, [rcx+10h]
0x18002d466  mov     edx, 22h ; '"'
0x18002d46b  mov     r9, [r9+8]
0x18002d46f  call    WPP_SF_S
0x18002d474  lea     rbx, [rdi+0D0h]
0x18002d47b  mov     rcx, rbx; struct _UBPM_SRWLOCK *
0x18002d47e  call    ?UBPM_ACQUIRE_SRWLOCK_EXCLUSIVE@@YAXAEAU_UBPM_SRWLOCK@@@Z; UBPM_ACQUIRE_SRWLOCK_EXCLUSIVE(_UBPM_SRWLOCK &)
0x18002d483  mov     rax, [rdi+120h]
0x18002d48a  mov     rcx, rbx
0x18002d48d  mov     byte ptr [rdi+128h], 1
0x18002d494  mov     [rsp+118h+var_D0], rax
0x18002d499  mov     qword ptr [rdi+120h], 0
0x18002d4a4  mov     dword ptr [rbx+8], 0
0x18002d4ab  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18002d4b2  nop     dword ptr [rax+rax+00h]
0x18002d4b7  mov     rcx, rdi
0x18002d4ba  call    UbpmConsumerDisable
0x18002d4bf  mov     rcx, [rdi+70h]; ptpcg
0x18002d4c3  xor     r8d, r8d; pvCleanupContext
0x18002d4c6  lea     edx, [r8+1]; fCancelPendingCallbacks
0x18002d4ca  call    cs:__imp_CloseThreadpoolCleanupGroupMembers
0x18002d4d1  nop     dword ptr [rax+rax+00h]
0x18002d4d6  xor     edx, edx; unsigned __int8
0x18002d4d8  lea     rcx, [rsp+118h+var_D0]; void **
0x18002d4dd  call    ?UbpmUtilsFreeTimerContext@@YAXPEAPEAXE@Z; UbpmUtilsFreeTimerContext(void * *,uchar)
0x18002d4e2  mov     rcx, rbx; struct _UBPM_SRWLOCK *
0x18002d4e5  call    ?UBPM_ACQUIRE_SRWLOCK_EXCLUSIVE@@YAXAEAU_UBPM_SRWLOCK@@@Z; UBPM_ACQUIRE_SRWLOCK_EXCLUSIVE(_UBPM_SRWLOCK &)
0x18002d4ea  xor     r8d, r8d
0x18002d4ed  xor     edx, edx
0x18002d4ef  mov     rcx, rdi
0x18002d4f2  call    UbpmpDrainActionQueue
0x18002d4f7  mov     rcx, rbx
0x18002d4fa  mov     byte ptr [rdi+128h], 0
0x18002d501  mov     dword ptr [rbx+8], 0
0x18002d508  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18002d50f  nop     dword ptr [rax+rax+00h]
0x18002d514  mov     dword ptr [r14+8], 0
0x18002d51c  mov     rcx, r14
0x18002d51f  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18002d526  nop     dword ptr [rax+rax+00h]
0x18002d52b  mov     rcx, rdi
0x18002d52e  call    UbpmConsumerDecPendingActions
0x18002d533  mov     ebx, cs:UbpmpLockTrackerId
0x18002d539  cmp     ebx, 0FFFFFFFFh
0x18002d53c  jz      short loc_18002D564
0x18002d53e  mov     ecx, ebx; dwTlsIndex
0x18002d540  call    cs:__imp_TlsGetValue
0x18002d547  nop     dword ptr [rax+rax+00h]
0x18002d54c  cmp     qword ptr [rax], 0
0x18002d550  jz      short loc_18002D554
0x18002d552  int     2Ch; Windows NT - assertion failure
0x18002d554  xor     edx, edx; lpTlsValue
0x18002d556  mov     ecx, ebx; dwTlsIndex
0x18002d558  call    cs:__imp_TlsSetValue
0x18002d55f  nop     dword ptr [rax+rax+00h]
0x18002d564  mov     eax, ebp
0x18002d566  mov     rcx, [rsp+118h+var_38]
0x18002d56e  xor     rcx, rsp; StackCookie
0x18002d571  call    __security_check_cookie
0x18002d576  lea     r11, [rsp+118h+var_28]
0x18002d57e  mov     rbx, [r11+38h]
0x18002d582  mov     rbp, [r11+40h]
0x18002d586  mov     rsp, r11
0x18002d589  pop     r15
0x18002d58b  pop     r14
0x18002d58d  pop     r12
0x18002d58f  pop     rdi
0x18002d590  pop     rsi
0x18002d591  retn
```
