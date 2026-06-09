# CClientLibrary::CleanupResources(void)

- ea: `0x180004d4c`
- end: `0x180004e85`
- name: `?CleanupResources@CClientLibrary@@AEAAKXZ`
- size: `313`
- prototype: `unsigned int __fastcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180006f80`
- `0x18000cfd0`

## callees

- `0x180004d4c`
- `0x18000bd5c`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x180004d5b`
- `KERNEL32!EnterCriticalSection` at `0x180004dd1`
- `KERNEL32!EnterCriticalSection` at `0x180004d5b`
- `KERNEL32!EnterCriticalSection` at `0x180004dd1`
- `KERNEL32!LeaveCriticalSection` at `0x180004e1d`
- `KERNEL32!LeaveCriticalSection` at `0x180004e6b`
- `KERNEL32!LeaveCriticalSection` at `0x180004e1d`
- `KERNEL32!LeaveCriticalSection` at `0x180004e6b`
- `WS2_32!__imp_WSAGetLastError` at `0x180004d77`
- `WS2_32!__imp_WSAGetLastError` at `0x180004d77`
- `WS2_32!__imp_WSACleanup` at `0x180004d67`
- `WS2_32!__imp_WSACleanup` at `0x180004d67`
- `WdsCommonLib!?Shutdown@CTrace@@QEAAKXZ` at `0x180004da0`
- `WdsCommonLib!?Shutdown@CTrace@@QEAAKXZ` at `0x180004da0`
- `WdsCommonLib!?WdsAssert@@YAXPEBDK0HH@Z` at `0x180004e03`
- `WdsCommonLib!?WdsAssert@@YAXPEBDK0HH@Z` at `0x180004e03`

## pseudocode

```c
__int64 __fastcall CClientLibrary::CleanupResources(LPCRITICAL_SECTION lpCriticalSection)
{
  unsigned int Error; // edi
  __int64 v3; // rdx
  unsigned int v4; // eax
  __int64 v5; // rdx
  __int64 v6; // rdx
  __int64 v7; // rdx

  Error = 0;
  EnterCriticalSection(lpCriticalSection);
  if ( WSACleanup() )
  {
    Error = WSAGetLastError();
    ElValidateWin32(Error, v3, "base\\eco\\wds\\wdscsl\\client\\clientlib.cpp", 287);
  }
  v4 = CTrace::Shutdown((CTrace *)g_WdsCslTrace);
  ElValidateWin32(v4, v5, "base\\eco\\wds\\wdscsl\\client\\clientlib.cpp", 293);
  if ( !HIDWORD(lpCriticalSection[1].DebugInfo) )
    goto LABEL_8;
  EnterCriticalSection(&stru_180015920);
  if ( !dword_180015948 )
    WdsAssert("base\\eco\\wds\\wdscsl\\client\\controllib.cpp", 0x7Fu, "m_uInitDone", 1, 0);
  dword_180015948 = 0;
  LeaveCriticalSection(&stru_180015920);
  Error = ElValidateWin32(0, v6, "base\\eco\\wds\\wdscsl\\client\\clientlib.cpp", 300);
  if ( !(unsigned int)ElValidateWin32(Error, v7, "base\\eco\\wds\\wdscsl\\client\\clientlib.cpp", 301) )
  {
    HIDWORD(lpCriticalSection[1].DebugInfo) = 0;
LABEL_8:
    lpCriticalSection[1].LockSemaphore = 0;
    lpCriticalSection[1].SpinCount = 0;
    lpCriticalSection[1].LockCount = 0;
  }
  LeaveCriticalSection(lpCriticalSection);
  return Error;
}

```

## disassembly

```asm
0x180004d4c  mov     [rsp+arg_0], rbx
0x180004d51  push    rdi
0x180004d52  sub     rsp, 30h
0x180004d56  mov     rbx, rcx
0x180004d59  xor     edi, edi
0x180004d5b  call    cs:__imp_EnterCriticalSection
0x180004d62  nop     dword ptr [rax+rax+00h]
0x180004d67  call    cs:__imp_WSACleanup
0x180004d6e  nop     dword ptr [rax+rax+00h]
0x180004d73  test    eax, eax
0x180004d75  jz      short loc_180004D99
0x180004d77  call    cs:__imp_WSAGetLastError
0x180004d7e  nop     dword ptr [rax+rax+00h]
0x180004d83  mov     r9d, 11Fh
0x180004d89  lea     r8, aBaseEcoWdsWdsc_0; "base\\eco\\wds\\wdscsl\\client\\clientl"...
0x180004d90  mov     ecx, eax
0x180004d92  mov     edi, eax
0x180004d94  call    ElValidateWin32
0x180004d99  lea     rcx, ?g_WdsCslTrace@@3VCTrace@@A; CTrace g_WdsCslTrace
0x180004da0  call    cs:__imp_?Shutdown@CTrace@@QEAAKXZ; CTrace::Shutdown(void)
0x180004da7  nop     dword ptr [rax+rax+00h]
0x180004dac  mov     r9d, 125h
0x180004db2  lea     r8, aBaseEcoWdsWdsc_0; "base\\eco\\wds\\wdscsl\\client\\clientl"...
0x180004db9  mov     ecx, eax
0x180004dbb  call    ElValidateWin32
0x180004dc0  cmp     dword ptr [rbx+2Ch], 0
0x180004dc4  jz      loc_180004E5A
0x180004dca  lea     rcx, stru_180015920; lpCriticalSection
0x180004dd1  call    cs:__imp_EnterCriticalSection
0x180004dd8  nop     dword ptr [rax+rax+00h]
0x180004ddd  cmp     cs:dword_180015948, 0
0x180004de4  jnz     short loc_180004E0F
0x180004de6  and     [rsp+38h+var_18], 0
0x180004deb  lea     r8, aMUinitdone; "m_uInitDone"
0x180004df2  mov     r9d, 1
0x180004df8  lea     rcx, aBaseEcoWdsWdsc; "base\\eco\\wds\\wdscsl\\client\\control"...
0x180004dff  lea     edx, [r9+7Eh]
0x180004e03  call    cs:__imp_?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x180004e0a  nop     dword ptr [rax+rax+00h]
0x180004e0f  and     cs:dword_180015948, 0
0x180004e16  lea     rcx, stru_180015920; lpCriticalSection
0x180004e1d  call    cs:__imp_LeaveCriticalSection
0x180004e24  nop     dword ptr [rax+rax+00h]
0x180004e29  mov     r9d, 12Ch
0x180004e2f  lea     r8, aBaseEcoWdsWdsc_0; "base\\eco\\wds\\wdscsl\\client\\clientl"...
0x180004e36  xor     ecx, ecx
0x180004e38  call    ElValidateWin32
0x180004e3d  mov     r9d, 12Dh
0x180004e43  lea     r8, aBaseEcoWdsWdsc_0; "base\\eco\\wds\\wdscsl\\client\\clientl"...
0x180004e4a  mov     ecx, eax
0x180004e4c  mov     edi, eax
0x180004e4e  call    ElValidateWin32
0x180004e53  test    eax, eax
0x180004e55  jnz     short loc_180004E68
0x180004e57  and     [rbx+2Ch], eax
0x180004e5a  and     qword ptr [rbx+40h], 0
0x180004e5f  and     qword ptr [rbx+48h], 0
0x180004e64  and     dword ptr [rbx+30h], 0
0x180004e68  mov     rcx, rbx; lpCriticalSection
0x180004e6b  call    cs:__imp_LeaveCriticalSection
0x180004e72  nop     dword ptr [rax+rax+00h]
0x180004e77  mov     rbx, [rsp+38h+arg_0]
0x180004e7c  mov     eax, edi
0x180004e7e  add     rsp, 30h
0x180004e82  pop     rdi
0x180004e83  retn
```
