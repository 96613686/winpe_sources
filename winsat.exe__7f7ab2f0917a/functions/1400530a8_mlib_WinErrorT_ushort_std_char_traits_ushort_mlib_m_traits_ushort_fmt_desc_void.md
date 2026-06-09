# mlib::WinErrorT<ushort,std::char_traits<ushort>,mlib::m_traits<ushort>>::fmt_desc(void)

- ea: `0x1400530a8`
- end: `0x1400531a4`
- name: `?fmt_desc@?$WinErrorT@GU?$char_traits@G@std@@V?$m_traits@G@mlib@@@mlib@@AEAAKXZ`
- size: `252`
- prototype: `__int64 __fastcall(LPWSTR lpBuffer)`
- caller_count: `39`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140008ed0`
- `0x14000a5a8`
- `0x14000ad60`
- `0x14000af10`
- `0x14000b2a0`
- `0x14000d65c`
- `0x14000fcb8`
- `0x140010258`
- `0x140011b30`
- `0x140011f58`
- `0x1400120e0`
- `0x140012984`
- `0x14001a54c`
- `0x14001f0cc`
- `0x14001f494`
- `0x14001f5f8`
- `0x14001f9cc`
- `0x14001fea4`
- `0x1400335dc`
- `0x14003bdf4`
- `0x140059b90`
- `0x140059ef4`
- `0x14005ccd0`
- `0x14005f020`
- `0x140064f30`
- `0x140066080`
- `0x14006d680`
- `0x14006d940`
- `0x1400709f0`
- `0x1400719f0`
- `0x140074140`
- `0x140074340`
- `0x140076410`
- `0x140076b98`
- `0x140076d90`
- `0x140078b6c`
- `0x140078e90`
- `0x14011643e`
- `0x1401165c3`

## callees

- `0x1400188d0`
- `0x1400530a8`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x140053193`
- `KERNEL32!FreeLibrary` at `0x140053193`
- `KERNEL32!FormatMessageW` at `0x140053156`
- `KERNEL32!FormatMessageW` at `0x140053156`
- `KERNEL32!LoadLibraryExW` at `0x1400530c6`
- `KERNEL32!LoadLibraryExW` at `0x1400530fd`
- `KERNEL32!LoadLibraryExW` at `0x1400530c6`
- `KERNEL32!LoadLibraryExW` at `0x1400530fd`

## string_xrefs

- `0x1400530ee`: `netmsg.dll`
- `0x140053115`: `Wininet.dll`

## pseudocode

```c
__int64 __fastcall mlib::WinErrorT<unsigned short,std::char_traits<unsigned short>,mlib::m_traits<unsigned short>>::fmt_desc(
        _QWORD *lpBuffer)
{
  const WCHAR *v2; // rcx
  HMODULE Library; // rbp
  DWORD *v4; // rdi
  int v5; // ecx
  const WCHAR *v6; // rcx
  DWORD v7; // eax
  WCHAR *i; // rsi

  v2 = (const WCHAR *)lpBuffer[65];
  if ( v2 )
  {
    Library = LoadLibraryExW(v2, 0, 2u);
    v4 = (DWORD *)(lpBuffer + 64);
    goto LABEL_9;
  }
  v4 = (DWORD *)(lpBuffer + 64);
  v5 = *((_DWORD *)lpBuffer + 128);
  if ( (unsigned int)(v5 - 2100) <= 0x383 )
  {
    v6 = L"netmsg.dll";
LABEL_5:
    Library = LoadLibraryExW(v6, 0, 2u);
    goto LABEL_9;
  }
  if ( (unsigned int)(v5 - 12000) <= 0xC0 )
  {
    v6 = L"Wininet.dll";
    goto LABEL_5;
  }
  Library = 0;
LABEL_9:
  v7 = FormatMessageW(Library != 0 ? 6144 : 4096, Library, *v4, 0x400u, (LPWSTR)lpBuffer, 0x100u, 0);
  if ( v7 )
  {
    for ( i = (WCHAR *)lpBuffer + (int)v7 - 1;
          i >= (WCHAR *)lpBuffer && (unsigned __int8)mlib::m_traits<unsigned short>::isSpace(*i);
          --i )
    {
      *i = 0;
    }
  }
  else
  {
    *(_WORD *)lpBuffer = 0;
  }
  if ( Library )
    FreeLibrary(Library);
  return *v4;
}

```

## disassembly

```asm
0x1400530a8  push    rbx
0x1400530aa  push    rbp
0x1400530ab  push    rsi
0x1400530ac  push    rdi
0x1400530ad  sub     rsp, 48h
0x1400530b1  mov     rbx, rcx
0x1400530b4  mov     rcx, [rcx+208h]; lpLibFileName
0x1400530bb  test    rcx, rcx
0x1400530be  jz      short loc_1400530D8
0x1400530c0  xor     edx, edx; hFile
0x1400530c2  lea     r8d, [rdx+2]; dwFlags
0x1400530c6  call    cs:__imp_LoadLibraryExW
0x1400530cc  mov     rbp, rax
0x1400530cf  lea     rdi, [rbx+200h]
0x1400530d6  jmp     short loc_140053120
0x1400530d8  lea     rdi, [rbx+200h]
0x1400530df  mov     ecx, [rdi]
0x1400530e1  lea     eax, [rcx-834h]
0x1400530e7  cmp     eax, 383h
0x1400530ec  ja      short loc_140053108
0x1400530ee  lea     rcx, aNetmsgDll_0; "netmsg.dll"
0x1400530f5  mov     r8d, 2; dwFlags
0x1400530fb  xor     edx, edx; hFile
0x1400530fd  call    cs:__imp_LoadLibraryExW
0x140053103  mov     rbp, rax
0x140053106  jmp     short loc_140053120
0x140053108  lea     eax, [rcx-2EE0h]
0x14005310e  cmp     eax, 0C0h
0x140053113  ja      short loc_14005311E
0x140053115  lea     rcx, aWininetDll; "Wininet.dll"
0x14005311c  jmp     short loc_1400530F5
0x14005311e  xor     ebp, ebp
0x140053120  mov     r8d, [rdi]; dwMessageId
0x140053123  mov     rax, rbp
0x140053126  neg     rax
0x140053129  mov     [rsp+68h+Arguments], 0; Arguments
0x140053132  mov     [rsp+68h+nSize], 100h; nSize
0x14005313a  mov     r9d, 400h; dwLanguageId
0x140053140  sbb     ecx, ecx
0x140053142  mov     [rsp+68h+lpBuffer], rbx; lpBuffer
0x140053147  and     ecx, 800h
0x14005314d  mov     rdx, rbp; lpSource
0x140053150  add     ecx, 1000h; dwFlags
0x140053156  call    cs:__imp_FormatMessageW
0x14005315c  test    eax, eax
0x14005315e  jnz     short loc_140053165
0x140053160  mov     [rbx], ax
0x140053163  jmp     short loc_14005318B
0x140053165  movsxd  rsi, eax
0x140053168  dec     rsi
0x14005316b  lea     rsi, [rbx+rsi*2]
0x14005316f  jmp     short loc_140053186
0x140053171  movzx   ecx, word ptr [rsi]
0x140053174  call    ?isSpace@?$m_traits@G@mlib@@SA_NG@Z; mlib::m_traits<ushort>::isSpace(ushort)
0x140053179  test    al, al
0x14005317b  jz      short loc_14005318B
0x14005317d  xor     eax, eax
0x14005317f  mov     [rsi], ax
0x140053182  sub     rsi, 2
0x140053186  cmp     rsi, rbx
0x140053189  jnb     short loc_140053171
0x14005318b  test    rbp, rbp
0x14005318e  jz      short loc_140053199
0x140053190  mov     rcx, rbp; hLibModule
0x140053193  call    cs:__imp_FreeLibrary
0x140053199  mov     eax, [rdi]
0x14005319b  add     rsp, 48h
0x14005319f  pop     rdi
0x1400531a0  pop     rsi
0x1400531a1  pop     rbp
0x1400531a2  pop     rbx
0x1400531a3  retn
```
