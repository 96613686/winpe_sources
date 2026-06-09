# HlibLoadDll

- ea: `0x180059a24`
- end: `0x180059b79`
- name: `HlibLoadDll`
- size: `341`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18003f93c`

## callees

- `0x180047098`
- `0x180059888`
- `0x180059a24`
- `0x180079490`

## import_xrefs

- `msvcrt!strrchr` at `0x180059aed`
- `msvcrt!strrchr` at `0x180059aed`
- `msvcrt!strcpy_s` at `0x180059b28`
- `msvcrt!strcpy_s` at `0x180059b28`
- `KERNEL32!LoadLibraryExA` at `0x180059b3f`
- `KERNEL32!LoadLibraryExA` at `0x180059b62`
- `KERNEL32!LoadLibraryExA` at `0x180059b3f`
- `KERNEL32!LoadLibraryExA` at `0x180059b62`
- `KERNEL32!GetModuleFileNameA` at `0x180059abe`
- `KERNEL32!GetModuleFileNameA` at `0x180059abe`

## pseudocode

```c
HMODULE __fastcall HlibLoadDll(__int16 a1, _DWORD *a2)
{
  HMODULE result; // rax
  __int64 v3; // rbx
  signed int ModuleFileNameA; // eax
  char *v5; // rax
  CHAR Filename[272]; // [rsp+20h] [rbp-238h] BYREF
  CHAR Source[272]; // [rsp+130h] [rbp-128h] BYREF

  *a2 = 1;
  if ( (a1 & 0x3FF) == 9 )
  {
    result = g_hInstance;
    *a2 = 0;
  }
  else if ( (unsigned int)FGenerateDllName(Source) )
  {
    v3 = -1;
    do
      ++v3;
    while ( Source[v3] );
    ModuleFileNameA = GetModuleFileNameA(g_hInstance, Filename, 0x104u);
    if ( (unsigned __int64)ModuleFileNameA >= 0x105 )
      _report_rangecheckfailure();
    Filename[ModuleFileNameA] = 0;
    if ( !ModuleFileNameA )
      return LoadLibraryExA(Source, 0, 0x60u);
    v5 = strrchr(Filename, 92);
    if ( !v5 )
      return LoadLibraryExA(Source, 0, 0x60u);
    if ( Filename - v5 + 259 < (int)v3 )
      return LoadLibraryExA(Source, 0, 0x60u);
    strcpy_s(v5 + 1, Filename - v5 + 260, Source);
    result = LoadLibraryExA(Filename, 0, 0x60u);
    if ( !result )
      return LoadLibraryExA(Source, 0, 0x60u);
  }
  else
  {
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180059a24  push    rbx
0x180059a26  sub     rsp, 250h
0x180059a2d  mov     rax, cs:__security_cookie
0x180059a34  xor     rax, rsp
0x180059a37  mov     [rsp+258h+var_18], rax
0x180059a3f  movzx   eax, cx
0x180059a42  mov     dword ptr [rdx], 1
0x180059a48  mov     r8d, 3FFh
0x180059a4e  and     ax, r8w
0x180059a52  cmp     ax, 9
0x180059a56  jnz     short loc_180059A7F
0x180059a58  mov     rax, cs:?g_hInstance@@3PEAXEA; void * g_hInstance
0x180059a5f  mov     dword ptr [rdx], 0
0x180059a65  mov     rcx, [rsp+258h+var_18]
0x180059a6d  xor     rcx, rsp; StackCookie
0x180059a70  call    __security_check_cookie
0x180059a75  add     rsp, 250h
0x180059a7c  pop     rbx
0x180059a7d  retn
0x180059a7f  mov     r8d, ecx
0x180059a82  lea     rcx, [rsp+258h+Source]; Destination
0x180059a8a  call    FGenerateDllName
0x180059a8f  test    eax, eax
0x180059a91  jnz     short loc_180059A97
0x180059a93  xor     eax, eax
0x180059a95  jmp     short loc_180059A65
0x180059a97  lea     rax, [rsp+258h+Source]
0x180059a9f  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180059aa3  inc     rbx
0x180059aa6  cmp     byte ptr [rax+rbx], 0
0x180059aaa  jnz     short loc_180059AA3
0x180059aac  mov     rcx, cs:?g_hInstance@@3PEAXEA; hModule
0x180059ab3  lea     rdx, [rsp+258h+Filename]; lpFilename
0x180059ab8  mov     r8d, 104h; nSize
0x180059abe  call    cs:__imp_GetModuleFileNameA
0x180059ac5  nop     dword ptr [rax+rax+00h]
0x180059aca  movsxd  rcx, eax
0x180059acd  cmp     rcx, 105h
0x180059ad4  jnb     loc_180059B73
0x180059ada  mov     [rsp+rcx+258h+Filename], 0
0x180059adf  test    eax, eax
0x180059ae1  jz      short loc_180059B54
0x180059ae3  mov     edx, 5Ch ; '\'; Ch
0x180059ae8  lea     rcx, [rsp+258h+Filename]; Str
0x180059aed  call    cs:__imp_strrchr
0x180059af4  nop     dword ptr [rax+rax+00h]
0x180059af9  test    rax, rax
0x180059afc  jz      short loc_180059B54
0x180059afe  lea     r9, [rsp+258h+Filename]
0x180059b03  movsxd  rcx, ebx
0x180059b06  sub     r9, rax
0x180059b09  lea     rdx, [r9+103h]
0x180059b10  cmp     rdx, rcx
0x180059b13  jl      short loc_180059B54
0x180059b15  lea     rdx, [r9+104h]; SizeInBytes
0x180059b1c  lea     rcx, [rax+1]; Destination
0x180059b20  lea     r8, [rsp+258h+Source]; Source
0x180059b28  call    cs:__imp_strcpy_s
0x180059b2f  nop     dword ptr [rax+rax+00h]
0x180059b34  xor     edx, edx; hFile
0x180059b36  lea     rcx, [rsp+258h+Filename]; lpLibFileName
0x180059b3b  lea     r8d, [rdx+60h]; dwFlags
0x180059b3f  call    cs:__imp_LoadLibraryExA
0x180059b46  nop     dword ptr [rax+rax+00h]
0x180059b4b  test    rax, rax
0x180059b4e  jnz     loc_180059A65
0x180059b54  xor     edx, edx; hFile
0x180059b56  lea     rcx, [rsp+258h+Source]; lpLibFileName
0x180059b5e  lea     r8d, [rdx+60h]; dwFlags
0x180059b62  call    cs:__imp_LoadLibraryExA
0x180059b69  nop     dword ptr [rax+rax+00h]
0x180059b6e  jmp     loc_180059A65
0x180059b73  call    __report_rangecheckfailure
```
