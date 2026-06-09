# AutoCalloutParameterLock::Clear(void)

- ea: `0x180002f40`
- end: `0x180002fba`
- name: `?Clear@AutoCalloutParameterLock@@QEAAXXZ`
- size: `122`
- prototype: `void __fastcall(AutoCalloutParameterLock *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x180004400`

## callees

- `0x180002f40`
- `0x180002fc0`

## import_xrefs

- `OLE32!CoTaskMemFree` at `0x180002fac`
- `OLE32!CoTaskMemFree` at `0x180002fac`

## pseudocode

```c
void __fastcall AutoCalloutParameterLock::Clear(AutoCalloutParameterLock *this)
{
  __int64 v1; // rax
  unsigned int v3; // edi
  char *v4; // rcx

  v1 = *((_QWORD *)this + 1);
  if ( v1 )
    *(_QWORD *)(v1 + 56) = **(_QWORD **)(v1 + 56);
  if ( *((_DWORD *)this + 6) )
  {
    v3 = 0;
    do
      AutoVariantRef::~AutoVariantRef((VARIANTARG *)(*((_QWORD *)this + 2) + 32LL * v3++));
    while ( v3 < *((_DWORD *)this + 6) );
    v4 = (char *)*((_QWORD *)this + 2);
    if ( v4 )
    {
      if ( v4 != (char *)this + 32 )
        CoTaskMemFree(v4);
    }
    *((_DWORD *)this + 6) = 0;
  }
}

```

## disassembly

```asm
0x180002f40  push    rbx
0x180002f42  sub     rsp, 20h
0x180002f46  mov     rax, [rcx+8]
0x180002f4a  mov     rbx, rcx
0x180002f4d  test    rax, rax
0x180002f50  jz      short loc_180002F5D
0x180002f52  mov     rdx, [rax+38h]
0x180002f56  mov     r8, [rdx]
0x180002f59  mov     [rax+38h], r8
0x180002f5d  mov     eax, [rcx+18h]
0x180002f60  test    eax, eax
0x180002f62  jnz     short loc_180002F6B
0x180002f64  add     rsp, 20h
0x180002f68  pop     rbx
0x180002f69  retn
0x180002f6b  mov     [rsp+28h+arg_0], rdi
0x180002f70  xor     edi, edi
0x180002f72  test    eax, eax
0x180002f74  jz      short loc_180002F8C
0x180002f76  mov     ecx, edi
0x180002f78  shl     rcx, 5
0x180002f7c  add     rcx, [rbx+10h]; pvarg
0x180002f80  call    ??1AutoVariantRef@@QEAA@XZ; AutoVariantRef::~AutoVariantRef(void)
0x180002f85  inc     edi
0x180002f87  cmp     edi, [rbx+18h]
0x180002f8a  jb      short loc_180002F76
0x180002f8c  mov     rcx, [rbx+10h]; pv
0x180002f90  mov     rdi, [rsp+28h+arg_0]
0x180002f95  test    rcx, rcx
0x180002f98  jnz     short loc_180002FA3
0x180002f9a  mov     dword ptr [rbx+18h], 0
0x180002fa1  jmp     short loc_180002F64
0x180002fa3  lea     rax, [rbx+20h]
0x180002fa7  cmp     rcx, rax
0x180002faa  jz      short loc_180002F9A
0x180002fac  call    cs:__imp_CoTaskMemFree
0x180002fb3  nop     dword ptr [rax+rax+00h]
0x180002fb8  jmp     short loc_180002F9A
```
