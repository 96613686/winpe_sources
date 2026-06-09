# WanIpDeleteInterfaceComplete

- ea: `0x14000d310`
- end: `0x14000d377`
- name: `WanIpDeleteInterfaceComplete`
- size: `103`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x14000457c`
- `0x14000d310`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000d32b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d32b`

## pseudocode

```c
void __fastcall WanIpDeleteInterfaceComplete(__int64 *a1)
{
  __int64 v1; // rcx
  char v2; // bl
  __int64 v3; // rcx
  __int64 *v4; // rcx

  v1 = *a1;
  v2 = *(_BYTE *)(v1 + 20);
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v1 + 64), 0xFFFFFFFF) == 1 )
    ExFreePoolWithTag((PVOID)v1, 0);
  v3 = qword_1400090D8;
  if ( !v2 )
    v3 = qword_140009328;
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v3 + 32), 0xFFFFFFFE) == 3 )
  {
    v4 = &WanNmrV4ProviderState;
    if ( !v2 )
      v4 = &WanNmrV6ProviderState;
    WanNmrFinalizeDetach((__int64)v4);
  }
}

```

## disassembly

```asm
0x14000d310  push    rbx
0x14000d312  sub     rsp, 20h
0x14000d316  mov     rcx, [rcx]; P
0x14000d319  or      eax, 0FFFFFFFFh
0x14000d31c  mov     bl, [rcx+14h]
0x14000d31f  lock xadd [rcx+40h], eax
0x14000d324  cmp     eax, 1
0x14000d327  jnz     short loc_14000D337
0x14000d329  xor     edx, edx; Tag
0x14000d32b  call    cs:__imp_ExFreePoolWithTag
0x14000d332  nop     dword ptr [rax+rax+00h]
0x14000d337  mov     rcx, cs:qword_1400090D8
0x14000d33e  test    bl, bl
0x14000d340  mov     eax, 0FFFFFFFEh
0x14000d345  cmovz   rcx, cs:qword_140009328
0x14000d34d  lock xadd [rcx+20h], eax
0x14000d352  cmp     eax, 3
0x14000d355  jnz     short loc_14000D370
0x14000d357  test    bl, bl
0x14000d359  lea     rax, WanNmrV6ProviderState
0x14000d360  lea     rcx, WanNmrV4ProviderState
0x14000d367  cmovz   rcx, rax
0x14000d36b  call    WanNmrFinalizeDetach
0x14000d370  add     rsp, 20h
0x14000d374  pop     rbx
0x14000d375  retn
```
