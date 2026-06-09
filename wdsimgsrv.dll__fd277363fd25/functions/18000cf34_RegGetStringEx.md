# RegGetStringEx

- ea: `0x18000cf34`
- end: `0x18000d0b8`
- name: `RegGetStringEx`
- size: `388`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000c3f8`

## callees

- `0x18000cf34`

## import_xrefs

- `KERNEL32!HeapFree` at `0x18000d06a`
- `KERNEL32!HeapFree` at `0x18000d06a`
- `KERNEL32!SetLastError` at `0x18000d09b`
- `KERNEL32!SetLastError` at `0x18000d09b`
- `KERNEL32!GetLastError` at `0x18000d07b`
- `KERNEL32!GetLastError` at `0x18000d07b`
- `KERNEL32!HeapAlloc` at `0x18000cfff`
- `KERNEL32!HeapAlloc` at `0x18000cfff`
- `KERNEL32!GetProcessHeap` at `0x18000cfe8`
- `KERNEL32!GetProcessHeap` at `0x18000d056`
- `KERNEL32!GetProcessHeap` at `0x18000cfe8`
- `KERNEL32!GetProcessHeap` at `0x18000d056`
- `ADVAPI32!RegCloseKey` at `0x18000d08d`
- `ADVAPI32!RegCloseKey` at `0x18000d08d`
- `ADVAPI32!RegOpenKeyExW` at `0x18000cf7e`
- `ADVAPI32!RegOpenKeyExW` at `0x18000cf7e`
- `ADVAPI32!RegQueryValueExW` at `0x18000cfbd`
- `ADVAPI32!RegQueryValueExW` at `0x18000d035`
- `ADVAPI32!RegQueryValueExW` at `0x18000cfbd`
- `ADVAPI32!RegQueryValueExW` at `0x18000d035`

## pseudocode

```c
BYTE *__fastcall RegGetStringEx(__int64 a1, __int64 a2, __int64 a3)
{
  BYTE *v3; // rdi
  DWORD LastError; // ebx
  DWORD v5; // ebx
  HANDLE ProcessHeap; // rax
  BYTE *lpData; // rax
  HANDLE v8; // rax
  HKEY hKey; // [rsp+58h] [rbp+28h] BYREF
  DWORD Type; // [rsp+60h] [rbp+30h] BYREF
  int v12; // [rsp+64h] [rbp+34h]
  DWORD cbData; // [rsp+68h] [rbp+38h] BYREF

  v12 = HIDWORD(a3);
  hKey = 0;
  cbData = 0;
  Type = 0;
  v3 = 0;
  LastError = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Windows NT\\CurrentVersion", 0, 0x20019u, &hKey);
  if ( !LastError && hKey )
  {
    LastError = RegQueryValueExW(hKey, L"RegisteredOrganization", 0, &Type, 0, &cbData);
    if ( !LastError )
    {
      if ( Type - 1 <= 1 )
      {
        v5 = cbData;
        ProcessHeap = GetProcessHeap();
        lpData = (BYTE *)HeapAlloc(ProcessHeap, 8u, v5);
        v3 = lpData;
        if ( !lpData )
        {
          LastError = GetLastError();
          goto LABEL_12;
        }
        *(_WORD *)lpData = 0;
        LastError = RegQueryValueExW(hKey, L"RegisteredOrganization", 0, 0, lpData, &cbData);
        if ( !LastError )
        {
          if ( Type - 1 <= 1 )
            goto LABEL_12;
          LastError = 13;
        }
        v8 = GetProcessHeap();
        HeapFree(v8, 0, v3);
        v3 = 0;
        goto LABEL_12;
      }
      LastError = 13;
    }
LABEL_12:
    RegCloseKey(hKey);
  }
  SetLastError(LastError);
  return v3;
}

```

## disassembly

```asm
0x18000cf34  mov     r11, rsp
0x18000cf37  mov     [r11+8], rbx
0x18000cf3b  mov     [r11+20h], r9d
0x18000cf3f  mov     [r11+18h], r8
0x18000cf43  mov     [r11+10h], rdx
0x18000cf47  push    rbp
0x18000cf48  push    rsi
0x18000cf49  push    rdi
0x18000cf4a  mov     rbp, rsp
0x18000cf4d  sub     rsp, 30h
0x18000cf51  xor     esi, esi
0x18000cf53  lea     rax, [rbp+hKey]
0x18000cf57  mov     r9d, 20019h; samDesired
0x18000cf5d  mov     [rbp+hKey], rsi
0x18000cf61  xor     r8d, r8d; ulOptions
0x18000cf64  mov     [rbp+cbData], esi
0x18000cf67  lea     rdx, SubKey; "Software\\Microsoft\\Windows NT\\Curren"...
0x18000cf6e  mov     [rbp+Type], esi
0x18000cf71  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000cf78  mov     [r11-28h], rax
0x18000cf7c  mov     edi, esi
0x18000cf7e  call    cs:__imp_RegOpenKeyExW
0x18000cf85  nop     dword ptr [rax+rax+00h]
0x18000cf8a  mov     ebx, eax
0x18000cf8c  test    eax, eax
0x18000cf8e  jnz     loc_18000D099
0x18000cf94  mov     rcx, [rbp+hKey]; hKey
0x18000cf98  test    rcx, rcx
0x18000cf9b  jz      loc_18000D099
0x18000cfa1  lea     rax, [rbp+cbData]
0x18000cfa5  xor     r8d, r8d; lpReserved
0x18000cfa8  mov     [rsp+30h+lpcbData], rax; lpcbData
0x18000cfad  lea     r9, [rbp+Type]; lpType
0x18000cfb1  lea     rdx, ValueName; "RegisteredOrganization"
0x18000cfb8  mov     [rsp+30h+lpData], rsi; lpData
0x18000cfbd  call    cs:__imp_RegQueryValueExW
0x18000cfc4  nop     dword ptr [rax+rax+00h]
0x18000cfc9  mov     ebx, eax
0x18000cfcb  test    eax, eax
0x18000cfcd  jnz     loc_18000D089
0x18000cfd3  mov     eax, [rbp+Type]
0x18000cfd6  dec     eax
0x18000cfd8  cmp     eax, 1
0x18000cfdb  jbe     short loc_18000CFE5
0x18000cfdd  lea     ebx, [rsi+0Dh]
0x18000cfe0  jmp     loc_18000D089
0x18000cfe5  mov     ebx, [rbp+cbData]
0x18000cfe8  call    cs:__imp_GetProcessHeap
0x18000cfef  nop     dword ptr [rax+rax+00h]
0x18000cff4  mov     r8d, ebx; dwBytes
0x18000cff7  mov     edx, 8; dwFlags
0x18000cffc  mov     rcx, rax; hHeap
0x18000cfff  call    cs:__imp_HeapAlloc
0x18000d006  nop     dword ptr [rax+rax+00h]
0x18000d00b  mov     rdi, rax
0x18000d00e  test    rax, rax
0x18000d011  jz      short loc_18000D07B
0x18000d013  mov     [rax], si
0x18000d016  lea     rdx, ValueName; "RegisteredOrganization"
0x18000d01d  mov     rcx, [rbp+hKey]; hKey
0x18000d021  lea     rax, [rbp+cbData]
0x18000d025  mov     [rsp+30h+lpcbData], rax; lpcbData
0x18000d02a  xor     r9d, r9d; lpType
0x18000d02d  xor     r8d, r8d; lpReserved
0x18000d030  mov     [rsp+30h+lpData], rdi; lpData
0x18000d035  call    cs:__imp_RegQueryValueExW
0x18000d03c  nop     dword ptr [rax+rax+00h]
0x18000d041  mov     ebx, eax
0x18000d043  test    eax, eax
0x18000d045  jnz     short loc_18000D056
0x18000d047  mov     eax, [rbp+Type]
0x18000d04a  dec     eax
0x18000d04c  cmp     eax, 1
0x18000d04f  jbe     short loc_18000D089
0x18000d051  mov     ebx, 0Dh
0x18000d056  call    cs:__imp_GetProcessHeap
0x18000d05d  nop     dword ptr [rax+rax+00h]
0x18000d062  mov     r8, rdi; lpMem
0x18000d065  xor     edx, edx; dwFlags
0x18000d067  mov     rcx, rax; hHeap
0x18000d06a  call    cs:__imp_HeapFree
0x18000d071  nop     dword ptr [rax+rax+00h]
0x18000d076  mov     rdi, rsi
0x18000d079  jmp     short loc_18000D089
0x18000d07b  call    cs:__imp_GetLastError
0x18000d082  nop     dword ptr [rax+rax+00h]
0x18000d087  mov     ebx, eax
0x18000d089  mov     rcx, [rbp+hKey]; hKey
0x18000d08d  call    cs:__imp_RegCloseKey
0x18000d094  nop     dword ptr [rax+rax+00h]
0x18000d099  mov     ecx, ebx; dwErrCode
0x18000d09b  call    cs:__imp_SetLastError
0x18000d0a2  nop     dword ptr [rax+rax+00h]
0x18000d0a7  mov     rbx, [rsp+30h+arg_0]
0x18000d0ac  mov     rax, rdi
0x18000d0af  add     rsp, 30h
0x18000d0b3  pop     rdi
0x18000d0b4  pop     rsi
0x18000d0b5  pop     rbp
0x18000d0b6  retn
```
