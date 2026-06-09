# GuestServiceUtilities::UpdateHvSocketServiceTable(void * const,Config::Devices::IC::HvSocketSystemWpConfig const &)

- ea: `0x1400b0698`
- end: `0x1400b09ee`
- name: `?UpdateHvSocketServiceTable@GuestServiceUtilities@@YAXQEAXAEBUHvSocketSystemWpConfig@IC@Devices@Config@@@Z`
- size: `854`
- prototype: `void __fastcall(HANDLE hDevice, void *const, const struct Config::Devices::IC::HvSocketSystemWpConfig *)`
- caller_count: `2`
- callee_count: `15`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x140170834`
- `0x140203d74`

## callees

- `0x14001bce0`
- `0x1400316cc`
- `0x140033a7c`
- `0x140080180`
- `0x1400a97c8`
- `0x1400b0660`
- `0x1400b0698`
- `0x1400b1dd0`
- `0x1400b20e4`
- `0x1400e4fc4`
- `0x1400f6494`
- `0x1401332f0`
- `0x14013624c`
- `0x1401365b9`
- `0x140246088`

## import_xrefs

- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1400b077a`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1400b07ef`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1400b077a`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1400b07ef`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1400b093a`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1400b093a`

## string_xrefs

- `0x1400b087f`: `onecore\vm\common\vdev\guestservice\guestserviceutilities.cpp`
- `0x1400b0894`: `onecore\vm\common\vdev\guestservice\guestserviceutilities.cpp`
- `0x1400b094a`: `onecore\vm\common\vdev\guestservice\guestserviceutilities.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall GuestServiceUtilities::UpdateHvSocketServiceTable(
        HANDLE hDevice,
        _QWORD *a2,
        const struct Config::Devices::IC::HvSocketSystemWpConfig *a3)
{
  __int128 v4; // xmm0
  __int64 v5; // rdx
  __int64 v6; // rbx
  char *v7; // r10
  __int128 v8; // xmm6
  const WCHAR *v9; // rcx
  const char *v10; // r9
  const WCHAR *v11; // rcx
  const char *v12; // r9
  __int64 v13; // rdi
  void *v14; // rax
  char *v15; // rbx
  const char *v16; // r9
  LPVOID *p_lpInBuffer; // [rsp+48h] [rbp-79h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+50h] [rbp-71h] BYREF
  char v19; // [rsp+58h] [rbp-69h]
  __int64 v20; // [rsp+60h] [rbp-61h] BYREF
  _BYTE v21[48]; // [rsp+68h] [rbp-59h] BYREF
  LPVOID lpInBuffer; // [rsp+98h] [rbp-29h] BYREF
  void *Src[2]; // [rsp+A0h] [rbp-21h] BYREF
  char *v24; // [rsp+B0h] [rbp-11h]
  DWORD BytesReturned; // [rsp+B8h] [rbp-9h] BYREF
  __int128 v26; // [rsp+C0h] [rbp-1h] BYREF
  __int64 v27; // [rsp+D0h] [rbp+Fh]
  wil::details::in1diag3 *retaddr; // [rsp+120h] [rbp+5Fh]

  if ( a2[9] )
  {
    v4 = 0;
    *(_OWORD *)Src = 0;
    v24 = 0;
    *(double *)&v4 = std::vector<Config::VirtualMachine::VpSubnodeMetadata>::vector<Config::VirtualMachine::VpSubnodeMetadata>(Src);
    v26 = v4;
    v27 = 0;
    std::vector<Config::VirtualMachine::VpSubnodeMetadata>::vector<Config::VirtualMachine::VpSubnodeMetadata>(&v26);
    v6 = **(_QWORD **)(v5 + 64);
    v20 = v6;
    v7 = (char *)Src[1];
    while ( !*(_BYTE *)(v6 + 25) )
    {
      memset(&v21[4], 0, 44);
      v8 = *(_OWORD *)(v6 + 32);
      *(_OWORD *)v21 = v8;
      v21[16] = *(_BYTE *)(v6 + 113) == 0;
      v21[40] = *(_BYTE *)(v6 + 112);
      if ( *(_QWORD *)(v6 + 64) )
      {
        lpInBuffer = 0;
        p_lpInBuffer = &lpInBuffer;
        SecurityDescriptor = 0;
        v19 = 1;
        v9 = (const WCHAR *)(v6 + 48);
        if ( *(_QWORD *)(v6 + 72) > 7u )
          v9 = *(const WCHAR **)v9;
        if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(v9, 1u, &SecurityDescriptor, 0) )
          wil::details::in1diag3::Throw_GetLastError(
            retaddr,
            (void *)0x133,
            (unsigned int)"onecore\\vm\\common\\vdev\\guestservice\\guestserviceutilities.cpp",
            v10);
        wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>(&p_lpInBuffer);
        *(_QWORD *)&v21[32] = lpInBuffer;
        std::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>::_Emplace_one_at_back<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>(
          &v26,
          &lpInBuffer);
        Vml::VmLocalPtr<_TOKEN_PRIMARY_GROUP>::~VmLocalPtr<_TOKEN_PRIMARY_GROUP>(&lpInBuffer);
        v7 = (char *)Src[1];
      }
      if ( *(_QWORD *)(v6 + 96) )
      {
        lpInBuffer = 0;
        p_lpInBuffer = &lpInBuffer;
        SecurityDescriptor = 0;
        v19 = 1;
        v11 = (const WCHAR *)(v6 + 80);
        if ( *(_QWORD *)(v6 + 104) > 7u )
          v11 = *(const WCHAR **)v11;
        if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(v11, 1u, &SecurityDescriptor, 0) )
          wil::details::in1diag3::Throw_GetLastError(
            retaddr,
            (void *)0x140,
            (unsigned int)"onecore\\vm\\common\\vdev\\guestservice\\guestserviceutilities.cpp",
            v12);
        wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>(&p_lpInBuffer);
        *(_QWORD *)&v21[24] = lpInBuffer;
        std::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>::_Emplace_one_at_back<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>(
          &v26,
          &lpInBuffer);
        Vml::VmLocalPtr<_TOKEN_PRIMARY_GROUP>::~VmLocalPtr<_TOKEN_PRIMARY_GROUP>(&lpInBuffer);
        v7 = (char *)Src[1];
      }
      if ( v7 == v24 )
      {
        std::vector<_HVSOCKET_SERVICE_INFO>::_Emplace_reallocate<_HVSOCKET_SERVICE_INFO const &>(Src, v7, v21);
      }
      else
      {
        *(_OWORD *)v7 = v8;
        *((_OWORD *)v7 + 1) = *(_OWORD *)&v21[16];
        *((_OWORD *)v7 + 2) = *(_OWORD *)&v21[32];
        Src[1] = (char *)Src[1] + 48;
      }
      std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,Schema::VirtualMachines::Resources::Vpci::VirtualPciDevice>>>,std::_Iterator_base0>::operator++(&v20);
      v6 = v20;
    }
    lpInBuffer = 0;
    v13 = 16 * (unsigned int)((v7 - (char *)Src[0]) >> 4);
    v14 = operator new[](v13 + 8);
    std::unique_ptr<unsigned char [0]>::reset<unsigned char *,0>(&lpInBuffer, v14);
    v15 = (char *)lpInBuffer;
    *(_DWORD *)lpInBuffer = v13;
    memcpy_0(v15 + 8, Src[0], 16 * (((char *)Src[1] - (char *)Src[0]) >> 4));
    BytesReturned = 0;
    if ( !DeviceIoControl(hDevice, 0x21C014u, v15, v13 + 8, 0, 0, &BytesReturned, 0) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x15B,
        (unsigned int)"onecore\\vm\\common\\vdev\\guestservice\\guestserviceutilities.cpp",
        v16);
    std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>(&lpInBuffer);
    if ( (_QWORD)v26 )
    {
      std::_Destroy_range<std::allocator<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>>(
        v26,
        *((_QWORD *)&v26 + 1));
      std::_Deallocate<16>(v26, (v27 - v26) & 0xFFFFFFFFFFFFFFF8uLL);
      v26 = 0;
      v27 = 0;
    }
    if ( Src[0] )
      std::_Deallocate<16>(Src[0], 16 * ((v24 - (char *)Src[0]) >> 4));
  }
}

```

## disassembly

```asm
0x1400b0698  mov     rax, rsp
0x1400b069b  mov     [rax+10h], rbx
0x1400b069f  mov     [rax+18h], rsi
0x1400b06a3  push    rbp
0x1400b06a4  push    rdi
0x1400b06a5  push    r12
0x1400b06a7  push    r14
0x1400b06a9  push    r15
0x1400b06ab  lea     rbp, [rax-5Fh]
0x1400b06af  sub     rsp, 0F0h
0x1400b06b6  movaps  xmmword ptr [rax-38h], xmm6
0x1400b06ba  mov     rax, cs:__security_cookie
0x1400b06c1  xor     rax, rsp
0x1400b06c4  mov     [rbp+57h+var_40], rax
0x1400b06c8  mov     r14, rcx
0x1400b06cb  xor     r15d, r15d
0x1400b06ce  cmp     [rdx+48h], r15
0x1400b06d2  jz      loc_1400B09C0
0x1400b06d8  xorps   xmm0, xmm0
0x1400b06db  xor     eax, eax
0x1400b06dd  movups  xmmword ptr [rbp+57h+Src], xmm0
0x1400b06e1  mov     [rbp+57h+var_68], rax
0x1400b06e5  lea     rcx, [rbp+57h+Src]
0x1400b06e9  call    ??0?$vector@UVpSubnodeMetadata@VirtualMachine@Config@@V?$allocator@UVpSubnodeMetadata@VirtualMachine@Config@@@std@@@std@@QEAA@XZ; std::vector<Config::VirtualMachine::VpSubnodeMetadata>::vector<Config::VirtualMachine::VpSubnodeMetadata>(void)
0x1400b06ee  nop
0x1400b06ef  xor     eax, eax
0x1400b06f1  movups  [rbp+57h+var_58], xmm0
0x1400b06f5  mov     [rbp+57h+var_48], rax
0x1400b06f9  lea     rcx, [rbp+57h+var_58]
0x1400b06fd  call    ??0?$vector@UVpSubnodeMetadata@VirtualMachine@Config@@V?$allocator@UVpSubnodeMetadata@VirtualMachine@Config@@@std@@@std@@QEAA@XZ; std::vector<Config::VirtualMachine::VpSubnodeMetadata>::vector<Config::VirtualMachine::VpSubnodeMetadata>(void)
0x1400b0702  nop
0x1400b0703  mov     rbx, [rdx+40h]
0x1400b0707  mov     rbx, [rbx]
0x1400b070a  mov     [rbp+57h+var_B8], rbx
0x1400b070e  lea     esi, [r15+1]
0x1400b0712  mov     r10, [rbp+57h+Src+8]
0x1400b0716  cmp     [rbx+19h], r15b
0x1400b071a  jnz     loc_1400B08A9
0x1400b0720  xorps   xmm0, xmm0
0x1400b0723  movups  [rbp+57h+var_B0+4], xmm0
0x1400b0727  movups  [rbp+57h+var_9C], xmm0
0x1400b072b  movups  [rbp+57h+var_9C+0Ch], xmm0
0x1400b072f  movups  xmm6, xmmword ptr [rbx+20h]
0x1400b0733  movups  [rbp+57h+var_B0], xmm6
0x1400b0737  cmp     [rbx+71h], r15b
0x1400b073b  setz    byte ptr [rbp-49h]
0x1400b073f  mov     al, [rbx+70h]
0x1400b0742  mov     [rbp+57h+var_88], al
0x1400b0745  cmp     [rbx+40h], r15
0x1400b0749  jz      short loc_1400B07BA
0x1400b074b  mov     [rbp+57h+lpInBuffer], r15
0x1400b074f  lea     rax, [rbp+57h+lpInBuffer]
0x1400b0753  mov     [rbp+57h+var_D0], rax
0x1400b0757  mov     [rbp+57h+SecurityDescriptor], r15
0x1400b075b  mov     [rbp+57h+var_C0], sil
0x1400b075f  lea     rcx, [rbx+30h]
0x1400b0763  cmp     qword ptr [rcx+18h], 7
0x1400b0768  jbe     short loc_1400B076D
0x1400b076a  mov     rcx, [rcx]; StringSecurityDescriptor
0x1400b076d  mov     rdi, [rbp+5Fh]
0x1400b0771  xor     r9d, r9d; SecurityDescriptorSize
0x1400b0774  lea     r8, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x1400b0778  mov     edx, esi; StringSDRevision
0x1400b077a  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x1400b0781  nop     dword ptr [rax+rax+00h]
0x1400b0786  test    eax, eax
0x1400b0788  jz      loc_1400B087F
0x1400b078e  lea     rcx, [rbp+57h+var_D0]
0x1400b0792  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>(void)
0x1400b0797  mov     rax, [rbp+57h+lpInBuffer]
0x1400b079b  mov     qword ptr [rbp+57h+var_9C+0Ch], rax
0x1400b079f  lea     rdx, [rbp+57h+lpInBuffer]
0x1400b07a3  lea     rcx, [rbp+57h+var_58]
0x1400b07a7  call    ??$_Emplace_one_at_back@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@?$vector@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@V?$allocator@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@@std@@AEAAAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@$$QEAV23@@Z; std::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>::_Emplace_one_at_back<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> &&)
0x1400b07ac  nop
0x1400b07ad  lea     rcx, [rbp+57h+lpInBuffer]
0x1400b07b1  call    ??1?$VmLocalPtr@U_TOKEN_PRIMARY_GROUP@@@Vml@@QEAA@XZ; Vml::VmLocalPtr<_TOKEN_PRIMARY_GROUP>::~VmLocalPtr<_TOKEN_PRIMARY_GROUP>(void)
0x1400b07b6  mov     r10, [rbp+57h+Src+8]
0x1400b07ba  cmp     [rbx+60h], r15
0x1400b07be  jz      short loc_1400B082F
0x1400b07c0  mov     [rbp+57h+lpInBuffer], r15
0x1400b07c4  lea     rax, [rbp+57h+lpInBuffer]
0x1400b07c8  mov     [rbp+57h+var_D0], rax
0x1400b07cc  mov     [rbp+57h+SecurityDescriptor], r15
0x1400b07d0  mov     [rbp+57h+var_C0], sil
0x1400b07d4  lea     rcx, [rbx+50h]
0x1400b07d8  cmp     qword ptr [rcx+18h], 7
0x1400b07dd  jbe     short loc_1400B07E2
0x1400b07df  mov     rcx, [rcx]; StringSecurityDescriptor
0x1400b07e2  mov     rbx, [rbp+5Fh]
0x1400b07e6  xor     r9d, r9d; SecurityDescriptorSize
0x1400b07e9  lea     r8, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x1400b07ed  mov     edx, esi; StringSDRevision
0x1400b07ef  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x1400b07f6  nop     dword ptr [rax+rax+00h]
0x1400b07fb  test    eax, eax
0x1400b07fd  jz      loc_1400B0894
0x1400b0803  lea     rcx, [rbp+57h+var_D0]
0x1400b0807  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>(void)
0x1400b080c  mov     rax, [rbp+57h+lpInBuffer]
0x1400b0810  mov     qword ptr [rbp+57h+var_9C+4], rax
0x1400b0814  lea     rdx, [rbp+57h+lpInBuffer]
0x1400b0818  lea     rcx, [rbp+57h+var_58]
0x1400b081c  call    ??$_Emplace_one_at_back@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@?$vector@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@V?$allocator@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@@std@@AEAAAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@$$QEAV23@@Z; std::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>::_Emplace_one_at_back<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> &&)
0x1400b0821  nop
0x1400b0822  lea     rcx, [rbp+57h+lpInBuffer]
0x1400b0826  call    ??1?$VmLocalPtr@U_TOKEN_PRIMARY_GROUP@@@Vml@@QEAA@XZ; Vml::VmLocalPtr<_TOKEN_PRIMARY_GROUP>::~VmLocalPtr<_TOKEN_PRIMARY_GROUP>(void)
0x1400b082b  mov     r10, [rbp+57h+Src+8]
0x1400b082f  cmp     r10, [rbp+57h+var_68]
0x1400b0833  jz      short loc_1400B0859
0x1400b0835  movups  xmmword ptr [r10], xmm6
0x1400b0839  movups  xmm0, xmmword ptr [rbp-49h]
0x1400b083d  movups  xmmword ptr [r10+10h], xmm0
0x1400b0842  movups  xmm1, [rbp+57h+var_9C+0Ch]
0x1400b0846  movups  xmmword ptr [r10+20h], xmm1
0x1400b084b  mov     r10, [rbp+57h+Src+8]
0x1400b084f  add     r10, 30h ; '0'
0x1400b0853  mov     [rbp+57h+Src+8], r10
0x1400b0857  jmp     short loc_1400B086D
0x1400b0859  lea     r8, [rbp+57h+var_B0]
0x1400b085d  mov     rdx, r10
0x1400b0860  lea     rcx, [rbp+57h+Src]
0x1400b0864  call    ??$_Emplace_reallocate@AEBU_HVSOCKET_SERVICE_INFO@@@?$vector@U_HVSOCKET_SERVICE_INFO@@V?$allocator@U_HVSOCKET_SERVICE_INFO@@@std@@@std@@AEAAPEAU_HVSOCKET_SERVICE_INFO@@QEAU2@AEBU2@@Z; std::vector<_HVSOCKET_SERVICE_INFO>::_Emplace_reallocate<_HVSOCKET_SERVICE_INFO const &>(_HVSOCKET_SERVICE_INFO * const,_HVSOCKET_SERVICE_INFO const &)
0x1400b0869  mov     r10, [rbp+57h+Src+8]
0x1400b086d  lea     rcx, [rbp+57h+var_B8]
0x1400b0871  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UVirtualPciDevice@Vpci@Resources@VirtualMachines@Schema@@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,Schema::VirtualMachines::Resources::Vpci::VirtualPciDevice>>>,std::_Iterator_base0>::operator++(void)
0x1400b0876  mov     rbx, [rbp+57h+var_B8]
0x1400b087a  jmp     loc_1400B0716
0x1400b087f  lea     r8, aOnecoreVmCommo_61; "onecore\\vm\\common\\vdev\\guestservice"...
0x1400b0886  mov     edx, 133h; void *
0x1400b088b  mov     rcx, rdi; this
0x1400b088e  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1400b0894  lea     r8, aOnecoreVmCommo_61; "onecore\\vm\\common\\vdev\\guestservice"...
0x1400b089b  mov     edx, 140h; void *
0x1400b08a0  mov     rcx, rbx; this
0x1400b08a3  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1400b08a9  mov     [rbp+57h+lpInBuffer], r15
0x1400b08ad  sub     r10, [rbp+57h+Src]
0x1400b08b1  sar     r10, 4
0x1400b08b5  mov     r12, 0AAAAAAAAAAAAAAABh
0x1400b08bf  imul    r10, r12
0x1400b08c3  lea     eax, [r10+r10*2]
0x1400b08c7  shl     eax, 4
0x1400b08ca  mov     edi, eax
0x1400b08cc  lea     rcx, [rax+8]; unsigned __int64
0x1400b08d0  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1400b08d5  mov     rdx, rax
0x1400b08d8  lea     rcx, [rbp+57h+lpInBuffer]
0x1400b08dc  call    ??$reset@PEAE$0A@@?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@std@@@std@@QEAAXPEAE@Z; std::unique_ptr<uchar [0]>::reset<uchar *,0>(uchar *)
0x1400b08e1  mov     rbx, [rbp+57h+lpInBuffer]
0x1400b08e5  mov     [rbx], edi
0x1400b08e7  mov     rax, [rbp+57h+Src+8]
0x1400b08eb  mov     rdx, [rbp+57h+Src]; Src
0x1400b08ef  sub     rax, rdx
0x1400b08f2  sar     rax, 4
0x1400b08f6  imul    rax, r12
0x1400b08fa  lea     r8, [rax+rax*2]
0x1400b08fe  shl     r8, 4; Size
0x1400b0902  lea     rcx, [rbx+8]; void *
0x1400b0906  call    memcpy_0
0x1400b090b  mov     [rbp+57h+BytesReturned], r15d
0x1400b090f  mov     rsi, [rbp+5Fh]
0x1400b0913  lea     r9d, [rdi+8]; nInBufferSize
0x1400b0917  mov     [rsp+110h+lpOverlapped], r15; lpOverlapped
0x1400b091c  lea     rax, [rbp+57h+BytesReturned]
0x1400b0920  mov     [rsp+110h+lpBytesReturned], rax; lpBytesReturned
0x1400b0925  mov     [rsp+110h+nOutBufferSize], r15d; nOutBufferSize
0x1400b092a  mov     [rsp+110h+lpOutBuffer], r15; lpOutBuffer
0x1400b092f  mov     r8, rbx; lpInBuffer
0x1400b0932  mov     edx, 21C014h; dwIoControlCode
0x1400b0937  mov     rcx, r14; hDevice
0x1400b093a  call    cs:__imp_DeviceIoControl
0x1400b0941  nop     dword ptr [rax+rax+00h]
0x1400b0946  test    eax, eax
0x1400b0948  jnz     short loc_1400B095F
0x1400b094a  lea     r8, aOnecoreVmCommo_61; "onecore\\vm\\common\\vdev\\guestservice"...
0x1400b0951  mov     edx, 15Bh; void *
0x1400b0956  mov     rcx, rsi; this
0x1400b0959  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1400b095f  lea     rcx, [rbp+57h+lpInBuffer]
0x1400b0963  call    ??1?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort [0]>::~unique_ptr<ushort [0]>(void)
0x1400b0968  nop
0x1400b0969  mov     rcx, qword ptr [rbp+57h+var_58]
0x1400b096d  test    rcx, rcx
0x1400b0970  jz      short loc_1400B099B
0x1400b0972  mov     rdx, qword ptr [rbp+57h+var_58+8]
0x1400b0976  call    ??$_Destroy_range@V?$allocator@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@@std@@YAXPEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@QEAV12@AEAV?$allocator@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@0@@Z; std::_Destroy_range<std::allocator<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> * const,std::allocator<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>> &)
0x1400b097b  mov     rcx, qword ptr [rbp+57h+var_58]
0x1400b097f  mov     rdx, [rbp+57h+var_48]
0x1400b0983  sub     rdx, rcx
0x1400b0986  and     rdx, 0FFFFFFFFFFFFFFF8h
0x1400b098a  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1400b098f  xorps   xmm0, xmm0
0x1400b0992  movdqu  [rbp+57h+var_58], xmm0
0x1400b0997  mov     [rbp+57h+var_48], r15
0x1400b099b  mov     rcx, [rbp+57h+Src]
0x1400b099f  test    rcx, rcx
0x1400b09a2  jz      short loc_1400B09C0
0x1400b09a4  mov     rax, [rbp+57h+var_68]
0x1400b09a8  sub     rax, rcx
0x1400b09ab  sar     rax, 4
0x1400b09af  imul    rax, r12
0x1400b09b3  lea     rdx, [rax+rax*2]
0x1400b09b7  shl     rdx, 4
0x1400b09bb  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1400b09c0  mov     rcx, [rbp+57h+var_40]
0x1400b09c4  xor     rcx, rsp; StackCookie
0x1400b09c7  call    __security_check_cookie
0x1400b09cc  lea     r11, [rsp+110h+var_20]
0x1400b09d4  mov     rbx, [r11+38h]
0x1400b09d8  mov     rsi, [r11+40h]
0x1400b09dc  movaps  xmm6, xmmword ptr [r11-10h]
0x1400b09e1  mov     rsp, r11
0x1400b09e4  pop     r15
0x1400b09e6  pop     r14
0x1400b09e8  pop     r12
0x1400b09ea  pop     rdi
0x1400b09eb  pop     rbp
0x1400b09ec  retn
```
