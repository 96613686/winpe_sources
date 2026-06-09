# CPool<IoOperation<CUdpEndpoint>>::Shutdown(void)

- ea: `0x18001a1f4`
- end: `0x18001a24a`
- name: `?Shutdown@?$CPool@U?$IoOperation@VCUdpEndpoint@@@@@@QEAAXXZ`
- size: `86`
- prototype: `__int64 __fastcall(PSLIST_HEADER ListHead)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800181bc`
- `0x18001a250`

## callees

- `0x1800025a0`
- `0x18001a1f4`

## import_xrefs

- `KERNEL32!InterlockedPopEntrySList` at `0x18001a204`
- `KERNEL32!InterlockedPopEntrySList` at `0x18001a204`
- `WdsServerCommonLib!?WdsPrivateHpFree@@YAKPEAX@Z` at `0x18001a230`
- `WdsServerCommonLib!?WdsPrivateHpFree@@YAKPEAX@Z` at `0x18001a230`

## pseudocode

```c
PSLIST_ENTRY __fastcall CPool<IoOperation<CUdpEndpoint>>::Shutdown(PSLIST_HEADER ListHead)
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
    IoOperation<CUdpEndpoint>::Cleanup((__int64)&result[-80]);
    WdsPrivateHpFree(v3);
  }
  return result;
}

```

## disassembly

```asm
0x18001a1f4  mov     [rsp+arg_0], rbx
0x18001a1f9  push    rdi
0x18001a1fa  sub     rsp, 20h
0x18001a1fe  mov     rbx, rcx
0x18001a201  mov     rcx, rbx; ListHead
0x18001a204  call    cs:__imp_InterlockedPopEntrySList
0x18001a20b  nop     dword ptr [rax+rax+00h]
0x18001a210  test    rax, rax
0x18001a213  jz      short loc_18001A23E
0x18001a215  lock dec dword ptr [rbx+10h]
0x18001a219  lea     rdi, [rax-500h]
0x18001a220  test    rdi, rdi
0x18001a223  jz      short loc_18001A23E
0x18001a225  mov     rcx, rdi
0x18001a228  call    ?Cleanup@?$IoOperation@VCUdpEndpoint@@@@QEAAXXZ; IoOperation<CUdpEndpoint>::Cleanup(void)
0x18001a22d  mov     rcx, rdi
0x18001a230  call    cs:__imp_?WdsPrivateHpFree@@YAKPEAX@Z; WdsPrivateHpFree(void *)
0x18001a237  nop     dword ptr [rax+rax+00h]
0x18001a23c  jmp     short loc_18001A201
0x18001a23e  mov     rbx, [rsp+28h+arg_0]
0x18001a243  add     rsp, 20h
0x18001a247  pop     rdi
0x18001a248  retn
```
