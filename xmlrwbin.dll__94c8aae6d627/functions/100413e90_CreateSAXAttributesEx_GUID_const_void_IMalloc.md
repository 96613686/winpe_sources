# CreateSAXAttributesEx(_GUID const &,void * *,IMalloc *)

- ea: `0x100413e90`
- end: `0x100413f41`
- name: `?CreateSAXAttributesEx@@YAJAEBU_GUID@@PEAPEAXPEAUIMalloc@@@Z`
- size: `177`
- prototype: `int(const struct _GUID *, void **, struct IMalloc *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x100413e80`

## callees

- `0x100413e90`
- `0x100414090`
- `0x100414140`
- `0x100424580`

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
0x100413e90  mov     [rsp+arg_0], rbx
0x100413e95  mov     [rsp+arg_10], rsi
0x100413e9a  mov     [rsp+arg_18], rdi
0x100413e9f  push    r14
0x100413ea1  sub     rsp, 50h
0x100413ea5  mov     rsi, rdx
0x100413ea8  mov     r14, rcx
0x100413eab  xor     edi, edi
0x100413ead  mov     [rsp+58h+arg_8], rdi
0x100413eb2  test    rdx, rdx
0x100413eb5  jnz     short loc_100413EBE
0x100413eb7  mov     ebx, 80004003h
0x100413ebc  jmp     short loc_100413F13
0x100413ebe  mov     [rdx], rdi
0x100413ec1  lea     rdx, [rsp+58h+arg_8]; struct SAXAttributesBase **
0x100413ec6  mov     rcx, r8; struct IMalloc *
0x100413ec9  call    ?newSAXAttributesBase@SAXAttributesBase@@SAJPEAUIMalloc@@PEAPEAV1@@Z; SAXAttributesBase::newSAXAttributesBase(IMalloc *,SAXAttributesBase * *)
0x100413ece  mov     ebx, eax
0x100413ed0  mov     [rsp+58h+var_30], eax
0x100413ed4  test    eax, eax
0x100413ed6  jz      short loc_100413EDF
0x100413ed8  mov     rdi, [rsp+58h+arg_8]
0x100413edd  jmp     short loc_100413F13
0x100413edf  mov     rdi, [rsp+58h+arg_8]
0x100413ee4  lea     rcx, [rdi+10h]
0x100413ee8  mov     rax, [rcx]
0x100413eeb  mov     r8, rsi
0x100413eee  mov     rdx, r14
0x100413ef1  mov     rax, [rax]
0x100413ef4  call    cs:__guard_dispatch_icall_fptr
0x100413efa  mov     ebx, eax
0x100413efc  mov     [rsp+58h+var_30], eax
0x100413f00  test    eax, eax
0x100413f02  jnz     short loc_100413F13
0x100413f04  jmp     short loc_100413F13
0x100413f06  mov     ebx, [rsp+58h+var_38]
0x100413f0a  mov     [rsp+58h+var_30], ebx
0x100413f0e  mov     rdi, [rsp+58h+arg_8]
0x100413f13  test    rdi, rdi
0x100413f16  jz      short loc_100413F29
0x100413f18  lea     rcx, [rdi+10h]
0x100413f1c  mov     rax, [rcx]
0x100413f1f  mov     rax, [rax+10h]
0x100413f23  call    cs:__guard_dispatch_icall_fptr
0x100413f29  mov     eax, ebx
0x100413f2b  mov     rbx, [rsp+58h+arg_0]
0x100413f30  mov     rsi, [rsp+58h+arg_10]
0x100413f35  mov     rdi, [rsp+58h+arg_18]
0x100413f3a  add     rsp, 50h
0x100413f3e  pop     r14
0x100413f40  retn
0x1004245b0  push    rbp
0x1004245b2  sub     rsp, 20h
0x1004245b6  mov     rbp, rdx
0x1004245b9  mov     [rbp+40h], rcx
0x1004245bd  mov     [rbp+38h], rcx
0x1004245c1  mov     rax, [rbp+38h]
0x1004245c5  mov     rcx, [rax]
0x1004245c8  mov     [rbp+30h], rcx
0x1004245cc  mov     rax, [rbp+30h]
0x1004245d0  mov     eax, [rax]
0x1004245d2  cmp     eax, 0C0000005h
0x1004245d7  jz      short loc_100424609
0x1004245d9  add     eax, 1FFFFFFFh
0x1004245de  cmp     eax, 1
0x1004245e1  ja      short loc_1004245F9
0x1004245e3  mov     rax, [rbp+30h]
0x1004245e7  cmp     dword ptr [rax+18h], 1
0x1004245eb  jnz     short loc_1004245F9
0x1004245ed  mov     rax, [rbp+30h]
0x1004245f1  mov     ecx, [rax+20h]
0x1004245f4  mov     [rbp+20h], ecx
0x1004245f7  jmp     short loc_100424600
0x1004245f9  mov     dword ptr [rbp+20h], 8000FFFFh
0x100424600  mov     dword ptr [rbp+24h], 1
0x100424607  jmp     short loc_100424610
0x100424609  mov     dword ptr [rbp+24h], 0
0x100424610  mov     eax, [rbp+24h]
0x100424613  add     rsp, 20h
0x100424617  pop     rbp
0x100424618  retn
```
