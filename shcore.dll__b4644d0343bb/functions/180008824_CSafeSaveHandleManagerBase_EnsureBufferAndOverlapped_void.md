# CSafeSaveHandleManagerBase::_EnsureBufferAndOverlapped(void)

- ea: `0x180008824`
- end: `0x180008929`
- name: `?_EnsureBufferAndOverlapped@CSafeSaveHandleManagerBase@@AEAAJXZ`
- size: `261`
- prototype: `__int64 __fastcall(CSafeSaveHandleManagerBase *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180008930`

## callees

- `0x1800083d0`
- `0x180008824`
- `0x180023730`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180008840`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180008840`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x1800088c0`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x1800088c0`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000886f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000886f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000885d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000885d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000890e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000890e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800088ea`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008905`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800088ea`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008905`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CSafeSaveHandleManagerBase::_EnsureBufferAndOverlapped(RTL_SRWLOCK *this)
{
  RTL_SRWLOCK *v2; // r14
  PVOID Ptr; // rbx
  signed int v4; // esi
  void *v5; // rbx
  HANDLE Event; // rax
  void *v7; // rdi
  PVOID v8; // rcx
  void *v10; // [rsp+40h] [rbp+8h] BYREF

  v2 = this + 3;
  AcquireSRWLockShared(this + 3);
  Ptr = this[12].Ptr;
  v4 = Ptr == 0 ? 0x80004005 : 0;
  ReleaseSRWLockShared(v2);
  if ( !Ptr )
  {
    AcquireSRWLockExclusive(v2);
    if ( this[12].Ptr )
    {
      v4 = 0;
    }
    else
    {
      LODWORD(this[11].Ptr) = 0x10000;
      v5 = 0;
      v10 = 0;
      if ( is_mul_ok(0x10000u, 1u) )
      {
        v4 = CTCoAllocPolicy::Alloc((void *)0x10000, 1u, 0x10000u, &v10);
        if ( v4 < 0
          || (Event = CreateEventExW(0, 0, 1u, 0x1F0003u),
              this[10].Ptr = Event,
              v4 = ResultFromWin32Bool(Event != 0),
              v4 < 0) )
        {
          v5 = v10;
        }
        else
        {
          v7 = v10;
          v8 = this[12].Ptr;
          this[12].Ptr = 0;
          CoTaskMemFree(v8);
          this[12].Ptr = v7;
        }
      }
      else
      {
        v4 = -2147024362;
      }
      CoTaskMemFree(v5);
    }
    ReleaseSRWLockExclusive(v2);
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180008824  mov     [rsp+arg_10], rbx
0x180008829  mov     [rsp+arg_18], rbp
0x18000882e  push    rsi
0x18000882f  push    rdi
0x180008830  push    r14
0x180008832  sub     rsp, 20h
0x180008836  mov     rbp, rcx
0x180008839  lea     r14, [rcx+18h]
0x18000883d  mov     rcx, r14; SRWLock
0x180008840  call    cs:__imp_AcquireSRWLockShared
0x180008846  mov     rbx, [rbp+60h]
0x18000884a  mov     rax, rbx
0x18000884d  neg     rax
0x180008850  sbb     esi, esi
0x180008852  not     esi
0x180008854  and     esi, 80004005h
0x18000885a  mov     rcx, r14; SRWLock
0x18000885d  call    cs:__imp_ReleaseSRWLockShared
0x180008863  test    rbx, rbx
0x180008866  jnz     loc_180008914
0x18000886c  mov     rcx, r14; SRWLock
0x18000886f  call    cs:__imp_AcquireSRWLockExclusive
0x180008875  cmp     [rbp+60h], rbx
0x180008879  jz      short loc_180008882
0x18000887b  xor     esi, esi
0x18000887d  jmp     loc_18000890B
0x180008882  mov     ecx, 10000h; void *
0x180008887  mov     [rbp+58h], ecx
0x18000888a  xor     ebx, ebx
0x18000888c  mov     [rsp+38h+arg_0], rbx
0x180008891  lea     edi, [rbx+1]
0x180008894  mov     eax, edi
0x180008896  mul     rcx
0x180008899  test    rdx, rdx
0x18000889c  jnz     short loc_1800088FD
0x18000889e  lea     r9, [rsp+38h+arg_0]; void **
0x1800088a3  mov     r8, rax; unsigned __int64
0x1800088a6  mov     edx, edi; unsigned int
0x1800088a8  call    ?Alloc@CTCoAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTCoAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x1800088ad  mov     esi, eax
0x1800088af  test    eax, eax
0x1800088b1  js      short loc_1800088F6
0x1800088b3  mov     r9d, 1F0003h; dwDesiredAccess
0x1800088b9  mov     r8d, edi; dwFlags
0x1800088bc  xor     edx, edx; lpName
0x1800088be  xor     ecx, ecx; lpEventAttributes
0x1800088c0  call    cs:__imp_CreateEventExW
0x1800088c6  mov     [rbp+50h], rax
0x1800088ca  xor     ecx, ecx
0x1800088cc  test    rax, rax
0x1800088cf  setnz   cl; int
0x1800088d2  call    ?ResultFromWin32Bool@@YAJH@Z; ResultFromWin32Bool(int)
0x1800088d7  mov     esi, eax
0x1800088d9  test    eax, eax
0x1800088db  js      short loc_1800088F6
0x1800088dd  mov     rdi, [rsp+38h+arg_0]
0x1800088e2  mov     rcx, [rbp+60h]; pv
0x1800088e6  mov     [rbp+60h], rbx
0x1800088ea  call    cs:__imp_CoTaskMemFree
0x1800088f0  mov     [rbp+60h], rdi
0x1800088f4  jmp     short loc_180008902
0x1800088f6  mov     rbx, [rsp+38h+arg_0]
0x1800088fb  jmp     short loc_180008902
0x1800088fd  mov     esi, 80070216h
0x180008902  mov     rcx, rbx; pv
0x180008905  call    cs:__imp_CoTaskMemFree
0x18000890b  mov     rcx, r14; SRWLock
0x18000890e  call    cs:__imp_ReleaseSRWLockExclusive
0x180008914  mov     eax, esi
0x180008916  mov     rbx, [rsp+38h+arg_10]
0x18000891b  mov     rbp, [rsp+38h+arg_18]
0x180008920  add     rsp, 20h
0x180008924  pop     r14
0x180008926  pop     rdi
0x180008927  pop     rsi
0x180008928  retn
```
