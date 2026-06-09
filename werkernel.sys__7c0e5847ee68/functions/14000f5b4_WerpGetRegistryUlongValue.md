# WerpGetRegistryUlongValue

- ea: `0x14000f5b4`
- end: `0x14000f638`
- name: `WerpGetRegistryUlongValue`
- size: `132`
- prototype: `__int64 __fastcall(void *, struct _UNICODE_STRING *, int, _DWORD *)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x14000f54c`
- `0x14000fba0`
- `0x140012588`

## callees

- `0x14000f5b4`
- `0x14000f640`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000f612`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000f612`

## pseudocode

```c
__int64 __fastcall WerpGetRegistryUlongValue(void *a1, struct _UNICODE_STRING *a2, int a3, _DWORD *a4)
{
  int RegistryValueInfo; // eax
  PVOID v7; // rcx
  unsigned int v8; // esi
  PVOID P; // [rsp+30h] [rbp+8h] BYREF

  if ( !a1 || !a2 || !a4 )
    return 3221225485LL;
  P = 0;
  RegistryValueInfo = WerpGetRegistryValueInfo(a1, a2, &P);
  v7 = P;
  v8 = RegistryValueInfo;
  if ( RegistryValueInfo >= 0 && P && *((_DWORD *)P + 1) == 4 && *((_DWORD *)P + 2) == 4 )
    a3 = *((_DWORD *)P + 3);
  *a4 = a3;
  if ( v7 )
    ExFreePoolWithTag(v7, 0);
  return v8;
}

```

## disassembly

```asm
0x14000f5b4  mov     rax, rsp
0x14000f5b7  mov     [rax+10h], rbx
0x14000f5bb  mov     [rax+18h], rsi
0x14000f5bf  push    rdi
0x14000f5c0  sub     rsp, 20h
0x14000f5c4  mov     rbx, r9
0x14000f5c7  mov     edi, r8d
0x14000f5ca  test    rcx, rcx
0x14000f5cd  jz      short loc_14000F622
0x14000f5cf  test    rdx, rdx
0x14000f5d2  jz      short loc_14000F622
0x14000f5d4  test    rbx, rbx
0x14000f5d7  jz      short loc_14000F622
0x14000f5d9  lea     r8, [rax+8]
0x14000f5dd  mov     qword ptr [rax+8], 0
0x14000f5e5  call    WerpGetRegistryValueInfo
0x14000f5ea  mov     rcx, [rsp+28h+P]; P
0x14000f5ef  mov     esi, eax
0x14000f5f1  test    eax, eax
0x14000f5f3  js      short loc_14000F609
0x14000f5f5  test    rcx, rcx
0x14000f5f8  jz      short loc_14000F609
0x14000f5fa  cmp     dword ptr [rcx+4], 4
0x14000f5fe  jnz     short loc_14000F609
0x14000f600  cmp     dword ptr [rcx+8], 4
0x14000f604  jnz     short loc_14000F609
0x14000f606  mov     edi, [rcx+0Ch]
0x14000f609  mov     [rbx], edi
0x14000f60b  test    rcx, rcx
0x14000f60e  jz      short loc_14000F61E
0x14000f610  xor     edx, edx; Tag
0x14000f612  call    cs:__imp_ExFreePoolWithTag
0x14000f619  nop     dword ptr [rax+rax+00h]
0x14000f61e  mov     eax, esi
0x14000f620  jmp     short loc_14000F627
0x14000f622  mov     eax, 0C000000Dh
0x14000f627  mov     rbx, [rsp+28h+arg_8]
0x14000f62c  mov     rsi, [rsp+28h+arg_10]
0x14000f631  add     rsp, 20h
0x14000f635  pop     rdi
0x14000f636  retn
```
