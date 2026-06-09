# CHidDeviceSqm::LogStreamEntry(CHidCollection &,CHidDevice &)

- ea: `0x180006f18`
- end: `0x18000712e`
- name: `?LogStreamEntry@CHidDeviceSqm@@AEAAXAEAVCHidCollection@@AEAVCHidDevice@@@Z`
- size: `534`
- prototype: `void __fastcall(CHidDeviceSqm *this, CDevNode **, volatile signed __int32 **)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180006d2c`

## callees

- `0x180001294`
- `0x180001cb0`
- `0x180003fec`
- `0x180004344`
- `0x180006f18`
- `0x180007248`
- `0x1800072b4`
- `0x1800073b4`
- `0x18000aa38`
- `0x18000aacc`
- `0x18000ab28`
- `0x18000ace8`
- `0x18000c0d0`
- `0x18000c114`

## string_xrefs

- `0x180006f51`: `SessionSecurityEnabled`

## pseudocode

```c
void __fastcall CHidDeviceSqm::LogStreamEntry(CHidDeviceSqm *this, CDevNode **a2, volatile signed __int32 **a3)
{
  int v5; // esi
  int v6; // r15d
  unsigned int Properties; // r12d
  unsigned int CollectionCount; // r13d
  unsigned int ProblemCode; // r14d
  volatile signed __int32 *v10; // rcx
  const char *String; // rbx
  __int64 v12; // rdx
  __int64 v13; // r8
  __int64 v14; // r9
  int v15; // ecx
  int v16; // r8d
  int v17; // r9d
  unsigned __int8 v18[4]; // [rsp+70h] [rbp-9h] BYREF
  int v19; // [rsp+74h] [rbp-5h] BYREF
  unsigned int v20; // [rsp+78h] [rbp-1h] BYREF
  CRegistryKey *v21; // [rsp+80h] [rbp+7h] BYREF
  const char *v22; // [rsp+88h] [rbp+Fh] BYREF
  CHidDeviceSqm *v23; // [rsp+E0h] [rbp+67h] BYREF
  CRegistryKey *v24; // [rsp+E8h] [rbp+6Fh] BYREF
  int v25; // [rsp+F0h] [rbp+77h] BYREF
  int v26; // [rsp+F8h] [rbp+7Fh] BYREF

  v23 = this;
  v5 = 0;
  v24 = 0;
  CDevNode::GetHardwareKey(*a2, &v24);
  v6 = 32;
  if ( CRegistryKey::QueryBoolValue(v24, L"SessionSecurityEnabled", (unsigned __int8 *)&v23) != 1 )
    v6 = 0;
  std::unique_ptr<CRegistryKey>::~unique_ptr<CRegistryKey>(&v24);
  Properties = CHidDevice::GetProperties((CHidDevice *)a3);
  LOWORD(v26) = 0;
  CDevNode::GetInterfaceProperty(*a2, &DEVPKEY_DeviceInterface_HID_VendorId, (unsigned __int16 *)&v26);
  LOWORD(v25) = 0;
  CDevNode::GetInterfaceProperty(*a2, &DEVPKEY_DeviceInterface_HID_ProductId, (unsigned __int16 *)&v25);
  LOWORD(v24) = 0;
  CDevNode::GetInterfaceProperty(*a2, &DEVPKEY_DeviceInterface_HID_VersionNumber, (unsigned __int16 *)&v24);
  LOBYTE(v23) = 0;
  CDevNode::GetInterfaceProperty(*a2, &DEVPKEY_DeviceInterface_HID_IsReadOnly, (unsigned __int8 *)&v23);
  CollectionCount = CHidDevice::GetCollectionCount((CHidDevice *)a3);
  if ( *((_BYTE *)a3 + 9) == 1 )
    ProblemCode = CDevNode::GetProblemCode((CDevNode *)*a3);
  else
    ProblemCode = 0;
  v21 = 0;
  *(_DWORD *)v18 = 0;
  CDevNode::GetHardwareKey(*a3, &v21);
  *(_DWORD *)v18 = 0;
  if ( CRegistryKey::QueryFixedLengthValue(v21, L"ParserErrorCode", 4u, v18) )
    v5 = *(_DWORD *)v18;
  std::unique_ptr<CRegistryKey>::~unique_ptr<CRegistryKey>(&v21);
  v10 = a3[2];
  v21 = (CRegistryKey *)v10;
  if ( v10 )
  {
    _InterlockedIncrement(v10 + 4);
    String = _bstr_t::Data_t::GetString((_bstr_t::Data_t *)v10);
  }
  else
  {
    String = 0;
  }
  _bstr_t::_Free((_bstr_t *)&v21);
  if ( (unsigned int)dword_18001C038 > 5 )
  {
    if ( (unsigned __int8)tlgKeywordOn(&dword_18001C038, v12, v13, v14) )
    {
      *(_DWORD *)v18 = Properties | v6;
      v22 = String;
      v19 = v5;
      v20 = ProblemCode;
      LODWORD(v21) = CollectionCount;
      LODWORD(v23) = (unsigned __int8)v23;
      LODWORD(v24) = (unsigned __int16)v24;
      v25 = (unsigned __int16)v25;
      v26 = (unsigned __int16)v26;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        v15,
        (unsigned int)byte_180017C9B,
        v16,
        v17,
        (__int64)&v26,
        (__int64)&v25,
        (__int64)&v24,
        (__int64)&v23,
        (__int64)&v21,
        (__int64)&v20,
        (__int64)&v19,
        (__int64)&v22,
        (__int64)v18);
    }
  }
}

```

## disassembly

```asm
0x180006f18  mov     [rsp-8+arg_0], rcx
0x180006f1d  push    rbp
0x180006f1e  push    rbx
0x180006f1f  push    rsi
0x180006f20  push    rdi
0x180006f21  push    r12
0x180006f23  push    r13
0x180006f25  push    r14
0x180006f27  push    r15
0x180006f29  lea     rbp, [rsp-1Fh]
0x180006f2e  sub     rsp, 98h
0x180006f35  mov     rdi, r8
0x180006f38  mov     rbx, rdx
0x180006f3b  xor     esi, esi
0x180006f3d  mov     [rbp+57h+arg_8], rsi
0x180006f41  lea     rdx, [rbp+57h+arg_8]
0x180006f45  mov     rcx, [rbx]
0x180006f48  call    ?GetHardwareKey@CDevNode@@QEAAXAEAV?$unique_ptr@VCRegistryKey@@U?$default_delete@VCRegistryKey@@@std@@@std@@@Z; CDevNode::GetHardwareKey(std::unique_ptr<CRegistryKey> &)
0x180006f4d  lea     r8, [rbp+57h+arg_0]; unsigned __int8 *
0x180006f51  lea     rdx, aSessionsecurit; "SessionSecurityEnabled"
0x180006f58  mov     rcx, [rbp+57h+arg_8]; this
0x180006f5c  call    ?QueryBoolValue@CRegistryKey@@QEAAEPEBGAEAE@Z; CRegistryKey::QueryBoolValue(ushort const *,uchar &)
0x180006f61  nop
0x180006f62  lea     r15d, [rsi+20h]
0x180006f66  cmp     al, 1
0x180006f68  cmovnz  r15d, esi
0x180006f6c  lea     rcx, [rbp+57h+arg_8]
0x180006f70  call    ??1?$unique_ptr@VCRegistryKey@@U?$default_delete@VCRegistryKey@@@std@@@std@@QEAA@XZ; std::unique_ptr<CRegistryKey>::~unique_ptr<CRegistryKey>(void)
0x180006f75  mov     rcx, rdi; this
0x180006f78  call    ?GetProperties@CHidDevice@@QEAAKXZ; CHidDevice::GetProperties(void)
0x180006f7d  mov     r12d, eax
0x180006f80  mov     word ptr [rbp+57h+arg_18], si
0x180006f84  lea     r8, [rbp+57h+arg_18]; unsigned __int16 *
0x180006f88  lea     rdx, DEVPKEY_DeviceInterface_HID_VendorId; struct _DEVPROPKEY *
0x180006f8f  mov     rcx, [rbx]; this
0x180006f92  call    ?GetInterfaceProperty@CDevNode@@QEAAXAEBU_DEVPROPKEY@@AEAG@Z; CDevNode::GetInterfaceProperty(_DEVPROPKEY const &,ushort &)
0x180006f97  mov     word ptr [rbp+57h+arg_10], si
0x180006f9b  lea     r8, [rbp+57h+arg_10]; unsigned __int16 *
0x180006f9f  lea     rdx, DEVPKEY_DeviceInterface_HID_ProductId; struct _DEVPROPKEY *
0x180006fa6  mov     rcx, [rbx]; this
0x180006fa9  call    ?GetInterfaceProperty@CDevNode@@QEAAXAEBU_DEVPROPKEY@@AEAG@Z; CDevNode::GetInterfaceProperty(_DEVPROPKEY const &,ushort &)
0x180006fae  mov     word ptr [rbp+57h+arg_8], si
0x180006fb2  lea     r8, [rbp+57h+arg_8]; unsigned __int16 *
0x180006fb6  lea     rdx, DEVPKEY_DeviceInterface_HID_VersionNumber; struct _DEVPROPKEY *
0x180006fbd  mov     rcx, [rbx]; this
0x180006fc0  call    ?GetInterfaceProperty@CDevNode@@QEAAXAEBU_DEVPROPKEY@@AEAG@Z; CDevNode::GetInterfaceProperty(_DEVPROPKEY const &,ushort &)
0x180006fc5  mov     byte ptr [rbp+57h+arg_0], sil
0x180006fc9  lea     r8, [rbp+57h+arg_0]; unsigned __int8 *
0x180006fcd  lea     rdx, DEVPKEY_DeviceInterface_HID_IsReadOnly; struct _DEVPROPKEY *
0x180006fd4  mov     rcx, [rbx]; this
0x180006fd7  call    ?GetInterfaceProperty@CDevNode@@QEAAXAEBU_DEVPROPKEY@@AEAE@Z; CDevNode::GetInterfaceProperty(_DEVPROPKEY const &,uchar &)
0x180006fdc  mov     rcx, rdi; this
0x180006fdf  call    ?GetCollectionCount@CHidDevice@@QEAAKXZ; CHidDevice::GetCollectionCount(void)
0x180006fe4  mov     r13d, eax
0x180006fe7  cmp     byte ptr [rdi+9], 1
0x180006feb  jnz     short loc_180006FFA
0x180006fed  mov     rcx, [rdi]; this
0x180006ff0  call    ?GetProblemCode@CDevNode@@QEAAKXZ; CDevNode::GetProblemCode(void)
0x180006ff5  mov     r14d, eax
0x180006ff8  jmp     short loc_180006FFD
0x180006ffa  mov     r14d, esi
0x180006ffd  mov     [rbp+57h+var_50], rsi
0x180007001  mov     dword ptr [rbp+57h+var_60], esi
0x180007004  lea     rdx, [rbp+57h+var_50]
0x180007008  mov     rcx, [rdi]
0x18000700b  call    ?GetHardwareKey@CDevNode@@QEAAXAEAV?$unique_ptr@VCRegistryKey@@U?$default_delete@VCRegistryKey@@@std@@@std@@@Z; CDevNode::GetHardwareKey(std::unique_ptr<CRegistryKey> &)
0x180007010  mov     dword ptr [rbp+57h+var_60], esi
0x180007013  lea     r9, [rbp+57h+var_60]; unsigned __int8 *
0x180007017  mov     r8d, 4; unsigned int
0x18000701d  lea     rdx, aParsererrorcod; "ParserErrorCode"
0x180007024  mov     rcx, [rbp+57h+var_50]; this
0x180007028  call    ?QueryFixedLengthValue@CRegistryKey@@QEAAEPEBGKPEAE@Z; CRegistryKey::QueryFixedLengthValue(ushort const *,ulong,uchar *)
0x18000702d  test    al, al
0x18000702f  jz      short loc_180007034
0x180007031  mov     esi, dword ptr [rbp+57h+var_60]
0x180007034  lea     rcx, [rbp+57h+var_50]
0x180007038  call    ??1?$unique_ptr@VCRegistryKey@@U?$default_delete@VCRegistryKey@@@std@@@std@@QEAA@XZ; std::unique_ptr<CRegistryKey>::~unique_ptr<CRegistryKey>(void)
0x18000703d  mov     rcx, [rdi+10h]; this
0x180007041  mov     [rbp+57h+var_50], rcx
0x180007045  test    rcx, rcx
0x180007048  jz      short loc_18000704E
0x18000704a  lock inc dword ptr [rcx+10h]
0x18000704e  test    rcx, rcx
0x180007051  jz      short loc_18000705D
0x180007053  call    ?GetString@Data_t@_bstr_t@@QEBAPEBDXZ; _bstr_t::Data_t::GetString(void)
0x180007058  mov     rbx, rax
0x18000705b  jmp     short loc_18000705F
0x18000705d  xor     ebx, ebx
0x18000705f  lea     rcx, [rbp+57h+var_50]; this
0x180007063  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x180007068  mov     eax, cs:dword_18001C038
0x18000706e  cmp     eax, 5
0x180007071  jbe     loc_18000711A
0x180007077  lea     rcx, dword_18001C038
0x18000707e  call    _tlgKeywordOn
0x180007083  test    al, al
0x180007085  jz      loc_18000711A
0x18000708b  or      r15d, r12d
0x18000708e  mov     dword ptr [rbp+57h+var_60], r15d
0x180007092  mov     [rbp+57h+var_48], rbx
0x180007096  mov     [rbp+57h+var_5C], esi
0x180007099  mov     [rbp+57h+var_58], r14d
0x18000709d  mov     dword ptr [rbp+57h+var_50], r13d
0x1800070a1  movzx   eax, byte ptr [rbp+57h+arg_0]
0x1800070a5  mov     dword ptr [rbp+57h+arg_0], eax
0x1800070a8  movzx   eax, word ptr [rbp+57h+arg_8]
0x1800070ac  mov     dword ptr [rbp+57h+arg_8], eax
0x1800070af  movzx   eax, word ptr [rbp+57h+arg_10]
0x1800070b3  mov     [rbp+57h+arg_10], eax
0x1800070b6  movzx   eax, word ptr [rbp+57h+arg_18]
0x1800070ba  mov     [rbp+57h+arg_18], eax
0x1800070bd  lea     rax, [rbp+57h+var_60]
0x1800070c1  mov     [rsp+0D0h+var_70], rax
0x1800070c6  lea     rax, [rbp+57h+var_48]
0x1800070ca  mov     [rsp+0D0h+var_78], rax
0x1800070cf  lea     rax, [rbp+57h+var_5C]
0x1800070d3  mov     [rsp+0D0h+var_80], rax
0x1800070d8  lea     rax, [rbp+57h+var_58]
0x1800070dc  mov     [rsp+0D0h+var_88], rax
0x1800070e1  lea     rax, [rbp+57h+var_50]
0x1800070e5  mov     [rsp+0D0h+var_90], rax
0x1800070ea  lea     rax, [rbp+57h+arg_0]
0x1800070ee  mov     [rsp+0D0h+var_98], rax
0x1800070f3  lea     rax, [rbp+57h+arg_8]
0x1800070f7  mov     [rsp+0D0h+var_A0], rax
0x1800070fc  lea     rax, [rbp+57h+arg_10]
0x180007100  mov     [rsp+0D0h+var_A8], rax
0x180007105  lea     rax, [rbp+57h+arg_18]
0x180007109  mov     [rsp+0D0h+var_B0], rax
0x18000710e  lea     rdx, byte_180017C9B
0x180007115  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U1@U1@U1@U1@U1@U?$_tlgWrapSz@D@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@333333AEBU?$_tlgWrapSz@D@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18000711a  add     rsp, 98h
0x180007121  pop     r15
0x180007123  pop     r14
0x180007125  pop     r13
0x180007127  pop     r12
0x180007129  pop     rdi
0x18000712a  pop     rsi
0x18000712b  pop     rbx
0x18000712c  pop     rbp
0x18000712d  retn
```
