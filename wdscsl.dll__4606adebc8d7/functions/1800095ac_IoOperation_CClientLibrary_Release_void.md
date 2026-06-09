# IoOperation<CClientLibrary>::Release(void)

- ea: `0x1800095ac`
- end: `0x180009632`
- name: `?Release@?$IoOperation@VCClientLibrary@@@@QEAAKXZ`
- size: `134`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180007e80`
- `0x180008174`
- `0x180008404`
- `0x18000a858`

## callees

- `0x180004cb0`
- `0x1800095ac`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1800095f3`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800095f3`
- `KERNEL32!InterlockedPushEntrySList` at `0x18000960b`
- `KERNEL32!InterlockedPushEntrySList` at `0x18000960b`

## pseudocode

```c
__int64 __fastcall IoOperation<CClientLibrary>::Release(__int64 a1)
{
  unsigned __int32 v2; // ebx
  __int64 v3; // rdi

  v2 = _InterlockedDecrement((volatile signed __int32 *)(a1 + 1248));
  if ( v2 == 1 )
  {
    v3 = *(_QWORD *)(a1 + 1256);
    IoOperation<CClientLibrary>::Cleanup(a1);
    if ( (unsigned int)_InterlockedExchangeAdd((volatile signed __int32 *)(v3 + 16), 0) <= *(_DWORD *)(v3 + 36) )
    {
      InterlockedPushEntrySList((PSLIST_HEADER)v3, (PSLIST_ENTRY)(a1 + 1280));
      _InterlockedIncrement((volatile signed __int32 *)(v3 + 16));
    }
    else
    {
      IoOperation<CClientLibrary>::Cleanup(a1);
      operator delete((void *)a1);
    }
    _InterlockedDecrement((volatile signed __int32 *)(v3 + 32));
  }
  return v2;
}

```

## disassembly

```asm
0x1800095ac  mov     [rsp+arg_0], rbx
0x1800095b1  mov     [rsp+arg_8], rsi
0x1800095b6  push    rdi
0x1800095b7  sub     rsp, 20h
0x1800095bb  mov     rsi, rcx
0x1800095be  or      ebx, 0FFFFFFFFh
0x1800095c1  lock xadd [rcx+4E0h], ebx
0x1800095c9  dec     ebx
0x1800095cb  cmp     ebx, 1
0x1800095ce  jnz     short loc_18000961F
0x1800095d0  mov     rdi, [rcx+4E8h]
0x1800095d7  call    ?Cleanup@?$IoOperation@VCClientLibrary@@@@QEAAXXZ; IoOperation<CClientLibrary>::Cleanup(void)
0x1800095dc  xor     eax, eax
0x1800095de  lock xadd [rdi+10h], eax
0x1800095e3  cmp     eax, [rdi+24h]
0x1800095e6  jbe     short loc_180009601
0x1800095e8  mov     rcx, rsi
0x1800095eb  call    ?Cleanup@?$IoOperation@VCClientLibrary@@@@QEAAXXZ; IoOperation<CClientLibrary>::Cleanup(void)
0x1800095f0  mov     rcx, rsi
0x1800095f3  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800095fa  nop     dword ptr [rax+rax+00h]
0x1800095ff  jmp     short loc_18000961B
0x180009601  lea     rdx, [rsi+500h]; ListEntry
0x180009608  mov     rcx, rdi; ListHead
0x18000960b  call    cs:__imp_InterlockedPushEntrySList
0x180009612  nop     dword ptr [rax+rax+00h]
0x180009617  lock inc dword ptr [rdi+10h]
0x18000961b  lock dec dword ptr [rdi+20h]
0x18000961f  mov     rsi, [rsp+28h+arg_8]
0x180009624  mov     eax, ebx
0x180009626  mov     rbx, [rsp+28h+arg_0]
0x18000962b  add     rsp, 20h
0x18000962f  pop     rdi
0x180009630  retn
```
