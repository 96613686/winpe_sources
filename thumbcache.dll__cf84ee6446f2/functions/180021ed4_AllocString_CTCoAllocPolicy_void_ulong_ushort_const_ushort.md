# _AllocString<CTCoAllocPolicy>(void *,ulong,ushort const *,ushort * *)

- ea: `0x180021ed4`
- end: `0x180022037`
- name: `??$_AllocString@VCTCoAllocPolicy@@@@YAJPEAXKPEBGPEAPEAG@Z`
- size: `355`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180021e40`
- `0x1800225f0`

## callees

- `0x180021ed4`
- `0x180035830`
- `0x1800364ac`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180021f4f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180021f4f`

## pseudocode

```c
__int64 __fastcall _AllocString<CTCoAllocPolicy>(__int64 a1, __int64 a2, __int64 *a3, _QWORD *a4)
{
  unsigned __int64 v4; // rsi
  unsigned __int64 v7; // rbx
  unsigned int v8; // edi
  _WORD *v10; // rax
  _WORD *v11; // rdx
  __int64 *v12; // rax
  __int64 v13; // rcx
  unsigned __int64 v14; // r8
  _WORD *v15; // r9
  __int64 v16; // r11
  _WORD *v17; // rcx
  __int64 v18; // r10
  __int64 v19; // rbx
  bool v20; // cf

  v4 = -1;
  do
    ++v4;
  while ( *((_WORD *)a3 + v4) );
  v7 = v4 + 1;
  *a4 = 0;
  if ( v4 + 1 < v4 || !is_mul_ok(v7, 2u) )
    return (unsigned int)-2147024362;
  v10 = CoTaskMemAlloc(2 * v7);
  *a4 = v10;
  v11 = v10;
  v8 = v10 == 0 ? 0x8007000E : 0;
  if ( !v10 )
    return v8;
  if ( v7 > 0x7FFFFFFF )
  {
LABEL_23:
    *v10 = 0;
    return v8;
  }
  if ( v4 >= 0x7FFFFFFF )
  {
    if ( v4 == -1 )
      return v8;
    goto LABEL_23;
  }
  v12 = &qword_1800509F8;
  v13 = v4 & -(__int64)(a3 != 0);
  if ( a3 )
    v12 = a3;
  v14 = v4 + 1;
  v15 = v11;
  v16 = 0;
  do
  {
    if ( !v13 )
      break;
    if ( !*(_WORD *)v12 )
      break;
    *v15 = *(_WORD *)v12;
    v12 = (__int64 *)((char *)v12 + 2);
    ++v15;
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
    v20 = v7 == v18;
    v19 = v7 - v18;
    if ( !v20 && v19 != 1 && (unsigned __int64)(2 * v19) > 2 )
      memset_0(&v11[v18 + 1], 0, 2 * v19 - 2);
  }
  return v8;
}

```

## disassembly

```asm
0x180021ed4  mov     [rsp+arg_0], rbx
0x180021ed9  mov     [rsp+arg_8], rbp
0x180021ede  push    rsi
0x180021edf  push    rdi
0x180021ee0  push    r14
0x180021ee2  sub     rsp, 30h
0x180021ee6  mov     rax, cs:__security_cookie
0x180021eed  xor     rax, rsp
0x180021ef0  mov     [rsp+48h+var_20], rax
0x180021ef5  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180021ef9  mov     rdi, r9
0x180021efc  xor     r14d, r14d
0x180021eff  mov     rbp, r8
0x180021f02  inc     rsi
0x180021f05  cmp     [r8+rsi*2], r14w
0x180021f0a  jnz     short loc_180021F02
0x180021f0c  lea     rbx, [rsi+1]
0x180021f10  mov     [r9], r14
0x180021f13  cmp     rbx, rsi
0x180021f16  jb      short loc_180021F25
0x180021f18  mov     eax, 2
0x180021f1d  mul     rbx
0x180021f20  test    rdx, rdx
0x180021f23  jz      short loc_180021F4C
0x180021f25  mov     edi, 80070216h
0x180021f2a  mov     eax, edi
0x180021f2c  mov     rcx, [rsp+48h+var_20]
0x180021f31  xor     rcx, rsp; StackCookie
0x180021f34  call    __security_check_cookie
0x180021f39  mov     rbx, [rsp+48h+arg_0]
0x180021f3e  mov     rbp, [rsp+48h+arg_8]
0x180021f43  add     rsp, 30h
0x180021f47  pop     r14
0x180021f49  pop     rdi
0x180021f4a  pop     rsi
0x180021f4b  retn
0x180021f4c  mov     rcx, rax; cb
0x180021f4f  call    cs:__imp_CoTaskMemAlloc
0x180021f55  mov     [rdi], rax
0x180021f58  mov     rcx, rax
0x180021f5b  neg     rcx
0x180021f5e  mov     rdx, rax
0x180021f61  sbb     edi, edi
0x180021f63  not     edi
0x180021f65  and     edi, 8007000Eh
0x180021f6b  test    rax, rax
0x180021f6e  jz      short loc_180021F2A
0x180021f70  mov     eax, 7FFFFFFFh
0x180021f75  cmp     rbx, rax
0x180021f78  ja      loc_18002202E
0x180021f7e  cmp     rsi, rax
0x180021f81  jnb     loc_180022025
0x180021f87  mov     rax, rbp
0x180021f8a  neg     rax
0x180021f8d  lea     rax, qword_1800509F8
0x180021f94  sbb     rcx, rcx
0x180021f97  and     rcx, rsi
0x180021f9a  test    rbp, rbp
0x180021f9d  cmovnz  rax, rbp
0x180021fa1  test    rbx, rbx
0x180021fa4  jz      short loc_180021F2A
0x180021fa6  mov     r8, rbx
0x180021fa9  mov     r9, rdx
0x180021fac  mov     r11, r14
0x180021faf  test    rcx, rcx
0x180021fb2  jz      short loc_180021FD6
0x180021fb4  movzx   r10d, word ptr [rax]
0x180021fb8  test    r10w, r10w
0x180021fbc  jz      short loc_180021FD6
0x180021fbe  mov     [r9], r10w
0x180021fc2  add     rax, 2
0x180021fc6  add     r9, 2
0x180021fca  dec     rcx
0x180021fcd  inc     r11
0x180021fd0  sub     r8, 1
0x180021fd4  jnz     short loc_180021FAF
0x180021fd6  test    r8, r8
0x180021fd9  lea     rcx, [r9-2]
0x180021fdd  lea     r10, [r11-1]
0x180021fe1  cmovnz  rcx, r9
0x180021fe5  cmovnz  r10, r11
0x180021fe9  mov     [rcx], r14w
0x180021fed  jz      loc_180021F2A
0x180021ff3  sub     rbx, r10
0x180021ff6  cmp     rbx, 1
0x180021ffa  jbe     loc_180021F2A
0x180022000  lea     r8, [rbx+rbx]
0x180022004  cmp     r8, 2
0x180022008  jbe     loc_180021F2A
0x18002200e  inc     r10
0x180022011  add     r8, 0FFFFFFFFFFFFFFFEh; Size
0x180022015  lea     rcx, [rdx+r10*2]; void *
0x180022019  xor     edx, edx; Val
0x18002201b  call    memset_0
0x180022020  jmp     loc_180021F2A
0x180022025  test    rbx, rbx
0x180022028  jz      loc_180021F2A
0x18002202e  mov     [rdx], r14w
0x180022032  jmp     loc_180021F2A
```
