# DismountVolume

- ea: `0x180008430`
- end: `0x180008671`
- name: `DismountVolume`
- size: `577`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x1800010b0`
- `0x1800050f0`
- `0x180008430`
- `0x18000b350`
- `0x1800267e0`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x1800084cb`
- `RPCRT4!NdrClientCall3` at `0x1800084cb`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000845b`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180008511`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000845b`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180008511`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180008498`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000850b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180008498`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000850b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000847f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000847f`

## pseudocode

```c
__int64 DismountVolume()
{
  ULONGLONG TickCount64; // rsi
  int Pointer; // ebx
  CLIENT_CALL_RETURN v2; // rax
  ULONGLONG v3; // r8
  __int64 v4; // r8
  ULONGLONG v6; // [rsp+48h] [rbp-100h] BYREF
  CLIENT_CALL_RETURN v7; // [rsp+50h] [rbp-F8h] BYREF
  __int64 v8; // [rsp+58h] [rbp-F0h] BYREF
  ULONGLONG v9; // [rsp+60h] [rbp-E8h] BYREF
  ULONGLONG v10; // [rsp+68h] [rbp-E0h] BYREF
  ULONGLONG v11; // [rsp+70h] [rbp-D8h] BYREF
  __int64 v12; // [rsp+78h] [rbp-D0h] BYREF
  char v13[32]; // [rsp+80h] [rbp-C8h] BYREF
  __int64 *v14; // [rsp+A0h] [rbp-A8h]
  __int64 v15; // [rsp+A8h] [rbp-A0h]
  ULONGLONG *v16; // [rsp+B0h] [rbp-98h]
  __int64 v17; // [rsp+B8h] [rbp-90h]
  ULONGLONG *v18; // [rsp+C0h] [rbp-88h]
  __int64 v19; // [rsp+C8h] [rbp-80h]
  ULONGLONG *v20; // [rsp+D0h] [rbp-78h]
  __int64 v21; // [rsp+D8h] [rbp-70h]
  ULONGLONG *v22; // [rsp+E0h] [rbp-68h]
  __int64 v23; // [rsp+E8h] [rbp-60h]
  CLIENT_CALL_RETURN *v24; // [rsp+F0h] [rbp-58h]
  __int64 v25; // [rsp+F8h] [rbp-50h]
  __int64 *v26; // [rsp+100h] [rbp-48h]
  __int64 v27; // [rsp+108h] [rbp-40h]

  TickCount64 = GetTickCount64();
  v6 = TickCount64;
  Pointer = OpenSvcContext();
  if ( Pointer >= 0 )
  {
    AcquireSRWLockShared(&g_SvcContextLock);
    if ( g_hSvcContext )
    {
      v2.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&stru_18002E100, 1u, 0).Pointer;
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
    LODWORD(v6) = 3;
    v22 = &v6;
    v23 = 4;
    LODWORD(v7.Pointer) = Pointer;
    v24 = &v7;
    v25 = 4;
    v12 = 0x1000000;
    v26 = &v12;
    v27 = 8;
    tlgWriteAgg((__int64)&dword_180040048, (unsigned __int8 *)word_1800367E2, 0, 9u, (__int64)v13);
  }
  return (unsigned int)Pointer;
}

```

## disassembly

```asm
0x180008430  push    rbx
0x180008432  push    rsi
0x180008433  push    r12
0x180008435  push    r14
0x180008437  push    r15
0x180008439  sub     rsp, 120h
0x180008440  mov     rax, cs:__security_cookie
0x180008447  xor     rax, rsp
0x18000844a  mov     [rsp+148h+var_38], rax
0x180008452  mov     r12d, r8d
0x180008455  mov     r15d, edx
0x180008458  mov     r14d, ecx
0x18000845b  call    cs:__imp_GetTickCount64
0x180008461  mov     rsi, rax
0x180008464  mov     [rsp+148h+var_100], rax
0x180008469  call    OpenSvcContext
0x18000846e  mov     ebx, eax
0x180008470  test    eax, eax
0x180008472  js      loc_180008511
0x180008478  lea     rcx, g_SvcContextLock; SRWLock
0x18000847f  call    cs:__imp_AcquireSRWLockShared
0x180008485  mov     r9, cs:g_hSvcContext
0x18000848c  test    r9, r9
0x18000848f  jnz     short loc_1800084A5
0x180008491  lea     rcx, g_SvcContextLock; SRWLock
0x180008498  call    cs:__imp_ReleaseSRWLockShared
0x18000849e  mov     ebx, 80070006h
0x1800084a3  jmp     short loc_180008511
0x1800084a5  mov     [rsp+148h+var_F8], 0
0x1800084ae  mov     [rsp+148h+var_118], r12d
0x1800084b3  mov     [rsp+148h+var_120], r15d
0x1800084b8  mov     dword ptr [rsp+148h+var_128], r14d
0x1800084bd  xor     r8d, r8d; pReturnValue
0x1800084c0  lea     edx, [r8+1]; nProcNum
0x1800084c4  lea     rcx, stru_18002E100; pProxyInfo
0x1800084cb  call    cs:__imp_NdrClientCall3
0x1800084d1  mov     rbx, rax
0x1800084d4  mov     [rsp+148h+var_F8], rax
0x1800084d9  mov     [rsp+148h+var_108], eax
0x1800084dd  jmp     short loc_180008504
0x1800084df  test    eax, eax
0x1800084e1  jle     short loc_1800084EB
0x1800084e3  movzx   eax, ax
0x1800084e6  or      eax, 80070000h
0x1800084eb  mov     [rsp+148h+var_108], eax
0x1800084ef  mov     ecx, 8000FFFFh
0x1800084f4  test    eax, eax
0x1800084f6  cmovns  eax, ecx
0x1800084f9  mov     ebx, eax
0x1800084fb  mov     [rsp+148h+var_108], eax
0x1800084ff  mov     rsi, [rsp+148h+var_100]
0x180008504  lea     rcx, g_SvcContextLock; SRWLock
0x18000850b  call    cs:__imp_ReleaseSRWLockShared
0x180008511  call    cs:__imp_GetTickCount64
0x180008517  mov     r8, rax
0x18000851a  mov     ecx, cs:dword_180040048
0x180008520  cmp     ecx, 5
0x180008523  jbe     loc_18000864F
0x180008529  mov     rdx, 400000000000h
0x180008533  lea     rcx, dword_180040048
0x18000853a  call    _tlgKeywordOn
0x18000853f  test    al, al
0x180008541  jz      loc_18000864F
0x180008547  sub     r8, rsi
0x18000854a  mov     [rsp+148h+var_F0], 1
0x180008553  lea     rax, [rsp+148h+var_F0]
0x180008558  mov     [rsp+148h+var_A8], rax
0x180008560  mov     [rsp+148h+var_A0], 8
0x18000856c  mov     [rsp+148h+var_E8], r8
0x180008571  lea     rax, [rsp+148h+var_E8]
0x180008576  mov     [rsp+148h+var_98], rax
0x18000857e  mov     [rsp+148h+var_90], 8
0x18000858a  mov     [rsp+148h+var_E0], r8
0x18000858f  lea     rax, [rsp+148h+var_E0]
0x180008594  mov     [rsp+148h+var_88], rax
0x18000859c  mov     [rsp+148h+var_80], 8
0x1800085a8  mov     [rsp+148h+var_D8], r8
0x1800085ad  lea     rax, [rsp+148h+var_D8]
0x1800085b2  mov     [rsp+148h+var_78], rax
0x1800085ba  mov     [rsp+148h+var_70], 8
0x1800085c6  mov     dword ptr [rsp+148h+var_100], 3
0x1800085ce  lea     rax, [rsp+148h+var_100]
0x1800085d3  mov     [rsp+148h+var_68], rax
0x1800085db  mov     [rsp+148h+var_60], 4
0x1800085e7  mov     dword ptr [rsp+148h+var_F8], ebx
0x1800085eb  lea     rax, [rsp+148h+var_F8]
0x1800085f0  mov     [rsp+148h+var_58], rax
0x1800085f8  mov     [rsp+148h+var_50], 4
0x180008604  mov     [rsp+148h+var_D0], 1000000h
0x18000860d  lea     rax, [rsp+148h+var_D0]
0x180008612  mov     [rsp+148h+var_48], rax
0x18000861a  mov     [rsp+148h+var_40], 8
0x180008626  lea     rax, [rsp+148h+var_C8]
0x18000862e  mov     [rsp+148h+var_128], rax
0x180008633  mov     r9d, 9
0x180008639  xor     r8d, r8d
0x18000863c  lea     rdx, word_1800367E2
0x180008643  lea     rcx, dword_180040048
0x18000864a  call    _tlgWriteAgg
0x18000864f  mov     eax, ebx
0x180008651  mov     rcx, [rsp+148h+var_38]
0x180008659  xor     rcx, rsp; StackCookie
0x18000865c  call    __security_check_cookie
0x180008661  add     rsp, 120h
0x180008668  pop     r15
0x18000866a  pop     r14
0x18000866c  pop     r12
0x18000866e  pop     rsi
0x18000866f  pop     rbx
0x180008670  retn
0x18002b19c  push    rbp
0x18002b19e  sub     rsp, 40h
0x18002b1a2  mov     rbp, rdx
0x18002b1a5  mov     rcx, [rcx]
0x18002b1a8  mov     ecx, [rcx]; ExceptionCode
0x18002b1aa  call    cs:__imp_I_RpcExceptionFilter
0x18002b1b0  nop
0x18002b1b1  add     rsp, 40h
0x18002b1b5  pop     rbp
0x18002b1b6  retn
```
