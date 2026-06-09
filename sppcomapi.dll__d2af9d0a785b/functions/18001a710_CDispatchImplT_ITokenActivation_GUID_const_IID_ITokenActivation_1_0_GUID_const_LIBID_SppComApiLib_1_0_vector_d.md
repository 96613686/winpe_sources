# CDispatchImplT<ITokenActivation,&_GUID const IID_ITokenActivation,1,0,&_GUID const LIBID_SppComApiLib,1,0>::`vector deleting destructor'(uint)

- ea: `0x18001a710`
- end: `0x18001a758`
- name: `??_E?$CDispatchImplT@UITokenActivation@@$1?IID_ITokenActivation@@3U_GUID@@B$00$0A@$1?LIBID_SppComApiLib@@3U3@B$00$0A@@@MEAAPEAXI@Z`
- size: `72`
- prototype: `__int64 __fastcall(LPVOID lpMem)`
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callees

- `0x18001a010`
- `0x18001a710`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001a729`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001a729`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001a73d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001a73d`

## pseudocode

```c
LPVOID __fastcall CDispatchImplT<ITokenActivation,&_GUID const IID_ITokenActivation,1,0,&_GUID const LIBID_SppComApiLib,1,0>::`vector deleting destructor'(
        LPVOID lpMem,
        char a2)
{
  HANDLE ProcessHeap; // rax

  CDispatchImplT<ITokenActivation,&_GUID const IID_ITokenActivation,1,0,&_GUID const LIBID_SppComApiLib,1,0>::~CDispatchImplT<ITokenActivation,&_GUID const IID_ITokenActivation,1,0,&_GUID const LIBID_SppComApiLib,1,0>((__int64)lpMem);
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
0x18001a710  mov     [rsp+arg_0], rbx
0x18001a715  push    rdi
0x18001a716  sub     rsp, 20h
0x18001a71a  mov     ebx, edx
0x18001a71c  mov     rdi, rcx
0x18001a71f  call    ??1?$CDispatchImplT@UITokenActivation@@$1?IID_ITokenActivation@@3U_GUID@@B$00$0A@$1?LIBID_SppComApiLib@@3U3@B$00$0A@@@MEAA@XZ; CDispatchImplT<ITokenActivation,&_GUID const IID_ITokenActivation,1,0,&_GUID const LIBID_SppComApiLib,1,0>::~CDispatchImplT<ITokenActivation,&_GUID const IID_ITokenActivation,1,0,&_GUID const LIBID_SppComApiLib,1,0>(void)
0x18001a724  test    bl, 1
0x18001a727  jz      short loc_18001A749
0x18001a729  call    cs:__imp_GetProcessHeap
0x18001a730  nop     dword ptr [rax+rax+00h]
0x18001a735  mov     r8, rdi; lpMem
0x18001a738  xor     edx, edx; dwFlags
0x18001a73a  mov     rcx, rax; hHeap
0x18001a73d  call    cs:__imp_HeapFree
0x18001a744  nop     dword ptr [rax+rax+00h]
0x18001a749  mov     rbx, [rsp+28h+arg_0]
0x18001a74e  mov     rax, rdi
0x18001a751  add     rsp, 20h
0x18001a755  pop     rdi
0x18001a756  retn
```
