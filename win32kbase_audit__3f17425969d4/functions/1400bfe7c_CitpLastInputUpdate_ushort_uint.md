# CitpLastInputUpdate(ushort,uint)

- ea: `0x1400bfe7c`
- end: `0x1400c078d`
- name: `?CitpLastInputUpdate@@YAXGI@Z`
- size: `2321`
- prototype: `void __fastcall(__int64, __int64)`
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
void __fastcall CitpLastInputUpdate(__int64 a1, __int64 a2)
{
  unsigned int v2; // ebp
  int v3; // r12d
  __int64 v4; // rdx
  __int64 v5; // rcx
  __int64 UserSessionState; // rax
  unsigned __int64 v7; // rcx
  __int64 v8; // rdx
  __int64 v9; // rax
  unsigned int v10; // r15d
  __int64 v11; // rcx
  __int64 v12; // rbx
  __int64 v13; // rdx
  unsigned __int64 v14; // rdx
  __int64 v15; // rcx
  __int64 v16; // r14
  unsigned int v17; // eax
  unsigned int v18; // esi
  int v19; // eax
  unsigned int v20; // r15d
  __int64 v21; // rdx
  __int64 v22; // rcx
  __int64 v23; // r14
  unsigned int v24; // eax
  unsigned int v25; // esi
  int v26; // eax
  unsigned __int64 *v27; // rdx
  unsigned __int64 v28; // rdi
  unsigned __int64 v29; // rcx
  __int16 v30; // si
  unsigned __int16 v31; // ax
  __int16 v32; // cx
  unsigned __int64 v33; // rdi
  int v34; // r8d
  unsigned __int64 v35; // rdi
  int v36; // r8d
  unsigned int v37; // edx
  unsigned int v38; // ecx
  unsigned int v39; // ecx
  __int64 v40; // rcx
  unsigned __int16 v41; // ax
  struct tagPROCESSINFO *v42; // rcx
  struct tagPROCESSINFO **v43; // rax
  struct tagPROCESSINFO **v44; // rdi
  struct _CIT_INTERACTION_SUMMARY *v45; // rsi
  _WORD *v46; // rbx
  __int64 v47; // rax
  int v48; // eax
  int v49; // eax
  __int64 v50; // rax
  unsigned __int64 v51; // rdx
  unsigned int v52; // eax
  unsigned int v53; // eax
  unsigned int v54; // [rsp+58h] [rbp+10h] BYREF

  v54 = a2;
  v2 = (unsigned __int16)a1;
  if ( (unsigned __int16)a1 == 32 )
  {
    v3 = 1;
  }
  else
  {
    v3 = 0;
    a2 = (unsigned int)(a2 - MEMORY[0xFFFFF780000002E4]);
    if ( (unsigned int)a2 > 0x3E8 )
      RtlSetSystemGlobalData(13, &v54, 4);
  }
  v5 = *(_QWORD *)(W32GetUserSessionState(a1, a2) + 18992);
  if ( !*(_QWORD *)(v5 + 32) )
    return;
  UserSessionState = W32GetUserSessionState(v5, v4);
  v7 = v54;
  v8 = *(_QWORD *)(UserSessionState + 18992);
  if ( v54 < *(_DWORD *)(v8 + 40) )
  {
    v7 = (MEMORY[0xFFFFF78000000320] * (unsigned __int64)MEMORY[0xFFFFF78000000004]) >> 24;
    v54 = v7;
  }
  *(_DWORD *)(v8 + 40) = v7;
  v9 = W32GetUserSessionState(v7, v8);
  v10 = v54;
  v11 = *(_QWORD *)(v9 + 18992);
  v12 = *(_QWORD *)(v11 + 32);
  v16 = W32GetUserSessionState(v11, v13);
  if ( !*(_DWORD *)(v16 + 19000) )
  {
    v15 = *(_QWORD *)(W32GetUserSessionState(v15, v14) + 18992);
    v14 = *(unsigned int *)(v15 + 8);
    *(_DWORD *)(v16 + 19000) = v14;
  }
  v17 = *(_DWORD *)(v12 + 236);
  v18 = v10 - v17;
  if ( v10 != v17 )
  {
    if ( v10 < v17 )
    {
      v52 = *(_DWORD *)(v12 + 236);
      v33 = (MEMORY[0xFFFFF78000000320] * (unsigned __int64)MEMORY[0xFFFFF78000000004]) >> 24;
      v18 = v33 - v52;
      if ( (unsigned int)v33 < v52 )
      {
        v50 = W32GetUserSessionState(v15, v14);
        v15 = 0xFFFFFFFFLL;
        v14 = ((((unsigned __int64)MEMORY[0xFFFFF78000000004] << 32)
              * (unsigned __int128)(unsigned __int64)(MEMORY[0xFFFFF78000000320] << 8)) >> 64)
            - *(_QWORD *)(*(_QWORD *)(v50 + 18992) + 64LL);
        if ( v14 > 0xFFFFFFFF )
          v14 = 0xFFFFFFFFLL;
        if ( v18 > (unsigned int)v14 || v18 > 0x240C8400 )
        {
          ++*(_DWORD *)(v12 + 240);
          *(_DWORD *)(v12 + 236) = v33;
          *(_DWORD *)(v12 + 232) = v33 - *(_DWORD *)(v16 + 19000);
          CIT_USER_ACTIVITY_STAT::SetActive((CIT_USER_ACTIVITY_STAT *)(v12 + 244), 0);
          goto LABEL_10;
        }
      }
    }
    else
    {
      LODWORD(v33) = v10;
    }
    if ( *(_DWORD *)(v12 + 228) )
    {
      *(_DWORD *)(v12 + 244) += v18;
    }
    else
    {
      v34 = *(_DWORD *)(v12 + 232);
      v14 = (unsigned int)(*(_DWORD *)(v12 + 236) - v34);
      v15 = *(unsigned int *)(v16 + 19000);
      if ( (unsigned int)v14 < (unsigned int)v15 )
      {
        if ( (int)v33 - v34 > (unsigned int)v15 )
        {
          v48 = *(_DWORD *)(v12 + 248);
          v15 = (unsigned int)(v15 - v14);
          if ( v48 < 0 )
            *(_DWORD *)(v12 + 248) = v48 & 0x7FFFFFFF;
        }
        else
        {
          v15 = v18;
        }
        *(_DWORD *)(v12 + 244) += v15;
      }
    }
    *(_DWORD *)(v12 + 236) = v33;
  }
LABEL_10:
  v19 = *(_DWORD *)(v12 + 248);
  if ( v19 >= 0 )
    *(_DWORD *)(v12 + 248) = (v19 + 1) | 0x80000000;
  *(_DWORD *)(v12 + 232) = v10;
  if ( !v3 )
  {
    v20 = v54;
    v23 = W32GetUserSessionState(v15, v14);
    if ( !*(_DWORD *)(v23 + 19000) )
    {
      v22 = *(_QWORD *)(W32GetUserSessionState(v22, v21) + 18992);
      v21 = *(unsigned int *)(v22 + 8);
      *(_DWORD *)(v23 + 19000) = v21;
    }
    v24 = *(_DWORD *)(v12 + 212);
    v25 = v20 - v24;
    if ( v20 == v24 )
      goto LABEL_16;
    if ( v20 < v24 )
    {
      v53 = *(_DWORD *)(v12 + 212);
      v35 = (MEMORY[0xFFFFF78000000320] * (unsigned __int64)MEMORY[0xFFFFF78000000004]) >> 24;
      v25 = v35 - v53;
      if ( (unsigned int)v35 < v53 )
      {
        v51 = ((((unsigned __int64)MEMORY[0xFFFFF78000000004] << 32)
              * (unsigned __int128)(unsigned __int64)(MEMORY[0xFFFFF78000000320] << 8)) >> 64)
            - *(_QWORD *)(*(_QWORD *)(W32GetUserSessionState(v22, v21) + 18992) + 64LL);
        if ( v51 > 0xFFFFFFFF )
          LODWORD(v51) = -1;
        if ( v25 > (unsigned int)v51 || v25 > 0x240C8400 )
        {
          ++*(_DWORD *)(v12 + 216);
          *(_DWORD *)(v12 + 212) = v35;
          *(_DWORD *)(v12 + 208) = v35 - *(_DWORD *)(v23 + 19000);
          CIT_USER_ACTIVITY_STAT::SetActive((CIT_USER_ACTIVITY_STAT *)(v12 + 220), 0);
LABEL_16:
          v26 = *(_DWORD *)(v12 + 224);
          if ( v26 >= 0 )
            *(_DWORD *)(v12 + 224) = (v26 + 1) | 0x80000000;
          *(_DWORD *)(v12 + 208) = v20;
          goto LABEL_19;
        }
      }
    }
    else
    {
      LODWORD(v35) = v20;
    }
    if ( *(_DWORD *)(v12 + 204) )
    {
      *(_DWORD *)(v12 + 220) += v25;
    }
    else
    {
      v36 = *(_DWORD *)(v12 + 208);
      v37 = *(_DWORD *)(v12 + 212) - v36;
      v38 = *(_DWORD *)(v23 + 19000);
      if ( v37 < v38 )
      {
        if ( (int)v35 - v36 > v38 )
        {
          v49 = *(_DWORD *)(v12 + 224);
          v39 = v38 - v37;
          if ( v49 < 0 )
            *(_DWORD *)(v12 + 224) = v49 & 0x7FFFFFFF;
        }
        else
        {
          v39 = v25;
        }
        *(_DWORD *)(v12 + 220) += v39;
      }
    }
    *(_DWORD *)(v12 + 212) = v35;
    goto LABEL_16;
  }
LABEL_19:
  v27 = *(unsigned __int64 **)(v12 + 120);
  if ( !v27 )
    return;
  v28 = v27[114];
  if ( v28 - 1 > 0xCEEE && v28 < 0xCEF2
    || (v29 = *(_QWORD *)(v28 + 24), v29 - 1 > 0xCEEE) && v29 < 0xCEF2
    || (v42 = *(struct tagPROCESSINFO **)(v29 + 8)) == 0
    || v42 == (struct tagPROCESSINFO *)v27 )
  {
    v30 = -1;
    if ( v54 - *(_DWORD *)(v28 + 100) > 0x3E8 )
    {
      *(_DWORD *)(v28 + 100) = v54;
      *(_WORD *)(v28 + 106) = 0;
      v31 = *(_WORD *)(v12 + 140);
      v32 = v31 + 1;
      if ( (unsigned __int16)(v31 + 1) < v31 )
        v32 = -1;
      *(_WORD *)(v12 + 140) = v32;
      PsUpdateComponentPower(**(_QWORD **)(v12 + 120), 9);
    }
    if ( ((unsigned __int16)v2 & *(_WORD *)(v28 + 106)) == 0 )
    {
      if ( v2 > 0x200 )
      {
        switch ( v2 )
        {
          case 0x800u:
            PsUpdateComponentPower(**(_QWORD **)(v12 + 120), 14);
            v40 = 150;
            break;
          case 0x400u:
            PsUpdateComponentPower(**(_QWORD **)(v12 + 120), 13);
            v40 = 146;
            break;
          case 0x1000u:
            v40 = 156;
            break;
          case 0x2000u:
            v40 = 160;
            break;
          case 0x4000u:
            v40 = 168;
            break;
          case 0x8000u:
            v40 = 162;
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
            PsUpdateComponentPower(**(_QWORD **)(v12 + 120), 13);
            v40 = 144;
            break;
          case 1u:
            PsUpdateComponentPower(**(_QWORD **)(v12 + 120), 13);
            v40 = 142;
            break;
          case 2u:
            PsUpdateComponentPower(**(_QWORD **)(v12 + 120), 14);
            v40 = 148;
            break;
          case 4u:
            v40 = 154;
            break;
          case 8u:
            v40 = 158;
            break;
          case 0x10u:
            v40 = 152;
            break;
          case 0x80u:
            v40 = 164;
            break;
          case 0x100u:
            v40 = 166;
            break;
          default:
            return;
        }
      }
      v41 = *(_WORD *)(v40 + v12);
      if ( (unsigned __int16)(v41 + 1) >= v41 )
        v30 = v41 + 1;
      *(_WORD *)(v40 + v12) = v30;
      *(_WORD *)(v28 + 106) |= v2;
    }
  }
  else
  {
    v43 = (struct tagPROCESSINFO **)CitpProcessEnsureContext(v42);
    v44 = v43;
    if ( v43 )
    {
      v45 = CitpInteractionSummaryEnsure((struct _CIT_IMPACT_CONTEXT *)v12, v43, 1);
      v46 = v44 + 12;
      if ( v54 - *((_DWORD *)v44 + 23) > 0x3E8 )
      {
        *((_DWORD *)v44 + 23) = v54;
        *v46 = 0;
        if ( v45 )
          CitpStatIncrement((unsigned __int16 *)v45 + 16, 1u);
        PsUpdateComponentPower(*(_QWORD *)v44[1], 9);
      }
      if ( v45 && ((unsigned __int16)v2 & *v46) == 0 )
      {
        if ( v2 > 0x200 )
        {
          switch ( v2 )
          {
            case 0x400u:
              PsUpdateComponentPower(*(_QWORD *)v44[1], 13);
              v47 = 38;
              goto LABEL_87;
            case 0x800u:
              PsUpdateComponentPower(*(_QWORD *)v44[1], 14);
              v47 = 42;
              goto LABEL_87;
            case 0x1000u:
              v47 = 48;
              goto LABEL_87;
            case 0x2000u:
              v47 = 52;
              goto LABEL_87;
            case 0x4000u:
              v47 = 60;
              goto LABEL_87;
            case 0x8000u:
              v47 = 54;
              goto LABEL_87;
          }
        }
        else
        {
          switch ( v2 )
          {
            case 0x200u:
              PsUpdateComponentPower(*(_QWORD *)v44[1], 13);
              v47 = 36;
              goto LABEL_87;
            case 1u:
              PsUpdateComponentPower(*(_QWORD *)v44[1], 13);
              v47 = 34;
              goto LABEL_87;
            case 2u:
              PsUpdateComponentPower(*(_QWORD *)v44[1], 14);
              v47 = 40;
              goto LABEL_87;
            case 4u:
              v47 = 46;
              goto LABEL_87;
            case 8u:
              v47 = 50;
              goto LABEL_87;
            case 0x10u:
              v47 = 44;
              goto LABEL_87;
            case 0x80u:
              v47 = 56;
              goto LABEL_87;
            case 0x100u:
              v47 = 58;
LABEL_87:
              CitpStatIncrement((unsigned __int16 *)((char *)v45 + v47), 1u);
              *v46 |= v2;
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
