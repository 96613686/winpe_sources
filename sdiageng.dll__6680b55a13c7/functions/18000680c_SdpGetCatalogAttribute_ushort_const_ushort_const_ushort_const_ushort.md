# SdpGetCatalogAttribute(ushort const *,ushort const *,ushort const *,ushort * *)

- ea: `0x18000680c`
- end: `0x180006983`
- name: `?SdpGetCatalogAttribute@@YAJPEBG00PEAPEAG@Z`
- size: `375`
- prototype: `__int64 __fastcall(WCHAR *, const unsigned __int16 *, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180011ba4`

## callees

- `0x1800012a4`
- `0x18000680c`
- `0x180026fa0`
- `0x180027aa0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800068e2`
- `KERNEL32!GetLastError` at `0x18000691d`
- `KERNEL32!GetLastError` at `0x1800068e2`
- `KERNEL32!GetLastError` at `0x18000691d`
- `WINTRUST!CryptCATOpen` at `0x18000686e`
- `WINTRUST!CryptCATOpen` at `0x18000686e`
- `WINTRUST!CryptCATGetCatAttrInfo` at `0x18000688e`
- `WINTRUST!CryptCATGetCatAttrInfo` at `0x18000688e`
- `WINTRUST!CryptCATClose` at `0x180006964`
- `WINTRUST!CryptCATClose` at `0x180006964`

## pseudocode

```c
__int64 __fastcall SdpGetCatalogAttribute(
        WCHAR *a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        unsigned __int16 **a4)
{
  unsigned __int16 *v4; // rsi
  unsigned int v6; // r8d
  signed int v7; // ebx
  char *v8; // rbp
  CRYPTCATATTRIBUTE *v9; // rdx
  int v10; // eax
  signed int v11; // eax
  signed int LastError; // eax
  unsigned __int16 *v14; // [rsp+70h] [rbp+18h] BYREF

  v4 = 0;
  v14 = 0;
  if ( !a1 )
  {
    v6 = 1026;
LABEL_3:
    v7 = -2147024809;
    SdpDebugTrace(1u, L"SdpGetCatalogAttribute", v6, -2147024809);
    return (unsigned int)v7;
  }
  if ( !a4 )
  {
    v6 = 1028;
    goto LABEL_3;
  }
  v8 = (char *)CryptCATOpen(a1, 0, 0, 1u, 0x10001u);
  if ( (unsigned __int64)(v8 - 1) > 0xFFFFFFFFFFFFFFFDuLL )
  {
    LastError = GetLastError();
    v7 = LastError;
    if ( LastError > 0 )
      v7 = (unsigned __int16)LastError | 0x80070000;
    if ( v7 >= 0 )
      v7 = -2147467259;
    SdpDebugTrace(1u, L"SdpGetCatalogAttribute", 0x40Bu, v7);
    if ( !v8 || v8 == (char *)-1LL )
      goto LABEL_23;
  }
  else
  {
    v9 = CryptCATGetCatAttrInfo(v8, (LPWSTR)L"PackageId");
    if ( (unsigned __int64)&v9[-1].dwReserved + 7 > 0xFFFFFFFFFFFFFFFDuLL )
    {
      v11 = GetLastError();
      v7 = v11;
      if ( v11 > 0 )
        v7 = (unsigned __int16)v11 | 0x80070000;
      if ( v7 >= 0 )
        v7 = -2147467259;
      SdpDebugTrace(1u, L"SdpGetCatalogAttribute", 0x416u, v7);
    }
    else
    {
      v10 = SdpStrCpy(&v14, (const unsigned __int16 *)v9->pbValue);
      v7 = v10;
      if ( v10 >= 0 )
      {
        *a4 = v14;
      }
      else
      {
        SdpDebugTrace(1u, L"SdpGetCatalogAttribute", 0x41Au, v10);
        v4 = v14;
      }
    }
  }
  CryptCATClose(v8);
LABEL_23:
  if ( v4 )
    operator delete(v4);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18000680c  mov     [rsp+arg_10], r8
0x180006811  push    rbx
0x180006812  push    rbp
0x180006813  push    rsi
0x180006814  push    r14
0x180006816  sub     rsp, 38h
0x18000681a  xor     esi, esi
0x18000681c  mov     r14, r9
0x18000681f  mov     [rsp+58h+arg_10], rsi
0x180006824  test    rcx, rcx
0x180006827  jnz     short loc_18000684E
0x180006829  mov     r8d, 402h; int
0x18000682f  mov     r9d, 80070057h; int
0x180006835  lea     rdx, aSdpgetcataloga; "SdpGetCatalogAttribute"
0x18000683c  mov     ecx, 1; Level
0x180006841  mov     ebx, r9d
0x180006844  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180006849  jmp     loc_180006977
0x18000684e  test    r14, r14
0x180006851  jnz     short loc_18000685B
0x180006853  mov     r8d, 404h
0x180006859  jmp     short loc_18000682F
0x18000685b  mov     r9d, 1; dwPublicVersion
0x180006861  mov     [rsp+58h+dwEncodingType], 10001h; dwEncodingType
0x180006869  xor     r8d, r8d; hProv
0x18000686c  xor     edx, edx; fdwOpenFlags
0x18000686e  call    cs:__imp_CryptCATOpen
0x180006874  mov     rbp, rax
0x180006877  dec     rax
0x18000687a  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000687e  ja      loc_18000691D
0x180006884  lea     rdx, pwszReferenceTag; "PackageId"
0x18000688b  mov     rcx, rbp; hCatalog
0x18000688e  call    cs:__imp_CryptCATGetCatAttrInfo
0x180006894  mov     rdx, rax
0x180006897  dec     rax
0x18000689a  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000689e  ja      short loc_1800068E2
0x1800068a0  mov     rdx, [rdx+18h]; unsigned __int16 *
0x1800068a4  lea     rcx, [rsp+58h+arg_10]; unsigned __int16 **
0x1800068a9  call    ?SdpStrCpy@@YAJPEAPEAGPEBG@Z; SdpStrCpy(ushort * *,ushort const *)
0x1800068ae  mov     ebx, eax
0x1800068b0  test    eax, eax
0x1800068b2  jns     short loc_1800068D8
0x1800068b4  mov     r9d, eax; int
0x1800068b7  lea     rdx, aSdpgetcataloga; "SdpGetCatalogAttribute"
0x1800068be  mov     r8d, 41Ah; int
0x1800068c4  mov     ecx, 1; Level
0x1800068c9  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x1800068ce  mov     rsi, [rsp+58h+arg_10]
0x1800068d3  jmp     loc_180006961
0x1800068d8  mov     rax, [rsp+58h+arg_10]
0x1800068dd  mov     [r14], rax
0x1800068e0  jmp     short loc_180006961
0x1800068e2  call    cs:__imp_GetLastError
0x1800068e8  mov     ebx, eax
0x1800068ea  test    eax, eax
0x1800068ec  jle     short loc_1800068F7
0x1800068ee  movzx   ebx, ax
0x1800068f1  or      ebx, 80070000h
0x1800068f7  test    ebx, ebx
0x1800068f9  lea     rdx, aSdpgetcataloga; "SdpGetCatalogAttribute"
0x180006900  mov     eax, 80004005h
0x180006905  mov     r8d, 416h; int
0x18000690b  cmovns  ebx, eax
0x18000690e  mov     ecx, 1; Level
0x180006913  mov     r9d, ebx; int
0x180006916  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x18000691b  jmp     short loc_180006961
0x18000691d  call    cs:__imp_GetLastError
0x180006923  mov     ebx, eax
0x180006925  test    eax, eax
0x180006927  jle     short loc_180006932
0x180006929  movzx   ebx, ax
0x18000692c  or      ebx, 80070000h
0x180006932  test    ebx, ebx
0x180006934  lea     rdx, aSdpgetcataloga; "SdpGetCatalogAttribute"
0x18000693b  mov     eax, 80004005h
0x180006940  mov     r8d, 40Bh; int
0x180006946  cmovns  ebx, eax
0x180006949  mov     ecx, 1; Level
0x18000694e  mov     r9d, ebx; int
0x180006951  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180006956  test    rbp, rbp
0x180006959  jz      short loc_18000696A
0x18000695b  cmp     rbp, 0FFFFFFFFFFFFFFFFh
0x18000695f  jz      short loc_18000696A
0x180006961  mov     rcx, rbp; hCatalog
0x180006964  call    cs:__imp_CryptCATClose
0x18000696a  test    rsi, rsi
0x18000696d  jz      short loc_180006977
0x18000696f  mov     rcx, rsi; Block
0x180006972  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180006977  mov     eax, ebx
0x180006979  add     rsp, 38h
0x18000697d  pop     r14
0x18000697f  pop     rsi
0x180006980  pop     rbp
0x180006981  pop     rbx
0x180006982  retn
```
