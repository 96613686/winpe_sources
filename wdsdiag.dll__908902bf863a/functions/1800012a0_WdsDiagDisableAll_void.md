# WdsDiagDisableAll(void)

- ea: `0x1800012a0`
- end: `0x1800012e5`
- name: `?WdsDiagDisableAll@@YAKXZ`
- size: `69`
- prototype: `unsigned int(void)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180001338`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x1800012b0`
- `KERNEL32!EnterCriticalSection` at `0x1800012b0`

## pseudocode

```c
__int64 WdsDiagDisableAll(void)
{
  struct _RTL_CRITICAL_SECTION *v1; // [rsp+20h] [rbp-18h] BYREF
  int v2; // [rsp+28h] [rbp-10h]

  v1 = &g_CSModules;
  EnterCriticalSection(&g_CSModules);
  v2 = 1;
  g_Modules = 0;
  qword_180005628 = 0;
  dword_180005630 = 0;
  CAutoTypeLock<CCriticalSection>::~CAutoTypeLock<CCriticalSection>((__int64)&v1);
  return 0;
}

```

## disassembly

```asm
0x1800012a0  sub     rsp, 38h
0x1800012a4  lea     rcx, ?g_CSModules@@3VCCriticalSection@@A; lpCriticalSection
0x1800012ab  mov     [rsp+38h+var_18], rcx
0x1800012b0  call    cs:__imp_EnterCriticalSection
0x1800012b6  xor     eax, eax
0x1800012b8  mov     [rsp+38h+var_10], 1
0x1800012c0  lea     rcx, [rsp+38h+var_18]
0x1800012c5  mov     cs:?g_Modules@@3PAHA, rax; int near * g_Modules
0x1800012cc  mov     cs:qword_180005628, rax
0x1800012d3  mov     cs:dword_180005630, eax
0x1800012d9  call    ??1?$CAutoTypeLock@VCCriticalSection@@@@QEAA@XZ; CAutoTypeLock<CCriticalSection>::~CAutoTypeLock<CCriticalSection>(void)
0x1800012de  xor     eax, eax
0x1800012e0  add     rsp, 38h
0x1800012e4  retn
```
