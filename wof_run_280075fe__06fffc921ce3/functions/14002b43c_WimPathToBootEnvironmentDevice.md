# WimPathToBootEnvironmentDevice

- ea: `0x14002b43c`
- end: `0x14002b6c7`
- name: `WimPathToBootEnvironmentDevice`
- size: `651`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: ``

## callers

- `0x14002ad28`
- `0x14002ba8c`

## callees

- `0x14000d3b8`
- `0x14000da0d`
- `0x14000ff9c`
- `0x1400116c0`
- `0x1400119c0`
- `0x14002b43c`
- `0x14002fc98`
- `0x140031500`

## import_xrefs

- `ntoskrnl!_wcsicmp` at `0x14002b4d5`
- `ntoskrnl!_wcsicmp` at `0x14002b4d5`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002b4f1`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002b507`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002b5b0`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002b691`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002b6a7`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002b4f1`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002b507`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002b5b0`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002b691`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002b6a7`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14002b532`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14002b5c9`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14002b532`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14002b5c9`

## pseudocode

```c
__int64 __fastcall WimPathToBootEnvironmentDevice(
        __int64 a1,
        const void **a2,
        const void **a3,
        _QWORD *a4,
        unsigned int *a5)
{
  unsigned int v9; // r15d
  __int64 PartitionVhdFilePathFromUnicodeString; // rax
  __int64 v11; // r8
  wchar_t *v12; // rdi
  __int64 v13; // rax
  __int64 v14; // r8
  wchar_t *v15; // rbx
  unsigned int v16; // r12d
  _DWORD *PoolWithTag; // rax
  _DWORD *v18; // r14
  int v19; // ebx
  PVOID v20; // rdi
  __int64 v21; // rax
  unsigned int v22; // ebp
  int v23; // eax
  _DWORD *v24; // rsi
  unsigned int *v25; // rax
  void *Src; // [rsp+78h] [rbp+10h] BYREF

  v9 = 0;
  PartitionVhdFilePathFromUnicodeString = BiGetPartitionVhdFilePathFromUnicodeString(a2);
  v12 = (wchar_t *)PartitionVhdFilePathFromUnicodeString;
  if ( PartitionVhdFilePathFromUnicodeString
    && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0xAu)
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_S(WPP_GLOBAL_Control->AttachedDevice, 43, v11, PartitionVhdFilePathFromUnicodeString);
  }
  v13 = BiGetPartitionVhdFilePathFromUnicodeString(a1);
  v15 = (wchar_t *)v13;
  if ( v13
    && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0xAu)
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_S(WPP_GLOBAL_Control->AttachedDevice, 44, v14, v13);
  }
  if ( v12 )
  {
    if ( v15 && !_wcsicmp(v12, v15) )
      v9 = 64;
    ExFreePoolWithTag(v12, 0);
  }
  if ( v15 )
    ExFreePoolWithTag(v15, 0);
  v16 = *(unsigned __int16 *)a2 + 48 + *(unsigned __int16 *)a3;
  PoolWithTag = ExAllocatePoolWithTag(PagedPool, v16, 0x66637077u);
  v18 = PoolWithTag;
  if ( PoolWithTag )
  {
    v20 = 0;
    memset(PoolWithTag, 0, v16);
    *v18 = 3;
    v21 = (unsigned int)*(unsigned __int16 *)a3 + 26;
    v18[5] = v21;
    *(_DWORD *)((char *)v18 + v21) = 2;
    memmove((char *)v18 + (unsigned int)v21 + 20, a2[1], *(unsigned __int16 *)a2);
    memmove(v18 + 6, a3[1], *(unsigned __int16 *)a3);
    v22 = 256;
    do
    {
      if ( v20 )
        ExFreePoolWithTag(v20, 0);
      v20 = ExAllocatePoolWithTag(PagedPool, v22, 0x66637077u);
      if ( !v20 )
      {
        v19 = -1073741801;
        goto LABEL_32;
      }
      Src = 0;
      v23 = BiConvertNtDeviceToBootEnvironment(v18, v16, v9, &Src);
      v24 = Src;
      v19 = v23;
      if ( v23 >= 0 )
      {
        if ( v22 >= *((_DWORD *)Src + 2) )
        {
          memmove(v20, Src, *((unsigned int *)Src + 2));
          v22 = v24[2];
          v19 = 0;
        }
        else
        {
          v22 = *((_DWORD *)Src + 2);
          v19 = -1073741789;
        }
      }
      if ( v24 )
        ExFreePoolWithTag_0(v24, 0x4B444342u);
    }
    while ( v19 == -1073741789 );
    if ( v19 >= 0 )
    {
      v25 = a5;
      *a4 = v20;
      v20 = 0;
      *v25 = v22;
      goto LABEL_35;
    }
LABEL_32:
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        45,
        WPP_8be5f4e5626c39736f1e2e11a2a58b62_Traceguids,
        (unsigned int)v19);
LABEL_35:
    ExFreePoolWithTag(v18, 0);
    if ( v20 )
      ExFreePoolWithTag(v20, 0);
  }
  else
  {
    return (unsigned int)-1073741801;
  }
  return (unsigned int)v19;
}

```

## disassembly

```asm
0x14002b43c  push    rbx
0x14002b43e  push    rbp
0x14002b43f  push    rsi
0x14002b440  push    rdi
0x14002b441  push    r12
0x14002b443  push    r13
0x14002b445  push    r14
0x14002b447  push    r15
0x14002b449  sub     rsp, 28h
0x14002b44d  mov     rbx, rcx
0x14002b450  mov     r13, r9
0x14002b453  mov     rcx, rdx
0x14002b456  mov     rbp, r8
0x14002b459  mov     rsi, rdx
0x14002b45c  xor     r15d, r15d
0x14002b45f  call    BiGetPartitionVhdFilePathFromUnicodeString
0x14002b464  mov     rdi, rax
0x14002b467  test    rax, rax
0x14002b46a  jz      short loc_14002B490
0x14002b46c  mov     rcx, cs:WPP_GLOBAL_Control
0x14002b473  bt      dword ptr [rcx+2Ch], 0Ah
0x14002b478  jnb     short loc_14002B490
0x14002b47a  cmp     byte ptr [rcx+29h], 4
0x14002b47e  jb      short loc_14002B490
0x14002b480  mov     rcx, [rcx+18h]
0x14002b484  lea     edx, [r15+2Bh]
0x14002b488  mov     r9, rax
0x14002b48b  call    WPP_SF_S
0x14002b490  mov     rcx, rbx
0x14002b493  call    BiGetPartitionVhdFilePathFromUnicodeString
0x14002b498  mov     rbx, rax
0x14002b49b  test    rax, rax
0x14002b49e  jz      short loc_14002B4C5
0x14002b4a0  mov     rcx, cs:WPP_GLOBAL_Control
0x14002b4a7  bt      dword ptr [rcx+2Ch], 0Ah
0x14002b4ac  jnb     short loc_14002B4C5
0x14002b4ae  cmp     byte ptr [rcx+29h], 4
0x14002b4b2  jb      short loc_14002B4C5
0x14002b4b4  mov     rcx, [rcx+18h]
0x14002b4b8  mov     edx, 2Ch ; ','
0x14002b4bd  mov     r9, rax
0x14002b4c0  call    WPP_SF_S
0x14002b4c5  test    rdi, rdi
0x14002b4c8  jz      short loc_14002B4FD
0x14002b4ca  test    rbx, rbx
0x14002b4cd  jz      short loc_14002B4EC
0x14002b4cf  mov     rdx, rbx; Str2
0x14002b4d2  mov     rcx, rdi; Str1
0x14002b4d5  call    cs:__imp__wcsicmp
0x14002b4dc  nop     dword ptr [rax+rax+00h]
0x14002b4e1  test    eax, eax
0x14002b4e3  mov     ecx, 40h ; '@'
0x14002b4e8  cmovz   r15d, ecx
0x14002b4ec  xor     edx, edx; Tag
0x14002b4ee  mov     rcx, rdi; P
0x14002b4f1  call    cs:__imp_ExFreePoolWithTag
0x14002b4f8  nop     dword ptr [rax+rax+00h]
0x14002b4fd  test    rbx, rbx
0x14002b500  jz      short loc_14002B513
0x14002b502  xor     edx, edx; Tag
0x14002b504  mov     rcx, rbx; P
0x14002b507  call    cs:__imp_ExFreePoolWithTag
0x14002b50e  nop     dword ptr [rax+rax+00h]
0x14002b513  movzx   ecx, word ptr [rsi]
0x14002b516  mov     r8d, 66637077h; Tag
0x14002b51c  movzx   r12d, word ptr [rbp+0]
0x14002b521  add     ecx, 30h ; '0'
0x14002b524  add     r12d, ecx
0x14002b527  mov     ecx, 1; PoolType
0x14002b52c  mov     edx, r12d; NumberOfBytes
0x14002b52f  mov     ebx, r12d
0x14002b532  call    cs:__imp_ExAllocatePoolWithTag
0x14002b539  nop     dword ptr [rax+rax+00h]
0x14002b53e  mov     r14, rax
0x14002b541  test    rax, rax
0x14002b544  jnz     short loc_14002B550
0x14002b546  mov     ebx, 0C0000017h
0x14002b54b  jmp     loc_14002B6B3
0x14002b550  mov     r8, rbx; Size
0x14002b553  xor     edx, edx; Val
0x14002b555  mov     rcx, r14; void *
0x14002b558  xor     edi, edi
0x14002b55a  call    memset
0x14002b55f  mov     dword ptr [r14], 3
0x14002b566  movzx   eax, word ptr [rbp+0]
0x14002b56a  add     eax, 1Ah
0x14002b56d  mov     [r14+14h], eax
0x14002b571  mov     ecx, eax
0x14002b573  add     rcx, 14h
0x14002b577  mov     dword ptr [rax+r14], 2
0x14002b57f  add     rcx, r14; void *
0x14002b582  movzx   r8d, word ptr [rsi]; Size
0x14002b586  mov     rdx, [rsi+8]; Src
0x14002b58a  call    memmove
0x14002b58f  movzx   r8d, word ptr [rbp+0]; Size
0x14002b594  lea     rcx, [r14+18h]; void *
0x14002b598  mov     rdx, [rbp+8]; Src
0x14002b59c  call    memmove
0x14002b5a1  mov     ebp, 100h
0x14002b5a6  test    rdi, rdi
0x14002b5a9  jz      short loc_14002B5BC
0x14002b5ab  xor     edx, edx; Tag
0x14002b5ad  mov     rcx, rdi; P
0x14002b5b0  call    cs:__imp_ExFreePoolWithTag
0x14002b5b7  nop     dword ptr [rax+rax+00h]
0x14002b5bc  mov     edx, ebp; NumberOfBytes
0x14002b5be  mov     ecx, 1; PoolType
0x14002b5c3  mov     r8d, 66637077h; Tag
0x14002b5c9  call    cs:__imp_ExAllocatePoolWithTag
0x14002b5d0  nop     dword ptr [rax+rax+00h]
0x14002b5d5  mov     rdi, rax
0x14002b5d8  test    rax, rax
0x14002b5db  jz      short loc_14002B65B
0x14002b5dd  lea     r9, [rsp+68h+Src]
0x14002b5e2  mov     [rsp+68h+Src], 0
0x14002b5eb  mov     r8d, r15d
0x14002b5ee  mov     edx, r12d
0x14002b5f1  mov     rcx, r14
0x14002b5f4  call    BiConvertNtDeviceToBootEnvironment
0x14002b5f9  mov     rsi, [rsp+68h+Src]
0x14002b5fe  mov     ebx, eax
0x14002b600  test    eax, eax
0x14002b602  js      short loc_14002B627
0x14002b604  mov     eax, [rsi+8]
0x14002b607  cmp     ebp, eax
0x14002b609  jnb     short loc_14002B614
0x14002b60b  mov     ebp, eax
0x14002b60d  mov     ebx, 0C0000023h
0x14002b612  jmp     short loc_14002B627
0x14002b614  mov     r8, rax; Size
0x14002b617  mov     rdx, rsi; Src
0x14002b61a  mov     rcx, rdi; void *
0x14002b61d  call    memmove
0x14002b622  mov     ebp, [rsi+8]
0x14002b625  xor     ebx, ebx
0x14002b627  test    rsi, rsi
0x14002b62a  jz      short loc_14002B639
0x14002b62c  mov     edx, 4B444342h; Tag
0x14002b631  mov     rcx, rsi; P
0x14002b634  call    ExFreePoolWithTag_0
0x14002b639  cmp     ebx, 0C0000023h
0x14002b63f  jz      loc_14002B5A6
0x14002b645  test    ebx, ebx
0x14002b647  js      short loc_14002B660
0x14002b649  mov     rax, [rsp+68h+arg_20]
0x14002b651  mov     [r13+0], rdi
0x14002b655  xor     edi, edi
0x14002b657  mov     [rax], ebp
0x14002b659  jmp     short loc_14002B68C
0x14002b65b  mov     ebx, 0C0000017h
0x14002b660  mov     rcx, cs:WPP_GLOBAL_Control
0x14002b667  mov     eax, [rcx+2Ch]
0x14002b66a  test    al, 8
0x14002b66c  jz      short loc_14002B68C
0x14002b66e  cmp     byte ptr [rcx+29h], 2
0x14002b672  jb      short loc_14002B68C
0x14002b674  mov     rcx, [rcx+18h]
0x14002b678  lea     r8, WPP_8be5f4e5626c39736f1e2e11a2a58b62_Traceguids
0x14002b67f  mov     edx, 2Dh ; '-'
0x14002b684  mov     r9d, ebx
0x14002b687  call    WPP_SF_d
0x14002b68c  xor     edx, edx; Tag
0x14002b68e  mov     rcx, r14; P
0x14002b691  call    cs:__imp_ExFreePoolWithTag
0x14002b698  nop     dword ptr [rax+rax+00h]
0x14002b69d  test    rdi, rdi
0x14002b6a0  jz      short loc_14002B6B3
0x14002b6a2  xor     edx, edx; Tag
0x14002b6a4  mov     rcx, rdi; P
0x14002b6a7  call    cs:__imp_ExFreePoolWithTag
0x14002b6ae  nop     dword ptr [rax+rax+00h]
0x14002b6b3  mov     eax, ebx
0x14002b6b5  add     rsp, 28h
0x14002b6b9  pop     r15
0x14002b6bb  pop     r14
0x14002b6bd  pop     r13
0x14002b6bf  pop     r12
0x14002b6c1  pop     rdi
0x14002b6c2  pop     rsi
0x14002b6c3  pop     rbp
0x14002b6c4  pop     rbx
0x14002b6c5  retn
```
