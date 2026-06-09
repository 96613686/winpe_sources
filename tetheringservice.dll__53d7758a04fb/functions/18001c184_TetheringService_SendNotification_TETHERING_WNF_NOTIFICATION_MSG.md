# TetheringService::SendNotification(_TETHERING_WNF_NOTIFICATION_MSG *)

- ea: `0x18001c184`
- end: `0x18001c326`
- name: `?SendNotification@TetheringService@@AEAAXPEAU_TETHERING_WNF_NOTIFICATION_MSG@@@Z`
- size: `418`
- prototype: `void __fastcall(TetheringService *__hidden this, struct _TETHERING_WNF_NOTIFICATION_MSG *)`
- caller_count: `7`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x18000cd20`
- `0x180014c8c`
- `0x18001b898`
- `0x18001c75c`
- `0x18001e4a4`
- `0x18001f740`
- `0x180020f4c`

## callees

- `0x18000bf4c`
- `0x18001c184`
- `0x18001c32c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18001c1c6`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18001c1c6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001c2a4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001c2a4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001c276`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001c276`
- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x18001c2bb`
- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x18001c2bb`

## pseudocode

```c
void __fastcall TetheringService::SendNotification(TetheringService *this, struct _TETHERING_WNF_NOTIFICATION_MSG *a2)
{
  TetheringService *v4; // rax
  TetheringService *v5; // rbx
  __int128 v6; // xmm1
  __int128 v7; // xmm0
  __int128 v8; // xmm1
  __int128 v9; // xmm0
  __int128 v10; // xmm1
  __int128 v11; // xmm0
  __int128 v12; // xmm1
  __int128 v13; // xmm0
  __int128 v14; // xmm1
  __int128 v15; // xmm0
  __int128 v16; // xmm1
  __int128 v17; // xmm0
  TetheringService **v18; // rcx
  TetheringServiceTelemetry *v19; // rcx

  if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 250, &WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids);
  }
  v4 = (TetheringService *)malloc(0xE8u);
  v5 = v4;
  if ( v4 )
  {
    v6 = *((_OWORD *)a2 + 1);
    *((_OWORD *)v4 + 1) = *(_OWORD *)a2;
    v7 = *((_OWORD *)a2 + 2);
    *((_OWORD *)v4 + 2) = v6;
    v8 = *((_OWORD *)a2 + 3);
    *((_OWORD *)v4 + 3) = v7;
    v9 = *((_OWORD *)a2 + 4);
    *((_OWORD *)v4 + 4) = v8;
    v10 = *((_OWORD *)a2 + 5);
    *((_OWORD *)v4 + 5) = v9;
    v11 = *((_OWORD *)a2 + 6);
    *((_OWORD *)v4 + 6) = v10;
    v12 = *((_OWORD *)a2 + 7);
    *((_OWORD *)v4 + 7) = v11;
    v13 = *((_OWORD *)a2 + 8);
    *((_OWORD *)v4 + 8) = v12;
    v14 = *((_OWORD *)a2 + 9);
    *((_OWORD *)v4 + 9) = v13;
    v15 = *((_OWORD *)a2 + 10);
    *((_OWORD *)v4 + 10) = v14;
    v16 = *((_OWORD *)a2 + 11);
    *((_OWORD *)v4 + 11) = v15;
    v17 = *((_OWORD *)a2 + 12);
    *((_OWORD *)v4 + 12) = v16;
    *((_OWORD *)v4 + 13) = v17;
    *((_DWORD *)v4 + 56) = *((_DWORD *)a2 + 52);
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 1304));
    v18 = (TetheringService **)*((_QWORD *)this + 169);
    if ( *v18 != (TetheringService *)((char *)this + 1344) )
      __fastfail(3u);
    *((_QWORD *)v5 + 1) = v18;
    *(_QWORD *)v5 = (char *)this + 1344;
    *v18 = v5;
    *((_QWORD *)this + 169) = v5;
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 1304));
    if ( !TrySubmitThreadpoolCallback(
            TetheringService::SendNotificationWorkerProc,
            this,
            (PTP_CALLBACK_ENVIRON)((char *)this + 1808)) )
      TetheringService::SendNotificationWorker(this);
    goto LABEL_12;
  }
  v19 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (TetheringServiceTelemetry *)&WPP_GLOBAL_Control )
    return;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 251, &WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids);
LABEL_12:
    v19 = WPP_GLOBAL_Control;
  }
  if ( v19 != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control && (*((_BYTE *)v19 + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)v19 + 2), 252, &WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids);
}

```

## disassembly

```asm
0x18001c184  push    rbx
0x18001c186  push    rbp
0x18001c187  push    rsi
0x18001c188  push    rdi
0x18001c189  sub     rsp, 28h
0x18001c18d  mov     rsi, rdx
0x18001c190  mov     rdi, rcx
0x18001c193  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c19a  lea     rbp, WPP_GLOBAL_Control
0x18001c1a1  cmp     rcx, rbp
0x18001c1a4  jz      short loc_18001C1C1
0x18001c1a6  test    byte ptr [rcx+1Ch], 8
0x18001c1aa  jz      short loc_18001C1C1
0x18001c1ac  mov     rcx, [rcx+10h]
0x18001c1b0  lea     r8, WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids
0x18001c1b7  mov     edx, 0FAh
0x18001c1bc  call    WPP_SF_
0x18001c1c1  mov     ecx, 0E8h; Size
0x18001c1c6  call    cs:__imp_malloc
0x18001c1cc  mov     rbx, rax
0x18001c1cf  test    rax, rax
0x18001c1d2  jz      loc_18001C2CF
0x18001c1d8  movups  xmm0, xmmword ptr [rsi]
0x18001c1db  movups  xmm1, xmmword ptr [rsi+10h]
0x18001c1df  movups  xmmword ptr [rax+10h], xmm0
0x18001c1e3  movups  xmm0, xmmword ptr [rsi+20h]
0x18001c1e7  movups  xmmword ptr [rax+20h], xmm1
0x18001c1eb  movups  xmm1, xmmword ptr [rsi+30h]
0x18001c1ef  movups  xmmword ptr [rax+30h], xmm0
0x18001c1f3  movups  xmm0, xmmword ptr [rsi+40h]
0x18001c1f7  movups  xmmword ptr [rax+40h], xmm1
0x18001c1fb  movups  xmm1, xmmword ptr [rsi+50h]
0x18001c1ff  movups  xmmword ptr [rax+50h], xmm0
0x18001c203  movups  xmm0, xmmword ptr [rsi+60h]
0x18001c207  movups  xmmword ptr [rax+60h], xmm1
0x18001c20b  movups  xmm1, xmmword ptr [rsi+70h]
0x18001c20f  movups  xmmword ptr [rax+70h], xmm0
0x18001c213  movups  xmm0, xmmword ptr [rsi+80h]
0x18001c21a  movups  xmmword ptr [rax+80h], xmm1
0x18001c221  movups  xmm1, xmmword ptr [rsi+90h]
0x18001c228  movups  xmmword ptr [rax+90h], xmm0
0x18001c22f  movups  xmm0, xmmword ptr [rsi+0A0h]
0x18001c236  movups  xmmword ptr [rax+0A0h], xmm1
0x18001c23d  movups  xmm1, xmmword ptr [rsi+0B0h]
0x18001c244  movups  xmmword ptr [rax+0B0h], xmm0
0x18001c24b  movups  xmm0, xmmword ptr [rsi+0C0h]
0x18001c252  movups  xmmword ptr [rax+0C0h], xmm1
0x18001c259  movups  xmmword ptr [rax+0D0h], xmm0
0x18001c260  mov     eax, [rsi+0D0h]
0x18001c266  lea     rsi, [rdi+518h]
0x18001c26d  mov     rcx, rsi; lpCriticalSection
0x18001c270  mov     [rbx+0E0h], eax
0x18001c276  call    cs:__imp_EnterCriticalSection
0x18001c27c  lea     rax, [rdi+540h]
0x18001c283  mov     rcx, [rax+8]
0x18001c287  cmp     [rcx], rax
0x18001c28a  jz      short loc_18001C293
0x18001c28c  mov     ecx, 3
0x18001c291  int     29h; Win8: RtlFailFast(ecx)
0x18001c293  mov     [rbx+8], rcx
0x18001c297  mov     [rbx], rax
0x18001c29a  mov     [rcx], rbx
0x18001c29d  mov     rcx, rsi; lpCriticalSection
0x18001c2a0  mov     [rax+8], rbx
0x18001c2a4  call    cs:__imp_LeaveCriticalSection
0x18001c2aa  lea     r8, [rdi+710h]; pcbe
0x18001c2b1  mov     rdx, rdi; pv
0x18001c2b4  lea     rcx, ?SendNotificationWorkerProc@TetheringService@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAX@Z; pfns
0x18001c2bb  call    cs:__imp_TrySubmitThreadpoolCallback
0x18001c2c1  test    eax, eax
0x18001c2c3  jnz     short loc_18001C2F6
0x18001c2c5  mov     rcx, rdi; this
0x18001c2c8  call    ?SendNotificationWorker@TetheringService@@AEAAXXZ; TetheringService::SendNotificationWorker(void)
0x18001c2cd  jmp     short loc_18001C2F6
0x18001c2cf  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c2d6  cmp     rcx, rbp
0x18001c2d9  jz      short loc_18001C31D
0x18001c2db  test    byte ptr [rcx+1Ch], 1
0x18001c2df  jz      short loc_18001C2FD
0x18001c2e1  mov     rcx, [rcx+10h]
0x18001c2e5  lea     r8, WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids
0x18001c2ec  mov     edx, 0FBh
0x18001c2f1  call    WPP_SF_
0x18001c2f6  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c2fd  cmp     rcx, rbp
0x18001c300  jz      short loc_18001C31D
0x18001c302  test    byte ptr [rcx+1Ch], 8
0x18001c306  jz      short loc_18001C31D
0x18001c308  mov     rcx, [rcx+10h]
0x18001c30c  lea     r8, WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids
0x18001c313  mov     edx, 0FCh
0x18001c318  call    WPP_SF_
0x18001c31d  add     rsp, 28h
0x18001c321  pop     rdi
0x18001c322  pop     rsi
0x18001c323  pop     rbp
0x18001c324  pop     rbx
0x18001c325  retn
```
