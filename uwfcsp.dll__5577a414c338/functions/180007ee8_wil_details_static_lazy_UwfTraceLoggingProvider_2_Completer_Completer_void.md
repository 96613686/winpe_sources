# wil::details::static_lazy<UwfTraceLoggingProvider<2>>::Completer::~Completer(void)

- ea: `0x180007ee8`
- end: `0x180007fbb`
- name: `??1Completer@?$static_lazy@V?$UwfTraceLoggingProvider@$01@@@details@wil@@QEAA@XZ`
- size: `211`
- prototype: `BOOL __fastcall(_DWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180009f60`

## callees

- `0x180007ee8`
- `0x18001a210`
- `0x18001b010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x180007f5e`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x180007f5e`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x180007f76`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x180007f76`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180007f9e`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180007f9e`

## pseudocode

```c
BOOL __fastcall wil::details::static_lazy<UwfTraceLoggingProvider<2>>::Completer::~Completer(_DWORD *a1)
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
0x180007ee8  push    rbx
0x180007eea  push    rsi
0x180007eeb  push    rdi
0x180007eec  push    r14
0x180007eee  sub     rsp, 48h
0x180007ef2  mov     rax, cs:__security_cookie
0x180007ef9  xor     rax, rsp
0x180007efc  mov     [rsp+68h+var_38], rax
0x180007f01  cmp     dword ptr [rcx+8], 0
0x180007f05  mov     rdi, rcx
0x180007f08  jnz     loc_180007F94
0x180007f0e  mov     rbx, [rcx]
0x180007f11  mov     rsi, [rbx+20h]
0x180007f15  mov     [rbx+10h], rsi
0x180007f19  mov     byte ptr [rbx+18h], 1
0x180007f1d  mov     rax, [rsi+8]
0x180007f21  lea     r14, [rsi+20h]
0x180007f25  cmp     qword ptr [r14], 0
0x180007f29  movups  xmm0, xmmword ptr [rax-10h]
0x180007f2d  movdqu  xmmword ptr [rsp+68h+ProviderId.Data1], xmm0
0x180007f33  jz      short loc_180007F3C
0x180007f35  mov     ecx, 5
0x180007f3a  int     29h; Win8: RtlFailFast(ecx)
0x180007f3c  mov     r9, r14; RegHandle
0x180007f3f  mov     qword ptr [rsi+28h], 0
0x180007f47  mov     r8, rsi; CallbackContext
0x180007f4a  mov     qword ptr [rsi+30h], 0
0x180007f52  lea     rdx, _tlgEnableCallback; EnableCallback
0x180007f59  lea     rcx, [rsp+68h+ProviderId]; ProviderId
0x180007f5e  call    cs:__imp_EventRegister
0x180007f64  test    eax, eax
0x180007f66  jnz     short loc_180007F7C
0x180007f68  mov     r8, [rsi+8]
0x180007f6c  lea     edx, [rax+2]
0x180007f6f  mov     rcx, [r14]
0x180007f72  movzx   r9d, word ptr [r8]
0x180007f76  call    cs:__imp_EventSetInformation
0x180007f7c  mov     rax, [rbx+8]
0x180007f80  lea     rcx, [rbx+8]
0x180007f84  mov     dword ptr [rbx+1Ch], 1
0x180007f8b  mov     rax, [rax+8]
0x180007f8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007f94  mov     rcx, [rdi]; lpInitOnce
0x180007f97  mov     edx, [rdi+8]; dwFlags
0x180007f9a  lea     r8, [rcx+8]; lpContext
0x180007f9e  call    cs:__imp_InitOnceComplete
0x180007fa4  mov     rcx, [rsp+68h+var_38]
0x180007fa9  xor     rcx, rsp; StackCookie
0x180007fac  call    __security_check_cookie
0x180007fb1  add     rsp, 48h
0x180007fb5  pop     r14
0x180007fb7  pop     rdi
0x180007fb8  pop     rsi
0x180007fb9  pop     rbx
0x180007fba  retn
```
