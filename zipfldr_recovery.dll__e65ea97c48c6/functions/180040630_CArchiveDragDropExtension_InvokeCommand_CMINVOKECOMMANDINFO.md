# CArchiveDragDropExtension::InvokeCommand(_CMINVOKECOMMANDINFO *)

- ea: `0x180040630`
- end: `0x1800407a6`
- name: `?InvokeCommand@CArchiveDragDropExtension@@UEAAJPEAU_CMINVOKECOMMANDINFO@@@Z`
- size: `374`
- prototype: `__int64 __fastcall(CArchiveDragDropExtension *__hidden this, struct _CMINVOKECOMMANDINFO *)`
- caller_count: `0`
- callee_count: `5`
- tags: `reparse_path, loader_planting, service_task, broker_com_uri`

## callees

- `0x18001f680`
- `0x180027388`
- `0x180036f50`
- `0x180040630`
- `0x180071010`

## import_xrefs

- `SHELL32!SHCreateShellItemArrayFromDataObject` at `0x1800406a4`
- `SHELL32!SHCreateShellItemArrayFromDataObject` at `0x1800406a4`
- `SHLWAPI!PathFindFileNameW` at `0x18004072e`
- `SHLWAPI!PathFindFileNameW` at `0x18004072e`
- `SHLWAPI!PathCombineW` at `0x180040740`
- `SHLWAPI!PathCombineW` at `0x180040740`
- `SHLWAPI!__imp_StrCmpICA` at `0x18004067f`
- `SHLWAPI!__imp_StrCmpICA` at `0x18004067f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004075c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004075c`

## pseudocode

```c
__int64 __fastcall CArchiveDragDropExtension::InvokeCommand(
        CArchiveDragDropExtension *this,
        struct _CMINVOKECOMMANDINFO *a2)
{
  HRESULT ZipFile; // esi
  const CHAR *lpVerb; // rcx
  bool v5; // zf
  IDataObject *v6; // rcx
  unsigned int v7; // r14d
  int ItemZipFilePath; // ebx
  const WCHAR *FileNameW; // rax
  LPCWSTR pszPath; // [rsp+20h] [rbp-E0h] BYREF
  void *ppv; // [rsp+28h] [rbp-D8h] BYREF
  struct IShellItem *v13; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v14; // [rsp+38h] [rbp-C8h] BYREF
  WCHAR pszDest[264]; // [rsp+40h] [rbp-C0h] BYREF

  ZipFile = -2147467259;
  lpVerb = a2->lpVerb;
  if ( (unsigned __int64)lpVerb >= 0x10000 )
    v5 = StrCmpICA(lpVerb, "extract") == 0;
  else
    v5 = (_WORD)lpVerb == 0;
  if ( v5 )
  {
    v6 = (IDataObject *)*((_QWORD *)this + 3);
    ppv = 0;
    ZipFile = SHCreateShellItemArrayFromDataObject(v6, &GUID_b63ea76d_1f85_456f_a19c_48159efa858b, &ppv);
    if ( ZipFile >= 0 )
    {
      v14 = 0;
      (*(void (__fastcall **)(void *, unsigned int *))(*(_QWORD *)ppv + 56LL))(ppv, &v14);
      v7 = 0;
      do
      {
        if ( v7 >= v14 )
          break;
        pszPath = 0;
        v13 = 0;
        if ( (*(int (__fastcall **)(void *, _QWORD, struct IShellItem **))(*(_QWORD *)ppv + 64LL))(ppv, v7, &v13) >= 0 )
        {
          ItemZipFilePath = _GetItemZipFilePath(v13, (unsigned __int16 **)&pszPath);
          ((void (__fastcall *)(struct IShellItem *))v13->lpVtbl->Release)(v13);
          if ( ItemZipFilePath >= 0 )
          {
            FileNameW = PathFindFileNameW(pszPath);
            PathCombineW(pszDest, *((LPCWSTR *)this + 4), FileNameW);
            ZipFile = ExtractZipFile(pszPath, pszDest);
            CoTaskMemFree((LPVOID)pszPath);
          }
        }
        ++v7;
      }
      while ( ZipFile >= 0 );
      (*(void (__fastcall **)(void *))(*(_QWORD *)ppv + 16LL))(ppv);
    }
  }
  return (unsigned int)ZipFile;
}

```

## disassembly

```asm
0x180040630  mov     [rsp-8+arg_10], rbx
0x180040635  push    rbp
0x180040636  push    rsi
0x180040637  push    rdi
0x180040638  push    r14
0x18004063a  push    r15
0x18004063c  lea     rbp, [rsp-160h]
0x180040644  sub     rsp, 260h
0x18004064b  mov     rax, cs:__security_cookie
0x180040652  xor     rax, rsp
0x180040655  mov     [rbp+180h+var_30], rax
0x18004065c  mov     r15, rcx
0x18004065f  mov     esi, 80004005h
0x180040664  mov     rcx, [rdx+10h]; pszStr1
0x180040668  cmp     rcx, 10000h
0x18004066f  jnb     short loc_180040678
0x180040671  xor     edi, edi
0x180040673  cmp     cx, di
0x180040676  jmp     short loc_180040689
0x180040678  lea     rdx, aExtract_0; "extract"
0x18004067f  call    cs:__imp_StrCmpICA
0x180040685  xor     edi, edi
0x180040687  test    eax, eax
0x180040689  jnz     loc_18004077E
0x18004068f  mov     rcx, [r15+18h]; pdo
0x180040693  lea     r8, [rsp+280h+ppv]; ppv
0x180040698  lea     rdx, _GUID_b63ea76d_1f85_456f_a19c_48159efa858b; riid
0x18004069f  mov     [rsp+280h+ppv], rdi
0x1800406a4  call    cs:__imp_SHCreateShellItemArrayFromDataObject
0x1800406aa  mov     esi, eax
0x1800406ac  test    eax, eax
0x1800406ae  js      loc_18004077E
0x1800406b4  mov     rcx, [rsp+280h+ppv]
0x1800406b9  mov     [rsp+280h+var_248], edi
0x1800406bd  mov     rdx, [rcx]
0x1800406c0  mov     rax, [rdx+38h]
0x1800406c4  lea     rdx, [rsp+280h+var_248]
0x1800406c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800406ce  mov     r14d, edi
0x1800406d1  cmp     r14d, [rsp+280h+var_248]
0x1800406d6  jnb     loc_18004076D
0x1800406dc  mov     rcx, [rsp+280h+ppv]
0x1800406e1  lea     r8, [rsp+280h+var_250]
0x1800406e6  mov     [rsp+280h+pszPath], rdi
0x1800406eb  mov     edx, r14d
0x1800406ee  mov     [rsp+280h+var_250], rdi
0x1800406f3  mov     rax, [rcx]
0x1800406f6  mov     rax, [rax+40h]
0x1800406fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800406ff  test    eax, eax
0x180040701  js      short loc_180040762
0x180040703  mov     rcx, [rsp+280h+var_250]; struct IShellItem *
0x180040708  lea     rdx, [rsp+280h+pszPath]; unsigned __int16 **
0x18004070d  call    ?_GetItemZipFilePath@@YAJPEAUIShellItem@@PEAPEAG@Z; _GetItemZipFilePath(IShellItem *,ushort * *)
0x180040712  mov     rcx, [rsp+280h+var_250]
0x180040717  mov     ebx, eax
0x180040719  mov     rdx, [rcx]
0x18004071c  mov     rax, [rdx+10h]
0x180040720  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040725  test    ebx, ebx
0x180040727  js      short loc_180040762
0x180040729  mov     rcx, [rsp+280h+pszPath]; pszPath
0x18004072e  call    cs:__imp_PathFindFileNameW
0x180040734  mov     rdx, [r15+20h]; pszDir
0x180040738  lea     rcx, [rsp+280h+pszDest]; pszDest
0x18004073d  mov     r8, rax; pszFile
0x180040740  call    cs:__imp_PathCombineW
0x180040746  mov     rcx, [rsp+280h+pszPath]; unsigned __int16 *
0x18004074b  lea     rdx, [rsp+280h+pszDest]; unsigned __int16 *
0x180040750  call    ?ExtractZipFile@@YAJPEBG0@Z; ExtractZipFile(ushort const *,ushort const *)
0x180040755  mov     rcx, [rsp+280h+pszPath]; pv
0x18004075a  mov     esi, eax
0x18004075c  call    cs:__imp_CoTaskMemFree
0x180040762  inc     r14d
0x180040765  test    esi, esi
0x180040767  jns     loc_1800406D1
0x18004076d  mov     rcx, [rsp+280h+ppv]
0x180040772  mov     rax, [rcx]
0x180040775  mov     rax, [rax+10h]
0x180040779  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004077e  mov     eax, esi
0x180040780  mov     rcx, [rbp+180h+var_30]
0x180040787  xor     rcx, rsp; StackCookie
0x18004078a  call    __security_check_cookie
0x18004078f  mov     rbx, [rsp+280h+arg_10]
0x180040797  add     rsp, 260h
0x18004079e  pop     r15
0x1800407a0  pop     r14
0x1800407a2  pop     rdi
0x1800407a3  pop     rsi
0x1800407a4  pop     rbp
0x1800407a5  retn
```
