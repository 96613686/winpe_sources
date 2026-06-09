# CASFContentBrandingObject::SetCopyrightURL(char const *)

- ea: `0x1800248f8`
- end: `0x18002498b`
- name: `?SetCopyrightURL@CASFContentBrandingObject@@QEAAJPEBD@Z`
- size: `147`
- prototype: `int(CASFContentBrandingObject *__hidden this, const char *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800188d0`

## callees

- `0x180001194`
- `0x1800011ec`
- `0x1800248f8`
- `0x1800268e4`
- `0x18002694c`

## pseudocode

```c
__int64 __fastcall CASFContentBrandingObject::SetCopyrightURL(CASFContentBrandingObject *this, const char *a2)
{
  char *v2; // rbx
  unsigned __int64 v6; // rbp
  char *v7; // rax
  int v8; // esi
  void *v9; // rcx
  unsigned __int64 v10; // [rsp+58h] [rbp+10h] BYREF

  v2 = 0;
  if ( !a2 )
    goto LABEL_8;
  v10 = 0;
  if ( (int)StringCchLengthA(a2, 0x81Au, &v10) < 0 )
    return 2147942487LL;
  v6 = v10;
  v7 = (char *)operator new[](v10 + 1);
  v2 = v7;
  if ( !v7 )
    return 2147942414LL;
  v8 = StringCchCopyA(v7, v6 + 1, a2);
  if ( v8 < 0 )
  {
    operator delete(v2);
    return (unsigned int)v8;
  }
  else
  {
LABEL_8:
    v9 = (void *)*((_QWORD *)this + 11);
    if ( v9 )
      operator delete(v9);
    *((_QWORD *)this + 11) = v2;
    return 0;
  }
}

```

## disassembly

```asm
0x1800248f8  push    rbx
0x1800248fa  push    rbp
0x1800248fb  push    rsi
0x1800248fc  push    rdi
0x1800248fd  sub     rsp, 28h
0x180024901  xor     ebx, ebx
0x180024903  mov     rsi, rdx
0x180024906  mov     rdi, rcx
0x180024909  test    rdx, rdx
0x18002490c  jz      short loc_18002496E
0x18002490e  lea     r8, [rsp+48h+arg_8]; unsigned __int64 *
0x180024913  mov     [rsp+48h+arg_8], rbx
0x180024918  mov     edx, 81Ah; unsigned __int64
0x18002491d  mov     rcx, rsi; char *
0x180024920  call    ?StringCchLengthA@@YAJPEBD_KPEA_K@Z; StringCchLengthA(char const *,unsigned __int64,unsigned __int64 *)
0x180024925  test    eax, eax
0x180024927  jns     short loc_180024930
0x180024929  mov     eax, 80070057h
0x18002492e  jmp     short loc_180024982
0x180024930  mov     rbp, [rsp+48h+arg_8]
0x180024935  lea     rcx, [rbp+1]; unsigned __int64
0x180024939  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18002493e  mov     rbx, rax
0x180024941  test    rax, rax
0x180024944  jnz     short loc_18002494D
0x180024946  mov     eax, 8007000Eh
0x18002494b  jmp     short loc_180024982
0x18002494d  mov     r8, rsi; char *
0x180024950  lea     rdx, [rbp+1]; unsigned __int64
0x180024954  mov     rcx, rbx; char *
0x180024957  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x18002495c  mov     esi, eax
0x18002495e  test    eax, eax
0x180024960  jns     short loc_18002496E
0x180024962  mov     rcx, rbx; void *
0x180024965  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002496a  mov     eax, esi
0x18002496c  jmp     short loc_180024982
0x18002496e  mov     rcx, [rdi+58h]; void *
0x180024972  test    rcx, rcx
0x180024975  jz      short loc_18002497C
0x180024977  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002497c  mov     [rdi+58h], rbx
0x180024980  xor     eax, eax
0x180024982  add     rsp, 28h
0x180024986  pop     rdi
0x180024987  pop     rsi
0x180024988  pop     rbp
0x180024989  pop     rbx
0x18002498a  retn
```
