# DllRegisterServer

- ea: `0x18001c580`
- end: `0x18001c681`
- name: `DllRegisterServer`
- size: `257`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180001ec0`
- `0x180006000`
- `0x18001b21c`
- `0x18001b334`
- `0x18001c014`
- `0x18001c580`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!SetThreadLocale` at `0x18001c634`
- `api-ms-win-core-localization-l1-2-0!SetThreadLocale` at `0x18001c643`
- `api-ms-win-core-localization-l1-2-0!SetThreadLocale` at `0x18001c634`
- `api-ms-win-core-localization-l1-2-0!SetThreadLocale` at `0x18001c643`
- `api-ms-win-core-localization-l1-2-0!GetThreadLocale` at `0x18001c627`
- `api-ms-win-core-localization-l1-2-0!GetThreadLocale` at `0x18001c627`
- `RPCRT4!NdrDllRegisterProxy` at `0x18001c618`
- `RPCRT4!NdrDllRegisterProxy` at `0x18001c618`

## string_xrefs

- `0x18001c5ab`: `DllRegisterServer`

## pseudocode

```c
HRESULT __stdcall DllRegisterServer()
{
  const CLSID *v0; // r8
  HRESULT v1; // edi
  LCID ThreadLocale; // ebx
  __int64 v3; // rdx
  __int64 v4; // rcx
  HRESULT v6; // [rsp+20h] [rbp-50h] BYREF
  int v7; // [rsp+24h] [rbp-4Ch] BYREF
  _QWORD *v8; // [rsp+28h] [rbp-48h] BYREF
  _QWORD v9[3]; // [rsp+30h] [rbp-40h] BYREF
  char v10[24]; // [rsp+48h] [rbp-28h] BYREF

  v9[0] = v10;
  v9[1] = &v7;
  v9[2] = &v6;
  v6 = 0;
  v7 = 0;
  strcpy(v10, "DllRegisterServer");
  lambda_3cbfc9904d78242d0848ebb0f730d72e_::operator()(v9);
  v7 = 1;
  v8 = v9;
  v0 = (const CLSID *)*aProxyFileList->pStubVtblList;
  if ( v0 )
    v0 = *(const CLSID **)&v0->Data1;
  v6 = NdrDllRegisterProxy(hProxyDll, (const ProxyFileInfo **)&aProxyFileList, v0);
  v1 = v6;
  if ( v6 >= 0 )
  {
    ThreadLocale = GetThreadLocale();
    SetThreadLocale(0x800u);
    v1 = ATL::CAtlModuleT<TpmVCardManagerModule>::RegisterServer(v4, v3);
    SetThreadLocale(ThreadLocale);
    v6 = v1;
    if ( v1 < 0 )
    {
      PrxDllUnregisterServer();
      v1 = v6;
    }
  }
  WppTraceUnwinder__lambda_3cbfc9904d78242d0848ebb0f730d72e____::_WppTraceUnwinder__lambda_3cbfc9904d78242d0848ebb0f730d72e____(&v8);
  return v1;
}

```

## disassembly

```asm
0x18001c580  mov     [rsp-8+arg_0], rbx
0x18001c585  mov     [rsp-8+arg_8], rdi
0x18001c58a  push    rbp
0x18001c58b  mov     rbp, rsp
0x18001c58e  sub     rsp, 70h
0x18001c592  mov     rax, cs:__security_cookie
0x18001c599  xor     rax, rsp
0x18001c59c  mov     [rbp+var_10], rax
0x18001c5a0  movzx   eax, word ptr cs:aDllregisterser_0+10h; "r"
0x18001c5a7  lea     rcx, [rbp+var_40]
0x18001c5ab  movups  xmm0, xmmword ptr cs:aDllregisterser_0; "DllRegisterServer"
0x18001c5b2  mov     word ptr [rbp+var_28+10h], ax
0x18001c5b6  lea     rax, [rbp+var_28]
0x18001c5ba  mov     [rbp+var_40], rax
0x18001c5be  lea     rax, [rbp+var_4C]
0x18001c5c2  mov     [rbp+var_38], rax
0x18001c5c6  lea     rax, [rbp+var_50]
0x18001c5ca  mov     [rbp+var_30], rax
0x18001c5ce  mov     [rbp+var_50], 0
0x18001c5d5  mov     [rbp+var_4C], 0
0x18001c5dc  movups  xmmword ptr [rbp+var_28], xmm0
0x18001c5e0  call    _lambda_3cbfc9904d78242d0848ebb0f730d72e___operator__
0x18001c5e5  lea     rax, [rbp+var_40]
0x18001c5e9  mov     [rbp+var_4C], 1
0x18001c5f0  mov     [rbp+var_48], rax
0x18001c5f4  mov     rax, cs:aProxyFileList
0x18001c5fb  mov     rcx, [rax+8]
0x18001c5ff  mov     r8, [rcx]
0x18001c602  test    r8, r8
0x18001c605  jz      short loc_18001C60A
0x18001c607  mov     r8, [r8]; pclsid
0x18001c60a  mov     rcx, cs:hProxyDll; hDll
0x18001c611  lea     rdx, aProxyFileList; pProxyFileList
0x18001c618  call    cs:__imp_NdrDllRegisterProxy
0x18001c61e  mov     [rbp+var_50], eax
0x18001c621  mov     edi, eax
0x18001c623  test    eax, eax
0x18001c625  js      short loc_18001C658
0x18001c627  call    cs:__imp_GetThreadLocale
0x18001c62d  mov     ecx, 800h; Locale
0x18001c632  mov     ebx, eax
0x18001c634  call    cs:__imp_SetThreadLocale
0x18001c63a  call    ?RegisterServer@?$CAtlModuleT@VTpmVCardManagerModule@@@ATL@@QEAAJHPEBU_GUID@@@Z; ATL::CAtlModuleT<TpmVCardManagerModule>::RegisterServer(int,_GUID const *)
0x18001c63f  mov     ecx, ebx; Locale
0x18001c641  mov     edi, eax
0x18001c643  call    cs:__imp_SetThreadLocale
0x18001c649  mov     [rbp+var_50], edi
0x18001c64c  test    edi, edi
0x18001c64e  jns     short loc_18001C658
0x18001c650  call    PrxDllUnregisterServer
0x18001c655  mov     edi, [rbp+var_50]
0x18001c658  lea     rcx, [rbp+var_48]
0x18001c65c  call    WppTraceUnwinder__lambda_3cbfc9904d78242d0848ebb0f730d72e_______WppTraceUnwinder__lambda_3cbfc9904d78242d0848ebb0f730d72e____
0x18001c661  mov     eax, edi
0x18001c663  mov     rcx, [rbp+var_10]
0x18001c667  xor     rcx, rsp; StackCookie
0x18001c66a  call    __security_check_cookie
0x18001c66f  lea     r11, [rsp+70h+var_s0]
0x18001c674  mov     rbx, [r11+10h]
0x18001c678  mov     rdi, [r11+18h]
0x18001c67c  mov     rsp, r11
0x18001c67f  pop     rbp
0x18001c680  retn
```
