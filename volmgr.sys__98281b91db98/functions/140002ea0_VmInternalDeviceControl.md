# VmInternalDeviceControl

- ea: `0x140002ea0`
- end: `0x140002ff7`
- name: `VmInternalDeviceControl`
- size: `343`
- prototype: `__int64 __fastcall(__int64, struct _IRP *)`
- caller_count: `0`
- callee_count: `13`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x140002ea0`
- `0x140003000`
- `0x140011e00`
- `0x140012508`
- `0x1400127f0`
- `0x1400129d0`
- `0x140012b3c`
- `0x140012eac`
- `0x140013594`
- `0x1400136b8`
- `0x1400139b4`
- `0x14001462c`
- `0x140014838`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x140002ed0`
- `ntoskrnl!IofCompleteRequest` at `0x140002ed0`

## pseudocode

```c
__int64 __fastcall VmInternalDeviceControl(__int64 a1, struct _IRP *a2)
{
  __int64 v2; // rax
  struct VM_ROOT_EXTENSION *v4; // rcx
  unsigned int v5; // edi
  __int64 result; // rax
  unsigned int LowPart; // edx

  v2 = *(_QWORD *)(a1 + 64);
  v4 = *(struct VM_ROOT_EXTENSION **)(v2 + 8);
  a2->IoStatus.Information = 0;
  if ( *(_DWORD *)(v2 + 16) )
  {
    v5 = -1073741808;
    a2->IoStatus.Status = -1073741808;
LABEL_3:
    IofCompleteRequest(a2, 0);
    return v5;
  }
  LowPart = a2->Tail.Overlay.CurrentStackLocation->Parameters.Read.ByteOffset.LowPart;
  if ( LowPart == 7733272 )
  {
LABEL_5:
    v5 = 0;
    goto LABEL_6;
  }
  if ( LowPart == 7733288 )
  {
    result = VmpSetPowerState(v4, a2);
  }
  else
  {
    if ( LowPart > 0x760640 )
    {
LABEL_25:
      v5 = -1073741808;
      goto LABEL_6;
    }
    if ( LowPart != 7734848 )
    {
      switch ( LowPart )
      {
        case 0x760000u:
          result = VmpPartitionArrived(v4, a2);
          goto LABEL_9;
        case 0x760004u:
          result = VmpPartitionRemoved(v4, a2);
          goto LABEL_9;
        case 0x760008u:
          result = VmpWholeDiskRemoved(v4, a2);
          goto LABEL_9;
        case 0x76000Cu:
          result = VmpReferenceDependantVolume(v4, a2);
          goto LABEL_9;
        case 0x76001Cu:
          goto LABEL_5;
        case 0x760020u:
          result = VmpPartitionChanged(v4, a2);
          goto LABEL_9;
        case 0x760024u:
          result = VmpPmWmiCounterLibContext(v4, a2);
          goto LABEL_9;
        case 0x76002Cu:
          result = VmpWholeDiskArrived(v4, a2);
          goto LABEL_9;
        case 0x760030u:
          result = VmpIsRedirectionSupported(v4, a2);
          goto LABEL_9;
        case 0x760034u:
          result = VmpRedirectRequest(v4, a2);
          goto LABEL_9;
        case 0x760038u:
          result = VmpQueryVetoQueryRemove(v4, a2);
          goto LABEL_9;
        default:
          goto LABEL_25;
      }
    }
    result = VmpExtensionDriverStarted(v4, a2);
  }
LABEL_9:
  v5 = result;
  if ( (_DWORD)result != 259 )
  {
LABEL_6:
    a2->IoStatus.Status = v5;
    goto LABEL_3;
  }
  return result;
}

```

## disassembly

```asm
0x140002ea0  mov     [rsp+arg_0], rbx
0x140002ea5  push    rdi
0x140002ea6  sub     rsp, 20h
0x140002eaa  mov     rax, [rcx+40h]
0x140002eae  mov     rbx, rdx
0x140002eb1  mov     rcx, [rax+8]; struct VM_ROOT_EXTENSION *
0x140002eb5  mov     qword ptr [rdx+38h], 0
0x140002ebd  cmp     dword ptr [rax+10h], 0
0x140002ec1  jz      short loc_140002EEA
0x140002ec3  mov     edi, 0C0000010h
0x140002ec8  mov     [rdx+30h], edi
0x140002ecb  xor     edx, edx; PriorityBoost
0x140002ecd  mov     rcx, rbx; Irp
0x140002ed0  call    cs:__imp_IofCompleteRequest
0x140002ed7  nop     dword ptr [rax+rax+00h]
0x140002edc  mov     eax, edi
0x140002ede  mov     rbx, [rsp+28h+arg_0]
0x140002ee3  add     rsp, 20h
0x140002ee7  pop     rdi
0x140002ee8  retn
0x140002eea  mov     rax, [rdx+0B8h]
0x140002ef1  mov     edx, [rax+18h]
0x140002ef4  cmp     edx, 760018h
0x140002efa  jnz     short loc_140002F03
0x140002efc  xor     edi, edi; jumptable 0000000140002F64 case 7733276
0x140002efe  mov     [rbx+30h], edi
0x140002f01  jmp     short loc_140002ECB
0x140002f03  cmp     edx, 760028h
0x140002f09  jnz     short loc_140002F28
0x140002f0b  mov     rdx, rbx; struct _IRP *
0x140002f0e  call    ?VmpSetPowerState@@YAJPEAVVM_ROOT_EXTENSION@@PEAU_IRP@@@Z; VmpSetPowerState(VM_ROOT_EXTENSION *,_IRP *)
0x140002f13  mov     edi, eax
0x140002f15  cmp     eax, 103h
0x140002f1a  jnz     short loc_140002EFE
0x140002f1c  mov     rbx, [rsp+28h+arg_0]
0x140002f21  add     rsp, 20h
0x140002f25  pop     rdi
0x140002f26  retn
0x140002f28  cmp     edx, 760640h
0x140002f2e  ja      def_140002F64; jumptable 0000000140002F64 default case, cases 7733249-7733251,7733253-7733255,7733257-7733259,7733261-7733275,7733277-7733279,7733281-7733283,7733285-7733291,7733293-7733295,7733297-7733299,7733301-7733303
0x140002f34  jz      loc_140002FE0
0x140002f3a  add     edx, 0FF8A0000h; switch 57 cases
0x140002f40  cmp     edx, 38h
0x140002f43  ja      def_140002F64; jumptable 0000000140002F64 default case, cases 7733249-7733251,7733253-7733255,7733257-7733259,7733261-7733275,7733277-7733279,7733281-7733283,7733285-7733291,7733293-7733295,7733297-7733299,7733301-7733303
0x140002f49  lea     r8, cs:140000000h
0x140002f50  movzx   eax, ds:(byte_140007C68 - 140000000h)[r8+rdx]
0x140002f59  mov     edx, ds:(jpt_140002F64 - 140000000h)[r8+rax*4]
0x140002f61  add     rdx, r8
0x140002f64  jmp     rdx; switch jump
0x140002f6a  mov     rdx, rbx; jumptable 0000000140002F64 case 7733292
0x140002f6d  call    ?VmpWholeDiskArrived@@YAJPEAVVM_ROOT_EXTENSION@@PEAU_IRP@@@Z; VmpWholeDiskArrived(VM_ROOT_EXTENSION *,_IRP *)
0x140002f72  jmp     short loc_140002F13
0x140002f74  mov     rdx, rbx; jumptable 0000000140002F64 case 7733248
0x140002f77  call    ?VmpPartitionArrived@@YAJPEAVVM_ROOT_EXTENSION@@PEAU_IRP@@@Z; VmpPartitionArrived(VM_ROOT_EXTENSION *,_IRP *)
0x140002f7c  jmp     short loc_140002F13
0x140002f7e  mov     rdx, rbx; jumptable 0000000140002F64 case 7733252
0x140002f81  call    ?VmpPartitionRemoved@@YAJPEAVVM_ROOT_EXTENSION@@PEAU_IRP@@@Z; VmpPartitionRemoved(VM_ROOT_EXTENSION *,_IRP *)
0x140002f86  jmp     short loc_140002F13
0x140002f88  mov     rdx, rbx; jumptable 0000000140002F64 case 7733256
0x140002f8b  call    ?VmpWholeDiskRemoved@@YAJPEAVVM_ROOT_EXTENSION@@PEAU_IRP@@@Z; VmpWholeDiskRemoved(VM_ROOT_EXTENSION *,_IRP *)
0x140002f90  jmp     short loc_140002F13
0x140002f92  mov     rdx, rbx; jumptable 0000000140002F64 case 7733280
0x140002f95  call    ?VmpPartitionChanged@@YAJPEAVVM_ROOT_EXTENSION@@PEAU_IRP@@@Z; VmpPartitionChanged(VM_ROOT_EXTENSION *,_IRP *)
0x140002f9a  jmp     loc_140002F13
0x140002f9f  mov     rdx, rbx; jumptable 0000000140002F64 case 7733260
0x140002fa2  call    ?VmpReferenceDependantVolume@@YAJPEAVVM_ROOT_EXTENSION@@PEAU_IRP@@@Z; VmpReferenceDependantVolume(VM_ROOT_EXTENSION *,_IRP *)
0x140002fa7  jmp     loc_140002F13
0x140002fac  mov     rdx, rbx; jumptable 0000000140002F64 case 7733304
0x140002faf  call    ?VmpQueryVetoQueryRemove@@YAJPEAVVM_ROOT_EXTENSION@@PEAU_IRP@@@Z; VmpQueryVetoQueryRemove(VM_ROOT_EXTENSION *,_IRP *)
0x140002fb4  jmp     loc_140002F13
0x140002fb9  mov     rdx, rbx; jumptable 0000000140002F64 case 7733296
0x140002fbc  call    ?VmpIsRedirectionSupported@@YAJPEAVVM_ROOT_EXTENSION@@PEAU_IRP@@@Z; VmpIsRedirectionSupported(VM_ROOT_EXTENSION *,_IRP *)
0x140002fc1  jmp     loc_140002F13
0x140002fc6  mov     rdx, rbx; jumptable 0000000140002F64 case 7733300
0x140002fc9  call    ?VmpRedirectRequest@@YAJPEAVVM_ROOT_EXTENSION@@PEAU_IRP@@@Z; VmpRedirectRequest(VM_ROOT_EXTENSION *,_IRP *)
0x140002fce  jmp     loc_140002F13
0x140002fd3  mov     rdx, rbx; jumptable 0000000140002F64 case 7733284
0x140002fd6  call    ?VmpPmWmiCounterLibContext@@YAJPEAVVM_ROOT_EXTENSION@@PEAU_IRP@@@Z; VmpPmWmiCounterLibContext(VM_ROOT_EXTENSION *,_IRP *)
0x140002fdb  jmp     loc_140002F13
0x140002fe0  mov     rdx, rbx; struct _IRP *
0x140002fe3  call    ?VmpExtensionDriverStarted@@YAJPEAVVM_ROOT_EXTENSION@@PEAU_IRP@@@Z; VmpExtensionDriverStarted(VM_ROOT_EXTENSION *,_IRP *)
0x140002fe8  jmp     loc_140002F13
0x140002fed  mov     edi, 0C0000010h; jumptable 0000000140002F64 default case, cases 7733249-7733251,7733253-7733255,7733257-7733259,7733261-7733275,7733277-7733279,7733281-7733283,7733285-7733291,7733293-7733295,7733297-7733299,7733301-7733303
0x140002ff2  jmp     loc_140002EFE
```
