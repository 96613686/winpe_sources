# SamIGetDefaultAdministratorName

- ea: `0x1800ae2d0`
- end: `0x1800ae3d4`
- name: `SamIGetDefaultAdministratorName`
- size: `260`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x180027e24`
- `0x1800ae2d0`
- `0x1800bb788`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800ae300`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800ae300`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800ae33d`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800ae33d`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800ae332`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800ae332`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800ae385`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800ae385`

## string_xrefs

- `0x1800ae2f4`: `SAMSRV.DLL`

## pseudocode

```c
__int64 __fastcall SamIGetDefaultAdministratorName(void *a1, _DWORD *a2)
{
  DWORD v4; // ebx
  HMODULE Library; // rdi
  __int64 v6; // rsi
  unsigned int v7; // edi
  void *v8; // rcx
  const void *Buffer; // [rsp+70h] [rbp+18h] BYREF

  Buffer = 0;
  v4 = 0;
  Library = LoadLibraryExW(L"SAMSRV.DLL", 0, 0);
  if ( Library )
  {
    v4 = FormatMessageW(0x900u, Library, 0x2000u, 0, (LPWSTR)&Buffer, 0, 0);
    FreeLibrary(Library);
  }
  if ( Buffer )
  {
    v6 = v4 - 2;
    if ( v4 <= 2 )
      v6 = v4;
    if ( *a2 <= (unsigned int)v6 )
    {
      v7 = -1073741789;
    }
    else
    {
      v7 = 0;
      memcpy_0(a1, Buffer, 2 * v6);
      *((_WORD *)a1 + v6) = 0;
    }
    v8 = (void *)Buffer;
    *a2 = v6;
    LocalFree(v8);
  }
  else
  {
    v7 = -1073741823;
  }
  if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
    WPP_SF_Dd(WPP_GLOBAL_Control[3].Buffer, 180, WPP_48bf36016493398285a8dbc678e80a21_Traceguids, v7, v7);
  return v7;
}

```

## disassembly

```asm
0x1800ae2d0  mov     [rsp+arg_0], rbx
0x1800ae2d5  mov     [rsp+arg_8], rsi
0x1800ae2da  push    rdi
0x1800ae2db  push    r14
0x1800ae2dd  push    r15
0x1800ae2df  sub     rsp, 40h
0x1800ae2e3  mov     r14, rdx
0x1800ae2e6  mov     [rsp+58h+Buffer], 0
0x1800ae2ef  mov     r15, rcx
0x1800ae2f2  xor     edx, edx; hFile
0x1800ae2f4  lea     rcx, LibFileName; "SAMSRV.DLL"
0x1800ae2fb  xor     r8d, r8d; dwFlags
0x1800ae2fe  xor     ebx, ebx
0x1800ae300  call    cs:__imp_LoadLibraryExW
0x1800ae306  mov     rdi, rax
0x1800ae309  test    rax, rax
0x1800ae30c  jz      short loc_1800AE343
0x1800ae30e  mov     [rsp+58h+Arguments], rbx; Arguments
0x1800ae313  lea     rax, [rsp+58h+Buffer]
0x1800ae318  mov     [rsp+58h+nSize], ebx; nSize
0x1800ae31c  xor     r9d, r9d; dwLanguageId
0x1800ae31f  mov     r8d, 2000h; dwMessageId
0x1800ae325  mov     [rsp+58h+lpBuffer], rax; lpBuffer
0x1800ae32a  mov     rdx, rdi; lpSource
0x1800ae32d  mov     ecx, 900h; dwFlags
0x1800ae332  call    cs:__imp_FormatMessageW
0x1800ae338  mov     rcx, rdi; hLibModule
0x1800ae33b  mov     ebx, eax
0x1800ae33d  call    cs:__imp_FreeLibrary
0x1800ae343  cmp     [rsp+58h+Buffer], 0
0x1800ae349  jz      short loc_1800AE38D
0x1800ae34b  cmp     ebx, 2
0x1800ae34e  lea     esi, [rbx-2]
0x1800ae351  cmovbe  esi, ebx
0x1800ae354  cmp     [r14], esi
0x1800ae357  jbe     short loc_1800AE378
0x1800ae359  mov     rdx, [rsp+58h+Buffer]; Src
0x1800ae35e  lea     rbx, [rsi+rsi]
0x1800ae362  mov     r8, rbx; Size
0x1800ae365  mov     rcx, r15; void *
0x1800ae368  xor     edi, edi
0x1800ae36a  call    memcpy_0
0x1800ae36f  xor     eax, eax
0x1800ae371  mov     [rbx+r15], ax
0x1800ae376  jmp     short loc_1800AE37D
0x1800ae378  mov     edi, 0C0000023h
0x1800ae37d  mov     rcx, [rsp+58h+Buffer]; hMem
0x1800ae382  mov     [r14], esi
0x1800ae385  call    cs:__imp_LocalFree
0x1800ae38b  jmp     short loc_1800AE392
0x1800ae38d  mov     edi, 0C0000001h
0x1800ae392  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ae399  test    dword ptr [rcx+44h], 20000h
0x1800ae3a0  jz      short loc_1800AE3BE
0x1800ae3a2  mov     rcx, [rcx+38h]
0x1800ae3a6  lea     r8, WPP_48bf36016493398285a8dbc678e80a21_Traceguids
0x1800ae3ad  mov     edx, 0B4h
0x1800ae3b2  mov     dword ptr [rsp+58h+lpBuffer], edi
0x1800ae3b6  mov     r9d, edi
0x1800ae3b9  call    WPP_SF_Dd
0x1800ae3be  mov     rbx, [rsp+58h+arg_0]
0x1800ae3c3  mov     eax, edi
0x1800ae3c5  mov     rsi, [rsp+58h+arg_8]
0x1800ae3ca  add     rsp, 40h
0x1800ae3ce  pop     r15
0x1800ae3d0  pop     r14
0x1800ae3d2  pop     rdi
0x1800ae3d3  retn
```
