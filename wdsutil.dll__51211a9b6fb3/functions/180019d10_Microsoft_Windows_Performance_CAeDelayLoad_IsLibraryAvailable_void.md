# Microsoft::Windows::Performance::CAeDelayLoad::IsLibraryAvailable(void)

- ea: `0x180019d10`
- end: `0x180019ddf`
- name: `?IsLibraryAvailable@CAeDelayLoad@Performance@Windows@Microsoft@@QEAA_NXZ`
- size: `207`
- prototype: `bool __fastcall(Microsoft::Windows::Performance::CAeDelayLoad *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001c2b8`
- `0x18001c548`

## callees

- `0x180019d10`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x180019d5a`
- `KERNEL32!GetProcAddress` at `0x180019d92`
- `KERNEL32!GetProcAddress` at `0x180019d5a`
- `KERNEL32!GetProcAddress` at `0x180019d92`
- `KERNEL32!LoadLibraryExW` at `0x180019d3b`
- `KERNEL32!LoadLibraryExW` at `0x180019d3b`
- `KERNEL32!FreeLibrary` at `0x180019d73`
- `KERNEL32!FreeLibrary` at `0x180019dab`
- `KERNEL32!FreeLibrary` at `0x180019d73`
- `KERNEL32!FreeLibrary` at `0x180019dab`

## string_xrefs

- `0x180019d2e`: `aepic.dll`

## pseudocode

```c
char __fastcall Microsoft::Windows::Performance::CAeDelayLoad::IsLibraryAvailable(
        Microsoft::Windows::Performance::CAeDelayLoad *this)
{
  char v2; // di
  HMODULE Library; // rax
  FARPROC ProcAddress; // rax
  FARPROC v5; // rax

  v2 = 1;
  if ( !*(_BYTE *)this )
  {
    *(_BYTE *)this = 1;
    Library = LoadLibraryExW(L"aepic.dll", 0, 0x800u);
    *((_QWORD *)this + 1) = Library;
    if ( Library )
    {
      ProcAddress = GetProcAddress(Library, "PicRetrieveFileInfo");
      *((_QWORD *)this + 2) = ProcAddress;
      if ( !ProcAddress )
      {
        FreeLibrary(*((HMODULE *)this + 1));
        *((_QWORD *)this + 1) = 0;
      }
      v5 = GetProcAddress(*((HMODULE *)this + 1), "PicFreeFileInfo");
      *((_QWORD *)this + 3) = v5;
      if ( !v5 )
      {
        FreeLibrary(*((HMODULE *)this + 1));
        *((_QWORD *)this + 1) = 0;
      }
    }
  }
  if ( !*((_QWORD *)this + 2) || !*((_QWORD *)this + 3) )
    return 0;
  return v2;
}

```

## disassembly

```asm
0x180019d10  mov     [rsp+arg_0], rbx
0x180019d15  push    rdi
0x180019d16  sub     rsp, 20h
0x180019d1a  cmp     byte ptr [rcx], 0
0x180019d1d  mov     rbx, rcx
0x180019d20  mov     dil, 1
0x180019d23  jnz     loc_180019DBF
0x180019d29  mov     [rcx], dil
0x180019d2c  xor     edx, edx; hFile
0x180019d2e  lea     rcx, aAepicDll; "aepic.dll"
0x180019d35  mov     r8d, 800h; dwFlags
0x180019d3b  call    cs:__imp_LoadLibraryExW
0x180019d42  nop     dword ptr [rax+rax+00h]
0x180019d47  mov     [rbx+8], rax
0x180019d4b  test    rax, rax
0x180019d4e  jz      short loc_180019DBF
0x180019d50  lea     rdx, aPicretrievefil; "PicRetrieveFileInfo"
0x180019d57  mov     rcx, rax; hModule
0x180019d5a  call    cs:__imp_GetProcAddress
0x180019d61  nop     dword ptr [rax+rax+00h]
0x180019d66  mov     [rbx+10h], rax
0x180019d6a  test    rax, rax
0x180019d6d  jnz     short loc_180019D87
0x180019d6f  mov     rcx, [rbx+8]; hLibModule
0x180019d73  call    cs:__imp_FreeLibrary
0x180019d7a  nop     dword ptr [rax+rax+00h]
0x180019d7f  mov     qword ptr [rbx+8], 0
0x180019d87  mov     rcx, [rbx+8]; hModule
0x180019d8b  lea     rdx, aPicfreefileinf; "PicFreeFileInfo"
0x180019d92  call    cs:__imp_GetProcAddress
0x180019d99  nop     dword ptr [rax+rax+00h]
0x180019d9e  mov     [rbx+18h], rax
0x180019da2  test    rax, rax
0x180019da5  jnz     short loc_180019DBF
0x180019da7  mov     rcx, [rbx+8]; hLibModule
0x180019dab  call    cs:__imp_FreeLibrary
0x180019db2  nop     dword ptr [rax+rax+00h]
0x180019db7  mov     qword ptr [rbx+8], 0
0x180019dbf  cmp     qword ptr [rbx+10h], 0
0x180019dc4  jz      short loc_180019DCD
0x180019dc6  cmp     qword ptr [rbx+18h], 0
0x180019dcb  jnz     short loc_180019DD0
0x180019dcd  xor     dil, dil
0x180019dd0  mov     rbx, [rsp+28h+arg_0]
0x180019dd5  mov     al, dil
0x180019dd8  add     rsp, 20h
0x180019ddc  pop     rdi
0x180019ddd  retn
```
