# CreateSXFormatReaderEx(_GUID const &,void * *,IMalloc *)

- ea: `0x1004040b0`
- end: `0x100404163`
- name: `?CreateSXFormatReaderEx@@YAJAEBU_GUID@@PEAPEAXPEAUIMalloc@@@Z`
- size: `179`
- prototype: `int(const struct _GUID *, void **, struct IMalloc *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1004040a0`

## callees

- `0x1004040b0`
- `0x100404170`
- `0x100414140`
- `0x100424580`

## pseudocode

```c
__int64 __fastcall CreateSXFormatReaderEx(const struct _GUID *a1, void **a2, struct IMalloc *a3)
{
  struct SXReader *v5; // rbx
  unsigned int v6; // edi
  struct SXReader *v8; // [rsp+68h] [rbp+10h] BYREF

  v5 = 0;
  v8 = 0;
  if ( a2 )
  {
    *a2 = 0;
    v6 = SXReader::newSXReader(a3, &v8);
    v5 = v8;
    if ( !v6 )
      v6 = (**((__int64 (__fastcall ***)(char *, const struct _GUID *, void **))v8 + 182))((char *)v8 + 1456, a1, a2);
  }
  else
  {
    v6 = -2147467261;
  }
  if ( v5 )
    (*(void (__fastcall **)(struct SXReader *, void **, struct IMalloc *))(*(_QWORD *)v5 + 16LL))(v5, a2, a3);
  return v6;
}

```

## disassembly

```asm
0x1004040b0  mov     [rsp+arg_0], rbx
0x1004040b5  mov     [rsp+arg_10], rsi
0x1004040ba  mov     [rsp+arg_18], rdi
0x1004040bf  push    r14
0x1004040c1  sub     rsp, 50h
0x1004040c5  mov     rsi, rdx
0x1004040c8  mov     r14, rcx
0x1004040cb  xor     ebx, ebx
0x1004040cd  mov     [rsp+58h+arg_8], rbx
0x1004040d2  test    rdx, rdx
0x1004040d5  jnz     short loc_1004040DE
0x1004040d7  mov     edi, 80004003h
0x1004040dc  jmp     short loc_100404136
0x1004040de  mov     [rdx], rbx
0x1004040e1  lea     rdx, [rsp+58h+arg_8]; struct SXReader **
0x1004040e6  mov     rcx, r8; struct IMalloc *
0x1004040e9  call    ?newSXReader@SXReader@@SAJPEAUIMalloc@@PEAPEAV1@@Z; SXReader::newSXReader(IMalloc *,SXReader * *)
0x1004040ee  mov     edi, eax
0x1004040f0  mov     [rsp+58h+var_30], eax
0x1004040f4  test    eax, eax
0x1004040f6  jz      short loc_1004040FF
0x1004040f8  mov     rbx, [rsp+58h+arg_8]
0x1004040fd  jmp     short loc_100404136
0x1004040ff  mov     rbx, [rsp+58h+arg_8]
0x100404104  lea     rcx, [rbx+5B0h]
0x10040410b  mov     rax, [rcx]
0x10040410e  mov     r8, rsi
0x100404111  mov     rdx, r14
0x100404114  mov     rax, [rax]
0x100404117  call    cs:__guard_dispatch_icall_fptr
0x10040411d  mov     edi, eax
0x10040411f  mov     [rsp+58h+var_30], eax
0x100404123  test    eax, eax
0x100404125  jnz     short loc_100404136
0x100404127  jmp     short loc_100404136
0x100404129  mov     edi, [rsp+58h+var_38]
0x10040412d  mov     [rsp+58h+var_30], edi
0x100404131  mov     rbx, [rsp+58h+arg_8]
0x100404136  test    rbx, rbx
0x100404139  jz      short loc_10040414B
0x10040413b  mov     rax, [rbx]
0x10040413e  mov     rcx, rbx
0x100404141  mov     rax, [rax+10h]
0x100404145  call    cs:__guard_dispatch_icall_fptr
0x10040414b  mov     eax, edi
0x10040414d  mov     rbx, [rsp+58h+arg_0]
0x100404152  mov     rsi, [rsp+58h+arg_10]
0x100404157  mov     rdi, [rsp+58h+arg_18]
0x10040415c  add     rsp, 50h
0x100404160  pop     r14
0x100404162  retn
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
