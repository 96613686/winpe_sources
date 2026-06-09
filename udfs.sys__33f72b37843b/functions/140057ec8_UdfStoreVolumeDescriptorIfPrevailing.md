# UdfStoreVolumeDescriptorIfPrevailing

- ea: `0x140057ec8`
- end: `0x140057f94`
- name: `UdfStoreVolumeDescriptorIfPrevailing`
- size: `204`
- prototype: `unsigned __int64 __fastcall(__int64, _DWORD **, unsigned int *, unsigned int *, unsigned int)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x140030034`
- `0x1400483a8`

## callees

- `0x14001bd80`
- `0x14001c080`
- `0x140057ec8`

## import_xrefs

- `ntoskrnl!ExAllocatePoolWithTag` at `0x140057f24`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140057f24`

## pseudocode

```c
unsigned __int64 __fastcall UdfStoreVolumeDescriptorIfPrevailing(
        __int64 a1,
        _DWORD **a2,
        unsigned int *a3,
        unsigned int *a4,
        unsigned int a5)
{
  _DWORD *v5; // rbx
  unsigned __int64 result; // rax
  SIZE_T v11; // rdi
  _DWORD *PoolWithTag; // rax

  v5 = *a2;
  if ( *a2 )
  {
    result = a3[4];
    if ( v5[4] >= (unsigned int)result )
      return result;
  }
  else
  {
    v11 = ((-*(_DWORD *)(a1 + 68) & (*(_DWORD *)(a1 + 68) + 511)) + 4095) & 0xFFFFF000;
    PoolWithTag = ExAllocatePoolWithTag((POOL_TYPE)1552, v11, 0x33666455u);
    v5 = PoolWithTag;
    if ( !ExPoolZeroingNativelySupported && PoolWithTag )
      memset(PoolWithTag, 0, v11);
    *a2 = v5;
  }
  result = (unsigned __int64)memmove(
                               v5,
                               a3,
                               ((-*(_DWORD *)(a1 + 68) & (*(_DWORD *)(a1 + 68) + 511)) + 4095) & 0xFFFFF000);
  if ( a4 )
  {
    result = a5;
    *a4 = a5;
  }
  return result;
}

```

## disassembly

```asm
0x140057ec8  push    rbx
0x140057eca  push    rbp
0x140057ecb  push    rsi
0x140057ecc  push    rdi
0x140057ecd  push    r13
0x140057ecf  push    r14
0x140057ed1  push    r15
0x140057ed3  sub     rsp, 20h
0x140057ed7  mov     rbx, [rdx]
0x140057eda  mov     rsi, r9
0x140057edd  mov     rbp, r8
0x140057ee0  mov     r14, rdx
0x140057ee3  mov     r15, rcx
0x140057ee6  mov     r13d, 0FFFFF000h
0x140057eec  test    rbx, rbx
0x140057eef  jz      short loc_140057F00
0x140057ef1  mov     eax, [r8+10h]
0x140057ef5  cmp     [rbx+10h], eax
0x140057ef8  jnb     loc_140057F84
0x140057efe  jmp     short loc_140057F51
0x140057f00  mov     ecx, [rcx+44h]
0x140057f03  mov     r8d, 33666455h; Tag
0x140057f09  lea     edi, [rcx+1FFh]
0x140057f0f  neg     ecx
0x140057f11  and     edi, ecx
0x140057f13  mov     ecx, 610h; PoolType
0x140057f18  add     edi, 0FFFh
0x140057f1e  and     rdi, r13
0x140057f21  mov     rdx, rdi; NumberOfBytes
0x140057f24  call    cs:__imp_ExAllocatePoolWithTag
0x140057f2b  nop     dword ptr [rax+rax+00h]
0x140057f30  cmp     cs:ExPoolZeroingNativelySupported, 0
0x140057f37  mov     rbx, rax
0x140057f3a  jnz     short loc_140057F4E
0x140057f3c  test    rax, rax
0x140057f3f  jz      short loc_140057F4E
0x140057f41  mov     r8, rdi; Size
0x140057f44  xor     edx, edx; Val
0x140057f46  mov     rcx, rax; void *
0x140057f49  call    memset
0x140057f4e  mov     [r14], rbx
0x140057f51  mov     edx, [r15+44h]
0x140057f55  mov     rcx, rbx; void *
0x140057f58  lea     r8d, [rdx+1FFh]
0x140057f5f  neg     edx
0x140057f61  and     r8d, edx
0x140057f64  mov     rdx, rbp; Src
0x140057f67  add     r8d, 0FFFh
0x140057f6e  and     r8, r13; Size
0x140057f71  call    memmove
0x140057f76  test    rsi, rsi
0x140057f79  jz      short loc_140057F84
0x140057f7b  mov     eax, [rsp+58h+arg_20]
0x140057f82  mov     [rsi], eax
0x140057f84  add     rsp, 20h
0x140057f88  pop     r15
0x140057f8a  pop     r14
0x140057f8c  pop     r13
0x140057f8e  pop     rdi
0x140057f8f  pop     rsi
0x140057f90  pop     rbp
0x140057f91  pop     rbx
0x140057f92  retn
```
