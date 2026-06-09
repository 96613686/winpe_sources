# IsVMAddedToACollection(void)

- ea: `0x180093828`
- end: `0x1800938b2`
- name: `?IsVMAddedToACollection@@YAHXZ`
- size: `138`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180010060`
- `0x180093758`

## callees

- `0x1800321f0`
- `0x180093828`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180093895`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180093895`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180093871`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180093871`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180093859`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180093859`

## string_xrefs

- `0x180093844`: `vmbuspipe.dll`

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
0x180093828  push    rbx
0x18009382a  sub     rsp, 40h
0x18009382e  mov     rax, cs:__security_cookie
0x180093835  xor     rax, rsp
0x180093838  mov     [rsp+48h+var_10], rax
0x18009383d  movups  xmm0, cs:RdvVmEndPointTypeGuidTransport
0x180093844  lea     rcx, aVmbuspipeDll; "vmbuspipe.dll"
0x18009384b  mov     [rsp+48h+var_28], 0
0x180093853  movdqu  [rsp+48h+var_20], xmm0
0x180093859  call    cs:__imp_LoadLibraryW
0x18009385f  mov     rbx, rax
0x180093862  test    rax, rax
0x180093865  jz      short loc_18009389B
0x180093867  lea     rdx, aVmbuspipeclien; "VmbusPipeClientEnumeratePipes"
0x18009386e  mov     rcx, rax; hModule
0x180093871  call    cs:__imp_GetProcAddress
0x180093877  test    rax, rax
0x18009387a  jz      short loc_180093892
0x18009387c  lea     r8, ?EnumeratePipeCallback@@YAXPEAXPEAEPEAU_VMBUS_PIPE_CHANNEL_INFO@@PEBU_GUID@@@Z; EnumeratePipeCallback(void *,uchar *,_VMBUS_PIPE_CHANNEL_INFO *,_GUID const *)
0x180093883  lea     rdx, [rsp+48h+var_28]
0x180093888  lea     rcx, [rsp+48h+var_20]
0x18009388d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180093892  mov     rcx, rbx; hLibModule
0x180093895  call    cs:__imp_FreeLibrary
0x18009389b  mov     eax, [rsp+48h+var_28]
0x18009389f  mov     rcx, [rsp+48h+var_10]
0x1800938a4  xor     rcx, rsp; StackCookie
0x1800938a7  call    __security_check_cookie
0x1800938ac  add     rsp, 40h
0x1800938b0  pop     rbx
0x1800938b1  retn
```
