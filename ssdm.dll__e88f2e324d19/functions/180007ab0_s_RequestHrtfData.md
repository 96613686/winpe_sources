# s_RequestHrtfData

- ea: `0x180007ab0`
- end: `0x180007bec`
- name: `s_RequestHrtfData`
- size: `316`
- prototype: `__int64 __fastcall(__int64, unsigned int, __int64)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180005ec0`
- `0x1800062cc`
- `0x180007484`
- `0x180007ab0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007b08`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007b08`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007b1b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007b1b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007b80`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007b80`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007bb3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007bb3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007b13`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007b65`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007b13`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007b65`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180007af4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180007b4b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180007af4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180007b4b`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall s_RequestHrtfData(__int64 a1, unsigned int a2, __int64 a3)
{
  HKEY v6; // rdi
  DWORD LastError; // ebx
  char v8; // bl
  __int64 result; // rax
  const char *v10; // r9
  int phkResult; // [rsp+20h] [rbp-28h]
  struct IHrtfAnthropometricsProvider *retaddr; // [rsp+48h] [rbp+0h]
  HKEY hKey; // [rsp+68h] [rbp+20h] BYREF

  hKey = 0;
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Multimedia\\Audio\\Hrtf", 0, 0x20119u, &hKey) )
    goto LABEL_6;
  v6 = hKey;
  if ( hKey )
  {
    LastError = GetLastError();
    RegCloseKey(v6);
    SetLastError(LastError);
  }
  hKey = 0;
  if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Multimedia\\Audio\\Hrtf", 0, 0x20219u, &hKey) )
    v8 = 0;
  else
LABEL_6:
    v8 = 1;
  if ( hKey )
    RegCloseKey(hKey);
  if ( !v8 )
    return 2147500033LL;
  EnterCriticalSection(&g_SharedDataManagerLock);
  try
  {
    hKey = (HKEY)&g_SharedDataManagerLock;
    if ( !a3 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x30,
        (unsigned int)"avcore\\xaudio\\hrtf\\ssdm\\lib\\spatialsounddatamanager.cpp",
        (const char *)0x80070057LL,
        phkResult);
    InitializeSsdm(retaddr);
    SharedDataManager::GetSharedData(qword_18001FA58, a1, a2, a3);
    LeaveCriticalSection(&g_SharedDataManagerLock);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x36,
                           (unsigned int)"avcore\\xaudio\\hrtf\\ssdm\\lib\\spatialsounddatamanager.cpp",
                           v10);
  }
  return result;
}

```

## disassembly

```asm
0x180007ab0  mov     r11, rsp
0x180007ab3  mov     [r11+8], rbx
0x180007ab7  mov     [r11+10h], rsi
0x180007abb  push    rdi
0x180007abc  push    r14
0x180007abe  push    r15
0x180007ac0  sub     rsp, 30h
0x180007ac4  mov     rsi, r8
0x180007ac7  mov     r14d, edx
0x180007aca  mov     r15, rcx
0x180007acd  mov     qword ptr [r11+20h], 0
0x180007ad5  lea     rax, [r11+20h]
0x180007ad9  mov     [r11-28h], rax
0x180007add  mov     r9d, 20119h; samDesired
0x180007ae3  xor     r8d, r8d; ulOptions
0x180007ae6  lea     rdx, SubKey; "Software\\Microsoft\\Multimedia\\Audio"...
0x180007aed  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180007af4  call    cs:__imp_RegOpenKeyExW
0x180007afa  test    eax, eax
0x180007afc  jz      short loc_180007B59
0x180007afe  mov     rdi, [rsp+48h+hKey]
0x180007b03  test    rdi, rdi
0x180007b06  jz      short loc_180007B21
0x180007b08  call    cs:__imp_GetLastError
0x180007b0e  mov     ebx, eax
0x180007b10  mov     rcx, rdi; hKey
0x180007b13  call    cs:__imp_RegCloseKey
0x180007b19  mov     ecx, ebx; dwErrCode
0x180007b1b  call    cs:__imp_SetLastError
0x180007b21  mov     [rsp+48h+hKey], 0
0x180007b2a  lea     rax, [rsp+48h+hKey]
0x180007b2f  mov     qword ptr [rsp+48h+phkResult], rax; phkResult
0x180007b34  mov     r9d, 20219h; samDesired
0x180007b3a  xor     r8d, r8d; ulOptions
0x180007b3d  lea     rdx, SubKey; "Software\\Microsoft\\Multimedia\\Audio"...
0x180007b44  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180007b4b  call    cs:__imp_RegOpenKeyExW
0x180007b51  test    eax, eax
0x180007b53  jz      short loc_180007B59
0x180007b55  xor     bl, bl
0x180007b57  jmp     short loc_180007B5B
0x180007b59  mov     bl, 1
0x180007b5b  mov     rcx, [rsp+48h+hKey]; hKey
0x180007b60  test    rcx, rcx
0x180007b63  jz      short loc_180007B6B
0x180007b65  call    cs:__imp_RegCloseKey
0x180007b6b  test    bl, bl
0x180007b6d  jnz     short loc_180007B76
0x180007b6f  mov     eax, 80004001h
0x180007b74  jmp     short loc_180007BC1
0x180007b76  lea     rbx, ?g_SharedDataManagerLock@@3VCriticalSection@Wrappers@WRL@Microsoft@@A; Microsoft::WRL::Wrappers::CriticalSection g_SharedDataManagerLock
0x180007b7d  mov     rcx, rbx; lpCriticalSection
0x180007b80  call    cs:__imp_EnterCriticalSection
0x180007b86  mov     [rsp+48h+hKey], rbx
0x180007b8b  mov     rcx, [rsp+48h]; this
0x180007b90  test    rsi, rsi
0x180007b93  jz      short loc_180007BD5
0x180007b95  call    ?InitializeSsdm@@YAXPEAUIHrtfAnthropometricsProvider@@@Z; InitializeSsdm(IHrtfAnthropometricsProvider *)
0x180007b9a  mov     r9, rsi
0x180007b9d  mov     r8d, r14d
0x180007ba0  mov     rdx, r15
0x180007ba3  mov     rcx, cs:qword_18001FA58
0x180007baa  call    ?GetSharedData@SharedDataManager@@QEAAXPEAXW4_HrtfDatasetType@@PEAPEAU_HrtfSharedData@@@Z; SharedDataManager::GetSharedData(void *,_HrtfDatasetType,_HrtfSharedData * *)
0x180007baf  nop
0x180007bb0  mov     rcx, rbx; lpCriticalSection
0x180007bb3  call    cs:__imp_LeaveCriticalSection
0x180007bb9  xor     eax, eax
0x180007bbb  jmp     short loc_180007BC1
0x180007bbd  mov     eax, dword ptr [rsp+48h+hKey]
0x180007bc1  mov     rbx, [rsp+48h+arg_0]
0x180007bc6  mov     rsi, [rsp+48h+arg_8]
0x180007bcb  add     rsp, 30h
0x180007bcf  pop     r15
0x180007bd1  pop     r14
0x180007bd3  pop     rdi
0x180007bd4  retn
0x180007bd5  mov     r9d, 80070057h; char *
0x180007bdb  lea     r8, aAvcoreXaudioHr_3; "avcore\\xaudio\\hrtf\\ssdm\\lib\\spatia"...
0x180007be2  lea     edx, [rsi+30h]; void *
0x180007be5  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
