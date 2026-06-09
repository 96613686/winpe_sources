# WdsDiagDisableModule(_WDS_DIAG_MODULE_ID)

- ea: `0x1800011e0`
- end: `0x180001236`
- name: `?WdsDiagDisableModule@@YAKW4_WDS_DIAG_MODULE_ID@@@Z`
- size: `86`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1800011e0`
- `0x180001338`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x1800011fb`
- `KERNEL32!EnterCriticalSection` at `0x1800011fb`

## pseudocode

```c
__int64 __fastcall WdsDiagDisableModule(int a1)
{
  __int64 v1; // rdi
  unsigned int v2; // ebx
  struct _RTL_CRITICAL_SECTION *v4; // [rsp+20h] [rbp-18h] BYREF
  int v5; // [rsp+28h] [rbp-10h]

  v1 = a1;
  v2 = 0;
  v4 = &g_CSModules;
  EnterCriticalSection(&g_CSModules);
  v5 = 1;
  if ( (unsigned int)v1 > 4 )
    v2 = 87;
  else
    *((_DWORD *)&g_Modules + v1) = 0;
  CAutoTypeLock<CCriticalSection>::~CAutoTypeLock<CCriticalSection>((__int64)&v4);
  return v2;
}

```

## disassembly

```asm
0x1800011e0  mov     [rsp+arg_0], rbx
0x1800011e5  push    rdi
0x1800011e6  sub     rsp, 30h
0x1800011ea  movsxd  rdi, ecx
0x1800011ed  xor     ebx, ebx
0x1800011ef  lea     rcx, ?g_CSModules@@3VCCriticalSection@@A; lpCriticalSection
0x1800011f6  mov     [rsp+38h+var_18], rcx
0x1800011fb  call    cs:__imp_EnterCriticalSection
0x180001201  mov     [rsp+38h+var_10], 1
0x180001209  cmp     edi, 4
0x18000120c  ja      short loc_18000121A
0x18000120e  lea     rcx, ?g_Modules@@3PAHA; int near * g_Modules
0x180001215  mov     [rcx+rdi*4], ebx
0x180001218  jmp     short loc_18000121F
0x18000121a  mov     ebx, 57h ; 'W'
0x18000121f  lea     rcx, [rsp+38h+var_18]
0x180001224  call    ??1?$CAutoTypeLock@VCCriticalSection@@@@QEAA@XZ; CAutoTypeLock<CCriticalSection>::~CAutoTypeLock<CCriticalSection>(void)
0x180001229  mov     eax, ebx
0x18000122b  mov     rbx, [rsp+38h+arg_0]
0x180001230  add     rsp, 30h
0x180001234  pop     rdi
0x180001235  retn
```
