# CreateProcThreadAttributeList(_SECURITY_CAPABILITIES *,_WIN32K_SYSCALL_FILTER *,_PROC_THREAD_ATTRIBUTE_LIST * *)

- ea: `0x1400426f0`
- end: `0x140042825`
- name: `?CreateProcThreadAttributeList@@YAJPEAU_SECURITY_CAPABILITIES@@PEAU_WIN32K_SYSCALL_FILTER@@PEAPEAU_PROC_THREAD_ATTRIBUTE_LIST@@@Z`
- size: `309`
- prototype: `__int64 __fastcall(PVOID lpValue, PVOID, struct _PROC_THREAD_ATTRIBUTE_LIST **)`
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140030590`

## callees

- `0x1400426f0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140042738`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400427e2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140042738`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400427e2`
- `api-ms-win-core-processthreads-l1-1-0!DeleteProcThreadAttributeList` at `0x140042802`
- `api-ms-win-core-processthreads-l1-1-0!DeleteProcThreadAttributeList` at `0x140042802`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x1400427a8`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x1400427d8`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x1400427a8`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x1400427d8`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x14004272a`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x14004277b`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x14004272a`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x14004277b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14004280b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14004280b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x140042752`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x140042752`

## pseudocode

```c
__int64 __fastcall CreateProcThreadAttributeList(PVOID lpValue, PVOID a2, struct _PROC_THREAD_ATTRIBUTE_LIST **a3)
{
  unsigned int v6; // ebx
  struct _PROC_THREAD_ATTRIBUTE_LIST *v7; // rdi
  BOOL v8; // esi
  struct _PROC_THREAD_ATTRIBUTE_LIST *v9; // rax
  BOOL v10; // esi
  signed int LastError; // eax
  SIZE_T uBytes; // [rsp+80h] [rbp+8h] BYREF

  uBytes = 0;
  v6 = 0;
  v7 = 0;
  v8 = lpValue != 0;
  if ( InitializeProcThreadAttributeList(0, v8 + 1, 0, &uBytes) || GetLastError() != 122 )
    goto LABEL_15;
  v9 = (struct _PROC_THREAD_ATTRIBUTE_LIST *)LocalAlloc(0x40u, uBytes);
  v7 = v9;
  if ( !v9 )
    return (unsigned int)-2147024882;
  v10 = InitializeProcThreadAttributeList(v9, v8 + 1, 0, &uBytes);
  if ( v10 )
  {
    if ( UpdateProcThreadAttribute(v7, 0, 0x20010u, a2, 8u, 0, 0)
      && (!lpValue || UpdateProcThreadAttribute(v7, 0, 0x20009u, lpValue, 0x18u, 0, 0)) )
    {
      goto LABEL_15;
    }
  }
  LastError = GetLastError();
  v6 = LastError;
  if ( LastError > 0 )
    v6 = (unsigned __int16)LastError | 0x80070000;
  if ( (v6 & 0x80000000) == 0 )
  {
LABEL_15:
    *a3 = v7;
    return v6;
  }
  if ( v10 )
    DeleteProcThreadAttributeList(v7);
  LocalFree(v7);
  return v6;
}

```

## disassembly

```asm
0x1400426f0  mov     r11, rsp
0x1400426f3  push    rbx
0x1400426f4  push    rbp
0x1400426f5  push    rsi
0x1400426f6  push    rdi
0x1400426f7  push    r14
0x1400426f9  push    r15
0x1400426fb  sub     rsp, 48h
0x1400426ff  mov     rax, rcx
0x140042702  mov     qword ptr [r11+8], 0
0x14004270a  mov     r15, r8
0x14004270d  lea     r9, [r11+8]; lpSize
0x140042711  mov     r14, rdx
0x140042714  mov     rbp, rcx
0x140042717  xor     ebx, ebx
0x140042719  xor     edi, edi
0x14004271b  neg     rax
0x14004271e  sbb     esi, esi
0x140042720  xor     r8d, r8d; dwFlags
0x140042723  neg     esi
0x140042725  xor     ecx, ecx; lpAttributeList
0x140042727  lea     edx, [rsi+1]; dwAttributeCount
0x14004272a  call    cs:__imp_InitializeProcThreadAttributeList
0x140042730  test    eax, eax
0x140042732  jnz     loc_140042813
0x140042738  call    cs:__imp_GetLastError
0x14004273e  cmp     eax, 7Ah ; 'z'
0x140042741  jnz     loc_140042813
0x140042747  mov     rdx, [rsp+78h+uBytes]; uBytes
0x14004274f  lea     ecx, [rbx+40h]; uFlags
0x140042752  call    cs:__imp_LocalAlloc
0x140042758  mov     rdi, rax
0x14004275b  test    rax, rax
0x14004275e  jnz     short loc_14004276A
0x140042760  mov     ebx, 8007000Eh
0x140042765  jmp     loc_140042816
0x14004276a  lea     r9, [rsp+78h+uBytes]; lpSize
0x140042772  xor     r8d, r8d; dwFlags
0x140042775  lea     edx, [rsi+1]; dwAttributeCount
0x140042778  mov     rcx, rdi; lpAttributeList
0x14004277b  call    cs:__imp_InitializeProcThreadAttributeList
0x140042781  mov     esi, eax
0x140042783  test    eax, eax
0x140042785  jz      short loc_1400427E2
0x140042787  mov     [rsp+78h+lpReturnSize], rbx; lpReturnSize
0x14004278c  mov     r9, r14; lpValue
0x14004278f  mov     [rsp+78h+lpPreviousValue], rbx; lpPreviousValue
0x140042794  xor     edx, edx; dwFlags
0x140042796  mov     r8d, 20010h; Attribute
0x14004279c  mov     [rsp+78h+cbSize], 8; cbSize
0x1400427a5  mov     rcx, rdi; lpAttributeList
0x1400427a8  call    cs:__imp_UpdateProcThreadAttribute
0x1400427ae  test    eax, eax
0x1400427b0  jz      short loc_1400427E2
0x1400427b2  test    rbp, rbp
0x1400427b5  jz      short loc_140042813
0x1400427b7  mov     [rsp+78h+lpReturnSize], rbx; lpReturnSize
0x1400427bc  mov     r9, rbp; lpValue
0x1400427bf  mov     [rsp+78h+lpPreviousValue], rbx; lpPreviousValue
0x1400427c4  xor     edx, edx; dwFlags
0x1400427c6  mov     r8d, 20009h; Attribute
0x1400427cc  mov     [rsp+78h+cbSize], 18h; cbSize
0x1400427d5  mov     rcx, rdi; lpAttributeList
0x1400427d8  call    cs:__imp_UpdateProcThreadAttribute
0x1400427de  test    eax, eax
0x1400427e0  jnz     short loc_140042813
0x1400427e2  call    cs:__imp_GetLastError
0x1400427e8  mov     ebx, eax
0x1400427ea  test    eax, eax
0x1400427ec  jle     short loc_1400427F7
0x1400427ee  movzx   ebx, ax
0x1400427f1  or      ebx, 80070000h
0x1400427f7  test    ebx, ebx
0x1400427f9  jns     short loc_140042813
0x1400427fb  test    esi, esi
0x1400427fd  jz      short loc_140042808
0x1400427ff  mov     rcx, rdi; lpAttributeList
0x140042802  call    cs:__imp_DeleteProcThreadAttributeList
0x140042808  mov     rcx, rdi; hMem
0x14004280b  call    cs:__imp_LocalFree
0x140042811  jmp     short loc_140042816
0x140042813  mov     [r15], rdi
0x140042816  mov     eax, ebx
0x140042818  add     rsp, 48h
0x14004281c  pop     r15
0x14004281e  pop     r14
0x140042820  pop     rdi
0x140042821  pop     rsi
0x140042822  pop     rbp
0x140042823  pop     rbx
0x140042824  retn
```
