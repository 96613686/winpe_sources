# GetModuleLanguage

- ea: `0x18001d040`
- end: `0x18001d0e1`
- name: `GetModuleLanguage`
- size: `161`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1800190a4`

## callees

- `0x180017ee0`
- `0x180019dc0`
- `0x18001d040`

## import_xrefs

- `VERSION!GetFileVersionInfoA` at `0x18001d094`
- `VERSION!GetFileVersionInfoA` at `0x18001d094`
- `VERSION!GetFileVersionInfoSizeA` at `0x18001d068`
- `VERSION!GetFileVersionInfoSizeA` at `0x18001d068`
- `VERSION!VerQueryValueA` at `0x18001d0b2`
- `VERSION!VerQueryValueA` at `0x18001d0b2`

## string_xrefs

- `0x18001d05a`: `GDI32.DLL`
- `0x18001d088`: `GDI32.DLL`

## pseudocode

```c
__int64 __fastcall GetModuleLanguage(__int64 a1)
{
  DWORD FileVersionInfoSizeA; // eax
  DWORD v2; // ebx
  void *v3; // rax
  void *v4; // rdi
  unsigned __int16 v5; // bx
  unsigned int puLen; // [rsp+30h] [rbp+8h] BYREF
  int v8; // [rsp+34h] [rbp+Ch]
  LPVOID lpBuffer; // [rsp+38h] [rbp+10h] BYREF

  v8 = HIDWORD(a1);
  lpBuffer = 0;
  puLen = 0;
  FileVersionInfoSizeA = GetFileVersionInfoSizeA("GDI32.DLL", 0);
  v2 = FileVersionInfoSizeA;
  if ( !FileVersionInfoSizeA )
    return 1033;
  v3 = (void *)T2malloc(FileVersionInfoSizeA);
  v4 = v3;
  if ( !v3
    || !GetFileVersionInfoA("GDI32.DLL", 0, v2, v3)
    || !VerQueryValueA(v4, "\\VarFileInfo\\Translation", &lpBuffer, &puLen) )
  {
    return 1033;
  }
  v5 = *(_WORD *)lpBuffer;
  T2free(v4);
  return v5;
}

```

## disassembly

```asm
0x18001d040  mov     rax, rsp
0x18001d043  mov     [rax+18h], rbx
0x18001d047  mov     [rax+8], rcx
0x18001d04b  push    rdi
0x18001d04c  sub     rsp, 20h
0x18001d050  xor     edx, edx; lpdwHandle
0x18001d052  mov     qword ptr [rax+10h], 0
0x18001d05a  lea     rcx, tstrFilename; "GDI32.DLL"
0x18001d061  mov     dword ptr [rax+8], 0
0x18001d068  call    cs:__imp_GetFileVersionInfoSizeA
0x18001d06e  mov     ebx, eax
0x18001d070  test    eax, eax
0x18001d072  jz      short loc_18001D0D1
0x18001d074  xor     edx, edx
0x18001d076  mov     ecx, eax; dwBytes
0x18001d078  call    T2malloc
0x18001d07d  mov     rdi, rax
0x18001d080  test    rax, rax
0x18001d083  jz      short loc_18001D0D1
0x18001d085  mov     r9, rax; lpData
0x18001d088  lea     rcx, tstrFilename; "GDI32.DLL"
0x18001d08f  mov     r8d, ebx; dwLen
0x18001d092  xor     edx, edx; dwHandle
0x18001d094  call    cs:__imp_GetFileVersionInfoA
0x18001d09a  test    eax, eax
0x18001d09c  jz      short loc_18001D0D1
0x18001d09e  lea     r9, [rsp+28h+puLen]; puLen
0x18001d0a3  mov     rcx, rdi; pBlock
0x18001d0a6  lea     r8, [rsp+28h+lpBuffer]; lplpBuffer
0x18001d0ab  lea     rdx, SubBlock; "\\VarFileInfo\\Translation"
0x18001d0b2  call    cs:__imp_VerQueryValueA
0x18001d0b8  test    eax, eax
0x18001d0ba  jz      short loc_18001D0D1
0x18001d0bc  mov     rax, [rsp+28h+lpBuffer]
0x18001d0c1  mov     rcx, rdi; lpMem
0x18001d0c4  movzx   ebx, word ptr [rax]
0x18001d0c7  call    T2free
0x18001d0cc  movzx   eax, bx
0x18001d0cf  jmp     short loc_18001D0D6
0x18001d0d1  mov     eax, 409h
0x18001d0d6  mov     rbx, [rsp+28h+arg_10]
0x18001d0db  add     rsp, 20h
0x18001d0df  pop     rdi
0x18001d0e0  retn
```
