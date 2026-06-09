# AutoVariantRef::~AutoVariantRef(void)

- ea: `0x180002fc0`
- end: `0x180003022`
- name: `??1AutoVariantRef@@QEAA@XZ`
- size: `98`
- prototype: `void __fastcall(VARIANTARG *pvarg)`
- caller_count: `4`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x180002f40`
- `0x180004400`
- `0x1800059f0`
- `0x180005a60`

## callees

- `0x180002ebc`
- `0x180002fc0`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x18000300f`
- `OLEAUT32!__imp_VariantInit` at `0x18000300f`
- `OLE32!CoTaskMemFree` at `0x180002ff7`
- `OLE32!CoTaskMemFree` at `0x180002ff7`

## pseudocode

```c
void __fastcall AutoVariantRef::~AutoVariantRef(VARIANTARG *pvarg)
{
  _QWORD *i; // rdi

  if ( pvarg->vt )
  {
    for ( i = *(_QWORD **)&pvarg[1].vt; i; i = *(_QWORD **)&pvarg[1].vt )
    {
      *(_QWORD *)&pvarg[1].vt = *i;
      AutoVariantRef::PinnableData::Unpin((AutoVariantRef::PinnableData *)(i + 1));
      CoTaskMemFree(i);
    }
    VariantInit(pvarg);
  }
}

```

## disassembly

```asm
0x180002fc0  push    rbx
0x180002fc2  sub     rsp, 20h
0x180002fc6  cmp     word ptr [rcx], 0
0x180002fca  mov     rbx, rcx
0x180002fcd  jnz     short loc_180002FD6
0x180002fcf  add     rsp, 20h
0x180002fd3  pop     rbx
0x180002fd4  retn
0x180002fd6  mov     [rsp+28h+arg_0], rdi
0x180002fdb  mov     rdi, [rcx+18h]
0x180002fdf  test    rdi, rdi
0x180002fe2  jz      short loc_18000300C
0x180002fe4  mov     rax, [rdi]
0x180002fe7  lea     rcx, [rdi+8]; this
0x180002feb  mov     [rbx+18h], rax
0x180002fef  call    ?Unpin@PinnableData@AutoVariantRef@@QEAAXXZ; AutoVariantRef::PinnableData::Unpin(void)
0x180002ff4  mov     rcx, rdi; pv
0x180002ff7  call    cs:__imp_CoTaskMemFree
0x180002ffe  nop     dword ptr [rax+rax+00h]
0x180003003  mov     rdi, [rbx+18h]
0x180003007  test    rdi, rdi
0x18000300a  jnz     short loc_180002FE4
0x18000300c  mov     rcx, rbx; pvarg
0x18000300f  call    cs:__imp_VariantInit
0x180003016  nop     dword ptr [rax+rax+00h]
0x18000301b  mov     rdi, [rsp+28h+arg_0]
0x180003020  jmp     short loc_180002FCF
```
