# wil::details::static_lazy<Diagnostics::Telemetry4Diag>::Completer::~Completer(void)

- ea: `0x180007b80`
- end: `0x180007c6a`
- name: `??1Completer@?$static_lazy@VTelemetry4Diag@Diagnostics@@@details@wil@@QEAA@XZ`
- size: `234`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800080f8`

## callees

- `0x180007b80`
- `0x18008fe00`
- `0x180096170`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x180007c19`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x180007c19`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x180007c01`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x180007c01`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180007c41`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180007c41`

## pseudocode

```c
BOOL __fastcall wil::details::static_lazy<Diagnostics::Telemetry4Diag>::Completer::~Completer(_DWORD *a1)
{
  __int64 v2; // rdi
  ULONGLONG *v3; // rsi
  bool v4; // zf
  __int64 v5; // rax
  GUID ProviderId; // [rsp+20h] [rbp-28h] BYREF

  if ( !a1[2] )
  {
    v2 = *(_QWORD *)a1;
    v3 = *(ULONGLONG **)(*(_QWORD *)a1 + 32LL);
    *(_QWORD *)(v2 + 16) = v3;
    *(_BYTE *)(v2 + 24) = 1;
    v4 = v3[4] == 0;
    ProviderId = *(GUID *)(v3[1] - 16);
    if ( !v4 )
      __fastfail(5u);
    v3[5] = 0;
    v3[6] = 0;
    if ( !EventRegister(&ProviderId, tlgEnableCallback, v3, v3 + 4) )
      EventSetInformation(
        v3[4],
        2,
        v3[1],
        *(unsigned __int16 *)v3[1],
        *(_QWORD *)&ProviderId.Data1,
        *(_QWORD *)ProviderId.Data4);
    v5 = *(_QWORD *)(v2 + 8);
    *(_DWORD *)(v2 + 28) = 1;
    (*(void (__fastcall **)(__int64))(v5 + 8))(v2 + 8);
  }
  return InitOnceComplete(*(LPINIT_ONCE *)a1, a1[2], (LPVOID)(*(_QWORD *)a1 + 8LL));
}

```

## disassembly

```asm
0x180007b80  mov     [rsp+arg_8], rbx
0x180007b85  mov     [rsp+arg_10], rsi
0x180007b8a  mov     [rsp+arg_18], rdi
0x180007b8f  push    r14
0x180007b91  sub     rsp, 40h
0x180007b95  mov     rax, cs:__security_cookie
0x180007b9c  xor     rax, rsp
0x180007b9f  mov     [rsp+48h+var_18], rax
0x180007ba4  cmp     dword ptr [rcx+8], 0
0x180007ba8  mov     rbx, rcx
0x180007bab  jnz     loc_180007C37
0x180007bb1  mov     rdi, [rcx]
0x180007bb4  mov     rsi, [rdi+20h]
0x180007bb8  mov     [rdi+10h], rsi
0x180007bbc  mov     byte ptr [rdi+18h], 1
0x180007bc0  mov     rax, [rsi+8]
0x180007bc4  lea     r14, [rsi+20h]
0x180007bc8  cmp     qword ptr [r14], 0
0x180007bcc  movups  xmm0, xmmword ptr [rax-10h]
0x180007bd0  movdqu  xmmword ptr [rsp+48h+ProviderId.Data1], xmm0
0x180007bd6  jz      short loc_180007BDF
0x180007bd8  mov     ecx, 5
0x180007bdd  int     29h; Win8: RtlFailFast(ecx)
0x180007bdf  mov     r9, r14; RegHandle
0x180007be2  mov     qword ptr [rsi+28h], 0
0x180007bea  mov     r8, rsi; CallbackContext
0x180007bed  mov     qword ptr [rsi+30h], 0
0x180007bf5  lea     rdx, _tlgEnableCallback; EnableCallback
0x180007bfc  lea     rcx, [rsp+48h+ProviderId]; ProviderId
0x180007c01  call    cs:__imp_EventRegister
0x180007c07  test    eax, eax
0x180007c09  jnz     short loc_180007C1F
0x180007c0b  mov     r8, [rsi+8]
0x180007c0f  lea     edx, [rax+2]
0x180007c12  mov     rcx, [r14]
0x180007c15  movzx   r9d, word ptr [r8]
0x180007c19  call    cs:__imp_EventSetInformation
0x180007c1f  mov     rax, [rdi+8]
0x180007c23  lea     rcx, [rdi+8]
0x180007c27  mov     dword ptr [rdi+1Ch], 1
0x180007c2e  mov     rax, [rax+8]
0x180007c32  call    _guard_dispatch_icall
0x180007c37  mov     rcx, [rbx]; lpInitOnce
0x180007c3a  mov     edx, [rbx+8]; dwFlags
0x180007c3d  lea     r8, [rcx+8]; lpContext
0x180007c41  call    cs:__imp_InitOnceComplete
0x180007c47  mov     rcx, [rsp+48h+var_18]
0x180007c4c  xor     rcx, rsp; StackCookie
0x180007c4f  call    __security_check_cookie
0x180007c54  mov     rbx, [rsp+48h+arg_8]
0x180007c59  mov     rsi, [rsp+48h+arg_10]
0x180007c5e  mov     rdi, [rsp+48h+arg_18]
0x180007c63  add     rsp, 40h
0x180007c67  pop     r14
0x180007c69  retn
```
