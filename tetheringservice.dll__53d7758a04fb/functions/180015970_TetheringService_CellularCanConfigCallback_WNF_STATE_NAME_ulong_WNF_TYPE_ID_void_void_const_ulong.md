# TetheringService::CellularCanConfigCallback(_WNF_STATE_NAME,ulong,_WNF_TYPE_ID *,void *,void const *,ulong)

- ea: `0x180015970`
- end: `0x180015aa6`
- name: `?CellularCanConfigCallback@TetheringService@@CAJU_WNF_STATE_NAME@@KPEAU_WNF_TYPE_ID@@PEAXPEBXK@Z`
- size: `310`
- prototype: `__int64 __fastcall(struct _WNF_STATE_NAME, __int64, struct _WNF_TYPE_ID *, void *, _DWORD *, unsigned int)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, service_task, installer_update`

## callees

- `0x18000299c`
- `0x18000bf4c`
- `0x180015970`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x180015a18`
- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x180015a18`

## pseudocode

```c
__int64 __fastcall TetheringService::CellularCanConfigCallback(
        struct _WNF_STATE_NAME a1,
        __int64 a2,
        struct _WNF_TYPE_ID *a3,
        void *a4,
        _DWORD *a5,
        unsigned int a6)
{
  TetheringServiceTelemetry *v6; // rcx
  _DWORD *v7; // rax
  void *v8; // rdi
  __int64 v9; // rbx

  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 369, &WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids);
    v6 = WPP_GLOBAL_Control;
  }
  if ( a6 == 116 )
  {
    v7 = operator new(4u, (const struct std::nothrow_t *)&std::nothrow);
    v8 = v7;
    if ( !v7 )
    {
      v6 = WPP_GLOBAL_Control;
      goto LABEL_18;
    }
    *v7 = a5[1];
    v9 = *(_QWORD *)g_pTetheringSessionId.Data4;
    if ( *(_QWORD *)g_pTetheringSessionId.Data4 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)g_pTetheringSessionId.Data4 + 8LL))(*(_QWORD *)g_pTetheringSessionId.Data4);
    if ( v9
      && !TrySubmitThreadpoolCallback(
            TetheringService::UpdateCellularConfigWorkerProc,
            v8,
            (PTP_CALLBACK_ENVIRON)(v9 + 1808)) )
    {
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      {
LABEL_14:
        if ( v9 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
          v6 = WPP_GLOBAL_Control;
        }
        goto LABEL_18;
      }
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 370, &WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids);
    }
    v6 = WPP_GLOBAL_Control;
    goto LABEL_14;
  }
LABEL_18:
  if ( v6 != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)v6 + 2), 371, &WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids);
  return 0;
}

```

## disassembly

```asm
0x180015970  mov     [rsp+arg_0], rbx
0x180015975  mov     [rsp+arg_8], rsi
0x18001597a  push    rdi
0x18001597b  sub     rsp, 20h
0x18001597f  lea     rsi, WPP_GLOBAL_Control
0x180015986  mov     rcx, cs:WPP_GLOBAL_Control
0x18001598d  cmp     rcx, rsi
0x180015990  jz      short loc_1800159B4
0x180015992  test    byte ptr [rcx+1Ch], 8
0x180015996  jz      short loc_1800159B4
0x180015998  mov     edx, 171h
0x18001599d  lea     r8, WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids
0x1800159a4  mov     rcx, [rcx+10h]
0x1800159a8  call    WPP_SF_
0x1800159ad  mov     rcx, cs:WPP_GLOBAL_Control
0x1800159b4  cmp     [rsp+28h+arg_28], 74h ; 't'
0x1800159b9  jnz     loc_180015A74
0x1800159bf  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800159c6  mov     ecx, 4; unsigned __int64
0x1800159cb  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800159d0  mov     rdi, rax
0x1800159d3  test    rax, rax
0x1800159d6  jz      loc_180015A6D
0x1800159dc  mov     rcx, [rsp+28h+arg_20]
0x1800159e1  mov     edx, [rcx+4]
0x1800159e4  mov     [rax], edx
0x1800159e6  mov     rbx, qword ptr cs:?g_pTetheringSessionId@@3PEAU_GUID@@EA.Data4; _GUID * g_pTetheringSessionId ...
0x1800159ed  test    rbx, rbx
0x1800159f0  jz      short loc_180015A02
0x1800159f2  mov     rcx, [rbx]
0x1800159f5  mov     rax, [rcx+8]
0x1800159f9  mov     rcx, rbx
0x1800159fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015a01  nop
0x180015a02  test    rbx, rbx
0x180015a05  jz      short loc_180015A49
0x180015a07  lea     r8, [rbx+710h]; pcbe
0x180015a0e  mov     rdx, rdi; pv
0x180015a11  lea     rcx, ?UpdateCellularConfigWorkerProc@TetheringService@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAX@Z; pfns
0x180015a18  call    cs:__imp_TrySubmitThreadpoolCallback
0x180015a1e  test    eax, eax
0x180015a20  jnz     short loc_180015A49
0x180015a22  mov     rcx, cs:WPP_GLOBAL_Control
0x180015a29  cmp     rcx, rsi
0x180015a2c  jz      short loc_180015A50
0x180015a2e  test    byte ptr [rcx+1Ch], 1
0x180015a32  jz      short loc_180015A50
0x180015a34  mov     edx, 172h
0x180015a39  lea     r8, WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids
0x180015a40  mov     rcx, [rcx+10h]
0x180015a44  call    WPP_SF_
0x180015a49  mov     rcx, cs:WPP_GLOBAL_Control
0x180015a50  test    rbx, rbx
0x180015a53  jz      short loc_180015A6B
0x180015a55  mov     rax, [rbx]
0x180015a58  mov     rcx, rbx
0x180015a5b  mov     rax, [rax+10h]
0x180015a5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015a64  mov     rcx, cs:WPP_GLOBAL_Control
0x180015a6b  jmp     short loc_180015A74
0x180015a6d  mov     rcx, cs:WPP_GLOBAL_Control
0x180015a74  cmp     rcx, rsi
0x180015a77  jz      short loc_180015A94
0x180015a79  test    byte ptr [rcx+1Ch], 8
0x180015a7d  jz      short loc_180015A94
0x180015a7f  mov     edx, 173h
0x180015a84  lea     r8, WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids
0x180015a8b  mov     rcx, [rcx+10h]
0x180015a8f  call    WPP_SF_
0x180015a94  xor     eax, eax
0x180015a96  mov     rbx, [rsp+28h+arg_0]
0x180015a9b  mov     rsi, [rsp+28h+arg_8]
0x180015aa0  add     rsp, 20h
0x180015aa4  pop     rdi
0x180015aa5  retn
```
