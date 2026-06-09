# CWdsDeviceControllerRequest::RevertToSelf(void)

- ea: `0x1800019d0`
- end: `0x180001a8e`
- name: `?RevertToSelf@CWdsDeviceControllerRequest@@UEAAJXZ`
- size: `190`
- prototype: `__int64 __fastcall(CWdsDeviceControllerRequest *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation`

## callees

- `0x1800019d0`
- `0x180014d58`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x1800019e9`
- `KERNEL32!EnterCriticalSection` at `0x1800019e9`
- `KERNEL32!LeaveCriticalSection` at `0x180001a76`
- `KERNEL32!LeaveCriticalSection` at `0x180001a76`
- `KERNEL32!GetCurrentThreadId` at `0x180001a05`
- `KERNEL32!GetCurrentThreadId` at `0x180001a05`
- `WDSSRV!WdsRevertToSelf` at `0x180001a39`
- `WDSSRV!WdsRevertToSelf` at `0x180001a39`

## pseudocode

```c
__int64 __fastcall CWdsDeviceControllerRequest::RevertToSelf(CWdsDeviceControllerRequest *this)
{
  struct _RTL_CRITICAL_SECTION *v1; // rsi
  const char *v3; // rdx
  unsigned int v4; // ebx
  signed int v5; // edi
  const char *v6; // rdx

  v1 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 64);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
  if ( *((_DWORD *)this + 26)
    && *((_QWORD *)this + 278)
    && *((_DWORD *)this + 27)
    && *((_DWORD *)this + 28) == GetCurrentThreadId()
    || !ElValidateWin32(0x139Fu, v3, "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\wdsdevicecontrollerrequest.cpp", 0x1EEu) )
  {
    v5 = WdsRevertToSelf(*((_QWORD *)this + 278));
    if ( ElValidateWin32(v5, v6, "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\wdsdevicecontrollerrequest.cpp", 0x1F2u) )
    {
      v4 = (unsigned __int16)v5 | 0x80070000;
      if ( v5 <= 0 )
        v4 = v5;
    }
    else
    {
      *((_DWORD *)this + 27) = 0;
      *((_DWORD *)this + 28) = 0;
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
0x1800019d0  mov     [rsp+arg_0], rbx
0x1800019d5  mov     [rsp+arg_8], rsi
0x1800019da  push    rdi
0x1800019db  sub     rsp, 20h
0x1800019df  lea     rsi, [rcx+40h]
0x1800019e3  mov     rbx, rcx
0x1800019e6  mov     rcx, rsi; lpCriticalSection
0x1800019e9  call    cs:__imp_EnterCriticalSection
0x1800019ef  cmp     dword ptr [rbx+68h], 0
0x1800019f3  jz      short loc_180001A10
0x1800019f5  cmp     qword ptr [rbx+8B0h], 0
0x1800019fd  jz      short loc_180001A10
0x1800019ff  cmp     dword ptr [rbx+6Ch], 0
0x180001a03  jz      short loc_180001A10
0x180001a05  call    cs:__imp_GetCurrentThreadId
0x180001a0b  cmp     [rbx+70h], eax
0x180001a0e  jz      short loc_180001A32
0x180001a10  mov     r9d, 1EEh; unsigned int
0x180001a16  lea     r8, aBaseEcoWdsWdss_3; "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\"...
0x180001a1d  mov     ecx, 139Fh; unsigned int
0x180001a22  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180001a27  test    eax, eax
0x180001a29  jz      short loc_180001A32
0x180001a2b  mov     ebx, 8007139Fh
0x180001a30  jmp     short loc_180001A73
0x180001a32  mov     rcx, [rbx+8B0h]
0x180001a39  call    cs:__imp_WdsRevertToSelf
0x180001a3f  mov     r9d, 1F2h; unsigned int
0x180001a45  lea     r8, aBaseEcoWdsWdss_3; "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\"...
0x180001a4c  mov     ecx, eax; unsigned int
0x180001a4e  mov     edi, eax
0x180001a50  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180001a55  test    eax, eax
0x180001a57  jz      short loc_180001A69
0x180001a59  movzx   ebx, di
0x180001a5c  or      ebx, 80070000h
0x180001a62  test    edi, edi
0x180001a64  cmovle  ebx, edi
0x180001a67  jmp     short loc_180001A73
0x180001a69  and     dword ptr [rbx+6Ch], 0
0x180001a6d  and     dword ptr [rbx+70h], 0
0x180001a71  xor     ebx, ebx
0x180001a73  mov     rcx, rsi; lpCriticalSection
0x180001a76  call    cs:__imp_LeaveCriticalSection
0x180001a7c  mov     rsi, [rsp+28h+arg_8]
0x180001a81  mov     eax, ebx
0x180001a83  mov     rbx, [rsp+28h+arg_0]
0x180001a88  add     rsp, 20h
0x180001a8c  pop     rdi
0x180001a8d  retn
```
