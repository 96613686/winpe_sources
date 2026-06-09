# wil::details::static_lazy<wil::details::FeatureLogging>::Completer::~Completer(void)

- ea: `0x18000ad78`
- end: `0x18000ae4b`
- name: `??1Completer@?$static_lazy@VFeatureLogging@details@wil@@@details@wil@@QEAA@XZ`
- size: `211`
- prototype: `BOOL __fastcall(_DWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000c1d8`

## callees

- `0x1800026d0`
- `0x18000ad78`
- `0x18000f010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x18000adee`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x18000adee`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x18000ae06`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x18000ae06`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000ae2e`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000ae2e`

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
0x18000ad78  push    rbx
0x18000ad7a  push    rsi
0x18000ad7b  push    rdi
0x18000ad7c  push    r14
0x18000ad7e  sub     rsp, 48h
0x18000ad82  mov     rax, cs:__security_cookie
0x18000ad89  xor     rax, rsp
0x18000ad8c  mov     [rsp+68h+var_38], rax
0x18000ad91  cmp     dword ptr [rcx+8], 0
0x18000ad95  mov     rdi, rcx
0x18000ad98  jnz     loc_18000AE24
0x18000ad9e  mov     rbx, [rcx]
0x18000ada1  mov     rsi, [rbx+20h]
0x18000ada5  mov     [rbx+10h], rsi
0x18000ada9  mov     byte ptr [rbx+18h], 1
0x18000adad  mov     rax, [rsi+8]
0x18000adb1  lea     r14, [rsi+20h]
0x18000adb5  cmp     qword ptr [r14], 0
0x18000adb9  movups  xmm0, xmmword ptr [rax-10h]
0x18000adbd  movdqu  xmmword ptr [rsp+68h+ProviderId.Data1], xmm0
0x18000adc3  jz      short loc_18000ADCC
0x18000adc5  mov     ecx, 5
0x18000adca  int     29h; Win8: RtlFailFast(ecx)
0x18000adcc  mov     r9, r14; RegHandle
0x18000adcf  mov     qword ptr [rsi+28h], 0
0x18000add7  mov     r8, rsi; CallbackContext
0x18000adda  mov     qword ptr [rsi+30h], 0
0x18000ade2  lea     rdx, _tlgEnableCallback; EnableCallback
0x18000ade9  lea     rcx, [rsp+68h+ProviderId]; ProviderId
0x18000adee  call    cs:__imp_EventRegister
0x18000adf4  test    eax, eax
0x18000adf6  jnz     short loc_18000AE0C
0x18000adf8  mov     r8, [rsi+8]
0x18000adfc  lea     edx, [rax+2]
0x18000adff  mov     rcx, [r14]
0x18000ae02  movzx   r9d, word ptr [r8]
0x18000ae06  call    cs:__imp_EventSetInformation
0x18000ae0c  mov     rax, [rbx+8]
0x18000ae10  lea     rcx, [rbx+8]
0x18000ae14  mov     dword ptr [rbx+1Ch], 1
0x18000ae1b  mov     rax, [rax+8]
0x18000ae1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ae24  mov     rcx, [rdi]; lpInitOnce
0x18000ae27  mov     edx, [rdi+8]; dwFlags
0x18000ae2a  lea     r8, [rcx+8]; lpContext
0x18000ae2e  call    cs:__imp_InitOnceComplete
0x18000ae34  mov     rcx, [rsp+68h+var_38]
0x18000ae39  xor     rcx, rsp; StackCookie
0x18000ae3c  call    __security_check_cookie
0x18000ae41  add     rsp, 48h
0x18000ae45  pop     r14
0x18000ae47  pop     rdi
0x18000ae48  pop     rsi
0x18000ae49  pop     rbx
0x18000ae4a  retn
```
