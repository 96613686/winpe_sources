# CitpLastInputUpdate(ushort,uint)

- ea: `0x14005cdbc`
- end: `0x14005d6cd`
- name: `?CitpLastInputUpdate@@YAXGI@Z`
- size: `2321`
- prototype: `void __fastcall(unsigned __int16, unsigned int)`
- caller_count: `4`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14005c640`
- `0x14005ccc0`
- `0x14005f0fc`
- `0x1400c0e98`

## callees

- `0x1400287d4`
- `0x14005cdbc`
- `0x14005eaa4`
- `0x140119260`
- `0x140132168`

## import_xrefs

- `ntoskrnl!PsUpdateComponentPower` at `0x14005cfb4`
- `ntoskrnl!PsUpdateComponentPower` at `0x14005d0dd`
- `ntoskrnl!PsUpdateComponentPower` at `0x14005d19c`
- `ntoskrnl!PsUpdateComponentPower` at `0x14005d35d`
- `ntoskrnl!PsUpdateComponentPower` at `0x14005d382`
- `ntoskrnl!PsUpdateComponentPower` at `0x14005d589`
- `ntoskrnl!PsUpdateComponentPower` at `0x14005d5d0`
- `ntoskrnl!PsUpdateComponentPower` at `0x14005d5f4`
- `ntoskrnl!PsUpdateComponentPower` at `0x14005d618`
- `ntoskrnl!PsUpdateComponentPower` at `0x14005d65a`
- `ntoskrnl!PsUpdateComponentPower` at `0x14005d67e`
- `ntoskrnl!PsUpdateComponentPower` at `0x14005d6a3`
- `ntoskrnl!PsUpdateComponentPower` at `0x14005cfb4`
- `ntoskrnl!PsUpdateComponentPower` at `0x14005d0dd`
- `ntoskrnl!PsUpdateComponentPower` at `0x14005d19c`
- `ntoskrnl!PsUpdateComponentPower` at `0x14005d35d`
- `ntoskrnl!PsUpdateComponentPower` at `0x14005d382`
- `ntoskrnl!PsUpdateComponentPower` at `0x14005d589`
- `ntoskrnl!PsUpdateComponentPower` at `0x14005d5d0`
- `ntoskrnl!PsUpdateComponentPower` at `0x14005d5f4`
- `ntoskrnl!PsUpdateComponentPower` at `0x14005d618`
- `ntoskrnl!PsUpdateComponentPower` at `0x14005d65a`
- `ntoskrnl!PsUpdateComponentPower` at `0x14005d67e`
- `ntoskrnl!PsUpdateComponentPower` at `0x14005d6a3`
- `ntoskrnl!RtlSetSystemGlobalData` at `0x14005ce08`
- `ntoskrnl!RtlSetSystemGlobalData` at `0x14005ce08`
- `WIN32K!W32GetUserSessionState` at `0x14005ce14`
- `WIN32K!W32GetUserSessionState` at `0x14005ce32`
- `WIN32K!W32GetUserSessionState` at `0x14005ce76`
- `WIN32K!W32GetUserSessionState` at `0x14005ce92`
- `WIN32K!W32GetUserSessionState` at `0x14005cede`
- `WIN32K!W32GetUserSessionState` at `0x14005d149`
- `WIN32K!W32GetUserSessionState` at `0x14005d16b`
- `WIN32K!W32GetUserSessionState` at `0x14005d408`
- `WIN32K!W32GetUserSessionState` at `0x14005d48b`
- `WIN32K!W32GetUserSessionState` at `0x14005ce14`
- `WIN32K!W32GetUserSessionState` at `0x14005ce32`
- `WIN32K!W32GetUserSessionState` at `0x14005ce76`
- `WIN32K!W32GetUserSessionState` at `0x14005ce92`
- `WIN32K!W32GetUserSessionState` at `0x14005cede`
- `WIN32K!W32GetUserSessionState` at `0x14005d149`
- `WIN32K!W32GetUserSessionState` at `0x14005d16b`
- `WIN32K!W32GetUserSessionState` at `0x14005d408`
- `WIN32K!W32GetUserSessionState` at `0x14005d48b`

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
0x14005cdbc  mov     [rsp+arg_0], rbx
0x14005cdc1  mov     [rsp+arg_10], rbp
0x14005cdc6  mov     [rsp+arg_8], edx
0x14005cdca  push    rsi
0x14005cdcb  push    rdi
0x14005cdcc  push    r12
0x14005cdce  push    r14
0x14005cdd0  push    r15
0x14005cdd2  sub     rsp, 20h
0x14005cdd6  movzx   ebp, cx
0x14005cdd9  cmp     ebp, 20h ; ' '
0x14005cddc  jz      loc_14005D090
0x14005cde2  mov     rax, 0FFFFF780000002E4h
0x14005cdec  xor     r12d, r12d
0x14005cdef  sub     edx, [rax]
0x14005cdf1  cmp     edx, 3E8h
0x14005cdf7  jbe     short loc_14005CE14
0x14005cdf9  lea     r8d, [r12+4]
0x14005cdfe  lea     rdx, [rsp+48h+arg_8]
0x14005ce03  lea     ecx, [r12+0Dh]
0x14005ce08  call    cs:__imp_RtlSetSystemGlobalData
0x14005ce0f  nop     dword ptr [rax+rax+00h]
0x14005ce14  call    cs:__imp_W32GetUserSessionState
0x14005ce1b  nop     dword ptr [rax+rax+00h]
0x14005ce20  mov     rcx, [rax+4A30h]
0x14005ce27  cmp     qword ptr [rcx+20h], 0
0x14005ce2c  jz      loc_14005CFCA
0x14005ce32  call    cs:__imp_W32GetUserSessionState
0x14005ce39  nop     dword ptr [rax+rax+00h]
0x14005ce3e  mov     ecx, [rsp+48h+arg_8]
0x14005ce42  mov     rdi, 0FFFFF78000000004h
0x14005ce4c  mov     rdx, [rax+4A30h]
0x14005ce53  mov     rax, 0FFFFF78000000320h
0x14005ce5d  cmp     ecx, [rdx+28h]
0x14005ce60  jnb     short loc_14005CE73
0x14005ce62  mov     rax, [rax]
0x14005ce65  mov     ecx, [rdi]
0x14005ce67  imul    rcx, rax
0x14005ce6b  shr     rcx, 18h
0x14005ce6f  mov     [rsp+48h+arg_8], ecx
0x14005ce73  mov     [rdx+28h], ecx
0x14005ce76  call    cs:__imp_W32GetUserSessionState
0x14005ce7d  nop     dword ptr [rax+rax+00h]
0x14005ce82  mov     r15d, [rsp+48h+arg_8]
0x14005ce87  mov     rcx, [rax+4A30h]
0x14005ce8e  mov     rbx, [rcx+20h]
0x14005ce92  call    cs:__imp_W32GetUserSessionState
0x14005ce99  nop     dword ptr [rax+rax+00h]
0x14005ce9e  mov     r14, rax
0x14005cea1  cmp     dword ptr [rax+4A38h], 0
0x14005cea8  jz      loc_14005D149
0x14005ceae  mov     eax, [rbx+0ECh]
0x14005ceb4  mov     esi, r15d
0x14005ceb7  sub     esi, eax
0x14005ceb9  jnz     loc_14005CFE2
0x14005cebf  mov     eax, [rbx+0F8h]
0x14005cec5  test    eax, eax
0x14005cec7  jns     loc_14005D2E4
0x14005cecd  mov     [rbx+0E8h], r15d
0x14005ced4  test    r12d, r12d
0x14005ced7  jnz     short loc_14005CF20
0x14005ced9  mov     r15d, [rsp+48h+arg_8]
0x14005cede  call    cs:__imp_W32GetUserSessionState
0x14005cee5  nop     dword ptr [rax+rax+00h]
0x14005ceea  mov     r14, rax
0x14005ceed  cmp     [rax+4A38h], r12d
0x14005cef4  jz      loc_14005D16B
0x14005cefa  mov     eax, [rbx+0D4h]
0x14005cf00  mov     esi, r15d
0x14005cf03  sub     esi, eax
0x14005cf05  jnz     loc_14005D040
0x14005cf0b  mov     eax, [rbx+0E0h]
0x14005cf11  test    eax, eax
0x14005cf13  jns     loc_14005D2F5
0x14005cf19  mov     [rbx+0D0h], r15d
0x14005cf20  mov     rdx, [rbx+78h]
0x14005cf24  test    rdx, rdx
0x14005cf27  jz      loc_14005CFCA
0x14005cf2d  mov     rdi, [rdx+390h]
0x14005cf34  mov     r8d, 0CEF2h
0x14005cf3a  lea     rax, [rdi-1]
0x14005cf3e  lea     r9d, [r8-4]
0x14005cf42  cmp     rax, r9
0x14005cf45  jbe     short loc_14005CF4C
0x14005cf47  cmp     rdi, r8
0x14005cf4a  jb      short loc_14005CF66
0x14005cf4c  mov     rcx, [rdi+18h]
0x14005cf50  lea     rax, [rcx-1]
0x14005cf54  cmp     rax, r9
0x14005cf57  jbe     loc_14005D204
0x14005cf5d  cmp     rcx, r8
0x14005cf60  jnb     loc_14005D204
0x14005cf66  mov     ecx, [rsp+48h+arg_8]
0x14005cf6a  mov     esi, 0FFFFh
0x14005cf6f  mov     eax, ecx
0x14005cf71  mov     r14d, 1
0x14005cf77  sub     eax, [rdi+64h]
0x14005cf7a  cmp     eax, 3E8h
0x14005cf7f  jbe     short loc_14005CFC0
0x14005cf81  xor     eax, eax
0x14005cf83  mov     [rdi+64h], ecx
0x14005cf86  mov     [rdi+6Ah], ax
0x14005cf8a  movzx   eax, word ptr [rbx+8Ch]
0x14005cf91  lea     ecx, [r14+rax]
0x14005cf95  cmp     cx, ax
0x14005cf98  jb      loc_14005D10B
0x14005cf9e  mov     [rbx+8Ch], cx
0x14005cfa5  mov     r8, r14
0x14005cfa8  mov     rcx, [rbx+78h]
0x14005cfac  mov     edx, 9
0x14005cfb1  mov     rcx, [rcx]
0x14005cfb4  call    cs:__imp_PsUpdateComponentPower
0x14005cfbb  nop     dword ptr [rax+rax+00h]
0x14005cfc0  test    [rdi+6Ah], bp
0x14005cfc4  jz      loc_14005D0AB
0x14005cfca  mov     rbx, [rsp+48h+arg_0]
0x14005cfcf  mov     rbp, [rsp+48h+arg_10]
0x14005cfd4  add     rsp, 20h
0x14005cfd8  pop     r15
0x14005cfda  pop     r14
0x14005cfdc  pop     r12
0x14005cfde  pop     rdi
0x14005cfdf  pop     rsi
0x14005cfe0  retn
0x14005cfe2  cmp     r15d, eax
0x14005cfe5  jb      loc_14005D505
0x14005cfeb  mov     edi, r15d
0x14005cfee  cmp     dword ptr [rbx+0E4h], 0
0x14005cff5  jnz     loc_14005D09B
0x14005cffb  mov     edx, [rbx+0ECh]
0x14005d001  mov     r8d, [rbx+0E8h]
0x14005d008  sub     edx, r8d
0x14005d00b  mov     ecx, [r14+4A38h]
0x14005d012  cmp     edx, ecx
0x14005d014  jnb     short loc_14005D02B
0x14005d016  mov     eax, edi
0x14005d018  sub     eax, r8d
0x14005d01b  cmp     eax, ecx
0x14005d01d  ja      loc_14005D310
0x14005d023  mov     ecx, esi
0x14005d025  add     [rbx+0F4h], ecx
0x14005d02b  mov     [rbx+0ECh], edi
0x14005d031  mov     rdi, 0FFFFF78000000004h
0x14005d03b  jmp     loc_14005CEBF
0x14005d040  cmp     r15d, eax
0x14005d043  jb      loc_14005D533
0x14005d049  mov     edi, r15d
0x14005d04c  cmp     dword ptr [rbx+0CCh], 0
0x14005d053  jnz     short loc_14005D0A3
0x14005d055  mov     edx, [rbx+0D4h]
0x14005d05b  mov     r8d, [rbx+0D0h]
0x14005d062  sub     edx, r8d
0x14005d065  mov     ecx, [r14+4A38h]
0x14005d06c  cmp     edx, ecx
0x14005d06e  jnb     short loc_14005D085
0x14005d070  mov     eax, edi
0x14005d072  sub     eax, r8d
0x14005d075  cmp     eax, ecx
0x14005d077  ja      loc_14005D32F
0x14005d07d  mov     ecx, esi
0x14005d07f  add     [rbx+0DCh], ecx
0x14005d085  mov     [rbx+0D4h], edi
0x14005d08b  jmp     loc_14005CF0B
0x14005d090  mov     r12d, 1
0x14005d096  jmp     loc_14005CE14
0x14005d09b  add     [rbx+0F4h], esi
0x14005d0a1  jmp     short loc_14005D02B
0x14005d0a3  add     [rbx+0DCh], esi
0x14005d0a9  jmp     short loc_14005D085
0x14005d0ab  mov     eax, 200h
0x14005d0b0  mov     ecx, ebp
0x14005d0b2  cmp     ebp, eax
0x14005d0b4  ja      loc_14005D1B2
0x14005d0ba  jz      loc_14005D694
0x14005d0c0  sub     ecx, 1
0x14005d0c3  jz      loc_14005D18D
0x14005d0c9  sub     ecx, 1
0x14005d0cc  jnz     short loc_14005D112
0x14005d0ce  mov     rcx, [rbx+78h]
0x14005d0d2  mov     r8, r14
0x14005d0d5  mov     edx, 0Eh
0x14005d0da  mov     rcx, [rcx]
0x14005d0dd  call    cs:__imp_PsUpdateComponentPower
0x14005d0e4  nop     dword ptr [rax+rax+00h]
0x14005d0e9  mov     ecx, 94h
0x14005d0ee  movzx   eax, word ptr [rcx+rbx]
0x14005d0f2  lea     edx, [r14+rax]
0x14005d0f6  cmp     dx, ax
0x14005d0f9  jb      short loc_14005D0FE
0x14005d0fb  movzx   esi, dx
0x14005d0fe  mov     [rcx+rbx], si
0x14005d102  or      [rdi+6Ah], bp
0x14005d106  jmp     loc_14005CFCA
0x14005d10b  mov     ecx, esi
0x14005d10d  jmp     loc_14005CF9E
0x14005d112  sub     ecx, 2
0x14005d115  jz      loc_14005D398
0x14005d11b  sub     ecx, 4
0x14005d11e  jz      loc_14005D3F4
0x14005d124  sub     ecx, 8
0x14005d127  jz      loc_14005D2DA
0x14005d12d  sub     ecx, 70h ; 'p'
0x14005d130  jz      loc_14005D306
0x14005d136  cmp     ecx, 80h
0x14005d13c  jnz     loc_14005CFCA
0x14005d142  mov     ecx, 0A6h
0x14005d147  jmp     short loc_14005D0EE
0x14005d149  call    cs:__imp_W32GetUserSessionState
0x14005d150  nop     dword ptr [rax+rax+00h]
0x14005d155  mov     rcx, [rax+4A30h]
0x14005d15c  mov     edx, [rcx+8]
0x14005d15f  mov     [r14+4A38h], edx
0x14005d166  jmp     loc_14005CEAE
0x14005d16b  call    cs:__imp_W32GetUserSessionState
0x14005d172  nop     dword ptr [rax+rax+00h]
0x14005d177  mov     rcx, [rax+4A30h]
0x14005d17e  mov     edx, [rcx+8]
0x14005d181  mov     [r14+4A38h], edx
0x14005d188  jmp     loc_14005CEFA
0x14005d18d  mov     rcx, [rbx+78h]
0x14005d191  mov     r8, r14
0x14005d194  mov     edx, 0Dh
0x14005d199  mov     rcx, [rcx]
0x14005d19c  call    cs:__imp_PsUpdateComponentPower
0x14005d1a3  nop     dword ptr [rax+rax+00h]
0x14005d1a8  mov     ecx, 8Eh
0x14005d1ad  jmp     loc_14005D0EE
0x14005d1b2  cmp     ecx, 800h
0x14005d1b8  jz      loc_14005D34E
0x14005d1be  cmp     ecx, 400h
0x14005d1c4  jz      loc_14005D373
0x14005d1ca  cmp     ecx, 1000h
0x14005d1d0  jz      loc_14005D3FE
0x14005d1d6  cmp     ecx, 2000h
0x14005d1dc  jz      loc_14005D6C3
0x14005d1e2  cmp     ecx, 4000h
0x14005d1e8  jz      loc_14005D6B9
0x14005d1ee  cmp     ecx, 8000h
0x14005d1f4  jnz     loc_14005CFCA
0x14005d1fa  mov     ecx, 0A2h
0x14005d1ff  jmp     loc_14005D0EE
0x14005d204  mov     rcx, [rcx+8]; struct tagPROCESSINFO *
0x14005d208  test    rcx, rcx
0x14005d20b  jz      loc_14005CF66
0x14005d211  cmp     rcx, rdx
0x14005d214  jz      loc_14005CF66
0x14005d21a  call    ?CitpProcessEnsureContext@@YAPEAU_CIT_PROCESS@@PEAUtagPROCESSINFO@@@Z; CitpProcessEnsureContext(tagPROCESSINFO *)
0x14005d21f  mov     rdi, rax
0x14005d222  test    rax, rax
0x14005d225  jz      loc_14005CFCA
0x14005d22b  mov     r8d, 1; unsigned __int16
0x14005d231  mov     rdx, rax; struct _CIT_PROCESS *
0x14005d234  mov     rcx, rbx; struct _CIT_IMPACT_CONTEXT *
0x14005d237  call    ?CitpInteractionSummaryEnsure@@YAPEAU_CIT_INTERACTION_SUMMARY@@PEAU_CIT_IMPACT_CONTEXT@@PEAU_CIT_PROCESS@@G@Z; CitpInteractionSummaryEnsure(_CIT_IMPACT_CONTEXT *,_CIT_PROCESS *,ushort)
0x14005d23c  mov     rsi, rax
0x14005d23f  lea     rbx, [rdi+60h]
0x14005d243  mov     eax, [rsp+48h+arg_8]
0x14005d247  mov     ecx, eax
0x14005d249  sub     ecx, [rdi+5Ch]
0x14005d24c  cmp     ecx, 3E8h
0x14005d252  ja      loc_14005D562
0x14005d258  test    rsi, rsi
0x14005d25b  jz      loc_14005CFCA
0x14005d261  test    [rbx], bp
0x14005d264  jnz     loc_14005CFCA
0x14005d26a  mov     eax, 200h
0x14005d26f  mov     ecx, ebp
0x14005d271  cmp     ebp, eax
0x14005d273  ja      loc_14005D3A2
0x14005d279  jz      loc_14005D60A
0x14005d27f  sub     ecx, 1
0x14005d282  jz      loc_14005D5E6
0x14005d288  sub     ecx, 1
0x14005d28b  jz      loc_14005D5C2
0x14005d291  sub     ecx, 2
0x14005d294  jz      loc_14005D5B8
0x14005d29a  sub     ecx, 4
0x14005d29d  jz      loc_14005D5AE
0x14005d2a3  sub     ecx, 8
0x14005d2a6  jz      loc_14005D5A4
0x14005d2ac  sub     ecx, 70h ; 'p'
0x14005d2af  jz      loc_14005D59A
0x14005d2b5  cmp     ecx, 80h
0x14005d2bb  jnz     loc_14005CFCA
0x14005d2c1  lea     eax, [rcx-46h]
0x14005d2c4  mov     edx, 1; unsigned __int16
0x14005d2c9  lea     rcx, [rax+rsi]; unsigned __int16 *
0x14005d2cd  call    ?CitpStatIncrement@@YAXPEAGG@Z; CitpStatIncrement(ushort *,ushort)
0x14005d2d2  or      [rbx], bp
0x14005d2d5  jmp     loc_14005CFCA
0x14005d2da  mov     ecx, 98h
0x14005d2df  jmp     loc_14005D0EE
0x14005d2e4  inc     eax
0x14005d2e6  bts     eax, 1Fh
0x14005d2ea  mov     [rbx+0F8h], eax
0x14005d2f0  jmp     loc_14005CECD
0x14005d2f5  inc     eax
0x14005d2f7  bts     eax, 1Fh
0x14005d2fb  mov     [rbx+0E0h], eax
0x14005d301  jmp     loc_14005CF19
  ... truncated ...
```
