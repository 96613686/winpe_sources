# SecpAddVMEx

- ea: `0x18000c4f0`
- end: `0x18000c566`
- name: `SecpAddVMEx`
- size: `118`
- prototype: ``
- caller_count: `10`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180001090`
- `0x1800012d0`
- `0x180004290`
- `0x1800049c0`
- `0x18001b700`
- `0x18001bdac`
- `0x18001c0a0`
- `0x18001c380`
- `0x18001c530`
- `0x18001c830`

## callees

- `0x18000c4f0`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x18000c54e`
- `ntdll!RtlLeaveCriticalSection` at `0x18000c54e`
- `ntdll!RtlEnterCriticalSection` at `0x18000c51a`
- `ntdll!RtlEnterCriticalSection` at `0x18000c51a`

## pseudocode

```c
NTSTATUS __fastcall SecpAddVMEx(__int64 a1, char a2, _DWORD *a3)
{
  _BYTE *v6; // rax
  __int64 v7; // r8
  NTSTATUS result; // eax

  if ( a1 )
  {
    if ( *a3 )
    {
      RtlEnterCriticalSection(&SecVMListLock);
      v6 = SecVMList;
      v7 = 2LL * SecVMListElements++;
      *((_QWORD *)SecVMList + v7) = a1;
      v6[8 * v7 + 8] = a2;
      result = RtlLeaveCriticalSection(&SecVMListLock);
      --*a3;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000c4f0  test    rcx, rcx
0x18000c4f3  jz      short locret_18000C565
0x18000c4f5  mov     [rsp+arg_0], rbx
0x18000c4fa  mov     [rsp+arg_8], rsi
0x18000c4ff  push    rdi
0x18000c500  sub     rsp, 20h
0x18000c504  cmp     dword ptr [r8], 0
0x18000c508  mov     rbx, r8
0x18000c50b  movzx   esi, dl
0x18000c50e  mov     rdi, rcx
0x18000c511  jz      short loc_18000C556
0x18000c513  lea     rcx, ?SecVMListLock@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x18000c51a  call    cs:__imp_RtlEnterCriticalSection
0x18000c520  mov     r9d, cs:?SecVMListElements@@3KA; ulong SecVMListElements
0x18000c527  lea     rcx, ?SecVMListLock@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x18000c52e  mov     rax, cs:?SecVMList@@3PEAU_VM_LIST_ENTRY@@EA; _VM_LIST_ENTRY * SecVMList
0x18000c535  mov     r8d, r9d
0x18000c538  add     r8, r8
0x18000c53b  inc     r9d
0x18000c53e  mov     cs:?SecVMListElements@@3KA, r9d; ulong SecVMListElements
0x18000c545  mov     [rax+r8*8], rdi
0x18000c549  mov     [rax+r8*8+8], sil
0x18000c54e  call    cs:__imp_RtlLeaveCriticalSection
0x18000c554  dec     dword ptr [rbx]
0x18000c556  mov     rbx, [rsp+28h+arg_0]
0x18000c55b  mov     rsi, [rsp+28h+arg_8]
0x18000c560  add     rsp, 20h
0x18000c564  pop     rdi
0x18000c565  retn
```
