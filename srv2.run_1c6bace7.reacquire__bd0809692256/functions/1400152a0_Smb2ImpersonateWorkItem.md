# Smb2ImpersonateWorkItem

- ea: `0x1400152a0`
- end: `0x14001531b`
- name: `Smb2ImpersonateWorkItem`
- size: `123`
- prototype: ``
- caller_count: `12`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140066300`
- `0x140066dc4`
- `0x1400773c8`
- `0x1400792e0`
- `0x140079c80`
- `0x14007a89c`
- `0x14007e390`
- `0x14007f510`
- `0x140080e00`
- `0x140082b30`
- `0x140085de0`
- `0x140086f50`

## callees

- `0x1400152a0`

## import_xrefs

- `ntoskrnl!PsImpersonateClient` at `0x1400152fb`
- `ntoskrnl!PsImpersonateClient` at `0x1400152fb`
- `ksecdd!ImpersonateSecurityContext` at `0x1400152cb`
- `ksecdd!ImpersonateSecurityContext` at `0x1400152cb`

## pseudocode

```c
SECURITY_STATUS __fastcall Smb2ImpersonateWorkItem(__int64 a1)
{
  __int64 v1; // rax
  __int64 v2; // rax

  v1 = *(_QWORD *)(a1 + 56);
  if ( !v1 || (v2 = *(_QWORD *)(v1 + 120)) == 0 )
    v2 = *(_QWORD *)(a1 + 48);
  if ( *(_BYTE *)(v2 + 24) )
    return PsImpersonateClient(
             KeGetCurrentThread(),
             *(PACCESS_TOKEN *)(v2 + 48),
             *(_BYTE *)(v2 + 60),
             *(_BYTE *)(v2 + 61),
             *(SECURITY_IMPERSONATION_LEVEL *)(v2 + 64));
  if ( *(_QWORD *)(v2 + 32) || *(_QWORD *)(v2 + 40) )
    return ImpersonateSecurityContext((PCtxtHandle)(v2 + 32));
  return -1073741790;
}

```

## disassembly

```asm
0x1400152a0  sub     rsp, 38h
0x1400152a4  mov     rax, [rcx+38h]
0x1400152a8  test    rax, rax
0x1400152ab  jz      short loc_1400152B6
0x1400152ad  mov     rax, [rax+78h]
0x1400152b1  test    rax, rax
0x1400152b4  jnz     short loc_1400152BA
0x1400152b6  mov     rax, [rcx+30h]
0x1400152ba  cmp     byte ptr [rax+18h], 0
0x1400152be  jnz     short loc_1400152DD
0x1400152c0  cmp     qword ptr [rax+20h], 0
0x1400152c5  lea     rcx, [rax+20h]; phContext
0x1400152c9  jz      short loc_14001530D
0x1400152cb  call    cs:__imp_ImpersonateSecurityContext
0x1400152d2  nop     dword ptr [rax+rax+00h]
0x1400152d7  add     rsp, 38h
0x1400152db  retn
0x1400152dd  mov     rcx, gs:188h; Thread
0x1400152e6  mov     edx, [rax+40h]
0x1400152e9  movzx   r9d, byte ptr [rax+3Dh]; EffectiveOnly
0x1400152ee  movzx   r8d, byte ptr [rax+3Ch]; CopyOnOpen
0x1400152f3  mov     [rsp+38h+ImpersonationLevel], edx; ImpersonationLevel
0x1400152f7  mov     rdx, [rax+30h]; Token
0x1400152fb  call    cs:__imp_PsImpersonateClient
0x140015302  nop     dword ptr [rax+rax+00h]
0x140015307  add     rsp, 38h
0x14001530b  retn
0x14001530d  cmp     qword ptr [rax+28h], 0
0x140015312  jnz     short loc_1400152CB
0x140015314  mov     eax, 0C0000022h
0x140015319  jmp     short loc_1400152D7
```
