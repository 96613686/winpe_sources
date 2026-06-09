# mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::eqi(mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x18000cad4`
- end: `0x18000cb5b`
- name: `?eqi@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEBA_NAEBV12@@Z`
- size: `135`
- prototype: `bool __fastcall(unsigned __int64 **, unsigned __int64 **)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800039c0`
- `0x18002a714`

## callees

- `0x18000cad4`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000cb20`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000cb20`

## pseudocode

```c
bool __fastcall mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::eqi(
        unsigned __int64 **a1,
        unsigned __int64 **a2)
{
  unsigned __int64 v2; // rbx
  unsigned __int64 cchCount2; // rdi
  const WCHAR *v4; // r8
  const WCHAR *lpString2; // rcx
  int v6; // eax
  int v7; // eax

  v2 = **a2;
  cchCount2 = **a1;
  if ( cchCount2 )
  {
    if ( v2 )
    {
      v4 = (const WCHAR *)(*a1)[3];
      lpString2 = (const WCHAR *)(*a2)[3];
      if ( cchCount2 >= v2 )
        v6 = CompareStringW(0x400u, 0x1001u, v4, v2, lpString2, v2);
      else
        v6 = CompareStringW(0x400u, 0x1001u, v4, cchCount2, lpString2, cchCount2);
      v7 = v6 - 2;
      if ( !v7 )
      {
        if ( cchCount2 >= v2 )
          v7 = cchCount2 != v2;
        else
          v7 = -1;
      }
    }
    else
    {
      v7 = 1;
    }
  }
  else
  {
    v7 = -(v2 != 0);
  }
  return v7 == 0;
}

```

## disassembly

```asm
0x18000cad4  mov     [rsp+arg_0], rbx
0x18000cad9  push    rdi
0x18000cada  sub     rsp, 30h
0x18000cade  mov     rax, [rdx]
0x18000cae1  mov     rdx, [rcx]
0x18000cae4  mov     rbx, [rax]
0x18000cae7  mov     rdi, [rdx]
0x18000caea  test    rdi, rdi
0x18000caed  jz      short loc_18000CB46
0x18000caef  test    rbx, rbx
0x18000caf2  jz      short loc_18000CB3F
0x18000caf4  mov     r8, [rdx+18h]; lpString1
0x18000caf8  mov     edx, 1001h; dwCmpFlags
0x18000cafd  mov     rcx, [rax+18h]
0x18000cb01  cmp     rdi, rbx
0x18000cb04  jnb     short loc_18000CB0F
0x18000cb06  mov     [rsp+38h+cchCount2], edi
0x18000cb0a  mov     r9d, edi
0x18000cb0d  jmp     short loc_18000CB16
0x18000cb0f  mov     [rsp+38h+cchCount2], ebx; cchCount2
0x18000cb13  mov     r9d, ebx; cchCount1
0x18000cb16  mov     [rsp+38h+lpString2], rcx; lpString2
0x18000cb1b  mov     ecx, 400h; Locale
0x18000cb20  call    cs:__imp_CompareStringW
0x18000cb26  add     eax, 0FFFFFFFEh
0x18000cb29  jnz     short loc_18000CB4B
0x18000cb2b  cmp     rdi, rbx
0x18000cb2e  jnb     short loc_18000CB35
0x18000cb30  or      eax, 0FFFFFFFFh
0x18000cb33  jmp     short loc_18000CB4B
0x18000cb35  xor     eax, eax
0x18000cb37  cmp     rdi, rbx
0x18000cb3a  setnz   al
0x18000cb3d  jmp     short loc_18000CB4B
0x18000cb3f  mov     eax, 1
0x18000cb44  jmp     short loc_18000CB4B
0x18000cb46  neg     rbx
0x18000cb49  sbb     eax, eax
0x18000cb4b  mov     rbx, [rsp+38h+arg_0]
0x18000cb50  test    eax, eax
0x18000cb52  setz    al
0x18000cb55  add     rsp, 30h
0x18000cb59  pop     rdi
0x18000cb5a  retn
```
