# CEphemKeyData::Reference(void)

- ea: `0x180078ca0`
- end: `0x180078cdb`
- name: `?Reference@CEphemKeyData@@UEAAEXZ`
- size: `59`
- prototype: `unsigned __int8 __fastcall(CEphemKeyData *__hidden this)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180078cb7`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180078cb7`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180078cca`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180078cca`

## pseudocode

```c
bool __fastcall CEphemKeyData::Reference(const FILETIME *this)
{
  struct _FILETIME SystemTimeAsFileTime; // [rsp+30h] [rbp+8h] BYREF

  SystemTimeAsFileTime = 0;
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  _InterlockedIncrement((volatile signed __int32 *)&this[1].dwHighDateTime);
  return CompareFileTime(&SystemTimeAsFileTime, this + 5) < 0;
}

```

## disassembly

```asm
0x180078ca0  push    rbx
0x180078ca2  sub     rsp, 20h
0x180078ca6  mov     rbx, rcx
0x180078ca9  mov     qword ptr [rsp+28h+SystemTimeAsFileTime.dwLowDateTime], 0
0x180078cb2  lea     rcx, [rsp+28h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180078cb7  call    cs:__imp_GetSystemTimeAsFileTime
0x180078cbd  lock inc dword ptr [rbx+0Ch]
0x180078cc1  lea     rdx, [rbx+28h]; lpFileTime2
0x180078cc5  lea     rcx, [rsp+28h+SystemTimeAsFileTime]; lpFileTime1
0x180078cca  call    cs:__imp_CompareFileTime
0x180078cd0  test    eax, eax
0x180078cd2  sets    al
0x180078cd5  add     rsp, 20h
0x180078cd9  pop     rbx
0x180078cda  retn
```
