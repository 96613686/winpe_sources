# CTSTimerHandler::ShouldApplyRemoteTimeoutsToGlass(ITSSession *)

- ea: `0x180073d24`
- end: `0x180073de6`
- name: `?ShouldApplyRemoteTimeoutsToGlass@CTSTimerHandler@@AEAAHPEAUITSSession@@@Z`
- size: `194`
- prototype: `__int64 __fastcall(CTSTimerHandler *__hidden this, struct ITSSession *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x1800724c0`

## callees

- `0x180009940`
- `0x180073d24`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180073db4`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180073db4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180073dd1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180073dd1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180073d6b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180073d6b`

## string_xrefs

- `0x180073d7b`: `Could not open machine TS policy for this session`

## pseudocode

```c
__int64 __fastcall CTSTimerHandler::ShouldApplyRemoteTimeoutsToGlass(CTSTimerHandler *this, struct ITSSession *a2)
{
  unsigned int v2; // ebx
  DWORD cbData; // [rsp+40h] [rbp+8h] BYREF
  int v5; // [rsp+44h] [rbp+Ch]
  unsigned int Data; // [rsp+48h] [rbp+10h] BYREF
  int v7; // [rsp+4Ch] [rbp+14h]
  DWORD Type; // [rsp+50h] [rbp+18h] BYREF
  HKEY hKey; // [rsp+58h] [rbp+20h] BYREF

  v7 = HIDWORD(a2);
  v5 = HIDWORD(this);
  v2 = 0;
  hKey = 0;
  Type = 0;
  Data = 0;
  cbData = 4;
  if ( RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"System\\CurrentControlSet\\Control\\Terminal server\\WinStations\\Console",
         0,
         0x20019u,
         &hKey) )
  {
    _DbgPrintMessage(4, "Could not open machine TS policy for this session");
  }
  else if ( !RegQueryValueExW(hKey, L"ApplySessionLimits", 0, &Type, (LPBYTE)&Data, &cbData) )
  {
    v2 = Data;
  }
  if ( hKey )
    RegCloseKey(hKey);
  return v2;
}

```

## disassembly

```asm
0x180073d24  mov     rax, rsp
0x180073d27  mov     [rax+10h], rdx
0x180073d2b  mov     [rax+8], rcx
0x180073d2f  push    rbx
0x180073d30  sub     rsp, 30h
0x180073d34  xor     ebx, ebx
0x180073d36  mov     qword ptr [rax+20h], 0
0x180073d3e  mov     [rax+18h], ebx
0x180073d41  mov     r9d, 20019h; samDesired
0x180073d47  mov     [rax+10h], ebx
0x180073d4a  xor     r8d, r8d; ulOptions
0x180073d4d  mov     dword ptr [rax+8], 4
0x180073d54  lea     rax, [rax+20h]
0x180073d58  lea     rdx, aSystemCurrentc_0; "System\\CurrentControlSet\\Control\\Ter"...
0x180073d5f  mov     [rsp+38h+phkResult], rax; phkResult
0x180073d64  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180073d6b  call    cs:__imp_RegOpenKeyExW
0x180073d72  nop     dword ptr [rax+rax+00h]
0x180073d77  test    eax, eax
0x180073d79  jz      short loc_180073D8C
0x180073d7b  lea     rdx, aCouldNotOpenMa; "Could not open machine TS policy for th"...
0x180073d82  lea     ecx, [rbx+4]; int
0x180073d85  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180073d8a  jmp     short loc_180073DC7
0x180073d8c  mov     rcx, [rsp+38h+hKey]; hKey
0x180073d91  lea     rax, [rsp+38h+cbData]
0x180073d96  mov     [rsp+38h+lpcbData], rax; lpcbData
0x180073d9b  lea     r9, [rsp+38h+Type]; lpType
0x180073da0  lea     rax, [rsp+38h+Data]
0x180073da5  xor     r8d, r8d; lpReserved
0x180073da8  lea     rdx, aApplysessionli; "ApplySessionLimits"
0x180073daf  mov     [rsp+38h+phkResult], rax; lpData
0x180073db4  call    cs:__imp_RegQueryValueExW
0x180073dbb  nop     dword ptr [rax+rax+00h]
0x180073dc0  test    eax, eax
0x180073dc2  cmovz   ebx, [rsp+38h+Data]
0x180073dc7  mov     rcx, [rsp+38h+hKey]; hKey
0x180073dcc  test    rcx, rcx
0x180073dcf  jz      short loc_180073DDD
0x180073dd1  call    cs:__imp_RegCloseKey
0x180073dd8  nop     dword ptr [rax+rax+00h]
0x180073ddd  mov     eax, ebx
0x180073ddf  add     rsp, 30h
0x180073de3  pop     rbx
0x180073de4  retn
```
