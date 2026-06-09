# WerpGetRegistryLong64Value

- ea: `0x14000f4b8`
- end: `0x14000f544`
- name: `WerpGetRegistryLong64Value`
- size: `140`
- prototype: `__int64 __fastcall(void *, struct _UNICODE_STRING *, void *, _QWORD *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x140012588`

## callees

- `0x14000f4b8`
- `0x14000f640`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000f523`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000f523`

## pseudocode

```c
__int64 __fastcall WerpGetRegistryLong64Value(void *a1, struct _UNICODE_STRING *a2, void *a3, _QWORD *a4)
{
  int RegistryValueInfo; // eax
  PVOID v6; // r8
  unsigned int v7; // edi
  PVOID P; // [rsp+40h] [rbp+18h] BYREF

  P = a3;
  if ( !a1 || !a2 || !a4 )
    return 3221225485LL;
  P = 0;
  RegistryValueInfo = WerpGetRegistryValueInfo(a1, a2, &P);
  v6 = P;
  v7 = RegistryValueInfo;
  if ( RegistryValueInfo >= 0 && P && *((_DWORD *)P + 1) == 11 && *((_DWORD *)P + 2) == 8 )
    *a4 = *(_QWORD *)((char *)P + 12);
  else
    *a4 = 0;
  if ( v6 )
    ExFreePoolWithTag(v6, 0);
  return v7;
}

```

## disassembly

```asm
0x14000f4b8  mov     rax, rsp
0x14000f4bb  mov     [rax+8], rbx
0x14000f4bf  mov     [rax+18h], r8
0x14000f4c3  push    rdi
0x14000f4c4  sub     rsp, 20h
0x14000f4c8  mov     rbx, r9
0x14000f4cb  test    rcx, rcx
0x14000f4ce  jz      short loc_14000F533
0x14000f4d0  test    rdx, rdx
0x14000f4d3  jz      short loc_14000F533
0x14000f4d5  test    rbx, rbx
0x14000f4d8  jz      short loc_14000F533
0x14000f4da  lea     r8, [rax+18h]
0x14000f4de  mov     qword ptr [rax+18h], 0
0x14000f4e6  call    WerpGetRegistryValueInfo
0x14000f4eb  mov     r8, [rsp+28h+P]
0x14000f4f0  mov     edi, eax
0x14000f4f2  test    eax, eax
0x14000f4f4  js      short loc_14000F512
0x14000f4f6  test    r8, r8
0x14000f4f9  jz      short loc_14000F512
0x14000f4fb  cmp     dword ptr [r8+4], 0Bh
0x14000f500  jnz     short loc_14000F512
0x14000f502  cmp     dword ptr [r8+8], 8
0x14000f507  jnz     short loc_14000F512
0x14000f509  mov     rcx, [r8+0Ch]
0x14000f50d  mov     [rbx], rcx
0x14000f510  jmp     short loc_14000F519
0x14000f512  mov     qword ptr [rbx], 0
0x14000f519  test    r8, r8
0x14000f51c  jz      short loc_14000F52F
0x14000f51e  xor     edx, edx; Tag
0x14000f520  mov     rcx, r8; P
0x14000f523  call    cs:__imp_ExFreePoolWithTag
0x14000f52a  nop     dword ptr [rax+rax+00h]
0x14000f52f  mov     eax, edi
0x14000f531  jmp     short loc_14000F538
0x14000f533  mov     eax, 0C000000Dh
0x14000f538  mov     rbx, [rsp+28h+arg_0]
0x14000f53d  add     rsp, 20h
0x14000f541  pop     rdi
0x14000f542  retn
```
