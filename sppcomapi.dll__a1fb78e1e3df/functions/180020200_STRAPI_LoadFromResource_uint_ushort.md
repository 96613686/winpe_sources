# STRAPI_LoadFromResource(uint,ushort * *)

- ea: `0x180020200`
- end: `0x180020313`
- name: `?STRAPI_LoadFromResource@@YAJIPEAPEAG@Z`
- size: `275`
- prototype: `__int64 __fastcall(unsigned int, unsigned __int16 **)`
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x18001fa70`
- `0x180023134`
- `0x180038f90`

## callees

- `0x180003520`
- `0x1800036ec`
- `0x180004288`
- `0x18001f540`
- `0x180020200`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x18002028b`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x18002028b`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x18002024a`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x18002024a`
- `api-ms-win-core-libraryloader-l1-2-0!LockResource` at `0x18002029f`
- `api-ms-win-core-libraryloader-l1-2-0!LockResource` at `0x18002029f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002025b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002025b`

## pseudocode

```c
__int64 __fastcall STRAPI_LoadFromResource(unsigned __int16 a1, unsigned __int16 **a2)
{
  int ThisModuleHandle; // eax
  signed int v5; // ebx
  int v6; // ecx
  HRSRC Resource; // rax
  signed int LastError; // eax
  int v9; // ecx
  HGLOBAL v10; // rax
  unsigned __int16 *v11; // rax
  __int64 v12; // rdx
  char *v13; // r9
  int i; // edi
  char *v15; // rcx
  int Internal; // eax
  HMODULE hModule; // [rsp+40h] [rbp+18h] BYREF

  hModule = 0;
  ThisModuleHandle = CImmutableStringsExT<unsigned short,CImmutableStringsPolicyDefault>::GetThisModuleHandle(&hModule);
  v5 = ThisModuleHandle;
  if ( ThisModuleHandle < 0 )
  {
    v6 = ThisModuleHandle;
LABEL_18:
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v6);
    goto LABEL_19;
  }
  Resource = FindResourceExW(hModule, (LPCWSTR)6, (LPCWSTR)((a1 >> 4) + 1), 0);
  if ( !Resource || (v10 = LoadResource(hModule, Resource)) == 0 || (v11 = (unsigned __int16 *)LockResource(v10)) == 0 )
  {
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError )
    {
      if ( LastError > 0 )
        v5 = (unsigned __int16)LastError | 0x80070000;
    }
    else
    {
      v5 = -2147467259;
    }
    v9 = v5;
    goto LABEL_15;
  }
  v12 = *v11;
  v13 = (char *)(v11 + 1);
  for ( i = a1 & 0xF; i; --i )
  {
    v15 = &v13[2 * v12];
    v12 = *(unsigned __int16 *)v15;
    v13 = v15 + 2;
  }
  Internal = CImmutableStringsT<unsigned short,CImmutableStringsPolicyDefault>::CreateInternal(v13, v12, a2);
  v5 = Internal;
  if ( Internal < 0 )
  {
    v9 = Internal;
LABEL_15:
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v9);
  }
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v5);
  if ( v5 < 0 )
  {
    v6 = v5;
    goto LABEL_18;
  }
LABEL_19:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v5);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180020200  mov     rax, rsp
0x180020203  mov     [rax+8], rbx
0x180020207  mov     [rax+10h], rsi
0x18002020b  push    rdi
0x18002020c  sub     rsp, 20h
0x180020210  mov     edi, ecx
0x180020212  mov     qword ptr [rax+18h], 0
0x18002021a  lea     rcx, [rax+18h]
0x18002021e  mov     rsi, rdx
0x180020221  call    ?GetThisModuleHandle@?$CImmutableStringsExT@GVCImmutableStringsPolicyDefault@@@@KAJPEAPEAUHINSTANCE__@@@Z; CImmutableStringsExT<ushort,CImmutableStringsPolicyDefault>::GetThisModuleHandle(HINSTANCE__ * *)
0x180020226  mov     ebx, eax
0x180020228  test    eax, eax
0x18002022a  jns     short loc_180020233
0x18002022c  mov     ecx, eax
0x18002022e  jmp     loc_1800202F4
0x180020233  mov     rcx, [rsp+28h+hModule]; hModule
0x180020238  xor     r9d, r9d; wLanguage
0x18002023b  movzx   r8d, di
0x18002023f  shr     r8d, 4
0x180020243  inc     r8d; lpName
0x180020246  lea     edx, [r9+6]; lpType
0x18002024a  call    cs:__imp_FindResourceExW
0x180020251  nop     dword ptr [rax+rax+00h]
0x180020256  test    rax, rax
0x180020259  jnz     short loc_180020283
0x18002025b  call    cs:__imp_GetLastError
0x180020262  nop     dword ptr [rax+rax+00h]
0x180020267  mov     ebx, eax
0x180020269  test    eax, eax
0x18002026b  jnz     short loc_180020274
0x18002026d  mov     ebx, 80004005h
0x180020272  jmp     short loc_18002027F
0x180020274  jle     short loc_18002027F
0x180020276  movzx   ebx, ax
0x180020279  or      ebx, 80070000h
0x18002027f  mov     ecx, ebx
0x180020281  jmp     short loc_1800202E2
0x180020283  mov     rcx, [rsp+28h+hModule]; hModule
0x180020288  mov     rdx, rax; hResInfo
0x18002028b  call    cs:__imp_LoadResource
0x180020292  nop     dword ptr [rax+rax+00h]
0x180020297  test    rax, rax
0x18002029a  jz      short loc_18002025B
0x18002029c  mov     rcx, rax; hResData
0x18002029f  call    cs:__imp_LockResource
0x1800202a6  nop     dword ptr [rax+rax+00h]
0x1800202ab  mov     r9, rax
0x1800202ae  test    rax, rax
0x1800202b1  jz      short loc_18002025B
0x1800202b3  movzx   edx, word ptr [rax]
0x1800202b6  add     r9, 2
0x1800202ba  and     edi, 0Fh
0x1800202bd  jz      short loc_1800202CF
0x1800202bf  lea     rcx, [r9+rdx*2]
0x1800202c3  movzx   edx, word ptr [rcx]
0x1800202c6  lea     r9, [rcx+2]
0x1800202ca  add     edi, 0FFFFFFFFh
0x1800202cd  jnz     short loc_1800202BF
0x1800202cf  mov     r8, rsi
0x1800202d2  mov     rcx, r9; Src
0x1800202d5  call    ?CreateInternal@?$CImmutableStringsT@GVCImmutableStringsPolicyDefault@@@@KAJPEBGKPEAPEAG@Z; CImmutableStringsT<ushort,CImmutableStringsPolicyDefault>::CreateInternal(ushort const *,ulong,ushort * *)
0x1800202da  mov     ebx, eax
0x1800202dc  test    eax, eax
0x1800202de  jns     short loc_1800202E7
0x1800202e0  mov     ecx, eax
0x1800202e2  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x1800202e7  mov     ecx, ebx
0x1800202e9  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x1800202ee  test    ebx, ebx
0x1800202f0  jns     short loc_1800202F9
0x1800202f2  mov     ecx, ebx
0x1800202f4  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x1800202f9  mov     ecx, ebx
0x1800202fb  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180020300  mov     rsi, [rsp+28h+arg_8]
0x180020305  mov     eax, ebx
0x180020307  mov     rbx, [rsp+28h+arg_0]
0x18002030c  add     rsp, 20h
0x180020310  pop     rdi
0x180020311  retn
```
