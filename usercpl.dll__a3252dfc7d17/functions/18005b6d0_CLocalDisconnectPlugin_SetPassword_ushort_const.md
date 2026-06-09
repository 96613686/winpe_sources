# CLocalDisconnectPlugin::SetPassword(ushort const *)

- ea: `0x18005b6d0`
- end: `0x18005b9f8`
- name: `?SetPassword@CLocalDisconnectPlugin@@UEAAJPEBG@Z`
- size: `808`
- prototype: `int(CLocalDisconnectPlugin *__hidden this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `8`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180006a54`
- `0x180006a74`
- `0x180026218`
- `0x18005a8f0`
- `0x18005acac`
- `0x18005b6d0`
- `0x18006e7f0`
- `0x180078010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005b842`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005b8a6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005b842`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005b8a6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005b7c8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005b7db`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005b853`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005b861`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005b8b7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005b8c5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005b7c8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005b7db`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005b853`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005b861`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005b8b7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005b8c5`
- `ADVAPI32!LogonUserW` at `0x18005b813`
- `ADVAPI32!LogonUserW` at `0x18005b813`

## string_xrefs

- `0x18005b70c`: `shell\cpls\usercpl\taskflows\plugins\localdisconnectplugin.cpp`
- `0x18005b7ab`: `shell\cpls\usercpl\taskflows\plugins\localdisconnectplugin.cpp`
- `0x18005b821`: `shell\cpls\usercpl\taskflows\plugins\localdisconnectplugin.cpp`
- `0x18005b8ee`: `shell\cpls\usercpl\taskflows\plugins\localdisconnectplugin.cpp`
- `0x18005b939`: `shell\cpls\usercpl\taskflows\plugins\localdisconnectplugin.cpp`
- `0x18005b981`: `shell\cpls\usercpl\taskflows\plugins\localdisconnectplugin.cpp`

## pseudocode

```c
__int64 __fastcall CLocalDisconnectPlugin::SetPassword(CLocalDisconnectPlugin *this, const unsigned __int16 *a2)
{
  int v4; // eax
  CLocalDisconnectPlugin *v5; // rcx
  unsigned int v6; // ebx
  void (*v7)(void); // rax
  int CurrentConnectedUser; // eax
  CLocalDisconnectPlugin *v10; // rcx
  __int64 v11; // rdx
  int ConnectedUserProperties; // eax
  WCHAR *v13; // rbx
  const char *v14; // r9
  unsigned int LastError; // esi
  int v16; // eax
  void (*v17)(void); // rax
  int dwLogonProvider; // [rsp+20h] [rbp-20h]
  int dwLogonProvidera; // [rsp+20h] [rbp-20h]
  LPCWSTR lpszUsername; // [rsp+30h] [rbp-10h] BYREF
  HANDLE hObject; // [rsp+38h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+18h]
  struct IUserData *v23; // [rsp+60h] [rbp+20h] BYREF
  struct IConnectedUser *v24; // [rsp+70h] [rbp+30h] BYREF
  LPVOID pv; // [rsp+78h] [rbp+38h] BYREF

  v23 = 0;
  v4 = (*(__int64 (__fastcall **)(_QWORD, struct IUserData **))(**((_QWORD **)this + 6) + 48LL))(
         *((_QWORD *)this + 6),
         &v23);
  v6 = v4;
  if ( v4 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA3,
      (unsigned int)"shell\\cpls\\usercpl\\taskflows\\plugins\\localdisconnectplugin.cpp",
      (const char *)(unsigned int)v4,
      dwLogonProvider);
LABEL_3:
    if ( !v23 )
      return v6;
    v7 = *(void (**)(void))(*(_QWORD *)v23 + 16LL);
LABEL_5:
    v7();
    return v6;
  }
  v24 = 0;
  CurrentConnectedUser = CLocalDisconnectPlugin::GetCurrentConnectedUser(v5, v23, &v24);
  v6 = CurrentConnectedUser;
  if ( CurrentConnectedUser == -805305819 || CurrentConnectedUser == -805306268 )
  {
    v6 = (*(__int64 (__fastcall **)(struct IUserData *, const unsigned __int16 *))(*(_QWORD *)v23 + 40LL))(v23, a2);
    if ( v6 == 1 )
    {
      v6 = -2147024810;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xAB,
        (unsigned int)"shell\\cpls\\usercpl\\taskflows\\plugins\\localdisconnectplugin.cpp",
        (const char *)0x80070056LL,
        dwLogonProvider);
      if ( v24 )
        (*(void (__fastcall **)(struct IConnectedUser *))(*(_QWORD *)v24 + 16LL))(v24);
      goto LABEL_3;
    }
    if ( (v6 & 0x80000000) != 0 )
    {
      v11 = 172;
      goto LABEL_42;
    }
  }
  else
  {
    if ( CurrentConnectedUser < 0 )
    {
      v11 = 176;
LABEL_42:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v11,
        (unsigned int)"shell\\cpls\\usercpl\\taskflows\\plugins\\localdisconnectplugin.cpp",
        (const char *)v6,
        dwLogonProvider);
      goto LABEL_43;
    }
    pv = 0;
    lpszUsername = 0;
    ConnectedUserProperties = CLocalDisconnectPlugin::GetConnectedUserProperties(
                                v10,
                                v24,
                                (unsigned __int16 **)&lpszUsername,
                                (unsigned __int16 **)&pv,
                                0);
    v6 = ConnectedUserProperties;
    if ( ConnectedUserProperties < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xB4,
        (unsigned int)"shell\\cpls\\usercpl\\taskflows\\plugins\\localdisconnectplugin.cpp",
        (const char *)(unsigned int)ConnectedUserProperties,
        dwLogonProvidera);
      if ( pv )
        CoTaskMemFree(pv);
      if ( lpszUsername )
        CoTaskMemFree((LPVOID)lpszUsername);
LABEL_43:
      if ( v24 )
      {
        v17 = *(void (**)(void))(*(_QWORD *)v24 + 16LL);
        goto LABEL_45;
      }
      goto LABEL_46;
    }
    v13 = (WCHAR *)lpszUsername;
    hObject = 0;
    if ( !LogonUserW(lpszUsername, (LPCWSTR)pv, a2, 2u, 0, &hObject) )
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0xBC,
                    (unsigned int)"shell\\cpls\\usercpl\\taskflows\\plugins\\localdisconnectplugin.cpp",
                    v14);
      if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        CloseHandle(hObject);
      if ( pv )
        CoTaskMemFree(pv);
      if ( v13 )
        CoTaskMemFree(v13);
      if ( v24 )
        (*(void (__fastcall **)(struct IConnectedUser *))(*(_QWORD *)v24 + 16LL))(v24);
      if ( v23 )
        (*(void (__fastcall **)(struct IUserData *))(*(_QWORD *)v23 + 16LL))(v23);
      return LastError;
    }
    if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(hObject);
    if ( pv )
      CoTaskMemFree(pv);
    if ( v13 )
      CoTaskMemFree(v13);
  }
  ClearAndFreeSecretString(*((unsigned __int16 **)this + 13));
  v16 = CoAllocString(a2, (unsigned __int16 **)this + 13);
  v6 = v16;
  if ( v16 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC0,
      (unsigned int)"shell\\cpls\\usercpl\\taskflows\\plugins\\localdisconnectplugin.cpp",
      (const char *)(unsigned int)v16,
      dwLogonProvider);
    if ( v24 )
    {
      v17 = *(void (**)(void))(*(_QWORD *)v24 + 16LL);
LABEL_45:
      v17();
    }
LABEL_46:
    if ( !v23 )
      return v6;
    v7 = *(void (**)(void))(*(_QWORD *)v23 + 16LL);
    goto LABEL_5;
  }
  if ( v24 )
    (*(void (__fastcall **)(struct IConnectedUser *))(*(_QWORD *)v24 + 16LL))(v24);
  if ( v23 )
    (*(void (__fastcall **)(struct IUserData *))(*(_QWORD *)v23 + 16LL))(v23);
  return 0;
}

```

## disassembly

```asm
0x18005b6d0  mov     [rsp-18h+arg_8], rbx
0x18005b6d5  push    rbp
0x18005b6d6  push    rsi
0x18005b6d7  push    r14
0x18005b6d9  mov     rbp, rsp
0x18005b6dc  sub     rsp, 40h
0x18005b6e0  mov     r14, rcx
0x18005b6e3  mov     [rbp+arg_0], 0
0x18005b6eb  mov     rcx, [rcx+30h]
0x18005b6ef  mov     rsi, rdx
0x18005b6f2  lea     rdx, [rbp+arg_0]
0x18005b6f6  mov     rax, [rcx]
0x18005b6f9  mov     rax, [rax+30h]
0x18005b6fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b702  mov     ebx, eax
0x18005b704  test    eax, eax
0x18005b706  jns     short loc_18005B73C
0x18005b708  mov     rcx, [rbp+18h]; this
0x18005b70c  lea     r8, aShellCplsUserc; "shell\\cpls\\usercpl\\taskflows\\plugin"...
0x18005b713  mov     r9d, eax; char *
0x18005b716  mov     edx, 0A3h; void *
0x18005b71b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005b720  mov     rcx, [rbp+arg_0]
0x18005b724  test    rcx, rcx
0x18005b727  jz      short loc_18005B735
0x18005b729  mov     rdx, [rcx]
0x18005b72c  mov     rax, [rdx+10h]
0x18005b730  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b735  mov     eax, ebx
0x18005b737  jmp     loc_18005B9EA
0x18005b73c  mov     rdx, [rbp+arg_0]; struct IUserData *
0x18005b740  lea     r8, [rbp+arg_10]; struct IConnectedUser **
0x18005b744  mov     [rbp+arg_10], 0
0x18005b74c  call    ?GetCurrentConnectedUser@CLocalDisconnectPlugin@@AEAAJPEAUIUserData@@PEAPEAUIConnectedUser@@@Z; CLocalDisconnectPlugin::GetCurrentConnectedUser(IUserData *,IConnectedUser * *)
0x18005b751  mov     ebx, eax
0x18005b753  cmp     eax, 0D0000225h
0x18005b758  jz      loc_18005B91B
0x18005b75e  cmp     eax, 0D0000064h
0x18005b763  jz      loc_18005B91B
0x18005b769  test    eax, eax
0x18005b76b  jns     short loc_18005B777
0x18005b76d  mov     edx, 0B0h
0x18005b772  jmp     loc_18005B97D
0x18005b777  mov     rdx, [rbp+arg_10]; struct IConnectedUser *
0x18005b77b  lea     r9, [rbp+pv]; unsigned __int16 **
0x18005b77f  lea     r8, [rbp+lpszUsername]; unsigned __int16 **
0x18005b783  mov     [rbp+pv], 0
0x18005b78b  mov     [rbp+lpszUsername], 0
0x18005b793  mov     qword ptr [rsp+40h+dwLogonProvider], 0; int
0x18005b79c  call    ?GetConnectedUserProperties@CLocalDisconnectPlugin@@AEAAJPEAUIConnectedUser@@PEAPEAG1PEAU_GUID@@@Z; CLocalDisconnectPlugin::GetConnectedUserProperties(IConnectedUser *,ushort * *,ushort * *,_GUID *)
0x18005b7a1  mov     ebx, eax
0x18005b7a3  test    eax, eax
0x18005b7a5  jns     short loc_18005B7E6
0x18005b7a7  mov     rcx, [rbp+18h]; this
0x18005b7ab  lea     r8, aShellCplsUserc; "shell\\cpls\\usercpl\\taskflows\\plugin"...
0x18005b7b2  mov     r9d, eax; char *
0x18005b7b5  mov     edx, 0B4h; void *
0x18005b7ba  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005b7bf  mov     rcx, [rbp+pv]; pv
0x18005b7c3  test    rcx, rcx
0x18005b7c6  jz      short loc_18005B7CE
0x18005b7c8  call    cs:__imp_CoTaskMemFree
0x18005b7ce  mov     rcx, [rbp+lpszUsername]; pv
0x18005b7d2  test    rcx, rcx
0x18005b7d5  jz      loc_18005B990
0x18005b7db  call    cs:__imp_CoTaskMemFree
0x18005b7e1  jmp     loc_18005B990
0x18005b7e6  mov     rbx, [rbp+lpszUsername]
0x18005b7ea  lea     rax, [rbp+hObject]
0x18005b7ee  mov     rdx, [rbp+pv]; lpszDomain
0x18005b7f2  mov     rcx, rbx; lpszUsername
0x18005b7f5  mov     [rsp+40h+phToken], rax; phToken
0x18005b7fa  mov     r9d, 2; dwLogonType
0x18005b800  mov     r8, rsi; lpszPassword
0x18005b803  mov     [rsp+40h+dwLogonProvider], 0; int
0x18005b80b  mov     [rbp+hObject], 0
0x18005b813  call    cs:__imp_LogonUserW
0x18005b819  test    eax, eax
0x18005b81b  jnz     short loc_18005B898
0x18005b81d  mov     rcx, [rbp+18h]; this
0x18005b821  lea     r8, aShellCplsUserc; "shell\\cpls\\usercpl\\taskflows\\plugin"...
0x18005b828  mov     edx, 0BCh; void *
0x18005b82d  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18005b832  mov     rcx, [rbp+hObject]; hObject
0x18005b836  mov     esi, eax
0x18005b838  lea     rdx, [rcx-1]
0x18005b83c  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18005b840  ja      short loc_18005B848
0x18005b842  call    cs:__imp_CloseHandle
0x18005b848  cmp     [rbp+pv], 0
0x18005b84d  jz      short loc_18005B859
0x18005b84f  mov     rcx, [rbp+pv]; pv
0x18005b853  call    cs:__imp_CoTaskMemFree
0x18005b859  test    rbx, rbx
0x18005b85c  jz      short loc_18005B867
0x18005b85e  mov     rcx, rbx; pv
0x18005b861  call    cs:__imp_CoTaskMemFree
0x18005b867  mov     rcx, [rbp+arg_10]
0x18005b86b  test    rcx, rcx
0x18005b86e  jz      short loc_18005B87C
0x18005b870  mov     rax, [rcx]
0x18005b873  mov     rax, [rax+10h]
0x18005b877  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b87c  mov     rcx, [rbp+arg_0]
0x18005b880  test    rcx, rcx
0x18005b883  jz      short loc_18005B891
0x18005b885  mov     rax, [rcx]
0x18005b888  mov     rax, [rax+10h]
0x18005b88c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b891  mov     eax, esi
0x18005b893  jmp     loc_18005B9EA
0x18005b898  mov     rcx, [rbp+hObject]; hObject
0x18005b89c  lea     rax, [rcx-1]
0x18005b8a0  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18005b8a4  ja      short loc_18005B8AC
0x18005b8a6  call    cs:__imp_CloseHandle
0x18005b8ac  cmp     [rbp+pv], 0
0x18005b8b1  jz      short loc_18005B8BD
0x18005b8b3  mov     rcx, [rbp+pv]; pv
0x18005b8b7  call    cs:__imp_CoTaskMemFree
0x18005b8bd  test    rbx, rbx
0x18005b8c0  jz      short loc_18005B8CB
0x18005b8c2  mov     rcx, rbx; pv
0x18005b8c5  call    cs:__imp_CoTaskMemFree
0x18005b8cb  mov     rcx, [r14+68h]; unsigned __int16 *
0x18005b8cf  call    ?ClearAndFreeSecretString@@YAXPEAG@Z; ClearAndFreeSecretString(ushort *)
0x18005b8d4  lea     rdx, [r14+68h]; unsigned __int16 **
0x18005b8d8  mov     rcx, rsi; unsigned __int16 *
0x18005b8db  call    ?CoAllocString@@YAJPEBGPEAPEAG@Z; CoAllocString(ushort const *,ushort * *)
0x18005b8e0  mov     ebx, eax
0x18005b8e2  test    eax, eax
0x18005b8e4  jns     loc_18005B9BE
0x18005b8ea  mov     rcx, [rbp+18h]; this
0x18005b8ee  lea     r8, aShellCplsUserc; "shell\\cpls\\usercpl\\taskflows\\plugin"...
0x18005b8f5  mov     r9d, eax; char *
0x18005b8f8  mov     edx, 0C0h; void *
0x18005b8fd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005b902  mov     rcx, [rbp+arg_10]
0x18005b906  test    rcx, rcx
0x18005b909  jz      loc_18005B9A5
0x18005b90f  mov     rdx, [rcx]
0x18005b912  mov     rax, [rdx+10h]
0x18005b916  jmp     loc_18005B9A0
0x18005b91b  mov     rcx, [rbp+arg_0]
0x18005b91f  mov     rdx, rsi
0x18005b922  mov     rax, [rcx]
0x18005b925  mov     rax, [rax+28h]
0x18005b929  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b92e  mov     ebx, eax
0x18005b930  cmp     eax, 1
0x18005b933  jnz     short loc_18005B970
0x18005b935  mov     rcx, [rbp+18h]; this
0x18005b939  lea     r8, aShellCplsUserc; "shell\\cpls\\usercpl\\taskflows\\plugin"...
0x18005b940  mov     ebx, 80070056h
0x18005b945  mov     edx, 0ABh; void *
0x18005b94a  mov     r9d, ebx; char *
0x18005b94d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005b952  mov     rcx, [rbp+arg_10]
0x18005b956  test    rcx, rcx
0x18005b959  jz      loc_18005B720
0x18005b95f  mov     rax, [rcx]
0x18005b962  mov     rax, [rax+10h]
0x18005b966  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b96b  jmp     loc_18005B720
0x18005b970  test    ebx, ebx
0x18005b972  jns     loc_18005B8CB
0x18005b978  mov     edx, 0ACh; void *
0x18005b97d  mov     rcx, [rbp+18h]; this
0x18005b981  lea     r8, aShellCplsUserc; "shell\\cpls\\usercpl\\taskflows\\plugin"...
0x18005b988  mov     r9d, ebx; char *
0x18005b98b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005b990  mov     rcx, [rbp+arg_10]
0x18005b994  test    rcx, rcx
0x18005b997  jz      short loc_18005B9A5
0x18005b999  mov     rax, [rcx]
0x18005b99c  mov     rax, [rax+10h]
0x18005b9a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b9a5  mov     rcx, [rbp+arg_0]
0x18005b9a9  test    rcx, rcx
0x18005b9ac  jz      loc_18005B735
0x18005b9b2  mov     rax, [rcx]
0x18005b9b5  mov     rax, [rax+10h]
0x18005b9b9  jmp     loc_18005B730
0x18005b9be  mov     rcx, [rbp+arg_10]
0x18005b9c2  test    rcx, rcx
0x18005b9c5  jz      short loc_18005B9D3
0x18005b9c7  mov     rax, [rcx]
0x18005b9ca  mov     rax, [rax+10h]
0x18005b9ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b9d3  mov     rcx, [rbp+arg_0]
0x18005b9d7  test    rcx, rcx
0x18005b9da  jz      short loc_18005B9E8
0x18005b9dc  mov     rax, [rcx]
0x18005b9df  mov     rax, [rax+10h]
0x18005b9e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b9e8  xor     eax, eax
0x18005b9ea  mov     rbx, [rsp+40h+arg_8]
0x18005b9ef  add     rsp, 40h
0x18005b9f3  pop     r14
0x18005b9f5  pop     rsi
0x18005b9f6  pop     rbp
0x18005b9f7  retn
```
