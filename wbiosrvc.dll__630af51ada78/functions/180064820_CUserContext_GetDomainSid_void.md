# CUserContext::GetDomainSid(void * *)

- ea: `0x180064820`
- end: `0x180064932`
- name: `?GetDomainSid@CUserContext@@QEBAJPEAPEAX@Z`
- size: `274`
- prototype: `__int64 __fastcall(CUserContext *__hidden this, void **)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800bb7b0`
- `0x1800bbc20`

## callees

- `0x180064820`
- `0x180064938`
- `0x1800bb728`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800648d0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800648d0`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180064893`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180064893`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800648ac`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800648f1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180064909`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006491e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800648ac`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800648f1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180064909`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006491e`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1800648c6`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1800648c6`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180064884`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180064884`
- `samcli!NetUserModalsGet` at `0x18006485a`
- `samcli!NetUserModalsGet` at `0x18006485a`

## pseudocode

```c
__int64 __fastcall CUserContext::GetDomainSid(CUserContext *this, void **a2)
{
  DWORD v3; // ebx
  SIZE_T LengthSid; // rbx
  HLOCAL v5; // rax
  void *v6; // rdi
  signed int LastError; // eax
  unsigned int v9; // ebx
  __int64 *v10; // [rsp+20h] [rbp-28h] BYREF
  LPBYTE bufptr; // [rsp+28h] [rbp-20h] BYREF
  char v12; // [rsp+30h] [rbp-18h]
  __int64 v13; // [rsp+70h] [rbp+28h] BYREF

  v13 = 0;
  bufptr = 0;
  v10 = &v13;
  v12 = 1;
  v3 = NetUserModalsGet(0, 2u, &bufptr);
  wil::details::out_param_ptr_t<unsigned char * *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_USER_MODALS_INFO_2 *,unsigned long (*)(void *),&unsigned long NetApiBufferFree(void *),wistd::integral_constant<unsigned __int64,0>,_USER_MODALS_INFO_2 *,_USER_MODALS_INFO_2 *,0,std::nullptr_t>>>>::~out_param_ptr_t<unsigned char * *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_USER_MODALS_INFO_2 *,unsigned long (*)(void *),&unsigned long NetApiBufferFree(void *),wistd::integral_constant<unsigned __int64,0>,_USER_MODALS_INFO_2 *,_USER_MODALS_INFO_2 *,0,std::nullptr_t>>>>(&v10);
  if ( v3 || !v13 )
  {
    wil::details::unique_storage<wil::details::resource_policy<_USER_MODALS_INFO_2 *,unsigned long (*)(void *),&unsigned long NetApiBufferFree(void *),wistd::integral_constant<unsigned __int64,0>,_USER_MODALS_INFO_2 *,_USER_MODALS_INFO_2 *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_USER_MODALS_INFO_2 *,unsigned long (*)(void *),&unsigned long NetApiBufferFree(void *),wistd::integral_constant<unsigned __int64,0>,_USER_MODALS_INFO_2 *,_USER_MODALS_INFO_2 *,0,std::nullptr_t>>(&v13);
    LocalFree(0);
    return 2147500037LL;
  }
  else
  {
    LengthSid = GetLengthSid(*(PSID *)(v13 + 8));
    v5 = LocalAlloc(0x40u, LengthSid);
    v6 = v5;
    if ( v5 )
    {
      if ( CopySid(LengthSid, v5, *(PSID *)(v13 + 8)) )
      {
        *a2 = v6;
        wil::details::unique_storage<wil::details::resource_policy<_USER_MODALS_INFO_2 *,unsigned long (*)(void *),&unsigned long NetApiBufferFree(void *),wistd::integral_constant<unsigned __int64,0>,_USER_MODALS_INFO_2 *,_USER_MODALS_INFO_2 *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_USER_MODALS_INFO_2 *,unsigned long (*)(void *),&unsigned long NetApiBufferFree(void *),wistd::integral_constant<unsigned __int64,0>,_USER_MODALS_INFO_2 *,_USER_MODALS_INFO_2 *,0,std::nullptr_t>>(&v13);
        LocalFree(0);
        return 0;
      }
      else
      {
        LastError = GetLastError();
        v9 = LastError;
        if ( LastError > 0 )
          v9 = (unsigned __int16)LastError | 0x80070000;
        wil::details::unique_storage<wil::details::resource_policy<_USER_MODALS_INFO_2 *,unsigned long (*)(void *),&unsigned long NetApiBufferFree(void *),wistd::integral_constant<unsigned __int64,0>,_USER_MODALS_INFO_2 *,_USER_MODALS_INFO_2 *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_USER_MODALS_INFO_2 *,unsigned long (*)(void *),&unsigned long NetApiBufferFree(void *),wistd::integral_constant<unsigned __int64,0>,_USER_MODALS_INFO_2 *,_USER_MODALS_INFO_2 *,0,std::nullptr_t>>(&v13);
        LocalFree(v6);
        return v9;
      }
    }
    else
    {
      wil::details::unique_storage<wil::details::resource_policy<_USER_MODALS_INFO_2 *,unsigned long (*)(void *),&unsigned long NetApiBufferFree(void *),wistd::integral_constant<unsigned __int64,0>,_USER_MODALS_INFO_2 *,_USER_MODALS_INFO_2 *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_USER_MODALS_INFO_2 *,unsigned long (*)(void *),&unsigned long NetApiBufferFree(void *),wistd::integral_constant<unsigned __int64,0>,_USER_MODALS_INFO_2 *,_USER_MODALS_INFO_2 *,0,std::nullptr_t>>(&v13);
      LocalFree(0);
      return 2147942414LL;
    }
  }
}

```

## disassembly

```asm
0x180064820  mov     [rsp-20h+arg_0], rcx
0x180064825  push    rbp
0x180064826  push    rbx
0x180064827  push    rsi
0x180064828  push    rdi
0x180064829  mov     rbp, rsp
0x18006482c  sub     rsp, 48h
0x180064830  mov     rsi, rdx
0x180064833  mov     [rbp+arg_0], 0
0x18006483b  lea     rax, [rbp+arg_0]
0x18006483f  mov     [rbp+bufptr], 0
0x180064847  mov     edx, 2; level
0x18006484c  mov     [rbp+var_28], rax
0x180064850  lea     r8, [rbp+bufptr]; bufptr
0x180064854  mov     [rbp+var_18], 1
0x180064858  xor     ecx, ecx; servername
0x18006485a  call    cs:__imp_NetUserModalsGet
0x180064860  lea     rcx, [rbp+var_28]
0x180064864  mov     ebx, eax
0x180064866  call    ??1?$out_param_ptr_t@PEAPEAEV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_USER_MODALS_INFO_2@@P6AKPEAX@Z$1?NetApiBufferFree@@YAK0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_ptr_t<uchar * *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_USER_MODALS_INFO_2 *,ulong (*)(void *),&NetApiBufferFree(void *),wistd::integral_constant<unsigned __int64,0>,_USER_MODALS_INFO_2 *,_USER_MODALS_INFO_2 *,0,std::nullptr_t>>>>::~out_param_ptr_t<uchar * *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_USER_MODALS_INFO_2 *,ulong (*)(void *),&NetApiBufferFree(void *),wistd::integral_constant<unsigned __int64,0>,_USER_MODALS_INFO_2 *,_USER_MODALS_INFO_2 *,0,std::nullptr_t>>>>(void)
0x18006486b  test    ebx, ebx
0x18006486d  jnz     loc_180064913
0x180064873  mov     rcx, [rbp+arg_0]
0x180064877  test    rcx, rcx
0x18006487a  jz      loc_180064913
0x180064880  mov     rcx, [rcx+8]; pSid
0x180064884  call    cs:__imp_GetLengthSid
0x18006488a  mov     edx, eax; uBytes
0x18006488c  mov     ecx, 40h ; '@'; uFlags
0x180064891  mov     ebx, eax
0x180064893  call    cs:__imp_LocalAlloc
0x180064899  mov     rdi, rax
0x18006489c  test    rax, rax
0x18006489f  jnz     short loc_1800648B9
0x1800648a1  lea     rcx, [rbp+arg_0]
0x1800648a5  call    ??1?$unique_storage@U?$resource_policy@PEAU_USER_MODALS_INFO_2@@P6AKPEAX@Z$1?NetApiBufferFree@@YAK0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_USER_MODALS_INFO_2 *,ulong (*)(void *),&NetApiBufferFree(void *),wistd::integral_constant<unsigned __int64,0>,_USER_MODALS_INFO_2 *,_USER_MODALS_INFO_2 *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_USER_MODALS_INFO_2 *,ulong (*)(void *),&NetApiBufferFree(void *),wistd::integral_constant<unsigned __int64,0>,_USER_MODALS_INFO_2 *,_USER_MODALS_INFO_2 *,0,std::nullptr_t>>(void)
0x1800648aa  xor     ecx, ecx; hMem
0x1800648ac  call    cs:__imp_LocalFree
0x1800648b2  mov     eax, 8007000Eh
0x1800648b7  jmp     short loc_180064929
0x1800648b9  mov     r8, [rbp+arg_0]
0x1800648bd  mov     rdx, rdi; pDestinationSid
0x1800648c0  mov     ecx, ebx; nDestinationSidLength
0x1800648c2  mov     r8, [r8+8]; pSourceSid
0x1800648c6  call    cs:__imp_CopySid
0x1800648cc  test    eax, eax
0x1800648ce  jnz     short loc_1800648FB
0x1800648d0  call    cs:__imp_GetLastError
0x1800648d6  mov     ebx, eax
0x1800648d8  test    eax, eax
0x1800648da  jle     short loc_1800648E5
0x1800648dc  movzx   ebx, ax
0x1800648df  or      ebx, 80070000h
0x1800648e5  lea     rcx, [rbp+arg_0]
0x1800648e9  call    ??1?$unique_storage@U?$resource_policy@PEAU_USER_MODALS_INFO_2@@P6AKPEAX@Z$1?NetApiBufferFree@@YAK0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_USER_MODALS_INFO_2 *,ulong (*)(void *),&NetApiBufferFree(void *),wistd::integral_constant<unsigned __int64,0>,_USER_MODALS_INFO_2 *,_USER_MODALS_INFO_2 *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_USER_MODALS_INFO_2 *,ulong (*)(void *),&NetApiBufferFree(void *),wistd::integral_constant<unsigned __int64,0>,_USER_MODALS_INFO_2 *,_USER_MODALS_INFO_2 *,0,std::nullptr_t>>(void)
0x1800648ee  mov     rcx, rdi; hMem
0x1800648f1  call    cs:__imp_LocalFree
0x1800648f7  mov     eax, ebx
0x1800648f9  jmp     short loc_180064929
0x1800648fb  lea     rcx, [rbp+arg_0]
0x1800648ff  mov     [rsi], rdi
0x180064902  call    ??1?$unique_storage@U?$resource_policy@PEAU_USER_MODALS_INFO_2@@P6AKPEAX@Z$1?NetApiBufferFree@@YAK0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_USER_MODALS_INFO_2 *,ulong (*)(void *),&NetApiBufferFree(void *),wistd::integral_constant<unsigned __int64,0>,_USER_MODALS_INFO_2 *,_USER_MODALS_INFO_2 *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_USER_MODALS_INFO_2 *,ulong (*)(void *),&NetApiBufferFree(void *),wistd::integral_constant<unsigned __int64,0>,_USER_MODALS_INFO_2 *,_USER_MODALS_INFO_2 *,0,std::nullptr_t>>(void)
0x180064907  xor     ecx, ecx; hMem
0x180064909  call    cs:__imp_LocalFree
0x18006490f  xor     eax, eax
0x180064911  jmp     short loc_180064929
0x180064913  lea     rcx, [rbp+arg_0]
0x180064917  call    ??1?$unique_storage@U?$resource_policy@PEAU_USER_MODALS_INFO_2@@P6AKPEAX@Z$1?NetApiBufferFree@@YAK0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_USER_MODALS_INFO_2 *,ulong (*)(void *),&NetApiBufferFree(void *),wistd::integral_constant<unsigned __int64,0>,_USER_MODALS_INFO_2 *,_USER_MODALS_INFO_2 *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_USER_MODALS_INFO_2 *,ulong (*)(void *),&NetApiBufferFree(void *),wistd::integral_constant<unsigned __int64,0>,_USER_MODALS_INFO_2 *,_USER_MODALS_INFO_2 *,0,std::nullptr_t>>(void)
0x18006491c  xor     ecx, ecx; hMem
0x18006491e  call    cs:__imp_LocalFree
0x180064924  mov     eax, 80004005h
0x180064929  add     rsp, 48h
0x18006492d  pop     rdi
0x18006492e  pop     rsi
0x18006492f  pop     rbx
0x180064930  pop     rbp
0x180064931  retn
```
