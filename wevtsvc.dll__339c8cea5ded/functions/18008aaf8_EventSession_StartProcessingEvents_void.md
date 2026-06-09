# EventSession::StartProcessingEvents(void)

- ea: `0x18008aaf8`
- end: `0x18008aeab`
- name: `?StartProcessingEvents@EventSession@@QEAAXXZ`
- size: `947`
- prototype: `void __fastcall(EventSession *__hidden this)`
- caller_count: `2`
- callee_count: `9`
- tags: ``

## callers

- `0x18000349c`
- `0x1800982f4`

## callees

- `0x18002b3e8`
- `0x18002de70`
- `0x18005ff90`
- `0x18008aaf8`
- `0x18008aeb4`
- `0x180092008`
- `0x18009aee0`
- `0x18009bb88`
- `0x1800d334c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18008ab33`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18008ab33`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18008ae13`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18008ae13`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008ac30`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008ad80`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008ac30`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008ad80`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18008ad5f`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18008ad5f`
- `api-ms-win-eventing-consumer-l1-1-0!OpenTraceW` at `0x18008ac16`
- `api-ms-win-eventing-consumer-l1-1-0!OpenTraceW` at `0x18008ac16`

## pseudocode

```c
void __fastcall EventSession::StartProcessingEvents(EventSession *this)
{
  TRACEHANDLE v2; // rax
  __int64 v3; // rdi
  DWORD LastError; // ebx
  _QWORD *v5; // rax
  HANDLE Thread; // rax
  DWORD v7; // ebx
  __int128 pExceptionObject; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v9; // [rsp+40h] [rbp-C0h]
  int v10; // [rsp+48h] [rbp-B8h]
  int v11; // [rsp+4Ch] [rbp-B4h]
  int v12; // [rsp+50h] [rbp-B0h]
  _QWORD v13[3]; // [rsp+58h] [rbp-A8h] BYREF
  struct _EVENT_TRACE_LOGFILEW Logfile; // [rsp+70h] [rbp-90h] BYREF

  v13[1] = &stru_180111D68;
  AcquireSRWLockExclusive(&stru_180111D68);
  if ( byte_18010F654 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x4000000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, &WPP_8b676d1c72cc33de7c97defb2afc7016_Traceguids, 4317);
    }
    pExceptionObject = 0;
    v9 = 0;
    v10 = 4317;
    v11 = -1;
    v12 = 161;
    throw (EvtException *)&pExceptionObject;
  }
  if ( *((_QWORD *)this + 10) != -1 || *((_QWORD *)this + 11) != -1 && *((_QWORD *)this + 11) != 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x4000000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, &WPP_8b676d1c72cc33de7c97defb2afc7016_Traceguids, 4317);
    }
    pExceptionObject = 0;
    v9 = 0;
    v10 = 4317;
    v11 = -1;
    v12 = 166;
    throw (EvtException *)&pExceptionObject;
  }
  memset_0(&Logfile, 0, sizeof(Logfile));
  Logfile.LoggerName = (LPWSTR)*((_QWORD *)this + 2);
  Logfile.EventCallback = (PEVENT_CALLBACK)EtwEventCallback;
  Logfile.LogFileMode = 268435712;
  Logfile.Context = this;
  v2 = OpenTraceW(&Logfile);
  tlx::unique_any<tlx::handle_traits<unsigned __int64,unsigned long (*)(unsigned __int64),&unsigned long CloseTrace(unsigned __int64),-1>>::reset(
    (char *)this + 80,
    v2);
  v3 = *((_QWORD *)this + 10);
  if ( v3 == -1 )
  {
    LastError = GetLastError();
    if ( !LastError )
      LastError = 1287;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x4000000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, &WPP_8b676d1c72cc33de7c97defb2afc7016_Traceguids, LastError);
    }
    pExceptionObject = 0;
    v9 = 0;
    v10 = LastError;
    v11 = -1;
    v12 = 178;
    throw (EvtException *)&pExceptionObject;
  }
  v5 = MIDL_user_allocate(0x10u);
  if ( v5 )
  {
    *v5 = v3;
    v5[1] = this;
  }
  else
  {
    v5 = 0;
  }
  v13[0] = v5;
  if ( !v5 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x4000000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, &WPP_8b676d1c72cc33de7c97defb2afc7016_Traceguids, 14);
    }
    pExceptionObject = 0;
    v9 = 0;
    v10 = 14;
    v11 = -1;
    v12 = 184;
    throw (EvtException *)&pExceptionObject;
  }
  Thread = CreateThread(0, 0x40000u, EventSession::ProcessEventsThread, v5, 0, 0);
  tlx::unique_any<tlx::file_handle_traits>::reset((char *)this + 88, Thread);
  if ( *((_QWORD *)this + 11) == -1 || *((_QWORD *)this + 11) == 0 )
  {
    v7 = GetLastError();
    if ( !v7 )
      v7 = 1287;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x4000000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, &WPP_8b676d1c72cc33de7c97defb2afc7016_Traceguids, v7);
    }
    pExceptionObject = 0;
    v9 = 0;
    v10 = v7;
    v11 = -1;
    v12 = 211;
    throw (EvtException *)&pExceptionObject;
  }
  v13[0] = 0;
  utl::unique_ptr<ProcessEventsThreadArgs,utl::default_delete<ProcessEventsThreadArgs>>::~unique_ptr<ProcessEventsThreadArgs,utl::default_delete<ProcessEventsThreadArgs>>(v13);
  ReleaseSRWLockExclusive(&stru_180111D68);
}

```

## disassembly

```asm
0x18008aaf8  push    rbp
0x18008aafa  push    rbx
0x18008aafb  push    rsi
0x18008aafc  push    rdi
0x18008aafd  push    r14
0x18008aaff  push    r15
0x18008ab01  lea     rbp, [rsp-148h]
0x18008ab09  sub     rsp, 248h
0x18008ab10  mov     rax, cs:__security_cookie
0x18008ab17  xor     rax, rsp
0x18008ab1a  mov     [rbp+170h+var_40], rax
0x18008ab21  mov     rbx, rcx
0x18008ab24  lea     r15, stru_180111D68
0x18008ab2b  mov     [rsp+270h+var_210], r15
0x18008ab30  mov     rcx, r15; SRWLock
0x18008ab33  call    cs:__imp_AcquireSRWLockExclusive
0x18008ab39  nop
0x18008ab3a  xor     r14d, r14d
0x18008ab3d  cmp     cs:byte_18010F654, r14b
0x18008ab44  jz      short loc_18008ABB8
0x18008ab46  lea     rax, WPP_GLOBAL_Control
0x18008ab4d  mov     ebx, 10DDh
0x18008ab52  mov     rcx, cs:WPP_GLOBAL_Control
0x18008ab59  cmp     rcx, rax
0x18008ab5c  jz      short loc_18008AB84
0x18008ab5e  test    dword ptr [rcx+1Ch], 4000000h
0x18008ab65  jz      short loc_18008AB84
0x18008ab67  cmp     byte ptr [rcx+19h], 2
0x18008ab6b  jb      short loc_18008AB84
0x18008ab6d  lea     edx, [r14+10h]
0x18008ab71  mov     r9d, ebx
0x18008ab74  lea     r8, WPP_8b676d1c72cc33de7c97defb2afc7016_Traceguids
0x18008ab7b  mov     rcx, [rcx+10h]
0x18008ab7f  call    WPP_SF_d
0x18008ab84  xorps   xmm0, xmm0
0x18008ab87  movdqu  [rsp+270h+pExceptionObject], xmm0
0x18008ab8d  mov     [rsp+270h+var_230], r14
0x18008ab92  mov     [rsp+270h+var_228], ebx
0x18008ab96  mov     [rsp+270h+var_224], 0FFFFFFFFh
0x18008ab9e  mov     [rsp+270h+var_220], 0A1h
0x18008aba6  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x18008abad  lea     rcx, [rsp+270h+pExceptionObject]; pExceptionObject
0x18008abb2  call    _CxxThrowException_0
0x18008abb8  lea     rdi, [rbx+50h]
0x18008abbc  cmp     qword ptr [rdi], 0FFFFFFFFFFFFFFFFh
0x18008abc0  jnz     loc_18008AE38
0x18008abc6  lea     rsi, [rbx+58h]
0x18008abca  mov     rax, [rsi]
0x18008abcd  inc     rax
0x18008abd0  cmp     rax, 1
0x18008abd4  ja      loc_18008AE38
0x18008abda  xor     edx, edx; Val
0x18008abdc  mov     r8d, 1C0h; Size
0x18008abe2  lea     rcx, [rsp+270h+Logfile]; void *
0x18008abe7  call    memset_0
0x18008abec  mov     rax, [rbx+10h]
0x18008abf0  mov     [rsp+270h+Logfile.LoggerName], rax
0x18008abf5  lea     rax, EtwEventCallback
0x18008abfc  mov     qword ptr [rbp+170h+Logfile.1A8h], rax
0x18008ac03  mov     dword ptr [rbp+170h+Logfile.1Ch], 10000100h
0x18008ac0a  mov     [rbp+170h+Logfile.Context], rbx
0x18008ac11  lea     rcx, [rsp+270h+Logfile]; Logfile
0x18008ac16  call    cs:__imp_OpenTraceW
0x18008ac1c  mov     rdx, rax
0x18008ac1f  mov     rcx, rdi
0x18008ac22  call    ?reset@?$unique_any@U?$handle_traits@_KP6AK_K@Z$1?CloseTrace@@YAK0@Z$0?0@tlx@@@tlx@@QEAAX_K@Z; tlx::unique_any<tlx::handle_traits<unsigned __int64,ulong (*)(unsigned __int64),&CloseTrace(unsigned __int64),-1>>::reset(unsigned __int64)
0x18008ac27  mov     rdi, [rdi]
0x18008ac2a  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x18008ac2e  jnz     short loc_18008ACAE
0x18008ac30  call    cs:__imp_GetLastError
0x18008ac36  mov     ebx, eax
0x18008ac38  mov     eax, 507h
0x18008ac3d  test    ebx, ebx
0x18008ac3f  cmovz   ebx, eax
0x18008ac42  lea     rax, WPP_GLOBAL_Control
0x18008ac49  mov     rcx, cs:WPP_GLOBAL_Control
0x18008ac50  cmp     rcx, rax
0x18008ac53  jz      short loc_18008AC7A
0x18008ac55  test    dword ptr [rcx+1Ch], 4000000h
0x18008ac5c  jz      short loc_18008AC7A
0x18008ac5e  cmp     byte ptr [rcx+19h], 2
0x18008ac62  jb      short loc_18008AC7A
0x18008ac64  lea     edx, [rdi+13h]
0x18008ac67  mov     r9d, ebx
0x18008ac6a  lea     r8, WPP_8b676d1c72cc33de7c97defb2afc7016_Traceguids
0x18008ac71  mov     rcx, [rcx+10h]
0x18008ac75  call    WPP_SF_d
0x18008ac7a  xorps   xmm0, xmm0
0x18008ac7d  movdqu  [rsp+270h+pExceptionObject], xmm0
0x18008ac83  mov     [rsp+270h+var_230], r14
0x18008ac88  mov     [rsp+270h+var_228], ebx
0x18008ac8c  mov     [rsp+270h+var_224], 0FFFFFFFFh
0x18008ac94  mov     [rsp+270h+var_220], 0B2h
0x18008ac9c  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x18008aca3  lea     rcx, [rsp+270h+pExceptionObject]; pExceptionObject
0x18008aca8  call    _CxxThrowException_0
0x18008acae  mov     ecx, 10h; size
0x18008acb3  call    MIDL_user_allocate
0x18008acb8  test    rax, rax
0x18008acbb  jz      short loc_18008ACC6
0x18008acbd  mov     [rax], rdi
0x18008acc0  mov     [rax+8], rbx
0x18008acc4  jmp     short loc_18008ACC9
0x18008acc6  mov     rax, r14
0x18008acc9  mov     [rsp+270h+var_218], rax
0x18008acce  test    rax, rax
0x18008acd1  jnz     short loc_18008AD44
0x18008acd3  lea     rax, WPP_GLOBAL_Control
0x18008acda  mov     ebx, 0Eh
0x18008acdf  mov     rcx, cs:WPP_GLOBAL_Control
0x18008ace6  cmp     rcx, rax
0x18008ace9  jz      short loc_18008AD10
0x18008aceb  test    dword ptr [rcx+1Ch], 4000000h
0x18008acf2  jz      short loc_18008AD10
0x18008acf4  cmp     byte ptr [rcx+19h], 2
0x18008acf8  jb      short loc_18008AD10
0x18008acfa  lea     edx, [rbx+5]
0x18008acfd  mov     r9d, ebx
0x18008ad00  lea     r8, WPP_8b676d1c72cc33de7c97defb2afc7016_Traceguids
0x18008ad07  mov     rcx, [rcx+10h]
0x18008ad0b  call    WPP_SF_d
0x18008ad10  xorps   xmm0, xmm0
0x18008ad13  movdqu  [rsp+270h+pExceptionObject], xmm0
0x18008ad19  mov     [rsp+270h+var_230], r14
0x18008ad1e  mov     [rsp+270h+var_228], ebx
0x18008ad22  mov     [rsp+270h+var_224], 0FFFFFFFFh
0x18008ad2a  mov     [rsp+270h+var_220], 0B8h
0x18008ad32  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x18008ad39  lea     rcx, [rsp+270h+pExceptionObject]; pExceptionObject
0x18008ad3e  call    _CxxThrowException_0
0x18008ad44  mov     [rsp+270h+lpThreadId], r14; lpThreadId
0x18008ad49  mov     [rsp+270h+dwCreationFlags], r14d; dwCreationFlags
0x18008ad4e  mov     r9, rax; lpParameter
0x18008ad51  lea     r8, ?ProcessEventsThread@EventSession@@CAKPEAX@Z; lpStartAddress
0x18008ad58  mov     edx, 40000h; dwStackSize
0x18008ad5d  xor     ecx, ecx; lpThreadAttributes
0x18008ad5f  call    cs:__imp_CreateThread
0x18008ad65  mov     rdx, rax
0x18008ad68  mov     rcx, rsi
0x18008ad6b  call    ?reset@?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAXPEAX@Z; tlx::unique_any<tlx::file_handle_traits>::reset(void *)
0x18008ad70  mov     rax, [rsi]
0x18008ad73  inc     rax
0x18008ad76  cmp     rax, 1
0x18008ad7a  ja      loc_18008AE00
0x18008ad80  call    cs:__imp_GetLastError
0x18008ad86  mov     ebx, eax
0x18008ad88  mov     eax, 507h
0x18008ad8d  test    ebx, ebx
0x18008ad8f  cmovz   ebx, eax
0x18008ad92  lea     rax, WPP_GLOBAL_Control
0x18008ad99  mov     rcx, cs:WPP_GLOBAL_Control
0x18008ada0  cmp     rcx, rax
0x18008ada3  jz      short loc_18008ADCC
0x18008ada5  test    dword ptr [rcx+1Ch], 4000000h
0x18008adac  jz      short loc_18008ADCC
0x18008adae  cmp     byte ptr [rcx+19h], 2
0x18008adb2  jb      short loc_18008ADCC
0x18008adb4  mov     edx, 14h
0x18008adb9  mov     r9d, ebx
0x18008adbc  lea     r8, WPP_8b676d1c72cc33de7c97defb2afc7016_Traceguids
0x18008adc3  mov     rcx, [rcx+10h]
0x18008adc7  call    WPP_SF_d
0x18008adcc  xorps   xmm0, xmm0
0x18008adcf  movdqu  [rsp+270h+pExceptionObject], xmm0
0x18008add5  mov     [rsp+270h+var_230], r14
0x18008adda  mov     [rsp+270h+var_228], ebx
0x18008adde  mov     [rsp+270h+var_224], 0FFFFFFFFh
0x18008ade6  mov     [rsp+270h+var_220], 0D3h
0x18008adee  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x18008adf5  lea     rcx, [rsp+270h+pExceptionObject]; pExceptionObject
0x18008adfa  call    _CxxThrowException_0
0x18008ae00  mov     [rsp+270h+var_218], r14
0x18008ae05  lea     rcx, [rsp+270h+var_218]
0x18008ae0a  call    ??1?$unique_ptr@UProcessEventsThreadArgs@@U?$default_delete@UProcessEventsThreadArgs@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<ProcessEventsThreadArgs,utl::default_delete<ProcessEventsThreadArgs>>::~unique_ptr<ProcessEventsThreadArgs,utl::default_delete<ProcessEventsThreadArgs>>(void)
0x18008ae0f  nop
0x18008ae10  mov     rcx, r15; SRWLock
0x18008ae13  call    cs:__imp_ReleaseSRWLockExclusive
0x18008ae19  mov     rcx, [rbp+170h+var_40]
0x18008ae20  xor     rcx, rsp; StackCookie
0x18008ae23  call    __security_check_cookie
0x18008ae28  add     rsp, 248h
0x18008ae2f  pop     r15
0x18008ae31  pop     r14
0x18008ae33  pop     rdi
0x18008ae34  pop     rsi
0x18008ae35  pop     rbx
0x18008ae36  pop     rbp
0x18008ae37  retn
0x18008ae38  lea     rax, WPP_GLOBAL_Control
0x18008ae3f  mov     ebx, 10DDh
0x18008ae44  mov     rcx, cs:WPP_GLOBAL_Control
0x18008ae4b  cmp     rcx, rax
0x18008ae4e  jz      short loc_18008AE77
0x18008ae50  test    dword ptr [rcx+1Ch], 4000000h
0x18008ae57  jz      short loc_18008AE77
0x18008ae59  cmp     byte ptr [rcx+19h], 2
0x18008ae5d  jb      short loc_18008AE77
0x18008ae5f  mov     edx, 11h
0x18008ae64  mov     r9d, ebx
0x18008ae67  lea     r8, WPP_8b676d1c72cc33de7c97defb2afc7016_Traceguids
0x18008ae6e  mov     rcx, [rcx+10h]
0x18008ae72  call    WPP_SF_d
0x18008ae77  xorps   xmm0, xmm0
0x18008ae7a  movdqu  [rsp+270h+pExceptionObject], xmm0
0x18008ae80  mov     [rsp+270h+var_230], r14
0x18008ae85  mov     [rsp+270h+var_228], ebx
0x18008ae89  mov     [rsp+270h+var_224], 0FFFFFFFFh
0x18008ae91  mov     [rsp+270h+var_220], 0A6h
0x18008ae99  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x18008aea0  lea     rcx, [rsp+270h+pExceptionObject]; pExceptionObject
0x18008aea5  call    _CxxThrowException_0
```
