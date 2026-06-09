# CreateMXXMLWriterEx(_GUID const &,void * *,IMalloc *)

- ea: `0x10041ca20`
- end: `0x10041cad1`
- name: `?CreateMXXMLWriterEx@@YAJAEBU_GUID@@PEAPEAXPEAUIMalloc@@@Z`
- size: `177`
- prototype: `int(const struct _GUID *, void **, struct IMalloc *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x10041ca10`

## callees

- `0x10041ca20`
- `0x10041cae0`
- `0x100423e80`
- `0x100439df0`

## pseudocode

```c
__int64 __fastcall CreateMXXMLWriterEx(const struct _GUID *a1, void **a2, struct IMalloc *a3)
{
  struct SAXWriter *v5; // rdi
  unsigned int v6; // ebx
  struct SAXWriter *v8; // [rsp+68h] [rbp+10h] BYREF

  v5 = 0;
  v8 = 0;
  if ( a2 )
  {
    *a2 = 0;
    v6 = SAXWriter::newSAXWriter(a3, &v8);
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
0x10041ca20  mov     [rsp+arg_0], rbx
0x10041ca25  mov     [rsp+arg_10], rsi
0x10041ca2a  mov     [rsp+arg_18], rdi
0x10041ca2f  push    r14
0x10041ca31  sub     rsp, 50h
0x10041ca35  mov     rsi, rdx
0x10041ca38  mov     r14, rcx
0x10041ca3b  xor     edi, edi
0x10041ca3d  mov     [rsp+58h+arg_8], rdi
0x10041ca42  test    rdx, rdx
0x10041ca45  jnz     short loc_10041CA4E
0x10041ca47  mov     ebx, 80004003h
0x10041ca4c  jmp     short loc_10041CAA3
0x10041ca4e  mov     [rdx], rdi
0x10041ca51  lea     rdx, [rsp+58h+arg_8]; struct SAXWriter **
0x10041ca56  mov     rcx, r8; struct IMalloc *
0x10041ca59  call    ?newSAXWriter@SAXWriter@@SAJPEAUIMalloc@@PEAPEAV1@@Z; SAXWriter::newSAXWriter(IMalloc *,SAXWriter * *)
0x10041ca5e  mov     ebx, eax
0x10041ca60  mov     [rsp+58h+var_30], eax
0x10041ca64  test    eax, eax
0x10041ca66  jz      short loc_10041CA6F
0x10041ca68  mov     rdi, [rsp+58h+arg_8]
0x10041ca6d  jmp     short loc_10041CAA3
0x10041ca6f  mov     rdi, [rsp+58h+arg_8]
0x10041ca74  lea     rcx, [rdi+10h]
0x10041ca78  mov     rax, [rcx]
0x10041ca7b  mov     r8, rsi
0x10041ca7e  mov     rdx, r14
0x10041ca81  mov     rax, [rax]
0x10041ca84  call    cs:__guard_dispatch_icall_fptr
0x10041ca8a  mov     ebx, eax
0x10041ca8c  mov     [rsp+58h+var_30], eax
0x10041ca90  test    eax, eax
0x10041ca92  jnz     short loc_10041CAA3
0x10041ca94  jmp     short loc_10041CAA3
0x10041ca96  mov     ebx, [rsp+58h+var_38]
0x10041ca9a  mov     [rsp+58h+var_30], ebx
0x10041ca9e  mov     rdi, [rsp+58h+arg_8]
0x10041caa3  test    rdi, rdi
0x10041caa6  jz      short loc_10041CAB9
0x10041caa8  lea     rcx, [rdi+10h]
0x10041caac  mov     rax, [rcx]
0x10041caaf  mov     rax, [rax+10h]
0x10041cab3  call    cs:__guard_dispatch_icall_fptr
0x10041cab9  mov     eax, ebx
0x10041cabb  mov     rbx, [rsp+58h+arg_0]
0x10041cac0  mov     rsi, [rsp+58h+arg_10]
0x10041cac5  mov     rdi, [rsp+58h+arg_18]
0x10041caca  add     rsp, 50h
0x10041cace  pop     r14
0x10041cad0  retn
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
