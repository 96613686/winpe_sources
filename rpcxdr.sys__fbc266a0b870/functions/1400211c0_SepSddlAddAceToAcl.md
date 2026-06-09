# SepSddlAddAceToAcl

- ea: `0x1400211c0`
- end: `0x1400212ab`
- name: `SepSddlAddAceToAcl`
- size: `235`
- prototype: `__int64 __fastcall(int, int, int, int, ACCESS_MASK AccessMask, int, PSID Sid)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x140021398`

## callees

- `0x140015840`
- `0x140015b40`
- `0x1400211c0`

## import_xrefs

- `ntoskrnl!RtlLengthSid` at `0x1400211e4`
- `ntoskrnl!RtlLengthSid` at `0x1400211e4`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x14002128d`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x14002128d`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14002121e`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14002121e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002125e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002125e`

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
0x1400211c0  push    rbx
0x1400211c2  push    rbp
0x1400211c3  push    rsi
0x1400211c4  push    rdi
0x1400211c5  push    r12
0x1400211c7  push    r13
0x1400211c9  push    r14
0x1400211cb  push    r15
0x1400211cd  sub     rsp, 28h
0x1400211d1  mov     rdi, [rcx]
0x1400211d4  mov     r15, rcx
0x1400211d7  mov     rcx, [rsp+68h+Sid]; Sid
0x1400211df  mov     r14, rdx
0x1400211e2  mov     esi, [rdx]
0x1400211e4  call    cs:__imp_RtlLengthSid
0x1400211eb  nop     dword ptr [rax+rax+00h]
0x1400211f0  lea     r8d, [rax+8]
0x1400211f4  movzx   eax, word ptr [rdi+2]
0x1400211f8  lea     ebp, [r8+rsi]
0x1400211fc  cmp     ebp, eax
0x1400211fe  jbe     short loc_14002126F
0x140021200  imul    r8d, [rsp+68h+arg_28]
0x140021209  mov     ecx, 1; PoolType
0x14002120e  lea     r12d, [r8+rsi]
0x140021212  mov     r8d, 6C416553h; Tag
0x140021218  mov     edx, r12d; NumberOfBytes
0x14002121b  mov     r13d, r12d
0x14002121e  call    cs:__imp_ExAllocatePoolWithTag
0x140021225  nop     dword ptr [rax+rax+00h]
0x14002122a  mov     rbx, rax
0x14002122d  test    rax, rax
0x140021230  jnz     short loc_140021239
0x140021232  mov     eax, 0C000009Ah
0x140021237  jmp     short loc_140021299
0x140021239  mov     r8, r13; Size
0x14002123c  xor     edx, edx; Val
0x14002123e  mov     rcx, rbx; void *
0x140021241  call    memset
0x140021246  mov     rdx, [r15]; Src
0x140021249  mov     r8, rsi; Size
0x14002124c  mov     rcx, rbx; void *
0x14002124f  call    memmove
0x140021254  xor     edx, edx; Tag
0x140021256  mov     [rbx+2], r12w
0x14002125b  mov     rcx, rdi; P
0x14002125e  call    cs:__imp_ExFreePoolWithTag
0x140021265  nop     dword ptr [rax+rax+00h]
0x14002126a  mov     [r15], rbx
0x14002126d  jmp     short loc_140021272
0x14002126f  mov     rbx, rdi
0x140021272  mov     r9, [rsp+68h+Sid]; Sid
0x14002127a  mov     edx, 2; AceRevision
0x14002127f  mov     r8d, [rsp+68h+AccessMask]; AccessMask
0x140021287  mov     rcx, rbx; Acl
0x14002128a  mov     [r14], ebp
0x14002128d  call    cs:__imp_RtlAddAccessAllowedAce
0x140021294  nop     dword ptr [rax+rax+00h]
0x140021299  add     rsp, 28h
0x14002129d  pop     r15
0x14002129f  pop     r14
0x1400212a1  pop     r13
0x1400212a3  pop     r12
0x1400212a5  pop     rdi
0x1400212a6  pop     rsi
0x1400212a7  pop     rbp
0x1400212a8  pop     rbx
0x1400212a9  retn
```
