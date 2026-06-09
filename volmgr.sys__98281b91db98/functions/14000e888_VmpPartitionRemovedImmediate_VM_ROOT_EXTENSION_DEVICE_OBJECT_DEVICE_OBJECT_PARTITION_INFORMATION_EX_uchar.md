# VmpPartitionRemovedImmediate(VM_ROOT_EXTENSION *,_DEVICE_OBJECT *,_DEVICE_OBJECT *,_PARTITION_INFORMATION_EX *,uchar *)

- ea: `0x14000e888`
- end: `0x14000eb2b`
- name: `?VmpPartitionRemovedImmediate@@YAJPEAVVM_ROOT_EXTENSION@@PEAU_DEVICE_OBJECT@@1PEAU_PARTITION_INFORMATION_EX@@PEAE@Z`
- size: `675`
- prototype: `__int64 __usercall@<rax>(struct VM_ROOT_EXTENSION *@<rcx>, struct _DEVICE_OBJECT *@<rdx>, struct _DEVICE_OBJECT *@<r8>, struct _PARTITION_INFORMATION_EX *@<r9>, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `16`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140012b3c`

## callees

- `0x1400030d0`
- `0x1400033a0`
- `0x1400039f0`
- `0x140003c50`
- `0x140003e70`
- `0x140003ef0`
- `0x140005050`
- `0x140005090`
- `0x140005540`
- `0x14000e888`
- `0x14000f158`
- `0x14000f19c`
- `0x14000f6fc`
- `0x140010ad8`
- `0x140011d94`
- `0x1400120f0`

## import_xrefs

- `ntoskrnl!IoDeleteDevice` at `0x14000e98c`
- `ntoskrnl!IoDeleteDevice` at `0x14000e98c`
- `ntoskrnl!IoInvalidateDeviceRelations` at `0x14000eb13`
- `ntoskrnl!IoInvalidateDeviceRelations` at `0x14000eb13`

## pseudocode

```c
__int64 __fastcall VmpPartitionRemovedImmediate(
        struct VM_ROOT_EXTENSION *a1,
        struct _DEVICE_OBJECT *a2,
        struct _DEVICE_OBJECT *a3,
        struct _PARTITION_INFORMATION_EX *a4,
        unsigned __int8 *a5)
{
  int v9; // ebx
  __int64 result; // rax
  struct VM_VOLUME_EXTENSION *ExtensionForPendingBasicVolume; // rbx
  __int64 v12; // rcx
  struct VM_VOLUME_EXTENSION **v13; // rdx
  int v14; // edx
  int v15; // ecx
  int v16; // r8d
  char v17; // di
  unsigned __int8 v18; // r8
  _QWORD **v19; // rdx
  _QWORD *i; // rax
  _QWORD *v21; // rcx
  struct VM_ROOT_EXTENSION *v22; // rbx
  __int64 v23; // rax
  struct VM_ROOT_EXTENSION **v24; // rdx
  struct VM_ROOT_EXTENSION **v25; // rdx
  _QWORD v26[14]; // [rsp+40h] [rbp-A8h] BYREF

  memset(v26, 0, 0x68u);
  *a5 = 0;
  if ( *((_QWORD *)a1 + 49) )
  {
    VmpRestoreExtensionDriver(a1);
    v9 = (*(__int64 (__fastcall **)(struct _DEVICE_OBJECT *, struct _DEVICE_OBJECT *, struct _PARTITION_INFORMATION_EX *, unsigned __int8 *))(*((_QWORD *)a1 + 49) + 32LL))(
           a2,
           a3,
           a4,
           a5);
    VmpPageExtensionDriver(a1);
    if ( v9 < 0 )
      return (unsigned int)v9;
  }
  ExtensionForPendingBasicVolume = VmpFindExtensionForPendingBasicVolume(a1, a3);
  if ( !ExtensionForPendingBasicVolume )
  {
    ExtensionForPendingBasicVolume = VmpFindExtensionForBasicVolume(a3);
    if ( !ExtensionForPendingBasicVolume )
      return 0;
  }
  if ( !*((_BYTE *)ExtensionForPendingBasicVolume + 158) )
  {
    v12 = *((_QWORD *)ExtensionForPendingBasicVolume + 4);
    if ( *(struct VM_VOLUME_EXTENSION **)(v12 + 8) == (struct VM_VOLUME_EXTENSION *)((char *)ExtensionForPendingBasicVolume
                                                                                   + 32) )
    {
      v13 = (struct VM_VOLUME_EXTENSION **)*((_QWORD *)ExtensionForPendingBasicVolume + 5);
      if ( *v13 == (struct VM_VOLUME_EXTENSION *)((char *)ExtensionForPendingBasicVolume + 32) )
      {
        *v13 = (struct VM_VOLUME_EXTENSION *)v12;
        *(_QWORD *)(v12 + 8) = v13;
        VmpCleanupVolumeExtension(ExtensionForPendingBasicVolume);
        IoDeleteDevice(*(PDEVICE_OBJECT *)ExtensionForPendingBasicVolume);
        return 0;
      }
    }
LABEL_33:
    __fastfail(3u);
  }
  result = VmpCompleteConversion(ExtensionForPendingBasicVolume, a3);
  if ( (int)result < 0 )
  {
    if ( a2 && !a4 )
      *((_BYTE *)ExtensionForPendingBasicVolume + 159) = 1;
    *((_QWORD *)ExtensionForPendingBasicVolume + 6) = MEMORY[0xFFFFF78000000014];
    if ( (Microsoft_Windows_StorageVolumeEnableBits & 1) != 0 )
      McTemplateK0qzqxt_EtwWriteTransfer(
        v15,
        v14,
        v16,
        *((_DWORD *)ExtensionForPendingBasicVolume + 41),
        *((_QWORD *)ExtensionForPendingBasicVolume + 47),
        *((_DWORD *)ExtensionForPendingBasicVolume + 96),
        *((_QWORD *)ExtensionForPendingBasicVolume + 49),
        *((_BYTE *)ExtensionForPendingBasicVolume + 159));
    v17 = *((_BYTE *)ExtensionForPendingBasicVolume + 424);
    if ( *((_BYTE *)ExtensionForPendingBasicVolume + 159) )
      VmpNotify(ExtensionForPendingBasicVolume, &GUID_IO_VOLUME_PREPARE_DELETE, 0, 0);
    VmpDeleteLegacyNameLinks(ExtensionForPendingBasicVolume, 0);
    VmpReleaseInterfaces(ExtensionForPendingBasicVolume);
    memset(v26, 0, 0x68u);
    v26[7] = *((_QWORD *)ExtensionForPendingBasicVolume + 49);
    v26[8] = *((_QWORD *)ExtensionForPendingBasicVolume + 50);
    VmpZeroRefCallback(
      ExtensionForPendingBasicVolume,
      (int (*)(struct VM_VOLUME_EXTENSION *, void *))VmpSetTargetCallback,
      v26);
    if ( *((_BYTE *)ExtensionForPendingBasicVolume + 159) && !v17 )
    {
      v19 = (_QWORD **)(*((_QWORD *)ExtensionForPendingBasicVolume + 1) + 208LL);
      for ( i = *v19; i != v19; i = (_QWORD *)*i )
      {
        v21 = i - 4;
        if ( i - 4 != (_QWORD *)ExtensionForPendingBasicVolume
          && !*((_BYTE *)v21 + 426)
          && (struct _DEVICE_OBJECT *)v21[45] == a2 )
        {
          goto LABEL_29;
        }
      }
      VmpDiskSetGptAttributes(a2, 0, v18);
    }
LABEL_29:
    v22 = (struct VM_VOLUME_EXTENSION *)((char *)ExtensionForPendingBasicVolume + 32);
    v23 = *(_QWORD *)v22;
    if ( *(struct VM_ROOT_EXTENSION **)(*(_QWORD *)v22 + 8LL) == v22 )
    {
      v24 = (struct VM_ROOT_EXTENSION **)*((_QWORD *)v22 + 1);
      if ( *v24 == v22 )
      {
        *v24 = (struct VM_ROOT_EXTENSION *)v23;
        *(_QWORD *)(v23 + 8) = v24;
        v25 = (struct VM_ROOT_EXTENSION **)*((_QWORD *)a1 + 29);
        if ( *v25 == (struct VM_ROOT_EXTENSION *)((char *)a1 + 224) )
        {
          *((_QWORD *)v22 + 1) = v25;
          *(_QWORD *)v22 = (char *)a1 + 224;
          *v25 = v22;
          *((_QWORD *)a1 + 29) = v22;
          IoInvalidateDeviceRelations(*((PDEVICE_OBJECT *)a1 + 6), SingleBusRelations);
          return 0;
        }
      }
    }
    goto LABEL_33;
  }
  return result;
}

```

## disassembly

```asm
0x14000e888  push    rbx
0x14000e88a  push    rbp
0x14000e88b  push    rsi
0x14000e88c  push    rdi
0x14000e88d  push    r14
0x14000e88f  sub     rsp, 0C0h
0x14000e896  mov     rax, cs:__security_cookie
0x14000e89d  xor     rax, rsp
0x14000e8a0  mov     [rsp+0E8h+var_38], rax
0x14000e8a8  mov     rbx, [rsp+0E8h+arg_20]
0x14000e8b0  mov     rbp, rdx
0x14000e8b3  xor     edx, edx; Val
0x14000e8b5  mov     rdi, r8
0x14000e8b8  mov     rsi, rcx
0x14000e8bb  mov     r14, r9
0x14000e8be  lea     rcx, [rsp+0E8h+var_A8]; void *
0x14000e8c3  lea     r8d, [rdx+68h]; Size
0x14000e8c7  call    memset
0x14000e8cc  mov     byte ptr [rbx], 0
0x14000e8cf  cmp     qword ptr [rsi+188h], 0
0x14000e8d7  jz      short loc_14000E92C
0x14000e8d9  mov     rcx, rsi
0x14000e8dc  call    VmpRestoreExtensionDriver
0x14000e8e1  mov     rax, [rsi+188h]
0x14000e8e8  mov     r9, rbx
0x14000e8eb  mov     r8, r14
0x14000e8ee  mov     rdx, rdi
0x14000e8f1  mov     rcx, rbp
0x14000e8f4  mov     rax, [rax+20h]
0x14000e8f8  call    _guard_dispatch_icall
0x14000e8fd  mov     rcx, rsi
0x14000e900  mov     ebx, eax
0x14000e902  call    VmpPageExtensionDriver
0x14000e907  test    ebx, ebx
0x14000e909  jns     short loc_14000E92C
0x14000e90b  mov     eax, ebx
0x14000e90d  mov     rcx, [rsp+0E8h+var_38]
0x14000e915  xor     rcx, rsp; StackCookie
0x14000e918  call    __security_check_cookie
0x14000e91d  add     rsp, 0C0h
0x14000e924  pop     r14
0x14000e926  pop     rdi
0x14000e927  pop     rsi
0x14000e928  pop     rbp
0x14000e929  pop     rbx
0x14000e92a  retn
0x14000e92c  mov     rdx, rdi; struct _DEVICE_OBJECT *
0x14000e92f  mov     rcx, rsi; struct VM_ROOT_EXTENSION *
0x14000e932  call    ?VmpFindExtensionForPendingBasicVolume@@YAPEAVVM_VOLUME_EXTENSION@@PEAVVM_ROOT_EXTENSION@@PEAU_DEVICE_OBJECT@@@Z; VmpFindExtensionForPendingBasicVolume(VM_ROOT_EXTENSION *,_DEVICE_OBJECT *)
0x14000e937  mov     rbx, rax
0x14000e93a  test    rax, rax
0x14000e93d  jnz     short loc_14000E953
0x14000e93f  mov     rcx, rdi; struct _DEVICE_OBJECT *
0x14000e942  call    ?VmpFindExtensionForBasicVolume@@YAPEAVVM_VOLUME_EXTENSION@@PEAU_DEVICE_OBJECT@@@Z; VmpFindExtensionForBasicVolume(_DEVICE_OBJECT *)
0x14000e947  mov     rbx, rax
0x14000e94a  test    rax, rax
0x14000e94d  jnz     short loc_14000E953
0x14000e94f  xor     eax, eax
0x14000e951  jmp     short loc_14000E90D
0x14000e953  cmp     byte ptr [rbx+9Eh], 0
0x14000e95a  jnz     short loc_14000E99A
0x14000e95c  lea     rax, [rbx+20h]
0x14000e960  mov     rcx, [rax]
0x14000e963  cmp     [rcx+8], rax
0x14000e967  jnz     loc_14000EB24
0x14000e96d  mov     rdx, [rax+8]
0x14000e971  cmp     [rdx], rax
0x14000e974  jnz     loc_14000EB24
0x14000e97a  mov     [rdx], rcx
0x14000e97d  mov     [rcx+8], rdx
0x14000e981  mov     rcx, rbx; struct VM_VOLUME_EXTENSION *
0x14000e984  call    ?VmpCleanupVolumeExtension@@YAXPEAVVM_VOLUME_EXTENSION@@@Z; VmpCleanupVolumeExtension(VM_VOLUME_EXTENSION *)
0x14000e989  mov     rcx, [rbx]; DeviceObject
0x14000e98c  call    cs:__imp_IoDeleteDevice
0x14000e993  nop     dword ptr [rax+rax+00h]
0x14000e998  jmp     short loc_14000E94F
0x14000e99a  mov     rdx, rdi; struct _DEVICE_OBJECT *
0x14000e99d  mov     rcx, rbx; struct VM_VOLUME_EXTENSION *
0x14000e9a0  call    ?VmpCompleteConversion@@YAJPEAVVM_VOLUME_EXTENSION@@PEAU_DEVICE_OBJECT@@@Z; VmpCompleteConversion(VM_VOLUME_EXTENSION *,_DEVICE_OBJECT *)
0x14000e9a5  test    eax, eax
0x14000e9a7  jns     loc_14000E90D
0x14000e9ad  test    rbp, rbp
0x14000e9b0  jz      short loc_14000E9BE
0x14000e9b2  test    r14, r14
0x14000e9b5  jnz     short loc_14000E9BE
0x14000e9b7  mov     byte ptr [rbx+9Fh], 1
0x14000e9be  mov     rax, ds:0FFFFF78000000014h
0x14000e9c8  mov     [rbx+30h], rax
0x14000e9cc  test    cs:Microsoft_Windows_StorageVolumeEnableBits, 1
0x14000e9d3  jz      short loc_14000EA0E
0x14000e9d5  movzx   eax, byte ptr [rbx+9Fh]
0x14000e9dc  mov     r9d, [rbx+0A4h]
0x14000e9e3  mov     [rsp+0E8h+var_B0], eax
0x14000e9e7  mov     rax, [rbx+188h]
0x14000e9ee  mov     [rsp+0E8h+var_B8], rax
0x14000e9f3  mov     eax, [rbx+180h]
0x14000e9f9  mov     [rsp+0E8h+var_C0], eax
0x14000e9fd  mov     rax, [rbx+178h]
0x14000ea04  mov     [rsp+0E8h+var_C8], rax
0x14000ea09  call    McTemplateK0qzqxt_EtwWriteTransfer
0x14000ea0e  cmp     byte ptr [rbx+9Fh], 0
0x14000ea15  mov     dil, [rbx+1A8h]
0x14000ea1c  jz      short loc_14000EA33
0x14000ea1e  xor     r8d, r8d; unsigned __int16
0x14000ea21  lea     rdx, GUID_IO_VOLUME_PREPARE_DELETE; struct _GUID *
0x14000ea28  xor     r9d, r9d; void *
0x14000ea2b  mov     rcx, rbx; struct VM_VOLUME_EXTENSION *
0x14000ea2e  call    ?VmpNotify@@YAXPEAVVM_VOLUME_EXTENSION@@PEBU_GUID@@GPEAX@Z; VmpNotify(VM_VOLUME_EXTENSION *,_GUID const *,ushort,void *)
0x14000ea33  xor     edx, edx; unsigned __int8
0x14000ea35  mov     rcx, rbx; struct VM_VOLUME_EXTENSION *
0x14000ea38  call    ?VmpDeleteLegacyNameLinks@@YAXPEAVVM_VOLUME_EXTENSION@@E@Z; VmpDeleteLegacyNameLinks(VM_VOLUME_EXTENSION *,uchar)
0x14000ea3d  mov     rcx, rbx
0x14000ea40  call    VmpReleaseInterfaces
0x14000ea45  xor     edx, edx; Val
0x14000ea47  lea     rcx, [rsp+0E8h+var_A8]; void *
0x14000ea4c  lea     r8d, [rdx+68h]; Size
0x14000ea50  call    memset
0x14000ea55  mov     rax, [rbx+188h]
0x14000ea5c  lea     r8, [rsp+0E8h+var_A8]; void *
0x14000ea61  mov     [rsp+0E8h+var_70], rax
0x14000ea66  lea     rdx, ?VmpSetTargetCallback@@YAJPEAVVM_VOLUME_EXTENSION@@PEAX@Z; int (*)(struct VM_VOLUME_EXTENSION *, void *)
0x14000ea6d  mov     rax, [rbx+190h]
0x14000ea74  mov     rcx, rbx; struct VM_VOLUME_EXTENSION *
0x14000ea77  mov     [rsp+0E8h+var_68], rax
0x14000ea7f  call    ?VmpZeroRefCallback@@YAJPEAVVM_VOLUME_EXTENSION@@P6AJ0PEAX@Z1@Z; VmpZeroRefCallback(VM_VOLUME_EXTENSION *,long (*)(VM_VOLUME_EXTENSION *,void *),void *)
0x14000ea84  cmp     byte ptr [rbx+9Fh], 0
0x14000ea8b  jz      short loc_14000EACF
0x14000ea8d  test    dil, dil
0x14000ea90  jnz     short loc_14000EACF
0x14000ea92  mov     rdx, [rbx+8]
0x14000ea96  add     rdx, 0D0h
0x14000ea9d  mov     rax, [rdx]
0x14000eaa0  cmp     rax, rdx
0x14000eaa3  jz      short loc_14000EAC5
0x14000eaa5  lea     rcx, [rax-20h]
0x14000eaa9  cmp     rcx, rbx
0x14000eaac  jz      short loc_14000EAC0
0x14000eaae  cmp     byte ptr [rcx+1AAh], 0
0x14000eab5  jnz     short loc_14000EAC0
0x14000eab7  cmp     [rcx+168h], rbp
0x14000eabe  jz      short loc_14000EACF
0x14000eac0  mov     rax, [rax]
0x14000eac3  jmp     short loc_14000EAA0
0x14000eac5  xor     edx, edx; unsigned __int64
0x14000eac7  mov     rcx, rbp; struct _DEVICE_OBJECT *
0x14000eaca  call    ?VmpDiskSetGptAttributes@@YAJPEAU_DEVICE_OBJECT@@_KE@Z; VmpDiskSetGptAttributes(_DEVICE_OBJECT *,unsigned __int64,uchar)
0x14000eacf  add     rbx, 20h ; ' '
0x14000ead3  mov     rax, [rbx]
0x14000ead6  cmp     [rax+8], rbx
0x14000eada  jnz     short loc_14000EB24
0x14000eadc  mov     rdx, [rbx+8]
0x14000eae0  cmp     [rdx], rbx
0x14000eae3  jnz     short loc_14000EB24
0x14000eae5  mov     [rdx], rax
0x14000eae8  mov     [rax+8], rdx
0x14000eaec  lea     rax, [rsi+0E0h]
0x14000eaf3  mov     rdx, [rax+8]
0x14000eaf7  cmp     [rdx], rax
0x14000eafa  jnz     short loc_14000EB24
0x14000eafc  mov     [rbx+8], rdx
0x14000eb00  mov     [rbx], rax
0x14000eb03  mov     [rdx], rbx
0x14000eb06  mov     edx, 5; Type
0x14000eb0b  mov     [rax+8], rbx
0x14000eb0f  mov     rcx, [rsi+30h]; DeviceObject
0x14000eb13  call    cs:__imp_IoInvalidateDeviceRelations
0x14000eb1a  nop     dword ptr [rax+rax+00h]
0x14000eb1f  jmp     loc_14000E94F
0x14000eb24  mov     ecx, 3
0x14000eb29  int     29h; Win8: RtlFailFast(ecx)
```
