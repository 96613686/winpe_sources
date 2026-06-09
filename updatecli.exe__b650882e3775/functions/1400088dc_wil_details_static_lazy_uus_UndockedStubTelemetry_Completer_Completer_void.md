# wil::details::static_lazy<uus::UndockedStubTelemetry>::Completer::~Completer(void)

- ea: `0x1400088dc`
- end: `0x1400089af`
- name: `??1Completer@?$static_lazy@VUndockedStubTelemetry@uus@@@details@wil@@QEAA@XZ`
- size: `211`
- prototype: `BOOL __fastcall(_DWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1400098ec`

## callees

- `0x140002130`
- `0x1400088dc`
- `0x14000c010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x14000896a`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x14000896a`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x140008952`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x140008952`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x140008992`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x140008992`

## pseudocode

```c
BOOL __fastcall wil::details::static_lazy<uus::UndockedStubTelemetry>::Completer::~Completer(_DWORD *a1)
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
0x1400088dc  push    rbx
0x1400088de  push    rsi
0x1400088df  push    rdi
0x1400088e0  push    r14
0x1400088e2  sub     rsp, 48h
0x1400088e6  mov     rax, cs:__security_cookie
0x1400088ed  xor     rax, rsp
0x1400088f0  mov     [rsp+68h+var_38], rax
0x1400088f5  cmp     dword ptr [rcx+8], 0
0x1400088f9  mov     rdi, rcx
0x1400088fc  jnz     loc_140008988
0x140008902  mov     rbx, [rcx]
0x140008905  mov     rsi, [rbx+20h]
0x140008909  mov     [rbx+10h], rsi
0x14000890d  mov     byte ptr [rbx+18h], 1
0x140008911  mov     rax, [rsi+8]
0x140008915  lea     r14, [rsi+20h]
0x140008919  cmp     qword ptr [r14], 0
0x14000891d  movups  xmm0, xmmword ptr [rax-10h]
0x140008921  movdqu  xmmword ptr [rsp+68h+ProviderId.Data1], xmm0
0x140008927  jz      short loc_140008930
0x140008929  mov     ecx, 5
0x14000892e  int     29h; Win8: RtlFailFast(ecx)
0x140008930  mov     r9, r14; RegHandle
0x140008933  mov     qword ptr [rsi+28h], 0
0x14000893b  mov     r8, rsi; CallbackContext
0x14000893e  mov     qword ptr [rsi+30h], 0
0x140008946  lea     rdx, _tlgEnableCallback; EnableCallback
0x14000894d  lea     rcx, [rsp+68h+ProviderId]; ProviderId
0x140008952  call    cs:__imp_EventRegister
0x140008958  test    eax, eax
0x14000895a  jnz     short loc_140008970
0x14000895c  mov     r8, [rsi+8]
0x140008960  lea     edx, [rax+2]
0x140008963  mov     rcx, [r14]
0x140008966  movzx   r9d, word ptr [r8]
0x14000896a  call    cs:__imp_EventSetInformation
0x140008970  mov     rax, [rbx+8]
0x140008974  lea     rcx, [rbx+8]
0x140008978  mov     dword ptr [rbx+1Ch], 1
0x14000897f  mov     rax, [rax+8]
0x140008983  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008988  mov     rcx, [rdi]; lpInitOnce
0x14000898b  mov     edx, [rdi+8]; dwFlags
0x14000898e  lea     r8, [rcx+8]; lpContext
0x140008992  call    cs:__imp_InitOnceComplete
0x140008998  mov     rcx, [rsp+68h+var_38]
0x14000899d  xor     rcx, rsp; StackCookie
0x1400089a0  call    __security_check_cookie
0x1400089a5  add     rsp, 48h
0x1400089a9  pop     r14
0x1400089ab  pop     rdi
0x1400089ac  pop     rsi
0x1400089ad  pop     rbx
0x1400089ae  retn
```
