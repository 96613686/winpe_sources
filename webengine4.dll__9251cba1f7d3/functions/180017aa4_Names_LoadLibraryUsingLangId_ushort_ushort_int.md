# Names::LoadLibraryUsingLangId(ushort,ushort *,int)

- ea: `0x180017aa4`
- end: `0x180017c66`
- name: `?LoadLibraryUsingLangId@Names@@CAPEAUHINSTANCE__@@GPEAGH@Z`
- size: `450`
- prototype: `static HINSTANCE(unsigned __int16, unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180017c68`

## callees

- `0x180002584`
- `0x180007824`
- `0x180016e08`
- `0x1800179ec`
- `0x180017aa4`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x180017b6c`
- `KERNEL32!LoadLibraryExW` at `0x180017bfb`
- `KERNEL32!LoadLibraryExW` at `0x180017b6c`
- `KERNEL32!LoadLibraryExW` at `0x180017bfb`
- `KERNEL32!lstrcmpW` at `0x180017c0e`
- `KERNEL32!lstrcmpW` at `0x180017c2b`
- `KERNEL32!lstrcmpW` at `0x180017c0e`
- `KERNEL32!lstrcmpW` at `0x180017c2b`

## string_xrefs

- `0x180017b4c`: `aspnet_rc.dll`
- `0x180017bdc`: `aspnet_rc.dll`

## pseudocode

```c
HINSTANCE __fastcall Names::LoadLibraryUsingLangId(unsigned __int16 a1, unsigned __int16 *a2, int a3)
{
  unsigned __int64 v3; // r15
  HMODULE Library; // rdi
  const unsigned __int16 *v6; // rbp
  const unsigned __int16 *v7; // r8
  LPCWSTR lpString1; // [rsp+20h] [rbp-28h] BYREF
  unsigned __int16 *v10; // [rsp+68h] [rbp+20h] BYREF

  v3 = a3;
  v10 = 0;
  lpString1 = 0;
  Library = 0;
  Names::ConvertLangIdToLanguageName(a1, &v10, (unsigned __int16 **)&lpString1);
  if ( v10 )
  {
    v6 = lpString1;
    if ( lpString1 )
    {
      if ( !(unsigned int)StringCchCopyW(a2, v3, &Names::s_wszInstallDirectory)
        && !(unsigned int)StringCchCatW(a2, v3, L"\\")
        && !(unsigned int)StringCchCatW(a2, v3, v10)
        && !(unsigned int)StringCchCatW(a2, v3, L"\\")
        && !(unsigned int)StringCchCatW(a2, v3, L"aspnet_rc.dll") )
      {
        Library = LoadLibraryExW(a2, 0, 2u);
      }
      if ( !Library )
      {
        if ( *v6 )
        {
          Library = 0;
          if ( !(unsigned int)StringCchCopyW(a2, v3, &Names::s_wszInstallDirectory)
            && !(unsigned int)StringCchCatW(a2, v3, L"\\")
            && !(unsigned int)StringCchCatW(a2, v3, v6)
            && !(unsigned int)StringCchCatW(a2, v3, L"\\")
            && !(unsigned int)StringCchCatW(a2, v3, L"aspnet_rc.dll") )
          {
            Library = LoadLibraryExW(a2, 0, 2u);
          }
        }
      }
      if ( !lstrcmpW(v6, L"zh-CHS") )
      {
        v7 = L"zh-Hans";
        return Names::LoadLibraryForCulture(a2, v3, v7);
      }
      if ( !lstrcmpW(v6, L"zh-CHT") )
      {
        v7 = L"zh-Hant";
        return Names::LoadLibraryForCulture(a2, v3, v7);
      }
    }
  }
  return Library;
}

```

## disassembly

```asm
0x180017aa4  mov     rax, rsp
0x180017aa7  mov     [rax+8], rbx
0x180017aab  mov     [rax+10h], rbp
0x180017aaf  mov     [rax+18h], rsi
0x180017ab3  push    rdi
0x180017ab4  push    r12
0x180017ab6  push    r15
0x180017ab8  sub     rsp, 30h
0x180017abc  xor     r12d, r12d
0x180017abf  movsxd  r15, r8d
0x180017ac2  mov     rbx, rdx
0x180017ac5  mov     [rax+20h], r12
0x180017ac9  lea     r8, [rax-28h]; unsigned __int16 **
0x180017acd  mov     [rax-28h], r12
0x180017ad1  lea     rdx, [rax+20h]; unsigned __int16 **
0x180017ad5  mov     edi, r12d
0x180017ad8  call    ?ConvertLangIdToLanguageName@Names@@SAJGPEAPEAG0@Z; Names::ConvertLangIdToLanguageName(ushort,ushort * *,ushort * *)
0x180017add  cmp     [rsp+48h+arg_18], r12
0x180017ae2  jz      loc_180017C4A
0x180017ae8  mov     rbp, [rsp+48h+lpString1]
0x180017aed  test    rbp, rbp
0x180017af0  jz      loc_180017C4A
0x180017af6  lea     r8, ?s_wszInstallDirectory@Names@@0PAGA; unsigned __int16 *
0x180017afd  mov     rdx, r15; unsigned __int64
0x180017b00  mov     rcx, rbx; unsigned __int16 *
0x180017b03  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180017b08  test    eax, eax
0x180017b0a  jnz     short loc_180017B75
0x180017b0c  lea     r8, SubBlock; "\\"
0x180017b13  mov     rdx, r15; unsigned __int64
0x180017b16  mov     rcx, rbx; unsigned __int16 *
0x180017b19  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180017b1e  test    eax, eax
0x180017b20  jnz     short loc_180017B75
0x180017b22  mov     r8, [rsp+48h+arg_18]; unsigned __int16 *
0x180017b27  mov     rdx, r15; unsigned __int64
0x180017b2a  mov     rcx, rbx; unsigned __int16 *
0x180017b2d  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180017b32  test    eax, eax
0x180017b34  jnz     short loc_180017B75
0x180017b36  lea     r8, SubBlock; "\\"
0x180017b3d  mov     rdx, r15; unsigned __int64
0x180017b40  mov     rcx, rbx; unsigned __int16 *
0x180017b43  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180017b48  test    eax, eax
0x180017b4a  jnz     short loc_180017B75
0x180017b4c  lea     r8, aAspnetRcDll; "aspnet_rc.dll"
0x180017b53  mov     rdx, r15; unsigned __int64
0x180017b56  mov     rcx, rbx; unsigned __int16 *
0x180017b59  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180017b5e  test    eax, eax
0x180017b60  jnz     short loc_180017B75
0x180017b62  xor     edx, edx; hFile
0x180017b64  lea     r8d, [r12+2]; dwFlags
0x180017b69  mov     rcx, rbx; lpLibFileName
0x180017b6c  call    cs:__imp_LoadLibraryExW
0x180017b72  mov     rdi, rax
0x180017b75  test    rdi, rdi
0x180017b78  jnz     loc_180017C04
0x180017b7e  cmp     [rbp+0], r12w
0x180017b83  jz      short loc_180017C04
0x180017b85  lea     r8, ?s_wszInstallDirectory@Names@@0PAGA; unsigned __int16 *
0x180017b8c  mov     rdx, r15; unsigned __int64
0x180017b8f  mov     rcx, rbx; unsigned __int16 *
0x180017b92  mov     rdi, r12
0x180017b95  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180017b9a  test    eax, eax
0x180017b9c  jnz     short loc_180017C04
0x180017b9e  lea     r8, SubBlock; "\\"
0x180017ba5  mov     rdx, r15; unsigned __int64
0x180017ba8  mov     rcx, rbx; unsigned __int16 *
0x180017bab  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180017bb0  test    eax, eax
0x180017bb2  jnz     short loc_180017C04
0x180017bb4  mov     r8, rbp; unsigned __int16 *
0x180017bb7  mov     rdx, r15; unsigned __int64
0x180017bba  mov     rcx, rbx; unsigned __int16 *
0x180017bbd  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180017bc2  test    eax, eax
0x180017bc4  jnz     short loc_180017C04
0x180017bc6  lea     r8, SubBlock; "\\"
0x180017bcd  mov     rdx, r15; unsigned __int64
0x180017bd0  mov     rcx, rbx; unsigned __int16 *
0x180017bd3  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180017bd8  test    eax, eax
0x180017bda  jnz     short loc_180017C04
0x180017bdc  lea     r8, aAspnetRcDll; "aspnet_rc.dll"
0x180017be3  mov     rdx, r15; unsigned __int64
0x180017be6  mov     rcx, rbx; unsigned __int16 *
0x180017be9  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180017bee  test    eax, eax
0x180017bf0  jnz     short loc_180017C04
0x180017bf2  xor     edx, edx; hFile
0x180017bf4  lea     r8d, [rax+2]; dwFlags
0x180017bf8  mov     rcx, rbx; lpLibFileName
0x180017bfb  call    cs:__imp_LoadLibraryExW
0x180017c01  mov     rdi, rax
0x180017c04  lea     rdx, aZhChs; "zh-CHS"
0x180017c0b  mov     rcx, rbp; lpString1
0x180017c0e  call    cs:__imp_lstrcmpW
0x180017c14  test    eax, eax
0x180017c16  jnz     short loc_180017C21
0x180017c18  lea     r8, aZhHans; "zh-Hans"
0x180017c1f  jmp     short loc_180017C3C
0x180017c21  lea     rdx, aZhCht; "zh-CHT"
0x180017c28  mov     rcx, rbp; lpString1
0x180017c2b  call    cs:__imp_lstrcmpW
0x180017c31  test    eax, eax
0x180017c33  jnz     short loc_180017C4A
0x180017c35  lea     r8, aZhHant; "zh-Hant"
0x180017c3c  mov     edx, r15d; int
0x180017c3f  mov     rcx, rbx; unsigned __int16 *
0x180017c42  call    ?LoadLibraryForCulture@Names@@CAPEAUHINSTANCE__@@PEAGHPEBG@Z; Names::LoadLibraryForCulture(ushort *,int,ushort const *)
0x180017c47  mov     rdi, rax
0x180017c4a  mov     rbx, [rsp+48h+arg_0]
0x180017c4f  mov     rax, rdi
0x180017c52  mov     rbp, [rsp+48h+arg_8]
0x180017c57  mov     rsi, [rsp+48h+arg_10]
0x180017c5c  add     rsp, 30h
0x180017c60  pop     r15
0x180017c62  pop     r12
0x180017c64  pop     rdi
0x180017c65  retn
```
