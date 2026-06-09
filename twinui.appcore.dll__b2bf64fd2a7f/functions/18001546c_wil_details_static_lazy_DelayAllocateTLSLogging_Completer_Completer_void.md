# wil::details::static_lazy<DelayAllocateTLSLogging>::Completer::~Completer(void)

- ea: `0x18001546c`
- end: `0x18001553f`
- name: `??1Completer@?$static_lazy@VDelayAllocateTLSLogging@@@details@wil@@QEAA@XZ`
- size: `211`
- prototype: ``
- caller_count: `5`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180012090`
- `0x1800244ac`
- `0x1800255e0`
- `0x18005fbfc`
- `0x18007f758`

## callees

- `0x18001546c`
- `0x18002b1b0`
- `0x180085010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180015522`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180015522`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x1800154fa`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x1800154fa`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x1800154e2`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x1800154e2`

## pseudocode

```c
BOOL __fastcall wil::details::static_lazy<DelayAllocateTLSLogging>::Completer::~Completer(_DWORD *a1)
{
  __int64 v2; // rbx
  ULONGLONG *v3; // rsi
  bool v4; // zf
  __int64 v5; // rax
  GUID ProviderId; // [rsp+20h] [rbp-48h] BYREF

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
      EventSetInformation(v3[4], 2, v3[1], *(unsigned __int16 *)v3[1]);
    v5 = *(_QWORD *)(v2 + 8);
    *(_DWORD *)(v2 + 28) = 1;
    (*(void (__fastcall **)(__int64))(v5 + 8))(v2 + 8);
  }
  return InitOnceComplete(*(LPINIT_ONCE *)a1, a1[2], (LPVOID)(*(_QWORD *)a1 + 8LL));
}

```

## disassembly

```asm
0x18001546c  push    rbx
0x18001546e  push    rsi
0x18001546f  push    rdi
0x180015470  push    r14
0x180015472  sub     rsp, 48h
0x180015476  mov     rax, cs:__security_cookie
0x18001547d  xor     rax, rsp
0x180015480  mov     [rsp+68h+var_38], rax
0x180015485  cmp     dword ptr [rcx+8], 0
0x180015489  mov     rdi, rcx
0x18001548c  jnz     loc_180015518
0x180015492  mov     rbx, [rcx]
0x180015495  mov     rsi, [rbx+20h]
0x180015499  mov     [rbx+10h], rsi
0x18001549d  mov     byte ptr [rbx+18h], 1
0x1800154a1  mov     rax, [rsi+8]
0x1800154a5  lea     r14, [rsi+20h]
0x1800154a9  cmp     qword ptr [r14], 0
0x1800154ad  movups  xmm0, xmmword ptr [rax-10h]
0x1800154b1  movdqu  xmmword ptr [rsp+68h+ProviderId.Data1], xmm0
0x1800154b7  jz      short loc_1800154C0
0x1800154b9  mov     ecx, 5
0x1800154be  int     29h; Win8: RtlFailFast(ecx)
0x1800154c0  mov     r9, r14; RegHandle
0x1800154c3  mov     qword ptr [rsi+28h], 0
0x1800154cb  mov     r8, rsi; CallbackContext
0x1800154ce  mov     qword ptr [rsi+30h], 0
0x1800154d6  lea     rdx, _tlgEnableCallback; EnableCallback
0x1800154dd  lea     rcx, [rsp+68h+ProviderId]; ProviderId
0x1800154e2  call    cs:__imp_EventRegister
0x1800154e8  test    eax, eax
0x1800154ea  jnz     short loc_180015500
0x1800154ec  mov     r8, [rsi+8]
0x1800154f0  lea     edx, [rax+2]
0x1800154f3  mov     rcx, [r14]
0x1800154f6  movzx   r9d, word ptr [r8]
0x1800154fa  call    cs:__imp_EventSetInformation
0x180015500  mov     rax, [rbx+8]
0x180015504  lea     rcx, [rbx+8]
0x180015508  mov     dword ptr [rbx+1Ch], 1
0x18001550f  mov     rax, [rax+8]
0x180015513  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015518  mov     rcx, [rdi]; lpInitOnce
0x18001551b  mov     edx, [rdi+8]; dwFlags
0x18001551e  lea     r8, [rcx+8]; lpContext
0x180015522  call    cs:__imp_InitOnceComplete
0x180015528  mov     rcx, [rsp+68h+var_38]
0x18001552d  xor     rcx, rsp; StackCookie
0x180015530  call    __security_check_cookie
0x180015535  add     rsp, 48h
0x180015539  pop     r14
0x18001553b  pop     rdi
0x18001553c  pop     rsi
0x18001553d  pop     rbx
0x18001553e  retn
```
