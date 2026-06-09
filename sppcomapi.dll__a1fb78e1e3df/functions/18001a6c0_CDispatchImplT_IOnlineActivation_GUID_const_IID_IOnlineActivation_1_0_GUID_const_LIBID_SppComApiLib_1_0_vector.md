# CDispatchImplT<IOnlineActivation,&_GUID const IID_IOnlineActivation,1,0,&_GUID const LIBID_SppComApiLib,1,0>::`vector deleting destructor'(uint)

- ea: `0x18001a6c0`
- end: `0x18001a708`
- name: `??_E?$CDispatchImplT@UIOnlineActivation@@$1?IID_IOnlineActivation@@3U_GUID@@B$00$0A@$1?LIBID_SppComApiLib@@3U3@B$00$0A@@@MEAAPEAXI@Z`
- size: `72`
- prototype: `__int64 __fastcall(LPVOID lpMem)`
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180019f78`
- `0x18001a6c0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001a6d9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001a6d9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001a6ed`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001a6ed`

## pseudocode

```c
LPVOID __fastcall CDispatchImplT<IOnlineActivation,&_GUID const IID_IOnlineActivation,1,0,&_GUID const LIBID_SppComApiLib,1,0>::`vector deleting destructor'(
        LPVOID lpMem,
        char a2)
{
  HANDLE ProcessHeap; // rax

  CDispatchImplT<IOnlineActivation,&_GUID const IID_IOnlineActivation,1,0,&_GUID const LIBID_SppComApiLib,1,0>::~CDispatchImplT<IOnlineActivation,&_GUID const IID_IOnlineActivation,1,0,&_GUID const LIBID_SppComApiLib,1,0>((__int64)lpMem);
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
0x18001a6c0  mov     [rsp+arg_0], rbx
0x18001a6c5  push    rdi
0x18001a6c6  sub     rsp, 20h
0x18001a6ca  mov     ebx, edx
0x18001a6cc  mov     rdi, rcx
0x18001a6cf  call    ??1?$CDispatchImplT@UIOnlineActivation@@$1?IID_IOnlineActivation@@3U_GUID@@B$00$0A@$1?LIBID_SppComApiLib@@3U3@B$00$0A@@@MEAA@XZ; CDispatchImplT<IOnlineActivation,&_GUID const IID_IOnlineActivation,1,0,&_GUID const LIBID_SppComApiLib,1,0>::~CDispatchImplT<IOnlineActivation,&_GUID const IID_IOnlineActivation,1,0,&_GUID const LIBID_SppComApiLib,1,0>(void)
0x18001a6d4  test    bl, 1
0x18001a6d7  jz      short loc_18001A6F9
0x18001a6d9  call    cs:__imp_GetProcessHeap
0x18001a6e0  nop     dword ptr [rax+rax+00h]
0x18001a6e5  mov     r8, rdi; lpMem
0x18001a6e8  xor     edx, edx; dwFlags
0x18001a6ea  mov     rcx, rax; hHeap
0x18001a6ed  call    cs:__imp_HeapFree
0x18001a6f4  nop     dword ptr [rax+rax+00h]
0x18001a6f9  mov     rbx, [rsp+28h+arg_0]
0x18001a6fe  mov     rax, rdi
0x18001a701  add     rsp, 20h
0x18001a705  pop     rdi
0x18001a706  retn
```
