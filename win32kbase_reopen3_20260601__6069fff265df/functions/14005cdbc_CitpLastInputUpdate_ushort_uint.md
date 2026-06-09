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
