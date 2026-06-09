# WcPreSetEa

- ea: `0x140028e00`
- end: `0x140028f1b`
- name: `WcPreSetEa`
- size: `283`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x140002264`
- `0x1400024fc`
- `0x140028e00`

## import_xrefs

- `ntoskrnl!FsRtlSetKernelEaFile` at `0x140028ee9`
- `ntoskrnl!FsRtlSetKernelEaFile` at `0x140028ee9`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140028e76`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140028e76`
- `FLTMGR!FltGetStreamContext` at `0x140028e2f`
- `FLTMGR!FltGetStreamContext` at `0x140028e2f`
- `FLTMGR!FltReleaseContext` at `0x140028f0a`
- `FLTMGR!FltReleaseContext` at `0x140028f0a`

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
0x140028e00  mov     rax, rsp
0x140028e03  mov     [rax+8], rbx
0x140028e07  mov     [rax+18h], rsi
0x140028e0b  push    rdi
0x140028e0c  sub     rsp, 30h
0x140028e10  mov     rsi, rdx
0x140028e13  mov     qword ptr [rax+10h], 0
0x140028e1b  mov     rdx, [rdx+20h]; FileObject
0x140028e1f  lea     r8, [rax+10h]; Context
0x140028e23  mov     rbx, rcx
0x140028e26  mov     edi, 1
0x140028e2b  mov     rcx, [rsi+18h]; Instance
0x140028e2f  call    cs:__imp_FltGetStreamContext
0x140028e36  nop     dword ptr [rax+rax+00h]
0x140028e3b  test    eax, eax
0x140028e3d  jns     short loc_140028E87
0x140028e3f  mov     rbx, [rsp+38h+arg_0]
0x140028e44  mov     eax, edi
0x140028e46  mov     rsi, [rsp+38h+arg_10]
0x140028e4b  add     rsp, 30h
0x140028e4f  pop     rdi
0x140028e50  retn
0x140028e52  test    byte ptr [rcx+0Ah], 5
0x140028e56  jz      short loc_140028E5E
0x140028e58  mov     rdx, [rcx+18h]
0x140028e5c  jmp     short loc_140028EB6
0x140028e5e  mov     [rsp+38h+Priority], 40000010h; Priority
0x140028e66  xor     r9d, r9d; RequestedAddress
0x140028e69  mov     r8d, edi; CacheType
0x140028e6c  mov     [rsp+38h+BugCheckOnFailure], 0; BugCheckOnFailure
0x140028e74  xor     edx, edx; AccessMode
0x140028e76  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x140028e7d  nop     dword ptr [rax+rax+00h]
0x140028e82  mov     rdx, rax
0x140028e85  jmp     short loc_140028EB6
0x140028e87  cmp     byte ptr [rbx+50h], 0
0x140028e8b  jnz     short loc_140028F05
0x140028e8d  mov     rdx, [rsp+38h+Context]
0x140028e92  mov     rcx, [rsi+20h]
0x140028e96  call    WcUsesSourceSectionObjectPointers
0x140028e9b  test    al, al
0x140028e9d  jz      short loc_140028F05
0x140028e9f  mov     rdx, [rbx+10h]
0x140028ea3  cmp     byte ptr [rdx+5], 4
0x140028ea7  jnz     short loc_140028F05
0x140028ea9  mov     rcx, [rdx+28h]; MemoryDescriptorList
0x140028ead  test    rcx, rcx
0x140028eb0  jnz     short loc_140028E52
0x140028eb2  mov     rdx, [rdx+20h]
0x140028eb6  test    rdx, rdx
0x140028eb9  jnz     short loc_140028EC2
0x140028ebb  mov     eax, 0C0000017h
0x140028ec0  jmp     short loc_140028EF5
0x140028ec2  mov     al, cs:WcDbgProtectPackage
0x140028ec8  test    al, al
0x140028eca  jz      short loc_140028ED3
0x140028ecc  mov     eax, 0C00000A2h
0x140028ed1  jmp     short loc_140028EF5
0x140028ed3  mov     rcx, [rsp+38h+Context]
0x140028ed8  mov     r8, [rbx+10h]
0x140028edc  call    WcGetSource
0x140028ee1  mov     r8d, [r8+18h]
0x140028ee5  mov     rcx, [rax+10h]
0x140028ee9  call    cs:__imp_FsRtlSetKernelEaFile
0x140028ef0  nop     dword ptr [rax+rax+00h]
0x140028ef5  mov     [rbx+18h], eax
0x140028ef8  mov     edi, 4
0x140028efd  mov     qword ptr [rbx+20h], 0
0x140028f05  mov     rcx, [rsp+38h+Context]; Context
0x140028f0a  call    cs:__imp_FltReleaseContext
0x140028f11  nop     dword ptr [rax+rax+00h]
0x140028f16  jmp     loc_140028E3F
```
