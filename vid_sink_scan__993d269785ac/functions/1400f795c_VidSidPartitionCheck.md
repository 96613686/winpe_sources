# VidSidPartitionCheck

- ea: `0x1400f795c`
- end: `0x1400f7aaa`
- name: `VidSidPartitionCheck`
- size: `334`
- prototype: `__int64 __fastcall(void *Buf2)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x140009988`

## callees

- `0x140022010`
- `0x140074cb4`
- `0x140075a04`
- `0x1400f795c`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400f7a90`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400f7a90`
- `ntoskrnl!RtlValidSid` at `0x1400f79a1`
- `ntoskrnl!RtlValidSid` at `0x1400f79a1`
- `ntoskrnl!RtlSubAuthorityCountSid` at `0x1400f79be`
- `ntoskrnl!RtlSubAuthorityCountSid` at `0x1400f79be`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1400f79d4`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1400f79ed`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1400f7a06`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1400f7a20`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1400f7a3a`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1400f7a54`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1400f79d4`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1400f79ed`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1400f7a06`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1400f7a20`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1400f7a3a`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1400f7a54`

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
0x1400f795c  mov     [rsp+arg_0], rbx
0x1400f7961  push    rdi
0x1400f7962  sub     rsp, 30h
0x1400f7966  mov     rdi, rcx
0x1400f7969  mov     [rsp+38h+P], 0
0x1400f7972  call    VidCurrentProcessIsAdmin
0x1400f7977  test    eax, eax
0x1400f7979  jz      short loc_1400F7982
0x1400f797b  xor     ebx, ebx
0x1400f797d  jmp     loc_1400F7A84
0x1400f7982  lea     rdx, [rsp+38h+P]
0x1400f7987  call    VidCurrentProcessQueryToken
0x1400f798c  mov     ebx, eax
0x1400f798e  test    eax, eax
0x1400f7990  js      loc_1400F7A84
0x1400f7996  mov     rax, [rsp+38h+P]
0x1400f799b  mov     rbx, [rax]
0x1400f799e  mov     rcx, rbx; Sid
0x1400f79a1  call    cs:__imp_RtlValidSid
0x1400f79a8  nop     dword ptr [rax+rax+00h]
0x1400f79ad  test    al, al
0x1400f79af  jnz     short loc_1400F79BB
0x1400f79b1  mov     ebx, 0C000000Dh
0x1400f79b6  jmp     loc_1400F7A84
0x1400f79bb  mov     rcx, rbx; Sid
0x1400f79be  call    cs:__imp_RtlSubAuthorityCountSid
0x1400f79c5  nop     dword ptr [rax+rax+00h]
0x1400f79ca  cmp     byte ptr [rax], 6
0x1400f79cd  jnz     short loc_1400F79B1
0x1400f79cf  xor     edx, edx; SubAuthority
0x1400f79d1  mov     rcx, rbx; Sid
0x1400f79d4  call    cs:__imp_RtlSubAuthoritySid
0x1400f79db  nop     dword ptr [rax+rax+00h]
0x1400f79e0  cmp     dword ptr [rax], 53h ; 'S'
0x1400f79e3  jnz     short loc_1400F79B1
0x1400f79e5  mov     edx, 1; SubAuthority
0x1400f79ea  mov     rcx, rbx; Sid
0x1400f79ed  call    cs:__imp_RtlSubAuthoritySid
0x1400f79f4  nop     dword ptr [rax+rax+00h]
0x1400f79f9  cmp     dword ptr [rax], 1
0x1400f79fc  jnz     short loc_1400F79B1
0x1400f79fe  mov     edx, 2; SubAuthority
0x1400f7a03  mov     rcx, rbx; Sid
0x1400f7a06  call    cs:__imp_RtlSubAuthoritySid
0x1400f7a0d  nop     dword ptr [rax+rax+00h]
0x1400f7a12  mov     rcx, rbx; Sid
0x1400f7a15  mov     edx, [rax]
0x1400f7a17  mov     [rsp+38h+Buf1], edx
0x1400f7a1b  mov     edx, 3; SubAuthority
0x1400f7a20  call    cs:__imp_RtlSubAuthoritySid
0x1400f7a27  nop     dword ptr [rax+rax+00h]
0x1400f7a2c  mov     rcx, rbx; Sid
0x1400f7a2f  mov     edx, [rax]
0x1400f7a31  mov     [rsp+38h+var_14], edx
0x1400f7a35  mov     edx, 4; SubAuthority
0x1400f7a3a  call    cs:__imp_RtlSubAuthoritySid
0x1400f7a41  nop     dword ptr [rax+rax+00h]
0x1400f7a46  mov     rcx, rbx; Sid
0x1400f7a49  mov     edx, [rax]
0x1400f7a4b  mov     [rsp+38h+var_10], edx
0x1400f7a4f  mov     edx, 5; SubAuthority
0x1400f7a54  call    cs:__imp_RtlSubAuthoritySid
0x1400f7a5b  nop     dword ptr [rax+rax+00h]
0x1400f7a60  mov     r8d, 10h; Size
0x1400f7a66  mov     rdx, rdi; Buf2
0x1400f7a69  mov     ecx, [rax]
0x1400f7a6b  mov     [rsp+38h+var_C], ecx
0x1400f7a6f  lea     rcx, [rsp+38h+Buf1]; Buf1
0x1400f7a74  call    memcmp
0x1400f7a79  neg     eax
0x1400f7a7b  mov     ebx, 0C000000Dh
0x1400f7a80  sbb     ecx, ecx
0x1400f7a82  and     ebx, ecx
0x1400f7a84  mov     rcx, [rsp+38h+P]; P
0x1400f7a89  test    rcx, rcx
0x1400f7a8c  jz      short loc_1400F7A9C
0x1400f7a8e  xor     edx, edx; Tag
0x1400f7a90  call    cs:__imp_ExFreePoolWithTag
0x1400f7a97  nop     dword ptr [rax+rax+00h]
0x1400f7a9c  mov     eax, ebx
0x1400f7a9e  mov     rbx, [rsp+38h+arg_0]
0x1400f7aa3  add     rsp, 30h
0x1400f7aa7  pop     rdi
0x1400f7aa8  retn
```
