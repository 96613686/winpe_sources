# DllUnregisterServer

- ea: `0x18001c690`
- end: `0x18001c763`
- name: `DllUnregisterServer`
- size: `211`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting`

## callees

- `0x180001ec0`
- `0x180006000`
- `0x18001b1e4`
- `0x18001b254`
- `0x18001c194`
- `0x18001c690`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!SetThreadLocale` at `0x18001c717`
- `api-ms-win-core-localization-l1-2-0!SetThreadLocale` at `0x18001c72b`
- `api-ms-win-core-localization-l1-2-0!SetThreadLocale` at `0x18001c717`
- `api-ms-win-core-localization-l1-2-0!SetThreadLocale` at `0x18001c72b`
- `api-ms-win-core-localization-l1-2-0!GetThreadLocale` at `0x18001c70a`
- `api-ms-win-core-localization-l1-2-0!GetThreadLocale` at `0x18001c70a`

## string_xrefs

- `0x18001c6ba`: `DllUnregisterServer`

## pseudocode

```c
HRESULT __stdcall DllUnregisterServer()
{
  LCID ThreadLocale; // ebx
  int v1; // eax
  HRESULT v2; // edi
  HRESULT v3; // ebx
  int v5; // [rsp+20h] [rbp-50h] BYREF
  int v6; // [rsp+24h] [rbp-4Ch] BYREF
  _QWORD *v7; // [rsp+28h] [rbp-48h] BYREF
  _QWORD v8[3]; // [rsp+30h] [rbp-40h] BYREF
  char v9[24]; // [rsp+48h] [rbp-28h] BYREF

  v8[0] = v9;
  v8[1] = &v6;
  v8[2] = &v5;
  v5 = 0;
  v6 = 0;
  strcpy(v9, "DllUnregisterServer");
  lambda_16004c6c3d04f347f7b40a85144c46e9_::operator()(v8);
  v6 = 1;
  v7 = v8;
  v5 = PrxDllUnregisterServer();
  ThreadLocale = GetThreadLocale();
  SetThreadLocale(0x800u);
  v1 = ATL::CAtlModuleT<TpmVCardManagerModule>::UnregisterServer();
  v2 = 0;
  if ( v1 < 0 )
    v2 = v1;
  SetThreadLocale(ThreadLocale);
  v3 = v5;
  if ( v5 >= 0 )
    v3 = v2;
  WppTraceUnwinder__lambda_16004c6c3d04f347f7b40a85144c46e9____::_WppTraceUnwinder__lambda_16004c6c3d04f347f7b40a85144c46e9____(&v7);
  return v3;
}

```

## disassembly

```asm
0x18001c690  mov     [rsp-8+arg_0], rbx
0x18001c695  mov     [rsp-8+arg_8], rdi
0x18001c69a  push    rbp
0x18001c69b  mov     rbp, rsp
0x18001c69e  sub     rsp, 70h
0x18001c6a2  mov     rax, cs:__security_cookie
0x18001c6a9  xor     rax, rsp
0x18001c6ac  mov     [rbp+var_10], rax
0x18001c6b0  mov     eax, dword ptr cs:aDllunregisters_0+10h; "ver"
0x18001c6b6  lea     rcx, [rbp+var_40]
0x18001c6ba  movups  xmm0, xmmword ptr cs:aDllunregisters_0; "DllUnregisterServer"
0x18001c6c1  mov     dword ptr [rbp+var_28+10h], eax
0x18001c6c4  lea     rax, [rbp+var_28]
0x18001c6c8  mov     [rbp+var_40], rax
0x18001c6cc  lea     rax, [rbp+var_4C]
0x18001c6d0  mov     [rbp+var_38], rax
0x18001c6d4  lea     rax, [rbp+var_50]
0x18001c6d8  mov     [rbp+var_30], rax
0x18001c6dc  mov     [rbp+var_50], 0
0x18001c6e3  mov     [rbp+var_4C], 0
0x18001c6ea  movups  xmmword ptr [rbp+var_28], xmm0
0x18001c6ee  call    _lambda_16004c6c3d04f347f7b40a85144c46e9___operator__
0x18001c6f3  lea     rax, [rbp+var_40]
0x18001c6f7  mov     [rbp+var_4C], 1
0x18001c6fe  mov     [rbp+var_48], rax
0x18001c702  call    PrxDllUnregisterServer
0x18001c707  mov     [rbp+var_50], eax
0x18001c70a  call    cs:__imp_GetThreadLocale
0x18001c710  mov     ecx, 800h; Locale
0x18001c715  mov     ebx, eax
0x18001c717  call    cs:__imp_SetThreadLocale
0x18001c71d  call    ?UnregisterServer@?$CAtlModuleT@VTpmVCardManagerModule@@@ATL@@QEAAJHPEBU_GUID@@@Z; ATL::CAtlModuleT<TpmVCardManagerModule>::UnregisterServer(int,_GUID const *)
0x18001c722  xor     edi, edi
0x18001c724  mov     ecx, ebx; Locale
0x18001c726  test    eax, eax
0x18001c728  cmovs   edi, eax
0x18001c72b  call    cs:__imp_SetThreadLocale
0x18001c731  mov     ebx, [rbp+var_50]
0x18001c734  test    ebx, ebx
0x18001c736  js      short loc_18001C73A
0x18001c738  mov     ebx, edi
0x18001c73a  lea     rcx, [rbp+var_48]
0x18001c73e  call    WppTraceUnwinder__lambda_16004c6c3d04f347f7b40a85144c46e9_______WppTraceUnwinder__lambda_16004c6c3d04f347f7b40a85144c46e9____
0x18001c743  mov     eax, ebx
0x18001c745  mov     rcx, [rbp+var_10]
0x18001c749  xor     rcx, rsp; StackCookie
0x18001c74c  call    __security_check_cookie
0x18001c751  lea     r11, [rsp+70h+var_s0]
0x18001c756  mov     rbx, [r11+10h]
0x18001c75a  mov     rdi, [r11+18h]
0x18001c75e  mov     rsp, r11
0x18001c761  pop     rbp
0x18001c762  retn
```
