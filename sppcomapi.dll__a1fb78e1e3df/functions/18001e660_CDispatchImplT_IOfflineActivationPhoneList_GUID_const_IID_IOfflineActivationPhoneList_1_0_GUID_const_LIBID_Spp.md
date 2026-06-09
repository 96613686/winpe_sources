# CDispatchImplT<IOfflineActivationPhoneList,&_GUID const IID_IOfflineActivationPhoneList,1,0,&_GUID const LIBID_SppComApiLib,1,0>::`scalar deleting destructor'(uint)

- ea: `0x18001e660`
- end: `0x18001e6a8`
- name: `??_G?$CDispatchImplT@UIOfflineActivationPhoneList@@$1?IID_IOfflineActivationPhoneList@@3U_GUID@@B$00$0A@$1?LIBID_SppComApiLib@@3U3@B$00$0A@@@MEAAPEAXI@Z`
- size: `72`
- prototype: `__int64 __fastcall(LPVOID lpMem)`
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callees

- `0x18001e460`
- `0x18001e660`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001e679`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001e679`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001e68d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001e68d`

## pseudocode

```c
LPVOID __fastcall CDispatchImplT<IOfflineActivationPhoneList,&_GUID const IID_IOfflineActivationPhoneList,1,0,&_GUID const LIBID_SppComApiLib,1,0>::`scalar deleting destructor'(
        LPVOID lpMem,
        char a2)
{
  HANDLE ProcessHeap; // rax

  CDispatchImplT<IOfflineActivationPhoneList,&_GUID const IID_IOfflineActivationPhoneList,1,0,&_GUID const LIBID_SppComApiLib,1,0>::~CDispatchImplT<IOfflineActivationPhoneList,&_GUID const IID_IOfflineActivationPhoneList,1,0,&_GUID const LIBID_SppComApiLib,1,0>((__int64)lpMem);
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
0x18001e660  mov     [rsp+arg_0], rbx
0x18001e665  push    rdi
0x18001e666  sub     rsp, 20h
0x18001e66a  mov     ebx, edx
0x18001e66c  mov     rdi, rcx
0x18001e66f  call    ??1?$CDispatchImplT@UIOfflineActivationPhoneList@@$1?IID_IOfflineActivationPhoneList@@3U_GUID@@B$00$0A@$1?LIBID_SppComApiLib@@3U3@B$00$0A@@@MEAA@XZ; CDispatchImplT<IOfflineActivationPhoneList,&_GUID const IID_IOfflineActivationPhoneList,1,0,&_GUID const LIBID_SppComApiLib,1,0>::~CDispatchImplT<IOfflineActivationPhoneList,&_GUID const IID_IOfflineActivationPhoneList,1,0,&_GUID const LIBID_SppComApiLib,1,0>(void)
0x18001e674  test    bl, 1
0x18001e677  jz      short loc_18001E699
0x18001e679  call    cs:__imp_GetProcessHeap
0x18001e680  nop     dword ptr [rax+rax+00h]
0x18001e685  mov     r8, rdi; lpMem
0x18001e688  xor     edx, edx; dwFlags
0x18001e68a  mov     rcx, rax; hHeap
0x18001e68d  call    cs:__imp_HeapFree
0x18001e694  nop     dword ptr [rax+rax+00h]
0x18001e699  mov     rbx, [rsp+28h+arg_0]
0x18001e69e  mov     rax, rdi
0x18001e6a1  add     rsp, 20h
0x18001e6a5  pop     rdi
0x18001e6a6  retn
```
