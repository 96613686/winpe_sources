# COSInstaller::CreateMergedSandboxDir(wchar_t * *)

- ea: `0x18002b2d4`
- end: `0x18002b4f5`
- name: `?CreateMergedSandboxDir@COSInstaller@@AEAAJPEAPEA_W@Z`
- size: `545`
- prototype: `__int64 __fastcall(COSInstaller *this, wchar_t **, __int64, unsigned int *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18002a83c`

## callees

- `0x180003950`
- `0x180005f64`
- `0x18000c0e4`
- `0x18000cbc4`
- `0x18000e05c`
- `0x18002b2d4`
- `0x180030110`
- `0x180042630`

## import_xrefs

- `RPCRT4!UuidCreate` at `0x18002b379`
- `RPCRT4!UuidCreate` at `0x18002b379`
- `RPCRT4!UuidToStringW` at `0x18002b3bf`
- `RPCRT4!UuidToStringW` at `0x18002b3bf`

## string_xrefs

- `0x18002b353`: `C:\__w\1\s\src\Client\lib\util\sdpath.cpp`
- `0x18002b335`: `MergedUpdates`
- `0x18002b40d`: `C:\__w\1\s\src\Client\Engine\handler\OSDeployment\Installer\OSInstaller.cpp`
- `0x18002b44e`: `C:\__w\1\s\src\Client\Engine\handler\OSDeployment\Installer\OSInstaller.cpp`
- `0x18002b48b`: `C:\__w\1\s\src\Client\Engine\handler\OSDeployment\Installer\OSInstaller.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall COSInstaller::CreateMergedSandboxDir(COSInstaller *this, wchar_t **a2, __int64 a3, unsigned int *a4)
{
  wchar_t *v4; // rbx
  WCHAR *v5; // rdi
  unsigned int v7; // esi
  __int64 v8; // rdx
  int SusBaseDirectoryW; // eax
  unsigned __int64 v10; // r9
  RPC_STATUS v11; // eax
  RPC_STATUS v12; // eax
  int v13; // eax
  int CombinedPath; // eax
  unsigned int v15; // edx
  void *v16; // r8
  int DirectoryW; // eax
  wchar_t *v18; // rax
  wchar_t *v20; // [rsp+20h] [rbp-E0h] BYREF
  PCNZWCH lpString1; // [rsp+28h] [rbp-D8h] BYREF
  RPC_WSTR StringUuid; // [rsp+30h] [rbp-D0h] BYREF
  UUID Uuid; // [rsp+38h] [rbp-C8h] BYREF
  wchar_t v24[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+188h]

  v4 = 0;
  StringUuid = 0;
  v5 = 0;
  v20 = 0;
  lpString1 = 0;
  Uuid = 0;
  if ( !a2 )
  {
    v7 = -2147467261;
    v8 = 1909;
LABEL_5:
    v10 = v7;
LABEL_20:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Installer\\OSInstaller.cpp",
      (const char *)v10,
      (int)v20);
    goto LABEL_22;
  }
  SusBaseDirectoryW = GetSusBaseDirectoryW(v24, (unsigned int)a2, L"MergedUpdates", a4);
  v7 = SusBaseDirectoryW;
  if ( SusBaseDirectoryW < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xB6,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\sdpath.cpp",
      (const char *)(unsigned int)SusBaseDirectoryW,
      (int)v20);
    v8 = 1912;
    goto LABEL_5;
  }
  v11 = UuidCreate(&Uuid);
  if ( v11 )
  {
    v7 = (unsigned __int16)v11 | 0x80070000;
    if ( v11 <= 0 )
      v7 = v11;
    v10 = v7;
    v8 = 1919;
    goto LABEL_20;
  }
  v12 = UuidToStringW(&Uuid, &StringUuid);
  if ( v12 )
  {
    v7 = (unsigned __int16)v12 | 0x80070000;
    if ( v12 <= 0 )
      v7 = v12;
    v10 = v7;
    v8 = 1924;
    goto LABEL_20;
  }
  v13 = CreateCombinedPath(v24, StringUuid, &v20);
  v7 = v13;
  if ( v13 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x788,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Installer\\OSInstaller.cpp",
      (const char *)(unsigned int)v13,
      (int)v20);
    v4 = v20;
    goto LABEL_22;
  }
  v4 = v20;
  CombinedPath = CreateCombinedPath(v20, L"Metadata", (wchar_t **)&lpString1);
  v7 = CombinedPath;
  if ( CombinedPath < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x78D,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Installer\\OSInstaller.cpp",
      (const char *)(unsigned int)CombinedPath,
      (int)v20);
    v5 = (WCHAR *)lpString1;
    goto LABEL_22;
  }
  v5 = (WCHAR *)lpString1;
  DirectoryW = SusMakeDirectoryW(lpString1, v15, v16);
  v7 = DirectoryW;
  if ( DirectoryW < 0 )
  {
    v10 = (unsigned int)DirectoryW;
    v8 = 1936;
    goto LABEL_20;
  }
  v18 = v4;
  v4 = 0;
  v7 = 0;
  *a2 = v18;
LABEL_22:
  if ( v5 )
    CSusBaseAllocTag<942762101>::operator delete(v5);
  if ( v4 )
    CSusBaseAllocTag<942762101>::operator delete(v4);
  if ( StringUuid )
    XPtrRpcStringFree(StringUuid);
  return v7;
}

```

## disassembly

```asm
0x18002b2d4  mov     [rsp-8+arg_0], rbx
0x18002b2d9  mov     [rsp-8+arg_10], rsi
0x18002b2de  push    rbp
0x18002b2df  push    rdi
0x18002b2e0  push    r14
0x18002b2e2  lea     rbp, [rsp-170h]
0x18002b2ea  sub     rsp, 270h
0x18002b2f1  mov     rax, cs:__security_cookie
0x18002b2f8  xor     rax, rsp
0x18002b2fb  mov     [rbp+180h+var_20], rax
0x18002b302  xor     ebx, ebx
0x18002b304  mov     [rsp+280h+StringUuid], 0
0x18002b30d  xor     edi, edi
0x18002b30f  mov     [rsp+280h+var_260], rbx; int
0x18002b314  mov     [rsp+280h+lpString1], rdi
0x18002b319  xorps   xmm0, xmm0
0x18002b31c  mov     r14, rdx
0x18002b31f  movups  xmmword ptr [rsp+280h+Uuid.Data1], xmm0
0x18002b324  test    rdx, rdx
0x18002b327  jnz     short loc_18002B335
0x18002b329  mov     esi, 80004003h
0x18002b32e  mov     edx, 775h; unsigned int
0x18002b333  jmp     short loc_18002B36C
0x18002b335  lea     r8, aMergedupdates; "MergedUpdates"
0x18002b33c  lea     rcx, [rsp+280h+var_230]; wchar_t *
0x18002b341  call    ?GetSusBaseDirectoryW@@YAJPEA_WKPEB_WPEAK@Z; GetSusBaseDirectoryW(wchar_t *,ulong,wchar_t const *,ulong *)
0x18002b346  mov     esi, eax
0x18002b348  test    eax, eax
0x18002b34a  jns     short loc_18002B374
0x18002b34c  mov     rcx, [rbp+188h]; this
0x18002b353  lea     r8, aCW1SSrcClientL_18; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x18002b35a  mov     r9d, eax; char *
0x18002b35d  mov     edx, 0B6h; void *
0x18002b362  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002b367  mov     edx, 778h
0x18002b36c  mov     r9d, esi
0x18002b36f  jmp     loc_18002B484
0x18002b374  lea     rcx, [rsp+280h+Uuid]; Uuid
0x18002b379  call    cs:__imp_UuidCreate
0x18002b37f  test    eax, eax
0x18002b381  jz      short loc_18002B3A6
0x18002b383  movzx   esi, ax
0x18002b386  or      esi, 80070000h
0x18002b38c  test    eax, eax
0x18002b38e  cmovle  esi, eax
0x18002b391  test    esi, esi
0x18002b393  jns     loc_18002B4A3
0x18002b399  mov     r9d, esi
0x18002b39c  mov     edx, 77Fh
0x18002b3a1  jmp     loc_18002B484
0x18002b3a6  mov     rcx, [rsp+280h+StringUuid]; void *
0x18002b3ab  test    rcx, rcx
0x18002b3ae  jz      short loc_18002B3B5
0x18002b3b0  call    ?XPtrRpcStringFree@@YAXPEAX@Z; XPtrRpcStringFree(void *)
0x18002b3b5  lea     rdx, [rsp+280h+StringUuid]; StringUuid
0x18002b3ba  lea     rcx, [rsp+280h+Uuid]; Uuid
0x18002b3bf  call    cs:__imp_UuidToStringW
0x18002b3c5  test    eax, eax
0x18002b3c7  jz      short loc_18002B3EC
0x18002b3c9  movzx   esi, ax
0x18002b3cc  or      esi, 80070000h
0x18002b3d2  test    eax, eax
0x18002b3d4  cmovle  esi, eax
0x18002b3d7  test    esi, esi
0x18002b3d9  jns     loc_18002B4A3
0x18002b3df  mov     r9d, esi
0x18002b3e2  mov     edx, 784h
0x18002b3e7  jmp     loc_18002B484
0x18002b3ec  mov     rdx, [rsp+280h+StringUuid]; wchar_t *
0x18002b3f1  lea     r8, [rsp+280h+var_260]; wchar_t **
0x18002b3f6  lea     rcx, [rsp+280h+var_230]; wchar_t *
0x18002b3fb  call    ?CreateCombinedPath@@YAJPEB_W0PEAPEA_W@Z; CreateCombinedPath(wchar_t const *,wchar_t const *,wchar_t * *)
0x18002b400  mov     esi, eax
0x18002b402  test    eax, eax
0x18002b404  jns     short loc_18002B428
0x18002b406  mov     rcx, [rbp+188h]; this
0x18002b40d  lea     r8, aCW1SSrcClientE_14; "C:\\__w\\1\\s\\src\\Client\\Engine\\han"...
0x18002b414  mov     r9d, eax; char *
0x18002b417  mov     edx, 788h; void *
0x18002b41c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002b421  mov     rbx, [rsp+280h+var_260]
0x18002b426  jmp     short loc_18002B4A3
0x18002b428  mov     rbx, [rsp+280h+var_260]
0x18002b42d  lea     r8, [rsp+280h+lpString1]; wchar_t **
0x18002b432  mov     rcx, rbx; wchar_t *
0x18002b435  lea     rdx, ?c_szUUPMetaDataSubFolder@CDeploymentSessionWrapper@OSDeploymentHelper@@2QB_WB; "Metadata"
0x18002b43c  call    ?CreateCombinedPath@@YAJPEB_W0PEAPEA_W@Z; CreateCombinedPath(wchar_t const *,wchar_t const *,wchar_t * *)
0x18002b441  mov     esi, eax
0x18002b443  test    eax, eax
0x18002b445  jns     short loc_18002B469
0x18002b447  mov     rcx, [rbp+188h]; this
0x18002b44e  lea     r8, aCW1SSrcClientE_14; "C:\\__w\\1\\s\\src\\Client\\Engine\\han"...
0x18002b455  mov     r9d, eax; char *
0x18002b458  mov     edx, 78Dh; void *
0x18002b45d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002b462  mov     rdi, [rsp+280h+lpString1]
0x18002b467  jmp     short loc_18002B4A3
0x18002b469  mov     rdi, [rsp+280h+lpString1]
0x18002b46e  mov     rcx, rdi; lpString1
0x18002b471  call    ?SusMakeDirectoryW@@YAJPEB_WKPEAX@Z; SusMakeDirectoryW(wchar_t const *,ulong,void *)
0x18002b476  mov     esi, eax
0x18002b478  test    eax, eax
0x18002b47a  jns     short loc_18002B499
0x18002b47c  mov     r9d, eax; char *
0x18002b47f  mov     edx, 790h; void *
0x18002b484  mov     rcx, [rbp+188h]; this
0x18002b48b  lea     r8, aCW1SSrcClientE_14; "C:\\__w\\1\\s\\src\\Client\\Engine\\han"...
0x18002b492  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002b497  jmp     short loc_18002B4A3
0x18002b499  mov     rax, rbx
0x18002b49c  xor     ebx, ebx
0x18002b49e  xor     esi, esi
0x18002b4a0  mov     [r14], rax
0x18002b4a3  test    rdi, rdi
0x18002b4a6  jz      short loc_18002B4B0
0x18002b4a8  mov     rcx, rdi; lpMem
0x18002b4ab  call    ??3?$CSusBaseAllocTag@$0DIDBGIHF@@@SAXPEAX@Z; CSusBaseAllocTag<942762101>::operator delete(void *)
0x18002b4b0  test    rbx, rbx
0x18002b4b3  jz      short loc_18002B4BD
0x18002b4b5  mov     rcx, rbx; lpMem
0x18002b4b8  call    ??3?$CSusBaseAllocTag@$0DIDBGIHF@@@SAXPEAX@Z; CSusBaseAllocTag<942762101>::operator delete(void *)
0x18002b4bd  mov     rcx, [rsp+280h+StringUuid]; void *
0x18002b4c2  test    rcx, rcx
0x18002b4c5  jz      short loc_18002B4CC
0x18002b4c7  call    ?XPtrRpcStringFree@@YAXPEAX@Z; XPtrRpcStringFree(void *)
0x18002b4cc  mov     eax, esi
0x18002b4ce  mov     rcx, [rbp+180h+var_20]
0x18002b4d5  xor     rcx, rsp; StackCookie
0x18002b4d8  call    __security_check_cookie
0x18002b4dd  lea     r11, [rsp+280h+var_10]
0x18002b4e5  mov     rbx, [r11+20h]
0x18002b4e9  mov     rsi, [r11+30h]
0x18002b4ed  mov     rsp, r11
0x18002b4f0  pop     r14
0x18002b4f2  pop     rdi
0x18002b4f3  pop     rbp
0x18002b4f4  retn
```
