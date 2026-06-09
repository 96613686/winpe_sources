# DispatchMessageWorker

- ea: `0x18000ae90`
- end: `0x18000b4cf`
- name: `DispatchMessageWorker`
- size: `1599`
- prototype: ``
- caller_count: `9`
- callee_count: `9`
- tags: `loader_planting, installer_update`

## callers

- `0x180009710`
- `0x18000a6a0`
- `0x18000acf0`
- `0x18000ae80`
- `0x180036cd0`
- `0x1800470a0`
- `0x18005db8c`
- `0x180077130`
- `0x18008cab8`

## callees

- `0x180007a50`
- `0x1800095a4`
- `0x18000ae90`
- `0x18000c490`
- `0x18000d9b0`
- `0x180020480`
- `0x180021ba4`
- `0x18004fa14`
- `0x180093a08`

## import_xrefs

- `win32u!NtUserGetThreadState` at `0x18000b46a`
- `win32u!NtUserGetThreadState` at `0x18000b46a`
- `win32u!NtUserValidateTimerCallback` at `0x18000b149`
- `win32u!NtUserValidateTimerCallback` at `0x18000b149`
- `win32u!NtUserDispatchMessage` at `0x18000b299`
- `win32u!NtUserDispatchMessage` at `0x18000b341`
- `win32u!NtUserDispatchMessage` at `0x18000b299`
- `win32u!NtUserDispatchMessage` at `0x18000b341`
- `win32u!NtUserMapDesktopObject` at `0x18000b447`
- `win32u!NtUserMapDesktopObject` at `0x18000b447`
- `win32u!NtUserValidateHandleSecure` at `0x18000b19d`
- `win32u!NtUserValidateHandleSecure` at `0x18000b19d`
- `ntdll!RtlSetLastWin32Error` at `0x18000b1b0`
- `ntdll!RtlSetLastWin32Error` at `0x18009860f`
- `ntdll!RtlSetLastWin32Error` at `0x18000b1b0`
- `ntdll!RtlSetLastWin32Error` at `0x18009860f`
- `api-ms-win-core-localization-l1-2-0!IsDBCSLeadByteEx` at `0x18000b3c7`
- `api-ms-win-core-localization-l1-2-0!IsDBCSLeadByteEx` at `0x1800985ed`
- `api-ms-win-core-localization-l1-2-0!IsDBCSLeadByteEx` at `0x18000b3c7`
- `api-ms-win-core-localization-l1-2-0!IsDBCSLeadByteEx` at `0x1800985ed`

## pseudocode

```c
__int64 __fastcall DispatchMessageWorker(_QWORD *a1, __int64 a2, __int64 a3)
{
  int v3; // r12d
  __int64 v5; // rsi
  __int64 v6; // r15
  struct _TEB *v7; // rdi
  __int64 v8; // rdi
  struct _TEB *v9; // r13
  __int64 v10; // r14
  SIZE_T *Win32ClientInfo; // r13
  _QWORD *v12; // rax
  __int64 v13; // rcx
  __int64 v14; // r14
  __int64 v15; // r13
  PVOID Win32ThreadInfo; // r8
  unsigned __int64 v17; // rcx
  __int64 v18; // rdx
  PVOID v19; // rax
  __int64 result; // rax
  int v21; // r12d
  __int64 i; // rdx
  __int64 v23; // rax
  struct _TEB *v24; // rcx
  int v25; // eax
  int v26; // eax
  int v27; // edx
  __int64 v28; // rcx
  unsigned __int16 v29; // ax
  struct _TEB *v30; // r12
  __int64 v31; // rax
  ULONG v32; // ecx
  struct _TEB *v33; // rcx
  unsigned __int16 v34; // dx
  struct _TEB *v35; // rdi
  __int64 v36; // rax

  v3 = a2;
  if ( (a1[1] & 0xFFFE0000) != 0 )
  {
    v32 = 87;
    goto LABEL_108;
  }
  v5 = *a1;
  v6 = 0;
  if ( *a1 )
  {
    v7 = NtCurrentTeb();
    if ( v5 == v7->Win32ClientInfo[8] )
    {
      v8 = v7->Win32ClientInfo[9];
    }
    else
    {
      v8 = 0;
      v9 = NtCurrentTeb();
      if ( (unsigned __int64)(unsigned __int16)v5 >= *(_QWORD *)(gpsi + 8) )
        goto LABEL_17;
      v10 = HANDLEENTRY_FROM_INDEX((unsigned __int16)v5, a2, a3);
      if ( !v10 || (WORD1(v5) & 0x7FFF) != *(_WORD *)(v10 + 26) && (WORD1(v5) & 0x7FFF) != 0x7FFF )
        goto LABEL_17;
      Win32ClientInfo = v9->Win32ClientInfo;
      if ( (*(_BYTE *)(v10 + 25) & 1) == 0 && *(_BYTE *)(v10 + 24) == 1 )
      {
        v12 = (_QWORD *)Win32ClientInfo[4];
        if ( v12 && *(_QWORD *)(v10 + 16) == *v12 )
          v8 = *(_QWORD *)v10 + Win32ClientInfo[5];
        else
          v8 = NtUserMapDesktopObject(v5);
      }
      if ( (*(_BYTE *)(v10 + 25) & 4) != 0
        || !Win32ClientInfo
        || (*((_DWORD *)Win32ClientInfo + 7) & 0x20000000) == 0
        || v8 && (unsigned int)NtUserValidateHandleSecure(v5) )
      {
LABEL_17:
        if ( v8 )
        {
LABEL_18:
          *a1 = *(_QWORD *)v8;
          goto LABEL_19;
        }
      }
      RtlSetLastWin32Error(0x578u);
      v8 = 0;
    }
    if ( !v8 )
      return 0;
    goto LABEL_18;
  }
  v8 = 0;
LABEL_19:
  v13 = *((unsigned int *)a1 + 2);
  if ( (unsigned int)v13 < 0x400 && ((MessageTable[v13] & 0x200) != 0 || (_DWORD)v13 == 537 && (a1[2] & 0x8000LL) != 0) )
  {
    v32 = 1159;
LABEL_108:
    RtlSetLastWin32Error(v32);
    return 0;
  }
  if ( (_DWORD)v13 == 275 || (_DWORD)v13 == 280 )
  {
    v23 = a1[3];
    if ( v23 )
    {
      if ( (_DWORD)v13 == 280 )
        return NtUserDispatchMessage(a1);
      if ( !*(_DWORD *)&gfServerProcess )
      {
        if ( (unsigned int)NtUserValidateTimerCallback(v23) )
        {
          if ( v8 )
            v6 = *(_QWORD *)(v8 + 224);
          return UserCallWinProc(
                   v6,
                   a1[3],
                   *a1,
                   *((unsigned int *)a1 + 2),
                   a1[2],
                   (unsigned int)((MEMORY[0x7FFE0320] * (unsigned __int64)MEMORY[0x7FFE0004]) >> 24));
        }
        return 0;
      }
    }
  }
  if ( !v8 )
    return 0;
  v14 = a1[2];
  if ( (*(_BYTE *)(v8 + 18) & 4) != 0 || (_DWORD)v13 == 15 )
  {
    if ( v3 )
    {
      if ( (*(_BYTE *)gpsi & 2) != 0 && ((_DWORD)v13 == 258 || (_DWORD)v13 == 204) )
      {
        if ( (v14 & 0xFF00) != 0 )
        {
          if ( (v14 & 0x80000000) == 0 )
          {
            if ( (v14 & 0xFF00) != 0 )
              v34 = BYTE1(v14) | ((unsigned __int8)v14 << 8);
            else
              v34 = (unsigned __int8)a1[2];
            a1[2] = v34;
          }
        }
        else
        {
          v35 = NtCurrentTeb();
          v36 = BYTE5(v35->Win32ClientInfo[19]);
          if ( (_BYTE)v36 )
          {
            a1[2] = v14 | (v36 << 8);
            BYTE5(v35->Win32ClientInfo[19]) = 0;
          }
          else if ( IsDBCSLeadByteEx(LOWORD(NtCurrentTeb()->Win32ClientInfo[19]), v14) )
          {
            BYTE5(v35->Win32ClientInfo[19]) = *((_BYTE *)a1 + 16);
            return 1;
          }
        }
      }
      RtlMBMessageWParamCharToWCS(*((unsigned int *)a1 + 2), a1 + 2);
    }
    result = NtUserDispatchMessage(a1);
    a1[2] = v14;
    return result;
  }
  v15 = *(_QWORD *)(v8 + 120);
  if ( (_DWORD)v13 == 576 )
  {
    PreprocessTouchInputMessage(0x240u, a1[2], a1 + 3);
  }
  else if ( (_DWORD)v13 == 281 )
  {
    PreprocessGestureMessage(0x119u, a1[2], a1 + 3);
  }
  if ( (v3 == 0) != (((unsigned __int8)~*(_BYTE *)(v8 + 18) >> 3) & 1) )
  {
    if ( NtCurrentTeb()->Win32ThreadInfo || NtUserGetThreadState(14) )
      Win32ThreadInfo = NtCurrentTeb()->Win32ThreadInfo;
    else
      Win32ThreadInfo = 0;
    v17 = (unsigned __int16)*(_DWORD *)v8;
    if ( v17 < *(_QWORD *)(gSharedInfo + 8)
      && (v18 = qword_1800C9378 + (unsigned int)(dword_1800C9380 * v17), *(_BYTE *)(v18 + 24))
      && v18 )
    {
      v19 = *(PVOID *)(v18 + 8);
    }
    else
    {
      v19 = 0;
    }
    if ( Win32ThreadInfo != v19 )
      return 0;
    if ( v3 )
    {
      if ( (*(_BYTE *)gpsi & 2) != 0 )
      {
        v26 = *((_DWORD *)a1 + 2);
        if ( v26 == 204 || v26 == 258 )
        {
          v27 = *((_DWORD *)a1 + 4);
          if ( (v27 & 0xFF00) != 0 )
          {
            v28 = a1[2];
            if ( (v28 & 0x80000000) == 0 )
            {
              if ( (v28 & 0xFF00) != 0 )
                v29 = BYTE1(v28) | ((unsigned __int8)v28 << 8);
              else
                v29 = (unsigned __int8)v28;
              a1[2] = v29;
            }
          }
          else
          {
            v30 = NtCurrentTeb();
            v31 = BYTE4(v30->Win32ClientInfo[19]);
            if ( (_BYTE)v31 )
            {
              a1[2] |= v31 << 8;
              BYTE4(v30->Win32ClientInfo[19]) = 0;
            }
            else if ( IsDBCSLeadByteEx(LOWORD(NtCurrentTeb()->Win32ClientInfo[19]), v27) )
            {
              BYTE4(v30->Win32ClientInfo[19]) = *((_BYTE *)a1 + 16);
              return 1;
            }
          }
        }
      }
      RtlMBMessageWParamCharToWCS(*((unsigned int *)a1 + 2), a1 + 2);
    }
    else
    {
      RtlWCSMessageWParamCharToMB(*((unsigned int *)a1 + 2), a1 + 2);
      if ( (*(_BYTE *)gpsi & 2) != 0 )
      {
        v25 = *((_DWORD *)a1 + 2);
        if ( v25 == 204 || v25 == 258 )
        {
          if ( (a1[2] & 0xFF00) != 0 )
          {
            v33 = NtCurrentTeb();
            v21 = 1;
            v33->Win32ClientInfo[20] = *a1;
            LODWORD(v33->Win32ClientInfo[21]) = *((_DWORD *)a1 + 2);
            v33->Win32ClientInfo[23] = a1[3];
            LODWORD(v33->Win32ClientInfo[24]) = *((_DWORD *)a1 + 8);
            *(SIZE_T *)((char *)&v33->Win32ClientInfo[24] + 4) = *(_QWORD *)((char *)a1 + 36);
            v33->Win32ClientInfo[22] = *((unsigned __int8 *)a1 + 16);
            a1[2] = *((unsigned __int8 *)a1 + 17);
            goto LABEL_43;
          }
          a1[2] = (unsigned __int8)a1[2];
        }
      }
    }
  }
  v21 = 0;
LABEL_43:
  for ( i = UserCallWinProcCheckWow(*(_QWORD *)(v8 + 224), v15, *a1, *((unsigned int *)a1 + 2), a1[2], a1[3]);
        (*(_BYTE *)gpsi & 2) != 0;
        i = UserCallWinProcCheckWow(*(_QWORD *)(v8 + 224), v15, *a1, *((unsigned int *)a1 + 2), a1[2], a1[3]) )
  {
    if ( !v21 )
      break;
    if ( !NtCurrentTeb()->Win32ClientInfo[22] )
      break;
    v24 = NtCurrentTeb();
    a1[2] = v24->Win32ClientInfo[22];
    v24->Win32ClientInfo[22] = 0;
  }
  a1[2] = v14;
  return i;
}

```

## disassembly

```asm
0x18000ae90  mov     [rsp+arg_8], rbx
0x18000ae95  mov     [rsp+arg_10], rsi
0x18000ae9a  mov     [rsp+arg_0], rcx
0x18000ae9f  push    rdi
0x18000aea0  push    r12
0x18000aea2  push    r13
0x18000aea4  push    r14
0x18000aea6  push    r15
0x18000aea8  sub     rsp, 50h
0x18000aeac  mov     r12d, edx
0x18000aeaf  mov     rbx, rcx
0x18000aeb2  test    dword ptr [rcx+8], 0FFFE0000h
0x18000aeb9  jnz     loc_18000B49E
0x18000aebf  mov     rsi, [rcx]
0x18000aec2  xor     r15d, r15d
0x18000aec5  test    rsi, rsi
0x18000aec8  jz      loc_18000B23F
0x18000aece  mov     rdi, gs:30h
0x18000aed7  cmp     rsi, [rdi+840h]
0x18000aede  jnz     short loc_18000AEF5
0x18000aee0  mov     rdi, [rdi+848h]
0x18000aee7  test    rdi, rdi
0x18000aeea  jz      loc_18000B090
0x18000aef0  jmp     loc_18000AF87
0x18000aef5  mov     rdi, r15
0x18000aef8  mov     r13, gs:30h
0x18000af01  movzx   ecx, si
0x18000af04  mov     rax, cs:gpsi
0x18000af0b  cmp     rcx, [rax+8]
0x18000af0f  jnb     short loc_18000AF7E
0x18000af11  call    _HANDLEENTRY_FROM_INDEX
0x18000af16  mov     r14, rax
0x18000af19  test    rax, rax
0x18000af1c  jz      short loc_18000AF7E
0x18000af1e  mov     rax, rsi
0x18000af21  shr     rax, 10h
0x18000af25  mov     ecx, 7FFFh
0x18000af2a  and     ax, cx
0x18000af2d  cmp     ax, [r14+1Ah]
0x18000af32  jnz     loc_18000B4A8
0x18000af38  add     r13, 800h
0x18000af3f  test    byte ptr [r14+19h], 1
0x18000af44  jnz     short loc_18000AF6E
0x18000af46  cmp     byte ptr [r14+18h], 1
0x18000af4b  jnz     short loc_18000AF6E
0x18000af4d  mov     rax, [r13+20h]
0x18000af51  test    rax, rax
0x18000af54  jz      loc_18000B444
0x18000af5a  mov     rax, [rax]
0x18000af5d  cmp     [r14+10h], rax
0x18000af61  jnz     loc_18000B444
0x18000af67  mov     rdi, [r13+28h]
0x18000af6b  add     rdi, [r14]
0x18000af6e  test    byte ptr [r14+19h], 4
0x18000af73  jnz     short loc_18000AF7E
0x18000af75  test    r13, r13
0x18000af78  jnz     loc_18000B187
0x18000af7e  test    rdi, rdi
0x18000af81  jz      loc_18000B1AB
0x18000af87  mov     rax, [rdi]
0x18000af8a  mov     [rbx], rax
0x18000af8d  mov     ecx, [rbx+8]; unsigned int
0x18000af90  cmp     ecx, 400h
0x18000af96  jnb     short loc_18000AFBC
0x18000af98  lea     rdx, MessageTable
0x18000af9f  mov     r8d, 200h
0x18000afa5  test    [rdx+rcx*2], r8w
0x18000afaa  jnz     loc_18000B393
0x18000afb0  cmp     ecx, 219h
0x18000afb6  jz      loc_18000B385
0x18000afbc  cmp     ecx, 113h
0x18000afc2  jz      loc_18000B120
0x18000afc8  cmp     ecx, 118h
0x18000afce  jz      loc_18000B120
0x18000afd4  test    rdi, rdi
0x18000afd7  jz      loc_18000B090
0x18000afdd  mov     r14, [rbx+10h]
0x18000afe1  test    byte ptr [rdi+12h], 4
0x18000afe5  jnz     loc_18000B28D
0x18000afeb  cmp     ecx, 0Fh
0x18000afee  jz      loc_18000B28D
0x18000aff4  mov     r13, [rdi+78h]
0x18000aff8  cmp     ecx, 240h
0x18000affe  jz      loc_18000B2A8
0x18000b004  cmp     ecx, 119h
0x18000b00a  jz      loc_18000B27C
0x18000b010  movzx   ecx, byte ptr [rdi+12h]
0x18000b014  not     cl
0x18000b016  shr     ecx, 3
0x18000b019  and     ecx, 1
0x18000b01c  mov     eax, r15d
0x18000b01f  test    r12d, r12d
0x18000b022  setz    al
0x18000b025  cmp     eax, ecx
0x18000b027  jz      loc_18000B0B9
0x18000b02d  mov     rax, gs:30h
0x18000b036  cmp     qword ptr [rax+78h], 0
0x18000b03b  jz      loc_18000B465
0x18000b041  mov     rax, gs:30h
0x18000b04a  mov     r8, [rax+78h]
0x18000b04e  mov     eax, [rdi]
0x18000b050  movzx   ecx, ax
0x18000b053  mov     rax, cs:gSharedInfo
0x18000b05a  cmp     rcx, [rax+8]
0x18000b05e  jnb     loc_18000B336
0x18000b064  imul    ecx, cs:dword_1800C9380
0x18000b06b  mov     edx, ecx
0x18000b06d  add     rdx, cs:qword_1800C9378
0x18000b074  cmp     byte ptr [rdx+18h], 0
0x18000b078  jz      loc_18000B336
0x18000b07e  test    rdx, rdx
0x18000b081  jz      loc_18000B336
0x18000b087  mov     rax, [rdx+8]
0x18000b08b  cmp     r8, rax
0x18000b08e  jz      short loc_18000B094
0x18000b090  xor     eax, eax
0x18000b092  jmp     short loc_18000B106
0x18000b094  test    r12d, r12d
0x18000b097  jz      loc_18000B2B9
0x18000b09d  mov     rax, cs:gpsi
0x18000b0a4  test    byte ptr [rax], 2
0x18000b0a7  jnz     loc_18000B2FF
0x18000b0ad  lea     rdx, [rbx+10h]
0x18000b0b1  mov     ecx, [rbx+8]
0x18000b0b4  call    RtlMBMessageWParamCharToWCS
0x18000b0b9  mov     r12d, r15d
0x18000b0bc  mov     [rsp+78h+var_40], 1
0x18000b0c4  mov     rax, [rbx+18h]
0x18000b0c8  mov     [rsp+78h+var_50], rax
0x18000b0cd  mov     rax, [rbx+10h]
0x18000b0d1  mov     [rsp+78h+var_58], rax
0x18000b0d6  mov     r9d, [rbx+8]
0x18000b0da  mov     r8, [rbx]
0x18000b0dd  mov     rdx, r13
0x18000b0e0  mov     rcx, [rdi+0E0h]
0x18000b0e7  call    ?UserCallWinProcCheckWow@@YA_JPEAU_ACTIVATION_CONTEXT@@P6A_JPEAUtagWND@@I_K_J@ZPEAUHWND__@@W4_WM_VALUE@@23PEAXH@Z; UserCallWinProcCheckWow(_ACTIVATION_CONTEXT *,__int64 (*)(tagWND *,uint,unsigned __int64,__int64),HWND__ *,_WM_VALUE,unsigned __int64,__int64,void *,int)
0x18000b0ec  mov     rdx, rax
0x18000b0ef  mov     rcx, cs:gpsi
0x18000b0f6  test    byte ptr [rcx], 2
0x18000b0f9  jnz     loc_18000B1C0
0x18000b0ff  mov     [rbx+10h], r14
0x18000b103  mov     rax, rdx
0x18000b106  lea     r11, [rsp+78h+var_28]
0x18000b10b  mov     rbx, [r11+38h]
0x18000b10f  mov     rsi, [r11+40h]
0x18000b113  mov     rsp, r11
0x18000b116  pop     r15
0x18000b118  pop     r14
0x18000b11a  pop     r13
0x18000b11c  pop     r12
0x18000b11e  pop     rdi
0x18000b11f  retn
0x18000b120  mov     rax, [rbx+18h]
0x18000b124  test    rax, rax
0x18000b127  jz      loc_18000AFD4
0x18000b12d  cmp     ecx, 118h
0x18000b133  jz      loc_18000B33E
0x18000b139  cmp     cs:gfServerProcess, 0
0x18000b140  jnz     loc_18000AFD4
0x18000b146  mov     rcx, rax
0x18000b149  call    cs:__imp_NtUserValidateTimerCallback
0x18000b14f  test    eax, eax
0x18000b151  jz      loc_18000B090
0x18000b157  mov     eax, 7FFE0320h
0x18000b15c  mov     rax, [rax]
0x18000b15f  mov     ecx, ds:7FFE0004h
0x18000b166  imul    rcx, rax
0x18000b16a  shr     rcx, 18h
0x18000b16e  mov     rdx, [rbx+10h]
0x18000b172  test    rdi, rdi
0x18000b175  jz      loc_18000B247
0x18000b17b  mov     r15, [rdi+0E0h]
0x18000b182  jmp     loc_18000B247
0x18000b187  test    dword ptr [r13+1Ch], 20000000h
0x18000b18f  jz      loc_18000AF7E
0x18000b195  test    rdi, rdi
0x18000b198  jz      short loc_18000B1AB
0x18000b19a  mov     rcx, rsi
0x18000b19d  call    cs:__imp_NtUserValidateHandleSecure
0x18000b1a3  test    eax, eax
0x18000b1a5  jnz     loc_18000AF7E
0x18000b1ab  mov     ecx, 578h; LastError
0x18000b1b0  call    cs:__imp_RtlSetLastWin32Error
0x18000b1b6  mov     rdi, r15
0x18000b1b9  jmp     loc_18000AEE7
0x18000b1c0  test    r12d, r12d
0x18000b1c3  jz      loc_18000B0FF
0x18000b1c9  mov     rcx, gs:30h
0x18000b1d2  cmp     qword ptr [rcx+8B0h], 0
0x18000b1da  jz      loc_18000B0FF
0x18000b1e0  mov     rcx, gs:30h
0x18000b1e9  mov     rax, [rcx+8B0h]
0x18000b1f0  mov     [rbx+10h], rax
0x18000b1f4  mov     [rcx+8B0h], r15
0x18000b1fb  mov     [rsp+78h+var_40], 1
0x18000b203  mov     rax, [rbx+18h]
0x18000b207  mov     [rsp+78h+var_50], rax
0x18000b20c  mov     rax, [rbx+10h]
0x18000b210  mov     [rsp+78h+var_58], rax
0x18000b215  mov     r9d, [rbx+8]
0x18000b219  mov     r8, [rbx]
0x18000b21c  mov     rdx, r13
0x18000b21f  mov     rcx, [rdi+0E0h]
0x18000b226  call    ?UserCallWinProcCheckWow@@YA_JPEAU_ACTIVATION_CONTEXT@@P6A_JPEAUtagWND@@I_K_J@ZPEAUHWND__@@W4_WM_VALUE@@23PEAXH@Z; UserCallWinProcCheckWow(_ACTIVATION_CONTEXT *,__int64 (*)(tagWND *,uint,unsigned __int64,__int64),HWND__ *,_WM_VALUE,unsigned __int64,__int64,void *,int)
0x18000b22b  mov     rdx, rax
0x18000b22e  mov     rax, cs:gpsi
0x18000b235  test    byte ptr [rax], 2
0x18000b238  jnz     short loc_18000B1C0
0x18000b23a  jmp     loc_18000B0FF
0x18000b23f  mov     rdi, r15
0x18000b242  jmp     loc_18000AF8D
0x18000b247  mov     eax, ecx
0x18000b249  mov     [rsp+78h+var_50], rax
0x18000b24e  mov     [rsp+78h+var_58], rdx
0x18000b253  mov     r9d, [rbx+8]
0x18000b257  mov     r8, [rbx]
0x18000b25a  mov     rdx, [rbx+18h]
0x18000b25e  mov     rcx, r15
0x18000b261  call    ?UserCallWinProc@@YA_JPEAU_ACTIVATION_CONTEXT@@P6A_JPEAUtagWND@@I_K_J@ZPEAUHWND__@@W4_WM_VALUE@@23@Z; UserCallWinProc(_ACTIVATION_CONTEXT *,__int64 (*)(tagWND *,uint,unsigned __int64,__int64),HWND__ *,_WM_VALUE,unsigned __int64,__int64)
0x18000b266  mov     [rsp+78h+var_38], rax
0x18000b26b  jmp     loc_18000B106
0x18000b270  xor     eax, eax
0x18000b272  mov     [rsp+78h+var_38], rax
0x18000b277  jmp     loc_18000B106
0x18000b27c  lea     r8, [rbx+18h]; __int64 *
0x18000b280  mov     rdx, r14; unsigned __int64
0x18000b283  call    ?PreprocessGestureMessage@@YAHI_KPEA_J@Z; PreprocessGestureMessage(uint,unsigned __int64,__int64 *)
0x18000b288  jmp     loc_18000B010
0x18000b28d  test    r12d, r12d
0x18000b290  jnz     loc_18000B481
0x18000b296  mov     rcx, rbx
0x18000b299  call    cs:__imp_NtUserDispatchMessage
0x18000b29f  mov     [rbx+10h], r14
0x18000b2a3  jmp     loc_18000B106
0x18000b2a8  lea     r8, [rbx+18h]; __int64 *
0x18000b2ac  mov     rdx, r14; unsigned __int64
0x18000b2af  call    ?PreprocessTouchInputMessage@@YAHI_KPEA_J@Z; PreprocessTouchInputMessage(uint,unsigned __int64,__int64 *)
0x18000b2b4  jmp     loc_18000B010
0x18000b2b9  lea     rdx, [rbx+10h]
0x18000b2bd  mov     ecx, [rbx+8]
0x18000b2c0  call    RtlWCSMessageWParamCharToMB
0x18000b2c5  mov     rax, cs:gpsi
0x18000b2cc  test    byte ptr [rax], 2
0x18000b2cf  jz      loc_18000B0B9
0x18000b2d5  mov     eax, [rbx+8]
0x18000b2d8  cmp     eax, 0CCh
0x18000b2dd  jnz     loc_18000B455
0x18000b2e3  mov     eax, 0FF00h
0x18000b2e8  test    [rbx+10h], eax
0x18000b2eb  jnz     loc_18000B3EB
0x18000b2f1  mov     ecx, 0FFh
0x18000b2f6  and     [rbx+10h], rcx
0x18000b2fa  jmp     loc_18000B0B9
0x18000b2ff  mov     eax, [rbx+8]
0x18000b302  cmp     eax, 0CCh
0x18000b307  jnz     short loc_18000B378
0x18000b309  mov     edx, [rbx+10h]; TestChar
0x18000b30c  mov     eax, 0FF00h
0x18000b311  test    eax, edx
0x18000b313  jz      short loc_18000B34C
0x18000b315  mov     rcx, [rbx+10h]
0x18000b319  bt      rcx, 1Fh
0x18000b31e  jb      loc_18000B0AD
0x18000b324  test    ax, cx
0x18000b327  jnz     short loc_18000B39D
0x18000b329  movzx   eax, cx
0x18000b32c  mov     ecx, 0FFh
0x18000b331  and     ax, cx
0x18000b334  jmp     short loc_18000B3AB
0x18000b336  mov     rax, r15
0x18000b339  jmp     loc_18000B08B
0x18000b33e  mov     rcx, rbx
0x18000b341  call    cs:__imp_NtUserDispatchMessage
0x18000b347  jmp     loc_18000B106
0x18000b34c  mov     r12, gs:30h
0x18000b355  movzx   eax, byte ptr [r12+89Ch]
0x18000b35e  test    al, al
0x18000b360  jz      short loc_18000B3B7
0x18000b362  shl     rax, 8
0x18000b366  or      [rbx+10h], rax
0x18000b36a  mov     byte ptr [r12+89Ch], 0
0x18000b373  jmp     loc_18000B0AD
0x18000b378  cmp     eax, 102h
0x18000b37d  jnz     loc_18000B0AD
0x18000b383  jmp     short loc_18000B309
0x18000b385  mov     eax, [rbx+10h]
0x18000b388  bt      rax, 0Fh
0x18000b38d  jnb     loc_18000AFBC
0x18000b393  mov     ecx, 487h; LastError
0x18000b398  jmp     loc_18009860F
0x18000b39d  movzx   eax, cl
0x18000b3a0  shl     ax, 8
0x18000b3a4  shr     cx, 8
0x18000b3a8  or      ax, cx
0x18000b3ab  movzx   eax, ax
0x18000b3ae  mov     [rbx+10h], rax
0x18000b3b2  jmp     loc_18000B0AD
0x18000b3b7  mov     rax, gs:30h
0x18000b3c0  movzx   ecx, word ptr [rax+898h]; CodePage
0x18000b3c7  call    cs:__imp_IsDBCSLeadByteEx
  ... truncated ...
```
