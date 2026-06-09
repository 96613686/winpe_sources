# WdipRevertPagePriorityThread

- ea: `0x1800011d0`
- end: `0x18000132b`
- name: `WdipRevertPagePriorityThread`
- size: `347`
- prototype: `__int64 __fastcall(unsigned int)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180001010`
- `0x180003420`
- `0x1800042c0`
- `0x1800063d0`
- `0x1800068f0`

## callees

- `0x1800011d0`
- `0x180002ba0`

## import_xrefs

- `ntdll!NtSetInformationThread` at `0x18000124c`
- `ntdll!NtSetInformationThread` at `0x18000124c`
- `ntdll!RtlNtStatusToDosError` at `0x18000125c`
- `ntdll!RtlNtStatusToDosError` at `0x18000125c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180001233`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180001233`

## string_xrefs

- `0x180001289`: `WdipSetPagePriorityThread`
- `0x1800012da`: `WdipSetPagePriorityThread`
- `0x1800011f6`: `WdipRevertPagePriorityThread`
- `0x180001306`: `WdipRevertPagePriorityThread`

## pseudocode

```c
__int64 __fastcall WdipRevertPagePriorityThread(unsigned int a1)
{
  unsigned int v1; // edi
  HANDLE CurrentThread; // rax
  int v4; // eax
  signed int Args; // ebx
  signed int v6; // eax
  unsigned int ThreadInformation; // [rsp+40h] [rbp+8h] BYREF

  v1 = a1;
  if ( a1 < 8 )
  {
    while ( 1 )
    {
      ThreadInformation = 0;
      if ( v1 >= 8 )
      {
        WdipTraceError(
          (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\library\\mempri.cpp",
          (int)L"WdipSetPagePriorityThread",
          104,
          (int)L"Error = %d",
          87);
        Args = -2147024809;
        goto LABEL_16;
      }
      ThreadInformation = v1;
      CurrentThread = GetCurrentThread();
      v4 = NtSetInformationThread(CurrentThread, ThreadPagePriority, &ThreadInformation, 4u);
      if ( v4 < 0 )
      {
        v6 = RtlNtStatusToDosError(v4);
        Args = v6;
        if ( v6 > 0 )
          Args = (unsigned __int16)v6 | 0x80070000;
      }
      else
      {
        Args = 0;
      }
      if ( Args < 0 )
        WdipTraceError(
          (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\library\\mempri.cpp",
          (int)L"WdipSetPagePriorityThread",
          115,
          (int)L"Error = %d",
          Args);
      if ( Args != -2147024891 )
        break;
      if ( !--v1 )
        goto LABEL_16;
    }
    if ( Args >= 0 )
      return (unsigned int)Args;
LABEL_16:
    WdipTraceError(
      (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\library\\mempri.cpp",
      (int)L"WdipRevertPagePriorityThread",
      236,
      (int)L"Error = %d",
      Args);
    return (unsigned int)Args;
  }
  else
  {
    WdipTraceError(
      (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\library\\mempri.cpp",
      (int)L"WdipRevertPagePriorityThread",
      226,
      (int)L"Error = %d",
      87);
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x1800011d0  mov     [rsp+arg_10], rbx
0x1800011d5  push    rdi
0x1800011d6  sub     rsp, 30h
0x1800011da  mov     edi, ecx
0x1800011dc  cmp     ecx, 8
0x1800011df  jb      short loc_18000121B
0x1800011e1  lea     r9, aErrorD_0; "Error = %d"
0x1800011e8  mov     dword ptr [rsp+38h+Args], 57h ; 'W'; Args
0x1800011f0  mov     r8d, 0E2h; int
0x1800011f6  lea     rdx, aWdiprevertpage; "WdipRevertPagePriorityThread"
0x1800011fd  lea     rcx, aClientcoreBase_4; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x180001204  mov     ebx, 80070057h
0x180001209  call    WdipTraceError
0x18000120e  mov     eax, ebx
0x180001210  mov     rbx, [rsp+38h+arg_10]
0x180001215  add     rsp, 30h
0x180001219  pop     rdi
0x18000121a  retn
0x18000121b  mov     [rsp+38h+arg_8], rsi
0x180001220  xor     esi, esi
0x180001222  mov     [rsp+38h+ThreadInformation], esi
0x180001226  cmp     edi, 8
0x180001229  jnb     loc_1800012C5
0x18000122f  mov     [rsp+38h+ThreadInformation], edi
0x180001233  call    cs:__imp_GetCurrentThread
0x180001239  mov     r9d, 4; ThreadInformationLength
0x18000123f  lea     r8, [rsp+38h+ThreadInformation]; ThreadInformation
0x180001244  mov     rcx, rax; ThreadHandle
0x180001247  mov     edx, 18h; ThreadInformationClass
0x18000124c  call    cs:__imp_NtSetInformationThread
0x180001252  test    eax, eax
0x180001254  js      short loc_18000125A
0x180001256  mov     ebx, esi
0x180001258  jmp     short loc_180001271
0x18000125a  mov     ecx, eax; Status
0x18000125c  call    cs:__imp_RtlNtStatusToDosError
0x180001262  mov     ebx, eax
0x180001264  test    eax, eax
0x180001266  jle     short loc_180001271
0x180001268  movzx   ebx, ax
0x18000126b  or      ebx, 80070000h
0x180001271  test    ebx, ebx
0x180001273  jns     short loc_18000129C
0x180001275  movzx   eax, bx
0x180001278  lea     r9, aErrorD_0; "Error = %d"
0x18000127f  mov     r8d, 73h ; 's'; int
0x180001285  mov     dword ptr [rsp+38h+Args], eax; Args
0x180001289  lea     rdx, aWdipsetpagepri; "WdipSetPagePriorityThread"
0x180001290  lea     rcx, aClientcoreBase_4; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x180001297  call    WdipTraceError
0x18000129c  cmp     ebx, 80070005h
0x1800012a2  jnz     short loc_1800012AF
0x1800012a4  add     edi, 0FFFFFFFFh
0x1800012a7  jnz     loc_180001222
0x1800012ad  jmp     short loc_1800012F2
0x1800012af  test    ebx, ebx
0x1800012b1  js      short loc_1800012F2
0x1800012b3  mov     rsi, [rsp+38h+arg_8]
0x1800012b8  mov     eax, ebx
0x1800012ba  mov     rbx, [rsp+38h+arg_10]
0x1800012bf  add     rsp, 30h
0x1800012c3  pop     rdi
0x1800012c4  retn
0x1800012c5  lea     r9, aErrorD_0; "Error = %d"
0x1800012cc  mov     dword ptr [rsp+38h+Args], 57h ; 'W'; Args
0x1800012d4  mov     r8d, 68h ; 'h'; int
0x1800012da  lea     rdx, aWdipsetpagepri; "WdipSetPagePriorityThread"
0x1800012e1  lea     rcx, aClientcoreBase_4; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x1800012e8  call    WdipTraceError
0x1800012ed  mov     ebx, 80070057h
0x1800012f2  movzx   eax, bx
0x1800012f5  lea     r9, aErrorD_0; "Error = %d"
0x1800012fc  mov     r8d, 0ECh; int
0x180001302  mov     dword ptr [rsp+38h+Args], eax; Args
0x180001306  lea     rdx, aWdiprevertpage; "WdipRevertPagePriorityThread"
0x18000130d  lea     rcx, aClientcoreBase_4; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x180001314  call    WdipTraceError
0x180001319  mov     rsi, [rsp+38h+arg_8]
0x18000131e  mov     eax, ebx
0x180001320  mov     rbx, [rsp+38h+arg_10]
0x180001325  add     rsp, 30h
0x180001329  pop     rdi
0x18000132a  retn
```
