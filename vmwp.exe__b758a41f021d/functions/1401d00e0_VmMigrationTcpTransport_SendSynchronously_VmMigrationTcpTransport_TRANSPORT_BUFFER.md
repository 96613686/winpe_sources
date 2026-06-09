# VmMigrationTcpTransport::SendSynchronously(VmMigrationTcpTransport::_TRANSPORT_BUFFER *)

- ea: `0x1401d00e0`
- end: `0x1401d02ef`
- name: `?SendSynchronously@VmMigrationTcpTransport@@IEAAJPEAU_TRANSPORT_BUFFER@1@@Z`
- size: `527`
- prototype: `__int64 __fastcall(VmMigrationTcpTransport *__hidden this, struct VmMigrationTcpTransport::_TRANSPORT_BUFFER *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1401cfe60`

## callees

- `0x140027fdc`
- `0x140078628`
- `0x140083990`
- `0x1400ba144`
- `0x14011ea40`
- `0x1401d00e0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1401d011e`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1401d011e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1401d0134`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1401d0134`
- `WS2_32!WSASend` at `0x1401d019d`
- `WS2_32!WSASend` at `0x1401d019d`
- `WS2_32!WSAGetOverlappedResult` at `0x1401d0266`
- `WS2_32!WSAGetOverlappedResult` at `0x1401d0266`
- `WS2_32!__imp_WSAGetLastError` at `0x1401d01b2`
- `WS2_32!__imp_WSAGetLastError` at `0x1401d0276`
- `WS2_32!__imp_WSAGetLastError` at `0x1401d01b2`
- `WS2_32!__imp_WSAGetLastError` at `0x1401d0276`
- `api-ms-win-core-io-l1-1-0!CancelIoEx` at `0x1401d0239`
- `api-ms-win-core-io-l1-1-0!CancelIoEx` at `0x1401d0239`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x1401d01ff`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x1401d01ff`

## string_xrefs

- `0x1401d015f`: `onecore\vm\common\migration\vmmigrationtcptransport.cpp`
- `0x1401d021c`: `onecore\vm\common\migration\vmmigrationtcptransport.cpp`
- `0x1401d028d`: `onecore\vm\common\migration\vmmigrationtcptransport.cpp`
- `0x1401d02a9`: `onecore\vm\common\migration\vmmigrationtcptransport.cpp`

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
0x1401d00e0  mov     [rsp+arg_10], rbx
0x1401d00e5  push    rdi
0x1401d00e6  sub     rsp, 90h
0x1401d00ed  mov     rax, cs:__security_cookie
0x1401d00f4  xor     rax, rsp
0x1401d00f7  mov     [rsp+98h+var_18], rax
0x1401d00ff  mov     rdi, rdx
0x1401d0102  mov     rbx, rcx
0x1401d0105  xorps   xmm0, xmm0
0x1401d0108  movups  xmmword ptr [rsp+98h+Overlapped.Internal], xmm0
0x1401d010d  movups  xmmword ptr [rsp+98h+Overlapped.10h], xmm0
0x1401d0112  xor     r9d, r9d; lpName
0x1401d0115  xor     r8d, r8d; bInitialState
0x1401d0118  lea     edx, [r9+1]; bManualReset
0x1401d011c  xor     ecx, ecx; lpEventAttributes
0x1401d011e  call    cs:__imp_CreateEventW
0x1401d0125  nop     dword ptr [rax+rax+00h]
0x1401d012a  mov     [rsp+98h+var_58], rax
0x1401d012f  mov     [rsp+98h+Overlapped.hEvent], rax
0x1401d0134  call    cs:__imp_GetLastError
0x1401d013b  nop     dword ptr [rax+rax+00h]
0x1401d0140  test    eax, eax
0x1401d0142  jle     short loc_1401D014C
0x1401d0144  movzx   eax, ax
0x1401d0147  or      eax, 80070000h
0x1401d014c  mov     rcx, [rsp+98h]; this
0x1401d0154  cmp     [rsp+98h+Overlapped.hEvent], 0
0x1401d015a  jnz     short loc_1401D0170
0x1401d015c  mov     r9d, eax; char *
0x1401d015f  lea     r8, aOnecoreVmCommo_43; "onecore\\vm\\common\\migration\\vmmigra"...
0x1401d0166  mov     edx, 204h; void *
0x1401d016b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1401d0170  lea     rdx, [rdi+60h]; lpBuffers
0x1401d0174  mov     [rsp+98h+lpCompletionRoutine], 0; lpCompletionRoutine
0x1401d017d  lea     rax, [rsp+98h+Overlapped]
0x1401d0182  mov     [rsp+98h+lpOverlapped], rax; lpOverlapped
0x1401d0187  mov     [rsp+98h+dwFlags], 0; unsigned int
0x1401d018f  xor     r9d, r9d; lpNumberOfBytesSent
0x1401d0192  lea     r8d, [r9+1]; dwBufferCount
0x1401d0196  mov     rcx, [rbx+208h]; s
0x1401d019d  call    cs:__imp_WSASend
0x1401d01a4  nop     dword ptr [rax+rax+00h]
0x1401d01a9  cmp     eax, 0FFFFFFFFh
0x1401d01ac  jnz     loc_1401D02BB
0x1401d01b2  call    cs:__imp_WSAGetLastError
0x1401d01b9  nop     dword ptr [rax+rax+00h]
0x1401d01be  cmp     eax, 3E5h
0x1401d01c3  jnz     loc_1401D029E
0x1401d01c9  mov     [rsp+98h+cbTransfer], 0
0x1401d01d1  mov     [rsp+98h+var_2C], 0
0x1401d01d9  mov     rax, [rbx+2D8h]
0x1401d01e0  mov     [rsp+98h+Handles], rax
0x1401d01e5  mov     rax, [rsp+98h+Overlapped.hEvent]
0x1401d01ea  mov     [rsp+98h+var_20], rax
0x1401d01ef  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x1401d01f3  xor     r8d, r8d; bWaitAll
0x1401d01f6  lea     rdx, [rsp+98h+Handles]; lpHandles
0x1401d01fb  lea     ecx, [r8+2]; nCount
0x1401d01ff  call    cs:__imp_WaitForMultipleObjects
0x1401d0206  nop     dword ptr [rax+rax+00h]
0x1401d020b  test    eax, eax
0x1401d020d  jz      short loc_1401D022D
0x1401d020f  cmp     eax, 1
0x1401d0212  jz      short loc_1401D0245
0x1401d0214  mov     rcx, [rsp+98h]; this
0x1401d021c  lea     r8, aOnecoreVmCommo_43; "onecore\\vm\\common\\migration\\vmmigra"...
0x1401d0223  mov     edx, 22Ah; void *
0x1401d0228  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1401d022d  lea     rdx, [rsp+98h+Overlapped]; lpOverlapped
0x1401d0232  mov     rcx, [rbx+208h]; hFile
0x1401d0239  call    cs:__imp_CancelIoEx
0x1401d0240  nop     dword ptr [rax+rax+00h]
0x1401d0245  lea     rax, [rsp+98h+var_2C]
0x1401d024a  mov     qword ptr [rsp+98h+dwFlags], rax; unsigned int
0x1401d024f  mov     r9d, 1; fWait
0x1401d0255  lea     r8, [rsp+98h+cbTransfer]; lpcbTransfer
0x1401d025a  lea     rdx, [rsp+98h+Overlapped]; lpOverlapped
0x1401d025f  mov     rcx, [rbx+208h]; s
0x1401d0266  call    cs:__imp_WSAGetOverlappedResult
0x1401d026d  nop     dword ptr [rax+rax+00h]
0x1401d0272  test    eax, eax
0x1401d0274  jnz     short loc_1401D02BB
0x1401d0276  call    cs:__imp_WSAGetLastError
0x1401d027d  nop     dword ptr [rax+rax+00h]
0x1401d0282  mov     r9d, eax; char *
0x1401d0285  mov     rcx, [rsp+98h]; this
0x1401d028d  lea     r8, aOnecoreVmCommo_43; "onecore\\vm\\common\\migration\\vmmigra"...
0x1401d0294  mov     edx, 236h; void *
0x1401d0299  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1401d029e  mov     rcx, [rsp+98h]; this
0x1401d02a6  mov     r9d, eax; char *
0x1401d02a9  lea     r8, aOnecoreVmCommo_43; "onecore\\vm\\common\\migration\\vmmigra"...
0x1401d02b0  mov     edx, 23Dh; void *
0x1401d02b5  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1401d02bb  lea     rcx, [rsp+98h+var_58]
0x1401d02c0  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1401d02c5  xor     eax, eax
0x1401d02c7  jmp     short loc_1401D02CD
0x1401d02c9  mov     eax, [rsp+98h+cbTransfer]
0x1401d02cd  mov     rcx, [rsp+98h+var_18]
0x1401d02d5  xor     rcx, rsp; StackCookie
0x1401d02d8  call    __security_check_cookie
0x1401d02dd  mov     rbx, [rsp+98h+arg_10]
0x1401d02e5  add     rsp, 90h
0x1401d02ec  pop     rdi
0x1401d02ed  retn
```
