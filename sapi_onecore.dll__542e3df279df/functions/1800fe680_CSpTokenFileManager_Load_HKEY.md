# CSpTokenFileManager::Load(HKEY__ *)

- ea: `0x1800fe680`
- end: `0x1800fe844`
- name: `?Load@CSpTokenFileManager@@QEAAJPEAUHKEY__@@@Z`
- size: `452`
- prototype: `int(CSpTokenFileManager *__hidden this, HKEY)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800103e0`

## callees

- `0x18000bec4`
- `0x1800213f0`
- `0x180026508`
- `0x1800265e0`
- `0x1800fe680`
- `0x1800fea40`
- `0x1800fedf8`
- `0x1800fef4c`
- `0x18028b010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800fe80d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800fe80d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800fe701`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800fe788`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800fe7cd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800fe701`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800fe788`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800fe7cd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800fe730`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800fe730`

## string_xrefs

- `0x1800fe6c1`: `onecoreuap\enduser\nui\onecore\sapi\sapi\sharedlib\tokenfilemanager.cpp`
- `0x1800fe7b8`: `onecoreuap\enduser\nui\onecore\sapi\sapi\sharedlib\tokenfilemanager.cpp`
- `0x1800fe81e`: `onecoreuap\enduser\nui\onecore\sapi\sapi\sharedlib\tokenfilemanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CSpTokenFileManager::Load(CSpTokenFileManager *this, HKEY a2)
{
  int v4; // eax
  int XMLTokensNodeFromPath; // ebx
  unsigned int i; // esi
  __int64 v8; // rdi
  __int64 (__fastcall *v9)(__int64, _QWORD, HSTRING *); // rbx
  int v10; // eax
  const unsigned __int16 *StringRawBuffer; // rdi
  CSpRegistryXMLLoader *v12; // rcx
  int v13; // r9d
  unsigned __int64 v14; // r9
  __int64 v15; // rdx
  unsigned int v16; // eax
  int lpData; // [rsp+20h] [rbp-20h]
  unsigned int lpDataa; // [rsp+20h] [rbp-20h]
  struct IXMLDOMNode *v19[2]; // [rsp+30h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+28h]
  unsigned int v21; // [rsp+70h] [rbp+30h] BYREF
  HSTRING string; // [rsp+80h] [rbp+40h] BYREF
  __int64 v23; // [rsp+88h] [rbp+48h] BYREF

  v21 = 0;
  v4 = (*(__int64 (__fastcall **)(_QWORD, unsigned int *))(**((_QWORD **)this + 2) + 56LL))(*((_QWORD *)this + 2), &v21);
  XMLTokensNodeFromPath = v4;
  if ( v4 >= 0 )
  {
    for ( i = 0; i < v21; ++i )
    {
      v23 = 0;
      string = 0;
      v8 = *((_QWORD *)this + 2);
      v9 = *(__int64 (__fastcall **)(__int64, _QWORD, HSTRING *))(*(_QWORD *)v8 + 48LL);
      WindowsDeleteString(0);
      string = 0;
      v10 = v9(v8, i, &string);
      XMLTokensNodeFromPath = v10;
      if ( v10 < 0 )
      {
        v14 = (unsigned int)v10;
        v15 = 89;
        goto LABEL_14;
      }
      StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
      v19[0] = 0;
      XMLTokensNodeFromPath = CSpRegistryXMLLoader::GenerateXMLTokensNodeFromPath(v12, StringRawBuffer, v19);
      if ( XMLTokensNodeFromPath >= 0 )
      {
        XMLTokensNodeFromPath = CSpRegistryXMLLoader::StoreParentDirectoryPath(
                                  (CSpRegistryXMLLoader *)&v23,
                                  StringRawBuffer);
        if ( XMLTokensNodeFromPath >= 0 )
          XMLTokensNodeFromPath = CSpRegistryXMLLoader::ProcessXMLTokensChildren(
                                    (CSpRegistryXMLLoader *)&v23,
                                    a2,
                                    v19[0],
                                    v13);
      }
      ATL::CComPtrBase<ISpLexicon2>::~CComPtrBase<ISpLexicon2>(v19);
      if ( XMLTokensNodeFromPath < 0 )
      {
        v14 = (unsigned int)XMLTokensNodeFromPath;
        v15 = 90;
LABEL_14:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v15,
          (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sharedlib\\tokenfilemanager.cpp",
          (const char *)v14,
          lpData);
        WindowsDeleteString(string);
        string = 0;
        CSpCollection<CSpCategory *>::~CSpCollection<CSpCategory *>(&v23);
        return (unsigned int)XMLTokensNodeFromPath;
      }
      WindowsDeleteString(string);
      string = 0;
      CSpCollection<CSpCategory *>::~CSpCollection<CSpCategory *>(&v23);
    }
    v16 = RegSetValueExW(a2, L"FileTimeHash", 0, 3u, (const BYTE *)this + 24, 0x20u);
    if ( v16 )
      return wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)0x5D,
               (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sharedlib\\tokenfilemanager.cpp",
               (const char *)v16,
               lpDataa);
    else
      return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x53,
      (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sharedlib\\tokenfilemanager.cpp",
      (const char *)(unsigned int)v4,
      lpData);
    return (unsigned int)XMLTokensNodeFromPath;
  }
}

```

## disassembly

```asm
0x1800fe680  mov     [rsp-28h+arg_8], rbx
0x1800fe685  push    rbp
0x1800fe686  push    rsi
0x1800fe687  push    rdi
0x1800fe688  push    r14
0x1800fe68a  push    r15
0x1800fe68c  mov     rbp, rsp
0x1800fe68f  sub     rsp, 40h
0x1800fe693  mov     r14, rdx
0x1800fe696  mov     r15, rcx
0x1800fe699  mov     [rbp+arg_0], 0
0x1800fe6a0  mov     rcx, [rcx+10h]
0x1800fe6a4  mov     rax, [rcx]
0x1800fe6a7  lea     rdx, [rbp+arg_0]
0x1800fe6ab  mov     rax, [rax+38h]
0x1800fe6af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fe6b4  mov     ebx, eax
0x1800fe6b6  test    eax, eax
0x1800fe6b8  jns     short loc_1800FE6D9
0x1800fe6ba  mov     rcx, [rbp+28h]; this
0x1800fe6be  mov     r9d, eax; char *
0x1800fe6c1  lea     r8, aOnecoreuapEndu_265; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x1800fe6c8  mov     edx, 53h ; 'S'; void *
0x1800fe6cd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800fe6d2  mov     eax, ebx
0x1800fe6d4  jmp     loc_1800FE833
0x1800fe6d9  xor     esi, esi
0x1800fe6db  cmp     esi, [rbp+arg_0]
0x1800fe6de  jnb     loc_1800FE7E9
0x1800fe6e4  mov     [rbp+arg_18], 0
0x1800fe6ec  mov     [rbp+string], 0
0x1800fe6f4  mov     rdi, [r15+10h]
0x1800fe6f8  mov     rax, [rdi]
0x1800fe6fb  mov     rbx, [rax+30h]
0x1800fe6ff  xor     ecx, ecx; string
0x1800fe701  call    cs:__imp_WindowsDeleteString
0x1800fe707  mov     [rbp+string], 0
0x1800fe70f  lea     r8, [rbp+string]
0x1800fe713  mov     edx, esi
0x1800fe715  mov     rcx, rdi
0x1800fe718  mov     rax, rbx
0x1800fe71b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fe720  mov     ebx, eax
0x1800fe722  test    eax, eax
0x1800fe724  js      loc_1800FE7B0
0x1800fe72a  xor     edx, edx; length
0x1800fe72c  mov     rcx, [rbp+string]; string
0x1800fe730  call    cs:__imp_WindowsGetStringRawBuffer
0x1800fe736  mov     rdi, rax
0x1800fe739  mov     [rbp+var_10], 0
0x1800fe741  lea     r8, [rbp+var_10]; struct IXMLDOMNode **
0x1800fe745  mov     rdx, rax; unsigned __int16 *
0x1800fe748  call    ?GenerateXMLTokensNodeFromPath@CSpRegistryXMLLoader@@AEAAJPEBGPEAPEAUIXMLDOMNode@@@Z; CSpRegistryXMLLoader::GenerateXMLTokensNodeFromPath(ushort const *,IXMLDOMNode * *)
0x1800fe74d  mov     ebx, eax
0x1800fe74f  test    eax, eax
0x1800fe751  js      short loc_1800FE777
0x1800fe753  mov     rdx, rdi; unsigned __int16 *
0x1800fe756  lea     rcx, [rbp+arg_18]; this
0x1800fe75a  call    ?StoreParentDirectoryPath@CSpRegistryXMLLoader@@AEAAJPEBG@Z; CSpRegistryXMLLoader::StoreParentDirectoryPath(ushort const *)
0x1800fe75f  mov     ebx, eax
0x1800fe761  test    eax, eax
0x1800fe763  js      short loc_1800FE777
0x1800fe765  mov     r8, [rbp+var_10]; struct IXMLDOMNode *
0x1800fe769  mov     rdx, r14; HKEY
0x1800fe76c  lea     rcx, [rbp+arg_18]; this
0x1800fe770  call    ?ProcessXMLTokensChildren@CSpRegistryXMLLoader@@AEAAJPEAUHKEY__@@PEAUIXMLDOMNode@@H@Z; CSpRegistryXMLLoader::ProcessXMLTokensChildren(HKEY__ *,IXMLDOMNode *,int)
0x1800fe775  mov     ebx, eax
0x1800fe777  lea     rcx, [rbp+var_10]
0x1800fe77b  call    ??1?$CComPtrBase@UISpLexicon2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISpLexicon2>::~CComPtrBase<ISpLexicon2>(void)
0x1800fe780  test    ebx, ebx
0x1800fe782  js      short loc_1800FE7A6
0x1800fe784  mov     rcx, [rbp+string]; string
0x1800fe788  call    cs:__imp_WindowsDeleteString
0x1800fe78e  mov     [rbp+string], 0
0x1800fe796  lea     rcx, [rbp+arg_18]
0x1800fe79a  call    ??1?$CSpCollection@PEAVCSpCategory@@@@QEAA@XZ; CSpCollection<CSpCategory *>::~CSpCollection<CSpCategory *>(void)
0x1800fe79f  inc     esi
0x1800fe7a1  jmp     loc_1800FE6DB
0x1800fe7a6  mov     r9d, ebx
0x1800fe7a9  mov     edx, 5Ah ; 'Z'
0x1800fe7ae  jmp     short loc_1800FE7B8
0x1800fe7b0  mov     r9d, eax; char *
0x1800fe7b3  mov     edx, 59h ; 'Y'; void *
0x1800fe7b8  lea     r8, aOnecoreuapEndu_265; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x1800fe7bf  mov     rcx, [rbp+28h]; this
0x1800fe7c3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800fe7c8  nop
0x1800fe7c9  mov     rcx, [rbp+string]; string
0x1800fe7cd  call    cs:__imp_WindowsDeleteString
0x1800fe7d3  mov     [rbp+string], 0
0x1800fe7db  lea     rcx, [rbp+arg_18]
0x1800fe7df  call    ??1?$CSpCollection@PEAVCSpCategory@@@@QEAA@XZ; CSpCollection<CSpCategory *>::~CSpCollection<CSpCategory *>(void)
0x1800fe7e4  jmp     loc_1800FE6D2
0x1800fe7e9  lea     rax, [r15+18h]
0x1800fe7ed  mov     [rsp+40h+cbData], 20h ; ' '; cbData
0x1800fe7f5  mov     [rsp+40h+lpData], rax; unsigned int
0x1800fe7fa  mov     r9d, 3; dwType
0x1800fe800  xor     r8d, r8d; Reserved
0x1800fe803  lea     rdx, aFiletimehash; "FileTimeHash"
0x1800fe80a  mov     rcx, r14; hKey
0x1800fe80d  call    cs:__imp_RegSetValueExW
0x1800fe813  test    eax, eax
0x1800fe815  jz      short loc_1800FE831
0x1800fe817  mov     rcx, [rbp+28h]; this
0x1800fe81b  mov     r9d, eax; char *
0x1800fe81e  lea     r8, aOnecoreuapEndu_265; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x1800fe825  mov     edx, 5Dh ; ']'; void *
0x1800fe82a  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800fe82f  jmp     short loc_1800FE833
0x1800fe831  xor     eax, eax
0x1800fe833  mov     rbx, [rsp+40h+arg_8]
0x1800fe838  add     rsp, 40h
0x1800fe83c  pop     r15
0x1800fe83e  pop     r14
0x1800fe840  pop     rdi
0x1800fe841  pop     rsi
0x1800fe842  pop     rbp
0x1800fe843  retn
```
