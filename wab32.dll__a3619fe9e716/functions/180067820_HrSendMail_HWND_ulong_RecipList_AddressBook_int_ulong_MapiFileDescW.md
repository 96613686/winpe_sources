# HrSendMail(HWND__ *,ulong,_RecipList *,AddressBook *,int,ulong,MapiFileDescW *)

- ea: `0x180067820`
- end: `0x180067c01`
- name: `?HrSendMail@@YAJPEAUHWND__@@KPEAU_RecipList@@PEAVAddressBook@@HKPEAUMapiFileDescW@@@Z`
- size: `993`
- prototype: `__int64 __fastcall(HWND, unsigned int, struct _RecipList *, struct AddressBook *, int, unsigned int, HLOCAL hMem)`
- caller_count: `2`
- callee_count: `12`
- tags: `file_ops, loader_planting, service_task`

## callers

- `0x18003fec0`
- `0x180068840`

## callees

- `0x180002818`
- `0x1800189ec`
- `0x180033ae0`
- `0x180063438`
- `0x180064068`
- `0x180064250`
- `0x1800642b8`
- `0x180067820`
- `0x180069e24`
- `0x180091eaa`
- `0x180091ef0`
- `0x180093010`

## import_xrefs

- `KERNEL32!GetProfileIntW` at `0x1800678d8`
- `KERNEL32!GetProfileIntW` at `0x1800678d8`
- `KERNEL32!LocalAlloc` at `0x180067955`
- `KERNEL32!LocalAlloc` at `0x180067955`
- `KERNEL32!LocalFree` at `0x180067b0d`
- `KERNEL32!LocalFree` at `0x180067b7d`
- `KERNEL32!LocalFree` at `0x180067b0d`
- `KERNEL32!LocalFree` at `0x180067b7d`
- `KERNEL32!LoadLibraryW` at `0x1800678ea`
- `KERNEL32!LoadLibraryW` at `0x180067923`
- `KERNEL32!LoadLibraryW` at `0x1800678ea`
- `KERNEL32!LoadLibraryW` at `0x180067923`
- `KERNEL32!FreeLibrary` at `0x180067ad3`
- `KERNEL32!FreeLibrary` at `0x180067ad3`
- `KERNEL32!DeleteFileW` at `0x180067b41`
- `KERNEL32!DeleteFileW` at `0x180067b41`
- `KERNEL32!GetProcAddress` at `0x180067a20`
- `KERNEL32!GetProcAddress` at `0x180067a35`
- `KERNEL32!GetProcAddress` at `0x180067a20`
- `KERNEL32!GetProcAddress` at `0x180067a35`
- `ole32!CoTaskMemFree` at `0x180067b4c`
- `ole32!CoTaskMemFree` at `0x180067b60`
- `ole32!CoTaskMemFree` at `0x180067b4c`
- `ole32!CoTaskMemFree` at `0x180067b60`
- `USER32!AllowSetForegroundWindow` at `0x180067a52`
- `USER32!AllowSetForegroundWindow` at `0x180067a52`

## string_xrefs

- `0x1800678e3`: `mapi32.dll`

## pseudocode

```c
__int64 __fastcall HrSendMail(
        HWND a1,
        unsigned int a2,
        struct _RecipList *a3,
        struct AddressBook *a4,
        int a5,
        ULONG a6,
        struct $1BBD227ADE6B037C0858ED01E38A8D22 *hMem)
{
  struct _RecipList *v7; // rdi
  __int64 v8; // r13
  unsigned int v9; // edx
  FARPROC v10; // r15
  unsigned int v11; // edi
  __int64 v12; // rbx
  __int64 v13; // rax
  unsigned int v14; // edx
  HMODULE LibraryW; // rsi
  struct $3210F0496CC29B5EF5249245FB1E5930 *v16; // rbx
  __int64 v17; // rcx
  __int64 v18; // rdx
  FARPROC ProcAddress; // rdi
  bool v20; // r8
  unsigned int i; // esi
  __int64 v22; // rcx
  __int64 v23; // rsi
  PWSTR lpszFileName; // rcx
  HWND v25; // rcx
  int v26; // edx
  char v28; // [rsp+40h] [rbp-C0h]
  struct MapiMessage *Block; // [rsp+50h] [rbp-B0h] BYREF
  HLOCAL v31; // [rsp+58h] [rbp-A8h]
  __int64 v32; // [rsp+60h] [rbp-A0h]
  struct AddressBook *v33; // [rsp+68h] [rbp-98h] BYREF
  void *v34; // [rsp+70h] [rbp-90h] BYREF
  void *v35; // [rsp+78h] [rbp-88h] BYREF
  void *v36; // [rsp+80h] [rbp-80h] BYREF
  MapiMessageW v37; // [rsp+90h] [rbp-70h] BYREF
  WCHAR LibFileName[264]; // [rsp+F0h] [rbp-10h] BYREF

  v7 = a3;
  v8 = a2;
  v31 = a3;
  v33 = a4;
  memset_0(&v37, 0, sizeof(v37));
  v10 = 0;
  if ( !(_DWORD)v8 && !a6 )
  {
    v11 = 263040;
    goto LABEL_39;
  }
  FindWindowsMailPath(LibFileName, v9);
  v12 = -1;
  v28 = 0;
  v13 = -1;
  do
    ++v13;
  while ( LibFileName[v13] );
  if ( v13 && a5 )
  {
LABEL_14:
    LibraryW = LoadLibraryW(LibFileName);
    if ( LibraryW )
      goto LABEL_15;
LABEL_38:
    v11 = -2147221233;
    goto LABEL_39;
  }
  if ( GetProfileIntW(L"mail", L"mapi", 0) != 1 || (LibraryW = LoadLibraryW(L"mapi32.dll")) == 0 )
  {
    FindWindowsMailPath(LibFileName, v14);
    do
      ++v12;
    while ( LibFileName[v12] );
    if ( !v12 )
      goto LABEL_38;
    goto LABEL_14;
  }
  v28 = 1;
LABEL_15:
  v16 = 0;
  if ( (_DWORD)v8 )
  {
    v16 = (struct $3210F0496CC29B5EF5249245FB1E5930 *)LocalAlloc(0x40u, 40 * v8);
    if ( v7 )
    {
      do
      {
        v17 = (unsigned int)v10;
        v16[v17].ulRecipClass = 1;
        v16[v17].lpszName = *(PWSTR *)v7;
        v16[v17].lpszAddress = (PWSTR)*((_QWORD *)v7 + 1);
        v32 = v17 * 5;
        if ( IsWABEntryID(
               **((_DWORD **)v7 + 2),
               *(struct ENTRYID **)(*((_QWORD *)v7 + 2) + 8LL),
               &v36,
               &v35,
               &v34,
               (unsigned int *)&Block,
               0) == 4 )
        {
          v18 = v32;
          *(&v16->ulEIDSize + 2 * v32) = **((_DWORD **)v7 + 2);
          *((_QWORD *)&v16->lpEntryID + v18) = *(_QWORD *)(*((_QWORD *)v7 + 2) + 8LL);
        }
        v7 = (struct _RecipList *)*((_QWORD *)v7 + 3);
        LODWORD(v10) = (_DWORD)v10 + 1;
      }
      while ( v7 );
      v10 = 0;
    }
  }
  v37.nRecipCount = v8;
  v37.lpRecips = v16;
  if ( hMem && a6 )
  {
    v37.nFileCount = a6;
    v37.lpFiles = hMem;
  }
  if ( v28 )
  {
    ProcAddress = GetProcAddress(LibraryW, "MAPISendMailW");
  }
  else
  {
    ProcAddress = 0;
    v10 = GetProcAddress(LibraryW, "MAPISendMail");
    if ( v10 )
      goto LABEL_29;
  }
  if ( !ProcAddress )
  {
    v11 = -2147221233;
    goto LABEL_33;
  }
LABEL_29:
  AllowSetForegroundWindow(0xFFFFFFFF);
  if ( v28 )
  {
    LODWORD(v10) = 0;
    v11 = ((__int64 (__fastcall *)(_QWORD, HWND, MapiMessageW *, __int64, _DWORD))ProcAddress)(0, a1, &v37, 8, 0);
    goto LABEL_34;
  }
  Block = 0;
  v11 = ConvertMessageFromUnicode(&v37, &Block, v20);
  if ( (v11 & 0x80000000) == 0 )
  {
    v11 = ((__int64 (__fastcall *)(_QWORD, HWND, struct MapiMessage *, __int64, _DWORD))v10)(0, a1, Block, 8, 0);
    FreeMessage(Block);
  }
LABEL_33:
  LODWORD(v10) = 0;
LABEL_34:
  FreeLibrary(LibraryW);
  if ( v16 )
  {
    for ( i = 0; i < (unsigned int)v8; ++i )
    {
      v22 = i;
      v16[v22].lpszName = 0;
      v16[v22].lpszAddress = 0;
      LocalFreeAndNull(&v16[v22].lpEntryID);
    }
    LocalFree(v16);
  }
LABEL_39:
  if ( v31 )
    FreeLPRecipList(v31);
  if ( hMem && a6 )
  {
    v23 = 0;
    do
    {
      DeleteFileW(hMem[v23].lpszPathName);
      CoTaskMemFree(hMem[v23].lpszPathName);
      lpszFileName = hMem[v23].lpszFileName;
      hMem[v23].lpszPathName = 0;
      CoTaskMemFree(lpszFileName);
      LODWORD(v10) = (_DWORD)v10 + 1;
      hMem[v23++].lpszFileName = 0;
    }
    while ( (unsigned int)v10 < a6 );
    LocalFree(hMem);
  }
  OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(&v33);
  if ( v11 == -2147221233 )
  {
    v25 = a1;
    v26 = 4414;
LABEL_53:
    ShowMessageBox(v25, v26, 48);
    return v11;
  }
  if ( v11 != -2147221229 && v11 >= 2 )
  {
    v25 = a1;
    if ( v11 == 263040 )
      v26 = 4090;
    else
      v26 = 4291;
    goto LABEL_53;
  }
  return v11;
}

```

## disassembly

```asm
0x180067820  push    rbp
0x180067822  push    rbx
0x180067823  push    rsi
0x180067824  push    rdi
0x180067825  push    r12
0x180067827  push    r13
0x180067829  push    r14
0x18006782b  push    r15
0x18006782d  lea     rbp, [rsp-218h]
0x180067835  sub     rsp, 318h
0x18006783c  mov     rax, cs:__security_cookie
0x180067843  xor     rax, rsp
0x180067846  mov     [rbp+250h+var_50], rax
0x18006784d  mov     r14, [rbp+250h+hMem]
0x180067854  mov     rdi, r8
0x180067857  mov     r13d, edx
0x18006785a  xor     edx, edx; Val
0x18006785c  mov     [rsp+350h+var_2F8], r8
0x180067861  mov     [rsp+350h+hWnd], rcx
0x180067866  lea     rcx, [rbp+250h+var_2C0]; void *
0x18006786a  mov     [rsp+350h+var_2E8], r9
0x18006786f  lea     r8d, [rdx+60h]; Size
0x180067873  call    memset_0
0x180067878  mov     r12d, [rbp+250h+arg_28]
0x18006787f  xor     r15d, r15d
0x180067882  test    r13d, r13d
0x180067885  jnz     short loc_180067896
0x180067887  test    r12d, r12d
0x18006788a  jnz     short loc_180067896
0x18006788c  mov     edi, 40380h
0x180067891  jmp     loc_180067B1A
0x180067896  lea     rcx, [rbp+250h+LibFileName]; unsigned __int16 *
0x18006789a  call    ?FindWindowsMailPath@@YAXPEAGK@Z; FindWindowsMailPath(ushort *,ulong)
0x18006789f  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800678a3  mov     [rsp+350h+var_310], r15b
0x1800678a8  mov     rax, rbx
0x1800678ab  lea     rcx, [rbp+250h+LibFileName]
0x1800678af  inc     rax
0x1800678b2  cmp     [rcx+rax*2], r15w
0x1800678b7  jnz     short loc_1800678AF
0x1800678b9  test    rax, rax
0x1800678bc  jz      short loc_1800678C7
0x1800678be  cmp     [rbp+250h+arg_20], r15d
0x1800678c5  jnz     short loc_18006791F
0x1800678c7  xor     r8d, r8d; nDefault
0x1800678ca  lea     rdx, KeyName; "mapi"
0x1800678d1  lea     rcx, AppName; "mail"
0x1800678d8  call    cs:__imp_GetProfileIntW
0x1800678de  cmp     eax, 1
0x1800678e1  jnz     short loc_1800678FF
0x1800678e3  lea     rcx, aMapi32Dll; "mapi32.dll"
0x1800678ea  call    cs:__imp_LoadLibraryW
0x1800678f0  mov     rsi, rax
0x1800678f3  test    rax, rax
0x1800678f6  jz      short loc_1800678FF
0x1800678f8  mov     [rsp+350h+var_310], 1
0x1800678fd  jmp     short loc_180067935
0x1800678ff  lea     rcx, [rbp+250h+LibFileName]; unsigned __int16 *
0x180067903  call    ?FindWindowsMailPath@@YAXPEAGK@Z; FindWindowsMailPath(ushort *,ulong)
0x180067908  lea     rax, [rbp+250h+LibFileName]
0x18006790c  inc     rbx
0x18006790f  cmp     [rax+rbx*2], r15w
0x180067914  jnz     short loc_18006790C
0x180067916  test    rbx, rbx
0x180067919  jz      loc_180067B15
0x18006791f  lea     rcx, [rbp+250h+LibFileName]; lpLibFileName
0x180067923  call    cs:__imp_LoadLibraryW
0x180067929  mov     rsi, rax
0x18006792c  test    rax, rax
0x18006792f  jz      loc_180067B15
0x180067935  mov     rbx, r15
0x180067938  test    r13d, r13d
0x18006793b  jz      loc_1800679F5
0x180067941  lea     rdx, ds:0[r13*4]
0x180067949  mov     ecx, 40h ; '@'; uFlags
0x18006794e  add     rdx, r13
0x180067951  shl     rdx, 3; uBytes
0x180067955  call    cs:__imp_LocalAlloc
0x18006795b  mov     rbx, rax
0x18006795e  cmp     rdi, 0
0x180067962  jz      loc_1800679F5
0x180067968  mov     eax, r15d
0x18006796b  lea     r9, [rsp+350h+var_2D8]; void **
0x180067970  mov     [rsp+350h+var_320], 0; unsigned int *
0x180067979  lea     r8, [rbp+250h+var_2D0]; void **
0x18006797d  lea     rcx, [rax+rax*4]
0x180067981  mov     dword ptr [rbx+rcx*8+4], 1
0x180067989  mov     rax, [rdi]
0x18006798c  mov     [rbx+rcx*8+8], rax
0x180067991  mov     rax, [rdi+8]
0x180067995  mov     [rbx+rcx*8+10h], rax
0x18006799a  lea     rax, [rsp+350h+Block]
0x18006799f  mov     [rsp+350h+var_2F0], rcx
0x1800679a4  mov     rcx, [rdi+10h]
0x1800679a8  mov     [rsp+350h+var_328], rax; unsigned int *
0x1800679ad  lea     rax, [rsp+350h+var_2E0]
0x1800679b2  mov     [rsp+350h+var_330], rax; void **
0x1800679b7  mov     rdx, [rcx+8]; struct ENTRYID *
0x1800679bb  mov     ecx, [rcx]; unsigned int
0x1800679bd  call    ?IsWABEntryID@@YAEKPEAUENTRYID@@PEAPEAX11PEAK2@Z; IsWABEntryID(ulong,ENTRYID *,void * *,void * *,void * *,ulong *,ulong *)
0x1800679c2  cmp     al, 4
0x1800679c4  jnz     short loc_1800679E2
0x1800679c6  mov     rax, [rdi+10h]
0x1800679ca  mov     rdx, [rsp+350h+var_2F0]
0x1800679cf  mov     ecx, [rax]
0x1800679d1  mov     [rbx+rdx*8+18h], ecx
0x1800679d5  mov     rax, [rdi+10h]
0x1800679d9  mov     rcx, [rax+8]
0x1800679dd  mov     [rbx+rdx*8+20h], rcx
0x1800679e2  mov     rdi, [rdi+18h]
0x1800679e6  inc     r15d
0x1800679e9  test    rdi, rdi
0x1800679ec  jnz     loc_180067968
0x1800679f2  xor     r15d, r15d
0x1800679f5  mov     [rbp+250h+var_2C0.nRecipCount], r13d
0x1800679f9  mov     [rbp+250h+var_2C0.lpRecips], rbx
0x1800679fd  test    r14, r14
0x180067a00  jz      short loc_180067A0F
0x180067a02  test    r12d, r12d
0x180067a05  jz      short loc_180067A0F
0x180067a07  mov     [rbp+250h+var_2C0.nFileCount], r12d
0x180067a0b  mov     [rbp+250h+var_2C0.lpFiles], r14
0x180067a0f  mov     rcx, rsi; hModule
0x180067a12  cmp     [rsp+350h+var_310], r15b
0x180067a17  jz      short loc_180067A2B
0x180067a19  lea     rdx, aMapisendmailw; "MAPISendMailW"
0x180067a20  call    cs:__imp_GetProcAddress
0x180067a26  mov     rdi, rax
0x180067a29  jmp     short loc_180067A43
0x180067a2b  lea     rdx, aMapisendmail; "MAPISendMail"
0x180067a32  mov     rdi, r15
0x180067a35  call    cs:__imp_GetProcAddress
0x180067a3b  mov     r15, rax
0x180067a3e  test    rax, rax
0x180067a41  jnz     short loc_180067A4F
0x180067a43  test    rdi, rdi
0x180067a46  jnz     short loc_180067A4F
0x180067a48  mov     edi, 8004010Fh
0x180067a4d  jmp     short loc_180067ACD
0x180067a4f  or      ecx, 0FFFFFFFFh; dwProcessId
0x180067a52  call    cs:__imp_AllowSetForegroundWindow
0x180067a58  cmp     [rsp+350h+var_310], 0
0x180067a5d  jz      short loc_180067A82
0x180067a5f  mov     rdx, [rsp+350h+hWnd]
0x180067a64  lea     r8, [rbp+250h+var_2C0]
0x180067a68  xor     r15d, r15d
0x180067a6b  xor     ecx, ecx
0x180067a6d  mov     rax, rdi
0x180067a70  mov     dword ptr [rsp+350h+var_330], r15d
0x180067a75  lea     r9d, [r15+8]
0x180067a79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067a7e  mov     edi, eax
0x180067a80  jmp     short loc_180067AD0
0x180067a82  lea     rdx, [rsp+350h+Block]; struct MapiMessage **
0x180067a87  mov     [rsp+350h+Block], 0
0x180067a90  lea     rcx, [rbp+250h+var_2C0]; struct MapiMessageW *
0x180067a94  call    ?ConvertMessageFromUnicode@@YAJPEBUMapiMessageW@@PEAPEAUMapiMessage@@_N@Z; ConvertMessageFromUnicode(MapiMessageW const *,MapiMessage * *,bool)
0x180067a99  mov     edi, eax
0x180067a9b  test    eax, eax
0x180067a9d  js      short loc_180067ACD
0x180067a9f  mov     r8, [rsp+350h+Block]
0x180067aa4  mov     r9d, 8
0x180067aaa  mov     rdx, [rsp+350h+hWnd]
0x180067aaf  xor     ecx, ecx
0x180067ab1  mov     rax, r15
0x180067ab4  mov     dword ptr [rsp+350h+var_330], 0
0x180067abc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067ac1  mov     rcx, [rsp+350h+Block]; Block
0x180067ac6  mov     edi, eax
0x180067ac8  call    ?FreeMessage@@YAXPEAUMapiMessage@@@Z; FreeMessage(MapiMessage *)
0x180067acd  xor     r15d, r15d
0x180067ad0  mov     rcx, rsi; hLibModule
0x180067ad3  call    cs:__imp_FreeLibrary
0x180067ad9  test    rbx, rbx
0x180067adc  jz      short loc_180067B1A
0x180067ade  mov     esi, r15d
0x180067ae1  test    r13d, r13d
0x180067ae4  jz      short loc_180067B0A
0x180067ae6  mov     eax, esi
0x180067ae8  lea     rcx, [rax+rax*4]
0x180067aec  mov     [rbx+rcx*8+8], r15
0x180067af1  mov     [rbx+rcx*8+10h], r15
0x180067af6  lea     rcx, [rcx+4]
0x180067afa  lea     rcx, [rbx+rcx*8]; void **
0x180067afe  call    ?LocalFreeAndNull@@YAXPEAPEAX@Z; LocalFreeAndNull(void * *)
0x180067b03  inc     esi
0x180067b05  cmp     esi, r13d
0x180067b08  jb      short loc_180067AE6
0x180067b0a  mov     rcx, rbx; hMem
0x180067b0d  call    cs:__imp_LocalFree
0x180067b13  jmp     short loc_180067B1A
0x180067b15  mov     edi, 8004010Fh
0x180067b1a  mov     rax, [rsp+350h+var_2F8]
0x180067b1f  test    rax, rax
0x180067b22  jz      short loc_180067B2C
0x180067b24  mov     rcx, rax; hMem
0x180067b27  call    ?FreeLPRecipList@@YAXPEAU_RecipList@@@Z; FreeLPRecipList(_RecipList *)
0x180067b2c  test    r14, r14
0x180067b2f  jz      short loc_180067B83
0x180067b31  test    r12d, r12d
0x180067b34  jz      short loc_180067B83
0x180067b36  xor     esi, esi
0x180067b38  lea     rbx, [rsi+rsi*4]
0x180067b3c  mov     rcx, [r14+rbx*8+10h]; lpFileName
0x180067b41  call    cs:__imp_DeleteFileW
0x180067b47  mov     rcx, [r14+rbx*8+10h]; pv
0x180067b4c  call    cs:__imp_CoTaskMemFree
0x180067b52  mov     rcx, [r14+rbx*8+18h]; pv
0x180067b57  mov     qword ptr [r14+rbx*8+10h], 0
0x180067b60  call    cs:__imp_CoTaskMemFree
0x180067b66  inc     r15d
0x180067b69  mov     qword ptr [r14+rbx*8+18h], 0
0x180067b72  inc     rsi
0x180067b75  cmp     r15d, r12d
0x180067b78  jb      short loc_180067B38
0x180067b7a  mov     rcx, r14; hMem
0x180067b7d  call    cs:__imp_LocalFree
0x180067b83  lea     rcx, [rsp+350h+var_2E8]
0x180067b88  call    ??$OE_SafeReleaseAndNullPtr@UIOleInPlaceActiveObject@@@@YAXAEAPEAUIOleInPlaceActiveObject@@@Z; OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(IOleInPlaceActiveObject * &)
0x180067b8d  cmp     edi, 8004010Fh
0x180067b93  jz      short loc_180067BC7
0x180067b95  cmp     edi, 80040113h
0x180067b9b  jz      short loc_180067BDC
0x180067b9d  test    edi, edi
0x180067b9f  jz      short loc_180067BDC
0x180067ba1  cmp     edi, 1
0x180067ba4  jz      short loc_180067BDC
0x180067ba6  mov     rcx, [rsp+350h+hWnd]
0x180067bab  mov     r8d, 30h ; '0'
0x180067bb1  cmp     edi, 40380h
0x180067bb7  jz      short loc_180067BC0
0x180067bb9  mov     edx, 10C3h
0x180067bbe  jmp     short loc_180067BD7
0x180067bc0  mov     edx, 0FFAh
0x180067bc5  jmp     short loc_180067BD7
0x180067bc7  mov     rcx, [rsp+350h+hWnd]; hWnd
0x180067bcc  mov     edx, 113Eh; int
0x180067bd1  mov     r8d, 30h ; '0'; int
0x180067bd7  call    ?ShowMessageBox@@YAHPEAUHWND__@@HH@Z; ShowMessageBox(HWND__ *,int,int)
0x180067bdc  mov     eax, edi
0x180067bde  mov     rcx, [rbp+250h+var_50]
0x180067be5  xor     rcx, rsp; StackCookie
0x180067be8  call    __security_check_cookie
0x180067bed  add     rsp, 318h
0x180067bf4  pop     r15
0x180067bf6  pop     r14
0x180067bf8  pop     r13
0x180067bfa  pop     r12
0x180067bfc  pop     rdi
0x180067bfd  pop     rsi
0x180067bfe  pop     rbx
0x180067bff  pop     rbp
0x180067c00  retn
```
