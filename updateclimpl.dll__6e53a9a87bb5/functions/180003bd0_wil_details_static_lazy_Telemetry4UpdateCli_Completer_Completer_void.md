# wil::details::static_lazy<Telemetry4UpdateCli>::Completer::~Completer(void)

- ea: `0x180003bd0`
- end: `0x180003cba`
- name: `??1Completer@?$static_lazy@VTelemetry4UpdateCli@@@details@wil@@QEAA@XZ`
- size: `234`
- prototype: `BOOL __fastcall(_DWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180004158`

## callees

- `0x180003bd0`
- `0x180010310`
- `0x1800148e0`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x180003c69`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x180003c69`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x180003c51`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x180003c51`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180003c91`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180003c91`

## pseudocode

```c
BOOL __fastcall wil::details::static_lazy<Telemetry4UpdateCli>::Completer::~Completer(_DWORD *a1)
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
0x180003bd0  mov     [rsp+arg_8], rbx
0x180003bd5  mov     [rsp+arg_10], rsi
0x180003bda  mov     [rsp+arg_18], rdi
0x180003bdf  push    r14
0x180003be1  sub     rsp, 40h
0x180003be5  mov     rax, cs:__security_cookie
0x180003bec  xor     rax, rsp
0x180003bef  mov     [rsp+48h+var_18], rax
0x180003bf4  cmp     dword ptr [rcx+8], 0
0x180003bf8  mov     rbx, rcx
0x180003bfb  jnz     loc_180003C87
0x180003c01  mov     rdi, [rcx]
0x180003c04  mov     rsi, [rdi+20h]
0x180003c08  mov     [rdi+10h], rsi
0x180003c0c  mov     byte ptr [rdi+18h], 1
0x180003c10  mov     rax, [rsi+8]
0x180003c14  lea     r14, [rsi+20h]
0x180003c18  cmp     qword ptr [r14], 0
0x180003c1c  movups  xmm0, xmmword ptr [rax-10h]
0x180003c20  movdqu  xmmword ptr [rsp+48h+ProviderId.Data1], xmm0
0x180003c26  jz      short loc_180003C2F
0x180003c28  mov     ecx, 5
0x180003c2d  int     29h; Win8: RtlFailFast(ecx)
0x180003c2f  mov     r9, r14; RegHandle
0x180003c32  mov     qword ptr [rsi+28h], 0
0x180003c3a  mov     r8, rsi; CallbackContext
0x180003c3d  mov     qword ptr [rsi+30h], 0
0x180003c45  lea     rdx, _tlgEnableCallback; EnableCallback
0x180003c4c  lea     rcx, [rsp+48h+ProviderId]; ProviderId
0x180003c51  call    cs:__imp_EventRegister
0x180003c57  test    eax, eax
0x180003c59  jnz     short loc_180003C6F
0x180003c5b  mov     r8, [rsi+8]
0x180003c5f  lea     edx, [rax+2]
0x180003c62  mov     rcx, [r14]
0x180003c65  movzx   r9d, word ptr [r8]
0x180003c69  call    cs:__imp_EventSetInformation
0x180003c6f  mov     rax, [rdi+8]
0x180003c73  lea     rcx, [rdi+8]
0x180003c77  mov     dword ptr [rdi+1Ch], 1
0x180003c7e  mov     rax, [rax+8]
0x180003c82  call    _guard_dispatch_icall
0x180003c87  mov     rcx, [rbx]; lpInitOnce
0x180003c8a  mov     edx, [rbx+8]; dwFlags
0x180003c8d  lea     r8, [rcx+8]; lpContext
0x180003c91  call    cs:__imp_InitOnceComplete
0x180003c97  mov     rcx, [rsp+48h+var_18]
0x180003c9c  xor     rcx, rsp; StackCookie
0x180003c9f  call    __security_check_cookie
0x180003ca4  mov     rbx, [rsp+48h+arg_8]
0x180003ca9  mov     rsi, [rsp+48h+arg_10]
0x180003cae  mov     rdi, [rsp+48h+arg_18]
0x180003cb3  add     rsp, 40h
0x180003cb7  pop     r14
0x180003cb9  retn
```
