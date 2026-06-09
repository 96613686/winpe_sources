# _hypothesis_builder::Create(ushort const *,_attribute_t &)

- ea: `0x180012940`
- end: `0x1800129e2`
- name: `?Create@_hypothesis_builder@@QEAAJPEBGAEAV_attribute_t@@@Z`
- size: `162`
- prototype: `__int64 __fastcall(_hypothesis_builder *__hidden this, const unsigned __int16 *, struct tagHELPER_ATTRIBUTE *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x180005b30`

## callees

- `0x180004330`
- `0x180004b38`
- `0x18000ca0c`
- `0x180012940`
- `0x180012b74`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001296c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001296c`

## pseudocode

```c
__int64 __fastcall _hypothesis_builder::Create(
        _hypothesis_builder *this,
        const unsigned __int16 *a2,
        struct tagHELPER_ATTRIBUTE *a3)
{
  __int64 result; // rax
  int v7; // ebx

  if ( !a2 )
    return 2147942487LL;
  _hypothesis_builder::FreeAll((LPVOID *)this);
  CoTaskMemFree(*(LPVOID *)this);
  *(_QWORD *)this = 0;
  result = StringCchCopyWithAlloc((unsigned __int16 **)this, 0xFFFF, a2);
  if ( (int)result >= 0 )
  {
    v7 = _hypothesis_builder::SetCount(this, 1u);
    if ( v7 >= 0 )
    {
      if ( a3->type && a3->pwszName )
      {
        _attribute_t::Copy(*((struct tagHELPER_ATTRIBUTE **)this + 3), a3);
        return 0;
      }
      v7 = -2147024809;
    }
    _hypothesis_builder::FreeAll((LPVOID *)this);
    return (unsigned int)v7;
  }
  return result;
}

```

## disassembly

```asm
0x180012940  mov     [rsp+arg_0], rbx
0x180012945  mov     [rsp+arg_8], rsi
0x18001294a  push    rdi
0x18001294b  sub     rsp, 20h
0x18001294f  mov     rsi, r8
0x180012952  mov     rbx, rdx
0x180012955  mov     rdi, rcx
0x180012958  test    rdx, rdx
0x18001295b  jnz     short loc_180012964
0x18001295d  mov     eax, 80070057h
0x180012962  jmp     short loc_1800129D1
0x180012964  call    ?FreeAll@_hypothesis_builder@@QEAAXXZ; _hypothesis_builder::FreeAll(void)
0x180012969  mov     rcx, [rdi]; pv
0x18001296c  call    cs:__imp_CoTaskMemFree
0x180012973  nop     dword ptr [rax+rax+00h]
0x180012978  mov     r8, rbx; unsigned __int16 *
0x18001297b  mov     qword ptr [rdi], 0
0x180012982  mov     edx, 0FFFFh; unsigned __int64
0x180012987  mov     rcx, rdi; unsigned __int16 **
0x18001298a  call    ?StringCchCopyWithAlloc@@YAJPEAPEAG_KPEBG@Z; StringCchCopyWithAlloc(ushort * *,unsigned __int64,ushort const *)
0x18001298f  test    eax, eax
0x180012991  js      short loc_1800129D1
0x180012993  mov     edx, 1; unsigned int
0x180012998  mov     rcx, rdi; this
0x18001299b  call    ?SetCount@_hypothesis_builder@@QEAAJK@Z; _hypothesis_builder::SetCount(ulong)
0x1800129a0  mov     ebx, eax
0x1800129a2  test    eax, eax
0x1800129a4  js      short loc_1800129C7
0x1800129a6  cmp     dword ptr [rsi+8], 0
0x1800129aa  jz      short loc_1800129C2
0x1800129ac  cmp     qword ptr [rsi], 0
0x1800129b0  jz      short loc_1800129C2
0x1800129b2  mov     rcx, [rdi+18h]; this
0x1800129b6  mov     rdx, rsi; struct tagHELPER_ATTRIBUTE *
0x1800129b9  call    ?Copy@_attribute_t@@QEAAJPEBUtagHELPER_ATTRIBUTE@@@Z; _attribute_t::Copy(tagHELPER_ATTRIBUTE const *)
0x1800129be  xor     eax, eax
0x1800129c0  jmp     short loc_1800129D1
0x1800129c2  mov     ebx, 80070057h
0x1800129c7  mov     rcx, rdi; this
0x1800129ca  call    ?FreeAll@_hypothesis_builder@@QEAAXXZ; _hypothesis_builder::FreeAll(void)
0x1800129cf  mov     eax, ebx
0x1800129d1  mov     rbx, [rsp+28h+arg_0]
0x1800129d6  mov     rsi, [rsp+28h+arg_8]
0x1800129db  add     rsp, 20h
0x1800129df  pop     rdi
0x1800129e0  retn
```
