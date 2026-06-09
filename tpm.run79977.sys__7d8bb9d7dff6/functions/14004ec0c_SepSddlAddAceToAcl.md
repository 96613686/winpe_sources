# SepSddlAddAceToAcl

- ea: `0x14004ec0c`
- end: `0x14004ecf7`
- name: `SepSddlAddAceToAcl`
- size: `235`
- prototype: `__int64 __fastcall(int, int, int, int, ACCESS_MASK AccessMask, int, PSID Sid)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x14004eddc`

## callees

- `0x140039840`
- `0x140039b40`
- `0x14004ec0c`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14004ecaa`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004ecaa`
- `ntoskrnl!RtlLengthSid` at `0x14004ec30`
- `ntoskrnl!RtlLengthSid` at `0x14004ec30`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x14004ecd9`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x14004ecd9`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14004ec6a`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14004ec6a`

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
0x14004ec0c  push    rbx
0x14004ec0e  push    rbp
0x14004ec0f  push    rsi
0x14004ec10  push    rdi
0x14004ec11  push    r12
0x14004ec13  push    r13
0x14004ec15  push    r14
0x14004ec17  push    r15
0x14004ec19  sub     rsp, 28h
0x14004ec1d  mov     rdi, [rcx]
0x14004ec20  mov     r15, rcx
0x14004ec23  mov     rcx, [rsp+68h+Sid]; Sid
0x14004ec2b  mov     r14, rdx
0x14004ec2e  mov     esi, [rdx]
0x14004ec30  call    cs:__imp_RtlLengthSid
0x14004ec37  nop     dword ptr [rax+rax+00h]
0x14004ec3c  lea     r8d, [rax+8]
0x14004ec40  movzx   eax, word ptr [rdi+2]
0x14004ec44  lea     ebp, [r8+rsi]
0x14004ec48  cmp     ebp, eax
0x14004ec4a  jbe     short loc_14004ECBB
0x14004ec4c  imul    r8d, [rsp+68h+arg_28]
0x14004ec55  mov     ecx, 1; PoolType
0x14004ec5a  lea     r12d, [r8+rsi]
0x14004ec5e  mov     r8d, 6C416553h; Tag
0x14004ec64  mov     edx, r12d; NumberOfBytes
0x14004ec67  mov     r13d, r12d
0x14004ec6a  call    cs:__imp_ExAllocatePoolWithTag
0x14004ec71  nop     dword ptr [rax+rax+00h]
0x14004ec76  mov     rbx, rax
0x14004ec79  test    rax, rax
0x14004ec7c  jnz     short loc_14004EC85
0x14004ec7e  mov     eax, 0C000009Ah
0x14004ec83  jmp     short loc_14004ECE5
0x14004ec85  mov     r8, r13; Size
0x14004ec88  xor     edx, edx; Val
0x14004ec8a  mov     rcx, rbx; void *
0x14004ec8d  call    memset
0x14004ec92  mov     rdx, [r15]; Src
0x14004ec95  mov     r8, rsi; Size
0x14004ec98  mov     rcx, rbx; void *
0x14004ec9b  call    memmove
0x14004eca0  xor     edx, edx; Tag
0x14004eca2  mov     [rbx+2], r12w
0x14004eca7  mov     rcx, rdi; P
0x14004ecaa  call    cs:__imp_ExFreePoolWithTag
0x14004ecb1  nop     dword ptr [rax+rax+00h]
0x14004ecb6  mov     [r15], rbx
0x14004ecb9  jmp     short loc_14004ECBE
0x14004ecbb  mov     rbx, rdi
0x14004ecbe  mov     r9, [rsp+68h+Sid]; Sid
0x14004ecc6  mov     edx, 2; AceRevision
0x14004eccb  mov     r8d, [rsp+68h+AccessMask]; AccessMask
0x14004ecd3  mov     rcx, rbx; Acl
0x14004ecd6  mov     [r14], ebp
0x14004ecd9  call    cs:__imp_RtlAddAccessAllowedAce
0x14004ece0  nop     dword ptr [rax+rax+00h]
0x14004ece5  add     rsp, 28h
0x14004ece9  pop     r15
0x14004eceb  pop     r14
0x14004eced  pop     r13
0x14004ecef  pop     r12
0x14004ecf1  pop     rdi
0x14004ecf2  pop     rsi
0x14004ecf3  pop     rbp
0x14004ecf4  pop     rbx
0x14004ecf5  retn
```
