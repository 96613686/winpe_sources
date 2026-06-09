# SepSddlAddAceToAcl

- ea: `0x1400205f0`
- end: `0x1400206db`
- name: `SepSddlAddAceToAcl`
- size: `235`
- prototype: `__int64 __fastcall(int, int, int, int, ACCESS_MASK AccessMask, int, PSID Sid)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x1400207c8`

## callees

- `0x14000fa40`
- `0x14000fd40`
- `0x1400205f0`

## import_xrefs

- `ntoskrnl!RtlLengthSid` at `0x140020614`
- `ntoskrnl!RtlLengthSid` at `0x140020614`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x1400206bd`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x1400206bd`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002068e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002068e`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14002064e`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14002064e`

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
0x1400205f0  push    rbx
0x1400205f2  push    rbp
0x1400205f3  push    rsi
0x1400205f4  push    rdi
0x1400205f5  push    r12
0x1400205f7  push    r13
0x1400205f9  push    r14
0x1400205fb  push    r15
0x1400205fd  sub     rsp, 28h
0x140020601  mov     rdi, [rcx]
0x140020604  mov     r15, rcx
0x140020607  mov     rcx, [rsp+68h+Sid]; Sid
0x14002060f  mov     r14, rdx
0x140020612  mov     esi, [rdx]
0x140020614  call    cs:__imp_RtlLengthSid
0x14002061b  nop     dword ptr [rax+rax+00h]
0x140020620  lea     r8d, [rax+8]
0x140020624  movzx   eax, word ptr [rdi+2]
0x140020628  lea     ebp, [r8+rsi]
0x14002062c  cmp     ebp, eax
0x14002062e  jbe     short loc_14002069F
0x140020630  imul    r8d, [rsp+68h+arg_28]
0x140020639  mov     ecx, 1; PoolType
0x14002063e  lea     r12d, [r8+rsi]
0x140020642  mov     r8d, 6C416553h; Tag
0x140020648  mov     edx, r12d; NumberOfBytes
0x14002064b  mov     r13d, r12d
0x14002064e  call    cs:__imp_ExAllocatePoolWithTag
0x140020655  nop     dword ptr [rax+rax+00h]
0x14002065a  mov     rbx, rax
0x14002065d  test    rax, rax
0x140020660  jnz     short loc_140020669
0x140020662  mov     eax, 0C000009Ah
0x140020667  jmp     short loc_1400206C9
0x140020669  mov     r8, r13; Size
0x14002066c  xor     edx, edx; Val
0x14002066e  mov     rcx, rbx; void *
0x140020671  call    memset
0x140020676  mov     rdx, [r15]; Src
0x140020679  mov     r8, rsi; Size
0x14002067c  mov     rcx, rbx; void *
0x14002067f  call    memmove
0x140020684  xor     edx, edx; Tag
0x140020686  mov     [rbx+2], r12w
0x14002068b  mov     rcx, rdi; P
0x14002068e  call    cs:__imp_ExFreePoolWithTag
0x140020695  nop     dword ptr [rax+rax+00h]
0x14002069a  mov     [r15], rbx
0x14002069d  jmp     short loc_1400206A2
0x14002069f  mov     rbx, rdi
0x1400206a2  mov     r9, [rsp+68h+Sid]; Sid
0x1400206aa  mov     edx, 2; AceRevision
0x1400206af  mov     r8d, [rsp+68h+AccessMask]; AccessMask
0x1400206b7  mov     rcx, rbx; Acl
0x1400206ba  mov     [r14], ebp
0x1400206bd  call    cs:__imp_RtlAddAccessAllowedAce
0x1400206c4  nop     dword ptr [rax+rax+00h]
0x1400206c9  add     rsp, 28h
0x1400206cd  pop     r15
0x1400206cf  pop     r14
0x1400206d1  pop     r13
0x1400206d3  pop     r12
0x1400206d5  pop     rdi
0x1400206d6  pop     rsi
0x1400206d7  pop     rbp
0x1400206d8  pop     rbx
0x1400206d9  retn
```
