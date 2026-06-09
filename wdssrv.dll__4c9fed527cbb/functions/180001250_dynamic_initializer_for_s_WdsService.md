# _dynamic_initializer_for__s_WdsService__

- ea: `0x180001250`
- end: `0x18000138a`
- name: `_dynamic_initializer_for__s_WdsService__`
- size: `314`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180001a28`
- `0x18001336c`

## import_xrefs

- `KERNEL32!InitializeCriticalSection` at `0x180001269`
- `KERNEL32!InitializeCriticalSection` at `0x18000132c`
- `KERNEL32!InitializeCriticalSection` at `0x180001269`
- `KERNEL32!InitializeCriticalSection` at `0x18000132c`
- `KERNEL32!InitializeSListHead` at `0x18000128f`
- `KERNEL32!InitializeSListHead` at `0x18000128f`
- `KERNEL32!GetSystemInfo` at `0x1800012e7`
- `KERNEL32!GetSystemInfo` at `0x1800012e7`
- `WdsServerCommonLib!??0CCompPort@@QEAA@XZ` at `0x1800012bd`
- `WdsServerCommonLib!??0CCompPort@@QEAA@XZ` at `0x1800012bd`

## pseudocode

```c
int dynamic_initializer_for__s_WdsService__()
{
  int v0; // eax
  _SYSTEM_INFO SystemInfo; // [rsp+20h] [rbp-38h] BYREF

  CInterfaceHandler::CInterfaceHandler((CInterfaceHandler *)&qword_180028C00);
  InitializeCriticalSection(&stru_1800391D0);
  xmmword_1800391C0 = 0;
  dword_1800391F8 = 0;
  InitializeSListHead(&ListHead);
  dword_180039210 = 0;
  qword_180039230 = (__int64)&CWorkItemHandler::`vftable';
  qword_180039220 = 0;
  CCompPort::CCompPort((CCompPort *)qword_180039238);
  qword_180039290 = 0;
  memset(&SystemInfo, 0, sizeof(SystemInfo));
  GetSystemInfo(&SystemInfo);
  v0 = 1;
  qword_1800392B0 = 0;
  qword_1800392C0 = 0;
  if ( SystemInfo.dwNumberOfProcessors > 1 )
    v0 = 4;
  xmmword_1800392A0 = 0;
  dword_180039298 = v0;
  dword_1800392B8 = 0;
  InitializeCriticalSection(&stru_1800392C8);
  qword_180028BD0 = 0;
  qword_180028BE8 = 0;
  dword_180028BF0 = 0;
  xmmword_180028BD8 = 0;
  qword_180028BF8 = 0;
  qword_180039280 = 0;
  dword_180039288 = 0;
  qword_1800392F8 = 0;
  dword_1800392F0 = 0;
  return atexit((void (__cdecl *)())dynamic_atexit_destructor_for__s_WdsService__);
}

```

## disassembly

```asm
0x180001250  push    rbx
0x180001252  sub     rsp, 50h
0x180001256  lea     rcx, qword_180028C00; this
0x18000125d  call    ??0CInterfaceHandler@@QEAA@XZ; CInterfaceHandler::CInterfaceHandler(void)
0x180001262  lea     rcx, stru_1800391D0; lpCriticalSection
0x180001269  call    cs:__imp_InitializeCriticalSection
0x180001270  nop     dword ptr [rax+rax+00h]
0x180001275  xorps   xmm0, xmm0
0x180001278  lea     rcx, ListHead; ListHead
0x18000127f  xor     ebx, ebx
0x180001281  movdqa  cs:xmmword_1800391C0, xmm0
0x180001289  mov     cs:dword_1800391F8, ebx
0x18000128f  call    cs:__imp_InitializeSListHead
0x180001296  nop     dword ptr [rax+rax+00h]
0x18000129b  lea     rax, ??_7CWorkItemHandler@@6B@; const CWorkItemHandler::`vftable'
0x1800012a2  mov     cs:dword_180039210, ebx
0x1800012a8  lea     rcx, qword_180039238
0x1800012af  mov     cs:qword_180039230, rax
0x1800012b6  mov     cs:qword_180039220, rbx
0x1800012bd  call    cs:__imp_??0CCompPort@@QEAA@XZ; CCompPort::CCompPort(void)
0x1800012c4  nop     dword ptr [rax+rax+00h]
0x1800012c9  xorps   xmm0, xmm0
0x1800012cc  mov     cs:qword_180039290, rbx
0x1800012d3  lea     rcx, [rsp+58h+SystemInfo]; lpSystemInfo
0x1800012d8  movups  xmmword ptr [rsp+58h+SystemInfo], xmm0
0x1800012dd  movups  xmmword ptr [rsp+58h+SystemInfo.lpMaximumApplicationAddress], xmm0
0x1800012e2  movups  xmmword ptr [rsp+58h+SystemInfo.dwNumberOfProcessors], xmm0
0x1800012e7  call    cs:__imp_GetSystemInfo
0x1800012ee  nop     dword ptr [rax+rax+00h]
0x1800012f3  lea     eax, [rbx+1]
0x1800012f6  mov     cs:qword_1800392B0, rbx
0x1800012fd  cmp     [rsp+58h+SystemInfo.dwNumberOfProcessors], eax
0x180001301  lea     ecx, [rbx+4]
0x180001304  xorps   xmm0, xmm0
0x180001307  mov     cs:qword_1800392C0, rbx
0x18000130e  cmova   eax, ecx
0x180001311  movdqa  cs:xmmword_1800392A0, xmm0
0x180001319  lea     rcx, stru_1800392C8; lpCriticalSection
0x180001320  mov     cs:dword_180039298, eax
0x180001326  mov     cs:dword_1800392B8, ebx
0x18000132c  call    cs:__imp_InitializeCriticalSection
0x180001333  nop     dword ptr [rax+rax+00h]
0x180001338  xor     eax, eax
0x18000133a  mov     cs:qword_180028BD0, rbx
0x180001341  xorps   xmm0, xmm0
0x180001344  mov     cs:qword_180028BE8, rax
0x18000134b  lea     rcx, _dynamic_atexit_destructor_for__s_WdsService__
0x180001352  mov     cs:dword_180028BF0, eax
0x180001358  movups  cs:xmmword_180028BD8, xmm0
0x18000135f  mov     cs:qword_180028BF8, rbx
0x180001366  mov     cs:qword_180039280, rbx
0x18000136d  mov     cs:dword_180039288, ebx
0x180001373  mov     cs:qword_1800392F8, rbx
0x18000137a  mov     cs:dword_1800392F0, ebx
0x180001380  add     rsp, 50h
0x180001384  pop     rbx
0x180001385  jmp     atexit
```
