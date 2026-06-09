# CitpLastInputUpdate(ushort,uint)

- ea: `0x1400bfe7c`
- end: `0x1400c078d`
- name: `?CitpLastInputUpdate@@YAXGI@Z`
- size: `2321`
- prototype: `void __fastcall(unsigned __int16, unsigned int)`
- caller_count: `4`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1400bf700`
- `0x1400bfd80`
- `0x1400c23ac`
- `0x1400cff38`

## callees

- `0x140037020`
- `0x1400bfe7c`
- `0x1400c1b64`
- `0x14011c240`
- `0x1401343c8`

## import_xrefs

- `ntoskrnl!PsUpdateComponentPower` at `0x1400c0074`
- `ntoskrnl!PsUpdateComponentPower` at `0x1400c019d`
- `ntoskrnl!PsUpdateComponentPower` at `0x1400c025c`
- `ntoskrnl!PsUpdateComponentPower` at `0x1400c041d`
- `ntoskrnl!PsUpdateComponentPower` at `0x1400c0442`
- `ntoskrnl!PsUpdateComponentPower` at `0x1400c0649`
- `ntoskrnl!PsUpdateComponentPower` at `0x1400c0690`
- `ntoskrnl!PsUpdateComponentPower` at `0x1400c06b4`
- `ntoskrnl!PsUpdateComponentPower` at `0x1400c06d8`
- `ntoskrnl!PsUpdateComponentPower` at `0x1400c071a`
- `ntoskrnl!PsUpdateComponentPower` at `0x1400c073e`
- `ntoskrnl!PsUpdateComponentPower` at `0x1400c0763`
- `ntoskrnl!PsUpdateComponentPower` at `0x1400c0074`
- `ntoskrnl!PsUpdateComponentPower` at `0x1400c019d`
- `ntoskrnl!PsUpdateComponentPower` at `0x1400c025c`
- `ntoskrnl!PsUpdateComponentPower` at `0x1400c041d`
- `ntoskrnl!PsUpdateComponentPower` at `0x1400c0442`
- `ntoskrnl!PsUpdateComponentPower` at `0x1400c0649`
- `ntoskrnl!PsUpdateComponentPower` at `0x1400c0690`
- `ntoskrnl!PsUpdateComponentPower` at `0x1400c06b4`
- `ntoskrnl!PsUpdateComponentPower` at `0x1400c06d8`
- `ntoskrnl!PsUpdateComponentPower` at `0x1400c071a`
- `ntoskrnl!PsUpdateComponentPower` at `0x1400c073e`
- `ntoskrnl!PsUpdateComponentPower` at `0x1400c0763`
- `ntoskrnl!RtlSetSystemGlobalData` at `0x1400bfec8`
- `ntoskrnl!RtlSetSystemGlobalData` at `0x1400bfec8`
- `WIN32K!W32GetUserSessionState` at `0x1400bfed4`
- `WIN32K!W32GetUserSessionState` at `0x1400bfef2`
- `WIN32K!W32GetUserSessionState` at `0x1400bff36`
- `WIN32K!W32GetUserSessionState` at `0x1400bff52`
- `WIN32K!W32GetUserSessionState` at `0x1400bff9e`
- `WIN32K!W32GetUserSessionState` at `0x1400c0209`
- `WIN32K!W32GetUserSessionState` at `0x1400c022b`
- `WIN32K!W32GetUserSessionState` at `0x1400c04c8`
- `WIN32K!W32GetUserSessionState` at `0x1400c054b`
- `WIN32K!W32GetUserSessionState` at `0x1400bfed4`
- `WIN32K!W32GetUserSessionState` at `0x1400bfef2`
- `WIN32K!W32GetUserSessionState` at `0x1400bff36`
- `WIN32K!W32GetUserSessionState` at `0x1400bff52`
- `WIN32K!W32GetUserSessionState` at `0x1400bff9e`
- `WIN32K!W32GetUserSessionState` at `0x1400c0209`
- `WIN32K!W32GetUserSessionState` at `0x1400c022b`
- `WIN32K!W32GetUserSessionState` at `0x1400c04c8`
- `WIN32K!W32GetUserSessionState` at `0x1400c054b`

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
0x1400bfe7c  mov     [rsp+arg_0], rbx
0x1400bfe81  mov     [rsp+arg_10], rbp
0x1400bfe86  mov     [rsp+arg_8], edx
0x1400bfe8a  push    rsi
0x1400bfe8b  push    rdi
0x1400bfe8c  push    r12
0x1400bfe8e  push    r14
0x1400bfe90  push    r15
0x1400bfe92  sub     rsp, 20h
0x1400bfe96  movzx   ebp, cx
0x1400bfe99  cmp     ebp, 20h ; ' '
0x1400bfe9c  jz      loc_1400C0150
0x1400bfea2  mov     rax, 0FFFFF780000002E4h
0x1400bfeac  xor     r12d, r12d
0x1400bfeaf  sub     edx, [rax]
0x1400bfeb1  cmp     edx, 3E8h
0x1400bfeb7  jbe     short loc_1400BFED4
0x1400bfeb9  lea     r8d, [r12+4]
0x1400bfebe  lea     rdx, [rsp+48h+arg_8]
0x1400bfec3  lea     ecx, [r12+0Dh]
0x1400bfec8  call    cs:__imp_RtlSetSystemGlobalData
0x1400bfecf  nop     dword ptr [rax+rax+00h]
0x1400bfed4  call    cs:__imp_W32GetUserSessionState
0x1400bfedb  nop     dword ptr [rax+rax+00h]
0x1400bfee0  mov     rcx, [rax+4A30h]
0x1400bfee7  cmp     qword ptr [rcx+20h], 0
0x1400bfeec  jz      loc_1400C008A
0x1400bfef2  call    cs:__imp_W32GetUserSessionState
0x1400bfef9  nop     dword ptr [rax+rax+00h]
0x1400bfefe  mov     ecx, [rsp+48h+arg_8]
0x1400bff02  mov     rdi, 0FFFFF78000000004h
0x1400bff0c  mov     rdx, [rax+4A30h]
0x1400bff13  mov     rax, 0FFFFF78000000320h
0x1400bff1d  cmp     ecx, [rdx+28h]
0x1400bff20  jnb     short loc_1400BFF33
0x1400bff22  mov     rax, [rax]
0x1400bff25  mov     ecx, [rdi]
0x1400bff27  imul    rcx, rax
0x1400bff2b  shr     rcx, 18h
0x1400bff2f  mov     [rsp+48h+arg_8], ecx
0x1400bff33  mov     [rdx+28h], ecx
0x1400bff36  call    cs:__imp_W32GetUserSessionState
0x1400bff3d  nop     dword ptr [rax+rax+00h]
0x1400bff42  mov     r15d, [rsp+48h+arg_8]
0x1400bff47  mov     rcx, [rax+4A30h]
0x1400bff4e  mov     rbx, [rcx+20h]
0x1400bff52  call    cs:__imp_W32GetUserSessionState
0x1400bff59  nop     dword ptr [rax+rax+00h]
0x1400bff5e  mov     r14, rax
0x1400bff61  cmp     dword ptr [rax+4A38h], 0
0x1400bff68  jz      loc_1400C0209
0x1400bff6e  mov     eax, [rbx+0ECh]
0x1400bff74  mov     esi, r15d
0x1400bff77  sub     esi, eax
0x1400bff79  jnz     loc_1400C00A2
0x1400bff7f  mov     eax, [rbx+0F8h]
0x1400bff85  test    eax, eax
0x1400bff87  jns     loc_1400C03A4
0x1400bff8d  mov     [rbx+0E8h], r15d
0x1400bff94  test    r12d, r12d
0x1400bff97  jnz     short loc_1400BFFE0
0x1400bff99  mov     r15d, [rsp+48h+arg_8]
0x1400bff9e  call    cs:__imp_W32GetUserSessionState
0x1400bffa5  nop     dword ptr [rax+rax+00h]
0x1400bffaa  mov     r14, rax
0x1400bffad  cmp     [rax+4A38h], r12d
0x1400bffb4  jz      loc_1400C022B
0x1400bffba  mov     eax, [rbx+0D4h]
0x1400bffc0  mov     esi, r15d
0x1400bffc3  sub     esi, eax
0x1400bffc5  jnz     loc_1400C0100
0x1400bffcb  mov     eax, [rbx+0E0h]
0x1400bffd1  test    eax, eax
0x1400bffd3  jns     loc_1400C03B5
0x1400bffd9  mov     [rbx+0D0h], r15d
0x1400bffe0  mov     rdx, [rbx+78h]
0x1400bffe4  test    rdx, rdx
0x1400bffe7  jz      loc_1400C008A
0x1400bffed  mov     rdi, [rdx+390h]
0x1400bfff4  mov     r8d, 0CEF2h
0x1400bfffa  lea     rax, [rdi-1]
0x1400bfffe  lea     r9d, [r8-4]
0x1400c0002  cmp     rax, r9
0x1400c0005  jbe     short loc_1400C000C
0x1400c0007  cmp     rdi, r8
0x1400c000a  jb      short loc_1400C0026
0x1400c000c  mov     rcx, [rdi+18h]
0x1400c0010  lea     rax, [rcx-1]
0x1400c0014  cmp     rax, r9
0x1400c0017  jbe     loc_1400C02C4
0x1400c001d  cmp     rcx, r8
0x1400c0020  jnb     loc_1400C02C4
0x1400c0026  mov     ecx, [rsp+48h+arg_8]
0x1400c002a  mov     esi, 0FFFFh
0x1400c002f  mov     eax, ecx
0x1400c0031  mov     r14d, 1
0x1400c0037  sub     eax, [rdi+64h]
0x1400c003a  cmp     eax, 3E8h
0x1400c003f  jbe     short loc_1400C0080
0x1400c0041  xor     eax, eax
0x1400c0043  mov     [rdi+64h], ecx
0x1400c0046  mov     [rdi+6Ah], ax
0x1400c004a  movzx   eax, word ptr [rbx+8Ch]
0x1400c0051  lea     ecx, [r14+rax]
0x1400c0055  cmp     cx, ax
0x1400c0058  jb      loc_1400C01CB
0x1400c005e  mov     [rbx+8Ch], cx
0x1400c0065  mov     r8, r14
0x1400c0068  mov     rcx, [rbx+78h]
0x1400c006c  mov     edx, 9
0x1400c0071  mov     rcx, [rcx]
0x1400c0074  call    cs:__imp_PsUpdateComponentPower
0x1400c007b  nop     dword ptr [rax+rax+00h]
0x1400c0080  test    [rdi+6Ah], bp
0x1400c0084  jz      loc_1400C016B
0x1400c008a  mov     rbx, [rsp+48h+arg_0]
0x1400c008f  mov     rbp, [rsp+48h+arg_10]
0x1400c0094  add     rsp, 20h
0x1400c0098  pop     r15
0x1400c009a  pop     r14
0x1400c009c  pop     r12
0x1400c009e  pop     rdi
0x1400c009f  pop     rsi
0x1400c00a0  retn
0x1400c00a2  cmp     r15d, eax
0x1400c00a5  jb      loc_1400C05C5
0x1400c00ab  mov     edi, r15d
0x1400c00ae  cmp     dword ptr [rbx+0E4h], 0
0x1400c00b5  jnz     loc_1400C015B
0x1400c00bb  mov     edx, [rbx+0ECh]
0x1400c00c1  mov     r8d, [rbx+0E8h]
0x1400c00c8  sub     edx, r8d
0x1400c00cb  mov     ecx, [r14+4A38h]
0x1400c00d2  cmp     edx, ecx
0x1400c00d4  jnb     short loc_1400C00EB
0x1400c00d6  mov     eax, edi
0x1400c00d8  sub     eax, r8d
0x1400c00db  cmp     eax, ecx
0x1400c00dd  ja      loc_1400C03D0
0x1400c00e3  mov     ecx, esi
0x1400c00e5  add     [rbx+0F4h], ecx
0x1400c00eb  mov     [rbx+0ECh], edi
0x1400c00f1  mov     rdi, 0FFFFF78000000004h
0x1400c00fb  jmp     loc_1400BFF7F
0x1400c0100  cmp     r15d, eax
0x1400c0103  jb      loc_1400C05F3
0x1400c0109  mov     edi, r15d
0x1400c010c  cmp     dword ptr [rbx+0CCh], 0
0x1400c0113  jnz     short loc_1400C0163
0x1400c0115  mov     edx, [rbx+0D4h]
0x1400c011b  mov     r8d, [rbx+0D0h]
0x1400c0122  sub     edx, r8d
0x1400c0125  mov     ecx, [r14+4A38h]
0x1400c012c  cmp     edx, ecx
0x1400c012e  jnb     short loc_1400C0145
0x1400c0130  mov     eax, edi
0x1400c0132  sub     eax, r8d
0x1400c0135  cmp     eax, ecx
0x1400c0137  ja      loc_1400C03EF
0x1400c013d  mov     ecx, esi
0x1400c013f  add     [rbx+0DCh], ecx
0x1400c0145  mov     [rbx+0D4h], edi
0x1400c014b  jmp     loc_1400BFFCB
0x1400c0150  mov     r12d, 1
0x1400c0156  jmp     loc_1400BFED4
0x1400c015b  add     [rbx+0F4h], esi
0x1400c0161  jmp     short loc_1400C00EB
0x1400c0163  add     [rbx+0DCh], esi
0x1400c0169  jmp     short loc_1400C0145
0x1400c016b  mov     eax, 200h
0x1400c0170  mov     ecx, ebp
0x1400c0172  cmp     ebp, eax
0x1400c0174  ja      loc_1400C0272
0x1400c017a  jz      loc_1400C0754
0x1400c0180  sub     ecx, 1
0x1400c0183  jz      loc_1400C024D
0x1400c0189  sub     ecx, 1
0x1400c018c  jnz     short loc_1400C01D2
0x1400c018e  mov     rcx, [rbx+78h]
0x1400c0192  mov     r8, r14
0x1400c0195  mov     edx, 0Eh
0x1400c019a  mov     rcx, [rcx]
0x1400c019d  call    cs:__imp_PsUpdateComponentPower
0x1400c01a4  nop     dword ptr [rax+rax+00h]
0x1400c01a9  mov     ecx, 94h
0x1400c01ae  movzx   eax, word ptr [rcx+rbx]
0x1400c01b2  lea     edx, [r14+rax]
0x1400c01b6  cmp     dx, ax
0x1400c01b9  jb      short loc_1400C01BE
0x1400c01bb  movzx   esi, dx
0x1400c01be  mov     [rcx+rbx], si
0x1400c01c2  or      [rdi+6Ah], bp
0x1400c01c6  jmp     loc_1400C008A
0x1400c01cb  mov     ecx, esi
0x1400c01cd  jmp     loc_1400C005E
0x1400c01d2  sub     ecx, 2
0x1400c01d5  jz      loc_1400C0458
0x1400c01db  sub     ecx, 4
0x1400c01de  jz      loc_1400C04B4
0x1400c01e4  sub     ecx, 8
0x1400c01e7  jz      loc_1400C039A
0x1400c01ed  sub     ecx, 70h ; 'p'
0x1400c01f0  jz      loc_1400C03C6
0x1400c01f6  cmp     ecx, 80h
0x1400c01fc  jnz     loc_1400C008A
0x1400c0202  mov     ecx, 0A6h
0x1400c0207  jmp     short loc_1400C01AE
0x1400c0209  call    cs:__imp_W32GetUserSessionState
0x1400c0210  nop     dword ptr [rax+rax+00h]
0x1400c0215  mov     rcx, [rax+4A30h]
0x1400c021c  mov     edx, [rcx+8]
0x1400c021f  mov     [r14+4A38h], edx
0x1400c0226  jmp     loc_1400BFF6E
0x1400c022b  call    cs:__imp_W32GetUserSessionState
0x1400c0232  nop     dword ptr [rax+rax+00h]
0x1400c0237  mov     rcx, [rax+4A30h]
0x1400c023e  mov     edx, [rcx+8]
0x1400c0241  mov     [r14+4A38h], edx
0x1400c0248  jmp     loc_1400BFFBA
0x1400c024d  mov     rcx, [rbx+78h]
0x1400c0251  mov     r8, r14
0x1400c0254  mov     edx, 0Dh
0x1400c0259  mov     rcx, [rcx]
0x1400c025c  call    cs:__imp_PsUpdateComponentPower
0x1400c0263  nop     dword ptr [rax+rax+00h]
0x1400c0268  mov     ecx, 8Eh
0x1400c026d  jmp     loc_1400C01AE
0x1400c0272  cmp     ecx, 800h
0x1400c0278  jz      loc_1400C040E
0x1400c027e  cmp     ecx, 400h
0x1400c0284  jz      loc_1400C0433
0x1400c028a  cmp     ecx, 1000h
0x1400c0290  jz      loc_1400C04BE
0x1400c0296  cmp     ecx, 2000h
0x1400c029c  jz      loc_1400C0783
0x1400c02a2  cmp     ecx, 4000h
0x1400c02a8  jz      loc_1400C0779
0x1400c02ae  cmp     ecx, 8000h
0x1400c02b4  jnz     loc_1400C008A
0x1400c02ba  mov     ecx, 0A2h
0x1400c02bf  jmp     loc_1400C01AE
0x1400c02c4  mov     rcx, [rcx+8]; struct tagPROCESSINFO *
0x1400c02c8  test    rcx, rcx
0x1400c02cb  jz      loc_1400C0026
0x1400c02d1  cmp     rcx, rdx
0x1400c02d4  jz      loc_1400C0026
0x1400c02da  call    ?CitpProcessEnsureContext@@YAPEAU_CIT_PROCESS@@PEAUtagPROCESSINFO@@@Z; CitpProcessEnsureContext(tagPROCESSINFO *)
0x1400c02df  mov     rdi, rax
0x1400c02e2  test    rax, rax
0x1400c02e5  jz      loc_1400C008A
0x1400c02eb  mov     r8d, 1; unsigned __int16
0x1400c02f1  mov     rdx, rax; struct _CIT_PROCESS *
0x1400c02f4  mov     rcx, rbx; struct _CIT_IMPACT_CONTEXT *
0x1400c02f7  call    ?CitpInteractionSummaryEnsure@@YAPEAU_CIT_INTERACTION_SUMMARY@@PEAU_CIT_IMPACT_CONTEXT@@PEAU_CIT_PROCESS@@G@Z; CitpInteractionSummaryEnsure(_CIT_IMPACT_CONTEXT *,_CIT_PROCESS *,ushort)
0x1400c02fc  mov     rsi, rax
0x1400c02ff  lea     rbx, [rdi+60h]
0x1400c0303  mov     eax, [rsp+48h+arg_8]
0x1400c0307  mov     ecx, eax
0x1400c0309  sub     ecx, [rdi+5Ch]
0x1400c030c  cmp     ecx, 3E8h
0x1400c0312  ja      loc_1400C0622
0x1400c0318  test    rsi, rsi
0x1400c031b  jz      loc_1400C008A
0x1400c0321  test    [rbx], bp
0x1400c0324  jnz     loc_1400C008A
0x1400c032a  mov     eax, 200h
0x1400c032f  mov     ecx, ebp
0x1400c0331  cmp     ebp, eax
0x1400c0333  ja      loc_1400C0462
0x1400c0339  jz      loc_1400C06CA
0x1400c033f  sub     ecx, 1
0x1400c0342  jz      loc_1400C06A6
0x1400c0348  sub     ecx, 1
0x1400c034b  jz      loc_1400C0682
0x1400c0351  sub     ecx, 2
0x1400c0354  jz      loc_1400C0678
0x1400c035a  sub     ecx, 4
0x1400c035d  jz      loc_1400C066E
0x1400c0363  sub     ecx, 8
0x1400c0366  jz      loc_1400C0664
0x1400c036c  sub     ecx, 70h ; 'p'
0x1400c036f  jz      loc_1400C065A
0x1400c0375  cmp     ecx, 80h
0x1400c037b  jnz     loc_1400C008A
0x1400c0381  lea     eax, [rcx-46h]
0x1400c0384  mov     edx, 1; unsigned __int16
0x1400c0389  lea     rcx, [rax+rsi]; unsigned __int16 *
0x1400c038d  call    ?CitpStatIncrement@@YAXPEAGG@Z; CitpStatIncrement(ushort *,ushort)
0x1400c0392  or      [rbx], bp
0x1400c0395  jmp     loc_1400C008A
0x1400c039a  mov     ecx, 98h
0x1400c039f  jmp     loc_1400C01AE
0x1400c03a4  inc     eax
0x1400c03a6  bts     eax, 1Fh
0x1400c03aa  mov     [rbx+0F8h], eax
0x1400c03b0  jmp     loc_1400BFF8D
0x1400c03b5  inc     eax
0x1400c03b7  bts     eax, 1Fh
0x1400c03bb  mov     [rbx+0E0h], eax
0x1400c03c1  jmp     loc_1400BFFD9
  ... truncated ...
```
