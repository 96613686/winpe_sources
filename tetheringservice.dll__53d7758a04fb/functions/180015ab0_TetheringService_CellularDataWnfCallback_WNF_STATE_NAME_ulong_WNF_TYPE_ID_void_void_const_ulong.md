# TetheringService::CellularDataWnfCallback(_WNF_STATE_NAME,ulong,_WNF_TYPE_ID *,void *,void const *,ulong)

- ea: `0x180015ab0`
- end: `0x180015be6`
- name: `?CellularDataWnfCallback@TetheringService@@CAJU_WNF_STATE_NAME@@KPEAU_WNF_TYPE_ID@@PEAXPEBXK@Z`
- size: `310`
- prototype: `__int64 __fastcall(struct _WNF_STATE_NAME, __int64, struct _WNF_TYPE_ID *, void *, _BYTE *, unsigned int)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, installer_update`

## callees

- `0x18000299c`
- `0x18000bf4c`
- `0x180015ab0`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x180015b58`
- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x180015b58`

## pseudocode

```c
__int64 __fastcall TetheringService::CellularDataWnfCallback(
        struct _WNF_STATE_NAME a1,
        __int64 a2,
        struct _WNF_TYPE_ID *a3,
        void *a4,
        _BYTE *a5,
        unsigned int a6)
{
  TetheringServiceTelemetry *v6; // rcx
  _BYTE *v7; // rax
  void *v8; // rdi
  __int64 v9; // rbx

  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 372, &WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids);
    v6 = WPP_GLOBAL_Control;
  }
  if ( a6 == 4 )
  {
    v7 = operator new(1u, (const struct std::nothrow_t *)&std::nothrow);
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
            TetheringService::UpdateCellDataSimWorkerProc,
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
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 373, &WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids);
    }
    v6 = WPP_GLOBAL_Control;
    goto LABEL_14;
  }
LABEL_18:
  if ( v6 != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)v6 + 2), 374, &WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids);
  return 0;
}

```

## disassembly

```asm
0x180015ab0  mov     [rsp+arg_0], rbx
0x180015ab5  mov     [rsp+arg_8], rsi
0x180015aba  push    rdi
0x180015abb  sub     rsp, 20h
0x180015abf  lea     rsi, WPP_GLOBAL_Control
0x180015ac6  mov     rcx, cs:WPP_GLOBAL_Control
0x180015acd  cmp     rcx, rsi
0x180015ad0  jz      short loc_180015AF4
0x180015ad2  test    byte ptr [rcx+1Ch], 8
0x180015ad6  jz      short loc_180015AF4
0x180015ad8  mov     edx, 174h
0x180015add  lea     r8, WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids
0x180015ae4  mov     rcx, [rcx+10h]
0x180015ae8  call    WPP_SF_
0x180015aed  mov     rcx, cs:WPP_GLOBAL_Control
0x180015af4  cmp     [rsp+28h+arg_28], 4
0x180015af9  jnz     loc_180015BB4
0x180015aff  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180015b06  mov     ecx, 1; unsigned __int64
0x180015b0b  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180015b10  mov     rdi, rax
0x180015b13  test    rax, rax
0x180015b16  jz      loc_180015BAD
0x180015b1c  mov     rcx, [rsp+28h+arg_20]
0x180015b21  mov     dl, [rcx+1]
0x180015b24  mov     [rax], dl
0x180015b26  mov     rbx, qword ptr cs:?g_pTetheringSessionId@@3PEAU_GUID@@EA.Data4; _GUID * g_pTetheringSessionId ...
0x180015b2d  test    rbx, rbx
0x180015b30  jz      short loc_180015B42
0x180015b32  mov     rcx, [rbx]
0x180015b35  mov     rax, [rcx+8]
0x180015b39  mov     rcx, rbx
0x180015b3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015b41  nop
0x180015b42  test    rbx, rbx
0x180015b45  jz      short loc_180015B89
0x180015b47  lea     r8, [rbx+710h]; pcbe
0x180015b4e  mov     rdx, rdi; pv
0x180015b51  lea     rcx, ?UpdateCellDataSimWorkerProc@TetheringService@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAX@Z; pfns
0x180015b58  call    cs:__imp_TrySubmitThreadpoolCallback
0x180015b5e  test    eax, eax
0x180015b60  jnz     short loc_180015B89
0x180015b62  mov     rcx, cs:WPP_GLOBAL_Control
0x180015b69  cmp     rcx, rsi
0x180015b6c  jz      short loc_180015B90
0x180015b6e  test    byte ptr [rcx+1Ch], 1
0x180015b72  jz      short loc_180015B90
0x180015b74  mov     edx, 175h
0x180015b79  lea     r8, WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids
0x180015b80  mov     rcx, [rcx+10h]
0x180015b84  call    WPP_SF_
0x180015b89  mov     rcx, cs:WPP_GLOBAL_Control
0x180015b90  test    rbx, rbx
0x180015b93  jz      short loc_180015BAB
0x180015b95  mov     rax, [rbx]
0x180015b98  mov     rcx, rbx
0x180015b9b  mov     rax, [rax+10h]
0x180015b9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015ba4  mov     rcx, cs:WPP_GLOBAL_Control
0x180015bab  jmp     short loc_180015BB4
0x180015bad  mov     rcx, cs:WPP_GLOBAL_Control
0x180015bb4  cmp     rcx, rsi
0x180015bb7  jz      short loc_180015BD4
0x180015bb9  test    byte ptr [rcx+1Ch], 8
0x180015bbd  jz      short loc_180015BD4
0x180015bbf  mov     edx, 176h
0x180015bc4  lea     r8, WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids
0x180015bcb  mov     rcx, [rcx+10h]
0x180015bcf  call    WPP_SF_
0x180015bd4  xor     eax, eax
0x180015bd6  mov     rbx, [rsp+28h+arg_0]
0x180015bdb  mov     rsi, [rsp+28h+arg_8]
0x180015be0  add     rsp, 20h
0x180015be4  pop     rdi
0x180015be5  retn
```
