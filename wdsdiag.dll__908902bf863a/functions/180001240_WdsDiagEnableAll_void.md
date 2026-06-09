# WdsDiagEnableAll(void)

- ea: `0x180001240`
- end: `0x18000128d`
- name: `?WdsDiagEnableAll@@YAKXZ`
- size: `77`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180001050`

## callees

- `0x180001338`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x180001250`
- `KERNEL32!EnterCriticalSection` at `0x180001250`

## pseudocode

```c
__int64 WdsDiagEnableAll(void)
{
  struct _RTL_CRITICAL_SECTION *v1; // [rsp+20h] [rbp-18h] BYREF
  int v2; // [rsp+28h] [rbp-10h]

  v1 = &g_CSModules;
  EnterCriticalSection(&g_CSModules);
  v2 = 1;
  g_Modules = (int near *)0x100000001LL;
  qword_180005628 = 0x100000001LL;
  dword_180005630 = 1;
  CAutoTypeLock<CCriticalSection>::~CAutoTypeLock<CCriticalSection>(&v1);
  return 0;
}

```

## disassembly

```asm
0x180001240  sub     rsp, 38h
0x180001244  lea     rcx, ?g_CSModules@@3VCCriticalSection@@A; lpCriticalSection
0x18000124b  mov     [rsp+38h+var_18], rcx
0x180001250  call    cs:__imp_EnterCriticalSection
0x180001256  mov     rax, 100000001h
0x180001260  mov     [rsp+38h+var_10], 1
0x180001268  lea     rcx, [rsp+38h+var_18]
0x18000126d  mov     cs:?g_Modules@@3PAHA, rax; int near * g_Modules
0x180001274  mov     cs:qword_180005628, rax
0x18000127b  mov     cs:dword_180005630, eax
0x180001281  call    ??1?$CAutoTypeLock@VCCriticalSection@@@@QEAA@XZ; CAutoTypeLock<CCriticalSection>::~CAutoTypeLock<CCriticalSection>(void)
0x180001286  xor     eax, eax
0x180001288  add     rsp, 38h
0x18000128c  retn
```
