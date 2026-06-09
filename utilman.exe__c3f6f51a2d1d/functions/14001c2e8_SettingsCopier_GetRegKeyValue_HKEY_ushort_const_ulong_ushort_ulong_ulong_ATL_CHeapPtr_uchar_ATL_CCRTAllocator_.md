# SettingsCopier::GetRegKeyValue(HKEY__ *,ushort const *,ulong,ushort *,ulong,ulong *,ATL::CHeapPtr<uchar,ATL::CCRTAllocator> &,ulong *)

- ea: `0x14001c2e8`
- end: `0x14001c643`
- name: `?GetRegKeyValue@SettingsCopier@@CAJPEAUHKEY__@@PEBGKPEAGKPEAKAEAV?$CHeapPtr@EVCCRTAllocator@ATL@@@ATL@@3@Z`
- size: `859`
- prototype: `__int64 __usercall@<rax>(HKEY hKey@<rcx>, LPCWSTR lpSubKey@<rdx>, DWORD cchValueName, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, registry_config`

## callers

- `0x14001bcec`

## callees

- `0x14001bc98`
- `0x14001c2e8`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x14001c3af`
- `ADVAPI32!RegOpenKeyExW` at `0x14001c3af`
- `ADVAPI32!RegCloseKey` at `0x14001c41f`
- `ADVAPI32!RegCloseKey` at `0x14001c4b9`
- `ADVAPI32!RegCloseKey` at `0x14001c525`
- `ADVAPI32!RegCloseKey` at `0x14001c57a`
- `ADVAPI32!RegCloseKey` at `0x14001c41f`
- `ADVAPI32!RegCloseKey` at `0x14001c4b9`
- `ADVAPI32!RegCloseKey` at `0x14001c525`
- `ADVAPI32!RegCloseKey` at `0x14001c57a`
- `ADVAPI32!RegQueryValueExW` at `0x14001c568`
- `ADVAPI32!RegQueryValueExW` at `0x14001c568`
- `ADVAPI32!RegEnumValueW` at `0x14001c466`
- `ADVAPI32!RegEnumValueW` at `0x14001c500`
- `ADVAPI32!RegEnumValueW` at `0x14001c466`
- `ADVAPI32!RegEnumValueW` at `0x14001c500`
- `ADVAPI32!RegNotifyChangeKeyValue` at `0x14001c3fa`
- `ADVAPI32!RegNotifyChangeKeyValue` at `0x14001c3fa`
- `KERNEL32!WaitForSingleObject` at `0x14001c58b`
- `KERNEL32!WaitForSingleObject` at `0x14001c58b`
- `KERNEL32!GetLastError` at `0x14001c373`
- `KERNEL32!GetLastError` at `0x14001c373`
- `KERNEL32!CloseHandle` at `0x14001c3c4`
- `KERNEL32!CloseHandle` at `0x14001c40f`
- `KERNEL32!CloseHandle` at `0x14001c4a9`
- `KERNEL32!CloseHandle` at `0x14001c515`
- `KERNEL32!CloseHandle` at `0x14001c59c`
- `KERNEL32!CloseHandle` at `0x14001c3c4`
- `KERNEL32!CloseHandle` at `0x14001c40f`
- `KERNEL32!CloseHandle` at `0x14001c4a9`
- `KERNEL32!CloseHandle` at `0x14001c515`
- `KERNEL32!CloseHandle` at `0x14001c59c`
- `KERNEL32!CreateEventW` at `0x14001c35f`
- `KERNEL32!CreateEventW` at `0x14001c35f`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14001c346`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14001c534`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14001c5bf`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14001c5fc`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14001c346`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14001c534`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14001c5bf`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14001c5fc`

## string_xrefs

- `0x14001c561`: `SymbolicLinkValue`

## pseudocode

```c
signed int __fastcall SettingsCopier::GetRegKeyValue(
        HKEY hKey,
        LPCWSTR lpSubKey,
        DWORD a3,
        WCHAR *a4,
        DWORD cchValueName,
        DWORD *a6,
        void **a7,
        DWORD *a8)
{
  DWORD *v8; // r12
  DWORD *v9; // r13
  void **v11; // rsi
  void *v14; // rcx
  HANDLE EventW; // r14
  signed int result; // eax
  LSTATUS v17; // ebx
  LSTATUS v18; // edi
  LSTATUS v19; // eax
  DWORD v20; // ebx
  BYTE *lpData; // [rsp+30h] [rbp-30h]
  DWORD Type; // [rsp+40h] [rbp-20h] BYREF
  DWORD v23; // [rsp+44h] [rbp-1Ch] BYREF
  DWORD v24; // [rsp+48h] [rbp-18h] BYREF
  HKEY hKeya; // [rsp+50h] [rbp-10h] BYREF
  DWORD cbData; // [rsp+B8h] [rbp+58h] BYREF

  v8 = a6;
  v9 = a8;
  v11 = a7;
  *a4 = 0;
  *v8 = 0;
  *v9 = 0;
  v14 = *v11;
  hKeya = 0;
  cchValueName = 260;
  Type = 0;
  cbData = 0;
  v23 = 0;
  v24 = 0;
  free(v14);
  *v11 = 0;
  EventW = CreateEventW(0, 0, 0, 0);
  if ( EventW )
  {
    v17 = RegOpenKeyExW(hKey, lpSubKey, 8u, 0x20019u, &hKeya);
    if ( v17 )
    {
      CloseHandle(EventW);
      goto LABEL_6;
    }
    v18 = 1;
    v17 = RegNotifyChangeKeyValue(hKeya, 0, 5u, EventW, 1);
    if ( v17 )
      goto LABEL_10;
    cchValueName = 260;
    v19 = RegEnumValueW(hKeya, a3, a4, &cchValueName, 0, &Type, 0, &cbData);
    v17 = v19;
    if ( v19 == 259 )
      goto LABEL_17;
    if ( v19 && v19 != 234 )
    {
LABEL_10:
      CloseHandle(EventW);
      RegCloseKey(hKeya);
      goto LABEL_6;
    }
    if ( cbData )
    {
      if ( !(unsigned __int8)ATL::CHeapPtr<unsigned char,ATL::CCRTAllocator>::Allocate(v11, cbData) )
      {
        v18 = -2147024882;
LABEL_17:
        CloseHandle(EventW);
        RegCloseKey(hKeya);
        return v18;
      }
      lpData = (BYTE *)*v11;
      cchValueName = 260;
      v17 = RegEnumValueW(hKeya, a3, a4, &cchValueName, 0, &Type, lpData, &cbData);
      if ( v17 )
      {
        CloseHandle(EventW);
        RegCloseKey(hKeya);
        free(*v11);
        *v11 = 0;
LABEL_6:
        if ( v17 > 0 )
          return (unsigned __int16)v17 | 0x80070000;
        return v17;
      }
    }
    v18 = RegQueryValueExW(hKeya, L"SymbolicLinkValue", 0, &v23, 0, &v24);
    RegCloseKey(hKeya);
    v20 = WaitForSingleObject(EventW, 0);
    CloseHandle(EventW);
    if ( !v20 )
    {
      v17 = -2147023590;
LABEL_29:
      free(*v11);
      *v11 = 0;
      *a4 = 0;
      return v17;
    }
    if ( v18 )
    {
      if ( v18 != 2 )
      {
        free(*v11);
        *v11 = 0;
        *a4 = 0;
        if ( v18 > 0 )
          return (unsigned __int16)v18 | 0x80070000;
        return v18;
      }
    }
    else if ( v23 == 6 )
    {
      v17 = -2147023432;
      goto LABEL_29;
    }
    *v8 = Type;
    *v9 = cbData;
    return 0;
  }
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x14001c2e8  mov     [rsp-38h+arg_0], rbx
0x14001c2ed  mov     [rsp-38h+dwIndex], r8d
0x14001c2f2  push    rbp
0x14001c2f3  push    rsi
0x14001c2f4  push    rdi
0x14001c2f5  push    r12
0x14001c2f7  push    r13
0x14001c2f9  push    r14
0x14001c2fb  push    r15
0x14001c2fd  mov     rbp, rsp
0x14001c300  sub     rsp, 60h
0x14001c304  mov     r12, [rbp+arg_28]
0x14001c308  xor     r14d, r14d
0x14001c30b  mov     r13, [rbp+arg_38]
0x14001c30f  mov     rdi, rcx
0x14001c312  mov     rsi, [rbp+arg_30]
0x14001c316  mov     r15, r9
0x14001c319  mov     [r9], r14w
0x14001c31d  mov     rbx, rdx
0x14001c320  mov     [r12], r14d
0x14001c324  mov     [r13+0], r14d
0x14001c328  mov     rcx, [rsi]; Block
0x14001c32b  mov     [rbp+hKey], r14
0x14001c32f  mov     [rbp+cchValueName], 104h
0x14001c336  mov     [rbp+Type], r14d
0x14001c33a  mov     [rbp+cbData], r14d
0x14001c33e  mov     [rbp+var_1C], r14d
0x14001c342  mov     [rbp+var_18], r14d
0x14001c346  call    cs:__imp_free
0x14001c34d  nop     dword ptr [rax+rax+00h]
0x14001c352  xor     r9d, r9d; lpName
0x14001c355  mov     [rsi], r14
0x14001c358  xor     r8d, r8d; bInitialState
0x14001c35b  xor     edx, edx; bManualReset
0x14001c35d  xor     ecx, ecx; lpEventAttributes
0x14001c35f  call    cs:__imp_CreateEventW
0x14001c366  nop     dword ptr [rax+rax+00h]
0x14001c36b  mov     r14, rax
0x14001c36e  test    rax, rax
0x14001c371  jnz     short loc_14001C394
0x14001c373  call    cs:__imp_GetLastError
0x14001c37a  nop     dword ptr [rax+rax+00h]
0x14001c37f  test    eax, eax
0x14001c381  jle     loc_14001C62A
0x14001c387  movzx   eax, ax
0x14001c38a  or      eax, 80070000h
0x14001c38f  jmp     loc_14001C62A
0x14001c394  lea     rax, [rbp+hKey]
0x14001c398  mov     r9d, 20019h; samDesired
0x14001c39e  mov     r8d, 8; ulOptions
0x14001c3a4  mov     [rsp+60h+phkResult], rax; phkResult
0x14001c3a9  mov     rdx, rbx; lpSubKey
0x14001c3ac  mov     rcx, rdi; hKey
0x14001c3af  call    cs:__imp_RegOpenKeyExW
0x14001c3b6  nop     dword ptr [rax+rax+00h]
0x14001c3bb  mov     ebx, eax
0x14001c3bd  test    eax, eax
0x14001c3bf  jz      short loc_14001C3E4
0x14001c3c1  mov     rcx, r14; hObject
0x14001c3c4  call    cs:__imp_CloseHandle
0x14001c3cb  nop     dword ptr [rax+rax+00h]
0x14001c3d0  test    ebx, ebx
0x14001c3d2  jle     short loc_14001C3DD
0x14001c3d4  movzx   ebx, bx
0x14001c3d7  or      ebx, 80070000h
0x14001c3dd  mov     eax, ebx
0x14001c3df  jmp     loc_14001C62A
0x14001c3e4  mov     rcx, [rbp+hKey]; hKey
0x14001c3e8  mov     edi, 1
0x14001c3ed  mov     r9, r14; hEvent
0x14001c3f0  mov     dword ptr [rsp+60h+phkResult], edi; fAsynchronous
0x14001c3f4  xor     edx, edx; bWatchSubtree
0x14001c3f6  lea     r8d, [rdi+4]; dwNotifyFilter
0x14001c3fa  call    cs:__imp_RegNotifyChangeKeyValue
0x14001c401  nop     dword ptr [rax+rax+00h]
0x14001c406  mov     ebx, eax
0x14001c408  test    eax, eax
0x14001c40a  jz      short loc_14001C42D
0x14001c40c  mov     rcx, r14; hObject
0x14001c40f  call    cs:__imp_CloseHandle
0x14001c416  nop     dword ptr [rax+rax+00h]
0x14001c41b  mov     rcx, [rbp+hKey]; hKey
0x14001c41f  call    cs:__imp_RegCloseKey
0x14001c426  nop     dword ptr [rax+rax+00h]
0x14001c42b  jmp     short loc_14001C3D0
0x14001c42d  mov     edx, [rbp+dwIndex]; dwIndex
0x14001c430  lea     rax, [rbp+cbData]
0x14001c434  mov     rcx, [rbp+hKey]; hKey
0x14001c438  lea     r9, [rbp+cchValueName]; lpcchValueName
0x14001c43c  mov     [rsp+60h+lpcbData], rax; lpcbData
0x14001c441  mov     r8, r15; lpValueName
0x14001c444  lea     rax, [rbp+Type]
0x14001c448  mov     [rsp+60h+lpData], 0; lpData
0x14001c451  mov     [rsp+60h+lpType], rax; lpType
0x14001c456  mov     [rsp+60h+phkResult], 0; lpReserved
0x14001c45f  mov     [rbp+cchValueName], 104h
0x14001c466  call    cs:__imp_RegEnumValueW
0x14001c46d  nop     dword ptr [rax+rax+00h]
0x14001c472  mov     ebx, eax
0x14001c474  cmp     eax, 103h
0x14001c479  jz      short loc_14001C4A6
0x14001c47b  xor     edi, edi
0x14001c47d  test    eax, eax
0x14001c47f  jz      short loc_14001C488
0x14001c481  cmp     eax, 0EAh
0x14001c486  jnz     short loc_14001C40C
0x14001c488  mov     eax, [rbp+cbData]
0x14001c48b  test    eax, eax
0x14001c48d  jz      loc_14001C548
0x14001c493  mov     edx, eax
0x14001c495  mov     rcx, rsi
0x14001c498  call    ?Allocate@?$CHeapPtr@EVCCRTAllocator@ATL@@@ATL@@QEAA_N_K@Z; ATL::CHeapPtr<uchar,ATL::CCRTAllocator>::Allocate(unsigned __int64)
0x14001c49d  test    al, al
0x14001c49f  jnz     short loc_14001C4CC
0x14001c4a1  mov     edi, 8007000Eh
0x14001c4a6  mov     rcx, r14; hObject
0x14001c4a9  call    cs:__imp_CloseHandle
0x14001c4b0  nop     dword ptr [rax+rax+00h]
0x14001c4b5  mov     rcx, [rbp+hKey]; hKey
0x14001c4b9  call    cs:__imp_RegCloseKey
0x14001c4c0  nop     dword ptr [rax+rax+00h]
0x14001c4c5  mov     eax, edi
0x14001c4c7  jmp     loc_14001C62A
0x14001c4cc  mov     edx, [rbp+dwIndex]; dwIndex
0x14001c4cf  lea     rax, [rbp+cbData]
0x14001c4d3  mov     rcx, [rbp+hKey]; hKey
0x14001c4d7  lea     r9, [rbp+cchValueName]; lpcchValueName
0x14001c4db  mov     [rsp+60h+lpcbData], rax; lpcbData
0x14001c4e0  mov     r8, r15; lpValueName
0x14001c4e3  mov     rax, [rsi]
0x14001c4e6  mov     [rsp+60h+lpData], rax; lpData
0x14001c4eb  lea     rax, [rbp+Type]
0x14001c4ef  mov     [rsp+60h+lpType], rax; lpType
0x14001c4f4  mov     [rsp+60h+phkResult], rdi; lpReserved
0x14001c4f9  mov     [rbp+cchValueName], 104h
0x14001c500  call    cs:__imp_RegEnumValueW
0x14001c507  nop     dword ptr [rax+rax+00h]
0x14001c50c  mov     ebx, eax
0x14001c50e  test    eax, eax
0x14001c510  jz      short loc_14001C548
0x14001c512  mov     rcx, r14; hObject
0x14001c515  call    cs:__imp_CloseHandle
0x14001c51c  nop     dword ptr [rax+rax+00h]
0x14001c521  mov     rcx, [rbp+hKey]; hKey
0x14001c525  call    cs:__imp_RegCloseKey
0x14001c52c  nop     dword ptr [rax+rax+00h]
0x14001c531  mov     rcx, [rsi]; Block
0x14001c534  call    cs:__imp_free
0x14001c53b  nop     dword ptr [rax+rax+00h]
0x14001c540  mov     [rsi], rdi
0x14001c543  jmp     loc_14001C3D0
0x14001c548  mov     rcx, [rbp+hKey]; hKey
0x14001c54c  lea     rax, [rbp+var_18]
0x14001c550  mov     [rsp+60h+lpType], rax; lpcbData
0x14001c555  lea     r9, [rbp+var_1C]; lpType
0x14001c559  xor     r8d, r8d; lpReserved
0x14001c55c  mov     [rsp+60h+phkResult], rdi; lpData
0x14001c561  lea     rdx, aSymboliclinkva; "SymbolicLinkValue"
0x14001c568  call    cs:__imp_RegQueryValueExW
0x14001c56f  nop     dword ptr [rax+rax+00h]
0x14001c574  mov     rcx, [rbp+hKey]; hKey
0x14001c578  mov     edi, eax
0x14001c57a  call    cs:__imp_RegCloseKey
0x14001c581  nop     dword ptr [rax+rax+00h]
0x14001c586  xor     edx, edx; dwMilliseconds
0x14001c588  mov     rcx, r14; hHandle
0x14001c58b  call    cs:__imp_WaitForSingleObject
0x14001c592  nop     dword ptr [rax+rax+00h]
0x14001c597  mov     rcx, r14; hObject
0x14001c59a  mov     ebx, eax
0x14001c59c  call    cs:__imp_CloseHandle
0x14001c5a3  nop     dword ptr [rax+rax+00h]
0x14001c5a8  test    ebx, ebx
0x14001c5aa  jnz     short loc_14001C5B3
0x14001c5ac  mov     ebx, 8007051Ah
0x14001c5b1  jmp     short loc_14001C5F9
0x14001c5b3  test    edi, edi
0x14001c5b5  jz      short loc_14001C5EE
0x14001c5b7  cmp     edi, 2
0x14001c5ba  jz      short loc_14001C61A
0x14001c5bc  mov     rcx, [rsi]; Block
0x14001c5bf  call    cs:__imp_free
0x14001c5c6  nop     dword ptr [rax+rax+00h]
0x14001c5cb  xor     eax, eax
0x14001c5cd  mov     qword ptr [rsi], 0
0x14001c5d4  mov     [r15], ax
0x14001c5d8  test    edi, edi
0x14001c5da  jle     loc_14001C4C5
0x14001c5e0  movzx   edi, di
0x14001c5e3  or      edi, 80070000h
0x14001c5e9  jmp     loc_14001C4C5
0x14001c5ee  cmp     [rbp+var_1C], 6
0x14001c5f2  jnz     short loc_14001C61A
0x14001c5f4  mov     ebx, 800705B8h
0x14001c5f9  mov     rcx, [rsi]; Block
0x14001c5fc  call    cs:__imp_free
0x14001c603  nop     dword ptr [rax+rax+00h]
0x14001c608  xor     ecx, ecx
0x14001c60a  mov     qword ptr [rsi], 0
0x14001c611  mov     [r15], cx
0x14001c615  jmp     loc_14001C3DD
0x14001c61a  mov     eax, [rbp+Type]
0x14001c61d  mov     [r12], eax
0x14001c621  mov     eax, [rbp+cbData]
0x14001c624  mov     [r13+0], eax
0x14001c628  xor     eax, eax
0x14001c62a  mov     rbx, [rsp+60h+arg_0]
0x14001c632  add     rsp, 60h
0x14001c636  pop     r15
0x14001c638  pop     r14
0x14001c63a  pop     r13
0x14001c63c  pop     r12
0x14001c63e  pop     rdi
0x14001c63f  pop     rsi
0x14001c640  pop     rbp
0x14001c641  retn
```
