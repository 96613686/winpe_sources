# web::json::value::value(void)

- ea: `0x1800296cc`
- end: `0x1800296ff`
- name: `??0value@json@web@@QEAA@XZ`
- size: `51`
- prototype: `web::json::value *__fastcall(web::json::value *this)`
- caller_count: `9`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18000af34`
- `0x1800297a0`
- `0x18002afd8`
- `0x18002b170`
- `0x180032760`
- `0x180032b3c`
- `0x180032fc8`
- `0x180035cb0`
- `0x180038884`

## callees

- `0x180042bfc`

## pseudocode

```c
web::json::value *__fastcall web::json::value::value(web::json::value *this)
{
  _QWORD *v3; // [rsp+20h] [rbp-18h]

  v3 = operator new(8u);
  *v3 = &web::json::details::_Null::`vftable';
  *(_QWORD *)this = v3;
  return this;
}

```

## disassembly

```asm
0x1800296cc  push    rbx
0x1800296ce  sub     rsp, 30h
0x1800296d2  mov     rbx, rcx
0x1800296d5  mov     [rsp+38h+var_18], rcx
0x1800296da  mov     ecx, 8; Size
0x1800296df  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800296e4  lea     rcx, ??_7_Null@details@json@web@@6B@; const web::json::details::_Null::`vftable'
0x1800296eb  mov     [rsp+38h+var_18], rax
0x1800296f0  mov     [rax], rcx
0x1800296f3  mov     [rbx], rax
0x1800296f6  mov     rax, rbx
0x1800296f9  add     rsp, 30h
0x1800296fd  pop     rbx
0x1800296fe  retn
```
