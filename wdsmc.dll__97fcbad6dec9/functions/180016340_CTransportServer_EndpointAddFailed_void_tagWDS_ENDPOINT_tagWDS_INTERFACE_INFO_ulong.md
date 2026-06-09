# CTransportServer::_EndpointAddFailed(void *,tagWDS_ENDPOINT *,tagWDS_INTERFACE_INFO *,ulong)

- ea: `0x180016340`
- end: `0x18001644c`
- name: `?_EndpointAddFailed@CTransportServer@@SAXPEAXPEAUtagWDS_ENDPOINT@@PEAUtagWDS_INTERFACE_INFO@@K@Z`
- size: `268`
- prototype: `void __fastcall(LPCRITICAL_SECTION lpCriticalSection, struct tagWDS_ENDPOINT *, struct tagWDS_INTERFACE_INFO *, unsigned int)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x180003c0c`
- `0x180016340`
- `0x180026670`
- `0x180026d3a`
- `0x180026d70`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x18001638d`
- `KERNEL32!LeaveCriticalSection` at `0x18001639b`
- `KERNEL32!LeaveCriticalSection` at `0x18001638d`
- `KERNEL32!LeaveCriticalSection` at `0x18001639b`
- `KERNEL32!EnterCriticalSection` at `0x18001636d`
- `KERNEL32!EnterCriticalSection` at `0x18001636d`

## string_xrefs

- `0x1800163f7`: `WDSMCTP[0x%x] WDS Server failed to open endpoint - %s, killing session.`

## pseudocode

```c
void __fastcall CTransportServer::_EndpointAddFailed(
        LPCRITICAL_SECTION lpCriticalSection,
        struct tagWDS_ENDPOINT *a2,
        struct tagWDS_INTERFACE_INFO *a3,
        int a4)
{
  int LockSemaphore_high; // eax
  const unsigned __int16 *v8; // r8
  _QWORD v9[2]; // [rsp+20h] [rbp-C8h] BYREF
  unsigned int v10; // [rsp+30h] [rbp-B8h]
  int v11; // [rsp+40h] [rbp-A8h] BYREF
  char v12; // [rsp+44h] [rbp-A4h] BYREF

  EnterCriticalSection(lpCriticalSection);
  LockSemaphore_high = HIDWORD(lpCriticalSection[56].LockSemaphore);
  if ( LockSemaphore_high > 0 && a4 == 50 )
  {
    HIDWORD(lpCriticalSection[56].LockSemaphore) = LockSemaphore_high - 1;
    LeaveCriticalSection(lpCriticalSection);
  }
  else
  {
    LeaveCriticalSection(lpCriticalSection);
    if ( g_ErrLibTraceFunction )
    {
      v10 = *((_DWORD *)a3 + 4);
      v9[0] = 0;
      v9[1] = 0;
      memmove_0(v9, a3, v10);
      CIPString::Initialize((CIPString *)&v11, (struct tagWDS_IP_ADDRESS6 *)v9);
      v8 = (const unsigned __int16 *)&v12;
      if ( v11 )
        v8 = L"<<Failed>>";
      g_ErrLibTraceFunction(
        L"WDSMCTP[0x%x] WDS Server failed to open endpoint - %s, killing session.",
        LODWORD(lpCriticalSection[55].OwningThread),
        v8);
    }
    _InterlockedExchange((volatile __int32 *)&lpCriticalSection[56].OwningThread, 1);
    (*(void (__fastcall **)(PRTL_CRITICAL_SECTION_DEBUG))(*(_QWORD *)lpCriticalSection[1].DebugInfo + 48LL))(lpCriticalSection[1].DebugInfo);
  }
}

```

## disassembly

```asm
0x180016340  mov     [rsp+arg_8], rbx
0x180016345  mov     [rsp+arg_18], rsi
0x18001634a  push    rdi
0x18001634b  sub     rsp, 0E0h
0x180016352  mov     rax, cs:__security_cookie
0x180016359  xor     rax, rsp
0x18001635c  mov     [rsp+0E8h+var_18], rax
0x180016364  mov     edi, r9d
0x180016367  mov     rsi, r8
0x18001636a  mov     rbx, rcx
0x18001636d  call    cs:__imp_EnterCriticalSection
0x180016373  mov     eax, [rbx+8DCh]
0x180016379  test    eax, eax
0x18001637b  jle     short loc_180016398
0x18001637d  cmp     edi, 32h ; '2'
0x180016380  jnz     short loc_180016398
0x180016382  dec     eax
0x180016384  mov     rcx, rbx; lpCriticalSection
0x180016387  mov     [rbx+8DCh], eax
0x18001638d  call    cs:__imp_LeaveCriticalSection
0x180016393  jmp     loc_180016427
0x180016398  mov     rcx, rbx; lpCriticalSection
0x18001639b  call    cs:__imp_LeaveCriticalSection
0x1800163a1  cmp     cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA, 0; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x1800163a9  jz      short loc_18001640B
0x1800163ab  mov     r8d, [rsi+10h]; Size
0x1800163af  lea     rcx, [rsp+0E8h+var_C8]; void *
0x1800163b4  xor     eax, eax
0x1800163b6  mov     [rsp+0E8h+var_B8], r8d
0x1800163bb  mov     rdx, rsi; Src
0x1800163be  mov     [rsp+0E8h+var_C8], rax
0x1800163c3  mov     [rsp+0E8h+var_C0], rax
0x1800163c8  call    memmove_0
0x1800163cd  lea     rdx, [rsp+0E8h+var_C8]; struct tagWDS_IP_ADDRESS6 *
0x1800163d2  lea     rcx, [rsp+0E8h+var_A8]; this
0x1800163d7  call    ?Initialize@CIPString@@QEAAKPEAUtagWDS_IP_ADDRESS6@@@Z; CIPString::Initialize(tagWDS_IP_ADDRESS6 *)
0x1800163dc  cmp     [rsp+0E8h+var_A8], 0
0x1800163e1  lea     rax, aFailed; "<<Failed>>"
0x1800163e8  mov     edx, [rbx+8A8h]
0x1800163ee  lea     r8, [rsp+0E8h+var_A4]
0x1800163f3  cmovnz  r8, rax
0x1800163f7  lea     rcx, aWdsmctp0xXWdsS; "WDSMCTP[0x%x] WDS Server failed to open"...
0x1800163fe  mov     rax, cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x180016405  call    cs:__guard_dispatch_icall_fptr
0x18001640b  mov     eax, 1
0x180016410  xchg    eax, [rbx+8D0h]
0x180016416  mov     rcx, [rbx+28h]
0x18001641a  mov     rax, [rcx]
0x18001641d  mov     rax, [rax+30h]
0x180016421  call    cs:__guard_dispatch_icall_fptr
0x180016427  mov     rcx, [rsp+0E8h+var_18]
0x18001642f  xor     rcx, rsp; StackCookie
0x180016432  call    __security_check_cookie
0x180016437  lea     r11, [rsp+0E8h+var_8]
0x18001643f  mov     rbx, [r11+18h]
0x180016443  mov     rsi, [r11+28h]
0x180016447  mov     rsp, r11
0x18001644a  pop     rdi
0x18001644b  retn
```
