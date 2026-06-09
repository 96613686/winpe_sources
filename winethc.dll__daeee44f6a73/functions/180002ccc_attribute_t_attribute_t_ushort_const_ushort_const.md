# _attribute_t::_attribute_t(ushort const *,ushort const *)

- ea: `0x180002ccc`
- end: `0x180002d43`
- name: `??0_attribute_t@@QEAA@PEBG0@Z`
- size: `119`
- prototype: `_attribute_t *__fastcall(_attribute_t *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180005b30`

## callees

- `0x180002ccc`
- `0x18000c6cc`
- `0x18000ca0c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180002ced`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180002ced`

## pseudocode

```c
_attribute_t *__fastcall _attribute_t::_attribute_t(
        _attribute_t *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  *(_QWORD *)this = 0;
  CoTaskMemFree(0);
  *(_QWORD *)this = 0;
  if ( a3 )
    StringCchCopyWithAlloc((unsigned __int16 **)this, 0xFFFF, a3);
  *((_DWORD *)this + 2) = 10;
  *((_QWORD *)this + 2) = 0;
  _attribute_t::SetValue((LPVOID *)this, a2);
  return this;
}

```

## disassembly

```asm
0x180002ccc  mov     [rsp+arg_0], rbx
0x180002cd1  mov     [rsp+arg_8], rsi
0x180002cd6  push    rdi
0x180002cd7  sub     rsp, 20h
0x180002cdb  mov     rbx, rcx
0x180002cde  mov     qword ptr [rcx], 0
0x180002ce5  xor     ecx, ecx; pv
0x180002ce7  mov     rdi, r8
0x180002cea  mov     rsi, rdx
0x180002ced  call    cs:__imp_CoTaskMemFree
0x180002cf4  nop     dword ptr [rax+rax+00h]
0x180002cf9  mov     qword ptr [rbx], 0
0x180002d00  test    rdi, rdi
0x180002d03  jz      short loc_180002D15
0x180002d05  mov     r8, rdi; unsigned __int16 *
0x180002d08  mov     edx, 0FFFFh; unsigned __int64
0x180002d0d  mov     rcx, rbx; unsigned __int16 **
0x180002d10  call    ?StringCchCopyWithAlloc@@YAJPEAPEAG_KPEBG@Z; StringCchCopyWithAlloc(ushort * *,unsigned __int64,ushort const *)
0x180002d15  mov     rdx, rsi; unsigned __int16 *
0x180002d18  mov     dword ptr [rbx+8], 0Ah
0x180002d1f  mov     rcx, rbx; this
0x180002d22  mov     qword ptr [rbx+10h], 0
0x180002d2a  call    ?SetValue@_attribute_t@@QEAAJPEBG@Z; _attribute_t::SetValue(ushort const *)
0x180002d2f  mov     rsi, [rsp+28h+arg_8]
0x180002d34  mov     rax, rbx
0x180002d37  mov     rbx, [rsp+28h+arg_0]
0x180002d3c  add     rsp, 20h
0x180002d40  pop     rdi
0x180002d41  retn
```
