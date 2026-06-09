# CDmpClient::InitPaths(wchar_t const *)

- ea: `0x100441610`
- end: `0x1004417b5`
- name: `?InitPaths@CDmpClient@@AEAAJPEB_W@Z`
- size: `421`
- prototype: `__int64 __fastcall(CDmpClient *__hidden this, const wchar_t *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x100441930`

## callees

- `0x100401aa0`
- `0x100441610`
- `0x1004417c0`
- `0x1004534f8`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x10044177c`
- `ADVAPI32!RegCloseKey` at `0x10044177c`
- `ADVAPI32!RegOpenKeyExW` at `0x100441642`
- `ADVAPI32!RegOpenKeyExW` at `0x100441642`
- `ADVAPI32!RegQueryValueExW` at `0x1004416d4`
- `ADVAPI32!RegQueryValueExW` at `0x1004416d4`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x10044172e`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x10044172e`

## pseudocode

```c
__int64 __fastcall CDmpClient::InitPaths(CDmpClient *this, const wchar_t *a2)
{
  signed int v2; // ebx
  CDmpClient *v3; // rdi
  char *v4; // rsi
  _WORD *v5; // rcx
  __int64 v6; // rdx
  __int16 v7; // ax
  _WORD *v8; // rax
  HKEY v9; // rcx
  LSTATUS v10; // eax
  unsigned __int64 v11; // rax
  struct __crt_locale_pointers *DefaultLocale; // rax
  signed int DefaultDir; // eax
  DWORD Type; // [rsp+58h] [rbp+10h] BYREF
  DWORD cbData; // [rsp+60h] [rbp+18h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+20h] BYREF

  v2 = 0;
  v3 = this;
  hKey = 0;
  if ( a2 )
  {
    if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, a2, 0, 1u, &hKey) )
    {
      v4 = (char *)v3 + 6680;
      Type = 0;
      v5 = (_WORD *)((char *)v3 + 6680);
      cbData = 520;
      v6 = 260;
      do
      {
        if ( v6 == -2147483386 )
          break;
        v7 = *(_WORD *)((char *)v5 + (char *)&dword_10045ADE4 - ((char *)v3 + 6680));
        if ( !v7 )
          break;
        *v5++ = v7;
        --v6;
      }
      while ( v6 );
      v8 = v5 - 1;
      if ( v6 )
        v8 = v5;
      v9 = hKey;
      *v8 = 0;
      v10 = RegQueryValueExW(v9, L"SharedCode", 0, &Type, (LPBYTE)v3 + 6680, &cbData);
      if ( v10 )
      {
        if ( v10 > 0 )
          v2 = (unsigned __int16)v10 | 0x80070000;
        else
          v2 = v10;
      }
      else if ( Type != 1 || (cbData & 1) != 0 || cbData < 2 )
      {
        v2 = -2147024885;
      }
      else
      {
        v11 = (unsigned __int64)cbData >> 1;
        if ( *(_WORD *)&v4[2 * v11 - 2] )
        {
          if ( v11 < 0x104 )
          {
            *(_WORD *)&v4[2 * v11] = 0;
            goto LABEL_22;
          }
          v2 = -2147024774;
        }
      }
      if ( v2 < 0 )
      {
        if ( v2 != -2147024894 )
        {
LABEL_26:
          RegCloseKey(hKey);
          goto LABEL_29;
        }
        _mm_lfence();
        DefaultDir = CDmpClient::GetDefaultDir(v3);
LABEL_25:
        v2 = DefaultDir;
        goto LABEL_26;
      }
LABEL_22:
      _mm_lfence();
      DefaultLocale = GetDefaultLocale();
      DefaultDir = StringCchPrintf_lW(
                     (wchar_t *)v3 + 3080,
                     0x104u,
                     L"%ls\\%ls",
                     DefaultLocale,
                     (char *)v3 + 6680,
                     L"SQLDUMPER.EXE");
      goto LABEL_25;
    }
    this = v3;
  }
  v2 = CDmpClient::GetDefaultDir(this);
LABEL_29:
  if ( v2 < 0 )
    memset_0((char *)v3 + 6160, 0, 0x410u);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x100441610  push    rbx
0x100441612  push    rdi
0x100441613  sub     rsp, 38h
0x100441617  xor     ebx, ebx
0x100441619  mov     rdi, rcx
0x10044161c  mov     [rsp+48h+hKey], rbx
0x100441621  test    rdx, rdx
0x100441624  jz      loc_10044178D
0x10044162a  lea     rax, [rsp+48h+hKey]
0x10044162f  xor     r8d, r8d; ulOptions
0x100441632  lea     r9d, [rbx+1]; samDesired
0x100441636  mov     [rsp+48h+phkResult], rax; phkResult
0x10044163b  mov     rcx, 0FFFFFFFF80000002h; hKey
0x100441642  call    cs:__imp_RegOpenKeyExW
0x100441648  test    eax, eax
0x10044164a  jnz     loc_10044178A
0x100441650  mov     [rsp+48h+var_18], rsi
0x100441655  lea     r8, dword_10045ADE4
0x10044165c  lea     rsi, [rdi+1A18h]
0x100441663  mov     [rsp+48h+Type], ebx
0x100441667  mov     rcx, rsi
0x10044166a  mov     [rsp+48h+cbData], 208h
0x100441672  sub     r8, rsi
0x100441675  mov     edx, 104h
0x10044167a  nop     word ptr [rax+rax+00h]
0x100441680  lea     rax, [rdx+7FFFFEFAh]
0x100441687  test    rax, rax
0x10044168a  jz      short loc_1004416A3
0x10044168c  movzx   eax, word ptr [r8+rcx]
0x100441691  test    ax, ax
0x100441694  jz      short loc_1004416A3
0x100441696  mov     [rcx], ax
0x100441699  add     rcx, 2
0x10044169d  sub     rdx, 1
0x1004416a1  jnz     short loc_100441680
0x1004416a3  test    rdx, rdx
0x1004416a6  lea     rax, [rcx-2]
0x1004416aa  lea     r9, [rsp+48h+Type]; lpType
0x1004416af  cmovnz  rax, rcx
0x1004416b3  lea     rdx, aSharedcode; "SharedCode"
0x1004416ba  mov     rcx, [rsp+48h+hKey]; hKey
0x1004416bf  xor     r8d, r8d; lpReserved
0x1004416c2  mov     [rax], bx
0x1004416c5  lea     rax, [rsp+48h+cbData]
0x1004416ca  mov     [rsp+48h+lpcbData], rax; lpcbData
0x1004416cf  mov     [rsp+48h+phkResult], rsi; lpData
0x1004416d4  call    cs:__imp_RegQueryValueExW
0x1004416da  test    eax, eax
0x1004416dc  jnz     short loc_100441718
0x1004416de  cmp     [rsp+48h+Type], 1
0x1004416e3  jnz     short loc_100441711
0x1004416e5  mov     eax, [rsp+48h+cbData]
0x1004416e9  test    al, 1
0x1004416eb  jnz     short loc_100441711
0x1004416ed  cmp     eax, 2
0x1004416f0  jb      short loc_100441711
0x1004416f2  shr     rax, 1
0x1004416f5  cmp     [rsi+rax*2-2], bx
0x1004416fa  jz      short loc_100441727
0x1004416fc  cmp     rax, 104h
0x100441702  jnb     short loc_10044170A
0x100441704  mov     [rsi+rax*2], bx
0x100441708  jmp     short loc_10044172B
0x10044170a  mov     ebx, 8007007Ah
0x10044170f  jmp     short loc_100441727
0x100441711  mov     ebx, 8007000Bh
0x100441716  jmp     short loc_100441727
0x100441718  jg      short loc_10044171E
0x10044171a  mov     ebx, eax
0x10044171c  jmp     short loc_100441727
0x10044171e  movzx   ebx, ax
0x100441721  or      ebx, 80070000h
0x100441727  test    ebx, ebx
0x100441729  js      short loc_100441762
0x10044172b  lfence
0x10044172e  call    cs:__imp_?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ; GetDefaultLocale(void)
0x100441734  lea     rcx, [rdi+1810h]; Buffer
0x10044173b  mov     edx, 104h; unsigned __int64
0x100441740  mov     r9, rax; struct __crt_locale_pointers *
0x100441743  lea     r8, aLsLs_1; "%ls\\%ls"
0x10044174a  lea     rax, aSqldumperExe; "SQLDUMPER.EXE"
0x100441751  mov     [rsp+48h+lpcbData], rax
0x100441756  mov     [rsp+48h+phkResult], rsi
0x10044175b  call    ?StringCchPrintf_lW@@YAJPEA_W_KPEB_WPEAU__crt_locale_pointers@@ZZ; StringCchPrintf_lW(wchar_t *,unsigned __int64,wchar_t const *,__crt_locale_pointers *,...)
0x100441760  jmp     short loc_100441775
0x100441762  cmp     ebx, 80070002h
0x100441768  jnz     short loc_100441777
0x10044176a  lfence
0x10044176d  mov     rcx, rdi; this
0x100441770  call    ?GetDefaultDir@CDmpClient@@AEAAJXZ; CDmpClient::GetDefaultDir(void)
0x100441775  mov     ebx, eax
0x100441777  mov     rcx, [rsp+48h+hKey]; hKey
0x10044177c  call    cs:__imp_RegCloseKey
0x100441782  mov     rsi, [rsp+48h+var_18]
0x100441787  jmp     short loc_100441794
0x10044178a  mov     rcx, rdi; this
0x10044178d  call    ?GetDefaultDir@CDmpClient@@AEAAJXZ; CDmpClient::GetDefaultDir(void)
0x100441792  mov     ebx, eax
0x100441794  test    ebx, ebx
0x100441796  jns     short loc_1004417AC
0x100441798  lea     rcx, [rdi+1810h]; void *
0x10044179f  xor     edx, edx; Val
0x1004417a1  mov     r8d, 410h; Size
0x1004417a7  call    memset_0
0x1004417ac  mov     eax, ebx
0x1004417ae  add     rsp, 38h
0x1004417b2  pop     rdi
0x1004417b3  pop     rbx
0x1004417b4  retn
```
