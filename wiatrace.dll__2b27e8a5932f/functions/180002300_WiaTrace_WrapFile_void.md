# WiaTrace::WrapFile(void *)

- ea: `0x180002300`
- end: `0x1800023dd`
- name: `?WrapFile@WiaTrace@@YAJPEAX@Z`
- size: `221`
- prototype: `__int64 __fastcall(HANDLE hFile, void *)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180001300`
- `0x180001fb0`

## callees

- `0x180002980`
- `0x1800031fa`

## import_xrefs

- `KERNEL32!SetFilePointerEx` at `0x1800023ab`
- `KERNEL32!SetFilePointerEx` at `0x1800023ab`
- `KERNEL32!CopyFileA` at `0x180002393`
- `KERNEL32!CopyFileA` at `0x180002393`
- `KERNEL32!SetEndOfFile` at `0x1800023b4`
- `KERNEL32!SetEndOfFile` at `0x1800023b4`
- `KERNEL32!ExpandEnvironmentStringsA` at `0x180002365`
- `KERNEL32!ExpandEnvironmentStringsA` at `0x18000237d`
- `KERNEL32!ExpandEnvironmentStringsA` at `0x180002365`
- `KERNEL32!ExpandEnvironmentStringsA` at `0x18000237d`

## pseudocode

```c
__int64 __fastcall WiaTrace::WrapFile(HANDLE hFile, void *a2)
{
  LARGE_INTEGER NewFilePointer; // [rsp+20h] [rbp-248h] BYREF
  CHAR NewFileName[272]; // [rsp+30h] [rbp-238h] BYREF
  CHAR Dst[272]; // [rsp+140h] [rbp-128h] BYREF

  memset_0(Dst, 0, 0x105u);
  memset_0(NewFileName, 0, 0x105u);
  ExpandEnvironmentStringsA("%systemroot%\\Debug\\WIA\\wiatrace.log", Dst, 0x105u);
  ExpandEnvironmentStringsA("%systemroot%\\Debug\\WIA\\wiatrace.bak.log", NewFileName, 0x105u);
  CopyFileA(Dst, NewFileName, 0);
  NewFilePointer.QuadPart = 0;
  SetFilePointerEx(hFile, 0, &NewFilePointer, 0);
  SetEndOfFile(hFile);
  return 0;
}

```

## disassembly

```asm
0x180002300  mov     [rsp+arg_8], rbx
0x180002305  push    rdi
0x180002306  sub     rsp, 260h
0x18000230d  mov     rax, cs:__security_cookie
0x180002314  xor     rax, rsp
0x180002317  mov     [rsp+268h+var_18], rax
0x18000231f  mov     rbx, rcx
0x180002322  xor     edx, edx; Val
0x180002324  lea     rcx, [rsp+268h+Dst]; void *
0x18000232c  mov     r8d, 105h; Size
0x180002332  call    memset_0
0x180002337  xor     edx, edx; Val
0x180002339  lea     rcx, [rsp+268h+NewFileName]; void *
0x18000233e  mov     r8d, 105h; Size
0x180002344  call    memset_0
0x180002349  xor     edi, edi
0x18000234b  lea     rdx, [rsp+268h+Dst]; lpDst
0x180002353  mov     r8d, 105h; nSize
0x180002359  mov     qword ptr [rsp+268h+NewFilePointer], rdi
0x18000235e  lea     rcx, aSystemrootDebu; "%systemroot%\\Debug\\WIA\\wiatrace.log"
0x180002365  call    cs:__imp_ExpandEnvironmentStringsA
0x18000236b  mov     r8d, 105h; nSize
0x180002371  lea     rdx, [rsp+268h+NewFileName]; lpDst
0x180002376  lea     rcx, Src; "%systemroot%\\Debug\\WIA\\wiatrace.bak."...
0x18000237d  call    cs:__imp_ExpandEnvironmentStringsA
0x180002383  xor     r8d, r8d; bFailIfExists
0x180002386  lea     rdx, [rsp+268h+NewFileName]; lpNewFileName
0x18000238b  lea     rcx, [rsp+268h+Dst]; lpExistingFileName
0x180002393  call    cs:__imp_CopyFileA
0x180002399  mov     edx, edi; liDistanceToMove
0x18000239b  lea     r8, [rsp+268h+NewFilePointer]; lpNewFilePointer
0x1800023a0  xor     r9d, r9d; dwMoveMethod
0x1800023a3  mov     qword ptr [rsp+268h+NewFilePointer], rdx
0x1800023a8  mov     rcx, rbx; hFile
0x1800023ab  call    cs:__imp_SetFilePointerEx
0x1800023b1  mov     rcx, rbx; hFile
0x1800023b4  call    cs:__imp_SetEndOfFile
0x1800023ba  xor     eax, eax
0x1800023bc  mov     rcx, [rsp+268h+var_18]
0x1800023c4  xor     rcx, rsp; StackCookie
0x1800023c7  call    __security_check_cookie
0x1800023cc  mov     rbx, [rsp+268h+arg_8]
0x1800023d4  add     rsp, 260h
0x1800023db  pop     rdi
0x1800023dc  retn
```
