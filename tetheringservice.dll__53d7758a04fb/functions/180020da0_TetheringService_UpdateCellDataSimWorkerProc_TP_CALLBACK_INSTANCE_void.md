# TetheringService::UpdateCellDataSimWorkerProc(_TP_CALLBACK_INSTANCE *,void *)

- ea: `0x180020da0`
- end: `0x180020e6b`
- name: `?UpdateCellDataSimWorkerProc@TetheringService@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAX@Z`
- size: `203`
- prototype: `void __stdcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, service_task, installer_update`

## callees

- `0x180002960`
- `0x18000bf4c`
- `0x180019034`
- `0x180020da0`
- `0x180033010`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall TetheringService::UpdateCellDataSimWorkerProc(PTP_CALLBACK_INSTANCE Instance, char *Context)
{
  char v3; // di
  TetheringService *v4; // rbx

  if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 227, &WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids);
  }
  v3 = *Context;
  operator delete(Context);
  v4 = *(TetheringService **)g_pTetheringSessionId.Data4;
  if ( *(_QWORD *)g_pTetheringSessionId.Data4 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)g_pTetheringSessionId.Data4 + 8LL))(*(_QWORD *)g_pTetheringSessionId.Data4);
  if ( v4 )
    TetheringService::HandleDataWnfChange(v4, v3);
  if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 228, &WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids);
  }
  if ( v4 )
    (*(void (__fastcall **)(TetheringService *))(*(_QWORD *)v4 + 16LL))(v4);
}

```

## disassembly

```asm
0x180020da0  mov     [rsp+arg_0], rbx
0x180020da5  mov     [rsp+arg_10], rsi
0x180020daa  push    rdi
0x180020dab  sub     rsp, 20h
0x180020daf  mov     rbx, rdx
0x180020db2  lea     rsi, WPP_GLOBAL_Control
0x180020db9  mov     rcx, cs:WPP_GLOBAL_Control
0x180020dc0  cmp     rcx, rsi
0x180020dc3  jz      short loc_180020DE0
0x180020dc5  test    byte ptr [rcx+1Ch], 8
0x180020dc9  jz      short loc_180020DE0
0x180020dcb  mov     edx, 0E3h
0x180020dd0  lea     r8, WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids
0x180020dd7  mov     rcx, [rcx+10h]
0x180020ddb  call    WPP_SF_
0x180020de0  mov     dil, [rbx]
0x180020de3  xor     edx, edx
0x180020de5  mov     rcx, rbx; Block
0x180020de8  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180020ded  mov     rbx, qword ptr cs:?g_pTetheringSessionId@@3PEAU_GUID@@EA.Data4; _GUID * g_pTetheringSessionId ...
0x180020df4  mov     [rsp+28h+arg_8], rbx
0x180020df9  test    rbx, rbx
0x180020dfc  jz      short loc_180020E0E
0x180020dfe  mov     rax, [rbx]
0x180020e01  mov     rcx, rbx
0x180020e04  mov     rax, [rax+8]
0x180020e08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020e0d  nop
0x180020e0e  test    rbx, rbx
0x180020e11  jz      short loc_180020E1E
0x180020e13  mov     dl, dil; unsigned __int8
0x180020e16  mov     rcx, rbx; this
0x180020e19  call    ?HandleDataWnfChange@TetheringService@@AEAAXE@Z; TetheringService::HandleDataWnfChange(uchar)
0x180020e1e  mov     rcx, cs:WPP_GLOBAL_Control
0x180020e25  cmp     rcx, rsi
0x180020e28  jz      short loc_180020E46
0x180020e2a  test    byte ptr [rcx+1Ch], 8
0x180020e2e  jz      short loc_180020E46
0x180020e30  mov     edx, 0E4h
0x180020e35  lea     r8, WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids
0x180020e3c  mov     rcx, [rcx+10h]
0x180020e40  call    WPP_SF_
0x180020e45  nop
0x180020e46  test    rbx, rbx
0x180020e49  jz      short loc_180020E5B
0x180020e4b  mov     rax, [rbx]
0x180020e4e  mov     rcx, rbx
0x180020e51  mov     rax, [rax+10h]
0x180020e55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020e5a  nop
0x180020e5b  mov     rbx, [rsp+28h+arg_0]
0x180020e60  mov     rsi, [rsp+28h+arg_10]
0x180020e65  add     rsp, 20h
0x180020e69  pop     rdi
0x180020e6a  retn
```
