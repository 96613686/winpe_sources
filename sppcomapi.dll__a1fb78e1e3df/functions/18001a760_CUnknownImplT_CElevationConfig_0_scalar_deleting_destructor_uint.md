# CUnknownImplT<CElevationConfig,0>::`scalar deleting destructor'(uint)

- ea: `0x18001a760`
- end: `0x18001a7cf`
- name: `??_G?$CUnknownImplT@VCElevationConfig@@$0A@@@UEAAPEAXI@Z`
- size: `111`
- prototype: `__int64 __fastcall(LPVOID lpMem)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x180019db0`
- `0x18001a760`
- `0x18003d010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001a7a0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001a7a0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001a7b4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001a7b4`

## pseudocode

```c
_QWORD *__fastcall CUnknownImplT<CElevationConfig,0>::`scalar deleting destructor'(_QWORD *lpMem, char a2)
{
  __int64 v4; // rcx
  HANDLE ProcessHeap; // rax

  v4 = lpMem[18];
  if ( v4 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
    lpMem[18] = 0;
  }
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
0x18001a760  mov     [rsp+arg_0], rbx
0x18001a765  push    rdi
0x18001a766  sub     rsp, 20h
0x18001a76a  mov     rbx, rcx
0x18001a76d  mov     edi, edx
0x18001a76f  mov     rcx, [rcx+90h]
0x18001a776  test    rcx, rcx
0x18001a779  jz      short loc_18001A792
0x18001a77b  mov     rax, [rcx]
0x18001a77e  mov     rax, [rax+10h]
0x18001a782  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a787  mov     qword ptr [rbx+90h], 0
0x18001a792  mov     rcx, rbx
0x18001a795  call    ??1?$CDispatchImplT@UIElevationConfig@@$1?IID_IElevationConfig@@3U_GUID@@B$00$0A@$1?LIBID_SppComApiLib@@3U3@B$00$0A@@@MEAA@XZ; CDispatchImplT<IElevationConfig,&_GUID const IID_IElevationConfig,1,0,&_GUID const LIBID_SppComApiLib,1,0>::~CDispatchImplT<IElevationConfig,&_GUID const IID_IElevationConfig,1,0,&_GUID const LIBID_SppComApiLib,1,0>(void)
0x18001a79a  test    dil, 1
0x18001a79e  jz      short loc_18001A7C0
0x18001a7a0  call    cs:__imp_GetProcessHeap
0x18001a7a7  nop     dword ptr [rax+rax+00h]
0x18001a7ac  mov     r8, rbx; lpMem
0x18001a7af  xor     edx, edx; dwFlags
0x18001a7b1  mov     rcx, rax; hHeap
0x18001a7b4  call    cs:__imp_HeapFree
0x18001a7bb  nop     dword ptr [rax+rax+00h]
0x18001a7c0  mov     rax, rbx
0x18001a7c3  mov     rbx, [rsp+28h+arg_0]
0x18001a7c8  add     rsp, 20h
0x18001a7cc  pop     rdi
0x18001a7cd  retn
```
