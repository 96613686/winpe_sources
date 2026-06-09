# CreateGuid(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x180012f20`
- end: `0x1800130d7`
- name: `?CreateGuid@@YAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `439`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180017510`
- `0x18001bdac`

## callees

- `0x18000195c`
- `0x180002510`
- `0x1800032dc`
- `0x18000669c`
- `0x180012f20`
- `0x18001fe50`

## import_xrefs

- `RPCRT4!UuidCreate` at `0x180012f5b`
- `RPCRT4!UuidCreate` at `0x180012f5b`
- `RPCRT4!UuidToStringW` at `0x180012ff6`
- `RPCRT4!UuidToStringW` at `0x180012ff6`
- `RPCRT4!RpcStringFreeW` at `0x180013089`

## string_xrefs

- `0x180012fa6`: `admin\wmi\events\forwarding\common\miscutil.cpp`
- `0x180013041`: `admin\wmi\events\forwarding\common\miscutil.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CreateGuid(__int64 a1)
{
  unsigned int v2; // eax
  unsigned int v3; // ebx
  unsigned int v4; // eax
  unsigned int v5; // ebx
  RPC_WSTR StringUuid; // [rsp+20h] [rbp-19h] BYREF
  void **pExceptionObject; // [rsp+28h] [rbp-11h] BYREF
  char v9; // [rsp+30h] [rbp-9h]
  const char *v10; // [rsp+38h] [rbp-1h]
  __int64 v11; // [rsp+40h] [rbp+7h]
  __int64 v12; // [rsp+48h] [rbp+Fh]
  unsigned int v13; // [rsp+50h] [rbp+17h]
  int v14; // [rsp+54h] [rbp+1Bh]
  int v15; // [rsp+58h] [rbp+1Fh]
  char v16[8]; // [rsp+60h] [rbp+27h] BYREF
  RPC_STATUS (__stdcall *v17)(RPC_WSTR *); // [rsp+68h] [rbp+2Fh]
  RPC_WSTR *p_StringUuid; // [rsp+70h] [rbp+37h]
  UUID Uuid; // [rsp+78h] [rbp+3Fh] BYREF

  Uuid = 0;
  StringUuid = 0;
  v2 = UuidCreate(&Uuid);
  v3 = v2;
  if ( v2 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_c2175ded1375322cff14e2fdbd13448a_Traceguids, v2);
    }
    v9 = 0;
    v10 = "admin\\wmi\\events\\forwarding\\common\\miscutil.cpp";
    v11 = 0;
    v12 = 0;
    v13 = v3;
    v14 = -1;
    v15 = 278;
    pExceptionObject = &wmi::GenericException::`vftable';
    throw (wmi::GenericException *)&pExceptionObject;
  }
  v4 = UuidToStringW(&Uuid, &StringUuid);
  v5 = v4;
  if ( v4 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_c2175ded1375322cff14e2fdbd13448a_Traceguids, v4);
    }
    v9 = 0;
    v10 = "admin\\wmi\\events\\forwarding\\common\\miscutil.cpp";
    v11 = 0;
    v12 = 0;
    v13 = v5;
    v14 = -1;
    v15 = 282;
    pExceptionObject = &wmi::GenericException::`vftable';
    throw (wmi::GenericException *)&pExceptionObject;
  }
  v16[0] = 0;
  v17 = RpcStringFreeW;
  p_StringUuid = &StringUuid;
  std::wstring::assign(a1, (__int64)StringUuid);
  return wmi::ScopeGuardImpl1<void (*)(std::vector<std::vector<unsigned short>> *),std::vector<std::vector<unsigned short>> *>::~ScopeGuardImpl1<void (*)(std::vector<std::vector<unsigned short>> *),std::vector<std::vector<unsigned short>> *>((__int64)v16);
}

```

## disassembly

```asm
0x180012f20  mov     [rsp-8+arg_8], rbx
0x180012f25  mov     [rsp-8+arg_10], rdi
0x180012f2a  push    rbp
0x180012f2b  lea     rbp, [rsp-57h]
0x180012f30  sub     rsp, 90h
0x180012f37  mov     rax, cs:__security_cookie
0x180012f3e  xor     rax, rsp
0x180012f41  mov     [rbp+57h+var_8], rax
0x180012f45  mov     rdi, rcx
0x180012f48  xorps   xmm0, xmm0
0x180012f4b  movups  xmmword ptr [rbp+57h+Uuid.Data1], xmm0
0x180012f4f  mov     [rbp+57h+StringUuid], 0
0x180012f57  lea     rcx, [rbp+57h+Uuid]; Uuid
0x180012f5b  call    cs:__imp_UuidCreate
0x180012f61  mov     ebx, eax
0x180012f63  test    eax, eax
0x180012f65  jz      loc_180012FEE
0x180012f6b  lea     rdx, WPP_GLOBAL_Control
0x180012f72  mov     rcx, cs:WPP_GLOBAL_Control
0x180012f79  cmp     rcx, rdx
0x180012f7c  jz      short loc_180012FA2
0x180012f7e  test    byte ptr [rcx+1Ch], 1
0x180012f82  jz      short loc_180012FA2
0x180012f84  cmp     byte ptr [rcx+19h], 2
0x180012f88  jb      short loc_180012FA2
0x180012f8a  mov     edx, 12h
0x180012f8f  mov     r9d, eax
0x180012f92  lea     r8, WPP_c2175ded1375322cff14e2fdbd13448a_Traceguids
0x180012f99  mov     rcx, [rcx+10h]
0x180012f9d  call    WPP_SF_D
0x180012fa2  mov     [rbp+57h+var_60], 0
0x180012fa6  lea     rax, aAdminWmiEvents_5; "admin\\wmi\\events\\forwarding\\common"...
0x180012fad  mov     [rbp+57h+var_58], rax
0x180012fb1  mov     [rbp+57h+var_50], 0
0x180012fb9  mov     [rbp+57h+var_48], 0
0x180012fc1  mov     [rbp+57h+var_40], ebx
0x180012fc4  mov     [rbp+57h+var_3C], 0FFFFFFFFh
0x180012fcb  mov     [rbp+57h+var_38], 116h
0x180012fd2  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x180012fd9  mov     [rbp+57h+pExceptionObject], rax
0x180012fdd  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x180012fe4  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180012fe8  call    _CxxThrowException_0
0x180012fee  lea     rdx, [rbp+57h+StringUuid]; StringUuid
0x180012ff2  lea     rcx, [rbp+57h+Uuid]; Uuid
0x180012ff6  call    cs:__imp_UuidToStringW
0x180012ffc  mov     ebx, eax
0x180012ffe  test    eax, eax
0x180013000  jz      loc_180013089
0x180013006  lea     rdx, WPP_GLOBAL_Control
0x18001300d  mov     rcx, cs:WPP_GLOBAL_Control
0x180013014  cmp     rcx, rdx
0x180013017  jz      short loc_18001303D
0x180013019  test    byte ptr [rcx+1Ch], 1
0x18001301d  jz      short loc_18001303D
0x18001301f  cmp     byte ptr [rcx+19h], 2
0x180013023  jb      short loc_18001303D
0x180013025  mov     edx, 13h
0x18001302a  mov     r9d, eax
0x18001302d  lea     r8, WPP_c2175ded1375322cff14e2fdbd13448a_Traceguids
0x180013034  mov     rcx, [rcx+10h]
0x180013038  call    WPP_SF_D
0x18001303d  mov     [rbp+57h+var_60], 0
0x180013041  lea     rax, aAdminWmiEvents_5; "admin\\wmi\\events\\forwarding\\common"...
0x180013048  mov     [rbp+57h+var_58], rax
0x18001304c  mov     [rbp+57h+var_50], 0
0x180013054  mov     [rbp+57h+var_48], 0
0x18001305c  mov     [rbp+57h+var_40], ebx
0x18001305f  mov     [rbp+57h+var_3C], 0FFFFFFFFh
0x180013066  mov     [rbp+57h+var_38], 11Ah
0x18001306d  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x180013074  mov     [rbp+57h+pExceptionObject], rax
0x180013078  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x18001307f  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180013083  call    _CxxThrowException_0
0x180013089  mov     rax, cs:__imp_RpcStringFreeW
0x180013090  mov     [rbp+57h+var_30], 0
0x180013094  mov     [rbp+57h+var_28], rax
0x180013098  lea     rax, [rbp+57h+StringUuid]
0x18001309c  mov     [rbp+57h+var_20], rax
0x1800130a0  mov     rdx, [rbp+57h+StringUuid]
0x1800130a4  mov     rcx, rdi
0x1800130a7  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::assign(ushort const *)
0x1800130ac  nop
0x1800130ad  lea     rcx, [rbp+57h+var_30]
0x1800130b1  call    ??1?$ScopeGuardImpl1@P6AXPEAV?$vector@V?$vector@GV?$allocator@G@std@@@std@@V?$allocator@V?$vector@GV?$allocator@G@std@@@std@@@2@@std@@@ZPEAV12@@wmi@@QEAA@XZ; wmi::ScopeGuardImpl1<void (*)(std::vector<std::vector<ushort>> *),std::vector<std::vector<ushort>> *>::~ScopeGuardImpl1<void (*)(std::vector<std::vector<ushort>> *),std::vector<std::vector<ushort>> *>(void)
0x1800130b6  mov     rcx, [rbp+57h+var_8]
0x1800130ba  xor     rcx, rsp; StackCookie
0x1800130bd  call    __security_check_cookie
0x1800130c2  lea     r11, [rsp+90h+var_s0]
0x1800130ca  mov     rbx, [r11+18h]
0x1800130ce  mov     rdi, [r11+20h]
0x1800130d2  mov     rsp, r11
0x1800130d5  pop     rbp
0x1800130d6  retn
```
