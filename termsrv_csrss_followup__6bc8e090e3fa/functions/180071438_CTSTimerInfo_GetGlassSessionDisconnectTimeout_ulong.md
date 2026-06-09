# CTSTimerInfo::GetGlassSessionDisconnectTimeout(ulong *)

- ea: `0x180071438`
- end: `0x18007151a`
- name: `?GetGlassSessionDisconnectTimeout@CTSTimerInfo@@QEAAJPEAK@Z`
- size: `226`
- prototype: `__int64 __fastcall(CTSTimerInfo *__hidden this, unsigned int *)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180071a80`
- `0x1800724c0`

## callees

- `0x180009940`
- `0x180071438`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800714d9`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800714d9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180071504`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180071504`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18007148c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18007148c`

## string_xrefs

- `0x180071479`: `Software\Policies\Microsoft\Windows NT\Terminal Services`
- `0x18007149c`: `Could not open the TS policy key for glass session`

## pseudocode

```c
__int64 __fastcall CTSTimerInfo::GetGlassSessionDisconnectTimeout(CTSTimerInfo *this, unsigned int *a2)
{
  unsigned int v3; // ebx
  unsigned int Data; // [rsp+50h] [rbp+8h] BYREF
  int v6; // [rsp+54h] [rbp+Ch]
  DWORD cbData; // [rsp+58h] [rbp+10h] BYREF
  DWORD Type; // [rsp+60h] [rbp+18h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+20h] BYREF

  v6 = HIDWORD(this);
  hKey = 0;
  Type = 0;
  cbData = 4;
  Data = 0;
  *a2 = 0;
  if ( RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"Software\\Policies\\Microsoft\\Windows NT\\Terminal Services",
         0,
         0x20019u,
         &hKey) )
  {
    _DbgPrintMessage(4, "Could not open the TS policy key for glass session");
LABEL_3:
    v3 = 1;
    goto LABEL_7;
  }
  if ( RegQueryValueExW(hKey, L"MaxDisconnectionTime", 0, &Type, (LPBYTE)&Data, &cbData) )
  {
    _DbgPrintMessage(4, "Could not obtain disconnection timeout value for glass");
    goto LABEL_3;
  }
  v3 = 0;
  *a2 = Data;
LABEL_7:
  if ( hKey )
    RegCloseKey(hKey);
  return v3;
}

```

## disassembly

```asm
0x180071438  mov     rax, rsp
0x18007143b  mov     [rax+8], rcx
0x18007143f  push    rbx
0x180071440  push    rdi
0x180071441  sub     rsp, 38h
0x180071445  mov     qword ptr [rax+20h], 0
0x18007144d  mov     rdi, rdx
0x180071450  mov     dword ptr [rax+18h], 0
0x180071457  mov     ebx, 4
0x18007145c  mov     [rax+10h], ebx
0x18007145f  mov     r9d, 20019h; samDesired
0x180071465  mov     dword ptr [rax+8], 0
0x18007146c  lea     rax, [rax+20h]
0x180071470  mov     dword ptr [rdx], 0
0x180071476  xor     r8d, r8d; ulOptions
0x180071479  lea     rdx, aSoftwarePolici; "Software\\Policies\\Microsoft\\Windows "...
0x180071480  mov     [rsp+48h+phkResult], rax; phkResult
0x180071485  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18007148c  call    cs:__imp_RegOpenKeyExW
0x180071493  nop     dword ptr [rax+rax+00h]
0x180071498  test    eax, eax
0x18007149a  jz      short loc_1800714B1
0x18007149c  lea     rdx, aCouldNotOpenTh; "Could not open the TS policy key for gl"...
0x1800714a3  mov     ecx, ebx; int
0x1800714a5  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800714aa  mov     ebx, 1
0x1800714af  jmp     short loc_1800714FA
0x1800714b1  mov     rcx, [rsp+48h+hKey]; hKey
0x1800714b6  lea     rax, [rsp+48h+cbData]
0x1800714bb  mov     [rsp+48h+lpcbData], rax; lpcbData
0x1800714c0  lea     r9, [rsp+48h+Type]; lpType
0x1800714c5  lea     rax, [rsp+48h+Data]
0x1800714ca  xor     r8d, r8d; lpReserved
0x1800714cd  lea     rdx, aMaxdisconnecti; "MaxDisconnectionTime"
0x1800714d4  mov     [rsp+48h+phkResult], rax; lpData
0x1800714d9  call    cs:__imp_RegQueryValueExW
0x1800714e0  nop     dword ptr [rax+rax+00h]
0x1800714e5  test    eax, eax
0x1800714e7  jz      short loc_1800714F2
0x1800714e9  lea     rdx, aCouldNotObtain; "Could not obtain disconnection timeout "...
0x1800714f0  jmp     short loc_1800714A3
0x1800714f2  mov     ecx, [rsp+48h+Data]
0x1800714f6  xor     ebx, ebx
0x1800714f8  mov     [rdi], ecx
0x1800714fa  mov     rcx, [rsp+48h+hKey]; hKey
0x1800714ff  test    rcx, rcx
0x180071502  jz      short loc_180071510
0x180071504  call    cs:__imp_RegCloseKey
0x18007150b  nop     dword ptr [rax+rax+00h]
0x180071510  mov     eax, ebx
0x180071512  add     rsp, 38h
0x180071516  pop     rdi
0x180071517  pop     rbx
0x180071518  retn
```
