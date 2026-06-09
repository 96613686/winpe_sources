# CDispatchImplT<IOfflineActivation,&_GUID const IID_IOfflineActivation,1,0,&_GUID const LIBID_SppComApiLib,1,0>::`vector deleting destructor'(uint)

- ea: `0x18001a670`
- end: `0x18001a6b8`
- name: `??_E?$CDispatchImplT@UIOfflineActivation@@$1?IID_IOfflineActivation@@3U_GUID@@B$00$0A@$1?LIBID_SppComApiLib@@3U3@B$00$0A@@@MEAAPEAXI@Z`
- size: `72`
- prototype: `__int64 __fastcall(LPVOID lpMem)`
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180019ee0`
- `0x18001a670`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001a689`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001a689`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001a69d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001a69d`

## pseudocode

```c
LPVOID __fastcall CDispatchImplT<IOfflineActivation,&_GUID const IID_IOfflineActivation,1,0,&_GUID const LIBID_SppComApiLib,1,0>::`vector deleting destructor'(
        LPVOID lpMem,
        char a2)
{
  HANDLE ProcessHeap; // rax

  CDispatchImplT<IOfflineActivation,&_GUID const IID_IOfflineActivation,1,0,&_GUID const LIBID_SppComApiLib,1,0>::~CDispatchImplT<IOfflineActivation,&_GUID const IID_IOfflineActivation,1,0,&_GUID const LIBID_SppComApiLib,1,0>((__int64)lpMem);
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
0x18001a670  mov     [rsp+arg_0], rbx
0x18001a675  push    rdi
0x18001a676  sub     rsp, 20h
0x18001a67a  mov     ebx, edx
0x18001a67c  mov     rdi, rcx
0x18001a67f  call    ??1?$CDispatchImplT@UIOfflineActivation@@$1?IID_IOfflineActivation@@3U_GUID@@B$00$0A@$1?LIBID_SppComApiLib@@3U3@B$00$0A@@@MEAA@XZ; CDispatchImplT<IOfflineActivation,&_GUID const IID_IOfflineActivation,1,0,&_GUID const LIBID_SppComApiLib,1,0>::~CDispatchImplT<IOfflineActivation,&_GUID const IID_IOfflineActivation,1,0,&_GUID const LIBID_SppComApiLib,1,0>(void)
0x18001a684  test    bl, 1
0x18001a687  jz      short loc_18001A6A9
0x18001a689  call    cs:__imp_GetProcessHeap
0x18001a690  nop     dword ptr [rax+rax+00h]
0x18001a695  mov     r8, rdi; lpMem
0x18001a698  xor     edx, edx; dwFlags
0x18001a69a  mov     rcx, rax; hHeap
0x18001a69d  call    cs:__imp_HeapFree
0x18001a6a4  nop     dword ptr [rax+rax+00h]
0x18001a6a9  mov     rbx, [rsp+28h+arg_0]
0x18001a6ae  mov     rax, rdi
0x18001a6b1  add     rsp, 20h
0x18001a6b5  pop     rdi
0x18001a6b6  retn
```
