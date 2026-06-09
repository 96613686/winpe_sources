# D3DCompilerHelper::Initialize(void)

- ea: `0x18001d560`
- end: `0x18001d5ff`
- name: `?Initialize@D3DCompilerHelper@@AEAAJXZ`
- size: `159`
- prototype: `__int64 __fastcall(D3DCompilerHelper *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000cf64`

## callees

- `0x18001d560`
- `0x18001f204`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001d5e9`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001d5e9`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001d595`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001d5b6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001d595`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001d5b6`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18001d574`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18001d574`

## string_xrefs

- `0x18001d56d`: `d3dcompiler_47.dll`
- `0x18001d5ac`: `D3DCompile`

## pseudocode

```c
__int64 __fastcall D3DCompilerHelper::Initialize(D3DCompilerHelper *this)
{
  HMODULE LibraryW; // rax
  HMODULE v3; // rdi
  unsigned int v4; // edx
  _QWORD *v5; // rsi
  FARPROC ProcAddress; // rax
  FARPROC v7; // rax
  unsigned int v8; // ebx

  LibraryW = LoadLibraryW(L"d3dcompiler_47.dll");
  v3 = LibraryW;
  if ( LibraryW )
  {
    ProcAddress = GetProcAddress(LibraryW, "D3DReflectLibrary");
    v5 = (_QWORD *)((char *)this + 8);
    *((_QWORD *)this + 1) = ProcAddress;
    if ( ProcAddress )
    {
      v7 = GetProcAddress(v3, "D3DCompile");
      *(_QWORD *)this = v7;
      if ( v7 )
        return 0;
      v4 = 26;
    }
    else
    {
      v4 = 23;
    }
  }
  else
  {
    v4 = 20;
    v5 = (_QWORD *)((char *)this + 8);
  }
  v8 = -2147024882;
  DoStackCaptureDirect(-2147024882, v4);
  *v5 = 0;
  *(_QWORD *)this = 0;
  if ( v3 )
    FreeLibrary(v3);
  return v8;
}

```

## disassembly

```asm
0x18001d560  push    rbx
0x18001d562  push    rsi
0x18001d563  push    rdi
0x18001d564  push    r14
0x18001d566  sub     rsp, 28h
0x18001d56a  mov     r14, rcx
0x18001d56d  lea     rcx, aD3dcompiler47D; "d3dcompiler_47.dll"
0x18001d574  call    cs:__imp_LoadLibraryW
0x18001d57a  mov     rdi, rax
0x18001d57d  test    rax, rax
0x18001d580  jnz     short loc_18001D58B
0x18001d582  lea     edx, [rax+14h]
0x18001d585  lea     rsi, [r14+8]
0x18001d589  jmp     short loc_18001D5C7
0x18001d58b  lea     rdx, aD3dreflectlibr; "D3DReflectLibrary"
0x18001d592  mov     rcx, rdi; hModule
0x18001d595  call    cs:__imp_GetProcAddress
0x18001d59b  lea     rsi, [r14+8]
0x18001d59f  mov     [rsi], rax
0x18001d5a2  test    rax, rax
0x18001d5a5  jnz     short loc_18001D5AC
0x18001d5a7  lea     edx, [rax+17h]
0x18001d5aa  jmp     short loc_18001D5C7
0x18001d5ac  lea     rdx, aD3dcompile; "D3DCompile"
0x18001d5b3  mov     rcx, rdi; hModule
0x18001d5b6  call    cs:__imp_GetProcAddress
0x18001d5bc  mov     [r14], rax
0x18001d5bf  test    rax, rax
0x18001d5c2  jnz     short loc_18001D5F1
0x18001d5c4  lea     edx, [rax+1Ah]; unsigned int
0x18001d5c7  mov     ebx, 8007000Eh
0x18001d5cc  mov     ecx, ebx; int
0x18001d5ce  call    ?DoStackCaptureDirect@@YAXJI@Z; DoStackCaptureDirect(long,uint)
0x18001d5d3  mov     qword ptr [rsi], 0
0x18001d5da  mov     qword ptr [r14], 0
0x18001d5e1  test    rdi, rdi
0x18001d5e4  jz      short loc_18001D5F3
0x18001d5e6  mov     rcx, rdi; hLibModule
0x18001d5e9  call    cs:__imp_FreeLibrary
0x18001d5ef  jmp     short loc_18001D5F3
0x18001d5f1  xor     ebx, ebx
0x18001d5f3  mov     eax, ebx
0x18001d5f5  add     rsp, 28h
0x18001d5f9  pop     r14
0x18001d5fb  pop     rdi
0x18001d5fc  pop     rsi
0x18001d5fd  pop     rbx
0x18001d5fe  retn
```
