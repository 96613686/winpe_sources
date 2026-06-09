# mlib::WinErrorT<char,std::char_traits<char>,mlib::m_traits<char>>::fmt_desc(void)

- ea: `0x18002d328`
- end: `0x18002d41e`
- name: `?fmt_desc@?$WinErrorT@DU?$char_traits@D@std@@V?$m_traits@D@mlib@@@mlib@@AEAAKXZ`
- size: `246`
- prototype: `__int64 __fastcall(_QWORD *lpBuffer)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800209fc`
- `0x18002177c`

## callees

- `0x18001bf78`
- `0x18002d328`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x18002d346`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x18002d37d`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x18002d346`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x18002d37d`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18002d40d`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18002d40d`
- `api-ms-win-core-localization-l1-2-0!FormatMessageA` at `0x18002d3d6`
- `api-ms-win-core-localization-l1-2-0!FormatMessageA` at `0x18002d3d6`

## string_xrefs

- `0x18002d36e`: `netmsg.dll`
- `0x18002d395`: `Wininet.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall mlib::WinErrorT<char,std::char_traits<char>,mlib::m_traits<char>>::fmt_desc(_QWORD *lpBuffer)
{
  const CHAR *v2; // rcx
  HMODULE Library; // rbp
  DWORD *v4; // rdi
  int v5; // ecx
  const CHAR *v6; // rcx
  DWORD v7; // eax
  __int64 v8; // rcx
  CHAR *i; // rsi

  v2 = (const CHAR *)lpBuffer[33];
  if ( v2 )
  {
    Library = LoadLibraryExA(v2, 0, 2u);
    v4 = (DWORD *)(lpBuffer + 32);
    goto LABEL_9;
  }
  v4 = (DWORD *)(lpBuffer + 32);
  v5 = *((_DWORD *)lpBuffer + 64);
  if ( (unsigned int)(v5 - 2100) <= 0x383 )
  {
    v6 = "netmsg.dll";
LABEL_5:
    Library = LoadLibraryExA(v6, 0, 2u);
    goto LABEL_9;
  }
  if ( (unsigned int)(v5 - 12000) <= 0xC0 )
  {
    v6 = "Wininet.dll";
    goto LABEL_5;
  }
  Library = 0;
LABEL_9:
  v7 = FormatMessageA(Library != 0 ? 6144 : 4096, Library, *v4, 0x400u, (LPSTR)lpBuffer, 0x100u, 0);
  if ( v7 )
  {
    for ( i = (char *)lpBuffer + (int)v7 - 1; i >= (CHAR *)lpBuffer; --i )
    {
      LOBYTE(v8) = *i;
      if ( !(unsigned __int8)mlib::m_traits<char>::isSpace(v8) )
        break;
      *i = 0;
    }
  }
  else
  {
    *(_BYTE *)lpBuffer = 0;
  }
  if ( Library )
    FreeLibrary(Library);
  return *v4;
}

```

## disassembly

```asm
0x18002d328  push    rbx
0x18002d32a  push    rbp
0x18002d32b  push    rsi
0x18002d32c  push    rdi
0x18002d32d  sub     rsp, 48h
0x18002d331  mov     rbx, rcx
0x18002d334  mov     rcx, [rcx+108h]; lpLibFileName
0x18002d33b  test    rcx, rcx
0x18002d33e  jz      short loc_18002D358
0x18002d340  xor     edx, edx; hFile
0x18002d342  lea     r8d, [rdx+2]; dwFlags
0x18002d346  call    cs:__imp_LoadLibraryExA
0x18002d34c  mov     rbp, rax
0x18002d34f  lea     rdi, [rbx+100h]
0x18002d356  jmp     short loc_18002D3A0
0x18002d358  lea     rdi, [rbx+100h]
0x18002d35f  mov     ecx, [rdi]
0x18002d361  lea     eax, [rcx-834h]
0x18002d367  cmp     eax, 383h
0x18002d36c  ja      short loc_18002D388
0x18002d36e  lea     rcx, aNetmsgDll; "netmsg.dll"
0x18002d375  mov     r8d, 2; dwFlags
0x18002d37b  xor     edx, edx; hFile
0x18002d37d  call    cs:__imp_LoadLibraryExA
0x18002d383  mov     rbp, rax
0x18002d386  jmp     short loc_18002D3A0
0x18002d388  lea     eax, [rcx-2EE0h]
0x18002d38e  cmp     eax, 0C0h
0x18002d393  ja      short loc_18002D39E
0x18002d395  lea     rcx, aWininetDll; "Wininet.dll"
0x18002d39c  jmp     short loc_18002D375
0x18002d39e  xor     ebp, ebp
0x18002d3a0  mov     r8d, [rdi]; dwMessageId
0x18002d3a3  mov     rax, rbp
0x18002d3a6  neg     rax
0x18002d3a9  mov     [rsp+68h+Arguments], 0; Arguments
0x18002d3b2  mov     [rsp+68h+nSize], 100h; nSize
0x18002d3ba  mov     r9d, 400h; dwLanguageId
0x18002d3c0  sbb     ecx, ecx
0x18002d3c2  mov     [rsp+68h+lpBuffer], rbx; lpBuffer
0x18002d3c7  and     ecx, 800h
0x18002d3cd  mov     rdx, rbp; lpSource
0x18002d3d0  add     ecx, 1000h; dwFlags
0x18002d3d6  call    cs:__imp_FormatMessageA
0x18002d3dc  test    eax, eax
0x18002d3de  jnz     short loc_18002D3E4
0x18002d3e0  mov     [rbx], al
0x18002d3e2  jmp     short loc_18002D405
0x18002d3e4  movsxd  rsi, eax
0x18002d3e7  dec     rsi
0x18002d3ea  add     rsi, rbx
0x18002d3ed  jmp     short loc_18002D400
0x18002d3ef  mov     cl, [rsi]
0x18002d3f1  call    ?isSpace@?$m_traits@D@mlib@@SA_ND@Z; mlib::m_traits<char>::isSpace(char)
0x18002d3f6  test    al, al
0x18002d3f8  jz      short loc_18002D405
0x18002d3fa  mov     byte ptr [rsi], 0
0x18002d3fd  dec     rsi
0x18002d400  cmp     rsi, rbx
0x18002d403  jnb     short loc_18002D3EF
0x18002d405  test    rbp, rbp
0x18002d408  jz      short loc_18002D413
0x18002d40a  mov     rcx, rbp; hLibModule
0x18002d40d  call    cs:__imp_FreeLibrary
0x18002d413  mov     eax, [rdi]
0x18002d415  add     rsp, 48h
0x18002d419  pop     rdi
0x18002d41a  pop     rsi
0x18002d41b  pop     rbp
0x18002d41c  pop     rbx
0x18002d41d  retn
```
