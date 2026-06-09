# WapDestroyDnsIoContext

- ea: `0x180020b24`
- end: `0x180020bfb`
- name: `WapDestroyDnsIoContext`
- size: `215`
- prototype: `__int64 __fastcall(LPVOID lpMem)`
- caller_count: `5`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x1800207e0`
- `0x18005d3d8`
- `0x18005fe9c`
- `0x180060068`
- `0x180065f20`

## callees

- `0x180020b24`
- `0x180022064`
- `0x180098010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180020b9f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180020b9f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x180020b47`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x180020b47`
- `WS2_32!FreeAddrInfoExW` at `0x180020be2`
- `WS2_32!FreeAddrInfoExW` at `0x180020be2`
- `WS2_32!WSACloseEvent` at `0x180020b64`
- `WS2_32!WSACloseEvent` at `0x180020b64`

## pseudocode

```c
signed __int32 __fastcall WapDestroyDnsIoContext(_QWORD *lpMem)
{
  struct addrinfoexW *v2; // rcx
  struct _TP_WAIT *v3; // rcx
  void *v4; // rcx
  bool v5; // zf
  volatile signed __int32 *v6; // rdi
  signed __int32 result; // eax

  v2 = (struct addrinfoexW *)lpMem[11];
  if ( v2 )
  {
    FreeAddrInfoExW(v2);
    lpMem[11] = 0;
  }
  v3 = (struct _TP_WAIT *)lpMem[12];
  if ( v3 )
  {
    CloseThreadpoolWait(v3);
    lpMem[12] = 0;
  }
  v4 = (void *)lpMem[10];
  if ( v4 )
  {
    WSACloseEvent(v4);
    lpMem[10] = 0;
  }
  v5 = g_fWxHeapExtensionInitialized == 0;
  v6 = (volatile signed __int32 *)lpMem[2];
  lpMem[2] = 0;
  *(_DWORD *)lpMem = 1769172580;
  if ( v5 )
    result = HeapFree(g_hWxProcessHeap, 0, lpMem);
  else
    result = g_WxHeapExtensionInterfaces(lpMem);
  if ( v6 )
  {
    result = _InterlockedExchangeAdd(v6 + 1, 0xFFFFFFFF);
    if ( result == 1 )
      return WapDestroyDnsCache((LPVOID)v6);
  }
  return result;
}

```

## disassembly

```asm
0x180020b24  mov     [rsp+arg_8], rbx
0x180020b29  push    rdi
0x180020b2a  sub     rsp, 30h
0x180020b2e  mov     rbx, rcx
0x180020b31  mov     rcx, [rcx+58h]; pAddrInfoEx
0x180020b35  test    rcx, rcx
0x180020b38  jnz     loc_180020BE2
0x180020b3e  mov     rcx, [rbx+60h]; pwa
0x180020b42  test    rcx, rcx
0x180020b45  jz      short loc_180020B5B
0x180020b47  call    cs:__imp_CloseThreadpoolWait
0x180020b4e  nop     dword ptr [rax+rax+00h]
0x180020b53  mov     qword ptr [rbx+60h], 0
0x180020b5b  mov     rcx, [rbx+50h]; hEvent
0x180020b5f  test    rcx, rcx
0x180020b62  jz      short loc_180020B78
0x180020b64  call    cs:__imp_WSACloseEvent
0x180020b6b  nop     dword ptr [rax+rax+00h]
0x180020b70  mov     qword ptr [rbx+50h], 0
0x180020b78  cmp     cs:?g_fWxHeapExtensionInitialized@@3HA, 0; int g_fWxHeapExtensionInitialized
0x180020b7f  mov     rdi, [rbx+10h]
0x180020b83  mov     qword ptr [rbx+10h], 0
0x180020b8b  mov     dword ptr [rbx], 69736E64h
0x180020b91  jnz     short loc_180020BD1
0x180020b93  mov     rcx, cs:g_hWxProcessHeap; hHeap
0x180020b9a  mov     r8, rbx; lpMem
0x180020b9d  xor     edx, edx; dwFlags
0x180020b9f  call    cs:__imp_HeapFree
0x180020ba6  nop     dword ptr [rax+rax+00h]
0x180020bab  test    rdi, rdi
0x180020bae  jz      short loc_180020BC5
0x180020bb0  or      eax, 0FFFFFFFFh
0x180020bb3  lock xadd [rdi+4], eax
0x180020bb8  cmp     eax, 1
0x180020bbb  jnz     short loc_180020BC5
0x180020bbd  mov     rcx, rdi; lpMem
0x180020bc0  call    WapDestroyDnsCache
0x180020bc5  mov     rbx, [rsp+38h+arg_8]
0x180020bca  add     rsp, 30h
0x180020bce  pop     rdi
0x180020bcf  retn
0x180020bd1  mov     rax, cs:?g_WxHeapExtensionInterfaces@@3U_WX_HEAP_EXTENSION@@A; _WX_HEAP_EXTENSION g_WxHeapExtensionInterfaces
0x180020bd8  mov     rcx, rbx
0x180020bdb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020be0  jmp     short loc_180020BAB
0x180020be2  call    cs:__imp_FreeAddrInfoExW
0x180020be9  nop     dword ptr [rax+rax+00h]
0x180020bee  mov     qword ptr [rbx+58h], 0
0x180020bf6  jmp     loc_180020B3E
```
