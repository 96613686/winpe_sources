# _mbtowc_internal

- ea: `0x10041f2d8`
- end: `0x10041f450`
- name: `_mbtowc_internal`
- size: `376`
- prototype: `__int64 __fastcall(__crt_mbstring *this, wchar_t *, char *, __crt_cached_ptd_host *)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x100420f38`

## callees

- `0x10041b270`
- `0x10041dc1c`
- `0x10041f2d8`
- `0x100421cec`

## pseudocode

```c
unsigned __int64 __fastcall mbtowc_internal(__crt_mbstring *this, wchar_t *a2, char *a3, __crt_cached_ptd_host *a4)
{
  __int64 v8; // rdx
  unsigned int v9; // r10d
  unsigned __int64 result; // rax
  int v11; // r9d
  struct __crt_cached_ptd_host *v12; // [rsp+28h] [rbp-10h]

  if ( !a2 || !a3 )
  {
    qword_100435E50 = 0;
    return 0;
  }
  if ( !*(_BYTE *)a2 )
  {
    if ( this )
      *(_WORD *)this = 0;
    return 0;
  }
  if ( !*((_BYTE *)a4 + 40) )
    __crt_cached_ptd_host::update_locale_slow(a4);
  v8 = *((_QWORD *)a4 + 3);
  v9 = *(_DWORD *)(v8 + 12);
  if ( v9 != 65001 )
  {
    if ( !*(_QWORD *)(v8 + 312) )
    {
      if ( this )
        *(_WORD *)this = *(unsigned __int8 *)a2;
      return 1;
    }
    if ( *(__int16 *)(*(_QWORD *)v8 + 2LL * *(unsigned __int8 *)a2) >= 0 )
    {
      if ( (unsigned int)_acrt_MultiByteToWideChar(v9, 9, a2) )
        return 1;
    }
    else
    {
      v11 = *(_DWORD *)(v8 + 8);
      if ( v11 > 1 && (int)a3 >= v11 && (unsigned int)_acrt_MultiByteToWideChar(v9, 9, a2)
        || (unsigned __int64)a3 >= *(int *)(*((_QWORD *)a4 + 3) + 8LL) && *((_BYTE *)a2 + 1) )
      {
        return *(unsigned int *)(*((_QWORD *)a4 + 3) + 8LL);
      }
    }
    *((_BYTE *)a4 + 48) = 1;
    result = 0xFFFFFFFFLL;
    *((_DWORD *)a4 + 11) = 42;
    return result;
  }
  result = __crt_mbstring::__mbrtowc_utf8(this, a2, a3, (unsigned __int64)&qword_100435E50, (struct _Mbstatet *)a4, v12);
  if ( (result & 0x80000000) != 0LL )
    return 0xFFFFFFFFLL;
  return result;
}

```

## disassembly

```asm
0x10041f2d8  mov     rax, rsp
0x10041f2db  mov     [rax+8], rbx
0x10041f2df  mov     [rax+10h], rbp
0x10041f2e3  mov     [rax+18h], rsi
0x10041f2e7  mov     [rax+20h], rdi
0x10041f2eb  push    r14
0x10041f2ed  sub     rsp, 30h
0x10041f2f1  xor     r14d, r14d
0x10041f2f4  mov     rbx, r9
0x10041f2f7  mov     rbp, r8
0x10041f2fa  mov     rsi, rdx
0x10041f2fd  mov     rdi, rcx
0x10041f300  test    rdx, rdx
0x10041f303  jz      loc_10041F42C
0x10041f309  test    r8, r8
0x10041f30c  jz      loc_10041F42C
0x10041f312  cmp     [rdx], r14b
0x10041f315  jnz     short loc_10041F329
0x10041f317  test    rcx, rcx
0x10041f31a  jz      loc_10041F433
0x10041f320  mov     [rcx], r14w
0x10041f324  jmp     loc_10041F433
0x10041f329  cmp     [r9+28h], r14b
0x10041f32d  jnz     short loc_10041F337
0x10041f32f  mov     rcx, rbx; this
0x10041f332  call    ?update_locale_slow@__crt_cached_ptd_host@@AEAAXXZ; __crt_cached_ptd_host::update_locale_slow(void)
0x10041f337  mov     rdx, [rbx+18h]
0x10041f33b  mov     r10d, [rdx+0Ch]
0x10041f33f  cmp     r10d, 0FDE9h
0x10041f346  jnz     short loc_10041F36F
0x10041f348  lea     r9, qword_100435E50; unsigned __int64
0x10041f34f  mov     [rsp+38h+var_18], rbx; struct _Mbstatet *
0x10041f354  mov     r8, rbp; char *
0x10041f357  mov     rdx, rsi; wchar_t *
0x10041f35a  mov     rcx, rdi; this
0x10041f35d  call    ?__mbrtowc_utf8@__crt_mbstring@@YA_KPEA_WPEBD_KPEAU_Mbstatet@@AEAV__crt_cached_ptd_host@@@Z; __crt_mbstring::__mbrtowc_utf8(wchar_t *,char const *,unsigned __int64,_Mbstatet *,__crt_cached_ptd_host &)
0x10041f362  or      ecx, 0FFFFFFFFh
0x10041f365  test    eax, eax
0x10041f367  cmovs   eax, ecx
0x10041f36a  jmp     loc_10041F435
0x10041f36f  cmp     [rdx+138h], r14
0x10041f376  jnz     short loc_10041F38C
0x10041f378  test    rdi, rdi
0x10041f37b  jz      loc_10041F425
0x10041f381  movzx   eax, byte ptr [rsi]
0x10041f384  mov     [rdi], ax
0x10041f387  jmp     loc_10041F425
0x10041f38c  movzx   ecx, byte ptr [rsi]
0x10041f38f  mov     rax, [rdx]
0x10041f392  cmp     [rax+rcx*2], r14w
0x10041f397  jge     short loc_10041F3FA
0x10041f399  mov     r9d, [rdx+8]
0x10041f39d  cmp     r9d, 1
0x10041f3a1  jle     short loc_10041F3CE
0x10041f3a3  cmp     ebp, r9d
0x10041f3a6  jl      short loc_10041F3CE
0x10041f3a8  mov     eax, r14d
0x10041f3ab  test    rdi, rdi
0x10041f3ae  mov     r8, rsi
0x10041f3b1  mov     edx, 9
0x10041f3b6  setnz   al
0x10041f3b9  mov     ecx, r10d
0x10041f3bc  mov     [rsp+38h+var_10], eax
0x10041f3c0  mov     [rsp+38h+var_18], rdi
0x10041f3c5  call    __acrt_MultiByteToWideChar
0x10041f3ca  test    eax, eax
0x10041f3cc  jnz     short loc_10041F3E1
0x10041f3ce  mov     rax, [rbx+18h]
0x10041f3d2  movsxd  rcx, dword ptr [rax+8]
0x10041f3d6  cmp     rbp, rcx
0x10041f3d9  jb      short loc_10041F3EA
0x10041f3db  cmp     [rsi+1], r14b
0x10041f3df  jz      short loc_10041F3EA
0x10041f3e1  mov     rax, [rbx+18h]
0x10041f3e5  mov     eax, [rax+8]
0x10041f3e8  jmp     short loc_10041F435
0x10041f3ea  mov     byte ptr [rbx+30h], 1
0x10041f3ee  or      eax, 0FFFFFFFFh
0x10041f3f1  mov     dword ptr [rbx+2Ch], 2Ah ; '*'
0x10041f3f8  jmp     short loc_10041F435
0x10041f3fa  mov     eax, r14d
0x10041f3fd  mov     r9d, 1
0x10041f403  test    rdi, rdi
0x10041f406  mov     r8, rsi
0x10041f409  mov     ecx, r10d
0x10041f40c  setnz   al
0x10041f40f  mov     [rsp+38h+var_10], eax
0x10041f413  lea     edx, [r9+8]
0x10041f417  mov     [rsp+38h+var_18], rdi
0x10041f41c  call    __acrt_MultiByteToWideChar
0x10041f421  test    eax, eax
0x10041f423  jz      short loc_10041F3EA
0x10041f425  mov     eax, 1
0x10041f42a  jmp     short loc_10041F435
0x10041f42c  mov     cs:qword_100435E50, r14
0x10041f433  xor     eax, eax
0x10041f435  mov     rbx, [rsp+38h+arg_0]
0x10041f43a  mov     rbp, [rsp+38h+arg_8]
0x10041f43f  mov     rsi, [rsp+38h+arg_10]
0x10041f444  mov     rdi, [rsp+38h+arg_18]
0x10041f449  add     rsp, 30h
0x10041f44d  pop     r14
0x10041f44f  retn
```
