# SepSddlAddAceToAcl

- ea: `0x1400d3bb8`
- end: `0x1400d3ca3`
- name: `SepSddlAddAceToAcl`
- size: `235`
- prototype: `__int64 __fastcall(int, int, int, int, ACCESS_MASK AccessMask, int, PSID Sid)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x1400d3d90`

## callees

- `0x14005da00`
- `0x14005dd00`
- `0x1400d3bb8`

## import_xrefs

- `ntoskrnl!RtlLengthSid` at `0x1400d3bdc`
- `ntoskrnl!RtlLengthSid` at `0x1400d3bdc`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x1400d3c85`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x1400d3c85`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400d3c56`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400d3c56`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400d3c16`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400d3c16`

## pseudocode

```c
NTSTATUS __fastcall SepSddlAddAceToAcl(
        const void **a1,
        _DWORD *a2,
        __int64 a3,
        __int64 a4,
        ACCESS_MASK AccessMask,
        int a6,
        PSID Sid)
{
  unsigned __int16 *v7; // rdi
  size_t v10; // rsi
  ULONG v11; // r8d
  int v12; // ebp
  unsigned int v13; // r12d
  struct _ACL *PoolWithTag; // rax
  struct _ACL *v15; // rbx

  v7 = (unsigned __int16 *)*a1;
  v10 = (unsigned int)*a2;
  v11 = RtlLengthSid(Sid) + 8;
  v12 = v11 + v10;
  if ( v11 + (unsigned int)v10 <= v7[1] )
  {
    v15 = (struct _ACL *)v7;
  }
  else
  {
    v13 = a6 * v11 + v10;
    PoolWithTag = (struct _ACL *)ExAllocatePoolWithTag(PagedPool, v13, 0x6C416553u);
    v15 = PoolWithTag;
    if ( !PoolWithTag )
      return -1073741670;
    memset(PoolWithTag, 0, v13);
    memmove(v15, *a1, v10);
    v15->AclSize = v13;
    ExFreePoolWithTag(v7, 0);
    *a1 = v15;
  }
  *a2 = v12;
  return RtlAddAccessAllowedAce(v15, 2u, AccessMask, Sid);
}

```

## disassembly

```asm
0x1400d3bb8  push    rbx
0x1400d3bba  push    rbp
0x1400d3bbb  push    rsi
0x1400d3bbc  push    rdi
0x1400d3bbd  push    r12
0x1400d3bbf  push    r13
0x1400d3bc1  push    r14
0x1400d3bc3  push    r15
0x1400d3bc5  sub     rsp, 28h
0x1400d3bc9  mov     rdi, [rcx]
0x1400d3bcc  mov     r15, rcx
0x1400d3bcf  mov     rcx, [rsp+68h+Sid]; Sid
0x1400d3bd7  mov     r14, rdx
0x1400d3bda  mov     esi, [rdx]
0x1400d3bdc  call    cs:__imp_RtlLengthSid
0x1400d3be3  nop     dword ptr [rax+rax+00h]
0x1400d3be8  lea     r8d, [rax+8]
0x1400d3bec  movzx   eax, word ptr [rdi+2]
0x1400d3bf0  lea     ebp, [r8+rsi]
0x1400d3bf4  cmp     ebp, eax
0x1400d3bf6  jbe     short loc_1400D3C67
0x1400d3bf8  imul    r8d, [rsp+68h+arg_28]
0x1400d3c01  mov     ecx, 1; PoolType
0x1400d3c06  lea     r12d, [r8+rsi]
0x1400d3c0a  mov     r8d, 6C416553h; Tag
0x1400d3c10  mov     edx, r12d; NumberOfBytes
0x1400d3c13  mov     r13d, r12d
0x1400d3c16  call    cs:__imp_ExAllocatePoolWithTag
0x1400d3c1d  nop     dword ptr [rax+rax+00h]
0x1400d3c22  mov     rbx, rax
0x1400d3c25  test    rax, rax
0x1400d3c28  jnz     short loc_1400D3C31
0x1400d3c2a  mov     eax, 0C000009Ah
0x1400d3c2f  jmp     short loc_1400D3C91
0x1400d3c31  mov     r8, r13; Size
0x1400d3c34  xor     edx, edx; Val
0x1400d3c36  mov     rcx, rbx; void *
0x1400d3c39  call    memset
0x1400d3c3e  mov     rdx, [r15]; Src
0x1400d3c41  mov     r8, rsi; Size
0x1400d3c44  mov     rcx, rbx; void *
0x1400d3c47  call    memmove
0x1400d3c4c  xor     edx, edx; Tag
0x1400d3c4e  mov     [rbx+2], r12w
0x1400d3c53  mov     rcx, rdi; P
0x1400d3c56  call    cs:__imp_ExFreePoolWithTag
0x1400d3c5d  nop     dword ptr [rax+rax+00h]
0x1400d3c62  mov     [r15], rbx
0x1400d3c65  jmp     short loc_1400D3C6A
0x1400d3c67  mov     rbx, rdi
0x1400d3c6a  mov     r9, [rsp+68h+Sid]; Sid
0x1400d3c72  mov     edx, 2; AceRevision
0x1400d3c77  mov     r8d, [rsp+68h+AccessMask]; AccessMask
0x1400d3c7f  mov     rcx, rbx; Acl
0x1400d3c82  mov     [r14], ebp
0x1400d3c85  call    cs:__imp_RtlAddAccessAllowedAce
0x1400d3c8c  nop     dword ptr [rax+rax+00h]
0x1400d3c91  add     rsp, 28h
0x1400d3c95  pop     r15
0x1400d3c97  pop     r14
0x1400d3c99  pop     r13
0x1400d3c9b  pop     r12
0x1400d3c9d  pop     rdi
0x1400d3c9e  pop     rsi
0x1400d3c9f  pop     rbp
0x1400d3ca0  pop     rbx
0x1400d3ca1  retn
```
