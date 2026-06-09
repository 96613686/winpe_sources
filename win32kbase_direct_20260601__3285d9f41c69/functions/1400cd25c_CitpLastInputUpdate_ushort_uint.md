# CitpLastInputUpdate(ushort,uint)

- ea: `0x1400cd25c`
- end: `0x1400cdb6d`
- name: `?CitpLastInputUpdate@@YAXGI@Z`
- size: `2321`
- prototype: `void __fastcall(unsigned __int16, unsigned int)`
- caller_count: `4`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1400a65c8`
- `0x1400ccae0`
- `0x1400cd160`
- `0x1400cf59c`

## callees

- `0x140031a54`
- `0x1400cd25c`
- `0x1400cef44`
- `0x140119610`
- `0x140132748`

## import_xrefs

- `ntoskrnl!PsUpdateComponentPower` at `0x1400cd454`
- `ntoskrnl!PsUpdateComponentPower` at `0x1400cd57d`
- `ntoskrnl!PsUpdateComponentPower` at `0x1400cd63c`
- `ntoskrnl!PsUpdateComponentPower` at `0x1400cd7fd`
- `ntoskrnl!PsUpdateComponentPower` at `0x1400cd822`
- `ntoskrnl!PsUpdateComponentPower` at `0x1400cda29`
- `ntoskrnl!PsUpdateComponentPower` at `0x1400cda70`
- `ntoskrnl!PsUpdateComponentPower` at `0x1400cda94`
- `ntoskrnl!PsUpdateComponentPower` at `0x1400cdab8`
- `ntoskrnl!PsUpdateComponentPower` at `0x1400cdafa`
- `ntoskrnl!PsUpdateComponentPower` at `0x1400cdb1e`
- `ntoskrnl!PsUpdateComponentPower` at `0x1400cdb43`
- `ntoskrnl!PsUpdateComponentPower` at `0x1400cd454`
- `ntoskrnl!PsUpdateComponentPower` at `0x1400cd57d`
- `ntoskrnl!PsUpdateComponentPower` at `0x1400cd63c`
- `ntoskrnl!PsUpdateComponentPower` at `0x1400cd7fd`
- `ntoskrnl!PsUpdateComponentPower` at `0x1400cd822`
- `ntoskrnl!PsUpdateComponentPower` at `0x1400cda29`
- `ntoskrnl!PsUpdateComponentPower` at `0x1400cda70`
- `ntoskrnl!PsUpdateComponentPower` at `0x1400cda94`
- `ntoskrnl!PsUpdateComponentPower` at `0x1400cdab8`
- `ntoskrnl!PsUpdateComponentPower` at `0x1400cdafa`
- `ntoskrnl!PsUpdateComponentPower` at `0x1400cdb1e`
- `ntoskrnl!PsUpdateComponentPower` at `0x1400cdb43`
- `ntoskrnl!RtlSetSystemGlobalData` at `0x1400cd2a8`
- `ntoskrnl!RtlSetSystemGlobalData` at `0x1400cd2a8`
- `WIN32K!W32GetUserSessionState` at `0x1400cd2b4`
- `WIN32K!W32GetUserSessionState` at `0x1400cd2d2`
- `WIN32K!W32GetUserSessionState` at `0x1400cd316`
- `WIN32K!W32GetUserSessionState` at `0x1400cd332`
- `WIN32K!W32GetUserSessionState` at `0x1400cd37e`
- `WIN32K!W32GetUserSessionState` at `0x1400cd5e9`
- `WIN32K!W32GetUserSessionState` at `0x1400cd60b`
- `WIN32K!W32GetUserSessionState` at `0x1400cd8a8`
- `WIN32K!W32GetUserSessionState` at `0x1400cd92b`
- `WIN32K!W32GetUserSessionState` at `0x1400cd2b4`
- `WIN32K!W32GetUserSessionState` at `0x1400cd2d2`
- `WIN32K!W32GetUserSessionState` at `0x1400cd316`
- `WIN32K!W32GetUserSessionState` at `0x1400cd332`
- `WIN32K!W32GetUserSessionState` at `0x1400cd37e`
- `WIN32K!W32GetUserSessionState` at `0x1400cd5e9`
- `WIN32K!W32GetUserSessionState` at `0x1400cd60b`
- `WIN32K!W32GetUserSessionState` at `0x1400cd8a8`
- `WIN32K!W32GetUserSessionState` at `0x1400cd92b`

## pseudocode

```c
void __fastcall CitpLastInputUpdate(__int64 a1, __int64 a2, __int64 a3)
{
  unsigned int v3; // ebp
  int v4; // r12d
  __int64 v5; // rdx
  __int64 v6; // rcx
  __int64 v7; // r8
  __int64 UserSessionState; // rax
  __int64 v9; // r8
  unsigned __int64 v10; // rcx
  __int64 v11; // rdx
  __int64 v12; // rax
  unsigned int v13; // r15d
  __int64 v14; // rcx
  __int64 v15; // rbx
  __int64 v16; // rdx
  __int64 v17; // r8
  unsigned __int64 v18; // rdx
  __int64 v19; // rcx
  __int64 v20; // r8
  __int64 v21; // r14
  unsigned int v22; // eax
  unsigned int v23; // esi
  int v24; // eax
  unsigned int v25; // r15d
  __int64 v26; // rdx
  __int64 v27; // rcx
  __int64 v28; // r8
  __int64 v29; // r14
  unsigned int v30; // eax
  unsigned int v31; // esi
  int v32; // eax
  unsigned __int64 *v33; // rdx
  unsigned __int64 v34; // rdi
  unsigned __int64 v35; // rcx
  __int16 v36; // si
  unsigned __int16 v37; // ax
  __int16 v38; // cx
  unsigned __int64 v39; // rdi
  unsigned __int64 v40; // rdi
  int v41; // r8d
  unsigned int v42; // edx
  unsigned int v43; // ecx
  unsigned int v44; // ecx
  __int64 v45; // rcx
  unsigned __int16 v46; // ax
  struct tagPROCESSINFO *v47; // rcx
  struct _CIT_PROCESS *v48; // rax
  struct _CIT_PROCESS *v49; // rdi
  struct _CIT_INTERACTION_SUMMARY *v50; // rsi
  _WORD *v51; // rbx
  __int64 v52; // rax
  int v53; // eax
  int v54; // eax
  unsigned __int64 v55; // rdx
  unsigned int v56; // eax
  unsigned int v57; // eax
  unsigned int v58; // [rsp+58h] [rbp+10h] BYREF

  v58 = a2;
  v3 = (unsigned __int16)a1;
  if ( (unsigned __int16)a1 == 32 )
  {
    v4 = 1;
  }
  else
  {
    v4 = 0;
    a2 = (unsigned int)(a2 - MEMORY[0xFFFFF780000002E4]);
    if ( (unsigned int)a2 > 0x3E8 )
      RtlSetSystemGlobalData(13, &v58, 4);
  }
  v6 = *(_QWORD *)(W32GetUserSessionState(a1, a2, a3) + 18992);
  if ( !*(_QWORD *)(v6 + 32) )
    return;
  UserSessionState = W32GetUserSessionState(v6, v5, v7);
  v10 = v58;
  v11 = *(_QWORD *)(UserSessionState + 18992);
  if ( v58 < *(_DWORD *)(v11 + 40) )
  {
    v10 = (MEMORY[0xFFFFF78000000320] * (unsigned __int64)MEMORY[0xFFFFF78000000004]) >> 24;
    v58 = v10;
  }
  *(_DWORD *)(v11 + 40) = v10;
  v12 = W32GetUserSessionState(v10, v11, v9);
  v13 = v58;
  v14 = *(_QWORD *)(v12 + 18992);
  v15 = *(_QWORD *)(v14 + 32);
  v21 = W32GetUserSessionState(v14, v16, v17);
  if ( !*(_DWORD *)(v21 + 19000) )
  {
    v19 = *(_QWORD *)(W32GetUserSessionState(v19, v18, v20) + 18992);
    v18 = *(unsigned int *)(v19 + 8);
    *(_DWORD *)(v21 + 19000) = v18;
  }
  v22 = *(_DWORD *)(v15 + 236);
  v23 = v13 - v22;
  if ( v13 != v22 )
  {
    if ( v13 < v22 )
    {
      v56 = *(_DWORD *)(v15 + 236);
      v39 = (MEMORY[0xFFFFF78000000320] * (unsigned __int64)MEMORY[0xFFFFF78000000004]) >> 24;
      v23 = v39 - v56;
      if ( (unsigned int)v39 < v56 )
      {
        v20 = *(_QWORD *)(W32GetUserSessionState(v19, v18, v20) + 18992);
        v19 = 0xFFFFFFFFLL;
        v18 = ((((unsigned __int64)MEMORY[0xFFFFF78000000004] << 32)
              * (unsigned __int128)(unsigned __int64)(MEMORY[0xFFFFF78000000320] << 8)) >> 64)
            - *(_QWORD *)(v20 + 64);
        if ( v18 > 0xFFFFFFFF )
          v18 = 0xFFFFFFFFLL;
        if ( v23 > (unsigned int)v18 || v23 > 0x240C8400 )
        {
          ++*(_DWORD *)(v15 + 240);
          *(_DWORD *)(v15 + 236) = v39;
          *(_DWORD *)(v15 + 232) = v39 - *(_DWORD *)(v21 + 19000);
          CIT_USER_ACTIVITY_STAT::SetActive((CIT_USER_ACTIVITY_STAT *)(v15 + 244), 0);
          goto LABEL_10;
        }
      }
    }
    else
    {
      LODWORD(v39) = v13;
    }
    if ( *(_DWORD *)(v15 + 228) )
    {
      *(_DWORD *)(v15 + 244) += v23;
    }
    else
    {
      v20 = *(unsigned int *)(v15 + 232);
      v18 = (unsigned int)(*(_DWORD *)(v15 + 236) - v20);
      v19 = *(unsigned int *)(v21 + 19000);
      if ( (unsigned int)v18 < (unsigned int)v19 )
      {
        if ( (int)v39 - (int)v20 > (unsigned int)v19 )
        {
          v53 = *(_DWORD *)(v15 + 248);
          v19 = (unsigned int)(v19 - v18);
          if ( v53 < 0 )
            *(_DWORD *)(v15 + 248) = v53 & 0x7FFFFFFF;
        }
        else
        {
          v19 = v23;
        }
        *(_DWORD *)(v15 + 244) += v19;
      }
    }
    *(_DWORD *)(v15 + 236) = v39;
  }
LABEL_10:
  v24 = *(_DWORD *)(v15 + 248);
  if ( v24 >= 0 )
    *(_DWORD *)(v15 + 248) = (v24 + 1) | 0x80000000;
  *(_DWORD *)(v15 + 232) = v13;
  if ( !v4 )
  {
    v25 = v58;
    v29 = W32GetUserSessionState(v19, v18, v20);
    if ( !*(_DWORD *)(v29 + 19000) )
    {
      v27 = *(_QWORD *)(W32GetUserSessionState(v27, v26, v28) + 18992);
      v26 = *(unsigned int *)(v27 + 8);
      *(_DWORD *)(v29 + 19000) = v26;
    }
    v30 = *(_DWORD *)(v15 + 212);
    v31 = v25 - v30;
    if ( v25 == v30 )
      goto LABEL_16;
    if ( v25 < v30 )
    {
      v57 = *(_DWORD *)(v15 + 212);
      v40 = (MEMORY[0xFFFFF78000000320] * (unsigned __int64)MEMORY[0xFFFFF78000000004]) >> 24;
      v31 = v40 - v57;
      if ( (unsigned int)v40 < v57 )
      {
        v55 = ((((unsigned __int64)MEMORY[0xFFFFF78000000004] << 32)
              * (unsigned __int128)(unsigned __int64)(MEMORY[0xFFFFF78000000320] << 8)) >> 64)
            - *(_QWORD *)(*(_QWORD *)(W32GetUserSessionState(v27, v26, v28) + 18992) + 64LL);
        if ( v55 > 0xFFFFFFFF )
          LODWORD(v55) = -1;
        if ( v31 > (unsigned int)v55 || v31 > 0x240C8400 )
        {
          ++*(_DWORD *)(v15 + 216);
          *(_DWORD *)(v15 + 212) = v40;
          *(_DWORD *)(v15 + 208) = v40 - *(_DWORD *)(v29 + 19000);
          CIT_USER_ACTIVITY_STAT::SetActive((CIT_USER_ACTIVITY_STAT *)(v15 + 220), 0);
LABEL_16:
          v32 = *(_DWORD *)(v15 + 224);
          if ( v32 >= 0 )
            *(_DWORD *)(v15 + 224) = (v32 + 1) | 0x80000000;
          *(_DWORD *)(v15 + 208) = v25;
          goto LABEL_19;
        }
      }
    }
    else
    {
      LODWORD(v40) = v25;
    }
    if ( *(_DWORD *)(v15 + 204) )
    {
      *(_DWORD *)(v15 + 220) += v31;
    }
    else
    {
      v41 = *(_DWORD *)(v15 + 208);
      v42 = *(_DWORD *)(v15 + 212) - v41;
      v43 = *(_DWORD *)(v29 + 19000);
      if ( v42 < v43 )
      {
        if ( (int)v40 - v41 > v43 )
        {
          v54 = *(_DWORD *)(v15 + 224);
          v44 = v43 - v42;
          if ( v54 < 0 )
            *(_DWORD *)(v15 + 224) = v54 & 0x7FFFFFFF;
        }
        else
        {
          v44 = v31;
        }
        *(_DWORD *)(v15 + 220) += v44;
      }
    }
    *(_DWORD *)(v15 + 212) = v40;
    goto LABEL_16;
  }
LABEL_19:
  v33 = *(unsigned __int64 **)(v15 + 120);
  if ( !v33 )
    return;
  v34 = v33[114];
  if ( v34 - 1 > 0xCEEE && v34 < 0xCEF2
    || (v35 = *(_QWORD *)(v34 + 24), v35 - 1 > 0xCEEE) && v35 < 0xCEF2
    || (v47 = *(struct tagPROCESSINFO **)(v35 + 8)) == 0
    || v47 == (struct tagPROCESSINFO *)v33 )
  {
    v36 = -1;
    if ( v58 - *(_DWORD *)(v34 + 100) > 0x3E8 )
    {
      *(_DWORD *)(v34 + 100) = v58;
      *(_WORD *)(v34 + 106) = 0;
      v37 = *(_WORD *)(v15 + 140);
      v38 = v37 + 1;
      if ( (unsigned __int16)(v37 + 1) < v37 )
        v38 = -1;
      *(_WORD *)(v15 + 140) = v38;
      PsUpdateComponentPower(**(_QWORD **)(v15 + 120), 9);
    }
    if ( ((unsigned __int16)v3 & *(_WORD *)(v34 + 106)) == 0 )
    {
      if ( v3 > 0x200 )
      {
        switch ( v3 )
        {
          case 0x800u:
            PsUpdateComponentPower(**(_QWORD **)(v15 + 120), 14);
            v45 = 150;
            break;
          case 0x400u:
            PsUpdateComponentPower(**(_QWORD **)(v15 + 120), 13);
            v45 = 146;
            break;
          case 0x1000u:
            v45 = 156;
            break;
          case 0x2000u:
            v45 = 160;
            break;
          case 0x4000u:
            v45 = 168;
            break;
          case 0x8000u:
            v45 = 162;
            break;
          default:
            return;
        }
      }
      else
      {
        switch ( v3 )
        {
          case 0x200u:
            PsUpdateComponentPower(**(_QWORD **)(v15 + 120), 13);
            v45 = 144;
            break;
          case 1u:
            PsUpdateComponentPower(**(_QWORD **)(v15 + 120), 13);
            v45 = 142;
            break;
          case 2u:
            PsUpdateComponentPower(**(_QWORD **)(v15 + 120), 14);
            v45 = 148;
            break;
          case 4u:
            v45 = 154;
            break;
          case 8u:
            v45 = 158;
            break;
          case 0x10u:
            v45 = 152;
            break;
          case 0x80u:
            v45 = 164;
            break;
          case 0x100u:
            v45 = 166;
            break;
          default:
            return;
        }
      }
      v46 = *(_WORD *)(v45 + v15);
      if ( (unsigned __int16)(v46 + 1) >= v46 )
        v36 = v46 + 1;
      *(_WORD *)(v45 + v15) = v36;
      *(_WORD *)(v34 + 106) |= v3;
    }
  }
  else
  {
    v48 = CitpProcessEnsureContext(v47);
    v49 = v48;
    if ( v48 )
    {
      v50 = CitpInteractionSummaryEnsure((struct _CIT_IMPACT_CONTEXT *)v15, v48, 1u);
      v51 = (_WORD *)((char *)v49 + 96);
      if ( v58 - *((_DWORD *)v49 + 23) > 0x3E8 )
      {
        *((_DWORD *)v49 + 23) = v58;
        *v51 = 0;
        if ( v50 )
          CitpStatIncrement((unsigned __int16 *)v50 + 16, 1u);
        PsUpdateComponentPower(**((_QWORD **)v49 + 1), 9);
      }
      if ( v50 && ((unsigned __int16)v3 & *v51) == 0 )
      {
        if ( v3 > 0x200 )
        {
          switch ( v3 )
          {
            case 0x400u:
              PsUpdateComponentPower(**((_QWORD **)v49 + 1), 13);
              v52 = 38;
              goto LABEL_87;
            case 0x800u:
              PsUpdateComponentPower(**((_QWORD **)v49 + 1), 14);
              v52 = 42;
              goto LABEL_87;
            case 0x1000u:
              v52 = 48;
              goto LABEL_87;
            case 0x2000u:
              v52 = 52;
              goto LABEL_87;
            case 0x4000u:
              v52 = 60;
              goto LABEL_87;
            case 0x8000u:
              v52 = 54;
              goto LABEL_87;
          }
        }
        else
        {
          switch ( v3 )
          {
            case 0x200u:
              PsUpdateComponentPower(**((_QWORD **)v49 + 1), 13);
              v52 = 36;
              goto LABEL_87;
            case 1u:
              PsUpdateComponentPower(**((_QWORD **)v49 + 1), 13);
              v52 = 34;
              goto LABEL_87;
            case 2u:
              PsUpdateComponentPower(**((_QWORD **)v49 + 1), 14);
              v52 = 40;
              goto LABEL_87;
            case 4u:
              v52 = 46;
              goto LABEL_87;
            case 8u:
              v52 = 50;
              goto LABEL_87;
            case 0x10u:
              v52 = 44;
              goto LABEL_87;
            case 0x80u:
              v52 = 56;
              goto LABEL_87;
            case 0x100u:
              v52 = 58;
LABEL_87:
              CitpStatIncrement((unsigned __int16 *)((char *)v50 + v52), 1u);
              *v51 |= v3;
              break;
          }
        }
      }
    }
  }
}

```

## disassembly

```asm
0x1400cd25c  mov     [rsp+arg_0], rbx
0x1400cd261  mov     [rsp+arg_10], rbp
0x1400cd266  mov     [rsp+arg_8], edx
0x1400cd26a  push    rsi
0x1400cd26b  push    rdi
0x1400cd26c  push    r12
0x1400cd26e  push    r14
0x1400cd270  push    r15
0x1400cd272  sub     rsp, 20h
0x1400cd276  movzx   ebp, cx
0x1400cd279  cmp     ebp, 20h ; ' '
0x1400cd27c  jz      loc_1400CD530
0x1400cd282  mov     rax, 0FFFFF780000002E4h
0x1400cd28c  xor     r12d, r12d
0x1400cd28f  sub     edx, [rax]
0x1400cd291  cmp     edx, 3E8h
0x1400cd297  jbe     short loc_1400CD2B4
0x1400cd299  lea     r8d, [r12+4]
0x1400cd29e  lea     rdx, [rsp+48h+arg_8]
0x1400cd2a3  lea     ecx, [r12+0Dh]
0x1400cd2a8  call    cs:__imp_RtlSetSystemGlobalData
0x1400cd2af  nop     dword ptr [rax+rax+00h]
0x1400cd2b4  call    cs:__imp_W32GetUserSessionState
0x1400cd2bb  nop     dword ptr [rax+rax+00h]
0x1400cd2c0  mov     rcx, [rax+4A30h]
0x1400cd2c7  cmp     qword ptr [rcx+20h], 0
0x1400cd2cc  jz      loc_1400CD46A
0x1400cd2d2  call    cs:__imp_W32GetUserSessionState
0x1400cd2d9  nop     dword ptr [rax+rax+00h]
0x1400cd2de  mov     ecx, [rsp+48h+arg_8]
0x1400cd2e2  mov     rdi, 0FFFFF78000000004h
0x1400cd2ec  mov     rdx, [rax+4A30h]
0x1400cd2f3  mov     rax, 0FFFFF78000000320h
0x1400cd2fd  cmp     ecx, [rdx+28h]
0x1400cd300  jnb     short loc_1400CD313
0x1400cd302  mov     rax, [rax]
0x1400cd305  mov     ecx, [rdi]
0x1400cd307  imul    rcx, rax
0x1400cd30b  shr     rcx, 18h
0x1400cd30f  mov     [rsp+48h+arg_8], ecx
0x1400cd313  mov     [rdx+28h], ecx
0x1400cd316  call    cs:__imp_W32GetUserSessionState
0x1400cd31d  nop     dword ptr [rax+rax+00h]
0x1400cd322  mov     r15d, [rsp+48h+arg_8]
0x1400cd327  mov     rcx, [rax+4A30h]
0x1400cd32e  mov     rbx, [rcx+20h]
0x1400cd332  call    cs:__imp_W32GetUserSessionState
0x1400cd339  nop     dword ptr [rax+rax+00h]
0x1400cd33e  mov     r14, rax
0x1400cd341  cmp     dword ptr [rax+4A38h], 0
0x1400cd348  jz      loc_1400CD5E9
0x1400cd34e  mov     eax, [rbx+0ECh]
0x1400cd354  mov     esi, r15d
0x1400cd357  sub     esi, eax
0x1400cd359  jnz     loc_1400CD482
0x1400cd35f  mov     eax, [rbx+0F8h]
0x1400cd365  test    eax, eax
0x1400cd367  jns     loc_1400CD784
0x1400cd36d  mov     [rbx+0E8h], r15d
0x1400cd374  test    r12d, r12d
0x1400cd377  jnz     short loc_1400CD3C0
0x1400cd379  mov     r15d, [rsp+48h+arg_8]
0x1400cd37e  call    cs:__imp_W32GetUserSessionState
0x1400cd385  nop     dword ptr [rax+rax+00h]
0x1400cd38a  mov     r14, rax
0x1400cd38d  cmp     [rax+4A38h], r12d
0x1400cd394  jz      loc_1400CD60B
0x1400cd39a  mov     eax, [rbx+0D4h]
0x1400cd3a0  mov     esi, r15d
0x1400cd3a3  sub     esi, eax
0x1400cd3a5  jnz     loc_1400CD4E0
0x1400cd3ab  mov     eax, [rbx+0E0h]
0x1400cd3b1  test    eax, eax
0x1400cd3b3  jns     loc_1400CD795
0x1400cd3b9  mov     [rbx+0D0h], r15d
0x1400cd3c0  mov     rdx, [rbx+78h]
0x1400cd3c4  test    rdx, rdx
0x1400cd3c7  jz      loc_1400CD46A
0x1400cd3cd  mov     rdi, [rdx+390h]
0x1400cd3d4  mov     r8d, 0CEF2h
0x1400cd3da  lea     rax, [rdi-1]
0x1400cd3de  lea     r9d, [r8-4]
0x1400cd3e2  cmp     rax, r9
0x1400cd3e5  jbe     short loc_1400CD3EC
0x1400cd3e7  cmp     rdi, r8
0x1400cd3ea  jb      short loc_1400CD406
0x1400cd3ec  mov     rcx, [rdi+18h]
0x1400cd3f0  lea     rax, [rcx-1]
0x1400cd3f4  cmp     rax, r9
0x1400cd3f7  jbe     loc_1400CD6A4
0x1400cd3fd  cmp     rcx, r8
0x1400cd400  jnb     loc_1400CD6A4
0x1400cd406  mov     ecx, [rsp+48h+arg_8]
0x1400cd40a  mov     esi, 0FFFFh
0x1400cd40f  mov     eax, ecx
0x1400cd411  mov     r14d, 1
0x1400cd417  sub     eax, [rdi+64h]
0x1400cd41a  cmp     eax, 3E8h
0x1400cd41f  jbe     short loc_1400CD460
0x1400cd421  xor     eax, eax
0x1400cd423  mov     [rdi+64h], ecx
0x1400cd426  mov     [rdi+6Ah], ax
0x1400cd42a  movzx   eax, word ptr [rbx+8Ch]
0x1400cd431  lea     ecx, [r14+rax]
0x1400cd435  cmp     cx, ax
0x1400cd438  jb      loc_1400CD5AB
0x1400cd43e  mov     [rbx+8Ch], cx
0x1400cd445  mov     r8, r14
0x1400cd448  mov     rcx, [rbx+78h]
0x1400cd44c  mov     edx, 9
0x1400cd451  mov     rcx, [rcx]
0x1400cd454  call    cs:__imp_PsUpdateComponentPower
0x1400cd45b  nop     dword ptr [rax+rax+00h]
0x1400cd460  test    [rdi+6Ah], bp
0x1400cd464  jz      loc_1400CD54B
0x1400cd46a  mov     rbx, [rsp+48h+arg_0]
0x1400cd46f  mov     rbp, [rsp+48h+arg_10]
0x1400cd474  add     rsp, 20h
0x1400cd478  pop     r15
0x1400cd47a  pop     r14
0x1400cd47c  pop     r12
0x1400cd47e  pop     rdi
0x1400cd47f  pop     rsi
0x1400cd480  retn
0x1400cd482  cmp     r15d, eax
0x1400cd485  jb      loc_1400CD9A5
0x1400cd48b  mov     edi, r15d
0x1400cd48e  cmp     dword ptr [rbx+0E4h], 0
0x1400cd495  jnz     loc_1400CD53B
0x1400cd49b  mov     edx, [rbx+0ECh]
0x1400cd4a1  mov     r8d, [rbx+0E8h]
0x1400cd4a8  sub     edx, r8d
0x1400cd4ab  mov     ecx, [r14+4A38h]
0x1400cd4b2  cmp     edx, ecx
0x1400cd4b4  jnb     short loc_1400CD4CB
0x1400cd4b6  mov     eax, edi
0x1400cd4b8  sub     eax, r8d
0x1400cd4bb  cmp     eax, ecx
0x1400cd4bd  ja      loc_1400CD7B0
0x1400cd4c3  mov     ecx, esi
0x1400cd4c5  add     [rbx+0F4h], ecx
0x1400cd4cb  mov     [rbx+0ECh], edi
0x1400cd4d1  mov     rdi, 0FFFFF78000000004h
0x1400cd4db  jmp     loc_1400CD35F
0x1400cd4e0  cmp     r15d, eax
0x1400cd4e3  jb      loc_1400CD9D3
0x1400cd4e9  mov     edi, r15d
0x1400cd4ec  cmp     dword ptr [rbx+0CCh], 0
0x1400cd4f3  jnz     short loc_1400CD543
0x1400cd4f5  mov     edx, [rbx+0D4h]
0x1400cd4fb  mov     r8d, [rbx+0D0h]
0x1400cd502  sub     edx, r8d
0x1400cd505  mov     ecx, [r14+4A38h]
0x1400cd50c  cmp     edx, ecx
0x1400cd50e  jnb     short loc_1400CD525
0x1400cd510  mov     eax, edi
0x1400cd512  sub     eax, r8d
0x1400cd515  cmp     eax, ecx
0x1400cd517  ja      loc_1400CD7CF
0x1400cd51d  mov     ecx, esi
0x1400cd51f  add     [rbx+0DCh], ecx
0x1400cd525  mov     [rbx+0D4h], edi
0x1400cd52b  jmp     loc_1400CD3AB
0x1400cd530  mov     r12d, 1
0x1400cd536  jmp     loc_1400CD2B4
0x1400cd53b  add     [rbx+0F4h], esi
0x1400cd541  jmp     short loc_1400CD4CB
0x1400cd543  add     [rbx+0DCh], esi
0x1400cd549  jmp     short loc_1400CD525
0x1400cd54b  mov     eax, 200h
0x1400cd550  mov     ecx, ebp
0x1400cd552  cmp     ebp, eax
0x1400cd554  ja      loc_1400CD652
0x1400cd55a  jz      loc_1400CDB34
0x1400cd560  sub     ecx, 1
0x1400cd563  jz      loc_1400CD62D
0x1400cd569  sub     ecx, 1
0x1400cd56c  jnz     short loc_1400CD5B2
0x1400cd56e  mov     rcx, [rbx+78h]
0x1400cd572  mov     r8, r14
0x1400cd575  mov     edx, 0Eh
0x1400cd57a  mov     rcx, [rcx]
0x1400cd57d  call    cs:__imp_PsUpdateComponentPower
0x1400cd584  nop     dword ptr [rax+rax+00h]
0x1400cd589  mov     ecx, 94h
0x1400cd58e  movzx   eax, word ptr [rcx+rbx]
0x1400cd592  lea     edx, [r14+rax]
0x1400cd596  cmp     dx, ax
0x1400cd599  jb      short loc_1400CD59E
0x1400cd59b  movzx   esi, dx
0x1400cd59e  mov     [rcx+rbx], si
0x1400cd5a2  or      [rdi+6Ah], bp
0x1400cd5a6  jmp     loc_1400CD46A
0x1400cd5ab  mov     ecx, esi
0x1400cd5ad  jmp     loc_1400CD43E
0x1400cd5b2  sub     ecx, 2
0x1400cd5b5  jz      loc_1400CD838
0x1400cd5bb  sub     ecx, 4
0x1400cd5be  jz      loc_1400CD894
0x1400cd5c4  sub     ecx, 8
0x1400cd5c7  jz      loc_1400CD77A
0x1400cd5cd  sub     ecx, 70h ; 'p'
0x1400cd5d0  jz      loc_1400CD7A6
0x1400cd5d6  cmp     ecx, 80h
0x1400cd5dc  jnz     loc_1400CD46A
0x1400cd5e2  mov     ecx, 0A6h
0x1400cd5e7  jmp     short loc_1400CD58E
0x1400cd5e9  call    cs:__imp_W32GetUserSessionState
0x1400cd5f0  nop     dword ptr [rax+rax+00h]
0x1400cd5f5  mov     rcx, [rax+4A30h]
0x1400cd5fc  mov     edx, [rcx+8]
0x1400cd5ff  mov     [r14+4A38h], edx
0x1400cd606  jmp     loc_1400CD34E
0x1400cd60b  call    cs:__imp_W32GetUserSessionState
0x1400cd612  nop     dword ptr [rax+rax+00h]
0x1400cd617  mov     rcx, [rax+4A30h]
0x1400cd61e  mov     edx, [rcx+8]
0x1400cd621  mov     [r14+4A38h], edx
0x1400cd628  jmp     loc_1400CD39A
0x1400cd62d  mov     rcx, [rbx+78h]
0x1400cd631  mov     r8, r14
0x1400cd634  mov     edx, 0Dh
0x1400cd639  mov     rcx, [rcx]
0x1400cd63c  call    cs:__imp_PsUpdateComponentPower
0x1400cd643  nop     dword ptr [rax+rax+00h]
0x1400cd648  mov     ecx, 8Eh
0x1400cd64d  jmp     loc_1400CD58E
0x1400cd652  cmp     ecx, 800h
0x1400cd658  jz      loc_1400CD7EE
0x1400cd65e  cmp     ecx, 400h
0x1400cd664  jz      loc_1400CD813
0x1400cd66a  cmp     ecx, 1000h
0x1400cd670  jz      loc_1400CD89E
0x1400cd676  cmp     ecx, 2000h
0x1400cd67c  jz      loc_1400CDB63
0x1400cd682  cmp     ecx, 4000h
0x1400cd688  jz      loc_1400CDB59
0x1400cd68e  cmp     ecx, 8000h
0x1400cd694  jnz     loc_1400CD46A
0x1400cd69a  mov     ecx, 0A2h
0x1400cd69f  jmp     loc_1400CD58E
0x1400cd6a4  mov     rcx, [rcx+8]; struct tagPROCESSINFO *
0x1400cd6a8  test    rcx, rcx
0x1400cd6ab  jz      loc_1400CD406
0x1400cd6b1  cmp     rcx, rdx
0x1400cd6b4  jz      loc_1400CD406
0x1400cd6ba  call    ?CitpProcessEnsureContext@@YAPEAU_CIT_PROCESS@@PEAUtagPROCESSINFO@@@Z; CitpProcessEnsureContext(tagPROCESSINFO *)
0x1400cd6bf  mov     rdi, rax
0x1400cd6c2  test    rax, rax
0x1400cd6c5  jz      loc_1400CD46A
0x1400cd6cb  mov     r8d, 1; unsigned __int16
0x1400cd6d1  mov     rdx, rax; struct _CIT_PROCESS *
0x1400cd6d4  mov     rcx, rbx; struct _CIT_IMPACT_CONTEXT *
0x1400cd6d7  call    ?CitpInteractionSummaryEnsure@@YAPEAU_CIT_INTERACTION_SUMMARY@@PEAU_CIT_IMPACT_CONTEXT@@PEAU_CIT_PROCESS@@G@Z; CitpInteractionSummaryEnsure(_CIT_IMPACT_CONTEXT *,_CIT_PROCESS *,ushort)
0x1400cd6dc  mov     rsi, rax
0x1400cd6df  lea     rbx, [rdi+60h]
0x1400cd6e3  mov     eax, [rsp+48h+arg_8]
0x1400cd6e7  mov     ecx, eax
0x1400cd6e9  sub     ecx, [rdi+5Ch]
0x1400cd6ec  cmp     ecx, 3E8h
0x1400cd6f2  ja      loc_1400CDA02
0x1400cd6f8  test    rsi, rsi
0x1400cd6fb  jz      loc_1400CD46A
0x1400cd701  test    [rbx], bp
0x1400cd704  jnz     loc_1400CD46A
0x1400cd70a  mov     eax, 200h
0x1400cd70f  mov     ecx, ebp
0x1400cd711  cmp     ebp, eax
0x1400cd713  ja      loc_1400CD842
0x1400cd719  jz      loc_1400CDAAA
0x1400cd71f  sub     ecx, 1
0x1400cd722  jz      loc_1400CDA86
0x1400cd728  sub     ecx, 1
0x1400cd72b  jz      loc_1400CDA62
0x1400cd731  sub     ecx, 2
0x1400cd734  jz      loc_1400CDA58
0x1400cd73a  sub     ecx, 4
0x1400cd73d  jz      loc_1400CDA4E
0x1400cd743  sub     ecx, 8
0x1400cd746  jz      loc_1400CDA44
0x1400cd74c  sub     ecx, 70h ; 'p'
0x1400cd74f  jz      loc_1400CDA3A
0x1400cd755  cmp     ecx, 80h
0x1400cd75b  jnz     loc_1400CD46A
0x1400cd761  lea     eax, [rcx-46h]
0x1400cd764  mov     edx, 1; unsigned __int16
0x1400cd769  lea     rcx, [rax+rsi]; unsigned __int16 *
0x1400cd76d  call    ?CitpStatIncrement@@YAXPEAGG@Z; CitpStatIncrement(ushort *,ushort)
0x1400cd772  or      [rbx], bp
0x1400cd775  jmp     loc_1400CD46A
0x1400cd77a  mov     ecx, 98h
0x1400cd77f  jmp     loc_1400CD58E
0x1400cd784  inc     eax
0x1400cd786  bts     eax, 1Fh
0x1400cd78a  mov     [rbx+0F8h], eax
0x1400cd790  jmp     loc_1400CD36D
0x1400cd795  inc     eax
0x1400cd797  bts     eax, 1Fh
0x1400cd79b  mov     [rbx+0E0h], eax
0x1400cd7a1  jmp     loc_1400CD3B9
  ... truncated ...
```
