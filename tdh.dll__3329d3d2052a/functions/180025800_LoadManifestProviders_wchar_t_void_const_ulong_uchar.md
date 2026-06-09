# LoadManifestProviders(wchar_t *,void const *,ulong,uchar)

- ea: `0x180025800`
- end: `0x18002599c`
- name: `?LoadManifestProviders@@YAKPEA_WPEBXKE@Z`
- size: `412`
- prototype: `__int64 __fastcall(wchar_t *, const void *, unsigned int, char)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, loader_planting`

## callers

- `0x180024980`
- `0x1800249d0`

## callees

- `0x1800254a8`
- `0x18002575c`
- `0x180025800`
- `0x1800259a4`
- `0x180032634`
- `0x1800335c0`
- `0x18003a720`
- `0x18003a954`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180025829`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180025829`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180025843`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180025843`

## string_xrefs

- `0x180025822`: `wevtapi.dll`
- `0x180025839`: `EvtIntCreateBinXMLFromCustomXML`

## pseudocode

```c
__int64 __fastcall LoadManifestProviders(wchar_t *a1, const void *a2, unsigned int a3, char a4)
{
  unsigned int v8; // ebx
  HMODULE Library; // rax
  void (*v10)(const char *, int, const wchar_t *, unsigned int, unsigned int); // rdx
  bool v11; // r8
  const wchar_t *v12; // rdx
  bool v13; // r8
  int XmlBytes; // eax
  int v16; // edi
  struct _GUID **v17; // rdi
  struct _GUID **v18; // rsi
  struct _GUID *v19; // rdx
  bool v20; // [rsp+20h] [rbp-98h]
  _QWORD v21[2]; // [rsp+30h] [rbp-88h] BYREF
  _BYTE v22[56]; // [rsp+40h] [rbp-78h] BYREF
  struct _GUID **v23; // [rsp+78h] [rbp-40h]
  struct _GUID **v24; // [rsp+80h] [rbp-38h]

  v8 = 0;
  Library = LoadLibraryExW(L"wevtapi.dll", 0, 0);
  v21[0] = Library;
  if ( Library )
    Library = (HMODULE)GetProcAddress(Library, "EvtIntCreateBinXMLFromCustomXML");
  MANPARSE_INFO::MANPARSE_INFO(
    (MANPARSE_INFO *)v22,
    v10,
    v11,
    (unsigned int (*)(unsigned int, const wchar_t *, unsigned int, unsigned int *, unsigned int, unsigned __int8 *, unsigned int *, struct _GUID *))Library);
  if ( a4 )
  {
    if ( !a2 )
    {
LABEL_5:
      MANPARSE_INFO::~MANPARSE_INFO((MANPARSE_INFO *)v22);
      std::unique_ptr<void,FreeLibraryDeleter>::~unique_ptr<void,FreeLibraryDeleter>(v21);
      return 87;
    }
    XmlBytes = MANPARSE_INFO::ReadXmlBytes((MANPARSE_INFO *)v22, v12, a2, a3, v20);
  }
  else
  {
    if ( !a1 )
      goto LABEL_5;
    XmlBytes = MANPARSE_INFO::ReadXmlFile((MANPARSE_INFO *)v22, a1, v13);
  }
  v16 = XmlBytes;
  if ( XmlBytes >= 0 )
  {
    v17 = v23;
    v18 = v24;
    while ( v17 != v18 )
    {
      v19 = *v17;
      v8 = (*v17)[17].Data1
         ? LoadMofProvider((__int64)v22, (__int64)v19)
         : LoadManifestProvider((struct TDH_CACHE *)v22, v19);
      if ( v8 )
        break;
      ++v17;
    }
    MANPARSE_INFO::~MANPARSE_INFO((MANPARSE_INFO *)v22);
  }
  else
  {
    MANPARSE_INFO::~MANPARSE_INFO((MANPARSE_INFO *)v22);
    switch ( v16 )
    {
      case -2147024893:
        v8 = 3;
        break;
      case -2147024891:
        v8 = 5;
        break;
      case -2147024894:
        v8 = 2;
        break;
      case -2147024882:
        v8 = 8;
        break;
      default:
        v8 = 1465;
        if ( v16 == -2147024846 )
          v8 = 50;
        break;
    }
  }
  std::unique_ptr<void,FreeLibraryDeleter>::~unique_ptr<void,FreeLibraryDeleter>(v21);
  return v8;
}

```

## disassembly

```asm
0x180025800  push    rbx
0x180025802  push    rsi
0x180025803  push    rdi
0x180025804  push    r14
0x180025806  push    r15
0x180025808  sub     rsp, 90h
0x18002580f  mov     r14b, r9b
0x180025812  mov     r15d, r8d
0x180025815  mov     rsi, rdx
0x180025818  mov     rdi, rcx
0x18002581b  xor     ebx, ebx
0x18002581d  xor     r8d, r8d; dwFlags
0x180025820  xor     edx, edx; hFile
0x180025822  lea     rcx, LibFileName; "wevtapi.dll"
0x180025829  call    cs:__imp_LoadLibraryExW
0x18002582f  mov     [rsp+0B8h+var_88], rax
0x180025834  test    rax, rax
0x180025837  jz      short loc_18002584A
0x180025839  lea     rdx, ProcName; "EvtIntCreateBinXMLFromCustomXML"
0x180025840  mov     rcx, rax; hModule
0x180025843  call    cs:__imp_GetProcAddress
0x180025849  nop
0x18002584a  mov     r9, rax; unsigned int (*)(unsigned int, const wchar_t *, unsigned int, unsigned int *, unsigned int, unsigned __int8 *, unsigned int *, struct _GUID *)
0x18002584d  lea     rcx, [rsp+0B8h+var_78]; this
0x180025852  call    ??0MANPARSE_INFO@@QEAA@P6AXPEBDJPEB_WII@Z_NP6AKK1KPEAKKPEAE4PEAU_GUID@@@Z@Z; MANPARSE_INFO::MANPARSE_INFO(void (*)(char const *,long,wchar_t const *,uint,uint),bool,ulong (*)(ulong,wchar_t const *,ulong,ulong *,ulong,uchar *,ulong *,_GUID *))
0x180025857  nop
0x180025858  test    r14b, r14b
0x18002585b  jz      short loc_180025893
0x18002585d  test    rsi, rsi
0x180025860  jnz     short loc_180025881
0x180025862  lea     rcx, [rsp+0B8h+var_78]; this
0x180025867  call    ??1MANPARSE_INFO@@QEAA@XZ; MANPARSE_INFO::~MANPARSE_INFO(void)
0x18002586c  nop
0x18002586d  lea     rcx, [rsp+0B8h+var_88]
0x180025872  call    ??1?$unique_ptr@XUFreeLibraryDeleter@@@std@@QEAA@XZ; std::unique_ptr<void,FreeLibraryDeleter>::~unique_ptr<void,FreeLibraryDeleter>(void)
0x180025877  mov     eax, 57h ; 'W'
0x18002587c  jmp     loc_18002598D
0x180025881  mov     r9d, r15d; unsigned int
0x180025884  mov     r8, rsi; void *
0x180025887  lea     rcx, [rsp+0B8h+var_78]; this
0x18002588c  call    ?ReadXmlBytes@MANPARSE_INFO@@QEAAJPEB_WPEBXK_N@Z; MANPARSE_INFO::ReadXmlBytes(wchar_t const *,void const *,ulong,bool)
0x180025891  jmp     short loc_1800258C4
0x180025893  test    rdi, rdi
0x180025896  jnz     short loc_1800258B7
0x180025898  lea     rcx, [rsp+0B8h+var_78]; this
0x18002589d  call    ??1MANPARSE_INFO@@QEAA@XZ; MANPARSE_INFO::~MANPARSE_INFO(void)
0x1800258a2  nop
0x1800258a3  lea     rcx, [rsp+0B8h+var_88]
0x1800258a8  call    ??1?$unique_ptr@XUFreeLibraryDeleter@@@std@@QEAA@XZ; std::unique_ptr<void,FreeLibraryDeleter>::~unique_ptr<void,FreeLibraryDeleter>(void)
0x1800258ad  mov     eax, 57h ; 'W'
0x1800258b2  jmp     loc_18002598D
0x1800258b7  mov     rdx, rdi; wchar_t *
0x1800258ba  lea     rcx, [rsp+0B8h+var_78]; this
0x1800258bf  call    ?ReadXmlFile@MANPARSE_INFO@@QEAAJPEB_W_N@Z; MANPARSE_INFO::ReadXmlFile(wchar_t const *,bool)
0x1800258c4  mov     edi, eax
0x1800258c6  test    eax, eax
0x1800258c8  jns     short loc_180025925
0x1800258ca  lea     rcx, [rsp+0B8h+var_78]; this
0x1800258cf  call    ??1MANPARSE_INFO@@QEAA@XZ; MANPARSE_INFO::~MANPARSE_INFO(void)
0x1800258d4  nop
0x1800258d5  cmp     edi, 80070003h
0x1800258db  jnz     short loc_1800258E7
0x1800258dd  mov     ebx, 3
0x1800258e2  jmp     loc_180025981
0x1800258e7  cmp     edi, 80070005h
0x1800258ed  jnz     short loc_1800258F9
0x1800258ef  mov     ebx, 5
0x1800258f4  jmp     loc_180025981
0x1800258f9  cmp     edi, 80070002h
0x1800258ff  jnz     short loc_180025908
0x180025901  mov     ebx, 2
0x180025906  jmp     short loc_180025981
0x180025908  cmp     edi, 8007000Eh
0x18002590e  jz      short loc_18002597C
0x180025910  mov     ebx, 5B9h
0x180025915  mov     eax, 32h ; '2'
0x18002591a  cmp     edi, 80070032h
0x180025920  cmovz   ebx, eax
0x180025923  jmp     short loc_180025981
0x180025925  mov     rdi, [rsp+0B8h+var_40]
0x18002592a  mov     rsi, [rsp+0B8h+var_38]
0x180025932  cmp     rdi, rsi
0x180025935  jz      short loc_18002596F
0x180025937  mov     rdx, [rdi]
0x18002593a  lea     rcx, [rsp+0B8h+var_78]
0x18002593f  cmp     dword ptr [rdx+110h], 0
0x180025946  jnz     short loc_180025951
0x180025948  call    LoadManifestProvider
0x18002594d  mov     ebx, eax
0x18002594f  jmp     short loc_180025958
0x180025951  call    LoadMofProvider
0x180025956  mov     ebx, eax
0x180025958  test    ebx, ebx
0x18002595a  jz      short loc_180025969
0x18002595c  lea     rcx, [rsp+0B8h+var_78]; this
0x180025961  call    ??1MANPARSE_INFO@@QEAA@XZ; MANPARSE_INFO::~MANPARSE_INFO(void)
0x180025966  nop
0x180025967  jmp     short loc_180025981
0x180025969  add     rdi, 8
0x18002596d  jmp     short loc_180025932
0x18002596f  lea     rcx, [rsp+0B8h+var_78]; this
0x180025974  call    ??1MANPARSE_INFO@@QEAA@XZ; MANPARSE_INFO::~MANPARSE_INFO(void)
0x180025979  nop
0x18002597a  jmp     short loc_180025981
0x18002597c  mov     ebx, 8
0x180025981  lea     rcx, [rsp+0B8h+var_88]
0x180025986  call    ??1?$unique_ptr@XUFreeLibraryDeleter@@@std@@QEAA@XZ; std::unique_ptr<void,FreeLibraryDeleter>::~unique_ptr<void,FreeLibraryDeleter>(void)
0x18002598b  mov     eax, ebx
0x18002598d  add     rsp, 90h
0x180025994  pop     r15
0x180025996  pop     r14
0x180025998  pop     rdi
0x180025999  pop     rsi
0x18002599a  pop     rbx
0x18002599b  retn
```
