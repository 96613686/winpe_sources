# _AllocStringWorker<CTCoAllocPolicy>(void *,ulong,ushort const *,unsigned __int64,unsigned __int64,ushort * *)

- ea: `0x18001a3ec`
- end: `0x18001a542`
- name: `??$_AllocStringWorker@VCTCoAllocPolicy@@@@YAJPEAXKPEBG_K2PEAPEAG@Z`
- size: `342`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000fa90`
- `0x18001a320`

## callees

- `0x18001a3ec`
- `0x180035830`
- `0x1800364ac`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001a45d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001a45d`

## pseudocode

```c
__int64 __fastcall _AllocStringWorker<CTCoAllocPolicy>(
        __int64 a1,
        __int64 a2,
        _WORD *a3,
        unsigned __int64 a4,
        __int64 a5,
        _QWORD *a6)
{
  unsigned __int64 v6; // rbx
  unsigned int v9; // edi
  _WORD *v11; // rax
  _WORD *v12; // rdx
  _WORD *v13; // rcx
  __int64 v14; // rax
  unsigned __int64 v15; // r8
  _WORD *v16; // r9
  __int64 v17; // r11
  _WORD *v18; // rcx
  __int64 v19; // r10
  __int64 v20; // rbx
  bool v21; // cf

  v6 = a4 + 1;
  *a6 = 0;
  if ( a4 + 1 < a4 || !is_mul_ok(v6, 2u) )
    return (unsigned int)-2147024362;
  v11 = CoTaskMemAlloc(2 * v6);
  *a6 = v11;
  v12 = v11;
  v9 = v11 == 0 ? 0x8007000E : 0;
  if ( !v11 )
    return v9;
  if ( v6 > 0x7FFFFFFF )
  {
LABEL_22:
    *v11 = 0;
    return v9;
  }
  if ( a4 >= 0x7FFFFFFF )
  {
    if ( !v6 )
      return v9;
    goto LABEL_22;
  }
  v13 = &unk_1800509F8;
  if ( a3 )
    v13 = a3;
  v14 = a4 & -(__int64)(a3 != 0);
  if ( v6 )
  {
    v15 = v6;
    v16 = v12;
    v17 = 0;
    do
    {
      if ( !v14 )
        break;
      if ( !*v13 )
        break;
      *v16++ = *v13++;
      --v14;
      ++v17;
      --v15;
    }
    while ( v15 );
    v18 = v16 - 1;
    v19 = v17 - 1;
    if ( v15 )
    {
      v18 = v16;
      v19 = v17;
    }
    *v18 = 0;
    if ( v15 )
    {
      v21 = v6 == v19;
      v20 = v6 - v19;
      if ( !v21 && v20 != 1 && (unsigned __int64)(2 * v20) > 2 )
        memset_0(&v12[v19 + 1], 0, 2 * v20 - 2);
    }
  }
  return v9;
}

```

## disassembly

```asm
0x18001a3ec  mov     [rsp+arg_0], rbx
0x18001a3f1  mov     [rsp+arg_8], rbp
0x18001a3f6  push    rsi
0x18001a3f7  push    rdi
0x18001a3f8  push    r14
0x18001a3fa  sub     rsp, 30h
0x18001a3fe  mov     rax, cs:__security_cookie
0x18001a405  xor     rax, rsp
0x18001a408  mov     [rsp+48h+var_20], rax
0x18001a40d  mov     rdi, [rsp+48h+arg_28]
0x18001a412  lea     rbx, [r9+1]
0x18001a416  xor     r14d, r14d
0x18001a419  mov     rsi, r9
0x18001a41c  mov     rbp, r8
0x18001a41f  mov     [rdi], r14
0x18001a422  cmp     rbx, r9
0x18001a425  jb      short loc_18001A433
0x18001a427  lea     eax, [r14+2]
0x18001a42b  mul     rbx
0x18001a42e  test    rdx, rdx
0x18001a431  jz      short loc_18001A45A
0x18001a433  mov     edi, 80070216h
0x18001a438  mov     eax, edi
0x18001a43a  mov     rcx, [rsp+48h+var_20]
0x18001a43f  xor     rcx, rsp; StackCookie
0x18001a442  call    __security_check_cookie
0x18001a447  mov     rbx, [rsp+48h+arg_0]
0x18001a44c  mov     rbp, [rsp+48h+arg_8]
0x18001a451  add     rsp, 30h
0x18001a455  pop     r14
0x18001a457  pop     rdi
0x18001a458  pop     rsi
0x18001a459  retn
0x18001a45a  mov     rcx, rax; cb
0x18001a45d  call    cs:__imp_CoTaskMemAlloc
0x18001a463  mov     [rdi], rax
0x18001a466  mov     rcx, rax
0x18001a469  neg     rcx
0x18001a46c  mov     rdx, rax
0x18001a46f  sbb     edi, edi
0x18001a471  not     edi
0x18001a473  and     edi, 8007000Eh
0x18001a479  test    rax, rax
0x18001a47c  jz      short loc_18001A438
0x18001a47e  mov     eax, 7FFFFFFFh
0x18001a483  cmp     rbx, rax
0x18001a486  ja      loc_18001A539
0x18001a48c  cmp     rsi, rax
0x18001a48f  jnb     loc_18001A530
0x18001a495  test    rbp, rbp
0x18001a498  lea     rcx, unk_1800509F8
0x18001a49f  cmovnz  rcx, rbp
0x18001a4a3  neg     rbp
0x18001a4a6  sbb     rax, rax
0x18001a4a9  and     rax, rsi
0x18001a4ac  test    rbx, rbx
0x18001a4af  jz      short loc_18001A438
0x18001a4b1  mov     r8, rbx
0x18001a4b4  mov     r9, rdx
0x18001a4b7  mov     r11, r14
0x18001a4ba  test    rax, rax
0x18001a4bd  jz      short loc_18001A4E1
0x18001a4bf  movzx   r10d, word ptr [rcx]
0x18001a4c3  test    r10w, r10w
0x18001a4c7  jz      short loc_18001A4E1
0x18001a4c9  mov     [r9], r10w
0x18001a4cd  add     rcx, 2
0x18001a4d1  add     r9, 2
0x18001a4d5  dec     rax
0x18001a4d8  inc     r11
0x18001a4db  sub     r8, 1
0x18001a4df  jnz     short loc_18001A4BA
0x18001a4e1  test    r8, r8
0x18001a4e4  lea     rcx, [r9-2]
0x18001a4e8  lea     r10, [r11-1]
0x18001a4ec  cmovnz  rcx, r9
0x18001a4f0  cmovnz  r10, r11
0x18001a4f4  mov     [rcx], r14w
0x18001a4f8  jz      loc_18001A438
0x18001a4fe  sub     rbx, r10
0x18001a501  cmp     rbx, 1
0x18001a505  jbe     loc_18001A438
0x18001a50b  lea     r8, [rbx+rbx]
0x18001a50f  cmp     r8, 2
0x18001a513  jbe     loc_18001A438
0x18001a519  inc     r10
0x18001a51c  add     r8, 0FFFFFFFFFFFFFFFEh; Size
0x18001a520  lea     rcx, [rdx+r10*2]; void *
0x18001a524  xor     edx, edx; Val
0x18001a526  call    memset_0
0x18001a52b  jmp     loc_18001A438
0x18001a530  test    rbx, rbx
0x18001a533  jz      loc_18001A438
0x18001a539  mov     [rdx], r14w
0x18001a53d  jmp     loc_18001A438
```
