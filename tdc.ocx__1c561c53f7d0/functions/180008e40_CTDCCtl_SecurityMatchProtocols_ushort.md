# CTDCCtl::SecurityMatchProtocols(ushort *)

- ea: `0x180008e40`
- end: `0x180008f0a`
- name: `?SecurityMatchProtocols@CTDCCtl@@EEAAJPEAG@Z`
- size: `202`
- prototype: `int(CTDCCtl *__hidden this, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x180005bd4`
- `0x180008e40`
- `0x18000ecb0`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180008ef2`
- `ole32!CoTaskMemFree` at `0x180008ef2`

## pseudocode

```c
__int64 __fastcall CTDCCtl::SecurityMatchProtocols(CTDCCtl *this, unsigned __int16 *a2)
{
  struct IOleClientSite *v2; // rcx
  unsigned int v4; // esi
  char *v5; // r8
  unsigned __int16 v6; // cx
  unsigned __int16 *v7; // rax
  __int64 v8; // r8
  LPVOID pv; // [rsp+30h] [rbp+8h] BYREF

  v2 = (struct IOleClientSite *)*((_QWORD *)this + 4);
  pv = 0;
  v4 = -2147467259;
  if ( (int)GetHostURL(v2, (unsigned __int16 **)&pv) >= 0 )
  {
    v5 = (char *)pv;
    if ( pv )
    {
      while ( *(_WORD *)v5 )
      {
        if ( *(_WORD *)v5 == 58 )
          goto LABEL_8;
        v5 += 2;
      }
    }
    v5 = 0;
LABEL_8:
    if ( a2 && (v6 = *a2) != 0 )
    {
      v7 = a2;
      while ( v6 != 58 )
      {
        v6 = *++v7;
        if ( !*v7 )
          goto LABEL_13;
      }
    }
    else
    {
LABEL_13:
      v7 = 0;
    }
    if ( v5 )
    {
      if ( v7 )
      {
        v8 = (v5 - (_BYTE *)pv) >> 1;
        if ( (_DWORD)v8 == (unsigned int)(v7 - a2) )
          v4 = (unsigned int)wch_ncmp((unsigned __int16 *)pv, a2, v8) != 0 ? 0x80004005 : 0;
      }
    }
  }
  if ( pv )
    CoTaskMemFree(pv);
  return v4;
}

```

## disassembly

```asm
0x180008e40  mov     rax, rsp
0x180008e43  mov     [rax+10h], rbp
0x180008e47  mov     [rax+18h], rsi
0x180008e4b  push    rdi
0x180008e4c  sub     rsp, 20h
0x180008e50  mov     rcx, [rcx+20h]; struct IOleClientSite *
0x180008e54  mov     rdi, rdx
0x180008e57  xor     ebp, ebp
0x180008e59  lea     rdx, [rax+8]; unsigned __int16 **
0x180008e5d  mov     [rax+8], rbp
0x180008e61  mov     esi, 80004005h
0x180008e66  call    ?GetHostURL@@YAJPEAUIOleClientSite@@PEAPEAG@Z; GetHostURL(IOleClientSite *,ushort * *)
0x180008e6b  test    eax, eax
0x180008e6d  js      short loc_180008EE6
0x180008e6f  mov     r8, [rsp+28h+pv]
0x180008e74  test    r8, r8
0x180008e77  jz      short loc_180008E8E
0x180008e79  jmp     short loc_180008E85
0x180008e7b  cmp     ax, 3Ah ; ':'
0x180008e7f  jz      short loc_180008E91
0x180008e81  add     r8, 2
0x180008e85  movzx   eax, word ptr [r8]
0x180008e89  test    ax, ax
0x180008e8c  jnz     short loc_180008E7B
0x180008e8e  mov     r8, rbp
0x180008e91  test    rdi, rdi
0x180008e94  jz      short loc_180008EB3
0x180008e96  movzx   ecx, word ptr [rdi]
0x180008e99  test    cx, cx
0x180008e9c  jz      short loc_180008EB3
0x180008e9e  mov     rax, rdi
0x180008ea1  cmp     cx, 3Ah ; ':'
0x180008ea5  jz      short loc_180008EB6
0x180008ea7  add     rax, 2
0x180008eab  movzx   ecx, word ptr [rax]
0x180008eae  test    cx, cx
0x180008eb1  jnz     short loc_180008EA1
0x180008eb3  mov     rax, rbp
0x180008eb6  test    r8, r8
0x180008eb9  jz      short loc_180008EE6
0x180008ebb  test    rax, rax
0x180008ebe  jz      short loc_180008EE6
0x180008ec0  sub     r8, [rsp+28h+pv]
0x180008ec5  sub     rax, rdi
0x180008ec8  sar     r8, 1; unsigned int
0x180008ecb  sar     rax, 1
0x180008ece  cmp     r8d, eax
0x180008ed1  jnz     short loc_180008EE6
0x180008ed3  mov     rcx, [rsp+28h+pv]; unsigned __int16 *
0x180008ed8  mov     rdx, rdi; unsigned __int16 *
0x180008edb  call    ?wch_ncmp@@YAHPEAG0K@Z; wch_ncmp(ushort *,ushort *,ulong)
0x180008ee0  neg     eax
0x180008ee2  sbb     edx, edx
0x180008ee4  and     esi, edx
0x180008ee6  cmp     [rsp+28h+pv], rbp
0x180008eeb  jz      short loc_180008EF8
0x180008eed  mov     rcx, [rsp+28h+pv]; pv
0x180008ef2  call    cs:__imp_CoTaskMemFree
0x180008ef8  mov     rbp, [rsp+28h+arg_8]
0x180008efd  mov     eax, esi
0x180008eff  mov     rsi, [rsp+28h+arg_10]
0x180008f04  add     rsp, 20h
0x180008f08  pop     rdi
0x180008f09  retn
```
