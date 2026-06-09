# Windows::System::Internal::Implementation::RegUtil::GetPersistedRegistryLocationAlloc(ushort const *,ushort const *,ushort * *)

- ea: `0x18004c3cc`
- end: `0x18004c55a`
- name: `?GetPersistedRegistryLocationAlloc@RegUtil@Implementation@Internal@System@Windows@@SAJPEBG0PEAPEAG@Z`
- size: `398`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18004c560`
- `0x1800c21d0`

## callees

- `0x18004bfa0`
- `0x18004c3cc`
- `0x180074aa0`
- `0x1800755e8`
- `0x180087f94`
- `0x180089f18`

## import_xrefs

- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x18004c40d`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x18004c496`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x18004c4b2`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x18004c40d`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x18004c496`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x18004c4b2`

## string_xrefs

- `0x18004c41e`: `onecore\ds\security\umstartup\usermgr\lib\regutil.h`
- `0x18004c4cf`: `onecore\ds\security\umstartup\usermgr\lib\regutil.h`
- `0x18004c506`: `onecore\ds\security\umstartup\usermgr\lib\regutil.h`
- `0x18004c444`: `IFC(onecore\ds\security\umstartup\usermgr\lib\regutil.h_409)`
- `0x18004c4ec`: `IFC(onecore\ds\security\umstartup\usermgr\lib\regutil.h_418)`
- `0x18004c528`: `IFC(onecore\ds\security\umstartup\usermgr\lib\regutil.h_415)`

## pseudocode

```c
__int64 __fastcall Windows::System::Internal::Implementation::RegUtil::GetPersistedRegistryLocationAlloc(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        unsigned __int16 **a3)
{
  const char *v6; // r9
  unsigned int v7; // ebx
  __int64 v8; // rcx
  const wchar_t *v9; // r8
  unsigned __int16 *v10; // rdi
  int PersistedRegistryLocationW; // eax
  _QWORD v13[2]; // [rsp+30h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+28h]
  int v15; // [rsp+80h] [rbp+40h] BYREF
  unsigned __int16 *v16; // [rsp+88h] [rbp+48h] BYREF

  *a3 = 0;
  v15 = 0;
  v16 = 0;
  if ( (unsigned int)GetPersistedRegistryLocationW(a1, a2, 0, 0) == 234 )
  {
    wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
      v13,
      0,
      (unsigned int)v15,
      v6);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
      &v16,
      v13);
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(v13);
    v10 = v16;
    if ( v16 )
    {
      v7 = 0;
      if ( !(unsigned int)GetPersistedRegistryLocationW(a1, a2, v16, (unsigned int)v15) )
        goto LABEL_11;
      PersistedRegistryLocationW = GetPersistedRegistryLocationW(a1, a2, v10, (unsigned int)v15);
      v7 = PersistedRegistryLocationW;
      if ( PersistedRegistryLocationW > 0 )
        v7 = (unsigned __int16)PersistedRegistryLocationW | 0x80070000;
      if ( (v7 & 0x80000000) != 0 )
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x1A2,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\regutil.h",
          (const char *)v7,
          0);
        if ( (Microsoft_Windows_User_UserManager_EventsEnableBits & 2) != 0 )
        {
          v9 = L"IFC(onecore\\ds\\security\\umstartup\\usermgr\\lib\\regutil.h_418)";
          goto LABEL_14;
        }
      }
      else
      {
LABEL_11:
        v16 = 0;
        *a3 = v10;
      }
    }
    else
    {
      v7 = -2147024882;
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x19F,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\regutil.h",
        (const char *)0x8007000ELL,
        (int)&v15);
      if ( (Microsoft_Windows_User_UserManager_EventsEnableBits & 2) != 0 )
      {
        v9 = L"IFC(onecore\\ds\\security\\umstartup\\usermgr\\lib\\regutil.h_415)";
        goto LABEL_14;
      }
    }
  }
  else
  {
    v7 = -2147418113;
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x199,
      (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\regutil.h",
      (const char *)0x8000FFFFLL,
      (int)&v15);
    if ( (Microsoft_Windows_User_UserManager_EventsEnableBits & 2) != 0 )
    {
      v9 = L"IFC(onecore\\ds\\security\\umstartup\\usermgr\\lib\\regutil.h_409)";
LABEL_14:
      McTemplateU0zd_EventWriteTransfer(v8, LogWarning, v9, v7);
    }
  }
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v16);
  return v7;
}

```

## disassembly

```asm
0x18004c3cc  mov     [rsp-28h+arg_0], rbx
0x18004c3d1  push    rbp
0x18004c3d2  push    rsi
0x18004c3d3  push    rdi
0x18004c3d4  push    r14
0x18004c3d6  push    r15
0x18004c3d8  mov     rbp, rsp
0x18004c3db  sub     rsp, 40h
0x18004c3df  mov     r15, r8
0x18004c3e2  mov     qword ptr [r8], 0
0x18004c3e9  lea     rax, [rbp+arg_10]
0x18004c3ed  mov     [rbp+arg_10], 0
0x18004c3f4  xor     r8d, r8d
0x18004c3f7  mov     qword ptr [rsp+40h+var_20], rax; int
0x18004c3fc  xor     r9d, r9d
0x18004c3ff  mov     [rbp+arg_18], 0
0x18004c407  mov     rsi, rdx
0x18004c40a  mov     r14, rcx
0x18004c40d  call    cs:__imp_GetPersistedRegistryLocationW
0x18004c413  cmp     eax, 0EAh
0x18004c418  jz      short loc_18004C450
0x18004c41a  mov     rcx, [rbp+28h]; this
0x18004c41e  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\umstartup\\userm"...
0x18004c425  mov     ebx, 8000FFFFh
0x18004c42a  mov     edx, 199h; void *
0x18004c42f  mov     r9d, ebx; char *
0x18004c432  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18004c437  test    cs:Microsoft_Windows_User_UserManager_EventsEnableBits, 2
0x18004c43e  jz      loc_18004C53E
0x18004c444  lea     r8, aIfcOnecoreDsSe_6; "IFC(onecore\\ds\\security\\umstartup\\u"...
0x18004c44b  jmp     loc_18004C52F
0x18004c450  mov     r8d, [rbp+arg_10]
0x18004c454  lea     rcx, [rbp+var_10]
0x18004c458  xor     edx, edx
0x18004c45a  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x18004c45f  lea     rdx, [rbp+var_10]
0x18004c463  lea     rcx, [rbp+arg_18]
0x18004c467  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x18004c46c  lea     rcx, [rbp+var_10]
0x18004c470  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18004c475  mov     rdi, [rbp+arg_18]
0x18004c479  test    rdi, rdi
0x18004c47c  jz      loc_18004C502
0x18004c482  mov     r9d, [rbp+arg_10]
0x18004c486  xor     ebx, ebx
0x18004c488  mov     r8, rdi
0x18004c48b  mov     qword ptr [rsp+40h+var_20], rbx
0x18004c490  mov     rdx, rsi
0x18004c493  mov     rcx, r14
0x18004c496  call    cs:__imp_GetPersistedRegistryLocationW
0x18004c49c  test    eax, eax
0x18004c49e  jz      short loc_18004C4F5
0x18004c4a0  mov     r9d, [rbp+arg_10]
0x18004c4a4  mov     r8, rdi
0x18004c4a7  mov     rdx, rsi
0x18004c4aa  mov     qword ptr [rsp+40h+var_20], rbx; int
0x18004c4af  mov     rcx, r14
0x18004c4b2  call    cs:__imp_GetPersistedRegistryLocationW
0x18004c4b8  mov     ebx, eax
0x18004c4ba  test    eax, eax
0x18004c4bc  jle     short loc_18004C4C7
0x18004c4be  movzx   ebx, ax
0x18004c4c1  or      ebx, 80070000h
0x18004c4c7  test    ebx, ebx
0x18004c4c9  jns     short loc_18004C4F5
0x18004c4cb  mov     rcx, [rbp+28h]; this
0x18004c4cf  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\umstartup\\userm"...
0x18004c4d6  mov     r9d, ebx; char *
0x18004c4d9  mov     edx, 1A2h; void *
0x18004c4de  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18004c4e3  test    cs:Microsoft_Windows_User_UserManager_EventsEnableBits, 2
0x18004c4ea  jz      short loc_18004C53E
0x18004c4ec  lea     r8, aIfcOnecoreDsSe_41; "IFC(onecore\\ds\\security\\umstartup\\u"...
0x18004c4f3  jmp     short loc_18004C52F
0x18004c4f5  mov     [rbp+arg_18], 0
0x18004c4fd  mov     [r15], rdi
0x18004c500  jmp     short loc_18004C53E
0x18004c502  mov     rcx, [rbp+28h]; this
0x18004c506  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\umstartup\\userm"...
0x18004c50d  mov     ebx, 8007000Eh
0x18004c512  mov     edx, 19Fh; void *
0x18004c517  mov     r9d, ebx; char *
0x18004c51a  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18004c51f  test    cs:Microsoft_Windows_User_UserManager_EventsEnableBits, 2
0x18004c526  jz      short loc_18004C53E
0x18004c528  lea     r8, aIfcOnecoreDsSe_23; "IFC(onecore\\ds\\security\\umstartup\\u"...
0x18004c52f  mov     r9d, ebx
0x18004c532  lea     rdx, LogWarning
0x18004c539  call    McTemplateU0zd_EventWriteTransfer
0x18004c53e  lea     rcx, [rbp+arg_18]
0x18004c542  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18004c547  mov     eax, ebx
0x18004c549  mov     rbx, [rsp+40h+arg_0]
0x18004c54e  add     rsp, 40h
0x18004c552  pop     r15
0x18004c554  pop     r14
0x18004c556  pop     rdi
0x18004c557  pop     rsi
0x18004c558  pop     rbp
0x18004c559  retn
```
