# UwfServicingSetStatusEx(UWFSERVICING_STATUS,UWFSERVICING_STATUS_INFO)

- ea: `0x1800030b8`
- end: `0x18000310a`
- name: `?UwfServicingSetStatusEx@@YAJW4UWFSERVICING_STATUS@@W4UWFSERVICING_STATUS_INFO@@@Z`
- size: `82`
- prototype: `LSTATUS __fastcall(int, int)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x180003540`
- `0x18000370c`

## callees

- `0x180003000`
- `0x1800030b8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1800030f3`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1800030f3`

## string_xrefs

- `0x1800030e0`: `SYSTEM\CurrentControlSet\Services\UwfServicingSvc\Servicing`

## pseudocode

```c
LSTATUS __fastcall UwfServicingSetStatusEx(int a1, int a2)
{
  LSTATUS result; // eax
  int Data; // [rsp+48h] [rbp+10h] BYREF

  Data = a2;
  result = UwfServicingSetStatus(a1);
  if ( result >= 0 )
  {
    result = RegSetKeyValueW(
               HKEY_LOCAL_MACHINE,
               L"SYSTEM\\CurrentControlSet\\Services\\UwfServicingSvc\\Servicing",
               L"Information",
               4u,
               &Data,
               4u);
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  return result;
}

```

## disassembly

```asm
0x1800030b8  mov     [rsp+Data], edx
0x1800030bc  sub     rsp, 38h
0x1800030c0  call    ?UwfServicingSetStatus@@YAJW4UWFSERVICING_STATUS@@@Z; UwfServicingSetStatus(UWFSERVICING_STATUS)
0x1800030c5  test    eax, eax
0x1800030c7  js      short loc_180003105
0x1800030c9  mov     r9d, 4; dwType
0x1800030cf  lea     rax, [rsp+38h+Data]
0x1800030d4  mov     [rsp+38h+cbData], r9d; cbData
0x1800030d9  lea     r8, Value; "Information"
0x1800030e0  lea     rdx, SubKey; "SYSTEM\\CurrentControlSet\\Services\\Uw"...
0x1800030e7  mov     [rsp+38h+lpData], rax; lpData
0x1800030ec  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800030f3  call    cs:__imp_RegSetKeyValueW
0x1800030f9  test    eax, eax
0x1800030fb  jle     short loc_180003105
0x1800030fd  movzx   eax, ax
0x180003100  or      eax, 80070000h
0x180003105  add     rsp, 38h
0x180003109  retn
```
