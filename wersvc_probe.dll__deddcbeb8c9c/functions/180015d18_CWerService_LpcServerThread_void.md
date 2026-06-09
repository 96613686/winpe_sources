# CWerService::LpcServerThread(void)

- ea: `0x180015d18`
- end: `0x180016312`
- name: `?LpcServerThread@CWerService@@AEAAXXZ`
- size: `1530`
- prototype: `void __fastcall(CWerService *__hidden this)`
- caller_count: `1`
- callee_count: `12`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180018910`

## callees

- `0x1800029d0`
- `0x1800035e8`
- `0x180006a80`
- `0x180011ef8`
- `0x180013df4`
- `0x180015d18`
- `0x18001c604`
- `0x18001d070`
- `0x18001d380`
- `0x18001d5cc`
- `0x18001d92c`
- `0x180034550`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180015dac`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180015e6d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180015eec`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180015f1c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180015dac`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180015e6d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180015eec`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180015f1c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180015e11`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180015f28`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180015f46`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800162e9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180015e11`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180015f28`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180015f46`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800162e9`
- `ntdll!NtClose` at `0x180016201`
- `ntdll!NtClose` at `0x180016201`
- `ntdll!NtAlpcSendWaitReceivePort` at `0x180015e5b`
- `ntdll!NtAlpcSendWaitReceivePort` at `0x180016148`
- `ntdll!NtAlpcSendWaitReceivePort` at `0x180015e5b`
- `ntdll!NtAlpcSendWaitReceivePort` at `0x180016148`
- `ntdll!AlpcInitializeMessageAttribute` at `0x180015dee`
- `ntdll!AlpcInitializeMessageAttribute` at `0x180015dee`
- `ntdll!AlpcGetMessageAttribute` at `0x180015e98`
- `ntdll!AlpcGetMessageAttribute` at `0x180015fc9`
- `ntdll!AlpcGetMessageAttribute` at `0x180015e98`
- `ntdll!AlpcGetMessageAttribute` at `0x180015fc9`

## pseudocode

```c
void __fastcall CWerService::LpcServerThread(CWerService *this)
{
  int v2; // r13d
  struct _RTL_CRITICAL_SECTION *v3; // rdi
  int v4; // esi
  __int64 *v5; // rcx
  int v6; // ebx
  int v7; // esi
  void **MessageAttribute; // rax
  void **v9; // rdi
  int v10; // r13d
  unsigned int v11; // r12d
  struct _RTL_CRITICAL_SECTION *v12; // rdi
  LONG LockCount; // ebx
  int v14; // eax
  void *v15; // r12
  int v16; // r15d
  __int64 v17; // rax
  __int64 v18; // rbx
  int v19; // eax
  _QWORD *v20; // rcx
  __int64 v21; // rdx
  HANDLE *v22; // rcx
  __int64 v23; // rdx
  int v24; // eax
  int v25; // eax
  int v26; // [rsp+40h] [rbp-C0h]
  __int64 v27; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v28; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v29; // [rsp+68h] [rbp-98h] BYREF
  _BYTE v30[4]; // [rsp+70h] [rbp-90h] BYREF
  int v31; // [rsp+74h] [rbp-8Ch]
  _BYTE Src[40]; // [rsp+110h] [rbp+10h] BYREF
  int v33; // [rsp+138h] [rbp+38h]
  _BYTE v34[40]; // [rsp+690h] [rbp+590h] BYREF
  __int64 v35; // [rsp+6B8h] [rbp+5B8h]

  memset_0(Src, 0, 0x578u);
  v27 = 0;
  if ( !*((_DWORD *)this + 54) )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  v27 = -10000LL * *((int *)this + 54);
  memset_0(v30, 0, 0xA0u);
  v2 = 1;
  v26 = 1;
  v3 = (struct _RTL_CRITICAL_SECTION *)this;
  EnterCriticalSection((LPCRITICAL_SECTION)this);
  if ( !*((_QWORD *)this + 49) )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  while ( 1 )
  {
    v28 = 0;
    v4 = AlpcInitializeMessageAttribute(805306369, v30, 160, &v28);
    if ( v4 < 0 )
      break;
    v29 = 1400;
    LeaveCriticalSection(v3);
    v5 = &v27;
    if ( *((_DWORD *)this + 54) == -1 )
      v5 = 0;
    v6 = NtAlpcSendWaitReceivePort(*((_QWORD *)this + 49), 0, 0, 0, Src, &v29, v30, v5);
    if ( !v3 )
      __int2c();
    EnterCriticalSection(v3);
    if ( v6 == -1073741758 )
      MicrosoftTelemetryAssertTriggeredNoArgs();
    v7 = v6 | 0x10000000;
    MessageAttribute = (void **)AlpcGetMessageAttribute(v30, 0x20000000);
    v9 = MessageAttribute;
    if ( v6 == 258 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 93, &WPP_fd0c3993e8f0396a73a01b4739c75d44_Traceguids);
      if ( !*((_DWORD *)this + 52) )
      {
        EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 416));
        if ( *((_QWORD *)this + 60) != -1 && *((_QWORD *)this + 60) != 0 )
          goto LABEL_22;
        v10 = 0;
        v11 = 0;
        if ( *((_DWORD *)this + 114) )
        {
          while ( 1 )
          {
            v12 = (struct _RTL_CRITICAL_SECTION *)(*((_QWORD *)this + 58) + 2456LL * v11);
            EnterCriticalSection(v12);
            LockCount = v12[1].LockCount;
            LeaveCriticalSection(v12);
            if ( LockCount )
              break;
            if ( ++v11 >= *((_DWORD *)this + 114) )
              goto LABEL_23;
          }
LABEL_22:
          v10 = 1;
        }
LABEL_23:
        LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 416));
        if ( !v10 )
        {
          v14 = *((_DWORD *)this + 53);
          if ( (v14 & 2) != 0 )
          {
            *((_DWORD *)this + 53) = v14 & 0xFFFFFFFD;
          }
          else
          {
            *((_DWORD *)this + 53) = v14 | 1;
            CWerService::_SignalStop(this);
          }
        }
        v2 = v26;
      }
    }
    else
    {
      if ( v6 >= 0 )
      {
        v15 = 0;
        v16 = Src[4];
        if ( (v31 & 0x10000000) != 0 )
        {
          v17 = AlpcGetMessageAttribute(v30, 0x10000000);
          v18 = v17;
          if ( v17 )
          {
            if ( *(_DWORD *)(v17 + 16) != 4 )
              MicrosoftTelemetryAssertTriggeredNoArgs();
            v15 = *(void **)(v18 + 8);
          }
        }
        if ( v16 == 1 )
        {
          v24 = CWerService::_ProcessRequest(this, (struct _WERSVC_MSG *)Src);
          v7 = v24;
          if ( v24 >= 0 )
          {
            if ( v33 == 2 )
            {
              memcpy_0(v34, Src, 0x578u);
              v35 = 2;
              NtAlpcSendWaitReceivePort(*((_QWORD *)this + 49), 0x10000, v34, 0, 0, 0, 0, 0);
              v2 = 0;
              v26 = 0;
            }
            goto LABEL_70;
          }
          v22 = (HANDLE *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              94,
              &WPP_fd0c3993e8f0396a73a01b4739c75d44_Traceguids,
              (unsigned int)v24);
            v22 = (HANDLE *)WPP_GLOBAL_Control;
          }
          if ( v9 )
          {
            v19 = CWerService::_CloseConnection(this, *v9);
            v7 = v19;
            if ( v19 >= 0 )
              goto LABEL_70;
            v20 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
              goto LABEL_70;
            v21 = 95;
LABEL_65:
            WPP_SF_d(v20[2], v21, &WPP_fd0c3993e8f0396a73a01b4739c75d44_Traceguids, (unsigned int)v19);
            goto LABEL_70;
          }
          if ( v22 == &WPP_GLOBAL_Control || (*((_BYTE *)v22 + 28) & 2) == 0 )
            goto LABEL_70;
          v23 = 96;
        }
        else
        {
          if ( v16 != 5 && v16 != 6 )
          {
            if ( v16 == 7 )
            {
              v7 = CWerService::_ProcessLpcExceptionMessage(this, (struct _WERSVC_MSG *)Src, v15);
              goto LABEL_27;
            }
            if ( v16 == 10 )
            {
              v19 = CWerService::_ProcessConnectionRequest(this, (struct _WERSVC_MSG *)Src);
              v7 = v19;
              if ( v19 < 0 )
              {
                v20 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
                {
                  v21 = 97;
                  goto LABEL_65;
                }
              }
            }
LABEL_70:
            if ( v15 )
              NtClose(v15);
            goto LABEL_27;
          }
          if ( v9 )
          {
            v19 = CWerService::_CloseConnection(this, *v9);
            v7 = v19;
            if ( v19 >= 0 )
              goto LABEL_70;
            v20 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
              goto LABEL_70;
            v21 = 98;
            goto LABEL_65;
          }
          v22 = (HANDLE *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
            goto LABEL_70;
          v23 = 99;
        }
        WPP_SF_(v22[2], v23, &WPP_fd0c3993e8f0396a73a01b4739c75d44_Traceguids);
        goto LABEL_70;
      }
      if ( v7 == -805306357 )
      {
        if ( MessageAttribute )
        {
          v25 = CWerService::_CloseConnection(this, *MessageAttribute);
          v7 = v25;
          if ( v25 < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              100,
              &WPP_fd0c3993e8f0396a73a01b4739c75d44_Traceguids,
              (unsigned int)v25);
        }
        else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 101, &WPP_fd0c3993e8f0396a73a01b4739c75d44_Traceguids);
        }
      }
    }
LABEL_27:
    if ( !v2 )
      goto LABEL_84;
    v3 = (struct _RTL_CRITICAL_SECTION *)this;
  }
  v7 = v4 | 0x10000000;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      92,
      &WPP_fd0c3993e8f0396a73a01b4739c75d44_Traceguids,
      (unsigned int)v7);
LABEL_84:
  if ( v7 < 0 )
    CWerService::_SignalStop(this);
  LeaveCriticalSection((LPCRITICAL_SECTION)this);
}

```

## disassembly

```asm
0x180015d18  push    rbp
0x180015d1a  push    rbx
0x180015d1b  push    rsi
0x180015d1c  push    rdi
0x180015d1d  push    r12
0x180015d1f  push    r13
0x180015d21  push    r14
0x180015d23  push    r15
0x180015d25  lea     rbp, [rsp-0B28h]
0x180015d2d  sub     rsp, 0C28h
0x180015d34  mov     rax, cs:__security_cookie
0x180015d3b  xor     rax, rsp
0x180015d3e  mov     [rbp+0B60h+var_50], rax
0x180015d45  mov     r14, rcx
0x180015d48  xor     edx, edx; Val
0x180015d4a  mov     r8d, 578h; Size
0x180015d50  lea     rcx, [rbp+0B60h+Src]; void *
0x180015d54  call    memset_0
0x180015d59  mov     [rsp+0C60h+var_C08], 0
0x180015d62  cmp     dword ptr [r14+0D8h], 0
0x180015d6a  jnz     short loc_180015D71
0x180015d6c  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180015d71  movsxd  rax, dword ptr [r14+0D8h]
0x180015d78  imul    rcx, rax, 0FFFFFFFFFFFFD8F0h
0x180015d7f  mov     [rsp+0C60h+var_C08], rcx
0x180015d84  xor     edx, edx; Val
0x180015d86  mov     r8d, 0A0h; Size
0x180015d8c  lea     rcx, [rsp+0C60h+var_BF0]; void *
0x180015d91  call    memset_0
0x180015d96  mov     r13d, 1
0x180015d9c  mov     [rsp+0C60h+var_C20], r13d
0x180015da1  mov     rdi, r14
0x180015da4  mov     [rsp+0C60h+lpCriticalSection], r14
0x180015da9  mov     rcx, r14; lpCriticalSection
0x180015dac  call    cs:__imp_EnterCriticalSection
0x180015db2  mov     r15b, r13b
0x180015db5  mov     [rsp+0C60h+var_C10], r13b
0x180015dba  cmp     qword ptr [r14+188h], 0
0x180015dc2  jnz     short loc_180015DC9
0x180015dc4  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180015dc9  lea     r12, WPP_GLOBAL_Control
0x180015dd0  mov     [rsp+0C60h+var_C00], 0
0x180015dd9  lea     r9, [rsp+0C60h+var_C00]
0x180015dde  mov     r8d, 0A0h
0x180015de4  lea     rdx, [rsp+0C60h+var_BF0]
0x180015de9  mov     ecx, 30000001h
0x180015dee  call    cs:__imp_AlpcInitializeMessageAttribute
0x180015df4  mov     esi, eax
0x180015df6  test    eax, eax
0x180015df8  js      loc_18001629D
0x180015dfe  mov     [rsp+0C60h+var_BF8], 578h
0x180015e07  test    r15b, r15b
0x180015e0a  jnz     short loc_180015E0E
0x180015e0c  int     2Ch; Windows NT - assertion failure
0x180015e0e  mov     rcx, rdi; lpCriticalSection
0x180015e11  call    cs:__imp_LeaveCriticalSection
0x180015e17  lea     rcx, [rsp+0C60h+var_C08]
0x180015e1c  xor     eax, eax
0x180015e1e  cmp     dword ptr [r14+0D8h], 0FFFFFFFFh
0x180015e26  cmovz   rcx, rax
0x180015e2a  mov     [rsp+0C60h+var_C28], rcx
0x180015e2f  lea     rax, [rsp+0C60h+var_BF0]
0x180015e34  mov     [rsp+0C60h+var_C30], rax
0x180015e39  lea     rax, [rsp+0C60h+var_BF8]
0x180015e3e  mov     [rsp+0C60h+var_C38], rax
0x180015e43  lea     rax, [rbp+0B60h+Src]
0x180015e47  mov     [rsp+0C60h+var_C40], rax
0x180015e4c  xor     r9d, r9d
0x180015e4f  xor     r8d, r8d
0x180015e52  xor     edx, edx
0x180015e54  mov     rcx, [r14+188h]
0x180015e5b  call    cs:__imp_NtAlpcSendWaitReceivePort
0x180015e61  mov     ebx, eax
0x180015e63  test    rdi, rdi
0x180015e66  jnz     short loc_180015E6A
0x180015e68  int     2Ch; Windows NT - assertion failure
0x180015e6a  mov     rcx, rdi; lpCriticalSection
0x180015e6d  call    cs:__imp_EnterCriticalSection
0x180015e73  mov     r15b, 1
0x180015e76  mov     [rsp+0C60h+var_C10], r15b
0x180015e7b  cmp     ebx, 0C0000042h
0x180015e81  jnz     short loc_180015E88
0x180015e83  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180015e88  mov     esi, ebx
0x180015e8a  bts     esi, 1Ch
0x180015e8e  mov     edx, 20000000h
0x180015e93  lea     rcx, [rsp+0C60h+var_BF0]
0x180015e98  call    cs:__imp_AlpcGetMessageAttribute
0x180015e9e  mov     rdi, rax
0x180015ea1  cmp     ebx, 102h
0x180015ea7  jnz     loc_180015F9C
0x180015ead  mov     rcx, cs:WPP_GLOBAL_Control
0x180015eb4  cmp     rcx, r12
0x180015eb7  jz      short loc_180015ED4
0x180015eb9  test    byte ptr [rcx+1Ch], 4
0x180015ebd  jz      short loc_180015ED4
0x180015ebf  mov     edx, 5Dh ; ']'
0x180015ec4  lea     r8, WPP_fd0c3993e8f0396a73a01b4739c75d44_Traceguids
0x180015ecb  mov     rcx, [rcx+10h]
0x180015ecf  call    WPP_SF_
0x180015ed4  cmp     dword ptr [r14+0D0h], 0
0x180015edc  jnz     loc_180015F70
0x180015ee2  lea     r15, [r14+1A0h]
0x180015ee9  mov     rcx, r15; lpCriticalSection
0x180015eec  call    cs:__imp_EnterCriticalSection
0x180015ef2  mov     rax, [r15+40h]
0x180015ef6  inc     rax
0x180015ef9  cmp     rax, 1
0x180015efd  ja      short loc_180015F3D
0x180015eff  xor     r13d, r13d
0x180015f02  xor     r12d, r12d
0x180015f05  cmp     [r15+28h], r12d
0x180015f09  jbe     short loc_180015F43
0x180015f0b  mov     eax, r12d
0x180015f0e  imul    rdi, rax, 998h
0x180015f15  add     rdi, [r15+30h]
0x180015f19  mov     rcx, rdi; lpCriticalSection
0x180015f1c  call    cs:__imp_EnterCriticalSection
0x180015f22  mov     ebx, [rdi+30h]
0x180015f25  mov     rcx, rdi; lpCriticalSection
0x180015f28  call    cs:__imp_LeaveCriticalSection
0x180015f2e  test    ebx, ebx
0x180015f30  jnz     short loc_180015F3D
0x180015f32  inc     r12d
0x180015f35  cmp     r12d, [r15+28h]
0x180015f39  jb      short loc_180015F0B
0x180015f3b  jmp     short loc_180015F43
0x180015f3d  mov     r13d, 1
0x180015f43  mov     rcx, r15; lpCriticalSection
0x180015f46  call    cs:__imp_LeaveCriticalSection
0x180015f4c  test    r13d, r13d
0x180015f4f  jnz     short loc_180015F66
0x180015f51  mov     eax, [r14+0D4h]
0x180015f58  test    al, 2
0x180015f5a  jz      short loc_180015F83
0x180015f5c  and     eax, 0FFFFFFFDh
0x180015f5f  mov     [r14+0D4h], eax
0x180015f66  mov     r13d, [rsp+0C60h+var_C20]
0x180015f6b  mov     r15b, [rsp+0C60h+var_C10]
0x180015f70  test    r13d, r13d
0x180015f73  jz      loc_1800162CB
0x180015f79  mov     rdi, [rsp+0C60h+lpCriticalSection]
0x180015f7e  jmp     loc_180015DC9
0x180015f83  or      eax, 1
0x180015f86  mov     [r14+0D4h], eax
0x180015f8d  lea     rdx, [rsp+0C60h+lpCriticalSection]
0x180015f92  mov     rcx, r14
0x180015f95  call    ?_SignalStop@CWerService@@AEAAJAEAV?$unique_lock@Vrecursive_mutex@utl@@@utl@@@Z; CWerService::_SignalStop(utl::unique_lock<utl::recursive_mutex> &)
0x180015f9a  jmp     short loc_180015F66
0x180015f9c  test    ebx, ebx
0x180015f9e  js      loc_18001620C
0x180015fa4  xor     r12d, r12d
0x180015fa7  movzx   eax, [rbp+0B60h+var_B4C]
0x180015fab  mov     ecx, 0FFh
0x180015fb0  and     ax, cx
0x180015fb3  movzx   r15d, ax
0x180015fb7  mov     eax, 10000000h
0x180015fbc  test    [rsp+0C60h+var_BEC], eax
0x180015fc0  jz      short loc_180015FE6
0x180015fc2  mov     edx, eax
0x180015fc4  lea     rcx, [rsp+0C60h+var_BF0]
0x180015fc9  call    cs:__imp_AlpcGetMessageAttribute
0x180015fcf  mov     rbx, rax
0x180015fd2  test    rax, rax
0x180015fd5  jz      short loc_180015FE6
0x180015fd7  cmp     dword ptr [rax+10h], 4
0x180015fdb  jz      short loc_180015FE2
0x180015fdd  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180015fe2  mov     r12, [rbx+8]
0x180015fe6  mov     ecx, r15d
0x180015fe9  sub     ecx, 1
0x180015fec  jz      loc_1800160D1
0x180015ff2  sub     ecx, 4
0x180015ff5  jz      short loc_180016061
0x180015ff7  sub     ecx, 1
0x180015ffa  jz      short loc_180016061
0x180015ffc  sub     ecx, 1
0x180015fff  jz      short loc_18001604B
0x180016001  cmp     ecx, 3
0x180016004  jnz     loc_1800161F5
0x18001600a  lea     rdx, [rbp+0B60h+Src]; struct _WERSVC_MSG *
0x18001600e  mov     rcx, r14; this
0x180016011  call    ?_ProcessConnectionRequest@CWerService@@AEAAJPEAU_WERSVC_MSG@@@Z; CWerService::_ProcessConnectionRequest(_WERSVC_MSG *)
0x180016016  mov     esi, eax
0x180016018  test    eax, eax
0x18001601a  jns     loc_1800161F5
0x180016020  mov     rcx, cs:WPP_GLOBAL_Control
0x180016027  lea     rbx, WPP_GLOBAL_Control
0x18001602e  cmp     rcx, rbx
0x180016031  jz      loc_1800161F5
0x180016037  test    byte ptr [rcx+1Ch], 2
0x18001603b  jz      loc_1800161F5
0x180016041  mov     edx, 61h ; 'a'
0x180016046  jmp     loc_1800161C0
0x18001604b  mov     r8, r12; Handle
0x18001604e  lea     rdx, [rbp+0B60h+Src]; struct _WERSVC_MSG *
0x180016052  mov     rcx, r14; this
0x180016055  call    ?_ProcessLpcExceptionMessage@CWerService@@AEAAJPEAU_WERSVC_MSG@@PEAX@Z; CWerService::_ProcessLpcExceptionMessage(_WERSVC_MSG *,void *)
0x18001605a  mov     esi, eax
0x18001605c  jmp     loc_180015F6B
0x180016061  test    rdi, rdi
0x180016064  jz      short loc_1800160A6
0x180016066  mov     rdx, [rdi]; void *
0x180016069  mov     rcx, r14; this
0x18001606c  call    ?_CloseConnection@CWerService@@AEAAJPEAX@Z; CWerService::_CloseConnection(void *)
0x180016071  mov     esi, eax
0x180016073  test    eax, eax
0x180016075  jns     loc_1800161F5
0x18001607b  mov     rcx, cs:WPP_GLOBAL_Control
0x180016082  lea     rbx, WPP_GLOBAL_Control
0x180016089  cmp     rcx, rbx
0x18001608c  jz      loc_1800161F5
0x180016092  test    byte ptr [rcx+1Ch], 2
0x180016096  jz      loc_1800161F5
0x18001609c  mov     edx, 62h ; 'b'
0x1800160a1  jmp     loc_1800161C0
0x1800160a6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800160ad  lea     rbx, WPP_GLOBAL_Control
0x1800160b4  cmp     rcx, rbx
0x1800160b7  jz      loc_1800161F5
0x1800160bd  test    byte ptr [rcx+1Ch], 2
0x1800160c1  jz      loc_1800161F5
0x1800160c7  mov     edx, 63h ; 'c'
0x1800160cc  jmp     loc_1800161E5
0x1800160d1  lea     rdx, [rbp+0B60h+Src]; struct _WERSVC_MSG *
0x1800160d5  mov     rcx, r14; this
0x1800160d8  call    ?_ProcessRequest@CWerService@@AEAAJPEAU_WERSVC_MSG@@@Z; CWerService::_ProcessRequest(_WERSVC_MSG *)
0x1800160dd  mov     esi, eax
0x1800160df  test    eax, eax
0x1800160e1  js      short loc_18001615B
0x1800160e3  cmp     [rbp+0B60h+var_B28], 2
0x1800160e7  jnz     loc_1800161F5
0x1800160ed  lea     rcx, [rbp+0B60h+var_5D0]; void *
0x1800160f4  lea     rdx, [rbp+0B60h+Src]; Src
0x1800160f8  mov     r8d, 578h; Size
0x1800160fe  call    memcpy_0
0x180016103  mov     [rbp+0B60h+var_5A8], 2
0x18001610e  mov     [rsp+0C60h+var_C28], 0
0x180016117  mov     [rsp+0C60h+var_C30], 0
0x180016120  mov     [rsp+0C60h+var_C38], 0
0x180016129  mov     [rsp+0C60h+var_C40], 0
0x180016132  xor     r9d, r9d
0x180016135  lea     r8, [rbp+0B60h+var_5D0]
0x18001613c  mov     edx, 10000h
0x180016141  mov     rcx, [r14+188h]
0x180016148  call    cs:__imp_NtAlpcSendWaitReceivePort
0x18001614e  xor     r13d, r13d
0x180016151  mov     [rsp+0C60h+var_C20], r13d
0x180016156  jmp     loc_1800161F5
0x18001615b  mov     rcx, cs:WPP_GLOBAL_Control
0x180016162  lea     rbx, WPP_GLOBAL_Control
0x180016169  cmp     rcx, rbx
0x18001616c  jz      short loc_180016193
0x18001616e  test    byte ptr [rcx+1Ch], 2
0x180016172  jz      short loc_180016193
0x180016174  mov     edx, 5Eh ; '^'
0x180016179  mov     r9d, eax
0x18001617c  lea     r8, WPP_fd0c3993e8f0396a73a01b4739c75d44_Traceguids
0x180016183  mov     rcx, [rcx+10h]
0x180016187  call    WPP_SF_d
0x18001618c  mov     rcx, cs:WPP_GLOBAL_Control
0x180016193  test    rdi, rdi
0x180016196  jz      short loc_1800161D5
0x180016198  mov     rdx, [rdi]; void *
0x18001619b  mov     rcx, r14; this
0x18001619e  call    ?_CloseConnection@CWerService@@AEAAJPEAX@Z; CWerService::_CloseConnection(void *)
0x1800161a3  mov     esi, eax
0x1800161a5  test    eax, eax
0x1800161a7  jns     short loc_1800161F5
0x1800161a9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800161b0  cmp     rcx, rbx
0x1800161b3  jz      short loc_1800161F5
0x1800161b5  test    byte ptr [rcx+1Ch], 2
0x1800161b9  jz      short loc_1800161F5
0x1800161bb  mov     edx, 5Fh ; '_'
0x1800161c0  mov     r9d, eax
0x1800161c3  lea     r8, WPP_fd0c3993e8f0396a73a01b4739c75d44_Traceguids
0x1800161ca  mov     rcx, [rcx+10h]
0x1800161ce  call    WPP_SF_d
0x1800161d3  jmp     short loc_1800161F5
0x1800161d5  cmp     rcx, rbx
0x1800161d8  jz      short loc_1800161F5
0x1800161da  test    byte ptr [rcx+1Ch], 2
0x1800161de  jz      short loc_1800161F5
0x1800161e0  mov     edx, 60h ; '`'
0x1800161e5  lea     r8, WPP_fd0c3993e8f0396a73a01b4739c75d44_Traceguids
0x1800161ec  mov     rcx, [rcx+10h]
0x1800161f0  call    WPP_SF_
0x1800161f5  test    r12, r12
0x1800161f8  jz      loc_180015F6B
0x1800161fe  mov     rcx, r12; Handle
0x180016201  call    cs:__imp_NtClose
0x180016207  jmp     loc_180015F6B
0x18001620c  cmp     esi, 0D000000Bh
0x180016212  jnz     loc_180015F70
0x180016218  test    rdi, rdi
0x18001621b  jz      short loc_180016269
0x18001621d  mov     rdx, [rax]; void *
0x180016220  mov     rcx, r14; this
0x180016223  call    ?_CloseConnection@CWerService@@AEAAJPEAX@Z; CWerService::_CloseConnection(void *)
  ... truncated ...
```
