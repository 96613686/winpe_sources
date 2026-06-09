# CTSTimerInfo::GetGlassSessionDisconnectTimeout(ulong *)

- ea: `0x18006df68`
- end: `0x18006e037`
- name: `?GetGlassSessionDisconnectTimeout@CTSTimerInfo@@QEAAJPEAK@Z`
- size: `207`
- prototype: `__int64 __fastcall(CTSTimerInfo *__hidden this, unsigned int *)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18006e598`
- `0x18006efd0`

## callees

- `0x18000a210`
- `0x18006df68`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18006e003`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18006e003`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006e028`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006e028`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006dfbc`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006dfbc`

## string_xrefs

- `0x18006dfa9`: `Software\Policies\Microsoft\Windows NT\Terminal Services`
- `0x18006dfc6`: `Could not open the TS policy key for glass session`

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
0x18006df68  mov     rax, rsp
0x18006df6b  mov     [rax+8], rcx
0x18006df6f  push    rbx
0x18006df70  push    rdi
0x18006df71  sub     rsp, 38h
0x18006df75  mov     qword ptr [rax+20h], 0
0x18006df7d  mov     rdi, rdx
0x18006df80  mov     dword ptr [rax+18h], 0
0x18006df87  mov     ebx, 4
0x18006df8c  mov     [rax+10h], ebx
0x18006df8f  mov     r9d, 20019h; samDesired
0x18006df95  mov     dword ptr [rax+8], 0
0x18006df9c  lea     rax, [rax+20h]
0x18006dfa0  mov     dword ptr [rdx], 0
0x18006dfa6  xor     r8d, r8d; ulOptions
0x18006dfa9  lea     rdx, aSoftwarePolici; "Software\\Policies\\Microsoft\\Windows "...
0x18006dfb0  mov     [rsp+48h+phkResult], rax; phkResult
0x18006dfb5  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18006dfbc  call    cs:__imp_RegOpenKeyExW
0x18006dfc2  test    eax, eax
0x18006dfc4  jz      short loc_18006DFDB
0x18006dfc6  lea     rdx, aCouldNotOpenTh; "Could not open the TS policy key for gl"...
0x18006dfcd  mov     ecx, ebx; int
0x18006dfcf  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18006dfd4  mov     ebx, 1
0x18006dfd9  jmp     short loc_18006E01E
0x18006dfdb  mov     rcx, [rsp+48h+hKey]; hKey
0x18006dfe0  lea     rax, [rsp+48h+cbData]
0x18006dfe5  mov     [rsp+48h+lpcbData], rax; lpcbData
0x18006dfea  lea     r9, [rsp+48h+Type]; lpType
0x18006dfef  lea     rax, [rsp+48h+Data]
0x18006dff4  xor     r8d, r8d; lpReserved
0x18006dff7  lea     rdx, aMaxdisconnecti; "MaxDisconnectionTime"
0x18006dffe  mov     [rsp+48h+phkResult], rax; lpData
0x18006e003  call    cs:__imp_RegQueryValueExW
0x18006e009  test    eax, eax
0x18006e00b  jz      short loc_18006E016
0x18006e00d  lea     rdx, aCouldNotObtain; "Could not obtain disconnection timeout "...
0x18006e014  jmp     short loc_18006DFCD
0x18006e016  mov     ecx, [rsp+48h+Data]
0x18006e01a  xor     ebx, ebx
0x18006e01c  mov     [rdi], ecx
0x18006e01e  mov     rcx, [rsp+48h+hKey]; hKey
0x18006e023  test    rcx, rcx
0x18006e026  jz      short loc_18006E02E
0x18006e028  call    cs:__imp_RegCloseKey
0x18006e02e  mov     eax, ebx
0x18006e030  add     rsp, 38h
0x18006e034  pop     rdi
0x18006e035  pop     rbx
0x18006e036  retn
```
