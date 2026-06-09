# SXAttributes::getURI(int,wchar_t const * *,int *)

- ea: `0x100411a40`
- end: `0x100411ae9`
- name: `?getURI@SXAttributes@@UEAAJHPEAPEB_WPEAH@Z`
- size: `169`
- prototype: `__int64 __fastcall(SXAttributes *__hidden this, int, const wchar_t **, int *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x100411a40`
- `0x100411ba0`
- `0x100411fb0`
- `0x100424580`

## pseudocode

```c
__int64 __fastcall SXAttributes::getURI(SXAttributes *this, int a2, const wchar_t **a3, int *a4)
{
  unsigned int v6; // ebx
  struct AttributeBase *v7; // r14
  struct AttributeBase *v9; // [rsp+38h] [rbp-20h] BYREF

  v6 = 0;
  if ( a3 && a4 )
  {
    if ( SXAttributes::getAttribute((SXAttributes *)((char *)this - 16), a2, &v9) )
    {
      v7 = v9;
      if ( (*(unsigned __int8 (__fastcall **)(struct AttributeBase *))(*(_QWORD *)v9 + 8LL))(v9) )
      {
        *a4 = 0;
        *a3 = 0;
      }
      else
      {
        *a4 = *(_DWORD *)(*((_QWORD *)v7 + 12) + 16LL);
        *a3 = (const wchar_t *)(*((_QWORD *)v7 + 12) + 24LL);
      }
    }
    else
    {
      return (unsigned int)-2147024809;
    }
  }
  else
  {
    return (unsigned int)-2147467261;
  }
  return v6;
}

```

## disassembly

```asm
0x100411a40  mov     [rsp+arg_0], rbx
0x100411a45  mov     [rsp+arg_8], rsi
0x100411a4a  mov     [rsp+arg_10], rdi
0x100411a4f  push    r14
0x100411a51  sub     rsp, 50h
0x100411a55  mov     rdi, r9
0x100411a58  mov     rsi, r8
0x100411a5b  xor     ebx, ebx
0x100411a5d  mov     [rsp+58h+var_34], ebx
0x100411a61  test    r8, r8
0x100411a64  jz      short loc_100411ABE
0x100411a66  test    r9, r9
0x100411a69  jz      short loc_100411ABE
0x100411a6b  add     rcx, 0FFFFFFFFFFFFFFF0h; this
0x100411a6f  lea     r8, [rsp+58h+var_20]; struct AttributeBase **
0x100411a74  call    ?getAttribute@SXAttributes@@AEAA_NHPEAPEAVAttributeBase@@@Z; SXAttributes::getAttribute(int,AttributeBase * *)
0x100411a79  test    al, al
0x100411a7b  jnz     short loc_100411A88
0x100411a7d  mov     ebx, 80070057h
0x100411a82  mov     [rsp+58h+var_34], ebx
0x100411a86  jmp     short loc_100411ABC
0x100411a88  mov     r14, [rsp+58h+var_20]
0x100411a8d  mov     rax, [r14]
0x100411a90  mov     rcx, r14
0x100411a93  mov     rax, [rax+8]
0x100411a97  call    cs:__guard_dispatch_icall_fptr
0x100411a9d  test    al, al
0x100411a9f  jnz     short loc_100411AB7
0x100411aa1  mov     rax, [r14+60h]
0x100411aa5  mov     ecx, [rax+10h]
0x100411aa8  mov     [rdi], ecx
0x100411aaa  mov     rax, [r14+60h]
0x100411aae  add     rax, 18h
0x100411ab2  mov     [rsi], rax
0x100411ab5  jmp     short loc_100411ABC
0x100411ab7  mov     [rdi], ebx
0x100411ab9  mov     [rsi], rbx
0x100411abc  jmp     short loc_100411AD1
0x100411abe  mov     ebx, 80004003h
0x100411ac3  mov     [rsp+58h+var_34], ebx
0x100411ac7  jmp     short loc_100411AD1
0x100411ac9  mov     ebx, [rsp+58h+var_38]
0x100411acd  mov     [rsp+58h+var_34], ebx
0x100411ad1  mov     eax, ebx
0x100411ad3  mov     rbx, [rsp+58h+arg_0]
0x100411ad8  mov     rsi, [rsp+58h+arg_8]
0x100411add  mov     rdi, [rsp+58h+arg_10]
0x100411ae2  add     rsp, 50h
0x100411ae6  pop     r14
0x100411ae8  retn
0x100424ba0  push    rbp
0x100424ba2  sub     rsp, 20h
0x100424ba6  mov     rbp, rdx
0x100424ba9  mov     [rbp+48h], rcx
0x100424bad  mov     [rbp+40h], rcx
0x100424bb1  mov     rax, [rbp+40h]
0x100424bb5  mov     rcx, [rax]
0x100424bb8  mov     [rbp+30h], rcx
0x100424bbc  mov     rax, [rbp+30h]
0x100424bc0  mov     eax, [rax]
0x100424bc2  cmp     eax, 0C0000005h
0x100424bc7  jz      short loc_100424BF9
0x100424bc9  add     eax, 1FFFFFFFh
0x100424bce  cmp     eax, 1
0x100424bd1  ja      short loc_100424BE9
0x100424bd3  mov     rax, [rbp+30h]
0x100424bd7  cmp     dword ptr [rax+18h], 1
0x100424bdb  jnz     short loc_100424BE9
0x100424bdd  mov     rax, [rbp+30h]
0x100424be1  mov     ecx, [rax+20h]
0x100424be4  mov     [rbp+20h], ecx
0x100424be7  jmp     short loc_100424BF0
0x100424be9  mov     dword ptr [rbp+20h], 8000FFFFh
0x100424bf0  mov     dword ptr [rbp+28h], 1
0x100424bf7  jmp     short loc_100424C00
0x100424bf9  mov     dword ptr [rbp+28h], 0
0x100424c00  mov     eax, [rbp+28h]
0x100424c03  add     rsp, 20h
0x100424c07  pop     rbp
0x100424c08  retn
```
