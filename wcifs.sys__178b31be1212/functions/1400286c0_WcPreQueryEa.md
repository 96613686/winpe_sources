# WcPreQueryEa

- ea: `0x1400286c0`
- end: `0x140028819`
- name: `WcPreQueryEa`
- size: `345`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x1400024fc`
- `0x140006340`
- `0x1400286c0`

## import_xrefs

- `ntoskrnl!FsRtlQueryKernelEaFile` at `0x1400287e2`
- `ntoskrnl!FsRtlQueryKernelEaFile` at `0x1400287e2`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14002872e`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14002872e`
- `FLTMGR!FltGetStreamContext` at `0x1400286ee`
- `FLTMGR!FltGetStreamContext` at `0x1400286ee`
- `FLTMGR!FltReleaseContext` at `0x140028808`
- `FLTMGR!FltReleaseContext` at `0x140028808`

## pseudocode

```c
__int64 __fastcall WcPreQueryEa(__int64 a1, __int64 a2)
{
  struct _FILE_OBJECT *v3; // rdx
  unsigned int v5; // edi
  struct _FLT_INSTANCE *v6; // rcx
  PVOID v8; // rdx
  __int64 v9; // rdx
  __int64 v10; // rcx
  int KernelEaFile; // ecx
  __int64 Source; // rax
  __int64 v13; // r8
  __int64 v14; // rdx
  PFLT_CONTEXT Context; // [rsp+88h] [rbp+20h] BYREF

  v3 = *(struct _FILE_OBJECT **)(a2 + 32);
  v5 = 1;
  v6 = *(struct _FLT_INSTANCE **)(a2 + 24);
  Context = 0;
  if ( FltGetStreamContext(v6, v3, &Context) >= 0 )
  {
    if ( WcShouldRedirectEaAndUsn(*(_BYTE *)(a1 + 80), *(_QWORD *)(a2 + 32), *((_QWORD *)Context + 4), (__int64)Context) )
    {
      v9 = *(_QWORD *)(a1 + 16);
      v10 = *(_QWORD *)(v9 + 64);
      if ( v10 )
      {
        if ( (*(_BYTE *)(v10 + 10) & 5) != 0 )
          v8 = *(PVOID *)(v10 + 24);
        else
          v8 = MmMapLockedPagesSpecifyCache((PMDL)v10, 0, MmCached, 0, 0, 0x40000010u);
      }
      else
      {
        v8 = *(PVOID *)(v9 + 56);
      }
      if ( v8 )
      {
        Source = WcGetSource(Context);
        KernelEaFile = FsRtlQueryKernelEaFile(*(_QWORD *)(Source + 16), v14, *(unsigned int *)(v13 + 24));
      }
      else
      {
        KernelEaFile = -1073741801;
      }
      *(_DWORD *)(a1 + 24) = KernelEaFile;
      v5 = 4;
      *(_QWORD *)(a1 + 32) = 0;
    }
    FltReleaseContext(Context);
  }
  return v5;
}

```

## disassembly

```asm
0x1400286c0  mov     rax, rsp
0x1400286c3  mov     [rax+8], rbx
0x1400286c7  push    rbp
0x1400286c8  push    rsi
0x1400286c9  push    rdi
0x1400286ca  sub     rsp, 50h
0x1400286ce  mov     rbx, rdx
0x1400286d1  lea     r8, [rax+20h]; Context
0x1400286d5  mov     rdx, [rdx+20h]; FileObject
0x1400286d9  mov     rsi, rcx
0x1400286dc  xor     ebp, ebp
0x1400286de  mov     edi, 1
0x1400286e3  mov     [rax+10h], ebp
0x1400286e6  mov     rcx, [rbx+18h]; Instance
0x1400286ea  mov     [rax+20h], rbp
0x1400286ee  call    cs:__imp_FltGetStreamContext
0x1400286f5  nop     dword ptr [rax+rax+00h]
0x1400286fa  test    eax, eax
0x1400286fc  jns     short loc_14002873F
0x1400286fe  mov     rbx, [rsp+68h+arg_0]
0x140028703  mov     eax, edi
0x140028705  add     rsp, 50h
0x140028709  pop     rdi
0x14002870a  pop     rsi
0x14002870b  pop     rbp
0x14002870c  retn
0x14002870e  test    byte ptr [rcx+0Ah], 5
0x140028712  jz      short loc_14002871A
0x140028714  mov     rdx, [rcx+18h]
0x140028718  jmp     short loc_140028774
0x14002871a  mov     [rsp+68h+Priority], 40000010h; Priority
0x140028722  xor     r9d, r9d; RequestedAddress
0x140028725  mov     r8d, edi; CacheType
0x140028728  mov     [rsp+68h+BugCheckOnFailure], ebp; BugCheckOnFailure
0x14002872c  xor     edx, edx; AccessMode
0x14002872e  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x140028735  nop     dword ptr [rax+rax+00h]
0x14002873a  mov     rdx, rax
0x14002873d  jmp     short loc_140028774
0x14002873f  mov     r8, [rsp+68h+Context]
0x140028747  mov     rdx, [rbx+20h]
0x14002874b  mov     r9, r8
0x14002874e  movzx   ecx, byte ptr [rsi+50h]
0x140028752  mov     r8, [r8+20h]
0x140028756  call    WcShouldRedirectEaAndUsn
0x14002875b  test    al, al
0x14002875d  jz      loc_140028800
0x140028763  mov     rdx, [rsi+10h]
0x140028767  mov     rcx, [rdx+40h]; MemoryDescriptorList
0x14002876b  test    rcx, rcx
0x14002876e  jnz     short loc_14002870E
0x140028770  mov     rdx, [rdx+38h]
0x140028774  test    rdx, rdx
0x140028777  jnz     short loc_140028786
0x140028779  mov     eax, ebp
0x14002877b  mov     ecx, 0C0000017h
0x140028780  mov     [rsp+68h+arg_8], eax
0x140028784  jmp     short loc_1400287F4
0x140028786  mov     r8, [rsi+10h]
0x14002878a  mov     rcx, [rsp+68h+Context]
0x140028792  movzx   r9d, byte ptr [r8+6]
0x140028797  lea     r10, [r8+30h]
0x14002879b  movzx   r11d, r9b
0x14002879f  and     r11b, dil
0x1400287a2  test    r9b, 4
0x1400287a6  cmovz   r10, rbp
0x1400287aa  shr     r9b, 1
0x1400287ad  and     r9b, dil
0x1400287b0  call    WcGetSource
0x1400287b5  mov     rcx, [rax+10h]
0x1400287b9  lea     rax, [rsp+68h+arg_8]
0x1400287be  mov     [rsp+68h+var_28], rax
0x1400287c3  mov     eax, [r8+28h]
0x1400287c7  mov     [rsp+68h+var_30], r11b
0x1400287cc  mov     [rsp+68h+var_38], r10
0x1400287d1  mov     [rsp+68h+Priority], eax
0x1400287d5  mov     rax, [r8+20h]
0x1400287d9  mov     r8d, [r8+18h]
0x1400287dd  mov     qword ptr [rsp+68h+BugCheckOnFailure], rax
0x1400287e2  call    cs:__imp_FsRtlQueryKernelEaFile
0x1400287e9  nop     dword ptr [rax+rax+00h]
0x1400287ee  mov     ecx, eax
0x1400287f0  mov     eax, [rsp+68h+arg_8]
0x1400287f4  mov     [rsi+18h], ecx
0x1400287f7  mov     edi, 4
0x1400287fc  mov     [rsi+20h], rax
0x140028800  mov     rcx, [rsp+68h+Context]; Context
0x140028808  call    cs:__imp_FltReleaseContext
0x14002880f  nop     dword ptr [rax+rax+00h]
0x140028814  jmp     loc_1400286FE
```
