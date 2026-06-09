# AutoVariantRef::~AutoVariantRef(void)

- ea: `0x1800051f0`
- end: `0x180005245`
- name: `??1AutoVariantRef@@QEAA@XZ`
- size: `85`
- prototype: `void __fastcall(VARIANTARG *pvarg)`
- caller_count: `4`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x180004a50`
- `0x180006550`
- `0x1800079a0`
- `0x180007a10`

## callees

- `0x1800049d4`
- `0x1800051f0`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x180005238`
- `OLEAUT32!__imp_VariantInit` at `0x180005238`
- `OLE32!CoTaskMemFree` at `0x180005226`
- `OLE32!CoTaskMemFree` at `0x180005226`

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
0x1800051f0  push    rbx
0x1800051f2  sub     rsp, 20h
0x1800051f6  cmp     word ptr [rcx], 0
0x1800051fa  mov     rbx, rcx
0x1800051fd  jnz     short loc_180005205
0x1800051ff  add     rsp, 20h
0x180005203  pop     rbx
0x180005204  retn
0x180005205  mov     [rsp+28h+arg_0], rdi
0x18000520a  mov     rdi, [rcx+18h]
0x18000520e  test    rdi, rdi
0x180005211  jz      short loc_180005235
0x180005213  mov     rax, [rdi]
0x180005216  lea     rcx, [rdi+8]; this
0x18000521a  mov     [rbx+18h], rax
0x18000521e  call    ?Unpin@PinnableData@AutoVariantRef@@QEAAXXZ; AutoVariantRef::PinnableData::Unpin(void)
0x180005223  mov     rcx, rdi; pv
0x180005226  call    cs:__imp_CoTaskMemFree
0x18000522c  mov     rdi, [rbx+18h]
0x180005230  test    rdi, rdi
0x180005233  jnz     short loc_180005213
0x180005235  mov     rcx, rbx; pvarg
0x180005238  call    cs:__imp_VariantInit
0x18000523e  mov     rdi, [rsp+28h+arg_0]
0x180005243  jmp     short loc_1800051FF
```
