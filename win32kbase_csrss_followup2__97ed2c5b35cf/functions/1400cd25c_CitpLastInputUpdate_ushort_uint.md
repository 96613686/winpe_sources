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
void __fastcall CitpLastInputUpdate(unsigned __int16 a1, unsigned int a2)
{
  unsigned int v2; // ebp
  int v3; // r12d
  __int64 UserSessionState; // rax
  unsigned __int64 v5; // rcx
  __int64 v6; // rdx
  __int64 v7; // rax
  unsigned int v8; // r15d
  __int64 v9; // rbx
  __int64 v10; // r14
  unsigned int v11; // eax
  unsigned int v12; // esi
  int v13; // eax
  unsigned int v14; // r15d
  __int64 v15; // r14
  unsigned int v16; // eax
  unsigned int v17; // esi
  int v18; // eax
  unsigned __int64 *v19; // rdx
  unsigned __int64 v20; // rdi
  unsigned __int64 v21; // rcx
  __int16 v22; // si
  unsigned __int16 v23; // ax
  __int16 v24; // cx
  unsigned __int64 v25; // rdi
  int v26; // r8d
  unsigned int v27; // edx
  unsigned int v28; // ecx
  unsigned int v29; // ecx
  unsigned __int64 v30; // rdi
  int v31; // r8d
  unsigned int v32; // edx
  unsigned int v33; // ecx
  unsigned int v34; // ecx
  __int64 v35; // rcx
  unsigned __int16 v36; // ax
  struct tagPROCESSINFO *v37; // rcx
  struct _CIT_PROCESS *v38; // rax
  struct _CIT_PROCESS *v39; // rdi
  struct _CIT_INTERACTION_SUMMARY *v40; // rsi
  _WORD *v41; // rbx
  __int64 v42; // rax
  int v43; // eax
  int v44; // eax
  unsigned __int64 v45; // rdx
  unsigned __int64 v46; // rdx
  unsigned int v47; // eax
  unsigned int v48; // eax
  unsigned int v49; // [rsp+58h] [rbp+10h] BYREF

  v49 = a2;
  v2 = a1;
  if ( a1 == 32 )
  {
    v3 = 1;
  }
  else
  {
    v3 = 0;
    if ( a2 - MEMORY[0xFFFFF780000002E4] > 0x3E8 )
      RtlSetSystemGlobalData(13, &v49, 4);
  }
  if ( !*(_QWORD *)(*(_QWORD *)(W32GetUserSessionState() + 18992) + 32LL) )
    return;
  UserSessionState = W32GetUserSessionState();
  LODWORD(v5) = v49;
  v6 = *(_QWORD *)(UserSessionState + 18992);
  if ( v49 < *(_DWORD *)(v6 + 40) )
  {
    v5 = (MEMORY[0xFFFFF78000000320] * (unsigned __int64)MEMORY[0xFFFFF78000000004]) >> 24;
    v49 = v5;
  }
  *(_DWORD *)(v6 + 40) = v5;
  v7 = W32GetUserSessionState();
  v8 = v49;
  v9 = *(_QWORD *)(*(_QWORD *)(v7 + 18992) + 32LL);
  v10 = W32GetUserSessionState();
  if ( !*(_DWORD *)(v10 + 19000) )
    *(_DWORD *)(v10 + 19000) = *(_DWORD *)(*(_QWORD *)(W32GetUserSessionState() + 18992) + 8LL);
  v11 = *(_DWORD *)(v9 + 236);
  v12 = v8 - v11;
  if ( v8 != v11 )
  {
    if ( v8 < v11 )
    {
      v47 = *(_DWORD *)(v9 + 236);
      v25 = (MEMORY[0xFFFFF78000000320] * (unsigned __int64)MEMORY[0xFFFFF78000000004]) >> 24;
      v12 = v25 - v47;
      if ( (unsigned int)v25 < v47 )
      {
        v45 = ((((unsigned __int64)MEMORY[0xFFFFF78000000004] << 32)
              * (unsigned __int128)(unsigned __int64)(MEMORY[0xFFFFF78000000320] << 8)) >> 64)
            - *(_QWORD *)(*(_QWORD *)(W32GetUserSessionState() + 18992) + 64LL);
        if ( v45 > 0xFFFFFFFF )
          LODWORD(v45) = -1;
        if ( v12 > (unsigned int)v45 || v12 > 0x240C8400 )
        {
          ++*(_DWORD *)(v9 + 240);
          *(_DWORD *)(v9 + 236) = v25;
          *(_DWORD *)(v9 + 232) = v25 - *(_DWORD *)(v10 + 19000);
          CIT_USER_ACTIVITY_STAT::SetActive((CIT_USER_ACTIVITY_STAT *)(v9 + 244), 0);
          goto LABEL_10;
        }
      }
    }
    else
    {
      LODWORD(v25) = v8;
    }
    if ( *(_DWORD *)(v9 + 228) )
    {
      *(_DWORD *)(v9 + 244) += v12;
    }
    else
    {
      v26 = *(_DWORD *)(v9 + 232);
      v27 = *(_DWORD *)(v9 + 236) - v26;
      v28 = *(_DWORD *)(v10 + 19000);
      if ( v27 < v28 )
      {
        if ( (int)v25 - v26 > v28 )
        {
          v43 = *(_DWORD *)(v9 + 248);
          v29 = v28 - v27;
          if ( v43 < 0 )
            *(_DWORD *)(v9 + 248) = v43 & 0x7FFFFFFF;
        }
        else
        {
          v29 = v12;
        }
        *(_DWORD *)(v9 + 244) += v29;
      }
    }
    *(_DWORD *)(v9 + 236) = v25;
  }
LABEL_10:
  v13 = *(_DWORD *)(v9 + 248);
  if ( v13 >= 0 )
    *(_DWORD *)(v9 + 248) = (v13 + 1) | 0x80000000;
  *(_DWORD *)(v9 + 232) = v8;
  if ( !v3 )
  {
    v14 = v49;
    v15 = W32GetUserSessionState();
    if ( !*(_DWORD *)(v15 + 19000) )
      *(_DWORD *)(v15 + 19000) = *(_DWORD *)(*(_QWORD *)(W32GetUserSessionState() + 18992) + 8LL);
    v16 = *(_DWORD *)(v9 + 212);
    v17 = v14 - v16;
    if ( v14 == v16 )
      goto LABEL_16;
    if ( v14 < v16 )
    {
      v48 = *(_DWORD *)(v9 + 212);
      v30 = (MEMORY[0xFFFFF78000000320] * (unsigned __int64)MEMORY[0xFFFFF78000000004]) >> 24;
      v17 = v30 - v48;
      if ( (unsigned int)v30 < v48 )
      {
        v46 = ((((unsigned __int64)MEMORY[0xFFFFF78000000004] << 32)
              * (unsigned __int128)(unsigned __int64)(MEMORY[0xFFFFF78000000320] << 8)) >> 64)
            - *(_QWORD *)(*(_QWORD *)(W32GetUserSessionState() + 18992) + 64LL);
        if ( v46 > 0xFFFFFFFF )
          LODWORD(v46) = -1;
        if ( v17 > (unsigned int)v46 || v17 > 0x240C8400 )
        {
          ++*(_DWORD *)(v9 + 216);
          *(_DWORD *)(v9 + 212) = v30;
          *(_DWORD *)(v9 + 208) = v30 - *(_DWORD *)(v15 + 19000);
          CIT_USER_ACTIVITY_STAT::SetActive((CIT_USER_ACTIVITY_STAT *)(v9 + 220), 0);
LABEL_16:
          v18 = *(_DWORD *)(v9 + 224);
          if ( v18 >= 0 )
            *(_DWORD *)(v9 + 224) = (v18 + 1) | 0x80000000;
          *(_DWORD *)(v9 + 208) = v14;
          goto LABEL_19;
        }
      }
    }
    else
    {
      LODWORD(v30) = v14;
    }
    if ( *(_DWORD *)(v9 + 204) )
    {
      *(_DWORD *)(v9 + 220) += v17;
    }
    else
    {
      v31 = *(_DWORD *)(v9 + 208);
      v32 = *(_DWORD *)(v9 + 212) - v31;
      v33 = *(_DWORD *)(v15 + 19000);
      if ( v32 < v33 )
      {
        if ( (int)v30 - v31 > v33 )
        {
          v44 = *(_DWORD *)(v9 + 224);
          v34 = v33 - v32;
          if ( v44 < 0 )
            *(_DWORD *)(v9 + 224) = v44 & 0x7FFFFFFF;
        }
        else
        {
          v34 = v17;
        }
        *(_DWORD *)(v9 + 220) += v34;
      }
    }
    *(_DWORD *)(v9 + 212) = v30;
    goto LABEL_16;
  }
LABEL_19:
  v19 = *(unsigned __int64 **)(v9 + 120);
  if ( !v19 )
    return;
  v20 = v19[114];
  if ( v20 - 1 > 0xCEEE && v20 < 0xCEF2
    || (v21 = *(_QWORD *)(v20 + 24), v21 - 1 > 0xCEEE) && v21 < 0xCEF2
    || (v37 = *(struct tagPROCESSINFO **)(v21 + 8)) == 0
    || v37 == (struct tagPROCESSINFO *)v19 )
  {
    v22 = -1;
    if ( v49 - *(_DWORD *)(v20 + 100) > 0x3E8 )
    {
      *(_DWORD *)(v20 + 100) = v49;
      *(_WORD *)(v20 + 106) = 0;
      v23 = *(_WORD *)(v9 + 140);
      v24 = v23 + 1;
      if ( (unsigned __int16)(v23 + 1) < v23 )
        v24 = -1;
      *(_WORD *)(v9 + 140) = v24;
      PsUpdateComponentPower(**(_QWORD **)(v9 + 120), 9);
    }
    if ( ((unsigned __int16)v2 & *(_WORD *)(v20 + 106)) == 0 )
    {
      if ( v2 > 0x200 )
      {
        switch ( v2 )
        {
          case 0x800u:
            PsUpdateComponentPower(**(_QWORD **)(v9 + 120), 14);
            v35 = 150;
            break;
          case 0x400u:
            PsUpdateComponentPower(**(_QWORD **)(v9 + 120), 13);
            v35 = 146;
            break;
          case 0x1000u:
            v35 = 156;
            break;
          case 0x2000u:
            v35 = 160;
            break;
          case 0x4000u:
            v35 = 168;
            break;
          case 0x8000u:
            v35 = 162;
            break;
          default:
            return;
        }
      }
      else
      {
        switch ( v2 )
        {
          case 0x200u:
            PsUpdateComponentPower(**(_QWORD **)(v9 + 120), 13);
            v35 = 144;
            break;
          case 1u:
            PsUpdateComponentPower(**(_QWORD **)(v9 + 120), 13);
            v35 = 142;
            break;
          case 2u:
            PsUpdateComponentPower(**(_QWORD **)(v9 + 120), 14);
            v35 = 148;
            break;
          case 4u:
            v35 = 154;
            break;
          case 8u:
            v35 = 158;
            break;
          case 0x10u:
            v35 = 152;
            break;
          case 0x80u:
            v35 = 164;
            break;
          case 0x100u:
            v35 = 166;
            break;
          default:
            return;
        }
      }
      v36 = *(_WORD *)(v35 + v9);
      if ( (unsigned __int16)(v36 + 1) >= v36 )
        v22 = v36 + 1;
      *(_WORD *)(v35 + v9) = v22;
      *(_WORD *)(v20 + 106) |= v2;
    }
  }
  else
  {
    v38 = CitpProcessEnsureContext(v37);
    v39 = v38;
    if ( v38 )
    {
      v40 = CitpInteractionSummaryEnsure((struct _CIT_IMPACT_CONTEXT *)v9, v38, 1u);
      v41 = (_WORD *)((char *)v39 + 96);
      if ( v49 - *((_DWORD *)v39 + 23) > 0x3E8 )
      {
        *((_DWORD *)v39 + 23) = v49;
        *v41 = 0;
        if ( v40 )
          CitpStatIncrement((unsigned __int16 *)v40 + 16, 1u);
        PsUpdateComponentPower(**((_QWORD **)v39 + 1), 9);
      }
      if ( v40 && ((unsigned __int16)v2 & *v41) == 0 )
      {
        if ( v2 > 0x200 )
        {
          switch ( v2 )
          {
            case 0x400u:
              PsUpdateComponentPower(**((_QWORD **)v39 + 1), 13);
              v42 = 38;
              goto LABEL_87;
            case 0x800u:
              PsUpdateComponentPower(**((_QWORD **)v39 + 1), 14);
              v42 = 42;
              goto LABEL_87;
            case 0x1000u:
              v42 = 48;
              goto LABEL_87;
            case 0x2000u:
              v42 = 52;
              goto LABEL_87;
            case 0x4000u:
              v42 = 60;
              goto LABEL_87;
            case 0x8000u:
              v42 = 54;
              goto LABEL_87;
          }
        }
        else
        {
          switch ( v2 )
          {
            case 0x200u:
              PsUpdateComponentPower(**((_QWORD **)v39 + 1), 13);
              v42 = 36;
              goto LABEL_87;
            case 1u:
              PsUpdateComponentPower(**((_QWORD **)v39 + 1), 13);
              v42 = 34;
              goto LABEL_87;
            case 2u:
              PsUpdateComponentPower(**((_QWORD **)v39 + 1), 14);
              v42 = 40;
              goto LABEL_87;
            case 4u:
              v42 = 46;
              goto LABEL_87;
            case 8u:
              v42 = 50;
              goto LABEL_87;
            case 0x10u:
              v42 = 44;
              goto LABEL_87;
            case 0x80u:
              v42 = 56;
              goto LABEL_87;
            case 0x100u:
              v42 = 58;
LABEL_87:
              CitpStatIncrement((unsigned __int16 *)((char *)v40 + v42), 1u);
              *v41 |= v2;
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
