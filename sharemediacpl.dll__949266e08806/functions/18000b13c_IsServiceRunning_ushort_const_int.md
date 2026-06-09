# IsServiceRunning(ushort const *,int *)

- ea: `0x18000b13c`
- end: `0x18000b2fb`
- name: `?IsServiceRunning@@YAJPEBGPEAH@Z`
- size: `447`
- prototype: `__int64 __fastcall(LPCWSTR lpServiceName, int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x18000c3d0`

## callees

- `0x180001d60`
- `0x180003860`
- `0x180003888`
- `0x18000b13c`

## import_xrefs

- `ADVAPI32!OpenSCManagerW` at `0x18000b1fb`
- `ADVAPI32!OpenSCManagerW` at `0x18000b1fb`
- `ADVAPI32!OpenServiceW` at `0x18000b233`
- `ADVAPI32!OpenServiceW` at `0x18000b233`
- `ADVAPI32!QueryServiceStatus` at `0x18000b26d`
- `ADVAPI32!QueryServiceStatus` at `0x18000b26d`
- `ADVAPI32!CloseServiceHandle` at `0x18000b29e`
- `ADVAPI32!CloseServiceHandle` at `0x18000b2a7`
- `ADVAPI32!CloseServiceHandle` at `0x18000b29e`
- `ADVAPI32!CloseServiceHandle` at `0x18000b2a7`
- `KERNEL32!GetLastError` at `0x18000b209`
- `KERNEL32!GetLastError` at `0x18000b241`
- `KERNEL32!GetLastError` at `0x18000b277`
- `KERNEL32!GetLastError` at `0x18000b209`
- `KERNEL32!GetLastError` at `0x18000b241`
- `KERNEL32!GetLastError` at `0x18000b277`

## pseudocode

```c
__int64 __fastcall IsServiceRunning(LPCWSTR lpServiceName, int *a2)
{
  _QWORD *v4; // r10
  LPCWSTR v5; // rax
  __int64 v6; // r8
  unsigned int v7; // ebx
  SC_HANDLE v8; // rax
  SC_HANDLE v9; // rsi
  signed int v10; // eax
  SC_HANDLE v11; // rax
  SC_HANDLE v12; // rdi
  signed int v13; // eax
  signed int LastError; // eax
  _SERVICE_STATUS ServiceStatus; // [rsp+20h] [rbp-58h] BYREF

  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 265, &WPP_59386dd0a0913b67da6dc13cee28e88f_Traceguids);
    v4 = WPP_GLOBAL_Control;
  }
  if ( !a2 || !lpServiceName )
    goto LABEL_10;
  v5 = lpServiceName;
  v6 = 0x7FFFFFFF;
  do
  {
    if ( !*v5 )
      break;
    ++v5;
    --v6;
  }
  while ( v6 );
  v7 = 0;
  if ( (v6 != 0 ? 0x7FFFFFFF - (_DWORD)v6 : 0) == 0 )
LABEL_10:
    v7 = -2147467261;
  if ( (v7 & 0x80000000) == 0 )
  {
    *a2 = 0;
    v8 = OpenSCManagerW(0, 0, 0x20001u);
    v9 = v8;
    if ( v8 )
    {
      v11 = OpenServiceW(v8, lpServiceName, 4u);
      v12 = v11;
      if ( v11 )
      {
        memset(&ServiceStatus, 0, sizeof(ServiceStatus));
        if ( QueryServiceStatus(v11, &ServiceStatus) )
        {
          *a2 = ServiceStatus.dwCurrentState == 4;
        }
        else
        {
          LastError = GetLastError();
          v7 = LastError;
          if ( LastError > 0 )
            v7 = (unsigned __int16)LastError | 0x80070000;
        }
        CloseServiceHandle(v12);
      }
      else
      {
        v13 = GetLastError();
        v7 = v13;
        if ( v13 > 0 )
          v7 = (unsigned __int16)v13 | 0x80070000;
      }
      CloseServiceHandle(v9);
    }
    else
    {
      v10 = GetLastError();
      v7 = v10;
      if ( v10 > 0 )
        v7 = (unsigned __int16)v10 | 0x80070000;
    }
    v4 = WPP_GLOBAL_Control;
  }
  if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 0x20) != 0 )
    WPP_SF_d(v4[2], 266, &WPP_59386dd0a0913b67da6dc13cee28e88f_Traceguids, v7);
  return v7;
}

```

## disassembly

```asm
0x18000b13c  mov     [rsp+arg_10], rbx
0x18000b141  push    rbp
0x18000b142  push    rsi
0x18000b143  push    rdi
0x18000b144  push    r14
0x18000b146  push    r15
0x18000b148  sub     rsp, 50h
0x18000b14c  mov     rax, cs:__security_cookie
0x18000b153  xor     rax, rsp
0x18000b156  mov     [rsp+78h+var_38], rax
0x18000b15b  mov     r14, rdx
0x18000b15e  mov     rdi, rcx
0x18000b161  mov     r10, cs:WPP_GLOBAL_Control
0x18000b168  lea     r15, WPP_GLOBAL_Control
0x18000b16f  cmp     r10, r15
0x18000b172  jz      short loc_18000B197
0x18000b174  test    byte ptr [r10+1Ch], 20h
0x18000b179  jz      short loc_18000B197
0x18000b17b  mov     rcx, [r10+10h]
0x18000b17f  lea     r8, WPP_59386dd0a0913b67da6dc13cee28e88f_Traceguids
0x18000b186  mov     edx, 109h
0x18000b18b  call    WPP_SF_
0x18000b190  mov     r10, cs:WPP_GLOBAL_Control
0x18000b197  xor     ebp, ebp
0x18000b199  test    r14, r14
0x18000b19c  jz      short loc_18000B1E1
0x18000b19e  test    rdi, rdi
0x18000b1a1  jz      short loc_18000B1E1
0x18000b1a3  mov     r9d, 7FFFFFFFh
0x18000b1a9  mov     rax, rdi
0x18000b1ac  mov     r8d, r9d
0x18000b1af  cmp     [rax], bp
0x18000b1b2  jz      short loc_18000B1BE
0x18000b1b4  add     rax, 2
0x18000b1b8  sub     r8, 1
0x18000b1bc  jnz     short loc_18000B1AF
0x18000b1be  sub     r9d, r8d
0x18000b1c1  mov     rax, r8
0x18000b1c4  neg     rax
0x18000b1c7  mov     rdx, r8
0x18000b1ca  mov     ebx, ebp
0x18000b1cc  sbb     ecx, ecx
0x18000b1ce  and     ecx, r9d
0x18000b1d1  neg     rdx
0x18000b1d4  sbb     edx, edx
0x18000b1d6  and     edx, ecx
0x18000b1d8  neg     r8
0x18000b1db  sbb     eax, eax
0x18000b1dd  test    edx, eax
0x18000b1df  ja      short loc_18000B1E6
0x18000b1e1  mov     ebx, 80004003h
0x18000b1e6  test    ebx, ebx
0x18000b1e8  js      loc_18000B2B4
0x18000b1ee  xor     edx, edx; lpDatabaseName
0x18000b1f0  mov     [r14], ebp
0x18000b1f3  xor     ecx, ecx; lpMachineName
0x18000b1f5  mov     r8d, 20001h; dwDesiredAccess
0x18000b1fb  call    cs:__imp_OpenSCManagerW
0x18000b201  mov     rsi, rax
0x18000b204  test    rax, rax
0x18000b207  jnz     short loc_18000B227
0x18000b209  call    cs:__imp_GetLastError
0x18000b20f  mov     ebx, eax
0x18000b211  test    eax, eax
0x18000b213  jle     loc_18000B2AD
0x18000b219  movzx   ebx, ax
0x18000b21c  or      ebx, 80070000h
0x18000b222  jmp     loc_18000B2AD
0x18000b227  mov     r8d, 4; dwDesiredAccess
0x18000b22d  mov     rdx, rdi; lpServiceName
0x18000b230  mov     rcx, rsi; hSCManager
0x18000b233  call    cs:__imp_OpenServiceW
0x18000b239  mov     rdi, rax
0x18000b23c  test    rax, rax
0x18000b23f  jnz     short loc_18000B258
0x18000b241  call    cs:__imp_GetLastError
0x18000b247  mov     ebx, eax
0x18000b249  test    eax, eax
0x18000b24b  jle     short loc_18000B2A4
0x18000b24d  movzx   ebx, ax
0x18000b250  or      ebx, 80070000h
0x18000b256  jmp     short loc_18000B2A4
0x18000b258  xorps   xmm0, xmm0
0x18000b25b  lea     rdx, [rsp+78h+ServiceStatus]; lpServiceStatus
0x18000b260  movups  xmmword ptr [rsp+78h+ServiceStatus.dwServiceType], xmm0
0x18000b265  mov     rcx, rdi; hService
0x18000b268  movups  xmmword ptr [rsp+78h+ServiceStatus.dwWin32ExitCode], xmm0
0x18000b26d  call    cs:__imp_QueryServiceStatus
0x18000b273  test    eax, eax
0x18000b275  jnz     short loc_18000B28E
0x18000b277  call    cs:__imp_GetLastError
0x18000b27d  mov     ebx, eax
0x18000b27f  test    eax, eax
0x18000b281  jle     short loc_18000B29B
0x18000b283  movzx   ebx, ax
0x18000b286  or      ebx, 80070000h
0x18000b28c  jmp     short loc_18000B29B
0x18000b28e  cmp     [rsp+78h+ServiceStatus.dwCurrentState], 4
0x18000b293  mov     eax, ebp
0x18000b295  setz    al
0x18000b298  mov     [r14], eax
0x18000b29b  mov     rcx, rdi; hSCObject
0x18000b29e  call    cs:__imp_CloseServiceHandle
0x18000b2a4  mov     rcx, rsi; hSCObject
0x18000b2a7  call    cs:__imp_CloseServiceHandle
0x18000b2ad  mov     r10, cs:WPP_GLOBAL_Control
0x18000b2b4  cmp     r10, r15
0x18000b2b7  jz      short loc_18000B2D8
0x18000b2b9  test    byte ptr [r10+1Ch], 20h
0x18000b2be  jz      short loc_18000B2D8
0x18000b2c0  mov     rcx, [r10+10h]
0x18000b2c4  lea     r8, WPP_59386dd0a0913b67da6dc13cee28e88f_Traceguids
0x18000b2cb  mov     edx, 10Ah
0x18000b2d0  mov     r9d, ebx
0x18000b2d3  call    WPP_SF_d
0x18000b2d8  mov     eax, ebx
0x18000b2da  mov     rcx, [rsp+78h+var_38]
0x18000b2df  xor     rcx, rsp; StackCookie
0x18000b2e2  call    __security_check_cookie
0x18000b2e7  mov     rbx, [rsp+78h+arg_10]
0x18000b2ef  add     rsp, 50h
0x18000b2f3  pop     r15
0x18000b2f5  pop     r14
0x18000b2f7  pop     rdi
0x18000b2f8  pop     rsi
0x18000b2f9  pop     rbp
0x18000b2fa  retn
```
