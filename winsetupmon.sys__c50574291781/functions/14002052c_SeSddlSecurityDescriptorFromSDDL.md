# SeSddlSecurityDescriptorFromSDDL

- ea: `0x14002052c`
- end: `0x1400205e8`
- name: `SeSddlSecurityDescriptorFromSDDL`
- size: `188`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400202a0`

## callees

- `0x14000fa40`
- `0x14000fd40`
- `0x14002052c`
- `0x140020d14`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400205ce`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400205ce`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140020571`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140020571`

## pseudocode

```c
__int64 __fastcall SeSddlSecurityDescriptorFromSDDL(unsigned __int16 *a1, __int64 a2, _QWORD *a3)
{
  unsigned __int64 v3; // rdx
  SIZE_T v6; // r9
  __int64 v7; // rcx
  unsigned __int64 v8; // rdx
  PVOID PoolWithTag; // rax
  void *v11; // r14
  ULONG v12; // edx
  unsigned int v13; // ebx

  v3 = *a1;
  v6 = v3 + 2;
  if ( a1[1] == v3 + 2 )
  {
    v7 = *((_QWORD *)a1 + 1);
    v8 = v3 >> 1;
    if ( !*(_WORD *)(v7 + 2 * v8) )
      return SepSddlSecurityDescriptorFromSDDLString(v7, v8, (__int64)a3);
  }
  PoolWithTag = ExAllocatePoolWithTag(PagedPool, v6, 0x73546553u);
  v11 = PoolWithTag;
  if ( PoolWithTag )
  {
    memset(PoolWithTag, 0, *a1 + 2LL);
    memmove(v11, *((const void **)a1 + 1), *a1);
    *((_WORD *)v11 + ((unsigned __int64)*a1 >> 1)) = 0;
    v13 = SepSddlSecurityDescriptorFromSDDLString((__int64)v11, v12, (__int64)a3);
    ExFreePoolWithTag(v11, 0);
    return v13;
  }
  else
  {
    *a3 = 0;
    return 3221225626LL;
  }
}

```

## disassembly

```asm
0x14002052c  push    rbx
0x14002052e  push    rbp
0x14002052f  push    rsi
0x140020530  push    rdi
0x140020531  push    r14
0x140020533  sub     rsp, 20h
0x140020537  movzx   edx, word ptr [rcx]
0x14002053a  xor     ebp, ebp
0x14002053c  movzx   eax, word ptr [rcx+2]
0x140020540  mov     rsi, r8
0x140020543  mov     rdi, rcx
0x140020546  lea     r9, [rdx+2]
0x14002054a  cmp     rax, r9
0x14002054d  jnz     short loc_140020563
0x14002054f  mov     rcx, [rcx+8]
0x140020553  shr     rdx, 1
0x140020556  cmp     [rcx+rdx*2], bp
0x14002055a  jnz     short loc_140020563
0x14002055c  call    SepSddlSecurityDescriptorFromSDDLString
0x140020561  jmp     short loc_1400205DC
0x140020563  mov     r8d, 73546553h; Tag
0x140020569  mov     rdx, r9; NumberOfBytes
0x14002056c  mov     ecx, 1; PoolType
0x140020571  call    cs:__imp_ExAllocatePoolWithTag
0x140020578  nop     dword ptr [rax+rax+00h]
0x14002057d  mov     r14, rax
0x140020580  test    rax, rax
0x140020583  jnz     short loc_14002058F
0x140020585  mov     [rsi], rbp
0x140020588  mov     eax, 0C000009Ah
0x14002058d  jmp     short loc_1400205DC
0x14002058f  movzx   r8d, word ptr [rdi]
0x140020593  xor     edx, edx; Val
0x140020595  add     r8, 2; Size
0x140020599  mov     rcx, r14; void *
0x14002059c  call    memset
0x1400205a1  movzx   r8d, word ptr [rdi]; Size
0x1400205a5  mov     rcx, r14; void *
0x1400205a8  mov     rdx, [rdi+8]; Src
0x1400205ac  call    memmove
0x1400205b1  movzx   ecx, word ptr [rdi]
0x1400205b4  mov     r8, rsi
0x1400205b7  shr     rcx, 1
0x1400205ba  mov     [r14+rcx*2], bp
0x1400205bf  mov     rcx, r14
0x1400205c2  call    SepSddlSecurityDescriptorFromSDDLString
0x1400205c7  xor     edx, edx; Tag
0x1400205c9  mov     rcx, r14; P
0x1400205cc  mov     ebx, eax
0x1400205ce  call    cs:__imp_ExFreePoolWithTag
0x1400205d5  nop     dword ptr [rax+rax+00h]
0x1400205da  mov     eax, ebx
0x1400205dc  add     rsp, 20h
0x1400205e0  pop     r14
0x1400205e2  pop     rdi
0x1400205e3  pop     rsi
0x1400205e4  pop     rbp
0x1400205e5  pop     rbx
0x1400205e6  retn
```
