# ProvisionForAppInstall

- ea: `0x18000b990`
- end: `0x18000bbbb`
- name: `ProvisionForAppInstall`
- size: `555`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `installer_update`

## callees

- `0x1800010b0`
- `0x1800050f0`
- `0x18000b350`
- `0x18000b990`
- `0x1800267e0`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x18000ba24`
- `RPCRT4!NdrClientCall3` at `0x18000ba24`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000b9b9`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000ba6a`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000b9b9`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000ba6a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000b9f6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000ba64`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000b9f6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000ba64`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000b9dd`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000b9dd`

## pseudocode

```c
__int64 ProvisionForAppInstall()
{
  ULONGLONG TickCount64; // rsi
  int Pointer; // ebx
  CLIENT_CALL_RETURN v2; // rax
  ULONGLONG v3; // r8
  __int64 v4; // r8
  ULONGLONG v6; // [rsp+38h] [rbp-F0h] BYREF
  CLIENT_CALL_RETURN v7; // [rsp+40h] [rbp-E8h] BYREF
  __int64 v8; // [rsp+48h] [rbp-E0h] BYREF
  ULONGLONG v9; // [rsp+50h] [rbp-D8h] BYREF
  ULONGLONG v10; // [rsp+58h] [rbp-D0h] BYREF
  ULONGLONG v11; // [rsp+60h] [rbp-C8h] BYREF
  __int64 v12; // [rsp+68h] [rbp-C0h] BYREF
  char v13[32]; // [rsp+70h] [rbp-B8h] BYREF
  __int64 *v14; // [rsp+90h] [rbp-98h]
  __int64 v15; // [rsp+98h] [rbp-90h]
  ULONGLONG *v16; // [rsp+A0h] [rbp-88h]
  __int64 v17; // [rsp+A8h] [rbp-80h]
  ULONGLONG *v18; // [rsp+B0h] [rbp-78h]
  __int64 v19; // [rsp+B8h] [rbp-70h]
  ULONGLONG *v20; // [rsp+C0h] [rbp-68h]
  __int64 v21; // [rsp+C8h] [rbp-60h]
  ULONGLONG *v22; // [rsp+D0h] [rbp-58h]
  __int64 v23; // [rsp+D8h] [rbp-50h]
  CLIENT_CALL_RETURN *v24; // [rsp+E0h] [rbp-48h]
  __int64 v25; // [rsp+E8h] [rbp-40h]
  __int64 *v26; // [rsp+F0h] [rbp-38h]
  __int64 v27; // [rsp+F8h] [rbp-30h]

  TickCount64 = GetTickCount64();
  v6 = TickCount64;
  Pointer = OpenSvcContext();
  if ( Pointer >= 0 )
  {
    AcquireSRWLockShared(&g_SvcContextLock);
    if ( g_hSvcContext )
    {
      v2.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&stru_18002E100, 0x11u, 0).Pointer;
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
    LODWORD(v6) = 8;
    v22 = &v6;
    v23 = 4;
    LODWORD(v7.Pointer) = Pointer;
    v24 = &v7;
    v25 = 4;
    v12 = 0x1000000;
    v26 = &v12;
    v27 = 8;
    tlgWriteAgg((__int64)&dword_180040048, (unsigned __int8 *)byte_180036659, 0, 9u, (__int64)v13);
  }
  return (unsigned int)Pointer;
}

```

## disassembly

```asm
0x18000b990  mov     [rsp+arg_10], rbx
0x18000b995  push    rsi
0x18000b996  push    r14
0x18000b998  push    r15
0x18000b99a  sub     rsp, 110h
0x18000b9a1  mov     rax, cs:__security_cookie
0x18000b9a8  xor     rax, rsp
0x18000b9ab  mov     [rsp+128h+var_28], rax
0x18000b9b3  mov     r15d, edx
0x18000b9b6  mov     r14d, ecx
0x18000b9b9  call    cs:__imp_GetTickCount64
0x18000b9bf  mov     rsi, rax
0x18000b9c2  mov     [rsp+128h+var_F0], rax
0x18000b9c7  call    OpenSvcContext
0x18000b9cc  mov     ebx, eax
0x18000b9ce  test    eax, eax
0x18000b9d0  js      loc_18000BA6A
0x18000b9d6  lea     rcx, g_SvcContextLock; SRWLock
0x18000b9dd  call    cs:__imp_AcquireSRWLockShared
0x18000b9e3  mov     r9, cs:g_hSvcContext
0x18000b9ea  test    r9, r9
0x18000b9ed  jnz     short loc_18000BA03
0x18000b9ef  lea     rcx, g_SvcContextLock; SRWLock
0x18000b9f6  call    cs:__imp_ReleaseSRWLockShared
0x18000b9fc  mov     ebx, 80070006h
0x18000ba01  jmp     short loc_18000BA6A
0x18000ba03  mov     [rsp+128h+var_E8], 0
0x18000ba0c  mov     [rsp+128h+var_100], r15d
0x18000ba11  mov     dword ptr [rsp+128h+var_108], r14d
0x18000ba16  xor     r8d, r8d; pReturnValue
0x18000ba19  lea     edx, [r8+11h]; nProcNum
0x18000ba1d  lea     rcx, stru_18002E100; pProxyInfo
0x18000ba24  call    cs:__imp_NdrClientCall3
0x18000ba2a  mov     rbx, rax
0x18000ba2d  mov     [rsp+128h+var_E8], rax
0x18000ba32  mov     [rsp+128h+var_F8], eax
0x18000ba36  jmp     short loc_18000BA5D
0x18000ba38  test    eax, eax
0x18000ba3a  jle     short loc_18000BA44
0x18000ba3c  movzx   eax, ax
0x18000ba3f  or      eax, 80070000h
0x18000ba44  mov     [rsp+128h+var_F8], eax
0x18000ba48  mov     ecx, 8000FFFFh
0x18000ba4d  test    eax, eax
0x18000ba4f  cmovns  eax, ecx
0x18000ba52  mov     ebx, eax
0x18000ba54  mov     [rsp+128h+var_F8], eax
0x18000ba58  mov     rsi, [rsp+128h+var_F0]
0x18000ba5d  lea     rcx, g_SvcContextLock; SRWLock
0x18000ba64  call    cs:__imp_ReleaseSRWLockShared
0x18000ba6a  call    cs:__imp_GetTickCount64
0x18000ba70  mov     r8, rax
0x18000ba73  mov     ecx, cs:dword_180040048
0x18000ba79  cmp     ecx, 5
0x18000ba7c  jbe     loc_18000BB94
0x18000ba82  mov     rdx, 400000000000h
0x18000ba8c  lea     rcx, dword_180040048
0x18000ba93  call    _tlgKeywordOn
0x18000ba98  test    al, al
0x18000ba9a  jz      loc_18000BB94
0x18000baa0  sub     r8, rsi
0x18000baa3  mov     [rsp+128h+var_E0], 1
0x18000baac  lea     rax, [rsp+128h+var_E0]
0x18000bab1  mov     [rsp+128h+var_98], rax
0x18000bab9  mov     r9d, 8
0x18000babf  mov     [rsp+128h+var_90], r9
0x18000bac7  mov     [rsp+128h+var_D8], r8
0x18000bacc  lea     rax, [rsp+128h+var_D8]
0x18000bad1  mov     [rsp+128h+var_88], rax
0x18000bad9  mov     [rsp+128h+var_80], r9
0x18000bae1  mov     [rsp+128h+var_D0], r8
0x18000bae6  lea     rax, [rsp+128h+var_D0]
0x18000baeb  mov     [rsp+128h+var_78], rax
0x18000baf3  mov     [rsp+128h+var_70], r9
0x18000bafb  mov     [rsp+128h+var_C8], r8
0x18000bb00  lea     rax, [rsp+128h+var_C8]
0x18000bb05  mov     [rsp+128h+var_68], rax
0x18000bb0d  mov     [rsp+128h+var_60], r9
0x18000bb15  mov     dword ptr [rsp+128h+var_F0], r9d
0x18000bb1a  lea     rax, [rsp+128h+var_F0]
0x18000bb1f  mov     [rsp+128h+var_58], rax
0x18000bb27  mov     [rsp+128h+var_50], 4
0x18000bb33  mov     dword ptr [rsp+128h+var_E8], ebx
0x18000bb37  lea     rax, [rsp+128h+var_E8]
0x18000bb3c  mov     [rsp+128h+var_48], rax
0x18000bb44  mov     [rsp+128h+var_40], 4
0x18000bb50  mov     [rsp+128h+var_C0], 1000000h
0x18000bb59  lea     rax, [rsp+128h+var_C0]
0x18000bb5e  mov     [rsp+128h+var_38], rax
0x18000bb66  mov     [rsp+128h+var_30], r9
0x18000bb6e  lea     rax, [rsp+128h+var_B8]
0x18000bb73  mov     [rsp+128h+var_108], rax
0x18000bb78  mov     r9d, 9
0x18000bb7e  xor     r8d, r8d
0x18000bb81  lea     rdx, byte_180036659
0x18000bb88  lea     rcx, dword_180040048
0x18000bb8f  call    _tlgWriteAgg
0x18000bb94  mov     eax, ebx
0x18000bb96  mov     rcx, [rsp+128h+var_28]
0x18000bb9e  xor     rcx, rsp; StackCookie
0x18000bba1  call    __security_check_cookie
0x18000bba6  mov     rbx, [rsp+128h+arg_10]
0x18000bbae  add     rsp, 110h
0x18000bbb5  pop     r15
0x18000bbb7  pop     r14
0x18000bbb9  pop     rsi
0x18000bbba  retn
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
