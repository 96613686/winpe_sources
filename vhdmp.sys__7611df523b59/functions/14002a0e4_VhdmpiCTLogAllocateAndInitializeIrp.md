# VhdmpiCTLogAllocateAndInitializeIrp

- ea: `0x14002a0e4`
- end: `0x14002a24e`
- name: `VhdmpiCTLogAllocateAndInitializeIrp`
- size: `362`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x14002c5a4`
- `0x1400a7d94`

## callees

- `0x14002a0e4`
- `0x14005dd00`

## import_xrefs

- `ntoskrnl!IoGetRelatedDeviceObject` at `0x14002a114`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x14002a114`
- `ntoskrnl!IoAllocateIrpEx` at `0x14002a15c`
- `ntoskrnl!IoAllocateIrpEx` at `0x14002a15c`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14002a229`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14002a229`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14002a12d`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14002a12d`

## pseudocode

```c
__int64 __fastcall VhdmpiCTLogAllocateAndInitializeIrp(
        __int64 a1,
        __int64 a2,
        char a3,
        __int64 a4,
        int a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        __int64 a9,
        _QWORD *a10)
{
  struct _FILE_OBJECT *v13; // r14
  struct _NPAGED_LOOKASIDE_LIST *v14; // rdi
  PDEVICE_OBJECT RelatedDeviceObject; // rsi
  _QWORD *v16; // rax
  _QWORD *v17; // rbx
  __int64 v18; // rdx
  __int64 Irp; // r8
  int v20; // ecx
  unsigned int v21; // edx
  __int64 v22; // rcx
  __int64 v23; // rcx
  __int64 v24; // rcx

  *a10 = 0;
  v13 = *(struct _FILE_OBJECT **)(a1 + 48);
  v14 = (struct _NPAGED_LOOKASIDE_LIST *)(a1 + 4224);
  RelatedDeviceObject = IoGetRelatedDeviceObject(v13);
  v16 = ExAllocateFromNPagedLookasideList(v14);
  v17 = v16;
  if ( !v16 )
    return (unsigned int)-1073741670;
  memset(v16, 0, 0x40u);
  LOBYTE(v18) = RelatedDeviceObject->StackSize;
  Irp = IoAllocateIrpEx(RelatedDeviceObject, v18, 0);
  if ( !Irp )
  {
    ExFreeToNPagedLookasideList(v14, v17);
    return (unsigned int)-1073741670;
  }
  v20 = 256;
  v21 = 0;
  if ( a3 != 3 )
    v20 = 512;
  *(_DWORD *)(Irp + 16) |= *(_DWORD *)(a1 + 80) | v20;
  v22 = VhdmpLockBackingFileThread;
  *(_QWORD *)(Irp + 8) = a7;
  *(_QWORD *)(Irp + 152) = v22;
  v23 = *(_QWORD *)(Irp + 184);
  *(_BYTE *)(Irp + 64) = 0;
  *(_QWORD *)(Irp + 192) = v13;
  *(_QWORD *)(Irp + 112) = 0;
  *(_QWORD *)(v23 - 32) = RelatedDeviceObject;
  *(_QWORD *)(v23 - 24) = v13;
  *(_BYTE *)(v23 - 72) = a3;
  *(_QWORD *)(v23 - 48) = a4;
  *(_DWORD *)(v23 - 64) = a5;
  v17[3] = a8;
  v17[5] = a9;
  v17[1] = a1;
  v17[2] = Irp;
  *v17 = 0;
  v17[4] = RelatedDeviceObject;
  v24 = *(_QWORD *)(Irp + 184);
  *(_QWORD *)(v24 - 16) = a6;
  *(_QWORD *)(v24 - 8) = v17;
  *(_BYTE *)(v24 - 69) = -32;
  *a10 = v17;
  return v21;
}

```

## disassembly

```asm
0x14002a0e4  push    rbx
0x14002a0e6  push    rbp
0x14002a0e7  push    rsi
0x14002a0e8  push    rdi
0x14002a0e9  push    r12
0x14002a0eb  push    r13
0x14002a0ed  push    r14
0x14002a0ef  push    r15
0x14002a0f1  sub     rsp, 28h
0x14002a0f5  mov     r15, [rsp+68h+arg_48]
0x14002a0fd  mov     rbp, rcx
0x14002a100  mov     r13, r9
0x14002a103  mov     r12b, r8b
0x14002a106  mov     qword ptr [r15], 0
0x14002a10d  mov     r14, [rcx+30h]
0x14002a111  mov     rcx, r14; FileObject
0x14002a114  call    cs:__imp_IoGetRelatedDeviceObject
0x14002a11b  nop     dword ptr [rax+rax+00h]
0x14002a120  lea     rdi, [rbp+1080h]
0x14002a127  mov     rsi, rax
0x14002a12a  mov     rcx, rdi; Lookaside
0x14002a12d  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x14002a134  nop     dword ptr [rax+rax+00h]
0x14002a139  mov     rbx, rax
0x14002a13c  test    rax, rax
0x14002a13f  jz      loc_14002A235
0x14002a145  xor     edx, edx; Val
0x14002a147  mov     rcx, rax; void *
0x14002a14a  lea     r8d, [rdx+40h]; Size
0x14002a14e  call    memset
0x14002a153  mov     dl, [rsi+4Ch]
0x14002a156  xor     r8d, r8d
0x14002a159  mov     rcx, rsi
0x14002a15c  call    cs:__imp_IoAllocateIrpEx
0x14002a163  nop     dword ptr [rax+rax+00h]
0x14002a168  xor     r9d, r9d
0x14002a16b  mov     r8, rax
0x14002a16e  test    rax, rax
0x14002a171  jz      loc_14002A223
0x14002a177  cmp     r12b, 3
0x14002a17b  mov     ecx, 100h
0x14002a180  mov     eax, 200h
0x14002a185  mov     edx, r9d
0x14002a188  cmovnz  ecx, eax
0x14002a18b  mov     rax, [rsp+68h+arg_30]
0x14002a193  or      ecx, [rbp+50h]
0x14002a196  or      [r8+10h], ecx
0x14002a19a  mov     rcx, cs:VhdmpLockBackingFileThread
0x14002a1a1  mov     [r8+8], rax
0x14002a1a5  mov     eax, [rsp+68h+arg_20]
0x14002a1ac  mov     [r8+98h], rcx
0x14002a1b3  mov     rcx, [r8+0B8h]
0x14002a1ba  mov     [r8+40h], r9b
0x14002a1be  mov     [r8+0C0h], r14
0x14002a1c5  mov     [r8+70h], r9
0x14002a1c9  mov     [rcx-20h], rsi
0x14002a1cd  mov     [rcx-18h], r14
0x14002a1d1  mov     [rcx-48h], r12b
0x14002a1d5  mov     [rcx-30h], r13
0x14002a1d9  mov     [rcx-40h], eax
0x14002a1dc  mov     rax, [rsp+68h+arg_38]
0x14002a1e4  mov     [rbx+18h], rax
0x14002a1e8  mov     rax, [rsp+68h+arg_40]
0x14002a1f0  mov     [rbx+28h], rax
0x14002a1f4  mov     rax, [rsp+68h+arg_28]
0x14002a1fc  mov     [rbx+8], rbp
0x14002a200  mov     [rbx+10h], r8
0x14002a204  mov     [rbx], r9
0x14002a207  mov     [rbx+20h], rsi
0x14002a20b  mov     rcx, [r8+0B8h]
0x14002a212  mov     [rcx-10h], rax
0x14002a216  mov     [rcx-8], rbx
0x14002a21a  mov     byte ptr [rcx-45h], 0E0h
0x14002a21e  mov     [r15], rbx
0x14002a221  jmp     short loc_14002A23A
0x14002a223  mov     rdx, rbx; Entry
0x14002a226  mov     rcx, rdi; Lookaside
0x14002a229  call    cs:__imp_ExFreeToNPagedLookasideList
0x14002a230  nop     dword ptr [rax+rax+00h]
0x14002a235  mov     edx, 0C000009Ah
0x14002a23a  mov     eax, edx
0x14002a23c  add     rsp, 28h
0x14002a240  pop     r15
0x14002a242  pop     r14
0x14002a244  pop     r13
0x14002a246  pop     r12
0x14002a248  pop     rdi
0x14002a249  pop     rsi
0x14002a24a  pop     rbp
0x14002a24b  pop     rbx
0x14002a24c  retn
```
