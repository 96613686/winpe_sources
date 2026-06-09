# CEventLog::CStrArray::Append(wchar_t const *)

- ea: `0x18000c234`
- end: `0x18000c31b`
- name: `?Append@CStrArray@CEventLog@@QEAAJPEB_W@Z`
- size: `231`
- prototype: `__int64 __fastcall(CEventLog::CStrArray *__hidden this, const wchar_t *)`
- caller_count: `7`
- callee_count: `2`
- tags: ``

## callers

- `0x180007d30`
- `0x180007de0`
- `0x180007e90`
- `0x180008510`
- `0x180008648`
- `0x1800087a8`
- `0x18000890c`

## callees

- `0x180003b7c`
- `0x18000c234`

## pseudocode

```c
__int64 __fastcall CEventLog::CStrArray::Append(CEventLog::CStrArray *this, const wchar_t *a2, __int64 a3, void *a4)
{
  unsigned int v5; // edx
  __int64 v7; // rbx
  unsigned __int64 v8; // rbx
  void *v9; // r8
  __int64 v10; // rcx
  _WORD *v11; // rax
  _WORD *v12; // rcx
  signed int v13; // eax
  void *v15; // [rsp+40h] [rbp+8h] BYREF

  v5 = -2147467259;
  if ( *(_DWORD *)this < 7u )
  {
    v7 = -1;
    do
      ++v7;
    while ( a2[v7] );
    v8 = v7 + 1;
    v15 = 0;
    if ( !is_mul_ok(v8, 2u) || (int)ProfNotif_HeapAlloc(2 * v8, (v8 * (unsigned __int128)2uLL) >> 64, &v15, a4) < 0 )
      return (unsigned int)-2147024882;
    v9 = v15;
    v5 = -2147024809;
    if ( v8 )
    {
      if ( v8 > 0x7FFFFFFF )
      {
        *(_WORD *)v15 = 0;
        return v5;
      }
      v10 = 2147483646;
      v11 = v15;
      do
      {
        if ( !v10 )
          break;
        if ( !*a2 )
          break;
        *v11++ = *a2++;
        --v10;
        --v8;
      }
      while ( v8 );
      v12 = v11 - 1;
      if ( v8 )
        v12 = v11;
      v13 = v8 == 0 ? 0x8007007A : 0;
      *v12 = 0;
    }
    else
    {
      v13 = -2147024809;
    }
    v5 = v13;
    if ( v13 >= 0 )
      *((_QWORD *)this + ++*(_DWORD *)this) = v9;
  }
  return v5;
}

```

## disassembly

```asm
0x18000c234  mov     [rsp+arg_8], rbx
0x18000c239  push    rbp
0x18000c23a  push    rsi
0x18000c23b  push    rdi
0x18000c23c  sub     rsp, 20h
0x18000c240  cmp     dword ptr [rcx], 7
0x18000c243  mov     rsi, rdx
0x18000c246  mov     edx, 80004005h; int
0x18000c24b  mov     rdi, rcx
0x18000c24e  jnb     loc_18000C30C
0x18000c254  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000c258  xor     ebp, ebp
0x18000c25a  inc     rbx
0x18000c25d  cmp     [rsi+rbx*2], bp
0x18000c261  jnz     short loc_18000C25A
0x18000c263  inc     rbx
0x18000c266  mov     [rsp+38h+arg_0], rbp
0x18000c26b  mov     eax, 2
0x18000c270  mul     rbx
0x18000c273  test    rdx, rdx
0x18000c276  jnz     loc_18000C307
0x18000c27c  lea     r8, [rsp+38h+arg_0]; void **
0x18000c281  mov     rcx, rax; dwBytes
0x18000c284  call    ?ProfNotif_HeapAlloc@@YAJ_KHPEAPEAXPEAX@Z; ProfNotif_HeapAlloc(unsigned __int64,int,void * *,void *)
0x18000c289  test    eax, eax
0x18000c28b  js      short loc_18000C307
0x18000c28d  mov     r8, [rsp+38h+arg_0]
0x18000c292  mov     edx, 80070057h
0x18000c297  test    rbx, rbx
0x18000c29a  jz      short loc_18000C2FA
0x18000c29c  cmp     rbx, 7FFFFFFFh
0x18000c2a3  ja      short loc_18000C301
0x18000c2a5  mov     ecx, 7FFFFFFEh
0x18000c2aa  mov     rax, r8
0x18000c2ad  test    rcx, rcx
0x18000c2b0  jz      short loc_18000C2CE
0x18000c2b2  movzx   edx, word ptr [rsi]
0x18000c2b5  test    dx, dx
0x18000c2b8  jz      short loc_18000C2CE
0x18000c2ba  mov     [rax], dx
0x18000c2bd  add     rsi, 2
0x18000c2c1  add     rax, 2
0x18000c2c5  dec     rcx
0x18000c2c8  sub     rbx, 1
0x18000c2cc  jnz     short loc_18000C2AD
0x18000c2ce  lea     rcx, [rax-2]
0x18000c2d2  test    rbx, rbx
0x18000c2d5  cmovnz  rcx, rax
0x18000c2d9  neg     rbx
0x18000c2dc  sbb     eax, eax
0x18000c2de  not     eax
0x18000c2e0  and     eax, 8007007Ah
0x18000c2e5  mov     [rcx], bp
0x18000c2e8  mov     edx, eax
0x18000c2ea  test    eax, eax
0x18000c2ec  js      short loc_18000C30C
0x18000c2ee  movsxd  rax, dword ptr [rdi]
0x18000c2f1  mov     [rdi+rax*8+8], r8
0x18000c2f6  inc     dword ptr [rdi]
0x18000c2f8  jmp     short loc_18000C30C
0x18000c2fa  mov     eax, edx
0x18000c2fc  test    rbx, rbx
0x18000c2ff  jz      short loc_18000C2E8
0x18000c301  mov     [r8], bp
0x18000c305  jmp     short loc_18000C30C
0x18000c307  mov     edx, 8007000Eh
0x18000c30c  mov     rbx, [rsp+38h+arg_8]
0x18000c311  mov     eax, edx
0x18000c313  add     rsp, 20h
0x18000c317  pop     rdi
0x18000c318  pop     rsi
0x18000c319  pop     rbp
0x18000c31a  retn
```
