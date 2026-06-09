# CreateSXFormatWriterEx(_GUID const &,void * *,IMalloc *)

- ea: `0x100407d50`
- end: `0x100407e01`
- name: `?CreateSXFormatWriterEx@@YAJAEBU_GUID@@PEAPEAXPEAUIMalloc@@@Z`
- size: `177`
- prototype: `int(const struct _GUID *, void **, struct IMalloc *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x100407d40`

## callees

- `0x100407d50`
- `0x100407e10`
- `0x100414140`
- `0x100424580`

## pseudocode

```c
__int64 __fastcall CreateSXFormatWriterEx(const struct _GUID *a1, void **a2, struct IMalloc *a3)
{
  struct SXWriter *v5; // rdi
  unsigned int v6; // ebx
  struct SXWriter *v8; // [rsp+68h] [rbp+10h] BYREF

  v5 = 0;
  v8 = 0;
  if ( a2 )
  {
    *a2 = 0;
    v6 = SXWriter::newSXWriter(a3, &v8);
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
0x100407d50  mov     [rsp+arg_0], rbx
0x100407d55  mov     [rsp+arg_10], rsi
0x100407d5a  mov     [rsp+arg_18], rdi
0x100407d5f  push    r14
0x100407d61  sub     rsp, 50h
0x100407d65  mov     rsi, rdx
0x100407d68  mov     r14, rcx
0x100407d6b  xor     edi, edi
0x100407d6d  mov     [rsp+58h+arg_8], rdi
0x100407d72  test    rdx, rdx
0x100407d75  jnz     short loc_100407D7E
0x100407d77  mov     ebx, 80004003h
0x100407d7c  jmp     short loc_100407DD3
0x100407d7e  mov     [rdx], rdi
0x100407d81  lea     rdx, [rsp+58h+arg_8]; struct SXWriter **
0x100407d86  mov     rcx, r8; struct IMalloc *
0x100407d89  call    ?newSXWriter@SXWriter@@SAJPEAUIMalloc@@PEAPEAV1@@Z; SXWriter::newSXWriter(IMalloc *,SXWriter * *)
0x100407d8e  mov     ebx, eax
0x100407d90  mov     [rsp+58h+var_30], eax
0x100407d94  test    eax, eax
0x100407d96  jz      short loc_100407D9F
0x100407d98  mov     rdi, [rsp+58h+arg_8]
0x100407d9d  jmp     short loc_100407DD3
0x100407d9f  mov     rdi, [rsp+58h+arg_8]
0x100407da4  lea     rcx, [rdi+10h]
0x100407da8  mov     rax, [rcx]
0x100407dab  mov     r8, rsi
0x100407dae  mov     rdx, r14
0x100407db1  mov     rax, [rax]
0x100407db4  call    cs:__guard_dispatch_icall_fptr
0x100407dba  mov     ebx, eax
0x100407dbc  mov     [rsp+58h+var_30], eax
0x100407dc0  test    eax, eax
0x100407dc2  jnz     short loc_100407DD3
0x100407dc4  jmp     short loc_100407DD3
0x100407dc6  mov     ebx, [rsp+58h+var_38]
0x100407dca  mov     [rsp+58h+var_30], ebx
0x100407dce  mov     rdi, [rsp+58h+arg_8]
0x100407dd3  test    rdi, rdi
0x100407dd6  jz      short loc_100407DE9
0x100407dd8  lea     rcx, [rdi+10h]
0x100407ddc  mov     rax, [rcx]
0x100407ddf  mov     rax, [rax+10h]
0x100407de3  call    cs:__guard_dispatch_icall_fptr
0x100407de9  mov     eax, ebx
0x100407deb  mov     rbx, [rsp+58h+arg_0]
0x100407df0  mov     rsi, [rsp+58h+arg_10]
0x100407df5  mov     rdi, [rsp+58h+arg_18]
0x100407dfa  add     rsp, 50h
0x100407dfe  pop     r14
0x100407e00  retn
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
