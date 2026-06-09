# MpQuerySessionIdFromObjects

- ea: `0x140068d64`
- end: `0x140068e96`
- name: `MpQuerySessionIdFromObjects`
- size: `306`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140055520`
- `0x140055eb0`

## callees

- `0x1400051bc`
- `0x1400118d0`
- `0x1400384b4`
- `0x140068d64`
- `0x140068e98`

## import_xrefs

- `ntoskrnl!PsDereferenceImpersonationToken` at `0x140068dee`
- `ntoskrnl!PsDereferenceImpersonationToken` at `0x140068dee`
- `ntoskrnl!PsReferenceImpersonationToken` at `0x140068dca`
- `ntoskrnl!PsReferenceImpersonationToken` at `0x140068dca`
- `ntoskrnl!PsGetCurrentProcessId` at `0x140068e5a`
- `ntoskrnl!PsGetCurrentProcessId` at `0x140068e5a`

## pseudocode

```c
__int64 __fastcall MpQuerySessionIdFromObjects(struct _KTHREAD *a1, struct _KPROCESS *a2, __int64 a3, _DWORD *a4)
{
  PACCESS_TOKEN v7; // rax
  void *v8; // rsi
  int SessionIdToken; // ebx
  HANDLE CurrentProcessId; // rax
  unsigned __int8 v12; // [rsp+30h] [rbp-28h] BYREF
  unsigned __int8 v13[3]; // [rsp+31h] [rbp-27h] BYREF
  int v14; // [rsp+34h] [rbp-24h] BYREF

  if ( !a1 || !a2 || !a4 )
    return 3221225485LL;
  *a4 = 0;
  v13[0] = 0;
  v12 = 0;
  v14 = 0;
  v7 = PsReferenceImpersonationToken(a1, v13, &v12, (PSECURITY_IMPERSONATION_LEVEL)&v14);
  v8 = v7;
  if ( !v7 )
  {
    if ( !a3 )
    {
      CurrentProcessId = PsGetCurrentProcessId();
      return MpQuerySessionIdFromProcess(a2, CurrentProcessId, a4);
    }
    *a4 = *(_DWORD *)(a3 + 256);
    return 0;
  }
  SessionIdToken = MpQuerySessionIdToken(v7, a4);
  PsDereferenceImpersonationToken(v8);
  if ( SessionIdToken >= 0 )
    return 0;
  _mm_lfence();
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
    WPP_SF_qD(
      WPP_GLOBAL_Control->AttachedDevice,
      15,
      WPP_81cd47ed6b7c3e33e522c0360ded0121_Traceguids,
      KeGetCurrentThread(),
      SessionIdToken);
  return (unsigned int)SessionIdToken;
}

```

## disassembly

```asm
0x140068d64  mov     r11, rsp
0x140068d67  mov     [r11+18h], rbx
0x140068d6b  push    rbp
0x140068d6c  push    rsi
0x140068d6d  push    rdi
0x140068d6e  sub     rsp, 40h
0x140068d72  mov     rax, cs:__security_cookie
0x140068d79  xor     rax, rsp
0x140068d7c  mov     [rsp+58h+var_20], rax
0x140068d81  mov     rbx, r9
0x140068d84  mov     rdi, r8
0x140068d87  mov     rbp, rdx
0x140068d8a  test    rcx, rcx
0x140068d8d  jz      loc_140068E76
0x140068d93  test    rdx, rdx
0x140068d96  jz      loc_140068E76
0x140068d9c  test    rbx, rbx
0x140068d9f  jz      loc_140068E76
0x140068da5  mov     dword ptr [r9], 0
0x140068dac  lea     r8, [r11-28h]; EffectiveOnly
0x140068db0  lea     r9, [r11-24h]; ImpersonationLevel
0x140068db4  mov     [rsp+58h+var_27], 0
0x140068db9  lea     rdx, [r11-27h]; CopyOnOpen
0x140068dbd  mov     [rsp+58h+var_28], 0
0x140068dc2  mov     [rsp+58h+var_24], 0
0x140068dca  call    cs:__imp_PsReferenceImpersonationToken
0x140068dd1  nop     dword ptr [rax+rax+00h]
0x140068dd6  mov     rsi, rax
0x140068dd9  test    rax, rax
0x140068ddc  jz      short loc_140068E49
0x140068dde  mov     rdx, rbx
0x140068de1  mov     rcx, rax
0x140068de4  call    MpQuerySessionIdToken
0x140068de9  mov     rcx, rsi; ImpersonationToken
0x140068dec  mov     ebx, eax
0x140068dee  call    cs:__imp_PsDereferenceImpersonationToken
0x140068df5  nop     dword ptr [rax+rax+00h]
0x140068dfa  test    ebx, ebx
0x140068dfc  jns     short loc_140068E56
0x140068dfe  lfence
0x140068e01  mov     rcx, cs:WPP_GLOBAL_Control
0x140068e08  lea     rax, WPP_GLOBAL_Control
0x140068e0f  cmp     rcx, rax
0x140068e12  jz      short loc_140068E45
0x140068e14  mov     ecx, [rcx+2Ch]
0x140068e17  test    cl, 1
0x140068e1a  jz      short loc_140068E45
0x140068e1c  mov     r9, gs:188h
0x140068e25  lea     r8, WPP_81cd47ed6b7c3e33e522c0360ded0121_Traceguids
0x140068e2c  mov     rcx, cs:WPP_GLOBAL_Control
0x140068e33  mov     edx, 0Fh
0x140068e38  mov     [rsp+58h+var_38], ebx
0x140068e3c  mov     rcx, [rcx+18h]
0x140068e40  call    WPP_SF_qD
0x140068e45  mov     eax, ebx
0x140068e47  jmp     short loc_140068E7B
0x140068e49  test    rdi, rdi
0x140068e4c  jz      short loc_140068E5A
0x140068e4e  mov     eax, [rdi+100h]
0x140068e54  mov     [rbx], eax
0x140068e56  xor     eax, eax
0x140068e58  jmp     short loc_140068E7B
0x140068e5a  call    cs:__imp_PsGetCurrentProcessId
0x140068e61  nop     dword ptr [rax+rax+00h]
0x140068e66  mov     r8, rbx
0x140068e69  mov     rcx, rbp
0x140068e6c  mov     rdx, rax
0x140068e6f  call    MpQuerySessionIdFromProcess
0x140068e74  jmp     short loc_140068E7B
0x140068e76  mov     eax, 0C000000Dh
0x140068e7b  mov     rcx, [rsp+58h+var_20]
0x140068e80  xor     rcx, rsp; StackCookie
0x140068e83  call    __security_check_cookie
0x140068e88  mov     rbx, [rsp+58h+arg_10]
0x140068e8d  add     rsp, 40h
0x140068e91  pop     rdi
0x140068e92  pop     rsi
0x140068e93  pop     rbp
0x140068e94  retn
```
