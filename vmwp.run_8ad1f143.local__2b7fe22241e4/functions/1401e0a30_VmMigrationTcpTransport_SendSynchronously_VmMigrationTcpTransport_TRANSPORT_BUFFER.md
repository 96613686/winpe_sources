# VmMigrationTcpTransport::SendSynchronously(VmMigrationTcpTransport::_TRANSPORT_BUFFER *)

- ea: `0x1401e0a30`
- end: `0x1401e0c3f`
- name: `?SendSynchronously@VmMigrationTcpTransport@@IEAAJPEAU_TRANSPORT_BUFFER@1@@Z`
- size: `527`
- prototype: `__int64 __fastcall(VmMigrationTcpTransport *__hidden this, struct VmMigrationTcpTransport::_TRANSPORT_BUFFER *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1401e07b0`

## callees

- `0x140027a6c`
- `0x14005b648`
- `0x14006af58`
- `0x14009d7cc`
- `0x140132960`
- `0x1401e0a30`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1401e0a6e`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1401e0a6e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1401e0a84`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1401e0a84`
- `WS2_32!WSASend` at `0x1401e0aed`
- `WS2_32!WSASend` at `0x1401e0aed`
- `WS2_32!WSAGetOverlappedResult` at `0x1401e0bb6`
- `WS2_32!WSAGetOverlappedResult` at `0x1401e0bb6`
- `WS2_32!__imp_WSAGetLastError` at `0x1401e0b02`
- `WS2_32!__imp_WSAGetLastError` at `0x1401e0bc6`
- `WS2_32!__imp_WSAGetLastError` at `0x1401e0b02`
- `WS2_32!__imp_WSAGetLastError` at `0x1401e0bc6`
- `api-ms-win-core-io-l1-1-0!CancelIoEx` at `0x1401e0b89`
- `api-ms-win-core-io-l1-1-0!CancelIoEx` at `0x1401e0b89`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x1401e0b4f`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x1401e0b4f`

## string_xrefs

- `0x1401e0aaf`: `onecore\vm\common\migration\vmmigrationtcptransport.cpp`
- `0x1401e0b6c`: `onecore\vm\common\migration\vmmigrationtcptransport.cpp`
- `0x1401e0bdd`: `onecore\vm\common\migration\vmmigrationtcptransport.cpp`
- `0x1401e0bf9`: `onecore\vm\common\migration\vmmigrationtcptransport.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall VmMigrationTcpTransport::SendSynchronously(HANDLE *this, struct _WSABUF *a2)
{
  signed int LastError; // eax
  unsigned int Error; // eax
  DWORD v6; // eax
  const char *v7; // r9
  unsigned int v8; // eax
  const char *v9; // r9
  __int64 result; // rax
  int dwFlags; // [rsp+20h] [rbp-78h]
  unsigned int dwFlagsa; // [rsp+20h] [rbp-78h]
  unsigned int dwFlagsb; // [rsp+20h] [rbp-78h]
  HANDLE EventW; // [rsp+40h] [rbp-58h] BYREF
  struct _OVERLAPPED Overlapped; // [rsp+48h] [rbp-50h] BYREF
  DWORD cbTransfer; // [rsp+68h] [rbp-30h] BYREF
  DWORD v17; // [rsp+6Ch] [rbp-2Ch] BYREF
  HANDLE Handles[2]; // [rsp+70h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]

  memset(&Overlapped, 0, 24);
  EventW = CreateEventW(0, 1, 0, 0);
  Overlapped.hEvent = EventW;
  LastError = GetLastError();
  if ( LastError > 0 )
    LastError = (unsigned __int16)LastError | 0x80070000;
  try
  {
    if ( !Overlapped.hEvent )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x204,
        (unsigned int)"onecore\\vm\\common\\migration\\vmmigrationtcptransport.cpp",
        (const char *)(unsigned int)LastError,
        dwFlags);
    if ( WSASend((SOCKET)this[65], a2 + 6, 1u, 0, 0, &Overlapped, 0) == -1 )
    {
      Error = WSAGetLastError();
      if ( Error != 997 )
        wil::details::in1diag3::Throw_Win32(
          retaddr,
          (void *)0x23D,
          (unsigned int)"onecore\\vm\\common\\migration\\vmmigrationtcptransport.cpp",
          (const char *)Error,
          dwFlagsa);
      cbTransfer = 0;
      v17 = 0;
      Handles[0] = this[91];
      Handles[1] = Overlapped.hEvent;
      v6 = WaitForMultipleObjects(2u, Handles, 0, 0xFFFFFFFF);
      if ( v6 )
      {
        if ( v6 != 1 )
          wil::details::in1diag3::Throw_GetLastError(
            retaddr,
            (void *)0x22A,
            (unsigned int)"onecore\\vm\\common\\migration\\vmmigrationtcptransport.cpp",
            v7);
      }
      else
      {
        CancelIoEx(this[65], &Overlapped);
      }
      if ( !WSAGetOverlappedResult((SOCKET)this[65], &Overlapped, &cbTransfer, 1, &v17) )
      {
        v8 = WSAGetLastError();
        wil::details::in1diag3::Throw_Win32(
          retaddr,
          (void *)0x236,
          (unsigned int)"onecore\\vm\\common\\migration\\vmmigrationtcptransport.cpp",
          (const char *)v8,
          dwFlagsb);
      }
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&EventW);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x244,
                           (unsigned int)"onecore\\vm\\common\\migration\\vmmigrationtcptransport.cpp",
                           v9);
  }
  return result;
}

```

## disassembly

```asm
0x1401e0a30  mov     [rsp+arg_10], rbx
0x1401e0a35  push    rdi
0x1401e0a36  sub     rsp, 90h
0x1401e0a3d  mov     rax, cs:__security_cookie
0x1401e0a44  xor     rax, rsp
0x1401e0a47  mov     [rsp+98h+var_18], rax
0x1401e0a4f  mov     rdi, rdx
0x1401e0a52  mov     rbx, rcx
0x1401e0a55  xorps   xmm0, xmm0
0x1401e0a58  movups  xmmword ptr [rsp+98h+Overlapped.Internal], xmm0
0x1401e0a5d  movups  xmmword ptr [rsp+98h+Overlapped.10h], xmm0
0x1401e0a62  xor     r9d, r9d; lpName
0x1401e0a65  xor     r8d, r8d; bInitialState
0x1401e0a68  lea     edx, [r9+1]; bManualReset
0x1401e0a6c  xor     ecx, ecx; lpEventAttributes
0x1401e0a6e  call    cs:__imp_CreateEventW
0x1401e0a75  nop     dword ptr [rax+rax+00h]
0x1401e0a7a  mov     [rsp+98h+var_58], rax
0x1401e0a7f  mov     [rsp+98h+Overlapped.hEvent], rax
0x1401e0a84  call    cs:__imp_GetLastError
0x1401e0a8b  nop     dword ptr [rax+rax+00h]
0x1401e0a90  test    eax, eax
0x1401e0a92  jle     short loc_1401E0A9C
0x1401e0a94  movzx   eax, ax
0x1401e0a97  or      eax, 80070000h
0x1401e0a9c  mov     rcx, [rsp+98h]; this
0x1401e0aa4  cmp     [rsp+98h+Overlapped.hEvent], 0
0x1401e0aaa  jnz     short loc_1401E0AC0
0x1401e0aac  mov     r9d, eax; char *
0x1401e0aaf  lea     r8, aOnecoreVmCommo_44; "onecore\\vm\\common\\migration\\vmmigra"...
0x1401e0ab6  mov     edx, 204h; void *
0x1401e0abb  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1401e0ac0  lea     rdx, [rdi+60h]; lpBuffers
0x1401e0ac4  mov     [rsp+98h+lpCompletionRoutine], 0; lpCompletionRoutine
0x1401e0acd  lea     rax, [rsp+98h+Overlapped]
0x1401e0ad2  mov     [rsp+98h+lpOverlapped], rax; lpOverlapped
0x1401e0ad7  mov     [rsp+98h+dwFlags], 0; unsigned int
0x1401e0adf  xor     r9d, r9d; lpNumberOfBytesSent
0x1401e0ae2  lea     r8d, [r9+1]; dwBufferCount
0x1401e0ae6  mov     rcx, [rbx+208h]; s
0x1401e0aed  call    cs:__imp_WSASend
0x1401e0af4  nop     dword ptr [rax+rax+00h]
0x1401e0af9  cmp     eax, 0FFFFFFFFh
0x1401e0afc  jnz     loc_1401E0C0B
0x1401e0b02  call    cs:__imp_WSAGetLastError
0x1401e0b09  nop     dword ptr [rax+rax+00h]
0x1401e0b0e  cmp     eax, 3E5h
0x1401e0b13  jnz     loc_1401E0BEE
0x1401e0b19  mov     [rsp+98h+cbTransfer], 0
0x1401e0b21  mov     [rsp+98h+var_2C], 0
0x1401e0b29  mov     rax, [rbx+2D8h]
0x1401e0b30  mov     [rsp+98h+Handles], rax
0x1401e0b35  mov     rax, [rsp+98h+Overlapped.hEvent]
0x1401e0b3a  mov     [rsp+98h+var_20], rax
0x1401e0b3f  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x1401e0b43  xor     r8d, r8d; bWaitAll
0x1401e0b46  lea     rdx, [rsp+98h+Handles]; lpHandles
0x1401e0b4b  lea     ecx, [r8+2]; nCount
0x1401e0b4f  call    cs:__imp_WaitForMultipleObjects
0x1401e0b56  nop     dword ptr [rax+rax+00h]
0x1401e0b5b  test    eax, eax
0x1401e0b5d  jz      short loc_1401E0B7D
0x1401e0b5f  cmp     eax, 1
0x1401e0b62  jz      short loc_1401E0B95
0x1401e0b64  mov     rcx, [rsp+98h]; this
0x1401e0b6c  lea     r8, aOnecoreVmCommo_44; "onecore\\vm\\common\\migration\\vmmigra"...
0x1401e0b73  mov     edx, 22Ah; void *
0x1401e0b78  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1401e0b7d  lea     rdx, [rsp+98h+Overlapped]; lpOverlapped
0x1401e0b82  mov     rcx, [rbx+208h]; hFile
0x1401e0b89  call    cs:__imp_CancelIoEx
0x1401e0b90  nop     dword ptr [rax+rax+00h]
0x1401e0b95  lea     rax, [rsp+98h+var_2C]
0x1401e0b9a  mov     qword ptr [rsp+98h+dwFlags], rax; unsigned int
0x1401e0b9f  mov     r9d, 1; fWait
0x1401e0ba5  lea     r8, [rsp+98h+cbTransfer]; lpcbTransfer
0x1401e0baa  lea     rdx, [rsp+98h+Overlapped]; lpOverlapped
0x1401e0baf  mov     rcx, [rbx+208h]; s
0x1401e0bb6  call    cs:__imp_WSAGetOverlappedResult
0x1401e0bbd  nop     dword ptr [rax+rax+00h]
0x1401e0bc2  test    eax, eax
0x1401e0bc4  jnz     short loc_1401E0C0B
0x1401e0bc6  call    cs:__imp_WSAGetLastError
0x1401e0bcd  nop     dword ptr [rax+rax+00h]
0x1401e0bd2  mov     r9d, eax; char *
0x1401e0bd5  mov     rcx, [rsp+98h]; this
0x1401e0bdd  lea     r8, aOnecoreVmCommo_44; "onecore\\vm\\common\\migration\\vmmigra"...
0x1401e0be4  mov     edx, 236h; void *
0x1401e0be9  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1401e0bee  mov     rcx, [rsp+98h]; this
0x1401e0bf6  mov     r9d, eax; char *
0x1401e0bf9  lea     r8, aOnecoreVmCommo_44; "onecore\\vm\\common\\migration\\vmmigra"...
0x1401e0c00  mov     edx, 23Dh; void *
0x1401e0c05  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1401e0c0b  lea     rcx, [rsp+98h+var_58]
0x1401e0c10  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1401e0c15  xor     eax, eax
0x1401e0c17  jmp     short loc_1401E0C1D
0x1401e0c19  mov     eax, [rsp+98h+cbTransfer]
0x1401e0c1d  mov     rcx, [rsp+98h+var_18]
0x1401e0c25  xor     rcx, rsp; StackCookie
0x1401e0c28  call    __security_check_cookie
0x1401e0c2d  mov     rbx, [rsp+98h+arg_10]
0x1401e0c35  add     rsp, 90h
0x1401e0c3c  pop     rdi
0x1401e0c3d  retn
```
