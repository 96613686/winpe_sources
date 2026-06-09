# WimFSFDestroyIntegrity

- ea: `0x1400287cc`
- end: `0x140028884`
- name: `WimFSFDestroyIntegrity`
- size: `184`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `5`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140022e2c`
- `0x140027680`
- `0x140028488`
- `0x1400290e0`
- `0x1400298c0`

## callees

- `0x1400287cc`

## import_xrefs

- `ntoskrnl!ExDeleteLookasideListEx` at `0x14002885d`
- `ntoskrnl!ExDeleteLookasideListEx` at `0x14002885d`
- `ntoskrnl!PsInitialSystemProcess` at `0x140028806`
- `ntoskrnl!MmUnmapViewOfSection` at `0x140028810`
- `ntoskrnl!MmUnmapViewOfSection` at `0x140028810`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400287e6`
- `ntoskrnl!ExFreePoolWithTag` at `0x140028871`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400287e6`
- `ntoskrnl!ExFreePoolWithTag` at `0x140028871`
- `ntoskrnl!ObfDereferenceObject` at `0x14002882d`
- `ntoskrnl!ObfDereferenceObject` at `0x14002884d`
- `ntoskrnl!ObfDereferenceObject` at `0x14002882d`
- `ntoskrnl!ObfDereferenceObject` at `0x14002884d`

## pseudocode

```c
void __fastcall WimFSFDestroyIntegrity(char *P)
{
  void *v2; // rcx
  void *v3; // rcx
  void *v4; // rcx

  v2 = (void *)*((_QWORD *)P + 22);
  if ( v2 )
  {
    ExFreePoolWithTag(v2, 0x69637077u);
    *((_QWORD *)P + 22) = 0;
  }
  if ( *((_QWORD *)P + 3) )
  {
    MmUnmapViewOfSection(PsInitialSystemProcess);
    *((_QWORD *)P + 3) = 0;
  }
  v3 = (void *)*((_QWORD *)P + 2);
  if ( v3 )
  {
    ObfDereferenceObject(v3);
    *((_QWORD *)P + 2) = 0;
  }
  v4 = (void *)*((_QWORD *)P + 20);
  if ( v4 )
    ObfDereferenceObject(v4);
  ExDeleteLookasideListEx((PLOOKASIDE_LIST_EX)(P + 64));
  ExFreePoolWithTag(P, 0x69637077u);
}

```

## disassembly

```asm
0x1400287cc  push    rbx
0x1400287ce  sub     rsp, 20h
0x1400287d2  mov     rbx, rcx
0x1400287d5  mov     rcx, [rcx+0B0h]; P
0x1400287dc  test    rcx, rcx
0x1400287df  jz      short loc_1400287FD
0x1400287e1  mov     edx, 69637077h; Tag
0x1400287e6  call    cs:__imp_ExFreePoolWithTag
0x1400287ed  nop     dword ptr [rax+rax+00h]
0x1400287f2  mov     qword ptr [rbx+0B0h], 0
0x1400287fd  mov     rdx, [rbx+18h]
0x140028801  test    rdx, rdx
0x140028804  jz      short loc_140028824
0x140028806  mov     rcx, cs:__imp_PsInitialSystemProcess
0x14002880d  mov     rcx, [rcx]
0x140028810  call    cs:__imp_MmUnmapViewOfSection
0x140028817  nop     dword ptr [rax+rax+00h]
0x14002881c  mov     qword ptr [rbx+18h], 0
0x140028824  mov     rcx, [rbx+10h]; Object
0x140028828  test    rcx, rcx
0x14002882b  jz      short loc_140028841
0x14002882d  call    cs:__imp_ObfDereferenceObject
0x140028834  nop     dword ptr [rax+rax+00h]
0x140028839  mov     qword ptr [rbx+10h], 0
0x140028841  mov     rcx, [rbx+0A0h]; Object
0x140028848  test    rcx, rcx
0x14002884b  jz      short loc_140028859
0x14002884d  call    cs:__imp_ObfDereferenceObject
0x140028854  nop     dword ptr [rax+rax+00h]
0x140028859  lea     rcx, [rbx+40h]; Lookaside
0x14002885d  call    cs:__imp_ExDeleteLookasideListEx
0x140028864  nop     dword ptr [rax+rax+00h]
0x140028869  mov     edx, 69637077h; Tag
0x14002886e  mov     rcx, rbx; P
0x140028871  call    cs:__imp_ExFreePoolWithTag
0x140028878  nop     dword ptr [rax+rax+00h]
0x14002887d  add     rsp, 20h
0x140028881  pop     rbx
0x140028882  retn
```
