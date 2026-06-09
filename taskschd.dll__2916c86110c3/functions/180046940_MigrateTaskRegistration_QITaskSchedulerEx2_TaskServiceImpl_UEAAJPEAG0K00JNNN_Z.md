# ?MigrateTaskRegistration@?QITaskSchedulerEx2@@TaskServiceImpl@@UEAAJPEAG0K00JNNN@Z

- ea: `0x180046940`
- end: `0x180046c54`
- name: `?MigrateTaskRegistration@?QITaskSchedulerEx2@@TaskServiceImpl@@UEAAJPEAG0K00JNNN@Z`
- size: `788`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x18004611c`
- `0x180046940`
- `0x18004e1f8`
- `0x18004e950`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180046a1c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180046a57`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180046ac4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180046aff`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180046b6f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180046baa`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180046c0b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180046c20`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180046a1c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180046a57`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180046ac4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180046aff`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180046b6f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180046baa`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180046c0b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180046c20`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180046998`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180046998`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046a04`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046a3f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046aac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046ae7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046b57`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046b92`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046a04`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046a3f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046aac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046ae7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046b57`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046b92`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180046a33`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180046adb`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180046b86`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180046a33`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180046adb`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180046b86`

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
0x180046940  push    rbx
0x180046942  push    rsi
0x180046943  push    rdi
0x180046944  push    r12
0x180046946  push    r13
0x180046948  push    r14
0x18004694a  push    r15
0x18004694c  sub     rsp, 0A0h
0x180046953  mov     rax, cs:__security_cookie
0x18004695a  xor     rax, rsp
0x18004695d  mov     [rsp+0D8h+var_40], rax
0x180046965  mov     r15d, r9d
0x180046968  mov     r14, r8
0x18004696b  mov     rsi, rdx
0x18004696e  mov     rbx, rcx
0x180046971  mov     r12, [rsp+0D8h+arg_20]
0x180046979  mov     r13, [rsp+0D8h+arg_28]
0x180046981  mov     [rsp+0D8h+var_98], 0
0x180046989  lea     rdi, [rcx+100h]
0x180046990  mov     [rsp+0D8h+var_78], rdi
0x180046995  mov     rcx, rdi; lpCriticalSection
0x180046998  call    cs:__imp_EnterCriticalSection
0x18004699e  nop
0x18004699f  xorps   xmm0, xmm0
0x1800469a2  movups  xmmword ptr [rsp+0D8h+SystemTime.wYear], xmm0
0x1800469a7  xor     edx, edx
0x1800469a9  mov     qword ptr [rsp+0D8h+FileTime.dwLowDateTime], rdx
0x1800469ae  mov     [rsp+0D8h+var_54], rdx
0x1800469b6  mov     [rsp+0D8h+var_4C], rdx
0x1800469be  mov     eax, [rsp+0D8h+arg_30]
0x1800469c5  mov     [rsp+0D8h+var_60], eax
0x1800469c9  mov     [rsp+0D8h+var_5C], rdx
0x1800469ce  movsd   xmm0, [rsp+0D8h+arg_38]
0x1800469d7  ucomisd xmm0, cs:__real@0000000000000000
0x1800469df  jp      short loc_1800469E7
0x1800469e1  jz      loc_180046A6E
0x1800469e7  movsd   [rsp+0D8h+var_88], xmm0
0x1800469ed  mov     [rsp+0D8h+var_80], edx
0x1800469f1  lea     rdx, [rsp+0D8h+SystemTime]; struct _SYSTEMTIME *
0x1800469f6  lea     rcx, [rsp+0D8h+var_88]; this
0x1800469fb  call    ?GetAsSystemTime@COleDateTime@ATL@@QEBA_NAEAU_SYSTEMTIME@@@Z; ATL::COleDateTime::GetAsSystemTime(_SYSTEMTIME &)
0x180046a00  test    al, al
0x180046a02  jnz     short loc_180046A29
0x180046a04  call    cs:__imp_GetLastError
0x180046a0a  mov     ebx, eax
0x180046a0c  test    eax, eax
0x180046a0e  jle     short loc_180046A19
0x180046a10  movzx   ebx, ax
0x180046a13  or      ebx, 80070000h
0x180046a19  mov     rcx, rdi; lpCriticalSection
0x180046a1c  call    cs:__imp_LeaveCriticalSection
0x180046a22  mov     eax, ebx
0x180046a24  jmp     loc_180046C30
0x180046a29  lea     rdx, [rsp+0D8h+FileTime]; lpFileTime
0x180046a2e  lea     rcx, [rsp+0D8h+SystemTime]; lpSystemTime
0x180046a33  call    cs:__imp_SystemTimeToFileTime
0x180046a39  xor     edx, edx
0x180046a3b  test    eax, eax
0x180046a3d  jnz     short loc_180046A64
0x180046a3f  call    cs:__imp_GetLastError
0x180046a45  mov     ebx, eax
0x180046a47  test    eax, eax
0x180046a49  jle     short loc_180046A54
0x180046a4b  movzx   ebx, ax
0x180046a4e  or      ebx, 80070000h
0x180046a54  mov     rcx, rdi; lpCriticalSection
0x180046a57  call    cs:__imp_LeaveCriticalSection
0x180046a5d  mov     eax, ebx
0x180046a5f  jmp     loc_180046C30
0x180046a64  mov     rax, qword ptr [rsp+0D8h+FileTime.dwLowDateTime]
0x180046a69  mov     [rsp+0D8h+var_5C], rax
0x180046a6e  mov     [rsp+0D8h+var_4C], rdx
0x180046a76  movsd   xmm0, [rsp+0D8h+arg_48]
0x180046a7f  ucomisd xmm0, cs:__real@0000000000000000
0x180046a87  jp      short loc_180046A8F
0x180046a89  jz      loc_180046B19
0x180046a8f  movsd   [rsp+0D8h+var_88], xmm0
0x180046a95  mov     [rsp+0D8h+var_80], edx
0x180046a99  lea     rdx, [rsp+0D8h+SystemTime]; struct _SYSTEMTIME *
0x180046a9e  lea     rcx, [rsp+0D8h+var_88]; this
0x180046aa3  call    ?GetAsSystemTime@COleDateTime@ATL@@QEBA_NAEAU_SYSTEMTIME@@@Z; ATL::COleDateTime::GetAsSystemTime(_SYSTEMTIME &)
0x180046aa8  test    al, al
0x180046aaa  jnz     short loc_180046AD1
0x180046aac  call    cs:__imp_GetLastError
0x180046ab2  mov     ebx, eax
0x180046ab4  test    eax, eax
0x180046ab6  jle     short loc_180046AC1
0x180046ab8  movzx   ebx, ax
0x180046abb  or      ebx, 80070000h
0x180046ac1  mov     rcx, rdi; lpCriticalSection
0x180046ac4  call    cs:__imp_LeaveCriticalSection
0x180046aca  mov     eax, ebx
0x180046acc  jmp     loc_180046C30
0x180046ad1  lea     rdx, [rsp+0D8h+FileTime]; lpFileTime
0x180046ad6  lea     rcx, [rsp+0D8h+SystemTime]; lpSystemTime
0x180046adb  call    cs:__imp_SystemTimeToFileTime
0x180046ae1  xor     edx, edx
0x180046ae3  test    eax, eax
0x180046ae5  jnz     short loc_180046B0C
0x180046ae7  call    cs:__imp_GetLastError
0x180046aed  mov     ebx, eax
0x180046aef  test    eax, eax
0x180046af1  jle     short loc_180046AFC
0x180046af3  movzx   ebx, ax
0x180046af6  or      ebx, 80070000h
0x180046afc  mov     rcx, rdi; lpCriticalSection
0x180046aff  call    cs:__imp_LeaveCriticalSection
0x180046b05  mov     eax, ebx
0x180046b07  jmp     loc_180046C30
0x180046b0c  mov     rax, qword ptr [rsp+0D8h+FileTime.dwLowDateTime]
0x180046b11  mov     [rsp+0D8h+var_4C], rax
0x180046b19  mov     [rsp+0D8h+var_54], rdx
0x180046b21  movsd   xmm0, [rsp+0D8h+arg_40]
0x180046b2a  ucomisd xmm0, cs:__real@0000000000000000
0x180046b32  jp      short loc_180046B3A
0x180046b34  jz      loc_180046BC1
0x180046b3a  movsd   [rsp+0D8h+var_88], xmm0
0x180046b40  mov     [rsp+0D8h+var_80], edx
0x180046b44  lea     rdx, [rsp+0D8h+SystemTime]; struct _SYSTEMTIME *
0x180046b49  lea     rcx, [rsp+0D8h+var_88]; this
0x180046b4e  call    ?GetAsSystemTime@COleDateTime@ATL@@QEBA_NAEAU_SYSTEMTIME@@@Z; ATL::COleDateTime::GetAsSystemTime(_SYSTEMTIME &)
0x180046b53  test    al, al
0x180046b55  jnz     short loc_180046B7C
0x180046b57  call    cs:__imp_GetLastError
0x180046b5d  mov     ebx, eax
0x180046b5f  test    eax, eax
0x180046b61  jle     short loc_180046B6C
0x180046b63  movzx   ebx, ax
0x180046b66  or      ebx, 80070000h
0x180046b6c  mov     rcx, rdi; lpCriticalSection
0x180046b6f  call    cs:__imp_LeaveCriticalSection
0x180046b75  mov     eax, ebx
0x180046b77  jmp     loc_180046C30
0x180046b7c  lea     rdx, [rsp+0D8h+FileTime]; lpFileTime
0x180046b81  lea     rcx, [rsp+0D8h+SystemTime]; lpSystemTime
0x180046b86  call    cs:__imp_SystemTimeToFileTime
0x180046b8c  xor     edx, edx
0x180046b8e  test    eax, eax
0x180046b90  jnz     short loc_180046BB4
0x180046b92  call    cs:__imp_GetLastError
0x180046b98  mov     ebx, eax
0x180046b9a  test    eax, eax
0x180046b9c  jle     short loc_180046BA7
0x180046b9e  movzx   ebx, ax
0x180046ba1  or      ebx, 80070000h
0x180046ba7  mov     rcx, rdi; lpCriticalSection
0x180046baa  call    cs:__imp_LeaveCriticalSection
0x180046bb0  mov     eax, ebx
0x180046bb2  jmp     short loc_180046C30
0x180046bb4  mov     rax, qword ptr [rsp+0D8h+FileTime.dwLowDateTime]
0x180046bb9  mov     [rsp+0D8h+var_54], rax
0x180046bc1  cmp     [rbx+128h], edx
0x180046bc7  jnz     short loc_180046BD0
0x180046bc9  mov     ebx, 800704E3h
0x180046bce  jmp     short loc_180046C19
0x180046bd0  mov     rcx, [rbx+130h]; this
0x180046bd7  test    rcx, rcx
0x180046bda  jz      short loc_180046C14
0x180046bdc  lea     rax, [rsp+0D8h+var_60]
0x180046be1  mov     [rsp+0D8h+var_A8], rax; struct _SCHRPC_DYNAMIC_TASK_INFO *
0x180046be6  mov     [rsp+0D8h+var_B0], r13; unsigned __int16 *
0x180046beb  mov     [rsp+0D8h+var_B8], r12; unsigned __int16 *
0x180046bf0  mov     r9d, r15d; unsigned int
0x180046bf3  mov     r8, r14; unsigned __int16 *
0x180046bf6  mov     rdx, rsi; unsigned __int16 *
0x180046bf9  call    ?MigrateTaskRegistration@RpcSession@@QEBAJPEBG0K00PEAU_SCHRPC_DYNAMIC_TASK_INFO@@@Z; RpcSession::MigrateTaskRegistration(ushort const *,ushort const *,ulong,ushort const *,ushort const *,_SCHRPC_DYNAMIC_TASK_INFO *)
0x180046bfe  mov     ebx, eax
0x180046c00  mov     [rsp+0D8h+var_98], eax
0x180046c04  test    eax, eax
0x180046c06  js      short loc_180046C1D
0x180046c08  mov     rcx, rdi; lpCriticalSection
0x180046c0b  call    cs:__imp_LeaveCriticalSection
0x180046c11  nop
0x180046c12  jmp     short loc_180046C2E
0x180046c14  mov     ebx, 80070032h
0x180046c19  mov     [rsp+0D8h+var_98], ebx
0x180046c1d  mov     rcx, rdi; lpCriticalSection
0x180046c20  call    cs:__imp_LeaveCriticalSection
0x180046c26  mov     eax, ebx
0x180046c28  jmp     short loc_180046C30
0x180046c2a  mov     ebx, [rsp+0D8h+var_98]
0x180046c2e  mov     eax, ebx
0x180046c30  mov     rcx, [rsp+0D8h+var_40]
0x180046c38  xor     rcx, rsp; StackCookie
0x180046c3b  call    __security_check_cookie
0x180046c40  add     rsp, 0A0h
0x180046c47  pop     r15
0x180046c49  pop     r14
0x180046c4b  pop     r13
0x180046c4d  pop     r12
0x180046c4f  pop     rdi
0x180046c50  pop     rsi
0x180046c51  pop     rbx
0x180046c52  retn
```
