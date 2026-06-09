# CSsdpService::HrStartTimer(void)

- ea: `0x1800177a0`
- end: `0x180017844`
- name: `?HrStartTimer@CSsdpService@@QEAAJXZ`
- size: `164`
- prototype: `__int64 __fastcall(PVOID Parameter)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x180018590`

## callees

- `0x180016620`
- `0x1800177a0`
- `0x1800271fc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180017825`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180017825`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800177be`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800177be`

## pseudocode

```c
__int64 __fastcall CSsdpService::HrStartTimer(char *Parameter)
{
  struct _RTL_CRITICAL_SECTION *v1; // rsi
  int v3; // ebx

  v1 = (struct _RTL_CRITICAL_SECTION *)(Parameter + 224);
  v3 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)(Parameter + 224));
  if ( (Parameter[264] & 2) != 0 || (v3 = CTimerBase::HrSetTimer(Parameter, 0), v3 >= 0) )
    **((_QWORD **)Parameter + 34) = Parameter;
  if ( v3 && WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 1) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_71fcbfaa684a35e38cde20de91eb05b5_Traceguids, (unsigned int)v3);
  LeaveCriticalSection(v1);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1800177a0  mov     [rsp+arg_0], rbx
0x1800177a5  mov     [rsp+arg_8], rsi
0x1800177aa  push    rdi
0x1800177ab  sub     rsp, 20h
0x1800177af  lea     rsi, [rcx+0E0h]
0x1800177b6  mov     rdi, rcx
0x1800177b9  mov     rcx, rsi; lpCriticalSection
0x1800177bc  xor     ebx, ebx
0x1800177be  call    cs:__imp_EnterCriticalSection
0x1800177c5  nop     dword ptr [rax+rax+00h]
0x1800177ca  test    byte ptr [rdi+108h], 2
0x1800177d1  jnz     short loc_1800177E3
0x1800177d3  xor     edx, edx; DueTime
0x1800177d5  mov     rcx, rdi; Parameter
0x1800177d8  call    ?HrSetTimer@CTimerBase@@QEAAJK@Z; CTimerBase::HrSetTimer(ulong)
0x1800177dd  mov     ebx, eax
0x1800177df  test    eax, eax
0x1800177e1  js      short loc_1800177ED
0x1800177e3  mov     rcx, [rdi+110h]
0x1800177ea  mov     [rcx], rdi
0x1800177ed  test    ebx, ebx
0x1800177ef  jz      short loc_180017822
0x1800177f1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800177f8  lea     rax, WPP_GLOBAL_Control
0x1800177ff  cmp     rcx, rax
0x180017802  jz      short loc_180017822
0x180017804  test    byte ptr [rcx+1Ch], 1
0x180017808  jz      short loc_180017822
0x18001780a  mov     rcx, [rcx+10h]
0x18001780e  lea     r8, WPP_71fcbfaa684a35e38cde20de91eb05b5_Traceguids
0x180017815  mov     edx, 12h
0x18001781a  mov     r9d, ebx
0x18001781d  call    WPP_SF_d
0x180017822  mov     rcx, rsi; lpCriticalSection
0x180017825  call    cs:__imp_LeaveCriticalSection
0x18001782c  nop     dword ptr [rax+rax+00h]
0x180017831  mov     rsi, [rsp+28h+arg_8]
0x180017836  mov     eax, ebx
0x180017838  mov     rbx, [rsp+28h+arg_0]
0x18001783d  add     rsp, 20h
0x180017841  pop     rdi
0x180017842  retn
```
