# CUsbDeviceSqm::LogStreamEntry(CUsbDevice &)

- ea: `0x1800045d0`
- end: `0x180004d6c`
- name: `?LogStreamEntry@CUsbDeviceSqm@@AEAAXAEAVCUsbDevice@@@Z`
- size: `1948`
- prototype: `void __fastcall(CUsbDeviceSqm *this, CUsbDevice **)`
- caller_count: `1`
- callee_count: `26`
- tags: `registry_config`

## callers

- `0x180004388`

## callees

- `0x180001294`
- `0x1800012c4`
- `0x180003c88`
- `0x180004240`
- `0x180004344`
- `0x1800045d0`
- `0x180007248`
- `0x180008b6c`
- `0x180008bf0`
- `0x180008f48`
- `0x180009054`
- `0x1800090d4`
- `0x180009204`
- `0x180009260`
- `0x180009424`
- `0x1800094c8`
- `0x180009748`
- `0x180009adc`
- `0x180009c50`
- `0x180009d50`
- `0x180009e50`
- `0x18000aa38`
- `0x18000ace8`
- `0x18000c0d0`
- `0x18000c114`
- `0x18000c16c`

## string_xrefs

- `0x180004788`: `MSOSDescriptorHang`

## pseudocode

```c
void __fastcall CUsbDeviceSqm::LogStreamEntry(CUsbDeviceSqm *this, CUsbDevice **a2)
{
  const char *v4; // r15
  CUsbDeviceSqm *v5; // rcx
  BOOL v6; // r14d
  BOOL v7; // esi
  unsigned __int8 v8; // r12
  __int64 v9; // rdx
  CUsbDevice *v10; // rcx
  _bstr_t::Data_t *v11; // rdi
  const char *String; // r13
  __int64 v13; // r8
  __int64 v14; // r9
  BOOL v15; // ebx
  int v16; // r8d
  unsigned int v17; // r9d
  unsigned int v18; // r10d
  BOOL v19; // r11d
  unsigned int v20; // ecx
  _QWORD *v21; // rax
  _QWORD *v22; // rax
  __int64 v23; // rcx
  int v24; // [rsp+130h] [rbp-80h] BYREF
  int v25; // [rsp+134h] [rbp-7Ch] BYREF
  unsigned int InterfaceAssociationDescriptorCount; // [rsp+138h] [rbp-78h] BYREF
  unsigned int EnumerationRetryCount; // [rsp+13Ch] [rbp-74h] BYREF
  BOOL v28; // [rsp+140h] [rbp-70h] BYREF
  unsigned int v29; // [rsp+144h] [rbp-6Ch] BYREF
  unsigned int v30; // [rsp+148h] [rbp-68h] BYREF
  unsigned int v31; // [rsp+14Ch] [rbp-64h] BYREF
  unsigned int v32; // [rsp+150h] [rbp-60h] BYREF
  unsigned int v33; // [rsp+154h] [rbp-5Ch] BYREF
  unsigned int v34; // [rsp+158h] [rbp-58h] BYREF
  unsigned int DescriptorValidationInfo; // [rsp+15Ch] [rbp-54h] BYREF
  unsigned int ProblemCode; // [rsp+160h] [rbp-50h] BYREF
  unsigned int DeviceProperties; // [rsp+164h] [rbp-4Ch] BYREF
  int v38; // [rsp+168h] [rbp-48h] BYREF
  int v39; // [rsp+16Ch] [rbp-44h] BYREF
  unsigned int TroubleshooterRootCause; // [rsp+170h] [rbp-40h] BYREF
  unsigned int DeviceCategory; // [rsp+174h] [rbp-3Ch] BYREF
  int v42; // [rsp+178h] [rbp-38h] BYREF
  BOOL v43; // [rsp+17Ch] [rbp-34h] BYREF
  unsigned int v44; // [rsp+180h] [rbp-30h] BYREF
  int v45; // [rsp+184h] [rbp-2Ch] BYREF
  BOOL v46; // [rsp+188h] [rbp-28h] BYREF
  BOOL v47; // [rsp+18Ch] [rbp-24h] BYREF
  __int128 v48; // [rsp+190h] [rbp-20h] BYREF
  _bstr_t::Data_t *v49[2]; // [rsp+1A0h] [rbp-10h] BYREF
  _bstr_t::Data_t *v50; // [rsp+1B0h] [rbp+0h]
  __int64 *v51; // [rsp+1B8h] [rbp+8h] BYREF
  _QWORD *v52; // [rsp+1C0h] [rbp+10h]
  _QWORD *v53; // [rsp+1C8h] [rbp+18h]
  _bstr_t::Data_t *v54; // [rsp+1D0h] [rbp+20h] BYREF
  const char *v55; // [rsp+1D8h] [rbp+28h] BYREF
  const char *v56; // [rsp+1E0h] [rbp+30h] BYREF
  _QWORD *v57; // [rsp+1E8h] [rbp+38h] BYREF
  _QWORD *v58; // [rsp+1F0h] [rbp+40h] BYREF
  CRegistryKey *v59; // [rsp+250h] [rbp+A0h] BYREF
  CRegistryKey *v60; // [rsp+258h] [rbp+A8h] BYREF
  CRegistryKey *v61; // [rsp+260h] [rbp+B0h] BYREF
  int v62; // [rsp+268h] [rbp+B8h] BYREF

  v48 = 0;
  v4 = 0;
  v51 = 0;
  v52 = 0;
  v53 = 0;
  v49[0] = 0;
  v49[1] = 0;
  v50 = 0;
  CUsbDevice::GetHardwareIdInformation((CUsbDevice *)a2, (struct _HARDWARE_ID_INFO *)&v51);
  DeviceProperties = CUsbDevice::GetDeviceProperties((CUsbDevice *)a2);
  DeviceCategory = CUsbDeviceSqm::GetDeviceCategory(v5, (struct CUsbDevice *)a2);
  v60 = 0;
  LOWORD(v59) = 0;
  v6 = CUsbDevice::TryGetPersistedDeviceUsbFlagsKey((unsigned __int16 *)a2, &v60)
    && CRegistryKey::QueryFixedLengthValue(v60, L"osvc", 2u, (unsigned __int8 *)&v59)
    && (_BYTE)v59 != 0;
  std::unique_ptr<CRegistryKey>::~unique_ptr<CRegistryKey>(&v60);
  v61 = 0;
  LOBYTE(v59) = 0;
  CDevNode::GetHardwareKey(*a2, &v61);
  if ( CRegistryKey::QueryBoolValue(v61, L"DeviceSelectiveSuspended", (unsigned __int8 *)&v59) )
    LOBYTE(v60) = (_BYTE)v59;
  else
    LOBYTE(v60) = 0;
  std::unique_ptr<CRegistryKey>::~unique_ptr<CRegistryKey>(&v61);
  v61 = 0;
  LOBYTE(v59) = 0;
  v7 = (unsigned __int8)CUsbDevice::TryGetDeviceUsbFlagsKey(a2, &v61)
    && CRegistryKey::QueryFixedLengthValue(v61, L"ResetOnResume", 1u, (unsigned __int8 *)&v59)
    && (_BYTE)v59 != 0;
  std::unique_ptr<CRegistryKey>::~unique_ptr<CRegistryKey>(&v61);
  v61 = 0;
  LOBYTE(v59) = 0;
  if ( (unsigned __int8)CUsbDevice::TryGetDeviceUsbFlagsKey(a2, &v61)
    && CRegistryKey::QueryBoolValue(v61, L"MSOSDescriptorHang", (unsigned __int8 *)&v59) )
  {
    v8 = (unsigned __int8)v59;
  }
  else
  {
    v8 = 0;
  }
  std::unique_ptr<CRegistryKey>::~unique_ptr<CRegistryKey>(&v61);
  TroubleshooterRootCause = CUsbDevice::GetTroubleshooterRootCause((CUsbDevice *)a2);
  v61 = 0;
  LODWORD(v59) = 0;
  if ( (unsigned __int8)CUsbDevice::TryGetDeviceUsbCeipKey(a2, &v61) )
  {
    LODWORD(v59) = 0;
    CRegistryKey::QueryFixedLengthValue(v61, L"NewInterfaceUsage", 4u, (unsigned __int8 *)&v59);
  }
  v39 = (int)v59;
  std::unique_ptr<CRegistryKey>::~unique_ptr<CRegistryKey>(&v61);
  v61 = 0;
  LODWORD(v59) = 0;
  CDevNode::GetHardwareKey(*a2, &v61);
  LODWORD(v59) = 0;
  CRegistryKey::QueryFixedLengthValue(v61, L"MsOS20Flags", 4u, (unsigned __int8 *)&v59);
  v38 = (int)v59;
  std::unique_ptr<CRegistryKey>::~unique_ptr<CRegistryKey>(&v61);
  ProblemCode = CDevNode::GetProblemCode(*a2);
  v61 = 0;
  LODWORD(v59) = 0;
  CDevNode::GetHardwareKey(*a2, &v61);
  LODWORD(v59) = 0;
  if ( CRegistryKey::QueryFixedLengthValue(v61, L"EnumerationFailureCode", 4u, (unsigned __int8 *)&v59) )
    v25 = (int)v59;
  else
    v25 = 0;
  std::unique_ptr<CRegistryKey>::~unique_ptr<CRegistryKey>(&v61);
  DescriptorValidationInfo = CUsbDevice::GetDescriptorValidationInfo((CUsbDevice *)a2, 0);
  v34 = CUsbDevice::GetDescriptorValidationInfo((CUsbDevice *)a2, 1u);
  v33 = CUsbDevice::GetDescriptorValidationInfo((CUsbDevice *)a2, 2u);
  v32 = CUsbDevice::GetDescriptorValidationInfo((CUsbDevice *)a2, 3u);
  v31 = CUsbDevice::GetDescriptorValidationInfo((CUsbDevice *)a2, 4u);
  v30 = CUsbDevice::GetDescriptorValidationInfo((CUsbDevice *)a2, 5u);
  v29 = CUsbDevice::GetDescriptorValidationInfo((CUsbDevice *)a2, 6u);
  if ( !*(_BYTE *)this )
  {
    CUsbDevice::ClearTroubleshooterRootCause((CUsbDevice *)a2);
    v59 = 0;
    if ( (unsigned __int8)CUsbDevice::TryGetDeviceUsbCeipKey(a2, &v59) )
      CRegistryKey::SetUlongValue((HKEY *)v59, L"NewInterfaceUsage");
    std::unique_ptr<CRegistryKey>::~unique_ptr<CRegistryKey>(&v59);
    CUsbDevice::ClearDeviceProperties((CUsbDevice *)a2);
  }
  if ( CUsbDevice::IsFunctional((CUsbDevice *)a2) )
  {
    CUsbDevice::GetDeviceClassInformation(v10, (struct _USB_DEVICE_CLASS_INFORMATION *)&v48);
    if ( a2[3] )
    {
      CUsbDevice::GetHardwareIdInformation(a2[1], (struct _HARDWARE_ID_INFO *)v49);
      v11 = v50;
    }
    else
    {
      v11 = 0;
      *(_OWORD *)v49 = 0;
      v50 = 0;
    }
    v28 = *((_DWORD *)a2 + 8) == 2;
    v24 = *((_DWORD *)a2 + 9);
    LODWORD(v61) = DWORD1(v48);
    v62 = v48;
    LODWORD(v59) = DWORD2(v48);
    if ( v49[0] )
      String = _bstr_t::Data_t::GetString(v49[0]);
    else
      String = 0;
    if ( v49[1] )
      v4 = _bstr_t::Data_t::GetString(v49[1]);
    if ( v11 )
      v11 = (_bstr_t::Data_t *)_bstr_t::Data_t::GetString(v11);
    InterfaceAssociationDescriptorCount = CUsbDevice::GetInterfaceAssociationDescriptorCount((CUsbDevice *)a2);
    EnumerationRetryCount = CUsbDevice::GetEnumerationRetryCount((CUsbDevice *)a2);
    CUsbDevice::GetInterconnectType((CUsbDevice *)a2);
    v13 = InterfaceAssociationDescriptorCount;
    v14 = HIDWORD(v48);
    v15 = v28;
  }
  else
  {
    v15 = 0;
    v24 = -1;
    v62 = 0;
    LODWORD(v61) = 0;
    LODWORD(v59) = 0;
    String = 0;
    v11 = 0;
    v13 = 0;
    v14 = 0;
  }
  if ( (unsigned int)dword_18001C038 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18001C038, v9, v13, v14) )
  {
    v28 = v19;
    EnumerationRetryCount = v18;
    InterfaceAssociationDescriptorCount = v17;
    v42 = v16;
    v54 = v11;
    v55 = v4;
    v56 = String;
    v43 = v15;
    v20 = DeviceProperties;
    DeviceProperties >>= 9;
    v44 = v20;
    v45 = v8;
    v46 = v7;
    LODWORD(v60) = (unsigned __int8)v60;
    v47 = v6;
    v21 = v53;
    if ( v53 )
      v21 = (_QWORD *)*v53;
    v57 = v21;
    v22 = v52;
    if ( v52 )
      v22 = (_QWORD *)*v52;
    v58 = v22;
    if ( v51 )
      v23 = *v51;
    else
      v23 = 0;
    *(_QWORD *)&v48 = v23;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      v23,
      (unsigned int)word_1800176FA,
      v16,
      v17,
      (__int64)&v48,
      (__int64)&v58,
      (__int64)&v57,
      (__int64)&DeviceCategory,
      (__int64)&v47,
      (__int64)&v60,
      (__int64)&v46,
      (__int64)&v45,
      (__int64)&TroubleshooterRootCause,
      (__int64)&v39,
      (__int64)&v38,
      (__int64)&v44,
      (__int64)&DeviceProperties,
      (__int64)&ProblemCode,
      (__int64)&v25,
      (__int64)&DescriptorValidationInfo,
      (__int64)&v34,
      (__int64)&v33,
      (__int64)&v32,
      (__int64)&v31,
      (__int64)&v30,
      (__int64)&v29,
      (__int64)&v43,
      (__int64)&v24,
      (__int64)&v62,
      (__int64)&v61,
      (__int64)&v59,
      (__int64)&v56,
      (__int64)&v55,
      (__int64)&v54,
      (__int64)&v42,
      (__int64)&InterfaceAssociationDescriptorCount,
      (__int64)&EnumerationRetryCount,
      (__int64)&v28);
  }
  _HARDWARE_ID_INFO::~_HARDWARE_ID_INFO((_HARDWARE_ID_INFO *)v49);
  _HARDWARE_ID_INFO::~_HARDWARE_ID_INFO((_HARDWARE_ID_INFO *)&v51);
}

```

## disassembly

```asm
0x1800045d0  push    rbp
0x1800045d2  push    rbx
0x1800045d3  push    rsi
0x1800045d4  push    rdi
0x1800045d5  push    r12
0x1800045d7  push    r13
0x1800045d9  push    r14
0x1800045db  push    r15
0x1800045dd  lea     rbp, [rsp-58h]
0x1800045e2  sub     rsp, 208h
0x1800045e9  mov     rbx, rdx
0x1800045ec  mov     rdi, rcx
0x1800045ef  xorps   xmm0, xmm0
0x1800045f2  movups  [rbp+90h+var_B0], xmm0
0x1800045f6  xor     r15d, r15d
0x1800045f9  mov     [rbp+90h+var_88], r15
0x1800045fd  mov     [rbp+90h+var_80], r15
0x180004601  mov     [rbp+90h+var_78], r15
0x180004605  mov     [rbp+90h+var_A0], r15
0x180004609  mov     [rbp+90h+var_A0+8], r15
0x18000460d  mov     [rbp+90h+var_90], r15
0x180004611  lea     rdx, [rbp+90h+var_88]; struct _HARDWARE_ID_INFO *
0x180004615  mov     rcx, rbx; this
0x180004618  call    ?GetHardwareIdInformation@CUsbDevice@@QEAAXPEAU_HARDWARE_ID_INFO@@@Z; CUsbDevice::GetHardwareIdInformation(_HARDWARE_ID_INFO *)
0x18000461d  mov     rcx, rbx; this
0x180004620  call    ?GetDeviceProperties@CUsbDevice@@QEAAKXZ; CUsbDevice::GetDeviceProperties(void)
0x180004625  mov     [rbp+90h+var_DC], eax
0x180004628  mov     rdx, rbx; struct CUsbDevice *
0x18000462b  call    ?GetDeviceCategory@CUsbDeviceSqm@@AEAAKAEAVCUsbDevice@@@Z; CUsbDeviceSqm::GetDeviceCategory(CUsbDevice &)
0x180004630  mov     [rbp+90h+var_CC], eax
0x180004633  mov     [rbp+90h+arg_8], r15
0x18000463a  mov     word ptr [rbp+90h+arg_0], r15w
0x180004642  lea     rdx, [rbp+90h+arg_8]
0x180004649  mov     rcx, rbx
0x18000464c  call    ?TryGetPersistedDeviceUsbFlagsKey@CUsbDevice@@AEAAEAEAV?$unique_ptr@VCRegistryKey@@U?$default_delete@VCRegistryKey@@@std@@@std@@@Z; CUsbDevice::TryGetPersistedDeviceUsbFlagsKey(std::unique_ptr<CRegistryKey> &)
0x180004651  lea     r13d, [r15+1]
0x180004655  test    al, al
0x180004657  jnz     short loc_18000465E
0x180004659  mov     r14d, r15d
0x18000465c  jmp     short loc_180004691
0x18000465e  lea     r9, [rbp+90h+arg_0]; unsigned __int8 *
0x180004665  mov     r8d, 2; unsigned int
0x18000466b  lea     rdx, aOsvc; "osvc"
0x180004672  mov     rcx, [rbp+90h+arg_8]; this
0x180004679  call    ?QueryFixedLengthValue@CRegistryKey@@QEAAEPEBGKPEAE@Z; CRegistryKey::QueryFixedLengthValue(ushort const *,ulong,uchar *)
0x18000467e  test    al, al
0x180004680  jz      short loc_180004659
0x180004682  cmp     byte ptr [rbp+90h+arg_0], r15b
0x180004689  mov     r14d, r15d
0x18000468c  jz      short loc_180004691
0x18000468e  mov     r14d, r13d
0x180004691  lea     rcx, [rbp+90h+arg_8]
0x180004698  call    ??1?$unique_ptr@VCRegistryKey@@U?$default_delete@VCRegistryKey@@@std@@@std@@QEAA@XZ; std::unique_ptr<CRegistryKey>::~unique_ptr<CRegistryKey>(void)
0x18000469d  mov     [rbp+90h+arg_10], r15
0x1800046a4  mov     byte ptr [rbp+90h+arg_0], r15b
0x1800046ab  lea     rdx, [rbp+90h+arg_10]
0x1800046b2  mov     rcx, [rbx]
0x1800046b5  call    ?GetHardwareKey@CDevNode@@QEAAXAEAV?$unique_ptr@VCRegistryKey@@U?$default_delete@VCRegistryKey@@@std@@@std@@@Z; CDevNode::GetHardwareKey(std::unique_ptr<CRegistryKey> &)
0x1800046ba  lea     r8, [rbp+90h+arg_0]; unsigned __int8 *
0x1800046c1  lea     rdx, aDeviceselectiv; "DeviceSelectiveSuspended"
0x1800046c8  mov     rcx, [rbp+90h+arg_10]; this
0x1800046cf  call    ?QueryBoolValue@CRegistryKey@@QEAAEPEBGAEAE@Z; CRegistryKey::QueryBoolValue(ushort const *,uchar &)
0x1800046d4  test    al, al
0x1800046d6  jnz     short loc_1800046E1
0x1800046d8  mov     byte ptr [rbp+90h+arg_8], r15b
0x1800046df  jmp     short loc_1800046ED
0x1800046e1  mov     al, byte ptr [rbp+90h+arg_0]
0x1800046e7  mov     byte ptr [rbp+90h+arg_8], al
0x1800046ed  lea     rcx, [rbp+90h+arg_10]
0x1800046f4  call    ??1?$unique_ptr@VCRegistryKey@@U?$default_delete@VCRegistryKey@@@std@@@std@@QEAA@XZ; std::unique_ptr<CRegistryKey>::~unique_ptr<CRegistryKey>(void)
0x1800046f9  mov     [rbp+90h+arg_10], r15
0x180004700  mov     byte ptr [rbp+90h+arg_0], r15b
0x180004707  lea     rdx, [rbp+90h+arg_10]
0x18000470e  mov     rcx, rbx
0x180004711  call    ?TryGetDeviceUsbFlagsKey@CUsbDevice@@AEAAEAEAV?$unique_ptr@VCRegistryKey@@U?$default_delete@VCRegistryKey@@@std@@@std@@@Z; CUsbDevice::TryGetDeviceUsbFlagsKey(std::unique_ptr<CRegistryKey> &)
0x180004716  test    al, al
0x180004718  jnz     short loc_18000471F
0x18000471a  mov     esi, r15d
0x18000471d  jmp     short loc_18000474F
0x18000471f  lea     r9, [rbp+90h+arg_0]; unsigned __int8 *
0x180004726  mov     r8d, r13d; unsigned int
0x180004729  lea     rdx, aResetonresume; "ResetOnResume"
0x180004730  mov     rcx, [rbp+90h+arg_10]; this
0x180004737  call    ?QueryFixedLengthValue@CRegistryKey@@QEAAEPEBGKPEAE@Z; CRegistryKey::QueryFixedLengthValue(ushort const *,ulong,uchar *)
0x18000473c  test    al, al
0x18000473e  jz      short loc_18000471A
0x180004740  cmp     byte ptr [rbp+90h+arg_0], r15b
0x180004747  mov     esi, r15d
0x18000474a  jz      short loc_18000474F
0x18000474c  mov     esi, r13d
0x18000474f  lea     rcx, [rbp+90h+arg_10]
0x180004756  call    ??1?$unique_ptr@VCRegistryKey@@U?$default_delete@VCRegistryKey@@@std@@@std@@QEAA@XZ; std::unique_ptr<CRegistryKey>::~unique_ptr<CRegistryKey>(void)
0x18000475b  mov     [rbp+90h+arg_10], r15
0x180004762  mov     byte ptr [rbp+90h+arg_0], r15b
0x180004769  lea     rdx, [rbp+90h+arg_10]
0x180004770  mov     rcx, rbx
0x180004773  call    ?TryGetDeviceUsbFlagsKey@CUsbDevice@@AEAAEAEAV?$unique_ptr@VCRegistryKey@@U?$default_delete@VCRegistryKey@@@std@@@std@@@Z; CUsbDevice::TryGetDeviceUsbFlagsKey(std::unique_ptr<CRegistryKey> &)
0x180004778  test    al, al
0x18000477a  jnz     short loc_180004781
0x18000477c  mov     r12b, r15b
0x18000477f  jmp     short loc_1800047A6
0x180004781  lea     r8, [rbp+90h+arg_0]; unsigned __int8 *
0x180004788  lea     rdx, aMsosdescriptor; "MSOSDescriptorHang"
0x18000478f  mov     rcx, [rbp+90h+arg_10]; this
0x180004796  call    ?QueryBoolValue@CRegistryKey@@QEAAEPEBGAEAE@Z; CRegistryKey::QueryBoolValue(ushort const *,uchar &)
0x18000479b  test    al, al
0x18000479d  jz      short loc_18000477C
0x18000479f  mov     r12b, byte ptr [rbp+90h+arg_0]
0x1800047a6  lea     rcx, [rbp+90h+arg_10]
0x1800047ad  call    ??1?$unique_ptr@VCRegistryKey@@U?$default_delete@VCRegistryKey@@@std@@@std@@QEAA@XZ; std::unique_ptr<CRegistryKey>::~unique_ptr<CRegistryKey>(void)
0x1800047b2  mov     rcx, rbx; this
0x1800047b5  call    ?GetTroubleshooterRootCause@CUsbDevice@@QEAAKXZ; CUsbDevice::GetTroubleshooterRootCause(void)
0x1800047ba  mov     [rbp+90h+var_D0], eax
0x1800047bd  mov     [rbp+90h+arg_10], r15
0x1800047c4  mov     dword ptr [rbp+90h+arg_0], r15d
0x1800047cb  lea     rdx, [rbp+90h+arg_10]
0x1800047d2  mov     rcx, rbx
0x1800047d5  call    ?TryGetDeviceUsbCeipKey@CUsbDevice@@AEAAEAEAV?$unique_ptr@VCRegistryKey@@U?$default_delete@VCRegistryKey@@@std@@@std@@@Z; CUsbDevice::TryGetDeviceUsbCeipKey(std::unique_ptr<CRegistryKey> &)
0x1800047da  test    al, al
0x1800047dc  jz      short loc_180004805
0x1800047de  mov     dword ptr [rbp+90h+arg_0], r15d
0x1800047e5  lea     r9, [rbp+90h+arg_0]; unsigned __int8 *
0x1800047ec  mov     r8d, 4; unsigned int
0x1800047f2  lea     rdx, aNewinterfaceus; "NewInterfaceUsage"
0x1800047f9  mov     rcx, [rbp+90h+arg_10]; this
0x180004800  call    ?QueryFixedLengthValue@CRegistryKey@@QEAAEPEBGKPEAE@Z; CRegistryKey::QueryFixedLengthValue(ushort const *,ulong,uchar *)
0x180004805  mov     eax, dword ptr [rbp+90h+arg_0]
0x18000480b  mov     [rbp+90h+var_D4], eax
0x18000480e  lea     rcx, [rbp+90h+arg_10]
0x180004815  call    ??1?$unique_ptr@VCRegistryKey@@U?$default_delete@VCRegistryKey@@@std@@@std@@QEAA@XZ; std::unique_ptr<CRegistryKey>::~unique_ptr<CRegistryKey>(void)
0x18000481a  mov     [rbp+90h+arg_10], r15
0x180004821  mov     dword ptr [rbp+90h+arg_0], r15d
0x180004828  lea     rdx, [rbp+90h+arg_10]
0x18000482f  mov     rcx, [rbx]
0x180004832  call    ?GetHardwareKey@CDevNode@@QEAAXAEAV?$unique_ptr@VCRegistryKey@@U?$default_delete@VCRegistryKey@@@std@@@std@@@Z; CDevNode::GetHardwareKey(std::unique_ptr<CRegistryKey> &)
0x180004837  mov     dword ptr [rbp+90h+arg_0], r15d
0x18000483e  lea     r9, [rbp+90h+arg_0]; unsigned __int8 *
0x180004845  mov     r8d, 4; unsigned int
0x18000484b  lea     rdx, aMsos20flags; "MsOS20Flags"
0x180004852  mov     rcx, [rbp+90h+arg_10]; this
0x180004859  call    ?QueryFixedLengthValue@CRegistryKey@@QEAAEPEBGKPEAE@Z; CRegistryKey::QueryFixedLengthValue(ushort const *,ulong,uchar *)
0x18000485e  mov     eax, dword ptr [rbp+90h+arg_0]
0x180004864  mov     [rbp+90h+var_D8], eax
0x180004867  lea     rcx, [rbp+90h+arg_10]
0x18000486e  call    ??1?$unique_ptr@VCRegistryKey@@U?$default_delete@VCRegistryKey@@@std@@@std@@QEAA@XZ; std::unique_ptr<CRegistryKey>::~unique_ptr<CRegistryKey>(void)
0x180004873  mov     rcx, [rbx]; this
0x180004876  call    ?GetProblemCode@CDevNode@@QEAAKXZ; CDevNode::GetProblemCode(void)
0x18000487b  mov     [rbp+90h+var_E0], eax
0x18000487e  mov     [rbp+90h+arg_10], r15
0x180004885  mov     dword ptr [rbp+90h+arg_0], r15d
0x18000488c  lea     rdx, [rbp+90h+arg_10]
0x180004893  mov     rcx, [rbx]
0x180004896  call    ?GetHardwareKey@CDevNode@@QEAAXAEAV?$unique_ptr@VCRegistryKey@@U?$default_delete@VCRegistryKey@@@std@@@std@@@Z; CDevNode::GetHardwareKey(std::unique_ptr<CRegistryKey> &)
0x18000489b  mov     dword ptr [rbp+90h+arg_0], r15d
0x1800048a2  lea     r9, [rbp+90h+arg_0]; unsigned __int8 *
0x1800048a9  mov     r8d, 4; unsigned int
0x1800048af  lea     rdx, aEnumerationfai; "EnumerationFailureCode"
0x1800048b6  mov     rcx, [rbp+90h+arg_10]; this
0x1800048bd  call    ?QueryFixedLengthValue@CRegistryKey@@QEAAEPEBGKPEAE@Z; CRegistryKey::QueryFixedLengthValue(ushort const *,ulong,uchar *)
0x1800048c2  test    al, al
0x1800048c4  jnz     short loc_1800048CC
0x1800048c6  mov     [rbp+90h+var_10C], r15d
0x1800048ca  jmp     short loc_1800048D5
0x1800048cc  mov     eax, dword ptr [rbp+90h+arg_0]
0x1800048d2  mov     [rbp+90h+var_10C], eax
0x1800048d5  lea     rcx, [rbp+90h+arg_10]
0x1800048dc  call    ??1?$unique_ptr@VCRegistryKey@@U?$default_delete@VCRegistryKey@@@std@@@std@@QEAA@XZ; std::unique_ptr<CRegistryKey>::~unique_ptr<CRegistryKey>(void)
0x1800048e1  xor     edx, edx; unsigned int
0x1800048e3  mov     rcx, rbx; this
0x1800048e6  call    ?GetDescriptorValidationInfo@CUsbDevice@@QEAAKK@Z; CUsbDevice::GetDescriptorValidationInfo(ulong)
0x1800048eb  mov     [rbp+90h+var_E4], eax
0x1800048ee  mov     edx, r13d; unsigned int
0x1800048f1  mov     rcx, rbx; this
0x1800048f4  call    ?GetDescriptorValidationInfo@CUsbDevice@@QEAAKK@Z; CUsbDevice::GetDescriptorValidationInfo(ulong)
0x1800048f9  mov     [rbp+90h+var_E8], eax
0x1800048fc  mov     edx, 2; unsigned int
0x180004901  mov     rcx, rbx; this
0x180004904  call    ?GetDescriptorValidationInfo@CUsbDevice@@QEAAKK@Z; CUsbDevice::GetDescriptorValidationInfo(ulong)
0x180004909  mov     [rbp+90h+var_EC], eax
0x18000490c  mov     edx, 3; unsigned int
0x180004911  mov     rcx, rbx; this
0x180004914  call    ?GetDescriptorValidationInfo@CUsbDevice@@QEAAKK@Z; CUsbDevice::GetDescriptorValidationInfo(ulong)
0x180004919  mov     [rbp+90h+var_F0], eax
0x18000491c  mov     edx, 4; unsigned int
0x180004921  mov     rcx, rbx; this
0x180004924  call    ?GetDescriptorValidationInfo@CUsbDevice@@QEAAKK@Z; CUsbDevice::GetDescriptorValidationInfo(ulong)
0x180004929  mov     [rbp+90h+var_F4], eax
0x18000492c  mov     edx, 5; unsigned int
0x180004931  mov     rcx, rbx; this
0x180004934  call    ?GetDescriptorValidationInfo@CUsbDevice@@QEAAKK@Z; CUsbDevice::GetDescriptorValidationInfo(ulong)
0x180004939  mov     [rbp+90h+var_F8], eax
0x18000493c  mov     edx, 6; unsigned int
0x180004941  mov     rcx, rbx; this
0x180004944  call    ?GetDescriptorValidationInfo@CUsbDevice@@QEAAKK@Z; CUsbDevice::GetDescriptorValidationInfo(ulong)
0x180004949  mov     [rbp+90h+var_FC], eax
0x18000494c  cmp     [rdi], r15b
0x18000494f  jnz     short loc_18000499B
0x180004951  mov     rcx, rbx; this
0x180004954  call    ?ClearTroubleshooterRootCause@CUsbDevice@@QEAAXXZ; CUsbDevice::ClearTroubleshooterRootCause(void)
0x180004959  mov     [rbp+90h+arg_0], r15
0x180004960  lea     rdx, [rbp+90h+arg_0]
0x180004967  mov     rcx, rbx
0x18000496a  call    ?TryGetDeviceUsbCeipKey@CUsbDevice@@AEAAEAEAV?$unique_ptr@VCRegistryKey@@U?$default_delete@VCRegistryKey@@@std@@@std@@@Z; CUsbDevice::TryGetDeviceUsbCeipKey(std::unique_ptr<CRegistryKey> &)
0x18000496f  test    al, al
0x180004971  jz      short loc_180004987
0x180004973  lea     rdx, aNewinterfaceus; "NewInterfaceUsage"
0x18000497a  mov     rcx, [rbp+90h+arg_0]; this
0x180004981  call    ?SetUlongValue@CRegistryKey@@QEAAXPEBGK@Z; CRegistryKey::SetUlongValue(ushort const *,ulong)
0x180004986  nop
0x180004987  lea     rcx, [rbp+90h+arg_0]
0x18000498e  call    ??1?$unique_ptr@VCRegistryKey@@U?$default_delete@VCRegistryKey@@@std@@@std@@QEAA@XZ; std::unique_ptr<CRegistryKey>::~unique_ptr<CRegistryKey>(void)
0x180004993  mov     rcx, rbx; this
0x180004996  call    ?ClearDeviceProperties@CUsbDevice@@QEAAXXZ; CUsbDevice::ClearDeviceProperties(void)
0x18000499b  mov     rcx, rbx; this
0x18000499e  call    ?IsFunctional@CUsbDevice@@QEAAEXZ; CUsbDevice::IsFunctional(void)
0x1800049a3  test    al, al
0x1800049a5  jz      loc_180004A71
0x1800049ab  lea     rdx, [rbp+90h+var_B0]; struct _USB_DEVICE_CLASS_INFORMATION *
0x1800049af  call    ?GetDeviceClassInformation@CUsbDevice@@QEAAXPEAU_USB_DEVICE_CLASS_INFORMATION@@@Z; CUsbDevice::GetDeviceClassInformation(_USB_DEVICE_CLASS_INFORMATION *)
0x1800049b4  cmp     [rbx+18h], r15
0x1800049b8  jz      short loc_1800049CD
0x1800049ba  lea     rdx, [rbp+90h+var_A0]; struct _HARDWARE_ID_INFO *
0x1800049be  mov     rcx, [rbx+8]; this
0x1800049c2  call    ?GetHardwareIdInformation@CUsbDevice@@QEAAXPEAU_HARDWARE_ID_INFO@@@Z; CUsbDevice::GetHardwareIdInformation(_HARDWARE_ID_INFO *)
0x1800049c7  mov     rdi, [rbp+90h+var_90]
0x1800049cb  jmp     short loc_1800049DA
0x1800049cd  xorps   xmm0, xmm0
0x1800049d0  xor     edi, edi
0x1800049d2  movups  xmmword ptr [rbp+90h+var_A0], xmm0
0x1800049d6  mov     [rbp+90h+var_90], rdi
0x1800049da  mov     eax, r15d
0x1800049dd  cmp     dword ptr [rbx+20h], 2
0x1800049e1  setz    al
0x1800049e4  mov     [rbp+90h+var_100], eax
0x1800049e7  mov     eax, [rbx+24h]
0x1800049ea  mov     [rbp+90h+var_110], eax
0x1800049ed  mov     eax, dword ptr [rbp+90h+var_B0]
0x1800049f0  mov     [rbp+90h+arg_18], eax
0x1800049f6  mov     eax, dword ptr [rbp+90h+var_B0+4]
0x1800049f9  mov     dword ptr [rbp+90h+arg_10], eax
0x1800049ff  mov     eax, dword ptr [rbp+90h+var_B0+8]
0x180004a02  mov     dword ptr [rbp+90h+arg_0], eax
0x180004a08  mov     rcx, [rbp+90h+var_A0]; this
0x180004a0c  test    rcx, rcx
0x180004a0f  jz      short loc_180004A1B
0x180004a11  call    ?GetString@Data_t@_bstr_t@@QEBAPEBDXZ; _bstr_t::Data_t::GetString(void)
0x180004a16  mov     r13, rax
0x180004a19  jmp     short loc_180004A1E
0x180004a1b  mov     r13, r15
0x180004a1e  mov     rcx, [rbp+90h+var_A0+8]; this
0x180004a22  test    rcx, rcx
0x180004a25  jz      short loc_180004A2F
0x180004a27  call    ?GetString@Data_t@_bstr_t@@QEBAPEBDXZ; _bstr_t::Data_t::GetString(void)
0x180004a2c  mov     r15, rax
0x180004a2f  test    rdi, rdi
0x180004a32  jz      short loc_180004A3F
0x180004a34  mov     rcx, rdi; this
0x180004a37  call    ?GetString@Data_t@_bstr_t@@QEBAPEBDXZ; _bstr_t::Data_t::GetString(void)
0x180004a3c  mov     rdi, rax
0x180004a3f  mov     rcx, rbx; this
0x180004a42  call    ?GetInterfaceAssociationDescriptorCount@CUsbDevice@@QEAAKXZ; CUsbDevice::GetInterfaceAssociationDescriptorCount(void)
0x180004a47  mov     [rbp+90h+var_108], eax
0x180004a4a  mov     rcx, rbx; this
0x180004a4d  call    ?GetEnumerationRetryCount@CUsbDevice@@QEAAKXZ; CUsbDevice::GetEnumerationRetryCount(void)
0x180004a52  mov     [rbp+90h+var_104], eax
0x180004a55  mov     rcx, rbx; this
0x180004a58  call    ?GetInterconnectType@CUsbDevice@@QEAAKXZ; CUsbDevice::GetInterconnectType(void)
0x180004a5d  mov     r11d, eax
0x180004a60  mov     r8d, [rbp+90h+var_108]
0x180004a64  mov     r9d, dword ptr [rbp+90h+var_B0+0Ch]
0x180004a68  mov     r10d, [rbp+90h+var_104]
0x180004a6c  mov     ebx, [rbp+90h+var_100]
0x180004a6f  jmp     short loc_180004AA1
0x180004a71  mov     ebx, r15d
0x180004a74  mov     [rbp+90h+var_110], 0FFFFFFFFh
0x180004a7b  mov     [rbp+90h+arg_18], r15d
0x180004a82  mov     dword ptr [rbp+90h+arg_10], r15d
0x180004a89  mov     dword ptr [rbp+90h+arg_0], r15d
0x180004a90  mov     r13, r15
0x180004a93  xor     edi, edi
0x180004a95  xor     r8d, r8d
0x180004a98  xor     r9d, r9d
0x180004a9b  xor     r10d, r10d
0x180004a9e  xor     r11d, r11d
0x180004aa1  mov     eax, cs:dword_18001C038
0x180004aa7  cmp     eax, 5
0x180004aaa  jbe     loc_180004D45
0x180004ab0  lea     rcx, dword_18001C038
0x180004ab7  call    _tlgKeywordOn
0x180004abc  test    al, al
0x180004abe  jz      loc_180004D45
0x180004ac4  mov     [rbp+90h+var_100], r11d
0x180004ac8  mov     [rbp+90h+var_104], r10d
0x180004acc  mov     [rbp+90h+var_108], r9d
0x180004ad0  mov     [rbp+90h+var_C8], r8d
0x180004ad4  mov     [rbp+90h+var_70], rdi
0x180004ad8  mov     [rbp+90h+var_68], r15
0x180004adc  mov     [rbp+90h+var_60], r13
0x180004ae0  mov     eax, dword ptr [rbp+90h+arg_0]
0x180004ae6  mov     dword ptr [rbp+90h+arg_0], eax
  ... truncated ...
```
