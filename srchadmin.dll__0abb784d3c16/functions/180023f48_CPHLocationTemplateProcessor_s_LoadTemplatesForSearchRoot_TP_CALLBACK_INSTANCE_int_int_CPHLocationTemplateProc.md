# CPHLocationTemplateProcessor::s_LoadTemplatesForSearchRoot(_TP_CALLBACK_INSTANCE *,int,int,CPHLocationTemplateProcessor * *)

- ea: `0x180023f48`
- end: `0x1800240e3`
- name: `?s_LoadTemplatesForSearchRoot@CPHLocationTemplateProcessor@@SAJPEAU_TP_CALLBACK_INSTANCE@@HHPEAPEAV1@@Z`
- size: `411`
- prototype: `__int64 __fastcall(struct _TP_CALLBACK_INSTANCE *, unsigned int, int, WCHAR **)`
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180021ac0`
- `0x1800230a0`

## callees

- `0x180005cc0`
- `0x18000687c`
- `0x1800095c0`
- `0x18001a7fc`
- `0x1800214dc`
- `0x180021878`
- `0x1800227dc`
- `0x180022efc`
- `0x180023b94`
- `0x180023f48`

## import_xrefs

- `SHELL32!SHCreateItemFromParsingName` at `0x180024074`
- `SHELL32!SHCreateItemFromParsingName` at `0x180024074`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180023fe8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180023fe8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800240a3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800240a3`

## string_xrefs

- `0x18002400a`: `DoNotCreateSearchConnectors`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall CPHLocationTemplateProcessor::s_LoadTemplatesForSearchRoot(
        struct _TP_CALLBACK_INSTANCE *a1,
        unsigned int a2,
        int a3,
        WCHAR **a4)
{
  unsigned __int16 *v7; // rax
  WCHAR *v8; // rdi
  int StringValue; // ebx
  unsigned int v10; // edx
  LSTATUS v11; // eax
  struct IShellItem *v12; // r8
  HKEY hKey; // [rsp+30h] [rbp-D0h] BYREF
  void *ppv; // [rsp+38h] [rbp-C8h] BYREF
  WCHAR pszPath; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v17[526]; // [rsp+42h] [rbp-BEh] BYREF

  *a4 = 0;
  v7 = (unsigned __int16 *)operator new(0x228u);
  v8 = v7;
  if ( v7 )
  {
    StringValue = StringCchPrintfW(v7, 0x104u, L"SOFTWARE\\Microsoft\\Windows Search\\ProcessedSearchRoots\\%04d", a2);
    if ( StringValue < 0 )
      goto LABEL_15;
    hKey = 0;
    v11 = RegOpenKeyExW(HKEY_CURRENT_USER, v8, 0, 0x20019u, &hKey);
    StringValue = v11;
    if ( v11 > 0 )
      StringValue = (unsigned __int16)v11 | 0x80070000;
    if ( StringValue < 0 )
      goto LABEL_15;
    if ( IsFlagNotSet(hKey, L"DoNotCreateSearchConnectors") )
    {
      pszPath = 0;
      memset_0(v17, 0, 0x206u);
      StringValue = RegGetStringValue(hKey, 0, &pszPath, 0x104u);
      if ( StringValue >= 0 )
      {
        v12 = 0;
        ppv = 0;
        if ( !a3 )
        {
          StringValue = SHCreateItemFromParsingName(&pszPath, 0, &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe, &ppv);
          if ( StringValue < 0 )
            goto LABEL_13;
          v12 = (struct IShellItem *)ppv;
        }
        StringValue = CPHLocationTemplateProcessor::_LoadTemplateInfo((CPHLocationTemplateProcessor *)v8, hKey, v12);
        SafeRelease<IShellItem>(&ppv);
      }
    }
LABEL_13:
    RegCloseKey(hKey);
    if ( StringValue >= 0 )
    {
      *a4 = v8;
      return (unsigned int)StringValue;
    }
LABEL_15:
    CPHLocationTemplateProcessor::`scalar deleting destructor'((CPHLocationTemplateProcessor *)v8, v10);
    return (unsigned int)StringValue;
  }
  return (unsigned int)-2147024882;
}

```

## disassembly

```asm
0x180023f48  mov     [rsp-8+arg_0], rbx
0x180023f4d  mov     [rsp-8+arg_10], rsi
0x180023f52  push    rbp
0x180023f53  push    rdi
0x180023f54  push    r14
0x180023f56  lea     rbp, [rsp-160h]
0x180023f5e  sub     rsp, 260h
0x180023f65  mov     rax, cs:__security_cookie
0x180023f6c  xor     rax, rsp
0x180023f6f  mov     [rbp+170h+var_20], rax
0x180023f76  mov     ecx, 228h; unsigned __int64
0x180023f7b  mov     qword ptr [r9], 0
0x180023f82  mov     rsi, r9
0x180023f85  mov     r14d, r8d
0x180023f88  mov     ebx, edx
0x180023f8a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180023f8f  mov     rdi, rax
0x180023f92  test    rax, rax
0x180023f95  jnz     short loc_180023FA1
0x180023f97  mov     ebx, 8007000Eh
0x180023f9c  jmp     loc_1800240BA
0x180023fa1  mov     r9d, ebx
0x180023fa4  lea     r8, aSoftwareMicros_9; "SOFTWARE\\Microsoft\\Windows Search\\Pr"...
0x180023fab  mov     edx, 104h; unsigned __int64
0x180023fb0  mov     rcx, rdi; unsigned __int16 *
0x180023fb3  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180023fb8  mov     ebx, eax
0x180023fba  test    eax, eax
0x180023fbc  js      loc_1800240B2
0x180023fc2  lea     rax, [rsp+270h+hKey]
0x180023fc7  mov     [rsp+270h+hKey], 0
0x180023fd0  mov     r9d, 20019h; samDesired
0x180023fd6  mov     [rsp+270h+phkResult], rax; phkResult
0x180023fdb  xor     r8d, r8d; ulOptions
0x180023fde  mov     rdx, rdi; lpSubKey
0x180023fe1  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180023fe8  call    cs:__imp_RegOpenKeyExW
0x180023fee  mov     ebx, eax
0x180023ff0  test    eax, eax
0x180023ff2  jle     short loc_180023FFD
0x180023ff4  movzx   ebx, ax
0x180023ff7  or      ebx, 80070000h
0x180023ffd  test    ebx, ebx
0x180023fff  js      loc_1800240B2
0x180024005  mov     rcx, [rsp+270h+hKey]; HKEY
0x18002400a  lea     rdx, aDonotcreatesea; "DoNotCreateSearchConnectors"
0x180024011  call    ?IsFlagNotSet@@YAHPEAUHKEY__@@PEBG@Z; IsFlagNotSet(HKEY__ *,ushort const *)
0x180024016  test    eax, eax
0x180024018  jz      loc_18002409E
0x18002401e  xor     eax, eax
0x180024020  lea     rcx, [rsp+270h+var_22E]; void *
0x180024025  xor     edx, edx; Val
0x180024027  mov     [rsp+270h+pszPath], ax
0x18002402c  mov     r8d, 206h; Size
0x180024032  call    memset_0
0x180024037  mov     rcx, [rsp+270h+hKey]; HKEY
0x18002403c  lea     r8, [rsp+270h+pszPath]; unsigned __int16 *
0x180024041  mov     r9d, 104h; unsigned int
0x180024047  xor     edx, edx; unsigned __int16 *
0x180024049  call    ?RegGetStringValue@@YAJPEAUHKEY__@@PEBGPEAGK@Z; RegGetStringValue(HKEY__ *,ushort const *,ushort *,ulong)
0x18002404e  mov     ebx, eax
0x180024050  test    eax, eax
0x180024052  js      short loc_18002409E
0x180024054  xor     r8d, r8d
0x180024057  mov     [rsp+270h+ppv], r8
0x18002405c  test    r14d, r14d
0x18002405f  jnz     short loc_180024085
0x180024061  lea     r9, [rsp+270h+ppv]; ppv
0x180024066  xor     edx, edx; pbc
0x180024068  lea     r8, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe; riid
0x18002406f  lea     rcx, [rsp+270h+pszPath]; pszPath
0x180024074  call    cs:__imp_SHCreateItemFromParsingName
0x18002407a  mov     ebx, eax
0x18002407c  test    eax, eax
0x18002407e  js      short loc_18002409E
0x180024080  mov     r8, [rsp+270h+ppv]; struct IShellItem *
0x180024085  mov     rdx, [rsp+270h+hKey]; HKEY
0x18002408a  mov     rcx, rdi; this
0x18002408d  call    ?_LoadTemplateInfo@CPHLocationTemplateProcessor@@AEAAJPEAUHKEY__@@PEAUIShellItem@@@Z; CPHLocationTemplateProcessor::_LoadTemplateInfo(HKEY__ *,IShellItem *)
0x180024092  lea     rcx, [rsp+270h+ppv]
0x180024097  mov     ebx, eax
0x180024099  call    ??$SafeRelease@UIShellItem@@@@YAXPEAPEAUIShellItem@@@Z; SafeRelease<IShellItem>(IShellItem * *)
0x18002409e  mov     rcx, [rsp+270h+hKey]; hKey
0x1800240a3  call    cs:__imp_RegCloseKey
0x1800240a9  test    ebx, ebx
0x1800240ab  js      short loc_1800240B2
0x1800240ad  mov     [rsi], rdi
0x1800240b0  jmp     short loc_1800240BA
0x1800240b2  mov     rcx, rdi; this
0x1800240b5  call    ??_GCPHLocationTemplateProcessor@@QEAAPEAXI@Z; CPHLocationTemplateProcessor::`scalar deleting destructor'(uint)
0x1800240ba  mov     eax, ebx
0x1800240bc  mov     rcx, [rbp+170h+var_20]
0x1800240c3  xor     rcx, rsp; StackCookie
0x1800240c6  call    __security_check_cookie
0x1800240cb  lea     r11, [rsp+270h+var_10]
0x1800240d3  mov     rbx, [r11+20h]
0x1800240d7  mov     rsi, [r11+30h]
0x1800240db  mov     rsp, r11
0x1800240de  pop     r14
0x1800240e0  pop     rdi
0x1800240e1  pop     rbp
0x1800240e2  retn
```
