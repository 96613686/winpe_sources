# VmpUpdateProperties(VM_VOLUME_EXTENSION *,_IRP *)

- ea: `0x14000f3b0`
- end: `0x14000f563`
- name: `?VmpUpdateProperties@@YAJPEAVVM_VOLUME_EXTENSION@@PEAU_IRP@@@Z`
- size: `435`
- prototype: `__int64 __fastcall(struct VM_VOLUME_EXTENSION *, struct _IRP *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x140001ae0`

## callees

- `0x140002db0`
- `0x1400031b0`
- `0x140005050`
- `0x140005090`
- `0x140005120`
- `0x140005540`
- `0x14000f3b0`
- `0x14000f56c`
- `0x14000f6fc`
- `0x140010ad8`
- `0x140015a70`
- `0x140015da0`

## pseudocode

```c
__int64 __fastcall VmpUpdateProperties(struct VM_VOLUME_EXTENSION *a1, struct _IRP *a2)
{
  unsigned __int64 v4; // rsi
  NTSTATUS GptAttributes; // ebx
  struct _DEVICE_OBJECT *v7; // rcx
  struct _DEVICE_OBJECT *v8; // r8
  unsigned __int64 v9; // [rsp+30h] [rbp-69h] BYREF
  struct _PARTITION_INFORMATION_EX v10; // [rsp+40h] [rbp-59h] BYREF

  v4 = 0;
  v9 = 0;
  memset(&v10, 0, sizeof(v10));
  if ( *((_BYTE *)a1 + 426) )
  {
    if ( *((_QWORD *)a1 + 54) )
      return (*(__int64 (__fastcall **)(_QWORD, struct _IRP *))(*(_QWORD *)(*((_QWORD *)a1 + 1) + 392LL) + 104LL))(
               *((_QWORD *)a1 + 54),
               a2);
    return (unsigned int)-1073741810;
  }
  v7 = (struct _DEVICE_OBJECT *)*((_QWORD *)a1 + 43);
  if ( v7 )
  {
    GptAttributes = VmpSendDeviceControl(v7, 0x70048u, 0, 0, &v10, 0x90u);
    if ( GptAttributes < 0 )
      return (unsigned int)GptAttributes;
    if ( *((_QWORD *)a1 + 44) )
    {
      if ( v10.PartitionStyle )
      {
        if ( v10.PartitionStyle != PARTITION_STYLE_GPT || memcmp(&v10.Mbr, PARTITION_SPACES_DATA_GUID, 0x10u) )
          goto LABEL_14;
      }
      else if ( v10.Mbr.PartitionType != 0xD7 )
      {
        goto LABEL_14;
      }
      GptAttributes = VmpCompleteConversion(a1, 0);
      if ( GptAttributes >= 0 )
        return (unsigned int)GptAttributes;
    }
LABEL_14:
    VmpSetPartitionInformation(a1, &v10);
    if ( SC_PART_ENTRY::IsRecognized((SC_PART_ENTRY *)&v10) )
    {
      GptAttributes = VmpDiskGetGptAttributes(v8, &v9);
      if ( GptAttributes < 0 )
        return (unsigned int)GptAttributes;
      v4 = v9;
    }
    else if ( (*((_DWORD *)v8->DeviceExtension + 10) & 0x200) == 0
           && (v10.PartitionStyle != PARTITION_STYLE_GPT || memcmp(&v10.Mbr, &PARTITION_SYSTEM_GUID, 0x10u)) )
    {
      v4 = 0x4000000000000000LL;
    }
    VmpApplyGptAttributes(a1, v4);
    VmpNotify(a1, &GUID_IO_VOLUME_PHYSICAL_CONFIGURATION_CHANGE, 0, 0);
    return (unsigned int)GptAttributes;
  }
  return (unsigned int)-1073741810;
}

```

## disassembly

```asm
0x14000f3b0  mov     [rsp-8+arg_10], rbx
0x14000f3b5  push    rbp
0x14000f3b6  push    rsi
0x14000f3b7  push    rdi
0x14000f3b8  lea     rbp, [rsp-47h]
0x14000f3bd  sub     rsp, 0E0h
0x14000f3c4  mov     rax, cs:__security_cookie
0x14000f3cb  xor     rax, rsp
0x14000f3ce  mov     [rbp+57h+var_20], rax
0x14000f3d2  mov     rbx, rdx
0x14000f3d5  mov     rdi, rcx
0x14000f3d8  xor     esi, esi
0x14000f3da  lea     rcx, [rbp+57h+var_B0]; void *
0x14000f3de  xor     edx, edx; Val
0x14000f3e0  mov     [rbp+57h+var_C0], rsi
0x14000f3e4  mov     r8d, 90h; Size
0x14000f3ea  call    memset
0x14000f3ef  cmp     [rdi+1AAh], sil
0x14000f3f6  jz      short loc_14000F42D
0x14000f3f8  mov     r8, [rdi+1B0h]
0x14000f3ff  test    r8, r8
0x14000f402  jnz     short loc_14000F40E
0x14000f404  mov     ebx, 0C000000Eh
0x14000f409  jmp     loc_14000F541
0x14000f40e  mov     rax, [rdi+8]
0x14000f412  mov     rdx, rbx
0x14000f415  mov     rcx, [rax+188h]
0x14000f41c  mov     rax, [rcx+68h]
0x14000f420  mov     rcx, r8
0x14000f423  call    _guard_dispatch_icall
0x14000f428  jmp     loc_14000F543
0x14000f42d  mov     rcx, [rdi+158h]; DeviceObject
0x14000f434  test    rcx, rcx
0x14000f437  jz      short loc_14000F404
0x14000f439  lea     rax, [rbp+57h+var_B0]
0x14000f43d  mov     [rsp+0F0h+var_C8], 90h; ULONG
0x14000f445  xor     r9d, r9d; InputBufferLength
0x14000f448  mov     [rsp+0F0h+var_D0], rax; PVOID
0x14000f44d  xor     r8d, r8d; InputBuffer
0x14000f450  mov     edx, 70048h; IoControlCode
0x14000f455  call    VmpSendDeviceControl
0x14000f45a  mov     ebx, eax
0x14000f45c  test    eax, eax
0x14000f45e  js      loc_14000F541
0x14000f464  cmp     [rdi+160h], rsi
0x14000f46b  jz      short loc_14000F4B2
0x14000f46d  mov     eax, [rbp+57h+var_B0.PartitionStyle]
0x14000f470  test    eax, eax
0x14000f472  jz      short loc_14000F498
0x14000f474  cmp     eax, 1
0x14000f477  jnz     short loc_14000F4B2
0x14000f479  lea     r8d, [rax+0Fh]; Size
0x14000f47d  lea     rdx, PARTITION_SPACES_DATA_GUID; Buf2
0x14000f484  lea     rcx, [rbp+57h+var_B0.20h]; Buf1
0x14000f488  call    memcmp
0x14000f48d  test    eax, eax
0x14000f48f  setz    al
0x14000f492  test    al, al
0x14000f494  jz      short loc_14000F4B2
0x14000f496  jmp     short loc_14000F49E
0x14000f498  cmp     byte ptr [rbp+57h+var_B0.20h], 0D7h
0x14000f49c  jnz     short loc_14000F4B2
0x14000f49e  xor     edx, edx; struct _DEVICE_OBJECT *
0x14000f4a0  mov     rcx, rdi; struct VM_VOLUME_EXTENSION *
0x14000f4a3  call    ?VmpCompleteConversion@@YAJPEAVVM_VOLUME_EXTENSION@@PEAU_DEVICE_OBJECT@@@Z; VmpCompleteConversion(VM_VOLUME_EXTENSION *,_DEVICE_OBJECT *)
0x14000f4a8  mov     ebx, eax
0x14000f4aa  test    eax, eax
0x14000f4ac  jns     loc_14000F541
0x14000f4b2  lea     rdx, [rbp+57h+var_B0]; struct _PARTITION_INFORMATION_EX *
0x14000f4b6  mov     rcx, rdi; struct VM_VOLUME_EXTENSION *
0x14000f4b9  call    ?VmpSetPartitionInformation@@YAXPEAVVM_VOLUME_EXTENSION@@PEAU_PARTITION_INFORMATION_EX@@@Z; VmpSetPartitionInformation(VM_VOLUME_EXTENSION *,_PARTITION_INFORMATION_EX *)
0x14000f4be  mov     r8, [rdi+158h]
0x14000f4c5  lea     rcx, [rbp+57h+var_B0]; this
0x14000f4c9  call    ?IsRecognized@SC_PART_ENTRY@@QEAAEXZ; SC_PART_ENTRY::IsRecognized(void)
0x14000f4ce  test    al, al
0x14000f4d0  jz      short loc_14000F4EA
0x14000f4d2  lea     rdx, [rbp+57h+var_C0]; unsigned __int64 *
0x14000f4d6  mov     rcx, r8; struct _DEVICE_OBJECT *
0x14000f4d9  call    ?VmpDiskGetGptAttributes@@YAJPEAU_DEVICE_OBJECT@@PEA_K@Z; VmpDiskGetGptAttributes(_DEVICE_OBJECT *,unsigned __int64 *)
0x14000f4de  mov     ebx, eax
0x14000f4e0  test    eax, eax
0x14000f4e2  js      short loc_14000F541
0x14000f4e4  mov     rsi, [rbp+57h+var_C0]
0x14000f4e8  jmp     short loc_14000F521
0x14000f4ea  mov     rax, [r8+40h]
0x14000f4ee  mov     ecx, [rax+28h]
0x14000f4f1  bt      ecx, 9
0x14000f4f5  jb      short loc_14000F521
0x14000f4f7  cmp     [rbp+57h+var_B0.PartitionStyle], 1
0x14000f4fb  jnz     short loc_14000F517
0x14000f4fd  mov     r8d, 10h; Size
0x14000f503  lea     rdx, PARTITION_SYSTEM_GUID; Buf2
0x14000f50a  lea     rcx, [rbp+57h+var_B0.20h]; Buf1
0x14000f50e  call    memcmp
0x14000f513  test    eax, eax
0x14000f515  jz      short loc_14000F521
0x14000f517  mov     rsi, 4000000000000000h
0x14000f521  mov     rdx, rsi; unsigned __int64
0x14000f524  mov     rcx, rdi; struct VM_VOLUME_EXTENSION *
0x14000f527  call    ?VmpApplyGptAttributes@@YAXPEAVVM_VOLUME_EXTENSION@@_K@Z; VmpApplyGptAttributes(VM_VOLUME_EXTENSION *,unsigned __int64)
0x14000f52c  xor     r8d, r8d; unsigned __int16
0x14000f52f  lea     rdx, GUID_IO_VOLUME_PHYSICAL_CONFIGURATION_CHANGE; struct _GUID *
0x14000f536  xor     r9d, r9d; void *
0x14000f539  mov     rcx, rdi; struct VM_VOLUME_EXTENSION *
0x14000f53c  call    ?VmpNotify@@YAXPEAVVM_VOLUME_EXTENSION@@PEBU_GUID@@GPEAX@Z; VmpNotify(VM_VOLUME_EXTENSION *,_GUID const *,ushort,void *)
0x14000f541  mov     eax, ebx
0x14000f543  mov     rcx, [rbp+57h+var_20]
0x14000f547  xor     rcx, rsp; StackCookie
0x14000f54a  call    __security_check_cookie
0x14000f54f  mov     rbx, [rsp+0F0h+arg_10]
0x14000f557  add     rsp, 0E0h
0x14000f55e  pop     rdi
0x14000f55f  pop     rsi
0x14000f560  pop     rbp
0x14000f561  retn
```
