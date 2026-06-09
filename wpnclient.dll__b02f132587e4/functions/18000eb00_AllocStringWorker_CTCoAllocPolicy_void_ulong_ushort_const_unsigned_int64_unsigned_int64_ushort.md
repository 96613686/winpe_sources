# _AllocStringWorker<CTCoAllocPolicy>(void *,ulong,ushort const *,unsigned __int64,unsigned __int64,ushort * *)

- ea: `0x18000eb00`
- end: `0x18000ec3b`
- name: `??$_AllocStringWorker@VCTCoAllocPolicy@@@@YAJPEAXKPEBG_K2PEAPEAG@Z`
- size: `315`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000e93c`

## callees

- `0x18000eb00`
- `0x180020d34`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000eb43`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000eb43`

## pseudocode

```c
__int64 __fastcall _AllocStringWorker<CTCoAllocPolicy>(
        __int64 a1,
        __int64 a2,
        const OLECHAR *a3,
        unsigned __int64 a4,
        __int64 a5,
        _QWORD *a6)
{
  unsigned __int64 v6; // r14
  _WORD *v9; // rax
  unsigned int v10; // edi
  _WORD *v11; // r11
  const OLECHAR *v12; // rdx
  unsigned __int64 v13; // rax
  unsigned __int64 v14; // r8
  _WORD *v15; // r9
  __int64 v16; // r10
  _WORD *v17; // rcx
  __int64 v18; // rdx
  __int64 v19; // r14
  bool v20; // cf

  v6 = a4 + 1;
  *a6 = 0;
  if ( a4 + 1 < a4 || !is_mul_ok(v6, 2u) )
    return (unsigned int)-2147024362;
  v9 = CoTaskMemAlloc(2 * v6);
  *a6 = v9;
  v10 = -2147024882;
  v11 = v9;
  if ( v9 )
    v10 = 0;
  if ( (v10 & 0x80000000) == 0 )
  {
    if ( (v9 || !v6) && v6 <= 0x7FFFFFFF )
    {
      if ( a4 < 0x7FFFFFFF )
      {
        v12 = &pwzBaseUrl;
        v13 = 0;
        if ( a3 )
        {
          v12 = a3;
          v13 = a4;
        }
        if ( v6 )
        {
          v14 = v6;
          v15 = v11;
          v16 = 0;
          do
          {
            if ( !v13 )
              break;
            if ( !*v12 )
              break;
            *v15++ = *v12++;
            --v13;
            ++v16;
            --v14;
          }
          while ( v14 );
          v17 = v15 - 1;
          v18 = v16 - 1;
          if ( v14 )
          {
            v17 = v15;
            v18 = v16;
          }
          *v17 = 0;
          if ( v14 )
          {
            v20 = v6 == v18;
            v19 = v6 - v18;
            if ( !v20 && v19 != 1 && (unsigned __int64)(2 * v19) > 2 )
              memset_0(&v11[v18 + 1], 0, 2 * v19 - 2);
          }
        }
        return v10;
      }
      if ( !v6 )
        return v10;
    }
    *v9 = 0;
  }
  return v10;
}

```

## disassembly

```asm
0x18000eb00  mov     [rsp+arg_8], rbx
0x18000eb05  mov     [rsp+arg_10], rbp
0x18000eb0a  push    rsi
0x18000eb0b  push    rdi
0x18000eb0c  push    r14
0x18000eb0e  sub     rsp, 20h
0x18000eb12  mov     rdi, [rsp+38h+arg_28]
0x18000eb17  lea     r14, [r9+1]
0x18000eb1b  xor     ebp, ebp
0x18000eb1d  mov     rbx, r9
0x18000eb20  mov     rsi, r8
0x18000eb23  mov     [rdi], rbp
0x18000eb26  cmp     r14, r9
0x18000eb29  jb      loc_18000EC0D
0x18000eb2f  mov     eax, 2
0x18000eb34  mul     r14
0x18000eb37  test    rdx, rdx
0x18000eb3a  jnz     loc_18000EC0D
0x18000eb40  mov     rcx, rax; cb
0x18000eb43  call    cs:__imp_CoTaskMemAlloc
0x18000eb49  mov     [rdi], rax
0x18000eb4c  test    rax, rax
0x18000eb4f  mov     edi, 8007000Eh
0x18000eb54  mov     r11, rax
0x18000eb57  cmovnz  edi, ebp
0x18000eb5a  test    edi, edi
0x18000eb5c  js      loc_18000EC12
0x18000eb62  test    rax, rax
0x18000eb65  jz      loc_18000EC31
0x18000eb6b  cmp     r14, 7FFFFFFFh
0x18000eb72  ja      loc_18000EC2C
0x18000eb78  cmp     rbx, 7FFFFFFFh
0x18000eb7f  jnb     loc_18000EC27
0x18000eb85  test    rsi, rsi
0x18000eb88  lea     rdx, pwzBaseUrl
0x18000eb8f  mov     rax, rbp
0x18000eb92  cmovnz  rdx, rsi
0x18000eb96  cmovnz  rax, rbx
0x18000eb9a  test    r14, r14
0x18000eb9d  jz      short loc_18000EC12
0x18000eb9f  mov     r8, r14
0x18000eba2  mov     r9, r11
0x18000eba5  mov     r10, rbp
0x18000eba8  test    rax, rax
0x18000ebab  jz      short loc_18000EBCD
0x18000ebad  movzx   ecx, word ptr [rdx]
0x18000ebb0  test    cx, cx
0x18000ebb3  jz      short loc_18000EBCD
0x18000ebb5  mov     [r9], cx
0x18000ebb9  add     rdx, 2
0x18000ebbd  add     r9, 2
0x18000ebc1  dec     rax
0x18000ebc4  inc     r10
0x18000ebc7  sub     r8, 1
0x18000ebcb  jnz     short loc_18000EBA8
0x18000ebcd  test    r8, r8
0x18000ebd0  lea     rcx, [r9-2]
0x18000ebd4  lea     rdx, [r10-1]
0x18000ebd8  cmovnz  rcx, r9
0x18000ebdc  cmovnz  rdx, r10
0x18000ebe0  mov     [rcx], bp
0x18000ebe3  jz      short loc_18000EC12
0x18000ebe5  sub     r14, rdx
0x18000ebe8  cmp     r14, 1
0x18000ebec  jbe     short loc_18000EC12
0x18000ebee  lea     r8, [r14+r14]
0x18000ebf2  cmp     r8, 2
0x18000ebf6  jbe     short loc_18000EC12
0x18000ebf8  lea     rcx, [r11+2]
0x18000ebfc  add     r8, 0FFFFFFFFFFFFFFFEh; Size
0x18000ec00  lea     rcx, [rcx+rdx*2]; void *
0x18000ec04  xor     edx, edx; Val
0x18000ec06  call    memset_0
0x18000ec0b  jmp     short loc_18000EC12
0x18000ec0d  mov     edi, 80070216h
0x18000ec12  mov     rbx, [rsp+38h+arg_8]
0x18000ec17  mov     eax, edi
0x18000ec19  mov     rbp, [rsp+38h+arg_10]
0x18000ec1e  add     rsp, 20h
0x18000ec22  pop     r14
0x18000ec24  pop     rdi
0x18000ec25  pop     rsi
0x18000ec26  retn
0x18000ec27  test    r14, r14
0x18000ec2a  jz      short loc_18000EC12
0x18000ec2c  mov     [rax], bp
0x18000ec2f  jmp     short loc_18000EC12
0x18000ec31  test    r14, r14
0x18000ec34  jnz     short loc_18000EC2C
0x18000ec36  jmp     loc_18000EB6B
```
