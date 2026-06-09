# SAXAttributesBase::setURI(int,wchar_t *)

- ea: `0x100414f70`
- end: `0x100414fd3`
- name: `?setURI@SAXAttributesBase@@UEAAJHPEA_W@Z`
- size: `99`
- prototype: `int(SAXAttributesBase *__hidden this, int, wchar_t *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1004141e0`
- `0x100414f70`

## import_xrefs

- `OLEAUT32!__imp_SysStringLen` at `0x100414f9c`
- `OLEAUT32!__imp_SysStringLen` at `0x100414f9c`

## pseudocode

```c
int __fastcall SAXAttributesBase::setURI(SAXAttributesBase *this, int a2, wchar_t *a3)
{
  int v5; // ebx
  UINT v6; // eax

  if ( a2 < 0 || a2 >= *((_DWORD *)this + 12) || !a3 )
    return -2147024809;
  _mm_lfence();
  v5 = 5 * a2;
  v6 = SysStringLen(a3);
  return SAXAttributesBase::allocWCHAR((SAXAttributesBase *)((char *)this - 16), a3, v6, v5);
}

```

## disassembly

```asm
0x100414f70  mov     [rsp+arg_8], rsi
0x100414f75  push    rdi
0x100414f76  sub     rsp, 20h
0x100414f7a  mov     rdi, r8
0x100414f7d  mov     rsi, rcx
0x100414f80  test    edx, edx
0x100414f82  js      short loc_100414FC3
0x100414f84  cmp     edx, [rcx+30h]
0x100414f87  jge     short loc_100414FC3
0x100414f89  test    r8, r8
0x100414f8c  jz      short loc_100414FC3
0x100414f8e  mov     [rsp+28h+arg_0], rbx
0x100414f93  lfence
0x100414f96  mov     rcx, r8; pbstr
0x100414f99  lea     ebx, [rdx+rdx*4]
0x100414f9c  call    cs:__imp_SysStringLen
0x100414fa2  lea     rcx, [rsi-10h]; this
0x100414fa6  mov     r9d, ebx; int
0x100414fa9  mov     r8d, eax; int
0x100414fac  mov     rdx, rdi; wchar_t *
0x100414faf  mov     rbx, [rsp+28h+arg_0]
0x100414fb4  mov     rsi, [rsp+28h+arg_8]
0x100414fb9  add     rsp, 20h
0x100414fbd  pop     rdi
0x100414fbe  jmp     ?allocWCHAR@SAXAttributesBase@@AEAAJPEB_WHH@Z; SAXAttributesBase::allocWCHAR(wchar_t const *,int,int)
0x100414fc3  mov     eax, 80070057h
0x100414fc8  mov     rsi, [rsp+28h+arg_8]
0x100414fcd  add     rsp, 20h
0x100414fd1  pop     rdi
0x100414fd2  retn
```
