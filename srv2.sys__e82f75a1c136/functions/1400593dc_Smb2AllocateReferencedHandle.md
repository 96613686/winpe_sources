# Smb2AllocateReferencedHandle

- ea: `0x1400593dc`
- end: `0x1400594e7`
- name: `Smb2AllocateReferencedHandle`
- size: `267`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x14000f060`
- `0x140063dd4`
- `0x1400664c4`
- `0x140075bb8`
- `0x14007a84c`
- `0x140081d90`

## callees

- `0x1400593dc`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140059414`
- `ntoskrnl!ExAllocatePool2` at `0x140059414`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140059496`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140059496`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400594ae`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400594ae`
- `ntoskrnl!IoSetFileOrigin` at `0x1400594c4`
- `ntoskrnl!IoSetFileOrigin` at `0x1400594c4`

## pseudocode

```c
PVOID *__fastcall Smb2AllocateReferencedHandle(__int64 a1, void *a2, struct _OBJECT_HANDLE_INFORMATION *a3)
{
  __int64 Pool2; // rax
  PVOID *v7; // rbx
  PFILE_OBJECT *v9; // rdi
  _QWORD *v10; // rax
  struct _OBJECT_HANDLE_INFORMATION *HandleInformation; // rax
  __int64 v12; // [rsp+68h] [rbp+20h] BYREF

  v12 = 0;
  Pool2 = ExAllocatePool2(64, 160, 1647465292);
  v7 = (PVOID *)Pool2;
  if ( !Pool2 )
    return 0;
  *(_QWORD *)Pool2 = 1;
  *(_DWORD *)(Pool2 + 8) = 6;
  *(_DWORD *)(Pool2 + 12) = 220;
  *(_WORD *)(Pool2 + 16) = 160;
  *(_QWORD *)(Pool2 + 48) = 0;
  *(_QWORD *)(Pool2 + 56) = Pool2;
  *(_QWORD *)(Pool2 + 64) = a1;
  v9 = (PFILE_OBJECT *)(Pool2 + 96);
  *(_DWORD *)(Pool2 + 72) = 0;
  *(_QWORD *)(Pool2 + 88) = a2;
  v10 = (_QWORD *)(Pool2 + 136);
  v10[1] = v10;
  *v10 = v10;
  HandleInformation = (struct _OBJECT_HANDLE_INFORMATION *)&v12;
  if ( a3 )
    HandleInformation = a3;
  if ( ObReferenceObjectByHandle(a2, 0, 0, 0, v7 + 12, HandleInformation) < 0 )
  {
    ExFreePoolWithTag(v7, 0x6232534Cu);
    return 0;
  }
  IoSetFileOrigin(*v9, 1u);
  return v7;
}

```

## disassembly

```asm
0x1400593dc  mov     [rsp+arg_0], rbx
0x1400593e1  mov     [rsp+arg_8], rbp
0x1400593e6  push    rsi
0x1400593e7  push    rdi
0x1400593e8  push    r12
0x1400593ea  sub     rsp, 30h
0x1400593ee  mov     r12d, 0A0h
0x1400593f4  mov     [rsp+48h+arg_18], 0
0x1400593fd  mov     rsi, r8
0x140059400  mov     rbp, rdx
0x140059403  mov     rdi, rcx
0x140059406  mov     r8d, 6232534Ch
0x14005940c  mov     edx, r12d
0x14005940f  lea     ecx, [r12-60h]
0x140059414  call    cs:__imp_ExAllocatePool2
0x14005941b  nop     dword ptr [rax+rax+00h]
0x140059420  mov     rbx, rax
0x140059423  test    rax, rax
0x140059426  jnz     short loc_14005942F
0x140059428  xor     eax, eax
0x14005942a  jmp     loc_1400594D3
0x14005942f  mov     qword ptr [rax], 1
0x140059436  mov     rcx, rbp; Handle
0x140059439  mov     dword ptr [rax+8], 6
0x140059440  mov     dword ptr [rax+0Ch], 0DCh
0x140059447  mov     [rax+10h], r12w
0x14005944c  mov     qword ptr [rax+30h], 0
0x140059454  mov     [rax+38h], rbx
0x140059458  mov     [rax+40h], rdi
0x14005945c  lea     rdi, [rbx+60h]
0x140059460  mov     dword ptr [rax+48h], 0
0x140059467  mov     [rax+58h], rbp
0x14005946b  add     rax, 88h
0x140059471  test    rsi, rsi
0x140059474  mov     [rax+8], rax
0x140059478  mov     [rax], rax
0x14005947b  lea     rax, [rsp+48h+arg_18]
0x140059480  cmovnz  rax, rsi
0x140059484  xor     r9d, r9d; AccessMode
0x140059487  mov     [rsp+48h+HandleInformation], rax; HandleInformation
0x14005948c  xor     r8d, r8d; ObjectType
0x14005948f  xor     edx, edx; DesiredAccess
0x140059491  mov     [rsp+48h+Object], rdi; Object
0x140059496  call    cs:__imp_ObReferenceObjectByHandle
0x14005949d  nop     dword ptr [rax+rax+00h]
0x1400594a2  test    eax, eax
0x1400594a4  jns     short loc_1400594BF
0x1400594a6  mov     edx, 6232534Ch; Tag
0x1400594ab  mov     rcx, rbx; P
0x1400594ae  call    cs:__imp_ExFreePoolWithTag
0x1400594b5  nop     dword ptr [rax+rax+00h]
0x1400594ba  jmp     loc_140059428
0x1400594bf  mov     rcx, [rdi]; FileObject
0x1400594c2  mov     dl, 1; Remote
0x1400594c4  call    cs:__imp_IoSetFileOrigin
0x1400594cb  nop     dword ptr [rax+rax+00h]
0x1400594d0  mov     rax, rbx
0x1400594d3  mov     rbx, [rsp+48h+arg_0]
0x1400594d8  mov     rbp, [rsp+48h+arg_8]
0x1400594dd  add     rsp, 30h
0x1400594e1  pop     r12
0x1400594e3  pop     rdi
0x1400594e4  pop     rsi
0x1400594e5  retn
```
