# RpcStartListener

- ea: `0x180028900`
- end: `0x180028c33`
- name: `RpcStartListener`
- size: `819`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x180009940`
- `0x18000ba50`
- `0x18000f760`
- `0x1800139c0`
- `0x18002558c`
- `0x180028900`
- `0x180028dd8`
- `0x180028e44`
- `0x180028f88`
- `0x180033f60`
- `0x180049490`
- `0x1800ce010`

## import_xrefs

- `RPCRT4!RpcRevertToSelf` at `0x180028a3a`
- `RPCRT4!RpcRevertToSelf` at `0x180028a3a`
- `RPCRT4!RpcImpersonateClient` at `0x1800289e1`
- `RPCRT4!RpcImpersonateClient` at `0x1800289e1`

## string_xrefs

- `0x180028a03`: `RpcImpersonateClient failed: 0x%x in %s`
- `0x180028aad`: `OpenKey failed: 0x%x in %s`
- `0x180028a76`: `AccessCheck( RESET ) failed: 0x%x in %s`
- `0x180028b36`: `OpenKey( ListenerName ) failed: 0x%x in %s`
- `0x180028b70`: `ReadRegDWord( WIN_ENABLEWINSTATION ) failed: 0x%x in %s`

## pseudocode

```c
__int64 __fastcall RpcStartListener(__int64 a1)
{
  signed int v2; // edi
  RPC_STATUS v3; // eax
  const char *v4; // rdx
  __int64 v5; // rbx
  int v6; // eax
  bool v7; // sf
  int v8; // eax
  int v9; // eax
  int v10; // eax
  int v11; // eax
  int v12; // eax
  const unsigned __int16 *v14; // [rsp+20h] [rbp-E0h]
  const unsigned __int16 *v15; // [rsp+20h] [rbp-E0h]
  unsigned int v16; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v17; // [rsp+38h] [rbp-C8h] BYREF
  _QWORD v18[2]; // [rsp+40h] [rbp-C0h] BYREF
  int v19; // [rsp+50h] [rbp-B0h]
  __int64 v20; // [rsp+58h] [rbp-A8h]
  int v21; // [rsp+60h] [rbp-A0h]
  int v22; // [rsp+64h] [rbp-9Ch]
  _QWORD v23[2]; // [rsp+68h] [rbp-98h] BYREF
  int v24; // [rsp+78h] [rbp-88h]
  HKEY v25; // [rsp+80h] [rbp-80h]
  int v26; // [rsp+88h] [rbp-78h]
  int v27; // [rsp+8Ch] [rbp-74h]
  _BYTE v28[592]; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int16 v29[32]; // [rsp+2E0h] [rbp+1E0h] BYREF

  v23[1] = 0;
  v24 = 0;
  v25 = 0;
  v23[0] = &CRegistry::`vftable';
  v18[0] = &CRegistry::`vftable';
  v26 = -1;
  v27 = -1;
  v18[1] = 0;
  v19 = 0;
  v20 = 0;
  v21 = -1;
  v22 = -1;
  v17 = 0;
  CRpcCallTrace::CRpcCallTrace((CRpcCallTrace *)v28, 1, "RpcStartListener");
  if ( !a1 )
  {
    _DbgPrintMessage(8, "Missing paramter %s in %s", "hListener", "RpcStartListener");
    v2 = -2147024809;
    goto LABEL_35;
  }
  SmartPtr<ITerminal>::operator=(&v17, *(_QWORD *)(a1 + 1592));
  v3 = RpcImpersonateClient(0);
  v2 = v3;
  if ( v3 > 0 )
    v2 = (unsigned __int16)v3 | 0x80070000;
  if ( v2 < 0 )
  {
    v4 = "RpcImpersonateClient failed: 0x%x in %s";
LABEL_7:
    _DbgPrintMessage(8, v4, (unsigned int)v2, "RpcStartListener");
    goto LABEL_35;
  }
  v5 = v17;
  v2 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v17 + 96LL))(v17, 5);
  v6 = RpcRevertToSelf();
  v7 = v6 < 0;
  if ( v6 > 0 )
  {
    v6 = (unsigned __int16)v6 | 0x80070000;
    v7 = v6 < 0;
  }
  if ( v7 )
  {
    v2 = -2147024891;
    _DbgPrintMessage(8, "RpcRevertToSelf failed: 0x%x", v6);
    goto LABEL_35;
  }
  if ( v2 < 0 )
  {
    v4 = "AccessCheck( RESET ) failed: 0x%x in %s";
    goto LABEL_7;
  }
  v8 = CRegistry::OpenKey(
         (CRegistry *)v23,
         HKEY_LOCAL_MACHINE,
         L"System\\CurrentControlSet\\Control\\Terminal Server\\WinStations",
         0x20019u,
         v14);
  v2 = v8;
  if ( v8 > 0 )
    v2 = (unsigned __int16)v8 | 0x80070000;
  if ( v2 < 0 )
  {
    v4 = "OpenKey failed: 0x%x in %s";
    goto LABEL_7;
  }
  v9 = (*(__int64 (__fastcall **)(__int64, unsigned __int16 *, __int64))(*(_QWORD *)v5 + 72LL))(v5, v29, 32);
  v2 = v9;
  if ( v9 < 0 )
  {
    _DbgPrintMessage(8, "Listener->getName failed: 0x%x in %s", (unsigned int)v9, "RpcStartListener");
    goto LABEL_35;
  }
  if ( (g_DebugTraceComponent & 1) != 0 )
    _DbgPrintMessage(2, "Starting Listener %ws", v29);
  v10 = CRegistry::OpenKey((CRegistry *)v18, v25, v29, 0x20019u, v15);
  v2 = v10;
  if ( v10 > 0 )
    v2 = (unsigned __int16)v10 | 0x80070000;
  if ( v2 < 0 )
  {
    v4 = "OpenKey( ListenerName ) failed: 0x%x in %s";
    goto LABEL_7;
  }
  v16 = 0;
  v11 = CRegistry::ReadRegDWord((CRegistry *)v18, L"fEnableWinStation", &v16);
  v2 = v11;
  if ( v11 > 0 )
    v2 = (unsigned __int16)v11 | 0x80070000;
  if ( v2 < 0 )
  {
    v4 = "ReadRegDWord( WIN_ENABLEWINSTATION ) failed: 0x%x in %s";
    goto LABEL_7;
  }
  if ( !v16 )
  {
    _DbgPrintMessage(4, "Listener->Start is denied because of local policy");
    v2 = -2147023636;
    goto LABEL_35;
  }
  v12 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v5 + 24LL))(v5);
  v2 = v12;
  if ( v12 < 0 )
  {
    CHelper::LogErrorEvent(0xC000040B, v12);
    _DbgPrintMessage(8, "Failed to start listener: %ws, 0x%x", v29, (unsigned int)v2);
    v4 = "Listener->Start failed: 0x%x in %s";
    goto LABEL_7;
  }
LABEL_35:
  CRpcCallTrace::~CRpcCallTrace((CRpcCallTrace *)v28);
  SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(&v17);
  CRegistry::~CRegistry((CRegistry *)v18);
  CRegistry::~CRegistry((CRegistry *)v23);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180028900  mov     [rsp-8+arg_8], rbx
0x180028905  mov     [rsp-8+arg_10], rdi
0x18002890a  push    rbp
0x18002890b  push    r14
0x18002890d  push    r15
0x18002890f  lea     rbp, [rsp-230h]
0x180028917  sub     rsp, 330h
0x18002891e  mov     rax, cs:__security_cookie
0x180028925  xor     rax, rsp
0x180028928  mov     [rbp+240h+var_20], rax
0x18002892f  or      eax, 0FFFFFFFFh
0x180028932  mov     [rsp+340h+var_2D0], 0
0x18002893b  mov     rbx, rcx
0x18002893e  mov     [rsp+340h+var_2C8], 0
0x180028946  lea     rcx, ??_7CRegistry@@6B@; const CRegistry::`vftable'
0x18002894d  mov     [rbp+240h+var_2C0], 0
0x180028955  mov     [rsp+340h+var_2D8], rcx
0x18002895a  lea     r14, aRpcstartlisten; "RpcStartListener"
0x180028961  mov     [rsp+340h+var_300], rcx
0x180028966  lea     edx, [rax+2]; int
0x180028969  mov     r8, r14; char *
0x18002896c  mov     [rbp+240h+var_2B8], eax
0x18002896f  lea     rcx, [rbp+240h+var_2B0]; this
0x180028973  mov     [rbp+240h+var_2B4], eax
0x180028976  mov     [rsp+340h+var_2F8], 0
0x18002897f  mov     [rsp+340h+var_2F0], 0
0x180028987  mov     [rsp+340h+var_2E8], 0
0x180028990  mov     [rsp+340h+var_2E0], eax
0x180028994  mov     [rsp+340h+var_2DC], eax
0x180028998  mov     [rsp+340h+var_308], 0
0x1800289a1  call    ??0CRpcCallTrace@@QEAA@HPEBD@Z; CRpcCallTrace::CRpcCallTrace(int,char const *)
0x1800289a6  test    rbx, rbx
0x1800289a9  jnz     short loc_1800289CE
0x1800289ab  mov     r9, r14
0x1800289ae  lea     r8, aHlistener; "hListener"
0x1800289b5  lea     rdx, aMissingParamte; "Missing paramter %s in %s"
0x1800289bc  lea     ecx, [rbx+8]; int
0x1800289bf  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800289c4  mov     edi, 80070057h
0x1800289c9  jmp     loc_180028BE1
0x1800289ce  mov     rdx, [rbx+638h]
0x1800289d5  lea     rcx, [rsp+340h+var_308]
0x1800289da  call    ??4?$SmartPtr@UITerminal@@@@QEAAAEAV0@PEAUITerminal@@@Z; SmartPtr<ITerminal>::operator=(ITerminal *)
0x1800289df  xor     ecx, ecx; BindingHandle
0x1800289e1  call    cs:__imp_RpcImpersonateClient
0x1800289e8  nop     dword ptr [rax+rax+00h]
0x1800289ed  mov     edi, eax
0x1800289ef  mov     r15d, 80070000h
0x1800289f5  test    eax, eax
0x1800289f7  jle     short loc_1800289FF
0x1800289f9  movzx   edi, ax
0x1800289fc  or      edi, r15d
0x1800289ff  test    edi, edi
0x180028a01  jns     short loc_180028A1F
0x180028a03  lea     rdx, aRpcimpersonate; "RpcImpersonateClient failed: 0x%x in %s"
0x180028a0a  mov     r8d, edi
0x180028a0d  mov     r9, r14
0x180028a10  mov     ecx, 8; int
0x180028a15  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180028a1a  jmp     loc_180028BE1
0x180028a1f  mov     rbx, [rsp+340h+var_308]
0x180028a24  mov     edx, 5
0x180028a29  mov     rcx, rbx
0x180028a2c  mov     rax, [rbx]
0x180028a2f  mov     rax, [rax+60h]
0x180028a33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028a38  mov     edi, eax
0x180028a3a  call    cs:__imp_RpcRevertToSelf
0x180028a41  nop     dword ptr [rax+rax+00h]
0x180028a46  test    eax, eax
0x180028a48  jle     short loc_180028A52
0x180028a4a  movzx   eax, ax
0x180028a4d  or      eax, r15d
0x180028a50  test    eax, eax
0x180028a52  jns     short loc_180028A72
0x180028a54  mov     r8d, eax
0x180028a57  lea     rdx, aRpcreverttosel_1; "RpcRevertToSelf failed: 0x%x"
0x180028a5e  mov     ecx, 8; int
0x180028a63  mov     edi, 80070005h
0x180028a68  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180028a6d  jmp     loc_180028BE1
0x180028a72  test    edi, edi
0x180028a74  jns     short loc_180028A7F
0x180028a76  lea     rdx, aAccesscheckRes; "AccessCheck( RESET ) failed: 0x%x in %s"
0x180028a7d  jmp     short loc_180028A0A
0x180028a7f  mov     r9d, 20019h; unsigned int
0x180028a85  lea     r8, SubKey; "System\\CurrentControlSet\\Control\\Ter"...
0x180028a8c  mov     rdx, 0FFFFFFFF80000002h; HKEY
0x180028a93  lea     rcx, [rsp+340h+var_2D8]; this
0x180028a98  call    ?OpenKey@CRegistry@@QEAAKPEAUHKEY__@@PEBGK1@Z; CRegistry::OpenKey(HKEY__ *,ushort const *,ulong,ushort const *)
0x180028a9d  mov     edi, eax
0x180028a9f  test    eax, eax
0x180028aa1  jle     short loc_180028AA9
0x180028aa3  movzx   edi, ax
0x180028aa6  or      edi, r15d
0x180028aa9  test    edi, edi
0x180028aab  jns     short loc_180028AB9
0x180028aad  lea     rdx, aOpenkeyFailed0; "OpenKey failed: 0x%x in %s"
0x180028ab4  jmp     loc_180028A0A
0x180028ab9  mov     rax, [rbx]
0x180028abc  lea     rdx, [rbp+240h+var_60]
0x180028ac3  mov     r8d, 20h ; ' '
0x180028ac9  mov     rcx, rbx
0x180028acc  mov     rax, [rax+48h]
0x180028ad0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028ad5  mov     edi, eax
0x180028ad7  test    eax, eax
0x180028ad9  jns     short loc_180028AEA
0x180028adb  mov     r8d, eax
0x180028ade  lea     rdx, aListenerGetnam; "Listener->getName failed: 0x%x in %s"
0x180028ae5  jmp     loc_180028A0D
0x180028aea  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 1; ulong g_DebugTraceComponent
0x180028af1  jz      short loc_180028B0B
0x180028af3  lea     r8, [rbp+240h+var_60]
0x180028afa  mov     ecx, 2; int
0x180028aff  lea     rdx, aStartingListen; "Starting Listener %ws"
0x180028b06  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180028b0b  mov     rdx, [rbp+240h+var_2C0]; HKEY
0x180028b0f  lea     r8, [rbp+240h+var_60]; unsigned __int16 *
0x180028b16  mov     r9d, 20019h; unsigned int
0x180028b1c  lea     rcx, [rsp+340h+var_300]; this
0x180028b21  call    ?OpenKey@CRegistry@@QEAAKPEAUHKEY__@@PEBGK1@Z; CRegistry::OpenKey(HKEY__ *,ushort const *,ulong,ushort const *)
0x180028b26  mov     edi, eax
0x180028b28  test    eax, eax
0x180028b2a  jle     short loc_180028B32
0x180028b2c  movzx   edi, ax
0x180028b2f  or      edi, r15d
0x180028b32  test    edi, edi
0x180028b34  jns     short loc_180028B42
0x180028b36  lea     rdx, aOpenkeyListene; "OpenKey( ListenerName ) failed: 0x%x in"...
0x180028b3d  jmp     loc_180028A0A
0x180028b42  lea     r8, [rsp+340h+var_310]; unsigned int *
0x180028b47  mov     [rsp+340h+var_310], 0
0x180028b4f  lea     rdx, aFenablewinstat; "fEnableWinStation"
0x180028b56  lea     rcx, [rsp+340h+var_300]; this
0x180028b5b  call    ?ReadRegDWord@CRegistry@@QEAAKPEBGPEAK@Z; CRegistry::ReadRegDWord(ushort const *,ulong *)
0x180028b60  mov     edi, eax
0x180028b62  test    eax, eax
0x180028b64  jle     short loc_180028B6C
0x180028b66  movzx   edi, ax
0x180028b69  or      edi, r15d
0x180028b6c  test    edi, edi
0x180028b6e  jns     short loc_180028B7C
0x180028b70  lea     rdx, aReadregdwordWi; "ReadRegDWord( WIN_ENABLEWINSTATION ) fa"...
0x180028b77  jmp     loc_180028A0A
0x180028b7c  cmp     [rsp+340h+var_310], 0
0x180028b81  jz      short loc_180028BCB
0x180028b83  mov     rax, [rbx]
0x180028b86  mov     rcx, rbx
0x180028b89  mov     rax, [rax+18h]
0x180028b8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028b92  mov     edi, eax
0x180028b94  test    eax, eax
0x180028b96  jns     short loc_180028BE1
0x180028b98  mov     edx, eax; int
0x180028b9a  mov     ecx, 0C000040Bh; unsigned int
0x180028b9f  call    ?LogErrorEvent@CHelper@@SAJIJ@Z; CHelper::LogErrorEvent(uint,long)
0x180028ba4  mov     r9d, edi
0x180028ba7  lea     r8, [rbp+240h+var_60]
0x180028bae  lea     rdx, aFailedToStartL; "Failed to start listener: %ws, 0x%x"
0x180028bb5  mov     ecx, 8; int
0x180028bba  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180028bbf  lea     rdx, aListenerStartF; "Listener->Start failed: 0x%x in %s"
0x180028bc6  jmp     loc_180028A0A
0x180028bcb  lea     rdx, aListenerStartI; "Listener->Start is denied because of lo"...
0x180028bd2  mov     ecx, 4; int
0x180028bd7  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180028bdc  mov     edi, 800704ECh
0x180028be1  lea     rcx, [rbp+240h+var_2B0]; this
0x180028be5  call    ??1CRpcCallTrace@@UEAA@XZ; CRpcCallTrace::~CRpcCallTrace(void)
0x180028bea  lea     rcx, [rsp+340h+var_308]; void *
0x180028bef  call    ??1?$SmartPtr@VCConnectionHandlerItem@@@@QEAA@XZ; SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(void)
0x180028bf4  lea     rcx, [rsp+340h+var_300]; this
0x180028bf9  call    ??1CRegistry@@UEAA@XZ; CRegistry::~CRegistry(void)
0x180028bfe  lea     rcx, [rsp+340h+var_2D8]; this
0x180028c03  call    ??1CRegistry@@UEAA@XZ; CRegistry::~CRegistry(void)
0x180028c08  mov     eax, edi
0x180028c0a  mov     rcx, [rbp+240h+var_20]
0x180028c11  xor     rcx, rsp; StackCookie
0x180028c14  call    __security_check_cookie
0x180028c19  lea     r11, [rsp+340h+var_10]
0x180028c21  mov     rbx, [r11+28h]
0x180028c25  mov     rdi, [r11+30h]
0x180028c29  mov     rsp, r11
0x180028c2c  pop     r15
0x180028c2e  pop     r14
0x180028c30  pop     rbp
0x180028c31  retn
```
