# MountVolume

- ea: `0x18000ae90`
- end: `0x18000b0cf`
- name: `MountVolume`
- size: `575`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x1800010b0`
- `0x1800050f0`
- `0x18000ae90`
- `0x18000b350`
- `0x1800267e0`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x18000af29`
- `RPCRT4!NdrClientCall3` at `0x18000af29`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000aebb`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000af6f`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000aebb`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000af6f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000aef8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000af69`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000aef8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000af69`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000aedf`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000aedf`

## pseudocode

```c
__int64 MountVolume()
{
  ULONGLONG TickCount64; // rsi
  int Pointer; // ebx
  CLIENT_CALL_RETURN v2; // rax
  __int64 v3; // r8
  ULONGLONG v5; // [rsp+48h] [rbp-100h] BYREF
  CLIENT_CALL_RETURN v6; // [rsp+50h] [rbp-F8h] BYREF
  __int64 v7; // [rsp+58h] [rbp-F0h] BYREF
  ULONGLONG v8; // [rsp+60h] [rbp-E8h] BYREF
  ULONGLONG v9; // [rsp+68h] [rbp-E0h] BYREF
  ULONGLONG v10; // [rsp+70h] [rbp-D8h] BYREF
  __int64 v11; // [rsp+78h] [rbp-D0h] BYREF
  char v12[32]; // [rsp+80h] [rbp-C8h] BYREF
  __int64 *v13; // [rsp+A0h] [rbp-A8h]
  __int64 v14; // [rsp+A8h] [rbp-A0h]
  ULONGLONG *v15; // [rsp+B0h] [rbp-98h]
  __int64 v16; // [rsp+B8h] [rbp-90h]
  ULONGLONG *v17; // [rsp+C0h] [rbp-88h]
  __int64 v18; // [rsp+C8h] [rbp-80h]
  ULONGLONG *v19; // [rsp+D0h] [rbp-78h]
  __int64 v20; // [rsp+D8h] [rbp-70h]
  ULONGLONG *v21; // [rsp+E0h] [rbp-68h]
  __int64 v22; // [rsp+E8h] [rbp-60h]
  CLIENT_CALL_RETURN *v23; // [rsp+F0h] [rbp-58h]
  __int64 v24; // [rsp+F8h] [rbp-50h]
  __int64 *v25; // [rsp+100h] [rbp-48h]
  __int64 v26; // [rsp+108h] [rbp-40h]

  TickCount64 = GetTickCount64();
  v5 = TickCount64;
  Pointer = OpenSvcContext();
  if ( Pointer >= 0 )
  {
    AcquireSRWLockShared(&g_SvcContextLock);
    if ( g_hSvcContext )
    {
      v2.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&stru_18002E100, 0, 0).Pointer;
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
    LODWORD(v5) = 2;
    v21 = &v5;
    v22 = 4;
    LODWORD(v6.Pointer) = Pointer;
    v23 = &v6;
    v24 = 4;
    v11 = 0x1000000;
    v25 = &v11;
    v26 = 8;
    tlgWriteAgg((__int64)&dword_180040048, (unsigned __int8 *)&byte_18003675F, 0, 9u, (__int64)v12);
  }
  return (unsigned int)Pointer;
}

```

## disassembly

```asm
0x18000ae90  push    rbx
0x18000ae92  push    rsi
0x18000ae93  push    r12
0x18000ae95  push    r14
0x18000ae97  push    r15
0x18000ae99  sub     rsp, 120h
0x18000aea0  mov     rax, cs:__security_cookie
0x18000aea7  xor     rax, rsp
0x18000aeaa  mov     [rsp+148h+var_38], rax
0x18000aeb2  mov     r12d, r8d
0x18000aeb5  mov     r15d, edx
0x18000aeb8  mov     r14d, ecx
0x18000aebb  call    cs:__imp_GetTickCount64
0x18000aec1  mov     rsi, rax
0x18000aec4  mov     [rsp+148h+var_100], rax
0x18000aec9  call    OpenSvcContext
0x18000aece  mov     ebx, eax
0x18000aed0  test    eax, eax
0x18000aed2  js      loc_18000AF6F
0x18000aed8  lea     rcx, g_SvcContextLock; SRWLock
0x18000aedf  call    cs:__imp_AcquireSRWLockShared
0x18000aee5  mov     r9, cs:g_hSvcContext
0x18000aeec  test    r9, r9
0x18000aeef  jnz     short loc_18000AF05
0x18000aef1  lea     rcx, g_SvcContextLock; SRWLock
0x18000aef8  call    cs:__imp_ReleaseSRWLockShared
0x18000aefe  mov     ebx, 80070006h
0x18000af03  jmp     short loc_18000AF6F
0x18000af05  mov     [rsp+148h+var_F8], 0
0x18000af0e  mov     [rsp+148h+var_118], r12d
0x18000af13  mov     [rsp+148h+var_120], r15d
0x18000af18  mov     dword ptr [rsp+148h+var_128], r14d
0x18000af1d  xor     r8d, r8d; pReturnValue
0x18000af20  xor     edx, edx; nProcNum
0x18000af22  lea     rcx, stru_18002E100; pProxyInfo
0x18000af29  call    cs:__imp_NdrClientCall3
0x18000af2f  mov     rbx, rax
0x18000af32  mov     [rsp+148h+var_F8], rax
0x18000af37  mov     [rsp+148h+var_108], eax
0x18000af3b  jmp     short loc_18000AF62
0x18000af3d  test    eax, eax
0x18000af3f  jle     short loc_18000AF49
0x18000af41  movzx   eax, ax
0x18000af44  or      eax, 80070000h
0x18000af49  mov     [rsp+148h+var_108], eax
0x18000af4d  mov     ecx, 8000FFFFh
0x18000af52  test    eax, eax
0x18000af54  cmovns  eax, ecx
0x18000af57  mov     ebx, eax
0x18000af59  mov     [rsp+148h+var_108], eax
0x18000af5d  mov     rsi, [rsp+148h+var_100]
0x18000af62  lea     rcx, g_SvcContextLock; SRWLock
0x18000af69  call    cs:__imp_ReleaseSRWLockShared
0x18000af6f  call    cs:__imp_GetTickCount64
0x18000af75  mov     r8, rax
0x18000af78  mov     ecx, cs:dword_180040048
0x18000af7e  cmp     ecx, 5
0x18000af81  jbe     loc_18000B0AD
0x18000af87  mov     rdx, 400000000000h
0x18000af91  lea     rcx, dword_180040048
0x18000af98  call    _tlgKeywordOn
0x18000af9d  test    al, al
0x18000af9f  jz      loc_18000B0AD
0x18000afa5  sub     r8, rsi
0x18000afa8  mov     [rsp+148h+var_F0], 1
0x18000afb1  lea     rax, [rsp+148h+var_F0]
0x18000afb6  mov     [rsp+148h+var_A8], rax
0x18000afbe  mov     [rsp+148h+var_A0], 8
0x18000afca  mov     [rsp+148h+var_E8], r8
0x18000afcf  lea     rax, [rsp+148h+var_E8]
0x18000afd4  mov     [rsp+148h+var_98], rax
0x18000afdc  mov     [rsp+148h+var_90], 8
0x18000afe8  mov     [rsp+148h+var_E0], r8
0x18000afed  lea     rax, [rsp+148h+var_E0]
0x18000aff2  mov     [rsp+148h+var_88], rax
0x18000affa  mov     [rsp+148h+var_80], 8
0x18000b006  mov     [rsp+148h+var_D8], r8
0x18000b00b  lea     rax, [rsp+148h+var_D8]
0x18000b010  mov     [rsp+148h+var_78], rax
0x18000b018  mov     [rsp+148h+var_70], 8
0x18000b024  mov     dword ptr [rsp+148h+var_100], 2
0x18000b02c  lea     rax, [rsp+148h+var_100]
0x18000b031  mov     [rsp+148h+var_68], rax
0x18000b039  mov     [rsp+148h+var_60], 4
0x18000b045  mov     dword ptr [rsp+148h+var_F8], ebx
0x18000b049  lea     rax, [rsp+148h+var_F8]
0x18000b04e  mov     [rsp+148h+var_58], rax
0x18000b056  mov     [rsp+148h+var_50], 4
0x18000b062  mov     [rsp+148h+var_D0], 1000000h
0x18000b06b  lea     rax, [rsp+148h+var_D0]
0x18000b070  mov     [rsp+148h+var_48], rax
0x18000b078  mov     [rsp+148h+var_40], 8
0x18000b084  lea     rax, [rsp+148h+var_C8]
0x18000b08c  mov     [rsp+148h+var_128], rax
0x18000b091  mov     r9d, 9
0x18000b097  xor     r8d, r8d
0x18000b09a  lea     rdx, byte_18003675F
0x18000b0a1  lea     rcx, dword_180040048
0x18000b0a8  call    _tlgWriteAgg
0x18000b0ad  mov     eax, ebx
0x18000b0af  mov     rcx, [rsp+148h+var_38]
0x18000b0b7  xor     rcx, rsp; StackCookie
0x18000b0ba  call    __security_check_cookie
0x18000b0bf  add     rsp, 120h
0x18000b0c6  pop     r15
0x18000b0c8  pop     r14
0x18000b0ca  pop     r12
0x18000b0cc  pop     rsi
0x18000b0cd  pop     rbx
0x18000b0ce  retn
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
