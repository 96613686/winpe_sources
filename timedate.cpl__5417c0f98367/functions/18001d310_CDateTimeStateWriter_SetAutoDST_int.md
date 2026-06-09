# CDateTimeStateWriter::SetAutoDST(int)

- ea: `0x18001d310`
- end: `0x18001d36a`
- name: `?SetAutoDST@CDateTimeStateWriter@@UEAAJH@Z`
- size: `90`
- prototype: `__int64 __fastcall(CDateTimeStateWriter *__hidden this, int)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180014db0`
- `0x18001d310`

## import_xrefs

- `SHLWAPI!SHSetValueW` at `0x18001d352`
- `SHLWAPI!SHSetValueW` at `0x18001d352`
- `SHLWAPI!SHDeleteValueW` at `0x18001d32d`
- `SHLWAPI!SHDeleteValueW` at `0x18001d32d`

## pseudocode

```c
LSTATUS __fastcall CDateTimeStateWriter::SetAutoDST(CDateTimeStateWriter *this, int a2)
{
  LSTATUS result; // eax
  int pvData; // [rsp+48h] [rbp+10h] BYREF

  if ( a2 )
  {
    result = SHDeleteValueW(
               HKEY_LOCAL_MACHINE,
               L"System\\CurrentControlSet\\Control\\TimeZoneInformation",
               L"DisableAutoDaylightTimeSet");
  }
  else
  {
    pvData = 1;
    result = SHSetValueW(
               HKEY_LOCAL_MACHINE,
               L"System\\CurrentControlSet\\Control\\TimeZoneInformation",
               L"DisableAutoDaylightTimeSet",
               4u,
               &pvData,
               4u);
  }
  if ( result )
    return ResultFromLastError();
  return result;
}

```

## disassembly

```asm
0x18001d310  sub     rsp, 38h
0x18001d314  test    edx, edx
0x18001d316  lea     r8, aDisableautoday; "DisableAutoDaylightTimeSet"
0x18001d31d  lea     rdx, aSystemCurrentc; "System\\CurrentControlSet\\Control\\Tim"...
0x18001d324  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18001d32b  jz      short loc_18001D335
0x18001d32d  call    cs:__imp_SHDeleteValueW
0x18001d333  jmp     short loc_18001D358
0x18001d335  mov     r9d, 4; dwType
0x18001d33b  mov     [rsp+38h+arg_8], 1
0x18001d343  lea     rax, [rsp+38h+arg_8]
0x18001d348  mov     [rsp+38h+cbData], r9d; cbData
0x18001d34d  mov     [rsp+38h+pvData], rax; pvData
0x18001d352  call    cs:__imp_SHSetValueW
0x18001d358  test    eax, eax
0x18001d35a  jnz     short loc_18001D361
0x18001d35c  add     rsp, 38h
0x18001d360  retn
0x18001d361  add     rsp, 38h
0x18001d365  jmp     ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
```
