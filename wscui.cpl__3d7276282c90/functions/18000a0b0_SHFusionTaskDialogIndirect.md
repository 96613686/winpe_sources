# SHFusionTaskDialogIndirect

- ea: `0x18000a0b0`
- end: `0x18000a148`
- name: `SHFusionTaskDialogIndirect`
- size: `152`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x180009590`

## callees

- `0x18000a08c`
- `0x18000a0b0`
- `0x18000a150`
- `0x18000a198`
- `0x18000a200`
- `0x18000c010`

## pseudocode

```c
__int64 SHFusionTaskDialogIndirect(__int64 a1, __int64 a2, __int64 a3, ...)
{
  int Error; // ebx
  ULONG_PTR ulCookie; // [rsp+50h] [rbp+18h] BYREF
  __int64 (__fastcall *v8)(__int64, __int64, _QWORD, _QWORD); // [rsp+58h] [rbp+20h] BYREF
  va_list va; // [rsp+58h] [rbp+20h]
  va_list va1; // [rsp+60h] [rbp+28h] BYREF

  va_start(va1, a3);
  va_start(va, a3);
  v8 = va_arg(va1, __int64 (__fastcall *)(__int64, __int64, _QWORD, _QWORD));
  ulCookie = 0;
  if ( (unsigned int)SHActivateContext(&ulCookie) || (Error = ResultFromLastError(), Error >= 0) )
  {
    v8 = 0;
    GetProcFromComCtl32((FARPROC *)va);
    if ( v8 || (Error = ResultFromLastError(), Error >= 0) )
      Error = v8(a1, a2, 0, 0);
    SHDeactivateContext(ulCookie);
  }
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x18000a0b0  mov     rax, rsp
0x18000a0b3  mov     [rax+8], rbx
0x18000a0b7  mov     [rax+10h], rbp
0x18000a0bb  mov     [rax+20h], r9
0x18000a0bf  mov     [rax+18h], r8
0x18000a0c3  push    rsi
0x18000a0c4  sub     rsp, 30h
0x18000a0c8  mov     rbp, rcx
0x18000a0cb  mov     qword ptr [rax+18h], 0
0x18000a0d3  lea     rcx, [rax+18h]
0x18000a0d7  mov     rsi, rdx
0x18000a0da  call    SHActivateContext
0x18000a0df  test    eax, eax
0x18000a0e1  jnz     short loc_18000A0EE
0x18000a0e3  call    ResultFromLastError
0x18000a0e8  mov     ebx, eax
0x18000a0ea  test    eax, eax
0x18000a0ec  js      short loc_18000A136
0x18000a0ee  lea     rcx, [rsp+38h+arg_18]
0x18000a0f3  mov     [rsp+38h+arg_18], 0
0x18000a0fc  call    _GetProcFromComCtl32
0x18000a101  cmp     [rsp+38h+arg_18], 0
0x18000a107  jnz     short loc_18000A114
0x18000a109  call    ResultFromLastError
0x18000a10e  mov     ebx, eax
0x18000a110  test    eax, eax
0x18000a112  js      short loc_18000A12C
0x18000a114  mov     rax, [rsp+38h+arg_18]
0x18000a119  xor     r9d, r9d
0x18000a11c  xor     r8d, r8d
0x18000a11f  mov     rdx, rsi
0x18000a122  mov     rcx, rbp
0x18000a125  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a12a  mov     ebx, eax
0x18000a12c  mov     rcx, [rsp+38h+ulCookie]; ulCookie
0x18000a131  call    SHDeactivateContext
0x18000a136  mov     rbp, [rsp+38h+arg_8]
0x18000a13b  mov     eax, ebx
0x18000a13d  mov     rbx, [rsp+38h+arg_0]
0x18000a142  add     rsp, 30h
0x18000a146  pop     rsi
0x18000a147  retn
```
