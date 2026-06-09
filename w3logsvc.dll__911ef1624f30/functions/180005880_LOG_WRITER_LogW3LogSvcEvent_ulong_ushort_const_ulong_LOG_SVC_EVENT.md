# LOG_WRITER::LogW3LogSvcEvent(ulong,ushort const *,ulong,LOG_SVC_EVENT)

- ea: `0x180005880`
- end: `0x18000595a`
- name: `?LogW3LogSvcEvent@LOG_WRITER@@AEAAXKPEBGKW4LOG_SVC_EVENT@@@Z`
- size: `218`
- prototype: `ULONGLONG __fastcall(__int64, unsigned int, __int64, unsigned int, int)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180004878`
- `0x180004bec`
- `0x180004fe4`

## callees

- `0x180005880`
- `0x18000e9a0`

## import_xrefs

- `msvcrt!_ultow` at `0x1800058f8`
- `msvcrt!_ultow` at `0x1800058f8`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800058d5`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180005930`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800058d5`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180005930`
- `iisutil!?LogEvent@EVENT_LOG@@QEAAXKGQEAPEBGK@Z` at `0x180005923`
- `iisutil!?LogEvent@EVENT_LOG@@QEAAXKGQEAPEBGK@Z` at `0x180005923`

## pseudocode

```c
ULONGLONG __fastcall LOG_WRITER::LogW3LogSvcEvent(__int64 a1, unsigned int a2, __int64 a3, unsigned int a4, int a5)
{
  EVENT_LOG *v9; // r12
  __int64 v10; // rbx
  ULONGLONG result; // rax
  _QWORD *v12; // rbx
  __int128 v13; // [rsp+30h] [rbp-68h] BYREF
  wchar_t Buffer[12]; // [rsp+40h] [rbp-58h] BYREF

  v9 = (EVENT_LOG *)((char *)g_pLogSvcAdmin + 1896);
  v10 = *((_QWORD *)g_pLogSvcAdmin + a5 + 238);
  v13 = 0;
  if ( !v10 || (result = GetTickCount64() - v10, result >= 0x36EE80) )
  {
    _ultow(*(_DWORD *)(*(_QWORD *)(a1 + 8) + 32LL), Buffer, 10);
    *((_QWORD *)&v13 + 1) = a3;
    *(_QWORD *)&v13 = Buffer;
    EVENT_LOG::LogEvent(v9, a2, 2u, (const unsigned __int16 **const)&v13, a4);
    v12 = g_pLogSvcAdmin;
    result = GetTickCount64();
    v12[a5 + 238] = result;
  }
  return result;
}

```

## disassembly

```asm
0x180005880  push    rbx
0x180005882  push    rbp
0x180005883  push    rsi
0x180005884  push    rdi
0x180005885  push    r12
0x180005887  push    r14
0x180005889  push    r15
0x18000588b  sub     rsp, 60h
0x18000588f  mov     rax, cs:__security_cookie
0x180005896  xor     rax, rsp
0x180005899  mov     [rsp+98h+var_40], rax
0x18000589e  mov     rax, cs:?g_pLogSvcAdmin@@3PEAVLOG_SVC_ADMIN@@EA; LOG_SVC_ADMIN * g_pLogSvcAdmin
0x1800058a5  xorps   xmm0, xmm0
0x1800058a8  movsxd  rdi, [rsp+98h+arg_20]
0x1800058b0  mov     r15d, r9d
0x1800058b3  mov     rsi, r8
0x1800058b6  mov     r14d, edx
0x1800058b9  mov     rbp, rcx
0x1800058bc  lea     r12, [rax+768h]
0x1800058c3  mov     rbx, [rax+rdi*8+770h]
0x1800058cb  movups  [rsp+98h+var_68], xmm0
0x1800058d0  test    rbx, rbx
0x1800058d3  jz      short loc_1800058E6
0x1800058d5  call    cs:__imp_GetTickCount64
0x1800058db  sub     rax, rbx
0x1800058de  cmp     rax, 36EE80h
0x1800058e4  jb      short loc_18000593E
0x1800058e6  mov     rcx, [rbp+8]
0x1800058ea  lea     rdx, [rsp+98h+Buffer]; Buffer
0x1800058ef  mov     r8d, 0Ah; Radix
0x1800058f5  mov     ecx, [rcx+20h]; Value
0x1800058f8  call    cs:__imp__ultow
0x1800058fe  lea     rax, [rsp+98h+Buffer]
0x180005903  mov     qword ptr [rsp+98h+var_68+8], rsi
0x180005908  mov     r8d, 2
0x18000590e  mov     qword ptr [rsp+98h+var_68], rax
0x180005913  lea     r9, [rsp+98h+var_68]
0x180005918  mov     [rsp+98h+var_78], r15d
0x18000591d  mov     edx, r14d
0x180005920  mov     rcx, r12
0x180005923  call    cs:__imp_?LogEvent@EVENT_LOG@@QEAAXKGQEAPEBGK@Z; EVENT_LOG::LogEvent(ulong,ushort,ushort const * * const,ulong)
0x180005929  mov     rbx, cs:?g_pLogSvcAdmin@@3PEAVLOG_SVC_ADMIN@@EA; LOG_SVC_ADMIN * g_pLogSvcAdmin
0x180005930  call    cs:__imp_GetTickCount64
0x180005936  mov     [rbx+rdi*8+770h], rax
0x18000593e  mov     rcx, [rsp+98h+var_40]
0x180005943  xor     rcx, rsp; StackCookie
0x180005946  call    __security_check_cookie
0x18000594b  add     rsp, 60h
0x18000594f  pop     r15
0x180005951  pop     r14
0x180005953  pop     r12
0x180005955  pop     rdi
0x180005956  pop     rsi
0x180005957  pop     rbp
0x180005958  pop     rbx
0x180005959  retn
```
