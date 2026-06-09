# WdsDiagEnableModule(_WDS_DIAG_MODULE_ID)

- ea: `0x180001180`
- end: `0x1800011d5`
- name: `?WdsDiagEnableModule@@YAKW4_WDS_DIAG_MODULE_ID@@@Z`
- size: `85`
- prototype: `__int64 __fastcall(int)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180001180`
- `0x180001338`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x18000119b`
- `KERNEL32!EnterCriticalSection` at `0x18000119b`

## pseudocode

```c
__int64 __fastcall WdsDiagEnableModule(int a1)
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
    *((_DWORD *)&g_Modules + v1) = 1;
  CAutoTypeLock<CCriticalSection>::~CAutoTypeLock<CCriticalSection>(&v4);
  return v2;
}

```

## disassembly

```asm
0x180001180  mov     [rsp+arg_0], rbx
0x180001185  push    rdi
0x180001186  sub     rsp, 30h
0x18000118a  movsxd  rdi, ecx
0x18000118d  xor     ebx, ebx
0x18000118f  lea     rcx, ?g_CSModules@@3VCCriticalSection@@A; lpCriticalSection
0x180001196  mov     [rsp+38h+var_18], rcx
0x18000119b  call    cs:__imp_EnterCriticalSection
0x1800011a1  lea     edx, [rbx+1]
0x1800011a4  mov     [rsp+38h+var_10], edx
0x1800011a8  cmp     edi, 4
0x1800011ab  ja      short loc_1800011B9
0x1800011ad  lea     rcx, ?g_Modules@@3PAHA; int near * g_Modules
0x1800011b4  mov     [rcx+rdi*4], edx
0x1800011b7  jmp     short loc_1800011BE
0x1800011b9  mov     ebx, 57h ; 'W'
0x1800011be  lea     rcx, [rsp+38h+var_18]
0x1800011c3  call    ??1?$CAutoTypeLock@VCCriticalSection@@@@QEAA@XZ; CAutoTypeLock<CCriticalSection>::~CAutoTypeLock<CCriticalSection>(void)
0x1800011c8  mov     eax, ebx
0x1800011ca  mov     rbx, [rsp+38h+arg_0]
0x1800011cf  add     rsp, 30h
0x1800011d3  pop     rdi
0x1800011d4  retn
```
