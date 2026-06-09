# VmpQueryId(VM_VOLUME_EXTENSION *,_IRP *)

- ea: `0x140015f70`
- end: `0x140016008`
- name: `?VmpQueryId@@YAJPEAVVM_VOLUME_EXTENSION@@PEAU_IRP@@@Z`
- size: `152`
- prototype: `__int64 __fastcall(struct VM_VOLUME_EXTENSION *, struct _IRP *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x140016aa0`

## callees

- `0x14000e6dc`
- `0x140012fa0`
- `0x140015f70`
- `0x140016010`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140015fee`
- `ntoskrnl!ExFreePoolWithTag` at `0x140015fee`

## pseudocode

```c
__int64 __fastcall VmpQueryId(struct VM_VOLUME_EXTENSION *a1, struct _IRP *a2)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rax
  ULONG Length; // r8d
  ULONG v5; // r8d
  int InstanceId; // eax
  unsigned int v8; // ebx
  PVOID P; // [rsp+38h] [rbp+10h] BYREF

  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  P = 0;
  Length = CurrentStackLocation->Parameters.Read.Length;
  if ( Length == 3 )
  {
    InstanceId = VmpQueryInstanceId(a1, (unsigned __int16 **)&P);
  }
  else if ( Length && (v5 = Length - 1) != 0 )
  {
    if ( v5 != 4 )
      return 3221225659LL;
    InstanceId = VmpQueryContainerId(a1, (unsigned __int16 **)&P);
  }
  else
  {
    InstanceId = VmpQueryDeviceId(a1, (unsigned __int16 **)&P);
  }
  v8 = InstanceId;
  if ( InstanceId < 0 )
  {
    if ( P )
      ExFreePoolWithTag(P, 0);
  }
  else
  {
    a2->IoStatus.Information = (ULONG_PTR)P;
  }
  return v8;
}

```

## disassembly

```asm
0x140015f70  mov     [rsp+arg_0], rbx
0x140015f75  push    rdi
0x140015f76  sub     rsp, 20h
0x140015f7a  mov     rax, [rdx+0B8h]
0x140015f81  mov     rdi, rdx
0x140015f84  mov     [rsp+28h+P], 0
0x140015f8d  mov     r8d, [rax+8]
0x140015f91  cmp     r8d, 3
0x140015f95  jz      short loc_140015FC7
0x140015f97  test    r8d, r8d
0x140015f9a  jz      short loc_140015FBB
0x140015f9c  sub     r8d, 1
0x140015fa0  jz      short loc_140015FBB
0x140015fa2  cmp     r8d, 4
0x140015fa6  jz      short loc_140015FAF
0x140015fa8  mov     eax, 0C00000BBh
0x140015fad  jmp     short loc_140015FFC
0x140015faf  lea     rdx, [rsp+28h+P]; unsigned __int16 **
0x140015fb4  call    ?VmpQueryContainerId@@YAJPEAVVM_VOLUME_EXTENSION@@PEAPEAG@Z; VmpQueryContainerId(VM_VOLUME_EXTENSION *,ushort * *)
0x140015fb9  jmp     short loc_140015FD1
0x140015fbb  lea     rdx, [rsp+28h+P]; unsigned __int16 **
0x140015fc0  call    ?VmpQueryDeviceId@@YAJPEAVVM_VOLUME_EXTENSION@@PEAPEAG@Z; VmpQueryDeviceId(VM_VOLUME_EXTENSION *,ushort * *)
0x140015fc5  jmp     short loc_140015FD1
0x140015fc7  lea     rdx, [rsp+28h+P]; unsigned __int16 **
0x140015fcc  call    ?VmpQueryInstanceId@@YAJPEAVVM_VOLUME_EXTENSION@@PEAPEAG@Z; VmpQueryInstanceId(VM_VOLUME_EXTENSION *,ushort * *)
0x140015fd1  mov     ebx, eax
0x140015fd3  test    eax, eax
0x140015fd5  js      short loc_140015FE2
0x140015fd7  mov     rax, [rsp+28h+P]
0x140015fdc  mov     [rdi+38h], rax
0x140015fe0  jmp     short loc_140015FFA
0x140015fe2  mov     rcx, [rsp+28h+P]; P
0x140015fe7  test    rcx, rcx
0x140015fea  jz      short loc_140015FFA
0x140015fec  xor     edx, edx; Tag
0x140015fee  call    cs:__imp_ExFreePoolWithTag
0x140015ff5  nop     dword ptr [rax+rax+00h]
0x140015ffa  mov     eax, ebx
0x140015ffc  mov     rbx, [rsp+28h+arg_0]
0x140016001  add     rsp, 20h
0x140016005  pop     rdi
0x140016006  retn
```
