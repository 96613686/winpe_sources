# TetheringService::SharedAccessWnfCallback(_WNF_STATE_NAME,ulong,_WNF_TYPE_ID *,void *,void const *,ulong)

- ea: `0x18001db10`
- end: `0x18001dc02`
- name: `?SharedAccessWnfCallback@TetheringService@@CAJU_WNF_STATE_NAME@@KPEAU_WNF_TYPE_ID@@PEAXPEBXK@Z`
- size: `242`
- prototype: `__int64 __fastcall(struct _WNF_STATE_NAME, __int64, struct _WNF_TYPE_ID *, void *)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, installer_update`

## callees

- `0x18000bf4c`
- `0x18001db10`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x18001db87`
- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x18001db87`

## pseudocode

```c
__int64 __fastcall TetheringService::SharedAccessWnfCallback(
        struct _WNF_STATE_NAME a1,
        __int64 a2,
        struct _WNF_TYPE_ID *a3,
        void *a4)
{
  TetheringServiceTelemetry *v4; // rcx
  __int64 v5; // rbx

  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 366, &WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids);
    v4 = WPP_GLOBAL_Control;
  }
  v5 = *(_QWORD *)g_pTetheringSessionId.Data4;
  if ( *(_QWORD *)g_pTetheringSessionId.Data4 )
  {
    (*(void (__fastcall **)(_QWORD, __int64, struct _WNF_TYPE_ID *, void *))(**(_QWORD **)g_pTetheringSessionId.Data4
                                                                           + 8LL))(
      *(_QWORD *)g_pTetheringSessionId.Data4,
      a2,
      a3,
      a4);
    v4 = WPP_GLOBAL_Control;
  }
  if ( !v5 )
    goto LABEL_12;
  if ( TrySubmitThreadpoolCallback(
         TetheringService::UpdatePeerListWorkerProc,
         (PVOID)v5,
         (PTP_CALLBACK_ENVIRON)(v5 + 1808)) )
  {
    goto LABEL_11;
  }
  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (TetheringServiceTelemetry *)&WPP_GLOBAL_Control )
    goto LABEL_15;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 367, &WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids);
LABEL_11:
    v4 = WPP_GLOBAL_Control;
  }
LABEL_12:
  if ( v4 != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)v4 + 2), 368, &WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids);
LABEL_15:
  if ( v5 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
  return 0;
}

```

## disassembly

```asm
0x18001db10  mov     [rsp+arg_0], rbx
0x18001db15  push    rdi
0x18001db16  sub     rsp, 20h
0x18001db1a  lea     rdi, WPP_GLOBAL_Control
0x18001db21  mov     rcx, cs:WPP_GLOBAL_Control
0x18001db28  cmp     rcx, rdi
0x18001db2b  jz      short loc_18001DB4F
0x18001db2d  test    byte ptr [rcx+1Ch], 8
0x18001db31  jz      short loc_18001DB4F
0x18001db33  mov     edx, 16Eh
0x18001db38  lea     r8, WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids
0x18001db3f  mov     rcx, [rcx+10h]
0x18001db43  call    WPP_SF_
0x18001db48  mov     rcx, cs:WPP_GLOBAL_Control
0x18001db4f  mov     rbx, qword ptr cs:?g_pTetheringSessionId@@3PEAU_GUID@@EA.Data4; _GUID * g_pTetheringSessionId ...
0x18001db56  test    rbx, rbx
0x18001db59  jz      short loc_18001DB71
0x18001db5b  mov     rax, [rbx]
0x18001db5e  mov     rcx, rbx
0x18001db61  mov     rax, [rax+8]
0x18001db65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001db6a  mov     rcx, cs:WPP_GLOBAL_Control
0x18001db71  test    rbx, rbx
0x18001db74  jz      short loc_18001DBBF
0x18001db76  lea     r8, [rbx+710h]; pcbe
0x18001db7d  mov     rdx, rbx; pv
0x18001db80  lea     rcx, ?UpdatePeerListWorkerProc@TetheringService@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAX@Z; pfns
0x18001db87  call    cs:__imp_TrySubmitThreadpoolCallback
0x18001db8d  test    eax, eax
0x18001db8f  jnz     short loc_18001DBB8
0x18001db91  mov     rcx, cs:WPP_GLOBAL_Control
0x18001db98  cmp     rcx, rdi
0x18001db9b  jz      short loc_18001DBE0
0x18001db9d  test    byte ptr [rcx+1Ch], 1
0x18001dba1  jz      short loc_18001DBBF
0x18001dba3  mov     edx, 16Fh
0x18001dba8  lea     r8, WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids
0x18001dbaf  mov     rcx, [rcx+10h]
0x18001dbb3  call    WPP_SF_
0x18001dbb8  mov     rcx, cs:WPP_GLOBAL_Control
0x18001dbbf  cmp     rcx, rdi
0x18001dbc2  jz      short loc_18001DBE0
0x18001dbc4  test    byte ptr [rcx+1Ch], 8
0x18001dbc8  jz      short loc_18001DBE0
0x18001dbca  mov     edx, 170h
0x18001dbcf  lea     r8, WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids
0x18001dbd6  mov     rcx, [rcx+10h]
0x18001dbda  call    WPP_SF_
0x18001dbdf  nop
0x18001dbe0  test    rbx, rbx
0x18001dbe3  jz      short loc_18001DBF5
0x18001dbe5  mov     rax, [rbx]
0x18001dbe8  mov     rcx, rbx
0x18001dbeb  mov     rax, [rax+10h]
0x18001dbef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dbf4  nop
0x18001dbf5  xor     eax, eax
0x18001dbf7  mov     rbx, [rsp+28h+arg_0]
0x18001dbfc  add     rsp, 20h
0x18001dc00  pop     rdi
0x18001dc01  retn
```
