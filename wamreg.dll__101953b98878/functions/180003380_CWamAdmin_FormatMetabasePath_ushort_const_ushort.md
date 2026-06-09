# CWamAdmin::FormatMetabasePath(ushort const *,ushort * *)

- ea: `0x180003380`
- end: `0x18000345a`
- name: `?FormatMetabasePath@CWamAdmin@@EEAAJPEBGPEAPEAG@Z`
- size: `218`
- prototype: `__int64 __fastcall(CWamAdmin *this, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180001044`
- `0x180003380`

## import_xrefs

- `msvcrt!wcsncpy_s` at `0x1800033ee`
- `msvcrt!wcsncpy_s` at `0x1800033ee`
- `KERNEL32!GetLastError` at `0x1800033fc`
- `KERNEL32!GetLastError` at `0x1800033fc`
- `iisutil!PuDbgPrint` at `0x180003445`
- `iisutil!PuDbgPrint` at `0x180003445`

## string_xrefs

- `0x180003421`: `FormatMetabasePath, failed to allocate memory. hr = %08x\n`
- `0x18000342c`: `CWamAdmin::FormatMetabasePath`

## pseudocode

```c
__int64 __fastcall CWamAdmin::FormatMetabasePath(CWamAdmin *this, const unsigned __int16 *a2, unsigned __int16 **a3)
{
  __int64 v4; // rax
  rsize_t v6; // rbx
  unsigned int v7; // ebx
  wchar_t *v8; // rax
  unsigned __int16 *v9; // rbp
  signed int LastError; // eax

  v4 = -1;
  do
    ++v4;
  while ( a2[v4] );
  v6 = (int)v4;
  if ( a2[(int)v4 - 1] == 92 || a2[(int)v4 - 1] == 47 )
  {
    v8 = (wchar_t *)operator new(saturated_mul((int)v4, 2u));
    v9 = v8;
    if ( v8 )
    {
      wcsncpy_s(v8, v6, a2, v6 - 1);
      *a3 = v9;
      return 0;
    }
    else
    {
      LastError = GetLastError();
      v7 = LastError;
      if ( LastError > 0 )
        v7 = (unsigned __int16)LastError | 0x80070000;
      if ( (g_dwDebugFlags & 3) != 0 )
        PuDbgPrint(
          g_pDebug,
          "inetsrv\\iis\\svcs\\wam\\wamreg\\wamadm.cpp",
          1483,
          "CWamAdmin::FormatMetabasePath",
          "FormatMetabasePath, failed to allocate memory. hr = %08x\n",
          v7);
    }
  }
  else
  {
    v7 = 0;
    *a3 = (unsigned __int16 *)a2;
  }
  return v7;
}

```

## disassembly

```asm
0x180003380  push    rbx
0x180003382  push    rbp
0x180003383  push    rsi
0x180003384  push    rdi
0x180003385  push    r14
0x180003387  push    r15
0x180003389  sub     rsp, 38h
0x18000338d  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180003391  mov     rsi, r8
0x180003394  mov     rax, rcx
0x180003397  xor     r15d, r15d
0x18000339a  mov     rdi, rdx
0x18000339d  inc     rax
0x1800033a0  cmp     [rdx+rax*2], r15w
0x1800033a5  jnz     short loc_18000339D
0x1800033a7  movsxd  rbx, eax
0x1800033aa  cmp     word ptr [rdx+rbx*2-2], 5Ch ; '\'
0x1800033b0  jz      short loc_1800033C5
0x1800033b2  cmp     word ptr [rdx+rbx*2-2], 2Fh ; '/'
0x1800033b8  jz      short loc_1800033C5
0x1800033ba  mov     ebx, r15d
0x1800033bd  mov     [r8], rdi
0x1800033c0  jmp     loc_18000344B
0x1800033c5  mov     eax, 2
0x1800033ca  mul     rbx
0x1800033cd  cmovb   rax, rcx
0x1800033d1  mov     rcx, rax; Size
0x1800033d4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800033d9  mov     rbp, rax
0x1800033dc  test    rax, rax
0x1800033df  jz      short loc_1800033FC
0x1800033e1  lea     r9, [rbx-1]; MaxCount
0x1800033e5  mov     r8, rdi; Source
0x1800033e8  mov     rdx, rbx; SizeInWords
0x1800033eb  mov     rcx, rax; Destination
0x1800033ee  call    cs:__imp_wcsncpy_s
0x1800033f4  mov     [rsi], rbp
0x1800033f7  mov     ebx, r15d
0x1800033fa  jmp     short loc_18000344B
0x1800033fc  call    cs:__imp_GetLastError
0x180003402  mov     ebx, eax
0x180003404  test    eax, eax
0x180003406  jle     short loc_180003411
0x180003408  movzx   ebx, ax
0x18000340b  or      ebx, 80070000h
0x180003411  test    byte ptr cs:g_dwDebugFlags, 3
0x180003418  jz      short loc_18000344B
0x18000341a  mov     rcx, cs:g_pDebug
0x180003421  lea     rax, aFormatmetabase; "FormatMetabasePath, failed to allocate "...
0x180003428  mov     [rsp+68h+var_40], ebx
0x18000342c  lea     r9, aCwamadminForma; "CWamAdmin::FormatMetabasePath"
0x180003433  mov     r8d, 5CBh
0x180003439  mov     [rsp+68h+var_48], rax
0x18000343e  lea     rdx, aInetsrvIisSvcs_2; "inetsrv\\iis\\svcs\\wam\\wamreg\\wamadm"...
0x180003445  call    cs:__imp_PuDbgPrint
0x18000344b  mov     eax, ebx
0x18000344d  add     rsp, 38h
0x180003451  pop     r15
0x180003453  pop     r14
0x180003455  pop     rdi
0x180003456  pop     rsi
0x180003457  pop     rbp
0x180003458  pop     rbx
0x180003459  retn
```
