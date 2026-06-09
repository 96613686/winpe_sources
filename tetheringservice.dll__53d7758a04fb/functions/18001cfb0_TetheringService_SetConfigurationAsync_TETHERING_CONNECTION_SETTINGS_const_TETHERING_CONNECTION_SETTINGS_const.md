# TetheringService::SetConfigurationAsync(_TETHERING_CONNECTION_SETTINGS * const,_TETHERING_CONNECTION_SETTINGS * const)

- ea: `0x18001cfb0`
- end: `0x18001d2a2`
- name: `?SetConfigurationAsync@TetheringService@@QEAAJQEAU_TETHERING_CONNECTION_SETTINGS@@0@Z`
- size: `754`
- prototype: `__int64 __fastcall(TetheringService *__hidden this, struct _TETHERING_CONNECTION_SETTINGS *const, struct _TETHERING_CONNECTION_SETTINGS *const)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task`

## callers

- `0x18000ccc0`

## callees

- `0x180003088`
- `0x18000bf4c`
- `0x18000bf74`
- `0x18001cfb0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001d208`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001d208`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18001cffc`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18001cffc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d1db`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d20e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d1db`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d20e`
- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x18001d1b6`
- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x18001d1b6`

## pseudocode

```c
__int64 __fastcall TetheringService::SetConfigurationAsync(
        TetheringService *this,
        struct _TETHERING_CONNECTION_SETTINGS *const a2,
        struct _TETHERING_CONNECTION_SETTINGS *const a3)
{
  _OWORD *v6; // rax
  _OWORD *v7; // rbx
  TetheringServiceTelemetry *v8; // rcx
  unsigned int v9; // ebx
  __int64 v10; // rdx
  __int128 v12; // xmm1
  __int128 v13; // xmm0
  __int128 v14; // xmm1
  __int128 v15; // xmm0
  __int128 v16; // xmm1
  __int128 v17; // xmm0
  __int128 v18; // xmm1
  __int128 v19; // xmm0
  __int128 v20; // xmm1
  __int128 v21; // xmm0
  __int128 v22; // xmm1
  __int128 v23; // xmm0
  __int128 v24; // xmm1
  __int128 v25; // xmm0
  __int128 v26; // xmm1
  __int128 v27; // xmm0
  __int128 v28; // xmm1
  __int128 v29; // xmm0
  __int128 v30; // xmm1
  __int128 v31; // xmm0
  __int128 v32; // xmm1
  __int128 v33; // xmm0
  __int128 v34; // xmm1
  __int128 v35; // xmm0
  signed int LastError; // eax
  signed int v37; // eax

  if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 193, &WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids);
  }
  v6 = malloc(0x1A0u);
  v7 = v6;
  if ( !v6 )
  {
    v8 = WPP_GLOBAL_Control;
    v9 = -2147024882;
    if ( WPP_GLOBAL_Control == (TetheringServiceTelemetry *)&WPP_GLOBAL_Control )
      return v9;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 194, &WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids, 2147942414LL);
      v8 = WPP_GLOBAL_Control;
    }
    if ( v8 == (TetheringServiceTelemetry *)&WPP_GLOBAL_Control || (*((_BYTE *)v8 + 28) & 8) == 0 )
      return v9;
    v10 = 195;
LABEL_11:
    WPP_SF_d(*((_QWORD *)v8 + 2), v10, &WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids, v9);
    return v9;
  }
  memset_0(v6, 0, 0x1A0u);
  if ( a2 )
  {
    v12 = *((_OWORD *)a2 + 1);
    *v7 = *(_OWORD *)a2;
    v13 = *((_OWORD *)a2 + 2);
    v7[1] = v12;
    v14 = *((_OWORD *)a2 + 3);
    v7[2] = v13;
    v15 = *((_OWORD *)a2 + 4);
    v7[3] = v14;
    v16 = *((_OWORD *)a2 + 5);
    v7[4] = v15;
    v17 = *((_OWORD *)a2 + 6);
    v7[5] = v16;
    v18 = *((_OWORD *)a2 + 7);
    v7[6] = v17;
    v19 = *((_OWORD *)a2 + 8);
    v7[7] = v18;
    v20 = *((_OWORD *)a2 + 9);
    v7[8] = v19;
    v21 = *((_OWORD *)a2 + 10);
    v7[9] = v20;
    v22 = *((_OWORD *)a2 + 11);
    v7[10] = v21;
    v23 = *((_OWORD *)a2 + 12);
    v7[11] = v22;
    v7[12] = v23;
  }
  if ( a3 )
  {
    v24 = *((_OWORD *)a3 + 1);
    v7[13] = *(_OWORD *)a3;
    v25 = *((_OWORD *)a3 + 2);
    v7[14] = v24;
    v26 = *((_OWORD *)a3 + 3);
    v7[15] = v25;
    v27 = *((_OWORD *)a3 + 4);
    v7[16] = v26;
    v28 = *((_OWORD *)a3 + 5);
    v7[17] = v27;
    v29 = *((_OWORD *)a3 + 6);
    v7[18] = v28;
    v30 = *((_OWORD *)a3 + 7);
    v7[19] = v29;
    v31 = *((_OWORD *)a3 + 8);
    v7[20] = v30;
    v32 = *((_OWORD *)a3 + 9);
    v7[21] = v31;
    v33 = *((_OWORD *)a3 + 10);
    v7[22] = v32;
    v34 = *((_OWORD *)a3 + 11);
    v7[23] = v33;
    v35 = *((_OWORD *)a3 + 12);
    v7[24] = v34;
    v7[25] = v35;
  }
  if ( !TrySubmitThreadpoolCallback(
          TetheringService::SetConfigurationWorkerProc,
          v7,
          (PTP_CALLBACK_ENVIRON)((char *)this + 1808)) )
  {
    if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        196,
        &WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids,
        (unsigned int)LastError);
    }
    free(v7);
    v37 = GetLastError();
    v9 = v37;
    if ( v37 > 0 )
      v9 = (unsigned __int16)v37 | 0x80070000;
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (TetheringServiceTelemetry *)&WPP_GLOBAL_Control )
      return v9;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 197, &WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids, v9);
      v8 = WPP_GLOBAL_Control;
    }
    if ( v8 == (TetheringServiceTelemetry *)&WPP_GLOBAL_Control || (*((_BYTE *)v8 + 28) & 8) == 0 )
      return v9;
    v10 = 198;
    goto LABEL_11;
  }
  if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 199, &WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids, 0);
  }
  return 0;
}

```

## disassembly

```asm
0x18001cfb0  push    rbx
0x18001cfb2  push    rbp
0x18001cfb3  push    rsi
0x18001cfb4  push    rdi
0x18001cfb5  push    r14
0x18001cfb7  push    r15
0x18001cfb9  sub     rsp, 28h
0x18001cfbd  mov     rdi, r8
0x18001cfc0  mov     rsi, rdx
0x18001cfc3  mov     rbp, rcx
0x18001cfc6  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cfcd  lea     r14, WPP_GLOBAL_Control
0x18001cfd4  lea     r15, WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids
0x18001cfdb  cmp     rcx, r14
0x18001cfde  jz      short loc_18001CFF7
0x18001cfe0  test    byte ptr [rcx+1Ch], 8
0x18001cfe4  jz      short loc_18001CFF7
0x18001cfe6  mov     rcx, [rcx+10h]
0x18001cfea  mov     edx, 0C1h
0x18001cfef  mov     r8, r15
0x18001cff2  call    WPP_SF_
0x18001cff7  mov     ecx, 1A0h; Size
0x18001cffc  call    cs:__imp_malloc
0x18001d002  mov     rbx, rax
0x18001d005  test    rax, rax
0x18001d008  jnz     short loc_18001D062
0x18001d00a  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d011  mov     ebx, 8007000Eh
0x18001d016  cmp     rcx, r14
0x18001d019  jz      short loc_18001D05B
0x18001d01b  test    byte ptr [rcx+1Ch], 1
0x18001d01f  jz      short loc_18001D03C
0x18001d021  mov     rcx, [rcx+10h]
0x18001d025  mov     edx, 0C2h
0x18001d02a  mov     r9d, ebx
0x18001d02d  mov     r8, r15
0x18001d030  call    WPP_SF_d
0x18001d035  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d03c  cmp     rcx, r14
0x18001d03f  jz      short loc_18001D05B
0x18001d041  test    byte ptr [rcx+1Ch], 8
0x18001d045  jz      short loc_18001D05B
0x18001d047  mov     edx, 0C3h
0x18001d04c  mov     rcx, [rcx+10h]
0x18001d050  mov     r9d, ebx
0x18001d053  mov     r8, r15
0x18001d056  call    WPP_SF_d
0x18001d05b  mov     eax, ebx
0x18001d05d  jmp     loc_18001D295
0x18001d062  xor     edx, edx; Val
0x18001d064  mov     r8d, 1A0h; Size
0x18001d06a  mov     rcx, rbx; void *
0x18001d06d  call    memset_0
0x18001d072  test    rsi, rsi
0x18001d075  jz      loc_18001D0FF
0x18001d07b  movups  xmm0, xmmword ptr [rsi]
0x18001d07e  movups  xmm1, xmmword ptr [rsi+10h]
0x18001d082  movups  xmmword ptr [rbx], xmm0
0x18001d085  movups  xmm0, xmmword ptr [rsi+20h]
0x18001d089  movups  xmmword ptr [rbx+10h], xmm1
0x18001d08d  movups  xmm1, xmmword ptr [rsi+30h]
0x18001d091  movups  xmmword ptr [rbx+20h], xmm0
0x18001d095  movups  xmm0, xmmword ptr [rsi+40h]
0x18001d099  movups  xmmword ptr [rbx+30h], xmm1
0x18001d09d  movups  xmm1, xmmword ptr [rsi+50h]
0x18001d0a1  movups  xmmword ptr [rbx+40h], xmm0
0x18001d0a5  movups  xmm0, xmmword ptr [rsi+60h]
0x18001d0a9  movups  xmmword ptr [rbx+50h], xmm1
0x18001d0ad  movups  xmm1, xmmword ptr [rsi+70h]
0x18001d0b1  movups  xmmword ptr [rbx+60h], xmm0
0x18001d0b5  movups  xmm0, xmmword ptr [rsi+80h]
0x18001d0bc  movups  xmmword ptr [rbx+70h], xmm1
0x18001d0c0  movups  xmm1, xmmword ptr [rsi+90h]
0x18001d0c7  movups  xmmword ptr [rbx+80h], xmm0
0x18001d0ce  movups  xmm0, xmmword ptr [rsi+0A0h]
0x18001d0d5  movups  xmmword ptr [rbx+90h], xmm1
0x18001d0dc  movups  xmm1, xmmword ptr [rsi+0B0h]
0x18001d0e3  movups  xmmword ptr [rbx+0A0h], xmm0
0x18001d0ea  movups  xmm0, xmmword ptr [rsi+0C0h]
0x18001d0f1  movups  xmmword ptr [rbx+0B0h], xmm1
0x18001d0f8  movups  xmmword ptr [rbx+0C0h], xmm0
0x18001d0ff  test    rdi, rdi
0x18001d102  jz      loc_18001D1A5
0x18001d108  movups  xmm0, xmmword ptr [rdi]
0x18001d10b  movups  xmm1, xmmword ptr [rdi+10h]
0x18001d10f  movups  xmmword ptr [rbx+0D0h], xmm0
0x18001d116  movups  xmm0, xmmword ptr [rdi+20h]
0x18001d11a  movups  xmmword ptr [rbx+0E0h], xmm1
0x18001d121  movups  xmm1, xmmword ptr [rdi+30h]
0x18001d125  movups  xmmword ptr [rbx+0F0h], xmm0
0x18001d12c  movups  xmm0, xmmword ptr [rdi+40h]
0x18001d130  movups  xmmword ptr [rbx+100h], xmm1
0x18001d137  movups  xmm1, xmmword ptr [rdi+50h]
0x18001d13b  movups  xmmword ptr [rbx+110h], xmm0
0x18001d142  movups  xmm0, xmmword ptr [rdi+60h]
0x18001d146  movups  xmmword ptr [rbx+120h], xmm1
0x18001d14d  movups  xmm1, xmmword ptr [rdi+70h]
0x18001d151  movups  xmmword ptr [rbx+130h], xmm0
0x18001d158  movups  xmm0, xmmword ptr [rdi+80h]
0x18001d15f  movups  xmmword ptr [rbx+140h], xmm1
0x18001d166  movups  xmm1, xmmword ptr [rdi+90h]
0x18001d16d  movups  xmmword ptr [rbx+150h], xmm0
0x18001d174  movups  xmm0, xmmword ptr [rdi+0A0h]
0x18001d17b  movups  xmmword ptr [rbx+160h], xmm1
0x18001d182  movups  xmm1, xmmword ptr [rdi+0B0h]
0x18001d189  movups  xmmword ptr [rbx+170h], xmm0
0x18001d190  movups  xmm0, xmmword ptr [rdi+0C0h]
0x18001d197  movups  xmmword ptr [rbx+180h], xmm1
0x18001d19e  movups  xmmword ptr [rbx+190h], xmm0
0x18001d1a5  lea     r8, [rbp+710h]; pcbe
0x18001d1ac  mov     rdx, rbx; pv
0x18001d1af  lea     rcx, ?SetConfigurationWorkerProc@TetheringService@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAX@Z; pfns
0x18001d1b6  call    cs:__imp_TrySubmitThreadpoolCallback
0x18001d1bc  test    eax, eax
0x18001d1be  jnz     loc_18001D26D
0x18001d1c4  mov     rax, cs:WPP_GLOBAL_Control
0x18001d1cb  mov     edi, 80070000h
0x18001d1d0  cmp     rax, r14
0x18001d1d3  jz      short loc_18001D205
0x18001d1d5  test    byte ptr [rax+1Ch], 1
0x18001d1d9  jz      short loc_18001D205
0x18001d1db  call    cs:__imp_GetLastError
0x18001d1e1  test    eax, eax
0x18001d1e3  jle     short loc_18001D1EA
0x18001d1e5  movzx   eax, ax
0x18001d1e8  or      eax, edi
0x18001d1ea  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d1f1  mov     edx, 0C4h
0x18001d1f6  mov     r9d, eax
0x18001d1f9  mov     r8, r15
0x18001d1fc  mov     rcx, [rcx+10h]
0x18001d200  call    WPP_SF_d
0x18001d205  mov     rcx, rbx; Block
0x18001d208  call    cs:__imp_free
0x18001d20e  call    cs:__imp_GetLastError
0x18001d214  mov     ebx, eax
0x18001d216  test    eax, eax
0x18001d218  jle     short loc_18001D21F
0x18001d21a  movzx   ebx, ax
0x18001d21d  or      ebx, edi
0x18001d21f  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d226  cmp     rcx, r14
0x18001d229  jz      loc_18001D05B
0x18001d22f  test    byte ptr [rcx+1Ch], 1
0x18001d233  jz      short loc_18001D250
0x18001d235  mov     rcx, [rcx+10h]
0x18001d239  mov     edx, 0C5h
0x18001d23e  mov     r9d, ebx
0x18001d241  mov     r8, r15
0x18001d244  call    WPP_SF_d
0x18001d249  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d250  cmp     rcx, r14
0x18001d253  jz      loc_18001D05B
0x18001d259  test    byte ptr [rcx+1Ch], 8
0x18001d25d  jz      loc_18001D05B
0x18001d263  mov     edx, 0C6h
0x18001d268  jmp     loc_18001D04C
0x18001d26d  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d274  cmp     rcx, r14
0x18001d277  jz      short loc_18001D293
0x18001d279  test    byte ptr [rcx+1Ch], 8
0x18001d27d  jz      short loc_18001D293
0x18001d27f  mov     rcx, [rcx+10h]
0x18001d283  mov     edx, 0C7h
0x18001d288  xor     r9d, r9d
0x18001d28b  mov     r8, r15
0x18001d28e  call    WPP_SF_d
0x18001d293  xor     eax, eax
0x18001d295  add     rsp, 28h
0x18001d299  pop     r15
0x18001d29b  pop     r14
0x18001d29d  pop     rdi
0x18001d29e  pop     rsi
0x18001d29f  pop     rbp
0x18001d2a0  pop     rbx
0x18001d2a1  retn
```
