# IPropertyStore_GetString

- ea: `0x180016880`
- end: `0x1800168f2`
- name: `IPropertyStore_GetString`
- size: `114`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180006ba0`
- `0x18000b410`
- `0x180010a3c`
- `0x180010b88`
- `0x180013770`

## callees

- `0x180016880`
- `0x180017010`

## import_xrefs

- `PROPSYS!PropVariantToStringAlloc` at `0x1800168cb`
- `PROPSYS!PropVariantToStringAlloc` at `0x1800168cb`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800168df`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800168df`

## pseudocode

```c
__int64 __fastcall IPropertyStore_GetString(__int64 *a1, __int64 a2, PWSTR *a3)
{
  __int64 v4; // rax
  HRESULT v5; // ebx
  PROPVARIANT propvar[2]; // [rsp+20h] [rbp-28h] BYREF
  __int64 v8; // [rsp+30h] [rbp-18h]

  *a3 = 0;
  v8 = 0;
  v4 = *a1;
  *(_OWORD *)propvar = 0;
  v5 = (*(__int64 (__fastcall **)(__int64 *, __int64, PROPVARIANT *))(v4 + 40))(a1, a2, propvar);
  if ( v5 >= 0 )
  {
    if ( LOWORD(propvar[0]) )
      v5 = PropVariantToStringAlloc(propvar, a3);
    else
      v5 = -2147023728;
    PropVariantClear(propvar);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180016880  mov     [rsp+arg_0], rbx
0x180016885  push    rdi
0x180016886  sub     rsp, 40h
0x18001688a  xor     eax, eax
0x18001688c  mov     qword ptr [r8], 0
0x180016893  mov     [rsp+48h+var_18], rax
0x180016898  mov     rdi, r8
0x18001689b  mov     rax, [rcx]
0x18001689e  lea     r8, [rsp+48h+propvar]
0x1800168a3  xorps   xmm0, xmm0
0x1800168a6  movups  xmmword ptr [rsp+48h+propvar], xmm0
0x1800168ab  mov     rax, [rax+28h]
0x1800168af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800168b4  mov     ebx, eax
0x1800168b6  test    eax, eax
0x1800168b8  js      short loc_1800168E5
0x1800168ba  xor     eax, eax
0x1800168bc  cmp     ax, word ptr [rsp+48h+propvar]
0x1800168c1  jz      short loc_1800168D5
0x1800168c3  mov     rdx, rdi; ppszOut
0x1800168c6  lea     rcx, [rsp+48h+propvar]; propvar
0x1800168cb  call    cs:__imp_PropVariantToStringAlloc
0x1800168d1  mov     ebx, eax
0x1800168d3  jmp     short loc_1800168DA
0x1800168d5  mov     ebx, 80070490h
0x1800168da  lea     rcx, [rsp+48h+propvar]; pvar
0x1800168df  call    cs:__imp_PropVariantClear
0x1800168e5  mov     eax, ebx
0x1800168e7  mov     rbx, [rsp+48h+arg_0]
0x1800168ec  add     rsp, 40h
0x1800168f0  pop     rdi
0x1800168f1  retn
```
