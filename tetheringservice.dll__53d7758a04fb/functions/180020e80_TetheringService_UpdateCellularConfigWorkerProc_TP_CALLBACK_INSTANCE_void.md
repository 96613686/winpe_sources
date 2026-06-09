# TetheringService::UpdateCellularConfigWorkerProc(_TP_CALLBACK_INSTANCE *,void *)

- ea: `0x180020e80`
- end: `0x180020f44`
- name: `?UpdateCellularConfigWorkerProc@TetheringService@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAX@Z`
- size: `196`
- prototype: `void __stdcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, registry_config, service_task, installer_update`

## callees

- `0x180002960`
- `0x18000bf4c`
- `0x180018f64`
- `0x180020e80`
- `0x180033010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall TetheringService::UpdateCellularConfigWorkerProc(PTP_CALLBACK_INSTANCE Instance, int *Context)
{
  int v3; // edi
  TetheringService *v4; // rbx

  if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 229, &WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids);
  }
  v3 = *Context;
  operator delete(Context);
  v4 = *(TetheringService **)g_pTetheringSessionId.Data4;
  if ( *(_QWORD *)g_pTetheringSessionId.Data4 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)g_pTetheringSessionId.Data4 + 8LL))(*(_QWORD *)g_pTetheringSessionId.Data4);
  if ( v4 )
    TetheringService::HandleCellularConfigWnfChange(v4, v3);
  if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 230, &WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids);
  }
  if ( v4 )
    (*(void (__fastcall **)(TetheringService *))(*(_QWORD *)v4 + 16LL))(v4);
}

```

## disassembly

```asm
0x180020e80  mov     [rsp+arg_0], rbx
0x180020e85  mov     [rsp+arg_8], rsi
0x180020e8a  push    rdi
0x180020e8b  sub     rsp, 20h
0x180020e8f  mov     rbx, rdx
0x180020e92  lea     rsi, WPP_GLOBAL_Control
0x180020e99  mov     rcx, cs:WPP_GLOBAL_Control
0x180020ea0  cmp     rcx, rsi
0x180020ea3  jz      short loc_180020EC0
0x180020ea5  test    byte ptr [rcx+1Ch], 8
0x180020ea9  jz      short loc_180020EC0
0x180020eab  mov     edx, 0E5h
0x180020eb0  lea     r8, WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids
0x180020eb7  mov     rcx, [rcx+10h]
0x180020ebb  call    WPP_SF_
0x180020ec0  mov     edi, [rbx]
0x180020ec2  xor     edx, edx
0x180020ec4  mov     rcx, rbx; Block
0x180020ec7  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180020ecc  mov     rbx, qword ptr cs:?g_pTetheringSessionId@@3PEAU_GUID@@EA.Data4; _GUID * g_pTetheringSessionId ...
0x180020ed3  test    rbx, rbx
0x180020ed6  jz      short loc_180020EE8
0x180020ed8  mov     rax, [rbx]
0x180020edb  mov     rcx, rbx
0x180020ede  mov     rax, [rax+8]
0x180020ee2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020ee7  nop
0x180020ee8  test    rbx, rbx
0x180020eeb  jz      short loc_180020EF7
0x180020eed  mov     edx, edi; unsigned int
0x180020eef  mov     rcx, rbx; this
0x180020ef2  call    ?HandleCellularConfigWnfChange@TetheringService@@AEAAXK@Z; TetheringService::HandleCellularConfigWnfChange(ulong)
0x180020ef7  mov     rcx, cs:WPP_GLOBAL_Control
0x180020efe  cmp     rcx, rsi
0x180020f01  jz      short loc_180020F1F
0x180020f03  test    byte ptr [rcx+1Ch], 8
0x180020f07  jz      short loc_180020F1F
0x180020f09  mov     edx, 0E6h
0x180020f0e  lea     r8, WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids
0x180020f15  mov     rcx, [rcx+10h]
0x180020f19  call    WPP_SF_
0x180020f1e  nop
0x180020f1f  test    rbx, rbx
0x180020f22  jz      short loc_180020F34
0x180020f24  mov     rax, [rbx]
0x180020f27  mov     rcx, rbx
0x180020f2a  mov     rax, [rax+10h]
0x180020f2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020f33  nop
0x180020f34  mov     rbx, [rsp+28h+arg_0]
0x180020f39  mov     rsi, [rsp+28h+arg_8]
0x180020f3e  add     rsp, 20h
0x180020f42  pop     rdi
0x180020f43  retn
```
