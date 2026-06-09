# ResolveWinSound(ushort const *,ushort * *)

- ea: `0x18000e93c`
- end: `0x18000eaa8`
- name: `?ResolveWinSound@@YAJPEBGPEAPEAG@Z`
- size: `364`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000e4c0`

## callees

- `0x18000e93c`
- `0x18000eb00`
- `0x180020d34`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18000e959`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18000e959`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000e99e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000e99e`

## pseudocode

```c
__int64 __fastcall ResolveWinSound(const unsigned __int16 *a1, unsigned __int16 **a2)
{
  wchar_t *v4; // rax
  int v5; // edx
  int v6; // ecx
  unsigned __int64 v7; // rsi
  unsigned __int64 v8; // rdi
  unsigned __int16 *v9; // rax
  unsigned __int16 *v10; // rdx
  unsigned int v11; // ebx
  const OLECHAR *v12; // rax
  __int64 v13; // rcx
  unsigned __int64 v14; // r8
  unsigned __int16 *v15; // r9
  __int64 v16; // r11
  unsigned __int16 *v17; // rcx
  __int64 v18; // r10
  __int64 v19; // rdi
  bool v20; // cf

  v4 = wcsrchr(a1, 0x3Fu);
  if ( v4 )
    return (unsigned int)_AllocStringWorker<CTCoAllocPolicy>(v6, v5, (_DWORD)a1, v4 - a1);
  v7 = -1;
  do
    ++v7;
  while ( a1[v7] );
  v8 = v7 + 1;
  *a2 = 0;
  if ( v7 + 1 < v7 || !is_mul_ok(v8, 2u) )
    return (unsigned int)-2147024362;
  v9 = (unsigned __int16 *)CoTaskMemAlloc(2 * v8);
  *a2 = v9;
  v10 = v9;
  v11 = v9 == 0 ? 0x8007000E : 0;
  if ( v9 )
  {
    if ( v8 <= 0x7FFFFFFF )
    {
      if ( v7 < 0x7FFFFFFF )
      {
        v12 = &pwzBaseUrl;
        v13 = v7 & -(__int64)(a1 != 0);
        if ( a1 )
          v12 = a1;
        v14 = v7 + 1;
        v15 = v10;
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
          v20 = v8 == v18;
          v19 = v8 - v18;
          if ( !v20 && v19 != 1 && (unsigned __int64)(2 * v19) > 2 )
            memset_0(&v10[v18 + 1], 0, 2 * v19 - 2);
        }
        return v11;
      }
      if ( v7 == -1 )
        return v11;
    }
    *v9 = 0;
  }
  return v11;
}

```

## disassembly

```asm
0x18000e93c  mov     [rsp+arg_0], rbx
0x18000e941  mov     [rsp+arg_8], rbp
0x18000e946  push    rsi
0x18000e947  push    rdi
0x18000e948  push    r14
0x18000e94a  sub     rsp, 30h
0x18000e94e  mov     rbx, rdx
0x18000e951  mov     rbp, rcx
0x18000e954  mov     edx, 3Fh ; '?'; Ch
0x18000e959  call    cs:__imp_wcsrchr
0x18000e95f  xor     r14d, r14d
0x18000e962  test    rax, rax
0x18000e965  jnz     loc_18000EA8E
0x18000e96b  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18000e96f  inc     rsi
0x18000e972  cmp     [rbp+rsi*2+0], r14w
0x18000e978  jnz     short loc_18000E96F
0x18000e97a  lea     rdi, [rsi+1]
0x18000e97e  mov     [rbx], r14
0x18000e981  cmp     rdi, rsi
0x18000e984  jb      loc_18000EA69
0x18000e98a  mov     eax, 2
0x18000e98f  mul     rdi
0x18000e992  test    rdx, rdx
0x18000e995  jnz     loc_18000EA69
0x18000e99b  mov     rcx, rax; cb
0x18000e99e  call    cs:__imp_CoTaskMemAlloc
0x18000e9a4  mov     [rbx], rax
0x18000e9a7  mov     rcx, rax
0x18000e9aa  neg     rcx
0x18000e9ad  mov     rdx, rax
0x18000e9b0  sbb     ebx, ebx
0x18000e9b2  not     ebx
0x18000e9b4  and     ebx, 8007000Eh
0x18000e9ba  test    rax, rax
0x18000e9bd  jz      loc_18000EA6E
0x18000e9c3  mov     eax, 7FFFFFFFh
0x18000e9c8  cmp     rdi, rax
0x18000e9cb  ja      loc_18000EA88
0x18000e9d1  cmp     rsi, rax
0x18000e9d4  jnb     loc_18000EA83
0x18000e9da  mov     rax, rbp
0x18000e9dd  neg     rax
0x18000e9e0  lea     rax, pwzBaseUrl
0x18000e9e7  sbb     rcx, rcx
0x18000e9ea  and     rcx, rsi
0x18000e9ed  test    rbp, rbp
0x18000e9f0  cmovnz  rax, rbp
0x18000e9f4  test    rdi, rdi
0x18000e9f7  jz      short loc_18000EA6E
0x18000e9f9  mov     r8, rdi
0x18000e9fc  mov     r9, rdx
0x18000e9ff  mov     r11, r14
0x18000ea02  test    rcx, rcx
0x18000ea05  jz      short loc_18000EA29
0x18000ea07  movzx   r10d, word ptr [rax]
0x18000ea0b  test    r10w, r10w
0x18000ea0f  jz      short loc_18000EA29
0x18000ea11  mov     [r9], r10w
0x18000ea15  add     rax, 2
0x18000ea19  add     r9, 2
0x18000ea1d  dec     rcx
0x18000ea20  inc     r11
0x18000ea23  sub     r8, 1
0x18000ea27  jnz     short loc_18000EA02
0x18000ea29  test    r8, r8
0x18000ea2c  lea     rcx, [r9-2]
0x18000ea30  lea     r10, [r11-1]
0x18000ea34  cmovnz  rcx, r9
0x18000ea38  cmovnz  r10, r11
0x18000ea3c  mov     [rcx], r14w
0x18000ea40  jz      short loc_18000EA6E
0x18000ea42  sub     rdi, r10
0x18000ea45  cmp     rdi, 1
0x18000ea49  jbe     short loc_18000EA6E
0x18000ea4b  lea     r8, [rdi+rdi]
0x18000ea4f  cmp     r8, 2
0x18000ea53  jbe     short loc_18000EA6E
0x18000ea55  inc     r10
0x18000ea58  add     r8, 0FFFFFFFFFFFFFFFEh; Size
0x18000ea5c  lea     rcx, [rdx+r10*2]; void *
0x18000ea60  xor     edx, edx; Val
0x18000ea62  call    memset_0
0x18000ea67  jmp     short loc_18000EA6E
0x18000ea69  mov     ebx, 80070216h
0x18000ea6e  mov     rbp, [rsp+48h+arg_8]
0x18000ea73  mov     eax, ebx
0x18000ea75  mov     rbx, [rsp+48h+arg_0]
0x18000ea7a  add     rsp, 30h
0x18000ea7e  pop     r14
0x18000ea80  pop     rdi
0x18000ea81  pop     rsi
0x18000ea82  retn
0x18000ea83  test    rdi, rdi
0x18000ea86  jz      short loc_18000EA6E
0x18000ea88  mov     [rdx], r14w
0x18000ea8c  jmp     short loc_18000EA6E
0x18000ea8e  sub     rax, rbp
0x18000ea91  mov     [rsp+48h+var_20], rbx
0x18000ea96  sar     rax, 1
0x18000ea99  mov     r8, rbp
0x18000ea9c  mov     r9, rax
0x18000ea9f  call    ??$_AllocStringWorker@VCTCoAllocPolicy@@@@YAJPEAXKPEBG_K2PEAPEAG@Z; _AllocStringWorker<CTCoAllocPolicy>(void *,ulong,ushort const *,unsigned __int64,unsigned __int64,ushort * *)
0x18000eaa4  mov     ebx, eax
0x18000eaa6  jmp     short loc_18000EA6E
```
