# LargeCritSec::LargeCritSec(void)

- ea: `0x180010a30`
- end: `0x180010acf`
- name: `??0LargeCritSec@@QEAA@XZ`
- size: `159`
- prototype: `LargeCritSec *__fastcall(LargeCritSec *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180011ce0`

## callees

- `0x180005094`
- `0x180008c4c`
- `0x180010a30`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x180010a50`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x180010a50`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010a6f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010a6f`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
LargeCritSec *__fastcall LargeCritSec::LargeCritSec(LargeCritSec *this)
{
  HANDLE MutexW; // rbx
  void **pExceptionObject; // [rsp+20h] [rbp-48h] BYREF
  char v5; // [rsp+28h] [rbp-40h]
  char *v6; // [rsp+30h] [rbp-38h]
  __int64 v7; // [rsp+38h] [rbp-30h]
  __int64 v8; // [rsp+40h] [rbp-28h]
  DWORD LastError; // [rsp+48h] [rbp-20h]
  __int64 v10; // [rsp+4Ch] [rbp-1Ch]

  *(_QWORD *)this = 0;
  MutexW = CreateMutexW(0, 0, 0);
  wmi::AutoHandle::Close(this);
  *(_QWORD *)this = MutexW;
  if ( !MutexW )
  {
    v5 = 0;
    pExceptionObject = &wmi::GenericException::`vftable';
    v6 = byte_180052608;
    v7 = 0;
    v8 = 0;
    LastError = GetLastError();
    v10 = -1;
    throw (wmi::GenericException *)&pExceptionObject;
  }
  return this;
}

```

## disassembly

```asm
0x180010a30  mov     [rsp+arg_8], rbx
0x180010a35  mov     [rsp+arg_0], rcx
0x180010a3a  push    rdi
0x180010a3b  sub     rsp, 60h
0x180010a3f  mov     rdi, rcx
0x180010a42  mov     qword ptr [rcx], 0
0x180010a49  xor     r8d, r8d; lpName
0x180010a4c  xor     edx, edx; bInitialOwner
0x180010a4e  xor     ecx, ecx; lpMutexAttributes
0x180010a50  call    cs:__imp_CreateMutexW
0x180010a57  nop     dword ptr [rax+rax+00h]
0x180010a5c  mov     rbx, rax
0x180010a5f  mov     rcx, rdi; this
0x180010a62  call    ?Close@AutoHandle@wmi@@QEAAXXZ; wmi::AutoHandle::Close(void)
0x180010a67  mov     [rdi], rbx
0x180010a6a  test    rbx, rbx
0x180010a6d  jnz     short loc_180010AC0
0x180010a6f  call    cs:__imp_GetLastError
0x180010a76  nop     dword ptr [rax+rax+00h]
0x180010a7b  mov     [rsp+68h+var_40], bl
0x180010a7f  lea     rcx, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x180010a86  mov     [rsp+68h+pExceptionObject], rcx
0x180010a8b  lea     rcx, byte_180052608
0x180010a92  mov     [rsp+68h+var_38], rcx
0x180010a97  mov     [rsp+68h+var_30], rbx
0x180010a9c  mov     [rsp+68h+var_28], rbx
0x180010aa1  mov     [rsp+68h+var_20], eax
0x180010aa5  mov     [rsp+68h+var_1C], 0FFFFFFFFFFFFFFFFh
0x180010aae  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x180010ab5  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x180010aba  call    _CxxThrowException_0
0x180010ac0  mov     rax, rdi
0x180010ac3  mov     rbx, [rsp+68h+arg_8]
0x180010ac8  add     rsp, 60h
0x180010acc  pop     rdi
0x180010acd  retn
```
