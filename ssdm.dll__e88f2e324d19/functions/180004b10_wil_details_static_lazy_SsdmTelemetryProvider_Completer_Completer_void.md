# wil::details::static_lazy<SsdmTelemetryProvider>::Completer::~Completer(void)

- ea: `0x180004b10`
- end: `0x180004be3`
- name: `??1Completer@?$static_lazy@VSsdmTelemetryProvider@@@details@wil@@QEAA@XZ`
- size: `211`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800063b4`

## callees

- `0x180004b10`
- `0x18000e990`
- `0x180010010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180004bc6`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180004bc6`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x180004b9e`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x180004b9e`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x180004b86`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x180004b86`

## pseudocode

```c
BOOL __fastcall wil::details::static_lazy<SsdmTelemetryProvider>::Completer::~Completer(_DWORD *a1)
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
0x180004b10  push    rbx
0x180004b12  push    rsi
0x180004b13  push    rdi
0x180004b14  push    r14
0x180004b16  sub     rsp, 48h
0x180004b1a  mov     rax, cs:__security_cookie
0x180004b21  xor     rax, rsp
0x180004b24  mov     [rsp+68h+var_38], rax
0x180004b29  cmp     dword ptr [rcx+8], 0
0x180004b2d  mov     rdi, rcx
0x180004b30  jnz     loc_180004BBC
0x180004b36  mov     rbx, [rcx]
0x180004b39  mov     rsi, [rbx+20h]
0x180004b3d  mov     [rbx+10h], rsi
0x180004b41  mov     byte ptr [rbx+18h], 1
0x180004b45  mov     rax, [rsi+8]
0x180004b49  lea     r14, [rsi+20h]
0x180004b4d  cmp     qword ptr [r14], 0
0x180004b51  movups  xmm0, xmmword ptr [rax-10h]
0x180004b55  movdqu  xmmword ptr [rsp+68h+ProviderId.Data1], xmm0
0x180004b5b  jz      short loc_180004B64
0x180004b5d  mov     ecx, 5
0x180004b62  int     29h; Win8: RtlFailFast(ecx)
0x180004b64  mov     r9, r14; RegHandle
0x180004b67  mov     qword ptr [rsi+28h], 0
0x180004b6f  mov     r8, rsi; CallbackContext
0x180004b72  mov     qword ptr [rsi+30h], 0
0x180004b7a  lea     rdx, _tlgEnableCallback; EnableCallback
0x180004b81  lea     rcx, [rsp+68h+ProviderId]; ProviderId
0x180004b86  call    cs:__imp_EventRegister
0x180004b8c  test    eax, eax
0x180004b8e  jnz     short loc_180004BA4
0x180004b90  mov     r8, [rsi+8]
0x180004b94  lea     edx, [rax+2]
0x180004b97  mov     rcx, [r14]
0x180004b9a  movzx   r9d, word ptr [r8]
0x180004b9e  call    cs:__imp_EventSetInformation
0x180004ba4  mov     rax, [rbx+8]
0x180004ba8  lea     rcx, [rbx+8]
0x180004bac  mov     dword ptr [rbx+1Ch], 1
0x180004bb3  mov     rax, [rax+8]
0x180004bb7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004bbc  mov     rcx, [rdi]; lpInitOnce
0x180004bbf  mov     edx, [rdi+8]; dwFlags
0x180004bc2  lea     r8, [rcx+8]; lpContext
0x180004bc6  call    cs:__imp_InitOnceComplete
0x180004bcc  mov     rcx, [rsp+68h+var_38]
0x180004bd1  xor     rcx, rsp; StackCookie
0x180004bd4  call    __security_check_cookie
0x180004bd9  add     rsp, 48h
0x180004bdd  pop     r14
0x180004bdf  pop     rdi
0x180004be0  pop     rsi
0x180004be1  pop     rbx
0x180004be2  retn
```
