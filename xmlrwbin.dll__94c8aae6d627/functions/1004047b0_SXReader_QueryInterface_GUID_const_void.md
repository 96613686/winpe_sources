# SXReader::QueryInterface(_GUID const &,void * *)

- ea: `0x1004047b0`
- end: `0x100404854`
- name: `?QueryInterface@SXReader@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `164`
- prototype: `__int64 __fastcall(SXReader *__hidden this, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x100406470`

## callees

- `0x1004047b0`
- `0x100424580`

## pseudocode

```c
__int64 __fastcall SXReader::QueryInterface(SXReader *this, const struct _GUID *a2, void **a3)
{
  char *v4; // rdx

  if ( !a3 )
    return 2147942487LL;
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IUnknown.Data1 && *(_QWORD *)a2->Data4 == *(_QWORD *)IID_IUnknown.Data4
    || *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_ISAXXMLReader.Data1
    && *(_QWORD *)a2->Data4 == *(_QWORD *)IID_ISAXXMLReader.Data4 )
  {
    v4 = (char *)this - 1456;
  }
  else
  {
    if ( *(_QWORD *)&a2->Data1 != *(_QWORD *)&IID_ISAXLocator.Data1
      || *(_QWORD *)a2->Data4 != *(_QWORD *)IID_ISAXLocator.Data4 )
    {
      *a3 = 0;
      return 2147500034LL;
    }
    v4 = (char *)this - 1456;
    this = (SXReader *)((char *)this + 8);
  }
  if ( !v4 )
    this = 0;
  *a3 = this;
  (*(void (__fastcall **)(char *))(*(_QWORD *)v4 + 8LL))(v4);
  return 0;
}

```

## disassembly

```asm
0x1004047b0  sub     rsp, 28h
0x1004047b4  test    r8, r8
0x1004047b7  jnz     short loc_1004047C3
0x1004047b9  mov     eax, 80070057h
0x1004047be  add     rsp, 28h
0x1004047c2  retn
0x1004047c3  mov     rax, [rdx]
0x1004047c6  cmp     rax, qword ptr cs:IID_IUnknown.Data1
0x1004047cd  jnz     short loc_1004047DC
0x1004047cf  mov     rax, [rdx+8]
0x1004047d3  cmp     rax, qword ptr cs:IID_IUnknown.Data4
0x1004047da  jz      short loc_1004047F5
0x1004047dc  mov     rax, [rdx]
0x1004047df  cmp     rax, qword ptr cs:IID_ISAXXMLReader.Data1
0x1004047e6  jnz     short loc_1004047FE
0x1004047e8  mov     rax, [rdx+8]
0x1004047ec  cmp     rax, qword ptr cs:IID_ISAXXMLReader.Data4
0x1004047f3  jnz     short loc_1004047FE
0x1004047f5  lea     rdx, [rcx-5B0h]
0x1004047fc  jmp     short loc_100404822
0x1004047fe  mov     rax, [rdx]
0x100404801  cmp     rax, qword ptr cs:IID_ISAXLocator.Data1
0x100404808  jnz     short loc_100404845
0x10040480a  mov     rax, [rdx+8]
0x10040480e  cmp     rax, qword ptr cs:IID_ISAXLocator.Data4
0x100404815  jnz     short loc_100404845
0x100404817  lea     rdx, [rcx-5B0h]
0x10040481e  add     rcx, 8
0x100404822  xor     eax, eax
0x100404824  test    rdx, rdx
0x100404827  cmovz   rcx, rax
0x10040482b  mov     [r8], rcx
0x10040482e  mov     rcx, rdx
0x100404831  mov     rax, [rdx]
0x100404834  mov     rax, [rax+8]
0x100404838  call    cs:__guard_dispatch_icall_fptr
0x10040483e  xor     eax, eax
0x100404840  add     rsp, 28h
0x100404844  retn
0x100404845  xor     eax, eax
0x100404847  mov     [r8], rax
0x10040484a  mov     eax, 80004002h
0x10040484f  add     rsp, 28h
0x100404853  retn
```
