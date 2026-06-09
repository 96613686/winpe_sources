# MarkCurrentThreadAsEcoQoS(void)

- ea: `0x180014bf4`
- end: `0x180014c48`
- name: `?MarkCurrentThreadAsEcoQoS@@YAXXZ`
- size: `84`
- prototype: `void(void)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180012434`
- `0x180014398`

## callees

- `0x1800032e0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180014c18`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180014c18`
- `api-ms-win-core-processthreads-l1-1-2!SetThreadInformation` at `0x180014c30`
- `api-ms-win-core-processthreads-l1-1-2!SetThreadInformation` at `0x180014c30`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void MarkCurrentThreadAsEcoQoS(void)
{
  HANDLE CurrentThread; // rax
  _DWORD v1[4]; // [rsp+20h] [rbp-28h] BYREF

  v1[0] = 1;
  v1[1] = 1;
  v1[2] = 1;
  CurrentThread = GetCurrentThread();
  SetThreadInformation(CurrentThread, 3, v1);
}

```

## disassembly

```asm
0x180014bf4  sub     rsp, 48h
0x180014bf8  mov     rax, cs:__security_cookie
0x180014bff  xor     rax, rsp
0x180014c02  mov     [rsp+48h+var_18], rax
0x180014c07  mov     eax, 1
0x180014c0c  mov     [rsp+48h+var_28], eax
0x180014c10  mov     [rsp+48h+var_24], eax
0x180014c14  mov     [rsp+48h+var_20], eax
0x180014c18  call    cs:__imp_GetCurrentThread
0x180014c1e  mov     r9d, 0Ch
0x180014c24  lea     r8, [rsp+48h+var_28]
0x180014c29  mov     rcx, rax
0x180014c2c  lea     edx, [r9-9]
0x180014c30  call    cs:__imp_SetThreadInformation
0x180014c36  mov     rcx, [rsp+48h+var_18]
0x180014c3b  xor     rcx, rsp; StackCookie
0x180014c3e  call    __security_check_cookie
0x180014c43  add     rsp, 48h
0x180014c47  retn
```
