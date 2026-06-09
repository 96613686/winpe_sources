# _hypothesis_builder::~_hypothesis_builder(void)

- ea: `0x1800032ec`
- end: `0x18000334f`
- name: `??1_hypothesis_builder@@QEAA@XZ`
- size: `99`
- prototype: `void __fastcall(_hypothesis_builder *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180005b30`

## callees

- `0x1800032ec`
- `0x180004ac4`
- `0x180004b38`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003328`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003328`

## pseudocode

```c
void __fastcall _hypothesis_builder::~_hypothesis_builder(LPVOID *this)
{
  __int64 i; // rdi

  _hypothesis_builder::FreeAll(this);
  if ( this[3] )
  {
    for ( i = 0; (unsigned int)i < *((_DWORD *)this + 4); i = (unsigned int)(i + 1) )
      _attribute_t::FreeAll((LPVOID *)this[3] + 18 * i);
  }
  CoTaskMemFree(this[3]);
  this[3] = 0;
  *((_DWORD *)this + 4) = 0;
}

```

## disassembly

```asm
0x1800032ec  mov     [rsp+arg_0], rbx
0x1800032f1  push    rdi
0x1800032f2  sub     rsp, 20h
0x1800032f6  mov     rbx, rcx
0x1800032f9  call    ?FreeAll@_hypothesis_builder@@QEAAXXZ; _hypothesis_builder::FreeAll(void)
0x1800032fe  cmp     qword ptr [rbx+18h], 0
0x180003303  jz      short loc_180003324
0x180003305  xor     edi, edi
0x180003307  cmp     [rbx+10h], edi
0x18000330a  jbe     short loc_180003324
0x18000330c  lea     rcx, [rdi+rdi*8]
0x180003310  shl     rcx, 4
0x180003314  add     rcx, [rbx+18h]; this
0x180003318  call    ?FreeAll@_attribute_t@@QEAAXXZ; _attribute_t::FreeAll(void)
0x18000331d  inc     edi
0x18000331f  cmp     edi, [rbx+10h]
0x180003322  jb      short loc_18000330C
0x180003324  mov     rcx, [rbx+18h]; pv
0x180003328  call    cs:__imp_CoTaskMemFree
0x18000332f  nop     dword ptr [rax+rax+00h]
0x180003334  mov     qword ptr [rbx+18h], 0
0x18000333c  mov     dword ptr [rbx+10h], 0
0x180003343  mov     rbx, [rsp+28h+arg_0]
0x180003348  add     rsp, 20h
0x18000334c  pop     rdi
0x18000334d  retn
```
