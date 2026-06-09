# UdfTearDownSpecialScb

- ea: `0x140058898`
- end: `0x14005893e`
- name: `UdfTearDownSpecialScb`
- size: `166`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140052864`

## callees

- `0x1400537b0`
- `0x140058898`
- `0x140058aac`

## import_xrefs

- `ntoskrnl!CcPurgeCacheSection` at `0x1400588de`
- `ntoskrnl!CcPurgeCacheSection` at `0x1400588de`

## pseudocode

```c
void __fastcall UdfTearDownSpecialScb(int a1, __int64 a2, _DWORD *a3)
{
  SECTION_OBJECT_POINTERS *v6; // rcx
  char v7; // [rsp+48h] [rbp+10h] BYREF

  if ( a2 )
  {
    v7 = 0;
    _InterlockedIncrement((volatile signed __int32 *)(a2 + 204));
    v6 = (SECTION_OBJECT_POINTERS *)(*(_QWORD *)(a2 + 424) + 8LL);
    if ( v6->DataSectionObject && !CcPurgeCacheSection(v6, 0, 0, 0) && !*a3 )
      *a3 = -1073741797;
    if ( *(_WORD *)a2 == 2355 )
      UdfDeleteInternalStream((__int64)v6, a2);
    _InterlockedDecrement((volatile signed __int32 *)(a2 + 204));
    UdfTeardownStructures(a1, a2, 0, 0, (__int64)&v7);
  }
}

```

## disassembly

```asm
0x140058898  test    rdx, rdx
0x14005889b  jz      locret_14005893C
0x1400588a1  mov     [rsp+arg_0], rbx
0x1400588a6  mov     [rsp+arg_10], rsi
0x1400588ab  push    rdi
0x1400588ac  sub     rsp, 30h
0x1400588b0  mov     rdi, r8
0x1400588b3  mov     [rsp+38h+arg_8], 0
0x1400588b8  mov     rbx, rdx
0x1400588bb  mov     rsi, rcx
0x1400588be  lock inc dword ptr [rdx+0CCh]
0x1400588c5  mov     rcx, [rdx+1A8h]
0x1400588cc  add     rcx, 8; SectionObjectPointer
0x1400588d0  cmp     qword ptr [rcx], 0
0x1400588d4  jz      short loc_1400588F9
0x1400588d6  xor     r9d, r9d; Flags
0x1400588d9  xor     r8d, r8d; Length
0x1400588dc  xor     edx, edx; FileOffset
0x1400588de  call    cs:__imp_CcPurgeCacheSection
0x1400588e5  nop     dword ptr [rax+rax+00h]
0x1400588ea  test    al, al
0x1400588ec  jnz     short loc_1400588F9
0x1400588ee  cmp     dword ptr [rdi], 0
0x1400588f1  jnz     short loc_1400588F9
0x1400588f3  mov     dword ptr [rdi], 0C000001Bh
0x1400588f9  mov     eax, 933h
0x1400588fe  cmp     ax, [rbx]
0x140058901  jnz     short loc_14005890B
0x140058903  mov     rdx, rbx
0x140058906  call    UdfDeleteInternalStream
0x14005890b  lock dec dword ptr [rbx+0CCh]
0x140058912  lea     rax, [rsp+38h+arg_8]
0x140058917  xor     r9d, r9d
0x14005891a  mov     [rsp+38h+var_18], rax
0x14005891f  xor     r8d, r8d
0x140058922  mov     rdx, rbx
0x140058925  mov     rcx, rsi
0x140058928  call    UdfTeardownStructures
0x14005892d  mov     rbx, [rsp+38h+arg_0]
0x140058932  mov     rsi, [rsp+38h+arg_10]
0x140058937  add     rsp, 30h
0x14005893b  pop     rdi
0x14005893c  retn
```
