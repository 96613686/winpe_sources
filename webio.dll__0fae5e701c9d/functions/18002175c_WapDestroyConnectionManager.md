# WapDestroyConnectionManager

- ea: `0x18002175c`
- end: `0x180021838`
- name: `WapDestroyConnectionManager`
- size: `220`
- prototype: `__int64 __fastcall(LPVOID lpMem)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x180026504`

## callees

- `0x18002175c`
- `0x180021840`
- `0x18002187c`
- `0x180021dcc`
- `0x180026504`
- `0x180098010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800217d0`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800217d0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800217f7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800217f7`

## pseudocode

```c
__int64 __fastcall WapDestroyConnectionManager(char *lpMem)
{
  __int64 v2; // rcx
  __int64 v3; // rcx
  void *v4; // rcx
  __int64 v5; // rdi
  bool v6; // zf

  v2 = *((_QWORD *)lpMem + 11);
  if ( v2 )
  {
    WaDereferenceEndpoint(v2);
    *((_QWORD *)lpMem + 11) = 0;
  }
  v3 = *((_QWORD *)lpMem + 12);
  if ( v3 )
  {
    WaDereferenceEndpoint(v3);
    *((_QWORD *)lpMem + 12) = 0;
  }
  v4 = (void *)*((_QWORD *)lpMem + 84);
  if ( v4 )
  {
    WaDereferenceConnectionManager(v4);
    *((_QWORD *)lpMem + 84) = 0;
  }
  WaTpTerminateWorkItem(lpMem + 272);
  WaFreeConnectionRequestProperties(lpMem + 336);
  v5 = *((_QWORD *)lpMem + 10);
  *((_QWORD *)lpMem + 10) = 0;
  DeleteCriticalSection((LPCRITICAL_SECTION)(lpMem + 32));
  v6 = g_fWxHeapExtensionInitialized == 0;
  *(_DWORD *)lpMem = 1919380835;
  if ( v6 )
    HeapFree(g_hWxProcessHeap, 0, lpMem);
  else
    g_WxHeapExtensionInterfaces(lpMem);
  return WaDereferenceEndpoint(v5);
}

```

## disassembly

```asm
0x18002175c  mov     [rsp+arg_8], rbx
0x180021761  push    rdi
0x180021762  sub     rsp, 20h
0x180021766  mov     rbx, rcx
0x180021769  mov     rcx, [rcx+58h]
0x18002176d  test    rcx, rcx
0x180021770  jz      short loc_18002177F
0x180021772  call    WaDereferenceEndpoint
0x180021777  mov     qword ptr [rbx+58h], 0
0x18002177f  mov     rcx, [rbx+60h]
0x180021783  test    rcx, rcx
0x180021786  jnz     loc_180021815
0x18002178c  mov     rcx, [rbx+2A0h]; lpMem
0x180021793  test    rcx, rcx
0x180021796  jz      short loc_1800217A8
0x180021798  call    WaDereferenceConnectionManager
0x18002179d  mov     qword ptr [rbx+2A0h], 0
0x1800217a8  lea     rcx, [rbx+110h]
0x1800217af  call    WaTpTerminateWorkItem
0x1800217b4  lea     rcx, [rbx+150h]
0x1800217bb  call    WaFreeConnectionRequestProperties
0x1800217c0  mov     rdi, [rbx+50h]
0x1800217c4  lea     rcx, [rbx+20h]; lpCriticalSection
0x1800217c8  mov     qword ptr [rbx+50h], 0
0x1800217d0  call    cs:__imp_DeleteCriticalSection
0x1800217d7  nop     dword ptr [rax+rax+00h]
0x1800217dc  cmp     cs:?g_fWxHeapExtensionInitialized@@3HA, 0; int g_fWxHeapExtensionInitialized
0x1800217e3  mov     dword ptr [rbx], 72676D63h
0x1800217e9  jnz     short loc_180021827
0x1800217eb  mov     rcx, cs:g_hWxProcessHeap; hHeap
0x1800217f2  mov     r8, rbx; lpMem
0x1800217f5  xor     edx, edx; dwFlags
0x1800217f7  call    cs:__imp_HeapFree
0x1800217fe  nop     dword ptr [rax+rax+00h]
0x180021803  mov     rcx, rdi
0x180021806  mov     rbx, [rsp+28h+arg_8]
0x18002180b  add     rsp, 20h
0x18002180f  pop     rdi
0x180021810  jmp     WaDereferenceEndpoint
0x180021815  call    WaDereferenceEndpoint
0x18002181a  mov     qword ptr [rbx+60h], 0
0x180021822  jmp     loc_18002178C
0x180021827  mov     rax, cs:?g_WxHeapExtensionInterfaces@@3U_WX_HEAP_EXTENSION@@A; _WX_HEAP_EXTENSION g_WxHeapExtensionInterfaces
0x18002182e  mov     rcx, rbx
0x180021831  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021836  jmp     short loc_180021803
```
