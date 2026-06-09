# CreateVhdFromSource(ushort const *,ushort const *,ulong)

- ea: `0x18005d148`
- end: `0x18005d24b`
- name: `?CreateVhdFromSource@@YAXPEBG0K@Z`
- size: `259`
- prototype: `void __fastcall(PCWSTR Path, const unsigned __int16 *, unsigned int)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180034e10`
- `0x180034f50`

## callees

- `0x180002f50`
- `0x180003c78`
- `0x180022d10`
- `0x18002ee18`
- `0x18005d148`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005d20a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005d20a`
- `VirtDisk!CreateVirtualDisk` at `0x18005d1e8`
- `VirtDisk!CreateVirtualDisk` at `0x18005d1e8`

## string_xrefs

- `0x18005d239`: `onecore\vm\compute\shared\storage\vhdutilities.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CreateVhdFromSource(PCWSTR Path, const unsigned __int16 *a2, int a3)
{
  void **Handle; // rax
  DWORD v7; // eax
  CREATE_VIRTUAL_DISK_FLAG Flags; // [rsp+20h] [rbp-E0h]
  struct _CREATE_VIRTUAL_DISK_PARAMETERS Parameters; // [rsp+50h] [rbp-B0h] BYREF
  HANDLE hObject; // [rsp+110h] [rbp+10h] BYREF
  struct _VIRTUAL_STORAGE_TYPE VirtualStorageType; // [rsp+118h] [rbp+18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+158h] [rbp+58h]

  *(_QWORD *)&Parameters.Version = 2;
  memset_0(&Parameters.Version1, 0, 0xB0u);
  Parameters.Version2.SourcePath = a2;
  Parameters.Version1.BlockSizeInBytes = a3 << 20;
  Parameters.Version2.OpenFlags = OPEN_VIRTUAL_DISK_FLAG_CACHED_IO;
  memset(&VirtualStorageType, 0, sizeof(VirtualStorageType));
  hObject = (HANDLE)-1LL;
  Handle = (void **)wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::operator&(&hObject);
  v7 = CreateVirtualDisk(
         &VirtualStorageType,
         Path,
         VIRTUAL_DISK_ACCESS_NONE,
         0,
         CREATE_VIRTUAL_DISK_FLAG_NONE,
         0,
         &Parameters,
         0,
         Handle);
  if ( v7 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x100,
      (unsigned int)"onecore\\vm\\compute\\shared\\storage\\vhdutilities.cpp",
      (const char *)v7,
      Flags);
  if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(hObject);
}

```

## disassembly

```asm
0x18005d148  mov     [rsp-8+arg_18], rbx
0x18005d14d  push    rbp
0x18005d14e  push    rsi
0x18005d14f  push    rdi
0x18005d150  lea     rbp, [rsp-40h]
0x18005d155  sub     rsp, 140h
0x18005d15c  mov     rax, cs:__security_cookie
0x18005d163  xor     rax, rsp
0x18005d166  mov     [rbp+50h+var_20], rax
0x18005d16a  mov     edi, r8d
0x18005d16d  mov     rbx, rdx
0x18005d170  mov     rsi, rcx
0x18005d173  mov     qword ptr [rsp+150h+var_100.Version], 2
0x18005d17c  xor     edx, edx; Val
0x18005d17e  mov     r8d, 0B0h; Size
0x18005d184  lea     rcx, [rsp+150h+var_100.8]; void *
0x18005d189  call    memset_0
0x18005d18e  mov     qword ptr [rbp+50h+var_100.8+30h], rbx
0x18005d192  shl     edi, 14h
0x18005d195  mov     dword ptr [rsp+150h+var_100.8+18h], edi
0x18005d199  mov     dword ptr [rbp+50h+var_100.8+38h], 8
0x18005d1a0  xorps   xmm0, xmm0
0x18005d1a3  xor     eax, eax
0x18005d1a5  movups  xmmword ptr [rbp+50h+VirtualStorageType.DeviceId], xmm0
0x18005d1a9  mov     dword ptr [rbp+50h+VirtualStorageType.VendorId.Data4+4], eax
0x18005d1ac  mov     [rbp+50h+hObject], 0FFFFFFFFFFFFFFFFh
0x18005d1b4  lea     rcx, [rbp+50h+hObject]
0x18005d1b8  call    ??I?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAPEAPEAXXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::operator&(void)
0x18005d1bd  mov     [rsp+150h+Handle], rax; Handle
0x18005d1c2  xor     ebx, ebx
0x18005d1c4  mov     [rsp+150h+Overlapped], rbx; Overlapped
0x18005d1c9  lea     rax, [rsp+150h+var_100]
0x18005d1ce  mov     [rsp+150h+Parameters], rax; Parameters
0x18005d1d3  mov     [rsp+150h+ProviderSpecificFlags], ebx; ProviderSpecificFlags
0x18005d1d7  mov     [rsp+150h+Flags], ebx; unsigned int
0x18005d1db  xor     r9d, r9d; SecurityDescriptor
0x18005d1de  xor     r8d, r8d; VirtualDiskAccessMask
0x18005d1e1  mov     rdx, rsi; Path
0x18005d1e4  lea     rcx, [rbp+50h+VirtualStorageType]; VirtualStorageType
0x18005d1e8  call    cs:__imp_CreateVirtualDisk
0x18005d1ef  nop     dword ptr [rax+rax+00h]
0x18005d1f4  mov     rcx, [rbp+58h]; this
0x18005d1f8  test    eax, eax
0x18005d1fa  jnz     short loc_18005D236
0x18005d1fc  mov     rcx, [rbp+50h+hObject]; hObject
0x18005d200  lea     rax, [rcx-1]
0x18005d204  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18005d208  ja      short loc_18005D216
0x18005d20a  call    cs:__imp_CloseHandle
0x18005d211  nop     dword ptr [rax+rax+00h]
0x18005d216  mov     rcx, [rbp+50h+var_20]
0x18005d21a  xor     rcx, rsp; StackCookie
0x18005d21d  call    __security_check_cookie
0x18005d222  mov     rbx, [rsp+150h+arg_18]
0x18005d22a  add     rsp, 140h
0x18005d231  pop     rdi
0x18005d232  pop     rsi
0x18005d233  pop     rbp
0x18005d234  retn
0x18005d236  mov     r9d, eax; char *
0x18005d239  lea     r8, aOnecoreVmCompu_19; "onecore\\vm\\compute\\shared\\storage\\"...
0x18005d240  mov     edx, 100h; void *
0x18005d245  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
```
