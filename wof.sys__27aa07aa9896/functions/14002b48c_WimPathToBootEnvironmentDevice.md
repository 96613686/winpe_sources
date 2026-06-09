# WimPathToBootEnvironmentDevice

- ea: `0x14002b48c`
- end: `0x14002b717`
- name: `WimPathToBootEnvironmentDevice`
- size: `651`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: ``

## callers

- `0x14002ad78`
- `0x14002badc`

## callees

- `0x14000d3b8`
- `0x14000da0d`
- `0x14000ff9c`
- `0x1400116c0`
- `0x1400119c0`
- `0x14002b48c`
- `0x14002fce8`
- `0x140031550`

## import_xrefs

- `ntoskrnl!_wcsicmp` at `0x14002b525`
- `ntoskrnl!_wcsicmp` at `0x14002b525`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002b541`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002b557`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002b600`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002b6e1`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002b6f7`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002b541`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002b557`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002b600`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002b6e1`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002b6f7`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14002b582`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14002b619`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14002b582`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14002b619`

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
0x14002b48c  push    rbx
0x14002b48e  push    rbp
0x14002b48f  push    rsi
0x14002b490  push    rdi
0x14002b491  push    r12
0x14002b493  push    r13
0x14002b495  push    r14
0x14002b497  push    r15
0x14002b499  sub     rsp, 28h
0x14002b49d  mov     rbx, rcx
0x14002b4a0  mov     r13, r9
0x14002b4a3  mov     rcx, rdx
0x14002b4a6  mov     rbp, r8
0x14002b4a9  mov     rsi, rdx
0x14002b4ac  xor     r15d, r15d
0x14002b4af  call    BiGetPartitionVhdFilePathFromUnicodeString
0x14002b4b4  mov     rdi, rax
0x14002b4b7  test    rax, rax
0x14002b4ba  jz      short loc_14002B4E0
0x14002b4bc  mov     rcx, cs:WPP_GLOBAL_Control
0x14002b4c3  bt      dword ptr [rcx+2Ch], 0Ah
0x14002b4c8  jnb     short loc_14002B4E0
0x14002b4ca  cmp     byte ptr [rcx+29h], 4
0x14002b4ce  jb      short loc_14002B4E0
0x14002b4d0  mov     rcx, [rcx+18h]
0x14002b4d4  lea     edx, [r15+2Bh]
0x14002b4d8  mov     r9, rax
0x14002b4db  call    WPP_SF_S
0x14002b4e0  mov     rcx, rbx
0x14002b4e3  call    BiGetPartitionVhdFilePathFromUnicodeString
0x14002b4e8  mov     rbx, rax
0x14002b4eb  test    rax, rax
0x14002b4ee  jz      short loc_14002B515
0x14002b4f0  mov     rcx, cs:WPP_GLOBAL_Control
0x14002b4f7  bt      dword ptr [rcx+2Ch], 0Ah
0x14002b4fc  jnb     short loc_14002B515
0x14002b4fe  cmp     byte ptr [rcx+29h], 4
0x14002b502  jb      short loc_14002B515
0x14002b504  mov     rcx, [rcx+18h]
0x14002b508  mov     edx, 2Ch ; ','
0x14002b50d  mov     r9, rax
0x14002b510  call    WPP_SF_S
0x14002b515  test    rdi, rdi
0x14002b518  jz      short loc_14002B54D
0x14002b51a  test    rbx, rbx
0x14002b51d  jz      short loc_14002B53C
0x14002b51f  mov     rdx, rbx; Str2
0x14002b522  mov     rcx, rdi; Str1
0x14002b525  call    cs:__imp__wcsicmp
0x14002b52c  nop     dword ptr [rax+rax+00h]
0x14002b531  test    eax, eax
0x14002b533  mov     ecx, 40h ; '@'
0x14002b538  cmovz   r15d, ecx
0x14002b53c  xor     edx, edx; Tag
0x14002b53e  mov     rcx, rdi; P
0x14002b541  call    cs:__imp_ExFreePoolWithTag
0x14002b548  nop     dword ptr [rax+rax+00h]
0x14002b54d  test    rbx, rbx
0x14002b550  jz      short loc_14002B563
0x14002b552  xor     edx, edx; Tag
0x14002b554  mov     rcx, rbx; P
0x14002b557  call    cs:__imp_ExFreePoolWithTag
0x14002b55e  nop     dword ptr [rax+rax+00h]
0x14002b563  movzx   ecx, word ptr [rsi]
0x14002b566  mov     r8d, 66637077h; Tag
0x14002b56c  movzx   r12d, word ptr [rbp+0]
0x14002b571  add     ecx, 30h ; '0'
0x14002b574  add     r12d, ecx
0x14002b577  mov     ecx, 1; PoolType
0x14002b57c  mov     edx, r12d; NumberOfBytes
0x14002b57f  mov     ebx, r12d
0x14002b582  call    cs:__imp_ExAllocatePoolWithTag
0x14002b589  nop     dword ptr [rax+rax+00h]
0x14002b58e  mov     r14, rax
0x14002b591  test    rax, rax
0x14002b594  jnz     short loc_14002B5A0
0x14002b596  mov     ebx, 0C0000017h
0x14002b59b  jmp     loc_14002B703
0x14002b5a0  mov     r8, rbx; Size
0x14002b5a3  xor     edx, edx; Val
0x14002b5a5  mov     rcx, r14; void *
0x14002b5a8  xor     edi, edi
0x14002b5aa  call    memset
0x14002b5af  mov     dword ptr [r14], 3
0x14002b5b6  movzx   eax, word ptr [rbp+0]
0x14002b5ba  add     eax, 1Ah
0x14002b5bd  mov     [r14+14h], eax
0x14002b5c1  mov     ecx, eax
0x14002b5c3  add     rcx, 14h
0x14002b5c7  mov     dword ptr [rax+r14], 2
0x14002b5cf  add     rcx, r14; void *
0x14002b5d2  movzx   r8d, word ptr [rsi]; Size
0x14002b5d6  mov     rdx, [rsi+8]; Src
0x14002b5da  call    memmove
0x14002b5df  movzx   r8d, word ptr [rbp+0]; Size
0x14002b5e4  lea     rcx, [r14+18h]; void *
0x14002b5e8  mov     rdx, [rbp+8]; Src
0x14002b5ec  call    memmove
0x14002b5f1  mov     ebp, 100h
0x14002b5f6  test    rdi, rdi
0x14002b5f9  jz      short loc_14002B60C
0x14002b5fb  xor     edx, edx; Tag
0x14002b5fd  mov     rcx, rdi; P
0x14002b600  call    cs:__imp_ExFreePoolWithTag
0x14002b607  nop     dword ptr [rax+rax+00h]
0x14002b60c  mov     edx, ebp; NumberOfBytes
0x14002b60e  mov     ecx, 1; PoolType
0x14002b613  mov     r8d, 66637077h; Tag
0x14002b619  call    cs:__imp_ExAllocatePoolWithTag
0x14002b620  nop     dword ptr [rax+rax+00h]
0x14002b625  mov     rdi, rax
0x14002b628  test    rax, rax
0x14002b62b  jz      short loc_14002B6AB
0x14002b62d  lea     r9, [rsp+68h+Src]
0x14002b632  mov     [rsp+68h+Src], 0
0x14002b63b  mov     r8d, r15d
0x14002b63e  mov     edx, r12d
0x14002b641  mov     rcx, r14
0x14002b644  call    BiConvertNtDeviceToBootEnvironment
0x14002b649  mov     rsi, [rsp+68h+Src]
0x14002b64e  mov     ebx, eax
0x14002b650  test    eax, eax
0x14002b652  js      short loc_14002B677
0x14002b654  mov     eax, [rsi+8]
0x14002b657  cmp     ebp, eax
0x14002b659  jnb     short loc_14002B664
0x14002b65b  mov     ebp, eax
0x14002b65d  mov     ebx, 0C0000023h
0x14002b662  jmp     short loc_14002B677
0x14002b664  mov     r8, rax; Size
0x14002b667  mov     rdx, rsi; Src
0x14002b66a  mov     rcx, rdi; void *
0x14002b66d  call    memmove
0x14002b672  mov     ebp, [rsi+8]
0x14002b675  xor     ebx, ebx
0x14002b677  test    rsi, rsi
0x14002b67a  jz      short loc_14002B689
0x14002b67c  mov     edx, 4B444342h; Tag
0x14002b681  mov     rcx, rsi; P
0x14002b684  call    ExFreePoolWithTag_0
0x14002b689  cmp     ebx, 0C0000023h
0x14002b68f  jz      loc_14002B5F6
0x14002b695  test    ebx, ebx
0x14002b697  js      short loc_14002B6B0
0x14002b699  mov     rax, [rsp+68h+arg_20]
0x14002b6a1  mov     [r13+0], rdi
0x14002b6a5  xor     edi, edi
0x14002b6a7  mov     [rax], ebp
0x14002b6a9  jmp     short loc_14002B6DC
0x14002b6ab  mov     ebx, 0C0000017h
0x14002b6b0  mov     rcx, cs:WPP_GLOBAL_Control
0x14002b6b7  mov     eax, [rcx+2Ch]
0x14002b6ba  test    al, 8
0x14002b6bc  jz      short loc_14002B6DC
0x14002b6be  cmp     byte ptr [rcx+29h], 2
0x14002b6c2  jb      short loc_14002B6DC
0x14002b6c4  mov     rcx, [rcx+18h]
0x14002b6c8  lea     r8, WPP_8be5f4e5626c39736f1e2e11a2a58b62_Traceguids
0x14002b6cf  mov     edx, 2Dh ; '-'
0x14002b6d4  mov     r9d, ebx
0x14002b6d7  call    WPP_SF_d
0x14002b6dc  xor     edx, edx; Tag
0x14002b6de  mov     rcx, r14; P
0x14002b6e1  call    cs:__imp_ExFreePoolWithTag
0x14002b6e8  nop     dword ptr [rax+rax+00h]
0x14002b6ed  test    rdi, rdi
0x14002b6f0  jz      short loc_14002B703
0x14002b6f2  xor     edx, edx; Tag
0x14002b6f4  mov     rcx, rdi; P
0x14002b6f7  call    cs:__imp_ExFreePoolWithTag
0x14002b6fe  nop     dword ptr [rax+rax+00h]
0x14002b703  mov     eax, ebx
0x14002b705  add     rsp, 28h
0x14002b709  pop     r15
0x14002b70b  pop     r14
0x14002b70d  pop     r13
0x14002b70f  pop     r12
0x14002b711  pop     rdi
0x14002b712  pop     rsi
0x14002b713  pop     rbp
0x14002b714  pop     rbx
0x14002b715  retn
```
