# SepSddlAddAceToAcl

- ea: `0x1400d3b48`
- end: `0x1400d3c33`
- name: `SepSddlAddAceToAcl`
- size: `235`
- prototype: `__int64 __fastcall(int, int, int, int, ACCESS_MASK AccessMask, int, PSID Sid)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x1400d3d20`

## callees

- `0x14005de00`
- `0x14005e100`
- `0x1400d3b48`

## import_xrefs

- `ntoskrnl!RtlLengthSid` at `0x1400d3b6c`
- `ntoskrnl!RtlLengthSid` at `0x1400d3b6c`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x1400d3c15`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x1400d3c15`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400d3be6`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400d3be6`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400d3ba6`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400d3ba6`

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
0x1400d3b48  push    rbx
0x1400d3b4a  push    rbp
0x1400d3b4b  push    rsi
0x1400d3b4c  push    rdi
0x1400d3b4d  push    r12
0x1400d3b4f  push    r13
0x1400d3b51  push    r14
0x1400d3b53  push    r15
0x1400d3b55  sub     rsp, 28h
0x1400d3b59  mov     rdi, [rcx]
0x1400d3b5c  mov     r15, rcx
0x1400d3b5f  mov     rcx, [rsp+68h+Sid]; Sid
0x1400d3b67  mov     r14, rdx
0x1400d3b6a  mov     esi, [rdx]
0x1400d3b6c  call    cs:__imp_RtlLengthSid
0x1400d3b73  nop     dword ptr [rax+rax+00h]
0x1400d3b78  lea     r8d, [rax+8]
0x1400d3b7c  movzx   eax, word ptr [rdi+2]
0x1400d3b80  lea     ebp, [r8+rsi]
0x1400d3b84  cmp     ebp, eax
0x1400d3b86  jbe     short loc_1400D3BF7
0x1400d3b88  imul    r8d, [rsp+68h+arg_28]
0x1400d3b91  mov     ecx, 1; PoolType
0x1400d3b96  lea     r12d, [r8+rsi]
0x1400d3b9a  mov     r8d, 6C416553h; Tag
0x1400d3ba0  mov     edx, r12d; NumberOfBytes
0x1400d3ba3  mov     r13d, r12d
0x1400d3ba6  call    cs:__imp_ExAllocatePoolWithTag
0x1400d3bad  nop     dword ptr [rax+rax+00h]
0x1400d3bb2  mov     rbx, rax
0x1400d3bb5  test    rax, rax
0x1400d3bb8  jnz     short loc_1400D3BC1
0x1400d3bba  mov     eax, 0C000009Ah
0x1400d3bbf  jmp     short loc_1400D3C21
0x1400d3bc1  mov     r8, r13; Size
0x1400d3bc4  xor     edx, edx; Val
0x1400d3bc6  mov     rcx, rbx; void *
0x1400d3bc9  call    memset
0x1400d3bce  mov     rdx, [r15]; Src
0x1400d3bd1  mov     r8, rsi; Size
0x1400d3bd4  mov     rcx, rbx; void *
0x1400d3bd7  call    memmove
0x1400d3bdc  xor     edx, edx; Tag
0x1400d3bde  mov     [rbx+2], r12w
0x1400d3be3  mov     rcx, rdi; P
0x1400d3be6  call    cs:__imp_ExFreePoolWithTag
0x1400d3bed  nop     dword ptr [rax+rax+00h]
0x1400d3bf2  mov     [r15], rbx
0x1400d3bf5  jmp     short loc_1400D3BFA
0x1400d3bf7  mov     rbx, rdi
0x1400d3bfa  mov     r9, [rsp+68h+Sid]; Sid
0x1400d3c02  mov     edx, 2; AceRevision
0x1400d3c07  mov     r8d, [rsp+68h+AccessMask]; AccessMask
0x1400d3c0f  mov     rcx, rbx; Acl
0x1400d3c12  mov     [r14], ebp
0x1400d3c15  call    cs:__imp_RtlAddAccessAllowedAce
0x1400d3c1c  nop     dword ptr [rax+rax+00h]
0x1400d3c21  add     rsp, 28h
0x1400d3c25  pop     r15
0x1400d3c27  pop     r14
0x1400d3c29  pop     r13
0x1400d3c2b  pop     r12
0x1400d3c2d  pop     rdi
0x1400d3c2e  pop     rsi
0x1400d3c2f  pop     rbp
0x1400d3c30  pop     rbx
0x1400d3c31  retn
```
