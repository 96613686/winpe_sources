# CEnumItemProperties::~CEnumItemProperties(void)

- ea: `0x1800157d8`
- end: `0x180015850`
- name: `??1CEnumItemProperties@@AEAA@XZ`
- size: `120`
- prototype: `void __fastcall(CEnumItemProperties *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, service_task`

## callers

- `0x1800164c0`

## callees

- `0x1800157d8`
- `0x18001ba40`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180015823`
- `ole32!CoTaskMemFree` at `0x180015823`
- `OLEAUT32!__imp_VariantClear` at `0x18001580f`
- `OLEAUT32!__imp_VariantClear` at `0x18001580f`

## pseudocode

```c
void __fastcall CEnumItemProperties::~CEnumItemProperties(CEnumItemProperties *this)
{
  bool v1; // zf
  unsigned int i; // esi
  __int64 v4; // rbx
  void *v5; // rcx

  v1 = *((_QWORD *)this + 3) == 0;
  *(_QWORD *)this = &CEnumItemProperties::`vftable';
  if ( !v1 )
  {
    for ( i = 0; i < *((_DWORD *)this + 4); ++i )
    {
      v4 = 32LL * i;
      VariantClear((VARIANTARG *)(v4 + *((_QWORD *)this + 3)));
      v5 = *(void **)(*((_QWORD *)this + 3) + v4 + 24);
      if ( v5 )
        CoTaskMemFree(v5);
    }
    operator delete(*((void **)this + 3));
  }
  _InterlockedDecrement((volatile signed __int32 *)&g_cObj);
}

```

## disassembly

```asm
0x1800157d8  mov     [rsp+arg_0], rbx
0x1800157dd  mov     [rsp+arg_8], rsi
0x1800157e2  push    rdi
0x1800157e3  sub     rsp, 20h
0x1800157e7  cmp     qword ptr [rcx+18h], 0
0x1800157ec  lea     rax, ??_7CEnumItemProperties@@6B@; const CEnumItemProperties::`vftable'
0x1800157f3  mov     [rcx], rax
0x1800157f6  mov     rdi, rcx
0x1800157f9  jz      short loc_180015839
0x1800157fb  xor     esi, esi
0x1800157fd  cmp     [rcx+10h], esi
0x180015800  jbe     short loc_180015830
0x180015802  mov     rcx, [rdi+18h]
0x180015806  mov     ebx, esi
0x180015808  shl     rbx, 5
0x18001580c  add     rcx, rbx; pvarg
0x18001580f  call    cs:__imp_VariantClear
0x180015815  mov     rax, [rdi+18h]
0x180015819  mov     rcx, [rax+rbx+18h]; pv
0x18001581e  test    rcx, rcx
0x180015821  jz      short loc_180015829
0x180015823  call    cs:__imp_CoTaskMemFree
0x180015829  inc     esi
0x18001582b  cmp     esi, [rdi+10h]
0x18001582e  jb      short loc_180015802
0x180015830  mov     rcx, [rdi+18h]; lpMem
0x180015834  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180015839  lock dec cs:?g_cObj@@3KA; ulong g_cObj
0x180015840  mov     rbx, [rsp+28h+arg_0]
0x180015845  mov     rsi, [rsp+28h+arg_8]
0x18001584a  add     rsp, 20h
0x18001584e  pop     rdi
0x18001584f  retn
```
