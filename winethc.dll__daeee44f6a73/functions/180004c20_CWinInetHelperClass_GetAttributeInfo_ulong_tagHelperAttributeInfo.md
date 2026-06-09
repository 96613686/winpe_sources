# CWinInetHelperClass::GetAttributeInfo(ulong *,tagHelperAttributeInfo * *)

- ea: `0x180004c20`
- end: `0x180004d4e`
- name: `?GetAttributeInfo@CWinInetHelperClass@@UEAAJPEAKPEAPEAUtagHelperAttributeInfo@@@Z`
- size: `302`
- prototype: `__int64 __fastcall(CWinInetHelperClass *__hidden this, unsigned int *, struct tagHelperAttributeInfo **)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x180004c20`
- `0x18000ca0c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180004c90`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180004c90`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004d12`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004d27`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004d12`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004d27`

## pseudocode

```c
__int64 __fastcall CWinInetHelperClass::GetAttributeInfo(
        CWinInetHelperClass *this,
        unsigned int *a2,
        struct tagHelperAttributeInfo **a3)
{
  unsigned int v3; // esi
  const struct tagHelperAttributeInfo near *const *v6; // r15
  const struct tagHelperAttributeInfo near *const *v7; // rax
  unsigned int v8; // edi
  int v9; // ebx
  SIZE_T v10; // rbx
  struct tagHelperAttributeInfo *v11; // rax
  struct tagHelperAttributeInfo *v12; // rbp
  struct tagHelperAttributeInfo *i; // r13
  unsigned int j; // edi
  LPWSTR pwszName; // rcx

  v3 = 0;
  if ( !a2 || !a3 )
    return (unsigned int)-2147024809;
  v6 = &CWinInetHelperClass::m_attrInfos;
  v7 = &CWinInetHelperClass::m_attrInfos;
  v8 = 0;
  if ( CWinInetHelperClass::m_attrInfos )
  {
    do
    {
      ++v8;
      v7 += 2;
    }
    while ( *v7 );
  }
  *a2 = 0;
  *a3 = 0;
  if ( !v8 )
    return 0;
  if ( v8 > 0x104 )
    return (unsigned int)-2147024809;
  v10 = 16LL * v8;
  v11 = (struct tagHelperAttributeInfo *)CoTaskMemAlloc(v10);
  v12 = v11;
  if ( v11 )
  {
    for ( i = v11; v10; --v10 )
    {
      LOBYTE(v11->pwszName) = 0;
      v11 = (struct tagHelperAttributeInfo *)((char *)v11 + 1);
    }
    while ( 1 )
    {
      v9 = StringCchCopyWithAlloc(&i->pwszName, 0xFFFFu, *(const unsigned __int16 **)v6);
      if ( v9 < 0 )
        break;
      ++v3;
      i->type = *((_DWORD *)v6 + 2);
      v6 += 2;
      ++i;
      if ( v3 >= v8 )
      {
        *a2 = v8;
        v9 = 0;
        *a3 = v12;
        return (unsigned int)v9;
      }
    }
    if ( v3 )
    {
      for ( j = 0; j < v3; ++j )
      {
        pwszName = v12[j].pwszName;
        if ( pwszName )
          CoTaskMemFree(pwszName);
      }
    }
    CoTaskMemFree(v12);
  }
  else
  {
    return (unsigned int)-2147024882;
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180004c20  push    rbx
0x180004c22  push    rbp
0x180004c23  push    rsi
0x180004c24  push    rdi
0x180004c25  push    r12
0x180004c27  push    r13
0x180004c29  push    r14
0x180004c2b  push    r15
0x180004c2d  sub     rsp, 28h
0x180004c31  xor     esi, esi
0x180004c33  mov     r14, r8
0x180004c36  mov     r12, rdx
0x180004c39  test    rdx, rdx
0x180004c3c  jz      loc_180004D35
0x180004c42  test    r8, r8
0x180004c45  jz      loc_180004D35
0x180004c4b  cmp     cs:?m_attrInfos@CWinInetHelperClass@@0QBUtagHelperAttributeInfo@@B, rsi; tagHelperAttributeInfo const near * const CWinInetHelperClass::m_attrInfos
0x180004c52  lea     r15, ?m_attrInfos@CWinInetHelperClass@@0QBUtagHelperAttributeInfo@@B; tagHelperAttributeInfo const near * const CWinInetHelperClass::m_attrInfos
0x180004c59  mov     rax, r15
0x180004c5c  mov     edi, esi
0x180004c5e  jz      short loc_180004C6B
0x180004c60  inc     edi
0x180004c62  lea     rax, [rax+10h]
0x180004c66  cmp     [rax], rsi
0x180004c69  jnz     short loc_180004C60
0x180004c6b  mov     [rdx], esi
0x180004c6d  mov     [r8], rsi
0x180004c70  test    edi, edi
0x180004c72  jnz     short loc_180004C7B
0x180004c74  mov     ebx, esi
0x180004c76  jmp     loc_180004D3A
0x180004c7b  cmp     edi, 104h
0x180004c81  ja      loc_180004D35
0x180004c87  mov     ebx, edi
0x180004c89  shl     rbx, 4
0x180004c8d  mov     rcx, rbx; cb
0x180004c90  call    cs:__imp_CoTaskMemAlloc
0x180004c97  nop     dword ptr [rax+rax+00h]
0x180004c9c  mov     rbp, rax
0x180004c9f  test    rax, rax
0x180004ca2  jnz     short loc_180004CAE
0x180004ca4  mov     ebx, 8007000Eh
0x180004ca9  jmp     loc_180004D3A
0x180004cae  mov     r13, rbp
0x180004cb1  test    rbx, rbx
0x180004cb4  jz      short loc_180004CC2
0x180004cb6  mov     [rax], sil
0x180004cb9  inc     rax
0x180004cbc  sub     rbx, 1
0x180004cc0  jnz     short loc_180004CB6
0x180004cc2  test    edi, edi
0x180004cc4  jz      short loc_180004CF2
0x180004cc6  mov     r8, [r15]; unsigned __int16 *
0x180004cc9  mov     edx, 0FFFFh; unsigned __int64
0x180004cce  mov     rcx, r13; unsigned __int16 **
0x180004cd1  call    ?StringCchCopyWithAlloc@@YAJPEAPEAG_KPEBG@Z; StringCchCopyWithAlloc(ushort * *,unsigned __int64,ushort const *)
0x180004cd6  mov     ebx, eax
0x180004cd8  test    eax, eax
0x180004cda  js      short loc_180004CFD
0x180004cdc  mov     eax, [r15+8]
0x180004ce0  inc     esi
0x180004ce2  mov     [r13+8], eax
0x180004ce6  add     r15, 10h
0x180004cea  add     r13, 10h
0x180004cee  cmp     esi, edi
0x180004cf0  jb      short loc_180004CC6
0x180004cf2  mov     [r12], edi
0x180004cf6  xor     ebx, ebx
0x180004cf8  mov     [r14], rbp
0x180004cfb  jmp     short loc_180004D3A
0x180004cfd  test    esi, esi
0x180004cff  jz      short loc_180004D24
0x180004d01  xor     edi, edi
0x180004d03  mov     eax, edi
0x180004d05  add     rax, rax
0x180004d08  mov     rcx, [rbp+rax*8+0]; pv
0x180004d0d  test    rcx, rcx
0x180004d10  jz      short loc_180004D1E
0x180004d12  call    cs:__imp_CoTaskMemFree
0x180004d19  nop     dword ptr [rax+rax+00h]
0x180004d1e  inc     edi
0x180004d20  cmp     edi, esi
0x180004d22  jb      short loc_180004D03
0x180004d24  mov     rcx, rbp; pv
0x180004d27  call    cs:__imp_CoTaskMemFree
0x180004d2e  nop     dword ptr [rax+rax+00h]
0x180004d33  jmp     short loc_180004D3A
0x180004d35  mov     ebx, 80070057h
0x180004d3a  mov     eax, ebx
0x180004d3c  add     rsp, 28h
0x180004d40  pop     r15
0x180004d42  pop     r14
0x180004d44  pop     r13
0x180004d46  pop     r12
0x180004d48  pop     rdi
0x180004d49  pop     rsi
0x180004d4a  pop     rbp
0x180004d4b  pop     rbx
0x180004d4c  retn
```
