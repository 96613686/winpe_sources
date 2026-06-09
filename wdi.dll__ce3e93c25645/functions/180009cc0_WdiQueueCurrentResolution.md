# WdiQueueCurrentResolution

- ea: `0x180009cc0`
- end: `0x180009d9d`
- name: `WdiQueueCurrentResolution`
- size: `221`
- prototype: `__int64 __fastcall(__int64, int, FILETIME)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180002ba0`
- `0x180009cc0`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180009d5c`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180009d5c`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180009d4c`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180009d4c`

## pseudocode

```c
__int64 __fastcall WdiQueueCurrentResolution(__int64 a1, int a2, FILETIME a3)
{
  unsigned int v3; // ebx
  int v5; // r8d
  __int64 v6; // rcx
  struct _FILETIME SystemTimeAsFileTime; // [rsp+40h] [rbp+8h] BYREF
  FILETIME FileTime1; // [rsp+50h] [rbp+18h] BYREF

  FileTime1 = a3;
  v3 = 0;
  SystemTimeAsFileTime = 0;
  if ( a1 )
  {
    v6 = *(_QWORD *)(a1 + 40);
    if ( v6 )
    {
      if ( (unsigned int)(*(_DWORD *)(a1 + 16) - 1) <= 1 || *(_DWORD *)(v6 + 44) != 8 || (*(_BYTE *)(v6 + 120) & 2) == 0 )
        return (unsigned int)-2147020579;
      if ( a2 )
      {
        if ( a2 != 32 )
          return (unsigned int)-2147024809;
        GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
        if ( CompareFileTime(&FileTime1, &SystemTimeAsFileTime) <= 0 )
          return (unsigned int)-2147024809;
        *(FILETIME *)(*(_QWORD *)(a1 + 40) + 148LL) = FileTime1;
        *(_DWORD *)(*(_QWORD *)(a1 + 40) + 144LL) |= 0x20u;
      }
      *(_DWORD *)(*(_QWORD *)(a1 + 40) + 120LL) |= 4u;
      return v3;
    }
    v5 = 1319;
  }
  else
  {
    v5 = 1318;
  }
  v3 = -2147024809;
  WdipTraceError(
    (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\library\\library.cpp",
    (int)L"WdiQueueCurrentResolution",
    v5,
    (int)L"Error = %d",
    87);
  return v3;
}

```

## disassembly

```asm
0x180009cc0  mov     [rsp+arg_8], rbx
0x180009cc5  mov     qword ptr [rsp+FileTime1.dwLowDateTime], r8
0x180009cca  push    rdi
0x180009ccb  sub     rsp, 30h
0x180009ccf  xor     ebx, ebx
0x180009cd1  mov     rdi, rcx
0x180009cd4  mov     qword ptr [rsp+38h+SystemTimeAsFileTime.dwLowDateTime], rbx
0x180009cd9  test    rcx, rcx
0x180009cdc  jnz     short loc_180009D10
0x180009cde  mov     r8d, 526h; int
0x180009ce4  lea     r9, aErrorD_0; "Error = %d"
0x180009ceb  mov     dword ptr [rsp+38h+Args], 57h ; 'W'; Args
0x180009cf3  lea     rdx, aWdiqueuecurren_0; "WdiQueueCurrentResolution"
0x180009cfa  mov     ebx, 80070057h
0x180009cff  lea     rcx, aClientcoreBase_6; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x180009d06  call    WdipTraceError
0x180009d0b  jmp     loc_180009D90
0x180009d10  mov     rcx, [rcx+28h]
0x180009d14  test    rcx, rcx
0x180009d17  jnz     short loc_180009D21
0x180009d19  mov     r8d, 527h
0x180009d1f  jmp     short loc_180009CE4
0x180009d21  mov     eax, [rdi+10h]
0x180009d24  dec     eax
0x180009d26  cmp     eax, 1
0x180009d29  jbe     short loc_180009D8B
0x180009d2b  cmp     dword ptr [rcx+2Ch], 8
0x180009d2f  jnz     short loc_180009D8B
0x180009d31  test    byte ptr [rcx+78h], 2
0x180009d35  jz      short loc_180009D8B
0x180009d37  test    edx, edx
0x180009d39  jz      short loc_180009D81
0x180009d3b  cmp     edx, 20h ; ' '
0x180009d3e  jz      short loc_180009D47
0x180009d40  mov     ebx, 80070057h
0x180009d45  jmp     short loc_180009D90
0x180009d47  lea     rcx, [rsp+38h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180009d4c  call    cs:__imp_GetSystemTimeAsFileTime
0x180009d52  lea     rdx, [rsp+38h+SystemTimeAsFileTime]; lpFileTime2
0x180009d57  lea     rcx, [rsp+38h+FileTime1]; lpFileTime1
0x180009d5c  call    cs:__imp_CompareFileTime
0x180009d62  test    eax, eax
0x180009d64  jle     short loc_180009D40
0x180009d66  mov     rax, qword ptr [rsp+38h+FileTime1.dwLowDateTime]
0x180009d6b  mov     rcx, [rdi+28h]
0x180009d6f  mov     [rcx+94h], rax
0x180009d76  mov     rax, [rdi+28h]
0x180009d7a  or      dword ptr [rax+90h], 20h
0x180009d81  mov     rax, [rdi+28h]
0x180009d85  or      dword ptr [rax+78h], 4
0x180009d89  jmp     short loc_180009D90
0x180009d8b  mov     ebx, 800710DDh
0x180009d90  mov     eax, ebx
0x180009d92  mov     rbx, [rsp+38h+arg_8]
0x180009d97  add     rsp, 30h
0x180009d9b  pop     rdi
0x180009d9c  retn
```
