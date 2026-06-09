# WcPreQueryEa

- ea: `0x140028670`
- end: `0x1400287c9`
- name: `WcPreQueryEa`
- size: `345`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x1400024fc`
- `0x140006340`
- `0x140028670`

## import_xrefs

- `ntoskrnl!FsRtlQueryKernelEaFile` at `0x140028792`
- `ntoskrnl!FsRtlQueryKernelEaFile` at `0x140028792`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400286de`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400286de`
- `FLTMGR!FltGetStreamContext` at `0x14002869e`
- `FLTMGR!FltGetStreamContext` at `0x14002869e`
- `FLTMGR!FltReleaseContext` at `0x1400287b8`
- `FLTMGR!FltReleaseContext` at `0x1400287b8`

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
    if ( (unsigned __int8)WcShouldRedirectEaAndUsn(
                            *(unsigned __int8 *)(a1 + 80),
                            *(_QWORD *)(a2 + 32),
                            *((_QWORD *)Context + 4),
                            Context) )
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
0x140028670  mov     rax, rsp
0x140028673  mov     [rax+8], rbx
0x140028677  push    rbp
0x140028678  push    rsi
0x140028679  push    rdi
0x14002867a  sub     rsp, 50h
0x14002867e  mov     rbx, rdx
0x140028681  lea     r8, [rax+20h]; Context
0x140028685  mov     rdx, [rdx+20h]; FileObject
0x140028689  mov     rsi, rcx
0x14002868c  xor     ebp, ebp
0x14002868e  mov     edi, 1
0x140028693  mov     [rax+10h], ebp
0x140028696  mov     rcx, [rbx+18h]; Instance
0x14002869a  mov     [rax+20h], rbp
0x14002869e  call    cs:__imp_FltGetStreamContext
0x1400286a5  nop     dword ptr [rax+rax+00h]
0x1400286aa  test    eax, eax
0x1400286ac  jns     short loc_1400286EF
0x1400286ae  mov     rbx, [rsp+68h+arg_0]
0x1400286b3  mov     eax, edi
0x1400286b5  add     rsp, 50h
0x1400286b9  pop     rdi
0x1400286ba  pop     rsi
0x1400286bb  pop     rbp
0x1400286bc  retn
0x1400286be  test    byte ptr [rcx+0Ah], 5
0x1400286c2  jz      short loc_1400286CA
0x1400286c4  mov     rdx, [rcx+18h]
0x1400286c8  jmp     short loc_140028724
0x1400286ca  mov     [rsp+68h+Priority], 40000010h; Priority
0x1400286d2  xor     r9d, r9d; RequestedAddress
0x1400286d5  mov     r8d, edi; CacheType
0x1400286d8  mov     [rsp+68h+BugCheckOnFailure], ebp; BugCheckOnFailure
0x1400286dc  xor     edx, edx; AccessMode
0x1400286de  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x1400286e5  nop     dword ptr [rax+rax+00h]
0x1400286ea  mov     rdx, rax
0x1400286ed  jmp     short loc_140028724
0x1400286ef  mov     r8, [rsp+68h+Context]
0x1400286f7  mov     rdx, [rbx+20h]
0x1400286fb  mov     r9, r8
0x1400286fe  movzx   ecx, byte ptr [rsi+50h]
0x140028702  mov     r8, [r8+20h]
0x140028706  call    WcShouldRedirectEaAndUsn
0x14002870b  test    al, al
0x14002870d  jz      loc_1400287B0
0x140028713  mov     rdx, [rsi+10h]
0x140028717  mov     rcx, [rdx+40h]; MemoryDescriptorList
0x14002871b  test    rcx, rcx
0x14002871e  jnz     short loc_1400286BE
0x140028720  mov     rdx, [rdx+38h]
0x140028724  test    rdx, rdx
0x140028727  jnz     short loc_140028736
0x140028729  mov     eax, ebp
0x14002872b  mov     ecx, 0C0000017h
0x140028730  mov     [rsp+68h+arg_8], eax
0x140028734  jmp     short loc_1400287A4
0x140028736  mov     r8, [rsi+10h]
0x14002873a  mov     rcx, [rsp+68h+Context]
0x140028742  movzx   r9d, byte ptr [r8+6]
0x140028747  lea     r10, [r8+30h]
0x14002874b  movzx   r11d, r9b
0x14002874f  and     r11b, dil
0x140028752  test    r9b, 4
0x140028756  cmovz   r10, rbp
0x14002875a  shr     r9b, 1
0x14002875d  and     r9b, dil
0x140028760  call    WcGetSource
0x140028765  mov     rcx, [rax+10h]
0x140028769  lea     rax, [rsp+68h+arg_8]
0x14002876e  mov     [rsp+68h+var_28], rax
0x140028773  mov     eax, [r8+28h]
0x140028777  mov     [rsp+68h+var_30], r11b
0x14002877c  mov     [rsp+68h+var_38], r10
0x140028781  mov     [rsp+68h+Priority], eax
0x140028785  mov     rax, [r8+20h]
0x140028789  mov     r8d, [r8+18h]
0x14002878d  mov     qword ptr [rsp+68h+BugCheckOnFailure], rax
0x140028792  call    cs:__imp_FsRtlQueryKernelEaFile
0x140028799  nop     dword ptr [rax+rax+00h]
0x14002879e  mov     ecx, eax
0x1400287a0  mov     eax, [rsp+68h+arg_8]
0x1400287a4  mov     [rsi+18h], ecx
0x1400287a7  mov     edi, 4
0x1400287ac  mov     [rsi+20h], rax
0x1400287b0  mov     rcx, [rsp+68h+Context]; Context
0x1400287b8  call    cs:__imp_FltReleaseContext
0x1400287bf  nop     dword ptr [rax+rax+00h]
0x1400287c4  jmp     loc_1400286AE
```
