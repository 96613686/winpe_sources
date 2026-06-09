# WcPreSetEa

- ea: `0x140028e50`
- end: `0x140028f6b`
- name: `WcPreSetEa`
- size: `283`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x140002264`
- `0x1400024fc`
- `0x140028e50`

## import_xrefs

- `ntoskrnl!FsRtlSetKernelEaFile` at `0x140028f39`
- `ntoskrnl!FsRtlSetKernelEaFile` at `0x140028f39`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140028ec6`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140028ec6`
- `FLTMGR!FltGetStreamContext` at `0x140028e7f`
- `FLTMGR!FltGetStreamContext` at `0x140028e7f`
- `FLTMGR!FltReleaseContext` at `0x140028f5a`
- `FLTMGR!FltReleaseContext` at `0x140028f5a`

## pseudocode

```c
__int64 __fastcall WcPreSetEa(__int64 a1, __int64 a2)
{
  unsigned int v4; // edi
  PVOID v6; // rdx
  __int64 v7; // rdx
  __int64 v8; // rcx
  int v9; // eax
  __int64 Source; // rax
  __int64 v11; // r8
  __int64 v12; // rdx
  PFLT_CONTEXT Context; // [rsp+48h] [rbp+10h] BYREF

  Context = 0;
  v4 = 1;
  if ( FltGetStreamContext(*(PFLT_INSTANCE *)(a2 + 24), *(PFILE_OBJECT *)(a2 + 32), &Context) >= 0 )
  {
    if ( !*(_BYTE *)(a1 + 80) )
    {
      if ( (unsigned __int8)WcUsesSourceSectionObjectPointers(*(_QWORD *)(a2 + 32), Context) )
      {
        v7 = *(_QWORD *)(a1 + 16);
        if ( *(_BYTE *)(v7 + 5) == 4 )
        {
          v8 = *(_QWORD *)(v7 + 40);
          if ( v8 )
          {
            if ( (*(_BYTE *)(v8 + 10) & 5) != 0 )
              v6 = *(PVOID *)(v8 + 24);
            else
              v6 = MmMapLockedPagesSpecifyCache((PMDL)v8, 0, MmCached, 0, 0, 0x40000010u);
          }
          else
          {
            v6 = *(PVOID *)(v7 + 32);
          }
          if ( v6 )
          {
            if ( WcDbgProtectPackage )
            {
              v9 = -1073741662;
            }
            else
            {
              Source = WcGetSource(Context);
              v9 = FsRtlSetKernelEaFile(*(_QWORD *)(Source + 16), v12, *(unsigned int *)(v11 + 24));
            }
          }
          else
          {
            v9 = -1073741801;
          }
          *(_DWORD *)(a1 + 24) = v9;
          v4 = 4;
          *(_QWORD *)(a1 + 32) = 0;
        }
      }
    }
    FltReleaseContext(Context);
  }
  return v4;
}

```

## disassembly

```asm
0x140028e50  mov     rax, rsp
0x140028e53  mov     [rax+8], rbx
0x140028e57  mov     [rax+18h], rsi
0x140028e5b  push    rdi
0x140028e5c  sub     rsp, 30h
0x140028e60  mov     rsi, rdx
0x140028e63  mov     qword ptr [rax+10h], 0
0x140028e6b  mov     rdx, [rdx+20h]; FileObject
0x140028e6f  lea     r8, [rax+10h]; Context
0x140028e73  mov     rbx, rcx
0x140028e76  mov     edi, 1
0x140028e7b  mov     rcx, [rsi+18h]; Instance
0x140028e7f  call    cs:__imp_FltGetStreamContext
0x140028e86  nop     dword ptr [rax+rax+00h]
0x140028e8b  test    eax, eax
0x140028e8d  jns     short loc_140028ED7
0x140028e8f  mov     rbx, [rsp+38h+arg_0]
0x140028e94  mov     eax, edi
0x140028e96  mov     rsi, [rsp+38h+arg_10]
0x140028e9b  add     rsp, 30h
0x140028e9f  pop     rdi
0x140028ea0  retn
0x140028ea2  test    byte ptr [rcx+0Ah], 5
0x140028ea6  jz      short loc_140028EAE
0x140028ea8  mov     rdx, [rcx+18h]
0x140028eac  jmp     short loc_140028F06
0x140028eae  mov     [rsp+38h+Priority], 40000010h; Priority
0x140028eb6  xor     r9d, r9d; RequestedAddress
0x140028eb9  mov     r8d, edi; CacheType
0x140028ebc  mov     [rsp+38h+BugCheckOnFailure], 0; BugCheckOnFailure
0x140028ec4  xor     edx, edx; AccessMode
0x140028ec6  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x140028ecd  nop     dword ptr [rax+rax+00h]
0x140028ed2  mov     rdx, rax
0x140028ed5  jmp     short loc_140028F06
0x140028ed7  cmp     byte ptr [rbx+50h], 0
0x140028edb  jnz     short loc_140028F55
0x140028edd  mov     rdx, [rsp+38h+Context]
0x140028ee2  mov     rcx, [rsi+20h]
0x140028ee6  call    WcUsesSourceSectionObjectPointers
0x140028eeb  test    al, al
0x140028eed  jz      short loc_140028F55
0x140028eef  mov     rdx, [rbx+10h]
0x140028ef3  cmp     byte ptr [rdx+5], 4
0x140028ef7  jnz     short loc_140028F55
0x140028ef9  mov     rcx, [rdx+28h]; MemoryDescriptorList
0x140028efd  test    rcx, rcx
0x140028f00  jnz     short loc_140028EA2
0x140028f02  mov     rdx, [rdx+20h]
0x140028f06  test    rdx, rdx
0x140028f09  jnz     short loc_140028F12
0x140028f0b  mov     eax, 0C0000017h
0x140028f10  jmp     short loc_140028F45
0x140028f12  mov     al, cs:WcDbgProtectPackage
0x140028f18  test    al, al
0x140028f1a  jz      short loc_140028F23
0x140028f1c  mov     eax, 0C00000A2h
0x140028f21  jmp     short loc_140028F45
0x140028f23  mov     rcx, [rsp+38h+Context]
0x140028f28  mov     r8, [rbx+10h]
0x140028f2c  call    WcGetSource
0x140028f31  mov     r8d, [r8+18h]
0x140028f35  mov     rcx, [rax+10h]
0x140028f39  call    cs:__imp_FsRtlSetKernelEaFile
0x140028f40  nop     dword ptr [rax+rax+00h]
0x140028f45  mov     [rbx+18h], eax
0x140028f48  mov     edi, 4
0x140028f4d  mov     qword ptr [rbx+20h], 0
0x140028f55  mov     rcx, [rsp+38h+Context]; Context
0x140028f5a  call    cs:__imp_FltReleaseContext
0x140028f61  nop     dword ptr [rax+rax+00h]
0x140028f66  jmp     loc_140028E8F
```
