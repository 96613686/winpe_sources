# Upgrade(void)

- ea: `0x18002ff20`
- end: `0x1800301e1`
- name: `?Upgrade@@YAJXZ`
- size: `705`
- prototype: `__int64(void)`
- caller_count: `0`
- callee_count: `13`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180002818`
- `0x1800045e4`
- `0x180005d08`
- `0x180009428`
- `0x180024b6c`
- `0x18002ff20`
- `0x1800421f8`
- `0x18006b400`
- `0x18006b620`
- `0x180075960`
- `0x180091eaa`
- `0x180091ef0`
- `0x180093010`

## import_xrefs

- `SHLWAPI!PathAppendW` at `0x1800300bd`
- `SHLWAPI!PathAppendW` at `0x1800300e7`
- `SHLWAPI!PathAppendW` at `0x1800300bd`
- `SHLWAPI!PathAppendW` at `0x1800300e7`
- `KERNEL32!GetLastError` at `0x180030062`
- `KERNEL32!GetLastError` at `0x180030181`
- `KERNEL32!GetLastError` at `0x180030062`
- `KERNEL32!GetLastError` at `0x180030181`
- `KERNEL32!FindFirstFileW` at `0x180030053`
- `KERNEL32!FindFirstFileW` at `0x180030053`
- `KERNEL32!FindClose` at `0x1800301ae`
- `KERNEL32!FindClose` at `0x1800301ae`
- `KERNEL32!FindNextFileW` at `0x1800300fd`
- `KERNEL32!FindNextFileW` at `0x1800300fd`
- `KERNEL32!MoveFileExW` at `0x180030120`
- `KERNEL32!MoveFileExW` at `0x180030120`

## pseudocode

```c
__int64 Upgrade(void)
{
  __int64 FirstFileW; // rdi
  unsigned int v1; // edx
  int v2; // r8d
  int LegacyWabPath; // eax
  unsigned __int64 v4; // rdx
  HRESULT ContactsFolderPath; // ebx
  bool v6; // zf
  LPWABOBJECT v7; // rsi
  LPADRBOOK v8; // r14
  char dwFileAttributes; // bl
  BOOL NextFileW; // r15d
  LPWABOBJECT pWABObject; // [rsp+30h] [rbp-D0h] BYREF
  LPADRBOOK pAdrBook; // [rsp+38h] [rbp-C8h] BYREF
  _QWORD v14[3]; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v15; // [rsp+58h] [rbp-A8h]
  int v16; // [rsp+5Ch] [rbp-A4h]
  WCHAR *v17; // [rsp+60h] [rbp-A0h]
  _BYTE v18[272]; // [rsp+70h] [rbp-90h] BYREF
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+180h] [rbp+80h] BYREF
  WCHAR NewFileName[264]; // [rsp+3D0h] [rbp+2D0h] BYREF
  unsigned __int16 v21[264]; // [rsp+5E0h] [rbp+4E0h] BYREF
  WCHAR pszPath[264]; // [rsp+7F0h] [rbp+6F0h] BYREF
  WCHAR FileName[264]; // [rsp+A00h] [rbp+900h] BYREF
  unsigned __int16 v24[264]; // [rsp+C10h] [rbp+B10h] BYREF

  FirstFileW = -1;
  memset_0(v21, 0, 0x208u);
  memset_0(v24, 0, 0x208u);
  memset_0(FileName, 0, 0x208u);
  memset_0(pszPath, 0, 0x208u);
  memset_0(NewFileName, 0, 0x208u);
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  pWABObject = 0;
  pAdrBook = 0;
  CComProtector::CComProtector((CComProtector *)v18);
  LegacyWabPath = GetLegacyWabPath(v21, v1, v2);
  ContactsFolderPath = LegacyWabPath;
  if ( LegacyWabPath == 1 )
    goto LABEL_17;
  if ( LegacyWabPath >= 0 )
  {
    ContactsFolderPath = GetContactsFolderPath(v24, v4);
    if ( ContactsFolderPath >= 0 )
    {
      ContactsFolderPath = StringCchPrintfW(FileName, 0x104u, L"%s*%s", v21, L".wab");
      if ( ContactsFolderPath >= 0 )
      {
        FirstFileW = (__int64)FindFirstFileW(FileName, &FindFileData);
        if ( FirstFileW == -1 )
        {
          v6 = GetLastError() == 2;
          goto LABEL_15;
        }
        ContactsFolderPath = WABOpen(&pAdrBook, &pWABObject, 0, 0);
        if ( ContactsFolderPath >= 0 )
        {
          v7 = pWABObject;
          v8 = pAdrBook;
          do
          {
            StringCchCopyW(pszPath, 0x104u, v21);
            PathAppendW(pszPath, FindFileData.cFileName);
            StringCchCopyW(NewFileName, 0x104u, v24);
            PathAppendW(NewFileName, FindFileData.cFileName);
            dwFileAttributes = FindFileData.dwFileAttributes;
            NextFileW = FindNextFileW((HANDLE)FirstFileW, &FindFileData);
            if ( (dwFileAttributes & 0x10) == 0 )
            {
              if ( MoveFileExW(pszPath, NewFileName, 2u) )
              {
                v14[0] = 40;
                v17 = NewFileName;
                v14[2] = 0;
                v16 = 0;
                v14[1] = v8;
                v15 = 0x80000000;
                ((void (__fastcall *)(LPWABOBJECT, _QWORD *))v7->lpVtbl->Import)(v7, v14);
              }
              else
              {
                HrGetLastError();
              }
            }
          }
          while ( NextFileW );
          v6 = GetLastError() == 18;
LABEL_15:
          if ( !v6 )
          {
            ContactsFolderPath = HrGetLastError();
            goto LABEL_18;
          }
LABEL_17:
          ContactsFolderPath = 0;
        }
      }
    }
  }
LABEL_18:
  OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(&pWABObject);
  OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(&pAdrBook);
  FindClose((HANDLE)FirstFileW);
  CComProtector::~CComProtector((CComProtector *)v18);
  return (unsigned int)ContactsFolderPath;
}

```

## disassembly

```asm
0x18002ff20  push    rbp
0x18002ff22  push    rbx
0x18002ff23  push    rsi
0x18002ff24  push    rdi
0x18002ff25  push    r13
0x18002ff27  push    r14
0x18002ff29  push    r15
0x18002ff2b  lea     rbp, [rsp-0D30h]
0x18002ff33  sub     rsp, 0E30h
0x18002ff3a  mov     rax, cs:__security_cookie
0x18002ff41  xor     rax, rsp
0x18002ff44  mov     [rbp+0D60h+var_40], rax
0x18002ff4b  mov     ebx, 208h
0x18002ff50  lea     rcx, [rbp+0D60h+var_880]; void *
0x18002ff57  mov     r8d, ebx; Size
0x18002ff5a  xor     edx, edx; Val
0x18002ff5c  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18002ff60  call    memset_0
0x18002ff65  mov     r8d, ebx; Size
0x18002ff68  lea     rcx, [rbp+0D60h+var_250]; void *
0x18002ff6f  xor     edx, edx; Val
0x18002ff71  call    memset_0
0x18002ff76  mov     r8d, ebx; Size
0x18002ff79  lea     rcx, [rbp+0D60h+FileName]; void *
0x18002ff80  xor     edx, edx; Val
0x18002ff82  call    memset_0
0x18002ff87  mov     r8d, ebx; Size
0x18002ff8a  lea     rcx, [rbp+0D60h+pszPath]; void *
0x18002ff91  xor     edx, edx; Val
0x18002ff93  call    memset_0
0x18002ff98  mov     r8d, ebx; Size
0x18002ff9b  lea     rcx, [rbp+0D60h+NewFileName]; void *
0x18002ffa2  xor     edx, edx; Val
0x18002ffa4  call    memset_0
0x18002ffa9  xor     edx, edx; Val
0x18002ffab  lea     r8d, [rbx+48h]; Size
0x18002ffaf  lea     rcx, [rbp+0D60h+FindFileData]; void *
0x18002ffb6  call    memset_0
0x18002ffbb  lea     rcx, [rsp+0E60h+var_DF0]; this
0x18002ffc0  mov     [rsp+0E60h+pWABObject], 0
0x18002ffc9  mov     [rsp+0E60h+pAdrBook], 0
0x18002ffd2  call    ??0CComProtector@@QEAA@XZ; CComProtector::CComProtector(void)
0x18002ffd7  lea     rcx, [rbp+0D60h+var_880]; unsigned __int16 *
0x18002ffde  call    ?GetLegacyWabPath@@YAJPEAGKH@Z; GetLegacyWabPath(ushort *,ulong,int)
0x18002ffe3  mov     ebx, eax
0x18002ffe5  cmp     eax, 1
0x18002ffe8  jz      loc_180030195
0x18002ffee  test    eax, eax
0x18002fff0  js      loc_180030197
0x18002fff6  lea     rcx, [rbp+0D60h+var_250]; unsigned __int16 *
0x18002fffd  call    ?GetContactsFolderPath@@YAJQEAG_K@Z; GetContactsFolderPath(ushort * const,unsigned __int64)
0x180030002  mov     ebx, eax
0x180030004  test    eax, eax
0x180030006  js      loc_180030197
0x18003000c  lea     rax, aWab; ".wab"
0x180030013  mov     r13d, 104h
0x180030019  mov     edx, r13d; unsigned __int64
0x18003001c  mov     [rsp+0E60h+var_E40], rax
0x180030021  lea     r9, [rbp+0D60h+var_880]
0x180030028  lea     r8, aSS_5; "%s*%s"
0x18003002f  lea     rcx, [rbp+0D60h+FileName]; unsigned __int16 *
0x180030036  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003003b  mov     ebx, eax
0x18003003d  test    eax, eax
0x18003003f  js      loc_180030197
0x180030045  lea     rdx, [rbp+0D60h+FindFileData]; lpFindFileData
0x18003004c  lea     rcx, [rbp+0D60h+FileName]; lpFileName
0x180030053  call    cs:__imp_FindFirstFileW
0x180030059  mov     rdi, rax
0x18003005c  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180030060  jnz     short loc_180030070
0x180030062  call    cs:__imp_GetLastError
0x180030068  cmp     eax, 2
0x18003006b  jmp     loc_18003018A
0x180030070  xor     r9d, r9d; Reserved2
0x180030073  lea     rdx, [rsp+0E60h+pWABObject]; lppWABObject
0x180030078  xor     r8d, r8d; lpWP
0x18003007b  lea     rcx, [rsp+0E60h+pAdrBook]; lppAdrBook
0x180030080  call    WABOpen
0x180030085  mov     ebx, eax
0x180030087  test    eax, eax
0x180030089  js      loc_180030197
0x18003008f  mov     rsi, [rsp+0E60h+pWABObject]
0x180030094  mov     r14, [rsp+0E60h+pAdrBook]
0x180030099  lea     r8, [rbp+0D60h+var_880]; unsigned __int16 *
0x1800300a0  mov     rdx, r13; unsigned __int64
0x1800300a3  lea     rcx, [rbp+0D60h+pszPath]; unsigned __int16 *
0x1800300aa  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800300af  lea     rdx, [rbp+0D60h+FindFileData.cFileName]; pszMore
0x1800300b6  lea     rcx, [rbp+0D60h+pszPath]; pszPath
0x1800300bd  call    cs:__imp_PathAppendW
0x1800300c3  lea     r8, [rbp+0D60h+var_250]; unsigned __int16 *
0x1800300ca  mov     rdx, r13; unsigned __int64
0x1800300cd  lea     rcx, [rbp+0D60h+NewFileName]; unsigned __int16 *
0x1800300d4  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800300d9  lea     rdx, [rbp+0D60h+FindFileData.cFileName]; pszMore
0x1800300e0  lea     rcx, [rbp+0D60h+NewFileName]; pszPath
0x1800300e7  call    cs:__imp_PathAppendW
0x1800300ed  mov     ebx, [rbp+0D60h+FindFileData.dwFileAttributes]
0x1800300f3  lea     rdx, [rbp+0D60h+FindFileData]; lpFindFileData
0x1800300fa  mov     rcx, rdi; hFindFile
0x1800300fd  call    cs:__imp_FindNextFileW
0x180030103  mov     r15d, eax
0x180030106  bt      ebx, 4
0x18003010a  jb      short loc_180030178
0x18003010c  mov     r8d, 2; dwFlags
0x180030112  lea     rdx, [rbp+0D60h+NewFileName]; lpNewFileName
0x180030119  lea     rcx, [rbp+0D60h+pszPath]; lpExistingFileName
0x180030120  call    cs:__imp_MoveFileExW
0x180030126  test    eax, eax
0x180030128  jnz     short loc_180030131
0x18003012a  call    ?HrGetLastError@@YAJXZ; HrGetLastError(void)
0x18003012f  jmp     short loc_180030178
0x180030131  lea     rax, [rbp+0D60h+NewFileName]
0x180030138  mov     [rsp+0E60h+var_E20], 28h ; '('
0x180030141  mov     [rsp+0E60h+var_E00], rax
0x180030146  lea     rdx, [rsp+0E60h+var_E20]
0x18003014b  mov     [rsp+0E60h+var_E10], 0
0x180030154  mov     rcx, rsi
0x180030157  mov     [rsp+0E60h+var_E04], 0
0x18003015f  mov     [rsp+0E60h+var_E18], r14
0x180030164  mov     [rsp+0E60h+var_E08], 80000000h
0x18003016c  mov     rax, [rsi]
0x18003016f  mov     rax, [rax+40h]
0x180030173  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030178  test    r15d, r15d
0x18003017b  jnz     loc_180030099
0x180030181  call    cs:__imp_GetLastError
0x180030187  cmp     eax, 12h
0x18003018a  jz      short loc_180030195
0x18003018c  call    ?HrGetLastError@@YAJXZ; HrGetLastError(void)
0x180030191  mov     ebx, eax
0x180030193  jmp     short loc_180030197
0x180030195  xor     ebx, ebx
0x180030197  lea     rcx, [rsp+0E60h+pWABObject]
0x18003019c  call    ??$OE_SafeReleaseAndNullPtr@UIOleInPlaceActiveObject@@@@YAXAEAPEAUIOleInPlaceActiveObject@@@Z; OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(IOleInPlaceActiveObject * &)
0x1800301a1  lea     rcx, [rsp+0E60h+pAdrBook]
0x1800301a6  call    ??$OE_SafeReleaseAndNullPtr@UIOleInPlaceActiveObject@@@@YAXAEAPEAUIOleInPlaceActiveObject@@@Z; OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(IOleInPlaceActiveObject * &)
0x1800301ab  mov     rcx, rdi; hFindFile
0x1800301ae  call    cs:__imp_FindClose
0x1800301b4  lea     rcx, [rsp+0E60h+var_DF0]; this
0x1800301b9  call    ??1CComProtector@@QEAA@XZ; CComProtector::~CComProtector(void)
0x1800301be  mov     eax, ebx
0x1800301c0  mov     rcx, [rbp+0D60h+var_40]
0x1800301c7  xor     rcx, rsp; StackCookie
0x1800301ca  call    __security_check_cookie
0x1800301cf  add     rsp, 0E30h
0x1800301d6  pop     r15
0x1800301d8  pop     r14
0x1800301da  pop     r13
0x1800301dc  pop     rdi
0x1800301dd  pop     rsi
0x1800301de  pop     rbx
0x1800301df  pop     rbp
0x1800301e0  retn
```
