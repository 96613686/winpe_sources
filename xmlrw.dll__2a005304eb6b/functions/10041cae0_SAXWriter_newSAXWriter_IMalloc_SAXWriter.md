# SAXWriter::newSAXWriter(IMalloc *,SAXWriter * *)

- ea: `0x10041cae0`
- end: `0x10041cb95`
- name: `?newSAXWriter@SAXWriter@@SAJPEAUIMalloc@@PEAPEAV1@@Z`
- size: `181`
- prototype: `__int64 __fastcall(struct IMalloc *, struct SAXWriter **)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x10041ca20`

## callees

- `0x10041bf50`
- `0x10041cae0`
- `0x10041cba0`
- `0x10041cdf0`
- `0x100423e80`
- `0x100439df0`

## pseudocode

```c
__int64 __fastcall SAXWriter::newSAXWriter(struct IMalloc *a1, struct SAXWriter **a2)
{
  int v4; // ebx
  SAXWriter *v5; // rax

  v4 = 0;
  if ( !a2 )
  {
    v4 = -2147467261;
LABEL_9:
    if ( a2 && *a2 )
    {
      (*(void (__fastcall **)(char *))(*((_QWORD *)*a2 + 2) + 16LL))((char *)*a2 + 16);
      *a2 = 0;
    }
    return (unsigned int)v4;
  }
  *a2 = 0;
  v5 = (SAXWriter *)Base::operator new(488, a1);
  if ( v5 )
    v5 = SAXWriter::SAXWriter(v5, a1);
  *a2 = v5;
  if ( v5 )
    SAXWriter::Initialize(v5);
  else
    v4 = -2147024882;
  if ( v4 < 0 )
    goto LABEL_9;
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x10041cae0  mov     [rsp+arg_0], rbx
0x10041cae5  mov     [rsp+arg_10], rsi
0x10041caea  mov     [rsp+arg_8], rdx
0x10041caef  push    rdi
0x10041caf0  sub     rsp, 50h
0x10041caf4  mov     rdi, rdx
0x10041caf7  mov     rsi, rcx
0x10041cafa  xor     ebx, ebx
0x10041cafc  mov     [rsp+58h+var_30], ebx
0x10041cb00  test    rdx, rdx
0x10041cb03  jnz     short loc_10041CB0C
0x10041cb05  mov     ebx, 80004003h
0x10041cb0a  jmp     short loc_10041CB5E
0x10041cb0c  mov     qword ptr [rdx], 0
0x10041cb13  mov     rdx, rsi
0x10041cb16  mov     ecx, 1E8h
0x10041cb1b  call    ??2Base@@SAPEAX_KPEAUIMalloc@@W4NewZeroMemoryEnum@@@Z; Base::operator new(unsigned __int64,IMalloc *,NewZeroMemoryEnum)
0x10041cb20  test    rax, rax
0x10041cb23  jz      short loc_10041CB30
0x10041cb25  mov     rdx, rsi; struct IMalloc *
0x10041cb28  mov     rcx, rax; this
0x10041cb2b  call    ??0SAXWriter@@IEAA@PEAUIMalloc@@@Z; SAXWriter::SAXWriter(IMalloc *)
0x10041cb30  mov     [rdi], rax
0x10041cb33  test    rax, rax
0x10041cb36  jnz     short loc_10041CB43
0x10041cb38  mov     ebx, 8007000Eh
0x10041cb3d  mov     [rsp+58h+var_30], ebx
0x10041cb41  jmp     short loc_10041CB5A
0x10041cb43  mov     rcx, rax; this
0x10041cb46  call    ?Initialize@SAXWriter@@IEAAXXZ; SAXWriter::Initialize(void)
0x10041cb4b  jmp     short loc_10041CB5A
0x10041cb4d  mov     ebx, [rsp+58h+var_38]
0x10041cb51  mov     [rsp+58h+var_30], ebx
0x10041cb55  mov     rdi, [rsp+58h+arg_8]
0x10041cb5a  test    ebx, ebx
0x10041cb5c  jns     short loc_10041CB83
0x10041cb5e  test    rdi, rdi
0x10041cb61  jz      short loc_10041CB83
0x10041cb63  mov     rcx, [rdi]
0x10041cb66  test    rcx, rcx
0x10041cb69  jz      short loc_10041CB83
0x10041cb6b  add     rcx, 10h
0x10041cb6f  mov     rdx, [rcx]
0x10041cb72  mov     rax, [rdx+10h]
0x10041cb76  call    cs:__guard_dispatch_icall_fptr
0x10041cb7c  mov     qword ptr [rdi], 0
0x10041cb83  mov     eax, ebx
0x10041cb85  mov     rbx, [rsp+58h+arg_0]
0x10041cb8a  mov     rsi, [rsp+58h+arg_10]
0x10041cb8f  add     rsp, 50h
0x10041cb93  pop     rdi
0x10041cb94  retn
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
