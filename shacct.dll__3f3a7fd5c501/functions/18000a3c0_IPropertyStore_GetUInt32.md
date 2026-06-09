# IPropertyStore_GetUInt32

- ea: `0x18000a3c0`
- end: `0x18000a427`
- name: `IPropertyStore_GetUInt32`
- size: `103`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000b410`
- `0x18000ef58`
- `0x180010a3c`
- `0x1800139c0`

## callees

- `0x18000a3c0`
- `0x180017010`

## import_xrefs

- `PROPSYS!PropVariantToUInt32` at `0x18000a405`
- `PROPSYS!PropVariantToUInt32` at `0x18000a405`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000a419`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000a419`

## pseudocode

```c
__int64 __fastcall IPropertyStore_GetUInt32(__int64 *a1, __int64 a2, ULONG *a3)
{
  __int64 v4; // rax
  __int64 result; // rax
  unsigned int v6; // ebx
  PROPVARIANT propvarIn[2]; // [rsp+20h] [rbp-28h] BYREF
  __int64 v8; // [rsp+30h] [rbp-18h]

  *a3 = 0;
  v8 = 0;
  v4 = *a1;
  *(_OWORD *)propvarIn = 0;
  result = (*(__int64 (__fastcall **)(__int64 *, __int64, PROPVARIANT *))(v4 + 40))(a1, a2, propvarIn);
  if ( (int)result >= 0 )
  {
    if ( LOWORD(propvarIn[0]) )
      v6 = PropVariantToUInt32(propvarIn, a3);
    else
      v6 = -2147023728;
    PropVariantClear(propvarIn);
    return v6;
  }
  return result;
}

```

## disassembly

```asm
0x18000a3c0  push    rbx
0x18000a3c2  sub     rsp, 40h
0x18000a3c6  xor     eax, eax
0x18000a3c8  mov     dword ptr [r8], 0
0x18000a3cf  mov     [rsp+48h+var_18], rax
0x18000a3d4  mov     rbx, r8
0x18000a3d7  mov     rax, [rcx]
0x18000a3da  lea     r8, [rsp+48h+propvarIn]
0x18000a3df  xorps   xmm0, xmm0
0x18000a3e2  movups  xmmword ptr [rsp+48h+propvarIn], xmm0
0x18000a3e7  mov     rax, [rax+28h]
0x18000a3eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a3f0  test    eax, eax
0x18000a3f2  js      short loc_18000A421
0x18000a3f4  xor     eax, eax
0x18000a3f6  cmp     ax, word ptr [rsp+48h+propvarIn]
0x18000a3fb  jz      short loc_18000A40F
0x18000a3fd  mov     rdx, rbx; pulRet
0x18000a400  lea     rcx, [rsp+48h+propvarIn]; propvarIn
0x18000a405  call    cs:__imp_PropVariantToUInt32
0x18000a40b  mov     ebx, eax
0x18000a40d  jmp     short loc_18000A414
0x18000a40f  mov     ebx, 80070490h
0x18000a414  lea     rcx, [rsp+48h+propvarIn]; pvar
0x18000a419  call    cs:__imp_PropVariantClear
0x18000a41f  mov     eax, ebx
0x18000a421  add     rsp, 40h
0x18000a425  pop     rbx
0x18000a426  retn
```
