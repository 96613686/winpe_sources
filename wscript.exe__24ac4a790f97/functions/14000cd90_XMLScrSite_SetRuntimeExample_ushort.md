# XMLScrSite::SetRuntimeExample(ushort *)

- ea: `0x14000cd90`
- end: `0x14000ce44`
- name: `?SetRuntimeExample@XMLScrSite@@UEAAJPEAG@Z`
- size: `180`
- prototype: `__int64 __fastcall(XMLScrSite *__hidden this, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x14000cd90`
- `0x140018010`

## pseudocode

```c
__int64 __fastcall XMLScrSite::SetRuntimeExample(XMLScrSite *this, unsigned __int16 *a2)
{
  __int64 v2; // rax
  int v4; // ebx
  __int64 v6; // [rsp+30h] [rbp+8h] BYREF
  __int64 v7; // [rsp+40h] [rbp+18h] BYREF

  v2 = *((_QWORD *)this + 2);
  v6 = 0;
  v7 = 0;
  v4 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(**(_QWORD **)(v2 + 624) + 128LL))(*(_QWORD *)(v2 + 624), &v6);
  if ( v4 >= 0 )
  {
    v4 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v6)(v6, &IID_IWshRuntime, &v7);
    if ( v4 >= 0 )
      v4 = (*(__int64 (__fastcall **)(__int64, unsigned __int16 *))(*(_QWORD *)v7 + 56LL))(v7, a2);
  }
  if ( v6 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
  if ( v7 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x14000cd90  mov     r11, rsp
0x14000cd93  mov     [r11+10h], rbx
0x14000cd97  push    rdi
0x14000cd98  sub     rsp, 20h
0x14000cd9c  mov     rax, [rcx+10h]
0x14000cda0  mov     rdi, rdx
0x14000cda3  mov     qword ptr [r11+8], 0
0x14000cdab  lea     rdx, [r11+8]
0x14000cdaf  mov     qword ptr [r11+18h], 0
0x14000cdb7  mov     rcx, [rax+270h]
0x14000cdbe  mov     rax, [rcx]
0x14000cdc1  mov     rax, [rax+80h]
0x14000cdc8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000cdcd  mov     ebx, eax
0x14000cdcf  test    eax, eax
0x14000cdd1  js      short loc_14000CE0B
0x14000cdd3  mov     rcx, [rsp+28h+arg_0]
0x14000cdd8  lea     r8, [rsp+28h+arg_10]
0x14000cddd  lea     rdx, ?IID_IWshRuntime@@3U_GUID@@B; _GUID const IID_IWshRuntime
0x14000cde4  mov     rax, [rcx]
0x14000cde7  mov     rax, [rax]
0x14000cdea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000cdef  mov     ebx, eax
0x14000cdf1  test    eax, eax
0x14000cdf3  js      short loc_14000CE0B
0x14000cdf5  mov     rcx, [rsp+28h+arg_10]
0x14000cdfa  mov     rdx, rdi
0x14000cdfd  mov     rax, [rcx]
0x14000ce00  mov     rax, [rax+38h]
0x14000ce04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ce09  mov     ebx, eax
0x14000ce0b  mov     rcx, [rsp+28h+arg_0]
0x14000ce10  test    rcx, rcx
0x14000ce13  jz      short loc_14000CE21
0x14000ce15  mov     rax, [rcx]
0x14000ce18  mov     rax, [rax+10h]
0x14000ce1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ce21  mov     rcx, [rsp+28h+arg_10]
0x14000ce26  test    rcx, rcx
0x14000ce29  jz      short loc_14000CE37
0x14000ce2b  mov     rax, [rcx]
0x14000ce2e  mov     rax, [rax+10h]
0x14000ce32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ce37  mov     eax, ebx
0x14000ce39  mov     rbx, [rsp+28h+arg_8]
0x14000ce3e  add     rsp, 20h
0x14000ce42  pop     rdi
0x14000ce43  retn
```
