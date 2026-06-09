# _attribute_t::_attribute_t(tagOCTET_STRING const &,ushort const *)

- ea: `0x180002c54`
- end: `0x180002cc4`
- name: `??0_attribute_t@@QEAA@AEBUtagOCTET_STRING@@PEBG@Z`
- size: `112`
- prototype: `_attribute_t *__fastcall(unsigned __int16 **this, const struct tagOCTET_STRING *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180005b30`

## callees

- `0x18000c764`
- `0x18000ca0c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180002c6d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180002c6d`

## pseudocode

```c
_attribute_t *__fastcall _attribute_t::_attribute_t(
        _attribute_t *this,
        const struct tagOCTET_STRING *a2,
        const unsigned __int16 *a3)
{
  *(_QWORD *)this = 0;
  CoTaskMemFree(0);
  *(_QWORD *)this = 0;
  StringCchCopyWithAlloc((unsigned __int16 **)this, 0xFFFF, L"userid");
  *((_DWORD *)this + 2) = 14;
  *((_DWORD *)this + 4) = 0;
  *((_QWORD *)this + 3) = 0;
  _attribute_t::SetValue((LPVOID *)this, a2);
  return this;
}

```

## disassembly

```asm
0x180002c54  mov     [rsp+arg_0], rbx
0x180002c59  push    rdi
0x180002c5a  sub     rsp, 20h
0x180002c5e  mov     rdi, rcx
0x180002c61  mov     qword ptr [rcx], 0
0x180002c68  xor     ecx, ecx; pv
0x180002c6a  mov     rbx, rdx
0x180002c6d  call    cs:__imp_CoTaskMemFree
0x180002c74  nop     dword ptr [rax+rax+00h]
0x180002c79  lea     r8, aUserid; "userid"
0x180002c80  mov     qword ptr [rdi], 0
0x180002c87  mov     edx, 0FFFFh; unsigned __int64
0x180002c8c  mov     rcx, rdi; unsigned __int16 **
0x180002c8f  call    ?StringCchCopyWithAlloc@@YAJPEAPEAG_KPEBG@Z; StringCchCopyWithAlloc(ushort * *,unsigned __int64,ushort const *)
0x180002c94  mov     rdx, rbx; struct tagOCTET_STRING *
0x180002c97  mov     dword ptr [rdi+8], 0Eh
0x180002c9e  mov     rcx, rdi; this
0x180002ca1  mov     dword ptr [rdi+10h], 0
0x180002ca8  mov     qword ptr [rdi+18h], 0
0x180002cb0  call    ?SetValue@_attribute_t@@QEAAJPEBUtagOCTET_STRING@@@Z; _attribute_t::SetValue(tagOCTET_STRING const *)
0x180002cb5  mov     rbx, [rsp+28h+arg_0]
0x180002cba  mov     rax, rdi
0x180002cbd  add     rsp, 20h
0x180002cc1  pop     rdi
0x180002cc2  retn
```
