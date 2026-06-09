# BtPanHandler::OnDeviceConnected(_BT_ADDRESS const *)

- ea: `0x180025174`
- end: `0x18002538d`
- name: `?OnDeviceConnected@BtPanHandler@@QEAAXPEBU_BT_ADDRESS@@@Z`
- size: `537`
- prototype: `void __fastcall(BtPanHandler *__hidden this, const struct _BT_ADDRESS *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, loader_planting, service_task`

## callers

- `0x180024e80`

## callees

- `0x180002960`
- `0x18000299c`
- `0x18000bf4c`
- `0x18000bf74`
- `0x180025174`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800252a5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800252a5`
- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x18002529b`
- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x18002529b`

## pseudocode

```c
void __fastcall BtPanHandler::OnDeviceConnected(BtPanHandler *this, const struct _BT_ADDRESS *a2)
{
  TetheringServiceTelemetry *v3; // rcx
  char v4; // si
  char v5; // bp
  char v6; // r14
  char v7; // r15
  char v8; // r12
  char v9; // bl
  __int64 v10; // r13
  _BYTE *v11; // rax
  void *v12; // rdi
  TetheringServiceTelemetry *v13; // rcx
  __int64 v14; // rdx
  __int64 v15; // r9
  signed int LastError; // eax
  unsigned int v17; // ebx
  TetheringServiceTelemetry *v18; // rcx

  v3 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, WPP_0b53a71487193501cbc3cdc44df626ed_Traceguids);
    v3 = WPP_GLOBAL_Control;
  }
  v4 = *((_BYTE *)a2 + 5);
  v5 = *((_BYTE *)a2 + 4);
  v6 = *((_BYTE *)a2 + 3);
  v7 = *((_BYTE *)a2 + 2);
  v8 = *((_BYTE *)a2 + 1);
  v9 = *(_BYTE *)a2;
  v10 = *(_QWORD *)g_pTetheringSessionId.Data4;
  if ( v3 != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control && (*((_BYTE *)v3 + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)v3 + 2), 264, &WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids);
  v11 = operator new(8u, (const struct std::nothrow_t *)&std::nothrow);
  v12 = v11;
  if ( v11 )
  {
    *v11 = v4;
    v11[1] = v5;
    v11[2] = v6;
    v11[3] = v7;
    v11[4] = v8;
    v11[5] = v9;
    if ( !TrySubmitThreadpoolCallback(
            (PTP_SIMPLE_CALLBACK)TetheringService::AddBluetoothPeerWorkerProc,
            v11,
            (PTP_CALLBACK_ENVIRON)(v10 + 1808)) )
    {
      LastError = GetLastError();
      v17 = LastError;
      if ( LastError > 0 )
        v17 = (unsigned __int16)LastError | 0x80070000;
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control )
      {
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 267, &WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids, v17);
          v18 = WPP_GLOBAL_Control;
        }
        if ( v18 != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control && (*((_BYTE *)v18 + 28) & 8) != 0 )
          WPP_SF_d(*((_QWORD *)v18 + 2), 268, &WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids, v17);
      }
      operator delete(v12);
      goto LABEL_28;
    }
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (TetheringServiceTelemetry *)&WPP_GLOBAL_Control )
      return;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
      goto LABEL_29;
    v14 = 269;
    v15 = 0;
LABEL_27:
    WPP_SF_d(*((_QWORD *)v13 + 2), v14, &WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids, v15);
LABEL_28:
    v13 = WPP_GLOBAL_Control;
LABEL_29:
    if ( v13 != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control && (*((_BYTE *)v13 + 28) & 4) != 0 )
      WPP_SF_(*((_QWORD *)v13 + 2), 35, WPP_0b53a71487193501cbc3cdc44df626ed_Traceguids);
    return;
  }
  v13 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 265, &WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids, 2147942414LL);
      v13 = WPP_GLOBAL_Control;
    }
    if ( v13 != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)v13 + 28) & 8) == 0 )
        goto LABEL_29;
      v14 = 266;
      v15 = 2147942414LL;
      goto LABEL_27;
    }
  }
}

```

## disassembly

```asm
0x180025174  push    rbx
0x180025176  push    rbp
0x180025177  push    rsi
0x180025178  push    rdi
0x180025179  push    r12
0x18002517b  push    r13
0x18002517d  push    r14
0x18002517f  push    r15
0x180025181  sub     rsp, 28h
0x180025185  mov     rbx, rdx
0x180025188  mov     rcx, cs:WPP_GLOBAL_Control
0x18002518f  lea     rdi, WPP_GLOBAL_Control
0x180025196  cmp     rcx, rdi
0x180025199  jz      short loc_1800251BD
0x18002519b  test    byte ptr [rcx+1Ch], 4
0x18002519f  jz      short loc_1800251BD
0x1800251a1  mov     rcx, [rcx+10h]
0x1800251a5  lea     r8, WPP_0b53a71487193501cbc3cdc44df626ed_Traceguids
0x1800251ac  mov     edx, 22h ; '"'
0x1800251b1  call    WPP_SF_
0x1800251b6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800251bd  mov     sil, [rbx+5]
0x1800251c1  mov     bpl, [rbx+4]
0x1800251c5  mov     r14b, [rbx+3]
0x1800251c9  mov     r15b, [rbx+2]
0x1800251cd  mov     r12b, [rbx+1]
0x1800251d1  mov     bl, [rbx]
0x1800251d3  mov     r13, qword ptr cs:?g_pTetheringSessionId@@3PEAU_GUID@@EA.Data4; _GUID * g_pTetheringSessionId ...
0x1800251da  cmp     rcx, rdi
0x1800251dd  jz      short loc_1800251FA
0x1800251df  test    byte ptr [rcx+1Ch], 8
0x1800251e3  jz      short loc_1800251FA
0x1800251e5  mov     rcx, [rcx+10h]
0x1800251e9  lea     r8, WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids
0x1800251f0  mov     edx, 108h
0x1800251f5  call    WPP_SF_
0x1800251fa  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180025201  mov     ecx, 8; unsigned __int64
0x180025206  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18002520b  mov     rdi, rax
0x18002520e  test    rax, rax
0x180025211  jnz     short loc_180025274
0x180025213  mov     rcx, cs:WPP_GLOBAL_Control
0x18002521a  lea     rsi, WPP_GLOBAL_Control
0x180025221  cmp     rcx, rsi
0x180025224  jz      loc_18002537C
0x18002522a  test    byte ptr [rcx+1Ch], 1
0x18002522e  mov     ebx, 8007000Eh
0x180025233  jz      short loc_180025254
0x180025235  mov     rcx, [rcx+10h]
0x180025239  lea     r8, WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids
0x180025240  mov     edx, 109h
0x180025245  mov     r9d, ebx
0x180025248  call    WPP_SF_d
0x18002524d  mov     rcx, cs:WPP_GLOBAL_Control
0x180025254  cmp     rcx, rsi
0x180025257  jz      loc_18002537C
0x18002525d  test    byte ptr [rcx+1Ch], 8
0x180025261  jz      loc_18002535C
0x180025267  mov     edx, 10Ah
0x18002526c  mov     r9d, ebx
0x18002526f  jmp     loc_180025345
0x180025274  mov     [rax], sil
0x180025277  lea     r8, [r13+710h]; pcbe
0x18002527e  mov     [rax+1], bpl
0x180025282  lea     rcx, ?AddBluetoothPeerWorkerProc@TetheringService@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAX@Z; pfns
0x180025289  mov     [rax+2], r14b
0x18002528d  mov     rdx, rdi; pv
0x180025290  mov     [rax+3], r15b
0x180025294  mov     [rax+4], r12b
0x180025298  mov     [rax+5], bl
0x18002529b  call    cs:__imp_TrySubmitThreadpoolCallback
0x1800252a1  test    eax, eax
0x1800252a3  jnz     short loc_180025324
0x1800252a5  call    cs:__imp_GetLastError
0x1800252ab  mov     ebx, eax
0x1800252ad  test    eax, eax
0x1800252af  jle     short loc_1800252BA
0x1800252b1  movzx   ebx, ax
0x1800252b4  or      ebx, 80070000h
0x1800252ba  mov     rcx, cs:WPP_GLOBAL_Control
0x1800252c1  lea     rsi, WPP_GLOBAL_Control
0x1800252c8  cmp     rcx, rsi
0x1800252cb  jz      short loc_180025315
0x1800252cd  test    byte ptr [rcx+1Ch], 1
0x1800252d1  jz      short loc_1800252F2
0x1800252d3  mov     rcx, [rcx+10h]
0x1800252d7  lea     r8, WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids
0x1800252de  mov     edx, 10Bh
0x1800252e3  mov     r9d, ebx
0x1800252e6  call    WPP_SF_d
0x1800252eb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800252f2  cmp     rcx, rsi
0x1800252f5  jz      short loc_180025315
0x1800252f7  test    byte ptr [rcx+1Ch], 8
0x1800252fb  jz      short loc_180025315
0x1800252fd  mov     rcx, [rcx+10h]
0x180025301  lea     r8, WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids
0x180025308  mov     edx, 10Ch
0x18002530d  mov     r9d, ebx
0x180025310  call    WPP_SF_d
0x180025315  mov     edx, 8
0x18002531a  mov     rcx, rdi; Block
0x18002531d  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180025322  jmp     short loc_180025355
0x180025324  mov     rcx, cs:WPP_GLOBAL_Control
0x18002532b  lea     rsi, WPP_GLOBAL_Control
0x180025332  cmp     rcx, rsi
0x180025335  jz      short loc_18002537C
0x180025337  test    byte ptr [rcx+1Ch], 8
0x18002533b  jz      short loc_18002535C
0x18002533d  mov     edx, 10Dh
0x180025342  xor     r9d, r9d
0x180025345  mov     rcx, [rcx+10h]
0x180025349  lea     r8, WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids
0x180025350  call    WPP_SF_d
0x180025355  mov     rcx, cs:WPP_GLOBAL_Control
0x18002535c  cmp     rcx, rsi
0x18002535f  jz      short loc_18002537C
0x180025361  test    byte ptr [rcx+1Ch], 4
0x180025365  jz      short loc_18002537C
0x180025367  mov     rcx, [rcx+10h]
0x18002536b  lea     r8, WPP_0b53a71487193501cbc3cdc44df626ed_Traceguids
0x180025372  mov     edx, 23h ; '#'
0x180025377  call    WPP_SF_
0x18002537c  add     rsp, 28h
0x180025380  pop     r15
0x180025382  pop     r14
0x180025384  pop     r13
0x180025386  pop     r12
0x180025388  pop     rdi
0x180025389  pop     rsi
0x18002538a  pop     rbp
0x18002538b  pop     rbx
0x18002538c  retn
```
