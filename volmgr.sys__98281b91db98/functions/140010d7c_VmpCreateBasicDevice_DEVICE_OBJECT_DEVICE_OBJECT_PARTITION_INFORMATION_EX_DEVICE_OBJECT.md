# VmpCreateBasicDevice(_DEVICE_OBJECT *,_DEVICE_OBJECT *,_PARTITION_INFORMATION_EX *,_DEVICE_OBJECT * *)

- ea: `0x140010d7c`
- end: `0x1400114f2`
- name: `?VmpCreateBasicDevice@@YAJPEAU_DEVICE_OBJECT@@0PEAU_PARTITION_INFORMATION_EX@@PEAPEAU1@@Z`
- size: `1910`
- prototype: `__int64 __fastcall(struct _DEVICE_OBJECT *, struct _DEVICE_OBJECT *, struct _PARTITION_INFORMATION_EX *this, struct _DEVICE_OBJECT **)`
- caller_count: `1`
- callee_count: `13`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14000e54c`

## callees

- `0x140001008`
- `0x140001190`
- `0x1400013e8`
- `0x140002db0`
- `0x1400031b0`
- `0x140003b00`
- `0x140005050`
- `0x140010898`
- `0x140010d7c`
- `0x1400114f8`
- `0x1400123e8`
- `0x1400130b0`
- `0x140015a70`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x140010e27`
- `ntoskrnl!ObfDereferenceObject` at `0x140010e27`
- `ntoskrnl!IoDeleteDevice` at `0x1400114c3`
- `ntoskrnl!IoDeleteDevice` at `0x1400114c3`
- `ntoskrnl!RtlCheckPortableOperatingSystem` at `0x140011178`
- `ntoskrnl!RtlCheckPortableOperatingSystem` at `0x140011178`
- `ntoskrnl!IoGetAttachedDeviceReference` at `0x140010deb`
- `ntoskrnl!IoGetAttachedDeviceReference` at `0x140010deb`

## pseudocode

```c
__int64 __fastcall VmpCreateBasicDevice(
        struct _DEVICE_OBJECT *a1,
        struct _DEVICE_OBJECT *a2,
        struct _PARTITION_INFORMATION_EX *this,
        struct _DEVICE_OBJECT **a4)
{
  DWORD64 Attributes; // rbx
  char *DeviceExtension; // rax
  ULONG Characteristics; // r14d
  NTSTATUS GptAttributes; // edi
  char v11; // r15
  char v12; // r8
  int v13; // r9d
  int v14; // r14d
  int v15; // eax
  PDEVICE_OBJECT v16; // r14
  char *v17; // rbx
  char *v18; // rax
  __int16 v19; // cx
  struct _DEVICE_OBJECT *v20; // r12
  int v21; // r8d
  int v22; // ecx
  union _PARTITION_INFORMATION_EX::$41520227951B374488E85ABED149FDD2 *p_Mbr; // r12
  __int64 v24; // rax
  bool v25; // al
  NTSTATUS v26; // eax
  PARTITION_STYLE PartitionStyle; // ecx
  int v28; // r9d
  __int64 v29; // rcx
  int v30; // r9d
  __int64 v31; // rcx
  char v33; // [rsp+A0h] [rbp-80h] BYREF
  bool v34; // [rsp+A1h] [rbp-7Fh] BYREF
  char v35; // [rsp+A2h] [rbp-7Eh] BYREF
  char v36; // [rsp+A3h] [rbp-7Dh] BYREF
  bool v37; // [rsp+A4h] [rbp-7Ch] BYREF
  char v38; // [rsp+A5h] [rbp-7Bh] BYREF
  char BootIndicator; // [rsp+A6h] [rbp-7Ah] BYREF
  char PartitionType; // [rsp+A7h] [rbp-79h] BYREF
  bool v41; // [rsp+A8h] [rbp-78h] BYREF
  bool v42; // [rsp+A9h] [rbp-77h] BYREF
  char v43[6]; // [rsp+AAh] [rbp-76h] BYREF
  unsigned int v44[2]; // [rsp+B0h] [rbp-70h] BYREF
  unsigned __int64 v45; // [rsp+B8h] [rbp-68h] BYREF
  char *v46; // [rsp+C0h] [rbp-60h] BYREF
  struct _DEVICE_OBJECT *AttachedDeviceReference; // [rsp+C8h] [rbp-58h] BYREF
  PDEVICE_OBJECT DeviceObject; // [rsp+D0h] [rbp-50h] BYREF
  _BYTE *v49; // [rsp+D8h] [rbp-48h] BYREF
  struct _DEVICE_OBJECT **v50; // [rsp+E0h] [rbp-40h]
  char *v51; // [rsp+E8h] [rbp-38h] BYREF
  int v52; // [rsp+F0h] [rbp-30h]
  _BYTE v53[40]; // [rsp+F8h] [rbp-28h] BYREF
  _OWORD v54[2]; // [rsp+120h] [rbp+0h] BYREF

  Attributes = 0;
  v50 = a4;
  v45 = 0;
  DeviceObject = 0;
  *(_QWORD *)&v53[32] = 0;
  DeviceExtension = (char *)a1->DeviceExtension;
  *a4 = 0;
  Characteristics = a1->Characteristics;
  memset(v54, 0, sizeof(v54));
  v41 = 0;
  v46 = DeviceExtension;
  memset(v53, 0, 32);
  v44[0] = 0;
  AttachedDeviceReference = IoGetAttachedDeviceReference(a2);
  GptAttributes = VmpSendDeviceControl(AttachedDeviceReference, 0x70214u, 0, 0, v54, 0x20u);
  ObfDereferenceObject(AttachedDeviceReference);
  v11 = 0;
  if ( GptAttributes < 0 )
    return (unsigned int)GptAttributes;
  if ( *((_QWORD *)VmRootExtension + 45) )
  {
    if ( this->PartitionStyle )
    {
      if ( this->PartitionStyle == PARTITION_STYLE_GPT )
        VmpCheckForRevertGptAttributes(VmRootExtension, 0, 1u, 0, &this->Gpt.PartitionId, 0, 0, a1);
    }
    else if ( (int)VmpQueryDiskSignature(a2, v44) >= 0 )
    {
      VmpCheckForRevertGptAttributes(VmRootExtension, 0, 0, 0, 0, v44[0], 0, a1);
    }
  }
  *(_QWORD *)v44 = BYTE8(v54[0]) & 1;
  if ( SC_PART_ENTRY::IsRecognized((SC_PART_ENTRY *)this) )
  {
    if ( v13 == 1 )
    {
      Attributes = this->Gpt.Attributes;
    }
    else
    {
      GptAttributes = VmpDiskGetGptAttributes(a1, &v45);
      if ( GptAttributes < 0 )
        return (unsigned int)GptAttributes;
      Attributes = v45;
      v12 = BYTE8(v54[0]);
    }
    v11 = (Attributes & 0x4000000000000000LL) != 0;
  }
  else if ( v13 != 1
         || *(_QWORD *)&this->Mbr != *(_QWORD *)&PARTITION_SYSTEM_GUID.Data1
         || *(_QWORD *)this->Gpt.PartitionType.Data4 != *(_QWORD *)PARTITION_SYSTEM_GUID.Data4 )
  {
    v12 = BYTE8(v54[0]);
    v11 = (*((_DWORD *)v46 + 10) & 0x200) == 0;
  }
  v14 = Characteristics & 0x40001;
  if ( (v12 & 2) != 0 && (v12 & 4) == 0 )
    v11 = 1;
  v15 = VmpCreateDeviceObject(v14, Attributes, v11, &DeviceObject);
  v16 = DeviceObject;
  GptAttributes = v15;
  if ( v15 < 0 )
    goto LABEL_53;
  v17 = (char *)DeviceObject->DeviceExtension;
  VmpGetInstancePath(a2, (unsigned __int16 **)v17 + 47);
  v17[153] = *(&this->RewritePartition + 1);
  v17[155] = v44[0];
  *((_QWORD *)v17 + 46) = AttachedDeviceReference;
  v18 = v46;
  *((_QWORD *)v17 + 43) = a1;
  *((_QWORD *)v17 + 45) = a2;
  *(_OWORD *)(v17 + 408) = *((_OWORD *)v18 + 4);
  v16->StackSize = a1->StackSize + 1;
  v16->AlignmentRequirement = *(_DWORD *)(*((_QWORD *)v17 + 43) + 152LL);
  v19 = *(_WORD *)(*((_QWORD *)v17 + 43) + 304LL);
  if ( (unsigned __int16)v19 <= 0x200u )
    v19 = 512;
  v16->SectorSize = v19;
  v16->Flags |= *(_DWORD *)(*((_QWORD *)v17 + 43) + 48LL) & 0x600100
              | ((*(_DWORD *)(*((_QWORD *)v17 + 46) + 48LL) & 0x4000) != 0 ? 0x4000 : 0x2000);
  if ( (*(_DWORD *)(*(_QWORD *)v17 + 48LL) & 0x600100) != 0 || *((_DWORD *)v17 + 37) )
    v17[160] = 0;
  v20 = (struct _DEVICE_OBJECT *)*((_QWORD *)v17 + 43);
  v51 = 0;
  v52 = 0;
  GptAttributes = VmpSendDeviceControl(v20, 0x2D1084u, 0, 0, v53, 0x28u);
  if ( GptAttributes >= 0 || (GptAttributes = VmpSendDeviceControl(v20, 0x2D1080u, 0, 0, &v51, 0xCu), GptAttributes < 0) )
  {
    if ( GptAttributes < 0 )
      goto LABEL_53;
    v22 = *(_DWORD *)&v53[16];
  }
  else
  {
    v22 = HIDWORD(v51);
    *(_DWORD *)v53 = 40;
    *(_QWORD *)&v53[12] = v51;
    *(_DWORD *)&v53[36] = v52;
    *(_QWORD *)&v53[4] = 40;
    *(_OWORD *)&v53[20] = 0;
  }
  *((_DWORD *)v17 + 96) = v22;
  p_Mbr = (union _PARTITION_INFORMATION_EX::$41520227951B374488E85ABED149FDD2 *)&this->Mbr;
  *((_DWORD *)v17 + 97) = *(_DWORD *)&v53[36];
  *((_QWORD *)v17 + 49) = this->StartingOffset.QuadPart;
  *((_QWORD *)v17 + 50) = this->PartitionLength.QuadPart;
  if ( this->PartitionStyle == PARTITION_STYLE_GPT )
  {
    v17[424] = 1;
    v24 = *(_QWORD *)&p_Mbr->Mbr - *(_QWORD *)&PARTITION_SYSTEM_GUID.Data1;
    if ( *(_QWORD *)&p_Mbr->Mbr == *(_QWORD *)&PARTITION_SYSTEM_GUID.Data1 )
      v24 = *(_QWORD *)this->Gpt.PartitionType.Data4 - *(_QWORD *)PARTITION_SYSTEM_GUID.Data4;
    v25 = v24 == 0;
    goto LABEL_42;
  }
  if ( (*(_DWORD *)(*((_QWORD *)v17 + 43) + 48LL) & 0x200000) == 0
    || (unsigned __int8)(p_Mbr->Mbr.PartitionType - 11) > 1u )
  {
    goto LABEL_43;
  }
  v26 = RtlCheckPortableOperatingSystem(&v41);
  GptAttributes = 0;
  if ( v26 != -1073741275 )
    GptAttributes = v26;
  if ( GptAttributes >= 0 )
  {
    v25 = v41;
LABEL_42:
    v17[425] = v25;
LABEL_43:
    v16->Flags &= ~0x80u;
    PartitionStyle = this->PartitionStyle;
    if ( this->PartitionStyle )
    {
      if ( PartitionStyle == PARTITION_STYLE_GPT && (unsigned int)dword_14000A048 > 5 && (unsigned __int8)tlgKeywordOn() )
      {
        v33 = v17[425];
        v29 = *((_QWORD *)v17 + 39);
        v44[0] = this->PartitionStyle;
        v37 = v11;
        v34 = (v29 & 0x2000000000000000LL) != 0;
        v36 = v17[153];
        LODWORD(v29) = (v29 & 0x1000000000000000LL) != 0;
        AttachedDeviceReference = (struct _DEVICE_OBJECT *)&this->Mbr;
        v35 = v29;
        v38 = (v16->Flags & 0x400000) != 0;
        BootIndicator = (v16->Flags & 0x200000) != 0;
        PartitionType = BYTE1(v16->Flags) & 1;
        v46 = (char *)*((_QWORD *)v17 + 50);
        DeviceObject = (PDEVICE_OBJECT)*((_QWORD *)v17 + 49);
        LODWORD(v45) = *((_DWORD *)v17 + 97);
        v49 = &v53[20];
        v51 = v17 + 408;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByRef<16>>(
          v29,
          (unsigned int)byte_140007F69,
          v21,
          v28,
          (__int64)&v51,
          (__int64)&v49,
          (__int64)&v45,
          (__int64)&DeviceObject,
          (__int64)&v46,
          (__int64)&PartitionType,
          (__int64)&BootIndicator,
          (__int64)&v38,
          (__int64)&v37,
          (__int64)&v36,
          (__int64)&v35,
          (__int64)&v34,
          (__int64)v44,
          (__int64)&v33,
          (__int64)&AttachedDeviceReference);
      }
    }
    else if ( (unsigned int)dword_14000A048 > 5 && (unsigned __int8)tlgKeywordOn() )
    {
      PartitionType = p_Mbr->Mbr.PartitionType;
      BootIndicator = this->Mbr.BootIndicator;
      v38 = v17[425];
      v31 = *((_QWORD *)v17 + 39);
      LODWORD(v45) = this->PartitionStyle;
      v34 = v11;
      v37 = (v31 & 0x2000000000000000LL) != 0;
      v35 = v17[153];
      LODWORD(v31) = (v31 & 0x1000000000000000LL) != 0;
      v36 = v31;
      v33 = (v16->Flags & 0x400000) != 0;
      v42 = (v16->Flags & 0x200000) != 0;
      v43[0] = BYTE1(v16->Flags) & 1;
      v51 = (char *)*((_QWORD *)v17 + 50);
      v49 = (_BYTE *)*((_QWORD *)v17 + 49);
      v44[0] = *((_DWORD *)v17 + 97);
      AttachedDeviceReference = (struct _DEVICE_OBJECT *)&v53[20];
      v46 = v17 + 408;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>>(
        v31,
        (unsigned int)byte_140008061,
        v21,
        v30,
        (__int64)&v46,
        (__int64)&AttachedDeviceReference,
        (__int64)v44,
        (__int64)&v49,
        (__int64)&v51,
        (__int64)v43,
        (__int64)&v42,
        (__int64)&v33,
        (__int64)&v34,
        (__int64)&v35,
        (__int64)&v36,
        (__int64)&v37,
        (__int64)&v45,
        (__int64)&v38,
        (__int64)&BootIndicator,
        (__int64)&PartitionType);
    }
    *v50 = v16;
    if ( (Microsoft_Windows_StorageVolumeEnableBits & 1) != 0 )
      McTemplateK0qzqx_EtwWriteTransfer(
        PartitionStyle,
        (unsigned int)VolumeArrived,
        v21,
        *((_DWORD *)v17 + 41),
        *((_QWORD *)v17 + 47),
        *((_DWORD *)v17 + 96),
        *((_QWORD *)v17 + 49));
    return (unsigned int)GptAttributes;
  }
LABEL_53:
  if ( v16 )
    IoDeleteDevice(v16);
  return (unsigned int)GptAttributes;
}

```

## disassembly

```asm
0x140010d7c  push    rbp
0x140010d7e  push    rbx
0x140010d7f  push    rsi
0x140010d80  push    rdi
0x140010d81  push    r12
0x140010d83  push    r13
0x140010d85  push    r14
0x140010d87  push    r15
0x140010d89  lea     rbp, [rsp-38h]
0x140010d8e  sub     rsp, 158h
0x140010d95  mov     rax, cs:__security_cookie
0x140010d9c  xor     rax, rsp
0x140010d9f  mov     [rbp+70h+var_50], rax
0x140010da3  xor     ebx, ebx
0x140010da5  mov     [rbp+70h+var_B0], r9
0x140010da9  xorps   xmm0, xmm0
0x140010dac  mov     [rbp+70h+var_D8], rbx
0x140010db0  xor     eax, eax
0x140010db2  mov     [rbp+70h+DeviceObject], rbx
0x140010db6  mov     [rbp+70h+var_78], rax
0x140010dba  mov     r13, rcx
0x140010dbd  mov     rax, [rcx+40h]
0x140010dc1  mov     rsi, r8
0x140010dc4  mov     [r9], rbx
0x140010dc7  mov     r12, rdx
0x140010dca  mov     r14d, [rcx+34h]
0x140010dce  mov     rcx, rdx; DeviceObject
0x140010dd1  movups  [rbp+70h+var_70], xmm0
0x140010dd5  mov     [rbp+70h+var_E8], bl
0x140010dd8  movups  [rbp+70h+var_60], xmm0
0x140010ddc  mov     [rbp+70h+var_D0], rax
0x140010de0  movups  [rbp+70h+var_98], xmm0
0x140010de4  mov     [rbp+70h+var_E0], ebx
0x140010de7  movups  [rbp+70h+var_88], xmm0
0x140010deb  call    cs:__imp_IoGetAttachedDeviceReference
0x140010df2  nop     dword ptr [rax+rax+00h]
0x140010df7  mov     [rsp+190h+var_168], 20h ; ' '; ULONG
0x140010dff  xor     r9d, r9d; InputBufferLength
0x140010e02  mov     r15, rax
0x140010e05  mov     [rbp+70h+var_C8], rax
0x140010e09  lea     rax, [rbp+70h+var_70]
0x140010e0d  mov     rcx, r15; DeviceObject
0x140010e10  xor     r8d, r8d; InputBuffer
0x140010e13  mov     [rsp+190h+var_170], rax; PVOID
0x140010e18  mov     edx, 70214h; IoControlCode
0x140010e1d  call    VmpSendDeviceControl
0x140010e22  mov     rcx, r15; Object
0x140010e25  mov     edi, eax
0x140010e27  call    cs:__imp_ObfDereferenceObject
0x140010e2e  nop     dword ptr [rax+rax+00h]
0x140010e33  xor     r15d, r15d
0x140010e36  test    edi, edi
0x140010e38  js      loc_1400114CF
0x140010e3e  mov     rcx, cs:?VmRootExtension@@3PEAVVM_ROOT_EXTENSION@@EA; VM_ROOT_EXTENSION * VmRootExtension
0x140010e45  lea     edi, [rbx+1]
0x140010e48  cmp     [rcx+168h], r15
0x140010e4f  jz      short loc_140010EB2
0x140010e51  mov     edx, [rsi]
0x140010e53  test    edx, edx
0x140010e55  jz      short loc_140010E78
0x140010e57  cmp     edx, edi
0x140010e59  jnz     short loc_140010EB2
0x140010e5b  mov     [rsp+190h+var_158], r13
0x140010e60  lea     rax, [rsi+30h]
0x140010e64  mov     [rsp+190h+var_160], r15
0x140010e69  mov     r8b, dil
0x140010e6c  mov     [rsp+190h+var_168], r15d
0x140010e71  mov     [rsp+190h+var_170], rax
0x140010e76  jmp     short loc_140010EA8
0x140010e78  lea     rdx, [rbp+70h+var_E0]; unsigned int *
0x140010e7c  mov     rcx, r12; struct _DEVICE_OBJECT *
0x140010e7f  call    ?VmpQueryDiskSignature@@YAJPEAU_DEVICE_OBJECT@@PEAK@Z; VmpQueryDiskSignature(_DEVICE_OBJECT *,ulong *)
0x140010e84  test    eax, eax
0x140010e86  js      short loc_140010EB2
0x140010e88  mov     eax, [rbp+70h+var_E0]
0x140010e8b  xor     r8d, r8d; unsigned __int8
0x140010e8e  mov     rcx, cs:?VmRootExtension@@3PEAVVM_ROOT_EXTENSION@@EA; struct VM_ROOT_EXTENSION *
0x140010e95  mov     [rsp+190h+var_158], r13; struct _DEVICE_OBJECT *
0x140010e9a  mov     [rsp+190h+var_160], r15; void *
0x140010e9f  mov     [rsp+190h+var_168], eax; unsigned int
0x140010ea3  mov     [rsp+190h+var_170], r15; struct _GUID *
0x140010ea8  xor     r9d, r9d; struct _GUID *
0x140010eab  xor     edx, edx; unsigned __int8
0x140010ead  call    ?VmpCheckForRevertGptAttributes@@YAXPEAVVM_ROOT_EXTENSION@@EEPEAU_GUID@@1KPEAXPEAU_DEVICE_OBJECT@@@Z; VmpCheckForRevertGptAttributes(VM_ROOT_EXTENSION *,uchar,uchar,_GUID *,_GUID *,ulong,void *,_DEVICE_OBJECT *)
0x140010eb2  mov     r8, qword ptr [rbp+70h+var_70+8]
0x140010eb6  mov     rcx, rsi; this
0x140010eb9  mov     r9d, [rsi]
0x140010ebc  mov     rax, r8
0x140010ebf  and     rax, rdi
0x140010ec2  mov     qword ptr [rbp+70h+var_E0], rax
0x140010ec6  call    ?IsRecognized@SC_PART_ENTRY@@QEAAEXZ; SC_PART_ENTRY::IsRecognized(void)
0x140010ecb  test    al, al
0x140010ecd  jz      short loc_140010F09
0x140010ecf  cmp     r9d, edi
0x140010ed2  jnz     short loc_140010EDA
0x140010ed4  mov     rbx, [rsi+40h]
0x140010ed8  jmp     short loc_140010EFD
0x140010eda  lea     rdx, [rbp+70h+var_D8]; unsigned __int64 *
0x140010ede  mov     rcx, r13; struct _DEVICE_OBJECT *
0x140010ee1  call    ?VmpDiskGetGptAttributes@@YAJPEAU_DEVICE_OBJECT@@PEA_K@Z; VmpDiskGetGptAttributes(_DEVICE_OBJECT *,unsigned __int64 *)
0x140010ee6  mov     edi, eax
0x140010ee8  test    eax, eax
0x140010eea  js      loc_1400114CF
0x140010ef0  mov     rbx, [rbp+70h+var_D8]
0x140010ef4  mov     edi, 1
0x140010ef9  mov     r8, qword ptr [rbp+70h+var_70+8]
0x140010efd  mov     r15, rbx
0x140010f00  shr     r15, 3Eh
0x140010f04  and     r15b, dil
0x140010f07  jmp     short loc_140010F40
0x140010f09  cmp     r9d, edi
0x140010f0c  jnz     short loc_140010F28
0x140010f0e  mov     rax, [rsi+20h]
0x140010f12  cmp     rax, qword ptr cs:PARTITION_SYSTEM_GUID.Data1
0x140010f19  jnz     short loc_140010F28
0x140010f1b  mov     rax, [rsi+28h]
0x140010f1f  cmp     rax, qword ptr cs:PARTITION_SYSTEM_GUID.Data4
0x140010f26  jz      short loc_140010F40
0x140010f28  mov     rax, [rbp+70h+var_D0]
0x140010f2c  mov     ecx, edi
0x140010f2e  mov     eax, [rax+28h]
0x140010f31  bt      eax, 9
0x140010f35  mov     r8, qword ptr [rbp+70h+var_70+8]
0x140010f39  cmovb   ecx, r15d
0x140010f3d  mov     r15b, cl
0x140010f40  and     r14d, 40001h
0x140010f47  test    r8b, 2
0x140010f4b  jz      short loc_140010F59
0x140010f4d  test    r8b, 4
0x140010f51  movzx   r15d, r15b
0x140010f55  cmovz   r15d, edi
0x140010f59  lea     r9, [rbp+70h+DeviceObject]; struct _DEVICE_OBJECT **
0x140010f5d  mov     r8b, r15b; unsigned __int8
0x140010f60  mov     rdx, rbx; unsigned __int64
0x140010f63  mov     ecx, r14d; unsigned int
0x140010f66  call    ?VmpCreateDeviceObject@@YAJK_KEPEAPEAU_DEVICE_OBJECT@@@Z; VmpCreateDeviceObject(ulong,unsigned __int64,uchar,_DEVICE_OBJECT * *)
0x140010f6b  mov     r14, [rbp+70h+DeviceObject]
0x140010f6f  mov     edi, eax
0x140010f71  test    eax, eax
0x140010f73  js      loc_1400114BB
0x140010f79  mov     rbx, [r14+40h]
0x140010f7d  mov     rcx, r12; Pdo
0x140010f80  lea     rdx, [rbx+178h]; unsigned __int16 **
0x140010f87  call    ?VmpGetInstancePath@@YAJPEAU_DEVICE_OBJECT@@PEAPEAG@Z; VmpGetInstancePath(_DEVICE_OBJECT *,ushort * *)
0x140010f8c  mov     al, [rsi+1Dh]
0x140010f8f  mov     [rbx+99h], al
0x140010f95  mov     rax, qword ptr [rbp+70h+var_E0]
0x140010f99  mov     [rbx+9Bh], al
0x140010f9f  mov     rax, [rbp+70h+var_C8]
0x140010fa3  mov     [rbx+170h], rax
0x140010faa  mov     rax, [rbp+70h+var_D0]
0x140010fae  mov     [rbx+158h], r13
0x140010fb5  mov     [rbx+168h], r12
0x140010fbc  movups  xmm0, xmmword ptr [rax+40h]
0x140010fc0  movdqu  xmmword ptr [rbx+198h], xmm0
0x140010fc8  mov     al, [r13+4Ch]
0x140010fcc  mov     r13d, 1
0x140010fd2  add     al, r13b
0x140010fd5  mov     [r14+4Ch], al
0x140010fd9  mov     rax, [rbx+158h]
0x140010fe0  mov     ecx, [rax+98h]
0x140010fe6  mov     [r14+98h], ecx
0x140010fed  mov     rax, [rbx+158h]
0x140010ff4  movzx   ecx, word ptr [rax+130h]
0x140010ffb  mov     eax, 200h
0x140011000  cmp     cx, ax
0x140011003  ja      short loc_140011007
0x140011005  mov     ecx, eax
0x140011007  mov     [r14+130h], cx
0x14001100f  mov     r9d, 600100h
0x140011015  mov     rax, [rbx+158h]
0x14001101c  mov     r8d, [rax+30h]
0x140011020  mov     rax, [rbx+170h]
0x140011027  mov     ecx, [rax+30h]
0x14001102a  mov     edx, [r14+30h]
0x14001102e  and     ecx, 4000h
0x140011034  neg     ecx
0x140011036  mov     ecx, 2000h
0x14001103b  sbb     eax, eax
0x14001103d  and     r8d, r9d
0x140011040  and     eax, ecx
0x140011042  add     eax, ecx
0x140011044  or      eax, r8d
0x140011047  or      eax, edx
0x140011049  mov     [r14+30h], eax
0x14001104d  mov     rax, [rbx]
0x140011050  mov     ecx, [rax+30h]
0x140011053  test    r9d, ecx
0x140011056  jnz     short loc_140011061
0x140011058  cmp     dword ptr [rbx+94h], 0
0x14001105f  jz      short loc_140011068
0x140011061  mov     byte ptr [rbx+0A0h], 0
0x140011068  mov     r12, [rbx+158h]
0x14001106f  xor     eax, eax
0x140011071  mov     [rbp+70h+var_A8], rax
0x140011075  xor     r9d, r9d; InputBufferLength
0x140011078  mov     [rbp+70h+var_A0], eax
0x14001107b  xor     r8d, r8d; InputBuffer
0x14001107e  lea     rax, [rbp+70h+var_98]
0x140011082  mov     [rsp+190h+var_168], 28h ; '('; ULONG
0x14001108a  mov     edx, 2D1084h; IoControlCode
0x14001108f  mov     [rsp+190h+var_170], rax; PVOID
0x140011094  mov     rcx, r12; DeviceObject
0x140011097  call    VmpSendDeviceControl
0x14001109c  mov     edi, eax
0x14001109e  test    eax, eax
0x1400110a0  jns     short loc_1400110F8
0x1400110a2  lea     rax, [rbp+70h+var_A8]
0x1400110a6  mov     [rsp+190h+var_168], 0Ch; ULONG
0x1400110ae  xor     r9d, r9d; InputBufferLength
0x1400110b1  mov     [rsp+190h+var_170], rax; PVOID
0x1400110b6  xor     r8d, r8d; InputBuffer
0x1400110b9  mov     edx, 2D1080h; IoControlCode
0x1400110be  mov     rcx, r12; DeviceObject
0x1400110c1  call    VmpSendDeviceControl
0x1400110c6  mov     edi, eax
0x1400110c8  test    eax, eax
0x1400110ca  js      short loc_1400110F8
0x1400110cc  mov     ecx, dword ptr [rbp+70h+var_A8+4]
0x1400110cf  mov     eax, 28h ; '('
0x1400110d4  mov     dword ptr [rbp+70h+var_98], eax
0x1400110d7  xorps   xmm0, xmm0
0x1400110da  mov     eax, dword ptr [rbp+70h+var_A8]
0x1400110dd  mov     dword ptr [rbp+70h+var_98+0Ch], eax
0x1400110e0  mov     eax, [rbp+70h+var_A0]
0x1400110e3  mov     dword ptr [rbp+70h+var_78+4], eax
0x1400110e6  mov     qword ptr [rbp+70h+var_98+4], 28h ; '('
0x1400110ee  movdqu  [rbp+70h+var_88+4], xmm0
0x1400110f3  mov     dword ptr [rbp+70h+var_88], ecx
0x1400110f6  jmp     short loc_140011103
0x1400110f8  test    edi, edi
0x1400110fa  js      loc_1400114BB
0x140011100  mov     ecx, dword ptr [rbp+70h+var_88]
0x140011103  mov     [rbx+180h], ecx
0x140011109  lea     r12, [rsi+20h]
0x14001110d  mov     eax, dword ptr [rbp+70h+var_78+4]
0x140011110  mov     [rbx+184h], eax
0x140011116  mov     rax, [rsi+8]
0x14001111a  mov     [rbx+188h], rax
0x140011121  mov     rax, [rsi+10h]
0x140011125  mov     [rbx+190h], rax
0x14001112c  cmp     [rsi], r13d
0x14001112f  jnz     short loc_140011159
0x140011131  mov     [rbx+1A8h], r13b
0x140011138  mov     rax, [r12]
0x14001113c  sub     rax, qword ptr cs:PARTITION_SYSTEM_GUID.Data1
0x140011143  jnz     short loc_140011151
0x140011145  mov     rax, [r12+8]
0x14001114a  sub     rax, qword ptr cs:PARTITION_SYSTEM_GUID.Data4
0x140011151  test    rax, rax
0x140011154  setz    al
0x140011157  jmp     short loc_140011199
0x140011159  mov     rax, [rbx+158h]
0x140011160  mov     ecx, [rax+30h]
0x140011163  bt      ecx, 15h
0x140011167  jnb     short loc_14001119F
0x140011169  mov     al, [r12]
0x14001116d  sub     al, 0Bh
0x14001116f  cmp     al, r13b
0x140011172  ja      short loc_14001119F
0x140011174  lea     rcx, [rbp+70h+var_E8]
0x140011178  call    cs:__imp_RtlCheckPortableOperatingSystem
0x14001117f  nop     dword ptr [rax+rax+00h]
0x140011184  xor     edi, edi
0x140011186  cmp     eax, 0C0000225h
0x14001118b  cmovnz  edi, eax
0x14001118e  test    edi, edi
0x140011190  js      loc_1400114BB
0x140011196  mov     al, [rbp+70h+var_E8]
0x140011199  mov     [rbx+1A9h], al
0x14001119f  mov     eax, [r14+30h]
0x1400111a3  btr     eax, 7
0x1400111a7  mov     [r14+30h], eax
0x1400111ab  mov     ecx, [rsi]
0x1400111ad  test    ecx, ecx
0x1400111af  jz      loc_140011311
0x1400111b5  cmp     ecx, r13d
0x1400111b8  jnz     loc_140011474
0x1400111be  mov     eax, cs:dword_14000A048
0x1400111c4  cmp     eax, 5
0x1400111c7  jbe     loc_140011474
0x1400111cd  call    _tlgKeywordOn
0x1400111d2  test    al, al
0x1400111d4  jz      loc_140011474
0x1400111da  mov     al, [rbx+1A9h]
0x1400111e0  lea     rdx, byte_140007F69
0x1400111e7  mov     [rbp+70h+var_F0], al
0x1400111ea  mov     eax, [rsi]
0x1400111ec  mov     rcx, [rbx+138h]
0x1400111f3  mov     [rbp+70h+var_E0], eax
0x1400111f6  mov     rax, rcx
0x1400111f9  shr     rax, 3Dh
0x1400111fd  and     al, r13b
0x140011200  mov     [rbp+70h+var_EC], r15b
0x140011204  mov     [rbp+70h+var_EF], al
0x140011207  mov     al, [rbx+99h]
0x14001120d  mov     [rbp+70h+var_ED], al
0x140011210  shr     rcx, 3Ch
0x140011214  and     cl, r13b
0x140011217  mov     [rbp+70h+var_C8], r12
  ... truncated ...
```
