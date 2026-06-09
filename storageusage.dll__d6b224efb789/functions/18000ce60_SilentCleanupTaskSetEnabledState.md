# SilentCleanupTaskSetEnabledState

- ea: `0x18000ce60`
- end: `0x18000d098`
- name: `SilentCleanupTaskSetEnabledState`
- size: `568`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `5`
- tags: `service_task`

## callees

- `0x1800010b0`
- `0x1800050f0`
- `0x18000b350`
- `0x18000ce60`
- `0x1800267e0`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x18000ceef`
- `RPCRT4!NdrClientCall3` at `0x18000ceef`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000ce89`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000cf35`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000ce89`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000cf35`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000cec6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000cf2f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000cec6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000cf2f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000cead`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000cead`

## pseudocode

```c
__int64 SilentCleanupTaskSetEnabledState()
{
  ULONGLONG TickCount64; // rsi
  int Pointer; // ebx
  CLIENT_CALL_RETURN v2; // rax
  ULONGLONG v3; // r8
  __int64 v4; // r8
  ULONGLONG v6; // [rsp+38h] [rbp-E0h] BYREF
  CLIENT_CALL_RETURN v7; // [rsp+40h] [rbp-D8h] BYREF
  __int64 v8; // [rsp+48h] [rbp-D0h] BYREF
  ULONGLONG v9; // [rsp+50h] [rbp-C8h] BYREF
  ULONGLONG v10; // [rsp+58h] [rbp-C0h] BYREF
  ULONGLONG v11; // [rsp+60h] [rbp-B8h] BYREF
  __int64 v12; // [rsp+68h] [rbp-B0h] BYREF
  char v13[32]; // [rsp+70h] [rbp-A8h] BYREF
  __int64 *v14; // [rsp+90h] [rbp-88h]
  __int64 v15; // [rsp+98h] [rbp-80h]
  ULONGLONG *v16; // [rsp+A0h] [rbp-78h]
  __int64 v17; // [rsp+A8h] [rbp-70h]
  ULONGLONG *v18; // [rsp+B0h] [rbp-68h]
  __int64 v19; // [rsp+B8h] [rbp-60h]
  ULONGLONG *v20; // [rsp+C0h] [rbp-58h]
  __int64 v21; // [rsp+C8h] [rbp-50h]
  ULONGLONG *v22; // [rsp+D0h] [rbp-48h]
  __int64 v23; // [rsp+D8h] [rbp-40h]
  CLIENT_CALL_RETURN *v24; // [rsp+E0h] [rbp-38h]
  __int64 v25; // [rsp+E8h] [rbp-30h]
  __int64 *v26; // [rsp+F0h] [rbp-28h]
  __int64 v27; // [rsp+F8h] [rbp-20h]

  TickCount64 = GetTickCount64();
  v6 = TickCount64;
  Pointer = OpenSvcContext();
  if ( Pointer >= 0 )
  {
    AcquireSRWLockShared(&g_SvcContextLock);
    if ( g_hSvcContext )
    {
      v2.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&stru_18002E100, 0x1Fu, 0).Pointer;
      Pointer = (int)v2.Pointer;
      v7.Pointer = v2.Pointer;
      ReleaseSRWLockShared(&g_SvcContextLock);
    }
    else
    {
      ReleaseSRWLockShared(&g_SvcContextLock);
      Pointer = -2147024890;
    }
  }
  v3 = GetTickCount64();
  if ( (unsigned int)dword_180040048 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180040048, 0x400000000000LL, v3) )
  {
    v8 = 1;
    v14 = &v8;
    v15 = 8;
    v9 = v4 - TickCount64;
    v16 = &v9;
    v17 = 8;
    v10 = v4 - TickCount64;
    v18 = &v10;
    v19 = 8;
    v11 = v4 - TickCount64;
    v20 = &v11;
    v21 = 8;
    LODWORD(v6) = 33;
    v22 = &v6;
    v23 = 4;
    LODWORD(v7.Pointer) = Pointer;
    v24 = &v7;
    v25 = 4;
    v12 = 0x1000000;
    v26 = &v12;
    v27 = 8;
    tlgWriteAgg((unsigned int)&dword_180040048, (unsigned int)byte_180036E05, 0, 9, (__int64)v13);
  }
  return (unsigned int)Pointer;
}

```

## disassembly

```asm
0x18000ce60  mov     [rsp+arg_8], rbx
0x18000ce65  mov     [rsp+arg_10], rsi
0x18000ce6a  push    r14
0x18000ce6c  sub     rsp, 110h
0x18000ce73  mov     rax, cs:__security_cookie
0x18000ce7a  xor     rax, rsp
0x18000ce7d  mov     [rsp+118h+var_18], rax
0x18000ce85  movsx   r14d, cx
0x18000ce89  call    cs:__imp_GetTickCount64
0x18000ce8f  mov     rsi, rax
0x18000ce92  mov     [rsp+118h+var_E0], rax
0x18000ce97  call    OpenSvcContext
0x18000ce9c  mov     ebx, eax
0x18000ce9e  test    eax, eax
0x18000cea0  js      loc_18000CF35
0x18000cea6  lea     rcx, g_SvcContextLock; SRWLock
0x18000cead  call    cs:__imp_AcquireSRWLockShared
0x18000ceb3  mov     r9, cs:g_hSvcContext
0x18000ceba  test    r9, r9
0x18000cebd  jnz     short loc_18000CED3
0x18000cebf  lea     rcx, g_SvcContextLock; SRWLock
0x18000cec6  call    cs:__imp_ReleaseSRWLockShared
0x18000cecc  mov     ebx, 80070006h
0x18000ced1  jmp     short loc_18000CF35
0x18000ced3  mov     [rsp+118h+var_D8], 0
0x18000cedc  mov     dword ptr [rsp+118h+var_F8], r14d
0x18000cee1  xor     r8d, r8d; pReturnValue
0x18000cee4  lea     edx, [r8+1Fh]; nProcNum
0x18000cee8  lea     rcx, stru_18002E100; pProxyInfo
0x18000ceef  call    cs:__imp_NdrClientCall3
0x18000cef5  mov     rbx, rax
0x18000cef8  mov     [rsp+118h+var_D8], rax
0x18000cefd  mov     [rsp+118h+var_E8], eax
0x18000cf01  jmp     short loc_18000CF28
0x18000cf03  test    eax, eax
0x18000cf05  jle     short loc_18000CF0F
0x18000cf07  movzx   eax, ax
0x18000cf0a  or      eax, 80070000h
0x18000cf0f  mov     [rsp+118h+var_E8], eax
0x18000cf13  mov     ecx, 8000FFFFh
0x18000cf18  test    eax, eax
0x18000cf1a  cmovns  eax, ecx
0x18000cf1d  mov     ebx, eax
0x18000cf1f  mov     [rsp+118h+var_E8], eax
0x18000cf23  mov     rsi, [rsp+118h+var_E0]
0x18000cf28  lea     rcx, g_SvcContextLock; SRWLock
0x18000cf2f  call    cs:__imp_ReleaseSRWLockShared
0x18000cf35  call    cs:__imp_GetTickCount64
0x18000cf3b  mov     r8, rax
0x18000cf3e  mov     ecx, cs:dword_180040048
0x18000cf44  cmp     ecx, 5
0x18000cf47  jbe     loc_18000D070
0x18000cf4d  mov     rdx, 400000000000h
0x18000cf57  lea     rcx, dword_180040048
0x18000cf5e  call    _tlgKeywordOn
0x18000cf63  test    al, al
0x18000cf65  jz      loc_18000D070
0x18000cf6b  sub     r8, rsi
0x18000cf6e  mov     [rsp+118h+var_D0], 1
0x18000cf77  lea     rax, [rsp+118h+var_D0]
0x18000cf7c  mov     [rsp+118h+var_88], rax
0x18000cf84  mov     [rsp+118h+var_80], 8
0x18000cf90  mov     [rsp+118h+var_C8], r8
0x18000cf95  lea     rax, [rsp+118h+var_C8]
0x18000cf9a  mov     [rsp+118h+var_78], rax
0x18000cfa2  mov     [rsp+118h+var_70], 8
0x18000cfae  mov     [rsp+118h+var_C0], r8
0x18000cfb3  lea     rax, [rsp+118h+var_C0]
0x18000cfb8  mov     [rsp+118h+var_68], rax
0x18000cfc0  mov     [rsp+118h+var_60], 8
0x18000cfcc  mov     [rsp+118h+var_B8], r8
0x18000cfd1  lea     rax, [rsp+118h+var_B8]
0x18000cfd6  mov     [rsp+118h+var_58], rax
0x18000cfde  mov     [rsp+118h+var_50], 8
0x18000cfea  mov     dword ptr [rsp+118h+var_E0], 21h ; '!'
0x18000cff2  lea     rax, [rsp+118h+var_E0]
0x18000cff7  mov     [rsp+118h+var_48], rax
0x18000cfff  mov     [rsp+118h+var_40], 4
0x18000d00b  mov     dword ptr [rsp+118h+var_D8], ebx
0x18000d00f  lea     rax, [rsp+118h+var_D8]
0x18000d014  mov     [rsp+118h+var_38], rax
0x18000d01c  mov     [rsp+118h+var_30], 4
0x18000d028  mov     [rsp+118h+var_B0], 1000000h
0x18000d031  lea     rax, [rsp+118h+var_B0]
0x18000d036  mov     [rsp+118h+var_28], rax
0x18000d03e  mov     [rsp+118h+var_20], 8
0x18000d04a  lea     rax, [rsp+118h+var_A8]
0x18000d04f  mov     [rsp+118h+var_F8], rax
0x18000d054  mov     r9d, 9
0x18000d05a  xor     r8d, r8d
0x18000d05d  lea     rdx, byte_180036E05
0x18000d064  lea     rcx, dword_180040048
0x18000d06b  call    _tlgWriteAgg
0x18000d070  mov     eax, ebx
0x18000d072  mov     rcx, [rsp+118h+var_18]
0x18000d07a  xor     rcx, rsp; StackCookie
0x18000d07d  call    __security_check_cookie
0x18000d082  lea     r11, [rsp+118h+var_8]
0x18000d08a  mov     rbx, [r11+18h]
0x18000d08e  mov     rsi, [r11+20h]
0x18000d092  mov     rsp, r11
0x18000d095  pop     r14
0x18000d097  retn
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
