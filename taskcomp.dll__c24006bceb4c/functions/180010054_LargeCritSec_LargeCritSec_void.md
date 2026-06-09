# LargeCritSec::LargeCritSec(void)

- ea: `0x180010054`
- end: `0x1800100e6`
- name: `??0LargeCritSec@@QEAA@XZ`
- size: `146`
- prototype: `LargeCritSec *__fastcall(LargeCritSec *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18001124c`

## callees

- `0x180004e1c`
- `0x18000878c`
- `0x180010054`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x180010074`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x180010074`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001008d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001008d`

## pseudocode

```c
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
    v6 = byte_1800505F8;
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
0x180010054  mov     [rsp+arg_8], rbx
0x180010059  mov     [rsp+arg_0], rcx
0x18001005e  push    rdi
0x18001005f  sub     rsp, 60h
0x180010063  mov     rdi, rcx
0x180010066  mov     qword ptr [rcx], 0
0x18001006d  xor     r8d, r8d; lpName
0x180010070  xor     edx, edx; bInitialOwner
0x180010072  xor     ecx, ecx; lpMutexAttributes
0x180010074  call    cs:__imp_CreateMutexW
0x18001007a  mov     rbx, rax
0x18001007d  mov     rcx, rdi; this
0x180010080  call    ?Close@AutoHandle@wmi@@QEAAXXZ; wmi::AutoHandle::Close(void)
0x180010085  mov     [rdi], rbx
0x180010088  test    rbx, rbx
0x18001008b  jnz     short loc_1800100D8
0x18001008d  call    cs:__imp_GetLastError
0x180010093  mov     [rsp+68h+var_40], bl
0x180010097  lea     rcx, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x18001009e  mov     [rsp+68h+pExceptionObject], rcx
0x1800100a3  lea     rcx, byte_1800505F8
0x1800100aa  mov     [rsp+68h+var_38], rcx
0x1800100af  mov     [rsp+68h+var_30], rbx
0x1800100b4  mov     [rsp+68h+var_28], rbx
0x1800100b9  mov     [rsp+68h+var_20], eax
0x1800100bd  mov     [rsp+68h+var_1C], 0FFFFFFFFFFFFFFFFh
0x1800100c6  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x1800100cd  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x1800100d2  call    _CxxThrowException_0
0x1800100d8  mov     rax, rdi
0x1800100db  mov     rbx, [rsp+68h+arg_8]
0x1800100e0  add     rsp, 60h
0x1800100e4  pop     rdi
0x1800100e5  retn
```
