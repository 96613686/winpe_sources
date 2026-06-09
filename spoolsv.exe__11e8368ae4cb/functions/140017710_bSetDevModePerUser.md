# bSetDevModePerUser

- ea: `0x140017710`
- end: `0x140017805`
- name: `bSetDevModePerUser`
- size: `245`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x140005c30`
- `0x14005c9e0`

## callees

- `0x140003df0`
- `0x1400140cc`
- `0x140015c30`
- `0x140017710`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400177d4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400177d4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14001773a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400177ce`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14001773a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400177ce`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x140017769`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x140017769`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14001779b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14001779b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400177c2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400177c2`

## pseudocode

```c
__int64 __fastcall bSetDevModePerUser(HKEY a1, const unsigned __int16 *a2, __int64 a3)
{
  LSTATUS v6; // ebx
  DWORD LastError; // eax
  HKEY hKey; // [rsp+48h] [rbp+10h] BYREF
  LPCWSTR lpValueName; // [rsp+58h] [rbp+20h] BYREF

  hKey = 0;
  lpValueName = 0;
  if ( !a2 )
  {
    SetLastError(6u);
    return 0;
  }
  if ( !(unsigned int)bGetDevModeLocation(a1, a2, &hKey, &lpValueName) )
    return 0;
  if ( a3 )
  {
    v6 = RegSetValueExW(
           hKey,
           lpValueName,
           0,
           3u,
           (const BYTE *)a3,
           *(unsigned __int16 *)(a3 + 68) + *(unsigned __int16 *)(a3 + 70));
    if ( !v6 )
      RouterBroadcastMessage(2u, 0, 0x1Bu, 0, (__int64)a2);
  }
  else
  {
    v6 = RegDeleteValueW(hKey, lpValueName);
    if ( v6 == 2 )
      v6 = 0;
  }
  RegCloseKey(hKey);
  if ( v6 )
  {
    SetLastError(v6);
    LastError = GetLastError();
    PrvSpoolssTelemetry::WriteDbgTraceError("bSetDevModePerUser", L"Failed to set devmode.  Error %d.", LastError);
    return 0;
  }
  return 1;
}

```

## disassembly

```asm
0x140017710  mov     [rsp+arg_0], rbx
0x140017715  push    rdi
0x140017716  sub     rsp, 30h
0x14001771a  mov     [rsp+38h+hKey], 0
0x140017723  mov     rbx, r8
0x140017726  mov     [rsp+38h+lpValueName], 0
0x14001772f  mov     rdi, rdx
0x140017732  test    rdx, rdx
0x140017735  jnz     short loc_140017747
0x140017737  lea     ecx, [rdx+6]; dwErrCode
0x14001773a  call    cs:__imp_SetLastError
0x140017740  xor     eax, eax
0x140017742  jmp     loc_1400177FA
0x140017747  lea     r9, [rsp+38h+lpValueName]; unsigned __int16 **
0x14001774c  lea     r8, [rsp+38h+hKey]; phkResult
0x140017751  call    ?bGetDevModeLocation@@YAHPEAUHKEY__@@PEBGPEAPEAU1@PEAPEBG@Z; bGetDevModeLocation(HKEY__ *,ushort const *,HKEY__ * *,ushort const * *)
0x140017756  test    eax, eax
0x140017758  jz      short loc_140017740
0x14001775a  mov     rdx, [rsp+38h+lpValueName]; lpValueName
0x14001775f  test    rbx, rbx
0x140017762  jnz     short loc_14001777A
0x140017764  mov     rcx, [rsp+38h+hKey]; hKey
0x140017769  call    cs:__imp_RegDeleteValueW
0x14001776f  mov     ebx, eax
0x140017771  cmp     eax, 2
0x140017774  jnz     short loc_1400177BD
0x140017776  xor     ebx, ebx
0x140017778  jmp     short loc_1400177BD
0x14001777a  movzx   ecx, word ptr [rbx+46h]
0x14001777e  mov     r9d, 3; dwType
0x140017784  movzx   eax, word ptr [rbx+44h]
0x140017788  xor     r8d, r8d; Reserved
0x14001778b  add     ecx, eax
0x14001778d  mov     [rsp+38h+cbData], ecx; cbData
0x140017791  mov     rcx, [rsp+38h+hKey]; hKey
0x140017796  mov     [rsp+38h+lpData], rbx; lpData
0x14001779b  call    cs:__imp_RegSetValueExW
0x1400177a1  mov     ebx, eax
0x1400177a3  test    eax, eax
0x1400177a5  jnz     short loc_1400177BD
0x1400177a7  xor     r9d, r9d; unsigned __int64
0x1400177aa  mov     [rsp+38h+lpData], rdi; __int64
0x1400177af  xor     edx, edx; unsigned int
0x1400177b1  lea     ecx, [rax+2]; unsigned int
0x1400177b4  lea     r8d, [rax+1Bh]; unsigned int
0x1400177b8  call    RouterBroadcastMessage
0x1400177bd  mov     rcx, [rsp+38h+hKey]; hKey
0x1400177c2  call    cs:__imp_RegCloseKey
0x1400177c8  test    ebx, ebx
0x1400177ca  jz      short loc_1400177F5
0x1400177cc  mov     ecx, ebx; dwErrCode
0x1400177ce  call    cs:__imp_SetLastError
0x1400177d4  call    cs:__imp_GetLastError
0x1400177da  mov     r8d, eax
0x1400177dd  lea     rdx, aFailedToSetDev; "Failed to set devmode.  Error %d."
0x1400177e4  lea     rcx, aBsetdevmodeper; "bSetDevModePerUser"
0x1400177eb  call    ?WriteDbgTraceError@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x1400177f0  jmp     loc_140017740
0x1400177f5  mov     eax, 1
0x1400177fa  mov     rbx, [rsp+38h+arg_0]
0x1400177ff  add     rsp, 30h
0x140017803  pop     rdi
0x140017804  retn
```
