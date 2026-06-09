# VmpGetGptAttributes(VM_VOLUME_EXTENSION *,_IRP *)

- ea: `0x140016ff0`
- end: `0x1400170b8`
- name: `?VmpGetGptAttributes@@YAJPEAVVM_VOLUME_EXTENSION@@PEAU_IRP@@@Z`
- size: `200`
- prototype: `__int64 __fastcall(struct VM_VOLUME_EXTENSION *, struct _IRP *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140001ae0`

## callees

- `0x140015900`
- `0x140016ff0`

## pseudocode

```c
__int64 __fastcall VmpGetGptAttributes(struct VM_VOLUME_EXTENSION *a1, struct _IRP *a2)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rax
  __int64 result; // rax
  struct _IRP *MasterIrp; // rsi
  unsigned int v7; // edx
  unsigned __int64 v8; // rax
  unsigned __int8 v9; // [rsp+38h] [rbp+10h] BYREF
  unsigned __int64 v10; // [rsp+40h] [rbp+18h] BYREF

  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  v10 = 0;
  v9 = 0;
  if ( CurrentStackLocation->Parameters.Read.Length < 8 )
    return 3221225485LL;
  if ( !*((_BYTE *)a1 + 426) )
  {
    if ( *((_QWORD *)a1 + 43) )
      goto LABEL_5;
    return 3221225486LL;
  }
  if ( !*((_QWORD *)a1 + 54) )
    return 3221225486LL;
LABEL_5:
  MasterIrp = a2->AssociatedIrp.MasterIrp;
  result = VmpGetGptAttributesInternal(a1, &v10, &v9);
  v7 = result;
  if ( (int)result >= 0 )
  {
    if ( v9 )
    {
      v8 = v10;
      if ( (*(_DWORD *)(*(_QWORD *)a1 + 48LL) & 0x100) != 0 )
        v8 = v10 & 0x7FFFFFFFFFFFFFFFLL;
      *(_QWORD *)&MasterIrp->Type = v8;
      result = v7;
      a2->IoStatus.Information = 8;
    }
    else
    {
      return 3221225485LL;
    }
  }
  return result;
}

```

## disassembly

```asm
0x140016ff0  mov     [rsp+arg_18], rbx
0x140016ff5  push    rdi
0x140016ff6  sub     rsp, 20h
0x140016ffa  mov     rax, [rdx+0B8h]
0x140017001  mov     rbx, rdx
0x140017004  mov     rdi, rcx
0x140017007  mov     [rsp+28h+arg_10], 0
0x140017010  mov     [rsp+28h+arg_8], 0
0x140017015  cmp     dword ptr [rax+8], 8
0x140017019  jnb     short loc_14001702C
0x14001701b  mov     eax, 0C000000Dh
0x140017020  mov     rbx, [rsp+28h+arg_18]
0x140017025  add     rsp, 20h
0x140017029  pop     rdi
0x14001702a  retn
0x14001702c  cmp     byte ptr [rcx+1AAh], 0
0x140017033  jnz     short loc_14001706B
0x140017035  cmp     qword ptr [rcx+158h], 0
0x14001703d  jz      short loc_140017075
0x14001703f  mov     [rsp+28h+arg_0], rsi
0x140017044  lea     r8, [rsp+28h+arg_8]; unsigned __int8 *
0x140017049  mov     rsi, [rdx+18h]
0x14001704d  lea     rdx, [rsp+28h+arg_10]; unsigned __int64 *
0x140017052  call    ?VmpGetGptAttributesInternal@@YAJPEAVVM_VOLUME_EXTENSION@@PEA_KPEAE@Z; VmpGetGptAttributesInternal(VM_VOLUME_EXTENSION *,unsigned __int64 *,uchar *)
0x140017057  mov     edx, eax
0x140017059  test    eax, eax
0x14001705b  js      short loc_1400170A7
0x14001705d  cmp     [rsp+28h+arg_8], 0
0x140017062  jnz     short loc_14001707C
0x140017064  mov     eax, 0C000000Dh
0x140017069  jmp     short loc_1400170A7
0x14001706b  cmp     qword ptr [rcx+1B0h], 0
0x140017073  jnz     short loc_14001703F
0x140017075  mov     eax, 0C000000Eh
0x14001707a  jmp     short loc_1400170AC
0x14001707c  mov     rax, [rdi]
0x14001707f  mov     ecx, [rax+30h]
0x140017082  mov     rax, [rsp+28h+arg_10]
0x140017087  bt      ecx, 8
0x14001708b  jnb     short loc_14001709A
0x14001708d  mov     rcx, 7FFFFFFFFFFFFFFFh
0x140017097  and     rax, rcx
0x14001709a  mov     [rsi], rax
0x14001709d  mov     eax, edx
0x14001709f  mov     qword ptr [rbx+38h], 8
0x1400170a7  mov     rsi, [rsp+28h+arg_0]
0x1400170ac  mov     rbx, [rsp+28h+arg_18]
0x1400170b1  add     rsp, 20h
0x1400170b5  pop     rdi
0x1400170b6  retn
```
