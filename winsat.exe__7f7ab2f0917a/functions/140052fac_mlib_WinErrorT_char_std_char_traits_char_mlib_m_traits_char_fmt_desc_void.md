# mlib::WinErrorT<char,std::char_traits<char>,mlib::m_traits<char>>::fmt_desc(void)

- ea: `0x140052fac`
- end: `0x1400530a2`
- name: `?fmt_desc@?$WinErrorT@DU?$char_traits@D@std@@V?$m_traits@D@mlib@@@mlib@@AEAAKXZ`
- size: `246`
- prototype: `__int64 __fastcall(LPSTR lpBuffer)`
- caller_count: `11`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140013ed4`
- `0x14001a54c`
- `0x14002d9a4`
- `0x14002e584`
- `0x14002e924`
- `0x14002f430`
- `0x14002fe20`
- `0x140034990`
- `0x14003baec`
- `0x14003c9e0`
- `0x140047750`

## callees

- `0x140039f10`
- `0x140052fac`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x140053091`
- `KERNEL32!FreeLibrary` at `0x140053091`
- `KERNEL32!LoadLibraryExA` at `0x140052fca`
- `KERNEL32!LoadLibraryExA` at `0x140053001`
- `KERNEL32!LoadLibraryExA` at `0x140052fca`
- `KERNEL32!LoadLibraryExA` at `0x140053001`
- `KERNEL32!FormatMessageA` at `0x14005305a`
- `KERNEL32!FormatMessageA` at `0x14005305a`

## string_xrefs

- `0x140052ff2`: `netmsg.dll`
- `0x140053019`: `Wininet.dll`

## pseudocode

```c
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
0x140052fac  push    rbx
0x140052fae  push    rbp
0x140052faf  push    rsi
0x140052fb0  push    rdi
0x140052fb1  sub     rsp, 48h
0x140052fb5  mov     rbx, rcx
0x140052fb8  mov     rcx, [rcx+108h]; lpLibFileName
0x140052fbf  test    rcx, rcx
0x140052fc2  jz      short loc_140052FDC
0x140052fc4  xor     edx, edx; hFile
0x140052fc6  lea     r8d, [rdx+2]; dwFlags
0x140052fca  call    cs:__imp_LoadLibraryExA
0x140052fd0  mov     rbp, rax
0x140052fd3  lea     rdi, [rbx+100h]
0x140052fda  jmp     short loc_140053024
0x140052fdc  lea     rdi, [rbx+100h]
0x140052fe3  mov     ecx, [rdi]
0x140052fe5  lea     eax, [rcx-834h]
0x140052feb  cmp     eax, 383h
0x140052ff0  ja      short loc_14005300C
0x140052ff2  lea     rcx, aNetmsgDll; "netmsg.dll"
0x140052ff9  mov     r8d, 2; dwFlags
0x140052fff  xor     edx, edx; hFile
0x140053001  call    cs:__imp_LoadLibraryExA
0x140053007  mov     rbp, rax
0x14005300a  jmp     short loc_140053024
0x14005300c  lea     eax, [rcx-2EE0h]
0x140053012  cmp     eax, 0C0h
0x140053017  ja      short loc_140053022
0x140053019  lea     rcx, aWininetDll_0; "Wininet.dll"
0x140053020  jmp     short loc_140052FF9
0x140053022  xor     ebp, ebp
0x140053024  mov     r8d, [rdi]; dwMessageId
0x140053027  mov     rax, rbp
0x14005302a  neg     rax
0x14005302d  mov     [rsp+68h+Arguments], 0; Arguments
0x140053036  mov     [rsp+68h+nSize], 100h; nSize
0x14005303e  mov     r9d, 400h; dwLanguageId
0x140053044  sbb     ecx, ecx
0x140053046  mov     [rsp+68h+lpBuffer], rbx; lpBuffer
0x14005304b  and     ecx, 800h
0x140053051  mov     rdx, rbp; lpSource
0x140053054  add     ecx, 1000h; dwFlags
0x14005305a  call    cs:__imp_FormatMessageA
0x140053060  test    eax, eax
0x140053062  jnz     short loc_140053068
0x140053064  mov     [rbx], al
0x140053066  jmp     short loc_140053089
0x140053068  movsxd  rsi, eax
0x14005306b  dec     rsi
0x14005306e  add     rsi, rbx
0x140053071  jmp     short loc_140053084
0x140053073  mov     cl, [rsi]
0x140053075  call    ?isSpace@?$m_traits@D@mlib@@SA_ND@Z; mlib::m_traits<char>::isSpace(char)
0x14005307a  test    al, al
0x14005307c  jz      short loc_140053089
0x14005307e  mov     byte ptr [rsi], 0
0x140053081  dec     rsi
0x140053084  cmp     rsi, rbx
0x140053087  jnb     short loc_140053073
0x140053089  test    rbp, rbp
0x14005308c  jz      short loc_140053097
0x14005308e  mov     rcx, rbp; hLibModule
0x140053091  call    cs:__imp_FreeLibrary
0x140053097  mov     eax, [rdi]
0x140053099  add     rsp, 48h
0x14005309d  pop     rdi
0x14005309e  pop     rsi
0x14005309f  pop     rbp
0x1400530a0  pop     rbx
0x1400530a1  retn
```
