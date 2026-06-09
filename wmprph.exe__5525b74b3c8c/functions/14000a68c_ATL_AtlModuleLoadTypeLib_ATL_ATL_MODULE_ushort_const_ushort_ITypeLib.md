# ATL::AtlModuleLoadTypeLib(ATL::_ATL_MODULE *,ushort const *,ushort * *,ITypeLib * *)

- ea: `0x14000a68c`
- end: `0x14000a821`
- name: `?AtlModuleLoadTypeLib@ATL@@YAJPEAU_ATL_MODULE@1@PEBGPEAPEAGPEAPEAUITypeLib@@@Z`
- size: `405`
- prototype: `int(struct ATL::_ATL_MODULE *, const unsigned __int16 *, unsigned __int16 **, struct ITypeLib **)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x14000a828`
- `0x14000a9ec`

## callees

- `0x140001390`
- `0x14000a68c`

## import_xrefs

- `KERNEL32!GetModuleFileNameW` at `0x14000a6eb`
- `KERNEL32!GetModuleFileNameW` at `0x14000a6eb`
- `KERNEL32!GetLastError` at `0x14000a706`
- `KERNEL32!GetLastError` at `0x14000a706`
- `USER32!CharNextW` at `0x14000a76a`
- `USER32!CharNextW` at `0x14000a76a`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x14000a7cd`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x14000a7cd`
- `OLEAUT32!__imp_SysAllocString` at `0x14000a7ec`
- `OLEAUT32!__imp_SysAllocString` at `0x14000a7ec`
- `OLEAUT32!__imp_LoadTypeLib` at `0x14000a729`
- `OLEAUT32!__imp_LoadTypeLib` at `0x14000a7db`
- `OLEAUT32!__imp_LoadTypeLib` at `0x14000a729`
- `OLEAUT32!__imp_LoadTypeLib` at `0x14000a7db`

## pseudocode

```c
HRESULT __fastcall ATL::AtlModuleLoadTypeLib(
        HMODULE *a1,
        const unsigned __int16 *a2,
        unsigned __int16 **a3,
        struct ITypeLib **a4)
{
  HRESULT result; // eax
  DWORD ModuleFileNameW; // eax
  HRESULT TypeLib; // ebx
  WCHAR v9; // cx
  WCHAR *v10; // r9
  WCHAR *v11; // rbx
  WCHAR *v12; // rax
  __int64 v13; // rcx
  __int64 v14; // [rsp+20h] [rbp-258h] BYREF
  wchar_t v15; // [rsp+28h] [rbp-250h]
  WCHAR Filename[272]; // [rsp+30h] [rbp-248h] BYREF

  if ( !a3 )
    return -2147467261;
  *a3 = 0;
  if ( !a4 )
    return -2147467261;
  *a4 = 0;
  if ( !a1 )
    return -2147024809;
  ModuleFileNameW = GetModuleFileNameW(a1[3], Filename, 0x104u);
  if ( ModuleFileNameW == 260 )
    return -2147024785;
  if ( ModuleFileNameW )
  {
    TypeLib = LoadTypeLib(Filename, a4);
    if ( TypeLib >= 0 )
      goto LABEL_25;
    v9 = Filename[0];
    v10 = Filename;
    v11 = 0;
    while ( v9 )
    {
      if ( v9 == 92 || v9 == 47 )
      {
        v11 = 0;
      }
      else
      {
        v12 = v10;
        if ( v9 != 46 )
          v12 = v11;
        v11 = v12;
      }
      v10 = CharNextW(v10);
      v9 = *v10;
    }
    if ( v11 )
      v10 = v11;
    v15 = aTlb[4];
    v14 = *(_QWORD *)L".tlb";
    v13 = v10 - Filename;
    if ( (unsigned __int64)(v13 + 5) > 0x104 )
      return -2147467259;
    _o_wcscpy_s(v10, 270 - v13, &v14);
    TypeLib = LoadTypeLib(Filename, a4);
    if ( TypeLib >= 0 )
LABEL_25:
      *a3 = SysAllocString(Filename);
    return TypeLib;
  }
  else
  {
    result = GetLastError();
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  return result;
}

```

## disassembly

```asm
0x14000a68c  mov     [rsp+arg_8], rbx
0x14000a691  push    rbp
0x14000a692  push    rsi
0x14000a693  push    rdi
0x14000a694  sub     rsp, 260h
0x14000a69b  mov     rax, cs:__security_cookie
0x14000a6a2  xor     rax, rsp
0x14000a6a5  mov     [rsp+278h+var_28], rax
0x14000a6ad  xor     ebp, ebp
0x14000a6af  mov     rdi, r9
0x14000a6b2  mov     rsi, r8
0x14000a6b5  test    r8, r8
0x14000a6b8  jz      loc_14000A7F9
0x14000a6be  mov     [r8], rbp
0x14000a6c1  test    r9, r9
0x14000a6c4  jz      loc_14000A7F9
0x14000a6ca  mov     [r9], rbp
0x14000a6cd  test    rcx, rcx
0x14000a6d0  jnz     short loc_14000A6DC
0x14000a6d2  mov     eax, 80070057h
0x14000a6d7  jmp     loc_14000A7FE
0x14000a6dc  mov     rcx, [rcx+18h]; hModule
0x14000a6e0  lea     rdx, [rsp+278h+Filename]; lpFilename
0x14000a6e5  mov     r8d, 104h; nSize
0x14000a6eb  call    cs:__imp_GetModuleFileNameW
0x14000a6f1  cmp     eax, 104h
0x14000a6f6  jnz     short loc_14000A702
0x14000a6f8  mov     eax, 8007006Fh
0x14000a6fd  jmp     loc_14000A7FE
0x14000a702  test    eax, eax
0x14000a704  jnz     short loc_14000A721
0x14000a706  call    cs:__imp_GetLastError
0x14000a70c  test    eax, eax
0x14000a70e  jle     loc_14000A7FE
0x14000a714  movzx   eax, ax
0x14000a717  or      eax, 80070000h
0x14000a71c  jmp     loc_14000A7FE
0x14000a721  mov     rdx, rdi; pptlib
0x14000a724  lea     rcx, [rsp+278h+Filename]; szFile
0x14000a729  call    cs:__imp_LoadTypeLib
0x14000a72f  mov     ebx, eax
0x14000a731  test    eax, eax
0x14000a733  jns     loc_14000A7E7
0x14000a739  movzx   ecx, [rsp+278h+Filename]
0x14000a73e  lea     r9, [rsp+278h+Filename]
0x14000a743  mov     rbx, rbp
0x14000a746  jmp     short loc_14000A776
0x14000a748  cmp     cx, 5Ch ; '\'
0x14000a74c  jz      short loc_14000A764
0x14000a74e  cmp     cx, 2Fh ; '/'
0x14000a752  jz      short loc_14000A764
0x14000a754  cmp     cx, 2Eh ; '.'
0x14000a758  mov     rax, r9
0x14000a75b  cmovnz  rax, rbx
0x14000a75f  mov     rbx, rax
0x14000a762  jmp     short loc_14000A767
0x14000a764  mov     rbx, rbp
0x14000a767  mov     rcx, r9; lpsz
0x14000a76a  call    cs:__imp_CharNextW
0x14000a770  mov     r9, rax
0x14000a773  movzx   ecx, word ptr [rax]
0x14000a776  test    cx, cx
0x14000a779  jnz     short loc_14000A748
0x14000a77b  movzx   eax, word ptr cs:aTlb+8; ""
0x14000a782  test    rbx, rbx
0x14000a785  movsd   xmm0, qword ptr cs:aTlb; ".tlb"
0x14000a78d  cmovnz  r9, rbx
0x14000a791  mov     [rsp+278h+var_250], ax
0x14000a796  lea     rax, [rsp+278h+Filename]
0x14000a79b  movsd   [rsp+278h+var_258], xmm0
0x14000a7a1  mov     rcx, r9
0x14000a7a4  sub     rcx, rax
0x14000a7a7  sar     rcx, 1
0x14000a7aa  lea     rax, [rcx+5]
0x14000a7ae  cmp     rax, 104h
0x14000a7b4  jbe     short loc_14000A7BD
0x14000a7b6  mov     eax, 80004005h
0x14000a7bb  jmp     short loc_14000A7FE
0x14000a7bd  mov     edx, 10Eh
0x14000a7c2  lea     r8, [rsp+278h+var_258]
0x14000a7c7  sub     rdx, rcx
0x14000a7ca  mov     rcx, r9
0x14000a7cd  call    cs:__imp__o_wcscpy_s
0x14000a7d3  mov     rdx, rdi; pptlib
0x14000a7d6  lea     rcx, [rsp+278h+Filename]; szFile
0x14000a7db  call    cs:__imp_LoadTypeLib
0x14000a7e1  mov     ebx, eax
0x14000a7e3  test    eax, eax
0x14000a7e5  js      short loc_14000A7F5
0x14000a7e7  lea     rcx, [rsp+278h+Filename]; psz
0x14000a7ec  call    cs:__imp_SysAllocString
0x14000a7f2  mov     [rsi], rax
0x14000a7f5  mov     eax, ebx
0x14000a7f7  jmp     short loc_14000A7FE
0x14000a7f9  mov     eax, 80004003h
0x14000a7fe  mov     rcx, [rsp+278h+var_28]
0x14000a806  xor     rcx, rsp; StackCookie
0x14000a809  call    __security_check_cookie
0x14000a80e  mov     rbx, [rsp+278h+arg_8]
0x14000a816  add     rsp, 260h
0x14000a81d  pop     rdi
0x14000a81e  pop     rsi
0x14000a81f  pop     rbp
0x14000a820  retn
```
