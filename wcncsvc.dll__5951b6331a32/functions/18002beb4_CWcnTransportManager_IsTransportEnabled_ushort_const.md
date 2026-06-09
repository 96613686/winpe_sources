# CWcnTransportManager::IsTransportEnabled(ushort const *)

- ea: `0x18002beb4`
- end: `0x18002bf19`
- name: `?IsTransportEnabled@CWcnTransportManager@@AEAA_NPEBG@Z`
- size: `101`
- prototype: `bool __fastcall(CWcnTransportManager *this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task`

## callers

- `0x18002bf20`

## callees

- `0x18002beb4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002befe`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002befe`

## string_xrefs

- `0x18002bee2`: `SYSTEM\CurrentControlSet\Services\wcncsvc\Parameters`

## pseudocode

```c
bool __fastcall CWcnTransportManager::IsTransportEnabled(CWcnTransportManager *this, const unsigned __int16 *a2)
{
  int v3; // [rsp+50h] [rbp+8h] BYREF
  int v4; // [rsp+54h] [rbp+Ch]
  DWORD v5; // [rsp+60h] [rbp+18h] BYREF

  v4 = HIDWORD(this);
  v3 = 0;
  v5 = 4;
  return RegGetValueW(
           HKEY_LOCAL_MACHINE,
           L"SYSTEM\\CurrentControlSet\\Services\\wcncsvc\\Parameters",
           a2,
           0x10u,
           0,
           &v3,
           &v5)
      || v3 == 0;
}

```

## disassembly

```asm
0x18002beb4  mov     r11, rsp
0x18002beb7  mov     [r11+8], rcx
0x18002bebb  sub     rsp, 48h
0x18002bebf  lea     rax, [r11+18h]
0x18002bec3  mov     [rsp+48h+arg_0], 0
0x18002becb  mov     [r11-18h], rax
0x18002becf  mov     r8, rdx; lpValue
0x18002bed2  lea     rax, [r11+8]
0x18002bed6  mov     [rsp+48h+arg_10], 4
0x18002bede  mov     [r11-20h], rax
0x18002bee2  lea     rdx, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Services\\wc"...
0x18002bee9  mov     r9d, 10h; dwFlags
0x18002beef  mov     qword ptr [r11-28h], 0
0x18002bef7  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18002befe  call    cs:__imp_RegGetValueW
0x18002bf04  test    eax, eax
0x18002bf06  jz      short loc_18002BF0C
0x18002bf08  mov     al, 1
0x18002bf0a  jmp     short loc_18002BF14
0x18002bf0c  cmp     [rsp+48h+arg_0], 0
0x18002bf11  setz    al
0x18002bf14  add     rsp, 48h
0x18002bf18  retn
```
