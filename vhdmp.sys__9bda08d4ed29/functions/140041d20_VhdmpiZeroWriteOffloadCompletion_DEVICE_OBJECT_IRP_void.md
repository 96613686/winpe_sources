# VhdmpiZeroWriteOffloadCompletion(_DEVICE_OBJECT *,_IRP *,void *)

- ea: `0x140041d20`
- end: `0x140041f39`
- name: `?VhdmpiZeroWriteOffloadCompletion@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@PEAX@Z`
- size: `537`
- prototype: `int(struct _DEVICE_OBJECT *, struct _IRP *, void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callees

- `0x140016cc0`
- `0x140023980`
- `0x140036284`
- `0x140041d20`

## import_xrefs

- `ntoskrnl!IoFreeIrp` at `0x140041f06`
- `ntoskrnl!IoFreeIrp` at `0x140041f06`
- `ntoskrnl!ExFreePoolWithTag` at `0x140041ef7`
- `ntoskrnl!ExFreePoolWithTag` at `0x140041ef7`

## string_xrefs

- `0x140041e86`: `VhdmpiZeroWriteOffloadCompletion() size too small or LengthWritten == 0: sizetoosmall: %d LengthWritten==0: %d`
- `0x140041d71`: `VhdmpiZeroWriteOffloadCompletion`
- `0x140041e17`: `VhdmpiZeroWriteOffloadCompletion`
- `0x140041e78`: `VhdmpiZeroWriteOffloadCompletion`
- `0x140041ebd`: `VhdmpiZeroWriteOffloadCompletion`
- `0x140041d88`: `VhdmpiZeroWriteOffloadCompletion() write zero token done: VDL(before update): %#016I64x Status: %08X`
- `0x140041ed5`: `VhdmpiZeroWriteOffloadCompletion() write zero token done: VDL(after update): %#016I64x Status: %08X`
- `0x140041e03`: `VhdmpiZeroWriteOffloadCompletion() increasing VDL: VDL(before update): %#016I64x LengthWritten: %#016I64x VDL(after update): %#016I64x`

## pseudocode

```c
__int64 __fastcall VhdmpiZeroWriteOffloadCompletion(struct _DEVICE_OBJECT *a1, struct _IRP *a2, _QWORD *a3)
{
  struct _IRP *MasterIrp; // rbp
  _QWORD *v6; // rbx
  NTSTATUS Status; // esi

  MasterIrp = a2->AssociatedIrp.MasterIrp;
  if ( (unsigned int)dword_1400876D0 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 2) )
  {
    v6 = a3 + 147;
    TraceEvents(
      "VhdmpiZeroWriteOffloadCompletion",
      0x13B9u,
      5u,
      2u,
      "VhdmpiZeroWriteOffloadCompletion() write zero token done: VDL(before update): %#016I64x Status: %08X",
      a3[147],
      a2->IoStatus.Status);
  }
  else
  {
    v6 = a3 + 147;
  }
  Status = a2->IoStatus.Status;
  if ( Status >= 0 )
  {
    if ( *(_DWORD *)&MasterIrp->Type >= 0x10u && MasterIrp->MdlAddress )
    {
      if ( (unsigned int)dword_1400876D0 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 2) )
      {
        v6 = a3 + 147;
        TraceEvents(
          "VhdmpiZeroWriteOffloadCompletion",
          0x13DEu,
          5u,
          2u,
          "VhdmpiZeroWriteOffloadCompletion() increasing VDL: VDL(before update): %#016I64x LengthWritten: %#016I64x VDL("
          "after update): %#016I64x",
          a3[147],
          MasterIrp->MdlAddress,
          (char *)MasterIrp->MdlAddress + a3[147]);
      }
      else
      {
        v6 = a3 + 147;
      }
      *v6 += MasterIrp->MdlAddress;
      Status = 0;
    }
    else
    {
      if ( (unsigned int)dword_1400876D0 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 2) )
        TraceEvents(
          "VhdmpiZeroWriteOffloadCompletion",
          0x13CCu,
          5u,
          2u,
          "VhdmpiZeroWriteOffloadCompletion() size too small or LengthWritten == 0: sizetoosmall: %d LengthWritten==0: %d",
          *(_DWORD *)&MasterIrp->Type < 0x10u,
          MasterIrp->MdlAddress == 0);
      Status = -1073741811;
    }
  }
  if ( (unsigned int)dword_1400876D0 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 2) )
    TraceEvents(
      "VhdmpiZeroWriteOffloadCompletion",
      0x13EEu,
      5u,
      2u,
      "VhdmpiZeroWriteOffloadCompletion() write zero token done: VDL(after update): %#016I64x Status: %08X",
      *v6,
      Status);
  *((_DWORD *)a3 + 305) = Status;
  ExFreePoolWithTag(MasterIrp, 0x66444856u);
  IoFreeIrp(a2);
  VhdmpiTriggerWorkItem(*((unsigned int *)a3 + 266), a3 + 153);
  return 3221225494LL;
}

```

## disassembly

```asm
0x140041d20  push    rbx
0x140041d22  push    rbp
0x140041d23  push    rsi
0x140041d24  push    rdi
0x140041d25  push    r12
0x140041d27  push    r14
0x140041d29  push    r15
0x140041d2b  sub     rsp, 40h
0x140041d2f  mov     eax, cs:dword_1400876D0
0x140041d35  mov     r12d, 2
0x140041d3b  mov     rbp, [rdx+18h]
0x140041d3f  mov     rdi, r8
0x140041d42  mov     r14, rdx
0x140041d45  lea     r15d, [r12+3]
0x140041d4a  cmp     eax, r15d
0x140041d4d  jbe     short loc_140041D9E
0x140041d4f  mov     edx, r12d
0x140041d52  lea     rcx, dword_1400876D0
0x140041d59  call    _tlgKeywordOn
0x140041d5e  test    al, al
0x140041d60  jz      short loc_140041D9E
0x140041d62  mov     eax, [r14+30h]
0x140041d66  lea     rbx, [r8+498h]
0x140041d6d  mov     dword ptr [rsp+78h+var_48], eax
0x140041d71  lea     rcx, aVhdmpizerowrit_1; "VhdmpiZeroWriteOffloadCompletion"
0x140041d78  mov     rax, [rbx]
0x140041d7b  mov     edx, 13B9h; int
0x140041d80  mov     qword ptr [rsp+78h+var_50], rax; char
0x140041d85  mov     r9d, r12d; int
0x140041d88  lea     rax, aVhdmpizerowrit_2; "VhdmpiZeroWriteOffloadCompletion() writ"...
0x140041d8f  mov     r8d, r15d; int
0x140041d92  mov     [rsp+78h+var_58], rax; char *
0x140041d97  call    TraceEvents
0x140041d9c  jmp     short loc_140041DA5
0x140041d9e  lea     rbx, [r8+498h]
0x140041da5  mov     esi, [r14+30h]
0x140041da9  test    esi, esi
0x140041dab  js      loc_140041E9C
0x140041db1  cmp     dword ptr [rbp+0], 10h
0x140041db5  jb      loc_140041E3C
0x140041dbb  cmp     qword ptr [rbp+8], 0
0x140041dc0  jz      short loc_140041E3C
0x140041dc2  mov     eax, cs:dword_1400876D0
0x140041dc8  cmp     eax, r15d
0x140041dcb  jbe     short loc_140041E2A
0x140041dcd  mov     rdx, r12
0x140041dd0  lea     rcx, dword_1400876D0
0x140041dd7  call    _tlgKeywordOn
0x140041ddc  test    al, al
0x140041dde  jz      short loc_140041E2A
0x140041de0  mov     rdx, [rbp+8]
0x140041de4  lea     rbx, [rdi+498h]
0x140041deb  mov     rcx, [rbx]
0x140041dee  mov     r10d, 13DEh
0x140041df4  mov     r9d, r12d; int
0x140041df7  mov     r8d, r15d; int
0x140041dfa  lea     rax, [rdx+rcx]
0x140041dfe  mov     [rsp+78h+var_40], rax
0x140041e03  lea     rax, aVhdmpizerowrit; "VhdmpiZeroWriteOffloadCompletion() incr"...
0x140041e0a  mov     [rsp+78h+var_48], rdx
0x140041e0f  mov     edx, r10d; int
0x140041e12  mov     qword ptr [rsp+78h+var_50], rcx; char
0x140041e17  lea     rcx, aVhdmpizerowrit_1; "VhdmpiZeroWriteOffloadCompletion"
0x140041e1e  mov     [rsp+78h+var_58], rax; char *
0x140041e23  call    TraceEvents
0x140041e28  jmp     short loc_140041E31
0x140041e2a  lea     rbx, [rdi+498h]
0x140041e31  mov     rax, [rbp+8]
0x140041e35  add     [rbx], rax
0x140041e38  xor     esi, esi
0x140041e3a  jmp     short loc_140041E9C
0x140041e3c  mov     eax, cs:dword_1400876D0
0x140041e42  cmp     eax, r15d
0x140041e45  jbe     short loc_140041E97
0x140041e47  mov     rdx, r12
0x140041e4a  lea     rcx, dword_1400876D0
0x140041e51  call    _tlgKeywordOn
0x140041e56  test    al, al
0x140041e58  jz      short loc_140041E97
0x140041e5a  xor     ecx, ecx
0x140041e5c  mov     edx, 13CCh; int
0x140041e61  cmp     [rbp+8], rcx
0x140041e65  mov     r9d, r12d; int
0x140041e68  mov     r8d, r15d; int
0x140041e6b  setz    cl
0x140041e6e  xor     eax, eax
0x140041e70  cmp     dword ptr [rbp+0], 10h
0x140041e74  mov     dword ptr [rsp+78h+var_48], ecx
0x140041e78  lea     rcx, aVhdmpizerowrit_1; "VhdmpiZeroWriteOffloadCompletion"
0x140041e7f  setb    al
0x140041e82  mov     dword ptr [rsp+78h+var_50], eax; char
0x140041e86  lea     rax, aVhdmpizerowrit_3; "VhdmpiZeroWriteOffloadCompletion() size"...
0x140041e8d  mov     [rsp+78h+var_58], rax; char *
0x140041e92  call    TraceEvents
0x140041e97  mov     esi, 0C000000Dh
0x140041e9c  mov     eax, cs:dword_1400876D0
0x140041ea2  cmp     eax, r15d
0x140041ea5  jbe     short loc_140041EE9
0x140041ea7  mov     rdx, r12
0x140041eaa  lea     rcx, dword_1400876D0
0x140041eb1  call    _tlgKeywordOn
0x140041eb6  test    al, al
0x140041eb8  jz      short loc_140041EE9
0x140041eba  mov     rax, [rbx]
0x140041ebd  lea     rcx, aVhdmpizerowrit_1; "VhdmpiZeroWriteOffloadCompletion"
0x140041ec4  mov     dword ptr [rsp+78h+var_48], esi
0x140041ec8  mov     edx, 13EEh; int
0x140041ecd  mov     qword ptr [rsp+78h+var_50], rax; char
0x140041ed2  mov     r9d, r12d; int
0x140041ed5  lea     rax, aVhdmpizerowrit_0; "VhdmpiZeroWriteOffloadCompletion() writ"...
0x140041edc  mov     r8d, r15d; int
0x140041edf  mov     [rsp+78h+var_58], rax; char *
0x140041ee4  call    TraceEvents
0x140041ee9  mov     edx, 66444856h; Tag
0x140041eee  mov     [rdi+4C4h], esi
0x140041ef4  mov     rcx, rbp; P
0x140041ef7  call    cs:__imp_ExFreePoolWithTag
0x140041efe  nop     dword ptr [rax+rax+00h]
0x140041f03  mov     rcx, r14; Irp
0x140041f06  call    cs:__imp_IoFreeIrp
0x140041f0d  nop     dword ptr [rax+rax+00h]
0x140041f12  mov     ecx, [rdi+428h]
0x140041f18  lea     rdx, [rdi+4C8h]
0x140041f1f  call    VhdmpiTriggerWorkItem
0x140041f24  mov     eax, 0C0000016h
0x140041f29  add     rsp, 40h
0x140041f2d  pop     r15
0x140041f2f  pop     r14
0x140041f31  pop     r12
0x140041f33  pop     rdi
0x140041f34  pop     rsi
0x140041f35  pop     rbp
0x140041f36  pop     rbx
0x140041f37  retn
```
