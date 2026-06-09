# WapTpIoCompletionRoutine

- ea: `0x1800509e0`
- end: `0x180050c23`
- name: `WapTpIoCompletionRoutine`
- size: `579`
- prototype: `void __stdcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PVOID Overlapped, ULONG IoResult, ULONG_PTR NumberOfBytesTransferred, PTP_IO Io)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1800180e0`
- `0x18001f9e8`
- `0x18002e460`
- `0x1800509e0`
- `0x1800722f0`
- `0x180098010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180050b00`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180050b00`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180050a4a`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180050a68`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180050ad7`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180050a4a`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180050a68`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180050ad7`
- `api-ms-win-core-threadpool-l1-2-0!CallbackMayRunLong` at `0x180050a1a`
- `api-ms-win-core-threadpool-l1-2-0!CallbackMayRunLong` at `0x180050a1a`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180050b25`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180050b25`

## pseudocode

```c
void __fastcall WapTpIoCompletionRoutine(
        PTP_CALLBACK_INSTANCE Instance,
        void (__fastcall *Context)(_QWORD, _QWORD, GUID *),
        char *Overlapped,
        ULONG IoResult,
        ULONG_PTR NumberOfBytesTransferred)
{
  GUID *v8; // rbx
  __int64 v9; // rdx
  __int64 v10; // rcx
  __int64 v11; // r8
  void *v12; // rdx
  __int64 v13; // r8
  __int64 v14; // rcx
  __int64 v15; // rcx
  unsigned int v16; // eax
  unsigned int LastError; // eax
  GUID *v18; // [rsp+40h] [rbp-49h] BYREF
  int v19; // [rsp+48h] [rbp-41h] BYREF
  GUID v20; // [rsp+50h] [rbp-39h]
  GUID ActivityId; // [rsp+60h] [rbp-29h] BYREF
  int v22; // [rsp+70h] [rbp-19h]
  struct _EVENT_DATA_DESCRIPTOR v23; // [rsp+78h] [rbp-11h] BYREF
  GUID **v24; // [rsp+88h] [rbp-1h]
  __int64 v25; // [rsp+90h] [rbp+7h]
  int *v26; // [rsp+98h] [rbp+Fh]
  __int64 v27; // [rsp+A0h] [rbp+17h]

  v20 = 0;
  CallbackMayRunLong(Instance);
  v8 = (GUID *)(Overlapped - 8);
  ActivityId = 0;
  v22 = 0;
  v20 = v8[3];
  if ( !EventActivityIdControl(1u, &ActivityId) )
  {
    if ( !(_BYTE)v22 )
      LOBYTE(v22) = EventActivityIdControl(2u, v8 + 3) == 0;
    if ( Microsoft_Windows_Networking_CorrelationEnabled )
      EtwEx_tidActivityInfoTransfer(v10, v9, &v8[3], &ActivityId);
  }
  if ( !(_BYTE)v22 )
    ActivityId = 0;
  if ( (Microsoft_Windows_WebIOEnableBits & 0x20000) != 0 )
  {
    v19 = 3;
    v24 = &v18;
    v18 = v8;
    v26 = &v19;
    v25 = 8;
    v27 = 4;
    McGenEventWrite_EventWriteTransfer(
      &WEB_ETW_PROVIDER_ID_Context,
      (const EVENT_DESCRIPTOR *)ThreadAction,
      v11,
      3u,
      &v23);
  }
  v12 = *(void **)v8[2].Data4;
  if ( v12 )
  {
    if ( !SetThreadToken(0, v12) )
    {
      LastError = WaGetLastError(v14);
      if ( LastError )
        __fastfail(LastError);
    }
    Context(IoResult, (unsigned int)NumberOfBytesTransferred, v8);
    if ( !RevertToSelf() )
    {
      v16 = WaGetLastError(v15);
      if ( v16 )
        __fastfail(v16);
    }
  }
  else
  {
    Context(IoResult, (unsigned int)NumberOfBytesTransferred, v8);
  }
  if ( (Microsoft_Windows_WebIOEnableBits & 0x20000) != 0 )
  {
    v19 = 3;
    v24 = &v18;
    v18 = v8;
    v26 = &v19;
    v25 = 8;
    v27 = 4;
    McGenEventWrite_EventWriteTransfer(
      &WEB_ETW_PROVIDER_ID_Context,
      (const EVENT_DESCRIPTOR *)ThreadActionComplete,
      v13,
      3u,
      &v23);
  }
  if ( (_BYTE)v22 )
    EventActivityIdControl(2u, &ActivityId);
}

```

## disassembly

```asm
0x1800509e0  push    rbp
0x1800509e2  push    rbx
0x1800509e3  push    rsi
0x1800509e4  push    rdi
0x1800509e5  push    r14
0x1800509e7  lea     rbp, [rsp-27h]
0x1800509ec  sub     rsp, 0B0h
0x1800509f3  mov     rax, cs:__security_cookie
0x1800509fa  xor     rax, rsp
0x1800509fd  mov     [rbp+47h+var_28], rax
0x180050a01  xorps   xmm0, xmm0
0x180050a04  xor     eax, eax
0x180050a06  movups  [rbp+47h+var_80], xmm0
0x180050a0a  mov     [rbp+47h+var_60], eax
0x180050a0d  mov     r14d, r9d
0x180050a10  movups  xmmword ptr [rbp+47h+ActivityId.Data1], xmm0
0x180050a14  mov     rbx, r8
0x180050a17  mov     rsi, rdx
0x180050a1a  call    cs:__imp_CallbackMayRunLong
0x180050a21  nop     dword ptr [rax+rax+00h]
0x180050a26  xorps   xmm0, xmm0
0x180050a29  lea     rdx, [rbp+47h+ActivityId]; ActivityId
0x180050a2d  xor     eax, eax
0x180050a2f  add     rbx, 0FFFFFFFFFFFFFFF8h
0x180050a33  movups  xmmword ptr [rbp+47h+ActivityId.Data1], xmm0
0x180050a37  mov     [rbp+47h+var_60], eax
0x180050a3a  mov     ecx, 1; ControlCode
0x180050a3f  mov     byte ptr [rbp+47h+var_60], al
0x180050a42  movups  xmm0, xmmword ptr [rbx+30h]
0x180050a46  movups  [rbp+47h+var_80], xmm0
0x180050a4a  call    cs:__imp_EventActivityIdControl
0x180050a51  nop     dword ptr [rax+rax+00h]
0x180050a56  test    eax, eax
0x180050a58  jnz     short loc_180050A8A
0x180050a5a  cmp     byte ptr [rbp+47h+var_60], al
0x180050a5d  jnz     short loc_180050A7C
0x180050a5f  lea     rdx, [rbx+30h]; ActivityId
0x180050a63  mov     ecx, 2; ControlCode
0x180050a68  call    cs:__imp_EventActivityIdControl
0x180050a6f  nop     dword ptr [rax+rax+00h]
0x180050a74  test    eax, eax
0x180050a76  jnz     short loc_180050A7C
0x180050a78  mov     byte ptr [rbp+47h+var_60], 1
0x180050a7c  mov     eax, cs:Microsoft_Windows_Networking_CorrelationEnabled
0x180050a82  test    eax, eax
0x180050a84  jnz     loc_180050BFB
0x180050a8a  cmp     byte ptr [rbp+47h+var_60], 0
0x180050a8e  jz      loc_180050B9D
0x180050a94  test    byte ptr cs:Microsoft_Windows_WebIOEnableBits+2, 2
0x180050a9b  jnz     loc_180050B4B
0x180050aa1  mov     rdx, [rbx+28h]; Token
0x180050aa5  test    rdx, rdx
0x180050aa8  jnz     short loc_180050AFE
0x180050aaa  mov     edx, dword ptr [rbp+47h+NumberOfBytesTransferred]
0x180050aad  mov     r8, rbx
0x180050ab0  mov     ecx, r14d
0x180050ab3  mov     rax, rsi
0x180050ab6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050abb  test    byte ptr cs:Microsoft_Windows_WebIOEnableBits+2, 2
0x180050ac2  jnz     loc_180050BA9
0x180050ac8  cmp     byte ptr [rbp+47h+var_60], 0
0x180050acc  jz      short loc_180050AE3
0x180050ace  lea     rdx, [rbp+47h+ActivityId]; ActivityId
0x180050ad2  mov     ecx, 2; ControlCode
0x180050ad7  call    cs:__imp_EventActivityIdControl
0x180050ade  nop     dword ptr [rax+rax+00h]
0x180050ae3  mov     rcx, [rbp+47h+var_28]
0x180050ae7  xor     rcx, rsp; StackCookie
0x180050aea  call    __security_check_cookie
0x180050aef  add     rsp, 0B0h
0x180050af6  pop     r14
0x180050af8  pop     rdi
0x180050af9  pop     rsi
0x180050afa  pop     rbx
0x180050afb  pop     rbp
0x180050afc  retn
0x180050afe  xor     ecx, ecx; Thread
0x180050b00  call    cs:__imp_SetThreadToken
0x180050b07  nop     dword ptr [rax+rax+00h]
0x180050b0c  test    eax, eax
0x180050b0e  jz      loc_180050C0D
0x180050b14  mov     edx, dword ptr [rbp+47h+NumberOfBytesTransferred]
0x180050b17  mov     r8, rbx
0x180050b1a  mov     ecx, r14d
0x180050b1d  mov     rax, rsi
0x180050b20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050b25  call    cs:__imp_RevertToSelf
0x180050b2c  nop     dword ptr [rax+rax+00h]
0x180050b31  test    eax, eax
0x180050b33  jnz     short loc_180050ABB
0x180050b35  call    WaGetLastError
0x180050b3a  test    eax, eax
0x180050b3c  jz      loc_180050ABB
0x180050b42  mov     ecx, eax
0x180050b44  int     29h; Win8: RtlFailFast(ecx)
0x180050b46  jmp     loc_180050ABB
0x180050b4b  lea     rax, [rbp+47h+var_90]
0x180050b4f  mov     [rbp+47h+var_88], 3
0x180050b56  mov     [rbp+47h+var_48], rax
0x180050b5a  lea     rdx, ThreadAction
0x180050b61  lea     rax, [rbp+47h+var_88]
0x180050b65  mov     [rbp+47h+var_90], rbx
0x180050b69  mov     [rbp+47h+var_38], rax
0x180050b6d  lea     rcx, WEB_ETW_PROVIDER_ID_Context
0x180050b74  lea     rax, [rbp+47h+var_58]
0x180050b78  mov     [rbp+47h+var_40], 8
0x180050b80  mov     r9d, 3
0x180050b86  mov     [rsp+0D0h+var_B0], rax
0x180050b8b  mov     [rbp+47h+var_30], 4
0x180050b93  call    McGenEventWrite_EventWriteTransfer
0x180050b98  jmp     loc_180050AA1
0x180050b9d  xorps   xmm0, xmm0
0x180050ba0  movups  xmmword ptr [rbp+47h+ActivityId.Data1], xmm0
0x180050ba4  jmp     loc_180050A94
0x180050ba9  lea     rax, [rbp+47h+var_90]
0x180050bad  mov     [rbp+47h+var_88], 3
0x180050bb4  mov     [rbp+47h+var_48], rax
0x180050bb8  lea     rdx, ThreadActionComplete
0x180050bbf  lea     rax, [rbp+47h+var_88]
0x180050bc3  mov     [rbp+47h+var_90], rbx
0x180050bc7  mov     [rbp+47h+var_38], rax
0x180050bcb  lea     rcx, WEB_ETW_PROVIDER_ID_Context
0x180050bd2  lea     rax, [rbp+47h+var_58]
0x180050bd6  mov     [rbp+47h+var_40], 8
0x180050bde  mov     r9d, 3
0x180050be4  mov     [rsp+0D0h+var_B0], rax
0x180050be9  mov     [rbp+47h+var_30], 4
0x180050bf1  call    McGenEventWrite_EventWriteTransfer
0x180050bf6  jmp     loc_180050AC8
0x180050bfb  lea     r9, [rbp+47h+ActivityId]
0x180050bff  lea     r8, [rbx+30h]
0x180050c03  call    EtwEx_tidActivityInfoTransfer
0x180050c08  jmp     loc_180050A8A
0x180050c0d  call    WaGetLastError
0x180050c12  test    eax, eax
0x180050c14  jz      loc_180050B14
0x180050c1a  mov     ecx, eax
0x180050c1c  int     29h; Win8: RtlFailFast(ecx)
0x180050c1e  jmp     loc_180050B14
```
