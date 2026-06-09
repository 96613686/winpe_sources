# CMulticastServer::FindNamespace(ulong)

- ea: `0x1800063e4`
- end: `0x180006480`
- name: `?FindNamespace@CMulticastServer@@AEAAPEAVCMulticastNamespace@@K@Z`
- size: `156`
- prototype: `struct CMulticastNamespace *__fastcall(CMulticastServer *__hidden this, unsigned int)`
- caller_count: `7`
- callee_count: `4`
- tags: ``

## callers

- `0x1800067f0`
- `0x180006f84`
- `0x1800071a0`
- `0x180007278`
- `0x180007358`
- `0x1800074bc`
- `0x180007668`

## callees

- `0x1800063e4`
- `0x180024c14`
- `0x180024ce0`
- `0x180026d70`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x180006431`
- `KERNEL32!LeaveCriticalSection` at `0x180006431`
- `KERNEL32!EnterCriticalSection` at `0x180006423`
- `KERNEL32!EnterCriticalSection` at `0x180006423`

## pseudocode

```c
struct CMulticastNamespace *__fastcall CMulticastServer::FindNamespace(struct _RTL_CRITICAL_SECTION *this, int a2)
{
  _QWORD *LockSemaphore; // rdi
  void (__fastcall ***v5)(_QWORD); // rbx
  _QWORD *v6; // rbp
  int v7; // r15d
  bool v8; // zf

  CMRSWLock::ReaderLock(this);
  LockSemaphore = this[20].LockSemaphore;
  v5 = 0;
  if ( LockSemaphore )
  {
    while ( 1 )
    {
      v6 = LockSemaphore;
      LockSemaphore = (_QWORD *)LockSemaphore[57];
      EnterCriticalSection((LPCRITICAL_SECTION)(v6 + 2));
      v7 = *((_DWORD *)v6 + 14);
      LeaveCriticalSection((LPCRITICAL_SECTION)(v6 + 2));
      v8 = v7 == a2;
      if ( v7 == a2 )
        break;
      if ( !LockSemaphore )
      {
        v8 = v7 == a2;
        break;
      }
    }
    if ( v8 )
      v5 = (void (__fastcall ***)(_QWORD))v6;
    if ( v5 )
      (**v5)(v5);
  }
  CMRSWLock::ReaderRelease(this);
  return (struct CMulticastNamespace *)v5;
}

```

## disassembly

```asm
0x1800063e4  mov     [rsp+arg_0], rbx
0x1800063e9  mov     [rsp+arg_8], rbp
0x1800063ee  mov     [rsp+arg_10], rsi
0x1800063f3  push    rdi
0x1800063f4  push    r14
0x1800063f6  push    r15
0x1800063f8  sub     rsp, 20h
0x1800063fc  mov     r14d, edx
0x1800063ff  mov     rsi, rcx
0x180006402  call    ?ReaderLock@CMRSWLock@@QEAAXXZ; CMRSWLock::ReaderLock(void)
0x180006407  mov     rdi, [rsi+338h]
0x18000640e  xor     ebx, ebx
0x180006410  test    rdi, rdi
0x180006413  jz      short loc_18000645C
0x180006415  mov     rbp, rdi
0x180006418  mov     rdi, [rdi+1C8h]
0x18000641f  lea     rcx, [rbp+10h]; lpCriticalSection
0x180006423  call    cs:__imp_EnterCriticalSection
0x180006429  mov     r15d, [rbp+38h]
0x18000642d  lea     rcx, [rbp+10h]; lpCriticalSection
0x180006431  call    cs:__imp_LeaveCriticalSection
0x180006437  cmp     r15d, r14d
0x18000643a  jz      short loc_180006444
0x18000643c  test    rdi, rdi
0x18000643f  jnz     short loc_180006415
0x180006441  cmp     r15d, r14d
0x180006444  cmovz   rbx, rbp
0x180006448  test    rbx, rbx
0x18000644b  jz      short loc_18000645C
0x18000644d  mov     rcx, [rbx]
0x180006450  mov     rax, [rcx]
0x180006453  mov     rcx, rbx
0x180006456  call    cs:__guard_dispatch_icall_fptr
0x18000645c  mov     rcx, rsi; this
0x18000645f  call    ?ReaderRelease@CMRSWLock@@QEAAXXZ; CMRSWLock::ReaderRelease(void)
0x180006464  mov     rbp, [rsp+38h+arg_8]
0x180006469  mov     rax, rbx
0x18000646c  mov     rbx, [rsp+38h+arg_0]
0x180006471  mov     rsi, [rsp+38h+arg_10]
0x180006476  add     rsp, 20h
0x18000647a  pop     r15
0x18000647c  pop     r14
0x18000647e  pop     rdi
0x18000647f  retn
```
