# _RNvXCs3PyRTeGQ7Na_12fallible_vecINtNtCsexo9QDNEsji_5alloc3vec3VeclINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EEINtB2_11FallibleVeclB12_E21try_extend_from_sliceCsdcpJtfrLhSH_7rgncore

- ea: `0x1400161a0`
- end: `0x1400162bd`
- name: `_RNvXCs3PyRTeGQ7Na_12fallible_vecINtNtCsexo9QDNEsji_5alloc3vec3VeclINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EEINtB2_11FallibleVeclB12_E21try_extend_from_sliceCsdcpJtfrLhSH_7rgncore`
- size: `285`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14000cc10`

## callees

- `0x1400161a0`
- `0x140017a10`
- `0x140017b00`
- `0x1400193b0`

## pseudocode

```c
unsigned __int64 __fastcall RNvXCs3PyRTeGQ7Na_12fallible_vecINtNtCsexo9QDNEsji_5alloc3vec3VeclINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EEINtB2_11FallibleVeclB12_E21try_extend_from_sliceCsdcpJtfrLhSH_7rgncore(
        unsigned __int64 *a1,
        const void *a2,
        unsigned __int64 a3)
{
  __int64 v3; // rax
  unsigned __int64 v4; // rdi
  unsigned __int64 result; // rax
  unsigned __int64 *v6; // rbx
  unsigned __int64 v7; // rcx
  unsigned __int64 v8; // rsi
  const void *v9; // r14
  unsigned __int64 v10; // r15
  unsigned __int64 v11; // rdx
  unsigned __int64 v12; // rsi
  __int64 v13; // [rsp+0h] [rbp-78h] BYREF
  __int64 v14; // [rsp+30h] [rbp-48h] BYREF
  unsigned __int64 v15; // [rsp+38h] [rbp-40h]
  __int64 v16; // [rsp+48h] [rbp-30h]

  v3 = *a1;
  v4 = a1[2];
  if ( a3 <= *a1 - v4 )
  {
    if ( !a3 )
    {
LABEL_7:
      a1[2] = v4;
      result = 0x8000000000000001uLL;
      goto LABEL_8;
    }
    v6 = a1;
    v7 = a1[1];
LABEL_6:
    v8 = a3;
    memmove((void *)(v7 + 4 * v4), a2, 4 * a3);
    v4 += ((4 * v8 - 4) >> 2) + 1;
    a1 = v6;
    goto LABEL_7;
  }
  if ( __CFADD__(a3, v4) )
  {
    result = 0;
    goto LABEL_8;
  }
  v9 = a2;
  v10 = a3;
  v11 = 2 * v3;
  if ( a3 + v4 > 2 * v3 )
    v11 = a3 + v4;
  v12 = 4;
  if ( v11 >= 5 )
    v12 = v11;
  v6 = a1;
  RNvMs4_NtCsexo9QDNEsji_5alloc7raw_vecINtB5_11RawVecInnerINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EE11finish_growCsdcpJtfrLhSH_7rgncore_llvm_18110786352924170244(
    &v14,
    v3,
    (const void *)a1[1],
    v12,
    4u,
    4u);
  if ( (_DWORD)v14 != 1 )
  {
    v7 = v15;
    v6[1] = v15;
    *v6 = v12;
    a3 = v10;
    a2 = v9;
    goto LABEL_6;
  }
  result = v15;
LABEL_8:
  if ( _security_cookie != ((unsigned __int64)&v13 ^ v16) )
    JUMPOUT(0x1400162BCLL);
  return result;
}

```

## disassembly

```asm
0x1400161a0  push    r15
0x1400161a2  push    r14
0x1400161a4  push    rsi
0x1400161a5  push    rdi
0x1400161a6  push    rbx
0x1400161a7  sub     rsp, 50h
0x1400161ab  mov     rax, cs:__security_cookie
0x1400161b2  xor     rax, rsp
0x1400161b5  mov     [rsp+78h+var_30], rax
0x1400161ba  mov     rax, [rcx]
0x1400161bd  mov     rdi, [rcx+10h]
0x1400161c1  mov     r9, rax
0x1400161c4  sub     r9, rdi
0x1400161c7  cmp     r8, r9
0x1400161ca  jbe     short loc_1400161D8
0x1400161cc  mov     r9, rdi
0x1400161cf  add     r9, r8
0x1400161d2  jnb     short loc_14001623E
0x1400161d4  xor     eax, eax
0x1400161d6  jmp     short loc_14001621E
0x1400161d8  test    r8, r8
0x1400161db  jz      short loc_140016210
0x1400161dd  mov     rbx, rcx
0x1400161e0  mov     rcx, [rcx+8]
0x1400161e4  lea     rax, ds:0[r8*4]
0x1400161ec  lea     rcx, [rcx+rdi*4]; void *
0x1400161f0  mov     rsi, r8
0x1400161f3  mov     r8, rax; Size
0x1400161f6  call    memmove
0x1400161fb  lea     rax, ds:0FFFFFFFFFFFFFFFCh[rsi*4]
0x140016203  shr     rax, 2
0x140016207  add     rdi, rax
0x14001620a  inc     rdi
0x14001620d  mov     rcx, rbx
0x140016210  mov     [rcx+10h], rdi
0x140016214  mov     rax, 8000000000000001h
0x14001621e  mov     rcx, [rsp+78h+var_30]
0x140016223  xor     rcx, rsp
0x140016226  mov     r8, cs:__security_cookie
0x14001622d  cmp     r8, rcx
0x140016230  jnz     short loc_1400162AF
0x140016232  add     rsp, 50h
0x140016236  pop     rbx
0x140016237  pop     rdi
0x140016238  pop     rsi
0x140016239  pop     r14
0x14001623b  pop     r15
0x14001623d  retn
0x14001623e  mov     r14, rdx
0x140016241  mov     r15, r8
0x140016244  lea     rdx, [rax+rax]
0x140016248  cmp     r9, rdx
0x14001624b  cmova   rdx, r9
0x14001624f  cmp     rdx, 5
0x140016253  mov     esi, 4
0x140016258  cmovnb  rsi, rdx
0x14001625c  mov     rbx, rcx
0x14001625f  mov     r8, [rcx+8]
0x140016263  mov     [rsp+78h+var_50], 4
0x14001626c  mov     [rsp+78h+var_58], 4
0x140016275  lea     rcx, [rsp+78h+var_48]
0x14001627a  mov     rdx, rax
0x14001627d  mov     r9, rsi
0x140016280  call    _RNvMs4_NtCsexo9QDNEsji_5alloc7raw_vecINtB5_11RawVecInnerINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EE11finish_growCsdcpJtfrLhSH_7rgncore_llvm_18110786352924170244
0x140016285  cmp     dword ptr [rsp+78h+var_48], 1
0x14001628a  jnz     short loc_140016298
0x14001628c  mov     rax, [rsp+78h+var_40]
0x140016291  mov     rdx, [rsp+78h+var_38]
0x140016296  jmp     short loc_14001621E
0x140016298  mov     rcx, [rsp+78h+var_40]
0x14001629d  mov     [rbx+8], rcx
0x1400162a1  mov     [rbx], rsi
0x1400162a4  mov     r8, r15
0x1400162a7  mov     rdx, r14
0x1400162aa  jmp     loc_1400161E4
0x1400162af  mov     rcx, [rsp+78h+var_30]
0x1400162b4  xor     rcx, rsp; StackCookie
0x1400162b7  call    __security_check_cookie
```
