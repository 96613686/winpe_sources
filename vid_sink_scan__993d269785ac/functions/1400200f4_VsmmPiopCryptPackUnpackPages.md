# VsmmPiopCryptPackUnpackPages

- ea: `0x1400200f4`
- end: `0x140020261`
- name: `VsmmPiopCryptPackUnpackPages`
- size: `365`
- prototype: `__int64 __fastcall(__int64, __int64, int, unsigned __int64, int)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x14001fbd8`
- `0x14001ff90`
- `0x1400202e0`

## callees

- `0x1400200f4`
- `0x140021650`
- `0x1400281f4`
- `0x1400edc70`

## import_xrefs

- `ntoskrnl!MmUnmapLockedPages` at `0x140020236`
- `ntoskrnl!MmUnmapLockedPages` at `0x140020236`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140020161`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140020161`

## pseudocode

```c
__int64 __fastcall VsmmPiopCryptPackUnpackPages(__int64 a1, __int64 a2, int a3, unsigned __int64 a4, int a5)
{
  __int64 v5; // r14
  int v8; // ebx
  int v9; // ebx
  struct _MDL *v10; // rbp
  PVOID v11; // rsi
  int v12; // edx
  __int64 v13; // r15
  unsigned __int64 i; // rdi
  __int64 v15; // r9
  __int64 v17; // [rsp+50h] [rbp-58h] BYREF
  __int128 v18; // [rsp+58h] [rbp-50h] BYREF

  v5 = *(_QWORD *)(a2 + 8);
  v18 = 0;
  v17 = 0;
  v8 = a2;
  if ( (*(_BYTE *)(v5 + 40) & 2) != 0 )
  {
    v10 = *(struct _MDL **)(a1 + 88);
    v11 = MmMapLockedPagesSpecifyCache(v10, 0, MmCached, 0, 0, 0x40000010u);
    if ( v11 )
    {
      v9 = VsmmGpaRangeLookupGpaByMbp(v5, v8, a3, 1, 4, (__int64)&v17, 0);
      if ( v9 >= 0 )
      {
        v13 = v17;
        for ( i = 0; i < a4; ++i )
        {
          v18 = v13 + i;
          v15 = *(_QWORD *)(v5 + 8568);
          LODWORD(v17) = 4096;
          v9 = VsmmCryptPackUnpack(
                 v5,
                 v12,
                 (unsigned int)&v18,
                 v15,
                 (__int64)v11 + 4096 * i,
                 (__int64)&v17,
                 (__int64)v11 + 4096 * i,
                 4096,
                 a5 != 0);
          if ( v9 < 0 )
            goto LABEL_11;
        }
        v9 = 0;
      }
LABEL_11:
      MmUnmapLockedPages(v11, v10);
    }
    else
    {
      return (unsigned int)-1073741670;
    }
  }
  else
  {
    return (unsigned int)-1073741790;
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1400200f4  push    rbx
0x1400200f6  push    rbp
0x1400200f7  push    rsi
0x1400200f8  push    rdi
0x1400200f9  push    r12
0x1400200fb  push    r14
0x1400200fd  push    r15
0x1400200ff  sub     rsp, 70h
0x140020103  mov     rax, cs:__security_cookie
0x14002010a  xor     rax, rsp
0x14002010d  mov     [rsp+0A8h+var_40], rax
0x140020112  mov     r14, [rdx+8]
0x140020116  xorps   xmm0, xmm0
0x140020119  movups  [rsp+0A8h+var_50], xmm0
0x14002011e  mov     r12, r9
0x140020121  mov     [rsp+0A8h+var_58], 0
0x14002012a  mov     rdi, r8
0x14002012d  mov     rbx, rdx
0x140020130  test    byte ptr [r14+28h], 2
0x140020135  jnz     short loc_140020141
0x140020137  mov     ebx, 0C0000022h
0x14002013c  jmp     loc_140020242
0x140020141  mov     rbp, [rcx+58h]
0x140020145  xor     r9d, r9d; RequestedAddress
0x140020148  mov     [rsp+0A8h+Priority], 40000010h; Priority
0x140020150  xor     edx, edx; AccessMode
0x140020152  mov     rcx, rbp; MemoryDescriptorList
0x140020155  mov     [rsp+0A8h+BugCheckOnFailure], 0; BugCheckOnFailure
0x14002015d  lea     r8d, [r9+1]; CacheType
0x140020161  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x140020168  nop     dword ptr [rax+rax+00h]
0x14002016d  mov     rsi, rax
0x140020170  test    rax, rax
0x140020173  jnz     short loc_14002017F
0x140020175  mov     ebx, 0C000009Ah
0x14002017a  jmp     loc_140020242
0x14002017f  lea     rax, [rsp+0A8h+var_58]
0x140020184  mov     [rsp+0A8h+var_78], 0
0x14002018d  mov     qword ptr [rsp+0A8h+Priority], rax
0x140020192  mov     r9d, 1
0x140020198  mov     r8, rdi
0x14002019b  mov     [rsp+0A8h+BugCheckOnFailure], 4
0x1400201a3  mov     rdx, rbx
0x1400201a6  mov     rcx, r14
0x1400201a9  call    VsmmGpaRangeLookupGpaByMbp
0x1400201ae  mov     ebx, eax
0x1400201b0  test    eax, eax
0x1400201b2  js      short loc_140020230
0x1400201b4  mov     r15, [rsp+0A8h+var_58]
0x1400201b9  xor     edi, edi
0x1400201bb  cmp     rdi, r12
0x1400201be  jnb     short loc_14002022E
0x1400201c0  lea     rax, [r15+rdi]
0x1400201c4  mov     qword ptr [rsp+0A8h+var_50+8], 0
0x1400201cd  mov     qword ptr [rsp+0A8h+var_50], rax
0x1400201d2  lea     r8, [rsp+0A8h+var_50]
0x1400201d7  mov     r9, [r14+2178h]
0x1400201de  mov     rcx, rdi
0x1400201e1  shl     rcx, 0Ch
0x1400201e5  add     rcx, rsi
0x1400201e8  mov     dword ptr [rsp+0A8h+var_58], 1000h
0x1400201f0  cmp     [rsp+0A8h+arg_20], 0
0x1400201f8  setnz   al
0x1400201fb  mov     [rsp+0A8h+var_68], al
0x1400201ff  lea     rax, [rsp+0A8h+var_58]
0x140020204  mov     [rsp+0A8h+var_70], 1000h
0x14002020c  mov     [rsp+0A8h+var_78], rcx
0x140020211  mov     qword ptr [rsp+0A8h+Priority], rax
0x140020216  mov     qword ptr [rsp+0A8h+BugCheckOnFailure], rcx
0x14002021b  mov     rcx, r14
0x14002021e  call    VsmmCryptPackUnpack
0x140020223  mov     ebx, eax
0x140020225  test    eax, eax
0x140020227  js      short loc_140020230
0x140020229  inc     rdi
0x14002022c  jmp     short loc_1400201BB
0x14002022e  xor     ebx, ebx
0x140020230  mov     rdx, rbp; MemoryDescriptorList
0x140020233  mov     rcx, rsi; BaseAddress
0x140020236  call    cs:__imp_MmUnmapLockedPages
0x14002023d  nop     dword ptr [rax+rax+00h]
0x140020242  mov     eax, ebx
0x140020244  mov     rcx, [rsp+0A8h+var_40]
0x140020249  xor     rcx, rsp; StackCookie
0x14002024c  call    __security_check_cookie
0x140020251  add     rsp, 70h
0x140020255  pop     r15
0x140020257  pop     r14
0x140020259  pop     r12
0x14002025b  pop     rdi
0x14002025c  pop     rsi
0x14002025d  pop     rbp
0x14002025e  pop     rbx
0x14002025f  retn
```
