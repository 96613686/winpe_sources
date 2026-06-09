# Smb2ImpersonateSecurityContext

- ea: `0x140015960`
- end: `0x1400159c8`
- name: `Smb2ImpersonateSecurityContext`
- size: `104`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `14`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14002ff54`
- `0x14005a31c`
- `0x140068014`
- `0x140068838`
- `0x140069bb0`
- `0x14006a1c4`
- `0x140075bb8`
- `0x140076de8`
- `0x140077594`
- `0x14007c260`
- `0x140085f90`
- `0x14008d858`
- `0x140091cc0`
- `0x1400921f0`

## callees

- `0x140015960`

## import_xrefs

- `ntoskrnl!PsImpersonateClient` at `0x1400159a8`
- `ntoskrnl!PsImpersonateClient` at `0x1400159a8`
- `ksecdd!ImpersonateSecurityContext` at `0x140015975`
- `ksecdd!ImpersonateSecurityContext` at `0x140015975`

## pseudocode

```c
SECURITY_STATUS __fastcall Smb2ImpersonateSecurityContext(__int64 a1)
{
  if ( *(_BYTE *)(a1 + 24) )
    return PsImpersonateClient(
             KeGetCurrentThread(),
             *(PACCESS_TOKEN *)(a1 + 48),
             *(_BYTE *)(a1 + 60),
             *(_BYTE *)(a1 + 61),
             *(SECURITY_IMPERSONATION_LEVEL *)(a1 + 64));
  if ( *(_QWORD *)(a1 + 32) || *(_QWORD *)(a1 + 40) )
    return ImpersonateSecurityContext((PCtxtHandle)(a1 + 32));
  return -1073741790;
}

```

## disassembly

```asm
0x140015960  sub     rsp, 38h
0x140015964  cmp     byte ptr [rcx+18h], 0
0x140015968  jnz     short loc_140015987
0x14001596a  cmp     qword ptr [rcx+20h], 0
0x14001596f  jz      short loc_1400159BA
0x140015971  add     rcx, 20h ; ' '; phContext
0x140015975  call    cs:__imp_ImpersonateSecurityContext
0x14001597c  nop     dword ptr [rax+rax+00h]
0x140015981  add     rsp, 38h
0x140015985  retn
0x140015987  mov     r10, gs:188h
0x140015990  mov     eax, [rcx+40h]
0x140015993  movzx   r9d, byte ptr [rcx+3Dh]; EffectiveOnly
0x140015998  movzx   r8d, byte ptr [rcx+3Ch]; CopyOnOpen
0x14001599d  mov     rdx, [rcx+30h]; Token
0x1400159a1  mov     rcx, r10; Thread
0x1400159a4  mov     [rsp+38h+ImpersonationLevel], eax; ImpersonationLevel
0x1400159a8  call    cs:__imp_PsImpersonateClient
0x1400159af  nop     dword ptr [rax+rax+00h]
0x1400159b4  add     rsp, 38h
0x1400159b8  retn
0x1400159ba  cmp     qword ptr [rcx+28h], 0
0x1400159bf  jnz     short loc_140015971
0x1400159c1  mov     eax, 0C0000022h
0x1400159c6  jmp     short loc_140015981
```
