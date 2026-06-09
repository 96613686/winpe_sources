# _GetURLTarget(ushort const *,ushort *,uint)

- ea: `0x180009330`
- end: `0x180009492`
- name: `?_GetURLTarget@@YAJPEBGPEAGI@Z`
- size: `354`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180008ea0`

## callees

- `0x180008de4`
- `0x180009330`
- `0x180029280`
- `0x18002a010`

## import_xrefs

- `SHLWAPI!PathFindExtensionW` at `0x180009362`
- `SHLWAPI!PathFindExtensionW` at `0x180009362`
- `ole32!CoCreateInstance` at `0x18000939e`
- `ole32!CoCreateInstance` at `0x18000939e`

## pseudocode

```c
__int64 __fastcall _GetURLTarget(const unsigned __int16 *a1, unsigned __int16 *a2)
{
  const WCHAR *ExtensionW; // rax
  HRESULT v5; // ebx
  LPVOID ppv; // [rsp+30h] [rbp-30h] BYREF
  __int64 v8; // [rsp+38h] [rbp-28h] BYREF
  __int64 v9; // [rsp+40h] [rbp-20h] BYREF
  IID rclsid; // [rsp+48h] [rbp-18h] BYREF

  ppv = 0;
  rclsid = 0;
  ExtensionW = PathFindExtensionW(a1);
  if ( (int)_CLSIDFromExtension(ExtensionW, &rclsid) < 0 )
    rclsid = CLSID_ShellLink;
  v5 = CoCreateInstance(&rclsid, 0, 1u, &IID_IShellLinkW, &ppv);
  if ( v5 >= 0 )
  {
    v8 = 0;
    v5 = (**(__int64 (__fastcall ***)(LPVOID, GUID *, __int64 *))ppv)(ppv, &IID_IPersistFile, &v8);
    if ( v5 >= 0 )
    {
      v5 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, _QWORD))(*(_QWORD *)v8 + 40LL))(v8, a1, 0);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
      if ( v5 >= 0 )
      {
        v9 = 0;
        v5 = (**(__int64 (__fastcall ***)(LPVOID, GUID *, __int64 *))ppv)(ppv, &IID_IUniformResourceLocatorW, &v9);
        if ( v5 >= 0 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
          v5 = (*(__int64 (__fastcall **)(LPVOID, unsigned __int16 *, __int64, _QWORD, int))(*(_QWORD *)ppv + 24LL))(
                 ppv,
                 a2,
                 2084,
                 0,
                 2);
        }
      }
    }
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180009330  mov     [rsp-18h+arg_10], rbx
0x180009335  push    rbp
0x180009336  push    rsi
0x180009337  push    rdi
0x180009338  mov     rbp, rsp
0x18000933b  sub     rsp, 60h
0x18000933f  mov     rax, cs:__security_cookie
0x180009346  xor     rax, rsp
0x180009349  mov     [rbp+var_8], rax
0x18000934d  xorps   xmm0, xmm0
0x180009350  mov     [rbp+var_30], 0
0x180009358  movups  xmmword ptr [rbp+rclsid.Data1], xmm0
0x18000935c  mov     rsi, rdx
0x18000935f  mov     rdi, rcx
0x180009362  call    cs:__imp_PathFindExtensionW
0x180009368  mov     rcx, rax; lpSubKey
0x18000936b  lea     rdx, [rbp+rclsid]; pclsid
0x18000936f  call    ?_CLSIDFromExtension@@YAJPEBGPEAU_GUID@@@Z; _CLSIDFromExtension(ushort const *,_GUID *)
0x180009374  test    eax, eax
0x180009376  jns     short loc_180009384
0x180009378  movups  xmm0, xmmword ptr cs:CLSID_ShellLink.Data1
0x18000937f  movdqu  xmmword ptr [rbp+rclsid.Data1], xmm0
0x180009384  xor     edx, edx; pUnkOuter
0x180009386  lea     rax, [rbp+var_30]
0x18000938a  lea     r9, IID_IShellLinkW; riid
0x180009391  mov     [rsp+60h+ppv], rax; ppv
0x180009396  lea     rcx, [rbp+rclsid]; rclsid
0x18000939a  lea     r8d, [rdx+1]; dwClsContext
0x18000939e  call    cs:__imp_CoCreateInstance
0x1800093a4  mov     ebx, eax
0x1800093a6  test    eax, eax
0x1800093a8  js      loc_180009474
0x1800093ae  mov     rcx, [rbp+var_30]
0x1800093b2  lea     r8, [rbp+var_28]
0x1800093b6  mov     [rbp+var_28], 0
0x1800093be  lea     rdx, IID_IPersistFile
0x1800093c5  mov     rax, [rcx]
0x1800093c8  mov     rax, [rax]
0x1800093cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800093d0  mov     ebx, eax
0x1800093d2  test    eax, eax
0x1800093d4  js      loc_180009464
0x1800093da  mov     rcx, [rbp+var_28]
0x1800093de  xor     r8d, r8d
0x1800093e1  mov     rdx, rdi
0x1800093e4  mov     rax, [rcx]
0x1800093e7  mov     rax, [rax+28h]
0x1800093eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800093f0  mov     rcx, [rbp+var_28]
0x1800093f4  mov     ebx, eax
0x1800093f6  mov     rax, [rcx]
0x1800093f9  mov     rax, [rax+10h]
0x1800093fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009402  test    ebx, ebx
0x180009404  js      short loc_180009464
0x180009406  mov     rcx, [rbp+var_30]
0x18000940a  lea     r8, [rbp+var_20]
0x18000940e  mov     [rbp+var_20], 0
0x180009416  lea     rdx, IID_IUniformResourceLocatorW
0x18000941d  mov     rax, [rcx]
0x180009420  mov     rax, [rax]
0x180009423  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009428  mov     ebx, eax
0x18000942a  test    eax, eax
0x18000942c  js      short loc_180009464
0x18000942e  mov     rcx, [rbp+var_20]
0x180009432  mov     rax, [rcx]
0x180009435  mov     rax, [rax+10h]
0x180009439  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000943e  mov     rcx, [rbp+var_30]
0x180009442  xor     r9d, r9d
0x180009445  mov     r8d, 824h
0x18000944b  mov     dword ptr [rsp+60h+ppv], 2
0x180009453  mov     rdx, rsi
0x180009456  mov     rax, [rcx]
0x180009459  mov     rax, [rax+18h]
0x18000945d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009462  mov     ebx, eax
0x180009464  mov     rcx, [rbp+var_30]
0x180009468  mov     rax, [rcx]
0x18000946b  mov     rax, [rax+10h]
0x18000946f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009474  mov     eax, ebx
0x180009476  mov     rcx, [rbp+var_8]
0x18000947a  xor     rcx, rsp; StackCookie
0x18000947d  call    __security_check_cookie
0x180009482  mov     rbx, [rsp+60h+arg_10]
0x18000948a  add     rsp, 60h
0x18000948e  pop     rdi
0x18000948f  pop     rsi
0x180009490  pop     rbp
0x180009491  retn
```
