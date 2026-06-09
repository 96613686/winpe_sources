# SepSddlAddAceToAcl

- ea: `0x140018400`
- end: `0x1400184eb`
- name: `SepSddlAddAceToAcl`
- size: `235`
- prototype: `__int64 __fastcall(int, int, int, int, ACCESS_MASK AccessMask, int, PSID Sid)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x1400185d8`

## callees

- `0x1400051c0`
- `0x1400054c0`
- `0x140018400`

## import_xrefs

- `ntoskrnl!RtlAddAccessAllowedAce` at `0x1400184cd`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x1400184cd`
- `ntoskrnl!RtlLengthSid` at `0x140018424`
- `ntoskrnl!RtlLengthSid` at `0x140018424`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001849e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001849e`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14001845e`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14001845e`

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
0x140018400  push    rbx
0x140018402  push    rbp
0x140018403  push    rsi
0x140018404  push    rdi
0x140018405  push    r12
0x140018407  push    r13
0x140018409  push    r14
0x14001840b  push    r15
0x14001840d  sub     rsp, 28h
0x140018411  mov     rdi, [rcx]
0x140018414  mov     r15, rcx
0x140018417  mov     rcx, [rsp+68h+Sid]; Sid
0x14001841f  mov     r14, rdx
0x140018422  mov     esi, [rdx]
0x140018424  call    cs:__imp_RtlLengthSid
0x14001842b  nop     dword ptr [rax+rax+00h]
0x140018430  lea     r8d, [rax+8]
0x140018434  movzx   eax, word ptr [rdi+2]
0x140018438  lea     ebp, [r8+rsi]
0x14001843c  cmp     ebp, eax
0x14001843e  jbe     short loc_1400184AF
0x140018440  imul    r8d, [rsp+68h+arg_28]
0x140018449  mov     ecx, 1; PoolType
0x14001844e  lea     r12d, [r8+rsi]
0x140018452  mov     r8d, 6C416553h; Tag
0x140018458  mov     edx, r12d; NumberOfBytes
0x14001845b  mov     r13d, r12d
0x14001845e  call    cs:__imp_ExAllocatePoolWithTag
0x140018465  nop     dword ptr [rax+rax+00h]
0x14001846a  mov     rbx, rax
0x14001846d  test    rax, rax
0x140018470  jnz     short loc_140018479
0x140018472  mov     eax, 0C000009Ah
0x140018477  jmp     short loc_1400184D9
0x140018479  mov     r8, r13; Size
0x14001847c  xor     edx, edx; Val
0x14001847e  mov     rcx, rbx; void *
0x140018481  call    memset
0x140018486  mov     rdx, [r15]; Src
0x140018489  mov     r8, rsi; Size
0x14001848c  mov     rcx, rbx; void *
0x14001848f  call    memmove
0x140018494  xor     edx, edx; Tag
0x140018496  mov     [rbx+2], r12w
0x14001849b  mov     rcx, rdi; P
0x14001849e  call    cs:__imp_ExFreePoolWithTag
0x1400184a5  nop     dword ptr [rax+rax+00h]
0x1400184aa  mov     [r15], rbx
0x1400184ad  jmp     short loc_1400184B2
0x1400184af  mov     rbx, rdi
0x1400184b2  mov     r9, [rsp+68h+Sid]; Sid
0x1400184ba  mov     edx, 2; AceRevision
0x1400184bf  mov     r8d, [rsp+68h+AccessMask]; AccessMask
0x1400184c7  mov     rcx, rbx; Acl
0x1400184ca  mov     [r14], ebp
0x1400184cd  call    cs:__imp_RtlAddAccessAllowedAce
0x1400184d4  nop     dword ptr [rax+rax+00h]
0x1400184d9  add     rsp, 28h
0x1400184dd  pop     r15
0x1400184df  pop     r14
0x1400184e1  pop     r13
0x1400184e3  pop     r12
0x1400184e5  pop     rdi
0x1400184e6  pop     rsi
0x1400184e7  pop     rbp
0x1400184e8  pop     rbx
0x1400184e9  retn
```
