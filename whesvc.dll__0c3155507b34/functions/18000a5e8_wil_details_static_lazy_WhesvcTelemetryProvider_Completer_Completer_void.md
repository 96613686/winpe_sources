# wil::details::static_lazy<WhesvcTelemetryProvider>::Completer::~Completer(void)

- ea: `0x18000a5e8`
- end: `0x18000a6bb`
- name: `??1Completer@?$static_lazy@VWhesvcTelemetryProvider@@@details@wil@@QEAA@XZ`
- size: `211`
- prototype: `BOOL __fastcall(_DWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000ae4c`

## callees

- `0x1800032e0`
- `0x18000a5e8`
- `0x180029010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000a69e`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000a69e`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x18000a65e`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x18000a65e`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x18000a676`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x18000a676`

## pseudocode

```c
BOOL __fastcall wil::details::static_lazy<WhesvcTelemetryProvider>::Completer::~Completer(_DWORD *a1)
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
0x18000a5e8  push    rbx
0x18000a5ea  push    rsi
0x18000a5eb  push    rdi
0x18000a5ec  push    r14
0x18000a5ee  sub     rsp, 48h
0x18000a5f2  mov     rax, cs:__security_cookie
0x18000a5f9  xor     rax, rsp
0x18000a5fc  mov     [rsp+68h+var_38], rax
0x18000a601  cmp     dword ptr [rcx+8], 0
0x18000a605  mov     rdi, rcx
0x18000a608  jnz     loc_18000A694
0x18000a60e  mov     rbx, [rcx]
0x18000a611  mov     rsi, [rbx+20h]
0x18000a615  mov     [rbx+10h], rsi
0x18000a619  mov     byte ptr [rbx+18h], 1
0x18000a61d  mov     rax, [rsi+8]
0x18000a621  lea     r14, [rsi+20h]
0x18000a625  cmp     qword ptr [r14], 0
0x18000a629  movups  xmm0, xmmword ptr [rax-10h]
0x18000a62d  movdqu  xmmword ptr [rsp+68h+ProviderId.Data1], xmm0
0x18000a633  jz      short loc_18000A63C
0x18000a635  mov     ecx, 5
0x18000a63a  int     29h; Win8: RtlFailFast(ecx)
0x18000a63c  mov     r9, r14; RegHandle
0x18000a63f  mov     qword ptr [rsi+28h], 0
0x18000a647  mov     r8, rsi; CallbackContext
0x18000a64a  mov     qword ptr [rsi+30h], 0
0x18000a652  lea     rdx, _tlgEnableCallback; EnableCallback
0x18000a659  lea     rcx, [rsp+68h+ProviderId]; ProviderId
0x18000a65e  call    cs:__imp_EventRegister
0x18000a664  test    eax, eax
0x18000a666  jnz     short loc_18000A67C
0x18000a668  mov     r8, [rsi+8]
0x18000a66c  lea     edx, [rax+2]
0x18000a66f  mov     rcx, [r14]
0x18000a672  movzx   r9d, word ptr [r8]
0x18000a676  call    cs:__imp_EventSetInformation
0x18000a67c  mov     rax, [rbx+8]
0x18000a680  lea     rcx, [rbx+8]
0x18000a684  mov     dword ptr [rbx+1Ch], 1
0x18000a68b  mov     rax, [rax+8]
0x18000a68f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a694  mov     rcx, [rdi]; lpInitOnce
0x18000a697  mov     edx, [rdi+8]; dwFlags
0x18000a69a  lea     r8, [rcx+8]; lpContext
0x18000a69e  call    cs:__imp_InitOnceComplete
0x18000a6a4  mov     rcx, [rsp+68h+var_38]
0x18000a6a9  xor     rcx, rsp; StackCookie
0x18000a6ac  call    __security_check_cookie
0x18000a6b1  add     rsp, 48h
0x18000a6b5  pop     r14
0x18000a6b7  pop     rdi
0x18000a6b8  pop     rsi
0x18000a6b9  pop     rbx
0x18000a6ba  retn
```
