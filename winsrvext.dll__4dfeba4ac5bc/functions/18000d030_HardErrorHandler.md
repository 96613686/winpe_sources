# HardErrorHandler

- ea: `0x18000d030`
- end: `0x18000d6e8`
- name: `HardErrorHandler`
- size: `1720`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task`

## callers

- `0x18000d924`

## callees

- `0x18000bbd0`
- `0x18000bc38`
- `0x18000d030`
- `0x18000da7c`
- `0x180012b48`
- `0x1800138c5`
- `0x1800138f0`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x18000d106`
- `ntdll!RtlLeaveCriticalSection` at `0x18000d163`
- `ntdll!RtlLeaveCriticalSection` at `0x18000d52c`
- `ntdll!RtlLeaveCriticalSection` at `0x18000d591`
- `ntdll!RtlLeaveCriticalSection` at `0x18000d601`
- `ntdll!RtlLeaveCriticalSection` at `0x18000d62e`
- `ntdll!RtlLeaveCriticalSection` at `0x18000d680`
- `ntdll!RtlLeaveCriticalSection` at `0x18000d6bb`
- `ntdll!RtlLeaveCriticalSection` at `0x18000d106`
- `ntdll!RtlLeaveCriticalSection` at `0x18000d163`
- `ntdll!RtlLeaveCriticalSection` at `0x18000d52c`
- `ntdll!RtlLeaveCriticalSection` at `0x18000d591`
- `ntdll!RtlLeaveCriticalSection` at `0x18000d601`
- `ntdll!RtlLeaveCriticalSection` at `0x18000d62e`
- `ntdll!RtlLeaveCriticalSection` at `0x18000d680`
- `ntdll!RtlLeaveCriticalSection` at `0x18000d6bb`
- `ntdll!RtlEnterCriticalSection` at `0x18000d0d2`
- `ntdll!RtlEnterCriticalSection` at `0x18000d470`
- `ntdll!RtlEnterCriticalSection` at `0x18000d4e2`
- `ntdll!RtlEnterCriticalSection` at `0x18000d57e`
- `ntdll!RtlEnterCriticalSection` at `0x18000d5e4`
- `ntdll!RtlEnterCriticalSection` at `0x18000d69a`
- `ntdll!RtlEnterCriticalSection` at `0x18000d0d2`
- `ntdll!RtlEnterCriticalSection` at `0x18000d470`
- `ntdll!RtlEnterCriticalSection` at `0x18000d4e2`
- `ntdll!RtlEnterCriticalSection` at `0x18000d57e`
- `ntdll!RtlEnterCriticalSection` at `0x18000d5e4`
- `ntdll!RtlEnterCriticalSection` at `0x18000d69a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d4fe`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d50e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d51d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d4fe`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d50e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d51d`
- `win32u!NtUserHardErrorControl` at `0x18000d0b3`
- `win32u!NtUserHardErrorControl` at `0x18000d342`
- `win32u!NtUserHardErrorControl` at `0x18000d3ea`
- `win32u!NtUserHardErrorControl` at `0x18000d65f`
- `win32u!NtUserHardErrorControl` at `0x18000d0b3`
- `win32u!NtUserHardErrorControl` at `0x18000d342`
- `win32u!NtUserHardErrorControl` at `0x18000d3ea`
- `win32u!NtUserHardErrorControl` at `0x18000d65f`
- `USER32!MsgWaitForMultipleObjects` at `0x18000d125`
- `USER32!MsgWaitForMultipleObjects` at `0x18000d125`
- `USER32!PeekMessageW` at `0x18000d143`
- `USER32!PeekMessageW` at `0x18000d143`
- `USER32!MB_GetString` at `0x18000d299`
- `USER32!MB_GetString` at `0x18000d299`
- `USER32!SoftModalMessageBox` at `0x18000d364`
- `USER32!SoftModalMessageBox` at `0x18000d364`
- `USER32!MessageBoxTimeoutW` at `0x18000d3ce`
- `USER32!MessageBoxTimeoutW` at `0x18000d3ce`

## pseudocode

```c
NTSTATUS HardErrorHandler()
{
  __int64 v0; // rbx
  __int64 v1; // rdi
  __int64 *v2; // r14
  int v3; // r12d
  char *v4; // rbx
  int v5; // eax
  __int64 *v6; // r13
  __int64 v7; // rcx
  __int64 v8; // r14
  unsigned int v9; // r9d
  char *v10; // r12
  bool v11; // zf
  int v12; // r13d
  int v13; // r14d
  unsigned __int16 v14; // r15
  int v15; // eax
  int v16; // eax
  __int64 v17; // rdx
  int v18; // r15d
  unsigned int v19; // eax
  unsigned int v20; // ebx
  int v21; // ecx
  int v22; // edx
  __int64 v23; // r9
  int v24; // edx
  __int64 v25; // rcx
  int v26; // r15d
  __int64 *v27; // rcx
  __int64 *i; // rdx
  int v29; // ebx
  __int64 v30; // rax
  int v31; // edx
  __int64 v33; // rbx
  int dwWakeMask; // [rsp+20h] [rbp-E0h]
  int v35; // [rsp+30h] [rbp-D0h]
  __int16 v36; // [rsp+34h] [rbp-CCh]
  int v37; // [rsp+34h] [rbp-CCh]
  unsigned int v38; // [rsp+38h] [rbp-C8h] BYREF
  unsigned int v39; // [rsp+3Ch] [rbp-C4h]
  _WORD v40[4]; // [rsp+40h] [rbp-C0h]
  __int64 v41; // [rsp+48h] [rbp-B8h]
  __int64 v42; // [rsp+50h] [rbp-B0h]
  __int64 *v43; // [rsp+58h] [rbp-A8h]
  _QWORD v44[2]; // [rsp+60h] [rbp-A0h] BYREF
  struct tagMSG Msg; // [rsp+70h] [rbp-90h] BYREF
  int v46; // [rsp+A0h] [rbp-60h] BYREF
  _DWORD v47[5]; // [rsp+A4h] [rbp-5Ch] BYREF
  __int64 v48; // [rsp+B8h] [rbp-48h]
  __int64 v49; // [rsp+C0h] [rbp-40h]
  int v50; // [rsp+C8h] [rbp-38h]
  _DWORD *v51; // [rsp+100h] [rbp+0h]
  __int128 *v52; // [rsp+108h] [rbp+8h]
  int v53; // [rsp+110h] [rbp+10h]
  int v54; // [rsp+114h] [rbp+14h]
  int v55; // [rsp+118h] [rbp+18h]
  int v56; // [rsp+11Ch] [rbp+1Ch]
  _DWORD v57[4]; // [rsp+140h] [rbp+40h] BYREF
  __int128 v58; // [rsp+150h] [rbp+50h] BYREF
  __int64 v59; // [rsp+160h] [rbp+60h]

  v0 = 0;
  v59 = 0;
  v38 = 0;
  v44[1] = 0;
  v47[0] = 0;
  v58 = 0;
  memset_0(&v46, 0, 0x9Cu);
  v44[0] = 0;
  memset(&Msg, 0, sizeof(Msg));
  if ( !gbExitInProgress )
  {
    v35 = 0;
    if ( (unsigned int)NtUserHardErrorControl(0, 0, 0) != 1 )
    {
      while ( 1 )
      {
LABEL_3:
        RtlEnterCriticalSection(&gcsUserSrv);
        v1 = gphiList;
        if ( gphiList )
        {
          while ( (*(_BYTE *)(v1 + 136) & 0x20) != 0 )
          {
            v1 = *(_QWORD *)v1;
            if ( !v1 )
            {
              RtlLeaveCriticalSection(&gcsUserSrv);
              MsgWaitForMultipleObjects(0, 0, 0, 0xFFFFFFFF, 8u);
              PeekMessageW(&Msg, 0, 0, 0, 1u);
              CheckDefaultDesktop();
              goto LABEL_3;
            }
          }
          *(_DWORD *)(v1 + 136) |= 1u;
        }
        else
        {
          gdwHardErrorThreadId = v0;
        }
        RtlLeaveCriticalSection(&gcsUserSrv);
        if ( !v1 )
          return NtUserHardErrorControl(1, 0, 0);
        v2 = (__int64 *)(v1 + 192);
        if ( gbExitInProgress != (_DWORD)v0 )
        {
          v3 = 6;
          v4 = (char *)(v1 + 136);
          v35 = 6;
          goto LABEL_51;
        }
        v5 = *(_DWORD *)(v1 + 176);
        v6 = (__int64 *)(v1 + 192);
        v7 = *(_QWORD *)(v1 + 8);
        v43 = (__int64 *)(v1 + 192);
        v8 = *v2;
        v9 = (v5 & 0x20000 | 0x40000u) >> 17;
        v42 = v8;
        v39 = v9;
        if ( v7 )
          v41 = *(_QWORD *)(v7 + 64);
        else
          v41 = v0;
        v10 = (char *)(v1 + 136);
        v11 = *(_BYTE *)(v1 + 136) >= 0;
        *(_DWORD *)(v1 + 176) = v5 & 0xFFDEEFFF;
        if ( !v11 )
        {
          memset_0(v47, 0, 0x9Cu);
          v46 = 80;
          v12 = v0;
          v13 = v0;
          v48 = *(_QWORD *)(v1 + 152);
          v49 = *(_QWORD *)(v1 + 168);
          v56 = -1;
          v40[0] = *(_WORD *)(v1 + 184);
          v40[1] = *(_WORD *)(v1 + 190);
          v40[2] = *(_WORD *)(v1 + 188);
          do
          {
            v36 = v40[v13];
            v14 = v36 & 0x7FFF;
            if ( (unsigned __int16)((v36 & 0x7FFF) - 1) <= 0xAu )
            {
              *((_QWORD *)&v58 + v12) = MB_GetString((unsigned int)v14 - 1);
              v57[v12] = v13 + 1;
              LODWORD(v0) = 0;
              v15 = v54;
              if ( v36 < 0 )
                v15 = v12;
              v54 = v15;
              v16 = v55;
              if ( v14 == 1 )
                v16 = v12;
              ++v12;
              v55 = v16;
            }
            ++v13;
          }
          while ( v13 < 3 );
          v50 = 0x40000;
          v10 = (char *)(v1 + 136);
          if ( v12 != 1 || v57[0] != 1 )
            v50 = 262145;
          v9 = v39;
          v8 = v42;
          v52 = &v58;
          v53 = v12;
          v6 = v43;
          v51 = v57;
        }
        while ( 1 )
        {
          v17 = v41;
          *(_DWORD *)(v1 + 84) = 1;
          v37 = v0;
          v18 = NtUserHardErrorControl(v9, v17, v44);
          if ( v18 )
          {
            LODWORD(v25) = 1;
            v24 = v0;
            goto LABEL_63;
          }
          if ( *v10 >= 0 )
          {
            if ( (unsigned int)CheckShellHardError(v1, &v38) )
            {
              v20 = v38;
              goto LABEL_40;
            }
            if ( v8 && (v21 = *(_DWORD *)(v8 + 44), (unsigned int)(v21 - 1) <= 0xFFFFFFFD) )
              v22 = 1000 * v21;
            else
              v22 = *(_DWORD *)(v1 + 180);
            v23 = *(unsigned int *)(v1 + 176);
            LODWORD(v23) = v23 & 0xFFF9FFFF | 0x40000;
            LOWORD(dwWakeMask) = v0;
            v19 = MessageBoxTimeoutW(0, *(_QWORD *)(v1 + 152), *(_QWORD *)(v1 + 168), v23, dwWakeMask, v22);
          }
          else
          {
            v19 = SoftModalMessageBox(&v46);
          }
          v20 = v19;
LABEL_40:
          v18 = NtUserHardErrorControl(4, 0, v44);
          if ( v18 != 3 && v8 )
          {
            *(_DWORD *)(v8 + 48) = v20;
            if ( v20 != 32000 )
              goto LABEL_46;
            v18 = 0;
          }
          if ( v20 != 32000 )
          {
LABEL_46:
            v24 = v37;
            goto LABEL_47;
          }
          v20 = 1;
          v24 = 1;
LABEL_47:
          v25 = v20 < 0xC ? v20 : 0;
          v38 = v20 < 0xC ? v20 : 0;
          if ( *((_DWORD *)dwResponses + v25) == 1 && v18 == 3 )
          {
            v4 = v10;
            v2 = v6;
            if ( gSessionId == gServiceSessionId )
              goto LABEL_50;
          }
LABEL_63:
          v38 = (unsigned int)v25 < 0xC ? v25 : 0;
          v35 = *((_DWORD *)dwResponses + v38);
          if ( v18 != 3 )
            goto LABEL_66;
          v4 = v10;
          v2 = v6;
          if ( v24 )
            break;
          CheckDefaultDesktop();
          RtlEnterCriticalSection(&gcsUserSrv);
          v29 = *(_DWORD *)v10;
          RtlLeaveCriticalSection(&gcsUserSrv);
          v9 = v39;
          v8 = v42;
          if ( (v29 & 2) != 0 )
          {
LABEL_66:
            if ( v18 == 2 )
            {
              v30 = *v6;
              v0 = 0;
              if ( !*v6 || !*(_BYTE *)(v30 + 82) )
              {
                RtlEnterCriticalSection(&gcsUserSrv);
                *(_DWORD *)v10 = *(_DWORD *)v10 & 0xFFFFFFDE ^ 0x20;
                RtlLeaveCriticalSection(&gcsUserSrv);
                goto LABEL_3;
              }
              *(_DWORD *)(v30 + 48) = 32000;
              v4 = v10;
              v35 = 1;
              v2 = v6;
            }
            else
            {
              v2 = v6;
              v4 = v10;
            }
LABEL_50:
            v3 = v35;
            goto LABEL_51;
          }
          LODWORD(v0) = 0;
        }
        v3 = *((_DWORD *)dwResponses + v38);
LABEL_51:
        RtlEnterCriticalSection(&gcsUserSrv);
        v26 = *(_DWORD *)v4 & 2;
        if ( !v26 )
        {
          v27 = (__int64 *)gphiList;
          for ( i = &gphiList; v27 != (__int64 *)v1; v27 = (__int64 *)*v27 )
          {
            if ( !v27 )
              break;
            i = v27;
          }
          *i = *(_QWORD *)v1;
        }
        v0 = *v2;
        if ( *v2 )
        {
          if ( !*(_BYTE *)(v0 + 80) )
            ReplyMessageToTerminalServer(
              0,
              *(_QWORD *)(v0 + 64),
              *(_DWORD *)(v0 + 48),
              *(_QWORD *)(v0 + 56),
              *(_QWORD *)(v0 + 72));
          RtlEnterCriticalSection(&gcsUserSrv);
          if ( *(_BYTE *)(v0 + 81) )
            --PendingMessages;
          LocalFree(*(HLOCAL *)(v0 + 32));
          LocalFree(*(HLOCAL *)(v0 + 24));
          LocalFree((HLOCAL)v0);
          RtlLeaveCriticalSection(&gcsUserSrv);
          v0 = 0;
          *v2 = 0;
        }
        RtlLeaveCriticalSection(&gcsUserSrv);
        v31 = v3;
        if ( v26 )
          v31 = 1;
        ReplyHardError(v1, v31);
      }
    }
  }
  while ( 1 )
  {
    RtlEnterCriticalSection(&gcsUserSrv);
    v33 = gphiList;
    if ( !gphiList )
      break;
    gphiList = *(_QWORD *)gphiList;
    RtlLeaveCriticalSection(&gcsUserSrv);
    ReplyHardError(v33, 1);
  }
  gdwHardErrorThreadId = 0;
  return RtlLeaveCriticalSection(&gcsUserSrv);
}

```

## disassembly

```asm
0x18000d030  push    rbp
0x18000d032  push    rbx
0x18000d033  push    rsi
0x18000d034  push    rdi
0x18000d035  push    r12
0x18000d037  push    r13
0x18000d039  push    r14
0x18000d03b  push    r15
0x18000d03d  lea     rbp, [rsp-78h]
0x18000d042  sub     rsp, 178h
0x18000d049  mov     rax, cs:__security_cookie
0x18000d050  xor     rax, rsp
0x18000d053  mov     [rbp+0B0h+var_48], rax
0x18000d057  xor     eax, eax
0x18000d059  lea     rcx, [rbp+0B0h+var_110]; void *
0x18000d05d  xor     ebx, ebx
0x18000d05f  mov     [rbp+0B0h+var_50], rax
0x18000d063  xorps   xmm0, xmm0
0x18000d066  mov     [rsp+1B0h+var_178], ebx
0x18000d06a  xor     edx, edx; Val
0x18000d06c  mov     [rsp+1B0h+var_148], rbx
0x18000d071  mov     r8d, 9Ch; Size
0x18000d077  mov     [rbp+0B0h+var_10C], eax
0x18000d07a  movups  [rbp+0B0h+var_60], xmm0
0x18000d07e  call    memset_0
0x18000d083  cmp     cs:gbExitInProgress, ebx
0x18000d089  lea     r15d, [rbx+1]
0x18000d08d  xorps   xmm0, xmm0
0x18000d090  mov     [rsp+1B0h+var_150], rbx
0x18000d095  movups  xmmword ptr [rsp+1B0h+Msg.hwnd], xmm0
0x18000d09a  movups  xmmword ptr [rbp+0B0h+Msg.wParam], xmm0
0x18000d09e  movups  xmmword ptr [rbp+0B0h+Msg.time], xmm0
0x18000d0a2  jnz     loc_18000D66D
0x18000d0a8  xor     r8d, r8d
0x18000d0ab  mov     [rsp+1B0h+var_180], ebx
0x18000d0af  xor     edx, edx
0x18000d0b1  xor     ecx, ecx
0x18000d0b3  call    cs:__imp_NtUserHardErrorControl
0x18000d0ba  nop     dword ptr [rax+rax+00h]
0x18000d0bf  cmp     eax, r15d
0x18000d0c2  jz      loc_18000D66D
0x18000d0c8  lea     rsi, gcsUserSrv
0x18000d0cf  mov     rcx, rsi; CriticalSection
0x18000d0d2  call    cs:__imp_RtlEnterCriticalSection
0x18000d0d9  nop     dword ptr [rax+rax+00h]
0x18000d0de  mov     rdi, cs:gphiList
0x18000d0e5  test    rdi, rdi
0x18000d0e8  jnz     short loc_18000D0F2
0x18000d0ea  mov     cs:gdwHardErrorThreadId, ebx
0x18000d0f0  jmp     short loc_18000D160
0x18000d0f2  test    byte ptr [rdi+88h], 20h
0x18000d0f9  jz      short loc_18000D159
0x18000d0fb  mov     rdi, [rdi]
0x18000d0fe  test    rdi, rdi
0x18000d101  jnz     short loc_18000D0F2
0x18000d103  mov     rcx, rsi; CriticalSection
0x18000d106  call    cs:__imp_RtlLeaveCriticalSection
0x18000d10d  nop     dword ptr [rax+rax+00h]
0x18000d112  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x18000d116  mov     [rsp+1B0h+dwWakeMask], 8; dwWakeMask
0x18000d11e  xor     r8d, r8d; fWaitAll
0x18000d121  xor     edx, edx; pHandles
0x18000d123  xor     ecx, ecx; nCount
0x18000d125  call    cs:__imp_MsgWaitForMultipleObjects
0x18000d12c  nop     dword ptr [rax+rax+00h]
0x18000d131  xor     r9d, r9d; wMsgFilterMax
0x18000d134  mov     [rsp+1B0h+dwWakeMask], r15d; wRemoveMsg
0x18000d139  xor     r8d, r8d; wMsgFilterMin
0x18000d13c  lea     rcx, [rsp+1B0h+Msg]; lpMsg
0x18000d141  xor     edx, edx; hWnd
0x18000d143  call    cs:__imp_PeekMessageW
0x18000d14a  nop     dword ptr [rax+rax+00h]
0x18000d14f  call    CheckDefaultDesktop
0x18000d154  jmp     loc_18000D0CF
0x18000d159  or      [rdi+88h], r15d
0x18000d160  mov     rcx, rsi; CriticalSection
0x18000d163  call    cs:__imp_RtlLeaveCriticalSection
0x18000d16a  nop     dword ptr [rax+rax+00h]
0x18000d16f  test    rdi, rdi
0x18000d172  jz      loc_18000D657
0x18000d178  cmp     cs:gbExitInProgress, ebx
0x18000d17e  lea     r14, [rdi+0C0h]
0x18000d185  jz      short loc_18000D19E
0x18000d187  mov     r12d, 6
0x18000d18d  lea     rbx, [rdi+88h]
0x18000d194  mov     [rsp+1B0h+var_180], r12d
0x18000d199  jmp     loc_18000D46D
0x18000d19e  mov     eax, [rdi+0B0h]
0x18000d1a4  mov     r13, r14
0x18000d1a7  mov     rcx, [rdi+8]
0x18000d1ab  mov     r9d, eax
0x18000d1ae  and     r9d, 20000h
0x18000d1b5  mov     [rsp+1B0h+var_158], r14
0x18000d1ba  mov     r14, [r14]
0x18000d1bd  bts     r9d, 12h
0x18000d1c2  shr     r9d, 11h
0x18000d1c6  mov     [rsp+1B0h+var_160], r14
0x18000d1cb  mov     [rsp+1B0h+var_174], r9d
0x18000d1d0  test    rcx, rcx
0x18000d1d3  jz      short loc_18000D1E0
0x18000d1d5  mov     rcx, [rcx+40h]
0x18000d1d9  mov     [rsp+1B0h+var_168], rcx
0x18000d1de  jmp     short loc_18000D1E5
0x18000d1e0  mov     [rsp+1B0h+var_168], rbx
0x18000d1e5  and     eax, 0FFDEEFFFh
0x18000d1ea  lea     r12, [rdi+88h]
0x18000d1f1  test    byte ptr [r12], 80h
0x18000d1f6  mov     [rdi+0B0h], eax
0x18000d1fc  jz      loc_18000D32A
0x18000d202  xor     edx, edx; Val
0x18000d204  lea     rcx, [rbp+0B0h+var_10C]; void *
0x18000d208  mov     r8d, 9Ch; Size
0x18000d20e  call    memset_0
0x18000d213  mov     [rbp+0B0h+var_110], 50h ; 'P'
0x18000d21a  mov     r13d, ebx
0x18000d21d  mov     rax, [rdi+98h]
0x18000d224  mov     r14d, ebx
0x18000d227  mov     [rbp+0B0h+var_F8], rax
0x18000d22b  mov     r12d, 1
0x18000d231  mov     rax, [rdi+0A8h]
0x18000d238  mov     [rbp+0B0h+var_F0], rax
0x18000d23c  mov     [rbp+0B0h+var_94], 0FFFFFFFFh
0x18000d243  movzx   eax, word ptr [rdi+0B8h]
0x18000d24a  mov     [rsp+1B0h+var_170], ax
0x18000d24f  movzx   eax, word ptr [rdi+0BEh]
0x18000d256  mov     [rsp+1B0h+var_16E], ax
0x18000d25b  movzx   eax, word ptr [rdi+0BCh]
0x18000d262  mov     [rsp+1B0h+var_16C], ax
0x18000d267  mov     eax, r14d
0x18000d26a  mov     ecx, 7FFFh
0x18000d26f  movzx   eax, [rsp+rax*2+1B0h+var_170]
0x18000d274  movzx   r15d, ax
0x18000d278  mov     word ptr [rsp+1B0h+var_17C], ax
0x18000d27d  and     r15w, cx
0x18000d281  movzx   eax, r15w
0x18000d285  sub     ax, r12w
0x18000d289  cmp     ax, 0Ah
0x18000d28d  ja      short loc_18000D2D4
0x18000d28f  movzx   ecx, r15w
0x18000d293  sub     ecx, r12d
0x18000d296  movsxd  rbx, r13d
0x18000d299  call    cs:__imp_MB_GetString
0x18000d2a0  nop     dword ptr [rax+rax+00h]
0x18000d2a5  mov     qword ptr [rbp+rbx*8+0B0h+var_60], rax
0x18000d2aa  lea     eax, [r14+1]
0x18000d2ae  mov     [rbp+rbx*4+0B0h+var_70], eax
0x18000d2b2  xor     ebx, ebx
0x18000d2b4  cmp     word ptr [rsp+1B0h+var_17C], bx
0x18000d2b9  mov     eax, [rbp+0B0h+var_9C]
0x18000d2bc  cmovl   eax, r13d
0x18000d2c0  cmp     r15w, r12w
0x18000d2c4  mov     [rbp+0B0h+var_9C], eax
0x18000d2c7  mov     eax, [rbp+0B0h+var_98]
0x18000d2ca  cmovz   eax, r13d
0x18000d2ce  add     r13d, r12d
0x18000d2d1  mov     [rbp+0B0h+var_98], eax
0x18000d2d4  add     r14d, r12d
0x18000d2d7  cmp     r14d, 3
0x18000d2db  jl      short loc_18000D267
0x18000d2dd  mov     r15d, 1
0x18000d2e3  mov     [rbp+0B0h+var_E8], 40000h
0x18000d2ea  lea     r12, [rdi+88h]
0x18000d2f1  cmp     r13d, r15d
0x18000d2f4  jnz     short loc_18000D2FC
0x18000d2f6  cmp     [rbp+0B0h+var_70], r15d
0x18000d2fa  jz      short loc_18000D303
0x18000d2fc  mov     [rbp+0B0h+var_E8], 40001h
0x18000d303  mov     r9d, [rsp+1B0h+var_174]
0x18000d308  lea     rax, [rbp+0B0h+var_60]
0x18000d30c  mov     r14, [rsp+1B0h+var_160]
0x18000d311  mov     [rbp+0B0h+var_A8], rax
0x18000d315  lea     rax, [rbp+0B0h+var_70]
0x18000d319  mov     [rbp+0B0h+var_A0], r13d
0x18000d31d  mov     r13, [rsp+1B0h+var_158]
0x18000d322  mov     [rbp+0B0h+var_B0], rax
0x18000d326  jmp     short loc_18000D32A
0x18000d328  xor     ebx, ebx
0x18000d32a  mov     rdx, [rsp+1B0h+var_168]
0x18000d32f  lea     r8, [rsp+1B0h+var_150]
0x18000d334  mov     ecx, r9d
0x18000d337  mov     dword ptr [rdi+54h], 1
0x18000d33e  mov     [rsp+1B0h+var_17C], ebx
0x18000d342  call    cs:__imp_NtUserHardErrorControl
0x18000d349  nop     dword ptr [rax+rax+00h]
0x18000d34e  mov     r15d, eax
0x18000d351  test    eax, eax
0x18000d353  jnz     loc_18000D542
0x18000d359  test    byte ptr [r12], 80h
0x18000d35e  jz      short loc_18000D374
0x18000d360  lea     rcx, [rbp+0B0h+var_110]
0x18000d364  call    cs:__imp_SoftModalMessageBox
0x18000d36b  nop     dword ptr [rax+rax+00h]
0x18000d370  mov     ebx, eax
0x18000d372  jmp     short loc_18000D3E0
0x18000d374  lea     rdx, [rsp+1B0h+var_178]
0x18000d379  mov     rcx, rdi
0x18000d37c  call    CheckShellHardError
0x18000d381  test    eax, eax
0x18000d383  jnz     short loc_18000D3DC
0x18000d385  test    r14, r14
0x18000d388  jz      short loc_18000D39E
0x18000d38a  mov     ecx, [r14+2Ch]
0x18000d38e  lea     eax, [rcx-1]
0x18000d391  cmp     eax, 0FFFFFFFDh
0x18000d394  ja      short loc_18000D39E
0x18000d396  imul    edx, ecx, 3E8h
0x18000d39c  jmp     short loc_18000D3A4
0x18000d39e  mov     edx, [rdi+0B4h]
0x18000d3a4  mov     r9d, [rdi+0B0h]
0x18000d3ab  xor     ecx, ecx
0x18000d3ad  mov     r8, [rdi+0A8h]
0x18000d3b4  btr     r9d, 11h
0x18000d3b9  mov     [rsp+1B0h+var_188], edx
0x18000d3bd  bts     r9d, 12h
0x18000d3c2  mov     rdx, [rdi+98h]
0x18000d3c9  mov     word ptr [rsp+1B0h+dwWakeMask], bx
0x18000d3ce  call    cs:__imp_MessageBoxTimeoutW
0x18000d3d5  nop     dword ptr [rax+rax+00h]
0x18000d3da  jmp     short loc_18000D370
0x18000d3dc  mov     ebx, [rsp+1B0h+var_178]
0x18000d3e0  xor     edx, edx
0x18000d3e2  lea     r8, [rsp+1B0h+var_150]
0x18000d3e7  lea     ecx, [rdx+4]
0x18000d3ea  call    cs:__imp_NtUserHardErrorControl
0x18000d3f1  nop     dword ptr [rax+rax+00h]
0x18000d3f6  mov     r15d, eax
0x18000d3f9  cmp     eax, 3
0x18000d3fc  jz      short loc_18000D412
0x18000d3fe  test    r14, r14
0x18000d401  jz      short loc_18000D412
0x18000d403  mov     [r14+30h], ebx
0x18000d407  cmp     ebx, 7D00h
0x18000d40d  jnz     short loc_18000D425
0x18000d40f  xor     r15d, r15d
0x18000d412  cmp     ebx, 7D00h
0x18000d418  jnz     short loc_18000D425
0x18000d41a  mov     eax, 1
0x18000d41f  mov     ebx, eax
0x18000d421  mov     edx, eax
0x18000d423  jmp     short loc_18000D429
0x18000d425  mov     edx, [rsp+1B0h+var_17C]
0x18000d429  cmp     ebx, 0Ch
0x18000d42c  lea     r8, dwResponses
0x18000d433  sbb     ecx, ecx
0x18000d435  and     ecx, ebx
0x18000d437  mov     [rsp+1B0h+var_178], ecx
0x18000d43b  cmp     dword ptr [r8+rcx*4], 1
0x18000d440  jnz     loc_18000D549
0x18000d446  cmp     r15d, 3
0x18000d44a  jnz     loc_18000D549
0x18000d450  mov     eax, cs:gServiceSessionId
0x18000d456  mov     rbx, r12
0x18000d459  cmp     cs:gSessionId, eax
0x18000d45f  mov     r14, r13
0x18000d462  jnz     loc_18000D549
0x18000d468  mov     r12d, [rsp+1B0h+var_180]
0x18000d46d  mov     rcx, rsi; CriticalSection
0x18000d470  call    cs:__imp_RtlEnterCriticalSection
0x18000d477  nop     dword ptr [rax+rax+00h]
0x18000d47c  mov     r15d, [rbx]
0x18000d47f  and     r15d, 2
0x18000d483  jnz     short loc_18000D4B1
0x18000d485  mov     rcx, cs:gphiList
0x18000d48c  lea     rdx, gphiList
0x18000d493  cmp     rcx, rdi
0x18000d496  jz      short loc_18000D4AB
0x18000d498  test    rcx, rcx
0x18000d49b  jz      short loc_18000D4AB
0x18000d49d  mov     rax, [rcx]
0x18000d4a0  mov     rdx, rcx
0x18000d4a3  mov     rcx, rax
0x18000d4a6  cmp     rax, rdi
0x18000d4a9  jnz     short loc_18000D498
0x18000d4ab  mov     rax, [rdi]
0x18000d4ae  mov     [rdx], rax
0x18000d4b1  mov     rbx, [r14]
0x18000d4b4  test    rbx, rbx
0x18000d4b7  jz      loc_18000D62B
0x18000d4bd  cmp     byte ptr [rbx+50h], 0
0x18000d4c1  jnz     short loc_18000D4DF
0x18000d4c3  mov     rax, [rbx+48h]
0x18000d4c7  xor     ecx, ecx
0x18000d4c9  mov     r9, [rbx+38h]
0x18000d4cd  mov     r8d, [rbx+30h]
0x18000d4d1  mov     rdx, [rbx+40h]
0x18000d4d5  mov     qword ptr [rsp+1B0h+dwWakeMask], rax
0x18000d4da  call    ReplyMessageToTerminalServer
0x18000d4df  mov     rcx, rsi; CriticalSection
0x18000d4e2  call    cs:__imp_RtlEnterCriticalSection
0x18000d4e9  nop     dword ptr [rax+rax+00h]
0x18000d4ee  cmp     byte ptr [rbx+51h], 0
0x18000d4f2  jz      short loc_18000D4FA
0x18000d4f4  dec     cs:PendingMessages
0x18000d4fa  mov     rcx, [rbx+20h]; hMem
0x18000d4fe  call    cs:__imp_LocalFree
0x18000d505  nop     dword ptr [rax+rax+00h]
0x18000d50a  mov     rcx, [rbx+18h]; hMem
0x18000d50e  call    cs:__imp_LocalFree
0x18000d515  nop     dword ptr [rax+rax+00h]
0x18000d51a  mov     rcx, rbx; hMem
  ... truncated ...
```
