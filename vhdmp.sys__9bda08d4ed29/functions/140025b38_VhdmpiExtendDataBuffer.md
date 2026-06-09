# VhdmpiExtendDataBuffer

- ea: `0x140025b38`
- end: `0x140025d09`
- name: `VhdmpiExtendDataBuffer`
- size: `465`
- prototype: ``
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x14000ec80`
- `0x140010fa0`
- `0x140011790`
- `0x140034860`

## callees

- `0x140012ab0`
- `0x140025b38`
- `0x140033354`
- `0x140033c90`
- `0x14005de00`

## import_xrefs

- `ntoskrnl!IoFreeMdl` at `0x140025cbf`
- `ntoskrnl!IoFreeMdl` at `0x140025cbf`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140025c27`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140025c27`
- `ntoskrnl!IoAllocateMdl` at `0x140025be0`
- `ntoskrnl!IoAllocateMdl` at `0x140025be0`
- `ntoskrnl!ExFreePoolWithTag` at `0x140025cdd`
- `ntoskrnl!ExFreePoolWithTag` at `0x140025cdd`
- `ntoskrnl!ExAllocatePool2` at `0x140025c71`
- `ntoskrnl!ExAllocatePool2` at `0x140025c71`

## pseudocode

```c
__int64 __fastcall VhdmpiExtendDataBuffer(__int64 *a1, ULONG a2, PVOID *a3, PMDL *a4, _BYTE *a5)
{
  __int64 v9; // rcx
  size_t v10; // r15
  unsigned int locked; // ebx
  ULONG v12; // edx
  PMDL Mdl; // rax
  __int64 v14; // rcx
  PVOID v15; // rbp
  __int64 Pool2; // rax
  unsigned int i; // ebx

  if ( a1 )
  {
    v9 = *a1;
    if ( v9 )
    {
      if ( a3 && !*a3 && a4 && !*a4 && a5 && (a1[8] & 0x800) != 0 )
      {
        v10 = *(unsigned int *)(v9 + 72);
        if ( 0x1000 % (unsigned int)v10 )
        {
          locked = -1073740684;
LABEL_23:
          if ( *a4 )
          {
            IoFreeMdl(*a4);
            *a4 = 0;
          }
          if ( *a3 )
          {
            ExFreePoolWithTag(*a3, a2);
            *a3 = 0;
          }
          return locked;
        }
        v12 = *((_DWORD *)a1 + 13);
        *a5 = 0;
        Mdl = IoAllocateMdl(0, v12, 0, 0, 0);
        *a4 = Mdl;
        if ( Mdl )
        {
          v14 = a1[9];
          v15 = (*(_BYTE *)(v14 + 10) & 5) != 0
              ? *(PVOID *)(v14 + 24)
              : MmMapLockedPagesSpecifyCache((PMDL)v14, 0, MmCached, 0, 0, 0xC0000010);
          if ( v15 )
          {
            if ( (unsigned __int8)VhdmpiIsBufferZero(v15, (unsigned int)v10) )
            {
              VhdmpiFillInitializedMdlWithPfn(*a4, VhdZeroPfn);
              locked = 0;
              *a5 = 1;
              return locked;
            }
            Pool2 = ExAllocatePool2(66, 4096, a2);
            *a3 = (PVOID)Pool2;
            if ( Pool2 )
            {
              for ( i = 0; i < 0x1000; i += v10 )
                memmove((char *)*a3 + i, v15, v10);
              locked = VhdmpiFillInitializedMdlWithLockedPages(*a4, *a3);
              if ( (locked & 0x80000000) != 0 )
                goto LABEL_23;
              return locked;
            }
          }
        }
        locked = -1073741670;
        goto LABEL_23;
      }
    }
  }
  return 3221225485LL;
}

```

## disassembly

```asm
0x140025b38  push    rbx
0x140025b3a  push    rbp
0x140025b3b  push    rsi
0x140025b3c  push    rdi
0x140025b3d  push    r12
0x140025b3f  push    r14
0x140025b41  push    r15
0x140025b43  sub     rsp, 30h
0x140025b47  mov     rdi, r9
0x140025b4a  mov     rsi, r8
0x140025b4d  mov     r12d, edx
0x140025b50  mov     rbx, rcx
0x140025b53  test    rcx, rcx
0x140025b56  jz      loc_140025CF4
0x140025b5c  mov     rcx, [rcx]
0x140025b5f  test    rcx, rcx
0x140025b62  jz      loc_140025CF4
0x140025b68  test    r8, r8
0x140025b6b  jz      loc_140025CF4
0x140025b71  cmp     qword ptr [r8], 0
0x140025b75  jnz     loc_140025CF4
0x140025b7b  test    r9, r9
0x140025b7e  jz      loc_140025CF4
0x140025b84  cmp     qword ptr [r9], 0
0x140025b88  jnz     loc_140025CF4
0x140025b8e  mov     r14, [rsp+68h+arg_20]
0x140025b96  test    r14, r14
0x140025b99  jz      loc_140025CF4
0x140025b9f  test    dword ptr [rbx+40h], 800h
0x140025ba6  jz      loc_140025CF4
0x140025bac  mov     r15d, [rcx+48h]
0x140025bb0  xor     edx, edx
0x140025bb2  mov     eax, 1000h
0x140025bb7  div     r15d
0x140025bba  test    edx, edx
0x140025bbc  jz      short loc_140025BC8
0x140025bbe  mov     ebx, 0C0000474h
0x140025bc3  jmp     loc_140025CB7
0x140025bc8  mov     edx, [rbx+34h]; Length
0x140025bcb  xor     r9d, r9d; ChargeQuota
0x140025bce  xor     r8d, r8d; SecondaryBuffer
0x140025bd1  mov     byte ptr [r14], 0
0x140025bd5  xor     ecx, ecx; VirtualAddress
0x140025bd7  mov     [rsp+68h+Irp], 0; Irp
0x140025be0  call    cs:__imp_IoAllocateMdl
0x140025be7  nop     dword ptr [rax+rax+00h]
0x140025bec  mov     [rdi], rax
0x140025bef  test    rax, rax
0x140025bf2  jnz     short loc_140025BFE
0x140025bf4  mov     ebx, 0C000009Ah
0x140025bf9  jmp     loc_140025CB7
0x140025bfe  mov     rcx, [rbx+48h]; MemoryDescriptorList
0x140025c02  test    byte ptr [rcx+0Ah], 5
0x140025c06  jz      short loc_140025C0E
0x140025c08  mov     rbp, [rcx+18h]
0x140025c0c  jmp     short loc_140025C36
0x140025c0e  xor     r9d, r9d; RequestedAddress
0x140025c11  mov     [rsp+68h+Priority], 0C0000010h; Priority
0x140025c19  xor     edx, edx; AccessMode
0x140025c1b  mov     dword ptr [rsp+68h+Irp], 0; BugCheckOnFailure
0x140025c23  lea     r8d, [r9+1]; CacheType
0x140025c27  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x140025c2e  nop     dword ptr [rax+rax+00h]
0x140025c33  mov     rbp, rax
0x140025c36  test    rbp, rbp
0x140025c39  jz      short loc_140025BF4
0x140025c3b  mov     edx, r15d
0x140025c3e  mov     rcx, rbp
0x140025c41  call    VhdmpiIsBufferZero
0x140025c46  test    al, al
0x140025c48  jz      short loc_140025C64
0x140025c4a  mov     rdx, cs:VhdZeroPfn; unsigned __int64
0x140025c51  mov     rcx, [rdi]; struct _MDL *
0x140025c54  call    ?VhdmpiFillInitializedMdlWithPfn@@YAXPEAU_MDL@@_K@Z; VhdmpiFillInitializedMdlWithPfn(_MDL *,unsigned __int64)
0x140025c59  xor     ebx, ebx
0x140025c5b  mov     byte ptr [r14], 1
0x140025c5f  jmp     loc_140025CF0
0x140025c64  mov     r8d, r12d
0x140025c67  mov     edx, 1000h
0x140025c6c  mov     ecx, 42h ; 'B'
0x140025c71  call    cs:__imp_ExAllocatePool2
0x140025c78  nop     dword ptr [rax+rax+00h]
0x140025c7d  mov     [rsi], rax
0x140025c80  test    rax, rax
0x140025c83  jz      loc_140025BF4
0x140025c89  xor     ebx, ebx
0x140025c8b  mov     ecx, ebx
0x140025c8d  mov     r8, r15; Size
0x140025c90  add     rcx, [rsi]; void *
0x140025c93  mov     rdx, rbp; Src
0x140025c96  call    memmove
0x140025c9b  add     ebx, r15d
0x140025c9e  cmp     ebx, 1000h
0x140025ca4  jb      short loc_140025C8B
0x140025ca6  mov     rdx, [rsi]; VirtualAddress
0x140025ca9  mov     rcx, [rdi]; struct _MDL *
0x140025cac  call    VhdmpiFillInitializedMdlWithLockedPages
0x140025cb1  mov     ebx, eax
0x140025cb3  test    eax, eax
0x140025cb5  jns     short loc_140025CF0
0x140025cb7  mov     rcx, [rdi]; Mdl
0x140025cba  test    rcx, rcx
0x140025cbd  jz      short loc_140025CD2
0x140025cbf  call    cs:__imp_IoFreeMdl
0x140025cc6  nop     dword ptr [rax+rax+00h]
0x140025ccb  mov     qword ptr [rdi], 0
0x140025cd2  mov     rcx, [rsi]; P
0x140025cd5  test    rcx, rcx
0x140025cd8  jz      short loc_140025CF0
0x140025cda  mov     edx, r12d; Tag
0x140025cdd  call    cs:__imp_ExFreePoolWithTag
0x140025ce4  nop     dword ptr [rax+rax+00h]
0x140025ce9  mov     qword ptr [rsi], 0
0x140025cf0  mov     eax, ebx
0x140025cf2  jmp     short loc_140025CF9
0x140025cf4  mov     eax, 0C000000Dh
0x140025cf9  add     rsp, 30h
0x140025cfd  pop     r15
0x140025cff  pop     r14
0x140025d01  pop     r12
0x140025d03  pop     rdi
0x140025d04  pop     rsi
0x140025d05  pop     rbp
0x140025d06  pop     rbx
0x140025d07  retn
```
