# GuestServiceUtilities::UpdateHvSocketServiceTable(void * const,Config::Devices::IC::HvSocketSystemWpConfig const &)

- ea: `0x1400ed49c`
- end: `0x1400ed83d`
- name: `?UpdateHvSocketServiceTable@GuestServiceUtilities@@YAXQEAXAEBUHvSocketSystemWpConfig@IC@Devices@Config@@@Z`
- size: `929`
- prototype: `void __fastcall(HANDLE hDevice, void *const, const struct Config::Devices::IC::HvSocketSystemWpConfig *)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x140087720`

## callees

- `0x140005360`
- `0x1400056c4`
- `0x140006080`
- `0x1400068e0`
- `0x14000ddac`
- `0x1400b1b04`
- `0x1400eced0`
- `0x1400ed0cc`
- `0x1400ed35c`
- `0x1400ed49c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400ed596`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400ed650`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400ed596`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400ed650`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400ed583`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400ed63d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400ed583`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400ed63d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400ed58e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400ed5d8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400ed648`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400ed692`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400ed58e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400ed5d8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400ed648`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400ed692`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1400ed7af`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1400ed7af`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1400ed55f`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1400ed619`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1400ed55f`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1400ed619`

## string_xrefs

- `0x1400ed7fe`: `onecore\vm\common\vdev\guestservice\guestserviceutilities.cpp`
- `0x1400ed813`: `onecore\vm\common\vdev\guestservice\guestserviceutilities.cpp`
- `0x1400ed828`: `onecore\vm\common\vdev\guestservice\guestserviceutilities.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall GuestServiceUtilities::UpdateHvSocketServiceTable(
        HANDLE hDevice,
        _QWORD **a2,
        const struct Config::Devices::IC::HvSocketSystemWpConfig *a3)
{
  __int64 *v4; // rbx
  __int128 v5; // xmm6
  const WCHAR *v6; // rcx
  const char *v7; // r9
  PSECURITY_DESCRIPTOR v8; // r15
  HLOCAL *v9; // rsi
  HLOCAL v10; // r14
  DWORD LastError; // edi
  HLOCAL v12; // rcx
  const WCHAR *v13; // rcx
  const char *v14; // r9
  PSECURITY_DESCRIPTOR v15; // r15
  HLOCAL *v16; // rsi
  HLOCAL v17; // r14
  DWORD v18; // edi
  HLOCAL v19; // rcx
  __int64 v20; // rax
  __int64 **v21; // rcx
  __int64 *i; // rax
  __int64 *j; // rcx
  __int64 v24; // rbx
  _DWORD *v25; // rdi
  unsigned __int64 v26; // rdx
  const char *v27; // r9
  _QWORD Src[3]; // [rsp+40h] [rbp-91h] BYREF
  __int64 v29; // [rsp+58h] [rbp-79h]
  HLOCAL *p_hMem; // [rsp+60h] [rbp-71h]
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+68h] [rbp-69h] BYREF
  char v32; // [rsp+70h] [rbp-61h]
  _BYTE v33[48]; // [rsp+78h] [rbp-59h] BYREF
  HLOCAL hMem; // [rsp+A8h] [rbp-29h] BYREF
  __int128 v35; // [rsp+B0h] [rbp-21h] BYREF
  __int64 v36; // [rsp+C0h] [rbp-11h]
  DWORD BytesReturned; // [rsp+C8h] [rbp-9h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+130h] [rbp+5Fh]

  if ( a2[9] )
  {
    *(_OWORD *)&Src[1] = 0;
    v29 = 0;
    v35 = 0;
    v36 = 0;
    v4 = (__int64 *)*a2[8];
    while ( !*((_BYTE *)v4 + 25) )
    {
      memset(&v33[4], 0, 44);
      v5 = *((_OWORD *)v4 + 2);
      *(_OWORD *)v33 = v5;
      v33[16] = *((_BYTE *)v4 + 113) == 0;
      v33[40] = *((_BYTE *)v4 + 112);
      if ( v4[8] )
      {
        hMem = 0;
        p_hMem = &hMem;
        SecurityDescriptor = 0;
        v32 = 1;
        v6 = (const WCHAR *)(v4 + 6);
        if ( (unsigned __int64)v4[9] > 7 )
          v6 = *(const WCHAR **)v6;
        if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(v6, 1u, &SecurityDescriptor, 0) )
          wil::details::in1diag3::Throw_GetLastError(
            retaddr,
            (void *)0x133,
            (unsigned int)"onecore\\vm\\common\\vdev\\guestservice\\guestserviceutilities.cpp",
            v7);
        if ( v32 )
        {
          v8 = SecurityDescriptor;
          v9 = p_hMem;
          v10 = *p_hMem;
          if ( *p_hMem )
          {
            LastError = GetLastError();
            LocalFree(v10);
            SetLastError(LastError);
          }
          *v9 = v8;
        }
        *(_QWORD *)&v33[32] = hMem;
        if ( *((_QWORD *)&v35 + 1) == v36 )
        {
          std::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>::_Emplace_reallocate<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>(
            &v35,
            *((_QWORD *)&v35 + 1),
            &hMem);
          v12 = hMem;
        }
        else
        {
          **((_QWORD **)&v35 + 1) = hMem;
          v12 = 0;
          hMem = 0;
          *((_QWORD *)&v35 + 1) += 8LL;
        }
        if ( v12 )
          LocalFree(v12);
      }
      if ( v4[12] )
      {
        hMem = 0;
        p_hMem = &hMem;
        SecurityDescriptor = 0;
        v32 = 1;
        v13 = (const WCHAR *)(v4 + 10);
        if ( (unsigned __int64)v4[13] > 7 )
          v13 = *(const WCHAR **)v13;
        if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(v13, 1u, &SecurityDescriptor, 0) )
          wil::details::in1diag3::Throw_GetLastError(
            retaddr,
            (void *)0x140,
            (unsigned int)"onecore\\vm\\common\\vdev\\guestservice\\guestserviceutilities.cpp",
            v14);
        if ( v32 )
        {
          v15 = SecurityDescriptor;
          v16 = p_hMem;
          v17 = *p_hMem;
          if ( *p_hMem )
          {
            v18 = GetLastError();
            LocalFree(v17);
            SetLastError(v18);
          }
          *v16 = v15;
        }
        *(_QWORD *)&v33[24] = hMem;
        if ( *((_QWORD *)&v35 + 1) == v36 )
        {
          std::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>::_Emplace_reallocate<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>(
            &v35,
            *((_QWORD *)&v35 + 1),
            &hMem);
          v19 = hMem;
        }
        else
        {
          **((_QWORD **)&v35 + 1) = hMem;
          v19 = 0;
          hMem = 0;
          *((_QWORD *)&v35 + 1) += 8LL;
        }
        if ( v19 )
          LocalFree(v19);
      }
      v20 = Src[2];
      if ( Src[2] == v29 )
      {
        std::vector<_HVSOCKET_SERVICE_INFO>::_Emplace_reallocate<_HVSOCKET_SERVICE_INFO const &>(
          &Src[1],
          (_BYTE *)Src[2],
          v33);
      }
      else
      {
        *(_OWORD *)Src[2] = v5;
        *(_OWORD *)(v20 + 16) = *(_OWORD *)&v33[16];
        *(_OWORD *)(v20 + 32) = *(_OWORD *)&v33[32];
        Src[2] += 48LL;
      }
      v21 = (__int64 **)v4[2];
      if ( *((_BYTE *)v21 + 25) )
      {
        for ( i = (__int64 *)v4[1]; !*((_BYTE *)i + 25) && v4 == (__int64 *)i[2]; i = (__int64 *)i[1] )
          v4 = i;
        v4 = i;
      }
      else
      {
        v4 = (__int64 *)v4[2];
        for ( j = *v21; !*((_BYTE *)j + 25); j = (__int64 *)*j )
          v4 = j;
      }
    }
    hMem = 0;
    v24 = 16 * (unsigned int)((__int64)(Src[2] - Src[1]) >> 4);
    v25 = operator new[](v24 + 8);
    hMem = v25;
    *v25 = v24;
    memcpy_0(v25 + 2, (const void *)Src[1], 16 * ((__int64)(Src[2] - Src[1]) >> 4));
    BytesReturned = 0;
    if ( !DeviceIoControl(hDevice, 0x21C014u, v25, v24 + 8, 0, 0, &BytesReturned, 0) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x15B,
        (unsigned int)"onecore\\vm\\common\\vdev\\guestservice\\guestserviceutilities.cpp",
        v27);
    operator delete(v25, v26);
    std::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>::~vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>(&v35);
    std::vector<ComputeService::Net::CFW_RULE>::~vector<ComputeService::Net::CFW_RULE>(&Src[1]);
  }
}

```

## disassembly

```asm
0x1400ed49c  mov     rax, rsp
0x1400ed49f  push    rbp
0x1400ed4a0  push    rbx
0x1400ed4a1  push    rsi
0x1400ed4a2  push    rdi
0x1400ed4a3  push    r12
0x1400ed4a5  push    r13
0x1400ed4a7  push    r14
0x1400ed4a9  push    r15
0x1400ed4ab  lea     rbp, [rax-5Fh]
0x1400ed4af  sub     rsp, 0E8h
0x1400ed4b6  movaps  xmmword ptr [rax-58h], xmm6
0x1400ed4ba  mov     rax, cs:__security_cookie
0x1400ed4c1  xor     rax, rsp
0x1400ed4c4  mov     qword ptr [rbp+57h+var_58], rax
0x1400ed4c8  mov     r12, rcx
0x1400ed4cb  xor     r13d, r13d
0x1400ed4ce  cmp     [rdx+48h], r13
0x1400ed4d2  jz      loc_1400ED7D6
0x1400ed4d8  xorps   xmm1, xmm1
0x1400ed4db  movdqu  xmmword ptr [rsp+120h+Src+8], xmm1
0x1400ed4e1  mov     [rbp+57h+var_D0], r13
0x1400ed4e5  movdqu  [rbp+57h+var_78], xmm1
0x1400ed4ea  mov     [rbp+57h+var_68], r13
0x1400ed4ee  mov     rbx, [rdx+40h]
0x1400ed4f2  mov     rbx, [rbx]
0x1400ed4f5  cmp     [rbx+19h], r13b
0x1400ed4f9  jnz     loc_1400ED720
0x1400ed4ff  xorps   xmm0, xmm0
0x1400ed502  movups  [rbp+57h+var_AC], xmm0
0x1400ed506  movups  [rbp+57h+var_9C], xmm0
0x1400ed50a  movups  [rbp+57h+var_9C+0Ch], xmm0
0x1400ed50e  movups  xmm6, xmmword ptr [rbx+20h]
0x1400ed512  movups  xmmword ptr [rbp-59h], xmm6
0x1400ed516  cmp     [rbx+71h], r13b
0x1400ed51a  setz    byte ptr [rbp+57h+var_AC+0Ch]
0x1400ed51e  mov     al, [rbx+70h]
0x1400ed521  mov     [rbp+57h+var_88], al
0x1400ed524  cmp     [rbx+40h], r13
0x1400ed528  jz      loc_1400ED5DE
0x1400ed52e  mov     [rbp+57h+hMem], r13
0x1400ed532  lea     rax, [rbp+57h+hMem]
0x1400ed536  mov     [rbp+57h+var_C8], rax
0x1400ed53a  mov     [rbp+57h+SecurityDescriptor], r13
0x1400ed53e  mov     [rbp+57h+var_B8], 1
0x1400ed542  lea     rcx, [rbx+30h]
0x1400ed546  cmp     qword ptr [rcx+18h], 7
0x1400ed54b  jbe     short loc_1400ED550
0x1400ed54d  mov     rcx, [rcx]; StringSecurityDescriptor
0x1400ed550  mov     rdi, [rbp+5Fh]
0x1400ed554  xor     r9d, r9d; SecurityDescriptorSize
0x1400ed557  lea     r8, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x1400ed55b  lea     edx, [r9+1]; StringSDRevision
0x1400ed55f  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x1400ed565  test    eax, eax
0x1400ed567  jz      loc_1400ED813
0x1400ed56d  cmp     [rbp+57h+var_B8], r13b
0x1400ed571  jz      short loc_1400ED59F
0x1400ed573  mov     r15, [rbp+57h+SecurityDescriptor]
0x1400ed577  mov     rsi, [rbp+57h+var_C8]
0x1400ed57b  mov     r14, [rsi]
0x1400ed57e  test    r14, r14
0x1400ed581  jz      short loc_1400ED59C
0x1400ed583  call    cs:__imp_GetLastError
0x1400ed589  mov     edi, eax
0x1400ed58b  mov     rcx, r14; hMem
0x1400ed58e  call    cs:__imp_LocalFree
0x1400ed594  mov     ecx, edi; dwErrCode
0x1400ed596  call    cs:__imp_SetLastError
0x1400ed59c  mov     [rsi], r15
0x1400ed59f  mov     rax, [rbp+57h+hMem]
0x1400ed5a3  mov     qword ptr [rbp+57h+var_9C+0Ch], rax
0x1400ed5a7  mov     rdx, qword ptr [rbp+57h+var_78+8]
0x1400ed5ab  cmp     rdx, [rbp+57h+var_68]
0x1400ed5af  jz      short loc_1400ED5C2
0x1400ed5b1  mov     [rdx], rax
0x1400ed5b4  mov     rcx, r13
0x1400ed5b7  mov     [rbp+57h+hMem], rcx
0x1400ed5bb  add     qword ptr [rbp+57h+var_78+8], 8
0x1400ed5c0  jmp     short loc_1400ED5D3
0x1400ed5c2  lea     r8, [rbp+57h+hMem]
0x1400ed5c6  lea     rcx, [rbp+57h+var_78]
0x1400ed5ca  call    ??$_Emplace_reallocate@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@?$vector@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@V?$allocator@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@@std@@AEAAPEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@QEAV23@$$QEAV23@@Z; std::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>::_Emplace_reallocate<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> * const,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> &&)
0x1400ed5cf  mov     rcx, [rbp+57h+hMem]; hMem
0x1400ed5d3  test    rcx, rcx
0x1400ed5d6  jz      short loc_1400ED5DE
0x1400ed5d8  call    cs:__imp_LocalFree
0x1400ed5de  cmp     [rbx+60h], r13
0x1400ed5e2  jz      loc_1400ED698
0x1400ed5e8  mov     [rbp+57h+hMem], r13
0x1400ed5ec  lea     rax, [rbp+57h+hMem]
0x1400ed5f0  mov     [rbp+57h+var_C8], rax
0x1400ed5f4  mov     [rbp+57h+SecurityDescriptor], r13
0x1400ed5f8  mov     [rbp+57h+var_B8], 1
0x1400ed5fc  lea     rcx, [rbx+50h]
0x1400ed600  cmp     qword ptr [rcx+18h], 7
0x1400ed605  jbe     short loc_1400ED60A
0x1400ed607  mov     rcx, [rcx]; StringSecurityDescriptor
0x1400ed60a  mov     rdi, [rbp+5Fh]
0x1400ed60e  xor     r9d, r9d; SecurityDescriptorSize
0x1400ed611  lea     r8, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x1400ed615  lea     edx, [r9+1]; StringSDRevision
0x1400ed619  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x1400ed61f  test    eax, eax
0x1400ed621  jz      loc_1400ED828
0x1400ed627  cmp     [rbp+57h+var_B8], r13b
0x1400ed62b  jz      short loc_1400ED659
0x1400ed62d  mov     r15, [rbp+57h+SecurityDescriptor]
0x1400ed631  mov     rsi, [rbp+57h+var_C8]
0x1400ed635  mov     r14, [rsi]
0x1400ed638  test    r14, r14
0x1400ed63b  jz      short loc_1400ED656
0x1400ed63d  call    cs:__imp_GetLastError
0x1400ed643  mov     edi, eax
0x1400ed645  mov     rcx, r14; hMem
0x1400ed648  call    cs:__imp_LocalFree
0x1400ed64e  mov     ecx, edi; dwErrCode
0x1400ed650  call    cs:__imp_SetLastError
0x1400ed656  mov     [rsi], r15
0x1400ed659  mov     rax, [rbp+57h+hMem]
0x1400ed65d  mov     qword ptr [rbp+57h+var_9C+4], rax
0x1400ed661  mov     rdx, qword ptr [rbp+57h+var_78+8]
0x1400ed665  cmp     rdx, [rbp+57h+var_68]
0x1400ed669  jz      short loc_1400ED67C
0x1400ed66b  mov     [rdx], rax
0x1400ed66e  mov     rcx, r13
0x1400ed671  mov     [rbp+57h+hMem], rcx
0x1400ed675  add     qword ptr [rbp+57h+var_78+8], 8
0x1400ed67a  jmp     short loc_1400ED68D
0x1400ed67c  lea     r8, [rbp+57h+hMem]
0x1400ed680  lea     rcx, [rbp+57h+var_78]
0x1400ed684  call    ??$_Emplace_reallocate@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@?$vector@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@V?$allocator@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@@std@@AEAAPEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@QEAV23@$$QEAV23@@Z; std::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>::_Emplace_reallocate<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> * const,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> &&)
0x1400ed689  mov     rcx, [rbp+57h+hMem]; hMem
0x1400ed68d  test    rcx, rcx
0x1400ed690  jz      short loc_1400ED698
0x1400ed692  call    cs:__imp_LocalFree
0x1400ed698  mov     rax, qword ptr [rsp+120h+Src+10h]
0x1400ed69d  cmp     rax, [rbp+57h+var_D0]
0x1400ed6a1  jz      short loc_1400ED6BE
0x1400ed6a3  movups  xmmword ptr [rax], xmm6
0x1400ed6a6  movups  xmm0, [rbp+57h+var_AC+0Ch]
0x1400ed6aa  movups  xmmword ptr [rax+10h], xmm0
0x1400ed6ae  movups  xmm1, [rbp+57h+var_9C+0Ch]
0x1400ed6b2  movups  xmmword ptr [rax+20h], xmm1
0x1400ed6b6  add     qword ptr [rsp+120h+Src+10h], 30h ; '0'
0x1400ed6bc  jmp     short loc_1400ED6D1
0x1400ed6be  lea     r8, [rbp+57h+var_B0]
0x1400ed6c2  mov     rdx, qword ptr [rsp+120h+Src+10h]
0x1400ed6c7  lea     rcx, [rsp+120h+Src+8]
0x1400ed6cc  call    ??$_Emplace_reallocate@AEBU_HVSOCKET_SERVICE_INFO@@@?$vector@U_HVSOCKET_SERVICE_INFO@@V?$allocator@U_HVSOCKET_SERVICE_INFO@@@std@@@std@@AEAAPEAU_HVSOCKET_SERVICE_INFO@@QEAU2@AEBU2@@Z; std::vector<_HVSOCKET_SERVICE_INFO>::_Emplace_reallocate<_HVSOCKET_SERVICE_INFO const &>(_HVSOCKET_SERVICE_INFO * const,_HVSOCKET_SERVICE_INFO const &)
0x1400ed6d1  mov     rcx, [rbx+10h]
0x1400ed6d5  cmp     [rcx+19h], r13b
0x1400ed6d9  jz      short loc_1400ED6FC
0x1400ed6db  mov     rax, [rbx+8]
0x1400ed6df  jmp     short loc_1400ED6EE
0x1400ed6e1  cmp     rbx, [rax+10h]
0x1400ed6e5  jnz     short loc_1400ED6F4
0x1400ed6e7  mov     rbx, rax
0x1400ed6ea  mov     rax, [rax+8]
0x1400ed6ee  cmp     [rax+19h], r13b
0x1400ed6f2  jz      short loc_1400ED6E1
0x1400ed6f4  mov     rbx, rax
0x1400ed6f7  jmp     loc_1400ED4F5
0x1400ed6fc  mov     rbx, rcx
0x1400ed6ff  mov     rcx, [rcx]
0x1400ed702  cmp     [rcx+19h], r13b
0x1400ed706  jnz     loc_1400ED4F5
0x1400ed70c  mov     rbx, rcx
0x1400ed70f  mov     rax, [rcx]
0x1400ed712  mov     rcx, rax
0x1400ed715  cmp     [rax+19h], r13b
0x1400ed719  jz      short loc_1400ED70C
0x1400ed71b  jmp     loc_1400ED4F5
0x1400ed720  mov     [rbp+57h+hMem], r13
0x1400ed724  mov     rax, qword ptr [rsp+120h+Src+10h]
0x1400ed729  sub     rax, qword ptr [rsp+120h+Src+8]
0x1400ed72e  sar     rax, 4
0x1400ed732  mov     rsi, 0AAAAAAAAAAAAAAABh
0x1400ed73c  imul    rax, rsi
0x1400ed740  lea     eax, [rax+rax*2]
0x1400ed743  shl     eax, 4
0x1400ed746  mov     ebx, eax
0x1400ed748  lea     rcx, [rax+8]; unsigned __int64
0x1400ed74c  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1400ed751  mov     rdi, rax
0x1400ed754  mov     [rbp+57h+hMem], rax
0x1400ed758  mov     [rax], ebx
0x1400ed75a  mov     rcx, qword ptr [rsp+120h+Src+10h]
0x1400ed75f  mov     rdx, qword ptr [rsp+120h+Src+8]; Src
0x1400ed764  sub     rcx, rdx
0x1400ed767  sar     rcx, 4
0x1400ed76b  imul    rcx, rsi
0x1400ed76f  lea     r8, [rcx+rcx*2]
0x1400ed773  shl     r8, 4; Size
0x1400ed777  lea     rcx, [rax+8]; void *
0x1400ed77b  call    memcpy_0
0x1400ed780  mov     [rbp+57h+BytesReturned], r13d
0x1400ed784  mov     rsi, [rbp+5Fh]
0x1400ed788  lea     r9d, [rbx+8]; nInBufferSize
0x1400ed78c  mov     qword ptr [rsp+120h+Src], r13; lpOverlapped
0x1400ed791  lea     rax, [rbp+57h+BytesReturned]
0x1400ed795  mov     [rsp+120h+lpBytesReturned], rax; lpBytesReturned
0x1400ed79a  mov     [rsp+120h+nOutBufferSize], r13d; nOutBufferSize
0x1400ed79f  mov     [rsp+120h+lpOutBuffer], r13; lpOutBuffer
0x1400ed7a4  mov     r8, rdi; lpInBuffer
0x1400ed7a7  mov     edx, 21C014h; dwIoControlCode
0x1400ed7ac  mov     rcx, r12; hDevice
0x1400ed7af  call    cs:__imp_DeviceIoControl
0x1400ed7b5  test    eax, eax
0x1400ed7b7  jz      short loc_1400ED7FE
0x1400ed7b9  mov     rcx, rdi; void *
0x1400ed7bc  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1400ed7c1  nop
0x1400ed7c2  lea     rcx, [rbp+57h+var_78]
0x1400ed7c6  call    ??1?$vector@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@V?$allocator@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@@std@@QEAA@XZ; std::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>::~vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>(void)
0x1400ed7cb  nop
0x1400ed7cc  lea     rcx, [rsp+120h+Src+8]
0x1400ed7d1  call    ??1?$vector@UCFW_RULE@Net@ComputeService@@V?$allocator@UCFW_RULE@Net@ComputeService@@@std@@@std@@QEAA@XZ; std::vector<ComputeService::Net::CFW_RULE>::~vector<ComputeService::Net::CFW_RULE>(void)
0x1400ed7d6  mov     rcx, qword ptr [rbp+57h+var_58]
0x1400ed7da  xor     rcx, rsp; StackCookie
0x1400ed7dd  call    __security_check_cookie
0x1400ed7e2  movaps  xmm6, [rsp+120h+var_58+8]
0x1400ed7ea  add     rsp, 0E8h
0x1400ed7f1  pop     r15
0x1400ed7f3  pop     r14
0x1400ed7f5  pop     r13
0x1400ed7f7  pop     r12
0x1400ed7f9  pop     rdi
0x1400ed7fa  pop     rsi
0x1400ed7fb  pop     rbx
0x1400ed7fc  pop     rbp
0x1400ed7fd  retn
0x1400ed7fe  lea     r8, aOnecoreVmCommo_13; "onecore\\vm\\common\\vdev\\guestservice"...
0x1400ed805  mov     edx, 15Bh; void *
0x1400ed80a  mov     rcx, rsi; this
0x1400ed80d  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1400ed813  lea     r8, aOnecoreVmCommo_13; "onecore\\vm\\common\\vdev\\guestservice"...
0x1400ed81a  mov     edx, 133h; void *
0x1400ed81f  mov     rcx, rdi; this
0x1400ed822  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1400ed828  lea     r8, aOnecoreVmCommo_13; "onecore\\vm\\common\\vdev\\guestservice"...
0x1400ed82f  mov     edx, 140h; void *
0x1400ed834  mov     rcx, rdi; this
0x1400ed837  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
