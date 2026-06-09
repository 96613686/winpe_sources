# JobStore::MarkMigrationCleanupCompletion(void)

- ea: `0x180073f90`
- end: `0x18007404b`
- name: `?MarkMigrationCleanupCompletion@JobStore@@AEBAJXZ`
- size: `187`
- prototype: `__int64 __fastcall(JobStore *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180070e78`

## callees

- `0x18002db40`
- `0x180073f90`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180074035`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180074035`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180073fe1`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180073fe1`

## string_xrefs

- `0x18007401d`: `MigrationCleanupCompleted`

## pseudocode

```c
__int64 __fastcall JobStore::MarkMigrationCleanupCompletion(JobStore *this)
{
  HKEY v1; // rcx
  LSTATUS v2; // eax
  unsigned int v3; // ebx
  int Data; // [rsp+60h] [rbp+8h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+10h] BYREF

  v1 = (HKEY)*((_QWORD *)this + 2);
  hKey = 0;
  Data = 1;
  v2 = RegCreateKeyExW(v1, &ChannelPath, 0, 0, 0, 2u, 0, &hKey, 0);
  v3 = v2;
  if ( !v2 )
  {
    v3 = 0;
    v2 = RegSetValueExW(hKey, L"MigrationCleanupCompleted", 0, 4u, (const BYTE *)&Data, 4u);
    if ( !v2 )
      goto LABEL_4;
    if ( v2 <= 0 )
    {
      v3 = v2;
      goto LABEL_4;
    }
    goto LABEL_3;
  }
  if ( v2 > 0 )
LABEL_3:
    v3 = (unsigned __int16)v2 | 0x80070000;
LABEL_4:
  wmi::AutoRegKey::Close((wmi::AutoRegKey *)&hKey);
  return v3;
}

```

## disassembly

```asm
0x180073f90  mov     r11, rsp
0x180073f93  push    rbx
0x180073f94  sub     rsp, 50h
0x180073f98  mov     rcx, [rcx+10h]; hKey
0x180073f9c  lea     rax, [r11+10h]
0x180073fa0  mov     qword ptr [r11-18h], 0
0x180073fa8  lea     rdx, ChannelPath; lpSubKey
0x180073faf  mov     [r11-20h], rax
0x180073fb3  xor     r9d, r9d; lpClass
0x180073fb6  mov     qword ptr [r11-28h], 0
0x180073fbe  xor     r8d, r8d; Reserved
0x180073fc1  mov     [rsp+58h+samDesired], 2; samDesired
0x180073fc9  mov     [rsp+58h+dwOptions], 0; dwOptions
0x180073fd1  mov     qword ptr [r11+10h], 0
0x180073fd9  mov     [rsp+58h+Data], 1
0x180073fe1  call    cs:__imp_RegCreateKeyExW
0x180073fe8  nop     dword ptr [rax+rax+00h]
0x180073fed  mov     ebx, eax
0x180073fef  test    eax, eax
0x180073ff1  jz      short loc_180074011
0x180073ff3  jle     short loc_180073FFE
0x180073ff5  movzx   ebx, ax
0x180073ff8  or      ebx, 80070000h
0x180073ffe  lea     rcx, [rsp+58h+hKey]; this
0x180074003  call    ?Close@AutoRegKey@wmi@@QEAAXXZ; wmi::AutoRegKey::Close(void)
0x180074008  mov     eax, ebx
0x18007400a  add     rsp, 50h
0x18007400e  pop     rbx
0x18007400f  retn
0x180074011  mov     rcx, [rsp+58h+hKey]; hKey
0x180074016  lea     rax, [rsp+58h+Data]
0x18007401b  xor     ebx, ebx
0x18007401d  lea     rdx, aMigrationclean; "MigrationCleanupCompleted"
0x180074024  xor     r8d, r8d; Reserved
0x180074027  lea     r9d, [rbx+4]; dwType
0x18007402b  mov     [rsp+58h+samDesired], r9d; cbData
0x180074030  mov     qword ptr [rsp+58h+dwOptions], rax; lpData
0x180074035  call    cs:__imp_RegSetValueExW
0x18007403c  nop     dword ptr [rax+rax+00h]
0x180074041  test    eax, eax
0x180074043  jz      short loc_180073FFE
0x180074045  jg      short loc_180073FF5
0x180074047  mov     ebx, eax
0x180074049  jmp     short loc_180073FFE
```
