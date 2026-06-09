# UserAwareCallerIdentity::GetAppIdFromProcessId(ulong,ushort * *)

- ea: `0x1800699e4`
- end: `0x180069b73`
- name: `?GetAppIdFromProcessId@UserAwareCallerIdentity@@YAJKPEAPEAG@Z`
- size: `399`
- prototype: `__int64 __fastcall(UserAwareCallerIdentity *__hidden this, unsigned int, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, service_task`

## callers

- `0x18006bd80`

## callees

- `0x1800192a8`
- `0x180019534`
- `0x180019b14`
- `0x18001cc38`
- `0x18001d95c`
- `0x18002b1b0`
- `0x18002bc68`
- `0x18002d43c`
- `0x1800366cc`
- `0x18004b7cc`
- `0x1800699e4`
- `0x180076818`

## import_xrefs

- `api-ms-win-appmodel-runtime-l1-1-1!GetApplicationUserModelIdFromToken` at `0x180069aa2`
- `api-ms-win-appmodel-runtime-l1-1-1!GetApplicationUserModelIdFromToken` at `0x180069aa2`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrOpenProcessTokenForQuery` at `0x180069a83`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrOpenProcessTokenForQuery` at `0x180069a83`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall UserAwareCallerIdentity::GetAppIdFromProcessId(
        UserAwareCallerIdentity *this,
        _QWORD *a2,
        unsigned __int16 **a3)
{
  DWORD v4; // esi
  unsigned __int16 **v5; // r8
  int AppIdFromProcessId; // eax
  __int64 v7; // rdx
  __int64 v8; // rcx
  __int64 v9; // r8
  int v10; // ebx
  int ApplicationUserModelIdFromToken; // eax
  __int64 v12; // rdx
  __int64 v13; // rcx
  bool v14; // sf
  __int64 v15; // rax
  int v17; // [rsp+20h] [rbp-E0h]
  __int64 v18; // [rsp+30h] [rbp-D0h] BYREF
  UINT32 applicationUserModelIdLength; // [rsp+38h] [rbp-C8h] BYREF
  HANDLE token; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD v21[2]; // [rsp+48h] [rbp-B8h] BYREF
  char v22; // [rsp+58h] [rbp-A8h]
  WCHAR applicationUserModelId[136]; // [rsp+60h] [rbp-A0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+198h] [rbp+98h]

  v4 = (unsigned int)this;
  *a2 = 0;
  v18 = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &v18,
    0);
  AppIdFromProcessId = CallerIdentity::GetAppIdFromProcessId(v4, &v18, v5);
  v10 = AppIdFromProcessId;
  if ( AppIdFromProcessId != -2147024891 )
  {
    if ( AppIdFromProcessId < 0 )
      goto LABEL_14;
    goto LABEL_13;
  }
  if ( (unsigned __int8)IsUMgrOpenProcessHandleForAccessPresent(v8, v7, v9) )
  {
    token = 0;
    memset_0(applicationUserModelId, 0, 0x106u);
    applicationUserModelIdLength = 131;
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      &token,
      0);
    v10 = UMgrOpenProcessTokenForQuery(v4, &token);
    if ( v10 < 0 )
    {
LABEL_10:
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&token);
      goto LABEL_14;
    }
    ApplicationUserModelIdFromToken = GetApplicationUserModelIdFromToken(
                                        token,
                                        &applicationUserModelIdLength,
                                        applicationUserModelId);
    v14 = ApplicationUserModelIdFromToken < 0;
    if ( ApplicationUserModelIdFromToken > 0 )
    {
      ApplicationUserModelIdFromToken = (unsigned __int16)ApplicationUserModelIdFromToken | 0x80070000;
      v14 = ApplicationUserModelIdFromToken < 0;
    }
    if ( v14 )
    {
      v10 = ApplicationUserModelIdFromToken;
      goto LABEL_10;
    }
    v21[0] = &v18;
    v21[1] = 0;
    v22 = 1;
    v10 = _AllocStringWorker<CTCoAllocPolicy>(v13, v12, applicationUserModelId, applicationUserModelIdLength);
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(v21);
    if ( v10 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x100,
        (unsigned int)"onecoreuap\\internal\\base\\inc\\UserAwareCallerIdentity.h",
        (const char *)(unsigned int)v10,
        v17);
      goto LABEL_10;
    }
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&token);
LABEL_13:
    v15 = v18;
    v18 = 0;
    *a2 = v15;
    v10 = 0;
  }
LABEL_14:
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v18);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1800699e4  mov     [rsp-8+arg_10], rbx
0x1800699e9  push    rbp
0x1800699ea  push    rsi
0x1800699eb  push    rdi
0x1800699ec  lea     rbp, [rsp-80h]
0x1800699f1  sub     rsp, 180h
0x1800699f8  mov     rax, cs:__security_cookie
0x1800699ff  xor     rax, rsp
0x180069a02  mov     [rbp+90h+var_20], rax
0x180069a06  mov     rdi, rdx
0x180069a09  mov     esi, ecx
0x180069a0b  mov     qword ptr [rdx], 0
0x180069a12  mov     [rsp+190h+var_160], 0
0x180069a1b  xor     edx, edx
0x180069a1d  lea     rcx, [rsp+190h+var_160]
0x180069a22  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180069a27  lea     rdx, [rsp+190h+var_160]; void *
0x180069a2c  mov     ecx, esi; dwProcessId
0x180069a2e  call    ?GetAppIdFromProcessId@CallerIdentity@@YAJKPEAPEAG@Z; CallerIdentity::GetAppIdFromProcessId(ulong,ushort * *)
0x180069a33  mov     ebx, eax
0x180069a35  cmp     eax, 80070005h
0x180069a3a  jnz     loc_180069B31
0x180069a40  call    IsUMgrOpenProcessHandleForAccessPresent
0x180069a45  test    al, al
0x180069a47  jz      loc_180069B48
0x180069a4d  mov     [rsp+190h+token], 0
0x180069a56  xor     edx, edx; Val
0x180069a58  mov     r8d, 106h; Size
0x180069a5e  lea     rcx, [rsp+190h+applicationUserModelId]; void *
0x180069a63  call    memset_0
0x180069a68  mov     [rsp+190h+applicationUserModelIdLength], 83h
0x180069a70  xor     edx, edx
0x180069a72  lea     rcx, [rsp+190h+token]
0x180069a77  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180069a7c  lea     rdx, [rsp+190h+token]
0x180069a81  mov     ecx, esi
0x180069a83  call    cs:__imp_UMgrOpenProcessTokenForQuery
0x180069a89  mov     ebx, eax
0x180069a8b  test    eax, eax
0x180069a8d  js      loc_180069B19
0x180069a93  lea     r8, [rsp+190h+applicationUserModelId]; applicationUserModelId
0x180069a98  lea     rdx, [rsp+190h+applicationUserModelIdLength]; applicationUserModelIdLength
0x180069a9d  mov     rcx, [rsp+190h+token]; token
0x180069aa2  call    cs:__imp_GetApplicationUserModelIdFromToken
0x180069aa8  test    eax, eax
0x180069aaa  jle     short loc_180069AB6
0x180069aac  movzx   eax, ax
0x180069aaf  or      eax, 80070000h
0x180069ab4  test    eax, eax
0x180069ab6  jns     short loc_180069ABC
0x180069ab8  mov     ebx, eax
0x180069aba  jmp     short loc_180069B19
0x180069abc  lea     rax, [rsp+190h+var_160]
0x180069ac1  mov     [rsp+190h+var_148], rax
0x180069ac6  mov     [rsp+190h+var_140], 0
0x180069acf  mov     [rsp+190h+var_138], 1
0x180069ad4  mov     r9d, [rsp+190h+applicationUserModelIdLength]
0x180069ad9  lea     rax, [rsp+190h+var_140]
0x180069ade  mov     [rsp+190h+var_168], rax
0x180069ae3  lea     r8, [rsp+190h+applicationUserModelId]
0x180069ae8  call    ??$_AllocStringWorker@VCTCoAllocPolicy@@@@YAJPEAXKPEBG_K2PEAPEAG@Z; _AllocStringWorker<CTCoAllocPolicy>(void *,ulong,ushort const *,unsigned __int64,unsigned __int64,ushort * *)
0x180069aed  mov     ebx, eax
0x180069aef  lea     rcx, [rsp+190h+var_148]
0x180069af4  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(void)
0x180069af9  test    ebx, ebx
0x180069afb  jns     short loc_180069B25
0x180069afd  mov     rcx, [rbp+98h]; this
0x180069b04  mov     r9d, ebx; char *
0x180069b07  lea     r8, aOnecoreuapInte_1; "onecoreuap\\internal\\base\\inc\\UserAw"...
0x180069b0e  mov     edx, 100h; void *
0x180069b13  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180069b18  nop
0x180069b19  lea     rcx, [rsp+190h+token]
0x180069b1e  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180069b23  jmp     short loc_180069B48
0x180069b25  lea     rcx, [rsp+190h+token]
0x180069b2a  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180069b2f  jmp     short loc_180069B35
0x180069b31  test    eax, eax
0x180069b33  js      short loc_180069B48
0x180069b35  mov     rax, [rsp+190h+var_160]
0x180069b3a  mov     [rsp+190h+var_160], 0
0x180069b43  mov     [rdi], rax
0x180069b46  xor     ebx, ebx
0x180069b48  lea     rcx, [rsp+190h+var_160]
0x180069b4d  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180069b52  mov     eax, ebx
0x180069b54  mov     rcx, [rbp+90h+var_20]
0x180069b58  xor     rcx, rsp; StackCookie
0x180069b5b  call    __security_check_cookie
0x180069b60  mov     rbx, [rsp+190h+arg_10]
0x180069b68  add     rsp, 180h
0x180069b6f  pop     rdi
0x180069b70  pop     rsi
0x180069b71  pop     rbp
0x180069b72  retn
```
