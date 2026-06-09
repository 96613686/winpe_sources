# SilentCleanupTaskGetEnabledState

- ea: `0x18000cc20`
- end: `0x18000ce57`
- name: `SilentCleanupTaskGetEnabledState`
- size: `567`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x180019c40`

## callees

- `0x1800010b0`
- `0x1800050f0`
- `0x18000b350`
- `0x18000cc20`
- `0x1800267e0`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x18000ccae`
- `RPCRT4!NdrClientCall3` at `0x18000ccae`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000cc48`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000ccf4`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000cc48`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000ccf4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000cc85`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000ccee`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000cc85`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000ccee`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000cc6c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000cc6c`

## pseudocode

```c
__int64 SilentCleanupTaskGetEnabledState()
{
  ULONGLONG TickCount64; // rsi
  int Pointer; // ebx
  CLIENT_CALL_RETURN v2; // rax
  __int64 v3; // r8
  ULONGLONG v5; // [rsp+38h] [rbp-E0h] BYREF
  CLIENT_CALL_RETURN v6; // [rsp+40h] [rbp-D8h] BYREF
  __int64 v7; // [rsp+48h] [rbp-D0h] BYREF
  ULONGLONG v8; // [rsp+50h] [rbp-C8h] BYREF
  ULONGLONG v9; // [rsp+58h] [rbp-C0h] BYREF
  ULONGLONG v10; // [rsp+60h] [rbp-B8h] BYREF
  __int64 v11; // [rsp+68h] [rbp-B0h] BYREF
  char v12[32]; // [rsp+70h] [rbp-A8h] BYREF
  __int64 *v13; // [rsp+90h] [rbp-88h]
  __int64 v14; // [rsp+98h] [rbp-80h]
  ULONGLONG *v15; // [rsp+A0h] [rbp-78h]
  __int64 v16; // [rsp+A8h] [rbp-70h]
  ULONGLONG *v17; // [rsp+B0h] [rbp-68h]
  __int64 v18; // [rsp+B8h] [rbp-60h]
  ULONGLONG *v19; // [rsp+C0h] [rbp-58h]
  __int64 v20; // [rsp+C8h] [rbp-50h]
  ULONGLONG *v21; // [rsp+D0h] [rbp-48h]
  __int64 v22; // [rsp+D8h] [rbp-40h]
  CLIENT_CALL_RETURN *v23; // [rsp+E0h] [rbp-38h]
  __int64 v24; // [rsp+E8h] [rbp-30h]
  __int64 *v25; // [rsp+F0h] [rbp-28h]
  __int64 v26; // [rsp+F8h] [rbp-20h]

  TickCount64 = GetTickCount64();
  v5 = TickCount64;
  Pointer = OpenSvcContext();
  if ( Pointer >= 0 )
  {
    AcquireSRWLockShared(&g_SvcContextLock);
    if ( g_hSvcContext )
    {
      v2.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&stru_18002E100, 0x20u, 0).Pointer;
      Pointer = (int)v2.Pointer;
      v6.Pointer = v2.Pointer;
      ReleaseSRWLockShared(&g_SvcContextLock);
    }
    else
    {
      ReleaseSRWLockShared(&g_SvcContextLock);
      Pointer = -2147024890;
    }
  }
  GetTickCount64();
  if ( (unsigned int)dword_180040048 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180040048, 0x400000000000LL) )
  {
    v7 = 1;
    v13 = &v7;
    v14 = 8;
    v8 = v3 - TickCount64;
    v15 = &v8;
    v16 = 8;
    v9 = v3 - TickCount64;
    v17 = &v9;
    v18 = 8;
    v10 = v3 - TickCount64;
    v19 = &v10;
    v20 = 8;
    LODWORD(v5) = 34;
    v21 = &v5;
    v22 = 4;
    LODWORD(v6.Pointer) = Pointer;
    v23 = &v6;
    v24 = 4;
    v11 = 0x1000000;
    v25 = &v11;
    v26 = 8;
    tlgWriteAgg((__int64)&dword_180040048, (unsigned __int8 *)byte_180036F0B, 0, 9u, (__int64)v12);
  }
  return (unsigned int)Pointer;
}

```

## disassembly

```asm
0x18000cc20  mov     [rsp+arg_8], rbx
0x18000cc25  mov     [rsp+arg_10], rsi
0x18000cc2a  push    r14
0x18000cc2c  sub     rsp, 110h
0x18000cc33  mov     rax, cs:__security_cookie
0x18000cc3a  xor     rax, rsp
0x18000cc3d  mov     [rsp+118h+var_18], rax
0x18000cc45  mov     r14, rcx
0x18000cc48  call    cs:__imp_GetTickCount64
0x18000cc4e  mov     rsi, rax
0x18000cc51  mov     [rsp+118h+var_E0], rax
0x18000cc56  call    OpenSvcContext
0x18000cc5b  mov     ebx, eax
0x18000cc5d  test    eax, eax
0x18000cc5f  js      loc_18000CCF4
0x18000cc65  lea     rcx, g_SvcContextLock; SRWLock
0x18000cc6c  call    cs:__imp_AcquireSRWLockShared
0x18000cc72  mov     r9, cs:g_hSvcContext
0x18000cc79  test    r9, r9
0x18000cc7c  jnz     short loc_18000CC92
0x18000cc7e  lea     rcx, g_SvcContextLock; SRWLock
0x18000cc85  call    cs:__imp_ReleaseSRWLockShared
0x18000cc8b  mov     ebx, 80070006h
0x18000cc90  jmp     short loc_18000CCF4
0x18000cc92  mov     [rsp+118h+var_D8], 0
0x18000cc9b  mov     [rsp+118h+var_F8], r14
0x18000cca0  xor     r8d, r8d; pReturnValue
0x18000cca3  lea     edx, [r8+20h]; nProcNum
0x18000cca7  lea     rcx, stru_18002E100; pProxyInfo
0x18000ccae  call    cs:__imp_NdrClientCall3
0x18000ccb4  mov     rbx, rax
0x18000ccb7  mov     [rsp+118h+var_D8], rax
0x18000ccbc  mov     [rsp+118h+var_E8], eax
0x18000ccc0  jmp     short loc_18000CCE7
0x18000ccc2  test    eax, eax
0x18000ccc4  jle     short loc_18000CCCE
0x18000ccc6  movzx   eax, ax
0x18000ccc9  or      eax, 80070000h
0x18000ccce  mov     [rsp+118h+var_E8], eax
0x18000ccd2  mov     ecx, 8000FFFFh
0x18000ccd7  test    eax, eax
0x18000ccd9  cmovns  eax, ecx
0x18000ccdc  mov     ebx, eax
0x18000ccde  mov     [rsp+118h+var_E8], eax
0x18000cce2  mov     rsi, [rsp+118h+var_E0]
0x18000cce7  lea     rcx, g_SvcContextLock; SRWLock
0x18000ccee  call    cs:__imp_ReleaseSRWLockShared
0x18000ccf4  call    cs:__imp_GetTickCount64
0x18000ccfa  mov     r8, rax
0x18000ccfd  mov     ecx, cs:dword_180040048
0x18000cd03  cmp     ecx, 5
0x18000cd06  jbe     loc_18000CE2F
0x18000cd0c  mov     rdx, 400000000000h
0x18000cd16  lea     rcx, dword_180040048
0x18000cd1d  call    _tlgKeywordOn
0x18000cd22  test    al, al
0x18000cd24  jz      loc_18000CE2F
0x18000cd2a  sub     r8, rsi
0x18000cd2d  mov     [rsp+118h+var_D0], 1
0x18000cd36  lea     rax, [rsp+118h+var_D0]
0x18000cd3b  mov     [rsp+118h+var_88], rax
0x18000cd43  mov     [rsp+118h+var_80], 8
0x18000cd4f  mov     [rsp+118h+var_C8], r8
0x18000cd54  lea     rax, [rsp+118h+var_C8]
0x18000cd59  mov     [rsp+118h+var_78], rax
0x18000cd61  mov     [rsp+118h+var_70], 8
0x18000cd6d  mov     [rsp+118h+var_C0], r8
0x18000cd72  lea     rax, [rsp+118h+var_C0]
0x18000cd77  mov     [rsp+118h+var_68], rax
0x18000cd7f  mov     [rsp+118h+var_60], 8
0x18000cd8b  mov     [rsp+118h+var_B8], r8
0x18000cd90  lea     rax, [rsp+118h+var_B8]
0x18000cd95  mov     [rsp+118h+var_58], rax
0x18000cd9d  mov     [rsp+118h+var_50], 8
0x18000cda9  mov     dword ptr [rsp+118h+var_E0], 22h ; '"'
0x18000cdb1  lea     rax, [rsp+118h+var_E0]
0x18000cdb6  mov     [rsp+118h+var_48], rax
0x18000cdbe  mov     [rsp+118h+var_40], 4
0x18000cdca  mov     dword ptr [rsp+118h+var_D8], ebx
0x18000cdce  lea     rax, [rsp+118h+var_D8]
0x18000cdd3  mov     [rsp+118h+var_38], rax
0x18000cddb  mov     [rsp+118h+var_30], 4
0x18000cde7  mov     [rsp+118h+var_B0], 1000000h
0x18000cdf0  lea     rax, [rsp+118h+var_B0]
0x18000cdf5  mov     [rsp+118h+var_28], rax
0x18000cdfd  mov     [rsp+118h+var_20], 8
0x18000ce09  lea     rax, [rsp+118h+var_A8]
0x18000ce0e  mov     [rsp+118h+var_F8], rax
0x18000ce13  mov     r9d, 9
0x18000ce19  xor     r8d, r8d
0x18000ce1c  lea     rdx, byte_180036F0B
0x18000ce23  lea     rcx, dword_180040048
0x18000ce2a  call    _tlgWriteAgg
0x18000ce2f  mov     eax, ebx
0x18000ce31  mov     rcx, [rsp+118h+var_18]
0x18000ce39  xor     rcx, rsp; StackCookie
0x18000ce3c  call    __security_check_cookie
0x18000ce41  lea     r11, [rsp+118h+var_8]
0x18000ce49  mov     rbx, [r11+18h]
0x18000ce4d  mov     rsi, [r11+20h]
0x18000ce51  mov     rsp, r11
0x18000ce54  pop     r14
0x18000ce56  retn
0x18002b17a  push    rbp
0x18002b17c  sub     rsp, 30h
0x18002b180  mov     rbp, rdx
0x18002b183  mov     rcx, [rcx]
0x18002b186  mov     ecx, [rcx]; ExceptionCode
0x18002b188  call    cs:__imp_I_RpcExceptionFilter
0x18002b18e  nop
0x18002b18f  add     rsp, 30h
0x18002b193  pop     rbp
0x18002b194  retn
```
