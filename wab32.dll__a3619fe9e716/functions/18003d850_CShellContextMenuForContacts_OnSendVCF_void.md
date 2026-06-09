# CShellContextMenuForContacts::_OnSendVCF(void)

- ea: `0x18003d850`
- end: `0x18003db14`
- name: `?_OnSendVCF@CShellContextMenuForContacts@@EEAAJXZ`
- size: `708`
- prototype: `__int64 __fastcall(CShellContextMenuForContacts *__hidden this)`
- caller_count: `0`
- callee_count: `11`
- tags: `file_ops, loader_planting, service_task`

## callees

- `0x180002818`
- `0x18002ba38`
- `0x18003d084`
- `0x18003d25c`
- `0x18003d850`
- `0x180068464`
- `0x18006aa24`
- `0x180075960`
- `0x180091eaa`
- `0x180091ef0`
- `0x180093010`

## import_xrefs

- `SHLWAPI!PathRenameExtensionW` at `0x18003d9f5`
- `SHLWAPI!PathRenameExtensionW` at `0x18003d9f5`
- `SHLWAPI!SHStrDupW` at `0x18003da10`
- `SHLWAPI!SHStrDupW` at `0x18003da2b`
- `SHLWAPI!SHStrDupW` at `0x18003da10`
- `SHLWAPI!SHStrDupW` at `0x18003da2b`
- `KERNEL32!LocalAlloc` at `0x18003d8e1`
- `KERNEL32!LocalAlloc` at `0x18003d8e1`
- `KERNEL32!LocalFree` at `0x18003da83`
- `KERNEL32!LocalFree` at `0x18003da83`
- `KERNEL32!DeleteFileW` at `0x18003da5b`
- `KERNEL32!DeleteFileW` at `0x18003da5b`
- `ole32!CoTaskMemFree` at `0x18003da66`
- `ole32!CoTaskMemFree` at `0x18003da71`
- `ole32!CoTaskMemFree` at `0x18003da66`
- `ole32!CoTaskMemFree` at `0x18003da71`
- `ntdll!WinSqmIncrementDWORD` at `0x18003d88b`
- `ntdll!WinSqmIncrementDWORD` at `0x18003d88b`
- `iertutil!__imp_DPA_GetPtr` at `0x18003d9b0`
- `iertutil!__imp_DPA_GetPtr` at `0x18003d9b0`

## pseudocode

```c
__int64 __fastcall CShellContextMenuForContacts::_OnSendVCF(CShellContextMenuForContacts *this)
{
  HRESULT MapiProp; // edi
  struct MapiFileDescW *v3; // r14
  unsigned int i; // ebx
  unsigned int v5; // eax
  HWND v6; // rdx
  struct IAddrBook *v7; // rcx
  const unsigned __int16 *Ptr; // rax
  unsigned __int64 v9; // r9
  unsigned int j; // r15d
  struct IMAPIProp *v12; // [rsp+30h] [rbp-D0h] BYREF
  LPADRBOOK pAdrBook; // [rsp+38h] [rbp-C8h] BYREF
  LPWABOBJECT pWABObject; // [rsp+40h] [rbp-C0h] BYREF
  struct IMailUser *v15; // [rsp+48h] [rbp-B8h] BYREF
  WCHAR psz[264]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR pszPath[264]; // [rsp+260h] [rbp+160h] BYREF

  WinSqmIncrementDWORD(0, 7236, 1);
  pWABObject = 0;
  pAdrBook = 0;
  v12 = 0;
  MapiProp = 0;
  v15 = 0;
  memset_0(psz, 0, 0x208u);
  memset_0(pszPath, 0, 0x208u);
  v3 = (struct MapiFileDescW *)LocalAlloc(0x40u, 40LL * *((unsigned int *)this + 10));
  if ( v3 )
  {
    MapiProp = WABOpen(&pAdrBook, &pWABObject, 0, 0);
    if ( MapiProp < 0 )
      goto LABEL_18;
    for ( i = 0; ; ++i )
    {
      v5 = *((_DWORD *)this + 10);
      if ( i >= v5 )
        break;
      OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(&v12);
      MapiProp = CShellContextMenuBase::_GetMapiProp(this, pAdrBook, i, &v12);
      if ( MapiProp < 0 )
        goto LABEL_18;
      MapiProp = ((__int64 (__fastcall *)(struct IMAPIProp *, GUID *, struct IMailUser **))v12->lpVtbl->QueryInterface)(
                   v12,
                   &IID_IMailUser,
                   &v15);
      if ( MapiProp < 0 )
        goto LABEL_18;
      MapiProp = GetTempFilePath(psz);
      if ( MapiProp < 0 )
        goto LABEL_18;
      MapiProp = VCardCreate(v7, v6, 8u, psz, v15);
      if ( MapiProp < 0 )
        goto LABEL_18;
      Ptr = (const unsigned __int16 *)DPA_GetPtr(*((HDPA *)this + 3), i);
      if ( !Ptr )
      {
        MapiProp = -2147418113;
        goto LABEL_18;
      }
      v9 = -1;
      do
        ++v9;
      while ( Ptr[v9] );
      MapiProp = StringCchCopyNW(pszPath, 0x104u, Ptr, v9);
      if ( MapiProp < 0 )
        goto LABEL_18;
      if ( !PathRenameExtensionW(pszPath, L".vcf") )
      {
        MapiProp = -2147467259;
        goto LABEL_18;
      }
      MapiProp = SHStrDupW(psz, &v3[i].lpszPathName);
      if ( MapiProp < 0 )
        goto LABEL_18;
      MapiProp = SHStrDupW(pszPath, &v3[i].lpszFileName);
      if ( MapiProp < 0 )
        goto LABEL_18;
    }
    MapiProp = HrStartMailThread(0, 0, 0, 0, v5, v3);
    if ( MapiProp < 0 )
    {
LABEL_18:
      for ( j = 0; j < *((_DWORD *)this + 10); ++j )
      {
        DeleteFileW(v3[j].lpszPathName);
        CoTaskMemFree(v3[j].lpszPathName);
        CoTaskMemFree(v3[j].lpszFileName);
      }
      LocalFree(v3);
    }
    else
    {
      MapiProp = 0;
    }
  }
  OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(&pWABObject);
  OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(&pAdrBook);
  OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(&pWABObject);
  OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(&v15);
  OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(&v12);
  return (unsigned int)MapiProp;
}

```

## disassembly

```asm
0x18003d850  push    rbp
0x18003d852  push    rbx
0x18003d853  push    rsi
0x18003d854  push    rdi
0x18003d855  push    r12
0x18003d857  push    r13
0x18003d859  push    r14
0x18003d85b  push    r15
0x18003d85d  lea     rbp, [rsp-388h]
0x18003d865  sub     rsp, 488h
0x18003d86c  mov     rax, cs:__security_cookie
0x18003d873  xor     rax, rsp
0x18003d876  mov     [rbp+3C0h+var_50], rax
0x18003d87d  mov     r13, rcx
0x18003d880  mov     edx, 1C44h
0x18003d885  xor     ecx, ecx
0x18003d887  lea     r8d, [rcx+1]
0x18003d88b  call    cs:__imp_WinSqmIncrementDWORD
0x18003d891  xor     r12d, r12d
0x18003d894  lea     rcx, [rsp+4C0h+psz]; void *
0x18003d899  mov     ebx, 208h
0x18003d89e  mov     [rsp+4C0h+pWABObject], r12
0x18003d8a3  mov     r8d, ebx; Size
0x18003d8a6  mov     [rsp+4C0h+pAdrBook], r12
0x18003d8ab  xor     edx, edx; Val
0x18003d8ad  mov     [rsp+4C0h+var_490], r12
0x18003d8b2  mov     edi, r12d
0x18003d8b5  mov     [rsp+4C0h+var_478], r12
0x18003d8ba  call    memset_0
0x18003d8bf  mov     r8d, ebx; Size
0x18003d8c2  lea     rcx, [rbp+3C0h+pszPath]; void *
0x18003d8c9  xor     edx, edx; Val
0x18003d8cb  call    memset_0
0x18003d8d0  mov     eax, [r13+28h]
0x18003d8d4  lea     ecx, [r12+40h]; uFlags
0x18003d8d9  lea     rdx, [rax+rax*4]
0x18003d8dd  shl     rdx, 3; uBytes
0x18003d8e1  call    cs:__imp_LocalAlloc
0x18003d8e7  mov     r14, rax
0x18003d8ea  test    rax, rax
0x18003d8ed  jz      loc_18003DA89
0x18003d8f3  xor     r9d, r9d; Reserved2
0x18003d8f6  lea     rdx, [rsp+4C0h+pWABObject]; lppWABObject
0x18003d8fb  xor     r8d, r8d; lpWP
0x18003d8fe  lea     rcx, [rsp+4C0h+pAdrBook]; lppAdrBook
0x18003d903  call    WABOpen
0x18003d908  mov     edi, eax
0x18003d90a  test    eax, eax
0x18003d90c  js      loc_18003DA43
0x18003d912  mov     ebx, r12d
0x18003d915  mov     eax, [r13+28h]
0x18003d919  cmp     ebx, eax
0x18003d91b  jnb     loc_18003DAEA
0x18003d921  lea     rcx, [rsp+4C0h+var_490]
0x18003d926  call    ??$OE_SafeReleaseAndNullPtr@UIOleInPlaceActiveObject@@@@YAXAEAPEAUIOleInPlaceActiveObject@@@Z; OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(IOleInPlaceActiveObject * &)
0x18003d92b  mov     rdx, [rsp+4C0h+pAdrBook]; struct IAddrBook *
0x18003d930  lea     r9, [rsp+4C0h+var_490]; struct IMAPIProp **
0x18003d935  mov     r8d, ebx; unsigned int
0x18003d938  mov     rcx, r13; this
0x18003d93b  call    ?_GetMapiProp@CShellContextMenuBase@@IEAAJPEAUIAddrBook@@IPEAPEAUIMAPIProp@@@Z; CShellContextMenuBase::_GetMapiProp(IAddrBook *,uint,IMAPIProp * *)
0x18003d940  mov     edi, eax
0x18003d942  test    eax, eax
0x18003d944  js      loc_18003DA43
0x18003d94a  mov     rcx, [rsp+4C0h+var_490]
0x18003d94f  lea     r8, [rsp+4C0h+var_478]
0x18003d954  lea     rdx, IID_IMailUser
0x18003d95b  mov     rax, [rcx]
0x18003d95e  mov     rax, [rax]
0x18003d961  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d966  mov     edi, eax
0x18003d968  test    eax, eax
0x18003d96a  js      loc_18003DA43
0x18003d970  lea     rcx, [rsp+4C0h+psz]; lpTempFileName
0x18003d975  call    _GetTempFilePath
0x18003d97a  mov     edi, eax
0x18003d97c  test    eax, eax
0x18003d97e  js      loc_18003DA43
0x18003d984  mov     rax, [rsp+4C0h+var_478]
0x18003d989  lea     r9, [rsp+4C0h+psz]; unsigned __int16 *
0x18003d98e  mov     r8d, 8; unsigned int
0x18003d994  mov     [rsp+4C0h+var_4A0], rax; struct IMailUser *
0x18003d999  call    ?VCardCreate@@YAJPEAUIAddrBook@@PEAUHWND__@@KPEBGPEAUIMailUser@@@Z; VCardCreate(IAddrBook *,HWND__ *,ulong,ushort const *,IMailUser *)
0x18003d99e  mov     edi, eax
0x18003d9a0  test    eax, eax
0x18003d9a2  js      loc_18003DA43
0x18003d9a8  mov     rcx, [r13+18h]; hdpa
0x18003d9ac  mov     edx, ebx; i
0x18003d9ae  mov     esi, ebx
0x18003d9b0  call    cs:__imp_DPA_GetPtr
0x18003d9b6  test    rax, rax
0x18003d9b9  jz      loc_18003DAE0
0x18003d9bf  or      r9, 0FFFFFFFFFFFFFFFFh
0x18003d9c3  inc     r9; unsigned __int64
0x18003d9c6  cmp     [rax+r9*2], r12w
0x18003d9cb  jnz     short loc_18003D9C3
0x18003d9cd  mov     r8, rax; unsigned __int16 *
0x18003d9d0  lea     rcx, [rbp+3C0h+pszPath]; unsigned __int16 *
0x18003d9d7  mov     edx, 104h; unsigned __int64
0x18003d9dc  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x18003d9e1  mov     edi, eax
0x18003d9e3  test    eax, eax
0x18003d9e5  js      short loc_18003DA43
0x18003d9e7  lea     rdx, pszExt; ".vcf"
0x18003d9ee  lea     rcx, [rbp+3C0h+pszPath]; pszPath
0x18003d9f5  call    cs:__imp_PathRenameExtensionW
0x18003d9fb  test    eax, eax
0x18003d9fd  jz      short loc_18003DA3E
0x18003d9ff  lea     rsi, [rsi+rsi*4]
0x18003da03  lea     rdx, [r14+10h]
0x18003da07  lea     rdx, [rdx+rsi*8]; ppwsz
0x18003da0b  lea     rcx, [rsp+4C0h+psz]; psz
0x18003da10  call    cs:__imp_SHStrDupW
0x18003da16  mov     edi, eax
0x18003da18  test    eax, eax
0x18003da1a  js      short loc_18003DA43
0x18003da1c  lea     rdx, [r14+18h]
0x18003da20  lea     rdx, [rdx+rsi*8]; ppwsz
0x18003da24  lea     rcx, [rbp+3C0h+pszPath]; psz
0x18003da2b  call    cs:__imp_SHStrDupW
0x18003da31  mov     edi, eax
0x18003da33  test    eax, eax
0x18003da35  js      short loc_18003DA43
0x18003da37  inc     ebx
0x18003da39  jmp     loc_18003D915
0x18003da3e  mov     edi, 80004005h
0x18003da43  mov     rsi, r14
0x18003da46  mov     r15d, r12d
0x18003da49  cmp     [r13+28h], r12d
0x18003da4d  jbe     short loc_18003DA80
0x18003da4f  mov     eax, r15d
0x18003da52  lea     rbx, [rax+rax*4]
0x18003da56  mov     rcx, [rsi+rbx*8+10h]; lpFileName
0x18003da5b  call    cs:__imp_DeleteFileW
0x18003da61  mov     rcx, [rsi+rbx*8+10h]; pv
0x18003da66  call    cs:__imp_CoTaskMemFree
0x18003da6c  mov     rcx, [rsi+rbx*8+18h]; pv
0x18003da71  call    cs:__imp_CoTaskMemFree
0x18003da77  inc     r15d
0x18003da7a  cmp     r15d, [r13+28h]
0x18003da7e  jb      short loc_18003DA4F
0x18003da80  mov     rcx, r14; hMem
0x18003da83  call    cs:__imp_LocalFree
0x18003da89  lea     rcx, [rsp+4C0h+pWABObject]
0x18003da8e  call    ??$OE_SafeReleaseAndNullPtr@UIOleInPlaceActiveObject@@@@YAXAEAPEAUIOleInPlaceActiveObject@@@Z; OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(IOleInPlaceActiveObject * &)
0x18003da93  lea     rcx, [rsp+4C0h+pAdrBook]
0x18003da98  call    ??$OE_SafeReleaseAndNullPtr@UIOleInPlaceActiveObject@@@@YAXAEAPEAUIOleInPlaceActiveObject@@@Z; OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(IOleInPlaceActiveObject * &)
0x18003da9d  lea     rcx, [rsp+4C0h+pWABObject]
0x18003daa2  call    ??$OE_SafeReleaseAndNullPtr@UIOleInPlaceActiveObject@@@@YAXAEAPEAUIOleInPlaceActiveObject@@@Z; OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(IOleInPlaceActiveObject * &)
0x18003daa7  lea     rcx, [rsp+4C0h+var_478]
0x18003daac  call    ??$OE_SafeReleaseAndNullPtr@UIOleInPlaceActiveObject@@@@YAXAEAPEAUIOleInPlaceActiveObject@@@Z; OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(IOleInPlaceActiveObject * &)
0x18003dab1  lea     rcx, [rsp+4C0h+var_490]
0x18003dab6  call    ??$OE_SafeReleaseAndNullPtr@UIOleInPlaceActiveObject@@@@YAXAEAPEAUIOleInPlaceActiveObject@@@Z; OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(IOleInPlaceActiveObject * &)
0x18003dabb  mov     eax, edi
0x18003dabd  mov     rcx, [rbp+3C0h+var_50]
0x18003dac4  xor     rcx, rsp; StackCookie
0x18003dac7  call    __security_check_cookie
0x18003dacc  add     rsp, 488h
0x18003dad3  pop     r15
0x18003dad5  pop     r14
0x18003dad7  pop     r13
0x18003dad9  pop     r12
0x18003dadb  pop     rdi
0x18003dadc  pop     rsi
0x18003dadd  pop     rbx
0x18003dade  pop     rbp
0x18003dadf  retn
0x18003dae0  mov     edi, 8000FFFFh
0x18003dae5  jmp     loc_18003DA43
0x18003daea  mov     [rsp+4C0h+var_498], r14; struct MapiFileDescW *
0x18003daef  xor     r9d, r9d; int
0x18003daf2  xor     r8d, r8d; struct _RecipList *
0x18003daf5  mov     dword ptr [rsp+4C0h+var_4A0], eax; unsigned int
0x18003daf9  xor     edx, edx; unsigned int
0x18003dafb  xor     ecx, ecx; hWnd
0x18003dafd  call    ?HrStartMailThread@@YAJPEAUHWND__@@KPEAU_RecipList@@HKPEAUMapiFileDescW@@@Z; HrStartMailThread(HWND__ *,ulong,_RecipList *,int,ulong,MapiFileDescW *)
0x18003db02  mov     edi, eax
0x18003db04  test    eax, eax
0x18003db06  js      loc_18003DA43
0x18003db0c  mov     edi, r12d
0x18003db0f  jmp     loc_18003DA89
```
