# _attribute_t::_attribute_t(bool,ushort const *)

- ea: `0x180002d4c`
- end: `0x180002da5`
- name: `??0_attribute_t@@QEAA@_NPEBG@Z`
- size: `89`
- prototype: `_attribute_t *__fastcall(unsigned __int16 **this, bool, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180005b30`

## callees

- `0x18000ca0c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180002d65`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180002d65`

## pseudocode

```c
_attribute_t *__fastcall _attribute_t::_attribute_t(_attribute_t *this, unsigned __int8 a2, const unsigned __int16 *a3)
{
  int v4; // ebx
  _attribute_t *result; // rax

  *(_QWORD *)this = 0;
  v4 = a2;
  CoTaskMemFree(0);
  *(_QWORD *)this = 0;
  StringCchCopyWithAlloc((unsigned __int16 **)this, 0xFFFF, L"BehindProxy");
  *((_DWORD *)this + 4) = v4;
  result = this;
  *((_DWORD *)this + 2) = 1;
  return result;
}

```

## disassembly

```asm
0x180002d4c  mov     [rsp+arg_0], rbx
0x180002d51  push    rdi
0x180002d52  sub     rsp, 20h
0x180002d56  mov     rdi, rcx
0x180002d59  mov     qword ptr [rcx], 0
0x180002d60  xor     ecx, ecx; pv
0x180002d62  movzx   ebx, dl
0x180002d65  call    cs:__imp_CoTaskMemFree
0x180002d6c  nop     dword ptr [rax+rax+00h]
0x180002d71  lea     r8, aBehindproxy; "BehindProxy"
0x180002d78  mov     qword ptr [rdi], 0
0x180002d7f  mov     edx, 0FFFFh; unsigned __int64
0x180002d84  mov     rcx, rdi; unsigned __int16 **
0x180002d87  call    ?StringCchCopyWithAlloc@@YAJPEAPEAG_KPEBG@Z; StringCchCopyWithAlloc(ushort * *,unsigned __int64,ushort const *)
0x180002d8c  mov     [rdi+10h], ebx
0x180002d8f  mov     rax, rdi
0x180002d92  mov     rbx, [rsp+28h+arg_0]
0x180002d97  mov     dword ptr [rdi+8], 1
0x180002d9e  add     rsp, 20h
0x180002da2  pop     rdi
0x180002da3  retn
```
