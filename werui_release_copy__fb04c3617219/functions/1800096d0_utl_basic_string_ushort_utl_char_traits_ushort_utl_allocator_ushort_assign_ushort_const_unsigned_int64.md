# utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)

- ea: `0x1800096d0`
- end: `0x180009774`
- name: `?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z`
- size: `164`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `11`
- callee_count: `6`
- tags: ``

## callers

- `0x180008dfc`
- `0x180008f3c`
- `0x1800096a8`
- `0x18000e18c`
- `0x18000ea8c`
- `0x18000ec8c`
- `0x18000fb24`
- `0x180010df0`
- `0x180011af0`
- `0x180011fa8`
- `0x180012d68`

## callees

- `0x180009408`
- `0x180009530`
- `0x1800096d0`
- `0x18000977c`
- `0x180016c06`
- `0x180016c12`

## pseudocode

```c
char __fastcall utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
        _QWORD *a1,
        const void *a2,
        __int64 a3)
{
  char v6; // bp
  unsigned __int64 v7; // rax
  const void *v8; // rdx
  void **v9; // rcx
  unsigned __int64 v10; // r8
  __int64 v11; // rbx
  _WORD *v12; // rcx
  _WORD *v13; // r15
  void *v15[2]; // [rsp+20h] [rbp-48h] BYREF

  v6 = 1;
  v7 = utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::capacity(
         a1,
         a2);
  if ( v10 > v7 )
  {
    utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_GrowAlloc(
      v9,
      v15,
      v10);
    v13 = v15[0];
    if ( v15[0] )
    {
      memcpy_0(v15[0], a2, 2 * a3);
      v13[a3] = 0;
      utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Reinit(
        a1,
        v15,
        a3);
    }
    else
    {
      return 0;
    }
  }
  else
  {
    v11 = 2 * v10;
    memmove_0(*v9, v8, 2 * v10);
    v12 = (_WORD *)(v11 + *a1);
    a1[1] = v12;
    *v12 = 0;
  }
  return v6;
}

```

## disassembly

```asm
0x1800096d0  push    rbx
0x1800096d2  push    rbp
0x1800096d3  push    rsi
0x1800096d4  push    rdi
0x1800096d5  push    r12
0x1800096d7  push    r14
0x1800096d9  push    r15
0x1800096db  sub     rsp, 30h
0x1800096df  mov     r14, r8
0x1800096e2  mov     r12, rdx
0x1800096e5  mov     rsi, rcx
0x1800096e8  mov     bpl, 1
0x1800096eb  call    ?capacity@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEBA_KXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::capacity(void)
0x1800096f0  cmp     r8, rax
0x1800096f3  ja      short loc_180009715
0x1800096f5  mov     rcx, [rcx]; void *
0x1800096f8  lea     rbx, [r8+r8]
0x1800096fc  mov     r8, rbx; Size
0x1800096ff  call    memmove_0
0x180009704  mov     rcx, [rsi]
0x180009707  add     rcx, rbx
0x18000970a  xor     edi, edi
0x18000970c  mov     [rsi+8], rcx
0x180009710  mov     [rcx], di
0x180009713  jmp     short loc_180009762
0x180009715  lea     rdx, [rsp+68h+var_48]
0x18000971a  call    ?_GrowAlloc@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAA?AU?$pair@PEAG_K@2@_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_GrowAlloc(unsigned __int64)
0x18000971f  mov     r15, [rsp+68h+var_48]
0x180009724  xor     edi, edi
0x180009726  test    r15, r15
0x180009729  jz      short loc_18000975F
0x18000972b  lea     rbx, [r14+r14]
0x18000972f  mov     rdx, r12; Src
0x180009732  mov     r8, rbx; Size
0x180009735  mov     rcx, r15; void *
0x180009738  call    memcpy_0
0x18000973d  movaps  xmm0, xmmword ptr [rsp+68h+var_48]
0x180009742  lea     rdx, [rsp+68h+var_48]
0x180009747  mov     r8, r14
0x18000974a  movdqa  xmmword ptr [rsp+68h+var_48], xmm0
0x180009750  mov     rcx, rsi
0x180009753  mov     [rbx+r15], di
0x180009758  call    ?_Reinit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXU?$pair@PEAG_K@2@_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Reinit(utl::pair<ushort *,unsigned __int64>,unsigned __int64)
0x18000975d  jmp     short loc_180009762
0x18000975f  mov     bpl, dil
0x180009762  mov     al, bpl
0x180009765  add     rsp, 30h
0x180009769  pop     r15
0x18000976b  pop     r14
0x18000976d  pop     r12
0x18000976f  pop     rdi
0x180009770  pop     rsi
0x180009771  pop     rbp
0x180009772  pop     rbx
0x180009773  retn
```
