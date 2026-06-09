# wil::details::static_lazy<wil::details::FeatureLogging>::Completer::~Completer(void)

- ea: `0x180019c14`
- end: `0x180019ce7`
- name: `??1Completer@?$static_lazy@VFeatureLogging@details@wil@@@details@wil@@QEAA@XZ`
- size: `211`
- prototype: `BOOL __fastcall(_DWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18001ae7c`

## callees

- `0x180019c14`
- `0x18001d370`
- `0x18001e010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180019cca`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180019cca`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x180019c8a`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x180019c8a`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x180019ca2`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x180019ca2`

## pseudocode

```c
BOOL __fastcall wil::details::static_lazy<wil::details::FeatureLogging>::Completer::~Completer(_DWORD *a1)
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
0x180019c14  push    rbx
0x180019c16  push    rsi
0x180019c17  push    rdi
0x180019c18  push    r14
0x180019c1a  sub     rsp, 48h
0x180019c1e  mov     rax, cs:__security_cookie
0x180019c25  xor     rax, rsp
0x180019c28  mov     [rsp+68h+var_38], rax
0x180019c2d  cmp     dword ptr [rcx+8], 0
0x180019c31  mov     rdi, rcx
0x180019c34  jnz     loc_180019CC0
0x180019c3a  mov     rbx, [rcx]
0x180019c3d  mov     rsi, [rbx+20h]
0x180019c41  mov     [rbx+10h], rsi
0x180019c45  mov     byte ptr [rbx+18h], 1
0x180019c49  mov     rax, [rsi+8]
0x180019c4d  lea     r14, [rsi+20h]
0x180019c51  cmp     qword ptr [r14], 0
0x180019c55  movups  xmm0, xmmword ptr [rax-10h]
0x180019c59  movdqu  xmmword ptr [rsp+68h+ProviderId.Data1], xmm0
0x180019c5f  jz      short loc_180019C68
0x180019c61  mov     ecx, 5
0x180019c66  int     29h; Win8: RtlFailFast(ecx)
0x180019c68  mov     r9, r14; RegHandle
0x180019c6b  mov     qword ptr [rsi+28h], 0
0x180019c73  mov     r8, rsi; CallbackContext
0x180019c76  mov     qword ptr [rsi+30h], 0
0x180019c7e  lea     rdx, _tlgEnableCallback; EnableCallback
0x180019c85  lea     rcx, [rsp+68h+ProviderId]; ProviderId
0x180019c8a  call    cs:__imp_EventRegister
0x180019c90  test    eax, eax
0x180019c92  jnz     short loc_180019CA8
0x180019c94  mov     r8, [rsi+8]
0x180019c98  lea     edx, [rax+2]
0x180019c9b  mov     rcx, [r14]
0x180019c9e  movzx   r9d, word ptr [r8]
0x180019ca2  call    cs:__imp_EventSetInformation
0x180019ca8  mov     rax, [rbx+8]
0x180019cac  lea     rcx, [rbx+8]
0x180019cb0  mov     dword ptr [rbx+1Ch], 1
0x180019cb7  mov     rax, [rax+8]
0x180019cbb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019cc0  mov     rcx, [rdi]; lpInitOnce
0x180019cc3  mov     edx, [rdi+8]; dwFlags
0x180019cc6  lea     r8, [rcx+8]; lpContext
0x180019cca  call    cs:__imp_InitOnceComplete
0x180019cd0  mov     rcx, [rsp+68h+var_38]
0x180019cd5  xor     rcx, rsp; StackCookie
0x180019cd8  call    __security_check_cookie
0x180019cdd  add     rsp, 48h
0x180019ce1  pop     r14
0x180019ce3  pop     rdi
0x180019ce4  pop     rsi
0x180019ce5  pop     rbx
0x180019ce6  retn
```
