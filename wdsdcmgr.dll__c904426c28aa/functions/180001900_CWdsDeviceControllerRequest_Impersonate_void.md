# CWdsDeviceControllerRequest::Impersonate(void)

- ea: `0x180001900`
- end: `0x1800019bb`
- name: `?Impersonate@CWdsDeviceControllerRequest@@UEAAJXZ`
- size: `187`
- prototype: `__int64 __fastcall(CWdsDeviceControllerRequest *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation`

## callees

- `0x180001900`
- `0x180014d58`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x180001919`
- `KERNEL32!EnterCriticalSection` at `0x180001919`
- `KERNEL32!LeaveCriticalSection` at `0x1800019a3`
- `KERNEL32!LeaveCriticalSection` at `0x1800019a3`
- `KERNEL32!GetCurrentThreadId` at `0x180001995`
- `KERNEL32!GetCurrentThreadId` at `0x180001995`
- `WDSSRV!WdsImpersonateClient` at `0x18000195e`
- `WDSSRV!WdsImpersonateClient` at `0x18000195e`

## pseudocode

```c
__int64 __fastcall CWdsDeviceControllerRequest::Impersonate(CWdsDeviceControllerRequest *this)
{
  struct _RTL_CRITICAL_SECTION *v1; // rsi
  const char *v3; // rdx
  unsigned int v4; // ebx
  signed int v5; // edi
  const char *v6; // rdx

  v1 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 64);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
  if ( *((_DWORD *)this + 26) && *((_QWORD *)this + 278) && !*((_DWORD *)this + 27)
    || !ElValidateWin32(0x139Fu, v3, "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\wdsdevicecontrollerrequest.cpp", 0x1C1u) )
  {
    v5 = WdsImpersonateClient(*((_QWORD *)this + 278));
    if ( ElValidateWin32(v5, v6, "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\wdsdevicecontrollerrequest.cpp", 0x1C5u) )
    {
      v4 = (unsigned __int16)v5 | 0x80070000;
      if ( v5 <= 0 )
        v4 = v5;
    }
    else
    {
      *((_DWORD *)this + 27) = 1;
      *((_DWORD *)this + 28) = GetCurrentThreadId();
      v4 = 0;
    }
  }
  else
  {
    v4 = -2147019873;
  }
  LeaveCriticalSection(v1);
  return v4;
}

```

## disassembly

```asm
0x180001900  mov     [rsp+arg_0], rbx
0x180001905  mov     [rsp+arg_8], rsi
0x18000190a  push    rdi
0x18000190b  sub     rsp, 20h
0x18000190f  lea     rsi, [rcx+40h]
0x180001913  mov     rbx, rcx
0x180001916  mov     rcx, rsi; lpCriticalSection
0x180001919  call    cs:__imp_EnterCriticalSection
0x18000191f  cmp     dword ptr [rbx+68h], 0
0x180001923  jz      short loc_180001935
0x180001925  cmp     qword ptr [rbx+8B0h], 0
0x18000192d  jz      short loc_180001935
0x18000192f  cmp     dword ptr [rbx+6Ch], 0
0x180001933  jz      short loc_180001957
0x180001935  mov     r9d, 1C1h; unsigned int
0x18000193b  lea     r8, aBaseEcoWdsWdss_3; "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\"...
0x180001942  mov     ecx, 139Fh; unsigned int
0x180001947  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18000194c  test    eax, eax
0x18000194e  jz      short loc_180001957
0x180001950  mov     ebx, 8007139Fh
0x180001955  jmp     short loc_1800019A0
0x180001957  mov     rcx, [rbx+8B0h]
0x18000195e  call    cs:__imp_WdsImpersonateClient
0x180001964  mov     r9d, 1C5h; unsigned int
0x18000196a  lea     r8, aBaseEcoWdsWdss_3; "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\"...
0x180001971  mov     ecx, eax; unsigned int
0x180001973  mov     edi, eax
0x180001975  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18000197a  test    eax, eax
0x18000197c  jz      short loc_18000198E
0x18000197e  movzx   ebx, di
0x180001981  or      ebx, 80070000h
0x180001987  test    edi, edi
0x180001989  cmovle  ebx, edi
0x18000198c  jmp     short loc_1800019A0
0x18000198e  mov     dword ptr [rbx+6Ch], 1
0x180001995  call    cs:__imp_GetCurrentThreadId
0x18000199b  mov     [rbx+70h], eax
0x18000199e  xor     ebx, ebx
0x1800019a0  mov     rcx, rsi; lpCriticalSection
0x1800019a3  call    cs:__imp_LeaveCriticalSection
0x1800019a9  mov     rsi, [rsp+28h+arg_8]
0x1800019ae  mov     eax, ebx
0x1800019b0  mov     rbx, [rsp+28h+arg_0]
0x1800019b5  add     rsp, 20h
0x1800019b9  pop     rdi
0x1800019ba  retn
```
