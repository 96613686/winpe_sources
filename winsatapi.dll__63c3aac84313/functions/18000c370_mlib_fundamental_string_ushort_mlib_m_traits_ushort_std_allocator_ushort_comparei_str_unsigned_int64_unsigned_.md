# mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::comparei_str(unsigned __int64,unsigned __int64,ushort const *,unsigned __int64)

- ea: `0x18000c370`
- end: `0x18000c405`
- name: `?comparei_str@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEBAH_K0PEBG0@Z`
- size: `149`
- prototype: `__int64 __fastcall(unsigned __int64 **, __int64, unsigned __int64, const WCHAR *lpString2, unsigned __int64 cchCount1)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18001cf78`

## callees

- `0x18000c370`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000c3c4`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000c3c4`

## pseudocode

```c
__int64 __fastcall mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::comparei_str(
        unsigned __int64 **a1,
        __int64 a2,
        unsigned __int64 a3,
        const WCHAR *lpString2,
        unsigned __int64 cchCount1)
{
  unsigned __int64 *v5; // rdx
  unsigned __int64 cchCount2; // rdi
  const WCHAR *v7; // r8
  int v8; // eax
  bool v9; // zf
  __int64 result; // rax

  v5 = *a1;
  cchCount2 = a3;
  if ( a3 > **a1 )
    cchCount2 = *v5;
  if ( !cchCount2 )
    return (unsigned int)-(cchCount1 != 0);
  if ( !cchCount1 )
    return 1;
  v7 = (const WCHAR *)v5[3];
  if ( cchCount2 >= cchCount1 )
    v8 = CompareStringW(0x400u, 0x1001u, v7, cchCount1, lpString2, cchCount1);
  else
    v8 = CompareStringW(0x400u, 0x1001u, v7, cchCount2, lpString2, cchCount2);
  v9 = v8 == 2;
  result = (unsigned int)(v8 - 2);
  if ( v9 )
  {
    if ( cchCount2 >= cchCount1 )
      return cchCount2 != cchCount1;
    else
      return 0xFFFFFFFFLL;
  }
  return result;
}

```

## disassembly

```asm
0x18000c370  push    rdi
0x18000c372  sub     rsp, 30h
0x18000c376  mov     rdx, [rcx]
0x18000c379  mov     rdi, r8
0x18000c37c  cmp     r8, [rdx]
0x18000c37f  cmova   rdi, [rdx]
0x18000c383  test    rdi, rdi
0x18000c386  jz      short loc_18000C3F5
0x18000c388  mov     [rsp+38h+arg_0], rbx
0x18000c38d  mov     rbx, qword ptr [rsp+38h+cchCount1]
0x18000c392  test    rbx, rbx
0x18000c395  jz      short loc_18000C3EE
0x18000c397  mov     r8, [rdx+18h]; lpString1
0x18000c39b  mov     edx, 1001h; dwCmpFlags
0x18000c3a0  mov     ecx, 400h; Locale
0x18000c3a5  cmp     rdi, rbx
0x18000c3a8  jnb     short loc_18000C3B8
0x18000c3aa  mov     [rsp+38h+cchCount2], edi
0x18000c3ae  mov     [rsp+38h+lpString2], r9
0x18000c3b3  mov     r9d, edi
0x18000c3b6  jmp     short loc_18000C3C4
0x18000c3b8  mov     [rsp+38h+cchCount2], ebx; cchCount2
0x18000c3bc  mov     [rsp+38h+lpString2], r9; lpString2
0x18000c3c1  mov     r9d, ebx; cchCount1
0x18000c3c4  call    cs:__imp_CompareStringW
0x18000c3ca  add     eax, 0FFFFFFFEh
0x18000c3cd  jnz     short loc_18000C3D9
0x18000c3cf  cmp     rdi, rbx
0x18000c3d2  jnb     short loc_18000C3E4
0x18000c3d4  mov     eax, 0FFFFFFFFh
0x18000c3d9  mov     rbx, [rsp+38h+arg_0]
0x18000c3de  add     rsp, 30h
0x18000c3e2  pop     rdi
0x18000c3e3  retn
0x18000c3e4  xor     eax, eax
0x18000c3e6  cmp     rdi, rbx
0x18000c3e9  setnz   al
0x18000c3ec  jmp     short loc_18000C3D9
0x18000c3ee  mov     eax, 1
0x18000c3f3  jmp     short loc_18000C3D9
0x18000c3f5  mov     rax, qword ptr [rsp+38h+cchCount1]
0x18000c3fa  neg     rax
0x18000c3fd  sbb     eax, eax
0x18000c3ff  add     rsp, 30h
0x18000c403  pop     rdi
0x18000c404  retn
```
