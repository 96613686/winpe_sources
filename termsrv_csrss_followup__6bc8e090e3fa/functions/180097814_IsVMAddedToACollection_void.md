# IsVMAddedToACollection(void)

- ea: `0x180097814`
- end: `0x1800978b1`
- name: `?IsVMAddedToACollection@@YAHXZ`
- size: `157`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180010780`
- `0x180097730`

## callees

- `0x180033f60`
- `0x180097814`
- `0x1800ce010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18009788d`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18009788d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180097863`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180097863`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180097845`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180097845`

## string_xrefs

- `0x180097830`: `vmbuspipe.dll`

## pseudocode

```c
__int64 IsVMAddedToACollection(void)
{
  HMODULE LibraryW; // rax
  HMODULE v1; // rbx
  FARPROC ProcAddress; // rax
  unsigned int v4; // [rsp+20h] [rbp-28h] BYREF
  __int128 v5; // [rsp+28h] [rbp-20h] BYREF

  v4 = 0;
  v5 = RdvVmEndPointTypeGuidTransport;
  LibraryW = LoadLibraryW(L"vmbuspipe.dll");
  v1 = LibraryW;
  if ( LibraryW )
  {
    ProcAddress = GetProcAddress(LibraryW, "VmbusPipeClientEnumeratePipes");
    if ( ProcAddress )
      ((void (__fastcall *)(__int128 *, unsigned int *, void (__fastcall *)(void *, unsigned __int8 *, struct _VMBUS_PIPE_CHANNEL_INFO *, const struct _GUID *)))ProcAddress)(
        &v5,
        &v4,
        EnumeratePipeCallback);
    FreeLibrary(v1);
  }
  return v4;
}

```

## disassembly

```asm
0x180097814  push    rbx
0x180097816  sub     rsp, 40h
0x18009781a  mov     rax, cs:__security_cookie
0x180097821  xor     rax, rsp
0x180097824  mov     [rsp+48h+var_10], rax
0x180097829  movups  xmm0, cs:RdvVmEndPointTypeGuidTransport
0x180097830  lea     rcx, aVmbuspipeDll; "vmbuspipe.dll"
0x180097837  mov     [rsp+48h+var_28], 0
0x18009783f  movdqu  [rsp+48h+var_20], xmm0
0x180097845  call    cs:__imp_LoadLibraryW
0x18009784c  nop     dword ptr [rax+rax+00h]
0x180097851  mov     rbx, rax
0x180097854  test    rax, rax
0x180097857  jz      short loc_180097899
0x180097859  lea     rdx, aVmbuspipeclien; "VmbusPipeClientEnumeratePipes"
0x180097860  mov     rcx, rax; hModule
0x180097863  call    cs:__imp_GetProcAddress
0x18009786a  nop     dword ptr [rax+rax+00h]
0x18009786f  test    rax, rax
0x180097872  jz      short loc_18009788A
0x180097874  lea     r8, ?EnumeratePipeCallback@@YAXPEAXPEAEPEAU_VMBUS_PIPE_CHANNEL_INFO@@PEBU_GUID@@@Z; EnumeratePipeCallback(void *,uchar *,_VMBUS_PIPE_CHANNEL_INFO *,_GUID const *)
0x18009787b  lea     rdx, [rsp+48h+var_28]
0x180097880  lea     rcx, [rsp+48h+var_20]
0x180097885  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009788a  mov     rcx, rbx; hLibModule
0x18009788d  call    cs:__imp_FreeLibrary
0x180097894  nop     dword ptr [rax+rax+00h]
0x180097899  mov     eax, [rsp+48h+var_28]
0x18009789d  mov     rcx, [rsp+48h+var_10]
0x1800978a2  xor     rcx, rsp; StackCookie
0x1800978a5  call    __security_check_cookie
0x1800978aa  add     rsp, 40h
0x1800978ae  pop     rbx
0x1800978af  retn
```
