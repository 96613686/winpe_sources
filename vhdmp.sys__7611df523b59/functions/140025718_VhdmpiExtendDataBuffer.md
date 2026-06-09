# VhdmpiExtendDataBuffer

- ea: `0x140025718`
- end: `0x1400258e9`
- name: `VhdmpiExtendDataBuffer`
- size: `465`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x14000e680`
- `0x14000fbf0`
- `0x140010460`
- `0x1400343a0`

## callees

- `0x140011780`
- `0x140025718`
- `0x140032e94`
- `0x1400337d0`
- `0x14005da00`

## import_xrefs

- `ntoskrnl!IoFreeMdl` at `0x14002589f`
- `ntoskrnl!IoFreeMdl` at `0x14002589f`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140025807`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140025807`
- `ntoskrnl!IoAllocateMdl` at `0x1400257c0`
- `ntoskrnl!IoAllocateMdl` at `0x1400257c0`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400258bd`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400258bd`
- `ntoskrnl!ExAllocatePool2` at `0x140025851`
- `ntoskrnl!ExAllocatePool2` at `0x140025851`

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
0x140025718  push    rbx
0x14002571a  push    rbp
0x14002571b  push    rsi
0x14002571c  push    rdi
0x14002571d  push    r12
0x14002571f  push    r14
0x140025721  push    r15
0x140025723  sub     rsp, 30h
0x140025727  mov     rdi, r9
0x14002572a  mov     rsi, r8
0x14002572d  mov     r12d, edx
0x140025730  mov     rbx, rcx
0x140025733  test    rcx, rcx
0x140025736  jz      loc_1400258D4
0x14002573c  mov     rcx, [rcx]
0x14002573f  test    rcx, rcx
0x140025742  jz      loc_1400258D4
0x140025748  test    r8, r8
0x14002574b  jz      loc_1400258D4
0x140025751  cmp     qword ptr [r8], 0
0x140025755  jnz     loc_1400258D4
0x14002575b  test    r9, r9
0x14002575e  jz      loc_1400258D4
0x140025764  cmp     qword ptr [r9], 0
0x140025768  jnz     loc_1400258D4
0x14002576e  mov     r14, [rsp+68h+arg_20]
0x140025776  test    r14, r14
0x140025779  jz      loc_1400258D4
0x14002577f  test    dword ptr [rbx+40h], 800h
0x140025786  jz      loc_1400258D4
0x14002578c  mov     r15d, [rcx+48h]
0x140025790  xor     edx, edx
0x140025792  mov     eax, 1000h
0x140025797  div     r15d
0x14002579a  test    edx, edx
0x14002579c  jz      short loc_1400257A8
0x14002579e  mov     ebx, 0C0000474h
0x1400257a3  jmp     loc_140025897
0x1400257a8  mov     edx, [rbx+34h]; Length
0x1400257ab  xor     r9d, r9d; ChargeQuota
0x1400257ae  xor     r8d, r8d; SecondaryBuffer
0x1400257b1  mov     byte ptr [r14], 0
0x1400257b5  xor     ecx, ecx; VirtualAddress
0x1400257b7  mov     [rsp+68h+Irp], 0; Irp
0x1400257c0  call    cs:__imp_IoAllocateMdl
0x1400257c7  nop     dword ptr [rax+rax+00h]
0x1400257cc  mov     [rdi], rax
0x1400257cf  test    rax, rax
0x1400257d2  jnz     short loc_1400257DE
0x1400257d4  mov     ebx, 0C000009Ah
0x1400257d9  jmp     loc_140025897
0x1400257de  mov     rcx, [rbx+48h]; MemoryDescriptorList
0x1400257e2  test    byte ptr [rcx+0Ah], 5
0x1400257e6  jz      short loc_1400257EE
0x1400257e8  mov     rbp, [rcx+18h]
0x1400257ec  jmp     short loc_140025816
0x1400257ee  xor     r9d, r9d; RequestedAddress
0x1400257f1  mov     [rsp+68h+Priority], 0C0000010h; Priority
0x1400257f9  xor     edx, edx; AccessMode
0x1400257fb  mov     dword ptr [rsp+68h+Irp], 0; BugCheckOnFailure
0x140025803  lea     r8d, [r9+1]; CacheType
0x140025807  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14002580e  nop     dword ptr [rax+rax+00h]
0x140025813  mov     rbp, rax
0x140025816  test    rbp, rbp
0x140025819  jz      short loc_1400257D4
0x14002581b  mov     edx, r15d
0x14002581e  mov     rcx, rbp
0x140025821  call    VhdmpiIsBufferZero
0x140025826  test    al, al
0x140025828  jz      short loc_140025844
0x14002582a  mov     rdx, cs:VhdZeroPfn; unsigned __int64
0x140025831  mov     rcx, [rdi]; struct _MDL *
0x140025834  call    ?VhdmpiFillInitializedMdlWithPfn@@YAXPEAU_MDL@@_K@Z; VhdmpiFillInitializedMdlWithPfn(_MDL *,unsigned __int64)
0x140025839  xor     ebx, ebx
0x14002583b  mov     byte ptr [r14], 1
0x14002583f  jmp     loc_1400258D0
0x140025844  mov     r8d, r12d
0x140025847  mov     edx, 1000h
0x14002584c  mov     ecx, 42h ; 'B'
0x140025851  call    cs:__imp_ExAllocatePool2
0x140025858  nop     dword ptr [rax+rax+00h]
0x14002585d  mov     [rsi], rax
0x140025860  test    rax, rax
0x140025863  jz      loc_1400257D4
0x140025869  xor     ebx, ebx
0x14002586b  mov     ecx, ebx
0x14002586d  mov     r8, r15; Size
0x140025870  add     rcx, [rsi]; void *
0x140025873  mov     rdx, rbp; Src
0x140025876  call    memmove
0x14002587b  add     ebx, r15d
0x14002587e  cmp     ebx, 1000h
0x140025884  jb      short loc_14002586B
0x140025886  mov     rdx, [rsi]; VirtualAddress
0x140025889  mov     rcx, [rdi]; struct _MDL *
0x14002588c  call    VhdmpiFillInitializedMdlWithLockedPages
0x140025891  mov     ebx, eax
0x140025893  test    eax, eax
0x140025895  jns     short loc_1400258D0
0x140025897  mov     rcx, [rdi]; Mdl
0x14002589a  test    rcx, rcx
0x14002589d  jz      short loc_1400258B2
0x14002589f  call    cs:__imp_IoFreeMdl
0x1400258a6  nop     dword ptr [rax+rax+00h]
0x1400258ab  mov     qword ptr [rdi], 0
0x1400258b2  mov     rcx, [rsi]; P
0x1400258b5  test    rcx, rcx
0x1400258b8  jz      short loc_1400258D0
0x1400258ba  mov     edx, r12d; Tag
0x1400258bd  call    cs:__imp_ExFreePoolWithTag
0x1400258c4  nop     dword ptr [rax+rax+00h]
0x1400258c9  mov     qword ptr [rsi], 0
0x1400258d0  mov     eax, ebx
0x1400258d2  jmp     short loc_1400258D9
0x1400258d4  mov     eax, 0C000000Dh
0x1400258d9  add     rsp, 30h
0x1400258dd  pop     r15
0x1400258df  pop     r14
0x1400258e1  pop     r12
0x1400258e3  pop     rdi
0x1400258e4  pop     rsi
0x1400258e5  pop     rbp
0x1400258e6  pop     rbx
0x1400258e7  retn
```
