# CWerService::_CleanupLpcServer(utl::unique_lock<utl::recursive_mutex> &)

- ea: `0x18001c258`
- end: `0x18001c5fc`
- name: `?_CleanupLpcServer@CWerService@@AEAAJAEAV?$unique_lock@Vrecursive_mutex@utl@@@utl@@@Z`
- size: `932`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `8`
- tags: `loader_planting, service_task`

## callers

- `0x18001d9e8`
- `0x18001e1d0`

## callees

- `0x1800029d0`
- `0x1800035e8`
- `0x180006a80`
- `0x180011ef8`
- `0x180013e9c`
- `0x18001c258`
- `0x1800344f0`
- `0x180034550`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001c473`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001c473`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001c4c1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001c4c1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001c2cb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001c2cb`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18001c519`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18001c519`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001c4ab`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001c550`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001c5c9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001c4ab`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001c550`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001c5c9`
- `ntdll!NtClose` at `0x18001c463`
- `ntdll!NtClose` at `0x18001c4d5`
- `ntdll!NtClose` at `0x18001c532`
- `ntdll!NtClose` at `0x18001c463`
- `ntdll!NtClose` at `0x18001c4d5`
- `ntdll!NtClose` at `0x18001c532`
- `ntdll!RtlInitUnicodeString` at `0x18001c359`
- `ntdll!RtlInitUnicodeString` at `0x18001c359`
- `ntdll!NtAlpcConnectPort` at `0x18001c39f`
- `ntdll!NtAlpcConnectPort` at `0x18001c39f`
- `ntdll!NtAlpcSendWaitReceivePort` at `0x18001c44c`
- `ntdll!NtAlpcSendWaitReceivePort` at `0x18001c44c`
- `api-ms-win-core-namespace-l1-1-0!ClosePrivateNamespace` at `0x18001c588`
- `api-ms-win-core-namespace-l1-1-0!ClosePrivateNamespace` at `0x18001c588`

## string_xrefs

- `0x18001c304`: `\WindowsErrorReportingServicePort`

## pseudocode

```c
__int64 __fastcall CWerService::_CleanupLpcServer(__int64 a1, __int64 a2)
{
  void *v2; // r14
  void *v5; // rbx
  int v6; // eax
  HANDLE v7; // rcx
  int v8; // ebx
  HANDLE v9; // rcx
  void *v10; // rcx
  void *v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // r8
  void *v14; // rcx
  HANDLE Handle; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v17; // [rsp+68h] [rbp-98h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+70h] [rbp-90h] BYREF
  _QWORD v19[4]; // [rsp+80h] [rbp-80h] BYREF
  __int128 v20; // [rsp+A0h] [rbp-60h]
  __int128 v21; // [rsp+B0h] [rbp-50h] BYREF
  __int128 v22; // [rsp+C0h] [rbp-40h]
  __int128 v23; // [rsp+D0h] [rbp-30h]
  __int128 v24; // [rsp+E0h] [rbp-20h]
  __int64 v25; // [rsp+F0h] [rbp-10h]
  _BYTE v26[1408]; // [rsp+100h] [rbp+0h] BYREF
  __int128 v27; // [rsp+680h] [rbp+580h] BYREF
  __int64 v28; // [rsp+690h] [rbp+590h]
  __int64 v29; // [rsp+698h] [rbp+598h]
  __int128 v30; // [rsp+6A0h] [rbp+5A0h]
  __int128 v31; // [rsp+6B0h] [rbp+5B0h]
  __int64 v32; // [rsp+6C0h] [rbp+5C0h]
  _DWORD Src[352]; // [rsp+6D0h] [rbp+5D0h] BYREF
  _DWORD v34[352]; // [rsp+C50h] [rbp+B50h] BYREF

  v2 = *(void **)(a1 + 400);
  *(_QWORD *)(a1 + 400) = 0;
  if ( (unsigned __int64)v2 + 1 > 1 )
  {
    if ( !*(_BYTE *)(a2 + 8) )
      __int2c();
    LeaveCriticalSection(*(LPCRITICAL_SECTION *)a2);
    *(_BYTE *)(a2 + 8) = 0;
    v19[0] = 48;
    memset(&v19[1], 0, 24);
    v20 = 0;
    memset_0(&v21, 0, 0x48u);
    v27 = v21;
    v30 = v23;
    v29 = *((_QWORD *)&v22 + 1);
    v32 = v25;
    DestinationString = 0;
    v28 = 1400;
    v31 = v24;
    RtlInitUnicodeString(&DestinationString, L"\\WindowsErrorReportingServicePort");
    Handle = 0;
    if ( (int)NtAlpcConnectPort(&Handle, &DestinationString, v19, &v27, 0x20000, 0, 0, 0, 0, 0, 0) >= 0 )
    {
      memset_0(Src, 0, 0x578u);
      memcpy_0(v34, Src, 0x578u);
      v34[0] = 91751760;
      v34[10] = 2;
      memset_0(v26, 0, 0x578u);
      memcpy_0(Src, v26, 0x578u);
      Src[0] = 91751760;
      v17 = 1400;
      v6 = NtAlpcSendWaitReceivePort(Handle, 0x20000, v34, 0, Src, &v17, 0, 0);
      v7 = Handle;
      v8 = v6;
      Handle = 0;
      if ( v7 )
        NtClose(v7);
      if ( v8 < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            78,
            WPP_fd0c3993e8f0396a73a01b4739c75d44_Traceguids,
            (unsigned int)v8);
      }
      else
      {
        WaitForSingleObject(v2, 0xFFFFFFFF);
      }
    }
    v5 = 0;
    CloseHandle(v2);
    if ( !*(_QWORD *)a2 || *(_BYTE *)(a2 + 8) )
      __int2c();
    EnterCriticalSection(*(LPCRITICAL_SECTION *)a2);
    v9 = Handle;
    *(_BYTE *)(a2 + 8) = 1;
    if ( v9 )
      NtClose(v9);
  }
  else
  {
    v5 = v2;
  }
  if ( *(_QWORD *)(a1 + 344) != -1 && *(_QWORD *)(a1 + 344) != 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 79, WPP_fd0c3993e8f0396a73a01b4739c75d44_Traceguids);
    ResetEvent(*(HANDLE *)(a1 + 344));
  }
  v10 = *(void **)(a1 + 392);
  *(_QWORD *)(a1 + 392) = 0;
  if ( v10 )
    NtClose(v10);
  v11 = *(void **)(a1 + 408);
  *(_QWORD *)(a1 + 408) = 0;
  if ( (unsigned __int64)v11 + 1 > 1 )
    CloseHandle(v11);
  v12 = *(_QWORD *)(a1 + 360);
  v13 = *(_QWORD *)(a1 + 368) - v12;
  *(_QWORD *)(a1 + 368) = v12;
  utl::_RangeDestroyApc<utl::allocator<utl::unique_ptr<CWerService::LpcConnection,utl::default_delete<CWerService::LpcConnection>>>>(
    (__int64)v11,
    v12,
    v13 >> 3);
  v14 = *(void **)(a1 + 384);
  if ( v14 )
  {
    ClosePrivateNamespace(v14, 1u);
    *(_QWORD *)(a1 + 384) = 0;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 80, WPP_fd0c3993e8f0396a73a01b4739c75d44_Traceguids);
  if ( (unsigned __int64)v5 + 1 > 1 )
    CloseHandle(v5);
  return 0;
}

```

## disassembly

```asm
0x18001c258  mov     [rsp-8+arg_10], rbx
0x18001c25d  mov     [rsp-8+arg_18], rsi
0x18001c262  push    rbp
0x18001c263  push    rdi
0x18001c264  push    r12
0x18001c266  push    r14
0x18001c268  push    r15
0x18001c26a  lea     rbp, [rsp-10E0h]
0x18001c272  mov     eax, 11E0h
0x18001c277  call    _alloca_probe
0x18001c27c  sub     rsp, rax
0x18001c27f  mov     rax, cs:__security_cookie
0x18001c286  xor     rax, rsp
0x18001c289  mov     [rbp+1100h+var_30], rax
0x18001c290  mov     r14, [rcx+190h]
0x18001c297  lea     r12, WPP_GLOBAL_Control
0x18001c29e  xor     r15d, r15d
0x18001c2a1  mov     rsi, rdx
0x18001c2a4  mov     rdi, rcx
0x18001c2a7  mov     [rcx+190h], r15
0x18001c2ae  lea     rax, [r14+1]
0x18001c2b2  cmp     rax, 1
0x18001c2b6  ja      short loc_18001C2C0
0x18001c2b8  mov     rbx, r14
0x18001c2bb  jmp     loc_18001C4DB
0x18001c2c0  cmp     [rdx+8], r15b
0x18001c2c4  jnz     short loc_18001C2C8
0x18001c2c6  int     2Ch; Windows NT - assertion failure
0x18001c2c8  mov     rcx, [rdx]; lpCriticalSection
0x18001c2cb  call    cs:__imp_LeaveCriticalSection
0x18001c2d1  xor     edx, edx; Val
0x18001c2d3  mov     [rsi+8], r15b
0x18001c2d7  xorps   xmm0, xmm0
0x18001c2da  mov     [rbp+1100h+var_1180], 30h ; '0'
0x18001c2e2  lea     rcx, [rbp+1100h+var_1150]; void *
0x18001c2e6  mov     [rbp+1100h+var_1168], r15
0x18001c2ea  mov     [rbp+1100h+var_1178], r15
0x18001c2ee  lea     r8d, [rdx+48h]; Size
0x18001c2f2  mov     [rbp+1100h+var_1170], r15
0x18001c2f6  movdqu  [rbp+1100h+var_1160], xmm0
0x18001c2fb  call    memset_0
0x18001c300  movaps  xmm0, [rbp+1100h+var_1150]
0x18001c304  lea     rdx, aWindowserrorre; "\\WindowsErrorReportingServicePort"
0x18001c30b  movaps  xmm1, [rbp+1100h+var_1140]
0x18001c30f  lea     rcx, [rsp+1200h+DestinationString]; DestinationString
0x18001c314  movaps  [rbp+1100h+var_B80], xmm0
0x18001c31b  mov     ebx, 578h
0x18001c320  movaps  xmm0, [rbp+1100h+var_1130]
0x18001c324  movaps  [rbp+1100h+var_B60], xmm0
0x18001c32b  movsd   xmm0, [rbp+1100h+var_1110]
0x18001c330  movaps  [rbp+1100h+var_B70], xmm1
0x18001c337  movaps  xmm1, [rbp+1100h+var_1120]
0x18001c33b  movsd   [rbp+1100h+var_B40], xmm0
0x18001c343  xorps   xmm0, xmm0
0x18001c346  movups  xmmword ptr [rsp+1200h+DestinationString.Length], xmm0
0x18001c34b  mov     qword ptr [rbp+1100h+var_B70], rbx
0x18001c352  movaps  [rbp+1100h+var_B50], xmm1
0x18001c359  call    cs:__imp_RtlInitUnicodeString
0x18001c35f  mov     [rsp+1200h+var_11B0], r15
0x18001c364  lea     r9, [rbp+1100h+var_B80]
0x18001c36b  mov     [rsp+1200h+var_11B8], r15
0x18001c370  lea     r8, [rbp+1100h+var_1180]
0x18001c374  mov     [rsp+1200h+var_11C0], r15
0x18001c379  lea     rdx, [rsp+1200h+DestinationString]
0x18001c37e  mov     [rsp+1200h+var_11C8], r15
0x18001c383  lea     rcx, [rsp+1200h+Handle]
0x18001c388  mov     [rsp+1200h+var_11D0], r15
0x18001c38d  mov     [rsp+1200h+var_11D8], r15
0x18001c392  mov     dword ptr [rsp+1200h+var_11E0], 20000h
0x18001c39a  mov     [rsp+1200h+Handle], r15
0x18001c39f  call    cs:__imp_NtAlpcConnectPort
0x18001c3a5  test    eax, eax
0x18001c3a7  js      loc_18001C4A5
0x18001c3ad  mov     r8d, ebx; Size
0x18001c3b0  lea     rcx, [rbp+1100h+Src]; void *
0x18001c3b7  xor     edx, edx; Val
0x18001c3b9  call    memset_0
0x18001c3be  lea     rcx, [rbp+1100h+var_5B0]; void *
0x18001c3c5  mov     r8d, ebx; Size
0x18001c3c8  lea     rdx, [rbp+1100h+Src]; Src
0x18001c3cf  call    memcpy_0
0x18001c3d4  mov     r8d, ebx; Size
0x18001c3d7  mov     [rbp+1100h+var_5B0], 5780550h
0x18001c3e1  xor     edx, edx; Val
0x18001c3e3  mov     [rbp+1100h+var_588], 2
0x18001c3ed  lea     rcx, [rbp+1100h+var_1100]; void *
0x18001c3f1  call    memset_0
0x18001c3f6  lea     rcx, [rbp+1100h+Src]; void *
0x18001c3fd  mov     r8d, ebx; Size
0x18001c400  lea     rdx, [rbp+1100h+var_1100]; Src
0x18001c404  call    memcpy_0
0x18001c409  mov     rcx, [rsp+1200h+Handle]
0x18001c40e  lea     rax, [rsp+1200h+var_1198]
0x18001c413  mov     [rsp+1200h+var_11C8], r15
0x18001c418  lea     r8, [rbp+1100h+var_5B0]
0x18001c41f  mov     [rsp+1200h+var_11D0], r15
0x18001c424  xor     r9d, r9d
0x18001c427  mov     [rsp+1200h+var_11D8], rax
0x18001c42c  mov     edx, 20000h
0x18001c431  lea     rax, [rbp+1100h+Src]
0x18001c438  mov     [rbp+1100h+Src], 5780550h
0x18001c442  mov     [rsp+1200h+var_11E0], rax
0x18001c447  mov     [rsp+1200h+var_1198], rbx
0x18001c44c  call    cs:__imp_NtAlpcSendWaitReceivePort
0x18001c452  mov     rcx, [rsp+1200h+Handle]; Handle
0x18001c457  mov     ebx, eax
0x18001c459  mov     [rsp+1200h+Handle], r15
0x18001c45e  test    rcx, rcx
0x18001c461  jz      short loc_18001C469
0x18001c463  call    cs:__imp_NtClose
0x18001c469  test    ebx, ebx
0x18001c46b  js      short loc_18001C47B
0x18001c46d  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18001c470  mov     rcx, r14; hHandle
0x18001c473  call    cs:__imp_WaitForSingleObject
0x18001c479  jmp     short loc_18001C4A5
0x18001c47b  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c482  cmp     rcx, r12
0x18001c485  jz      short loc_18001C4A5
0x18001c487  test    byte ptr [rcx+1Ch], 1
0x18001c48b  jz      short loc_18001C4A5
0x18001c48d  mov     rcx, [rcx+10h]
0x18001c491  lea     r8, WPP_fd0c3993e8f0396a73a01b4739c75d44_Traceguids
0x18001c498  mov     edx, 4Eh ; 'N'
0x18001c49d  mov     r9d, ebx
0x18001c4a0  call    WPP_SF_d
0x18001c4a5  mov     rcx, r14; hObject
0x18001c4a8  mov     rbx, r15
0x18001c4ab  call    cs:__imp_CloseHandle
0x18001c4b1  mov     rcx, [rsi]; lpCriticalSection
0x18001c4b4  test    rcx, rcx
0x18001c4b7  jz      short loc_18001C4BF
0x18001c4b9  cmp     [rsi+8], r15b
0x18001c4bd  jz      short loc_18001C4C1
0x18001c4bf  int     2Ch; Windows NT - assertion failure
0x18001c4c1  call    cs:__imp_EnterCriticalSection
0x18001c4c7  mov     rcx, [rsp+1200h+Handle]; Handle
0x18001c4cc  mov     byte ptr [rsi+8], 1
0x18001c4d0  test    rcx, rcx
0x18001c4d3  jz      short loc_18001C4DB
0x18001c4d5  call    cs:__imp_NtClose
0x18001c4db  mov     rax, [rdi+158h]
0x18001c4e2  inc     rax
0x18001c4e5  cmp     rax, 1
0x18001c4e9  jbe     short loc_18001C51F
0x18001c4eb  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c4f2  cmp     rcx, r12
0x18001c4f5  jz      short loc_18001C512
0x18001c4f7  test    byte ptr [rcx+1Ch], 8
0x18001c4fb  jz      short loc_18001C512
0x18001c4fd  mov     rcx, [rcx+10h]
0x18001c501  lea     r8, WPP_fd0c3993e8f0396a73a01b4739c75d44_Traceguids
0x18001c508  mov     edx, 4Fh ; 'O'
0x18001c50d  call    WPP_SF_
0x18001c512  mov     rcx, [rdi+158h]; hEvent
0x18001c519  call    cs:__imp_ResetEvent
0x18001c51f  mov     rcx, [rdi+188h]; Handle
0x18001c526  mov     [rdi+188h], r15
0x18001c52d  test    rcx, rcx
0x18001c530  jz      short loc_18001C538
0x18001c532  call    cs:__imp_NtClose
0x18001c538  mov     rcx, [rdi+198h]; hObject
0x18001c53f  mov     [rdi+198h], r15
0x18001c546  lea     rax, [rcx+1]
0x18001c54a  cmp     rax, 1
0x18001c54e  jbe     short loc_18001C556
0x18001c550  call    cs:__imp_CloseHandle
0x18001c556  mov     rdx, [rdi+168h]
0x18001c55d  mov     r8, [rdi+170h]
0x18001c564  sub     r8, rdx
0x18001c567  mov     [rdi+170h], rdx
0x18001c56e  sar     r8, 3
0x18001c572  call    ??$_RangeDestroyApc@V?$allocator@V?$unique_ptr@ULpcConnection@CWerService@@U?$default_delete@ULpcConnection@CWerService@@@utl@@@utl@@@utl@@@utl@@YAXAEAV?$allocator@V?$unique_ptr@ULpcConnection@CWerService@@U?$default_delete@ULpcConnection@CWerService@@@utl@@@utl@@@0@PEAV?$unique_ptr@ULpcConnection@CWerService@@U?$default_delete@ULpcConnection@CWerService@@@utl@@@0@_K@Z; utl::_RangeDestroyApc<utl::allocator<utl::unique_ptr<CWerService::LpcConnection,utl::default_delete<CWerService::LpcConnection>>>>(utl::allocator<utl::unique_ptr<CWerService::LpcConnection,utl::default_delete<CWerService::LpcConnection>>> &,utl::unique_ptr<CWerService::LpcConnection,utl::default_delete<CWerService::LpcConnection>> *,unsigned __int64)
0x18001c577  mov     rcx, [rdi+180h]; Handle
0x18001c57e  test    rcx, rcx
0x18001c581  jz      short loc_18001C595
0x18001c583  mov     edx, 1; Flags
0x18001c588  call    cs:__imp_ClosePrivateNamespace
0x18001c58e  mov     [rdi+180h], r15
0x18001c595  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c59c  cmp     rcx, r12
0x18001c59f  jz      short loc_18001C5BC
0x18001c5a1  test    byte ptr [rcx+1Ch], 4
0x18001c5a5  jz      short loc_18001C5BC
0x18001c5a7  mov     rcx, [rcx+10h]
0x18001c5ab  lea     r8, WPP_fd0c3993e8f0396a73a01b4739c75d44_Traceguids
0x18001c5b2  mov     edx, 50h ; 'P'
0x18001c5b7  call    WPP_SF_
0x18001c5bc  lea     rax, [rbx+1]
0x18001c5c0  cmp     rax, 1
0x18001c5c4  jbe     short loc_18001C5CF
0x18001c5c6  mov     rcx, rbx; hObject
0x18001c5c9  call    cs:__imp_CloseHandle
0x18001c5cf  xor     eax, eax
0x18001c5d1  mov     rcx, [rbp+1100h+var_30]
0x18001c5d8  xor     rcx, rsp; StackCookie
0x18001c5db  call    __security_check_cookie
0x18001c5e0  lea     r11, [rsp+1200h+var_20]
0x18001c5e8  mov     rbx, [r11+40h]
0x18001c5ec  mov     rsi, [r11+48h]
0x18001c5f0  mov     rsp, r11
0x18001c5f3  pop     r15
0x18001c5f5  pop     r14
0x18001c5f7  pop     r12
0x18001c5f9  pop     rdi
0x18001c5fa  pop     rbp
0x18001c5fb  retn
```
