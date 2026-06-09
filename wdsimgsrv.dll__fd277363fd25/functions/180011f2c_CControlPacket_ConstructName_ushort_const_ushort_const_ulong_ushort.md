# CControlPacket::ConstructName(ushort const *,ushort const *,ulong,ushort * *)

- ea: `0x180011f2c`
- end: `0x180012005`
- name: `?ConstructName@CControlPacket@@QEAAKPEBG0KPEAPEAG@Z`
- size: `217`
- prototype: `unsigned int __fastcall(CControlPacket *__hidden this, const unsigned __int16 *, const unsigned __int16 *, unsigned int, unsigned __int16 **)`
- caller_count: `8`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180011834`
- `0x1800118fc`
- `0x1800119d4`
- `0x180011a90`
- `0x180011bd4`
- `0x180011cb4`
- `0x18001231c`
- `0x180012510`

## callees

- `0x180011f2c`

## import_xrefs

- `WdsCommonLib!?FormatString@@YAKPEAPEAG_KPEBGZZ` at `0x180011f8e`
- `WdsCommonLib!?FormatString@@YAKPEAPEAG_KPEBGZZ` at `0x180011f8e`
- `WdsCommonLib!?FormatString@@YAKPEAPEAG_KPEBGZZ` at `0x180011fdf`
- `WdsCommonLib!?DuplicateStringW@@YAKPEBGPEAPEAG@Z` at `0x180011ff3`
- `WdsCommonLib!?DuplicateStringW@@YAKPEBGPEAPEAG@Z` at `0x180011ff3`

## pseudocode

```c
unsigned int __fastcall CControlPacket::ConstructName(
        CControlPacket *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        int a4,
        unsigned __int16 **a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        __int64 a9)
{
  __int64 v10; // rax
  __int64 v11; // rdx
  unsigned __int64 v12; // rdx
  const WCHAR *v13; // rax
  __int64 v15; // rax
  __int64 v16; // rdx

  if ( a4 == -1 )
  {
    if ( a3 )
    {
      v15 = -1;
      v16 = -1;
      do
        ++v16;
      while ( a2[v16] );
      do
        ++v15;
      while ( a3[v15] );
      return FormatString(a5, v15 + 6 + v16, L"%s.%s", a2, a3, a6, a7, a8, a9);
    }
    else
    {
      return DuplicateStringW(a2, a5);
    }
  }
  else
  {
    v10 = -1;
    if ( a3 )
    {
      v11 = -1;
      do
        ++v11;
      while ( a3[v11] );
    }
    else
    {
      v11 = 0;
    }
    do
      ++v10;
    while ( a2[v10] );
    v12 = v10 + 26 + v11;
    v13 = &pszSrch;
    if ( a3 )
      v13 = a3;
    return FormatString(a5, v12, L"%s.%s[%u]", a2, v13, a4);
  }
}

```

## disassembly

```asm
0x180011f2c  sub     rsp, 38h
0x180011f30  xor     ecx, ecx
0x180011f32  mov     r10, rdx
0x180011f35  cmp     r9d, 0FFFFFFFFh
0x180011f39  jz      short loc_180011FA0
0x180011f3b  or      rax, 0FFFFFFFFFFFFFFFFh
0x180011f3f  test    r8, r8
0x180011f42  jz      short loc_180011F53
0x180011f44  mov     rdx, rax
0x180011f47  inc     rdx
0x180011f4a  cmp     [r8+rdx*2], cx
0x180011f4f  jnz     short loc_180011F47
0x180011f51  jmp     short loc_180011F56
0x180011f53  mov     rdx, rcx
0x180011f56  inc     rax
0x180011f59  cmp     [r10+rax*2], cx
0x180011f5e  jnz     short loc_180011F56
0x180011f60  mov     rcx, [rsp+38h+arg_20]
0x180011f65  add     rax, 1Ah
0x180011f69  add     rdx, rax
0x180011f6c  mov     [rsp+38h+var_10], r9d
0x180011f71  test    r8, r8
0x180011f74  lea     rax, pszSrch
0x180011f7b  mov     r9, r10
0x180011f7e  cmovnz  rax, r8
0x180011f82  lea     r8, aSSU; "%s.%s[%u]"
0x180011f89  mov     [rsp+38h+var_18], rax
0x180011f8e  call    cs:__imp_?FormatString@@YAKPEAPEAG_KPEBGZZ; FormatString(ushort * *,unsigned __int64,ushort const *,...)
0x180011f95  nop     dword ptr [rax+rax+00h]
0x180011f9a  add     rsp, 38h
0x180011f9e  retn
0x180011fa0  test    r8, r8
0x180011fa3  jz      short loc_180011FEB
0x180011fa5  or      rax, 0FFFFFFFFFFFFFFFFh
0x180011fa9  mov     rdx, rax
0x180011fac  inc     rdx
0x180011faf  cmp     [r10+rdx*2], cx
0x180011fb4  jnz     short loc_180011FAC
0x180011fb6  inc     rax
0x180011fb9  cmp     [r8+rax*2], cx
0x180011fbe  jnz     short loc_180011FB6
0x180011fc0  mov     rcx, [rsp+38h+arg_20]
0x180011fc5  add     rax, 6
0x180011fc9  mov     [rsp+38h+arg_20], r8
0x180011fce  add     rdx, rax
0x180011fd1  mov     r9, r10
0x180011fd4  lea     r8, aSS; "%s.%s"
0x180011fdb  add     rsp, 38h
0x180011fdf  jmp     cs:__imp_?FormatString@@YAKPEAPEAG_KPEBGZZ; FormatString(ushort * *,unsigned __int64,ushort const *,...)
0x180011feb  mov     rdx, [rsp+38h+arg_20]
0x180011ff0  mov     rcx, r10
0x180011ff3  call    cs:__imp_?DuplicateStringW@@YAKPEBGPEAPEAG@Z; DuplicateStringW(ushort const *,ushort * *)
0x180011ffa  nop     dword ptr [rax+rax+00h]
0x180011fff  add     rsp, 38h
0x180012003  retn
```
