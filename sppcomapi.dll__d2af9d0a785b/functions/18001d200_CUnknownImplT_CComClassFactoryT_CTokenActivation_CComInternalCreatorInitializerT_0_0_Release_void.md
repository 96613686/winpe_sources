# CUnknownImplT<CComClassFactoryT<CTokenActivation,CComInternalCreatorInitializerT,0>,0>::Release(void)

- ea: `0x18001d200`
- end: `0x18001d24f`
- name: `?Release@?$CUnknownImplT@V?$CComClassFactoryT@VCTokenActivation@@VCComInternalCreatorInitializerT@@$0A@@@$0A@@@UEAAKXZ`
- size: `79`
- prototype: `__int64 __fastcall(LPVOID lpMem)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18001d200`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001d21a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001d21a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001d22e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001d22e`

## pseudocode

```c
__int64 __fastcall CUnknownImplT<CComClassFactoryT<CTokenActivation,CComInternalCreatorInitializerT,0>,0>::Release(
        volatile signed __int32 *lpMem)
{
  unsigned __int32 v2; // ebx
  HANDLE ProcessHeap; // rax

  v2 = _InterlockedDecrement(lpMem + 2);
  if ( !v2 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, (LPVOID)lpMem);
    _InterlockedDecrement(&CComProcessCounter<0>::g_lServerLockCount);
  }
  return v2;
}

```

## disassembly

```asm
0x18001d200  mov     [rsp+arg_0], rbx
0x18001d205  push    rdi
0x18001d206  sub     rsp, 20h
0x18001d20a  mov     rdi, rcx
0x18001d20d  or      ebx, 0FFFFFFFFh
0x18001d210  lock xadd [rcx+8], ebx
0x18001d215  sub     ebx, 1
0x18001d218  jnz     short loc_18001D241
0x18001d21a  call    cs:__imp_GetProcessHeap
0x18001d221  nop     dword ptr [rax+rax+00h]
0x18001d226  mov     r8, rdi; lpMem
0x18001d229  xor     edx, edx; dwFlags
0x18001d22b  mov     rcx, rax; hHeap
0x18001d22e  call    cs:__imp_HeapFree
0x18001d235  nop     dword ptr [rax+rax+00h]
0x18001d23a  lock dec cs:?g_lServerLockCount@?$CComProcessCounter@$0A@@@0JA; long CComProcessCounter<0>::g_lServerLockCount
0x18001d241  mov     eax, ebx
0x18001d243  mov     rbx, [rsp+28h+arg_0]
0x18001d248  add     rsp, 20h
0x18001d24c  pop     rdi
0x18001d24d  retn
```
