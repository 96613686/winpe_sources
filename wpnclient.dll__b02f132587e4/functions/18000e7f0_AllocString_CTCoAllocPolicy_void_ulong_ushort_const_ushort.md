# _AllocString<CTCoAllocPolicy>(void *,ulong,ushort const *,ushort * *)

- ea: `0x18000e7f0`
- end: `0x18000e935`
- name: `??$_AllocString@VCTCoAllocPolicy@@@@YAJPEAXKPEBGPEAPEAG@Z`
- size: `325`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000bbf0`
- `0x18000e4c0`
- `0x18001ecb0`
- `0x18002e100`

## callees

- `0x18000e7f0`
- `0x180020d34`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000e841`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000e841`

## pseudocode

```c
__int64 __fastcall _AllocString<CTCoAllocPolicy>(__int64 a1, __int64 a2, const OLECHAR *a3, _QWORD *a4)
{
  unsigned __int64 v6; // rbx
  unsigned __int64 v7; // r14
  _WORD *v8; // rax
  unsigned int v9; // esi
  const OLECHAR *v10; // rcx
  unsigned __int64 v11; // rdx
  _WORD *v12; // r8
  __int64 v13; // r9
  _WORD *v14; // rcx
  __int64 v15; // r10
  __int64 v16; // r14
  bool v17; // cf

  v6 = -1;
  do
    ++v6;
  while ( a3[v6] );
  v7 = v6 + 1;
  *a4 = 0;
  if ( v6 + 1 < v6 || !is_mul_ok(v7, 2u) )
    return (unsigned int)-2147024362;
  v8 = CoTaskMemAlloc(2 * v7);
  *a4 = v8;
  v9 = -2147024882;
  if ( v8 )
    v9 = 0;
  if ( (v9 & 0x80000000) == 0 )
  {
    if ( (v8 || v6 == -1) && v7 <= 0x7FFFFFFF )
    {
      if ( v6 < 0x7FFFFFFF )
      {
        v10 = &pwzBaseUrl;
        if ( a3 )
          v10 = a3;
        else
          v6 = 0;
        if ( v7 )
        {
          v11 = v7;
          v12 = v8;
          v13 = 0;
          do
          {
            if ( !v6 )
              break;
            if ( !*v10 )
              break;
            *v12++ = *v10++;
            --v6;
            ++v13;
            --v11;
          }
          while ( v11 );
          v14 = v12 - 1;
          v15 = v13 - 1;
          if ( v11 )
          {
            v14 = v12;
            v15 = v13;
          }
          *v14 = 0;
          if ( v11 )
          {
            v17 = v7 == v15;
            v16 = v7 - v15;
            if ( !v17 && v16 != 1 && (unsigned __int64)(2 * v16) > 2 )
              memset_0(&v8[v15 + 1], 0, 2 * v16 - 2);
          }
        }
        return v9;
      }
      if ( v6 == -1 )
        return v9;
    }
    *v8 = 0;
  }
  return v9;
}

```

## disassembly

```asm
0x18000e7f0  mov     [rsp+arg_8], rbx
0x18000e7f5  mov     [rsp+arg_10], rbp
0x18000e7fa  push    rsi
0x18000e7fb  push    rdi
0x18000e7fc  push    r14
0x18000e7fe  sub     rsp, 20h
0x18000e802  mov     rsi, r9
0x18000e805  mov     rdi, r8
0x18000e808  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x18000e80f  nop
0x18000e810  inc     rbx
0x18000e813  cmp     word ptr [r8+rbx*2], 0
0x18000e819  jnz     short loc_18000E810
0x18000e81b  xor     ebp, ebp
0x18000e81d  lea     r14, [rbx+1]
0x18000e821  mov     [r9], rbp
0x18000e824  cmp     r14, rbx
0x18000e827  jb      loc_18000E907
0x18000e82d  mov     eax, 2
0x18000e832  mul     r14
0x18000e835  test    rdx, rdx
0x18000e838  jnz     loc_18000E907
0x18000e83e  mov     rcx, rax; cb
0x18000e841  call    cs:__imp_CoTaskMemAlloc
0x18000e847  mov     [rsi], rax
0x18000e84a  test    rax, rax
0x18000e84d  mov     esi, 8007000Eh
0x18000e852  mov     r11, rax
0x18000e855  cmovnz  esi, ebp
0x18000e858  test    esi, esi
0x18000e85a  js      loc_18000E90C
0x18000e860  test    rax, rax
0x18000e863  jz      loc_18000E92B
0x18000e869  cmp     r14, 7FFFFFFFh
0x18000e870  ja      loc_18000E926
0x18000e876  cmp     rbx, 7FFFFFFFh
0x18000e87d  jnb     loc_18000E921
0x18000e883  test    rdi, rdi
0x18000e886  lea     rcx, pwzBaseUrl
0x18000e88d  cmovz   rbx, rbp
0x18000e891  cmovnz  rcx, rdi
0x18000e895  test    r14, r14
0x18000e898  jz      short loc_18000E90C
0x18000e89a  mov     rdx, r14
0x18000e89d  mov     r8, r11
0x18000e8a0  mov     r9, rbp
0x18000e8a3  test    rbx, rbx
0x18000e8a6  jz      short loc_18000E8C8
0x18000e8a8  movzx   eax, word ptr [rcx]
0x18000e8ab  test    ax, ax
0x18000e8ae  jz      short loc_18000E8C8
0x18000e8b0  mov     [r8], ax
0x18000e8b4  add     rcx, 2
0x18000e8b8  add     r8, 2
0x18000e8bc  dec     rbx
0x18000e8bf  inc     r9
0x18000e8c2  sub     rdx, 1
0x18000e8c6  jnz     short loc_18000E8A3
0x18000e8c8  test    rdx, rdx
0x18000e8cb  lea     rcx, [r8-2]
0x18000e8cf  lea     r10, [r9-1]
0x18000e8d3  cmovnz  rcx, r8
0x18000e8d7  cmovnz  r10, r9
0x18000e8db  mov     [rcx], bp
0x18000e8de  jz      short loc_18000E90C
0x18000e8e0  sub     r14, r10
0x18000e8e3  cmp     r14, 1
0x18000e8e7  jbe     short loc_18000E90C
0x18000e8e9  lea     r8, [r14+r14]
0x18000e8ed  cmp     r8, 2
0x18000e8f1  jbe     short loc_18000E90C
0x18000e8f3  inc     r10
0x18000e8f6  add     r8, 0FFFFFFFFFFFFFFFEh; Size
0x18000e8fa  xor     edx, edx; Val
0x18000e8fc  lea     rcx, [r11+r10*2]; void *
0x18000e900  call    memset_0
0x18000e905  jmp     short loc_18000E90C
0x18000e907  mov     esi, 80070216h
0x18000e90c  mov     rbx, [rsp+38h+arg_8]
0x18000e911  mov     eax, esi
0x18000e913  mov     rbp, [rsp+38h+arg_10]
0x18000e918  add     rsp, 20h
0x18000e91c  pop     r14
0x18000e91e  pop     rdi
0x18000e91f  pop     rsi
0x18000e920  retn
0x18000e921  test    r14, r14
0x18000e924  jz      short loc_18000E90C
0x18000e926  mov     [rax], bp
0x18000e929  jmp     short loc_18000E90C
0x18000e92b  test    r14, r14
0x18000e92e  jnz     short loc_18000E926
0x18000e930  jmp     loc_18000E869
```
