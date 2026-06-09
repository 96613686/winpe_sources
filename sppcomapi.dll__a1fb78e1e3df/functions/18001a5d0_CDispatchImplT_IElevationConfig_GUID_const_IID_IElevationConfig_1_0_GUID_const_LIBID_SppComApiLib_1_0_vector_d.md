# CDispatchImplT<IElevationConfig,&_GUID const IID_IElevationConfig,1,0,&_GUID const LIBID_SppComApiLib,1,0>::`vector deleting destructor'(uint)

- ea: `0x18001a5d0`
- end: `0x18001a618`
- name: `??_E?$CDispatchImplT@UIElevationConfig@@$1?IID_IElevationConfig@@3U_GUID@@B$00$0A@$1?LIBID_SppComApiLib@@3U3@B$00$0A@@@MEAAPEAXI@Z`
- size: `72`
- prototype: `__int64 __fastcall(LPVOID lpMem)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x180019db0`
- `0x18001a5d0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001a5e9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001a5e9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001a5fd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001a5fd`

## pseudocode

```c
LPVOID __fastcall CDispatchImplT<IElevationConfig,&_GUID const IID_IElevationConfig,1,0,&_GUID const LIBID_SppComApiLib,1,0>::`vector deleting destructor'(
        LPVOID lpMem,
        char a2)
{
  HANDLE ProcessHeap; // rax

  CDispatchImplT<IElevationConfig,&_GUID const IID_IElevationConfig,1,0,&_GUID const LIBID_SppComApiLib,1,0>::~CDispatchImplT<IElevationConfig,&_GUID const IID_IElevationConfig,1,0,&_GUID const LIBID_SppComApiLib,1,0>((__int64)lpMem);
  if ( (a2 & 1) != 0 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, lpMem);
  }
  return lpMem;
}

```

## disassembly

```asm
0x18001a5d0  mov     [rsp+arg_0], rbx
0x18001a5d5  push    rdi
0x18001a5d6  sub     rsp, 20h
0x18001a5da  mov     ebx, edx
0x18001a5dc  mov     rdi, rcx
0x18001a5df  call    ??1?$CDispatchImplT@UIElevationConfig@@$1?IID_IElevationConfig@@3U_GUID@@B$00$0A@$1?LIBID_SppComApiLib@@3U3@B$00$0A@@@MEAA@XZ; CDispatchImplT<IElevationConfig,&_GUID const IID_IElevationConfig,1,0,&_GUID const LIBID_SppComApiLib,1,0>::~CDispatchImplT<IElevationConfig,&_GUID const IID_IElevationConfig,1,0,&_GUID const LIBID_SppComApiLib,1,0>(void)
0x18001a5e4  test    bl, 1
0x18001a5e7  jz      short loc_18001A609
0x18001a5e9  call    cs:__imp_GetProcessHeap
0x18001a5f0  nop     dword ptr [rax+rax+00h]
0x18001a5f5  mov     r8, rdi; lpMem
0x18001a5f8  xor     edx, edx; dwFlags
0x18001a5fa  mov     rcx, rax; hHeap
0x18001a5fd  call    cs:__imp_HeapFree
0x18001a604  nop     dword ptr [rax+rax+00h]
0x18001a609  mov     rbx, [rsp+28h+arg_0]
0x18001a60e  mov     rax, rdi
0x18001a611  add     rsp, 20h
0x18001a615  pop     rdi
0x18001a616  retn
```
