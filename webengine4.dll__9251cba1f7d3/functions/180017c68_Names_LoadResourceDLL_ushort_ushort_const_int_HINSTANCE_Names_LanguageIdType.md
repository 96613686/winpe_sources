# Names::LoadResourceDLL(ushort *,ushort * const,int,HINSTANCE__ * *,Names::LanguageIdType)

- ea: `0x180017c68`
- end: `0x180017d8f`
- name: `?LoadResourceDLL@Names@@SAJPEAGQEAGHPEAPEAUHINSTANCE__@@W4LanguageIdType@1@@Z`
- size: `295`
- prototype: `static int __high(unsigned __int16 *, unsigned __int16 *const, int, HINSTANCE *, enum Names::LanguageIdType)`
- caller_count: `2`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callers

- `0x180016e00`
- `0x180016fd8`

## callees

- `0x180002584`
- `0x180007824`
- `0x180016eb0`
- `0x180017aa4`
- `0x180017c68`
- `0x18004d350`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x180017d5d`
- `KERNEL32!LoadLibraryExW` at `0x180017d5d`
- `KERNEL32!GetSystemDefaultUILanguage` at `0x180017cec`
- `KERNEL32!GetSystemDefaultUILanguage` at `0x180017cec`
- `KERNEL32!GetUserDefaultUILanguage` at `0x180017c99`
- `KERNEL32!GetUserDefaultUILanguage` at `0x180017c99`

## string_xrefs

- `0x180017d3c`: `aspnet_rc.dll`

## pseudocode

```c
__int64 __fastcall Names::LoadResourceDLL(LANGID *a1, unsigned __int16 *a2, int a3, HINSTANCE *a4, int a5)
{
  unsigned int v5; // ebx
  unsigned __int64 v6; // rbp
  LANGID UserDefaultUILanguage; // ax
  HINSTANCE LibraryUsingLangId; // rax
  unsigned __int16 ConsoleLangId; // ax
  HINSTANCE v13; // rax
  LANGID SystemDefaultUILanguage; // ax
  HMODULE Library; // rax

  v5 = 0;
  v6 = a3;
  *a4 = 0;
  if ( a5 == 2 )
  {
    UserDefaultUILanguage = GetUserDefaultUILanguage();
    *a1 = UserDefaultUILanguage;
    LibraryUsingLangId = Names::LoadLibraryUsingLangId(UserDefaultUILanguage, a2, v6);
    *a4 = LibraryUsingLangId;
    if ( !LibraryUsingLangId )
    {
LABEL_7:
      SystemDefaultUILanguage = GetSystemDefaultUILanguage();
      *a1 = SystemDefaultUILanguage;
      *a4 = Names::LoadLibraryUsingLangId(SystemDefaultUILanguage, a2, v6);
    }
  }
  else if ( a5 == 1 )
  {
    ConsoleLangId = GetConsoleLangId();
    *a1 = ConsoleLangId;
    v13 = Names::LoadLibraryUsingLangId(ConsoleLangId, a2, v6);
    *a4 = v13;
    if ( !v13 && *a1 != 1033 )
      goto LABEL_7;
  }
  if ( !*a4 )
  {
    v5 = StringCchCopyW(a2, v6, &Names::s_wszInstallDirectory);
    if ( !v5 )
    {
      v5 = StringCchCatW(a2, v6, L"\\");
      if ( !v5 )
      {
        v5 = StringCchCatW(a2, v6, L"aspnet_rc.dll");
        if ( !v5 )
        {
          Library = LoadLibraryExW(a2, 0, 2u);
          *a4 = Library;
          if ( !Library )
            return (unsigned int)GetLastWin32Error();
        }
      }
    }
  }
  return v5;
}

```

## disassembly

```asm
0x180017c68  mov     rax, rsp
0x180017c6b  mov     [rax+8], rbx
0x180017c6f  mov     [rax+10h], rbp
0x180017c73  mov     [rax+18h], rsi
0x180017c77  mov     [rax+20h], rdi
0x180017c7b  push    r14
0x180017c7d  sub     rsp, 20h
0x180017c81  xor     ebx, ebx
0x180017c83  movsxd  rbp, r8d
0x180017c86  and     [r9], rbx
0x180017c89  mov     rsi, r9
0x180017c8c  cmp     [rsp+28h+arg_20], 2
0x180017c91  mov     rdi, rdx
0x180017c94  mov     r14, rcx
0x180017c97  jnz     short loc_180017CBB
0x180017c99  call    cs:__imp_GetUserDefaultUILanguage
0x180017c9f  mov     r8d, ebp; int
0x180017ca2  mov     rdx, rdi; unsigned __int16 *
0x180017ca5  movzx   ecx, ax; unsigned __int16
0x180017ca8  mov     [r14], ax
0x180017cac  call    ?LoadLibraryUsingLangId@Names@@CAPEAUHINSTANCE__@@GPEAGH@Z; Names::LoadLibraryUsingLangId(ushort,ushort *,int)
0x180017cb1  mov     [rsi], rax
0x180017cb4  test    rax, rax
0x180017cb7  jnz     short loc_180017D07
0x180017cb9  jmp     short loc_180017CEC
0x180017cbb  cmp     [rsp+28h+arg_20], 1
0x180017cc0  jnz     short loc_180017D07
0x180017cc2  call    ?GetConsoleLangId@@YAGXZ; GetConsoleLangId(void)
0x180017cc7  mov     r8d, ebp; int
0x180017cca  mov     [r14], ax
0x180017cce  mov     rdx, rdi; unsigned __int16 *
0x180017cd1  movzx   ecx, ax; unsigned __int16
0x180017cd4  call    ?LoadLibraryUsingLangId@Names@@CAPEAUHINSTANCE__@@GPEAGH@Z; Names::LoadLibraryUsingLangId(ushort,ushort *,int)
0x180017cd9  mov     [rsi], rax
0x180017cdc  test    rax, rax
0x180017cdf  jnz     short loc_180017D07
0x180017ce1  mov     eax, 409h
0x180017ce6  cmp     [r14], ax
0x180017cea  jz      short loc_180017D07
0x180017cec  call    cs:__imp_GetSystemDefaultUILanguage
0x180017cf2  mov     r8d, ebp; int
0x180017cf5  mov     rdx, rdi; unsigned __int16 *
0x180017cf8  movzx   ecx, ax; unsigned __int16
0x180017cfb  mov     [r14], ax
0x180017cff  call    ?LoadLibraryUsingLangId@Names@@CAPEAUHINSTANCE__@@GPEAGH@Z; Names::LoadLibraryUsingLangId(ushort,ushort *,int)
0x180017d04  mov     [rsi], rax
0x180017d07  cmp     [rsi], rbx
0x180017d0a  jnz     short loc_180017D72
0x180017d0c  lea     r8, ?s_wszInstallDirectory@Names@@0PAGA; unsigned __int16 *
0x180017d13  mov     rdx, rbp; unsigned __int64
0x180017d16  mov     rcx, rdi; unsigned __int16 *
0x180017d19  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180017d1e  mov     ebx, eax
0x180017d20  test    eax, eax
0x180017d22  jnz     short loc_180017D72
0x180017d24  lea     r8, SubBlock; "\\"
0x180017d2b  mov     rdx, rbp; unsigned __int64
0x180017d2e  mov     rcx, rdi; unsigned __int16 *
0x180017d31  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180017d36  mov     ebx, eax
0x180017d38  test    eax, eax
0x180017d3a  jnz     short loc_180017D72
0x180017d3c  lea     r8, aAspnetRcDll; "aspnet_rc.dll"
0x180017d43  mov     rdx, rbp; unsigned __int64
0x180017d46  mov     rcx, rdi; unsigned __int16 *
0x180017d49  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180017d4e  mov     ebx, eax
0x180017d50  test    eax, eax
0x180017d52  jnz     short loc_180017D72
0x180017d54  xor     edx, edx; hFile
0x180017d56  lea     r8d, [rax+2]; dwFlags
0x180017d5a  mov     rcx, rdi; lpLibFileName
0x180017d5d  call    cs:__imp_LoadLibraryExW
0x180017d63  mov     [rsi], rax
0x180017d66  test    rax, rax
0x180017d69  jnz     short loc_180017D72
0x180017d6b  call    ?GetLastWin32Error@@YAJXZ; GetLastWin32Error(void)
0x180017d70  mov     ebx, eax
0x180017d72  mov     rbp, [rsp+28h+arg_8]
0x180017d77  mov     eax, ebx
0x180017d79  mov     rbx, [rsp+28h+arg_0]
0x180017d7e  mov     rsi, [rsp+28h+arg_10]
0x180017d83  mov     rdi, [rsp+28h+arg_18]
0x180017d88  add     rsp, 20h
0x180017d8c  pop     r14
0x180017d8e  retn
```
