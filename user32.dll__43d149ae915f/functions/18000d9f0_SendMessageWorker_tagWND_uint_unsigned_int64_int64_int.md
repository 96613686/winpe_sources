# SendMessageWorker(tagWND *,uint,unsigned __int64,__int64,int)

- ea: `0x18000d9f0`
- end: `0x18000e104`
- name: `?SendMessageWorker@@YA_JPEAUtagWND@@I_K_JH@Z`
- size: `1812`
- prototype: `__int64(struct tagWND *, unsigned int, unsigned __int64, __int64, int)`
- caller_count: `33`
- callee_count: `13`
- tags: `authz_impersonation, loader_planting, installer_update`

## callers

- `0x18000a6a0`
- `0x18000d0a0`
- `0x18000f140`
- `0x1800105c0`
- `0x180010610`
- `0x180010b70`
- `0x180015f90`
- `0x18002869c`
- `0x18002b854`
- `0x180037968`
- `0x180037bd0`
- `0x18004cff4`
- `0x180051d40`
- `0x180052578`
- `0x180057fa0`
- `0x180064164`
- `0x18006ea48`
- `0x18006f548`
- `0x180070830`
- `0x1800753c8`
- `0x1800755e4`
- `0x1800757a4`
- `0x18007583c`
- `0x180075970`
- `0x180075f5c`
- `0x180076168`
- `0x180076400`
- `0x180076d3c`
- `0x18007c6c4`
- `0x180083b00`
- `0x180083c9c`
- `0x180084a70`
- `0x18008a5d0`

## callees

- `0x180008610`
- `0x18000acb0`
- `0x18000c490`
- `0x18000d9f0`
- `0x180010950`
- `0x180021ba4`
- `0x1800221fc`
- `0x18002257c`
- `0x18004acf8`
- `0x18004fa14`
- `0x180050c10`
- `0x18006eaa4`
- `0x1800a2010`

## import_xrefs

- `win32u!NtUserGetThreadState` at `0x18000db5d`
- `win32u!NtUserGetThreadState` at `0x18000db5d`
- `win32u!ABI_Get_apfnClientWorkerNtDll` at `0x18000e0a1`
- `win32u!ABI_Get_apfnClientWorkerNtDll` at `0x180098a4e`
- `win32u!ABI_Get_apfnClientWorkerNtDll` at `0x18000e0a1`
- `win32u!ABI_Get_apfnClientWorkerNtDll` at `0x180098a4e`
- `win32u!NtUserMessageCall` at `0x18000db08`
- `win32u!NtUserMessageCall` at `0x18000db08`
- `ntdll!RtlSetLastWin32Error` at `0x18000de5d`
- `ntdll!RtlSetLastWin32Error` at `0x18000de96`
- `ntdll!RtlSetLastWin32Error` at `0x18000de5d`
- `ntdll!RtlSetLastWin32Error` at `0x18000de96`
- `ntdll!RtlNtStatusToDosError` at `0x18000de55`
- `ntdll!RtlNtStatusToDosError` at `0x18000de8e`
- `ntdll!RtlNtStatusToDosError` at `0x18000de55`
- `ntdll!RtlNtStatusToDosError` at `0x18000de8e`
- `ntdll!RtlEnterCriticalSection` at `0x18000de22`
- `ntdll!RtlEnterCriticalSection` at `0x18000de22`
- `ntdll!RtlLeaveCriticalSection` at `0x18000de49`
- `ntdll!RtlLeaveCriticalSection` at `0x18000de49`
- `api-ms-win-core-localization-l1-2-0!IsDBCSLeadByteEx` at `0x180098923`
- `api-ms-win-core-localization-l1-2-0!IsDBCSLeadByteEx` at `0x180098923`

## pseudocode

```c
__int64 __fastcall SendMessageWorker(
        struct tagWND *a1,
        unsigned int a2,
        unsigned __int64 a3,
        HTOUCHINPUT a4,
        unsigned int a5)
{
  SIZE_T v5; // r12
  unsigned __int64 v7; // rdi
  PVOID Win32ThreadInfo; // r8
  unsigned __int64 v10; // rax
  __int64 v11; // rdx
  PVOID v12; // rax
  struct _TEB *v13; // r9
  int v14; // r15d
  unsigned int v15; // esi
  __int64 result; // rax
  char *v17; // rcx
  __int64 v18; // rdx
  unsigned __int64 v19; // rcx
  char v20; // r10
  int v21; // r11d
  __int64 v22; // r8
  __int64 v23; // r9
  __int64 v24; // rax
  __int64 v25; // rsi
  SIZE_T v26; // rcx
  struct _TEB *v27; // rax
  struct _TEB *v28; // rax
  __int64 v29; // rax
  struct _TEB *v30; // r8
  __int64 v31; // r9
  SIZE_T v32; // rcx
  __int64 v33; // rdx
  unsigned __int64 v34; // rcx
  struct _TEB *v35; // rdx
  __int64 v36; // rcx
  __int64 v37; // rax
  struct _TEB *v38; // rcx
  unsigned __int64 v39; // rcx
  __int64 v40; // rdx
  int v41; // eax
  int v42; // eax
  ULONG v43; // eax
  ULONG v44; // eax
  unsigned __int64 v45; // rax
  int v46; // eax
  __int64 v47; // rax
  __int64 v48; // r9
  __int64 v49; // rax
  struct _TEB *v50; // rcx
  __int64 v51; // r9
  __int64 (__fastcall *v52)(struct tagWND *, _QWORD, unsigned __int64, HTOUCHINPUT, unsigned int); // rax
  unsigned __int64 v53; // rdx
  struct _TEB *v54; // rsi
  __int64 v55; // rax
  struct _TEB *v56; // rcx
  unsigned __int64 v57; // rax
  _QWORD *v58; // r8
  __int64 v59; // rax
  __int64 (__fastcall *v60)(struct tagWND *, _QWORD, unsigned __int64, HTOUCHINPUT, unsigned int); // rax
  struct _TEB *v61; // rcx
  __int64 v62; // rdx
  struct _TEB *v63; // rcx
  struct _TEB *v64; // rax
  __int64 v65; // [rsp+40h] [rbp-10h]
  SIZE_T v66; // [rsp+40h] [rbp-10h]
  unsigned __int64 v67; // [rsp+90h] [rbp+40h]
  char v68; // [rsp+90h] [rbp+40h]
  unsigned __int64 v69; // [rsp+90h] [rbp+40h]
  char v70; // [rsp+98h] [rbp+48h]
  unsigned __int64 v71; // [rsp+A0h] [rbp+50h] BYREF

  v71 = a3;
  v5 = *(_QWORD *)a1;
  v7 = a2;
  if ( a2 - 992 <= 8 )
  {
    v15 = a5;
    goto LABEL_12;
  }
  v65 = *((_QWORD *)a1 + 15);
  if ( NtCurrentTeb()->Win32ThreadInfo || NtUserGetThreadState(14) )
    Win32ThreadInfo = NtCurrentTeb()->Win32ThreadInfo;
  else
    Win32ThreadInfo = 0;
  v10 = (unsigned __int16)*(_DWORD *)a1;
  if ( v10 < *(_QWORD *)(gSharedInfo + 8)
    && (v11 = qword_1800C9378 + (unsigned int)(dword_1800C9380 * v10), *(_BYTE *)(v11 + 24))
    && v11 )
  {
    v12 = *(PVOID *)(v11 + 8);
  }
  else
  {
    v12 = 0;
  }
  if ( Win32ThreadInfo != v12
    || (*((_BYTE *)a1 + 18) & 4) != 0
    || (v13 = NtCurrentTeb(),
        v14 = v13->Win32ClientInfo[0],
        ((LODWORD(v13->Win32ClientInfo[7]) | *(_DWORD *)(v13->Win32ClientInfo[4] + 16)) & 0x2020) != 0) )
  {
    v15 = a5;
    goto LABEL_12;
  }
  v70 = 0;
  if ( g_systemCallFilterId == 5 && CLocalHookManager::IsLocalHookInstalled(4) )
    *(_QWORD *)(v51 + 2272) |= 0x100uLL;
  v15 = a5;
  if ( (a5 == 0) != (((unsigned __int8)~*((_BYTE *)a1 + 18) >> 3) & 1) )
  {
    if ( (_DWORD)v7 == 320 )
    {
LABEL_23:
      if ( (*(_BYTE *)gpsi & 2) != 0
        && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          10,
          &WPP_98f54186fc203383a3f513efbad818bc_Traceguids,
          (unsigned int)v7);
      }
    }
    else if ( (unsigned int)v7 <= 0x286 )
    {
      if ( (_DWORD)v7 != 646 )
      {
        switch ( (int)v7 )
        {
          case 47:
          case 204:
          case 258:
          case 259:
          case 262:
          case 263:
          case 271:
          case 288:
            break;
          case 176:
          case 177:
            goto LABEL_23;
          default:
            goto LABEL_26;
        }
      }
      if ( a5 )
      {
        if ( (*(_BYTE *)gpsi & 2) != 0 && ((_DWORD)v7 == 258 || (_DWORD)v7 == 204) )
        {
          if ( (v71 & 0xFF00) != 0 )
          {
            if ( (v71 & 0x80000000) == 0 )
            {
              if ( (v71 & 0xFF00) != 0 )
                v53 = ((unsigned __int64)(unsigned __int16)v71 >> 8) | (unsigned __int16)((unsigned __int8)v71 << 8);
              else
                v53 = (unsigned __int8)v71;
              v71 = v53;
            }
          }
          else
          {
            v54 = NtCurrentTeb();
            v55 = BYTE4(v54->Win32ClientInfo[19]);
            if ( (_BYTE)v55 )
            {
              v71 |= v55 << 8;
              BYTE4(v54->Win32ClientInfo[19]) = 0;
            }
            else if ( IsDBCSLeadByteEx(LOWORD(NtCurrentTeb()->Win32ClientInfo[19]), v71) )
            {
              result = 1;
              BYTE4(v54->Win32ClientInfo[19]) = v71;
              return result;
            }
          }
        }
        RtlMBMessageWParamCharToWCS((unsigned int)v7, &v71);
        v15 = 0;
      }
      else
      {
        RtlWCSMessageWParamCharToMB((unsigned int)v7, &v71);
        if ( (*(_BYTE *)gpsi & 2) != 0 && ((_DWORD)v7 == 258 || (_DWORD)v7 == 204) )
        {
          if ( (v71 & 0xFF00) != 0 )
          {
            v56 = NtCurrentTeb();
            v70 = 1;
            v56->Win32ClientInfo[20] = v5;
            LODWORD(v56->Win32ClientInfo[21]) = v7;
            v56->Win32ClientInfo[23] = (SIZE_T)a4;
            v56->Win32ClientInfo[24] = 0;
            LODWORD(v56->Win32ClientInfo[25]) = 0;
            v56->Win32ClientInfo[22] = (unsigned __int8)v71;
            v57 = BYTE1(v71);
          }
          else
          {
            v57 = (unsigned __int8)v71;
          }
          v71 = v57;
        }
        v15 = 1;
      }
    }
  }
LABEL_26:
  v17 = (char *)*((_QWORD *)a1 + 16);
  if ( v17 )
    v17 = &v17[(_QWORD)a1 - *((_QWORD *)a1 + 1)];
  v67 = (unsigned __int64)v17;
  if ( (unsigned int)IsInsideUserApiHook()
    || (v22 = *(unsigned __int16 *)(v19 + 4), (_WORD)v22 != 666) && (unsigned __int16)(v22 - 673) > 9u
    || (v23 = *((_QWORD *)a1 + 15), v24 = v22 - 666, v23 != *(_QWORD *)(v18 + 8 * (v22 - 666) + 584))
    && v23 != *(_QWORD *)(v18 + 8 * v24 + 392) )
  {
    if ( !v20 )
    {
      v25 = v65;
      while ( 1 )
      {
        if ( (unsigned int)v7 >= 0x240 )
        {
          if ( (unsigned int)v7 <= 0x240 )
          {
            v45 = GETPTI(a1, 1281);
            a4 = TransferTouchInput(a4, v45);
            if ( !a4 )
              return 0;
LABEL_57:
            v66 = NtCurrentTeb()->Win32ClientInfo[35];
LABEL_37:
            v68 = 0;
            goto LABEL_38;
          }
        }
        else if ( (_DWORD)v7 == 281 )
        {
          v39 = (unsigned __int16)*(_DWORD *)a1;
          if ( v39 < *(_QWORD *)(gSharedInfo + 8)
            && (v40 = qword_1800C9378 + (unsigned int)(dword_1800C9380 * v39), *(_BYTE *)(v40 + 24))
            && v40 )
          {
            v69 = *(_QWORD *)(v40 + 8);
          }
          else
          {
            v69 = 0;
          }
          v41 = RtlEnterCriticalSection(&CriticalSection);
          if ( v41 < 0 )
          {
            v44 = RtlNtStatusToDosError(v41);
            RtlSetLastWin32Error(v44);
            return 0;
          }
          a4 = (HTOUCHINPUT)TransferUMHandle((struct tagUMHANDLELIST *)&CriticalSection, a4, v69);
          v42 = RtlLeaveCriticalSection(&CriticalSection);
          if ( v42 < 0 )
          {
            v43 = RtlNtStatusToDosError(v42);
            RtlSetLastWin32Error(v43);
          }
          if ( !a4 )
            return 0;
          goto LABEL_57;
        }
        v26 = NtCurrentTeb()->Win32ClientInfo[35];
        v66 = v26;
        if ( (_DWORD)v7 != 233 )
          goto LABEL_37;
        v46 = *(_DWORD *)(v26 + 8);
        if ( v46 == 31 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, &WPP_98f54186fc203383a3f513efbad818bc_Traceguids, 31);
          }
          v64 = NtCurrentTeb();
          v64->Win32ClientInfo[28] |= 0x4000uLL;
          return 0;
        }
        v68 = 1;
        *(_DWORD *)(v26 + 8) = v46 + 1;
LABEL_38:
        v27 = NtCurrentTeb();
        v27->Win32ClientInfo[0] |= 0x40000000uLL;
        v28 = NtCurrentTeb();
        v28->Win32ClientInfo[0] |= 0x80000000uLL;
        if ( (_DWORD)v7 == 273 && WORD1(v71) == 1281 )
          CtfHookProcWorker(983044, 0, (__int64)a4, 0);
        v29 = UserCallWinProcCheckWow(*((_QWORD *)a1 + 28), v25, v5, (unsigned int)v7, v71, a4);
        v30 = NtCurrentTeb();
        v31 = v29;
        v32 = v30->Win32ClientInfo[0];
        v33 = v32 | 0x40000000;
        v34 = v32 & 0xFFFFFFFFBFFFFFFFuLL;
        if ( (v14 & 0x40000000) == 0 )
          v33 = v34;
        v30->Win32ClientInfo[0] = v33;
        v35 = NtCurrentTeb();
        v37 = v35->Win32ClientInfo[0];
        v36 = v37 | 0x80000000LL;
        LODWORD(v37) = v37 & 0x7FFFFFFF;
        if ( v14 >= 0 )
          v36 = v37;
        v35->Win32ClientInfo[0] = v36;
        if ( v68 )
          --*(_DWORD *)(v66 + 8);
        if ( (*(_BYTE *)gpsi & 2) == 0 || !v70 || !NtCurrentTeb()->Win32ClientInfo[22] )
          return v31;
        v38 = NtCurrentTeb();
        v71 = v38->Win32ClientInfo[22];
        v38->Win32ClientInfo[22] = 0;
      }
    }
LABEL_12:
    if ( (unsigned int)v7 >= 0x400 )
      return NtUserMessageCall(v5, (unsigned int)v7, v71, a4, 0, 689, v15);
    _mm_lfence();
    return ((__int64 (__fastcall **)(SIZE_T, _QWORD, unsigned __int64, HTOUCHINPUT, _QWORD, int, unsigned int))gapfnScSendMessage)[(unsigned __int8)MessageTable[v7]](
             v5,
             (unsigned int)v7,
             v71,
             a4,
             0,
             689,
             v15);
  }
  v47 = 2 * v24;
  v48 = qword_1800C93A0[v47];
  if ( !v48
    || (unsigned int)v7 <= dword_1800C9398[2 * v47]
    && (v19 = v67, ((unsigned __int8)(v21 << (v7 & 7)) & *(_BYTE *)((v7 >> 3) + v48)) != 0) )
  {
    while ( 1 )
    {
      v49 = *(unsigned __int16 *)(v19 + 4);
      if ( (_WORD)v49 == 666 )
      {
        v52 = *(__int64 (__fastcall **)(struct tagWND *, _QWORD, unsigned __int64, HTOUCHINPUT, unsigned int))(ABI_Get_apfnClientWorkerNtDll(v18) + 88);
        result = v52(a1, (unsigned int)v7, v71, a4, v15);
      }
      else
      {
        result = (*(__int64 (__fastcall **)(struct tagWND *, _QWORD, unsigned __int64, HTOUCHINPUT, unsigned int))(v18 + 8 * v49 - 4608))(
                   a1,
                   (unsigned int)v7,
                   v71,
                   a4,
                   v15);
      }
      if ( (*(_BYTE *)gpsi & 2) == 0 || !v70 || !NtCurrentTeb()->Win32ClientInfo[22] )
        break;
      v50 = NtCurrentTeb();
      v18 = gpsi;
      v71 = v50->Win32ClientInfo[22];
      v50->Win32ClientInfo[22] = 0;
      v19 = v67;
    }
    return result;
  }
  if ( (_WORD)v22 == 676 )
  {
    v58 = *(_QWORD **)(*((_QWORD *)a1 + 37) + 8LL);
    if ( v58 )
    {
      if ( *v58 )
      {
        if ( !v20 )
        {
          while ( 1 )
          {
            v59 = *(unsigned __int16 *)(v19 + 4);
            if ( (_WORD)v59 == 666 )
            {
              v60 = *(__int64 (__fastcall **)(struct tagWND *, _QWORD, unsigned __int64, HTOUCHINPUT, unsigned int))(ABI_Get_apfnClientWorkerNtDll(v18) + 88);
              result = v60(a1, (unsigned int)v7, v71, a4, v15);
            }
            else
            {
              result = (*(__int64 (__fastcall **)(struct tagWND *, _QWORD, unsigned __int64, HTOUCHINPUT, unsigned int))(v18 + 8 * v59 - 4608))(
                         a1,
                         (unsigned int)v7,
                         v71,
                         a4,
                         v15);
            }
            if ( (*(_BYTE *)gpsi & 2) == 0 || !v70 || !NtCurrentTeb()->Win32ClientInfo[22] )
              break;
            v61 = NtCurrentTeb();
            v18 = gpsi;
            v71 = v61->Win32ClientInfo[22];
            v61->Win32ClientInfo[22] = 0;
            v19 = v67;
          }
          return result;
        }
        goto LABEL_12;
      }
    }
  }
  v62 = DefWindowProcWorker(a1, v7, v71, (__int64)a4, v15);
  if ( (*(_BYTE *)gpsi & 2) != 0 && v70 )
  {
    do
    {
      if ( !NtCurrentTeb()->Win32ClientInfo[22] )
        break;
      v63 = NtCurrentTeb();
      v71 = v63->Win32ClientInfo[22];
      v63->Win32ClientInfo[22] = 0;
      v62 = DefWindowProcWorker(a1, v7, v71, (__int64)a4, v15);
    }
    while ( (*(_BYTE *)gpsi & 2) != 0 );
  }
  return v62;
}

```

## disassembly

```asm
0x18000d9f0  mov     [rsp-38h+arg_18], rbx
0x18000d9f5  mov     [rsp-38h+arg_10], r8
0x18000d9fa  push    rbp
0x18000d9fb  push    rsi
0x18000d9fc  push    rdi
0x18000d9fd  push    r12
0x18000d9ff  push    r13
0x18000da01  push    r14
0x18000da03  push    r15
0x18000da05  mov     rbp, rsp
0x18000da08  sub     rsp, 50h
0x18000da0c  mov     r12, [rcx]
0x18000da0f  mov     r14, r9
0x18000da12  mov     edi, edx
0x18000da14  mov     rbx, rcx
0x18000da17  lea     rdx, __ImageBase
0x18000da1e  lea     eax, [rdi-3E0h]
0x18000da24  cmp     eax, 8
0x18000da27  jbe     loc_18000DB4C
0x18000da2d  mov     rax, [rcx+78h]
0x18000da31  mov     [rbp+var_10], rax
0x18000da35  mov     rax, gs:30h
0x18000da3e  cmp     qword ptr [rax+78h], 0
0x18000da43  jz      loc_18000DB58
0x18000da49  mov     rax, gs:30h
0x18000da52  mov     r8, [rax+78h]
0x18000da56  mov     rcx, cs:gSharedInfo
0x18000da5d  mov     eax, [rbx]
0x18000da5f  movzx   eax, ax
0x18000da62  cmp     rax, [rcx+8]
0x18000da66  jnb     loc_18000DB51
0x18000da6c  imul    eax, cs:dword_1800C9380
0x18000da73  mov     edx, eax
0x18000da75  add     rdx, cs:qword_1800C9378
0x18000da7c  cmp     byte ptr [rdx+18h], 0
0x18000da80  jz      loc_18000DB51
0x18000da86  test    rdx, rdx
0x18000da89  jz      loc_18000DB51
0x18000da8f  mov     rax, [rdx+8]
0x18000da93  cmp     r8, rax
0x18000da96  jnz     short loc_18000DAD5
0x18000da98  test    byte ptr [rbx+12h], 4
0x18000da9c  jnz     short loc_18000DAD5
0x18000da9e  mov     r9, gs:30h
0x18000daa7  mov     rax, [r9+820h]
0x18000daae  mov     r15d, [r9+800h]
0x18000dab5  mov     r13d, r15d
0x18000dab8  and     r13d, 40000000h
0x18000dabf  mov     ecx, [rax+10h]
0x18000dac2  or      ecx, [r9+838h]
0x18000dac9  test    ecx, 2020h
0x18000dacf  jz      loc_18000DB74
0x18000dad5  mov     esi, [rbp+arg_20]
0x18000dad8  lea     rdx, __ImageBase
0x18000dadf  mov     [rsp+50h+var_20], esi
0x18000dae3  mov     r9, r14
0x18000dae6  mov     dword ptr [rsp+50h+var_28], 2B1h
0x18000daee  mov     qword ptr [rsp+50h+var_30], 0
0x18000daf7  cmp     edi, 400h
0x18000dafd  jb      short loc_18000DB26
0x18000daff  mov     r8, [rbp+arg_10]
0x18000db03  mov     edx, edi
0x18000db05  mov     rcx, r12
0x18000db08  call    cs:__imp_NtUserMessageCall
0x18000db0e  mov     rbx, [rsp+50h+arg_18]
0x18000db16  add     rsp, 50h
0x18000db1a  pop     r15
0x18000db1c  pop     r14
0x18000db1e  pop     r13
0x18000db20  pop     r12
0x18000db22  pop     rdi
0x18000db23  pop     rsi
0x18000db24  pop     rbp
0x18000db25  retn
0x18000db26  lfence
0x18000db29  movzx   eax, ds:(MessageTable - 180000000h)[rdx+rdi*2]
0x18000db31  mov     r8, [rbp+arg_10]
0x18000db35  movzx   ecx, al
0x18000db38  mov     rax, ds:(gapfnScSendMessage - 180000000h)[rdx+rcx*8]
0x18000db40  mov     edx, edi
0x18000db42  mov     rcx, r12
0x18000db45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000db4a  jmp     short loc_18000DB0E
0x18000db4c  mov     esi, [rbp+arg_20]
0x18000db4f  jmp     short loc_18000DADF
0x18000db51  xor     eax, eax
0x18000db53  jmp     loc_18000DA93
0x18000db58  mov     ecx, 0Eh
0x18000db5d  call    cs:__imp_NtUserGetThreadState
0x18000db63  test    rax, rax
0x18000db66  jnz     loc_18000DA49
0x18000db6c  xor     r8d, r8d
0x18000db6f  jmp     loc_18000DA56
0x18000db74  xor     r10b, r10b
0x18000db77  cmp     cs:?g_systemCallFilterId@@3KA, 5; ulong g_systemCallFilterId
0x18000db7e  mov     dword ptr [rbp+arg_0], r10d
0x18000db82  mov     [rbp+arg_8], r10b
0x18000db86  jz      loc_18000E016
0x18000db8c  movzx   ecx, byte ptr [rbx+12h]
0x18000db90  lea     r9, WPP_GLOBAL_Control
0x18000db97  mov     esi, [rbp+arg_20]
0x18000db9a  xor     eax, eax
0x18000db9c  not     cl
0x18000db9e  mov     r11d, 1
0x18000dba4  shr     ecx, 3
0x18000dba7  and     ecx, 1
0x18000dbaa  test    esi, esi
0x18000dbac  setz    al
0x18000dbaf  cmp     eax, ecx
0x18000dbb1  jz      loc_18000E00A
0x18000dbb7  cmp     edi, 140h
0x18000dbbd  jnz     loc_18009882C
0x18000dbc3  lea     r8, __ImageBase
0x18000dbca  mov     rdx, cs:gpsi; jumptable 000000018009885F cases 176,177
0x18000dbd1  test    byte ptr [rdx], 2
0x18000dbd4  jz      short loc_18000DBEC
0x18000dbd6  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dbdd  cmp     rcx, r9
0x18000dbe0  jz      short loc_18000DBEC
0x18000dbe2  test    byte ptr [rcx+1Ch], 40h
0x18000dbe6  jnz     loc_18000E038
0x18000dbec  cmp     edi, 400h
0x18000dbf2  jnb     short loc_18000DC0A
0x18000dbf4  mov     ecx, 100h
0x18000dbf9  movzx   r10d, r10b
0x18000dbfd  test    ds:rva MessageTable[r8+rdi*2], cx
0x18000dc06  cmovnz  r10d, r11d
0x18000dc0a  mov     rcx, [rbx+80h]
0x18000dc11  test    rcx, rcx
0x18000dc14  jz      loc_18000E069
0x18000dc1a  sub     rcx, [rbx+8]
0x18000dc1e  add     rcx, rbx
0x18000dc21  mov     [rbp+arg_0], rcx
0x18000dc25  call    ?IsInsideUserApiHook@@YAHXZ; IsInsideUserApiHook(void)
0x18000dc2a  test    eax, eax
0x18000dc2c  jnz     short loc_18000DC69
0x18000dc2e  movzx   r8d, word ptr [rcx+4]
0x18000dc33  mov     eax, 29Ah
0x18000dc38  cmp     r8w, ax
0x18000dc3c  jnz     loc_18000DF3B
0x18000dc42  mov     r9, [rbx+78h]
0x18000dc46  lea     rax, [r8-29Ah]
0x18000dc4d  cmp     r9, [rdx+rax*8+248h]
0x18000dc55  jz      loc_18000DF58
0x18000dc5b  cmp     r9, [rdx+rax*8+188h]
0x18000dc63  jz      loc_18000DF58
0x18000dc69  test    r10b, r10b
0x18000dc6c  jnz     loc_18000DAD8
0x18000dc72  mov     rsi, [rbp+var_10]
0x18000dc76  mov     edx, 501h
0x18000dc7b  nop     dword ptr [rax+rax+00h]
0x18000dc80  cmp     edi, 240h
0x18000dc86  jnb     loc_18000DEAF
0x18000dc8c  cmp     edi, 119h
0x18000dc92  jz      loc_18000DDDA
0x18000dc98  mov     rax, gs:30h
0x18000dca1  mov     rcx, [rax+918h]
0x18000dca8  mov     [rbp+var_10], rcx
0x18000dcac  cmp     edi, 0E9h
0x18000dcb2  jz      loc_18000DEE6
0x18000dcb8  mov     byte ptr [rbp+arg_0], 0
0x18000dcbc  mov     rax, gs:30h
0x18000dcc5  mov     ecx, 80000000h
0x18000dcca  or      qword ptr [rax+800h], 40000000h
0x18000dcd5  mov     rax, gs:30h
0x18000dcde  or      [rax+800h], rcx
0x18000dce5  cmp     edi, 111h
0x18000dceb  jz      loc_18000DF0D
0x18000dcf1  mov     rax, [rbp+arg_10]
0x18000dcf5  mov     r9d, edi
0x18000dcf8  mov     rcx, [rbx+0E0h]
0x18000dcff  mov     r8, r12
0x18000dd02  mov     [rsp+50h+var_18], r11d
0x18000dd07  mov     rdx, rsi
0x18000dd0a  mov     [rsp+50h+var_28], r14
0x18000dd0f  mov     qword ptr [rsp+50h+var_30], rax
0x18000dd14  call    ?UserCallWinProcCheckWow@@YA_JPEAU_ACTIVATION_CONTEXT@@P6A_JPEAUtagWND@@I_K_J@ZPEAUHWND__@@W4_WM_VALUE@@23PEAXH@Z; UserCallWinProcCheckWow(_ACTIVATION_CONTEXT *,__int64 (*)(tagWND *,uint,unsigned __int64,__int64),HWND__ *,_WM_VALUE,unsigned __int64,__int64,void *,int)
0x18000dd19  mov     r8, gs:30h
0x18000dd22  mov     r9, rax
0x18000dd25  mov     rdx, [r8+800h]
0x18000dd2c  mov     rcx, rdx
0x18000dd2f  bts     rdx, 1Eh
0x18000dd34  btr     rcx, 1Eh
0x18000dd39  test    r13d, r13d
0x18000dd3c  cmovz   rdx, rcx
0x18000dd40  mov     [r8+800h], rdx
0x18000dd47  mov     r8d, 80000000h
0x18000dd4d  mov     rdx, gs:30h
0x18000dd56  mov     rcx, [rdx+800h]
0x18000dd5d  mov     rax, rcx
0x18000dd60  or      rcx, r8
0x18000dd63  btr     eax, 1Fh
0x18000dd67  test    r15d, r15d
0x18000dd6a  cmovns  rcx, rax
0x18000dd6e  cmp     byte ptr [rbp+arg_0], 0
0x18000dd72  mov     [rdx+800h], rcx
0x18000dd79  jnz     loc_18000DEA3
0x18000dd7f  mov     rax, cs:gpsi
0x18000dd86  test    byte ptr [rax], 2
0x18000dd89  jz      loc_18000E0FC
0x18000dd8f  cmp     [rbp+arg_8], 0
0x18000dd93  jz      loc_18000E0FC
0x18000dd99  mov     rax, gs:30h
0x18000dda2  cmp     qword ptr [rax+8B0h], 0
0x18000ddaa  jz      loc_18000E0FC
0x18000ddb0  mov     rcx, gs:30h
0x18000ddb9  mov     r11d, 1
0x18000ddbf  mov     rax, [rcx+8B0h]
0x18000ddc6  mov     [rbp+arg_10], rax
0x18000ddca  mov     qword ptr [rcx+8B0h], 0
0x18000ddd5  jmp     loc_18000DC76
0x18000ddda  mov     eax, [rbx]
0x18000dddc  movzx   ecx, ax
0x18000dddf  mov     rax, cs:gSharedInfo
0x18000dde6  cmp     rcx, [rax+8]
0x18000ddea  jnb     loc_18000DF00
0x18000ddf0  imul    ecx, cs:dword_1800C9380
0x18000ddf7  mov     edx, ecx
0x18000ddf9  add     rdx, cs:qword_1800C9378
0x18000de00  cmp     byte ptr [rdx+18h], 0
0x18000de04  jz      loc_18000DF00
0x18000de0a  test    rdx, rdx
0x18000de0d  jz      loc_18000DF00
0x18000de13  mov     rax, [rdx+8]
0x18000de17  mov     [rbp+arg_0], rax
0x18000de1b  lea     rcx, CriticalSection; CriticalSection
0x18000de22  call    cs:__imp_RtlEnterCriticalSection
0x18000de28  test    eax, eax
0x18000de2a  js      short loc_18000DE8C
0x18000de2c  mov     r8, [rbp+arg_0]; unsigned __int64
0x18000de30  lea     rcx, CriticalSection; struct tagUMHANDLELIST *
0x18000de37  mov     rdx, r14; void *
0x18000de3a  call    ?TransferUMHandle@@YAPEAXPEAUtagUMHANDLELIST@@PEAX_K@Z; TransferUMHandle(tagUMHANDLELIST *,void *,unsigned __int64)
0x18000de3f  lea     rcx, CriticalSection; CriticalSection
0x18000de46  mov     r14, rax
0x18000de49  call    cs:__imp_RtlLeaveCriticalSection
0x18000de4f  test    eax, eax
0x18000de51  jns     short loc_18000DE63
0x18000de53  mov     ecx, eax; Status
0x18000de55  call    cs:__imp_RtlNtStatusToDosError
0x18000de5b  mov     ecx, eax; LastError
0x18000de5d  call    cs:__imp_RtlSetLastWin32Error
0x18000de63  test    r14, r14
0x18000de66  jz      short loc_18000DE9C
0x18000de68  mov     rax, gs:30h
0x18000de71  mov     rax, [rax+918h]
0x18000de78  mov     [rbp+var_10], rax
0x18000de7c  mov     edx, 501h
0x18000de81  mov     r11d, 1
0x18000de87  jmp     loc_18000DCB8
0x18000de8c  mov     ecx, eax; Status
0x18000de8e  call    cs:__imp_RtlNtStatusToDosError
0x18000de94  mov     ecx, eax; LastError
0x18000de96  call    cs:__imp_RtlSetLastWin32Error
0x18000de9c  xor     eax, eax
0x18000de9e  jmp     loc_18000DB0E
0x18000dea3  mov     rax, [rbp+var_10]
0x18000dea7  dec     dword ptr [rax+8]
0x18000deaa  jmp     loc_18000DD7F
0x18000deaf  ja      loc_18000DC98
0x18000deb5  mov     rcx, rbx
0x18000deb8  call    _GETPTI
0x18000debd  mov     rdx, rax; unsigned __int64
0x18000dec0  mov     rcx, r14; HTOUCHINPUT
0x18000dec3  call    ?TransferTouchInput@@YAPEAUHTOUCHINPUT__@@PEAU1@_K@Z; TransferTouchInput(HTOUCHINPUT__ *,unsigned __int64)
0x18000dec8  mov     r14, rax
0x18000decb  test    rax, rax
0x18000dece  jz      short loc_18000DE9C
0x18000ded0  mov     rax, gs:30h
0x18000ded9  mov     rcx, [rax+918h]
0x18000dee0  mov     [rbp+var_10], rcx
0x18000dee4  jmp     short loc_18000DE7C
0x18000dee6  mov     eax, [rcx+8]
0x18000dee9  cmp     eax, 1Fh
0x18000deec  jz      loc_18000E0B0
0x18000def2  inc     eax
0x18000def4  mov     byte ptr [rbp+arg_0], 1
0x18000def8  mov     [rcx+8], eax
0x18000defb  jmp     loc_18000DCBC
0x18000df00  mov     [rbp+arg_0], 0
0x18000df08  jmp     loc_18000DE1B
0x18000df0d  mov     rax, [rbp+arg_10]
0x18000df11  shr     rax, 10h
0x18000df15  cmp     ax, dx
0x18000df18  jnz     loc_18000DCF1
0x18000df1e  xor     r9d, r9d; unsigned __int64
0x18000df21  mov     r8, r14; __int64
0x18000df24  xor     edx, edx; unsigned __int64
0x18000df26  mov     ecx, 0F0004h; int
0x18000df2b  call    ?CtfHookProcWorker@@YA_JH_K_J0@Z; CtfHookProcWorker(int,unsigned __int64,__int64,unsigned __int64)
0x18000df30  mov     r11d, 1
0x18000df36  jmp     loc_18000DCF1
0x18000df3b  mov     r9d, 2A1h
0x18000df41  movzx   eax, r8w
0x18000df45  sub     ax, r9w
0x18000df49  cmp     ax, 9
0x18000df4d  jbe     loc_18000DC42
0x18000df53  jmp     loc_18000DC69
0x18000df58  add     rax, rax
0x18000df5b  lea     r15, __ImageBase
  ... truncated ...
```
