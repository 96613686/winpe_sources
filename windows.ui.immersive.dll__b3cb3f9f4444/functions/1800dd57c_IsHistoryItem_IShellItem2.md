# _IsHistoryItem(IShellItem2 *)

- ea: `0x1800dd57c`
- end: `0x1800dd723`
- name: `?_IsHistoryItem@@YA_NPEAUIShellItem2@@@Z`
- size: `423`
- prototype: `bool __fastcall(struct IShellItem2 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800dd360`

## callees

- `0x18000af00`
- `0x18001b760`
- `0x180054130`
- `0x1800dd57c`
- `0x1800ed010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800dd622`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800dd6e3`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800dd622`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800dd6e3`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800dd674`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800dd674`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindExtensionW` at `0x1800dd5fe`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindExtensionW` at `0x1800dd5fe`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x1800dd6c5`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x1800dd6c5`

## pseudocode

```c
bool __fastcall _IsHistoryItem(struct IShellItem2 *a1)
{
  struct IShellItem2Vtbl *lpVtbl; // rax
  bool v3; // si
  HRESULT (__stdcall *GetDisplayName)(IShellItem2 *, SIGDN, LPWSTR *); // rbx
  const WCHAR *ExtensionW; // rax
  int ValueW; // eax
  bool v7; // sf
  WCHAR v8; // cx
  const WCHAR *FileNameW; // rax
  DWORD pcbData; // [rsp+40h] [rbp-C0h] BYREF
  LPCWSTR pszPath; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v13; // [rsp+50h] [rbp-B0h]
  __int64 v14; // [rsp+58h] [rbp-A8h]
  WCHAR String2[264]; // [rsp+60h] [rbp-A0h] BYREF

  lpVtbl = a1->lpVtbl;
  pszPath = 0;
  v13 = 0;
  v3 = 0;
  v14 = 0;
  GetDisplayName = lpVtbl->GetDisplayName;
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&pszPath);
  v13 = -1;
  v14 = -1;
  if ( ((int (__fastcall *)(struct IShellItem2 *, __int64, LPCWSTR *))GetDisplayName)(a1, 2147844096LL, &pszPath) < 0 )
    goto LABEL_12;
  ExtensionW = PathFindExtensionW(pszPath);
  if ( CompareStringOrdinal(ExtensionW, -1, L".accountpicture-ms", -1, 1) != 2 )
    goto LABEL_12;
  pcbData = 520;
  v3 = 1;
  ValueW = RegGetValueW(
             HKEY_CURRENT_USER,
             L"Software\\Microsoft\\Windows\\CurrentVersion\\AccountPicture",
             L"SourceId",
             2u,
             0,
             String2,
             &pcbData);
  v7 = ValueW < 0;
  if ( !ValueW )
  {
    v8 = String2[0];
    goto LABEL_7;
  }
  v8 = 0;
  String2[0] = 0;
  if ( ValueW > 0 )
  {
    ValueW = (unsigned __int16)ValueW | 0x80070000;
LABEL_7:
    v7 = ValueW < 0;
  }
  if ( !v7 && v8 && (int)StringCchCatW(String2, 0x104u, L".accountpicture-ms") >= 0 )
  {
    FileNameW = PathFindFileNameW(pszPath);
    v3 = CompareStringOrdinal(FileNameW, -1, String2, -1, 1) != 2;
  }
LABEL_12:
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&pszPath);
  return v3;
}

```

## disassembly

```asm
0x1800dd57c  push    rbp
0x1800dd57e  push    rbx
0x1800dd57f  push    rsi
0x1800dd580  push    rdi
0x1800dd581  push    r14
0x1800dd583  push    r15
0x1800dd585  lea     rbp, [rsp-188h]
0x1800dd58d  sub     rsp, 288h
0x1800dd594  mov     rax, cs:__security_cookie
0x1800dd59b  xor     rax, rsp
0x1800dd59e  mov     [rbp+1B0h+var_40], rax
0x1800dd5a5  mov     rax, [rcx]
0x1800dd5a8  xor     r14d, r14d
0x1800dd5ab  mov     rdi, rcx
0x1800dd5ae  mov     [rsp+2B0h+pszPath], r14
0x1800dd5b3  lea     rcx, [rsp+2B0h+pszPath]
0x1800dd5b8  mov     [rsp+2B0h+var_260], r14
0x1800dd5bd  mov     sil, r14b
0x1800dd5c0  mov     [rsp+2B0h+var_258], r14
0x1800dd5c5  mov     rbx, [rax+28h]
0x1800dd5c9  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800dd5ce  or      r15, 0FFFFFFFFFFFFFFFFh
0x1800dd5d2  lea     r8, [rsp+2B0h+pszPath]
0x1800dd5d7  mov     edx, 80058000h
0x1800dd5dc  mov     [rsp+2B0h+var_260], r15
0x1800dd5e1  mov     rcx, rdi
0x1800dd5e4  mov     [rsp+2B0h+var_258], r15
0x1800dd5e9  mov     rax, rbx
0x1800dd5ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dd5f1  test    eax, eax
0x1800dd5f3  js      loc_1800DD6F6
0x1800dd5f9  mov     rcx, [rsp+2B0h+pszPath]; pszPath
0x1800dd5fe  call    cs:__imp_PathFindExtensionW
0x1800dd605  nop     dword ptr [rax+rax+00h]
0x1800dd60a  lea     ebx, [r14+1]
0x1800dd60e  mov     r9d, r15d; cchCount2
0x1800dd611  mov     rcx, rax; lpString1
0x1800dd614  mov     [rsp+2B0h+bIgnoreCase], ebx; bIgnoreCase
0x1800dd618  lea     r8, aAccountpicture; ".accountpicture-ms"
0x1800dd61f  mov     edx, r15d; cchCount1
0x1800dd622  call    cs:__imp_CompareStringOrdinal
0x1800dd629  nop     dword ptr [rax+rax+00h]
0x1800dd62e  cmp     eax, 2
0x1800dd631  jnz     loc_1800DD6F6
0x1800dd637  lea     rax, [rsp+2B0h+var_270]
0x1800dd63c  mov     [rsp+2B0h+var_270], 208h
0x1800dd644  mov     [rsp+2B0h+pcbData], rax; pcbData
0x1800dd649  lea     r9d, [r14+2]; dwFlags
0x1800dd64d  lea     rax, [rsp+2B0h+String2]
0x1800dd652  mov     rcx, 0FFFFFFFF80000001h; hkey
0x1800dd659  mov     [rsp+2B0h+pvData], rax; pvData
0x1800dd65e  lea     r8, aSourceid; "SourceId"
0x1800dd665  lea     rdx, aSoftwareMicros_13; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800dd66c  mov     qword ptr [rsp+2B0h+bIgnoreCase], r14; pdwType
0x1800dd671  mov     sil, bl
0x1800dd674  call    cs:__imp_RegGetValueW
0x1800dd67b  nop     dword ptr [rax+rax+00h]
0x1800dd680  test    eax, eax
0x1800dd682  jz      short loc_1800DD698
0x1800dd684  mov     ecx, r14d
0x1800dd687  mov     [rsp+2B0h+String2], cx
0x1800dd68c  jle     short loc_1800DD69F
0x1800dd68e  movzx   eax, ax
0x1800dd691  or      eax, 80070000h
0x1800dd696  jmp     short loc_1800DD69D
0x1800dd698  movzx   ecx, [rsp+2B0h+String2]
0x1800dd69d  test    eax, eax
0x1800dd69f  js      short loc_1800DD6F6
0x1800dd6a1  test    cx, cx
0x1800dd6a4  jz      short loc_1800DD6F6
0x1800dd6a6  lea     r8, aAccountpicture; ".accountpicture-ms"
0x1800dd6ad  mov     edx, 104h; unsigned __int64
0x1800dd6b2  lea     rcx, [rsp+2B0h+String2]; unsigned __int16 *
0x1800dd6b7  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800dd6bc  test    eax, eax
0x1800dd6be  js      short loc_1800DD6F6
0x1800dd6c0  mov     rcx, [rsp+2B0h+pszPath]; pszPath
0x1800dd6c5  call    cs:__imp_PathFindFileNameW
0x1800dd6cc  nop     dword ptr [rax+rax+00h]
0x1800dd6d1  mov     r9d, r15d; cchCount2
0x1800dd6d4  mov     [rsp+2B0h+bIgnoreCase], ebx; bIgnoreCase
0x1800dd6d8  mov     rcx, rax; lpString1
0x1800dd6db  lea     r8, [rsp+2B0h+String2]; lpString2
0x1800dd6e0  mov     edx, r15d; cchCount1
0x1800dd6e3  call    cs:__imp_CompareStringOrdinal
0x1800dd6ea  nop     dword ptr [rax+rax+00h]
0x1800dd6ef  cmp     eax, 2
0x1800dd6f2  setnz   sil
0x1800dd6f6  lea     rcx, [rsp+2B0h+pszPath]
0x1800dd6fb  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800dd700  mov     al, sil
0x1800dd703  mov     rcx, [rbp+1B0h+var_40]
0x1800dd70a  xor     rcx, rsp; StackCookie
0x1800dd70d  call    __security_check_cookie
0x1800dd712  add     rsp, 288h
0x1800dd719  pop     r15
0x1800dd71b  pop     r14
0x1800dd71d  pop     rdi
0x1800dd71e  pop     rsi
0x1800dd71f  pop     rbx
0x1800dd720  pop     rbp
0x1800dd721  retn
```
