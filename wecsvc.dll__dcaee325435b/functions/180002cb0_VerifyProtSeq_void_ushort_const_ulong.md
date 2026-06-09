# VerifyProtSeq(void *,ushort const * *,ulong)

- ea: `0x180002cb0`
- end: `0x180002f0e`
- name: `?VerifyProtSeq@@YAXPEAXPEAPEBGK@Z`
- size: `606`
- prototype: `void __fastcall(void *, const unsigned __int16 **)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x180002990`

## callees

- `0x18000195c`
- `0x180002510`
- `0x180002cb0`
- `0x1800032dc`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180002dc8`
- `msvcrt!_wcsicmp` at `0x180002dc8`
- `RPCRT4!RpcStringBindingParseW` at `0x180002d92`
- `RPCRT4!RpcStringBindingParseW` at `0x180002d92`
- `RPCRT4!RpcStringFreeW` at `0x180002d60`
- `RPCRT4!RpcBindingToStringBindingW` at `0x180002cd8`
- `RPCRT4!RpcBindingToStringBindingW` at `0x180002cd8`

## string_xrefs

- `0x180002d20`: `admin\wmi\events\forwarding\collector\service\srvmain.cpp`
- `0x180002e23`: `admin\wmi\events\forwarding\collector\service\srvmain.cpp`
- `0x180002ece`: `admin\wmi\events\forwarding\collector\service\srvmain.cpp`

## pseudocode

```c
void __fastcall VerifyProtSeq(void *a1, const unsigned __int16 **a2)
{
  unsigned int v3; // eax
  unsigned int v4; // ebx
  unsigned int v5; // ebx
  void **pExceptionObject; // [rsp+30h] [rbp-29h] BYREF
  char v7; // [rsp+38h] [rbp-21h]
  const char *v8; // [rsp+40h] [rbp-19h]
  __int64 v9; // [rsp+48h] [rbp-11h]
  __int64 v10; // [rsp+50h] [rbp-9h]
  int v11; // [rsp+58h] [rbp-1h]
  int v12; // [rsp+5Ch] [rbp+3h]
  int v13; // [rsp+60h] [rbp+7h]
  RPC_WSTR StringBinding; // [rsp+68h] [rbp+Fh] BYREF
  _BYTE v15[8]; // [rsp+70h] [rbp+17h] BYREF
  RPC_STATUS (__stdcall *v16)(RPC_WSTR *); // [rsp+78h] [rbp+1Fh]
  RPC_WSTR *p_Protseq; // [rsp+80h] [rbp+27h]
  _BYTE v18[8]; // [rsp+88h] [rbp+2Fh] BYREF
  RPC_STATUS (__stdcall *v19)(RPC_WSTR *); // [rsp+90h] [rbp+37h]
  RPC_WSTR *p_StringBinding; // [rsp+98h] [rbp+3Fh]
  RPC_WSTR Protseq; // [rsp+D8h] [rbp+7Fh] BYREF

  StringBinding = 0;
  v3 = RpcBindingToStringBindingW(a1, &StringBinding);
  v4 = v3;
  if ( v3 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_ca6bc7c05c2a3d506e8ee1e48e049877_Traceguids, v3);
    }
    v7 = 0;
    v8 = "admin\\wmi\\events\\forwarding\\collector\\service\\srvmain.cpp";
    v9 = 0;
    v10 = 0;
    v11 = v4;
    v12 = -1;
    v13 = 57;
    pExceptionObject = &wmi::GenericException::`vftable';
    throw (wmi::GenericException *)&pExceptionObject;
  }
  v18[0] = 0;
  v19 = RpcStringFreeW;
  p_StringBinding = &StringBinding;
  Protseq = 0;
  v5 = RpcStringBindingParseW(StringBinding, 0, &Protseq, 0, 0, 0);
  if ( v5 )
  {
LABEL_17:
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_ca6bc7c05c2a3d506e8ee1e48e049877_Traceguids, v5);
    }
    v7 = 0;
    v8 = "admin\\wmi\\events\\forwarding\\collector\\service\\srvmain.cpp";
    v9 = 0;
    v10 = 0;
    v11 = v5;
    v12 = -1;
    v13 = 70;
    pExceptionObject = &wmi::GenericException::`vftable';
    throw (wmi::GenericException *)&pExceptionObject;
  }
  if ( !Protseq )
  {
    v5 = 1287;
    goto LABEL_17;
  }
  v15[0] = 0;
  v16 = RpcStringFreeW;
  p_Protseq = &Protseq;
  if ( _wcsicmp(Protseq, *a2) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_ca6bc7c05c2a3d506e8ee1e48e049877_Traceguids, 5);
    }
    v7 = 0;
    v8 = "admin\\wmi\\events\\forwarding\\collector\\service\\srvmain.cpp";
    v9 = 0;
    v10 = 0;
    v11 = 5;
    v12 = -1;
    v13 = 82;
    pExceptionObject = &wmi::GenericException::`vftable';
    throw (wmi::GenericException *)&pExceptionObject;
  }
  wmi::ScopeGuardImpl1<void (*)(std::vector<std::vector<unsigned short>> *),std::vector<std::vector<unsigned short>> *>::~ScopeGuardImpl1<void (*)(std::vector<std::vector<unsigned short>> *),std::vector<std::vector<unsigned short>> *>(v15);
  wmi::ScopeGuardImpl1<void (*)(std::vector<std::vector<unsigned short>> *),std::vector<std::vector<unsigned short>> *>::~ScopeGuardImpl1<void (*)(std::vector<std::vector<unsigned short>> *),std::vector<std::vector<unsigned short>> *>(v18);
}

```

## disassembly

```asm
0x180002cb0  mov     [rsp-8+arg_0], rbx
0x180002cb5  mov     [rsp-8+arg_8], rsi
0x180002cba  push    rbp
0x180002cbb  push    rdi
0x180002cbc  push    r14
0x180002cbe  lea     rbp, [rsp-47h]
0x180002cc3  sub     rsp, 0A0h
0x180002cca  mov     rsi, rdx
0x180002ccd  xor     r14d, r14d
0x180002cd0  mov     [rbp+57h+StringBinding], r14
0x180002cd4  lea     rdx, [rbp+57h+StringBinding]; StringBinding
0x180002cd8  call    cs:__imp_RpcBindingToStringBindingW
0x180002cde  mov     ebx, eax
0x180002ce0  test    eax, eax
0x180002ce2  jz      short loc_180002D60
0x180002ce4  lea     rcx, WPP_GLOBAL_Control
0x180002ceb  mov     r10, cs:WPP_GLOBAL_Control
0x180002cf2  cmp     r10, rcx
0x180002cf5  jz      short loc_180002D1C
0x180002cf7  test    byte ptr [r10+1Ch], 10h
0x180002cfc  jz      short loc_180002D1C
0x180002cfe  cmp     byte ptr [r10+19h], 2
0x180002d03  jb      short loc_180002D1C
0x180002d05  lea     edx, [r14+0Ah]
0x180002d09  mov     r9d, eax
0x180002d0c  lea     r8, WPP_ca6bc7c05c2a3d506e8ee1e48e049877_Traceguids
0x180002d13  mov     rcx, [r10+10h]
0x180002d17  call    WPP_SF_D
0x180002d1c  mov     [rbp+57h+var_78], r14b
0x180002d20  lea     rax, aAdminWmiEvents; "admin\\wmi\\events\\forwarding\\collect"...
0x180002d27  mov     [rbp+57h+var_70], rax
0x180002d2b  mov     [rbp+57h+var_68], r14
0x180002d2f  mov     [rbp+57h+var_60], r14
0x180002d33  mov     [rbp+57h+var_58], ebx
0x180002d36  mov     [rbp+57h+var_54], 0FFFFFFFFh
0x180002d3d  mov     [rbp+57h+var_50], 39h ; '9'
0x180002d44  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x180002d4b  mov     [rbp+57h+pExceptionObject], rax
0x180002d4f  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x180002d56  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180002d5a  call    _CxxThrowException_0
0x180002d60  mov     rdi, cs:__imp_RpcStringFreeW
0x180002d67  mov     [rbp+57h+var_28], r14b
0x180002d6b  mov     [rbp+57h+var_20], rdi
0x180002d6f  lea     rax, [rbp+57h+StringBinding]
0x180002d73  mov     [rbp+57h+var_18], rax
0x180002d77  mov     [rbp+57h+Protseq], r14
0x180002d7b  mov     [rsp+0B0h+NetworkOptions], r14; NetworkOptions
0x180002d80  mov     [rsp+0B0h+Endpoint], r14; Endpoint
0x180002d85  xor     r9d, r9d; NetworkAddr
0x180002d88  lea     r8, [rbp+57h+Protseq]; Protseq
0x180002d8c  xor     edx, edx; ObjUuid
0x180002d8e  mov     rcx, [rbp+57h+StringBinding]; StringBinding
0x180002d92  call    cs:__imp_RpcStringBindingParseW
0x180002d98  mov     ebx, eax
0x180002d9a  test    eax, eax
0x180002d9c  jnz     loc_180002E93
0x180002da2  mov     rcx, [rbp+57h+Protseq]; String1
0x180002da6  test    rcx, rcx
0x180002da9  jz      loc_180002E8E
0x180002daf  mov     [rbp+57h+var_40], r14b
0x180002db3  mov     [rbp+57h+var_38], rdi
0x180002db7  lea     rax, [rbp+57h+Protseq]
0x180002dbb  mov     [rbp+57h+var_30], rax
0x180002dbf  mov     ebx, r14d
0x180002dc2  mov     edx, ebx
0x180002dc4  mov     rdx, [rsi+rdx*8]; String2
0x180002dc8  call    cs:__imp__wcsicmp
0x180002dce  test    eax, eax
0x180002dd0  jz      loc_180002E63
0x180002dd6  inc     ebx
0x180002dd8  cmp     ebx, 1
0x180002ddb  jnb     short loc_180002DE3
0x180002ddd  mov     rcx, [rbp+57h+Protseq]
0x180002de1  jmp     short loc_180002DC2
0x180002de3  jnz     short loc_180002E63
0x180002de5  lea     rcx, WPP_GLOBAL_Control
0x180002dec  mov     ebx, 5
0x180002df1  mov     rax, cs:WPP_GLOBAL_Control
0x180002df8  cmp     rax, rcx
0x180002dfb  jz      short loc_180002E1F
0x180002dfd  test    byte ptr [rax+1Ch], 10h
0x180002e01  jz      short loc_180002E1F
0x180002e03  cmp     byte ptr [rax+19h], 2
0x180002e07  jb      short loc_180002E1F
0x180002e09  lea     edx, [rbx+7]
0x180002e0c  mov     r9d, ebx
0x180002e0f  lea     r8, WPP_ca6bc7c05c2a3d506e8ee1e48e049877_Traceguids
0x180002e16  mov     rcx, [rax+10h]
0x180002e1a  call    WPP_SF_D
0x180002e1f  mov     [rbp+57h+var_78], r14b
0x180002e23  lea     rax, aAdminWmiEvents; "admin\\wmi\\events\\forwarding\\collect"...
0x180002e2a  mov     [rbp+57h+var_70], rax
0x180002e2e  mov     [rbp+57h+var_68], r14
0x180002e32  mov     [rbp+57h+var_60], r14
0x180002e36  mov     [rbp+57h+var_58], ebx
0x180002e39  mov     [rbp+57h+var_54], 0FFFFFFFFh
0x180002e40  mov     [rbp+57h+var_50], 52h ; 'R'
0x180002e47  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x180002e4e  mov     [rbp+57h+pExceptionObject], rax
0x180002e52  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x180002e59  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180002e5d  call    _CxxThrowException_0
0x180002e63  lea     rcx, [rbp+57h+var_40]
0x180002e67  call    ??1?$ScopeGuardImpl1@P6AXPEAV?$vector@V?$vector@GV?$allocator@G@std@@@std@@V?$allocator@V?$vector@GV?$allocator@G@std@@@std@@@2@@std@@@ZPEAV12@@wmi@@QEAA@XZ; wmi::ScopeGuardImpl1<void (*)(std::vector<std::vector<ushort>> *),std::vector<std::vector<ushort>> *>::~ScopeGuardImpl1<void (*)(std::vector<std::vector<ushort>> *),std::vector<std::vector<ushort>> *>(void)
0x180002e6c  nop
0x180002e6d  lea     rcx, [rbp+57h+var_28]
0x180002e71  call    ??1?$ScopeGuardImpl1@P6AXPEAV?$vector@V?$vector@GV?$allocator@G@std@@@std@@V?$allocator@V?$vector@GV?$allocator@G@std@@@std@@@2@@std@@@ZPEAV12@@wmi@@QEAA@XZ; wmi::ScopeGuardImpl1<void (*)(std::vector<std::vector<ushort>> *),std::vector<std::vector<ushort>> *>::~ScopeGuardImpl1<void (*)(std::vector<std::vector<ushort>> *),std::vector<std::vector<ushort>> *>(void)
0x180002e76  lea     r11, [rsp+0B0h+var_10]
0x180002e7e  mov     rbx, [r11+20h]
0x180002e82  mov     rsi, [r11+28h]
0x180002e86  mov     rsp, r11
0x180002e89  pop     r14
0x180002e8b  pop     rdi
0x180002e8c  pop     rbp
0x180002e8d  retn
0x180002e8e  mov     ebx, 507h
0x180002e93  lea     rcx, WPP_GLOBAL_Control
0x180002e9a  mov     rax, cs:WPP_GLOBAL_Control
0x180002ea1  cmp     rax, rcx
0x180002ea4  jz      short loc_180002ECA
0x180002ea6  test    byte ptr [rax+1Ch], 10h
0x180002eaa  jz      short loc_180002ECA
0x180002eac  cmp     byte ptr [rax+19h], 2
0x180002eb0  jb      short loc_180002ECA
0x180002eb2  mov     edx, 0Bh
0x180002eb7  mov     r9d, ebx
0x180002eba  lea     r8, WPP_ca6bc7c05c2a3d506e8ee1e48e049877_Traceguids
0x180002ec1  mov     rcx, [rax+10h]
0x180002ec5  call    WPP_SF_D
0x180002eca  mov     [rbp+57h+var_78], r14b
0x180002ece  lea     rax, aAdminWmiEvents; "admin\\wmi\\events\\forwarding\\collect"...
0x180002ed5  mov     [rbp+57h+var_70], rax
0x180002ed9  mov     [rbp+57h+var_68], r14
0x180002edd  mov     [rbp+57h+var_60], r14
0x180002ee1  mov     [rbp+57h+var_58], ebx
0x180002ee4  mov     [rbp+57h+var_54], 0FFFFFFFFh
0x180002eeb  mov     [rbp+57h+var_50], 46h ; 'F'
0x180002ef2  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x180002ef9  mov     [rbp+57h+pExceptionObject], rax
0x180002efd  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x180002f04  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180002f08  call    _CxxThrowException_0
```
