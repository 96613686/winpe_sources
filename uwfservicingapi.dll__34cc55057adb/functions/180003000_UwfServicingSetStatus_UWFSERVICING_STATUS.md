# UwfServicingSetStatus(UWFSERVICING_STATUS)

- ea: `0x180003000`
- end: `0x1800030b2`
- name: `?UwfServicingSetStatus@@YAJW4UWFSERVICING_STATUS@@@Z`
- size: `178`
- prototype: `LSTATUS __fastcall(int)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x1800030b8`

## callees

- `0x180003000`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180003050`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180003050`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180003097`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180003097`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000308a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000308a`

## string_xrefs

- `0x18000301c`: `SYSTEM\CurrentControlSet\Services\UwfServicingSvc\Servicing`

## pseudocode

```c
LSTATUS __fastcall UwfServicingSetStatus(int a1)
{
  LSTATUS result; // eax
  LSTATUS v2; // ebx
  int Data; // [rsp+60h] [rbp+8h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+10h] BYREF

  Data = a1;
  hKey = 0;
  result = RegCreateKeyExW(
             HKEY_LOCAL_MACHINE,
             L"SYSTEM\\CurrentControlSet\\Services\\UwfServicingSvc\\Servicing",
             0,
             0,
             0,
             0x2001Fu,
             0,
             &hKey,
             0);
  if ( result )
  {
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  else
  {
    v2 = RegSetValueExW(hKey, L"Status", 0, 4u, (const BYTE *)&Data, 4u);
    RegCloseKey(hKey);
    if ( v2 > 0 )
      return (unsigned __int16)v2 | 0x80070000;
    return v2;
  }
  return result;
}

```

## disassembly

```asm
0x180003000  mov     [rsp+Data], ecx
0x180003004  mov     r11, rsp
0x180003007  push    rbx
0x180003008  sub     rsp, 50h
0x18000300c  mov     qword ptr [r11-18h], 0
0x180003014  lea     rax, [r11+10h]
0x180003018  mov     [r11-20h], rax
0x18000301c  lea     rdx, SubKey; "SYSTEM\\CurrentControlSet\\Services\\Uw"...
0x180003023  mov     qword ptr [r11-28h], 0
0x18000302b  xor     r9d, r9d; lpClass
0x18000302e  mov     [rsp+58h+samDesired], 2001Fh; samDesired
0x180003036  xor     r8d, r8d; Reserved
0x180003039  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180003040  mov     [rsp+58h+dwOptions], 0; dwOptions
0x180003048  mov     qword ptr [r11+10h], 0
0x180003050  call    cs:__imp_RegCreateKeyExW
0x180003056  test    eax, eax
0x180003058  jz      short loc_180003066
0x18000305a  jle     short loc_1800030AC
0x18000305c  movzx   eax, ax
0x18000305f  or      eax, 80070000h
0x180003064  jmp     short loc_1800030AC
0x180003066  mov     rcx, [rsp+58h+hKey]; hKey
0x18000306b  lea     rax, [rsp+58h+Data]
0x180003070  mov     r9d, 4; dwType
0x180003076  lea     rdx, ValueName; "Status"
0x18000307d  mov     [rsp+58h+samDesired], r9d; cbData
0x180003082  xor     r8d, r8d; Reserved
0x180003085  mov     qword ptr [rsp+58h+dwOptions], rax; lpData
0x18000308a  call    cs:__imp_RegSetValueExW
0x180003090  mov     rcx, [rsp+58h+hKey]; hKey
0x180003095  mov     ebx, eax
0x180003097  call    cs:__imp_RegCloseKey
0x18000309d  test    ebx, ebx
0x18000309f  jle     short loc_1800030AA
0x1800030a1  movzx   ebx, bx
0x1800030a4  or      ebx, 80070000h
0x1800030aa  mov     eax, ebx
0x1800030ac  add     rsp, 50h
0x1800030b0  pop     rbx
0x1800030b1  retn
```
