# TetheringSessionTelemetry::AddThread(void)

- ea: `0x1800271b0`
- end: `0x18002727f`
- name: `?AddThread@TetheringSessionTelemetry@@AEAAJXZ`
- size: `207`
- prototype: `__int64 __fastcall(TetheringSessionTelemetry *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800272c0`

## callees

- `0x180002590`
- `0x1800271b0`
- `0x180027394`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800271ff`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800271ff`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18002724d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18002724d`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1800271f3`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180027241`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1800271f3`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180027241`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x180027214`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x180027234`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x180027214`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x180027234`

## pseudocode

```c
__int64 __fastcall TetheringSessionTelemetry::AddThread(TetheringSessionTelemetry *this)
{
  signed int v3; // ebx
  GUID ActivityId; // [rsp+20h] [rbp-28h] BYREF

  ActivityId = 0;
  if ( !(unsigned int)TetheringSessionTelemetry::Initialized(this) )
    return 2147947423LL;
  v3 = EventActivityIdControl(1u, &ActivityId);
  AcquireSRWLockShared((PSRWLOCK)this + 2);
  if ( RtlCompareMemory(&ActivityId, (char *)this + 28, 0x10u) != 16 && !v3 )
  {
    RtlCompareMemory(&GUID_NULL, &ActivityId, 0x10u);
    v3 = EventActivityIdControl(2u, (LPGUID)((char *)this + 28));
  }
  ReleaseSRWLockShared((PSRWLOCK)this + 2);
  if ( v3 > 0 )
    return (unsigned __int16)v3 | 0x80070000;
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1800271b0  mov     [rsp+arg_8], rbx
0x1800271b5  mov     [rsp+arg_10], rsi
0x1800271ba  push    rdi
0x1800271bb  sub     rsp, 40h
0x1800271bf  mov     rax, cs:__security_cookie
0x1800271c6  xor     rax, rsp
0x1800271c9  mov     [rsp+48h+var_18], rax
0x1800271ce  xorps   xmm0, xmm0
0x1800271d1  mov     rdi, rcx
0x1800271d4  movups  xmmword ptr [rsp+48h+ActivityId.Data1], xmm0
0x1800271d9  call    ?Initialized@TetheringSessionTelemetry@@QEAAHXZ; TetheringSessionTelemetry::Initialized(void)
0x1800271de  test    eax, eax
0x1800271e0  jnz     short loc_1800271E9
0x1800271e2  mov     eax, 8007139Fh
0x1800271e7  jmp     short loc_180027262
0x1800271e9  lea     rdx, [rsp+48h+ActivityId]; ActivityId
0x1800271ee  mov     ecx, 1; ControlCode
0x1800271f3  call    cs:__imp_EventActivityIdControl
0x1800271f9  lea     rcx, [rdi+10h]; SRWLock
0x1800271fd  mov     ebx, eax
0x1800271ff  call    cs:__imp_AcquireSRWLockShared
0x180027205  mov     r8d, 10h; Length
0x18002720b  lea     rdx, [rdi+1Ch]; Source2
0x18002720f  lea     rcx, [rsp+48h+ActivityId]; Source1
0x180027214  call    cs:__imp_RtlCompareMemory
0x18002721a  cmp     rax, 10h
0x18002721e  jz      short loc_180027249
0x180027220  test    ebx, ebx
0x180027222  jnz     short loc_180027249
0x180027224  lea     r8d, [rbx+10h]; Length
0x180027228  lea     rdx, [rsp+48h+ActivityId]; Source2
0x18002722d  lea     rcx, GUID_NULL; Source1
0x180027234  call    cs:__imp_RtlCompareMemory
0x18002723a  lea     rdx, [rdi+1Ch]; ActivityId
0x18002723e  lea     ecx, [rbx+2]; ControlCode
0x180027241  call    cs:__imp_EventActivityIdControl
0x180027247  mov     ebx, eax
0x180027249  lea     rcx, [rdi+10h]; SRWLock
0x18002724d  call    cs:__imp_ReleaseSRWLockShared
0x180027253  test    ebx, ebx
0x180027255  jle     short loc_180027260
0x180027257  movzx   ebx, bx
0x18002725a  or      ebx, 80070000h
0x180027260  mov     eax, ebx
0x180027262  mov     rcx, [rsp+48h+var_18]
0x180027267  xor     rcx, rsp; StackCookie
0x18002726a  call    __security_check_cookie
0x18002726f  mov     rbx, [rsp+48h+arg_8]
0x180027274  mov     rsi, [rsp+48h+arg_10]
0x180027279  add     rsp, 40h
0x18002727d  pop     rdi
0x18002727e  retn
```
