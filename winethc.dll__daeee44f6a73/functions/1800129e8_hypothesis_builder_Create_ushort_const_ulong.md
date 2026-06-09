# _hypothesis_builder::Create(ushort const *,ulong)

- ea: `0x1800129e8`
- end: `0x180012a56`
- name: `?Create@_hypothesis_builder@@QEAAJPEBGK@Z`
- size: `110`
- prototype: `__int64 __fastcall(_hypothesis_builder *__hidden this, const unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x180005b30`

## callees

- `0x180004b38`
- `0x18000ca0c`
- `0x1800129e8`
- `0x180012b74`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180012a14`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180012a14`

## pseudocode

```c
__int64 __fastcall _hypothesis_builder::Create(LPVOID *this, const unsigned __int16 *a2, unsigned int a3)
{
  __int64 result; // rax

  if ( !a2 )
    return 2147942487LL;
  _hypothesis_builder::FreeAll(this);
  CoTaskMemFree(*this);
  *this = 0;
  result = StringCchCopyWithAlloc((unsigned __int16 **)this, 0xFFFF, a2);
  if ( (int)result >= 0 )
    return _hypothesis_builder::SetCount((_hypothesis_builder *)this, a3);
  return result;
}

```

## disassembly

```asm
0x1800129e8  mov     [rsp+arg_0], rbx
0x1800129ed  mov     [rsp+arg_8], rsi
0x1800129f2  push    rdi
0x1800129f3  sub     rsp, 20h
0x1800129f7  mov     esi, r8d
0x1800129fa  mov     rdi, rdx
0x1800129fd  mov     rbx, rcx
0x180012a00  test    rdx, rdx
0x180012a03  jnz     short loc_180012A0C
0x180012a05  mov     eax, 80070057h
0x180012a0a  jmp     short loc_180012A45
0x180012a0c  call    ?FreeAll@_hypothesis_builder@@QEAAXXZ; _hypothesis_builder::FreeAll(void)
0x180012a11  mov     rcx, [rbx]; pv
0x180012a14  call    cs:__imp_CoTaskMemFree
0x180012a1b  nop     dword ptr [rax+rax+00h]
0x180012a20  mov     r8, rdi; unsigned __int16 *
0x180012a23  mov     qword ptr [rbx], 0
0x180012a2a  mov     edx, 0FFFFh; unsigned __int64
0x180012a2f  mov     rcx, rbx; unsigned __int16 **
0x180012a32  call    ?StringCchCopyWithAlloc@@YAJPEAPEAG_KPEBG@Z; StringCchCopyWithAlloc(ushort * *,unsigned __int64,ushort const *)
0x180012a37  test    eax, eax
0x180012a39  js      short loc_180012A45
0x180012a3b  mov     edx, esi; unsigned int
0x180012a3d  mov     rcx, rbx; this
0x180012a40  call    ?SetCount@_hypothesis_builder@@QEAAJK@Z; _hypothesis_builder::SetCount(ulong)
0x180012a45  mov     rbx, [rsp+28h+arg_0]
0x180012a4a  mov     rsi, [rsp+28h+arg_8]
0x180012a4f  add     rsp, 20h
0x180012a53  pop     rdi
0x180012a54  retn
```
