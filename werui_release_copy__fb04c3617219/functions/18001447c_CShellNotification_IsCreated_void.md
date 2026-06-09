# CShellNotification::IsCreated(void)

- ea: `0x18001447c`
- end: `0x1800144ad`
- name: `?IsCreated@CShellNotification@@QEAAHXZ`
- size: `49`
- prototype: `__int64 __fastcall(CShellNotification *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180010234`
- `0x180014674`
- `0x180014740`

## callees

- `0x180013ef0`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x18001448e`
- `KERNEL32!EnterCriticalSection` at `0x18001448e`

## pseudocode

```c
__int64 __fastcall CShellNotification::IsCreated(CShellNotification *this)
{
  CShellNotification *v1; // rbx
  char *v3; // [rsp+20h] [rbp-18h] BYREF
  char v4; // [rsp+28h] [rbp-10h]

  v1 = this;
  v3 = (char *)this + 24;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  LODWORD(v1) = *(_DWORD *)v1;
  v4 = 1;
  utl::unique_lock<utl::recursive_mutex>::~unique_lock<utl::recursive_mutex>(&v3);
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x18001447c  push    rbx
0x18001447e  sub     rsp, 30h
0x180014482  mov     rbx, rcx
0x180014485  add     rcx, 18h; lpCriticalSection
0x180014489  mov     [rsp+38h+var_18], rcx
0x18001448e  call    cs:__imp_EnterCriticalSection
0x180014494  mov     ebx, [rbx]
0x180014496  lea     rcx, [rsp+38h+var_18]
0x18001449b  mov     [rsp+38h+var_10], 1
0x1800144a0  call    ??1?$unique_lock@Vrecursive_mutex@utl@@@utl@@QEAA@XZ; utl::unique_lock<utl::recursive_mutex>::~unique_lock<utl::recursive_mutex>(void)
0x1800144a5  mov     eax, ebx
0x1800144a7  add     rsp, 30h
0x1800144ab  pop     rbx
0x1800144ac  retn
```
