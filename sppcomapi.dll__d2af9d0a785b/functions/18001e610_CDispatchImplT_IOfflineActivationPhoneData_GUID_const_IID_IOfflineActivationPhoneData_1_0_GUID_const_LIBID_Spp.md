# CDispatchImplT<IOfflineActivationPhoneData,&_GUID const IID_IOfflineActivationPhoneData,1,0,&_GUID const LIBID_SppComApiLib,1,0>::`scalar deleting destructor'(uint)

- ea: `0x18001e610`
- end: `0x18001e658`
- name: `??_G?$CDispatchImplT@UIOfflineActivationPhoneData@@$1?IID_IOfflineActivationPhoneData@@3U_GUID@@B$00$0A@$1?LIBID_SppComApiLib@@3U3@B$00$0A@@@MEAAPEAXI@Z`
- size: `72`
- prototype: `__int64 __fastcall(LPVOID lpMem)`
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callees

- `0x18001e3c8`
- `0x18001e610`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001e629`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001e629`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001e63d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001e63d`

## pseudocode

```c
LPVOID __fastcall CDispatchImplT<IOfflineActivationPhoneData,&_GUID const IID_IOfflineActivationPhoneData,1,0,&_GUID const LIBID_SppComApiLib,1,0>::`scalar deleting destructor'(
        LPVOID lpMem,
        char a2)
{
  HANDLE ProcessHeap; // rax

  CDispatchImplT<IOfflineActivationPhoneData,&_GUID const IID_IOfflineActivationPhoneData,1,0,&_GUID const LIBID_SppComApiLib,1,0>::~CDispatchImplT<IOfflineActivationPhoneData,&_GUID const IID_IOfflineActivationPhoneData,1,0,&_GUID const LIBID_SppComApiLib,1,0>((__int64)lpMem);
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
0x18001e610  mov     [rsp+arg_0], rbx
0x18001e615  push    rdi
0x18001e616  sub     rsp, 20h
0x18001e61a  mov     ebx, edx
0x18001e61c  mov     rdi, rcx
0x18001e61f  call    ??1?$CDispatchImplT@UIOfflineActivationPhoneData@@$1?IID_IOfflineActivationPhoneData@@3U_GUID@@B$00$0A@$1?LIBID_SppComApiLib@@3U3@B$00$0A@@@MEAA@XZ; CDispatchImplT<IOfflineActivationPhoneData,&_GUID const IID_IOfflineActivationPhoneData,1,0,&_GUID const LIBID_SppComApiLib,1,0>::~CDispatchImplT<IOfflineActivationPhoneData,&_GUID const IID_IOfflineActivationPhoneData,1,0,&_GUID const LIBID_SppComApiLib,1,0>(void)
0x18001e624  test    bl, 1
0x18001e627  jz      short loc_18001E649
0x18001e629  call    cs:__imp_GetProcessHeap
0x18001e630  nop     dword ptr [rax+rax+00h]
0x18001e635  mov     r8, rdi; lpMem
0x18001e638  xor     edx, edx; dwFlags
0x18001e63a  mov     rcx, rax; hHeap
0x18001e63d  call    cs:__imp_HeapFree
0x18001e644  nop     dword ptr [rax+rax+00h]
0x18001e649  mov     rbx, [rsp+28h+arg_0]
0x18001e64e  mov     rax, rdi
0x18001e651  add     rsp, 20h
0x18001e655  pop     rdi
0x18001e656  retn
```
