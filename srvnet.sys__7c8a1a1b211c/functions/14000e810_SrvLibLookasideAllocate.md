# SrvLibLookasideAllocate

- ea: `0x14000e810`
- end: `0x14000e8c0`
- name: `SrvLibLookasideAllocate`
- size: `176`
- prototype: `__int64 __fastcall(PSLIST_HEADER ListHead)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation`

## callees

- `0x14000e810`
- `0x14002a4c0`

## import_xrefs

- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x14000e863`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x14000e8aa`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x14000e863`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x14000e8aa`

## pseudocode

```c
PSLIST_ENTRY __fastcall SrvLibLookasideAllocate(PSLIST_HEADER ListHead)
{
  PSLIST_ENTRY result; // rax
  __int64 v3; // r8
  union _SLIST_HEADER *v4; // rdi

  if ( SrvNetNumberOfActiveProcessorsAtServerStart != 1 )
  {
    v3 = HIDWORD(KeGetPcr()[1].LockArray) % SrvNetNumberOfActiveProcessorsAtServerStart + 1LL;
    v4 = &ListHead[12 * v3];
    ++*((_DWORD *)&v4[1].HeaderX64 + 1);
    if ( LOWORD(v4[8].Alignment) )
    {
      result = ExpInterlockedPopEntrySList(&ListHead[12 * v3]);
      if ( result )
        return result;
    }
    ++*((_DWORD *)&v4[1].HeaderX64 + 2);
  }
  ++*((_DWORD *)&ListHead[1].HeaderX64 + 1);
  if ( !LOWORD(ListHead[8].Alignment) || (result = ExpInterlockedPopEntrySList(ListHead)) == 0 )
  {
    ++*((_DWORD *)&ListHead[1].HeaderX64 + 2);
    return (PSLIST_ENTRY)((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD))ListHead[3].Alignment)(
                           *((unsigned int *)&ListHead[2].HeaderX64 + 1),
                           *((unsigned int *)&ListHead[2].HeaderX64 + 3),
                           *((unsigned int *)&ListHead[2].HeaderX64 + 2));
  }
  return result;
}

```

## disassembly

```asm
0x14000e810  mov     [rsp+arg_0], rbx
0x14000e815  mov     [rsp+arg_8], rsi
0x14000e81a  push    rdi
0x14000e81b  sub     rsp, 20h
0x14000e81f  xor     esi, esi
0x14000e821  mov     rbx, rcx
0x14000e824  cmp     cs:SrvNetNumberOfActiveProcessorsAtServerStart, 1
0x14000e82b  jnz     short loc_14000E876
0x14000e82d  inc     dword ptr [rbx+14h]
0x14000e830  cmp     [rbx+80h], si
0x14000e837  jnz     short loc_14000E860
0x14000e839  inc     dword ptr [rbx+18h]
0x14000e83c  mov     edx, [rbx+2Ch]
0x14000e83f  mov     rax, [rbx+30h]
0x14000e843  mov     r8d, [rbx+28h]
0x14000e847  mov     ecx, [rbx+24h]
0x14000e84a  call    _guard_dispatch_icall
0x14000e84f  mov     rbx, [rsp+28h+arg_0]
0x14000e854  mov     rsi, [rsp+28h+arg_8]
0x14000e859  add     rsp, 20h
0x14000e85d  pop     rdi
0x14000e85e  retn
0x14000e860  mov     rcx, rbx; ListHead
0x14000e863  call    cs:__imp_ExpInterlockedPopEntrySList
0x14000e86a  nop     dword ptr [rax+rax+00h]
0x14000e86f  test    rax, rax
0x14000e872  jz      short loc_14000E839
0x14000e874  jmp     short loc_14000E84F
0x14000e876  mov     eax, gs:1A4h
0x14000e87e  xor     edx, edx
0x14000e880  div     cs:SrvNetNumberOfActiveProcessorsAtServerStart
0x14000e886  mov     r8d, edx
0x14000e889  inc     r8
0x14000e88c  lea     rdi, [r8+r8*2]
0x14000e890  shl     rdi, 6
0x14000e894  add     rdi, rbx
0x14000e897  inc     dword ptr [rdi+14h]
0x14000e89a  cmp     [rdi+80h], si
0x14000e8a1  jz      loc_14002C7A2
0x14000e8a7  mov     rcx, rdi; ListHead
0x14000e8aa  call    cs:__imp_ExpInterlockedPopEntrySList
0x14000e8b1  nop     dword ptr [rax+rax+00h]
0x14000e8b6  test    rax, rax
0x14000e8b9  jnz     short loc_14000E84F
0x14000e8bb  jmp     loc_14002C7A2
0x14002c7a2  inc     dword ptr [rdi+18h]
0x14002c7a5  jmp     loc_14000E82D
```
