# ExecuteRemoveUserFiles

- ea: `0x1800088d0`
- end: `0x180008b0c`
- name: `ExecuteRemoveUserFiles`
- size: `572`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x1800010b0`
- `0x1800050f0`
- `0x1800088d0`
- `0x18000b350`
- `0x1800267e0`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x180008964`
- `RPCRT4!NdrClientCall3` at `0x180008964`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800088f9`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800089aa`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800088f9`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800089aa`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180008936`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800089a4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180008936`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800089a4`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000891d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000891d`

## pseudocode

```c
__int64 ExecuteRemoveUserFiles()
{
  ULONGLONG TickCount64; // rsi
  CLIENT_CALL_RETURN v1; // rbx
  ULONGLONG v2; // r8
  __int64 v3; // r8
  ULONGLONG v5; // [rsp+38h] [rbp-F0h] BYREF
  CLIENT_CALL_RETURN v6; // [rsp+40h] [rbp-E8h] BYREF
  __int64 v7; // [rsp+48h] [rbp-E0h] BYREF
  ULONGLONG v8; // [rsp+50h] [rbp-D8h] BYREF
  ULONGLONG v9; // [rsp+58h] [rbp-D0h] BYREF
  ULONGLONG v10; // [rsp+60h] [rbp-C8h] BYREF
  __int64 v11; // [rsp+68h] [rbp-C0h] BYREF
  char v12[32]; // [rsp+70h] [rbp-B8h] BYREF
  __int64 *v13; // [rsp+90h] [rbp-98h]
  __int64 v14; // [rsp+98h] [rbp-90h]
  ULONGLONG *v15; // [rsp+A0h] [rbp-88h]
  __int64 v16; // [rsp+A8h] [rbp-80h]
  ULONGLONG *v17; // [rsp+B0h] [rbp-78h]
  __int64 v18; // [rsp+B8h] [rbp-70h]
  ULONGLONG *v19; // [rsp+C0h] [rbp-68h]
  __int64 v20; // [rsp+C8h] [rbp-60h]
  ULONGLONG *v21; // [rsp+D0h] [rbp-58h]
  __int64 v22; // [rsp+D8h] [rbp-50h]
  CLIENT_CALL_RETURN *v23; // [rsp+E0h] [rbp-48h]
  __int64 v24; // [rsp+E8h] [rbp-40h]
  __int64 *v25; // [rsp+F0h] [rbp-38h]
  __int64 v26; // [rsp+F8h] [rbp-30h]

  TickCount64 = GetTickCount64();
  v5 = TickCount64;
  LODWORD(v1.Pointer) = OpenSvcContext();
  if ( SLODWORD(v1.Simple) >= 0 )
  {
    AcquireSRWLockShared(&g_SvcContextLock);
    if ( g_hSvcContext )
    {
      v1.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&stru_18002E100, 0x19u, 0).Pointer;
      v6.Pointer = v1.Pointer;
      ReleaseSRWLockShared(&g_SvcContextLock);
    }
    else
    {
      ReleaseSRWLockShared(&g_SvcContextLock);
      LODWORD(v1.Pointer) = -2147024890;
    }
  }
  v2 = GetTickCount64();
  if ( (unsigned int)dword_180040048 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180040048, 0x400000000000LL, v2) )
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
    LODWORD(v5) = 22;
    v21 = &v5;
    v22 = 4;
    LODWORD(v6.Pointer) = v1.Pointer;
    v23 = &v6;
    v24 = 4;
    v11 = 0x1000000;
    v25 = &v11;
    v26 = 8;
    tlgWriteAgg((unsigned int)&dword_180040048, (unsigned int)qword_1800360B8, 0, 9, (__int64)v12);
  }
  return LODWORD(v1.Pointer);
}

```

## disassembly

```asm
0x1800088d0  mov     [rsp+arg_10], rbx
0x1800088d5  push    rsi
0x1800088d6  push    r14
0x1800088d8  push    r15
0x1800088da  sub     rsp, 110h
0x1800088e1  mov     rax, cs:__security_cookie
0x1800088e8  xor     rax, rsp
0x1800088eb  mov     [rsp+128h+var_28], rax
0x1800088f3  mov     r15, rdx
0x1800088f6  mov     r14, rcx
0x1800088f9  call    cs:__imp_GetTickCount64
0x1800088ff  mov     rsi, rax
0x180008902  mov     [rsp+128h+var_F0], rax
0x180008907  call    OpenSvcContext
0x18000890c  mov     ebx, eax
0x18000890e  test    eax, eax
0x180008910  js      loc_1800089AA
0x180008916  lea     rcx, g_SvcContextLock; SRWLock
0x18000891d  call    cs:__imp_AcquireSRWLockShared
0x180008923  mov     r9, cs:g_hSvcContext
0x18000892a  test    r9, r9
0x18000892d  jnz     short loc_180008943
0x18000892f  lea     rcx, g_SvcContextLock; SRWLock
0x180008936  call    cs:__imp_ReleaseSRWLockShared
0x18000893c  mov     ebx, 80070006h
0x180008941  jmp     short loc_1800089AA
0x180008943  mov     [rsp+128h+var_E8], 0
0x18000894c  mov     [rsp+128h+var_100], r15
0x180008951  mov     [rsp+128h+var_108], r14
0x180008956  xor     r8d, r8d; pReturnValue
0x180008959  lea     edx, [r8+19h]; nProcNum
0x18000895d  lea     rcx, stru_18002E100; pProxyInfo
0x180008964  call    cs:__imp_NdrClientCall3
0x18000896a  mov     rbx, rax
0x18000896d  mov     [rsp+128h+var_E8], rax
0x180008972  mov     [rsp+128h+var_F8], eax
0x180008976  jmp     short loc_18000899D
0x180008978  test    eax, eax
0x18000897a  jle     short loc_180008984
0x18000897c  movzx   eax, ax
0x18000897f  or      eax, 80070000h
0x180008984  mov     [rsp+128h+var_F8], eax
0x180008988  mov     ecx, 8000FFFFh
0x18000898d  test    eax, eax
0x18000898f  cmovns  eax, ecx
0x180008992  mov     ebx, eax
0x180008994  mov     [rsp+128h+var_F8], eax
0x180008998  mov     rsi, [rsp+128h+var_F0]
0x18000899d  lea     rcx, g_SvcContextLock; SRWLock
0x1800089a4  call    cs:__imp_ReleaseSRWLockShared
0x1800089aa  call    cs:__imp_GetTickCount64
0x1800089b0  mov     r8, rax
0x1800089b3  mov     ecx, cs:dword_180040048
0x1800089b9  cmp     ecx, 5
0x1800089bc  jbe     loc_180008AE5
0x1800089c2  mov     rdx, 400000000000h
0x1800089cc  lea     rcx, dword_180040048
0x1800089d3  call    _tlgKeywordOn
0x1800089d8  test    al, al
0x1800089da  jz      loc_180008AE5
0x1800089e0  sub     r8, rsi
0x1800089e3  mov     [rsp+128h+var_E0], 1
0x1800089ec  lea     rax, [rsp+128h+var_E0]
0x1800089f1  mov     [rsp+128h+var_98], rax
0x1800089f9  mov     [rsp+128h+var_90], 8
0x180008a05  mov     [rsp+128h+var_D8], r8
0x180008a0a  lea     rax, [rsp+128h+var_D8]
0x180008a0f  mov     [rsp+128h+var_88], rax
0x180008a17  mov     [rsp+128h+var_80], 8
0x180008a23  mov     [rsp+128h+var_D0], r8
0x180008a28  lea     rax, [rsp+128h+var_D0]
0x180008a2d  mov     [rsp+128h+var_78], rax
0x180008a35  mov     [rsp+128h+var_70], 8
0x180008a41  mov     [rsp+128h+var_C8], r8
0x180008a46  lea     rax, [rsp+128h+var_C8]
0x180008a4b  mov     [rsp+128h+var_68], rax
0x180008a53  mov     [rsp+128h+var_60], 8
0x180008a5f  mov     dword ptr [rsp+128h+var_F0], 16h
0x180008a67  lea     rax, [rsp+128h+var_F0]
0x180008a6c  mov     [rsp+128h+var_58], rax
0x180008a74  mov     [rsp+128h+var_50], 4
0x180008a80  mov     dword ptr [rsp+128h+var_E8], ebx
0x180008a84  lea     rax, [rsp+128h+var_E8]
0x180008a89  mov     [rsp+128h+var_48], rax
0x180008a91  mov     [rsp+128h+var_40], 4
0x180008a9d  mov     [rsp+128h+var_C0], 1000000h
0x180008aa6  lea     rax, [rsp+128h+var_C0]
0x180008aab  mov     [rsp+128h+var_38], rax
0x180008ab3  mov     [rsp+128h+var_30], 8
0x180008abf  lea     rax, [rsp+128h+var_B8]
0x180008ac4  mov     [rsp+128h+var_108], rax
0x180008ac9  mov     r9d, 9
0x180008acf  xor     r8d, r8d
0x180008ad2  lea     rdx, qword_1800360B8
0x180008ad9  lea     rcx, dword_180040048
0x180008ae0  call    _tlgWriteAgg
0x180008ae5  mov     eax, ebx
0x180008ae7  mov     rcx, [rsp+128h+var_28]
0x180008aef  xor     rcx, rsp; StackCookie
0x180008af2  call    __security_check_cookie
0x180008af7  mov     rbx, [rsp+128h+arg_10]
0x180008aff  add     rsp, 110h
0x180008b06  pop     r15
0x180008b08  pop     r14
0x180008b0a  pop     rsi
0x180008b0b  retn
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
