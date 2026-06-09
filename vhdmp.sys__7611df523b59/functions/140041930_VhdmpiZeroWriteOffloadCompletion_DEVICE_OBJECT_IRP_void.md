# VhdmpiZeroWriteOffloadCompletion(_DEVICE_OBJECT *,_IRP *,void *)

- ea: `0x140041930`
- end: `0x140041b49`
- name: `?VhdmpiZeroWriteOffloadCompletion@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@PEAX@Z`
- size: `537`
- prototype: `int(struct _DEVICE_OBJECT *, struct _IRP *, void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callees

- `0x140016820`
- `0x140023560`
- `0x140035e94`
- `0x140041930`

## import_xrefs

- `ntoskrnl!IoFreeIrp` at `0x140041b16`
- `ntoskrnl!IoFreeIrp` at `0x140041b16`
- `ntoskrnl!ExFreePoolWithTag` at `0x140041b07`
- `ntoskrnl!ExFreePoolWithTag` at `0x140041b07`

## string_xrefs

- `0x140041a13`: `VhdmpiZeroWriteOffloadCompletion() increasing VDL: VDL(before update): %#016I64x LengthWritten: %#016I64x VDL(after update): %#016I64x`
- `0x140041a96`: `VhdmpiZeroWriteOffloadCompletion() size too small or LengthWritten == 0: sizetoosmall: %d LengthWritten==0: %d`
- `0x140041981`: `VhdmpiZeroWriteOffloadCompletion`
- `0x140041a27`: `VhdmpiZeroWriteOffloadCompletion`
- `0x140041a88`: `VhdmpiZeroWriteOffloadCompletion`
- `0x140041acd`: `VhdmpiZeroWriteOffloadCompletion`
- `0x140041998`: `VhdmpiZeroWriteOffloadCompletion() write zero token done: VDL(before update): %#016I64x Status: %08X`
- `0x140041ae5`: `VhdmpiZeroWriteOffloadCompletion() write zero token done: VDL(after update): %#016I64x Status: %08X`

## pseudocode

```c
__int64 __fastcall VhdmpiZeroWriteOffloadCompletion(struct _DEVICE_OBJECT *a1, struct _IRP *a2, _QWORD *a3)
{
  struct _IRP *MasterIrp; // rbp
  _QWORD *v6; // rbx
  NTSTATUS Status; // esi

  MasterIrp = a2->AssociatedIrp.MasterIrp;
  if ( (unsigned int)dword_140087708 > 5 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 2) )
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
      if ( (unsigned int)dword_140087708 > 5 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 2) )
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
      if ( (unsigned int)dword_140087708 > 5 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 2) )
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
  if ( (unsigned int)dword_140087708 > 5 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 2) )
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
0x140041930  push    rbx
0x140041932  push    rbp
0x140041933  push    rsi
0x140041934  push    rdi
0x140041935  push    r12
0x140041937  push    r14
0x140041939  push    r15
0x14004193b  sub     rsp, 40h
0x14004193f  mov     eax, cs:dword_140087708
0x140041945  mov     r12d, 2
0x14004194b  mov     rbp, [rdx+18h]
0x14004194f  mov     rdi, r8
0x140041952  mov     r14, rdx
0x140041955  lea     r15d, [r12+3]
0x14004195a  cmp     eax, r15d
0x14004195d  jbe     short loc_1400419AE
0x14004195f  mov     edx, r12d
0x140041962  lea     rcx, dword_140087708
0x140041969  call    _tlgKeywordOn
0x14004196e  test    al, al
0x140041970  jz      short loc_1400419AE
0x140041972  mov     eax, [r14+30h]
0x140041976  lea     rbx, [r8+498h]
0x14004197d  mov     dword ptr [rsp+78h+var_48], eax
0x140041981  lea     rcx, aVhdmpizerowrit_1; "VhdmpiZeroWriteOffloadCompletion"
0x140041988  mov     rax, [rbx]
0x14004198b  mov     edx, 13B9h; int
0x140041990  mov     qword ptr [rsp+78h+var_50], rax; char
0x140041995  mov     r9d, r12d; int
0x140041998  lea     rax, aVhdmpizerowrit_2; "VhdmpiZeroWriteOffloadCompletion() writ"...
0x14004199f  mov     r8d, r15d; int
0x1400419a2  mov     [rsp+78h+var_58], rax; char *
0x1400419a7  call    TraceEvents
0x1400419ac  jmp     short loc_1400419B5
0x1400419ae  lea     rbx, [r8+498h]
0x1400419b5  mov     esi, [r14+30h]
0x1400419b9  test    esi, esi
0x1400419bb  js      loc_140041AAC
0x1400419c1  cmp     dword ptr [rbp+0], 10h
0x1400419c5  jb      loc_140041A4C
0x1400419cb  cmp     qword ptr [rbp+8], 0
0x1400419d0  jz      short loc_140041A4C
0x1400419d2  mov     eax, cs:dword_140087708
0x1400419d8  cmp     eax, r15d
0x1400419db  jbe     short loc_140041A3A
0x1400419dd  mov     rdx, r12
0x1400419e0  lea     rcx, dword_140087708
0x1400419e7  call    _tlgKeywordOn
0x1400419ec  test    al, al
0x1400419ee  jz      short loc_140041A3A
0x1400419f0  mov     rdx, [rbp+8]
0x1400419f4  lea     rbx, [rdi+498h]
0x1400419fb  mov     rcx, [rbx]
0x1400419fe  mov     r10d, 13DEh
0x140041a04  mov     r9d, r12d; int
0x140041a07  mov     r8d, r15d; int
0x140041a0a  lea     rax, [rdx+rcx]
0x140041a0e  mov     [rsp+78h+var_40], rax
0x140041a13  lea     rax, aVhdmpizerowrit; "VhdmpiZeroWriteOffloadCompletion() incr"...
0x140041a1a  mov     [rsp+78h+var_48], rdx
0x140041a1f  mov     edx, r10d; int
0x140041a22  mov     qword ptr [rsp+78h+var_50], rcx; char
0x140041a27  lea     rcx, aVhdmpizerowrit_1; "VhdmpiZeroWriteOffloadCompletion"
0x140041a2e  mov     [rsp+78h+var_58], rax; char *
0x140041a33  call    TraceEvents
0x140041a38  jmp     short loc_140041A41
0x140041a3a  lea     rbx, [rdi+498h]
0x140041a41  mov     rax, [rbp+8]
0x140041a45  add     [rbx], rax
0x140041a48  xor     esi, esi
0x140041a4a  jmp     short loc_140041AAC
0x140041a4c  mov     eax, cs:dword_140087708
0x140041a52  cmp     eax, r15d
0x140041a55  jbe     short loc_140041AA7
0x140041a57  mov     rdx, r12
0x140041a5a  lea     rcx, dword_140087708
0x140041a61  call    _tlgKeywordOn
0x140041a66  test    al, al
0x140041a68  jz      short loc_140041AA7
0x140041a6a  xor     ecx, ecx
0x140041a6c  mov     edx, 13CCh; int
0x140041a71  cmp     [rbp+8], rcx
0x140041a75  mov     r9d, r12d; int
0x140041a78  mov     r8d, r15d; int
0x140041a7b  setz    cl
0x140041a7e  xor     eax, eax
0x140041a80  cmp     dword ptr [rbp+0], 10h
0x140041a84  mov     dword ptr [rsp+78h+var_48], ecx
0x140041a88  lea     rcx, aVhdmpizerowrit_1; "VhdmpiZeroWriteOffloadCompletion"
0x140041a8f  setb    al
0x140041a92  mov     dword ptr [rsp+78h+var_50], eax; char
0x140041a96  lea     rax, aVhdmpizerowrit_3; "VhdmpiZeroWriteOffloadCompletion() size"...
0x140041a9d  mov     [rsp+78h+var_58], rax; char *
0x140041aa2  call    TraceEvents
0x140041aa7  mov     esi, 0C000000Dh
0x140041aac  mov     eax, cs:dword_140087708
0x140041ab2  cmp     eax, r15d
0x140041ab5  jbe     short loc_140041AF9
0x140041ab7  mov     rdx, r12
0x140041aba  lea     rcx, dword_140087708
0x140041ac1  call    _tlgKeywordOn
0x140041ac6  test    al, al
0x140041ac8  jz      short loc_140041AF9
0x140041aca  mov     rax, [rbx]
0x140041acd  lea     rcx, aVhdmpizerowrit_1; "VhdmpiZeroWriteOffloadCompletion"
0x140041ad4  mov     dword ptr [rsp+78h+var_48], esi
0x140041ad8  mov     edx, 13EEh; int
0x140041add  mov     qword ptr [rsp+78h+var_50], rax; char
0x140041ae2  mov     r9d, r12d; int
0x140041ae5  lea     rax, aVhdmpizerowrit_0; "VhdmpiZeroWriteOffloadCompletion() writ"...
0x140041aec  mov     r8d, r15d; int
0x140041aef  mov     [rsp+78h+var_58], rax; char *
0x140041af4  call    TraceEvents
0x140041af9  mov     edx, 66444856h; Tag
0x140041afe  mov     [rdi+4C4h], esi
0x140041b04  mov     rcx, rbp; P
0x140041b07  call    cs:__imp_ExFreePoolWithTag
0x140041b0e  nop     dword ptr [rax+rax+00h]
0x140041b13  mov     rcx, r14; Irp
0x140041b16  call    cs:__imp_IoFreeIrp
0x140041b1d  nop     dword ptr [rax+rax+00h]
0x140041b22  mov     ecx, [rdi+428h]
0x140041b28  lea     rdx, [rdi+4C8h]
0x140041b2f  call    VhdmpiTriggerWorkItem
0x140041b34  mov     eax, 0C0000016h
0x140041b39  add     rsp, 40h
0x140041b3d  pop     r15
0x140041b3f  pop     r14
0x140041b41  pop     r12
0x140041b43  pop     rdi
0x140041b44  pop     rsi
0x140041b45  pop     rbp
0x140041b46  pop     rbx
0x140041b47  retn
```
