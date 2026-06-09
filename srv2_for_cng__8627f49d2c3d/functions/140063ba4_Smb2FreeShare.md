# Smb2FreeShare

- ea: `0x140063ba4`
- end: `0x140063d49`
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
- `0x140063ba4`
- `0x140063d50`

## import_xrefs

- `ntoskrnl!PcwCloseInstance` at `0x140063cbb`
- `ntoskrnl!PcwCloseInstance` at `0x140063cbb`
- `ntoskrnl!ExDeleteResourceLite` at `0x140063bb7`
- `ntoskrnl!ExDeleteResourceLite` at `0x140063bcd`
- `ntoskrnl!ExDeleteResourceLite` at `0x140063bb7`
- `ntoskrnl!ExDeleteResourceLite` at `0x140063bcd`
- `ntoskrnl!ExFreePoolWithTag` at `0x140063c16`
- `ntoskrnl!ExFreePoolWithTag` at `0x140063c4e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140063c73`
- `ntoskrnl!ExFreePoolWithTag` at `0x140063c98`
- `ntoskrnl!ExFreePoolWithTag` at `0x140063cf7`
- `ntoskrnl!ExFreePoolWithTag` at `0x140063d16`
- `ntoskrnl!ExFreePoolWithTag` at `0x140063d33`
- `ntoskrnl!ExFreePoolWithTag` at `0x140063c16`
- `ntoskrnl!ExFreePoolWithTag` at `0x140063c4e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140063c73`
- `ntoskrnl!ExFreePoolWithTag` at `0x140063c98`
- `ntoskrnl!ExFreePoolWithTag` at `0x140063cf7`
- `ntoskrnl!ExFreePoolWithTag` at `0x140063d16`
- `ntoskrnl!ExFreePoolWithTag` at `0x140063d33`

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
0x140063ba4  push    rbx
0x140063ba6  push    rbp
0x140063ba7  push    rsi
0x140063ba8  push    rdi
0x140063ba9  sub     rsp, 28h
0x140063bad  mov     rbx, rcx
0x140063bb0  mov     rcx, [rcx]
0x140063bb3  add     rcx, 60h ; '`'; Resource
0x140063bb7  call    cs:__imp_ExDeleteResourceLite
0x140063bbe  nop     dword ptr [rax+rax+00h]
0x140063bc3  mov     rcx, [rbx]
0x140063bc6  add     rcx, 0C8h; Resource
0x140063bcd  call    cs:__imp_ExDeleteResourceLite
0x140063bd4  nop     dword ptr [rax+rax+00h]
0x140063bd9  mov     rcx, [rbx+138h]; P
0x140063be0  test    rcx, rcx
0x140063be3  jz      short loc_140063BEA
0x140063be5  call    Smb2DereferenceHandle
0x140063bea  mov     rcx, [rbx+140h]; P
0x140063bf1  test    rcx, rcx
0x140063bf4  jz      short loc_140063BFB
0x140063bf6  call    Smb2DereferenceHandle
0x140063bfb  mov     rcx, [rbx+148h]; P
0x140063c02  test    rcx, rcx
0x140063c05  jz      short loc_140063C0C
0x140063c07  call    Smb2DereferenceHandle
0x140063c0c  mov     rcx, [rbx]; P
0x140063c0f  test    rcx, rcx
0x140063c12  jz      short loc_140063C29
0x140063c14  xor     edx, edx; Tag
0x140063c16  call    cs:__imp_ExFreePoolWithTag
0x140063c1d  nop     dword ptr [rax+rax+00h]
0x140063c22  mov     qword ptr [rbx], 0
0x140063c29  mov     rcx, [rbx+178h]
0x140063c30  call    Smb2FreeVolumeUniqueId
0x140063c35  mov     rcx, [rbx+90h]; P
0x140063c3c  mov     qword ptr [rbx+178h], 0
0x140063c47  test    rcx, rcx
0x140063c4a  jz      short loc_140063C65
0x140063c4c  xor     edx, edx; Tag
0x140063c4e  call    cs:__imp_ExFreePoolWithTag
0x140063c55  nop     dword ptr [rax+rax+00h]
0x140063c5a  mov     qword ptr [rbx+90h], 0
0x140063c65  mov     rcx, [rbx+0C0h]; P
0x140063c6c  test    rcx, rcx
0x140063c6f  jz      short loc_140063C8A
0x140063c71  xor     edx, edx; Tag
0x140063c73  call    cs:__imp_ExFreePoolWithTag
0x140063c7a  nop     dword ptr [rax+rax+00h]
0x140063c7f  mov     qword ptr [rbx+0C0h], 0
0x140063c8a  mov     rcx, [rbx+0B0h]; P
0x140063c91  test    rcx, rcx
0x140063c94  jz      short loc_140063CAF
0x140063c96  xor     edx, edx; Tag
0x140063c98  call    cs:__imp_ExFreePoolWithTag
0x140063c9f  nop     dword ptr [rax+rax+00h]
0x140063ca4  mov     qword ptr [rbx+0B0h], 0
0x140063caf  mov     rcx, [rbx+190h]; Instance
0x140063cb6  test    rcx, rcx
0x140063cb9  jz      short loc_140063CD2
0x140063cbb  call    cs:__imp_PcwCloseInstance
0x140063cc2  nop     dword ptr [rax+rax+00h]
0x140063cc7  mov     qword ptr [rbx+190h], 0
0x140063cd2  lea     rsi, [rbx+150h]
0x140063cd9  mov     rdi, [rsi]
0x140063cdc  jmp     short loc_140063D03
0x140063cde  mov     rbp, rdi
0x140063ce1  mov     rdi, [rdi]
0x140063ce4  mov     rcx, [rbp+18h]; P
0x140063ce8  test    rcx, rcx
0x140063ceb  jz      short loc_140063CF2
0x140063ced  call    Smb2DereferenceHandle
0x140063cf2  xor     edx, edx; Tag
0x140063cf4  mov     rcx, rbp; P
0x140063cf7  call    cs:__imp_ExFreePoolWithTag
0x140063cfe  nop     dword ptr [rax+rax+00h]
0x140063d03  cmp     rdi, rsi
0x140063d06  jnz     short loc_140063CDE
0x140063d08  mov     rcx, [rbx+108h]; P
0x140063d0f  test    rcx, rcx
0x140063d12  jz      short loc_140063D22
0x140063d14  xor     edx, edx; Tag
0x140063d16  call    cs:__imp_ExFreePoolWithTag
0x140063d1d  nop     dword ptr [rax+rax+00h]
0x140063d22  mov     rcx, [rbx+198h]; Context
0x140063d29  call    Srv2DereferenceInstance
0x140063d2e  xor     edx, edx; Tag
0x140063d30  mov     rcx, rbx; P
0x140063d33  call    cs:__imp_ExFreePoolWithTag
0x140063d3a  nop     dword ptr [rax+rax+00h]
0x140063d3f  add     rsp, 28h
0x140063d43  pop     rdi
0x140063d44  pop     rsi
0x140063d45  pop     rbp
0x140063d46  pop     rbx
0x140063d47  retn
```
