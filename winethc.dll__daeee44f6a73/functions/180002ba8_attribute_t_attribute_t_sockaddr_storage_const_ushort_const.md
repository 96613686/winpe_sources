# _attribute_t::_attribute_t(sockaddr_storage const &,ushort const *)

- ea: `0x180002ba8`
- end: `0x180002c4e`
- name: `??0_attribute_t@@QEAA@AEBUsockaddr_storage@@PEBG@Z`
- size: `166`
- prototype: `_attribute_t *__fastcall(unsigned __int16 **this, const struct sockaddr_storage *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180005b30`

## callees

- `0x180002ba8`
- `0x18000ca0c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180002bc9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180002bc9`

## pseudocode

```c
_attribute_t *__fastcall _attribute_t::_attribute_t(
        _attribute_t *this,
        const struct sockaddr_storage *a2,
        const unsigned __int16 *a3)
{
  _attribute_t *result; // rax

  *(_QWORD *)this = 0;
  CoTaskMemFree(0);
  *(_QWORD *)this = 0;
  if ( a3 )
    StringCchCopyWithAlloc((unsigned __int16 **)this, 0xFFFF, a3);
  result = this;
  *((_DWORD *)this + 2) = 13;
  *((_OWORD *)this + 1) = *(_OWORD *)&a2->ss_family;
  *((_OWORD *)this + 2) = *(_OWORD *)a2->__ss_pad2;
  *((_OWORD *)this + 3) = *(_OWORD *)&a2->__ss_pad2[16];
  *((_OWORD *)this + 4) = *(_OWORD *)&a2->__ss_pad2[32];
  *((_OWORD *)this + 5) = *(_OWORD *)&a2->__ss_pad2[48];
  *((_OWORD *)this + 6) = *(_OWORD *)&a2->__ss_pad2[64];
  *((_OWORD *)this + 7) = *(_OWORD *)&a2->__ss_pad2[80];
  *((_OWORD *)this + 8) = *(_OWORD *)&a2->__ss_pad2[96];
  return result;
}

```

## disassembly

```asm
0x180002ba8  mov     [rsp+arg_0], rbx
0x180002bad  mov     [rsp+arg_8], rsi
0x180002bb2  push    rdi
0x180002bb3  sub     rsp, 20h
0x180002bb7  mov     rbx, rcx
0x180002bba  mov     qword ptr [rcx], 0
0x180002bc1  xor     ecx, ecx; pv
0x180002bc3  mov     rsi, r8
0x180002bc6  mov     rdi, rdx
0x180002bc9  call    cs:__imp_CoTaskMemFree
0x180002bd0  nop     dword ptr [rax+rax+00h]
0x180002bd5  mov     qword ptr [rbx], 0
0x180002bdc  test    rsi, rsi
0x180002bdf  jz      short loc_180002BF1
0x180002be1  mov     r8, rsi; unsigned __int16 *
0x180002be4  mov     edx, 0FFFFh; unsigned __int64
0x180002be9  mov     rcx, rbx; unsigned __int16 **
0x180002bec  call    ?StringCchCopyWithAlloc@@YAJPEAPEAG_KPEBG@Z; StringCchCopyWithAlloc(ushort * *,unsigned __int64,ushort const *)
0x180002bf1  mov     rsi, [rsp+28h+arg_8]
0x180002bf6  mov     rax, rbx
0x180002bf9  mov     dword ptr [rbx+8], 0Dh
0x180002c00  movups  xmm0, xmmword ptr [rdi]
0x180002c03  movups  xmmword ptr [rbx+10h], xmm0
0x180002c07  movups  xmm1, xmmword ptr [rdi+10h]
0x180002c0b  movups  xmmword ptr [rbx+20h], xmm1
0x180002c0f  movups  xmm0, xmmword ptr [rdi+20h]
0x180002c13  movups  xmmword ptr [rbx+30h], xmm0
0x180002c17  movups  xmm1, xmmword ptr [rdi+30h]
0x180002c1b  movups  xmmword ptr [rbx+40h], xmm1
0x180002c1f  movups  xmm0, xmmword ptr [rdi+40h]
0x180002c23  movups  xmmword ptr [rbx+50h], xmm0
0x180002c27  movups  xmm1, xmmword ptr [rdi+50h]
0x180002c2b  movups  xmmword ptr [rbx+60h], xmm1
0x180002c2f  movups  xmm0, xmmword ptr [rdi+60h]
0x180002c33  movups  xmmword ptr [rbx+70h], xmm0
0x180002c37  movups  xmm1, xmmword ptr [rdi+70h]
0x180002c3b  movups  xmmword ptr [rbx+80h], xmm1
0x180002c42  mov     rbx, [rsp+28h+arg_0]
0x180002c47  add     rsp, 20h
0x180002c4b  pop     rdi
0x180002c4c  retn
```
