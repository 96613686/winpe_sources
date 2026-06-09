# VidSidPartitionCheck

- ea: `0x1400fa3ac`
- end: `0x1400fa4fa`
- name: `VidSidPartitionCheck`
- size: `334`
- prototype: `__int64 __fastcall(void *Buf2)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x1400094b8`

## callees

- `0x140022610`
- `0x140075c10`
- `0x1400768e0`
- `0x1400fa3ac`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400fa4e0`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400fa4e0`
- `ntoskrnl!RtlValidSid` at `0x1400fa3f1`
- `ntoskrnl!RtlValidSid` at `0x1400fa3f1`
- `ntoskrnl!RtlSubAuthorityCountSid` at `0x1400fa40e`
- `ntoskrnl!RtlSubAuthorityCountSid` at `0x1400fa40e`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1400fa424`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1400fa43d`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1400fa456`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1400fa470`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1400fa48a`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1400fa4a4`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1400fa424`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1400fa43d`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1400fa456`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1400fa470`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1400fa48a`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1400fa4a4`

## pseudocode

```c
__int64 __fastcall VidSidPartitionCheck(void *Buf2)
{
  __int64 v2; // rcx
  signed int v3; // ebx
  PSID v4; // rbx
  _DWORD Buf1[6]; // [rsp+20h] [rbp-18h] BYREF
  PVOID P; // [rsp+48h] [rbp+10h] BYREF

  P = 0;
  if ( (unsigned int)VidCurrentProcessIsAdmin() )
  {
    v3 = 0;
  }
  else
  {
    v3 = VidCurrentProcessQueryToken(v2, &P);
    if ( v3 >= 0 )
    {
      v4 = *(PSID *)P;
      if ( RtlValidSid(*(PSID *)P)
        && *RtlSubAuthorityCountSid(v4) == 6
        && *RtlSubAuthoritySid(v4, 0) == 83
        && *RtlSubAuthoritySid(v4, 1u) == 1 )
      {
        Buf1[0] = *RtlSubAuthoritySid(v4, 2u);
        Buf1[1] = *RtlSubAuthoritySid(v4, 3u);
        Buf1[2] = *RtlSubAuthoritySid(v4, 4u);
        Buf1[3] = *RtlSubAuthoritySid(v4, 5u);
        v3 = memcmp(Buf1, Buf2, 0x10u) != 0 ? 0xC000000D : 0;
      }
      else
      {
        v3 = -1073741811;
      }
    }
  }
  if ( P )
    ExFreePoolWithTag(P, 0);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1400fa3ac  mov     [rsp+arg_0], rbx
0x1400fa3b1  push    rdi
0x1400fa3b2  sub     rsp, 30h
0x1400fa3b6  mov     rdi, rcx
0x1400fa3b9  mov     [rsp+38h+P], 0
0x1400fa3c2  call    VidCurrentProcessIsAdmin
0x1400fa3c7  test    eax, eax
0x1400fa3c9  jz      short loc_1400FA3D2
0x1400fa3cb  xor     ebx, ebx
0x1400fa3cd  jmp     loc_1400FA4D4
0x1400fa3d2  lea     rdx, [rsp+38h+P]
0x1400fa3d7  call    VidCurrentProcessQueryToken
0x1400fa3dc  mov     ebx, eax
0x1400fa3de  test    eax, eax
0x1400fa3e0  js      loc_1400FA4D4
0x1400fa3e6  mov     rax, [rsp+38h+P]
0x1400fa3eb  mov     rbx, [rax]
0x1400fa3ee  mov     rcx, rbx; Sid
0x1400fa3f1  call    cs:__imp_RtlValidSid
0x1400fa3f8  nop     dword ptr [rax+rax+00h]
0x1400fa3fd  test    al, al
0x1400fa3ff  jnz     short loc_1400FA40B
0x1400fa401  mov     ebx, 0C000000Dh
0x1400fa406  jmp     loc_1400FA4D4
0x1400fa40b  mov     rcx, rbx; Sid
0x1400fa40e  call    cs:__imp_RtlSubAuthorityCountSid
0x1400fa415  nop     dword ptr [rax+rax+00h]
0x1400fa41a  cmp     byte ptr [rax], 6
0x1400fa41d  jnz     short loc_1400FA401
0x1400fa41f  xor     edx, edx; SubAuthority
0x1400fa421  mov     rcx, rbx; Sid
0x1400fa424  call    cs:__imp_RtlSubAuthoritySid
0x1400fa42b  nop     dword ptr [rax+rax+00h]
0x1400fa430  cmp     dword ptr [rax], 53h ; 'S'
0x1400fa433  jnz     short loc_1400FA401
0x1400fa435  mov     edx, 1; SubAuthority
0x1400fa43a  mov     rcx, rbx; Sid
0x1400fa43d  call    cs:__imp_RtlSubAuthoritySid
0x1400fa444  nop     dword ptr [rax+rax+00h]
0x1400fa449  cmp     dword ptr [rax], 1
0x1400fa44c  jnz     short loc_1400FA401
0x1400fa44e  mov     edx, 2; SubAuthority
0x1400fa453  mov     rcx, rbx; Sid
0x1400fa456  call    cs:__imp_RtlSubAuthoritySid
0x1400fa45d  nop     dword ptr [rax+rax+00h]
0x1400fa462  mov     rcx, rbx; Sid
0x1400fa465  mov     edx, [rax]
0x1400fa467  mov     [rsp+38h+Buf1], edx
0x1400fa46b  mov     edx, 3; SubAuthority
0x1400fa470  call    cs:__imp_RtlSubAuthoritySid
0x1400fa477  nop     dword ptr [rax+rax+00h]
0x1400fa47c  mov     rcx, rbx; Sid
0x1400fa47f  mov     edx, [rax]
0x1400fa481  mov     [rsp+38h+var_14], edx
0x1400fa485  mov     edx, 4; SubAuthority
0x1400fa48a  call    cs:__imp_RtlSubAuthoritySid
0x1400fa491  nop     dword ptr [rax+rax+00h]
0x1400fa496  mov     rcx, rbx; Sid
0x1400fa499  mov     edx, [rax]
0x1400fa49b  mov     [rsp+38h+var_10], edx
0x1400fa49f  mov     edx, 5; SubAuthority
0x1400fa4a4  call    cs:__imp_RtlSubAuthoritySid
0x1400fa4ab  nop     dword ptr [rax+rax+00h]
0x1400fa4b0  mov     r8d, 10h; Size
0x1400fa4b6  mov     rdx, rdi; Buf2
0x1400fa4b9  mov     ecx, [rax]
0x1400fa4bb  mov     [rsp+38h+var_C], ecx
0x1400fa4bf  lea     rcx, [rsp+38h+Buf1]; Buf1
0x1400fa4c4  call    memcmp
0x1400fa4c9  neg     eax
0x1400fa4cb  mov     ebx, 0C000000Dh
0x1400fa4d0  sbb     ecx, ecx
0x1400fa4d2  and     ebx, ecx
0x1400fa4d4  mov     rcx, [rsp+38h+P]; P
0x1400fa4d9  test    rcx, rcx
0x1400fa4dc  jz      short loc_1400FA4EC
0x1400fa4de  xor     edx, edx; Tag
0x1400fa4e0  call    cs:__imp_ExFreePoolWithTag
0x1400fa4e7  nop     dword ptr [rax+rax+00h]
0x1400fa4ec  mov     eax, ebx
0x1400fa4ee  mov     rbx, [rsp+38h+arg_0]
0x1400fa4f3  add     rsp, 30h
0x1400fa4f7  pop     rdi
0x1400fa4f8  retn
```
