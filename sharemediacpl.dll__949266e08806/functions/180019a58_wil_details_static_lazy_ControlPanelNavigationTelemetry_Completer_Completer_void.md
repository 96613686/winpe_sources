# wil::details::static_lazy<ControlPanelNavigationTelemetry>::Completer::~Completer(void)

- ea: `0x180019a58`
- end: `0x180019b2b`
- name: `??1Completer@?$static_lazy@VControlPanelNavigationTelemetry@@@details@wil@@QEAA@XZ`
- size: `211`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180019824`

## callees

- `0x180001d60`
- `0x180019a58`
- `0x18001e010`

## import_xrefs

- `KERNEL32!InitOnceComplete` at `0x180019b0e`
- `KERNEL32!InitOnceComplete` at `0x180019b0e`
- `ntdll!EtwEventSetInformation` at `0x180019ae6`
- `ntdll!EtwEventSetInformation` at `0x180019ae6`
- `ntdll!EtwEventRegister` at `0x180019ace`
- `ntdll!EtwEventRegister` at `0x180019ace`

## pseudocode

```c
BOOL __fastcall wil::details::static_lazy<ControlPanelNavigationTelemetry>::Completer::~Completer(_DWORD *a1)
{
  __int64 v2; // rbx
  _QWORD *v3; // rsi
  bool v4; // zf
  __int64 v5; // rax
  __int128 v7; // [rsp+20h] [rbp-48h] BYREF

  if ( !a1[2] )
  {
    v2 = *(_QWORD *)a1;
    v3 = *(_QWORD **)(*(_QWORD *)a1 + 32LL);
    *(_QWORD *)(v2 + 16) = v3;
    *(_BYTE *)(v2 + 24) = 1;
    v4 = v3[4] == 0;
    v7 = *(_OWORD *)(v3[1] - 16LL);
    if ( !v4 )
      __fastfail(5u);
    v3[5] = 0;
    v3[6] = 0;
    if ( !(unsigned int)((__int64 (__fastcall *)(__int128 *, __int64 (__fastcall *)(int, int, int, int, __int64, __int64, __int64), _QWORD *, _QWORD *))EtwEventRegister)(
                          &v7,
                          tlgEnableCallback,
                          v3,
                          v3 + 4) )
      EtwEventSetInformation(v3[4], 2, v3[1], *(unsigned __int16 *)v3[1], v7, *((_QWORD *)&v7 + 1));
    v5 = *(_QWORD *)(v2 + 8);
    *(_DWORD *)(v2 + 28) = 1;
    (*(void (__fastcall **)(__int64))(v5 + 8))(v2 + 8);
  }
  return InitOnceComplete(*(LPINIT_ONCE *)a1, a1[2], (LPVOID)(*(_QWORD *)a1 + 8LL));
}

```

## disassembly

```asm
0x180019a58  push    rbx
0x180019a5a  push    rsi
0x180019a5b  push    rdi
0x180019a5c  push    r14
0x180019a5e  sub     rsp, 48h
0x180019a62  mov     rax, cs:__security_cookie
0x180019a69  xor     rax, rsp
0x180019a6c  mov     [rsp+68h+var_38], rax
0x180019a71  cmp     dword ptr [rcx+8], 0
0x180019a75  mov     rdi, rcx
0x180019a78  jnz     loc_180019B04
0x180019a7e  mov     rbx, [rcx]
0x180019a81  mov     rsi, [rbx+20h]
0x180019a85  mov     [rbx+10h], rsi
0x180019a89  mov     byte ptr [rbx+18h], 1
0x180019a8d  mov     rax, [rsi+8]
0x180019a91  lea     r14, [rsi+20h]
0x180019a95  cmp     qword ptr [r14], 0
0x180019a99  movups  xmm0, xmmword ptr [rax-10h]
0x180019a9d  movdqu  [rsp+68h+var_48], xmm0
0x180019aa3  jz      short loc_180019AAC
0x180019aa5  mov     ecx, 5
0x180019aaa  int     29h; Win8: RtlFailFast(ecx)
0x180019aac  mov     r9, r14
0x180019aaf  mov     qword ptr [rsi+28h], 0
0x180019ab7  mov     r8, rsi
0x180019aba  mov     qword ptr [rsi+30h], 0
0x180019ac2  lea     rdx, _tlgEnableCallback
0x180019ac9  lea     rcx, [rsp+68h+var_48]
0x180019ace  call    cs:__imp_EtwEventRegister
0x180019ad4  test    eax, eax
0x180019ad6  jnz     short loc_180019AEC
0x180019ad8  mov     r8, [rsi+8]
0x180019adc  lea     edx, [rax+2]
0x180019adf  mov     rcx, [r14]
0x180019ae2  movzx   r9d, word ptr [r8]
0x180019ae6  call    cs:__imp_EtwEventSetInformation
0x180019aec  mov     rax, [rbx+8]
0x180019af0  lea     rcx, [rbx+8]
0x180019af4  mov     dword ptr [rbx+1Ch], 1
0x180019afb  mov     rax, [rax+8]
0x180019aff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019b04  mov     rcx, [rdi]; lpInitOnce
0x180019b07  mov     edx, [rdi+8]; dwFlags
0x180019b0a  lea     r8, [rcx+8]; lpContext
0x180019b0e  call    cs:__imp_InitOnceComplete
0x180019b14  mov     rcx, [rsp+68h+var_38]
0x180019b19  xor     rcx, rsp; StackCookie
0x180019b1c  call    __security_check_cookie
0x180019b21  add     rsp, 48h
0x180019b25  pop     r14
0x180019b27  pop     rdi
0x180019b28  pop     rsi
0x180019b29  pop     rbx
0x180019b2a  retn
```
