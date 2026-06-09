# ManagementProc

- ea: `0x18002b8f0`
- end: `0x18002ba09`
- name: `ManagementProc`
- size: `281`
- prototype: `DWORD __fastcall(LPVOID lpThreadParameter)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x18002b8f0`
- `0x18002bc98`
- `0x18003d4ec`
- `0x18003dc84`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x18002b99b`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x18002b99b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002b9ea`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002b9ea`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002b92b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002b92b`
- `KERNEL32!CreateEventW` at `0x18002b957`
- `KERNEL32!CreateEventW` at `0x18002b957`
- `KERNEL32!WaitForMultipleObjects` at `0x18002b9b0`
- `KERNEL32!WaitForMultipleObjects` at `0x18002b9b0`
- `KERNEL32!CloseHandle` at `0x18002b9f8`
- `KERNEL32!CloseHandle` at `0x18002b9f8`

## string_xrefs

- `0x18002b937`: `RegOpenKeyExW failed in ManagementProc`

## pseudocode

```c
DWORD __fastcall ManagementProc(LPVOID lpThreadParameter)
{
  void *v1; // rbx
  HANDLE EventW; // rax
  DWORD v3; // edi
  DWORD v4; // eax
  __int128 Handles; // [rsp+30h] [rbp-18h] BYREF
  HKEY hKey; // [rsp+58h] [rbp+10h] BYREF

  hKey = 0;
  Handles = 0;
  if ( RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"Software\\Microsoft\\Windows\\CurrentVersion\\Telephony\\Server",
         0,
         0x20019u,
         &hKey) )
  {
    v1 = 0;
    LODWORD(EventW) = TRACELogPrint(65538, "RegOpenKeyExW failed in ManagementProc");
  }
  else
  {
    EventW = CreateEventW(0, 0, 0, 0);
    v1 = EventW;
    if ( EventW )
    {
      *(_QWORD *)&Handles = EventW;
      *((_QWORD *)&Handles + 1) = ghEventService;
      v3 = (unsigned int)(60000 * *(_DWORD *)&gdwTapiSCPTTL) >> 1;
      while ( 1 )
      {
        while ( 1 )
        {
          RegNotifyChangeKeyValue(hKey, 1, 4u, v1, 1);
          v4 = WaitForMultipleObjects(2u, (const HANDLE *)&Handles, 0, v3);
          if ( v4 )
            break;
          ReadAndInitManagementDlls();
        }
        if ( v4 == 1 )
          break;
        if ( v4 == 258 )
          UpdateTapiSCP(1);
      }
      LODWORD(EventW) = UpdateTapiSCP(0);
    }
  }
  if ( hKey )
    LODWORD(EventW) = RegCloseKey(hKey);
  if ( v1 )
    LODWORD(EventW) = CloseHandle(v1);
  return (unsigned int)EventW;
}

```

## disassembly

```asm
0x18002b8f0  mov     rax, rsp
0x18002b8f3  mov     [rax+8], rbx
0x18002b8f7  push    rdi
0x18002b8f8  sub     rsp, 40h
0x18002b8fc  xorps   xmm0, xmm0
0x18002b8ff  mov     qword ptr [rax+10h], 0
0x18002b907  movups  xmmword ptr [rax-18h], xmm0
0x18002b90b  lea     rax, [rax+10h]
0x18002b90f  mov     r9d, 20019h; samDesired
0x18002b915  xor     r8d, r8d; ulOptions
0x18002b918  mov     [rsp+48h+phkResult], rax; phkResult
0x18002b91d  lea     rdx, gszRegKeyServer; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18002b924  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002b92b  call    cs:__imp_RegOpenKeyExW
0x18002b931  test    eax, eax
0x18002b933  jz      short loc_18002B94D
0x18002b935  xor     ebx, ebx
0x18002b937  lea     rdx, aRegopenkeyexwF; "RegOpenKeyExW failed in ManagementProc"
0x18002b93e  mov     ecx, 10002h
0x18002b943  call    TRACELogPrint
0x18002b948  jmp     loc_18002B9E0
0x18002b94d  xor     r9d, r9d; lpName
0x18002b950  xor     r8d, r8d; bInitialState
0x18002b953  xor     edx, edx; bManualReset
0x18002b955  xor     ecx, ecx; lpEventAttributes
0x18002b957  call    cs:__imp_CreateEventW
0x18002b95d  mov     rbx, rax
0x18002b960  test    rax, rax
0x18002b963  jz      short loc_18002B9E0
0x18002b965  imul    edi, cs:gdwTapiSCPTTL, 0EA60h
0x18002b96f  mov     rcx, cs:ghEventService
0x18002b976  mov     [rsp+48h+Handles], rax
0x18002b97b  mov     [rsp+48h+var_10], rcx
0x18002b980  shr     edi, 1
0x18002b982  mov     rcx, [rsp+48h+hKey]; hKey
0x18002b987  mov     edx, 1; bWatchSubtree
0x18002b98c  mov     r9, rbx; hEvent
0x18002b98f  mov     dword ptr [rsp+48h+phkResult], 1; fAsynchronous
0x18002b997  lea     r8d, [rdx+3]; dwNotifyFilter
0x18002b99b  call    cs:__imp_RegNotifyChangeKeyValue
0x18002b9a1  xor     r8d, r8d; bWaitAll
0x18002b9a4  lea     rdx, [rsp+48h+Handles]; lpHandles
0x18002b9a9  mov     r9d, edi; dwMilliseconds
0x18002b9ac  lea     ecx, [r8+2]; nCount
0x18002b9b0  call    cs:__imp_WaitForMultipleObjects
0x18002b9b6  test    eax, eax
0x18002b9b8  jnz     short loc_18002B9C1
0x18002b9ba  call    ReadAndInitManagementDlls
0x18002b9bf  jmp     short loc_18002B982
0x18002b9c1  cmp     eax, 1
0x18002b9c4  jz      short loc_18002B9D9
0x18002b9c6  cmp     eax, 102h
0x18002b9cb  jnz     short loc_18002B982
0x18002b9cd  mov     ecx, 1
0x18002b9d2  call    UpdateTapiSCP
0x18002b9d7  jmp     short loc_18002B982
0x18002b9d9  xor     ecx, ecx
0x18002b9db  call    UpdateTapiSCP
0x18002b9e0  mov     rcx, [rsp+48h+hKey]; hKey
0x18002b9e5  test    rcx, rcx
0x18002b9e8  jz      short loc_18002B9F0
0x18002b9ea  call    cs:__imp_RegCloseKey
0x18002b9f0  test    rbx, rbx
0x18002b9f3  jz      short loc_18002B9FE
0x18002b9f5  mov     rcx, rbx; hObject
0x18002b9f8  call    cs:__imp_CloseHandle
0x18002b9fe  mov     rbx, [rsp+48h+arg_0]
0x18002ba03  add     rsp, 40h
0x18002ba07  pop     rdi
0x18002ba08  retn
```
