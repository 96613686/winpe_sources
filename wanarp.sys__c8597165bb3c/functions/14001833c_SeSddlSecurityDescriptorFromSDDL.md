# SeSddlSecurityDescriptorFromSDDL

- ea: `0x14001833c`
- end: `0x1400183f8`
- name: `SeSddlSecurityDescriptorFromSDDL`
- size: `188`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400180b0`

## callees

- `0x1400051c0`
- `0x1400054c0`
- `0x14001833c`
- `0x140018b14`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400183de`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400183de`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140018381`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140018381`

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
0x14001833c  push    rbx
0x14001833e  push    rbp
0x14001833f  push    rsi
0x140018340  push    rdi
0x140018341  push    r14
0x140018343  sub     rsp, 20h
0x140018347  movzx   edx, word ptr [rcx]
0x14001834a  xor     ebp, ebp
0x14001834c  movzx   eax, word ptr [rcx+2]
0x140018350  mov     rsi, r8
0x140018353  mov     rdi, rcx
0x140018356  lea     r9, [rdx+2]
0x14001835a  cmp     rax, r9
0x14001835d  jnz     short loc_140018373
0x14001835f  mov     rcx, [rcx+8]
0x140018363  shr     rdx, 1
0x140018366  cmp     [rcx+rdx*2], bp
0x14001836a  jnz     short loc_140018373
0x14001836c  call    SepSddlSecurityDescriptorFromSDDLString
0x140018371  jmp     short loc_1400183EC
0x140018373  mov     r8d, 73546553h; Tag
0x140018379  mov     rdx, r9; NumberOfBytes
0x14001837c  mov     ecx, 1; PoolType
0x140018381  call    cs:__imp_ExAllocatePoolWithTag
0x140018388  nop     dword ptr [rax+rax+00h]
0x14001838d  mov     r14, rax
0x140018390  test    rax, rax
0x140018393  jnz     short loc_14001839F
0x140018395  mov     [rsi], rbp
0x140018398  mov     eax, 0C000009Ah
0x14001839d  jmp     short loc_1400183EC
0x14001839f  movzx   r8d, word ptr [rdi]
0x1400183a3  xor     edx, edx; Val
0x1400183a5  add     r8, 2; Size
0x1400183a9  mov     rcx, r14; void *
0x1400183ac  call    memset
0x1400183b1  movzx   r8d, word ptr [rdi]; Size
0x1400183b5  mov     rcx, r14; void *
0x1400183b8  mov     rdx, [rdi+8]; Src
0x1400183bc  call    memmove
0x1400183c1  movzx   ecx, word ptr [rdi]
0x1400183c4  mov     r8, rsi
0x1400183c7  shr     rcx, 1
0x1400183ca  mov     [r14+rcx*2], bp
0x1400183cf  mov     rcx, r14
0x1400183d2  call    SepSddlSecurityDescriptorFromSDDLString
0x1400183d7  xor     edx, edx; Tag
0x1400183d9  mov     rcx, r14; P
0x1400183dc  mov     ebx, eax
0x1400183de  call    cs:__imp_ExFreePoolWithTag
0x1400183e5  nop     dword ptr [rax+rax+00h]
0x1400183ea  mov     eax, ebx
0x1400183ec  add     rsp, 20h
0x1400183f0  pop     r14
0x1400183f2  pop     rdi
0x1400183f3  pop     rsi
0x1400183f4  pop     rbp
0x1400183f5  pop     rbx
0x1400183f6  retn
```
