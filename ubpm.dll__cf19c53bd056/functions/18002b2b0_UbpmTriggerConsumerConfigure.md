# UbpmTriggerConsumerConfigure

- ea: `0x18002b2b0`
- end: `0x18002b5ae`
- name: `UbpmTriggerConsumerConfigure`
- size: `766`
- prototype: `__int64 __fastcall(struct _UBPM_TRIGGER_CONSUMER_BLOCK *, char *)`
- caller_count: `0`
- callee_count: `15`
- tags: `registry_config, loader_planting`

## callees

- `0x180007c50`
- `0x180007e30`
- `0x18000a500`
- `0x18000a6e0`
- `0x18001311c`
- `0x1800138e0`
- `0x18001cccc`
- `0x18001e9f4`
- `0x1800270f0`
- `0x180027994`
- `0x180029470`
- `0x18002b2b0`
- `0x180032dd8`
- `0x18003d7de`
- `0x18003d810`

## import_xrefs

- `ntdll!RtlReleaseSRWLockExclusive` at `0x18002b3ed`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18002b426`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18002b4eb`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18002b53c`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18002b54d`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18002b3ed`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18002b426`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18002b4eb`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18002b53c`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18002b54d`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002b568`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002b568`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18002b57a`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18002b57a`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x18002b504`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x18002b504`

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
  v4 = UbpmConsumerIncPendingActions(a1);
  if ( !v4 )
  {
    v5 = 0;
    UBPM_ACQUIRE_SRWLOCK_EXCLUSIVE((struct _UBPM_TRIGGER_CONSUMER_BLOCK *)((char *)a1 + 312));
    UBPM_ACQUIRE_SRWLOCK_EXCLUSIVE((struct _UBPM_TRIGGER_CONSUMER_BLOCK *)((char *)a1 + 48));
    v8 = (char *)a1 + 24;
    if ( (unsigned int)dword_18004C0F0 > 4 )
    {
      v9 = *(_QWORD *)v8;
      v18 = *a2;
      v19[0] = (*(_BYTE *)(v9 + 16) & 1) == 0;
      v20 = *(void **)(v9 + 8);
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>>(
        v9,
        (unsigned int)&word_180042E8E,
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
          UbpmConsumerDecPendingActions(a1);
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
0x18002b2b0  mov     [rsp+arg_8], rbx
0x18002b2b5  mov     [rsp+arg_10], rbp
0x18002b2ba  push    rsi
0x18002b2bb  push    rdi
0x18002b2bc  push    r12
0x18002b2be  push    r14
0x18002b2c0  push    r15
0x18002b2c2  sub     rsp, 0F0h
0x18002b2c9  mov     rax, cs:__security_cookie
0x18002b2d0  xor     rax, rsp
0x18002b2d3  mov     [rsp+118h+var_38], rax
0x18002b2db  mov     r12, rdx
0x18002b2de  mov     rdi, rcx
0x18002b2e1  xor     edx, edx; Val
0x18002b2e3  lea     rcx, [rsp+118h+var_C8]; void *
0x18002b2e8  mov     r8d, 88h; Size
0x18002b2ee  call    memset_0
0x18002b2f3  lea     rcx, [rsp+118h+var_C8]; lpTlsValue
0x18002b2f8  call    ?UbpmUtilsStartLockTracking@@YAXPEAU_CEM_LOCK_TRACKER@@@Z; UbpmUtilsStartLockTracking(_CEM_LOCK_TRACKER *)
0x18002b2fd  mov     rcx, rdi
0x18002b300  call    UbpmConsumerIncPendingActions
0x18002b305  mov     ebp, eax
0x18002b307  test    eax, eax
0x18002b309  jnz     loc_18002B55B
0x18002b30f  lea     r14, [rdi+138h]
0x18002b316  xor     r15b, r15b
0x18002b319  mov     rcx, r14; struct _UBPM_SRWLOCK *
0x18002b31c  call    ?UBPM_ACQUIRE_SRWLOCK_EXCLUSIVE@@YAXAEAU_UBPM_SRWLOCK@@@Z; UBPM_ACQUIRE_SRWLOCK_EXCLUSIVE(_UBPM_SRWLOCK &)
0x18002b321  lea     rcx, [rdi+30h]; struct _UBPM_SRWLOCK *
0x18002b325  call    ?UBPM_ACQUIRE_SRWLOCK_EXCLUSIVE@@YAXAEAU_UBPM_SRWLOCK@@@Z; UBPM_ACQUIRE_SRWLOCK_EXCLUSIVE(_UBPM_SRWLOCK &)
0x18002b32a  mov     ecx, cs:dword_18004C0F0
0x18002b330  lea     rbx, [rdi+18h]
0x18002b334  cmp     ecx, 4
0x18002b337  jbe     short loc_18002B382
0x18002b339  mov     al, [r12]
0x18002b33d  lea     rdx, word_180042E8E
0x18002b344  mov     rcx, [rbx]
0x18002b347  mov     [rsp+118h+var_D8], al
0x18002b34b  mov     al, [rcx+10h]
0x18002b34e  not     al
0x18002b350  and     al, 1
0x18002b352  mov     [rsp+118h+var_D7], al
0x18002b356  mov     rax, [rcx+8]
0x18002b35a  mov     [rsp+118h+var_D0], rax
0x18002b35f  lea     rax, [rsp+118h+var_D8]
0x18002b364  mov     [rsp+118h+var_E8], rax
0x18002b369  lea     rax, [rsp+118h+var_D7]
0x18002b36e  mov     [rsp+118h+var_F0], rax
0x18002b373  lea     rax, [rsp+118h+var_D0]
0x18002b378  mov     [rsp+118h+var_F8], rax
0x18002b37d  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$00@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$00@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<1> const &)
0x18002b382  mov     rdx, [rbx]
0x18002b385  mov     ecx, [rdx+10h]
0x18002b388  mov     eax, ecx
0x18002b38a  and     eax, 1
0x18002b38d  cmp     [r12], r15b
0x18002b391  jz      short loc_18002B40E
0x18002b393  test    eax, eax
0x18002b395  jz      loc_18002B41B
0x18002b39b  mov     rcx, rdi; struct _UBPM_TRIGGER_CONSUMER_BLOCK *
0x18002b39e  call    UbpmConsumerEnable
0x18002b3a3  mov     ebp, eax
0x18002b3a5  test    eax, eax
0x18002b3a7  jz      short loc_18002B41B
0x18002b3a9  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b3b0  lea     rsi, WPP_GLOBAL_Control
0x18002b3b7  cmp     rcx, rsi
0x18002b3ba  jz      short loc_18002B3E2
0x18002b3bc  test    byte ptr [rcx+1Ch], 1
0x18002b3c0  jz      short loc_18002B3E2
0x18002b3c2  mov     r9, [rbx]
0x18002b3c5  lea     r8, WPP_854cad5030553c91fcf88b43a20977bf_Traceguids
0x18002b3cc  mov     rcx, [rcx+10h]
0x18002b3d0  mov     edx, 20h ; ' '
0x18002b3d5  mov     dword ptr [rsp+118h+var_F8], eax
0x18002b3d9  mov     r9, [r9+8]
0x18002b3dd  call    WPP_SF_Sd
0x18002b3e2  lea     rcx, [rdi+30h]
0x18002b3e6  mov     dword ptr [rcx+8], 0
0x18002b3ed  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18002b3f3  mov     rcx, rdi
0x18002b3f6  call    UbpmConsumerDisable
0x18002b3fb  lea     rcx, [rdi+138h]
0x18002b402  mov     dword ptr [rcx+8], 0
0x18002b409  jmp     loc_18002B54D
0x18002b40e  test    eax, eax
0x18002b410  jnz     short loc_18002B41B
0x18002b412  or      ecx, 1
0x18002b415  mov     r15b, 1
0x18002b418  mov     [rdx+10h], ecx
0x18002b41b  lea     rcx, [rdi+30h]
0x18002b41f  mov     dword ptr [rcx+8], 0
0x18002b426  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18002b42c  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b433  lea     rsi, WPP_GLOBAL_Control
0x18002b43a  cmp     rcx, rsi
0x18002b43d  jz      short loc_18002B484
0x18002b43f  test    byte ptr [rcx+1Ch], 4
0x18002b443  jz      short loc_18002B484
0x18002b445  mov     r9, [rbx]
0x18002b448  lea     rdx, aDisabled; "DISABLED"
0x18002b44f  cmp     byte ptr [r12], 0
0x18002b454  lea     rax, aEnabled; "ENABLED"
0x18002b45b  mov     rcx, [rcx+10h]
0x18002b45f  lea     r8, WPP_854cad5030553c91fcf88b43a20977bf_Traceguids
0x18002b466  cmovz   rax, rdx
0x18002b46a  mov     edx, 21h ; '!'
0x18002b46f  mov     r9, [r9+8]
0x18002b473  mov     [rsp+118h+var_F8], rax
0x18002b478  call    WPP_SF_SS
0x18002b47d  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b484  test    r15b, r15b
0x18002b487  jz      loc_18002B542
0x18002b48d  cmp     rcx, rsi
0x18002b490  jz      short loc_18002B4B4
0x18002b492  test    byte ptr [rcx+1Ch], 4
0x18002b496  jz      short loc_18002B4B4
0x18002b498  mov     r9, [rbx]
0x18002b49b  lea     r8, WPP_854cad5030553c91fcf88b43a20977bf_Traceguids
0x18002b4a2  mov     rcx, [rcx+10h]
0x18002b4a6  mov     edx, 22h ; '"'
0x18002b4ab  mov     r9, [r9+8]
0x18002b4af  call    WPP_SF_S
0x18002b4b4  lea     rbx, [rdi+0D0h]
0x18002b4bb  mov     rcx, rbx; struct _UBPM_SRWLOCK *
0x18002b4be  call    ?UBPM_ACQUIRE_SRWLOCK_EXCLUSIVE@@YAXAEAU_UBPM_SRWLOCK@@@Z; UBPM_ACQUIRE_SRWLOCK_EXCLUSIVE(_UBPM_SRWLOCK &)
0x18002b4c3  mov     rax, [rdi+120h]
0x18002b4ca  mov     rcx, rbx
0x18002b4cd  mov     byte ptr [rdi+128h], 1
0x18002b4d4  mov     [rsp+118h+var_D0], rax
0x18002b4d9  mov     qword ptr [rdi+120h], 0
0x18002b4e4  mov     dword ptr [rbx+8], 0
0x18002b4eb  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18002b4f1  mov     rcx, rdi
0x18002b4f4  call    UbpmConsumerDisable
0x18002b4f9  mov     rcx, [rdi+70h]; ptpcg
0x18002b4fd  xor     r8d, r8d; pvCleanupContext
0x18002b500  lea     edx, [r8+1]; fCancelPendingCallbacks
0x18002b504  call    cs:__imp_CloseThreadpoolCleanupGroupMembers
0x18002b50a  xor     edx, edx; unsigned __int8
0x18002b50c  lea     rcx, [rsp+118h+var_D0]; void **
0x18002b511  call    ?UbpmUtilsFreeTimerContext@@YAXPEAPEAXE@Z; UbpmUtilsFreeTimerContext(void * *,uchar)
0x18002b516  mov     rcx, rbx; struct _UBPM_SRWLOCK *
0x18002b519  call    ?UBPM_ACQUIRE_SRWLOCK_EXCLUSIVE@@YAXAEAU_UBPM_SRWLOCK@@@Z; UBPM_ACQUIRE_SRWLOCK_EXCLUSIVE(_UBPM_SRWLOCK &)
0x18002b51e  xor     r8d, r8d
0x18002b521  xor     edx, edx
0x18002b523  mov     rcx, rdi
0x18002b526  call    UbpmpDrainActionQueue
0x18002b52b  mov     rcx, rbx
0x18002b52e  mov     byte ptr [rdi+128h], 0
0x18002b535  mov     dword ptr [rbx+8], 0
0x18002b53c  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18002b542  mov     dword ptr [r14+8], 0
0x18002b54a  mov     rcx, r14
0x18002b54d  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18002b553  mov     rcx, rdi
0x18002b556  call    UbpmConsumerDecPendingActions
0x18002b55b  mov     ebx, cs:UbpmpLockTrackerId
0x18002b561  cmp     ebx, 0FFFFFFFFh
0x18002b564  jz      short loc_18002B580
0x18002b566  mov     ecx, ebx; dwTlsIndex
0x18002b568  call    cs:__imp_TlsGetValue
0x18002b56e  cmp     qword ptr [rax], 0
0x18002b572  jz      short loc_18002B576
0x18002b574  int     2Ch; Windows NT - assertion failure
0x18002b576  xor     edx, edx; lpTlsValue
0x18002b578  mov     ecx, ebx; dwTlsIndex
0x18002b57a  call    cs:__imp_TlsSetValue
0x18002b580  mov     eax, ebp
0x18002b582  mov     rcx, [rsp+118h+var_38]
0x18002b58a  xor     rcx, rsp; StackCookie
0x18002b58d  call    __security_check_cookie
0x18002b592  lea     r11, [rsp+118h+var_28]
0x18002b59a  mov     rbx, [r11+38h]
0x18002b59e  mov     rbp, [r11+40h]
0x18002b5a2  mov     rsp, r11
0x18002b5a5  pop     r15
0x18002b5a7  pop     r14
0x18002b5a9  pop     r12
0x18002b5ab  pop     rdi
0x18002b5ac  pop     rsi
0x18002b5ad  retn
```
