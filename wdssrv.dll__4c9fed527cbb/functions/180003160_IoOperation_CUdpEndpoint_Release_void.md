# IoOperation<CUdpEndpoint>::Release(void)

- ea: `0x180003160`
- end: `0x1800031e6`
- name: `?Release@?$IoOperation@VCUdpEndpoint@@@@QEAAKXZ`
- size: `134`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `8`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800032c0`
- `0x1800032d0`
- `0x180019340`
- `0x180019498`
- `0x1800197b0`
- `0x180019c3c`
- `0x180019d14`
- `0x18001a250`

## callees

- `0x1800025a0`
- `0x180003160`

## import_xrefs

- `KERNEL32!InterlockedPushEntrySList` at `0x1800031bf`
- `KERNEL32!InterlockedPushEntrySList` at `0x1800031bf`
- `WdsServerCommonLib!?WdsPrivateHpFree@@YAKPEAX@Z` at `0x1800031a7`
- `WdsServerCommonLib!?WdsPrivateHpFree@@YAKPEAX@Z` at `0x1800031a7`

## pseudocode

```c
__int64 __fastcall IoOperation<CUdpEndpoint>::Release(__int64 a1)
{
  unsigned __int32 v2; // ebx
  __int64 v3; // rdi

  v2 = _InterlockedDecrement((volatile signed __int32 *)(a1 + 1248));
  if ( v2 == 1 )
  {
    v3 = *(_QWORD *)(a1 + 1256);
    ((void (*)(void))IoOperation<CUdpEndpoint>::Cleanup)();
    if ( (unsigned int)_InterlockedExchangeAdd((volatile signed __int32 *)(v3 + 16), 0) <= *(_DWORD *)(v3 + 36) )
    {
      InterlockedPushEntrySList((PSLIST_HEADER)v3, (PSLIST_ENTRY)(a1 + 1280));
      _InterlockedIncrement((volatile signed __int32 *)(v3 + 16));
    }
    else
    {
      IoOperation<CUdpEndpoint>::Cleanup(a1);
      WdsPrivateHpFree((void *)a1);
    }
    _InterlockedDecrement((volatile signed __int32 *)(v3 + 32));
  }
  return v2;
}

```

## disassembly

```asm
0x180003160  mov     [rsp+arg_0], rbx
0x180003165  mov     [rsp+arg_8], rsi
0x18000316a  push    rdi
0x18000316b  sub     rsp, 20h
0x18000316f  mov     rsi, rcx
0x180003172  or      ebx, 0FFFFFFFFh
0x180003175  lock xadd [rcx+4E0h], ebx
0x18000317d  dec     ebx
0x18000317f  cmp     ebx, 1
0x180003182  jnz     short loc_1800031D3
0x180003184  mov     rdi, [rcx+4E8h]
0x18000318b  call    ?Cleanup@?$IoOperation@VCUdpEndpoint@@@@QEAAXXZ; IoOperation<CUdpEndpoint>::Cleanup(void)
0x180003190  xor     eax, eax
0x180003192  lock xadd [rdi+10h], eax
0x180003197  cmp     eax, [rdi+24h]
0x18000319a  jbe     short loc_1800031B5
0x18000319c  mov     rcx, rsi
0x18000319f  call    ?Cleanup@?$IoOperation@VCUdpEndpoint@@@@QEAAXXZ; IoOperation<CUdpEndpoint>::Cleanup(void)
0x1800031a4  mov     rcx, rsi
0x1800031a7  call    cs:__imp_?WdsPrivateHpFree@@YAKPEAX@Z; WdsPrivateHpFree(void *)
0x1800031ae  nop     dword ptr [rax+rax+00h]
0x1800031b3  jmp     short loc_1800031CF
0x1800031b5  lea     rdx, [rsi+500h]; ListEntry
0x1800031bc  mov     rcx, rdi; ListHead
0x1800031bf  call    cs:__imp_InterlockedPushEntrySList
0x1800031c6  nop     dword ptr [rax+rax+00h]
0x1800031cb  lock inc dword ptr [rdi+10h]
0x1800031cf  lock dec dword ptr [rdi+20h]
0x1800031d3  mov     rsi, [rsp+28h+arg_8]
0x1800031d8  mov     eax, ebx
0x1800031da  mov     rbx, [rsp+28h+arg_0]
0x1800031df  add     rsp, 20h
0x1800031e3  pop     rdi
0x1800031e4  retn
```
