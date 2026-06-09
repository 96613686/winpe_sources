# Windows::System::Internal::Implementation::RegUtil::ReadValue<HSTRING__ *>(HKEY__ *,ushort const *,HSTRING__ * *)

- ea: `0x18004df20`
- end: `0x18004e12e`
- name: `??$ReadValue@PEAUHSTRING__@@@RegUtil@Implementation@Internal@System@Windows@@SAJPEAUHKEY__@@PEBGPEAPEAUHSTRING__@@@Z`
- size: `526`
- prototype: `__int64 __fastcall(HKEY hKey, LPCWSTR lpValueName, HSTRING *string)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18004c06c`
- `0x18004f294`

## callees

- `0x18000acdc`
- `0x18004df20`
- `0x18004e508`
- `0x18006c380`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x18004e10f`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18004e10f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18004e016`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18004e0e6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18004e016`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18004e0e6`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18004df95`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18004e0b3`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18004df95`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18004e0b3`

## string_xrefs

- `0x18004df48`: `onecore\ds\security\umstartup\usermgr\lib\regutil.h`
- `0x18004dfa7`: `onecore\ds\security\umstartup\usermgr\lib\regutil.h`
- `0x18004dfcf`: `onecore\ds\security\umstartup\usermgr\lib\regutil.h`
- `0x18004dffc`: `onecore\ds\security\umstartup\usermgr\lib\regutil.h`
- `0x18004e02c`: `onecore\ds\security\umstartup\usermgr\lib\regutil.h`
- `0x18004e089`: `onecore\ds\security\umstartup\usermgr\lib\regutil.h`
- `0x18004e0c5`: `onecore\ds\security\umstartup\usermgr\lib\regutil.h`
- `0x18004e0f8`: `onecore\ds\security\umstartup\usermgr\lib\regutil.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::System::Internal::Implementation::RegUtil::ReadValue<HSTRING__ *>(
        HKEY hKey,
        LPCWSTR lpValueName,
        HSTRING *string)
{
  unsigned int v6; // eax
  HRESULT v7; // eax
  const char *v8; // r9
  unsigned __int64 v9; // rax
  WCHAR *v10; // rax
  unsigned int v11; // eax
  HRESULT v12; // eax
  __int64 result; // rax
  int lpData; // [rsp+20h] [rbp-38h]
  unsigned int lpDataa; // [rsp+20h] [rbp-38h]
  unsigned int lpDatab; // [rsp+20h] [rbp-38h]
  PCNZWCH sourceString[2]; // [rsp+30h] [rbp-28h] BYREF
  char v18; // [rsp+40h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  DWORD cbData; // [rsp+70h] [rbp+18h] BYREF
  DWORD Type; // [rsp+78h] [rbp+20h] BYREF

  try
  {
    if ( !string )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x4A,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\regutil.h",
        (const char *)0x80004003LL,
        lpData);
    *string = 0;
    sourceString[0] = 0;
    cbData = 0;
    Type = 0;
    v6 = RegQueryValueExW(hKey, lpValueName, 0, &Type, 0, &cbData);
    if ( v6 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x50,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\regutil.h",
        (const char *)v6,
        lpDataa);
    if ( Type != 1 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x53,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\regutil.h",
        (const char *)0x8000FFFFLL,
        lpDataa);
    if ( cbData > 0x202 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x54,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\regutil.h",
        (const char *)0x80A20F05LL,
        lpDataa);
    if ( cbData )
    {
      v9 = 2 * ((unsigned __int64)cbData >> 1);
      if ( !is_mul_ok((unsigned __int64)cbData >> 1, 2u) )
        v9 = -1;
      v10 = (WCHAR *)operator new[](v9, (const struct std::nothrow_t *)std::nothrow);
      sourceString[0] = v10;
      sourceString[1] = (PCNZWCH)sourceString;
      v18 = 1;
      if ( !v10 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x5F,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\regutil.h",
          (const char *)0x8007000ELL,
          lpDataa);
      v11 = RegQueryValueExW(hKey, lpValueName, 0, 0, (LPBYTE)v10, &cbData);
      if ( v11 )
        wil::details::in1diag3::Throw_Win32(
          retaddr,
          (void *)0x60,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\regutil.h",
          (const char *)v11,
          lpDatab);
      v12 = WindowsCreateString(sourceString[0], (cbData >> 1) - 1, string);
      if ( v12 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x62,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\regutil.h",
          (const char *)(unsigned int)v12,
          lpDatab);
      operator delete[]((void *)sourceString[0]);
    }
    else
    {
      v7 = WindowsCreateString(0, 0, string);
      if ( v7 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x58,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\regutil.h",
          (const char *)(unsigned int)v7,
          lpDataa);
    }
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x67,
                           (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\regutil.h",
                           v8);
  }
  return result;
}

```

## disassembly

```asm
0x18004df20  mov     [rsp+arg_0], rbx
0x18004df25  mov     [rsp+arg_8], rsi
0x18004df2a  push    rdi
0x18004df2b  sub     rsp, 50h
0x18004df2f  mov     rbx, r8
0x18004df32  mov     rdi, rdx
0x18004df35  mov     rsi, rcx
0x18004df38  mov     rcx, [rsp+58h]; this
0x18004df3d  test    rbx, rbx
0x18004df40  jnz     short loc_18004DF57
0x18004df42  mov     r9d, 80004003h; char *
0x18004df48  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\umstartup\\userm"...
0x18004df4f  lea     edx, [rbx+4Ah]; void *
0x18004df52  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004df57  mov     qword ptr [r8], 0
0x18004df5e  mov     [rsp+58h+sourceString], 0
0x18004df67  mov     [rsp+58h+cbData], 0
0x18004df6f  mov     [rsp+58h+Type], 0
0x18004df77  lea     rax, [rsp+58h+cbData]
0x18004df7c  mov     [rsp+58h+lpcbData], rax; lpcbData
0x18004df81  mov     [rsp+58h+lpData], 0; int
0x18004df8a  lea     r9, [rsp+58h+Type]; lpType
0x18004df8f  xor     r8d, r8d; lpReserved
0x18004df92  mov     rcx, rsi; hKey
0x18004df95  call    cs:__imp_RegQueryValueExW
0x18004df9b  mov     rcx, [rsp+58h]; this
0x18004dfa0  test    eax, eax
0x18004dfa2  jz      short loc_18004DFB8
0x18004dfa4  mov     r9d, eax; char *
0x18004dfa7  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\umstartup\\userm"...
0x18004dfae  mov     edx, 50h ; 'P'; void *
0x18004dfb3  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18004dfb8  cmp     [rsp+58h+Type], 1
0x18004dfbd  setz    al
0x18004dfc0  mov     rcx, [rsp+58h]; this
0x18004dfc5  test    al, al
0x18004dfc7  jnz     short loc_18004DFE0
0x18004dfc9  mov     r9d, 8000FFFFh; char *
0x18004dfcf  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\umstartup\\userm"...
0x18004dfd6  mov     edx, 53h ; 'S'; void *
0x18004dfdb  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004dfe0  mov     edx, [rsp+58h+cbData]; length
0x18004dfe4  cmp     edx, 202h
0x18004dfea  setnbe  al
0x18004dfed  mov     rcx, [rsp+58h]; this
0x18004dff2  test    al, al
0x18004dff4  jz      short loc_18004E00D
0x18004dff6  mov     r9d, 80A20F05h; char *
0x18004dffc  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\umstartup\\userm"...
0x18004e003  mov     edx, 54h ; 'T'; void *
0x18004e008  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004e00d  test    edx, edx
0x18004e00f  jnz     short loc_18004E03D
0x18004e011  mov     r8, rbx; string
0x18004e014  xor     ecx, ecx; sourceString
0x18004e016  call    cs:__imp_WindowsCreateString
0x18004e01c  mov     rcx, [rsp+58h]; this
0x18004e021  test    eax, eax
0x18004e023  jns     loc_18004E115
0x18004e029  mov     r9d, eax; char *
0x18004e02c  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\umstartup\\userm"...
0x18004e033  mov     edx, 58h ; 'X'; void *
0x18004e038  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004e03d  mov     rcx, rdx
0x18004e040  shr     rcx, 1
0x18004e043  mov     eax, 2
0x18004e048  mul     rcx
0x18004e04b  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18004e052  cmovb   rax, rcx
0x18004e056  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18004e05d  mov     rcx, rax; unsigned __int64
0x18004e060  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18004e065  mov     [rsp+58h+sourceString], rax
0x18004e06a  lea     rcx, [rsp+58h+sourceString]
0x18004e06f  mov     [rsp+58h+var_20], rcx
0x18004e074  mov     [rsp+58h+var_18], 1
0x18004e079  mov     rcx, [rsp+58h]; this
0x18004e07e  test    rax, rax
0x18004e081  jnz     short loc_18004E098
0x18004e083  mov     r9d, 8007000Eh; char *
0x18004e089  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\umstartup\\userm"...
0x18004e090  lea     edx, [rax+5Fh]; void *
0x18004e093  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004e098  lea     rcx, [rsp+58h+cbData]
0x18004e09d  mov     [rsp+58h+lpcbData], rcx; lpcbData
0x18004e0a2  mov     [rsp+58h+lpData], rax; int
0x18004e0a7  xor     r9d, r9d; lpType
0x18004e0aa  xor     r8d, r8d; lpReserved
0x18004e0ad  mov     rdx, rdi; lpValueName
0x18004e0b0  mov     rcx, rsi; hKey
0x18004e0b3  call    cs:__imp_RegQueryValueExW
0x18004e0b9  mov     rcx, [rsp+58h]; this
0x18004e0be  test    eax, eax
0x18004e0c0  jz      short loc_18004E0D6
0x18004e0c2  mov     r9d, eax; char *
0x18004e0c5  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\umstartup\\userm"...
0x18004e0cc  mov     edx, 60h ; '`'; void *
0x18004e0d1  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18004e0d6  mov     edx, [rsp+58h+cbData]
0x18004e0da  shr     edx, 1
0x18004e0dc  dec     edx; length
0x18004e0de  mov     r8, rbx; string
0x18004e0e1  mov     rcx, [rsp+58h+sourceString]; sourceString
0x18004e0e6  call    cs:__imp_WindowsCreateString
0x18004e0ec  mov     rcx, [rsp+58h]; this
0x18004e0f1  test    eax, eax
0x18004e0f3  jns     short loc_18004E10A
0x18004e0f5  mov     r9d, eax; char *
0x18004e0f8  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\umstartup\\userm"...
0x18004e0ff  mov     edx, 62h ; 'b'; void *
0x18004e104  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004e10a  mov     rcx, [rsp+58h+sourceString]
0x18004e10f  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18004e115  xor     eax, eax
0x18004e117  jmp     short loc_18004E11D
0x18004e119  mov     eax, [rsp+58h+cbData]
0x18004e11d  mov     rbx, [rsp+58h+arg_0]
0x18004e122  mov     rsi, [rsp+58h+arg_8]
0x18004e127  add     rsp, 50h
0x18004e12b  pop     rdi
0x18004e12c  retn
```
