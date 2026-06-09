# _mbtowc_internal

- ea: `0x100432868`
- end: `0x1004329e0`
- name: `_mbtowc_internal`
- size: `376`
- prototype: `__int64 __fastcall(__crt_mbstring *this, wchar_t *, char *, __crt_cached_ptd_host *)`
- caller_count: `3`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x10042cae4`
- `0x10042d244`
- `0x1004344e8`

## callees

- `0x10042d4f0`
- `0x1004301ac`
- `0x100432868`
- `0x100436c74`

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
    qword_100451DC0 = 0;
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
  result = __crt_mbstring::__mbrtowc_utf8(this, a2, a3, (unsigned __int64)&qword_100451DC0, (struct _Mbstatet *)a4, v12);
  if ( (result & 0x80000000) != 0LL )
    return 0xFFFFFFFFLL;
  return result;
}

```

## disassembly

```asm
0x100432868  mov     rax, rsp
0x10043286b  mov     [rax+8], rbx
0x10043286f  mov     [rax+10h], rbp
0x100432873  mov     [rax+18h], rsi
0x100432877  mov     [rax+20h], rdi
0x10043287b  push    r14
0x10043287d  sub     rsp, 30h
0x100432881  xor     r14d, r14d
0x100432884  mov     rbx, r9
0x100432887  mov     rbp, r8
0x10043288a  mov     rsi, rdx
0x10043288d  mov     rdi, rcx
0x100432890  test    rdx, rdx
0x100432893  jz      loc_1004329BC
0x100432899  test    r8, r8
0x10043289c  jz      loc_1004329BC
0x1004328a2  cmp     [rdx], r14b
0x1004328a5  jnz     short loc_1004328B9
0x1004328a7  test    rcx, rcx
0x1004328aa  jz      loc_1004329C3
0x1004328b0  mov     [rcx], r14w
0x1004328b4  jmp     loc_1004329C3
0x1004328b9  cmp     [r9+28h], r14b
0x1004328bd  jnz     short loc_1004328C7
0x1004328bf  mov     rcx, rbx; this
0x1004328c2  call    ?update_locale_slow@__crt_cached_ptd_host@@AEAAXXZ; __crt_cached_ptd_host::update_locale_slow(void)
0x1004328c7  mov     rdx, [rbx+18h]
0x1004328cb  mov     r10d, [rdx+0Ch]
0x1004328cf  cmp     r10d, 0FDE9h
0x1004328d6  jnz     short loc_1004328FF
0x1004328d8  lea     r9, qword_100451DC0; unsigned __int64
0x1004328df  mov     [rsp+38h+var_18], rbx; struct _Mbstatet *
0x1004328e4  mov     r8, rbp; char *
0x1004328e7  mov     rdx, rsi; wchar_t *
0x1004328ea  mov     rcx, rdi; this
0x1004328ed  call    ?__mbrtowc_utf8@__crt_mbstring@@YA_KPEA_WPEBD_KPEAU_Mbstatet@@AEAV__crt_cached_ptd_host@@@Z; __crt_mbstring::__mbrtowc_utf8(wchar_t *,char const *,unsigned __int64,_Mbstatet *,__crt_cached_ptd_host &)
0x1004328f2  or      ecx, 0FFFFFFFFh
0x1004328f5  test    eax, eax
0x1004328f7  cmovs   eax, ecx
0x1004328fa  jmp     loc_1004329C5
0x1004328ff  cmp     [rdx+138h], r14
0x100432906  jnz     short loc_10043291C
0x100432908  test    rdi, rdi
0x10043290b  jz      loc_1004329B5
0x100432911  movzx   eax, byte ptr [rsi]
0x100432914  mov     [rdi], ax
0x100432917  jmp     loc_1004329B5
0x10043291c  movzx   ecx, byte ptr [rsi]
0x10043291f  mov     rax, [rdx]
0x100432922  cmp     [rax+rcx*2], r14w
0x100432927  jge     short loc_10043298A
0x100432929  mov     r9d, [rdx+8]
0x10043292d  cmp     r9d, 1
0x100432931  jle     short loc_10043295E
0x100432933  cmp     ebp, r9d
0x100432936  jl      short loc_10043295E
0x100432938  mov     eax, r14d
0x10043293b  test    rdi, rdi
0x10043293e  mov     r8, rsi
0x100432941  mov     edx, 9
0x100432946  setnz   al
0x100432949  mov     ecx, r10d
0x10043294c  mov     [rsp+38h+var_10], eax
0x100432950  mov     [rsp+38h+var_18], rdi
0x100432955  call    __acrt_MultiByteToWideChar
0x10043295a  test    eax, eax
0x10043295c  jnz     short loc_100432971
0x10043295e  mov     rax, [rbx+18h]
0x100432962  movsxd  rcx, dword ptr [rax+8]
0x100432966  cmp     rbp, rcx
0x100432969  jb      short loc_10043297A
0x10043296b  cmp     [rsi+1], r14b
0x10043296f  jz      short loc_10043297A
0x100432971  mov     rax, [rbx+18h]
0x100432975  mov     eax, [rax+8]
0x100432978  jmp     short loc_1004329C5
0x10043297a  mov     byte ptr [rbx+30h], 1
0x10043297e  or      eax, 0FFFFFFFFh
0x100432981  mov     dword ptr [rbx+2Ch], 2Ah ; '*'
0x100432988  jmp     short loc_1004329C5
0x10043298a  mov     eax, r14d
0x10043298d  mov     r9d, 1
0x100432993  test    rdi, rdi
0x100432996  mov     r8, rsi
0x100432999  mov     ecx, r10d
0x10043299c  setnz   al
0x10043299f  mov     [rsp+38h+var_10], eax
0x1004329a3  lea     edx, [r9+8]
0x1004329a7  mov     [rsp+38h+var_18], rdi
0x1004329ac  call    __acrt_MultiByteToWideChar
0x1004329b1  test    eax, eax
0x1004329b3  jz      short loc_10043297A
0x1004329b5  mov     eax, 1
0x1004329ba  jmp     short loc_1004329C5
0x1004329bc  mov     cs:qword_100451DC0, r14
0x1004329c3  xor     eax, eax
0x1004329c5  mov     rbx, [rsp+38h+arg_0]
0x1004329ca  mov     rbp, [rsp+38h+arg_8]
0x1004329cf  mov     rsi, [rsp+38h+arg_10]
0x1004329d4  mov     rdi, [rsp+38h+arg_18]
0x1004329d9  add     rsp, 30h
0x1004329dd  pop     r14
0x1004329df  retn
```
