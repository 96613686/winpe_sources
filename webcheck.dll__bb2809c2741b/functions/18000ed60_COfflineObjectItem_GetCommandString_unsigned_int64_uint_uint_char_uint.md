# COfflineObjectItem::GetCommandString(unsigned __int64,uint,uint *,char *,uint)

- ea: `0x18000ed60`
- end: `0x18000ee7a`
- name: `?GetCommandString@COfflineObjectItem@@UEAAJ_KIPEAIPEADI@Z`
- size: `282`
- prototype: `__int64 __fastcall(COfflineObjectItem *__hidden this, unsigned __int64, unsigned int, unsigned int *, LPSTR, unsigned int cchBufferMax)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0x18000ed60`
- `0x18000f9e0`

## import_xrefs

- `KERNEL32!LocalAlloc` at `0x18000ee0a`
- `KERNEL32!LocalAlloc` at `0x18000ee0a`
- `KERNEL32!LocalFree` at `0x18000ee60`
- `KERNEL32!LocalFree` at `0x18000ee60`
- `KERNEL32!WideCharToMultiByte` at `0x18000ee57`
- `KERNEL32!WideCharToMultiByte` at `0x18000ee57`
- `USER32!LoadStringW` at `0x18000ee26`
- `USER32!LoadStringW` at `0x18000ee26`

## string_xrefs

- `0x18000eda0`: `delete`

## pseudocode

```c
__int64 __fastcall COfflineObjectItem::GetCommandString(
        COfflineObjectItem *this,
        unsigned __int64 a2,
        int a3,
        unsigned int *a4,
        LPSTR lpMultiByteStr,
        unsigned int cchBufferMax)
{
  int v6; // esi
  unsigned int v7; // ecx
  const char *v8; // r8
  WCHAR *v9; // rdi

  v6 = a2;
  v7 = -2147467259;
  if ( a3 )
  {
    if ( a3 == 1 && (a2 < 4 || a2 - 4 <= 1) )
    {
      v9 = (WCHAR *)LocalAlloc(0x40u, 2LL * cchBufferMax);
      LoadStringW(g_hinstMUI, v6 + 8600, v9, cchBufferMax);
      WideCharToMultiByte(0, 0, v9, -1, lpMultiByteStr, cchBufferMax, 0, 0);
      LocalFree(v9);
      return 0;
    }
  }
  else
  {
    switch ( a2 )
    {
      case 0uLL:
        v8 = "open";
        goto LABEL_10;
      case 3uLL:
        v8 = "copy";
        goto LABEL_10;
      case 4uLL:
        v8 = "delete";
        goto LABEL_10;
      case 5uLL:
        v8 = "properties";
LABEL_10:
        StringCchCopyA(lpMultiByteStr, cchBufferMax, v8);
        return 0;
    }
  }
  return v7;
}

```

## disassembly

```asm
0x18000ed60  mov     [rsp+arg_0], rbx
0x18000ed65  mov     [rsp+arg_8], rsi
0x18000ed6a  push    rdi
0x18000ed6b  sub     rsp, 40h
0x18000ed6f  mov     rsi, rdx
0x18000ed72  mov     ecx, 80004005h
0x18000ed77  test    r8d, r8d
0x18000ed7a  jnz     short loc_18000EDCC
0x18000ed7c  test    rdx, rdx
0x18000ed7f  jz      short loc_18000EDB2
0x18000ed81  sub     rsi, 3
0x18000ed85  jz      short loc_18000EDA9
0x18000ed87  sub     rsi, 1
0x18000ed8b  jz      short loc_18000EDA0
0x18000ed8d  cmp     rsi, 1
0x18000ed91  jnz     loc_18000EE68
0x18000ed97  lea     r8, c_szProperties; "properties"
0x18000ed9e  jmp     short loc_18000EDB9
0x18000eda0  lea     r8, c_szDelete; "delete"
0x18000eda7  jmp     short loc_18000EDB9
0x18000eda9  lea     r8, c_szCopy; "copy"
0x18000edb0  jmp     short loc_18000EDB9
0x18000edb2  lea     r8, c_szOpen; "open"
0x18000edb9  mov     edx, [rsp+48h+cchBufferMax]; unsigned __int64
0x18000edbd  mov     rcx, [rsp+48h+arg_20]; char *
0x18000edc2  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x18000edc7  jmp     loc_18000EE66
0x18000edcc  cmp     r8d, 1
0x18000edd0  jnz     loc_18000EE68
0x18000edd6  mov     rax, rsi
0x18000edd9  test    rsi, rsi
0x18000eddc  jz      short loc_18000EDFC
0x18000edde  sub     rax, 1
0x18000ede2  jz      short loc_18000EDFC
0x18000ede4  sub     rax, 1
0x18000ede8  jz      short loc_18000EDFC
0x18000edea  sub     rax, 1
0x18000edee  jz      short loc_18000EDFC
0x18000edf0  sub     rax, 1
0x18000edf4  jz      short loc_18000EDFC
0x18000edf6  cmp     rax, 1
0x18000edfa  jnz     short loc_18000EE68
0x18000edfc  mov     ebx, [rsp+48h+cchBufferMax]
0x18000ee00  mov     ecx, 40h ; '@'; uFlags
0x18000ee05  mov     edx, ebx
0x18000ee07  add     rdx, rdx; uBytes
0x18000ee0a  call    cs:__imp_LocalAlloc
0x18000ee10  mov     rcx, cs:g_hinstMUI; hInstance
0x18000ee17  lea     edx, [rsi+2198h]; uID
0x18000ee1d  mov     r8, rax; lpBuffer
0x18000ee20  mov     r9d, ebx; cchBufferMax
0x18000ee23  mov     rdi, rax
0x18000ee26  call    cs:__imp_LoadStringW
0x18000ee2c  mov     rax, [rsp+48h+arg_20]
0x18000ee31  or      r9d, 0FFFFFFFFh; cchWideChar
0x18000ee35  mov     [rsp+48h+lpUsedDefaultChar], 0; lpUsedDefaultChar
0x18000ee3e  mov     r8, rdi; lpWideCharStr
0x18000ee41  mov     [rsp+48h+lpDefaultChar], 0; lpDefaultChar
0x18000ee4a  xor     edx, edx; dwFlags
0x18000ee4c  mov     [rsp+48h+cbMultiByte], ebx; cbMultiByte
0x18000ee50  xor     ecx, ecx; CodePage
0x18000ee52  mov     [rsp+48h+lpMultiByteStr], rax; lpMultiByteStr
0x18000ee57  call    cs:__imp_WideCharToMultiByte
0x18000ee5d  mov     rcx, rdi; hMem
0x18000ee60  call    cs:__imp_LocalFree
0x18000ee66  xor     ecx, ecx
0x18000ee68  mov     rbx, [rsp+48h+arg_0]
0x18000ee6d  mov     eax, ecx
0x18000ee6f  mov     rsi, [rsp+48h+arg_8]
0x18000ee74  add     rsp, 40h
0x18000ee78  pop     rdi
0x18000ee79  retn
```
