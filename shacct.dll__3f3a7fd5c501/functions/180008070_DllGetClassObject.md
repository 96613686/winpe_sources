# DllGetClassObject

- ea: `0x180008070`
- end: `0x180008224`
- name: `DllGetClassObject`
- size: `436`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180008070`
- `0x18000be0c`
- `0x18000d80c`
- `0x180017010`

## pseudocode

```c
HRESULT __stdcall DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  __int64 v5; // rax
  int (*v6)(const struct _GUID *, void **); // rdi
  __int64 v7; // rax
  __int64 v8; // rax
  __int64 v10; // rax
  __int64 v11; // rax
  __int64 v12; // rax
  __int64 v13; // rax
  CClassFactory *v14; // rax
  CClassFactory *v15; // rax
  CClassFactory *v16; // rdi
  HRESULT v17; // ebx

  *ppv = 0;
  v5 = *(_QWORD *)&rclsid->Data1 - *(_QWORD *)&CLSID_LocalUserAccounts.Data1;
  if ( *(_QWORD *)&rclsid->Data1 == *(_QWORD *)&CLSID_LocalUserAccounts.Data1 )
    v5 = *(_QWORD *)rclsid->Data4 - *(_QWORD *)CLSID_LocalUserAccounts.Data4;
  if ( v5 )
  {
    v7 = *(_QWORD *)&rclsid->Data1 - *(_QWORD *)&CLSID_LocalGroups.Data1;
    if ( *(_QWORD *)&rclsid->Data1 == *(_QWORD *)&CLSID_LocalGroups.Data1 )
      v7 = *(_QWORD *)rclsid->Data4 - *(_QWORD *)CLSID_LocalGroups.Data4;
    if ( v7 )
    {
      v8 = *(_QWORD *)&rclsid->Data1 - *(_QWORD *)&CLSID_ProfileNotificationHandler.Data1;
      if ( *(_QWORD *)&rclsid->Data1 == *(_QWORD *)&CLSID_ProfileNotificationHandler.Data1 )
        v8 = *(_QWORD *)rclsid->Data4 - *(_QWORD *)CLSID_ProfileNotificationHandler.Data4;
      if ( !v8 )
        return -2147467259;
      v10 = *(_QWORD *)&rclsid->Data1 - *(_QWORD *)&CLSID_LoggedOnAccounts.Data1;
      if ( *(_QWORD *)&rclsid->Data1 == *(_QWORD *)&CLSID_LoggedOnAccounts.Data1 )
        v10 = *(_QWORD *)rclsid->Data4 - *(_QWORD *)CLSID_LoggedOnAccounts.Data4;
      if ( v10 )
      {
        v11 = *(_QWORD *)&rclsid->Data1 - *(_QWORD *)&CLSID_ProfileAccounts.Data1;
        if ( *(_QWORD *)&rclsid->Data1 == *(_QWORD *)&CLSID_ProfileAccounts.Data1 )
          v11 = *(_QWORD *)rclsid->Data4 - *(_QWORD *)CLSID_ProfileAccounts.Data4;
        if ( v11 )
        {
          v12 = *(_QWORD *)&rclsid->Data1 - *(_QWORD *)&CLSID_ConnectedAccounts.Data1;
          if ( *(_QWORD *)&rclsid->Data1 == *(_QWORD *)&CLSID_ConnectedAccounts.Data1 )
            v12 = *(_QWORD *)rclsid->Data4 - *(_QWORD *)CLSID_ConnectedAccounts.Data4;
          if ( v12 )
          {
            v13 = *(_QWORD *)&rclsid->Data1 - *(_QWORD *)&CLSID_UserAccounts.Data1;
            if ( *(_QWORD *)&rclsid->Data1 == *(_QWORD *)&CLSID_UserAccounts.Data1 )
              v13 = *(_QWORD *)rclsid->Data4 - *(_QWORD *)CLSID_UserAccounts.Data4;
            if ( v13 )
              return -2147221231;
            v6 = (int (*)(const struct _GUID *, void **))CUserAccounts_CreateInstance;
          }
          else
          {
            v6 = (int (*)(const struct _GUID *, void **))CConnectedAccounts_CreateInstance;
          }
        }
        else
        {
          v6 = (int (*)(const struct _GUID *, void **))CProfileAccounts_CreateInstance;
        }
      }
      else
      {
        v6 = (int (*)(const struct _GUID *, void **))CLoggedOnAccounts_CreateInstance;
      }
    }
    else
    {
      v6 = (int (*)(const struct _GUID *, void **))CLocalGroups_CreateInstance;
    }
  }
  else
  {
    v6 = (int (*)(const struct _GUID *, void **))CLocalUsers_CreateInstance;
  }
  v14 = (CClassFactory *)operator new(0x18u);
  if ( !v14 )
    return -2147024882;
  v15 = CClassFactory::CClassFactory(v14, v6);
  v16 = v15;
  if ( !v15 )
    return -2147024882;
  v17 = (**(__int64 (__fastcall ***)(CClassFactory *, const IID *const, LPVOID *))v15)(v15, riid, ppv);
  (*(void (__fastcall **)(CClassFactory *))(*(_QWORD *)v16 + 16LL))(v16);
  return v17;
}

```

## disassembly

```asm
0x180008070  mov     [rsp+arg_8], rbx
0x180008075  push    rsi
0x180008076  sub     rsp, 20h
0x18000807a  mov     qword ptr [r8], 0
0x180008081  mov     rbx, r8
0x180008084  mov     rax, [rcx]
0x180008087  mov     rsi, rdx
0x18000808a  sub     rax, qword ptr cs:CLSID_LocalUserAccounts.Data1
0x180008091  jnz     short loc_18000809E
0x180008093  mov     rax, [rcx+8]
0x180008097  sub     rax, qword ptr cs:CLSID_LocalUserAccounts.Data4
0x18000809e  mov     [rsp+28h+arg_0], rdi
0x1800080a3  test    rax, rax
0x1800080a6  jnz     short loc_1800080B4
0x1800080a8  lea     rdi, ?CLocalUsers_CreateInstance@@YAJAEBU_GUID@@PEAPEAX@Z; CLocalUsers_CreateInstance(_GUID const &,void * *)
0x1800080af  jmp     loc_18000819F
0x1800080b4  mov     rax, [rcx]
0x1800080b7  sub     rax, qword ptr cs:CLSID_LocalGroups.Data1
0x1800080be  jnz     short loc_1800080CB
0x1800080c0  mov     rax, [rcx+8]
0x1800080c4  sub     rax, qword ptr cs:CLSID_LocalGroups.Data4
0x1800080cb  test    rax, rax
0x1800080ce  jnz     short loc_1800080DC
0x1800080d0  lea     rdi, ?CLocalGroups_CreateInstance@@YAJAEBU_GUID@@PEAPEAX@Z; CLocalGroups_CreateInstance(_GUID const &,void * *)
0x1800080d7  jmp     loc_18000819F
0x1800080dc  mov     rax, [rcx]
0x1800080df  sub     rax, qword ptr cs:CLSID_ProfileNotificationHandler.Data1
0x1800080e6  jnz     short loc_1800080F3
0x1800080e8  mov     rax, [rcx+8]
0x1800080ec  sub     rax, qword ptr cs:CLSID_ProfileNotificationHandler.Data4
0x1800080f3  test    rax, rax
0x1800080f6  jnz     short loc_18000810D
0x1800080f8  mov     eax, 80004005h
0x1800080fd  mov     rdi, [rsp+28h+arg_0]
0x180008102  mov     rbx, [rsp+28h+arg_8]
0x180008107  add     rsp, 20h
0x18000810b  pop     rsi
0x18000810c  retn
0x18000810d  mov     rax, [rcx]
0x180008110  sub     rax, qword ptr cs:CLSID_LoggedOnAccounts.Data1
0x180008117  jnz     short loc_180008124
0x180008119  mov     rax, [rcx+8]
0x18000811d  sub     rax, qword ptr cs:CLSID_LoggedOnAccounts.Data4
0x180008124  test    rax, rax
0x180008127  jnz     short loc_180008132
0x180008129  lea     rdi, ?CLoggedOnAccounts_CreateInstance@@YAJAEBU_GUID@@PEAPEAX@Z; CLoggedOnAccounts_CreateInstance(_GUID const &,void * *)
0x180008130  jmp     short loc_18000819F
0x180008132  mov     rax, [rcx]
0x180008135  sub     rax, qword ptr cs:CLSID_ProfileAccounts.Data1
0x18000813c  jnz     short loc_180008149
0x18000813e  mov     rax, [rcx+8]
0x180008142  sub     rax, qword ptr cs:CLSID_ProfileAccounts.Data4
0x180008149  test    rax, rax
0x18000814c  jnz     short loc_180008157
0x18000814e  lea     rdi, ?CProfileAccounts_CreateInstance@@YAJAEBU_GUID@@PEAPEAX@Z; CProfileAccounts_CreateInstance(_GUID const &,void * *)
0x180008155  jmp     short loc_18000819F
0x180008157  mov     rax, [rcx]
0x18000815a  sub     rax, qword ptr cs:CLSID_ConnectedAccounts.Data1
0x180008161  jnz     short loc_18000816E
0x180008163  mov     rax, [rcx+8]
0x180008167  sub     rax, qword ptr cs:CLSID_ConnectedAccounts.Data4
0x18000816e  test    rax, rax
0x180008171  jnz     short loc_18000817C
0x180008173  lea     rdi, ?CConnectedAccounts_CreateInstance@@YAJAEBU_GUID@@PEAPEAX@Z; CConnectedAccounts_CreateInstance(_GUID const &,void * *)
0x18000817a  jmp     short loc_18000819F
0x18000817c  mov     rax, [rcx]
0x18000817f  sub     rax, qword ptr cs:CLSID_UserAccounts.Data1
0x180008186  jnz     short loc_180008193
0x180008188  mov     rax, [rcx+8]
0x18000818c  sub     rax, qword ptr cs:CLSID_UserAccounts.Data4
0x180008193  test    rax, rax
0x180008196  jnz     short loc_18000820F
0x180008198  lea     rdi, ?CUserAccounts_CreateInstance@@YAJAEBU_GUID@@PEAPEAX@Z; CUserAccounts_CreateInstance(_GUID const &,void * *)
0x18000819f  mov     ecx, 18h; Size
0x1800081a4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800081a9  test    rax, rax
0x1800081ac  jz      short loc_1800081F8
0x1800081ae  mov     rdx, rdi; int (*)(const struct _GUID *, void **)
0x1800081b1  mov     rcx, rax; this
0x1800081b4  call    ??0CClassFactory@@QEAA@P6AJAEBU_GUID@@PEAPEAX@Z@Z; CClassFactory::CClassFactory(long (*)(_GUID const &,void * *))
0x1800081b9  mov     rdi, rax
0x1800081bc  test    rax, rax
0x1800081bf  jz      short loc_1800081F8
0x1800081c1  mov     rcx, [rax]
0x1800081c4  mov     r8, rbx
0x1800081c7  mov     rdx, rsi
0x1800081ca  mov     rax, [rcx]
0x1800081cd  mov     rcx, rdi
0x1800081d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800081d5  mov     rcx, [rdi]
0x1800081d8  mov     ebx, eax
0x1800081da  mov     rax, [rcx+10h]
0x1800081de  mov     rcx, rdi
0x1800081e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800081e6  mov     eax, ebx
0x1800081e8  mov     rdi, [rsp+28h+arg_0]
0x1800081ed  mov     rbx, [rsp+28h+arg_8]
0x1800081f2  add     rsp, 20h
0x1800081f6  pop     rsi
0x1800081f7  retn
0x1800081f8  mov     ebx, 8007000Eh
0x1800081fd  mov     eax, ebx
0x1800081ff  mov     rdi, [rsp+28h+arg_0]
0x180008204  mov     rbx, [rsp+28h+arg_8]
0x180008209  add     rsp, 20h
0x18000820d  pop     rsi
0x18000820e  retn
0x18000820f  mov     rdi, [rsp+28h+arg_0]
0x180008214  mov     eax, 80040111h
0x180008219  mov     rbx, [rsp+28h+arg_8]
0x18000821e  add     rsp, 20h
0x180008222  pop     rsi
0x180008223  retn
```
