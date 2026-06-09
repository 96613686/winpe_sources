# IsCallerSettingsBroker(void)

- ea: `0x1800aa63c`
- end: `0x1800aa918`
- name: `?IsCallerSettingsBroker@@YAHXZ`
- size: `732`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180074940`
- `0x18007e060`

## callees

- `0x1800137a0`
- `0x180019434`
- `0x180037cd0`
- `0x18003a540`
- `0x18006900c`
- `0x18007ff00`
- `0x180084f50`
- `0x180085bc4`
- `0x1800a9cf8`
- `0x1800aa264`
- `0x1800aa63c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800aa753`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800aa7db`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800aa753`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800aa7db`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800aa848`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800aa848`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x1800aa673`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x1800aa673`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800aa70d`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800aa70d`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x1800aa7a6`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x1800aa7a6`
- `RPCRT4!RpcRevertToSelf` at `0x1800aa8d3`
- `RPCRT4!RpcRevertToSelf` at `0x1800aa8f5`
- `RPCRT4!RpcRevertToSelf` at `0x1800aa8d3`
- `RPCRT4!RpcRevertToSelf` at `0x1800aa8f5`
- `RPCRT4!RpcImpersonateClient` at `0x1800aa6f9`
- `RPCRT4!RpcImpersonateClient` at `0x1800aa6f9`

## pseudocode

```c
__int64 IsCallerSettingsBroker(void)
{
  unsigned int RpcClientProcessId; // eax
  RPC_STATUS v1; // edi
  HANDLE v2; // rbx
  DWORD LastError; // eax
  __int64 v4; // rdx
  __int64 v5; // rcx
  __int64 v6; // rcx
  __int64 v7; // rdx
  DWORD dwProcessId[2]; // [rsp+30h] [rbp-D0h] BYREF
  HANDLE v10; // [rsp+38h] [rbp-C8h] BYREF
  int v11; // [rsp+40h] [rbp-C0h] BYREF
  DWORD dwSize[3]; // [rsp+44h] [rbp-BCh] BYREF
  WCHAR ExeName[264]; // [rsp+50h] [rbp-B0h] BYREF

  v11 = 0;
  RtlGetDeviceFamilyInfoEnum(0, &v11, 0);
  if ( v11 != 10
    || !(unsigned int)CheckServicePrivilege(L"S-1-5-80-992094038-249327908-3517859850-571231379-4184271305") )
  {
    dwProcessId[0] = 0;
    RpcClientProcessId = GetRpcClientProcessId(dwProcessId);
    if ( RpcClientProcessId )
    {
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *(_BYTE *)(WPP_GLOBAL_Control + 25LL)
        && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      {
        WPP_SF_d(
          *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
          94,
          WPP_59cb1c30c417333f98d499625c161da5_Traceguids,
          RpcClientProcessId);
      }
      return 0;
    }
    v1 = RpcImpersonateClient(0);
    v2 = OpenProcess(0x1000u, 0, dwProcessId[0]);
    v10 = v2;
    if ( (((unsigned __int64)v2 + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
    {
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *(_BYTE *)(WPP_GLOBAL_Control + 25LL)
        && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      {
        LastError = GetLastError();
        v4 = 95;
LABEL_13:
        WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), v4, WPP_59cb1c30c417333f98d499625c161da5_Traceguids, LastError);
        goto LABEL_36;
      }
      goto LABEL_36;
    }
    memset_0(ExeName, 0, 0x208u);
    dwSize[0] = 260;
    if ( !QueryFullProcessImageNameW(v2, 0, ExeName, dwSize) )
    {
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *(_BYTE *)(WPP_GLOBAL_Control + 25LL)
        && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      {
        LastError = GetLastError();
        v4 = 96;
        goto LABEL_13;
      }
LABEL_36:
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v10);
      if ( !v1 )
        RpcRevertToSelf();
      return 0;
    }
    *(_QWORD *)dwProcessId = 0;
    if ( (int)wil::ExpandEnvironmentStringsW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,256>(
                v5,
                (__int64)dwProcessId) < 0 )
    {
      v6 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || !*(_BYTE *)(WPP_GLOBAL_Control + 25LL)
        || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
      {
        goto LABEL_35;
      }
      v7 = 97;
LABEL_34:
      WPP_SF_(*(_QWORD *)(v6 + 16), v7, WPP_59cb1c30c417333f98d499625c161da5_Traceguids);
LABEL_35:
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(dwProcessId);
      goto LABEL_36;
    }
    if ( CompareStringOrdinal(*(LPCWCH *)dwProcessId, -1, ExeName, -1, 1) != 2 )
    {
      v6 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || !*(_BYTE *)(WPP_GLOBAL_Control + 25LL)
        || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
      {
        goto LABEL_35;
      }
      v7 = 98;
      goto LABEL_34;
    }
    if ( (int)ValidateFileSignedByMicrosoft(ExeName) < 0 )
    {
      v6 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || !*(_BYTE *)(WPP_GLOBAL_Control + 25LL)
        || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
      {
        goto LABEL_35;
      }
      v7 = 99;
      goto LABEL_34;
    }
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(dwProcessId);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v10);
    if ( !v1 )
      RpcRevertToSelf();
  }
  return 1;
}

```

## disassembly

```asm
0x1800aa63c  push    rbp
0x1800aa63e  push    rbx
0x1800aa63f  push    rsi
0x1800aa640  push    rdi
0x1800aa641  lea     rbp, [rsp-178h]
0x1800aa649  sub     rsp, 278h
0x1800aa650  mov     rax, cs:__security_cookie
0x1800aa657  xor     rax, rsp
0x1800aa65a  mov     [rbp+190h+var_30], rax
0x1800aa661  xor     r8d, r8d
0x1800aa664  mov     [rsp+290h+var_250], 0
0x1800aa66c  lea     rdx, [rsp+290h+var_250]
0x1800aa671  xor     ecx, ecx
0x1800aa673  call    cs:__imp_RtlGetDeviceFamilyInfoEnum
0x1800aa679  cmp     [rsp+290h+var_250], 0Ah
0x1800aa67e  mov     esi, 1
0x1800aa683  jnz     short loc_1800AA699
0x1800aa685  lea     rcx, aS1580992094038; "S-1-5-80-992094038-249327908-3517859850"...
0x1800aa68c  call    ?CheckServicePrivilege@@YAHPEBG@Z; CheckServicePrivilege(ushort const *)
0x1800aa691  test    eax, eax
0x1800aa693  jnz     loc_1800AA8FB
0x1800aa699  lea     rcx, [rsp+290h+dwProcessId]; unsigned int *
0x1800aa69e  mov     [rsp+290h+dwProcessId], 0
0x1800aa6a6  call    ?GetRpcClientProcessId@@YAKPEAK@Z; GetRpcClientProcessId(ulong *)
0x1800aa6ab  test    eax, eax
0x1800aa6ad  jz      short loc_1800AA6F7
0x1800aa6af  mov     rcx, cs:WPP_GLOBAL_Control
0x1800aa6b6  lea     rdx, WPP_GLOBAL_Control
0x1800aa6bd  cmp     rcx, rdx
0x1800aa6c0  jz      loc_1800AA8D9
0x1800aa6c6  cmp     [rcx+19h], sil
0x1800aa6ca  jb      loc_1800AA8D9
0x1800aa6d0  test    [rcx+1Ch], sil
0x1800aa6d4  jz      loc_1800AA8D9
0x1800aa6da  mov     rcx, [rcx+10h]
0x1800aa6de  lea     r8, WPP_59cb1c30c417333f98d499625c161da5_Traceguids
0x1800aa6e5  mov     edx, 5Eh ; '^'
0x1800aa6ea  mov     r9d, eax
0x1800aa6ed  call    WPP_SF_d
0x1800aa6f2  jmp     loc_1800AA8D9
0x1800aa6f7  xor     ecx, ecx; BindingHandle
0x1800aa6f9  call    cs:__imp_RpcImpersonateClient
0x1800aa6ff  mov     r8d, [rsp+290h+dwProcessId]; dwProcessId
0x1800aa704  xor     edx, edx; bInheritHandle
0x1800aa706  mov     ecx, 1000h; dwDesiredAccess
0x1800aa70b  mov     edi, eax
0x1800aa70d  call    cs:__imp_OpenProcess
0x1800aa713  mov     rbx, rax
0x1800aa716  mov     [rsp+290h+var_258], rax
0x1800aa71b  lea     rcx, [rax+1]
0x1800aa71f  test    rcx, 0FFFFFFFFFFFFFFFEh
0x1800aa726  jnz     short loc_1800AA77D
0x1800aa728  mov     rax, cs:WPP_GLOBAL_Control
0x1800aa72f  lea     rdx, WPP_GLOBAL_Control
0x1800aa736  cmp     rax, rdx
0x1800aa739  jz      loc_1800AA8C5
0x1800aa73f  cmp     [rax+19h], sil
0x1800aa743  jb      loc_1800AA8C5
0x1800aa749  test    [rax+1Ch], sil
0x1800aa74d  jz      loc_1800AA8C5
0x1800aa753  call    cs:__imp_GetLastError
0x1800aa759  mov     edx, 5Fh ; '_'
0x1800aa75e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800aa765  lea     r8, WPP_59cb1c30c417333f98d499625c161da5_Traceguids
0x1800aa76c  mov     r9d, eax
0x1800aa76f  mov     rcx, [rcx+10h]
0x1800aa773  call    WPP_SF_d
0x1800aa778  jmp     loc_1800AA8C5
0x1800aa77d  xor     edx, edx; Val
0x1800aa77f  lea     rcx, [rsp+290h+ExeName]; void *
0x1800aa784  mov     r8d, 208h; Size
0x1800aa78a  call    memset_0
0x1800aa78f  lea     r9, [rsp+290h+dwSize]; lpdwSize
0x1800aa794  mov     [rsp+290h+dwSize], 104h
0x1800aa79c  lea     r8, [rsp+290h+ExeName]; lpExeName
0x1800aa7a1  xor     edx, edx; dwFlags
0x1800aa7a3  mov     rcx, rbx; hProcess
0x1800aa7a6  call    cs:__imp_QueryFullProcessImageNameW
0x1800aa7ac  test    eax, eax
0x1800aa7ae  jnz     short loc_1800AA7EB
0x1800aa7b0  mov     rax, cs:WPP_GLOBAL_Control
0x1800aa7b7  lea     rdx, WPP_GLOBAL_Control
0x1800aa7be  cmp     rax, rdx
0x1800aa7c1  jz      loc_1800AA8C5
0x1800aa7c7  cmp     [rax+19h], sil
0x1800aa7cb  jb      loc_1800AA8C5
0x1800aa7d1  test    [rax+1Ch], sil
0x1800aa7d5  jz      loc_1800AA8C5
0x1800aa7db  call    cs:__imp_GetLastError
0x1800aa7e1  mov     edx, 60h ; '`'
0x1800aa7e6  jmp     loc_1800AA75E
0x1800aa7eb  lea     rdx, [rsp+290h+dwProcessId]
0x1800aa7f0  mov     qword ptr [rsp+290h+dwProcessId], 0
0x1800aa7f9  call    ??$ExpandEnvironmentStringsW@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@$0BAA@@wil@@YAJPEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@@Z; wil::ExpandEnvironmentStringsW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,256>(ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)
0x1800aa7fe  test    eax, eax
0x1800aa800  jns     short loc_1800AA834
0x1800aa802  mov     rcx, cs:WPP_GLOBAL_Control
0x1800aa809  lea     rdx, WPP_GLOBAL_Control
0x1800aa810  cmp     rcx, rdx
0x1800aa813  jz      loc_1800AA8BB
0x1800aa819  cmp     [rcx+19h], sil
0x1800aa81d  jb      loc_1800AA8BB
0x1800aa823  test    [rcx+1Ch], sil
0x1800aa827  jz      loc_1800AA8BB
0x1800aa82d  mov     edx, 61h ; 'a'
0x1800aa832  jmp     short loc_1800AA8AB
0x1800aa834  mov     rcx, qword ptr [rsp+290h+dwProcessId]; lpString1
0x1800aa839  lea     r8, [rsp+290h+ExeName]; lpString2
0x1800aa83e  or      edx, 0FFFFFFFFh; cchCount1
0x1800aa841  mov     [rsp+290h+bIgnoreCase], esi; bIgnoreCase
0x1800aa845  mov     r9d, edx; cchCount2
0x1800aa848  call    cs:__imp_CompareStringOrdinal
0x1800aa84e  cmp     eax, 2
0x1800aa851  jz      short loc_1800AA879
0x1800aa853  mov     rcx, cs:WPP_GLOBAL_Control
0x1800aa85a  lea     rdx, WPP_GLOBAL_Control
0x1800aa861  cmp     rcx, rdx
0x1800aa864  jz      short loc_1800AA8BB
0x1800aa866  cmp     [rcx+19h], sil
0x1800aa86a  jb      short loc_1800AA8BB
0x1800aa86c  test    [rcx+1Ch], sil
0x1800aa870  jz      short loc_1800AA8BB
0x1800aa872  mov     edx, 62h ; 'b'
0x1800aa877  jmp     short loc_1800AA8AB
0x1800aa879  lea     rcx, [rsp+290h+ExeName]; unsigned __int16 *
0x1800aa87e  call    ?ValidateFileSignedByMicrosoft@@YAJPEBG@Z; ValidateFileSignedByMicrosoft(ushort const *)
0x1800aa883  test    eax, eax
0x1800aa885  jns     short loc_1800AA8DD
0x1800aa887  mov     rcx, cs:WPP_GLOBAL_Control
0x1800aa88e  lea     rdx, WPP_GLOBAL_Control
0x1800aa895  cmp     rcx, rdx
0x1800aa898  jz      short loc_1800AA8BB
0x1800aa89a  cmp     [rcx+19h], sil
0x1800aa89e  jb      short loc_1800AA8BB
0x1800aa8a0  test    [rcx+1Ch], sil
0x1800aa8a4  jz      short loc_1800AA8BB
0x1800aa8a6  mov     edx, 63h ; 'c'
0x1800aa8ab  mov     rcx, [rcx+10h]
0x1800aa8af  lea     r8, WPP_59cb1c30c417333f98d499625c161da5_Traceguids
0x1800aa8b6  call    WPP_SF_
0x1800aa8bb  lea     rcx, [rsp+290h+dwProcessId]
0x1800aa8c0  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800aa8c5  lea     rcx, [rsp+290h+var_258]
0x1800aa8ca  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800aa8cf  test    edi, edi
0x1800aa8d1  jnz     short loc_1800AA8D9
0x1800aa8d3  call    cs:__imp_RpcRevertToSelf
0x1800aa8d9  xor     eax, eax
0x1800aa8db  jmp     short loc_1800AA8FD
0x1800aa8dd  lea     rcx, [rsp+290h+dwProcessId]
0x1800aa8e2  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800aa8e7  lea     rcx, [rsp+290h+var_258]
0x1800aa8ec  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800aa8f1  test    edi, edi
0x1800aa8f3  jnz     short loc_1800AA8FB
0x1800aa8f5  call    cs:__imp_RpcRevertToSelf
0x1800aa8fb  mov     eax, esi
0x1800aa8fd  mov     rcx, [rbp+190h+var_30]
0x1800aa904  xor     rcx, rsp; StackCookie
0x1800aa907  call    __security_check_cookie
0x1800aa90c  add     rsp, 278h
0x1800aa913  pop     rdi
0x1800aa914  pop     rsi
0x1800aa915  pop     rbx
0x1800aa916  pop     rbp
0x1800aa917  retn
```
