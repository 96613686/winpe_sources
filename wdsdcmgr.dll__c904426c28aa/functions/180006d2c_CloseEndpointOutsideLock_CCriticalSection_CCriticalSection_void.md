# CloseEndpointOutsideLock<CCriticalSection>(CCriticalSection &,void * &)

- ea: `0x180006d2c`
- end: `0x180006d89`
- name: `??$CloseEndpointOutsideLock@VCCriticalSection@@@@YAXAEAVCCriticalSection@@AEAPEAX@Z`
- size: `93`
- prototype: `__int64 __fastcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x18000259c`

## callees

- `0x180006d2c`
- `0x180014d58`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x180006d41`
- `KERNEL32!EnterCriticalSection` at `0x180006d41`
- `KERNEL32!LeaveCriticalSection` at `0x180006d51`
- `KERNEL32!LeaveCriticalSection` at `0x180006d51`
- `WDSSRV!WdsEndpointClose` at `0x180006d5f`
- `WDSSRV!WdsEndpointClose` at `0x180006d5f`

## pseudocode

```c
void __fastcall CloseEndpointOutsideLock<CCriticalSection>(LPCRITICAL_SECTION lpCriticalSection, __int64 *a2)
{
  __int64 v4; // rsi
  unsigned int v5; // eax
  const char *v6; // rdx

  EnterCriticalSection(lpCriticalSection);
  v4 = *a2;
  *a2 = 0;
  LeaveCriticalSection(lpCriticalSection);
  if ( v4 )
  {
    v5 = WdsEndpointClose(v4);
    ElValidateWin32(v5, v6, "internal\\onecorebase\\inc\\wdssrv.h", 0x3F7u);
  }
}

```

## disassembly

```asm
0x180006d2c  mov     [rsp+arg_0], rbx
0x180006d31  mov     [rsp+arg_8], rsi
0x180006d36  push    rdi
0x180006d37  sub     rsp, 20h
0x180006d3b  mov     rbx, rdx
0x180006d3e  mov     rdi, rcx
0x180006d41  call    cs:__imp_EnterCriticalSection
0x180006d47  mov     rsi, [rbx]
0x180006d4a  mov     rcx, rdi; lpCriticalSection
0x180006d4d  and     qword ptr [rbx], 0
0x180006d51  call    cs:__imp_LeaveCriticalSection
0x180006d57  test    rsi, rsi
0x180006d5a  jz      short loc_180006D79
0x180006d5c  mov     rcx, rsi
0x180006d5f  call    cs:__imp_WdsEndpointClose
0x180006d65  mov     r9d, 3F7h; unsigned int
0x180006d6b  lea     r8, aInternalOnecor_0; "internal\\onecorebase\\inc\\wdssrv.h"
0x180006d72  mov     ecx, eax; unsigned int
0x180006d74  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180006d79  mov     rbx, [rsp+28h+arg_0]
0x180006d7e  mov     rsi, [rsp+28h+arg_8]
0x180006d83  add     rsp, 20h
0x180006d87  pop     rdi
0x180006d88  retn
```
