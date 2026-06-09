# JobStore::MarkPermissionsRestoreCompletion(void)

- ea: `0x180070720`
- end: `0x1800707ce`
- name: `?MarkPermissionsRestoreCompletion@JobStore@@AEBAJXZ`
- size: `174`
- prototype: `__int64 __fastcall(JobStore *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18006d788`

## callees

- `0x180021300`
- `0x180070720`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800707be`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800707be`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180070771`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180070771`

## string_xrefs

- `0x1800707a6`: `OwnUpdateCompleted`

## pseudocode

```c
__int64 __fastcall JobStore::MarkPermissionsRestoreCompletion(JobStore *this)
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
    v2 = RegSetValueExW(hKey, L"OwnUpdateCompleted", 0, 4u, (const BYTE *)&Data, 4u);
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
  wmi::AutoRegKey::Close(&hKey);
  return v3;
}

```

## disassembly

```asm
0x180070720  mov     r11, rsp
0x180070723  push    rbx
0x180070724  sub     rsp, 50h
0x180070728  mov     rcx, [rcx+10h]; hKey
0x18007072c  lea     rax, [r11+10h]
0x180070730  mov     qword ptr [r11-18h], 0
0x180070738  lea     rdx, ChannelPath; lpSubKey
0x18007073f  mov     [r11-20h], rax
0x180070743  xor     r9d, r9d; lpClass
0x180070746  mov     qword ptr [r11-28h], 0
0x18007074e  xor     r8d, r8d; Reserved
0x180070751  mov     [rsp+58h+samDesired], 2; samDesired
0x180070759  mov     [rsp+58h+dwOptions], 0; dwOptions
0x180070761  mov     qword ptr [r11+10h], 0
0x180070769  mov     [rsp+58h+Data], 1
0x180070771  call    cs:__imp_RegCreateKeyExW
0x180070777  mov     ebx, eax
0x180070779  test    eax, eax
0x18007077b  jz      short loc_18007079A
0x18007077d  jle     short loc_180070788
0x18007077f  movzx   ebx, ax
0x180070782  or      ebx, 80070000h
0x180070788  lea     rcx, [rsp+58h+hKey]; this
0x18007078d  call    ?Close@AutoRegKey@wmi@@QEAAXXZ; wmi::AutoRegKey::Close(void)
0x180070792  mov     eax, ebx
0x180070794  add     rsp, 50h
0x180070798  pop     rbx
0x180070799  retn
0x18007079a  mov     rcx, [rsp+58h+hKey]; hKey
0x18007079f  lea     rax, [rsp+58h+Data]
0x1800707a4  xor     ebx, ebx
0x1800707a6  lea     rdx, aOwnupdatecompl; "OwnUpdateCompleted"
0x1800707ad  xor     r8d, r8d; Reserved
0x1800707b0  lea     r9d, [rbx+4]; dwType
0x1800707b4  mov     [rsp+58h+samDesired], r9d; cbData
0x1800707b9  mov     qword ptr [rsp+58h+dwOptions], rax; lpData
0x1800707be  call    cs:__imp_RegSetValueExW
0x1800707c4  test    eax, eax
0x1800707c6  jz      short loc_180070788
0x1800707c8  jg      short loc_18007077F
0x1800707ca  mov     ebx, eax
0x1800707cc  jmp     short loc_180070788
```
