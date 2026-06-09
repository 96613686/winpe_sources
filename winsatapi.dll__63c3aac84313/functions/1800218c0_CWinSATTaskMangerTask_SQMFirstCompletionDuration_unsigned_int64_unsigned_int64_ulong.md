# CWinSATTaskMangerTask::SQMFirstCompletionDuration(unsigned __int64,unsigned __int64,ulong &)

- ea: `0x1800218c0`
- end: `0x1800218fb`
- name: `?SQMFirstCompletionDuration@CWinSATTaskMangerTask@@AEAAX_K0AEAK@Z`
- size: `59`
- prototype: `void __fastcall(CWinSATTaskMangerTask *__hidden this, unsigned __int64, unsigned __int64, unsigned int *)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180021294`
- `0x1800213d0`

## callees

- `0x18001c21c`
- `0x1800218c0`

## string_xrefs

- `0x1800218d1`: `base\winsat\api-dll\winsattaskmangertasksqm.cpp`
- `0x1800218c5`: `First idle run time is is greater than first sucesfully completion time`
- `0x1800218e9`: `Completion to first run time difference is greater than 32 bits can hold`

## pseudocode

```c
void __fastcall CWinSATTaskMangerTask::SQMFirstCompletionDuration(
        CWinSATTaskMangerTask *this,
        unsigned __int64 a2,
        unsigned __int64 a3,
        unsigned int *a4)
{
  unsigned __int64 v4; // r8

  if ( a2 < a3 )
  {
    v4 = a3 - a2;
    if ( v4 <= 0xFFFF )
      *a4 = v4;
    else
      Record_InternalError_w(
        "base\\winsat\\api-dll\\winsattaskmangertasksqm.cpp",
        154,
        L"Completion to first run time difference is greater than 32 bits can hold",
        a4);
  }
  else
  {
    Record_InternalError_w(
      "base\\winsat\\api-dll\\winsattaskmangertasksqm.cpp",
      141,
      L"First idle run time is is greater than first sucesfully completion time",
      a4);
  }
}

```

## disassembly

```asm
0x1800218c0  cmp     rdx, r8
0x1800218c3  jb      short loc_1800218DD
0x1800218c5  lea     r8, aFirstIdleRunTi; "First idle run time is is greater than "...
0x1800218cc  mov     edx, 8Dh
0x1800218d1  lea     rcx, aBaseWinsatApiD_2; "base\\winsat\\api-dll\\winsattaskmanger"...
0x1800218d8  jmp     Record_InternalError_w
0x1800218dd  sub     r8, rdx
0x1800218e0  cmp     r8, 0FFFFh
0x1800218e7  jbe     short loc_1800218F7
0x1800218e9  lea     r8, aCompletionToFi; "Completion to first run time difference"...
0x1800218f0  mov     edx, 9Ah
0x1800218f5  jmp     short loc_1800218D1
0x1800218f7  mov     [r9], r8d
0x1800218fa  retn
```
