# TetheringService::DisableGlobalSharing(void)

- ea: `0x180016b68`
- end: `0x180016cc7`
- name: `?DisableGlobalSharing@TetheringService@@AEAAJXZ`
- size: `351`
- prototype: `__int64 __fastcall(TetheringService *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18001afb4`

## callees

- `0x18000bf4c`
- `0x18000bf74`
- `0x18000d8e4`
- `0x180016b68`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180016bcc`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180016bcc`

## pseudocode

```c
__int64 __fastcall TetheringService::DisableGlobalSharing(TetheringService *this)
{
  HRESULT v1; // eax
  unsigned int v2; // ebx
  TetheringServiceTelemetry *v3; // rcx
  __int64 v4; // rdx
  TetheringService *v6; // [rsp+50h] [rbp+8h] BYREF
  int v7; // [rsp+58h] [rbp+10h] BYREF
  LPVOID ppv; // [rsp+60h] [rbp+18h] BYREF

  v6 = this;
  if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 409, &WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids);
  }
  ppv = 0;
  v1 = CoCreateInstance(&CLSID_HNetCfgMgr, 0, 0x17u, &GUID_85d18b6f_3032_11d4_9348_00c04f8eeb71, &ppv);
  v2 = v1;
  if ( v1 < 0 )
  {
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (TetheringServiceTelemetry *)&WPP_GLOBAL_Control )
      goto LABEL_20;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_17;
    v4 = 410;
    goto LABEL_8;
  }
  v7 = 0;
  LODWORD(v6) = 0;
  v1 = (*(__int64 (__fastcall **)(LPVOID, int *, TetheringService **))(*(_QWORD *)ppv + 40LL))(ppv, &v7, &v6);
  v2 = v1;
  if ( v1 < 0 )
  {
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (TetheringServiceTelemetry *)&WPP_GLOBAL_Control )
      goto LABEL_20;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_17;
    v4 = 411;
LABEL_8:
    WPP_SF_d(*((_QWORD *)v3 + 2), v4, &WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids, (unsigned int)v1);
LABEL_16:
    v3 = WPP_GLOBAL_Control;
    goto LABEL_17;
  }
  v3 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (TetheringServiceTelemetry *)&WPP_GLOBAL_Control )
    goto LABEL_20;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 412, &WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids);
    goto LABEL_16;
  }
LABEL_17:
  if ( v3 != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control && (*((_BYTE *)v3 + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)v3 + 2), 413, &WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids);
LABEL_20:
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  return v2;
}

```

## disassembly

```asm
0x180016b68  mov     [rsp+arg_0], rcx
0x180016b6d  push    rbx
0x180016b6e  push    rsi
0x180016b6f  push    rdi
0x180016b70  sub     rsp, 30h
0x180016b74  lea     rdi, WPP_GLOBAL_Control
0x180016b7b  lea     rsi, WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids
0x180016b82  mov     rcx, cs:WPP_GLOBAL_Control
0x180016b89  cmp     rcx, rdi
0x180016b8c  jz      short loc_180016BA5
0x180016b8e  test    byte ptr [rcx+1Ch], 8
0x180016b92  jz      short loc_180016BA5
0x180016b94  mov     edx, 199h
0x180016b99  mov     r8, rsi
0x180016b9c  mov     rcx, [rcx+10h]
0x180016ba0  call    WPP_SF_
0x180016ba5  mov     [rsp+48h+arg_10], 0
0x180016bae  lea     rax, [rsp+48h+arg_10]
0x180016bb3  mov     [rsp+48h+ppv], rax; ppv
0x180016bb8  lea     r9, _GUID_85d18b6f_3032_11d4_9348_00c04f8eeb71; riid
0x180016bbf  xor     edx, edx; pUnkOuter
0x180016bc1  lea     r8d, [rdx+17h]; dwClsContext
0x180016bc5  lea     rcx, CLSID_HNetCfgMgr; rclsid
0x180016bcc  call    cs:__imp_CoCreateInstance
0x180016bd2  mov     ebx, eax
0x180016bd4  test    eax, eax
0x180016bd6  jns     short loc_180016C08
0x180016bd8  mov     rcx, cs:WPP_GLOBAL_Control
0x180016bdf  cmp     rcx, rdi
0x180016be2  jz      loc_180016CA6
0x180016be8  test    byte ptr [rcx+1Ch], 1
0x180016bec  jz      loc_180016C89
0x180016bf2  mov     edx, 19Ah
0x180016bf7  mov     r9d, eax
0x180016bfa  mov     r8, rsi
0x180016bfd  mov     rcx, [rcx+10h]
0x180016c01  call    WPP_SF_d
0x180016c06  jmp     short loc_180016C82
0x180016c08  mov     [rsp+48h+arg_8], 0
0x180016c10  mov     dword ptr [rsp+48h+arg_0], 0
0x180016c18  mov     rcx, [rsp+48h+arg_10]
0x180016c1d  mov     rax, [rcx]
0x180016c20  lea     r8, [rsp+48h+arg_0]
0x180016c25  lea     rdx, [rsp+48h+arg_8]
0x180016c2a  mov     rax, [rax+28h]
0x180016c2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016c33  mov     ebx, eax
0x180016c35  test    eax, eax
0x180016c37  jns     short loc_180016C52
0x180016c39  mov     rcx, cs:WPP_GLOBAL_Control
0x180016c40  cmp     rcx, rdi
0x180016c43  jz      short loc_180016CA6
0x180016c45  test    byte ptr [rcx+1Ch], 1
0x180016c49  jz      short loc_180016C89
0x180016c4b  mov     edx, 19Bh
0x180016c50  jmp     short loc_180016BF7
0x180016c52  mov     rcx, cs:WPP_GLOBAL_Control
0x180016c59  cmp     rcx, rdi
0x180016c5c  jz      short loc_180016CA6
0x180016c5e  test    byte ptr [rcx+1Ch], 4
0x180016c62  jz      short loc_180016C89
0x180016c64  mov     edx, 19Ch
0x180016c69  mov     eax, dword ptr [rsp+48h+arg_0]
0x180016c6d  mov     dword ptr [rsp+48h+ppv], eax
0x180016c71  mov     r9d, [rsp+48h+arg_8]
0x180016c76  mov     r8, rsi
0x180016c79  mov     rcx, [rcx+10h]
0x180016c7d  call    WPP_SF_dd
0x180016c82  mov     rcx, cs:WPP_GLOBAL_Control
0x180016c89  cmp     rcx, rdi
0x180016c8c  jz      short loc_180016CA6
0x180016c8e  test    byte ptr [rcx+1Ch], 8
0x180016c92  jz      short loc_180016CA6
0x180016c94  mov     edx, 19Dh
0x180016c99  mov     r8, rsi
0x180016c9c  mov     rcx, [rcx+10h]
0x180016ca0  call    WPP_SF_
0x180016ca5  nop
0x180016ca6  mov     rcx, [rsp+48h+arg_10]
0x180016cab  test    rcx, rcx
0x180016cae  jz      short loc_180016CBD
0x180016cb0  mov     rax, [rcx]
0x180016cb3  mov     rax, [rax+10h]
0x180016cb7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016cbc  nop
0x180016cbd  mov     eax, ebx
0x180016cbf  add     rsp, 30h
0x180016cc3  pop     rdi
0x180016cc4  pop     rsi
0x180016cc5  pop     rbx
0x180016cc6  retn
```
