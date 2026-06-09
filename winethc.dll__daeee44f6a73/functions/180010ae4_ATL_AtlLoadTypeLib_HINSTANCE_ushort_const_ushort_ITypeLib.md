# ATL::AtlLoadTypeLib(HINSTANCE__ *,ushort const *,ushort * *,ITypeLib * *)

- ea: `0x180010ae4`
- end: `0x180010cb2`
- name: `?AtlLoadTypeLib@ATL@@YAJPEAUHINSTANCE__@@PEBGPEAPEAGPEAPEAUITypeLib@@@Z`
- size: `462`
- prototype: `int(HINSTANCE, const unsigned __int16 *, unsigned __int16 **, struct ITypeLib **)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x1800111dc`
- `0x1800114b4`

## callees

- `0x1800041b8`
- `0x1800041f8`
- `0x180010ae4`
- `0x180012db0`

## import_xrefs

- `msvcrt!wcscpy_s` at `0x180010c08`
- `msvcrt!wcscpy_s` at `0x180010c08`
- `KERNEL32!GetModuleFileNameW` at `0x180010b2f`
- `KERNEL32!GetModuleFileNameW` at `0x180010b2f`
- `USER32!CharNextW` at `0x180010b80`
- `USER32!CharNextW` at `0x180010b80`
- `OLEAUT32!__imp_SysAllocString` at `0x180010c4f`
- `OLEAUT32!__imp_SysAllocString` at `0x180010c4f`
- `OLEAUT32!__imp_LoadTypeLib` at `0x180010ba7`
- `OLEAUT32!__imp_LoadTypeLib` at `0x180010c38`
- `OLEAUT32!__imp_LoadTypeLib` at `0x180010ba7`
- `OLEAUT32!__imp_LoadTypeLib` at `0x180010c38`

## pseudocode

```c
__int64 __fastcall ATL::AtlLoadTypeLib(
        HINSTANCE a1,
        const unsigned __int16 *a2,
        unsigned __int16 **a3,
        struct ITypeLib **a4)
{
  DWORD ModuleFileNameW; // eax
  WCHAR v8; // ax
  WCHAR *v9; // rcx
  wchar_t *v10; // rdi
  HRESULT TypeLib; // ebx
  __int64 v12; // rcx
  errno_t v13; // eax
  unsigned __int16 *v14; // rax
  wchar_t Source[8]; // [rsp+20h] [rbp-268h] BYREF
  WCHAR Filename[272]; // [rsp+30h] [rbp-258h] BYREF

  if ( !a3 || !a4 )
    return 2147500035LL;
  *a3 = 0;
  *a4 = 0;
  ModuleFileNameW = GetModuleFileNameW(a1, Filename, 0x104u);
  if ( !ModuleFileNameW )
    return ATL::AtlHresultFromLastError();
  if ( ModuleFileNameW == 260 )
    return 2147942522LL;
  v8 = Filename[0];
  v9 = Filename;
  if ( !Filename[0] )
    goto LABEL_15;
  v10 = 0;
  do
  {
    if ( v8 == 46 )
    {
      v10 = v9;
    }
    else if ( v8 == 92 )
    {
      v10 = 0;
    }
    v9 = CharNextW(v9);
    v8 = *v9;
  }
  while ( *v9 );
  if ( !v10 )
LABEL_15:
    v10 = v9;
  TypeLib = LoadTypeLib(Filename, a4);
  if ( TypeLib >= 0 )
    goto LABEL_25;
  wcscpy(Source, L".tlb");
  v12 = v10 - Filename;
  if ( (unsigned __int64)(v12 + 5) > 0x104 )
    return 2147500037LL;
  v13 = wcscpy_s(v10, 270 - v12, Source);
  if ( v13 )
  {
    if ( v13 == 12 )
      ATL::AtlThrowImpl(-2147024882);
    if ( v13 == 22 || v13 == 34 )
      ATL::AtlThrowImpl(-2147024809);
    if ( v13 != 80 )
      ATL::AtlThrowImpl(-2147467259);
  }
  TypeLib = LoadTypeLib(Filename, a4);
  if ( TypeLib >= 0 )
  {
LABEL_25:
    v14 = SysAllocString(Filename);
    *a3 = v14;
    if ( !v14 )
      return (unsigned int)-2147024882;
  }
  return (unsigned int)TypeLib;
}

```

## disassembly

```asm
0x180010ae4  push    rbx
0x180010ae6  push    rbp
0x180010ae7  push    rsi
0x180010ae8  push    rdi
0x180010ae9  push    r14
0x180010aeb  sub     rsp, 260h
0x180010af2  mov     rax, cs:__security_cookie
0x180010af9  xor     rax, rsp
0x180010afc  mov     [rsp+288h+var_38], rax
0x180010b04  xor     ebp, ebp
0x180010b06  mov     rsi, r9
0x180010b09  mov     r14, r8
0x180010b0c  test    r8, r8
0x180010b0f  jz      loc_180010C6D
0x180010b15  test    r9, r9
0x180010b18  jz      loc_180010C6D
0x180010b1e  mov     [r8], rbp
0x180010b21  lea     rdx, [rsp+288h+Filename]; lpFilename
0x180010b26  mov     r8d, 104h; nSize
0x180010b2c  mov     [r9], rbp
0x180010b2f  call    cs:__imp_GetModuleFileNameW
0x180010b36  nop     dword ptr [rax+rax+00h]
0x180010b3b  test    eax, eax
0x180010b3d  jnz     short loc_180010B49
0x180010b3f  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180010b44  jmp     loc_180010C72
0x180010b49  cmp     eax, 104h
0x180010b4e  jnz     short loc_180010B5A
0x180010b50  mov     eax, 8007007Ah
0x180010b55  jmp     loc_180010C72
0x180010b5a  movzx   eax, [rsp+288h+Filename]
0x180010b5f  lea     rcx, [rsp+288h+Filename]; lpsz
0x180010b64  test    ax, ax
0x180010b67  jz      short loc_180010B9C
0x180010b69  mov     rdi, rbp
0x180010b6c  cmp     ax, 2Eh ; '.'
0x180010b70  jz      short loc_180010B7D
0x180010b72  cmp     ax, 5Ch ; '\'
0x180010b76  jnz     short loc_180010B80
0x180010b78  mov     rdi, rbp
0x180010b7b  jmp     short loc_180010B80
0x180010b7d  mov     rdi, rcx
0x180010b80  call    cs:__imp_CharNextW
0x180010b87  nop     dword ptr [rax+rax+00h]
0x180010b8c  mov     rcx, rax
0x180010b8f  movzx   eax, word ptr [rax]
0x180010b92  test    ax, ax
0x180010b95  jnz     short loc_180010B6C
0x180010b97  test    rdi, rdi
0x180010b9a  jnz     short loc_180010B9F
0x180010b9c  mov     rdi, rcx
0x180010b9f  mov     rdx, rsi; pptlib
0x180010ba2  lea     rcx, [rsp+288h+Filename]; szFile
0x180010ba7  call    cs:__imp_LoadTypeLib
0x180010bae  nop     dword ptr [rax+rax+00h]
0x180010bb3  mov     ebx, eax
0x180010bb5  test    eax, eax
0x180010bb7  jns     loc_180010C4A
0x180010bbd  movzx   eax, word ptr cs:aTlb+8; ""
0x180010bc4  mov     rcx, rdi
0x180010bc7  movsd   xmm0, qword ptr cs:aTlb; ".tlb"
0x180010bcf  mov     [rsp+288h+var_260], ax
0x180010bd4  lea     rax, [rsp+288h+Filename]
0x180010bd9  sub     rcx, rax
0x180010bdc  movsd   qword ptr [rsp+288h+Source], xmm0
0x180010be2  sar     rcx, 1
0x180010be5  lea     rax, [rcx+5]
0x180010be9  cmp     rax, 104h
0x180010bef  jbe     short loc_180010BF8
0x180010bf1  mov     eax, 80004005h
0x180010bf6  jmp     short loc_180010C72
0x180010bf8  mov     edx, 10Eh
0x180010bfd  lea     r8, [rsp+288h+Source]; Source
0x180010c02  sub     rdx, rcx; SizeInWords
0x180010c05  mov     rcx, rdi; Destination
0x180010c08  call    cs:__imp_wcscpy_s
0x180010c0f  nop     dword ptr [rax+rax+00h]
0x180010c14  test    eax, eax
0x180010c16  jz      short loc_180010C30
0x180010c18  cmp     eax, 0Ch
0x180010c1b  jz      short loc_180010C91
0x180010c1d  cmp     eax, 16h
0x180010c20  jz      loc_180010CA7
0x180010c26  cmp     eax, 22h ; '"'
0x180010c29  jz      short loc_180010CA7
0x180010c2b  cmp     eax, 50h ; 'P'
0x180010c2e  jnz     short loc_180010C9C
0x180010c30  mov     rdx, rsi; pptlib
0x180010c33  lea     rcx, [rsp+288h+Filename]; szFile
0x180010c38  call    cs:__imp_LoadTypeLib
0x180010c3f  nop     dword ptr [rax+rax+00h]
0x180010c44  mov     ebx, eax
0x180010c46  test    eax, eax
0x180010c48  js      short loc_180010C69
0x180010c4a  lea     rcx, [rsp+288h+Filename]; psz
0x180010c4f  call    cs:__imp_SysAllocString
0x180010c56  nop     dword ptr [rax+rax+00h]
0x180010c5b  test    rax, rax
0x180010c5e  mov     [r14], rax
0x180010c61  mov     ecx, 8007000Eh
0x180010c66  cmovz   ebx, ecx
0x180010c69  mov     eax, ebx
0x180010c6b  jmp     short loc_180010C72
0x180010c6d  mov     eax, 80004003h
0x180010c72  mov     rcx, [rsp+288h+var_38]
0x180010c7a  xor     rcx, rsp; StackCookie
0x180010c7d  call    __security_check_cookie
0x180010c82  add     rsp, 260h
0x180010c89  pop     r14
0x180010c8b  pop     rdi
0x180010c8c  pop     rsi
0x180010c8d  pop     rbp
0x180010c8e  pop     rbx
0x180010c8f  retn
0x180010c91  mov     ecx, 8007000Eh; int
0x180010c96  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180010c9c  mov     ecx, 80004005h; int
0x180010ca1  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180010ca7  mov     ecx, 80070057h; int
0x180010cac  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
