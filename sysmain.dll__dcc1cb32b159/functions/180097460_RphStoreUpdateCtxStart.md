# RphStoreUpdateCtxStart

- ea: `0x180097460`
- end: `0x1800974e1`
- name: `RphStoreUpdateCtxStart`
- size: `129`
- prototype: `__int64 __fastcall(LPVOID lpParameter)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, installer_update`

## callers

- `0x1800971b0`

## callees

- `0x180097460`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x18009747f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180097490`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180097490`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800974a4`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800974ca`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800974ca`
- `ext-ms-win-sysmain-pfsapi-l1-1-0!SmuGetControlDeviceHandle` at `0x18009746e`
- `ext-ms-win-sysmain-pfsapi-l1-1-0!SmuGetControlDeviceHandle` at `0x18009746e`

## pseudocode

```c
ULONG __fastcall RphStoreUpdateCtxStart(_QWORD *lpParameter)
{
  NTSTATUS ControlDeviceHandle; // eax
  HANDLE EventW; // rax
  HANDLE Thread; // rax

  ControlDeviceHandle = SmuGetControlDeviceHandle(lpParameter, 3221225472LL);
  if ( ControlDeviceHandle < 0 )
    return RtlNtStatusToDosError(ControlDeviceHandle);
  EventW = CreateEventW(0, 0, 0, 0);
  lpParameter[3] = EventW;
  if ( EventW && (Thread = CreateThread(0, 0, RphStoreUpdateWorker, lpParameter, 0, 0), (lpParameter[1] = Thread) != 0) )
    return 0;
  else
    return GetLastError();
}

```

## disassembly

```asm
0x180097460  push    rbx
0x180097462  sub     rsp, 30h
0x180097466  mov     edx, 0C0000000h
0x18009746b  mov     rbx, rcx
0x18009746e  call    cs:__imp_SmuGetControlDeviceHandle
0x180097474  test    eax, eax
0x180097476  jns     short loc_180097486
0x180097478  mov     ecx, eax
0x18009747a  add     rsp, 30h
0x18009747e  pop     rbx
0x18009747f  jmp     cs:__imp_RtlNtStatusToDosError
0x180097486  xor     r9d, r9d; lpName
0x180097489  xor     r8d, r8d; bInitialState
0x18009748c  xor     edx, edx; bManualReset
0x18009748e  xor     ecx, ecx; lpEventAttributes
0x180097490  call    cs:__imp_CreateEventW
0x180097496  mov     [rbx+18h], rax
0x18009749a  test    rax, rax
0x18009749d  jnz     short loc_1800974AB
0x18009749f  add     rsp, 30h
0x1800974a3  pop     rbx
0x1800974a4  jmp     cs:__imp_GetLastError
0x1800974ab  mov     [rsp+38h+lpThreadId], 0; lpThreadId
0x1800974b4  lea     r8, RphStoreUpdateWorker; lpStartAddress
0x1800974bb  mov     r9, rbx; lpParameter
0x1800974be  mov     [rsp+38h+dwCreationFlags], 0; dwCreationFlags
0x1800974c6  xor     edx, edx; dwStackSize
0x1800974c8  xor     ecx, ecx; lpThreadAttributes
0x1800974ca  call    cs:__imp_CreateThread
0x1800974d0  mov     [rbx+8], rax
0x1800974d4  test    rax, rax
0x1800974d7  jz      short loc_18009749F
0x1800974d9  xor     eax, eax
0x1800974db  add     rsp, 30h
0x1800974df  pop     rbx
0x1800974e0  retn
```
