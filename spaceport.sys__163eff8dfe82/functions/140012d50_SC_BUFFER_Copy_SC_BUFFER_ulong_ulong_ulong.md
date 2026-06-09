# SC_BUFFER::Copy(SC_BUFFER *,ulong,ulong,ulong)

- ea: `0x140012d50`
- end: `0x140012e9e`
- name: `?Copy@SC_BUFFER@@QEAAJPEAV1@KKK@Z`
- size: `334`
- prototype: `__int64 __fastcall(SC_BUFFER *__hidden this, struct SC_BUFFER *, unsigned int, unsigned int, size_t Size)`
- caller_count: `6`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x140007010`
- `0x140012880`
- `0x1400129d0`
- `0x1400242a0`
- `0x14004a990`
- `0x14004e9b0`

## callees

- `0x140012d50`
- `0x140068300`

## import_xrefs

- `ntoskrnl!MmMapMdl` at `0x140012dbc`
- `ntoskrnl!MmMapMdl` at `0x140012dbc`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140012def`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140012e32`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140012e83`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140012def`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140012e32`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140012e83`

## pseudocode

```c
__int64 __fastcall SC_BUFFER::Copy(
        SC_BUFFER *this,
        struct SC_BUFFER *a2,
        unsigned int a3,
        unsigned int a4,
        size_t Size)
{
  __int64 v5; // rsi
  bool v6; // zf
  __int64 v7; // rbp
  __int64 v10; // rcx
  PVOID v11; // rax
  unsigned int v12; // r14d
  __int64 v13; // rcx
  __int64 result; // rax
  __int64 v15; // rcx
  char *v16; // rdi
  __int64 v17; // rcx
  char *v18; // rax
  __int128 v19; // [rsp+30h] [rbp-48h] BYREF
  __int64 v20; // [rsp+40h] [rbp-38h]

  v5 = a4;
  v6 = *(_DWORD *)this == 3;
  v7 = a3;
  v20 = 0;
  v19 = 0;
  if ( !v6 )
  {
    v12 = Size;
LABEL_7:
    v15 = *((_QWORD *)a2 + 1);
    if ( (*(_BYTE *)(v15 + 10) & 5) != 0 )
      v16 = *(char **)(v15 + 24);
    else
      v16 = (char *)MmMapLockedPagesSpecifyCache((PMDL)v15, 0, MmCached, 0, 0, 0x40000020u);
    if ( !v16 )
      return 3221225626LL;
    v17 = *((_QWORD *)this + 1);
    if ( (*(_BYTE *)(v17 + 10) & 5) != 0 )
      v18 = *(char **)(v17 + 24);
    else
      v18 = (char *)MmMapLockedPagesSpecifyCache((PMDL)v17, 0, MmCached, 0, 0, 0x40000020u);
    memmove(&v18[v5], &v16[v7], v12);
    return 0;
  }
  v10 = *((_QWORD *)this + 1);
  if ( (*(_BYTE *)(v10 + 10) & 5) != 0 )
    v11 = *(PVOID *)(v10 + 24);
  else
    v11 = MmMapLockedPagesSpecifyCache((PMDL)v10, 0, MmCached, 0, 0, 0x40000020u);
  v12 = Size;
  v13 = *((_QWORD *)a2 + 1);
  LODWORD(v20) = Size;
  *(_QWORD *)&v19 = v11;
  *((_QWORD *)&v19 + 1) = __PAIR64__(v5, v7);
  result = MmMapMdl(v13, 4, SC_BUFFER::CopyCallback, &v19);
  if ( (int)result < 0 )
    goto LABEL_7;
  return result;
}

```

## disassembly

```asm
0x140012d50  push    rbx
0x140012d52  push    rbp
0x140012d53  push    rsi
0x140012d54  push    rdi
0x140012d55  push    r14
0x140012d57  sub     rsp, 50h
0x140012d5b  xor     eax, eax
0x140012d5d  mov     esi, r9d
0x140012d60  cmp     dword ptr [rcx], 3
0x140012d63  xorps   xmm0, xmm0
0x140012d66  mov     ebp, r8d
0x140012d69  mov     rdi, rdx
0x140012d6c  mov     rbx, rcx
0x140012d6f  mov     [rsp+78h+var_38], rax
0x140012d74  movups  [rsp+78h+var_48], xmm0
0x140012d79  jnz     loc_140012E91
0x140012d7f  mov     rcx, [rcx+8]; MemoryDescriptorList
0x140012d83  test    byte ptr [rcx+0Ah], 5
0x140012d87  jz      short loc_140012DD8
0x140012d89  mov     rax, [rcx+18h]
0x140012d8d  mov     r14d, dword ptr [rsp+78h+Size]
0x140012d95  lea     r9, [rsp+78h+var_48]
0x140012d9a  mov     rcx, [rdi+8]
0x140012d9e  lea     r8, ?CopyCallback@SC_BUFFER@@SAXPEAXPEAE@Z; SC_BUFFER::CopyCallback(void *,uchar *)
0x140012da5  mov     edx, 4
0x140012daa  mov     dword ptr [rsp+78h+var_38], r14d
0x140012daf  mov     qword ptr [rsp+78h+var_48], rax
0x140012db4  mov     dword ptr [rsp+78h+var_48+8], ebp
0x140012db8  mov     dword ptr [rsp+78h+var_48+0Ch], esi
0x140012dbc  call    cs:__imp_MmMapMdl
0x140012dc3  nop     dword ptr [rax+rax+00h]
0x140012dc8  test    eax, eax
0x140012dca  js      short loc_140012DFD
0x140012dcc  add     rsp, 50h
0x140012dd0  pop     r14
0x140012dd2  pop     rdi
0x140012dd3  pop     rsi
0x140012dd4  pop     rbp
0x140012dd5  pop     rbx
0x140012dd6  retn
0x140012dd8  mov     [rsp+78h+Priority], 40000020h; Priority
0x140012de0  xor     r9d, r9d; RequestedAddress
0x140012de3  xor     edx, edx; AccessMode
0x140012de5  mov     [rsp+78h+BugCheckOnFailure], eax; BugCheckOnFailure
0x140012de9  mov     r8d, 1; CacheType
0x140012def  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x140012df6  nop     dword ptr [rax+rax+00h]
0x140012dfb  jmp     short loc_140012D8D
0x140012dfd  mov     rcx, [rdi+8]; MemoryDescriptorList
0x140012e01  test    byte ptr [rcx+0Ah], 5
0x140012e05  jz      short loc_140012E17
0x140012e07  mov     rdi, [rcx+18h]
0x140012e0b  test    rdi, rdi
0x140012e0e  jnz     short loc_140012E43
0x140012e10  mov     eax, 0C000009Ah
0x140012e15  jmp     short loc_140012DCC
0x140012e17  mov     [rsp+78h+Priority], 40000020h; Priority
0x140012e1f  xor     r9d, r9d; RequestedAddress
0x140012e22  xor     edx, edx; AccessMode
0x140012e24  mov     [rsp+78h+BugCheckOnFailure], 0; BugCheckOnFailure
0x140012e2c  mov     r8d, 1; CacheType
0x140012e32  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x140012e39  nop     dword ptr [rax+rax+00h]
0x140012e3e  mov     rdi, rax
0x140012e41  jmp     short loc_140012E0B
0x140012e43  mov     rcx, [rbx+8]; MemoryDescriptorList
0x140012e47  test    byte ptr [rcx+0Ah], 5
0x140012e4b  jz      short loc_140012E68
0x140012e4d  mov     rax, [rcx+18h]
0x140012e51  mov     r8d, r14d; Size
0x140012e54  lea     rdx, [rdi+rbp]; Src
0x140012e58  lea     rcx, [rax+rsi]; void *
0x140012e5c  call    memmove
0x140012e61  xor     eax, eax
0x140012e63  jmp     loc_140012DCC
0x140012e68  mov     [rsp+78h+Priority], 40000020h; Priority
0x140012e70  xor     r9d, r9d; RequestedAddress
0x140012e73  xor     edx, edx; AccessMode
0x140012e75  mov     [rsp+78h+BugCheckOnFailure], 0; BugCheckOnFailure
0x140012e7d  mov     r8d, 1; CacheType
0x140012e83  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x140012e8a  nop     dword ptr [rax+rax+00h]
0x140012e8f  jmp     short loc_140012E51
0x140012e91  mov     r14d, dword ptr [rsp+78h+Size]
0x140012e99  jmp     loc_140012DFD
```
