# MailToProtocolHandler

- ea: `0x180001b10`
- end: `0x180001c16`
- name: `MailToProtocolHandler`
- size: `262`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001b10`
- `0x1800021b2`
- `0x180003010`

## import_xrefs

- `KERNEL32!LoadLibraryExA` at `0x180001b33`
- `KERNEL32!LoadLibraryExA` at `0x180001b33`
- `KERNEL32!GetProcAddress` at `0x180001b55`
- `KERNEL32!GetProcAddress` at `0x180001b55`
- `KERNEL32!FreeLibrary` at `0x180001bfd`
- `KERNEL32!FreeLibrary` at `0x180001bfd`
- `SHLWAPI!__imp_ParseURLA` at `0x180001b87`
- `SHLWAPI!__imp_ParseURLA` at `0x180001b87`

## string_xrefs

- `0x180001b24`: `mapi32.dll`

## pseudocode

```c
int __fastcall MailToProtocolHandler(__int64 a1, __int64 a2, const CHAR *a3)
{
  HMODULE Library; // rax
  HMODULE v5; // rbx
  FARPROC ProcAddress; // rdi
  PARSEDURLA ppu; // [rsp+30h] [rbp-79h] BYREF
  _DWORD v9[2]; // [rsp+58h] [rbp-51h] BYREF
  LPCSTR pszSuffix; // [rsp+60h] [rbp-49h]
  __int128 v11; // [rsp+68h] [rbp-41h]
  __int64 v12; // [rsp+78h] [rbp-31h]
  _BYTE v13[64]; // [rsp+80h] [rbp-29h] BYREF
  int v14; // [rsp+C0h] [rbp+17h]
  _DWORD *v15; // [rsp+C8h] [rbp+1Fh]

  Library = LoadLibraryExA("mapi32.dll", 0, 0x800u);
  v5 = Library;
  if ( Library )
  {
    ProcAddress = GetProcAddress(Library, "MAPISendMail");
    if ( ProcAddress )
    {
      *(_QWORD *)&ppu.cbSize = 40;
      memset(&ppu.pszProtocol, 0, 32);
      if ( ParseURLA(a3, &ppu) >= 0 && ppu.nScheme == 4 )
      {
        v9[0] = 0;
        v12 = 0;
        v9[1] = 1;
        v11 = 0;
        pszSuffix = ppu.pszSuffix;
        memset_0(v13, 0, 0x60u);
        v14 = 1;
        v15 = v9;
        ((void (__fastcall *)(_QWORD, _QWORD, _BYTE *, __int64, _DWORD))ProcAddress)(0, 0, v13, 9, 0);
      }
    }
    LODWORD(Library) = FreeLibrary(v5);
  }
  return (int)Library;
}

```

## disassembly

```asm
0x180001b10  push    rbp; MailToProtocolHandler
0x180001b12  push    rbx
0x180001b13  push    rsi
0x180001b14  push    rdi
0x180001b15  lea     rbp, [rsp-3Fh]
0x180001b1a  sub     rsp, 0E8h
0x180001b21  mov     rsi, r8
0x180001b24  lea     rcx, LibFileName; "mapi32.dll"
0x180001b2b  mov     r8d, 800h; dwFlags
0x180001b31  xor     edx, edx; hFile
0x180001b33  call    cs:__imp_LoadLibraryExA
0x180001b3a  nop     dword ptr [rax+rax+00h]
0x180001b3f  mov     rbx, rax
0x180001b42  test    rax, rax
0x180001b45  jz      loc_180001C09
0x180001b4b  lea     rdx, ProcName; "MAPISendMail"
0x180001b52  mov     rcx, rax; hModule
0x180001b55  call    cs:__imp_GetProcAddress
0x180001b5c  nop     dword ptr [rax+rax+00h]
0x180001b61  mov     rdi, rax
0x180001b64  test    rax, rax
0x180001b67  jz      loc_180001BFA
0x180001b6d  xorps   xmm0, xmm0
0x180001b70  mov     qword ptr [rbp+57h+ppu.cbSize], 28h ; '('
0x180001b78  lea     rdx, [rbp+57h+ppu]; ppu
0x180001b7c  mov     rcx, rsi; pcszURL
0x180001b7f  movups  xmmword ptr [rbp+57h+ppu.pszProtocol], xmm0
0x180001b83  movups  xmmword ptr [rbp+57h+ppu.pszSuffix], xmm0
0x180001b87  call    cs:__imp_ParseURLA
0x180001b8e  nop     dword ptr [rax+rax+00h]
0x180001b93  test    eax, eax
0x180001b95  js      short loc_180001BFA
0x180001b97  cmp     [rbp+57h+ppu.nScheme], 4
0x180001b9b  jnz     short loc_180001BFA
0x180001b9d  mov     rax, [rbp+57h+ppu.pszSuffix]
0x180001ba1  lea     rcx, [rbp+57h+var_80]; void *
0x180001ba5  mov     esi, 1
0x180001baa  mov     [rbp+57h+var_A8], 0
0x180001bb1  xorps   xmm0, xmm0
0x180001bb4  mov     [rbp+57h+var_88], 0
0x180001bbc  xor     edx, edx; Val
0x180001bbe  mov     [rbp+57h+var_A4], esi
0x180001bc1  movdqu  [rbp+57h+var_98], xmm0
0x180001bc6  lea     r8d, [rsi+5Fh]; Size
0x180001bca  mov     [rbp+57h+var_A0], rax
0x180001bce  call    memset_0
0x180001bd3  lea     rax, [rbp+57h+var_A8]
0x180001bd7  mov     [rbp+57h+var_40], esi
0x180001bda  mov     [rbp+57h+var_38], rax
0x180001bde  lea     r9d, [rsi+8]
0x180001be2  mov     rax, rdi
0x180001be5  mov     [rsp+100h+var_E0], 0
0x180001bed  lea     r8, [rbp+57h+var_80]
0x180001bf1  xor     edx, edx
0x180001bf3  xor     ecx, ecx
0x180001bf5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001bfa  mov     rcx, rbx; hLibModule
0x180001bfd  call    cs:__imp_FreeLibrary
0x180001c04  nop     dword ptr [rax+rax+00h]
0x180001c09  add     rsp, 0E8h
0x180001c10  pop     rdi
0x180001c11  pop     rsi
0x180001c12  pop     rbx
0x180001c13  pop     rbp
0x180001c14  retn
```
