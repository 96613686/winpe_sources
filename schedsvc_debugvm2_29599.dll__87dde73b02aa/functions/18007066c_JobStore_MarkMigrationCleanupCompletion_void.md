# JobStore::MarkMigrationCleanupCompletion(void)

- ea: `0x18007066c`
- end: `0x18007071a`
- name: `?MarkMigrationCleanupCompletion@JobStore@@AEBAJXZ`
- size: `174`
- prototype: `__int64 __fastcall(JobStore *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18006d788`

## callees

- `0x180021300`
- `0x18007066c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18007070a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18007070a`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800706bd`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800706bd`

## string_xrefs

- `0x1800706f2`: `MigrationCleanupCompleted`

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
0x18007066c  mov     r11, rsp
0x18007066f  push    rbx
0x180070670  sub     rsp, 50h
0x180070674  mov     rcx, [rcx+10h]; hKey
0x180070678  lea     rax, [r11+10h]
0x18007067c  mov     qword ptr [r11-18h], 0
0x180070684  lea     rdx, ChannelPath; lpSubKey
0x18007068b  mov     [r11-20h], rax
0x18007068f  xor     r9d, r9d; lpClass
0x180070692  mov     qword ptr [r11-28h], 0
0x18007069a  xor     r8d, r8d; Reserved
0x18007069d  mov     [rsp+58h+samDesired], 2; samDesired
0x1800706a5  mov     [rsp+58h+dwOptions], 0; dwOptions
0x1800706ad  mov     qword ptr [r11+10h], 0
0x1800706b5  mov     [rsp+58h+Data], 1
0x1800706bd  call    cs:__imp_RegCreateKeyExW
0x1800706c3  mov     ebx, eax
0x1800706c5  test    eax, eax
0x1800706c7  jz      short loc_1800706E6
0x1800706c9  jle     short loc_1800706D4
0x1800706cb  movzx   ebx, ax
0x1800706ce  or      ebx, 80070000h
0x1800706d4  lea     rcx, [rsp+58h+hKey]; this
0x1800706d9  call    ?Close@AutoRegKey@wmi@@QEAAXXZ; wmi::AutoRegKey::Close(void)
0x1800706de  mov     eax, ebx
0x1800706e0  add     rsp, 50h
0x1800706e4  pop     rbx
0x1800706e5  retn
0x1800706e6  mov     rcx, [rsp+58h+hKey]; hKey
0x1800706eb  lea     rax, [rsp+58h+Data]
0x1800706f0  xor     ebx, ebx
0x1800706f2  lea     rdx, aMigrationclean; "MigrationCleanupCompleted"
0x1800706f9  xor     r8d, r8d; Reserved
0x1800706fc  lea     r9d, [rbx+4]; dwType
0x180070700  mov     [rsp+58h+samDesired], r9d; cbData
0x180070705  mov     qword ptr [rsp+58h+dwOptions], rax; lpData
0x18007070a  call    cs:__imp_RegSetValueExW
0x180070710  test    eax, eax
0x180070712  jz      short loc_1800706D4
0x180070714  jg      short loc_1800706CB
0x180070716  mov     ebx, eax
0x180070718  jmp     short loc_1800706D4
```
