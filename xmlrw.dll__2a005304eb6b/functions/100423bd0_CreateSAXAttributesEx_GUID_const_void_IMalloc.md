# CreateSAXAttributesEx(_GUID const &,void * *,IMalloc *)

- ea: `0x100423bd0`
- end: `0x100423c81`
- name: `?CreateSAXAttributesEx@@YAJAEBU_GUID@@PEAPEAXPEAUIMalloc@@@Z`
- size: `177`
- prototype: `int(const struct _GUID *, void **, struct IMalloc *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x100423bc0`

## callees

- `0x100423bd0`
- `0x100423dd0`
- `0x100423e80`
- `0x100439df0`

## pseudocode

```c
__int64 __fastcall CreateSAXAttributesEx(const struct _GUID *a1, void **a2, struct IMalloc *a3)
{
  struct SAXAttributesBase *v5; // rdi
  unsigned int v6; // ebx
  struct SAXAttributesBase *v8; // [rsp+68h] [rbp+10h] BYREF

  v5 = 0;
  v8 = 0;
  if ( a2 )
  {
    *a2 = 0;
    v6 = SAXAttributesBase::newSAXAttributesBase(a3, &v8);
    v5 = v8;
    if ( !v6 )
      v6 = (**((__int64 (__fastcall ***)(char *, const struct _GUID *, void **))v8 + 2))((char *)v8 + 16, a1, a2);
  }
  else
  {
    v6 = -2147467261;
  }
  if ( v5 )
    (*(void (__fastcall **)(__int64, void **, struct IMalloc *))(*((_QWORD *)v5 + 2) + 16LL))((__int64)v5 + 16, a2, a3);
  return v6;
}

```

## disassembly

```asm
0x100423bd0  mov     [rsp+arg_0], rbx
0x100423bd5  mov     [rsp+arg_10], rsi
0x100423bda  mov     [rsp+arg_18], rdi
0x100423bdf  push    r14
0x100423be1  sub     rsp, 50h
0x100423be5  mov     rsi, rdx
0x100423be8  mov     r14, rcx
0x100423beb  xor     edi, edi
0x100423bed  mov     [rsp+58h+arg_8], rdi
0x100423bf2  test    rdx, rdx
0x100423bf5  jnz     short loc_100423BFE
0x100423bf7  mov     ebx, 80004003h
0x100423bfc  jmp     short loc_100423C53
0x100423bfe  mov     [rdx], rdi
0x100423c01  lea     rdx, [rsp+58h+arg_8]; struct SAXAttributesBase **
0x100423c06  mov     rcx, r8; struct IMalloc *
0x100423c09  call    ?newSAXAttributesBase@SAXAttributesBase@@SAJPEAUIMalloc@@PEAPEAV1@@Z; SAXAttributesBase::newSAXAttributesBase(IMalloc *,SAXAttributesBase * *)
0x100423c0e  mov     ebx, eax
0x100423c10  mov     [rsp+58h+var_30], eax
0x100423c14  test    eax, eax
0x100423c16  jz      short loc_100423C1F
0x100423c18  mov     rdi, [rsp+58h+arg_8]
0x100423c1d  jmp     short loc_100423C53
0x100423c1f  mov     rdi, [rsp+58h+arg_8]
0x100423c24  lea     rcx, [rdi+10h]
0x100423c28  mov     rax, [rcx]
0x100423c2b  mov     r8, rsi
0x100423c2e  mov     rdx, r14
0x100423c31  mov     rax, [rax]
0x100423c34  call    cs:__guard_dispatch_icall_fptr
0x100423c3a  mov     ebx, eax
0x100423c3c  mov     [rsp+58h+var_30], eax
0x100423c40  test    eax, eax
0x100423c42  jnz     short loc_100423C53
0x100423c44  jmp     short loc_100423C53
0x100423c46  mov     ebx, [rsp+58h+var_38]
0x100423c4a  mov     [rsp+58h+var_30], ebx
0x100423c4e  mov     rdi, [rsp+58h+arg_8]
0x100423c53  test    rdi, rdi
0x100423c56  jz      short loc_100423C69
0x100423c58  lea     rcx, [rdi+10h]
0x100423c5c  mov     rax, [rcx]
0x100423c5f  mov     rax, [rax+10h]
0x100423c63  call    cs:__guard_dispatch_icall_fptr
0x100423c69  mov     eax, ebx
0x100423c6b  mov     rbx, [rsp+58h+arg_0]
0x100423c70  mov     rsi, [rsp+58h+arg_10]
0x100423c75  mov     rdi, [rsp+58h+arg_18]
0x100423c7a  add     rsp, 50h
0x100423c7e  pop     r14
0x100423c80  retn
0x10043a070  push    rbp
0x10043a072  sub     rsp, 20h
0x10043a076  mov     rbp, rdx
0x10043a079  mov     [rbp+40h], rcx
0x10043a07d  mov     [rbp+38h], rcx
0x10043a081  mov     rax, [rbp+38h]
0x10043a085  mov     rcx, [rax]
0x10043a088  mov     [rbp+30h], rcx
0x10043a08c  mov     rax, [rbp+30h]
0x10043a090  mov     eax, [rax]
0x10043a092  cmp     eax, 0C0000005h
0x10043a097  jz      short loc_10043A0C9
0x10043a099  add     eax, 1FFFFFFFh
0x10043a09e  cmp     eax, 1
0x10043a0a1  ja      short loc_10043A0B9
0x10043a0a3  mov     rax, [rbp+30h]
0x10043a0a7  cmp     dword ptr [rax+18h], 1
0x10043a0ab  jnz     short loc_10043A0B9
0x10043a0ad  mov     rax, [rbp+30h]
0x10043a0b1  mov     ecx, [rax+20h]
0x10043a0b4  mov     [rbp+20h], ecx
0x10043a0b7  jmp     short loc_10043A0C0
0x10043a0b9  mov     dword ptr [rbp+20h], 8000FFFFh
0x10043a0c0  mov     dword ptr [rbp+24h], 1
0x10043a0c7  jmp     short loc_10043A0D0
0x10043a0c9  mov     dword ptr [rbp+24h], 0
0x10043a0d0  mov     eax, [rbp+24h]
0x10043a0d3  add     rsp, 20h
0x10043a0d7  pop     rbp
0x10043a0d8  retn
```
