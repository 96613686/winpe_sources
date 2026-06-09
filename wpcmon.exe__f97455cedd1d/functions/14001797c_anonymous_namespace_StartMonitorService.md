# _anonymous_namespace_::StartMonitorService

- ea: `0x14001797c`
- end: `0x140017c6f`
- name: `_anonymous_namespace_::StartMonitorService`
- size: `755`
- prototype: `BOOL()`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task`

## callers

- `0x14001b070`

## callees

- `0x140005530`
- `0x140006338`
- `0x14001797c`
- `0x140018e34`
- `0x14001f62c`
- `0x14001f6b4`
- `0x140060f58`

## import_xrefs

- `ADVAPI32!QueryServiceStatusEx` at `0x140017a0c`
- `ADVAPI32!QueryServiceStatusEx` at `0x140017a0c`
- `ADVAPI32!OpenServiceW` at `0x1400179cb`
- `ADVAPI32!OpenServiceW` at `0x1400179cb`
- `ADVAPI32!StartServiceW` at `0x140017a3a`
- `ADVAPI32!StartServiceW` at `0x140017a3a`
- `ADVAPI32!OpenSCManagerW` at `0x1400179a5`
- `ADVAPI32!OpenSCManagerW` at `0x1400179a5`
- `ADVAPI32!CloseServiceHandle` at `0x140017a75`
- `ADVAPI32!CloseServiceHandle` at `0x140017a7f`
- `ADVAPI32!CloseServiceHandle` at `0x140017a75`
- `ADVAPI32!CloseServiceHandle` at `0x140017a7f`
- `KERNEL32!GetLastError` at `0x140017ae7`
- `KERNEL32!GetLastError` at `0x140017b49`
- `KERNEL32!GetLastError` at `0x140017bab`
- `KERNEL32!GetLastError` at `0x140017c0d`
- `KERNEL32!GetLastError` at `0x140017ae7`
- `KERNEL32!GetLastError` at `0x140017b49`
- `KERNEL32!GetLastError` at `0x140017bab`
- `KERNEL32!GetLastError` at `0x140017c0d`

## pseudocode

```c
// Hidden C++ exception states: #wind=24
BOOL anonymous_namespace_::StartMonitorService()
{
  SC_HANDLE v0; // rax
  SC_HANDLE v1; // rsi
  SC_HANDLE v2; // rdi
  unsigned int v3; // ebx
  signed int LastError; // eax
  unsigned int v6; // ebx
  signed int v7; // eax
  unsigned int v8; // ebx
  signed int v9; // eax
  unsigned int v10; // ebx
  signed int v11; // eax
  unsigned int v12; // ebx
  DWORD pcbBytesNeeded; // [rsp+30h] [rbp-39h] BYREF
  _BYTE pExceptionObject[40]; // [rsp+38h] [rbp-31h] BYREF
  SC_HANDLE v15; // [rsp+60h] [rbp-9h]
  SC_HANDLE v16; // [rsp+68h] [rbp-1h]
  BYTE Buffer[16]; // [rsp+70h] [rbp+7h] BYREF
  __int128 v18; // [rsp+80h] [rbp+17h]
  int v19; // [rsp+90h] [rbp+27h]

  v0 = OpenSCManagerW(0, 0, 0x80000000);
  v1 = v0;
  v15 = v0;
  if ( !v0 )
  {
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError > 0 )
      v6 = (unsigned __int16)LastError | 0x80070000;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 13, &WPP_a6cd8b416fde3d696d6e4fad87c378e4_Traceguids, v6);
    ErrorCodeException::ErrorCodeException((ErrorCodeException *)pExceptionObject, v6);
    throw (ErrorCodeException *)pExceptionObject;
  }
  v2 = OpenServiceW(v0, L"wpcmonsvc", 0x14u);
  v16 = v2;
  if ( !v2 )
  {
    v7 = GetLastError();
    v8 = v7;
    if ( v7 > 0 )
      v8 = (unsigned __int16)v7 | 0x80070000;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 14, &WPP_a6cd8b416fde3d696d6e4fad87c378e4_Traceguids, v8);
    ErrorCodeException::ErrorCodeException((ErrorCodeException *)pExceptionObject, v8);
    throw (ErrorCodeException *)pExceptionObject;
  }
  *(_OWORD *)Buffer = 0;
  v18 = 0;
  v19 = 0;
  pcbBytesNeeded = 0;
  if ( !QueryServiceStatusEx(v2, SC_STATUS_PROCESS_INFO, Buffer, 0x24u, &pcbBytesNeeded) )
  {
    v9 = GetLastError();
    v10 = v9;
    if ( v9 > 0 )
      v10 = (unsigned __int16)v9 | 0x80070000;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 15, &WPP_a6cd8b416fde3d696d6e4fad87c378e4_Traceguids, v10);
    ErrorCodeException::ErrorCodeException((ErrorCodeException *)pExceptionObject, v10);
    throw (ErrorCodeException *)pExceptionObject;
  }
  if ( *(_DWORD *)&Buffer[4] != 4 )
  {
    anonymous_namespace_::WaitIfServicePending(v2, Buffer);
    if ( !StartServiceW(v2, 0, 0) )
    {
      v11 = GetLastError();
      v12 = v11;
      if ( v11 > 0 )
        v12 = (unsigned __int16)v11 | 0x80070000;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
        WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 16, &WPP_a6cd8b416fde3d696d6e4fad87c378e4_Traceguids, v12);
      ErrorCodeException::ErrorCodeException((ErrorCodeException *)pExceptionObject, v12);
      throw (ErrorCodeException *)pExceptionObject;
    }
    anonymous_namespace_::WaitIfServicePending(v2, Buffer);
    v3 = *(_DWORD *)&Buffer[12];
    if ( *(int *)&Buffer[12] > 0 )
      v3 = *(unsigned __int16 *)&Buffer[12] | 0x80070000;
    if ( *(_DWORD *)&Buffer[4] == 4 )
    {
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
        WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 17, &WPP_a6cd8b416fde3d696d6e4fad87c378e4_Traceguids);
      ErrorCodeException::ErrorCodeException((ErrorCodeException *)pExceptionObject, v3);
      throw (ErrorCodeException *)pExceptionObject;
    }
  }
  CloseServiceHandle(v2);
  return CloseServiceHandle(v1);
}

```

## disassembly

```asm
0x14001797c  push    rbp
0x14001797e  push    rbx
0x14001797f  push    rsi
0x140017980  push    rdi
0x140017981  lea     rbp, [rsp-3Fh]
0x140017986  sub     rsp, 0A8h
0x14001798d  mov     rax, cs:__security_cookie
0x140017994  xor     rax, rsp
0x140017997  mov     [rbp+57h+var_28], rax
0x14001799b  xor     edx, edx; lpDatabaseName
0x14001799d  xor     ecx, ecx; lpMachineName
0x14001799f  mov     r8d, 80000000h; dwDesiredAccess
0x1400179a5  call    cs:__imp_OpenSCManagerW
0x1400179ab  mov     rsi, rax
0x1400179ae  mov     [rbp+57h+var_60], rax
0x1400179b2  test    rax, rax
0x1400179b5  jz      loc_140017AE7
0x1400179bb  mov     r8d, 14h; dwDesiredAccess
0x1400179c1  lea     rdx, ServiceName; "wpcmonsvc"
0x1400179c8  mov     rcx, rax; hSCManager
0x1400179cb  call    cs:__imp_OpenServiceW
0x1400179d1  mov     rdi, rax
0x1400179d4  mov     [rbp+57h+var_58], rax
0x1400179d8  test    rax, rax
0x1400179db  jz      loc_140017B49
0x1400179e1  xorps   xmm0, xmm0
0x1400179e4  xor     eax, eax
0x1400179e6  movups  xmmword ptr [rbp+57h+Buffer], xmm0
0x1400179ea  movups  [rbp+57h+var_40], xmm0
0x1400179ee  mov     [rbp+57h+var_30], eax
0x1400179f1  mov     [rbp+57h+var_90], eax
0x1400179f4  lea     rax, [rbp+57h+var_90]
0x1400179f8  mov     [rsp+0C0h+pcbBytesNeeded], rax; pcbBytesNeeded
0x1400179fd  mov     r9d, 24h ; '$'; cbBufSize
0x140017a03  lea     r8, [rbp+57h+Buffer]; lpBuffer
0x140017a07  xor     edx, edx; InfoLevel
0x140017a09  mov     rcx, rdi; hService
0x140017a0c  call    cs:__imp_QueryServiceStatusEx
0x140017a12  test    eax, eax
0x140017a14  jz      loc_140017BAB
0x140017a1a  cmp     dword ptr [rbp+57h+Buffer+4], 4
0x140017a1e  jz      short loc_140017A72
0x140017a20  mov     r8d, 3
0x140017a26  lea     rdx, [rbp+57h+Buffer]; lpBuffer
0x140017a2a  mov     rcx, rdi; hService
0x140017a2d  call    _anonymous_namespace___WaitIfServicePending
0x140017a32  xor     r8d, r8d; lpServiceArgVectors
0x140017a35  xor     edx, edx; dwNumServiceArgs
0x140017a37  mov     rcx, rdi; hService
0x140017a3a  call    cs:__imp_StartServiceW
0x140017a40  test    eax, eax
0x140017a42  jz      loc_140017C0D
0x140017a48  mov     r8d, 2
0x140017a4e  lea     rdx, [rbp+57h+Buffer]; lpBuffer
0x140017a52  mov     rcx, rdi; hService
0x140017a55  call    _anonymous_namespace___WaitIfServicePending
0x140017a5a  mov     ebx, dword ptr [rbp+57h+Buffer+0Ch]
0x140017a5d  test    ebx, ebx
0x140017a5f  js      short loc_140017A6C
0x140017a61  jle     short loc_140017A6C
0x140017a63  movzx   ebx, bx
0x140017a66  or      ebx, 80070000h
0x140017a6c  cmp     dword ptr [rbp+57h+Buffer+4], 4
0x140017a70  jz      short loc_140017A9D
0x140017a72  mov     rcx, rdi; hSCObject
0x140017a75  call    cs:__imp_CloseServiceHandle
0x140017a7b  nop
0x140017a7c  mov     rcx, rsi; hSCObject
0x140017a7f  call    cs:__imp_CloseServiceHandle
0x140017a85  mov     rcx, [rbp+57h+var_28]
0x140017a89  xor     rcx, rsp; StackCookie
0x140017a8c  call    __security_check_cookie
0x140017a91  add     rsp, 0A8h
0x140017a98  pop     rdi
0x140017a99  pop     rsi
0x140017a9a  pop     rbx
0x140017a9b  pop     rbp
0x140017a9c  retn
0x140017a9d  lea     rax, WPP_GLOBAL_Control
0x140017aa4  mov     rcx, cs:WPP_GLOBAL_Control
0x140017aab  cmp     rcx, rax
0x140017aae  jz      short loc_140017ACB
0x140017ab0  test    byte ptr [rcx+1Ch], 1
0x140017ab4  jz      short loc_140017ACB
0x140017ab6  mov     edx, 11h
0x140017abb  lea     r8, WPP_a6cd8b416fde3d696d6e4fad87c378e4_Traceguids
0x140017ac2  mov     rcx, [rcx+10h]
0x140017ac6  call    WPP_SF_
0x140017acb  mov     edx, ebx; int
0x140017acd  lea     rcx, [rbp+57h+pExceptionObject]; this
0x140017ad1  call    ??0ErrorCodeException@@QEAA@J@Z; ErrorCodeException::ErrorCodeException(long)
0x140017ad6  lea     rdx, _TI2?AVErrorCodeException@@; pThrowInfo
0x140017add  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x140017ae1  call    _CxxThrowException_0
0x140017ae7  call    cs:__imp_GetLastError
0x140017aed  mov     ebx, eax
0x140017aef  test    eax, eax
0x140017af1  jle     short loc_140017AFC
0x140017af3  movzx   ebx, ax
0x140017af6  or      ebx, 80070000h
0x140017afc  lea     rax, WPP_GLOBAL_Control
0x140017b03  mov     rcx, cs:WPP_GLOBAL_Control
0x140017b0a  cmp     rcx, rax
0x140017b0d  jz      short loc_140017B2D
0x140017b0f  test    byte ptr [rcx+1Ch], 1
0x140017b13  jz      short loc_140017B2D
0x140017b15  mov     edx, 0Dh
0x140017b1a  mov     r9d, ebx
0x140017b1d  lea     r8, WPP_a6cd8b416fde3d696d6e4fad87c378e4_Traceguids
0x140017b24  mov     rcx, [rcx+10h]
0x140017b28  call    WPP_SF_d
0x140017b2d  mov     edx, ebx; int
0x140017b2f  lea     rcx, [rbp+57h+pExceptionObject]; this
0x140017b33  call    ??0ErrorCodeException@@QEAA@J@Z; ErrorCodeException::ErrorCodeException(long)
0x140017b38  lea     rdx, _TI2?AVErrorCodeException@@; pThrowInfo
0x140017b3f  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x140017b43  call    _CxxThrowException_0
0x140017b49  call    cs:__imp_GetLastError
0x140017b4f  mov     ebx, eax
0x140017b51  test    eax, eax
0x140017b53  jle     short loc_140017B5E
0x140017b55  movzx   ebx, ax
0x140017b58  or      ebx, 80070000h
0x140017b5e  lea     rax, WPP_GLOBAL_Control
0x140017b65  mov     rcx, cs:WPP_GLOBAL_Control
0x140017b6c  cmp     rcx, rax
0x140017b6f  jz      short loc_140017B8F
0x140017b71  test    byte ptr [rcx+1Ch], 1
0x140017b75  jz      short loc_140017B8F
0x140017b77  mov     edx, 0Eh
0x140017b7c  mov     r9d, ebx
0x140017b7f  lea     r8, WPP_a6cd8b416fde3d696d6e4fad87c378e4_Traceguids
0x140017b86  mov     rcx, [rcx+10h]
0x140017b8a  call    WPP_SF_d
0x140017b8f  mov     edx, ebx; int
0x140017b91  lea     rcx, [rbp+57h+pExceptionObject]; this
0x140017b95  call    ??0ErrorCodeException@@QEAA@J@Z; ErrorCodeException::ErrorCodeException(long)
0x140017b9a  lea     rdx, _TI2?AVErrorCodeException@@; pThrowInfo
0x140017ba1  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x140017ba5  call    _CxxThrowException_0
0x140017bab  call    cs:__imp_GetLastError
0x140017bb1  mov     ebx, eax
0x140017bb3  test    eax, eax
0x140017bb5  jle     short loc_140017BC0
0x140017bb7  movzx   ebx, ax
0x140017bba  or      ebx, 80070000h
0x140017bc0  lea     rax, WPP_GLOBAL_Control
0x140017bc7  mov     rcx, cs:WPP_GLOBAL_Control
0x140017bce  cmp     rcx, rax
0x140017bd1  jz      short loc_140017BF1
0x140017bd3  test    byte ptr [rcx+1Ch], 1
0x140017bd7  jz      short loc_140017BF1
0x140017bd9  mov     edx, 0Fh
0x140017bde  mov     r9d, ebx
0x140017be1  lea     r8, WPP_a6cd8b416fde3d696d6e4fad87c378e4_Traceguids
0x140017be8  mov     rcx, [rcx+10h]
0x140017bec  call    WPP_SF_d
0x140017bf1  mov     edx, ebx; int
0x140017bf3  lea     rcx, [rbp+57h+pExceptionObject]; this
0x140017bf7  call    ??0ErrorCodeException@@QEAA@J@Z; ErrorCodeException::ErrorCodeException(long)
0x140017bfc  lea     rdx, _TI2?AVErrorCodeException@@; pThrowInfo
0x140017c03  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x140017c07  call    _CxxThrowException_0
0x140017c0d  call    cs:__imp_GetLastError
0x140017c13  mov     ebx, eax
0x140017c15  test    eax, eax
0x140017c17  jle     short loc_140017C22
0x140017c19  movzx   ebx, ax
0x140017c1c  or      ebx, 80070000h
0x140017c22  lea     rax, WPP_GLOBAL_Control
0x140017c29  mov     rcx, cs:WPP_GLOBAL_Control
0x140017c30  cmp     rcx, rax
0x140017c33  jz      short loc_140017C53
0x140017c35  test    byte ptr [rcx+1Ch], 1
0x140017c39  jz      short loc_140017C53
0x140017c3b  mov     edx, 10h
0x140017c40  mov     r9d, ebx
0x140017c43  lea     r8, WPP_a6cd8b416fde3d696d6e4fad87c378e4_Traceguids
0x140017c4a  mov     rcx, [rcx+10h]
0x140017c4e  call    WPP_SF_d
0x140017c53  mov     edx, ebx; int
0x140017c55  lea     rcx, [rbp+57h+pExceptionObject]; this
0x140017c59  call    ??0ErrorCodeException@@QEAA@J@Z; ErrorCodeException::ErrorCodeException(long)
0x140017c5e  lea     rdx, _TI2?AVErrorCodeException@@; pThrowInfo
0x140017c65  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x140017c69  call    _CxxThrowException_0
```
