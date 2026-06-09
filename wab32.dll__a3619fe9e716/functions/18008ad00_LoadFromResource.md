# _LoadFromResource

- ea: `0x18008ad00`
- end: `0x18008addc`
- name: `_LoadFromResource`
- size: `220`
- prototype: `__int64 __fastcall(LPCWSTR lpName)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18008249c`
- `0x180089f30`

## callees

- `0x180005d08`
- `0x18008ad00`

## import_xrefs

- `SHLWAPI!__imp_SHCreateMemStream` at `0x18008ada1`
- `SHLWAPI!__imp_SHCreateMemStream` at `0x18008ada1`
- `KERNEL32!FindResourceW` at `0x18008ad4f`
- `KERNEL32!FindResourceW` at `0x18008ad4f`
- `KERNEL32!LoadResource` at `0x18008ad79`
- `KERNEL32!LoadResource` at `0x18008ad79`
- `KERNEL32!LockResource` at `0x18008ad8a`
- `KERNEL32!LockResource` at `0x18008ad8a`
- `KERNEL32!SizeofResource` at `0x18008ad65`
- `KERNEL32!SizeofResource` at `0x18008ad65`
- `KERNEL32!FreeResource` at `0x18008adba`
- `KERNEL32!FreeResource` at `0x18008adba`
- `KERNEL32!GetModuleHandleExW` at `0x18008ad2a`
- `KERNEL32!GetModuleHandleExW` at `0x18008ad2a`
- `KERNEL32!FreeLibrary` at `0x18008adca`
- `KERNEL32!FreeLibrary` at `0x18008adca`

## string_xrefs

- `0x18008ad45`: `XML_FILE`

## pseudocode

```c
__int64 __fastcall LoadFromResource(LPCWSTR lpName, IStream **a2)
{
  unsigned int LastError; // ebx
  HRSRC ResourceW; // rax
  HRSRC v6; // rbx
  UINT v7; // esi
  HGLOBAL Resource; // rax
  void *v9; // rdi
  const BYTE *v10; // rax
  IStream *v11; // rax
  HMODULE phModule; // [rsp+60h] [rbp+18h] BYREF

  phModule = 0;
  if ( GetModuleHandleExW(4u, (LPCWSTR)LoadFromResource, &phModule)
    && (ResourceW = FindResourceW(phModule, lpName, L"XML_FILE"), (v6 = ResourceW) != 0)
    && (v7 = SizeofResource(phModule, ResourceW)) != 0
    && (Resource = LoadResource(phModule, v6), (v9 = Resource) != 0) )
  {
    v10 = (const BYTE *)LockResource(Resource);
    if ( v10 )
    {
      v11 = SHCreateMemStream(v10, v7);
      LastError = 0;
      *a2 = v11;
      if ( !v11 )
        LastError = -2147024882;
    }
    else
    {
      LastError = -2147467259;
    }
    FreeResource(v9);
  }
  else
  {
    LastError = HrGetLastError();
  }
  if ( phModule )
    FreeLibrary(phModule);
  return LastError;
}

```

## disassembly

```asm
0x18008ad00  push    rbx
0x18008ad02  push    rsi
0x18008ad03  push    rdi
0x18008ad04  push    r14
0x18008ad06  sub     rsp, 28h
0x18008ad0a  mov     r14, rdx
0x18008ad0d  mov     [rsp+48h+phModule], 0
0x18008ad16  mov     rbx, rcx
0x18008ad19  lea     rdx, _LoadFromResource; lpModuleName
0x18008ad20  mov     ecx, 4; dwFlags
0x18008ad25  lea     r8, [rsp+48h+phModule]; phModule
0x18008ad2a  call    cs:__imp_GetModuleHandleExW
0x18008ad30  test    eax, eax
0x18008ad32  jnz     short loc_18008AD40
0x18008ad34  call    ?HrGetLastError@@YAJXZ; HrGetLastError(void)
0x18008ad39  mov     ebx, eax
0x18008ad3b  jmp     loc_18008ADC0
0x18008ad40  mov     rcx, [rsp+48h+phModule]; hModule
0x18008ad45  lea     r8, Type; "XML_FILE"
0x18008ad4c  mov     rdx, rbx; lpName
0x18008ad4f  call    cs:__imp_FindResourceW
0x18008ad55  mov     rbx, rax
0x18008ad58  test    rax, rax
0x18008ad5b  jz      short loc_18008AD34
0x18008ad5d  mov     rcx, [rsp+48h+phModule]; hModule
0x18008ad62  mov     rdx, rax; hResInfo
0x18008ad65  call    cs:__imp_SizeofResource
0x18008ad6b  mov     esi, eax
0x18008ad6d  test    eax, eax
0x18008ad6f  jz      short loc_18008AD34
0x18008ad71  mov     rcx, [rsp+48h+phModule]; hModule
0x18008ad76  mov     rdx, rbx; hResInfo
0x18008ad79  call    cs:__imp_LoadResource
0x18008ad7f  mov     rdi, rax
0x18008ad82  test    rax, rax
0x18008ad85  jz      short loc_18008AD34
0x18008ad87  mov     rcx, rax; hResData
0x18008ad8a  call    cs:__imp_LockResource
0x18008ad90  test    rax, rax
0x18008ad93  jnz     short loc_18008AD9C
0x18008ad95  mov     ebx, 80004005h
0x18008ad9a  jmp     short loc_18008ADB7
0x18008ad9c  mov     edx, esi; cbInit
0x18008ad9e  mov     rcx, rax; pInit
0x18008ada1  call    cs:__imp_SHCreateMemStream
0x18008ada7  xor     ebx, ebx
0x18008ada9  mov     ecx, 8007000Eh
0x18008adae  test    rax, rax
0x18008adb1  mov     [r14], rax
0x18008adb4  cmovz   ebx, ecx
0x18008adb7  mov     rcx, rdi; hResData
0x18008adba  call    cs:__imp_FreeResource
0x18008adc0  mov     rcx, [rsp+48h+phModule]; hLibModule
0x18008adc5  test    rcx, rcx
0x18008adc8  jz      short loc_18008ADD0
0x18008adca  call    cs:__imp_FreeLibrary
0x18008add0  mov     eax, ebx
0x18008add2  add     rsp, 28h
0x18008add6  pop     r14
0x18008add8  pop     rdi
0x18008add9  pop     rsi
0x18008adda  pop     rbx
0x18008addb  retn
```
