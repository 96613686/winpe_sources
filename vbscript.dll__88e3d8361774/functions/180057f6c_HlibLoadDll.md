# HlibLoadDll

- ea: `0x180057f6c`
- end: `0x1800580a2`
- name: `HlibLoadDll`
- size: `310`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18002ad98`

## callees

- `0x180045ca8`
- `0x180057dec`
- `0x180057f6c`
- `0x1800767a0`

## import_xrefs

- `msvcrt!strrchr` at `0x18005802e`
- `msvcrt!strrchr` at `0x18005802e`
- `msvcrt!strcpy_s` at `0x180058063`
- `msvcrt!strcpy_s` at `0x180058063`
- `KERNEL32!LoadLibraryExA` at `0x180058074`
- `KERNEL32!LoadLibraryExA` at `0x180058091`
- `KERNEL32!LoadLibraryExA` at `0x180058074`
- `KERNEL32!LoadLibraryExA` at `0x180058091`
- `KERNEL32!GetModuleFileNameA` at `0x180058005`
- `KERNEL32!GetModuleFileNameA` at `0x180058005`

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
0x180057f6c  push    rbx
0x180057f6e  sub     rsp, 250h
0x180057f75  mov     rax, cs:__security_cookie
0x180057f7c  xor     rax, rsp
0x180057f7f  mov     [rsp+258h+var_18], rax
0x180057f87  movzx   eax, cx
0x180057f8a  mov     dword ptr [rdx], 1
0x180057f90  mov     r8d, 3FFh
0x180057f96  and     ax, r8w
0x180057f9a  cmp     ax, 9
0x180057f9e  jnz     short loc_180057FC6
0x180057fa0  mov     rax, cs:?g_hInstance@@3PEAXEA; void * g_hInstance
0x180057fa7  mov     dword ptr [rdx], 0
0x180057fad  mov     rcx, [rsp+258h+var_18]
0x180057fb5  xor     rcx, rsp; StackCookie
0x180057fb8  call    __security_check_cookie
0x180057fbd  add     rsp, 250h
0x180057fc4  pop     rbx
0x180057fc5  retn
0x180057fc6  mov     r8d, ecx
0x180057fc9  lea     rcx, [rsp+258h+Source]; Destination
0x180057fd1  call    FGenerateDllName
0x180057fd6  test    eax, eax
0x180057fd8  jnz     short loc_180057FDE
0x180057fda  xor     eax, eax
0x180057fdc  jmp     short loc_180057FAD
0x180057fde  lea     rax, [rsp+258h+Source]
0x180057fe6  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180057fea  inc     rbx
0x180057fed  cmp     byte ptr [rax+rbx], 0
0x180057ff1  jnz     short loc_180057FEA
0x180057ff3  mov     rcx, cs:?g_hInstance@@3PEAXEA; hModule
0x180057ffa  lea     rdx, [rsp+258h+Filename]; lpFilename
0x180057fff  mov     r8d, 104h; nSize
0x180058005  call    cs:__imp_GetModuleFileNameA
0x18005800b  movsxd  rcx, eax
0x18005800e  cmp     rcx, 105h
0x180058015  jnb     loc_18005809C
0x18005801b  mov     [rsp+rcx+258h+Filename], 0
0x180058020  test    eax, eax
0x180058022  jz      short loc_180058083
0x180058024  mov     edx, 5Ch ; '\'; Ch
0x180058029  lea     rcx, [rsp+258h+Filename]; Str
0x18005802e  call    cs:__imp_strrchr
0x180058034  test    rax, rax
0x180058037  jz      short loc_180058083
0x180058039  lea     r9, [rsp+258h+Filename]
0x18005803e  movsxd  rcx, ebx
0x180058041  sub     r9, rax
0x180058044  lea     rdx, [r9+103h]
0x18005804b  cmp     rdx, rcx
0x18005804e  jl      short loc_180058083
0x180058050  lea     rdx, [r9+104h]; SizeInBytes
0x180058057  lea     rcx, [rax+1]; Destination
0x18005805b  lea     r8, [rsp+258h+Source]; Source
0x180058063  call    cs:__imp_strcpy_s
0x180058069  xor     edx, edx; hFile
0x18005806b  lea     rcx, [rsp+258h+Filename]; lpLibFileName
0x180058070  lea     r8d, [rdx+60h]; dwFlags
0x180058074  call    cs:__imp_LoadLibraryExA
0x18005807a  test    rax, rax
0x18005807d  jnz     loc_180057FAD
0x180058083  xor     edx, edx; hFile
0x180058085  lea     rcx, [rsp+258h+Source]; lpLibFileName
0x18005808d  lea     r8d, [rdx+60h]; dwFlags
0x180058091  call    cs:__imp_LoadLibraryExA
0x180058097  jmp     loc_180057FAD
0x18005809c  call    __report_rangecheckfailure
```
