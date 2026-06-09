# CColorSwatchStore::LoadSwatchConfig(CResourceCache *,void *,uint,CColorSwatchConfig *)

- ea: `0x18000fc50`
- end: `0x18000ff6c`
- name: `?LoadSwatchConfig@CColorSwatchStore@@AEAAJPEAVCResourceCache@@PEAXIPEAVCColorSwatchConfig@@@Z`
- size: `796`
- prototype: `int(CColorSwatchStore *__hidden this, struct CResourceCache *, void *, unsigned int, struct CColorSwatchConfig *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18000ff74`

## callees

- `0x180002280`
- `0x18000f774`
- `0x18000fc50`
- `0x180024474`

## import_xrefs

- `SHLWAPI!SHRegQueryUSValueW` at `0x18000fd35`
- `SHLWAPI!SHRegQueryUSValueW` at `0x18000fd9f`
- `SHLWAPI!SHRegQueryUSValueW` at `0x18000fead`
- `SHLWAPI!SHRegQueryUSValueW` at `0x18000feff`
- `SHLWAPI!SHRegQueryUSValueW` at `0x18000ff55`
- `SHLWAPI!SHRegQueryUSValueW` at `0x18000fd35`
- `SHLWAPI!SHRegQueryUSValueW` at `0x18000fd9f`
- `SHLWAPI!SHRegQueryUSValueW` at `0x18000fead`
- `SHLWAPI!SHRegQueryUSValueW` at `0x18000feff`
- `SHLWAPI!SHRegQueryUSValueW` at `0x18000ff55`
- `SHLWAPI!SHRegEnumUSKeyW` at `0x18000fcb5`
- `SHLWAPI!SHRegEnumUSKeyW` at `0x18000fcb5`
- `SHLWAPI!SHRegCloseUSKey` at `0x18000fe12`
- `SHLWAPI!SHRegCloseUSKey` at `0x18000fe12`
- `SHLWAPI!SHRegOpenUSKeyW` at `0x18000fce7`
- `SHLWAPI!SHRegOpenUSKeyW` at `0x18000fce7`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18000fdc9`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18000fdc9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fddd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fddd`

## pseudocode

```c
__int64 __fastcall CColorSwatchStore::LoadSwatchConfig(
        CColorSwatchStore *this,
        struct CResourceCache *a2,
        void *a3,
        DWORD a4,
        struct CColorSwatchConfig *a5)
{
  signed int CachedHandle; // ebx
  signed int LastError; // eax
  int enumRegFlags; // [rsp+20h] [rbp-E0h]
  DWORD v11; // [rsp+40h] [rbp-C0h] BYREF
  int v12; // [rsp+44h] [rbp-BCh] BYREF
  unsigned int v13; // [rsp+48h] [rbp-B8h] BYREF
  int v14; // [rsp+4Ch] [rbp-B4h] BYREF
  DWORD pcbData; // [rsp+50h] [rbp-B0h] BYREF
  HUSKEY phNewUSKey; // [rsp+58h] [rbp-A8h] BYREF
  DWORD pcchName; // [rsp+60h] [rbp-A0h] BYREF
  HINSTANCE hInstance; // [rsp+68h] [rbp-98h] BYREF
  unsigned __int16 pvData[264]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR pwzName[264]; // [rsp+280h] [rbp+180h] BYREF
  WCHAR Buffer[264]; // [rsp+490h] [rbp+390h] BYREF

  pcchName = 260;
  CachedHandle = -2147467259;
  if ( SHRegEnumUSKeyW(a3, a4, pwzName, &pcchName, SHREGENUM_DEFAULT) )
    return (unsigned int)CachedHandle;
  phNewUSKey = 0;
  if ( SHRegOpenUSKeyW(pwzName, 0x20019u, a3, &phNewUSKey, 0) )
    return (unsigned int)CachedHandle;
  hInstance = 0;
  pcbData = 520;
  if ( SHRegQueryUSValueW(phNewUSKey, L"Resource", 0, pvData, &pcbData, 0, 0, 0) )
    goto LABEL_11;
  CachedHandle = CResourceCache::GetCachedHandle(a2, pvData, &hInstance);
  if ( CachedHandle >= 0 )
  {
    pcbData = 0;
    v11 = 4;
    if ( !SHRegQueryUSValueW(phNewUSKey, L"NameId", 0, &pcbData, &v11, 0, 0, 0)
      && !LoadStringW(hInstance, pcbData, Buffer, 260) )
    {
      LastError = GetLastError();
      CachedHandle = LastError;
      if ( LastError > 0 )
        CachedHandle = (unsigned __int16)LastError | 0x80070000;
      if ( CachedHandle >= 0 )
        CachedHandle = -2147467259;
LABEL_11:
      v14 = 0;
LABEL_12:
      v13 = 0;
      goto LABEL_13;
    }
  }
  v14 = 0;
  if ( CachedHandle >= 0 )
  {
    v11 = 4;
    if ( SHRegQueryUSValueW(phNewUSKey, L"PreviewId", 0, &v14, &v11, 0, 0, 0) )
    {
      CachedHandle = -2147467259;
      goto LABEL_12;
    }
  }
  v13 = 0;
  if ( CachedHandle < 0 || (v11 = 4, !SHRegQueryUSValueW(phNewUSKey, L"Color", 0, &v13, &v11, 0, 0, 0)) )
  {
    v12 = 0;
    if ( CachedHandle >= 0 )
    {
      v11 = 4;
      if ( SHRegQueryUSValueW(phNewUSKey, L"PreviewOrder", 0, &v12, &v11, 0, 0, 0) )
        CachedHandle = -2147467259;
    }
    goto LABEL_14;
  }
  CachedHandle = -2147467259;
LABEL_13:
  v12 = 0;
LABEL_14:
  SHRegCloseUSKey(phNewUSKey);
  if ( CachedHandle >= 0 )
  {
    LOWORD(enumRegFlags) = v14;
    return (unsigned int)CColorSwatchConfig::Initialize(a5, Buffer, v13, pvData, enumRegFlags, v12);
  }
  return (unsigned int)CachedHandle;
}

```

## disassembly

```asm
0x18000fc50  push    rbp
0x18000fc52  push    rbx
0x18000fc53  push    rsi
0x18000fc54  push    rdi
0x18000fc55  push    r12
0x18000fc57  push    r14
0x18000fc59  push    r15
0x18000fc5b  lea     rbp, [rsp-5B0h]
0x18000fc63  sub     rsp, 6B0h
0x18000fc6a  mov     rax, cs:__security_cookie
0x18000fc71  xor     rax, rsp
0x18000fc74  mov     [rbp+5E0h+var_40], rax
0x18000fc7b  mov     r14, [rbp+5E0h+arg_20]
0x18000fc82  mov     eax, r9d
0x18000fc85  mov     rdi, r8
0x18000fc88  mov     [rsp+6E0h+pcchName], 104h
0x18000fc90  mov     rsi, rdx
0x18000fc93  lea     r9, [rsp+6E0h+pcchName]; pcchName
0x18000fc98  mov     r12d, 80004005h
0x18000fc9e  lea     r8, [rbp+5E0h+pwzName]; pwzName
0x18000fca5  xor     r15d, r15d
0x18000fca8  mov     edx, eax; dwIndex
0x18000fcaa  mov     rcx, rdi; hUSKey
0x18000fcad  mov     [rsp+6E0h+enumRegFlags], r15d; enumRegFlags
0x18000fcb2  mov     ebx, r12d
0x18000fcb5  call    cs:__imp_SHRegEnumUSKeyW
0x18000fcbc  nop     dword ptr [rax+rax+00h]
0x18000fcc1  test    eax, eax
0x18000fcc3  jnz     loc_18000FE4F
0x18000fcc9  lea     r9, [rsp+6E0h+phNewUSKey]; phNewUSKey
0x18000fcce  mov     [rsp+6E0h+phNewUSKey], r15
0x18000fcd3  mov     r8, rdi; hRelativeUSKey
0x18000fcd6  mov     [rsp+6E0h+enumRegFlags], r15d; fIgnoreHKCU
0x18000fcdb  mov     edx, 20019h; samDesired
0x18000fce0  lea     rcx, [rbp+5E0h+pwzName]; pwzPath
0x18000fce7  call    cs:__imp_SHRegOpenUSKeyW
0x18000fcee  nop     dword ptr [rax+rax+00h]
0x18000fcf3  test    eax, eax
0x18000fcf5  jnz     loc_18000FE4F
0x18000fcfb  mov     rcx, [rsp+6E0h+phNewUSKey]; hUSKey
0x18000fd00  lea     rax, [rsp+6E0h+pcbData]
0x18000fd05  mov     [rsp+6E0h+dwDefaultDataSize], r15d; dwDefaultDataSize
0x18000fd0a  lea     r9, [rsp+6E0h+pvData]; pvData
0x18000fd0f  mov     [rsp+6E0h+pvDefaultData], r15; pvDefaultData
0x18000fd14  lea     rdx, pszValue; "Resource"
0x18000fd1b  mov     [rsp+6E0h+fIgnoreHKCU], r15d; fIgnoreHKCU
0x18000fd20  xor     r8d, r8d; pdwType
0x18000fd23  mov     qword ptr [rsp+6E0h+enumRegFlags], rax; pcbData
0x18000fd28  mov     [rsp+6E0h+hInstance], r15
0x18000fd2d  mov     [rsp+6E0h+pcbData], 208h
0x18000fd35  call    cs:__imp_SHRegQueryUSValueW
0x18000fd3c  nop     dword ptr [rax+rax+00h]
0x18000fd41  test    eax, eax
0x18000fd43  jnz     loc_18000FDFE
0x18000fd49  lea     r8, [rsp+6E0h+hInstance]; HINSTANCE *
0x18000fd4e  mov     rcx, rsi; this
0x18000fd51  lea     rdx, [rsp+6E0h+pvData]; unsigned __int16 *
0x18000fd56  call    ?GetCachedHandle@CResourceCache@@QEAAJPEBGPEAPEAUHINSTANCE__@@@Z; CResourceCache::GetCachedHandle(ushort const *,HINSTANCE__ * *)
0x18000fd5b  lea     edi, [r15+4]
0x18000fd5f  mov     ebx, eax
0x18000fd61  test    eax, eax
0x18000fd63  js      loc_18000FE73
0x18000fd69  mov     rcx, [rsp+6E0h+phNewUSKey]; hUSKey
0x18000fd6e  lea     rax, [rsp+6E0h+var_6A0]
0x18000fd73  mov     [rsp+6E0h+dwDefaultDataSize], r15d; dwDefaultDataSize
0x18000fd78  lea     r9, [rsp+6E0h+pcbData]; pvData
0x18000fd7d  mov     [rsp+6E0h+pvDefaultData], r15; pvDefaultData
0x18000fd82  lea     rdx, aNameid; "NameId"
0x18000fd89  mov     [rsp+6E0h+fIgnoreHKCU], r15d; fIgnoreHKCU
0x18000fd8e  xor     r8d, r8d; pdwType
0x18000fd91  mov     qword ptr [rsp+6E0h+enumRegFlags], rax; pcbData
0x18000fd96  mov     [rsp+6E0h+pcbData], r15d
0x18000fd9b  mov     [rsp+6E0h+var_6A0], edi
0x18000fd9f  call    cs:__imp_SHRegQueryUSValueW
0x18000fda6  nop     dword ptr [rax+rax+00h]
0x18000fdab  test    eax, eax
0x18000fdad  jnz     loc_18000FE73
0x18000fdb3  mov     edx, [rsp+6E0h+pcbData]; uID
0x18000fdb7  lea     r8, [rbp+5E0h+Buffer]; lpBuffer
0x18000fdbe  mov     rcx, [rsp+6E0h+hInstance]; hInstance
0x18000fdc3  mov     r9d, 104h; cchBufferMax
0x18000fdc9  call    cs:__imp_LoadStringW
0x18000fdd0  nop     dword ptr [rax+rax+00h]
0x18000fdd5  test    eax, eax
0x18000fdd7  jnz     loc_18000FE73
0x18000fddd  call    cs:__imp_GetLastError
0x18000fde4  nop     dword ptr [rax+rax+00h]
0x18000fde9  mov     ebx, eax
0x18000fdeb  test    eax, eax
0x18000fded  jle     short loc_18000FDF8
0x18000fdef  movzx   ebx, ax
0x18000fdf2  or      ebx, 80070000h
0x18000fdf8  test    ebx, ebx
0x18000fdfa  cmovns  ebx, r12d
0x18000fdfe  mov     [rsp+6E0h+var_694], r15d
0x18000fe03  mov     [rsp+6E0h+var_698], r15d
0x18000fe08  mov     [rsp+6E0h+var_69C], r15d
0x18000fe0d  mov     rcx, [rsp+6E0h+phNewUSKey]; hUSKey
0x18000fe12  call    cs:__imp_SHRegCloseUSKey
0x18000fe19  nop     dword ptr [rax+rax+00h]
0x18000fe1e  test    ebx, ebx
0x18000fe20  js      short loc_18000FE4F
0x18000fe22  mov     eax, [rsp+6E0h+var_69C]
0x18000fe26  lea     r9, [rsp+6E0h+pvData]
0x18000fe2b  mov     r8d, [rsp+6E0h+var_698]
0x18000fe30  lea     rdx, [rbp+5E0h+Buffer]
0x18000fe37  mov     [rsp+6E0h+fIgnoreHKCU], eax
0x18000fe3b  mov     rcx, r14
0x18000fe3e  movzx   eax, word ptr [rsp+6E0h+var_694]
0x18000fe43  mov     word ptr [rsp+6E0h+enumRegFlags], ax
0x18000fe48  call    ?Initialize@CColorSwatchConfig@@QEAAJPEAGVCColorizationColor@@0GI@Z; CColorSwatchConfig::Initialize(ushort *,CColorizationColor,ushort *,ushort,uint)
0x18000fe4d  mov     ebx, eax
0x18000fe4f  mov     eax, ebx
0x18000fe51  mov     rcx, [rbp+5E0h+var_40]
0x18000fe58  xor     rcx, rsp; StackCookie
0x18000fe5b  call    __security_check_cookie
0x18000fe60  add     rsp, 6B0h
0x18000fe67  pop     r15
0x18000fe69  pop     r14
0x18000fe6b  pop     r12
0x18000fe6d  pop     rdi
0x18000fe6e  pop     rsi
0x18000fe6f  pop     rbx
0x18000fe70  pop     rbp
0x18000fe71  retn
0x18000fe73  mov     [rsp+6E0h+var_694], r15d
0x18000fe78  test    ebx, ebx
0x18000fe7a  js      short loc_18000FEC5
0x18000fe7c  mov     rcx, [rsp+6E0h+phNewUSKey]; hUSKey
0x18000fe81  lea     rax, [rsp+6E0h+var_6A0]
0x18000fe86  mov     [rsp+6E0h+dwDefaultDataSize], r15d; dwDefaultDataSize
0x18000fe8b  lea     r9, [rsp+6E0h+var_694]; pvData
0x18000fe90  mov     [rsp+6E0h+pvDefaultData], r15; pvDefaultData
0x18000fe95  lea     rdx, aPreviewid; "PreviewId"
0x18000fe9c  mov     [rsp+6E0h+fIgnoreHKCU], r15d; fIgnoreHKCU
0x18000fea1  xor     r8d, r8d; pdwType
0x18000fea4  mov     qword ptr [rsp+6E0h+enumRegFlags], rax; pcbData
0x18000fea9  mov     [rsp+6E0h+var_6A0], edi
0x18000fead  call    cs:__imp_SHRegQueryUSValueW
0x18000feb4  nop     dword ptr [rax+rax+00h]
0x18000feb9  test    eax, eax
0x18000febb  jz      short loc_18000FEC5
0x18000febd  mov     ebx, r12d
0x18000fec0  jmp     loc_18000FE03
0x18000fec5  mov     [rsp+6E0h+var_698], r15d
0x18000feca  test    ebx, ebx
0x18000fecc  js      short loc_18000FF17
0x18000fece  mov     rcx, [rsp+6E0h+phNewUSKey]; hUSKey
0x18000fed3  lea     rax, [rsp+6E0h+var_6A0]
0x18000fed8  mov     [rsp+6E0h+dwDefaultDataSize], r15d; dwDefaultDataSize
0x18000fedd  lea     r9, [rsp+6E0h+var_698]; pvData
0x18000fee2  mov     [rsp+6E0h+pvDefaultData], r15; pvDefaultData
0x18000fee7  lea     rdx, aColor; "Color"
0x18000feee  mov     [rsp+6E0h+fIgnoreHKCU], r15d; fIgnoreHKCU
0x18000fef3  xor     r8d, r8d; pdwType
0x18000fef6  mov     qword ptr [rsp+6E0h+enumRegFlags], rax; pcbData
0x18000fefb  mov     [rsp+6E0h+var_6A0], edi
0x18000feff  call    cs:__imp_SHRegQueryUSValueW
0x18000ff06  nop     dword ptr [rax+rax+00h]
0x18000ff0b  test    eax, eax
0x18000ff0d  jz      short loc_18000FF17
0x18000ff0f  mov     ebx, r12d
0x18000ff12  jmp     loc_18000FE08
0x18000ff17  mov     [rsp+6E0h+var_69C], r15d
0x18000ff1c  test    ebx, ebx
0x18000ff1e  js      loc_18000FE0D
0x18000ff24  mov     rcx, [rsp+6E0h+phNewUSKey]; hUSKey
0x18000ff29  lea     rax, [rsp+6E0h+var_6A0]
0x18000ff2e  mov     [rsp+6E0h+dwDefaultDataSize], r15d; dwDefaultDataSize
0x18000ff33  lea     r9, [rsp+6E0h+var_69C]; pvData
0x18000ff38  mov     [rsp+6E0h+pvDefaultData], r15; pvDefaultData
0x18000ff3d  lea     rdx, aPrevieworder; "PreviewOrder"
0x18000ff44  mov     [rsp+6E0h+fIgnoreHKCU], r15d; fIgnoreHKCU
0x18000ff49  xor     r8d, r8d; pdwType
0x18000ff4c  mov     qword ptr [rsp+6E0h+enumRegFlags], rax; pcbData
0x18000ff51  mov     [rsp+6E0h+var_6A0], edi
0x18000ff55  call    cs:__imp_SHRegQueryUSValueW
0x18000ff5c  nop     dword ptr [rax+rax+00h]
0x18000ff61  test    eax, eax
0x18000ff63  cmovnz  ebx, r12d
0x18000ff67  jmp     loc_18000FE0D
```
