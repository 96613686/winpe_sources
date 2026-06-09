# CEnumImages::~CEnumImages(void)

- ea: `0x180007cac`
- end: `0x180007d0d`
- name: `??1CEnumImages@@UEAA@XZ`
- size: `97`
- prototype: `void __fastcall(CEnumImages *__hidden this)`
- caller_count: `4`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180007d20`
- `0x1800096c0`
- `0x18000a570`
- `0x18000b8b0`

## callees

- `0x1800072d4`
- `0x180007cac`
- `0x180011010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180007cc8`
- `msvcrt!??3@YAXPEAX@Z` at `0x180007cc8`

## pseudocode

```c
void __fastcall CEnumImages::~CEnumImages(CEnumImages *this)
{
  void *v2; // rcx
  __int64 v3; // rcx

  *(_QWORD *)this = &CEnumImages::`vftable';
  v2 = (void *)*((_QWORD *)this + 7);
  if ( v2 )
  {
    operator delete(v2);
    *((_QWORD *)this + 7) = 0;
  }
  v3 = *((_QWORD *)this + 8);
  if ( v3 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 8LL))(v3);
    *((_QWORD *)this + 8) = 0;
  }
  CDynArray<unsigned short *,CDeallocateString>::~CDynArray<unsigned short *,CDeallocateString>((char *)this + 24);
  *(_QWORD *)this = &CRefCount::`vftable';
}

```

## disassembly

```asm
0x180007cac  push    rbx
0x180007cae  sub     rsp, 20h
0x180007cb2  lea     rax, ??_7CEnumImages@@6B@; const CEnumImages::`vftable'
0x180007cb9  mov     rbx, rcx
0x180007cbc  mov     [rcx], rax
0x180007cbf  mov     rcx, [rcx+38h]
0x180007cc3  test    rcx, rcx
0x180007cc6  jz      short loc_180007CD9
0x180007cc8  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180007ccf  nop     dword ptr [rax+rax+00h]
0x180007cd4  and     qword ptr [rbx+38h], 0
0x180007cd9  mov     rcx, [rbx+40h]
0x180007cdd  test    rcx, rcx
0x180007ce0  jz      short loc_180007CF3
0x180007ce2  mov     rax, [rcx]
0x180007ce5  mov     rax, [rax+8]
0x180007ce9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007cee  and     qword ptr [rbx+40h], 0
0x180007cf3  lea     rcx, [rbx+18h]
0x180007cf7  call    ??1?$CDynArray@PEAGVCDeallocateString@@@@QEAA@XZ; CDynArray<ushort *,CDeallocateString>::~CDynArray<ushort *,CDeallocateString>(void)
0x180007cfc  lea     rax, ??_7CRefCount@@6B@; const CRefCount::`vftable'
0x180007d03  mov     [rbx], rax
0x180007d06  add     rsp, 20h
0x180007d0a  pop     rbx
0x180007d0b  retn
```
