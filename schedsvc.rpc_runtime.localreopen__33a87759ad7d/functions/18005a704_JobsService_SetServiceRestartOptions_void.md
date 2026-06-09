# JobsService::SetServiceRestartOptions(void)

- ea: `0x18005a704`
- end: `0x18005a8e6`
- name: `?SetServiceRestartOptions@JobsService@@SAJXZ`
- size: `482`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task`

## callers

- `0x18005ab30`

## callees

- `0x180054084`
- `0x18005a704`
- `0x18007e6d0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005a790`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005a7b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005a80d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005a830`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005a87f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005a8a4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005a790`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005a7b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005a80d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005a830`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005a87f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005a8a4`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfig2W` at `0x18005a857`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfig2W` at `0x18005a857`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18005a8c0`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18005a8c9`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18005a8c0`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18005a8c9`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18005a7e1`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18005a7e1`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18005a764`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18005a764`

## pseudocode

```c
__int64 JobsService::SetServiceRestartOptions(void)
{
  SC_HANDLE v0; // rax
  SC_HANDLE v1; // rsi
  DWORD v2; // eax
  signed int v3; // eax
  unsigned int v4; // ebx
  SC_HANDLE v5; // rax
  SC_HANDLE v6; // rdi
  DWORD v7; // eax
  signed int v8; // eax
  DWORD LastError; // eax
  signed int v10; // eax
  __int64 Info; // [rsp+20h] [rbp-58h] BYREF
  __int128 v13; // [rsp+28h] [rbp-50h]
  __int64 v14; // [rsp+38h] [rbp-40h]
  __int64 *v15; // [rsp+40h] [rbp-38h]
  __int64 v16; // [rsp+48h] [rbp-30h] BYREF
  int v17; // [rsp+50h] [rbp-28h]
  __int64 v18; // [rsp+54h] [rbp-24h]
  int v19; // [rsp+5Ch] [rbp-1Ch]

  Info = 86400;
  v14 = 3;
  v16 = 4;
  v15 = &v16;
  v17 = 1;
  v18 = 60000;
  v13 = 0;
  v19 = 0;
  v0 = OpenSCManagerW(0, 0, 4u);
  v1 = v0;
  if ( v0 )
  {
    v5 = OpenServiceW(v0, L"Schedule", 0x12u);
    v6 = v5;
    if ( v5 )
    {
      if ( ChangeServiceConfig2W(v5, 2u, &Info) )
      {
        v4 = 0;
      }
      else
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          LastError = GetLastError();
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, WPP_e3966bf9b81b3ab085a9dfdc4dace9ef_Traceguids, LastError);
        }
        v10 = GetLastError();
        v4 = v10;
        if ( v10 > 0 )
          v4 = (unsigned __int16)v10 | 0x80070000;
      }
      CloseServiceHandle(v6);
    }
    else
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v7 = GetLastError();
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, WPP_e3966bf9b81b3ab085a9dfdc4dace9ef_Traceguids, v7);
      }
      v8 = GetLastError();
      v4 = v8;
      if ( v8 > 0 )
        v4 = (unsigned __int16)v8 | 0x80070000;
    }
    CloseServiceHandle(v1);
  }
  else
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v2 = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, WPP_e3966bf9b81b3ab085a9dfdc4dace9ef_Traceguids, v2);
    }
    v3 = GetLastError();
    v4 = v3;
    if ( v3 > 0 )
      return (unsigned __int16)v3 | 0x80070000;
  }
  return v4;
}

```

## disassembly

```asm
0x18005a704  push    rbp
0x18005a706  push    rbx
0x18005a707  push    rsi
0x18005a708  push    rdi
0x18005a709  mov     rbp, rsp
0x18005a70c  sub     rsp, 78h
0x18005a710  mov     rax, cs:__security_cookie
0x18005a717  xor     rax, rsp
0x18005a71a  mov     [rbp+var_18], rax
0x18005a71e  mov     ebx, 4
0x18005a723  mov     [rbp+Info], 15180h
0x18005a72b  xorps   xmm0, xmm0
0x18005a72e  mov     [rbp+var_40], 3
0x18005a736  lea     rax, [rbp+var_30]
0x18005a73a  mov     [rbp+var_30], rbx
0x18005a73e  mov     r8d, ebx; dwDesiredAccess
0x18005a741  mov     [rbp+var_38], rax
0x18005a745  xor     edx, edx; lpDatabaseName
0x18005a747  mov     [rbp+var_28], 1
0x18005a74e  xor     ecx, ecx; lpMachineName
0x18005a750  mov     [rbp+var_24], 0EA60h
0x18005a758  movdqu  [rbp+var_50], xmm0
0x18005a75d  mov     [rbp+var_1C], 0
0x18005a764  call    cs:__imp_OpenSCManagerW
0x18005a76a  mov     rsi, rax
0x18005a76d  test    rax, rax
0x18005a770  jnz     short loc_18005A7D1
0x18005a772  mov     rcx, cs:WPP_GLOBAL_Control
0x18005a779  lea     rax, WPP_GLOBAL_Control
0x18005a780  cmp     rcx, rax
0x18005a783  jz      short loc_18005A7B3
0x18005a785  test    [rcx+1Ch], bl
0x18005a788  jz      short loc_18005A7B3
0x18005a78a  cmp     byte ptr [rcx+19h], 2
0x18005a78e  jb      short loc_18005A7B3
0x18005a790  call    cs:__imp_GetLastError
0x18005a796  mov     rcx, cs:WPP_GLOBAL_Control
0x18005a79d  lea     edx, [rbx+1Bh]
0x18005a7a0  mov     r9d, eax
0x18005a7a3  lea     r8, WPP_e3966bf9b81b3ab085a9dfdc4dace9ef_Traceguids
0x18005a7aa  mov     rcx, [rcx+10h]
0x18005a7ae  call    WPP_SF_d
0x18005a7b3  call    cs:__imp_GetLastError
0x18005a7b9  mov     ebx, eax
0x18005a7bb  test    eax, eax
0x18005a7bd  jle     loc_18005A8CF
0x18005a7c3  movzx   ebx, ax
0x18005a7c6  or      ebx, 80070000h
0x18005a7cc  jmp     loc_18005A8CF
0x18005a7d1  mov     r8d, 12h; dwDesiredAccess
0x18005a7d7  lea     rdx, aSchedule; "Schedule"
0x18005a7de  mov     rcx, rsi; hSCManager
0x18005a7e1  call    cs:__imp_OpenServiceW
0x18005a7e7  mov     rdi, rax
0x18005a7ea  test    rax, rax
0x18005a7ed  jnz     short loc_18005A84B
0x18005a7ef  mov     rcx, cs:WPP_GLOBAL_Control
0x18005a7f6  lea     rax, WPP_GLOBAL_Control
0x18005a7fd  cmp     rcx, rax
0x18005a800  jz      short loc_18005A830
0x18005a802  test    [rcx+1Ch], bl
0x18005a805  jz      short loc_18005A830
0x18005a807  cmp     byte ptr [rcx+19h], 2
0x18005a80b  jb      short loc_18005A830
0x18005a80d  call    cs:__imp_GetLastError
0x18005a813  mov     rcx, cs:WPP_GLOBAL_Control
0x18005a81a  lea     edx, [rdi+20h]
0x18005a81d  mov     r9d, eax
0x18005a820  lea     r8, WPP_e3966bf9b81b3ab085a9dfdc4dace9ef_Traceguids
0x18005a827  mov     rcx, [rcx+10h]
0x18005a82b  call    WPP_SF_d
0x18005a830  call    cs:__imp_GetLastError
0x18005a836  mov     ebx, eax
0x18005a838  test    eax, eax
0x18005a83a  jle     loc_18005A8C6
0x18005a840  movzx   ebx, ax
0x18005a843  or      ebx, 80070000h
0x18005a849  jmp     short loc_18005A8C6
0x18005a84b  lea     r8, [rbp+Info]; lpInfo
0x18005a84f  mov     edx, 2; dwInfoLevel
0x18005a854  mov     rcx, rdi; hService
0x18005a857  call    cs:__imp_ChangeServiceConfig2W
0x18005a85d  test    eax, eax
0x18005a85f  jnz     short loc_18005A8BB
0x18005a861  mov     rcx, cs:WPP_GLOBAL_Control
0x18005a868  lea     rax, WPP_GLOBAL_Control
0x18005a86f  cmp     rcx, rax
0x18005a872  jz      short loc_18005A8A4
0x18005a874  test    [rcx+1Ch], bl
0x18005a877  jz      short loc_18005A8A4
0x18005a879  cmp     byte ptr [rcx+19h], 2
0x18005a87d  jb      short loc_18005A8A4
0x18005a87f  call    cs:__imp_GetLastError
0x18005a885  mov     rcx, cs:WPP_GLOBAL_Control
0x18005a88c  lea     r8, WPP_e3966bf9b81b3ab085a9dfdc4dace9ef_Traceguids
0x18005a893  mov     edx, 21h ; '!'
0x18005a898  mov     r9d, eax
0x18005a89b  mov     rcx, [rcx+10h]
0x18005a89f  call    WPP_SF_d
0x18005a8a4  call    cs:__imp_GetLastError
0x18005a8aa  mov     ebx, eax
0x18005a8ac  test    eax, eax
0x18005a8ae  jle     short loc_18005A8BD
0x18005a8b0  movzx   ebx, ax
0x18005a8b3  or      ebx, 80070000h
0x18005a8b9  jmp     short loc_18005A8BD
0x18005a8bb  xor     ebx, ebx
0x18005a8bd  mov     rcx, rdi; hSCObject
0x18005a8c0  call    cs:__imp_CloseServiceHandle
0x18005a8c6  mov     rcx, rsi; hSCObject
0x18005a8c9  call    cs:__imp_CloseServiceHandle
0x18005a8cf  mov     eax, ebx
0x18005a8d1  mov     rcx, [rbp+var_18]
0x18005a8d5  xor     rcx, rsp; StackCookie
0x18005a8d8  call    __security_check_cookie
0x18005a8dd  add     rsp, 78h
0x18005a8e1  pop     rdi
0x18005a8e2  pop     rsi
0x18005a8e3  pop     rbx
0x18005a8e4  pop     rbp
0x18005a8e5  retn
```
