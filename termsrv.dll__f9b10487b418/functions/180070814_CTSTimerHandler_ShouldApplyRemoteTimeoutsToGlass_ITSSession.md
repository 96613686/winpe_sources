# CTSTimerHandler::ShouldApplyRemoteTimeoutsToGlass(ITSSession *)

- ea: `0x180070814`
- end: `0x1800708c3`
- name: `?ShouldApplyRemoteTimeoutsToGlass@CTSTimerHandler@@AEAAHPEAUITSSession@@@Z`
- size: `175`
- prototype: `__int64 __fastcall(CTSTimerHandler *__hidden this, struct ITSSession *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x18006efd0`

## callees

- `0x18000a210`
- `0x180070814`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18007089e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18007089e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800708b5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800708b5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18007085b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18007085b`

## string_xrefs

- `0x180070865`: `Could not open machine TS policy for this session`

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
0x180070814  mov     rax, rsp
0x180070817  mov     [rax+10h], rdx
0x18007081b  mov     [rax+8], rcx
0x18007081f  push    rbx
0x180070820  sub     rsp, 30h
0x180070824  xor     ebx, ebx
0x180070826  mov     qword ptr [rax+20h], 0
0x18007082e  mov     [rax+18h], ebx
0x180070831  mov     r9d, 20019h; samDesired
0x180070837  mov     [rax+10h], ebx
0x18007083a  xor     r8d, r8d; ulOptions
0x18007083d  mov     dword ptr [rax+8], 4
0x180070844  lea     rax, [rax+20h]
0x180070848  lea     rdx, aSystemCurrentc_0; "System\\CurrentControlSet\\Control\\Ter"...
0x18007084f  mov     [rsp+38h+phkResult], rax; phkResult
0x180070854  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18007085b  call    cs:__imp_RegOpenKeyExW
0x180070861  test    eax, eax
0x180070863  jz      short loc_180070876
0x180070865  lea     rdx, aCouldNotOpenMa; "Could not open machine TS policy for th"...
0x18007086c  lea     ecx, [rbx+4]; int
0x18007086f  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180070874  jmp     short loc_1800708AB
0x180070876  mov     rcx, [rsp+38h+hKey]; hKey
0x18007087b  lea     rax, [rsp+38h+cbData]
0x180070880  mov     [rsp+38h+lpcbData], rax; lpcbData
0x180070885  lea     r9, [rsp+38h+Type]; lpType
0x18007088a  lea     rax, [rsp+38h+Data]
0x18007088f  xor     r8d, r8d; lpReserved
0x180070892  lea     rdx, aApplysessionli; "ApplySessionLimits"
0x180070899  mov     [rsp+38h+phkResult], rax; lpData
0x18007089e  call    cs:__imp_RegQueryValueExW
0x1800708a4  test    eax, eax
0x1800708a6  cmovz   ebx, [rsp+38h+Data]
0x1800708ab  mov     rcx, [rsp+38h+hKey]; hKey
0x1800708b0  test    rcx, rcx
0x1800708b3  jz      short loc_1800708BB
0x1800708b5  call    cs:__imp_RegCloseKey
0x1800708bb  mov     eax, ebx
0x1800708bd  add     rsp, 30h
0x1800708c1  pop     rbx
0x1800708c2  retn
```
