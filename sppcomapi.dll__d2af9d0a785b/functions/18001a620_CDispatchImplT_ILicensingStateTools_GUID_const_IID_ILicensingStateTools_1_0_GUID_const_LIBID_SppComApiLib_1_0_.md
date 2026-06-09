# CDispatchImplT<ILicensingStateTools,&_GUID const IID_ILicensingStateTools,1,0,&_GUID const LIBID_SppComApiLib,1,0>::`scalar deleting destructor'(uint)

- ea: `0x18001a620`
- end: `0x18001a668`
- name: `??_G?$CDispatchImplT@UILicensingStateTools@@$1?IID_ILicensingStateTools@@3U_GUID@@B$00$0A@$1?LIBID_SppComApiLib@@3U3@B$00$0A@@@MEAAPEAXI@Z`
- size: `72`
- prototype: `__int64 __fastcall(LPVOID lpMem)`
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180019e48`
- `0x18001a620`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001a639`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001a639`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001a64d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001a64d`

## pseudocode

```c
LPVOID __fastcall CDispatchImplT<ILicensingStateTools,&_GUID const IID_ILicensingStateTools,1,0,&_GUID const LIBID_SppComApiLib,1,0>::`scalar deleting destructor'(
        LPVOID lpMem,
        char a2)
{
  HANDLE ProcessHeap; // rax

  CDispatchImplT<ILicensingStateTools,&_GUID const IID_ILicensingStateTools,1,0,&_GUID const LIBID_SppComApiLib,1,0>::~CDispatchImplT<ILicensingStateTools,&_GUID const IID_ILicensingStateTools,1,0,&_GUID const LIBID_SppComApiLib,1,0>((__int64)lpMem);
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
0x18001a620  mov     [rsp+arg_0], rbx
0x18001a625  push    rdi
0x18001a626  sub     rsp, 20h
0x18001a62a  mov     ebx, edx
0x18001a62c  mov     rdi, rcx
0x18001a62f  call    ??1?$CDispatchImplT@UILicensingStateTools@@$1?IID_ILicensingStateTools@@3U_GUID@@B$00$0A@$1?LIBID_SppComApiLib@@3U3@B$00$0A@@@MEAA@XZ; CDispatchImplT<ILicensingStateTools,&_GUID const IID_ILicensingStateTools,1,0,&_GUID const LIBID_SppComApiLib,1,0>::~CDispatchImplT<ILicensingStateTools,&_GUID const IID_ILicensingStateTools,1,0,&_GUID const LIBID_SppComApiLib,1,0>(void)
0x18001a634  test    bl, 1
0x18001a637  jz      short loc_18001A659
0x18001a639  call    cs:__imp_GetProcessHeap
0x18001a640  nop     dword ptr [rax+rax+00h]
0x18001a645  mov     r8, rdi; lpMem
0x18001a648  xor     edx, edx; dwFlags
0x18001a64a  mov     rcx, rax; hHeap
0x18001a64d  call    cs:__imp_HeapFree
0x18001a654  nop     dword ptr [rax+rax+00h]
0x18001a659  mov     rbx, [rsp+28h+arg_0]
0x18001a65e  mov     rax, rdi
0x18001a661  add     rsp, 20h
0x18001a665  pop     rdi
0x18001a666  retn
```
