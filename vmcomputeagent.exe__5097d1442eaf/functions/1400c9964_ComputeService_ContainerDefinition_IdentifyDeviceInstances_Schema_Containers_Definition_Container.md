# ComputeService::ContainerDefinition::IdentifyDeviceInstances(Schema::Containers::Definition::Container &)

- ea: `0x1400c9964`
- end: `0x1400ca05a`
- name: `?IdentifyDeviceInstances@ContainerDefinition@ComputeService@@YAXAEAUContainer@Definition@Containers@Schema@@@Z`
- size: `1782`
- prototype: `void __fastcall(ComputeService::ContainerDefinition *__hidden this, struct Schema::Containers::Definition::Container *)`
- caller_count: `1`
- callee_count: `22`
- tags: `file_ops, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1400d051c`

## callees

- `0x140005360`
- `0x1400056c4`
- `0x1400056fc`
- `0x140006098`
- `0x1400068e0`
- `0x140008760`
- `0x14001bfa4`
- `0x14001f420`
- `0x14002c244`
- `0x14003a318`
- `0x14003dc74`
- `0x14003f1c4`
- `0x14005905c`
- `0x1400bf468`
- `0x1400c62c8`
- `0x1400c71d0`
- `0x1400c7a38`
- `0x1400c9964`
- `0x1400cc644`
- `0x1400db280`
- `0x1400db4a8`
- `0x1400db850`

## import_xrefs

- `api-ms-win-devices-config-l1-1-1!CM_Get_Device_Interface_List_SizeW` at `0x1400c9ed4`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Device_Interface_List_SizeW` at `0x1400c9ed4`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Device_ID_ListW` at `0x1400c9a67`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Device_ID_ListW` at `0x1400c9a67`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Device_ID_List_SizeW` at `0x1400c9a01`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Device_ID_List_SizeW` at `0x1400c9a01`
- `api-ms-win-devices-config-l1-1-1!CM_Get_DevNode_Registry_PropertyW` at `0x1400c9bcc`
- `api-ms-win-devices-config-l1-1-1!CM_Get_DevNode_Registry_PropertyW` at `0x1400c9bcc`
- `api-ms-win-devices-config-l1-1-1!CM_Locate_DevNodeW` at `0x1400c9b43`
- `api-ms-win-devices-config-l1-1-1!CM_Locate_DevNodeW` at `0x1400c9b43`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x1400c9a82`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x1400c9b54`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x1400c9bed`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x1400c9f34`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x1400c9a82`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x1400c9b54`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x1400c9bed`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x1400c9f34`
- `CFGMGR32!CM_Enumerate_Classes` at `0x1400c9ea9`
- `CFGMGR32!CM_Enumerate_Classes` at `0x1400c9f1e`
- `CFGMGR32!CM_Enumerate_Classes` at `0x1400c9ea9`
- `CFGMGR32!CM_Enumerate_Classes` at `0x1400c9f1e`

## string_xrefs

- `0x1400c9acb`: `onecore\vm\compute\management\shared\container\definitionfiledevice.cpp`
- `0x1400c9d5b`: `onecore\vm\compute\management\shared\container\definitionfiledevice.cpp`
- `0x1400c9e22`: `onecore\vm\compute\management\shared\container\definitionfiledevice.cpp`
- `0x1400c9e7c`: `onecore\vm\compute\management\shared\container\definitionfiledevice.cpp`
- `0x1400c9f5c`: `onecore\vm\compute\management\shared\container\definitionfiledevice.cpp`
- `0x1400c9e0c`: `Could not find the location path`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall ComputeService::ContainerDefinition::IdentifyDeviceInstances(
        ComputeService::ContainerDefinition *this,
        struct Schema::Containers::Definition::Container *a2)
{
  ComputeService::ContainerDefinition *v2; // r15
  _QWORD *v3; // rax
  unsigned int v4; // r14d
  void *v5; // rbx
  void *v6; // rsi
  unsigned __int64 v7; // rdx
  unsigned __int64 v8; // rdi
  unsigned __int64 v9; // rdx
  CONFIGRET Device_ID_ListW; // eax
  signed int v11; // eax
  DEVINSTID_W v12; // rsi
  DEVINSTID_W v13; // r12
  char *v14; // rbx
  char *v15; // rdi
  void *v16; // rbx
  WCHAR *v17; // rdx
  CONFIGRET v18; // eax
  signed int v19; // eax
  unsigned __int64 v20; // rdx
  unsigned int v21; // edi
  void *v22; // rax
  void *v23; // r14
  unsigned __int64 v24; // rcx
  unsigned __int64 v25; // rdi
  unsigned __int64 v26; // rdx
  CONFIGRET DevNode_Registry_PropertyW; // eax
  signed int v28; // eax
  char *v29; // rdi
  char *i; // rbx
  void **v31; // rax
  DEVINSTID_W v32; // rdx
  __int64 v33; // rdx
  __int64 v34; // rax
  __int64 v35; // r13
  __int64 v36; // r12
  __int64 v37; // rdi
  _OWORD *v38; // rbx
  __int64 v39; // rbx
  char v40; // al
  _QWORD *v41; // rax
  unsigned __int64 v42; // r8
  unsigned int PortNameFromDeviceID; // eax
  unsigned int v44; // ebx
  ULONG v45; // esi
  CONFIGRET j; // eax
  WCHAR *v47; // r8
  CONFIGRET Device_Interface_List_SizeW; // eax
  signed int v49; // eax
  _OWORD *v50; // r14
  __int64 v51; // rdx
  __int128 v52; // xmm0
  __int64 v53; // xmm1_8
  __int64 v54; // rdx
  int pulLength; // [rsp+20h] [rbp-99h]
  int pulLengthb; // [rsp+20h] [rbp-99h]
  int pulLengthc; // [rsp+20h] [rbp-99h]
  int pulLengtha; // [rsp+20h] [rbp-99h]
  const char *ulFlags; // [rsp+28h] [rbp-91h]
  const char *ulFlagsa; // [rsp+28h] [rbp-91h]
  const char *ulFlagsb; // [rsp+28h] [rbp-91h]
  __int128 v62; // [rsp+30h] [rbp-89h] BYREF
  __int64 v63; // [rsp+40h] [rbp-79h]
  void *v64; // [rsp+48h] [rbp-71h]
  ULONG pulLen; // [rsp+50h] [rbp-69h] BYREF
  ULONG pulRegDataType[2]; // [rsp+58h] [rbp-61h] BYREF
  _BYTE ClassGuid[24]; // [rsp+60h] [rbp-59h] BYREF
  DEVNODE pdnDevInst; // [rsp+78h] [rbp-41h] BYREF
  __int128 v69; // [rsp+80h] [rbp-39h] BYREF
  void *v70[2]; // [rsp+90h] [rbp-29h] BYREF
  __int64 v71; // [rsp+A0h] [rbp-19h]
  DEVINSTID_W pDeviceID[2]; // [rsp+A8h] [rbp-11h] BYREF
  __int64 v73; // [rsp+B8h] [rbp-1h]
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+5Fh]

  v2 = this;
  *(_QWORD *)ClassGuid = this;
  *(_OWORD *)pDeviceID = 0;
  v73 = 0;
  *(_OWORD *)v70 = 0;
  v71 = 0;
  v62 = 0;
  v63 = 0;
  v69 = 0u;
  v3 = operator new(0x60u);
  *v3 = v3;
  v3[1] = v3;
  v3[2] = v3;
  *((_WORD *)v3 + 12) = 257;
  *(_QWORD *)&v69 = v3;
  v4 = 0;
  v5 = 0;
  *(_QWORD *)pulRegDataType = 0;
  pulLen = 0;
  v6 = 0;
  while ( !CM_Get_Device_ID_List_SizeW(&pulLen, 0, 0x100u) && pulLen )
  {
    v8 = saturated_mul(pulLen, 2u);
    v5 = operator new[](v8);
    memset_0(v5, 0, v8);
    *(_QWORD *)pulRegDataType = v5;
    if ( v6 )
      operator delete(v6, v9);
    Device_ID_ListW = CM_Get_Device_ID_ListW(0, (PZZWSTR)v5, pulLen, 0x100u);
    if ( Device_ID_ListW != 26 )
    {
      if ( Device_ID_ListW )
      {
        v11 = CM_MapCrToWin32Err(Device_ID_ListW, 0xDu);
        v4 = v11;
        if ( v11 > 0 )
          v4 = (unsigned __int16)v11 | 0x80070000;
      }
      else
      {
        ComputeService::ContainerDevice::Details::CopyRegMultiSzToVector((int)v5);
      }
      v6 = v5;
      break;
    }
    v6 = v5;
  }
  if ( v6 )
    operator delete(v5, v7);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x52,
    (unsigned int)"onecore\\vm\\compute\\management\\shared\\container\\definitionfiledevice.cpp",
    (const char *)v4,
    (int)"Failed to get device IDs",
    ulFlags);
  v12 = pDeviceID[0];
  v13 = pDeviceID[1];
  if ( pDeviceID[0] != pDeviceID[1] )
  {
    do
    {
      v14 = (char *)v70[0];
      v15 = (char *)v70[1];
      if ( v70[0] != v70[1] )
      {
        do
        {
          std::wstring::~wstring(v14);
          v14 += 32;
        }
        while ( v14 != v15 );
        v70[1] = v70[0];
      }
      pdnDevInst = 0;
      pulRegDataType[0] = 0;
      v16 = 0;
      v64 = 0;
      pulLen = 200;
      if ( *((_QWORD *)v12 + 3) <= 7u )
        v17 = v12;
      else
        v17 = *(WCHAR **)v12;
      v18 = CM_Locate_DevNodeW(&pdnDevInst, v17, 0);
      if ( v18 )
      {
        v19 = CM_MapCrToWin32Err(v18, 0xDu);
        v21 = v19;
        if ( v19 > 0 )
          v21 = (unsigned __int16)v19 | 0x80070000;
        v22 = 0;
      }
      else
      {
        v23 = 0;
        v24 = pulLen;
        do
        {
          v25 = saturated_mul(v24, 2u);
          v16 = operator new[](v25);
          memset_0(v16, 0, v25);
          v64 = v16;
          if ( v23 )
            operator delete(v23, v26);
          DevNode_Registry_PropertyW = CM_Get_DevNode_Registry_PropertyW(
                                         pdnDevInst,
                                         0x24u,
                                         pulRegDataType,
                                         v16,
                                         &pulLen,
                                         0);
          v24 = 2 * pulLen;
          pulLen *= 2;
          v23 = v16;
        }
        while ( DevNode_Registry_PropertyW == 26 );
        if ( DevNode_Registry_PropertyW )
        {
          v28 = CM_MapCrToWin32Err(DevNode_Registry_PropertyW, 0xDu);
          v21 = v28;
          if ( v28 > 0 )
            v21 = (unsigned __int16)v28 | 0x80070000;
        }
        else if ( pulRegDataType[0] == 7 )
        {
          v21 = 0;
          ComputeService::ContainerDevice::Details::CopyRegMultiSzToVector((int)v16);
        }
        else
        {
          v21 = -2147024883;
        }
        v22 = v16;
      }
      if ( v22 )
        operator delete(v16, v20);
      if ( !v21 )
      {
        v29 = (char *)v70[1];
        for ( i = (char *)v70[0]; i != v29; i += 32 )
        {
          v31 = (void **)std::map<std::wstring,std::wstring>::operator[](&v69, i);
          if ( v31 != (void **)v12 )
          {
            v32 = v12;
            if ( *((_QWORD *)v12 + 3) > 7u )
              v32 = *(DEVINSTID_W *)v12;
            std::wstring::_Assign<unsigned short>(v31, v32, *((_QWORD *)v12 + 2));
          }
        }
      }
      v12 += 16;
    }
    while ( v12 != v13 );
    v2 = *(ComputeService::ContainerDefinition **)ClassGuid;
  }
  if ( !*((_BYTE *)v2 + 496) )
    __fastfail(5u);
  v33 = *((_QWORD *)v2 + 57);
  if ( v33 == *((_QWORD *)v2 + 58) )
  {
    std::vector<Schema::Containers::Definition::DeviceCategory>::_Emplace_reallocate<>((char *)v2 + 448);
  }
  else
  {
    *(_OWORD *)v33 = 0;
    *(_QWORD *)(v33 + 16) = 0;
    *(_QWORD *)(v33 + 24) = 7;
    *(_WORD *)v33 = 0;
    *(_QWORD *)(v33 + 32) = 0;
    *(_QWORD *)(v33 + 40) = 0;
    *(_QWORD *)(v33 + 48) = 0;
    *((_QWORD *)v2 + 57) += 56LL;
  }
  v34 = *((_QWORD *)v2 + 57);
  if ( !*((_BYTE *)v2 + 496) )
    __fastfail(5u);
  v35 = v34 - 56;
  std::wstring::_Assign<unsigned short>((void **)(v34 - 56), L"deviceInstances", 0xFu);
  if ( !*((_BYTE *)v2 + 496) )
    __fastfail(5u);
  v36 = *((_QWORD *)v2 + 60);
  v37 = *((_QWORD *)v2 + 59);
  if ( v37 != v36 )
  {
    v38 = (_OWORD *)v62;
    do
    {
      if ( v38 != *((_OWORD **)&v62 + 1) )
        *((_QWORD *)&v62 + 1) = v38;
      LOBYTE(pulLength) = *(_QWORD *)(v37 + 16) == 0;
      wil::details::in1diag3::Throw_HrIfFalseMsg(
        retaddr,
        (void *)0x86,
        (unsigned int)"onecore\\vm\\compute\\management\\shared\\container\\definitionfiledevice.cpp",
        (const char *)0x80070057LL,
        pulLength,
        (bool)"Device instance IDs must be empty",
        (const char *)v62);
      LOBYTE(pulLengthb) = *(_QWORD *)(v37 + 80) == 0;
      wil::details::in1diag3::Throw_HrIfFalseMsg(
        retaddr,
        (void *)0x89,
        (unsigned int)"onecore\\vm\\compute\\management\\shared\\container\\definitionfiledevice.cpp",
        (const char *)0x80070057LL,
        pulLengthb,
        (bool)"Device instance port names must be empty",
        (const char *)v62);
      LOBYTE(pulLengthc) = *(_QWORD *)(v37 + 96) == *(_QWORD *)(v37 + 104);
      wil::details::in1diag3::Throw_HrIfFalseMsg(
        retaddr,
        (void *)0x8C,
        (unsigned int)"onecore\\vm\\compute\\management\\shared\\container\\definitionfiledevice.cpp",
        (const char *)0x80070057LL,
        pulLengthc,
        (bool)"Device instance interface classes must be empty",
        (const char *)v62);
      std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Find_lower_bound<std::wstring>(
        &v69,
        ClassGuid,
        v37 + 32);
      v39 = *(_QWORD *)&ClassGuid[16];
      if ( *(_BYTE *)(*(_QWORD *)&ClassGuid[16] + 25LL)
        || (unsigned __int8)std::operator<<unsigned short>(v37 + 32, *(_QWORD *)&ClassGuid[16] + 32LL)
        || (v40 = 0, v39 == (_QWORD)v69) )
      {
        v40 = 1;
      }
      LOBYTE(pulLengtha) = v40;
      wil::details::in1diag3::Throw_HrIfMsg(
        retaddr,
        (void *)0x90,
        (unsigned int)"onecore\\vm\\compute\\management\\shared\\container\\definitionfiledevice.cpp",
        (const char *)0x8007000DLL,
        pulLengtha,
        (bool)"Could not find the location path",
        (const char *)v62);
      v41 = (_QWORD *)std::map<std::wstring,std::wstring>::operator[](&v69, v37 + 32);
      if ( (_QWORD *)v37 != v41 )
      {
        v42 = v41[2];
        if ( v41[3] > 7u )
          v41 = (_QWORD *)*v41;
        std::wstring::_Assign<unsigned short>((void **)v37, v41, v42);
      }
      PortNameFromDeviceID = ComputeService::ContainerDevice::GetPortNameFromDeviceID((DEVINSTID_W)v37);
      wil::details::in1diag3::Throw_IfFailedMsg(
        retaddr,
        (void *)0x97,
        (unsigned int)"onecore\\vm\\compute\\management\\shared\\container\\definitionfiledevice.cpp",
        (const char *)PortNameFromDeviceID,
        (int)"Failed to get port name from device instance ID",
        ulFlagsa);
      v44 = 0;
      *(_OWORD *)ClassGuid = 0;
      pulRegDataType[0] = 0;
      v45 = 1;
      for ( j = CM_Enumerate_Classes(0, (LPGUID)ClassGuid, 1u);
            j != 37;
            j = CM_Enumerate_Classes(v45++, (LPGUID)ClassGuid, 1u) )
      {
        if ( j != 31 )
        {
          if ( j )
          {
            v49 = CM_MapCrToWin32Err(j, 0xDu);
            v44 = v49;
            if ( v49 > 0 )
              v44 = (unsigned __int16)v49 | 0x80070000;
            break;
          }
          do
          {
            if ( *(_QWORD *)(v37 + 24) <= 7u )
              v47 = (WCHAR *)v37;
            else
              v47 = *(WCHAR **)v37;
            Device_Interface_List_SizeW = CM_Get_Device_Interface_List_SizeW(pulRegDataType, (LPGUID)ClassGuid, v47, 0);
          }
          while ( Device_Interface_List_SizeW == 26 );
          if ( !Device_Interface_List_SizeW && pulRegDataType[0] > 1 )
          {
            if ( *((_QWORD *)&v62 + 1) == v63 )
            {
              std::vector<_GUID>::_Emplace_reallocate<_GUID>(&v62, *((_QWORD *)&v62 + 1), ClassGuid);
            }
            else
            {
              **((_OWORD **)&v62 + 1) = *(_OWORD *)ClassGuid;
              *((_QWORD *)&v62 + 1) += 16LL;
            }
          }
        }
      }
      wil::details::in1diag3::Throw_IfFailedMsg(
        retaddr,
        (void *)0x9A,
        (unsigned int)"onecore\\vm\\compute\\management\\shared\\container\\definitionfiledevice.cpp",
        (const char *)v44,
        (int)"Failed to get interface class GUIDs from device instance ID",
        ulFlagsb);
      v50 = (_OWORD *)*((_QWORD *)&v62 + 1);
      v38 = (_OWORD *)v62;
      if ( (_QWORD)v62 != *((_QWORD *)&v62 + 1) )
      {
        do
        {
          ClassGuid[20] = 0;
          *(_OWORD *)&ClassGuid[4] = *v38;
          *(_DWORD *)ClassGuid = 1;
          v51 = *(_QWORD *)(v37 + 104);
          if ( v51 == *(_QWORD *)(v37 + 112) )
          {
            std::vector<Schema::Containers::Definition::InterfaceClass>::_Emplace_reallocate<Schema::Containers::Definition::InterfaceClass const &>(
              v37 + 96,
              v51,
              ClassGuid);
            v53 = *(_QWORD *)&ClassGuid[16];
            v52 = *(_OWORD *)ClassGuid;
          }
          else
          {
            v52 = *(_OWORD *)ClassGuid;
            *(_OWORD *)v51 = *(_OWORD *)ClassGuid;
            v53 = *(_QWORD *)&ClassGuid[16];
            *(_QWORD *)(v51 + 16) = *(_QWORD *)&ClassGuid[16];
            *(_QWORD *)(v37 + 104) += 24LL;
          }
          v54 = *(_QWORD *)(v35 + 40);
          if ( v54 == *(_QWORD *)(v35 + 48) )
          {
            std::vector<Schema::Containers::Definition::InterfaceClass>::_Emplace_reallocate<Schema::Containers::Definition::InterfaceClass const &>(
              v35 + 32,
              v54,
              ClassGuid);
          }
          else
          {
            *(_OWORD *)v54 = v52;
            *(_QWORD *)(v54 + 16) = v53;
            *(_QWORD *)(v35 + 40) += 24LL;
          }
          ++v38;
        }
        while ( v38 != v50 );
        v38 = (_OWORD *)v62;
      }
      v37 += 120;
    }
    while ( v37 != v36 );
  }
  std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::wstring>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *>>>(
    &v69,
    &v69);
  std::vector<_GUID>::~vector<_GUID>(&v62);
  std::vector<std::wstring>::_Tidy(v70);
  std::vector<std::wstring>::_Tidy(pDeviceID);
}

```

## disassembly

```asm
0x1400c9964  push    rbp
0x1400c9966  push    rbx
0x1400c9967  push    rsi
0x1400c9968  push    rdi
0x1400c9969  push    r12
0x1400c996b  push    r13
0x1400c996d  push    r14
0x1400c996f  push    r15
0x1400c9971  lea     rbp, [rsp-1Fh]
0x1400c9976  sub     rsp, 0D8h
0x1400c997d  mov     rax, cs:__security_cookie
0x1400c9984  xor     rax, rsp
0x1400c9987  mov     [rbp+57h+var_50], rax
0x1400c998b  mov     r15, rcx
0x1400c998e  mov     qword ptr [rbp+57h+ClassGuid.Data1], rcx
0x1400c9992  xor     r13d, r13d
0x1400c9995  xorps   xmm0, xmm0
0x1400c9998  xorps   xmm1, xmm1
0x1400c999b  movdqu  xmmword ptr [rbp+57h+pDeviceID], xmm1
0x1400c99a0  mov     [rbp+57h+var_58], r13
0x1400c99a4  movdqu  xmmword ptr [rbp+57h+var_80], xmm1
0x1400c99a9  mov     [rbp+57h+var_70], r13
0x1400c99ad  movdqu  [rsp+110h+var_E0], xmm1
0x1400c99b3  mov     [rbp+57h+var_D0], r13
0x1400c99b7  movups  [rbp+57h+var_90], xmm0
0x1400c99bb  mov     qword ptr [rbp+57h+var_90], r13
0x1400c99bf  mov     qword ptr [rbp+57h+var_90+8], r13
0x1400c99c3  lea     ecx, [r13+60h]; Size
0x1400c99c7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400c99cc  mov     [rax], rax
0x1400c99cf  mov     [rax+8], rax
0x1400c99d3  mov     [rax+10h], rax
0x1400c99d7  mov     word ptr [rax+18h], 101h
0x1400c99dd  mov     qword ptr [rbp+57h+var_90], rax
0x1400c99e1  mov     r14d, r13d
0x1400c99e4  mov     ebx, r13d
0x1400c99e7  mov     qword ptr [rbp+57h+pulRegDataType], rbx
0x1400c99eb  mov     [rbp+57h+pulLen], r13d
0x1400c99ef  mov     esi, r13d
0x1400c99f2  mov     r12d, 100h
0x1400c99f8  mov     r8d, r12d; ulFlags
0x1400c99fb  xor     edx, edx; pszFilter
0x1400c99fd  lea     rcx, [rbp+57h+pulLen]; pulLen
0x1400c9a01  call    cs:__imp_CM_Get_Device_ID_List_SizeW
0x1400c9a07  test    eax, eax
0x1400c9a09  jnz     loc_1400C9AAB
0x1400c9a0f  mov     eax, [rbp+57h+pulLen]
0x1400c9a12  test    eax, eax
0x1400c9a14  jz      loc_1400C9AAB
0x1400c9a1a  mov     ecx, eax
0x1400c9a1c  mov     eax, 2
0x1400c9a21  mul     rcx
0x1400c9a24  mov     rdi, rax
0x1400c9a27  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1400c9a2e  cmovb   rdi, rax
0x1400c9a32  mov     rcx, rdi; unsigned __int64
0x1400c9a35  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1400c9a3a  mov     rbx, rax
0x1400c9a3d  mov     r8, rdi; Size
0x1400c9a40  xor     edx, edx; Val
0x1400c9a42  mov     rcx, rax; void *
0x1400c9a45  call    memset_0
0x1400c9a4a  mov     qword ptr [rbp+57h+pulRegDataType], rbx
0x1400c9a4e  test    rsi, rsi
0x1400c9a51  jz      short loc_1400C9A5B
0x1400c9a53  mov     rcx, rsi; void *
0x1400c9a56  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1400c9a5b  mov     r9d, r12d; ulFlags
0x1400c9a5e  mov     r8d, [rbp+57h+pulLen]; BufferLen
0x1400c9a62  mov     rdx, rbx; Buffer
0x1400c9a65  xor     ecx, ecx; pszFilter
0x1400c9a67  call    cs:__imp_CM_Get_Device_ID_ListW
0x1400c9a6d  cmp     eax, 1Ah
0x1400c9a70  jnz     short loc_1400C9A77
0x1400c9a72  mov     rsi, rbx
0x1400c9a75  jmp     short loc_1400C99F8
0x1400c9a77  test    eax, eax
0x1400c9a79  jz      short loc_1400C9A9C
0x1400c9a7b  mov     edx, 0Dh; DefaultErr
0x1400c9a80  mov     ecx, eax; CmReturnCode
0x1400c9a82  call    cs:__imp_CM_MapCrToWin32Err
0x1400c9a88  mov     r14d, eax
0x1400c9a8b  test    eax, eax
0x1400c9a8d  jle     short loc_1400C9AA8
0x1400c9a8f  movzx   r14d, ax
0x1400c9a93  or      r14d, 80070000h
0x1400c9a9a  jmp     short loc_1400C9AA8
0x1400c9a9c  lea     rdx, [rbp+57h+pDeviceID]
0x1400c9aa0  mov     rcx, rbx; int
0x1400c9aa3  call    ?CopyRegMultiSzToVector@Details@ContainerDevice@ComputeService@@YAXPEBGAEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z; ComputeService::ContainerDevice::Details::CopyRegMultiSzToVector(ushort const *,std::vector<std::wstring> &)
0x1400c9aa8  mov     rsi, rbx
0x1400c9aab  test    rsi, rsi
0x1400c9aae  jz      short loc_1400C9AB8
0x1400c9ab0  mov     rcx, rbx; void *
0x1400c9ab3  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1400c9ab8  mov     rcx, [rbp+5Fh]; this
0x1400c9abc  lea     rax, aFailedToGetDev_1; "Failed to get device IDs"
0x1400c9ac3  mov     [rsp+110h+pulLength], rax; int
0x1400c9ac8  mov     r9d, r14d; char *
0x1400c9acb  lea     r8, aOnecoreVmCompu_11; "onecore\\vm\\compute\\management\\share"...
0x1400c9ad2  mov     edx, 52h ; 'R'; void *
0x1400c9ad7  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x1400c9adc  mov     rsi, [rbp+57h+pDeviceID]
0x1400c9ae0  mov     r12, [rbp+57h+pDeviceID+8]
0x1400c9ae4  cmp     rsi, r12
0x1400c9ae7  jz      loc_1400C9C82
0x1400c9aed  or      r15, 0FFFFFFFFFFFFFFFFh
0x1400c9af1  mov     rbx, [rbp+57h+var_80]
0x1400c9af5  mov     rdi, [rbp+57h+var_80+8]
0x1400c9af9  cmp     rbx, rdi
0x1400c9afc  jz      short loc_1400C9B17
0x1400c9afe  mov     rcx, rbx; void *
0x1400c9b01  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400c9b06  add     rbx, 20h ; ' '
0x1400c9b0a  cmp     rbx, rdi
0x1400c9b0d  jnz     short loc_1400C9AFE
0x1400c9b0f  mov     rax, [rbp+57h+var_80]
0x1400c9b13  mov     [rbp+57h+var_80+8], rax
0x1400c9b17  mov     [rbp+57h+pdnDevInst], r13d
0x1400c9b1b  mov     [rbp+57h+pulRegDataType], r13d
0x1400c9b1f  mov     rbx, r13
0x1400c9b22  mov     [rbp+57h+var_C8], rbx
0x1400c9b26  mov     [rbp+57h+pulLen], 0C8h
0x1400c9b2d  cmp     qword ptr [rsi+18h], 7
0x1400c9b32  jbe     short loc_1400C9B39
0x1400c9b34  mov     rdx, [rsi]
0x1400c9b37  jmp     short loc_1400C9B3C
0x1400c9b39  mov     rdx, rsi; pDeviceID
0x1400c9b3c  xor     r8d, r8d; ulFlags
0x1400c9b3f  lea     rcx, [rbp+57h+pdnDevInst]; pdnDevInst
0x1400c9b43  call    cs:__imp_CM_Locate_DevNodeW
0x1400c9b49  test    eax, eax
0x1400c9b4b  jz      short loc_1400C9B71
0x1400c9b4d  mov     edx, 0Dh; DefaultErr
0x1400c9b52  mov     ecx, eax; CmReturnCode
0x1400c9b54  call    cs:__imp_CM_MapCrToWin32Err
0x1400c9b5a  mov     edi, eax
0x1400c9b5c  test    eax, eax
0x1400c9b5e  jle     short loc_1400C9B69
0x1400c9b60  movzx   edi, ax
0x1400c9b63  or      edi, 80070000h
0x1400c9b69  mov     rax, r13
0x1400c9b6c  jmp     loc_1400C9C23
0x1400c9b71  mov     r14, r13
0x1400c9b74  mov     ecx, [rbp+57h+pulLen]
0x1400c9b77  mov     eax, 2
0x1400c9b7c  mul     rcx
0x1400c9b7f  mov     rdi, rax
0x1400c9b82  cmovb   rdi, r15
0x1400c9b86  mov     rcx, rdi; unsigned __int64
0x1400c9b89  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1400c9b8e  mov     rbx, rax
0x1400c9b91  mov     r8, rdi; Size
0x1400c9b94  xor     edx, edx; Val
0x1400c9b96  mov     rcx, rax; void *
0x1400c9b99  call    memset_0
0x1400c9b9e  mov     [rbp+57h+var_C8], rbx
0x1400c9ba2  test    r14, r14
0x1400c9ba5  jz      short loc_1400C9BAF
0x1400c9ba7  mov     rcx, r14; void *
0x1400c9baa  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1400c9baf  mov     [rsp+110h+ulFlags], r13d; ulFlags
0x1400c9bb4  lea     rax, [rbp+57h+pulLen]
0x1400c9bb8  mov     [rsp+110h+pulLength], rax; pulLength
0x1400c9bbd  mov     r9, rbx; Buffer
0x1400c9bc0  lea     r8, [rbp+57h+pulRegDataType]; pulRegDataType
0x1400c9bc4  mov     edx, 24h ; '$'; ulProperty
0x1400c9bc9  mov     ecx, [rbp+57h+pdnDevInst]; dnDevInst
0x1400c9bcc  call    cs:__imp_CM_Get_DevNode_Registry_PropertyW
0x1400c9bd2  mov     ecx, [rbp+57h+pulLen]
0x1400c9bd5  add     ecx, ecx
0x1400c9bd7  mov     [rbp+57h+pulLen], ecx
0x1400c9bda  mov     r14, rbx
0x1400c9bdd  cmp     eax, 1Ah
0x1400c9be0  jz      short loc_1400C9B77
0x1400c9be2  test    eax, eax
0x1400c9be4  jz      short loc_1400C9C04
0x1400c9be6  mov     edx, 0Dh; DefaultErr
0x1400c9beb  mov     ecx, eax; CmReturnCode
0x1400c9bed  call    cs:__imp_CM_MapCrToWin32Err
0x1400c9bf3  mov     edi, eax
0x1400c9bf5  test    eax, eax
0x1400c9bf7  jle     short loc_1400C9C20
0x1400c9bf9  movzx   edi, ax
0x1400c9bfc  or      edi, 80070000h
0x1400c9c02  jmp     short loc_1400C9C20
0x1400c9c04  cmp     [rbp+57h+pulRegDataType], 7
0x1400c9c08  jz      short loc_1400C9C11
0x1400c9c0a  mov     edi, 8007000Dh
0x1400c9c0f  jmp     short loc_1400C9C20
0x1400c9c11  mov     edi, r13d
0x1400c9c14  lea     rdx, [rbp+57h+var_80]
0x1400c9c18  mov     rcx, rbx; int
0x1400c9c1b  call    ?CopyRegMultiSzToVector@Details@ContainerDevice@ComputeService@@YAXPEBGAEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z; ComputeService::ContainerDevice::Details::CopyRegMultiSzToVector(ushort const *,std::vector<std::wstring> &)
0x1400c9c20  mov     rax, rbx
0x1400c9c23  test    rax, rax
0x1400c9c26  jz      short loc_1400C9C30
0x1400c9c28  mov     rcx, rbx; void *
0x1400c9c2b  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1400c9c30  test    edi, edi
0x1400c9c32  jnz     short loc_1400C9C71
0x1400c9c34  mov     rdi, [rbp+57h+var_80+8]
0x1400c9c38  mov     rbx, [rbp+57h+var_80]
0x1400c9c3c  jmp     short loc_1400C9C6C
0x1400c9c3e  mov     rdx, rbx
0x1400c9c41  lea     rcx, [rbp+57h+var_90]
0x1400c9c45  call    ??A?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@QEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@AEBV21@@Z; std::map<std::wstring,std::wstring>::operator[](std::wstring const &)
0x1400c9c4a  cmp     rax, rsi
0x1400c9c4d  jz      short loc_1400C9C68
0x1400c9c4f  mov     rdx, rsi
0x1400c9c52  cmp     qword ptr [rsi+18h], 7
0x1400c9c57  jbe     short loc_1400C9C5C
0x1400c9c59  mov     rdx, [rsi]
0x1400c9c5c  mov     r8, [rsi+10h]
0x1400c9c60  mov     rcx, rax
0x1400c9c63  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x1400c9c68  add     rbx, 20h ; ' '
0x1400c9c6c  cmp     rbx, rdi
0x1400c9c6f  jnz     short loc_1400C9C3E
0x1400c9c71  add     rsi, 20h ; ' '
0x1400c9c75  cmp     rsi, r12
0x1400c9c78  jnz     loc_1400C9AF1
0x1400c9c7e  mov     r15, qword ptr [rbp+57h+ClassGuid.Data1]
0x1400c9c82  mov     edi, 5
0x1400c9c87  cmp     [r15+1F0h], r13b
0x1400c9c8e  jnz     short loc_1400C9C94
0x1400c9c90  mov     ecx, edi
0x1400c9c92  int     29h; Win8: RtlFailFast(ecx)
0x1400c9c94  lea     rbx, [r15+1C0h]
0x1400c9c9b  mov     rdx, [rbx+8]
0x1400c9c9f  cmp     rdx, [rbx+10h]
0x1400c9ca3  jz      short loc_1400C9CCE
0x1400c9ca5  xorps   xmm0, xmm0
0x1400c9ca8  movups  xmmword ptr [rdx], xmm0
0x1400c9cab  mov     [rdx+10h], r13
0x1400c9caf  mov     qword ptr [rdx+18h], 7
0x1400c9cb7  mov     [rdx], r13w
0x1400c9cbb  mov     [rdx+20h], r13
0x1400c9cbf  mov     [rdx+28h], r13
0x1400c9cc3  mov     [rdx+30h], r13
0x1400c9cc7  add     qword ptr [rbx+8], 38h ; '8'
0x1400c9ccc  jmp     short loc_1400C9CD6
0x1400c9cce  mov     rcx, rbx
0x1400c9cd1  call    ??$_Emplace_reallocate@$$V@?$vector@UDeviceCategory@Definition@Containers@Schema@@V?$allocator@UDeviceCategory@Definition@Containers@Schema@@@std@@@std@@AEAAPEAUDeviceCategory@Definition@Containers@Schema@@QEAU2345@@Z; std::vector<Schema::Containers::Definition::DeviceCategory>::_Emplace_reallocate<>(Schema::Containers::Definition::DeviceCategory * const)
0x1400c9cd6  mov     rax, [rbx+8]
0x1400c9cda  cmp     [r15+1F0h], r13b
0x1400c9ce1  jnz     short loc_1400C9CE8
0x1400c9ce3  mov     rcx, rdi
0x1400c9ce6  int     29h; Win8: RtlFailFast(ecx)
0x1400c9ce8  lea     r13, [rax-38h]
0x1400c9cec  mov     r8d, 0Fh
0x1400c9cf2  lea     rdx, aDeviceinstance_0; "deviceInstances"
0x1400c9cf9  mov     rcx, r13
0x1400c9cfc  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x1400c9d01  xor     r14d, r14d
0x1400c9d04  cmp     [r15+1F0h], r14b
0x1400c9d0b  jnz     short loc_1400C9D12
0x1400c9d0d  mov     rcx, rdi
0x1400c9d10  int     29h; Win8: RtlFailFast(ecx)
0x1400c9d12  mov     r12, [r15+1E0h]
0x1400c9d19  mov     rdi, [r15+1D8h]
0x1400c9d20  cmp     rdi, r12
0x1400c9d23  jz      loc_1400CA00E
0x1400c9d29  mov     rbx, qword ptr [rsp+110h+var_E0]
0x1400c9d2e  cmp     rbx, qword ptr [rsp+110h+var_E0+8]
0x1400c9d33  jz      short loc_1400C9D3A
0x1400c9d35  mov     qword ptr [rsp+110h+var_E0+8], rbx
0x1400c9d3a  cmp     [rdi+10h], r14
0x1400c9d3e  setz    al
0x1400c9d41  mov     rcx, [rbp+5Fh]; this
0x1400c9d45  lea     rdx, aDeviceInstance_1; "Device instance IDs must be empty"
0x1400c9d4c  mov     qword ptr [rsp+110h+ulFlags], rdx; bool
0x1400c9d51  mov     byte ptr [rsp+110h+pulLength], al; int
0x1400c9d55  mov     r9d, 80070057h; char *
0x1400c9d5b  lea     rbx, aOnecoreVmCompu_11; "onecore\\vm\\compute\\management\\share"...
0x1400c9d62  mov     r8, rbx; unsigned int
0x1400c9d65  mov     edx, 86h; void *
0x1400c9d6a  call    ?Throw_HrIfFalseMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfFalseMsg(void *,uint,char const *,long,bool,char const *,...)
0x1400c9d6f  cmp     [rdi+50h], r14
0x1400c9d73  setz    al
0x1400c9d76  mov     rcx, [rbp+5Fh]; this
0x1400c9d7a  lea     rdx, aDeviceInstance_2; "Device instance port names must be empt"...
0x1400c9d81  mov     qword ptr [rsp+110h+ulFlags], rdx; bool
0x1400c9d86  mov     byte ptr [rsp+110h+pulLength], al; int
0x1400c9d8a  mov     r9d, 80070057h; char *
0x1400c9d90  mov     r8, rbx; unsigned int
0x1400c9d93  mov     edx, 89h; void *
0x1400c9d98  call    ?Throw_HrIfFalseMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfFalseMsg(void *,uint,char const *,long,bool,char const *,...)
0x1400c9d9d  mov     rax, [rdi+68h]
0x1400c9da1  cmp     [rdi+60h], rax
0x1400c9da5  setz    al
0x1400c9da8  mov     rcx, [rbp+5Fh]; this
0x1400c9dac  lea     rdx, aDeviceInstance_0; "Device instance interface classes must "...
0x1400c9db3  mov     qword ptr [rsp+110h+ulFlags], rdx; bool
0x1400c9db8  mov     byte ptr [rsp+110h+pulLength], al; int
0x1400c9dbc  mov     r9d, 80070057h; char *
0x1400c9dc2  mov     r8, rbx; unsigned int
0x1400c9dc5  mov     edx, 8Ch; void *
0x1400c9dca  call    ?Throw_HrIfFalseMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfFalseMsg(void *,uint,char const *,long,bool,char const *,...)
0x1400c9dcf  lea     rsi, [rdi+20h]
  ... truncated ...
```
