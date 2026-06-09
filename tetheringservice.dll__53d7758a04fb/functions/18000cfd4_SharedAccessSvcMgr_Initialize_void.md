# SharedAccessSvcMgr::Initialize(void)

- ea: `0x18000cfd4`
- end: `0x18000d12c`
- name: `?Initialize@SharedAccessSvcMgr@@QEAAJXZ`
- size: `344`
- prototype: `__int64 __fastcall(SharedAccessSvcMgr *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x18001935c`

## callees

- `0x18000bf4c`
- `0x18000bf74`
- `0x18000cfd4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d02a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d070`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d02a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d070`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18000d0c5`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18000d0e3`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18000d0c5`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18000d0e3`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18000d05d`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18000d05d`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18000d01c`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18000d01c`

## string_xrefs

- `0x18000d051`: `SharedAccess`

## pseudocode

```c
__int64 __fastcall SharedAccessSvcMgr::Initialize(SharedAccessSvcMgr *this)
{
  SC_HANDLE v2; // rax
  signed int LastError; // ebx
  TetheringServiceTelemetry *v4; // rcx
  __int64 v5; // rdx
  SC_HANDLE v6; // rax
  bool v7; // sf

  if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_61b13f64d1073f22fbe44920aae21d64_Traceguids);
  }
  v2 = OpenSCManagerW(0, 0, 1u);
  *(_QWORD *)this = v2;
  if ( v2 )
  {
    LastError = 0;
    v6 = OpenServiceW(v2, L"SharedAccess", 0x135u);
    *((_QWORD *)this + 1) = v6;
    if ( v6 )
    {
LABEL_20:
      v4 = WPP_GLOBAL_Control;
      goto LABEL_21;
    }
    LastError = GetLastError();
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v5 = 12;
      goto LABEL_12;
    }
  }
  else
  {
    LastError = GetLastError();
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v5 = 11;
LABEL_12:
      WPP_SF_d(*((_QWORD *)v4 + 2), v5, &WPP_61b13f64d1073f22fbe44920aae21d64_Traceguids, (unsigned int)LastError);
      v4 = WPP_GLOBAL_Control;
    }
  }
  v7 = LastError < 0;
  if ( LastError > 0 )
  {
    LastError = (unsigned __int16)LastError | 0x80070000;
    v7 = LastError < 0;
  }
  if ( v7 )
  {
    if ( *((_QWORD *)this + 1) )
    {
      CloseServiceHandle(*((SC_HANDLE *)this + 1));
      *((_QWORD *)this + 1) = 0;
      v4 = WPP_GLOBAL_Control;
    }
    if ( *(_QWORD *)this )
    {
      CloseServiceHandle(*(SC_HANDLE *)this);
      *(_QWORD *)this = 0;
      goto LABEL_20;
    }
  }
LABEL_21:
  if ( v4 != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 8) != 0 )
    WPP_SF_d(*((_QWORD *)v4 + 2), 13, &WPP_61b13f64d1073f22fbe44920aae21d64_Traceguids, (unsigned int)LastError);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x18000cfd4  mov     [rsp+arg_0], rbx
0x18000cfd9  mov     [rsp+arg_8], rbp
0x18000cfde  push    rdi
0x18000cfdf  sub     rsp, 20h
0x18000cfe3  mov     rdi, rcx
0x18000cfe6  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cfed  lea     rbp, WPP_GLOBAL_Control
0x18000cff4  cmp     rcx, rbp
0x18000cff7  jz      short loc_18000D014
0x18000cff9  test    byte ptr [rcx+1Ch], 8
0x18000cffd  jz      short loc_18000D014
0x18000cfff  mov     rcx, [rcx+10h]
0x18000d003  lea     r8, WPP_61b13f64d1073f22fbe44920aae21d64_Traceguids
0x18000d00a  mov     edx, 0Ah
0x18000d00f  call    WPP_SF_
0x18000d014  xor     edx, edx; lpDatabaseName
0x18000d016  xor     ecx, ecx; lpMachineName
0x18000d018  lea     r8d, [rdx+1]; dwDesiredAccess
0x18000d01c  call    cs:__imp_OpenSCManagerW
0x18000d022  mov     [rdi], rax
0x18000d025  test    rax, rax
0x18000d028  jnz     short loc_18000D04B
0x18000d02a  call    cs:__imp_GetLastError
0x18000d030  mov     ebx, eax
0x18000d032  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d039  cmp     rcx, rbp
0x18000d03c  jz      short loc_18000D0A9
0x18000d03e  test    byte ptr [rcx+1Ch], 1
0x18000d042  jz      short loc_18000D0A9
0x18000d044  mov     edx, 0Bh
0x18000d049  jmp     short loc_18000D08F
0x18000d04b  mov     r8d, 135h; dwDesiredAccess
0x18000d051  lea     rdx, aSharedaccess; "SharedAccess"
0x18000d058  mov     rcx, rax; hSCManager
0x18000d05b  xor     ebx, ebx
0x18000d05d  call    cs:__imp_OpenServiceW
0x18000d063  mov     [rdi+8], rax
0x18000d067  test    rax, rax
0x18000d06a  jnz     loc_18000D0F0
0x18000d070  call    cs:__imp_GetLastError
0x18000d076  mov     ebx, eax
0x18000d078  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d07f  cmp     rcx, rbp
0x18000d082  jz      short loc_18000D0A9
0x18000d084  test    byte ptr [rcx+1Ch], 1
0x18000d088  jz      short loc_18000D0A9
0x18000d08a  mov     edx, 0Ch
0x18000d08f  mov     rcx, [rcx+10h]
0x18000d093  lea     r8, WPP_61b13f64d1073f22fbe44920aae21d64_Traceguids
0x18000d09a  mov     r9d, ebx
0x18000d09d  call    WPP_SF_d
0x18000d0a2  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d0a9  test    ebx, ebx
0x18000d0ab  jle     short loc_18000D0B8
0x18000d0ad  movzx   ebx, bx
0x18000d0b0  or      ebx, 80070000h
0x18000d0b6  test    ebx, ebx
0x18000d0b8  jns     short loc_18000D0F7
0x18000d0ba  cmp     qword ptr [rdi+8], 0
0x18000d0bf  jz      short loc_18000D0DA
0x18000d0c1  mov     rcx, [rdi+8]; hSCObject
0x18000d0c5  call    cs:__imp_CloseServiceHandle
0x18000d0cb  mov     qword ptr [rdi+8], 0
0x18000d0d3  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d0da  cmp     qword ptr [rdi], 0
0x18000d0de  jz      short loc_18000D0F7
0x18000d0e0  mov     rcx, [rdi]; hSCObject
0x18000d0e3  call    cs:__imp_CloseServiceHandle
0x18000d0e9  mov     qword ptr [rdi], 0
0x18000d0f0  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d0f7  cmp     rcx, rbp
0x18000d0fa  jz      short loc_18000D11A
0x18000d0fc  test    byte ptr [rcx+1Ch], 8
0x18000d100  jz      short loc_18000D11A
0x18000d102  mov     rcx, [rcx+10h]
0x18000d106  lea     r8, WPP_61b13f64d1073f22fbe44920aae21d64_Traceguids
0x18000d10d  mov     edx, 0Dh
0x18000d112  mov     r9d, ebx
0x18000d115  call    WPP_SF_d
0x18000d11a  mov     rbp, [rsp+28h+arg_8]
0x18000d11f  mov     eax, ebx
0x18000d121  mov     rbx, [rsp+28h+arg_0]
0x18000d126  add     rsp, 20h
0x18000d12a  pop     rdi
0x18000d12b  retn
```
