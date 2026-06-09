# SXWriter::MapHandleToUnitoken(unsigned __int64)

- ea: `0x10040aab0`
- end: `0x10040ab85`
- name: `?MapHandleToUnitoken@SXWriter@@AEAAK_K@Z`
- size: `213`
- prototype: `unsigned int __fastcall(SXWriter *__hidden this, unsigned __int64)`
- caller_count: `4`
- callee_count: `4`
- tags: ``

## callers

- `0x1004092b0`
- `0x1004093d0`
- `0x10040a980`
- `0x10040aa20`

## callees

- `0x100401350`
- `0x100407330`
- `0x100409da0`
- `0x10040aab0`

## pseudocode

```c
__int64 __fastcall SXWriter::MapHandleToUnitoken(SXWriter *this, unsigned __int64 a2)
{
  __int64 v3; // rbx
  __int64 result; // rax
  __int64 v5; // rax
  __int64 v6; // r10
  wchar_t *v7; // rcx
  wchar_t *v8; // rdx
  int v9; // r8d
  unsigned int v10; // [rsp+30h] [rbp-58h]
  __int128 v11; // [rsp+50h] [rbp-38h] BYREF
  __int64 v12; // [rsp+60h] [rbp-28h]
  unsigned int v13; // [rsp+90h] [rbp+8h] BYREF

  if ( a2 >= *((unsigned int *)this + 27) )
  {
    MXRRaiseException(-2147467259);
    JUMPOUT(0x10040AB84LL);
  }
  v3 = *((_QWORD *)this + 14) + 32LL * (unsigned int)a2;
  result = *(unsigned int *)(v3 + 24);
  if ( !(_DWORD)result )
  {
    v5 = *(_QWORD *)(v3 + 16);
    v6 = *(_QWORD *)(v3 + 8);
    v7 = (wchar_t *)(v5 + 24);
    v8 = (wchar_t *)(*(_QWORD *)v3 + 24LL);
    v9 = *(_DWORD *)(*(_QWORD *)v3 + 16LL);
    v10 = *(_DWORD *)(v5 + 16);
    LODWORD(v5) = *(_DWORD *)(v6 + 16);
    v11 = 0;
    v12 = 0;
    SXWriter::getUnitokenFromNames(this, v8, v9, (wchar_t *)(v6 + 24), v5, v7, v10, &v13, (struct Unitoken *)&v11);
    *(_DWORD *)(v3 + 24) = v13;
    WriterHandleEntry::~WriterHandleEntry((WriterHandleEntry *)&v11);
    return *(unsigned int *)(v3 + 24);
  }
  return result;
}

```

## disassembly

```asm
0x10040aab0  sub     rsp, 88h
0x10040aab7  mov     eax, [rcx+6Ch]
0x10040aaba  mov     r11, rcx
0x10040aabd  cmp     rdx, rax
0x10040aac0  jnb     loc_10040AB7A
0x10040aac6  mov     [rsp+88h+arg_8], rbx
0x10040aace  mov     ebx, edx
0x10040aad0  shl     rbx, 5
0x10040aad4  add     rbx, [rcx+70h]
0x10040aad8  mov     eax, [rbx+18h]
0x10040aadb  test    eax, eax
0x10040aadd  jnz     loc_10040AB6A
0x10040aae3  mov     rax, [rbx+10h]
0x10040aae7  xorps   xmm0, xmm0
0x10040aaea  mov     r8, [rbx]
0x10040aaed  mov     r10, [rbx+8]
0x10040aaf1  mov     [rsp+88h+var_8], rdi
0x10040aaf9  lea     rdi, [rsp+88h+var_38]
0x10040aafe  mov     [rsp+88h+var_48], rdi; struct Unitoken *
0x10040ab03  lea     rcx, [rax+18h]
0x10040ab07  mov     eax, [rax+10h]
0x10040ab0a  lea     rdx, [r8+18h]; wchar_t *
0x10040ab0e  mov     r8d, [r8+10h]; int
0x10040ab12  lea     rdi, [rsp+88h+arg_0]
0x10040ab1a  mov     [rsp+88h+var_50], rdi; unsigned int *
0x10040ab1f  lea     r9, [r10+18h]; wchar_t *
0x10040ab23  mov     [rsp+88h+var_58], eax; int
0x10040ab27  mov     eax, [r10+10h]
0x10040ab2b  mov     [rsp+88h+var_60], rcx; wchar_t *
0x10040ab30  mov     rcx, r11; this
0x10040ab33  movdqu  [rsp+88h+var_38], xmm0
0x10040ab39  mov     [rsp+88h+var_28], 0
0x10040ab42  mov     [rsp+88h+var_68], eax; int
0x10040ab46  call    ?getUnitokenFromNames@SXWriter@@AEAAXPEB_WH0H0HPEAKPEAVUnitoken@@@Z; SXWriter::getUnitokenFromNames(wchar_t const *,int,wchar_t const *,int,wchar_t const *,int,ulong *,Unitoken *)
0x10040ab4b  mov     eax, [rsp+88h+arg_0]
0x10040ab52  lea     rcx, [rsp+88h+var_38]; this
0x10040ab57  mov     [rbx+18h], eax
0x10040ab5a  call    ??1WriterHandleEntry@@QEAA@XZ; WriterHandleEntry::~WriterHandleEntry(void)
0x10040ab5f  mov     eax, [rbx+18h]
0x10040ab62  mov     rdi, [rsp+88h+var_8]
0x10040ab6a  mov     rbx, [rsp+88h+arg_8]
0x10040ab72  add     rsp, 88h
0x10040ab79  retn
0x10040ab7a  mov     ecx, 80004005h; int
0x10040ab7f  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
```
