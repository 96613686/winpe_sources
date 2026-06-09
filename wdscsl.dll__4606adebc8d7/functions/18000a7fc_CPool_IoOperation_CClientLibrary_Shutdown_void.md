# CPool<IoOperation<CClientLibrary>>::Shutdown(void)

- ea: `0x18000a7fc`
- end: `0x18000a852`
- name: `?Shutdown@?$CPool@U?$IoOperation@VCClientLibrary@@@@@@QEAAXXZ`
- size: `86`
- prototype: `__int64 __fastcall(PSLIST_HEADER ListHead)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18000342c`
- `0x18000a858`

## callees

- `0x180004cb0`
- `0x18000a7fc`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000a838`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000a838`
- `KERNEL32!InterlockedPopEntrySList` at `0x18000a80c`
- `KERNEL32!InterlockedPopEntrySList` at `0x18000a80c`

## pseudocode

```c
PSLIST_ENTRY __fastcall CPool<IoOperation<CClientLibrary>>::Shutdown(PSLIST_HEADER ListHead)
{
  PSLIST_ENTRY result; // rax
  struct _SLIST_ENTRY *v3; // rdi

  while ( 1 )
  {
    result = InterlockedPopEntrySList(ListHead);
    if ( !result )
      break;
    _InterlockedDecrement((volatile signed __int32 *)&ListHead[1]);
    v3 = result - 80;
    if ( result == (PSLIST_ENTRY)1280 )
      break;
    IoOperation<CClientLibrary>::Cleanup(&result[-80]);
    operator delete(v3);
  }
  return result;
}

```

## disassembly

```asm
0x18000a7fc  mov     [rsp+arg_0], rbx
0x18000a801  push    rdi
0x18000a802  sub     rsp, 20h
0x18000a806  mov     rbx, rcx
0x18000a809  mov     rcx, rbx; ListHead
0x18000a80c  call    cs:__imp_InterlockedPopEntrySList
0x18000a813  nop     dword ptr [rax+rax+00h]
0x18000a818  test    rax, rax
0x18000a81b  jz      short loc_18000A846
0x18000a81d  lock dec dword ptr [rbx+10h]
0x18000a821  lea     rdi, [rax-500h]
0x18000a828  test    rdi, rdi
0x18000a82b  jz      short loc_18000A846
0x18000a82d  mov     rcx, rdi
0x18000a830  call    ?Cleanup@?$IoOperation@VCClientLibrary@@@@QEAAXXZ; IoOperation<CClientLibrary>::Cleanup(void)
0x18000a835  mov     rcx, rdi
0x18000a838  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000a83f  nop     dword ptr [rax+rax+00h]
0x18000a844  jmp     short loc_18000A809
0x18000a846  mov     rbx, [rsp+28h+arg_0]
0x18000a84b  add     rsp, 20h
0x18000a84f  pop     rdi
0x18000a850  retn
```
