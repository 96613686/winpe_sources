# bSetDevModePerUser

- ea: `0x140018bc0`
- end: `0x140018cda`
- name: `bSetDevModePerUser`
- size: `282`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1400065e0`
- `0x1400625a0`

## callees

- `0x140003fb0`
- `0x140015378`
- `0x140016e60`
- `0x140018bc0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140018ca2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140018ca2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140018bea`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140018c96`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140018bea`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140018c96`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x140018c1f`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x140018c1f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140018c57`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140018c57`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140018c84`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140018c84`

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
0x140018bc0  mov     [rsp+arg_0], rbx
0x140018bc5  push    rdi
0x140018bc6  sub     rsp, 30h
0x140018bca  mov     [rsp+38h+hKey], 0
0x140018bd3  mov     rbx, r8
0x140018bd6  mov     [rsp+38h+lpValueName], 0
0x140018bdf  mov     rdi, rdx
0x140018be2  test    rdx, rdx
0x140018be5  jnz     short loc_140018BFD
0x140018be7  lea     ecx, [rdx+6]; dwErrCode
0x140018bea  call    cs:__imp_SetLastError
0x140018bf1  nop     dword ptr [rax+rax+00h]
0x140018bf6  xor     eax, eax
0x140018bf8  jmp     loc_140018CCE
0x140018bfd  lea     r9, [rsp+38h+lpValueName]; unsigned __int16 **
0x140018c02  lea     r8, [rsp+38h+hKey]; phkResult
0x140018c07  call    ?bGetDevModeLocation@@YAHPEAUHKEY__@@PEBGPEAPEAU1@PEAPEBG@Z; bGetDevModeLocation(HKEY__ *,ushort const *,HKEY__ * *,ushort const * *)
0x140018c0c  test    eax, eax
0x140018c0e  jz      short loc_140018BF6
0x140018c10  mov     rdx, [rsp+38h+lpValueName]; lpValueName
0x140018c15  test    rbx, rbx
0x140018c18  jnz     short loc_140018C36
0x140018c1a  mov     rcx, [rsp+38h+hKey]; hKey
0x140018c1f  call    cs:__imp_RegDeleteValueW
0x140018c26  nop     dword ptr [rax+rax+00h]
0x140018c2b  mov     ebx, eax
0x140018c2d  cmp     eax, 2
0x140018c30  jnz     short loc_140018C7F
0x140018c32  xor     ebx, ebx
0x140018c34  jmp     short loc_140018C7F
0x140018c36  movzx   ecx, word ptr [rbx+46h]
0x140018c3a  mov     r9d, 3; dwType
0x140018c40  movzx   eax, word ptr [rbx+44h]
0x140018c44  xor     r8d, r8d; Reserved
0x140018c47  add     ecx, eax
0x140018c49  mov     [rsp+38h+cbData], ecx; cbData
0x140018c4d  mov     rcx, [rsp+38h+hKey]; hKey
0x140018c52  mov     [rsp+38h+lpData], rbx; lpData
0x140018c57  call    cs:__imp_RegSetValueExW
0x140018c5e  nop     dword ptr [rax+rax+00h]
0x140018c63  mov     ebx, eax
0x140018c65  test    eax, eax
0x140018c67  jnz     short loc_140018C7F
0x140018c69  xor     r9d, r9d; unsigned __int64
0x140018c6c  mov     [rsp+38h+lpData], rdi; __int64
0x140018c71  xor     edx, edx; unsigned int
0x140018c73  lea     ecx, [rax+2]; unsigned int
0x140018c76  lea     r8d, [rax+1Bh]; unsigned int
0x140018c7a  call    RouterBroadcastMessage
0x140018c7f  mov     rcx, [rsp+38h+hKey]; hKey
0x140018c84  call    cs:__imp_RegCloseKey
0x140018c8b  nop     dword ptr [rax+rax+00h]
0x140018c90  test    ebx, ebx
0x140018c92  jz      short loc_140018CC9
0x140018c94  mov     ecx, ebx; dwErrCode
0x140018c96  call    cs:__imp_SetLastError
0x140018c9d  nop     dword ptr [rax+rax+00h]
0x140018ca2  call    cs:__imp_GetLastError
0x140018ca9  nop     dword ptr [rax+rax+00h]
0x140018cae  mov     r8d, eax
0x140018cb1  lea     rdx, aFailedToSetDev; "Failed to set devmode.  Error %d."
0x140018cb8  lea     rcx, aBsetdevmodeper; "bSetDevModePerUser"
0x140018cbf  call    ?WriteDbgTraceError@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x140018cc4  jmp     loc_140018BF6
0x140018cc9  mov     eax, 1
0x140018cce  mov     rbx, [rsp+38h+arg_0]
0x140018cd3  add     rsp, 30h
0x140018cd7  pop     rdi
0x140018cd8  retn
```
