# VmpPartitionArrivedImmediate(VM_ROOT_EXTENSION *,_DEVICE_OBJECT *,_DEVICE_OBJECT *,_PARTITION_INFORMATION_EX *,uchar *,uchar *)

- ea: `0x14000e54c`
- end: `0x14000e6d6`
- name: `?VmpPartitionArrivedImmediate@@YAJPEAVVM_ROOT_EXTENSION@@PEAU_DEVICE_OBJECT@@1PEAU_PARTITION_INFORMATION_EX@@PEAE3@Z`
- size: `394`
- prototype: `int(struct VM_ROOT_EXTENSION *, struct _DEVICE_OBJECT *, struct _DEVICE_OBJECT *, struct _PARTITION_INFORMATION_EX *, unsigned __int8 *, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x1400127f0`

## callees

- `0x140003e70`
- `0x140003ef0`
- `0x140005090`
- `0x14000e484`
- `0x14000e54c`
- `0x140010d7c`

## import_xrefs

- `ntoskrnl!IoInvalidateDeviceRelations` at `0x14000e6b8`
- `ntoskrnl!IoInvalidateDeviceRelations` at `0x14000e6b8`

## pseudocode

```c
__int64 __fastcall VmpPartitionArrivedImmediate(
        struct VM_ROOT_EXTENSION *a1,
        struct _DEVICE_OBJECT *a2,
        struct _DEVICE_OBJECT *a3,
        struct _PARTITION_INFORMATION_EX *a4,
        unsigned __int8 *a5,
        unsigned __int8 *a6)
{
  unsigned int v7; // esi
  __int64 v11; // rax
  __int64 v12; // rax
  bool v13; // zf
  char *v14; // rcx
  char *v15; // rdi
  char **v16; // rax
  struct VM_ROOT_EXTENSION **v17; // rdx
  struct _DEVICE_OBJECT *v19; // [rsp+30h] [rbp-48h] BYREF

  v7 = 0;
  v19 = 0;
  *a5 = 0;
  *a6 = 1;
  if ( VmpIsConversionInProgress(a3) )
  {
    *a6 = 0;
    return v7;
  }
  if ( !*((_QWORD *)a1 + 49)
    || (VmpRestoreExtensionDriver((__int64)a1),
        v7 = (*(__int64 (__fastcall **)(struct _DEVICE_OBJECT *, struct _DEVICE_OBJECT *, struct _PARTITION_INFORMATION_EX *, unsigned __int8 *))(*((_QWORD *)a1 + 49) + 16LL))(
               a2,
               a3,
               a4,
               a5),
        VmpPageExtensionDriver((__int64)a1),
        (v7 & 0x80000000) == 0) )
  {
    if ( a4->PartitionStyle )
    {
      if ( a4->PartitionStyle != PARTITION_STYLE_GPT )
        return (unsigned int)-1073741823;
      v11 = *(_QWORD *)&a4->Mbr - *(_QWORD *)&PARTITION_LDM_DATA_GUID.Data1;
      if ( !v11 )
        v11 = *(_QWORD *)a4->Gpt.PartitionType.Data4 - *(_QWORD *)PARTITION_LDM_DATA_GUID.Data4;
      if ( !v11 )
      {
LABEL_16:
        *a6 = 0;
        return v7;
      }
      v12 = *(_QWORD *)&a4->Mbr - *(_QWORD *)&PARTITION_LDM_METADATA_GUID.Data1;
      if ( !v12 )
        v12 = *(_QWORD *)a4->Gpt.PartitionType.Data4 - *(_QWORD *)PARTITION_LDM_METADATA_GUID.Data4;
      v13 = v12 == 0;
    }
    else
    {
      v13 = a4->Mbr.PartitionType == 66;
    }
    if ( v13 )
      goto LABEL_16;
    v7 = VmpCreateBasicDevice(a3, a2, a4, &v19);
    if ( (v7 & 0x80000000) == 0 )
    {
      v14 = (char *)v19->DeviceExtension + 32;
      if ( *((struct _DEVICE_OBJECT **)a1 + 34) == a2 )
      {
        v15 = (char *)a1 + 256;
        v16 = (char **)*((_QWORD *)v15 + 1);
        if ( *v16 == v15 )
        {
          *(_QWORD *)v14 = v15;
          *((_QWORD *)v14 + 1) = v16;
          *v16 = v14;
          *((_QWORD *)v15 + 1) = v14;
          return v7;
        }
      }
      else
      {
        v17 = (struct VM_ROOT_EXTENSION **)*((_QWORD *)a1 + 27);
        if ( *v17 == (struct VM_ROOT_EXTENSION *)((char *)a1 + 208) )
        {
          *((_QWORD *)v19->DeviceExtension + 5) = v17;
          *(_QWORD *)v14 = (char *)a1 + 208;
          *v17 = (struct VM_ROOT_EXTENSION *)v14;
          *((_QWORD *)a1 + 27) = v14;
          IoInvalidateDeviceRelations(*((PDEVICE_OBJECT *)a1 + 6), SingleBusRelations);
          return v7;
        }
      }
      __fastfail(3u);
    }
  }
  return v7;
}

```

## disassembly

```asm
0x14000e54c  push    rbx
0x14000e54e  push    rbp
0x14000e54f  push    rsi
0x14000e550  push    rdi
0x14000e551  push    r12
0x14000e553  push    r14
0x14000e555  push    r15
0x14000e557  sub     rsp, 40h
0x14000e55b  mov     r12, [rsp+78h+arg_20]
0x14000e563  mov     rdi, rcx
0x14000e566  mov     r14, [rsp+78h+arg_28]
0x14000e56e  xor     esi, esi
0x14000e570  mov     rcx, r8; struct _DEVICE_OBJECT *
0x14000e573  mov     [rsp+78h+var_48], 0
0x14000e57c  mov     rbx, r9
0x14000e57f  mov     r15, r8
0x14000e582  mov     [r12], sil
0x14000e586  mov     rbp, rdx
0x14000e589  mov     byte ptr [r14], 1
0x14000e58d  call    ?VmpIsConversionInProgress@@YAEPEAU_DEVICE_OBJECT@@@Z; VmpIsConversionInProgress(_DEVICE_OBJECT *)
0x14000e592  test    al, al
0x14000e594  jz      short loc_14000E59E
0x14000e596  mov     [r14], sil
0x14000e599  jmp     loc_14000E6C4
0x14000e59e  cmp     [rdi+188h], rsi
0x14000e5a5  jz      short loc_14000E5DD
0x14000e5a7  mov     rcx, rdi
0x14000e5aa  call    VmpRestoreExtensionDriver
0x14000e5af  mov     rax, [rdi+188h]
0x14000e5b6  mov     r9, r12
0x14000e5b9  mov     r8, rbx
0x14000e5bc  mov     rdx, r15
0x14000e5bf  mov     rcx, rbp
0x14000e5c2  mov     rax, [rax+10h]
0x14000e5c6  call    _guard_dispatch_icall
0x14000e5cb  mov     rcx, rdi
0x14000e5ce  mov     esi, eax
0x14000e5d0  call    VmpPageExtensionDriver
0x14000e5d5  test    esi, esi
0x14000e5d7  js      loc_14000E6C4
0x14000e5dd  mov     eax, [rbx]
0x14000e5df  test    eax, eax
0x14000e5e1  jz      short loc_14000E62C
0x14000e5e3  cmp     eax, 1
0x14000e5e6  jz      short loc_14000E5F2
0x14000e5e8  mov     esi, 0C0000001h
0x14000e5ed  jmp     loc_14000E6C4
0x14000e5f2  mov     rax, [rbx+20h]
0x14000e5f6  sub     rax, qword ptr cs:PARTITION_LDM_DATA_GUID.Data1
0x14000e5fd  jnz     short loc_14000E60A
0x14000e5ff  mov     rax, [rbx+28h]
0x14000e603  sub     rax, qword ptr cs:PARTITION_LDM_DATA_GUID.Data4
0x14000e60a  test    rax, rax
0x14000e60d  jz      short loc_14000E632
0x14000e60f  mov     rax, [rbx+20h]
0x14000e613  sub     rax, qword ptr cs:PARTITION_LDM_METADATA_GUID.Data1
0x14000e61a  jnz     short loc_14000E627
0x14000e61c  mov     rax, [rbx+28h]
0x14000e620  sub     rax, qword ptr cs:PARTITION_LDM_METADATA_GUID.Data4
0x14000e627  test    rax, rax
0x14000e62a  jmp     short loc_14000E630
0x14000e62c  cmp     byte ptr [rbx+20h], 42h ; 'B'
0x14000e630  jnz     short loc_14000E63B
0x14000e632  mov     byte ptr [r14], 0
0x14000e636  jmp     loc_14000E6C4
0x14000e63b  lea     r9, [rsp+78h+var_48]; struct _DEVICE_OBJECT **
0x14000e640  mov     r8, rbx; this
0x14000e643  mov     rdx, rbp; struct _DEVICE_OBJECT *
0x14000e646  mov     rcx, r15; struct _DEVICE_OBJECT *
0x14000e649  call    ?VmpCreateBasicDevice@@YAJPEAU_DEVICE_OBJECT@@0PEAU_PARTITION_INFORMATION_EX@@PEAPEAU1@@Z; VmpCreateBasicDevice(_DEVICE_OBJECT *,_DEVICE_OBJECT *,_PARTITION_INFORMATION_EX *,_DEVICE_OBJECT * *)
0x14000e64e  mov     esi, eax
0x14000e650  test    eax, eax
0x14000e652  js      short loc_14000E6C4
0x14000e654  mov     rax, [rsp+78h+var_48]
0x14000e659  mov     rcx, [rax+40h]
0x14000e65d  add     rcx, 20h ; ' '
0x14000e661  cmp     [rdi+110h], rbp
0x14000e668  jnz     short loc_14000E68A
0x14000e66a  add     rdi, 100h
0x14000e671  mov     rax, [rdi+8]
0x14000e675  cmp     [rax], rdi
0x14000e678  jnz     short loc_14000E69A
0x14000e67a  mov     [rcx], rdi
0x14000e67d  mov     [rcx+8], rax
0x14000e681  mov     [rax], rcx
0x14000e684  mov     [rdi+8], rcx
0x14000e688  jmp     short loc_14000E6C4
0x14000e68a  lea     rax, [rdi+0D0h]
0x14000e691  mov     rdx, [rax+8]
0x14000e695  cmp     [rdx], rax
0x14000e698  jz      short loc_14000E6A1
0x14000e69a  mov     ecx, 3
0x14000e69f  int     29h; Win8: RtlFailFast(ecx)
0x14000e6a1  mov     [rcx+8], rdx
0x14000e6a5  mov     [rcx], rax
0x14000e6a8  mov     [rdx], rcx
0x14000e6ab  mov     edx, 5; Type
0x14000e6b0  mov     [rax+8], rcx
0x14000e6b4  mov     rcx, [rdi+30h]; DeviceObject
0x14000e6b8  call    cs:__imp_IoInvalidateDeviceRelations
0x14000e6bf  nop     dword ptr [rax+rax+00h]
0x14000e6c4  mov     eax, esi
0x14000e6c6  add     rsp, 40h
0x14000e6ca  pop     r15
0x14000e6cc  pop     r14
0x14000e6ce  pop     r12
0x14000e6d0  pop     rdi
0x14000e6d1  pop     rsi
0x14000e6d2  pop     rbp
0x14000e6d3  pop     rbx
0x14000e6d4  retn
```
