# GetModuleHandleW(wchar_t const *,wistd::unique_ptr<uus::Session,wistd::default_delete<uus::Session>> &,HINSTANCE__ * *)

- ea: `0x140008c78`
- end: `0x140008f17`
- name: `?GetModuleHandleW@@YAJPEB_WAEAV?$unique_ptr@USession@uus@@U?$default_delete@USession@uus@@@wistd@@@wistd@@PEAPEAUHINSTANCE__@@@Z`
- size: `671`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x1400080bc`

## callees

- `0x140002ac0`
- `0x1400074c8`
- `0x140008c78`
- `0x14001aa60`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x140008d29`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x140008ed0`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x140008d29`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x140008ed0`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x140008d05`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x140008d63`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x140008d98`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x140008dcd`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x140008dfa`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x140008e27`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x140008d05`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x140008d63`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x140008d98`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x140008dcd`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x140008dfa`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x140008e27`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x140008cc9`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x140008cc9`

## string_xrefs

- `0x140008e32`: `wu.handler.updatedeploy`
- `0x140008cd2`: `UpdateDeploy.dll`
- `0x140008e05`: `UpdateDeploy.dll`
- `0x140008dd8`: `wuuhosdeployment.dll`
- `0x140008da7`: `wuauengcore.dll`
- `0x140008d72`: `wuuhdrv.dll`
- `0x140008d34`: `wuuhext.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall GetModuleHandleW(const WCHAR *a1, __int64 a2, HMODULE *a3)
{
  unsigned int v4; // ebx
  __int64 v5; // rdx
  const WCHAR *FileNameW; // rbx
  __int64 v7; // rdx
  wchar_t *v8; // rcx
  HMODULE v9; // rcx
  HMODULE v10; // rax
  int lpString2; // [rsp+20h] [rbp-68h]
  HMODULE hLibModule; // [rsp+40h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  if ( !a1 || !*a1 )
  {
    v4 = -2147024809;
    v5 = 280;
    goto LABEL_33;
  }
  if ( !a3 )
  {
    v4 = -2147467261;
    v5 = 281;
LABEL_33:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v5,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\UserProcess\\core\\WinMain.cpp",
      (const char *)v4,
      lpString2);
    return v4;
  }
  hLibModule = 0;
  FileNameW = PathFindFileNameW(a1);
  if ( FileNameW != L"UpdateDeploy.dll"
    && (!FileNameW || CompareStringW(0x7Fu, 1u, FileNameW, -1, L"UpdateDeploy.dll", -1) != 2) )
  {
    v4 = -2145124297;
    v7 = 288;
LABEL_28:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\UserProcess\\core\\WinMain.cpp",
      (const char *)v4,
      lpString2);
    v9 = hLibModule;
    goto LABEL_30;
  }
  if ( FileNameW != L"wuuhext.dll" )
  {
    if ( !FileNameW )
    {
LABEL_24:
      v8 = L"wu.handler";
      goto LABEL_26;
    }
    if ( CompareStringW(0x7Fu, 1u, FileNameW, -1, L"wuuhext.dll", -1) != 2 )
    {
      if ( FileNameW == L"wuuhdrv.dll" || CompareStringW(0x7Fu, 1u, FileNameW, -1, L"wuuhdrv.dll", -1) == 2 )
      {
        v8 = L"wu.handler.wuuhdrv";
        goto LABEL_26;
      }
      if ( FileNameW == L"wuauengcore.dll" || CompareStringW(0x7Fu, 1u, FileNameW, -1, L"wuauengcore.dll", -1) == 2 )
      {
        v8 = L"wu.handler.wuauengcore";
        goto LABEL_26;
      }
      if ( FileNameW == L"wuuhosdeployment.dll"
        || CompareStringW(0x7Fu, 1u, FileNameW, -1, L"wuuhosdeployment.dll", -1) == 2 )
      {
        v8 = L"wu.handler.wuuhosdeployment";
        goto LABEL_26;
      }
      if ( FileNameW == L"UpdateDeploy.dll" || CompareStringW(0x7Fu, 1u, FileNameW, -1, L"UpdateDeploy.dll", -1) == 2 )
      {
        v8 = L"wu.handler.updatedeploy";
        goto LABEL_26;
      }
      goto LABEL_24;
    }
  }
  v8 = (wchar_t *)L"wu.handler.wuuhext";
LABEL_26:
  v4 = UndockedModuleLoader::Load(v8, (__int64)&hLibModule);
  if ( (v4 & 0x80000000) != 0 )
  {
    v7 = 301;
    goto LABEL_28;
  }
  v10 = hLibModule;
  v9 = 0;
  hLibModule = 0;
  *a3 = v10;
  v4 = 0;
LABEL_30:
  if ( v9 )
    FreeLibrary(v9);
  return v4;
}

```

## disassembly

```asm
0x140008c78  push    rbx
0x140008c7a  push    rbp
0x140008c7b  push    rsi
0x140008c7c  push    rdi
0x140008c7d  push    r12
0x140008c7f  push    r14
0x140008c81  push    r15
0x140008c83  sub     rsp, 50h
0x140008c87  mov     rax, cs:__security_cookie
0x140008c8e  xor     rax, rsp
0x140008c91  mov     [rsp+88h+var_40], rax
0x140008c96  mov     rdi, r8
0x140008c99  mov     rsi, rdx
0x140008c9c  xor     ebp, ebp
0x140008c9e  test    rcx, rcx
0x140008ca1  jz      loc_140008ED8
0x140008ca7  cmp     [rcx], bp
0x140008caa  jz      loc_140008ED8
0x140008cb0  test    r8, r8
0x140008cb3  jnz     short loc_140008CC4
0x140008cb5  mov     ebx, 80004003h
0x140008cba  mov     edx, 119h
0x140008cbf  jmp     loc_140008EE2
0x140008cc4  mov     [rsp+88h+hLibModule], rbp
0x140008cc9  call    cs:__imp_PathFindFileNameW
0x140008ccf  mov     rbx, rax
0x140008cd2  lea     rax, ?c_szUpdateDeployDll@@3QB_WB; "UpdateDeploy.dll"
0x140008cd9  or      r14d, 0FFFFFFFFh
0x140008cdd  lea     r15d, [r14+2]
0x140008ce1  lea     r12d, [r15+7Eh]
0x140008ce5  cmp     rbx, rax
0x140008ce8  jz      short loc_140008D1F
0x140008cea  test    rbx, rbx
0x140008ced  jz      short loc_140008D10
0x140008cef  mov     [rsp+88h+cchCount2], r14d; cchCount2
0x140008cf4  mov     [rsp+88h+lpString2], rax; lpString2
0x140008cf9  mov     r9d, r14d; cchCount1
0x140008cfc  mov     r8, rbx; lpString1
0x140008cff  mov     edx, r15d; dwCmpFlags
0x140008d02  mov     ecx, r12d; Locale
0x140008d05  call    cs:__imp_CompareStringW
0x140008d0b  cmp     eax, 2
0x140008d0e  jz      short loc_140008D1F
0x140008d10  mov     ebx, 80240037h
0x140008d15  mov     edx, 120h
0x140008d1a  jmp     loc_140008E9B
0x140008d1f  mov     rcx, [rsp+88h+hLibModule]; hLibModule
0x140008d24  test    rcx, rcx
0x140008d27  jz      short loc_140008D34
0x140008d29  call    cs:__imp_FreeLibrary
0x140008d2f  mov     [rsp+88h+hLibModule], rbp
0x140008d34  lea     rax, ?c_szWuuhextDll@@3QB_WB; "wuuhext.dll"
0x140008d3b  cmp     rbx, rax
0x140008d3e  jz      loc_140008E5F
0x140008d44  test    rbx, rbx
0x140008d47  jz      loc_140008E56
0x140008d4d  mov     [rsp+88h+cchCount2], r14d; cchCount2
0x140008d52  mov     [rsp+88h+lpString2], rax; lpString2
0x140008d57  mov     r9d, r14d; cchCount1
0x140008d5a  mov     r8, rbx; lpString1
0x140008d5d  mov     edx, r15d; dwCmpFlags
0x140008d60  mov     ecx, r12d; Locale
0x140008d63  call    cs:__imp_CompareStringW
0x140008d69  cmp     eax, 2
0x140008d6c  jz      loc_140008E5F
0x140008d72  lea     rax, ?c_szWuuhdrvDll@@3QB_WB; "wuuhdrv.dll"
0x140008d79  cmp     rbx, rax
0x140008d7c  jz      loc_140008E4D
0x140008d82  mov     [rsp+88h+cchCount2], r14d; cchCount2
0x140008d87  mov     [rsp+88h+lpString2], rax; lpString2
0x140008d8c  mov     r9d, r14d; cchCount1
0x140008d8f  mov     r8, rbx; lpString1
0x140008d92  mov     edx, r15d; dwCmpFlags
0x140008d95  mov     ecx, r12d; Locale
0x140008d98  call    cs:__imp_CompareStringW
0x140008d9e  cmp     eax, 2
0x140008da1  jz      loc_140008E4D
0x140008da7  lea     rax, ?c_szWuauengCoreDll@@3QB_WB; "wuauengcore.dll"
0x140008dae  cmp     rbx, rax
0x140008db1  jz      loc_140008E44
0x140008db7  mov     [rsp+88h+cchCount2], r14d; cchCount2
0x140008dbc  mov     [rsp+88h+lpString2], rax; lpString2
0x140008dc1  mov     r9d, r14d; cchCount1
0x140008dc4  mov     r8, rbx; lpString1
0x140008dc7  mov     edx, r15d; dwCmpFlags
0x140008dca  mov     ecx, r12d; Locale
0x140008dcd  call    cs:__imp_CompareStringW
0x140008dd3  cmp     eax, 2
0x140008dd6  jz      short loc_140008E44
0x140008dd8  lea     rax, ?c_szWuuhosdeploymentDll@@3QB_WB; "wuuhosdeployment.dll"
0x140008ddf  cmp     rbx, rax
0x140008de2  jz      short loc_140008E3B
0x140008de4  mov     [rsp+88h+cchCount2], r14d; cchCount2
0x140008de9  mov     [rsp+88h+lpString2], rax; lpString2
0x140008dee  mov     r9d, r14d; cchCount1
0x140008df1  mov     r8, rbx; lpString1
0x140008df4  mov     edx, r15d; dwCmpFlags
0x140008df7  mov     ecx, r12d; Locale
0x140008dfa  call    cs:__imp_CompareStringW
0x140008e00  cmp     eax, 2
0x140008e03  jz      short loc_140008E3B
0x140008e05  lea     rax, ?c_szUpdateDeployDll@@3QB_WB; "UpdateDeploy.dll"
0x140008e0c  cmp     rbx, rax
0x140008e0f  jz      short loc_140008E32
0x140008e11  mov     [rsp+88h+cchCount2], r14d; cchCount2
0x140008e16  mov     [rsp+88h+lpString2], rax; lpString2
0x140008e1b  mov     r9d, r14d; cchCount1
0x140008e1e  mov     r8, rbx; lpString1
0x140008e21  mov     edx, r15d; dwCmpFlags
0x140008e24  mov     ecx, r12d; Locale
0x140008e27  call    cs:__imp_CompareStringW
0x140008e2d  cmp     eax, 2
0x140008e30  jnz     short loc_140008E56
0x140008e32  lea     rcx, aWuHandlerUpdat; "wu.handler.updatedeploy"
0x140008e39  jmp     short loc_140008E66
0x140008e3b  lea     rcx, aWuHandlerWuuho; "wu.handler.wuuhosdeployment"
0x140008e42  jmp     short loc_140008E66
0x140008e44  lea     rcx, aWuHandlerWuaue; "wu.handler.wuauengcore"
0x140008e4b  jmp     short loc_140008E66
0x140008e4d  lea     rcx, aWuHandlerWuuhd; "wu.handler.wuuhdrv"
0x140008e54  jmp     short loc_140008E66
0x140008e56  lea     rcx, aWuHandler; "wu.handler"
0x140008e5d  jmp     short loc_140008E66
0x140008e5f  lea     rcx, aWuHandlerWuuhe; "wu.handler.wuuhext"
0x140008e66  mov     [rsp+88h+var_50], rbp
0x140008e6b  mov     [rsp+88h+var_58], rbp
0x140008e70  mov     qword ptr [rsp+88h+cchCount2], rbp
0x140008e75  lea     rax, [rsp+88h+hLibModule]
0x140008e7a  mov     [rsp+88h+lpString2], rax; int
0x140008e7f  mov     r9, rsi
0x140008e82  mov     r8d, 3
0x140008e88  mov     rdx, rbx
0x140008e8b  call    UndockedModuleLoader__Load
0x140008e90  mov     ebx, eax
0x140008e92  test    eax, eax
0x140008e94  jns     short loc_140008EB9
0x140008e96  mov     edx, 12Dh; void *
0x140008e9b  mov     rcx, [rsp+88h]; this
0x140008ea3  mov     r9d, ebx; char *
0x140008ea6  lea     r8, aCW1SSrcClientU_0; "C:\\__w\\1\\s\\src\\Client\\UserProcess"...
0x140008ead  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140008eb2  mov     rcx, [rsp+88h+hLibModule]
0x140008eb7  jmp     short loc_140008ECB
0x140008eb9  mov     rax, [rsp+88h+hLibModule]
0x140008ebe  mov     rcx, rbp; hLibModule
0x140008ec1  mov     [rsp+88h+hLibModule], rcx
0x140008ec6  mov     [rdi], rax
0x140008ec9  mov     ebx, ebp
0x140008ecb  test    rcx, rcx
0x140008ece  jz      short loc_140008EF9
0x140008ed0  call    cs:__imp_FreeLibrary
0x140008ed6  jmp     short loc_140008EF9
0x140008ed8  mov     ebx, 80070057h
0x140008edd  mov     edx, 118h; void *
0x140008ee2  mov     r9d, ebx; char *
0x140008ee5  lea     r8, aCW1SSrcClientU_0; "C:\\__w\\1\\s\\src\\Client\\UserProcess"...
0x140008eec  mov     rcx, [rsp+88h]; this
0x140008ef4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140008ef9  mov     eax, ebx
0x140008efb  mov     rcx, [rsp+88h+var_40]
0x140008f00  xor     rcx, rsp; StackCookie
0x140008f03  call    __security_check_cookie
0x140008f08  add     rsp, 50h
0x140008f0c  pop     r15
0x140008f0e  pop     r14
0x140008f10  pop     r12
0x140008f12  pop     rdi
0x140008f13  pop     rsi
0x140008f14  pop     rbp
0x140008f15  pop     rbx
0x140008f16  retn
```
