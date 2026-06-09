# CUserNameFormat::FormatDisplayName(ushort const *,ushort const *,ushort * *,bool *)

- ea: `0x180069578`
- end: `0x180069630`
- name: `?FormatDisplayName@CUserNameFormat@@QEAAJPEBG0PEAPEAGPEA_N@Z`
- size: `184`
- prototype: `int(CUserNameFormat *__hidden this, const unsigned __int16 *, const unsigned __int16 *, unsigned __int16 **, bool *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18003ff0c`

## callees

- `0x180026218`
- `0x180063d40`
- `0x180069578`
- `0x180069798`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18006959e`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18006959e`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18006961d`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18006961d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800695ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800695ac`

## string_xrefs

- `0x180069585`: `ShCore.dll`

## pseudocode

```c
__int64 __fastcall CUserNameFormat::FormatDisplayName(
        CUserNameFormat *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        unsigned __int16 **a4)
{
  HMODULE Library; // rax
  const WCHAR *v8; // rcx
  HMODULE v9; // rsi
  signed int LastError; // eax
  unsigned int v11; // ebx
  bool IsDefaultNameFormatSupported; // al
  bool v13; // zf
  unsigned int v14; // eax

  *a4 = 0;
  Library = LoadLibraryExW(L"ShCore.dll", 0, 0x22u);
  v9 = Library;
  if ( Library )
  {
    IsDefaultNameFormatSupported = CUserNameFormat::_IsDefaultNameFormatSupported(v8, Library, a2, a3);
    if ( *a2 )
    {
      v13 = *a3 == 0;
      if ( *a3 )
      {
        v14 = ResourceStringCoAllocFormatMessage(v9, !IsDefaultNameFormatSupported + 1002, a4, a2, a3);
LABEL_14:
        v11 = v14;
        FreeLibrary(v9);
        return v11;
      }
    }
    else
    {
      v13 = *a3 == 0;
    }
    if ( !v13 )
      a2 = a3;
    v14 = CoAllocString(a2, a4);
    goto LABEL_14;
  }
  LastError = GetLastError();
  v11 = LastError;
  if ( LastError > 0 )
    v11 = (unsigned __int16)LastError | 0x80070000;
  if ( (v11 & 0x80000000) == 0 )
    return (unsigned int)-2147467259;
  return v11;
}

```

## disassembly

```asm
0x180069578  push    rbx
0x18006957a  push    rbp
0x18006957b  push    rsi
0x18006957c  push    rdi
0x18006957d  push    r14
0x18006957f  sub     rsp, 30h
0x180069583  xor     ebp, ebp
0x180069585  lea     rcx, aShcoreDll_0; "ShCore.dll"
0x18006958c  mov     rdi, r8
0x18006958f  mov     [r9], rbp
0x180069592  mov     rbx, rdx
0x180069595  mov     r14, r9
0x180069598  xor     edx, edx; hFile
0x18006959a  lea     r8d, [rbp+22h]; dwFlags
0x18006959e  call    cs:__imp_LoadLibraryExW
0x1800695a4  mov     rsi, rax
0x1800695a7  test    rax, rax
0x1800695aa  jnz     short loc_1800695CD
0x1800695ac  call    cs:__imp_GetLastError
0x1800695b2  mov     ebx, eax
0x1800695b4  test    eax, eax
0x1800695b6  jle     short loc_1800695C1
0x1800695b8  movzx   ebx, ax
0x1800695bb  or      ebx, 80070000h
0x1800695c1  test    ebx, ebx
0x1800695c3  mov     eax, 80004005h
0x1800695c8  cmovns  ebx, eax
0x1800695cb  jmp     short loc_180069623
0x1800695cd  mov     r9, rdi; unsigned __int16 *
0x1800695d0  mov     r8, rbx; unsigned __int16 *
0x1800695d3  mov     rdx, rsi; HINSTANCE
0x1800695d6  call    ?_IsDefaultNameFormatSupported@CUserNameFormat@@AEAA_NPEAUHINSTANCE__@@PEBG1@Z; CUserNameFormat::_IsDefaultNameFormatSupported(HINSTANCE__ *,ushort const *,ushort const *)
0x1800695db  cmp     [rbx], bp
0x1800695de  jz      short loc_180069606
0x1800695e0  cmp     [rdi], bp
0x1800695e3  jz      short loc_180069609
0x1800695e5  movzx   edx, al
0x1800695e8  mov     r9, rbx
0x1800695eb  xor     edx, 1
0x1800695ee  mov     [rsp+58h+var_38], rdi
0x1800695f3  add     edx, 3EAh
0x1800695f9  mov     r8, r14
0x1800695fc  mov     rcx, rsi
0x1800695ff  call    ResourceStringCoAllocFormatMessage
0x180069604  jmp     short loc_180069618
0x180069606  cmp     [rdi], bp
0x180069609  cmovnz  rbx, rdi
0x18006960d  mov     rdx, r14; unsigned __int16 **
0x180069610  mov     rcx, rbx; unsigned __int16 *
0x180069613  call    ?CoAllocString@@YAJPEBGPEAPEAG@Z; CoAllocString(ushort const *,ushort * *)
0x180069618  mov     rcx, rsi; hLibModule
0x18006961b  mov     ebx, eax
0x18006961d  call    cs:__imp_FreeLibrary
0x180069623  mov     eax, ebx
0x180069625  add     rsp, 30h
0x180069629  pop     r14
0x18006962b  pop     rdi
0x18006962c  pop     rsi
0x18006962d  pop     rbp
0x18006962e  pop     rbx
0x18006962f  retn
```
