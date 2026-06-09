# mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::compare_str(unsigned __int64,unsigned __int64,ushort const *,unsigned __int64)

- ea: `0x18000cc40`
- end: `0x18000ccd5`
- name: `?compare_str@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEBAH_K0PEBG0@Z`
- size: `149`
- prototype: `__int64 __fastcall(unsigned __int64 **, __int64, unsigned __int64, const WCHAR *lpString2, unsigned __int64 cchCount1)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18002ba4c`

## callees

- `0x18000cc40`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000cc94`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000cc94`

## pseudocode

```c
__int64 __fastcall mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::compare_str(
        unsigned __int64 **a1,
        __int64 a2,
        unsigned __int64 a3,
        const WCHAR *lpString2,
        unsigned __int64 cchCount1)
{
  unsigned __int64 *v5; // rdx
  unsigned __int64 cchCount2; // rbx
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
    v8 = CompareStringW(0x400u, 0x1000u, v7, cchCount1, lpString2, cchCount1);
  else
    v8 = CompareStringW(0x400u, 0x1000u, v7, cchCount2, lpString2, cchCount2);
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
0x18000cc40  push    rbx
0x18000cc42  sub     rsp, 30h
0x18000cc46  mov     rdx, [rcx]
0x18000cc49  mov     rbx, r8
0x18000cc4c  cmp     r8, [rdx]
0x18000cc4f  cmova   rbx, [rdx]
0x18000cc53  test    rbx, rbx
0x18000cc56  jz      short loc_18000CCC5
0x18000cc58  mov     [rsp+38h+arg_0], rdi
0x18000cc5d  mov     rdi, qword ptr [rsp+38h+cchCount1]
0x18000cc62  test    rdi, rdi
0x18000cc65  jz      short loc_18000CCBE
0x18000cc67  mov     r8, [rdx+18h]; lpString1
0x18000cc6b  mov     edx, 1000h; dwCmpFlags
0x18000cc70  mov     ecx, 400h; Locale
0x18000cc75  cmp     rbx, rdi
0x18000cc78  jnb     short loc_18000CC88
0x18000cc7a  mov     [rsp+38h+cchCount2], ebx
0x18000cc7e  mov     [rsp+38h+lpString2], r9
0x18000cc83  mov     r9d, ebx
0x18000cc86  jmp     short loc_18000CC94
0x18000cc88  mov     [rsp+38h+cchCount2], edi; cchCount2
0x18000cc8c  mov     [rsp+38h+lpString2], r9; lpString2
0x18000cc91  mov     r9d, edi; cchCount1
0x18000cc94  call    cs:__imp_CompareStringW
0x18000cc9a  add     eax, 0FFFFFFFEh
0x18000cc9d  jnz     short loc_18000CCA9
0x18000cc9f  cmp     rbx, rdi
0x18000cca2  jnb     short loc_18000CCB4
0x18000cca4  mov     eax, 0FFFFFFFFh
0x18000cca9  mov     rdi, [rsp+38h+arg_0]
0x18000ccae  add     rsp, 30h
0x18000ccb2  pop     rbx
0x18000ccb3  retn
0x18000ccb4  xor     eax, eax
0x18000ccb6  cmp     rbx, rdi
0x18000ccb9  setnz   al
0x18000ccbc  jmp     short loc_18000CCA9
0x18000ccbe  mov     eax, 1
0x18000ccc3  jmp     short loc_18000CCA9
0x18000ccc5  mov     rax, qword ptr [rsp+38h+cchCount1]
0x18000ccca  neg     rax
0x18000cccd  sbb     eax, eax
0x18000cccf  add     rsp, 30h
0x18000ccd3  pop     rbx
0x18000ccd4  retn
```
