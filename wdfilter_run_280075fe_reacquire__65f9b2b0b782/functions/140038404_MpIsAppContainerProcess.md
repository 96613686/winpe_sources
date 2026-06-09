# MpIsAppContainerProcess

- ea: `0x140038404`
- end: `0x1400384b4`
- name: `MpIsAppContainerProcess`
- size: `176`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1400387f0`

## callees

- `0x1400118d0`
- `0x140038404`

## import_xrefs

- `ntoskrnl!PsDereferencePrimaryToken` at `0x14003849d`
- `ntoskrnl!PsDereferencePrimaryToken` at `0x14003849d`
- `ntoskrnl!SeQueryInformationToken` at `0x14003847e`
- `ntoskrnl!SeQueryInformationToken` at `0x14003847e`
- `ntoskrnl!PsReferencePrimaryToken` at `0x14003843a`
- `ntoskrnl!PsReferencePrimaryToken` at `0x14003843a`

## pseudocode

```c
__int64 __fastcall MpIsAppContainerProcess(struct _KPROCESS *a1, bool *a2)
{
  PACCESS_TOKEN v3; // rax
  void *v4; // rdi
  NTSTATUS v6; // esi
  PVOID TokenInformation; // [rsp+20h] [rbp-18h] BYREF

  LODWORD(TokenInformation) = 0;
  if ( !a1 || !a2 )
    return 3221225485LL;
  *a2 = 0;
  v3 = PsReferencePrimaryToken(a1);
  v4 = v3;
  if ( !v3 )
    return 3221225473LL;
  v6 = SeQueryInformationToken(v3, TokenIsAppContainer, &TokenInformation);
  if ( v6 >= 0 )
    *a2 = (_DWORD)TokenInformation != 0;
  PsDereferencePrimaryToken(v4);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x140038404  mov     [rsp+arg_10], rbx
0x140038409  mov     [rsp+arg_18], rsi
0x14003840e  push    rdi
0x14003840f  sub     rsp, 30h
0x140038413  mov     rax, cs:__security_cookie
0x14003841a  xor     rax, rsp
0x14003841d  mov     [rsp+38h+var_10], rax
0x140038422  mov     dword ptr [rsp+38h+TokenInformation], 0
0x14003842a  mov     rbx, rdx
0x14003842d  test    rcx, rcx
0x140038430  jz      short loc_1400384AD
0x140038432  test    rdx, rdx
0x140038435  jz      short loc_1400384AD
0x140038437  mov     byte ptr [rdx], 0
0x14003843a  call    cs:__imp_PsReferencePrimaryToken
0x140038441  nop     dword ptr [rax+rax+00h]
0x140038446  mov     rdi, rax
0x140038449  test    rax, rax
0x14003844c  jnz     short loc_140038471
0x14003844e  mov     eax, 0C0000001h
0x140038453  mov     rcx, [rsp+38h+var_10]
0x140038458  xor     rcx, rsp; StackCookie
0x14003845b  call    __security_check_cookie
0x140038460  mov     rbx, [rsp+38h+arg_10]
0x140038465  mov     rsi, [rsp+38h+arg_18]
0x14003846a  add     rsp, 30h
0x14003846e  pop     rdi
0x14003846f  retn
0x140038471  lea     r8, [rsp+38h+TokenInformation]; TokenInformation
0x140038476  mov     edx, 1Dh; TokenInformationClass
0x14003847b  mov     rcx, rdi; Token
0x14003847e  call    cs:__imp_SeQueryInformationToken
0x140038485  nop     dword ptr [rax+rax+00h]
0x14003848a  mov     esi, eax
0x14003848c  test    eax, eax
0x14003848e  js      short loc_14003849A
0x140038490  cmp     dword ptr [rsp+38h+TokenInformation], 0
0x140038495  setnz   cl
0x140038498  mov     [rbx], cl
0x14003849a  mov     rcx, rdi; PrimaryToken
0x14003849d  call    cs:__imp_PsDereferencePrimaryToken
0x1400384a4  nop     dword ptr [rax+rax+00h]
0x1400384a9  mov     eax, esi
0x1400384ab  jmp     short loc_140038453
0x1400384ad  mov     eax, 0C000000Dh
0x1400384b2  jmp     short loc_140038453
```
