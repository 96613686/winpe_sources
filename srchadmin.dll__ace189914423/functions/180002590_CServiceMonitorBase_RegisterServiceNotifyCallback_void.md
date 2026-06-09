# CServiceMonitorBase::_RegisterServiceNotifyCallback(void)

- ea: `0x180002590`
- end: `0x180002636`
- name: `?_RegisterServiceNotifyCallback@CServiceMonitorBase@@AEAAJXZ`
- size: `166`
- prototype: `__int64 __fastcall(CServiceMonitorBase *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x180002530`
- `0x18002c5b4`

## callees

- `0x180002590`
- `0x18002c7bc`

## import_xrefs

- `api-ms-win-service-management-l2-1-0!NotifyServiceStatusChangeW` at `0x1800025e8`
- `api-ms-win-service-management-l2-1-0!NotifyServiceStatusChangeW` at `0x1800025e8`

## pseudocode

```c
__int64 __fastcall CServiceMonitorBase::_RegisterServiceNotifyCallback(CServiceMonitorBase *this)
{
  SERVICE_NOTIFY_2W *v1; // r8
  SC_HANDLE v3; // rcx
  signed int v4; // eax
  unsigned int v5; // esi

  v1 = (SERVICE_NOTIFY_2W *)((char *)this + 8);
  *((_DWORD *)this + 3) = 0;
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 5) = 0;
  *((_QWORD *)this + 6) = 0;
  *((_QWORD *)this + 7) = 0;
  *((_QWORD *)this + 8) = 0;
  *((_QWORD *)this + 9) = 0;
  *((_QWORD *)this + 10) = 0;
  *((_QWORD *)this + 2) = CServiceMonitorBase::s_ServiceNotifyCallback;
  *((_QWORD *)this + 3) = this;
  v3 = (SC_HANDLE)*((_QWORD *)this + 11);
  v1->dwVersion = 2;
  v4 = NotifyServiceStatusChangeW(v3, 9u, v1);
  v5 = v4;
  if ( v4 )
  {
    if ( v4 == 1072 )
    {
      CServiceMonitorBase::UninitializeServiceListening(this);
    }
    else if ( v4 <= 0 )
    {
      return v5;
    }
    return (unsigned __int16)v5 | 0x80070000;
  }
  return 0;
}

```

## disassembly

```asm
0x180002590  mov     [rsp+arg_0], rbx
0x180002595  mov     [rsp+arg_8], rsi
0x18000259a  push    rdi
0x18000259b  sub     rsp, 20h
0x18000259f  xor     eax, eax
0x1800025a1  lea     r8, [rcx+8]; pNotifyBuffer
0x1800025a5  mov     [rcx+0Ch], eax
0x1800025a8  mov     edi, eax
0x1800025aa  mov     [rcx+20h], rax
0x1800025ae  mov     rbx, rcx
0x1800025b1  mov     [rcx+28h], rax
0x1800025b5  mov     edx, 9; dwNotifyMask
0x1800025ba  mov     [rcx+30h], rax
0x1800025be  mov     [rcx+38h], rax
0x1800025c2  mov     [rcx+40h], rax
0x1800025c6  mov     [rcx+48h], rax
0x1800025ca  mov     [rcx+50h], rax
0x1800025ce  lea     rax, ?s_ServiceNotifyCallback@CServiceMonitorBase@@CAXPEAX@Z; CServiceMonitorBase::s_ServiceNotifyCallback(void *)
0x1800025d5  mov     [rcx+10h], rax
0x1800025d9  mov     [rcx+18h], rcx
0x1800025dd  mov     rcx, [rcx+58h]; hService
0x1800025e1  mov     dword ptr [r8], 2
0x1800025e8  call    cs:__imp_NotifyServiceStatusChangeW
0x1800025ee  mov     esi, eax
0x1800025f0  test    eax, eax
0x1800025f2  jz      short loc_180002624
0x1800025f4  cmp     eax, 430h
0x1800025f9  jnz     short loc_180002605
0x1800025fb  mov     rcx, rbx; this
0x1800025fe  call    ?UninitializeServiceListening@CServiceMonitorBase@@QEAAXXZ; CServiceMonitorBase::UninitializeServiceListening(void)
0x180002603  jmp     short loc_180002609
0x180002605  test    esi, esi
0x180002607  jle     short loc_180002612
0x180002609  movzx   esi, si
0x18000260c  or      esi, 80070000h
0x180002612  mov     eax, esi
0x180002614  mov     rbx, [rsp+28h+arg_0]
0x180002619  mov     rsi, [rsp+28h+arg_8]
0x18000261e  add     rsp, 20h
0x180002622  pop     rdi
0x180002623  retn
0x180002624  mov     rbx, [rsp+28h+arg_0]
0x180002629  mov     eax, edi
0x18000262b  mov     rsi, [rsp+28h+arg_8]
0x180002630  add     rsp, 20h
0x180002634  pop     rdi
0x180002635  retn
```
