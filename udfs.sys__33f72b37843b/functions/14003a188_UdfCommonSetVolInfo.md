# UdfCommonSetVolInfo

- ea: `0x14003a188`
- end: `0x14003a26c`
- name: `UdfCommonSetVolInfo`
- size: `228`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1400077f0`
- `0x1400094c0`

## callees

- `0x1400030e0`
- `0x14003a188`
- `0x14003a274`
- `0x1400444c4`
- `0x14004ce50`
- `0x140054460`

## import_xrefs

- `ntoskrnl!ExReleaseResourceLite` at `0x14003a25b`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005c241`
- `ntoskrnl!ExReleaseResourceLite` at `0x14003a25b`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005c241`

## pseudocode

```c
__int64 __fastcall UdfCommonSetVolInfo(_QWORD *a1, IRP *a2)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // r14
  __int64 v5; // rbx
  struct _IRP *MasterIrp; // r12
  unsigned int v7; // ebx
  int v9; // eax
  struct _ERESOURCE *v10; // r15
  __int64 v11; // r8
  __int64 v12; // [rsp+50h] [rbp+8h] BYREF
  char v13; // [rsp+58h] [rbp+10h] BYREF

  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  v5 = a1[2];
  MasterIrp = a2->AssociatedIrp.MasterIrp;
  if ( (unsigned int)UdfDecodeFileObject(CurrentStackLocation->FileObject, &v13, &v12) == 2 )
  {
    v12 = v5;
    v9 = *(_DWORD *)(v5 + 48);
    if ( (v9 & 0x10) != 0 )
    {
      if ( (v9 & 0x80u) == 0 )
        v7 = (v9 & 0x20) != 0 ? -1073739770 : -1073741790;
      else
        v7 = -1073741662;
    }
    else
    {
      v10 = (struct _ERESOURCE *)(v5 + 1480);
      UdfAcquireResource(a1, v5 + 1480, 0, 0);
      UdfVerifyVcb(a1, v5, v11);
      if ( CurrentStackLocation->Parameters.Create.Options == 2 )
        v7 = UdfSetFsLabelInfo(a1, MasterIrp);
      else
        v7 = -1073741811;
      ExReleaseResourceLite(v10);
    }
  }
  else
  {
    v7 = -1073741811;
  }
  UdfCompleteRequest(a1, a2, v7);
  return v7;
}

```

## disassembly

```asm
0x14003a188  mov     [rsp+arg_10], rbx
0x14003a18d  push    rsi
0x14003a18e  push    rdi
0x14003a18f  push    r12
0x14003a191  push    r14
0x14003a193  push    r15
0x14003a195  sub     rsp, 20h
0x14003a199  mov     rsi, rdx
0x14003a19c  mov     rdi, rcx
0x14003a19f  mov     r14, [rdx+0B8h]
0x14003a1a6  mov     rbx, [rcx+10h]
0x14003a1aa  mov     r12, [rdx+18h]
0x14003a1ae  lea     r8, [rsp+48h+arg_0]
0x14003a1b3  lea     rdx, [rsp+48h+arg_8]
0x14003a1b8  mov     rcx, [r14+30h]
0x14003a1bc  call    UdfDecodeFileObject
0x14003a1c1  cmp     eax, 2
0x14003a1c4  jz      short loc_14003A1EE
0x14003a1c6  mov     ebx, 0C000000Dh
0x14003a1cb  mov     r8d, ebx
0x14003a1ce  mov     rdx, rsi
0x14003a1d1  mov     rcx, rdi
0x14003a1d4  call    UdfCompleteRequest
0x14003a1d9  mov     eax, ebx
0x14003a1db  mov     rbx, [rsp+48h+arg_10]
0x14003a1e0  add     rsp, 20h
0x14003a1e4  pop     r15
0x14003a1e6  pop     r14
0x14003a1e8  pop     r12
0x14003a1ea  pop     rdi
0x14003a1eb  pop     rsi
0x14003a1ec  retn
0x14003a1ee  mov     [rsp+48h+arg_0], rbx
0x14003a1f3  mov     eax, [rbx+30h]
0x14003a1f6  test    al, 10h
0x14003a1f8  jz      short loc_14003A219
0x14003a1fa  test    al, al
0x14003a1fc  jns     short loc_14003A205
0x14003a1fe  mov     ebx, 0C00000A2h
0x14003a203  jmp     short loc_14003A1CB
0x14003a205  and     al, 20h
0x14003a207  neg     al
0x14003a209  sbb     ebx, ebx
0x14003a20b  and     ebx, 7E4h
0x14003a211  add     ebx, 0C0000022h
0x14003a217  jmp     short loc_14003A1CB
0x14003a219  lea     r15, [rbx+5C8h]
0x14003a220  xor     r9d, r9d
0x14003a223  xor     r8d, r8d
0x14003a226  mov     rdx, r15
0x14003a229  mov     rcx, rdi
0x14003a22c  call    UdfAcquireResource
0x14003a231  nop
0x14003a232  mov     rdx, rbx
0x14003a235  mov     rcx, rdi
0x14003a238  call    UdfVerifyVcb
0x14003a23d  cmp     dword ptr [r14+10h], 2
0x14003a242  jz      short loc_14003A24B
0x14003a244  mov     ebx, 0C000000Dh
0x14003a249  jmp     short loc_14003A258
0x14003a24b  mov     rdx, r12
0x14003a24e  mov     rcx, rdi
0x14003a251  call    UdfSetFsLabelInfo
0x14003a256  mov     ebx, eax
0x14003a258  mov     rcx, r15; Resource
0x14003a25b  call    cs:__imp_ExReleaseResourceLite
0x14003a262  nop     dword ptr [rax+rax+00h]
0x14003a267  jmp     loc_14003A1CB
0x14005c22d  push    rbp
0x14005c22f  sub     rsp, 20h
0x14005c233  mov     rbp, rdx
0x14005c236  mov     rcx, [rbp+50h]
0x14005c23a  add     rcx, 5C8h; Resource
0x14005c241  call    cs:__imp_ExReleaseResourceLite
0x14005c248  nop     dword ptr [rax+rax+00h]
0x14005c24d  nop
0x14005c24e  add     rsp, 20h
0x14005c252  pop     rbp
0x14005c253  retn
```
