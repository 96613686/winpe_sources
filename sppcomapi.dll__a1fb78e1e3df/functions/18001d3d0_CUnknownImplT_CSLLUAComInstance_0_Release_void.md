# CUnknownImplT<CSLLUAComInstance,0>::Release(void)

- ea: `0x18001d3d0`
- end: `0x18001d41f`
- name: `?Release@?$CUnknownImplT@VCSLLUAComInstance@@$0A@@@UEAAKXZ`
- size: `79`
- prototype: `__int64 __fastcall(LPVOID lpMem)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18001d3d0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001d3ea`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001d3ea`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001d3fe`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001d3fe`

## pseudocode

```c
__int64 __fastcall CUnknownImplT<CSLLUAComInstance,0>::Release(volatile signed __int32 *lpMem)
{
  unsigned __int32 v2; // ebx
  HANDLE ProcessHeap; // rax

  v2 = _InterlockedDecrement(lpMem + 4);
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
0x18001d3d0  mov     [rsp+arg_0], rbx
0x18001d3d5  push    rdi
0x18001d3d6  sub     rsp, 20h
0x18001d3da  mov     rdi, rcx
0x18001d3dd  or      ebx, 0FFFFFFFFh
0x18001d3e0  lock xadd [rcx+10h], ebx
0x18001d3e5  sub     ebx, 1
0x18001d3e8  jnz     short loc_18001D411
0x18001d3ea  call    cs:__imp_GetProcessHeap
0x18001d3f1  nop     dword ptr [rax+rax+00h]
0x18001d3f6  mov     r8, rdi; lpMem
0x18001d3f9  xor     edx, edx; dwFlags
0x18001d3fb  mov     rcx, rax; hHeap
0x18001d3fe  call    cs:__imp_HeapFree
0x18001d405  nop     dword ptr [rax+rax+00h]
0x18001d40a  lock dec cs:?g_lServerLockCount@?$CComProcessCounter@$0A@@@0JA; long CComProcessCounter<0>::g_lServerLockCount
0x18001d411  mov     eax, ebx
0x18001d413  mov     rbx, [rsp+28h+arg_0]
0x18001d418  add     rsp, 20h
0x18001d41c  pop     rdi
0x18001d41d  retn
```
