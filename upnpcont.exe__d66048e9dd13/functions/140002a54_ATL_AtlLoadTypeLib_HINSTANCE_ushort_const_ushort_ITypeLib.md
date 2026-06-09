# ATL::AtlLoadTypeLib(HINSTANCE__ *,ushort const *,ushort * *,ITypeLib * *)

- ea: `0x140002a54`
- end: `0x140002bf5`
- name: `?AtlLoadTypeLib@ATL@@YAJPEAUHINSTANCE__@@PEBGPEAPEAGPEAPEAUITypeLib@@@Z`
- size: `417`
- prototype: `HRESULT __fastcall(HINSTANCE, const unsigned __int16 *, unsigned __int16 **, struct ITypeLib **)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x1400030b8`
- `0x1400053a0`

## callees

- `0x140001490`
- `0x140002a18`
- `0x140002a54`
- `0x140003298`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x140002b62`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x140002b62`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x140002a9f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x140002a9f`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x140002aea`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x140002aea`
- `OLEAUT32!__imp_SysAllocString` at `0x140002b99`
- `OLEAUT32!__imp_SysAllocString` at `0x140002b99`
- `OLEAUT32!__imp_LoadTypeLib` at `0x140002b0b`
- `OLEAUT32!__imp_LoadTypeLib` at `0x140002b88`
- `OLEAUT32!__imp_LoadTypeLib` at `0x140002b0b`
- `OLEAUT32!__imp_LoadTypeLib` at `0x140002b88`

## pseudocode

```c
HRESULT __fastcall ATL::AtlLoadTypeLib(
        HINSTANCE a1,
        const unsigned __int16 *a2,
        unsigned __int16 **a3,
        struct ITypeLib **a4)
{
  DWORD ModuleFileNameW; // eax
  WCHAR v8; // ax
  WCHAR *v9; // rcx
  WCHAR *v10; // rdi
  HRESULT TypeLib; // ebx
  __int64 v12; // rcx
  int v13; // eax
  unsigned __int16 *v14; // rax
  __int64 v15; // [rsp+20h] [rbp-268h] BYREF
  wchar_t v16; // [rsp+28h] [rbp-260h]
  WCHAR Filename[272]; // [rsp+30h] [rbp-258h] BYREF

  if ( !a3 || !a4 )
    return -2147467261;
  *a3 = 0;
  *a4 = 0;
  ModuleFileNameW = GetModuleFileNameW(a1, Filename, 0x104u);
  if ( !ModuleFileNameW )
    return ATL::AtlHresultFromLastError();
  if ( ModuleFileNameW == 260 )
    return -2147024774;
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
  v16 = aTlb[4];
  v15 = *(_QWORD *)L".tlb";
  v12 = v10 - Filename;
  if ( (unsigned __int64)(v12 + 5) > 0x104 )
    return -2147467259;
  v13 = _o_wcscpy_s(v10, 270 - v12, &v15);
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
      return -2147024882;
  }
  return TypeLib;
}

```

## disassembly

```asm
0x140002a54  push    rbx
0x140002a56  push    rbp
0x140002a57  push    rsi
0x140002a58  push    rdi
0x140002a59  push    r14
0x140002a5b  sub     rsp, 260h
0x140002a62  mov     rax, cs:__security_cookie
0x140002a69  xor     rax, rsp
0x140002a6c  mov     [rsp+288h+var_38], rax
0x140002a74  xor     ebp, ebp
0x140002a76  mov     rsi, r9
0x140002a79  mov     r14, r8
0x140002a7c  test    r8, r8
0x140002a7f  jz      loc_140002BB1
0x140002a85  test    r9, r9
0x140002a88  jz      loc_140002BB1
0x140002a8e  mov     [r8], rbp
0x140002a91  lea     rdx, [rsp+288h+Filename]; lpFilename
0x140002a96  mov     r8d, 104h; nSize
0x140002a9c  mov     [r9], rbp
0x140002a9f  call    cs:__imp_GetModuleFileNameW
0x140002aa5  test    eax, eax
0x140002aa7  jnz     short loc_140002AB3
0x140002aa9  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x140002aae  jmp     loc_140002BB6
0x140002ab3  cmp     eax, 104h
0x140002ab8  jnz     short loc_140002AC4
0x140002aba  mov     eax, 8007007Ah
0x140002abf  jmp     loc_140002BB6
0x140002ac4  movzx   eax, [rsp+288h+Filename]
0x140002ac9  lea     rcx, [rsp+288h+Filename]; lpsz
0x140002ace  test    ax, ax
0x140002ad1  jz      short loc_140002B00
0x140002ad3  mov     rdi, rbp
0x140002ad6  cmp     ax, 2Eh ; '.'
0x140002ada  jz      short loc_140002AE7
0x140002adc  cmp     ax, 5Ch ; '\'
0x140002ae0  jnz     short loc_140002AEA
0x140002ae2  mov     rdi, rbp
0x140002ae5  jmp     short loc_140002AEA
0x140002ae7  mov     rdi, rcx
0x140002aea  call    cs:__imp_CharNextW
0x140002af0  mov     rcx, rax
0x140002af3  movzx   eax, word ptr [rax]
0x140002af6  test    ax, ax
0x140002af9  jnz     short loc_140002AD6
0x140002afb  test    rdi, rdi
0x140002afe  jnz     short loc_140002B03
0x140002b00  mov     rdi, rcx
0x140002b03  mov     rdx, rsi; pptlib
0x140002b06  lea     rcx, [rsp+288h+Filename]; szFile
0x140002b0b  call    cs:__imp_LoadTypeLib
0x140002b11  mov     ebx, eax
0x140002b13  test    eax, eax
0x140002b15  jns     short loc_140002B94
0x140002b17  movzx   eax, word ptr cs:aTlb+8; ""
0x140002b1e  mov     rcx, rdi
0x140002b21  movsd   xmm0, qword ptr cs:aTlb; ".tlb"
0x140002b29  mov     [rsp+288h+var_260], ax
0x140002b2e  lea     rax, [rsp+288h+Filename]
0x140002b33  sub     rcx, rax
0x140002b36  movsd   [rsp+288h+var_268], xmm0
0x140002b3c  sar     rcx, 1
0x140002b3f  lea     rax, [rcx+5]
0x140002b43  cmp     rax, 104h
0x140002b49  jbe     short loc_140002B52
0x140002b4b  mov     eax, 80004005h
0x140002b50  jmp     short loc_140002BB6
0x140002b52  mov     edx, 10Eh
0x140002b57  lea     r8, [rsp+288h+var_268]
0x140002b5c  sub     rdx, rcx
0x140002b5f  mov     rcx, rdi
0x140002b62  call    cs:__imp__o_wcscpy_s
0x140002b68  test    eax, eax
0x140002b6a  jz      short loc_140002B80
0x140002b6c  cmp     eax, 0Ch
0x140002b6f  jz      short loc_140002BD4
0x140002b71  cmp     eax, 16h
0x140002b74  jz      short loc_140002BEA
0x140002b76  cmp     eax, 22h ; '"'
0x140002b79  jz      short loc_140002BEA
0x140002b7b  cmp     eax, 50h ; 'P'
0x140002b7e  jnz     short loc_140002BDF
0x140002b80  mov     rdx, rsi; pptlib
0x140002b83  lea     rcx, [rsp+288h+Filename]; szFile
0x140002b88  call    cs:__imp_LoadTypeLib
0x140002b8e  mov     ebx, eax
0x140002b90  test    eax, eax
0x140002b92  js      short loc_140002BAD
0x140002b94  lea     rcx, [rsp+288h+Filename]; psz
0x140002b99  call    cs:__imp_SysAllocString
0x140002b9f  test    rax, rax
0x140002ba2  mov     [r14], rax
0x140002ba5  mov     ecx, 8007000Eh
0x140002baa  cmovz   ebx, ecx
0x140002bad  mov     eax, ebx
0x140002baf  jmp     short loc_140002BB6
0x140002bb1  mov     eax, 80004003h
0x140002bb6  mov     rcx, [rsp+288h+var_38]
0x140002bbe  xor     rcx, rsp; StackCookie
0x140002bc1  call    __security_check_cookie
0x140002bc6  add     rsp, 260h
0x140002bcd  pop     r14
0x140002bcf  pop     rdi
0x140002bd0  pop     rsi
0x140002bd1  pop     rbp
0x140002bd2  pop     rbx
0x140002bd3  retn
0x140002bd4  mov     ecx, 8007000Eh; int
0x140002bd9  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x140002bdf  mov     ecx, 80004005h; int
0x140002be4  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x140002bea  mov     ecx, 80070057h; int
0x140002bef  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
