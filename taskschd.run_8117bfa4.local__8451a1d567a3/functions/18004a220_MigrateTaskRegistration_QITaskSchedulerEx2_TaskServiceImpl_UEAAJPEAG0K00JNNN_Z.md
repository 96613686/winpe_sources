# ?MigrateTaskRegistration@?QITaskSchedulerEx2@@TaskServiceImpl@@UEAAJPEAG0K00JNNN@Z

- ea: `0x18004a220`
- end: `0x18004a5a3`
- name: `?MigrateTaskRegistration@?QITaskSchedulerEx2@@TaskServiceImpl@@UEAAJPEAG0K00JNNN@Z`
- size: `899`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x180049924`
- `0x18004a220`
- `0x180051e78`
- `0x180052640`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004a308`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004a355`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004a3ce`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004a41b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004a497`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004a4e4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004a54e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004a569`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004a308`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004a355`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004a3ce`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004a41b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004a497`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004a4e4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004a54e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004a569`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004a278`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004a278`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a2ea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a337`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a3b0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a3fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a479`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a4c6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a2ea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a337`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a3b0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a3fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a479`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a4c6`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18004a325`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18004a3eb`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18004a4b4`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18004a325`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18004a3eb`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18004a4b4`

## pseudocode

```c
// Hidden C++ exception states: #wind=1 #try_helpers=1
__int64 __fastcall _MigrateTaskRegistration__QITaskSchedulerEx2__TaskServiceImpl__UEAAJPEAG0K00JNNN_Z(
        __int64 a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        unsigned int a4,
        unsigned __int16 *a5,
        unsigned __int16 *a6,
        int a7,
        double a8,
        double a9,
        double a10)
{
  struct _RTL_CRITICAL_SECTION *v14; // rdi
  signed int v15; // eax
  unsigned int v16; // ebx
  signed int LastError; // eax
  unsigned int v19; // ebx
  signed int v20; // eax
  signed int v21; // eax
  signed int v22; // eax
  signed int v23; // eax
  RpcSession *v24; // rcx
  struct _FILETIME FileTime; // [rsp+48h] [rbp-90h] BYREF
  double v26; // [rsp+50h] [rbp-88h] BYREF
  int v27; // [rsp+58h] [rbp-80h]
  __int64 v28; // [rsp+60h] [rbp-78h]
  SYSTEMTIME SystemTime; // [rsp+68h] [rbp-70h] BYREF
  int v30; // [rsp+78h] [rbp-60h] BYREF
  struct _FILETIME v31; // [rsp+7Ch] [rbp-5Ch]
  struct _FILETIME v32; // [rsp+84h] [rbp-54h]
  struct _FILETIME v33; // [rsp+8Ch] [rbp-4Ch]

  v14 = (struct _RTL_CRITICAL_SECTION *)(a1 + 256);
  v28 = a1 + 256;
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 256));
  SystemTime = 0;
  FileTime = 0;
  v32 = 0;
  v33 = 0;
  v30 = a7;
  v31 = 0;
  if ( a8 == 0.0 )
    goto LABEL_11;
  v26 = a8;
  v27 = 0;
  if ( ATL::COleDateTime::GetAsSystemTime((ATL::COleDateTime *)&v26, &SystemTime) )
  {
    if ( !SystemTimeToFileTime(&SystemTime, &FileTime) )
    {
      LastError = GetLastError();
      v19 = LastError;
      if ( LastError > 0 )
        v19 = (unsigned __int16)LastError | 0x80070000;
      goto LABEL_36;
    }
    v31 = FileTime;
LABEL_11:
    v33 = 0;
    if ( a10 != 0.0 )
    {
      v26 = a10;
      v27 = 0;
      if ( !ATL::COleDateTime::GetAsSystemTime((ATL::COleDateTime *)&v26, &SystemTime) )
      {
        v20 = GetLastError();
        v19 = v20;
        if ( v20 > 0 )
          v19 = (unsigned __int16)v20 | 0x80070000;
        goto LABEL_36;
      }
      if ( !SystemTimeToFileTime(&SystemTime, &FileTime) )
      {
        v21 = GetLastError();
        v19 = v21;
        if ( v21 > 0 )
          v19 = (unsigned __int16)v21 | 0x80070000;
        goto LABEL_36;
      }
      v33 = FileTime;
    }
    v32 = 0;
    if ( a9 != 0.0 )
    {
      v26 = a9;
      v27 = 0;
      if ( !ATL::COleDateTime::GetAsSystemTime((ATL::COleDateTime *)&v26, &SystemTime) )
      {
        v22 = GetLastError();
        v19 = v22;
        if ( v22 > 0 )
          v19 = (unsigned __int16)v22 | 0x80070000;
        goto LABEL_36;
      }
      if ( !SystemTimeToFileTime(&SystemTime, &FileTime) )
      {
        v23 = GetLastError();
        v19 = v23;
        if ( v23 > 0 )
          v19 = (unsigned __int16)v23 | 0x80070000;
        goto LABEL_36;
      }
      v32 = FileTime;
    }
    if ( *(_DWORD *)(a1 + 296) )
    {
      v24 = *(RpcSession **)(a1 + 304);
      if ( v24 )
        v19 = RpcSession::MigrateTaskRegistration(v24, a2, a3, a4, a5, a6, (struct _SCHRPC_DYNAMIC_TASK_INFO *)&v30);
      else
        v19 = -2147024846;
    }
    else
    {
      v19 = -2147023645;
    }
LABEL_36:
    LeaveCriticalSection(v14);
    return v19;
  }
  v15 = GetLastError();
  v16 = v15;
  if ( v15 > 0 )
    v16 = (unsigned __int16)v15 | 0x80070000;
  LeaveCriticalSection(v14);
  return v16;
}

```

## disassembly

```asm
0x18004a220  push    rbx
0x18004a222  push    rsi
0x18004a223  push    rdi
0x18004a224  push    r12
0x18004a226  push    r13
0x18004a228  push    r14
0x18004a22a  push    r15
0x18004a22c  sub     rsp, 0A0h
0x18004a233  mov     rax, cs:__security_cookie
0x18004a23a  xor     rax, rsp
0x18004a23d  mov     [rsp+0D8h+var_40], rax
0x18004a245  mov     r15d, r9d
0x18004a248  mov     r14, r8
0x18004a24b  mov     rsi, rdx
0x18004a24e  mov     rbx, rcx
0x18004a251  mov     r12, [rsp+0D8h+arg_20]
0x18004a259  mov     r13, [rsp+0D8h+arg_28]
0x18004a261  mov     [rsp+0D8h+var_98], 0
0x18004a269  lea     rdi, [rcx+100h]
0x18004a270  mov     [rsp+0D8h+var_78], rdi
0x18004a275  mov     rcx, rdi; lpCriticalSection
0x18004a278  call    cs:__imp_EnterCriticalSection
0x18004a27f  nop     dword ptr [rax+rax+00h]
0x18004a284  nop
0x18004a285  xorps   xmm0, xmm0
0x18004a288  movups  xmmword ptr [rsp+0D8h+SystemTime.wYear], xmm0
0x18004a28d  xor     edx, edx
0x18004a28f  mov     qword ptr [rsp+0D8h+FileTime.dwLowDateTime], rdx
0x18004a294  mov     [rsp+0D8h+var_54], rdx
0x18004a29c  mov     [rsp+0D8h+var_4C], rdx
0x18004a2a4  mov     eax, [rsp+0D8h+arg_30]
0x18004a2ab  mov     [rsp+0D8h+var_60], eax
0x18004a2af  mov     [rsp+0D8h+var_5C], rdx
0x18004a2b4  movsd   xmm0, [rsp+0D8h+arg_38]
0x18004a2bd  ucomisd xmm0, cs:__real@0000000000000000
0x18004a2c5  jp      short loc_18004A2CD
0x18004a2c7  jz      loc_18004A372
0x18004a2cd  movsd   [rsp+0D8h+var_88], xmm0
0x18004a2d3  mov     [rsp+0D8h+var_80], edx
0x18004a2d7  lea     rdx, [rsp+0D8h+SystemTime]; struct _SYSTEMTIME *
0x18004a2dc  lea     rcx, [rsp+0D8h+var_88]; this
0x18004a2e1  call    ?GetAsSystemTime@COleDateTime@ATL@@QEBA_NAEAU_SYSTEMTIME@@@Z; ATL::COleDateTime::GetAsSystemTime(_SYSTEMTIME &)
0x18004a2e6  test    al, al
0x18004a2e8  jnz     short loc_18004A31B
0x18004a2ea  call    cs:__imp_GetLastError
0x18004a2f1  nop     dword ptr [rax+rax+00h]
0x18004a2f6  mov     ebx, eax
0x18004a2f8  test    eax, eax
0x18004a2fa  jle     short loc_18004A305
0x18004a2fc  movzx   ebx, ax
0x18004a2ff  or      ebx, 80070000h
0x18004a305  mov     rcx, rdi; lpCriticalSection
0x18004a308  call    cs:__imp_LeaveCriticalSection
0x18004a30f  nop     dword ptr [rax+rax+00h]
0x18004a314  mov     eax, ebx
0x18004a316  jmp     loc_18004A57F
0x18004a31b  lea     rdx, [rsp+0D8h+FileTime]; lpFileTime
0x18004a320  lea     rcx, [rsp+0D8h+SystemTime]; lpSystemTime
0x18004a325  call    cs:__imp_SystemTimeToFileTime
0x18004a32c  nop     dword ptr [rax+rax+00h]
0x18004a331  xor     edx, edx
0x18004a333  test    eax, eax
0x18004a335  jnz     short loc_18004A368
0x18004a337  call    cs:__imp_GetLastError
0x18004a33e  nop     dword ptr [rax+rax+00h]
0x18004a343  mov     ebx, eax
0x18004a345  test    eax, eax
0x18004a347  jle     short loc_18004A352
0x18004a349  movzx   ebx, ax
0x18004a34c  or      ebx, 80070000h
0x18004a352  mov     rcx, rdi; lpCriticalSection
0x18004a355  call    cs:__imp_LeaveCriticalSection
0x18004a35c  nop     dword ptr [rax+rax+00h]
0x18004a361  mov     eax, ebx
0x18004a363  jmp     loc_18004A57F
0x18004a368  mov     rax, qword ptr [rsp+0D8h+FileTime.dwLowDateTime]
0x18004a36d  mov     [rsp+0D8h+var_5C], rax
0x18004a372  mov     [rsp+0D8h+var_4C], rdx
0x18004a37a  movsd   xmm0, [rsp+0D8h+arg_48]
0x18004a383  ucomisd xmm0, cs:__real@0000000000000000
0x18004a38b  jp      short loc_18004A393
0x18004a38d  jz      loc_18004A43B
0x18004a393  movsd   [rsp+0D8h+var_88], xmm0
0x18004a399  mov     [rsp+0D8h+var_80], edx
0x18004a39d  lea     rdx, [rsp+0D8h+SystemTime]; struct _SYSTEMTIME *
0x18004a3a2  lea     rcx, [rsp+0D8h+var_88]; this
0x18004a3a7  call    ?GetAsSystemTime@COleDateTime@ATL@@QEBA_NAEAU_SYSTEMTIME@@@Z; ATL::COleDateTime::GetAsSystemTime(_SYSTEMTIME &)
0x18004a3ac  test    al, al
0x18004a3ae  jnz     short loc_18004A3E1
0x18004a3b0  call    cs:__imp_GetLastError
0x18004a3b7  nop     dword ptr [rax+rax+00h]
0x18004a3bc  mov     ebx, eax
0x18004a3be  test    eax, eax
0x18004a3c0  jle     short loc_18004A3CB
0x18004a3c2  movzx   ebx, ax
0x18004a3c5  or      ebx, 80070000h
0x18004a3cb  mov     rcx, rdi; lpCriticalSection
0x18004a3ce  call    cs:__imp_LeaveCriticalSection
0x18004a3d5  nop     dword ptr [rax+rax+00h]
0x18004a3da  mov     eax, ebx
0x18004a3dc  jmp     loc_18004A57F
0x18004a3e1  lea     rdx, [rsp+0D8h+FileTime]; lpFileTime
0x18004a3e6  lea     rcx, [rsp+0D8h+SystemTime]; lpSystemTime
0x18004a3eb  call    cs:__imp_SystemTimeToFileTime
0x18004a3f2  nop     dword ptr [rax+rax+00h]
0x18004a3f7  xor     edx, edx
0x18004a3f9  test    eax, eax
0x18004a3fb  jnz     short loc_18004A42E
0x18004a3fd  call    cs:__imp_GetLastError
0x18004a404  nop     dword ptr [rax+rax+00h]
0x18004a409  mov     ebx, eax
0x18004a40b  test    eax, eax
0x18004a40d  jle     short loc_18004A418
0x18004a40f  movzx   ebx, ax
0x18004a412  or      ebx, 80070000h
0x18004a418  mov     rcx, rdi; lpCriticalSection
0x18004a41b  call    cs:__imp_LeaveCriticalSection
0x18004a422  nop     dword ptr [rax+rax+00h]
0x18004a427  mov     eax, ebx
0x18004a429  jmp     loc_18004A57F
0x18004a42e  mov     rax, qword ptr [rsp+0D8h+FileTime.dwLowDateTime]
0x18004a433  mov     [rsp+0D8h+var_4C], rax
0x18004a43b  mov     [rsp+0D8h+var_54], rdx
0x18004a443  movsd   xmm0, [rsp+0D8h+arg_40]
0x18004a44c  ucomisd xmm0, cs:__real@0000000000000000
0x18004a454  jp      short loc_18004A45C
0x18004a456  jz      loc_18004A504
0x18004a45c  movsd   [rsp+0D8h+var_88], xmm0
0x18004a462  mov     [rsp+0D8h+var_80], edx
0x18004a466  lea     rdx, [rsp+0D8h+SystemTime]; struct _SYSTEMTIME *
0x18004a46b  lea     rcx, [rsp+0D8h+var_88]; this
0x18004a470  call    ?GetAsSystemTime@COleDateTime@ATL@@QEBA_NAEAU_SYSTEMTIME@@@Z; ATL::COleDateTime::GetAsSystemTime(_SYSTEMTIME &)
0x18004a475  test    al, al
0x18004a477  jnz     short loc_18004A4AA
0x18004a479  call    cs:__imp_GetLastError
0x18004a480  nop     dword ptr [rax+rax+00h]
0x18004a485  mov     ebx, eax
0x18004a487  test    eax, eax
0x18004a489  jle     short loc_18004A494
0x18004a48b  movzx   ebx, ax
0x18004a48e  or      ebx, 80070000h
0x18004a494  mov     rcx, rdi; lpCriticalSection
0x18004a497  call    cs:__imp_LeaveCriticalSection
0x18004a49e  nop     dword ptr [rax+rax+00h]
0x18004a4a3  mov     eax, ebx
0x18004a4a5  jmp     loc_18004A57F
0x18004a4aa  lea     rdx, [rsp+0D8h+FileTime]; lpFileTime
0x18004a4af  lea     rcx, [rsp+0D8h+SystemTime]; lpSystemTime
0x18004a4b4  call    cs:__imp_SystemTimeToFileTime
0x18004a4bb  nop     dword ptr [rax+rax+00h]
0x18004a4c0  xor     edx, edx
0x18004a4c2  test    eax, eax
0x18004a4c4  jnz     short loc_18004A4F7
0x18004a4c6  call    cs:__imp_GetLastError
0x18004a4cd  nop     dword ptr [rax+rax+00h]
0x18004a4d2  mov     ebx, eax
0x18004a4d4  test    eax, eax
0x18004a4d6  jle     short loc_18004A4E1
0x18004a4d8  movzx   ebx, ax
0x18004a4db  or      ebx, 80070000h
0x18004a4e1  mov     rcx, rdi; lpCriticalSection
0x18004a4e4  call    cs:__imp_LeaveCriticalSection
0x18004a4eb  nop     dword ptr [rax+rax+00h]
0x18004a4f0  mov     eax, ebx
0x18004a4f2  jmp     loc_18004A57F
0x18004a4f7  mov     rax, qword ptr [rsp+0D8h+FileTime.dwLowDateTime]
0x18004a4fc  mov     [rsp+0D8h+var_54], rax
0x18004a504  cmp     [rbx+128h], edx
0x18004a50a  jnz     short loc_18004A513
0x18004a50c  mov     ebx, 800704E3h
0x18004a511  jmp     short loc_18004A562
0x18004a513  mov     rcx, [rbx+130h]; this
0x18004a51a  test    rcx, rcx
0x18004a51d  jz      short loc_18004A55D
0x18004a51f  lea     rax, [rsp+0D8h+var_60]
0x18004a524  mov     [rsp+0D8h+var_A8], rax; struct _SCHRPC_DYNAMIC_TASK_INFO *
0x18004a529  mov     [rsp+0D8h+var_B0], r13; unsigned __int16 *
0x18004a52e  mov     [rsp+0D8h+var_B8], r12; unsigned __int16 *
0x18004a533  mov     r9d, r15d; unsigned int
0x18004a536  mov     r8, r14; unsigned __int16 *
0x18004a539  mov     rdx, rsi; unsigned __int16 *
0x18004a53c  call    ?MigrateTaskRegistration@RpcSession@@QEBAJPEBG0K00PEAU_SCHRPC_DYNAMIC_TASK_INFO@@@Z; RpcSession::MigrateTaskRegistration(ushort const *,ushort const *,ulong,ushort const *,ushort const *,_SCHRPC_DYNAMIC_TASK_INFO *)
0x18004a541  mov     ebx, eax
0x18004a543  mov     [rsp+0D8h+var_98], eax
0x18004a547  test    eax, eax
0x18004a549  js      short loc_18004A566
0x18004a54b  mov     rcx, rdi; lpCriticalSection
0x18004a54e  call    cs:__imp_LeaveCriticalSection
0x18004a555  nop     dword ptr [rax+rax+00h]
0x18004a55a  nop
0x18004a55b  jmp     short loc_18004A57D
0x18004a55d  mov     ebx, 80070032h
0x18004a562  mov     [rsp+0D8h+var_98], ebx
0x18004a566  mov     rcx, rdi; lpCriticalSection
0x18004a569  call    cs:__imp_LeaveCriticalSection
0x18004a570  nop     dword ptr [rax+rax+00h]
0x18004a575  mov     eax, ebx
0x18004a577  jmp     short loc_18004A57F
0x18004a579  mov     ebx, [rsp+0D8h+var_98]
0x18004a57d  mov     eax, ebx
0x18004a57f  mov     rcx, [rsp+0D8h+var_40]
0x18004a587  xor     rcx, rsp; StackCookie
0x18004a58a  call    __security_check_cookie
0x18004a58f  add     rsp, 0A0h
0x18004a596  pop     r15
0x18004a598  pop     r14
0x18004a59a  pop     r13
0x18004a59c  pop     r12
0x18004a59e  pop     rdi
0x18004a59f  pop     rsi
0x18004a5a0  pop     rbx
0x18004a5a1  retn
```
