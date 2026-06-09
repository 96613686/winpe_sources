# RtmCreateBestRouteEnum

- ea: `0x1800058a0`
- end: `0x1800059f9`
- name: `RtmCreateBestRouteEnum`
- size: `345`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1800058a0`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x18000594c`
- `KERNEL32!HeapAlloc` at `0x18000594c`
- `KERNEL32!GetProcessHeap` at `0x180005938`
- `KERNEL32!GetProcessHeap` at `0x1800059b1`
- `KERNEL32!GetProcessHeap` at `0x180005938`
- `KERNEL32!GetProcessHeap` at `0x1800059b1`
- `KERNEL32!HeapFree` at `0x1800059c1`
- `KERNEL32!HeapFree` at `0x1800059c1`
- `KERNEL32!InitializeCriticalSection` at `0x18000597a`
- `KERNEL32!InitializeCriticalSection` at `0x18000597a`
- `KERNEL32!DeleteCriticalSection` at `0x1800059ab`
- `KERNEL32!DeleteCriticalSection` at `0x1800059ab`

## pseudocode

```c
__int64 __fastcall RtmCreateBestRouteEnum(__int64 a1, __int64 a2, LONG a3, __int64 *a4)
{
  volatile signed __int32 *v6; // rsi
  volatile signed __int32 *v7; // rdi
  HANDLE ProcessHeap; // rax
  struct _RTL_CRITICAL_SECTION *v10; // rax
  unsigned __int64 v11; // rbx

  v6 = (volatile signed __int32 *)(a1 ^ 0x7754DF32);
  if ( a1 == 0x7754DF32 || *(_DWORD *)((a1 ^ 0x7754DF32) + 0x30) == 1 )
    return 6;
  if ( !a2 )
    return 87;
  v7 = (volatile signed __int32 *)(a2 ^ 0x7754DF32);
  if ( a2 == 0x7754DF32 || *(_WORD *)((a2 ^ 0x7754DF32) + 0x6C) == 1 )
    return 6;
  if ( (a3 & 0xFFFFFFFD) != 0 && (a3 & 0xFFFFFFFE) != 0 )
    return 87;
  if ( (~*(_DWORD *)(*(_QWORD *)((a1 ^ 0x7754DF32) + 0x10) + 40LL) & a3) != 0 )
    return 50;
  ProcessHeap = GetProcessHeap();
  v10 = (struct _RTL_CRITICAL_SECTION *)HeapAlloc(ProcessHeap, 8u, 0x88u);
  v11 = (unsigned __int64)v10;
  if ( !v10 )
    return 8;
  BYTE4(v10->DebugInfo) = 8;
  v10->LockCount = a3;
  InitializeCriticalSection(v10 + 1);
  *(_QWORD *)(v11 + 104) = v7;
  _InterlockedAdd(v7, 1u);
  _InterlockedAdd(v6, 1u);
  *a4 = v11 ^ 0x7754DF32;
  return 0;
}

```

## disassembly

```asm
0x1800058a0  mov     [rsp+arg_8], rbx
0x1800058a5  mov     [rsp+arg_10], rsi
0x1800058aa  mov     [rsp+arg_18], r9
0x1800058af  push    rdi
0x1800058b0  push    r12
0x1800058b2  push    r13
0x1800058b4  push    r14
0x1800058b6  push    r15
0x1800058b8  sub     rsp, 30h
0x1800058bc  mov     r15, r9
0x1800058bf  mov     r14d, r8d
0x1800058c2  mov     rdi, rdx
0x1800058c5  mov     rsi, rcx
0x1800058c8  mov     r13d, 7754DF32h
0x1800058ce  xor     rsi, r13
0x1800058d1  jz      loc_1800059DC
0x1800058d7  mov     r12d, 1
0x1800058dd  cmp     [rsi+30h], r12d
0x1800058e1  jz      loc_1800059DC
0x1800058e7  test    rdx, rdx
0x1800058ea  jz      loc_1800059D5
0x1800058f0  xor     rdi, r13
0x1800058f3  jz      loc_1800059DC
0x1800058f9  cmp     [rdi+6Ch], r12w
0x1800058fe  jz      loc_1800059DC
0x180005904  test    r8d, 0FFFFFFFDh
0x18000590b  setnz   cl
0x18000590e  test    r8d, 0FFFFFFFEh
0x180005915  setnz   al
0x180005918  test    al, cl
0x18000591a  jnz     loc_1800059D5
0x180005920  mov     rax, [rsi+10h]
0x180005924  mov     ecx, [rax+28h]
0x180005927  not     ecx
0x180005929  test    r8d, ecx
0x18000592c  jz      short loc_180005938
0x18000592e  lea     eax, [r12+31h]
0x180005933  jmp     loc_1800059E1
0x180005938  call    cs:__imp_GetProcessHeap
0x18000593e  mov     rcx, rax; hHeap
0x180005941  mov     edx, 8; dwFlags
0x180005946  mov     r8d, 88h; dwBytes
0x18000594c  call    cs:__imp_HeapAlloc
0x180005952  mov     rbx, rax
0x180005955  mov     [rsp+58h+lpMem], rax
0x18000595a  test    rax, rax
0x18000595d  jnz     short loc_180005966
0x18000595f  mov     eax, 8
0x180005964  jmp     short loc_1800059E1
0x180005966  mov     [rsp+58h+var_38], 0
0x18000596e  mov     byte ptr [rax+4], 8
0x180005972  mov     [rax+8], r14d
0x180005976  lea     rcx, [rax+28h]; lpCriticalSection
0x18000597a  call    cs:__imp_InitializeCriticalSection
0x180005980  mov     [rsp+58h+var_38], r12d
0x180005985  mov     [rbx+68h], rdi
0x180005989  lock add [rdi], r12d
0x18000598d  lock add [rsi], r12d
0x180005991  xor     rbx, r13
0x180005994  mov     [r15], rbx
0x180005997  xor     eax, eax
0x180005999  jmp     short loc_1800059E1
0x18000599b  cmp     [rsp+58h+var_38], 0
0x1800059a0  jz      short loc_1800059B1
0x1800059a2  mov     rcx, [rsp+58h+lpMem]
0x1800059a7  add     rcx, 28h ; '('; lpCriticalSection
0x1800059ab  call    cs:__imp_DeleteCriticalSection
0x1800059b1  call    cs:__imp_GetProcessHeap
0x1800059b7  mov     rcx, rax; hHeap
0x1800059ba  mov     r8, [rsp+58h+lpMem]; lpMem
0x1800059bf  xor     edx, edx; dwFlags
0x1800059c1  call    cs:__imp_HeapFree
0x1800059c7  mov     rax, [rsp+58h+arg_18]
0x1800059cc  mov     qword ptr [rax], 0
0x1800059d3  jmp     short loc_18000595F
0x1800059d5  mov     eax, 57h ; 'W'
0x1800059da  jmp     short loc_1800059E1
0x1800059dc  mov     eax, 6
0x1800059e1  mov     rbx, [rsp+58h+arg_8]
0x1800059e6  mov     rsi, [rsp+58h+arg_10]
0x1800059eb  add     rsp, 30h
0x1800059ef  pop     r15
0x1800059f1  pop     r14
0x1800059f3  pop     r13
0x1800059f5  pop     r12
0x1800059f7  pop     rdi
0x1800059f8  retn
```
