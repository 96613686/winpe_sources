# wil::details::static_lazy<SearchIndexerTraceProvider>::Completer::~Completer(void)

- ea: `0x1800046d8`
- end: `0x1800047ab`
- name: `??1Completer@?$static_lazy@USearchIndexerTraceProvider@@@details@wil@@QEAA@XZ`
- size: `211`
- prototype: `BOOL __fastcall(_DWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180008d9c`

## callees

- `0x1800020e0`
- `0x1800046d8`
- `0x180017010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x18000474e`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x18000474e`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x180004766`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x180004766`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000478e`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000478e`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
BOOL __fastcall wil::details::static_lazy<SearchIndexerTraceProvider>::Completer::~Completer(_DWORD *a1)
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
0x1800046d8  push    rbx
0x1800046da  push    rsi
0x1800046db  push    rdi
0x1800046dc  push    r14
0x1800046de  sub     rsp, 48h
0x1800046e2  mov     rax, cs:__security_cookie
0x1800046e9  xor     rax, rsp
0x1800046ec  mov     [rsp+68h+var_38], rax
0x1800046f1  cmp     dword ptr [rcx+8], 0
0x1800046f5  mov     rdi, rcx
0x1800046f8  jnz     loc_180004784
0x1800046fe  mov     rbx, [rcx]
0x180004701  mov     rsi, [rbx+20h]
0x180004705  mov     [rbx+10h], rsi
0x180004709  mov     byte ptr [rbx+18h], 1
0x18000470d  mov     rax, [rsi+8]
0x180004711  lea     r14, [rsi+20h]
0x180004715  cmp     qword ptr [r14], 0
0x180004719  movups  xmm0, xmmword ptr [rax-10h]
0x18000471d  movdqu  xmmword ptr [rsp+68h+ProviderId.Data1], xmm0
0x180004723  jz      short loc_18000472C
0x180004725  mov     ecx, 5
0x18000472a  int     29h; Win8: RtlFailFast(ecx)
0x18000472c  mov     r9, r14; RegHandle
0x18000472f  mov     qword ptr [rsi+28h], 0
0x180004737  mov     r8, rsi; CallbackContext
0x18000473a  mov     qword ptr [rsi+30h], 0
0x180004742  lea     rdx, _tlgEnableCallback; EnableCallback
0x180004749  lea     rcx, [rsp+68h+ProviderId]; ProviderId
0x18000474e  call    cs:__imp_EventRegister
0x180004754  test    eax, eax
0x180004756  jnz     short loc_18000476C
0x180004758  mov     r8, [rsi+8]
0x18000475c  lea     edx, [rax+2]
0x18000475f  mov     rcx, [r14]
0x180004762  movzx   r9d, word ptr [r8]
0x180004766  call    cs:__imp_EventSetInformation
0x18000476c  mov     rax, [rbx+8]
0x180004770  lea     rcx, [rbx+8]
0x180004774  mov     dword ptr [rbx+1Ch], 1
0x18000477b  mov     rax, [rax+8]
0x18000477f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004784  mov     rcx, [rdi]; lpInitOnce
0x180004787  mov     edx, [rdi+8]; dwFlags
0x18000478a  lea     r8, [rcx+8]; lpContext
0x18000478e  call    cs:__imp_InitOnceComplete
0x180004794  mov     rcx, [rsp+68h+var_38]
0x180004799  xor     rcx, rsp; StackCookie
0x18000479c  call    __security_check_cookie
0x1800047a1  add     rsp, 48h
0x1800047a5  pop     r14
0x1800047a7  pop     rdi
0x1800047a8  pop     rsi
0x1800047a9  pop     rbx
0x1800047aa  retn
```
