# Smb2FreeShare

- ea: `0x140063bf4`
- end: `0x140063d99`
- name: `Smb2FreeShare`
- size: `421`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `5`
- callee_count: `4`
- tags: ``

## callers

- `0x14007ca40`
- `0x14007cbf0`
- `0x1400809c0`
- `0x140085260`
- `0x140085d00`

## callees

- `0x14000c450`
- `0x140013810`
- `0x140063bf4`
- `0x140063da0`

## import_xrefs

- `ntoskrnl!PcwCloseInstance` at `0x140063d0b`
- `ntoskrnl!PcwCloseInstance` at `0x140063d0b`
- `ntoskrnl!ExDeleteResourceLite` at `0x140063c07`
- `ntoskrnl!ExDeleteResourceLite` at `0x140063c1d`
- `ntoskrnl!ExDeleteResourceLite` at `0x140063c07`
- `ntoskrnl!ExDeleteResourceLite` at `0x140063c1d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140063c66`
- `ntoskrnl!ExFreePoolWithTag` at `0x140063c9e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140063cc3`
- `ntoskrnl!ExFreePoolWithTag` at `0x140063ce8`
- `ntoskrnl!ExFreePoolWithTag` at `0x140063d47`
- `ntoskrnl!ExFreePoolWithTag` at `0x140063d66`
- `ntoskrnl!ExFreePoolWithTag` at `0x140063d83`
- `ntoskrnl!ExFreePoolWithTag` at `0x140063c66`
- `ntoskrnl!ExFreePoolWithTag` at `0x140063c9e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140063cc3`
- `ntoskrnl!ExFreePoolWithTag` at `0x140063ce8`
- `ntoskrnl!ExFreePoolWithTag` at `0x140063d47`
- `ntoskrnl!ExFreePoolWithTag` at `0x140063d66`
- `ntoskrnl!ExFreePoolWithTag` at `0x140063d83`

## pseudocode

```c
void __fastcall Smb2FreeShare(char *P)
{
  void *v2; // rcx
  void *v3; // rcx
  void *v4; // rcx
  void *v5; // rcx
  void *v6; // rcx
  void *v7; // rcx
  struct _PCW_INSTANCE *v8; // rcx
  char *v9; // rdi
  char *v10; // rbp
  void *v11; // rcx
  void *v12; // rcx

  ExDeleteResourceLite((PERESOURCE)(*(_QWORD *)P + 96LL));
  ExDeleteResourceLite((PERESOURCE)(*(_QWORD *)P + 200LL));
  v2 = (void *)*((_QWORD *)P + 39);
  if ( v2 )
    Smb2DereferenceHandle(v2);
  v3 = (void *)*((_QWORD *)P + 40);
  if ( v3 )
    Smb2DereferenceHandle(v3);
  v4 = (void *)*((_QWORD *)P + 41);
  if ( v4 )
    Smb2DereferenceHandle(v4);
  if ( *(_QWORD *)P )
  {
    ExFreePoolWithTag(*(PVOID *)P, 0);
    *(_QWORD *)P = 0;
  }
  Smb2FreeVolumeUniqueId(*((_QWORD *)P + 47));
  v5 = (void *)*((_QWORD *)P + 18);
  *((_QWORD *)P + 47) = 0;
  if ( v5 )
  {
    ExFreePoolWithTag(v5, 0);
    *((_QWORD *)P + 18) = 0;
  }
  v6 = (void *)*((_QWORD *)P + 24);
  if ( v6 )
  {
    ExFreePoolWithTag(v6, 0);
    *((_QWORD *)P + 24) = 0;
  }
  v7 = (void *)*((_QWORD *)P + 22);
  if ( v7 )
  {
    ExFreePoolWithTag(v7, 0);
    *((_QWORD *)P + 22) = 0;
  }
  v8 = (struct _PCW_INSTANCE *)*((_QWORD *)P + 50);
  if ( v8 )
  {
    PcwCloseInstance(v8);
    *((_QWORD *)P + 50) = 0;
  }
  v9 = (char *)*((_QWORD *)P + 42);
  while ( v9 != P + 336 )
  {
    v10 = v9;
    v9 = *(char **)v9;
    v11 = (void *)*((_QWORD *)v10 + 3);
    if ( v11 )
      Smb2DereferenceHandle(v11);
    ExFreePoolWithTag(v10, 0);
  }
  v12 = (void *)*((_QWORD *)P + 33);
  if ( v12 )
    ExFreePoolWithTag(v12, 0);
  Srv2DereferenceInstance(*((PVOID *)P + 51));
  ExFreePoolWithTag(P, 0);
}

```

## disassembly

```asm
0x140063bf4  push    rbx
0x140063bf6  push    rbp
0x140063bf7  push    rsi
0x140063bf8  push    rdi
0x140063bf9  sub     rsp, 28h
0x140063bfd  mov     rbx, rcx
0x140063c00  mov     rcx, [rcx]
0x140063c03  add     rcx, 60h ; '`'; Resource
0x140063c07  call    cs:__imp_ExDeleteResourceLite
0x140063c0e  nop     dword ptr [rax+rax+00h]
0x140063c13  mov     rcx, [rbx]
0x140063c16  add     rcx, 0C8h; Resource
0x140063c1d  call    cs:__imp_ExDeleteResourceLite
0x140063c24  nop     dword ptr [rax+rax+00h]
0x140063c29  mov     rcx, [rbx+138h]; P
0x140063c30  test    rcx, rcx
0x140063c33  jz      short loc_140063C3A
0x140063c35  call    Smb2DereferenceHandle
0x140063c3a  mov     rcx, [rbx+140h]; P
0x140063c41  test    rcx, rcx
0x140063c44  jz      short loc_140063C4B
0x140063c46  call    Smb2DereferenceHandle
0x140063c4b  mov     rcx, [rbx+148h]; P
0x140063c52  test    rcx, rcx
0x140063c55  jz      short loc_140063C5C
0x140063c57  call    Smb2DereferenceHandle
0x140063c5c  mov     rcx, [rbx]; P
0x140063c5f  test    rcx, rcx
0x140063c62  jz      short loc_140063C79
0x140063c64  xor     edx, edx; Tag
0x140063c66  call    cs:__imp_ExFreePoolWithTag
0x140063c6d  nop     dword ptr [rax+rax+00h]
0x140063c72  mov     qword ptr [rbx], 0
0x140063c79  mov     rcx, [rbx+178h]
0x140063c80  call    Smb2FreeVolumeUniqueId
0x140063c85  mov     rcx, [rbx+90h]; P
0x140063c8c  mov     qword ptr [rbx+178h], 0
0x140063c97  test    rcx, rcx
0x140063c9a  jz      short loc_140063CB5
0x140063c9c  xor     edx, edx; Tag
0x140063c9e  call    cs:__imp_ExFreePoolWithTag
0x140063ca5  nop     dword ptr [rax+rax+00h]
0x140063caa  mov     qword ptr [rbx+90h], 0
0x140063cb5  mov     rcx, [rbx+0C0h]; P
0x140063cbc  test    rcx, rcx
0x140063cbf  jz      short loc_140063CDA
0x140063cc1  xor     edx, edx; Tag
0x140063cc3  call    cs:__imp_ExFreePoolWithTag
0x140063cca  nop     dword ptr [rax+rax+00h]
0x140063ccf  mov     qword ptr [rbx+0C0h], 0
0x140063cda  mov     rcx, [rbx+0B0h]; P
0x140063ce1  test    rcx, rcx
0x140063ce4  jz      short loc_140063CFF
0x140063ce6  xor     edx, edx; Tag
0x140063ce8  call    cs:__imp_ExFreePoolWithTag
0x140063cef  nop     dword ptr [rax+rax+00h]
0x140063cf4  mov     qword ptr [rbx+0B0h], 0
0x140063cff  mov     rcx, [rbx+190h]; Instance
0x140063d06  test    rcx, rcx
0x140063d09  jz      short loc_140063D22
0x140063d0b  call    cs:__imp_PcwCloseInstance
0x140063d12  nop     dword ptr [rax+rax+00h]
0x140063d17  mov     qword ptr [rbx+190h], 0
0x140063d22  lea     rsi, [rbx+150h]
0x140063d29  mov     rdi, [rsi]
0x140063d2c  jmp     short loc_140063D53
0x140063d2e  mov     rbp, rdi
0x140063d31  mov     rdi, [rdi]
0x140063d34  mov     rcx, [rbp+18h]; P
0x140063d38  test    rcx, rcx
0x140063d3b  jz      short loc_140063D42
0x140063d3d  call    Smb2DereferenceHandle
0x140063d42  xor     edx, edx; Tag
0x140063d44  mov     rcx, rbp; P
0x140063d47  call    cs:__imp_ExFreePoolWithTag
0x140063d4e  nop     dword ptr [rax+rax+00h]
0x140063d53  cmp     rdi, rsi
0x140063d56  jnz     short loc_140063D2E
0x140063d58  mov     rcx, [rbx+108h]; P
0x140063d5f  test    rcx, rcx
0x140063d62  jz      short loc_140063D72
0x140063d64  xor     edx, edx; Tag
0x140063d66  call    cs:__imp_ExFreePoolWithTag
0x140063d6d  nop     dword ptr [rax+rax+00h]
0x140063d72  mov     rcx, [rbx+198h]; Context
0x140063d79  call    Srv2DereferenceInstance
0x140063d7e  xor     edx, edx; Tag
0x140063d80  mov     rcx, rbx; P
0x140063d83  call    cs:__imp_ExFreePoolWithTag
0x140063d8a  nop     dword ptr [rax+rax+00h]
0x140063d8f  add     rsp, 28h
0x140063d93  pop     rdi
0x140063d94  pop     rsi
0x140063d95  pop     rbp
0x140063d96  pop     rbx
0x140063d97  retn
```
