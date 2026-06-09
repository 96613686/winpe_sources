# OsEventsStartType

- ea: `0x1800976d4`
- end: `0x18009776b`
- name: `OsEventsStartType`
- size: `151`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180094248`

## callees

- `0x18003420c`
- `0x180092008`
- `0x1800976d4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180097702`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180097702`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x1800976e8`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x1800976e8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180097736`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180097736`

## string_xrefs

- `0x1800976da`: `Global\SC_AutoStartComplete`

## pseudocode

```c
__int64 OsEventsStartType()
{
  HANDLE v0; // rax
  unsigned int v1; // ebx
  DWORD LastError; // eax
  HANDLE v4; // [rsp+30h] [rbp+8h] BYREF

  v0 = OpenEventW(0x100000u, 0, L"Global\\SC_AutoStartComplete");
  v4 = v0;
  if ( (unsigned __int64)v0 + 1 <= 1 )
  {
    v1 = -1;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x4000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      LastError = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_2c2d62d8dcc43732bdae633c77dd2d8d_Traceguids, LastError);
    }
  }
  else
  {
    v1 = WaitForSingleObject(v0, 0) == 0;
  }
  tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&v4);
  return v1;
}

```

## disassembly

```asm
0x1800976d4  push    rbx
0x1800976d6  sub     rsp, 20h
0x1800976da  lea     r8, Name; "Global\\SC_AutoStartComplete"
0x1800976e1  xor     edx, edx; bInheritHandle
0x1800976e3  mov     ecx, 100000h; dwDesiredAccess
0x1800976e8  call    cs:__imp_OpenEventW
0x1800976ee  mov     [rsp+28h+arg_0], rax
0x1800976f3  lea     rcx, [rax+1]
0x1800976f7  cmp     rcx, 1
0x1800976fb  jbe     short loc_180097711
0x1800976fd  xor     edx, edx; dwMilliseconds
0x1800976ff  mov     rcx, rax; hHandle
0x180097702  call    cs:__imp_WaitForSingleObject
0x180097708  xor     ebx, ebx
0x18009770a  test    eax, eax
0x18009770c  setz    bl
0x18009770f  jmp     short loc_180097759
0x180097711  mov     rax, cs:WPP_GLOBAL_Control
0x180097718  lea     rcx, WPP_GLOBAL_Control
0x18009771f  or      ebx, 0FFFFFFFFh
0x180097722  cmp     rax, rcx
0x180097725  jz      short loc_180097759
0x180097727  test    dword ptr [rax+1Ch], 4000h
0x18009772e  jz      short loc_180097759
0x180097730  cmp     byte ptr [rax+19h], 2
0x180097734  jb      short loc_180097759
0x180097736  call    cs:__imp_GetLastError
0x18009773c  mov     rcx, cs:WPP_GLOBAL_Control
0x180097743  lea     edx, [rbx+12h]
0x180097746  mov     r9d, eax
0x180097749  lea     r8, WPP_2c2d62d8dcc43732bdae633c77dd2d8d_Traceguids
0x180097750  mov     rcx, [rcx+10h]
0x180097754  call    WPP_SF_d
0x180097759  lea     rcx, [rsp+28h+arg_0]
0x18009775e  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x180097763  mov     eax, ebx
0x180097765  add     rsp, 20h
0x180097769  pop     rbx
0x18009776a  retn
```
