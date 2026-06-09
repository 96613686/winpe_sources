# _MonitorFromPoint

- ea: `0x180014310`
- end: `0x180014a43`
- name: `_MonitorFromPoint`
- size: `1843`
- prototype: ``
- caller_count: `4`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180013900`
- `0x1800142d0`
- `0x18002b854`
- `0x18003142c`

## callees

- `0x1800089f0`
- `0x180014310`
- `0x180014c10`
- `0x180015090`
- `0x180096e00`

## import_xrefs

- `win32u!NtUserGetThreadState` at `0x180014a26`
- `win32u!NtUserGetThreadState` at `0x180014a26`
- `ntdll!RtlSetLastWin32Error` at `0x1800975e0`
- `ntdll!RtlSetLastWin32Error` at `0x180097623`
- `ntdll!RtlSetLastWin32Error` at `0x18009766c`
- `ntdll!RtlSetLastWin32Error` at `0x1800975e0`
- `ntdll!RtlSetLastWin32Error` at `0x180097623`
- `ntdll!RtlSetLastWin32Error` at `0x18009766c`
- `ntdll!RtlNtStatusToDosError` at `0x1800975d4`
- `ntdll!RtlNtStatusToDosError` at `0x180097611`
- `ntdll!RtlNtStatusToDosError` at `0x18009765a`
- `ntdll!RtlNtStatusToDosError` at `0x1800975d4`
- `ntdll!RtlNtStatusToDosError` at `0x180097611`
- `ntdll!RtlNtStatusToDosError` at `0x18009765a`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x18001443c`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x180014454`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x1800144b5`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x1800144d7`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x180014506`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x180014528`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x180014696`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x1800146b1`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x18001470f`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x180014731`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x180014760`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x180014782`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x18001443c`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x180014454`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x1800144b5`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x1800144d7`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x180014506`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x180014528`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x180014696`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x1800146b1`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x18001470f`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x180014731`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x180014760`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x180014782`

## pseudocode

```c
struct tagMONITOR *__fastcall MonitorFromPoint(unsigned __int64 a1, unsigned int a2, unsigned int a3)
{
  unsigned int v3; // r15d
  int v5; // edi
  unsigned __int64 v6; // rsi
  __int64 v7; // r14
  __int64 v8; // r9
  __int64 v9; // rcx
  int v10; // r10d
  int v11; // r13d
  int v12; // ebx
  __int64 v13; // r12
  int v14; // ebx
  __int64 v15; // r8
  __int64 v17; // rcx
  __int64 v18; // r9
  unsigned int v19; // r8d
  __int64 v20; // r10
  __int64 v21; // rdx
  int v22; // r11d
  int v23; // r13d
  int v24; // ebx
  __int64 v25; // r12
  unsigned int v26; // eax
  int v27; // ebx
  unsigned int v28; // ecx
  int v29; // r9d
  unsigned int v30; // ecx
  __int64 v31; // rax
  unsigned __int64 v32; // r12
  __int64 v33; // rcx
  __int64 i; // r14
  int *MonitorRectForDpiContext; // rax
  int *v36; // r8
  int v37; // edx
  int v38; // eax
  int v39; // eax
  unsigned __int64 v40; // rcx
  __int64 v41; // rdx
  int v42; // r9d
  int v43; // eax
  __int64 v44; // [rsp+20h] [rbp-F8h]
  unsigned int v45; // [rsp+2Ch] [rbp-ECh]
  __int64 v46; // [rsp+30h] [rbp-E8h]
  int nNumber[4]; // [rsp+38h] [rbp-E0h] BYREF
  int v48; // [rsp+48h] [rbp-D0h]
  int v49; // [rsp+50h] [rbp-C8h]
  int v50; // [rsp+54h] [rbp-C4h]
  int v51[2]; // [rsp+58h] [rbp-C0h]
  int v52; // [rsp+60h] [rbp-B8h]
  int v53; // [rsp+64h] [rbp-B4h]
  __int64 v54; // [rsp+B0h] [rbp-68h]
  int v55[2]; // [rsp+B8h] [rbp-60h]
  __int64 v56; // [rsp+C0h] [rbp-58h]
  __int64 v57; // [rsp+C8h] [rbp-50h]

  v3 = a3;
  v45 = a3;
  v5 = a1;
  v6 = HIDWORD(a1);
  v7 = qword_1800C9388;
  if ( *(_DWORD *)qword_1800C9388 == 1 && a2 )
  {
    v17 = *(_QWORD *)(qword_1800C9388 + 8);
    if ( v17 )
      return (struct tagMONITOR *)(v17 + qword_1800C9390);
    return 0;
  }
  if ( !a3 )
  {
    if ( *(_DWORD *)&gfServerProcess || NtCurrentTeb() == (struct _TEB *)-2048LL && !NtUserGetThreadState(14) )
      v3 = 18;
    else
      v3 = LODWORD(NtCurrentTeb()->Win32ClientInfo[29])
         ? LODWORD(NtCurrentTeb()->Win32ClientInfo[29])
         : gDefaultDpiContext;
    v45 = v3;
    if ( (v3 & 0xF) != 2 )
    {
      if ( !(unsigned int)IsThreadDesktopComposited() )
        v3 = 18;
      v45 = v3;
    }
  }
  if ( a2 == 2 )
  {
    v18 = 0;
    v44 = 0;
    if ( (unsigned int)(v5 + 0x8000) > 0xFFFF || (unsigned int)(v6 + 0x8000) > 0xFFFF )
    {
      v32 = -1;
      v56 = -1;
      v33 = *(_QWORD *)(v7 + 16);
LABEL_69:
      for ( i = v33 + qword_1800C9390; i; i = 0 )
      {
        if ( (*(_BYTE *)(i + 24) & 1) != 0 )
        {
          MonitorRectForDpiContext = (int *)GetMonitorRectForDpiContext(nNumber, i, v3);
          v36 = MonitorRectForDpiContext;
          if ( v5 >= *MonitorRectForDpiContext )
          {
            v43 = MonitorRectForDpiContext[2];
            if ( v5 >= v43 )
              v37 = v5 - v43 + 1;
            else
              v37 = 0;
          }
          else
          {
            v37 = *MonitorRectForDpiContext - v5;
          }
          if ( v37 >= v32 )
          {
            v18 = v44;
          }
          else
          {
            v38 = v36[1];
            if ( (int)v6 >= v38 )
            {
              v42 = v36[3];
              if ( (int)v6 >= v42 )
              {
                v39 = v6 - v42 + 1;
              }
              else
              {
                if ( !v37 )
                  return (struct tagMONITOR *)i;
                v39 = 0;
              }
            }
            else
            {
              v39 = v38 - v6;
            }
            v40 = v37 * (__int64)v37;
            if ( v40 >= v32 )
            {
              v18 = v44;
            }
            else if ( v39 + v40 >= v32 )
            {
              v18 = v44;
            }
            else
            {
              v41 = v39 * (__int64)v39;
              if ( v41 + v40 < v32 )
              {
                v32 = v41 + v40;
                v56 = v41 + v40;
                v18 = i;
                v44 = i;
                v54 = i;
              }
              else
              {
                v18 = v44;
              }
            }
          }
        }
        v33 = *(_QWORD *)(i + 16);
        if ( v33 )
          goto LABEL_69;
      }
    }
    else
    {
      v19 = -1;
      v48 = -1;
      v20 = qword_1800C9390;
      v21 = qword_1800C9390 + *(_QWORD *)(v7 + 16);
LABEL_33:
      *(_QWORD *)v51 = v21;
      while ( v21 )
      {
        if ( (*(_BYTE *)(v21 + 24) & 1) != 0 )
        {
          v22 = *(unsigned __int16 *)(v21 + 62);
          v23 = *(unsigned __int16 *)(v21 + 60);
          *(_OWORD *)nNumber = *(_OWORD *)(v21 + 28);
          if ( ((v3 >> 8) & 0x1FF) != 0 )
          {
            *(_QWORD *)v55 = *(_QWORD *)nNumber;
            v24 = v22;
            v25 = (unsigned int)MulDiv(nNumber[0], (v3 >> 8) & 0x1FF, v22);
            v26 = MulDiv(nNumber[1], (v3 >> 8) & 0x1FF, v24);
            v57 = v26;
            v50 = HIDWORD(v25) | v26;
            v27 = nNumber[0];
            v53 = nNumber[1];
            v49 = nNumber[1];
            v52 = nNumber[3];
            nNumber[0] = MulDiv(0, (v3 >> 8) & 0x1FF, v23) + v25;
            nNumber[1] = MulDiv(0, (v3 >> 8) & 0x1FF, v23) + v57;
            nNumber[2] = MulDiv(nNumber[2] - v27, (v3 >> 8) & 0x1FF, v23) + nNumber[0];
            nNumber[3] = MulDiv(nNumber[3] - v49, (v3 >> 8) & 0x1FF, v23) + nNumber[1];
            v20 = qword_1800C9390;
            v21 = *(_QWORD *)v51;
            v3 = v45;
            v19 = v48;
            v18 = v44;
          }
          if ( v5 < nNumber[0] )
            v28 = nNumber[0] - v5;
          else
            v28 = v5 >= nNumber[2] ? v5 - nNumber[2] + 1 : 0;
          if ( v28 < v19 )
          {
            if ( (int)v6 < nNumber[1] )
            {
              v29 = nNumber[1] - v6;
            }
            else if ( (int)v6 >= nNumber[3] )
            {
              v29 = v6 - nNumber[3] + 1;
            }
            else
            {
              if ( !v28 )
                return (struct tagMONITOR *)v21;
              v29 = 0;
            }
            v30 = v28 * v28;
            if ( v30 < v19 )
            {
              if ( v30 + v29 >= v19 )
              {
                v18 = v44;
              }
              else if ( v29 * v29 + v30 >= v19 )
              {
                v18 = v44;
              }
              else
              {
                v19 = v29 * v29 + v30;
                v48 = v19;
                v18 = v21;
                v44 = v21;
                v54 = v21;
              }
            }
            else
            {
              v18 = v44;
            }
          }
        }
        v31 = *(_QWORD *)(v21 + 16);
        if ( v31 )
        {
          v21 = v31 + v20;
          goto LABEL_33;
        }
        v21 = 0;
        *(_QWORD *)v51 = 0;
      }
    }
    return (struct tagMONITOR *)v18;
  }
  else
  {
    if ( a2 > 1 )
      return 0;
    v8 = qword_1800C9390;
    v9 = qword_1800C9390 + *(_QWORD *)(v7 + 16);
LABEL_11:
    v46 = v9;
    while ( v9 )
    {
      if ( (*(_BYTE *)(v9 + 24) & 1) != 0 )
      {
        v10 = *(unsigned __int16 *)(v9 + 62);
        v11 = *(unsigned __int16 *)(v9 + 60);
        *(_OWORD *)nNumber = *(_OWORD *)(v9 + 28);
        if ( ((v3 >> 8) & 0x1FF) != 0 )
        {
          *(_QWORD *)v51 = *(_QWORD *)nNumber;
          v12 = v10;
          v13 = (unsigned int)MulDiv(nNumber[0], (v3 >> 8) & 0x1FF, v10);
          *(_QWORD *)v55 = (unsigned int)MulDiv(nNumber[1], (v3 >> 8) & 0x1FF, v12);
          v57 = v13 | (*(_QWORD *)v55 << 32);
          v14 = nNumber[0];
          v50 = nNumber[1];
          v52 = nNumber[1];
          v49 = nNumber[3];
          nNumber[0] = MulDiv(0, (v3 >> 8) & 0x1FF, v11) + v13;
          nNumber[1] = MulDiv(0, (v3 >> 8) & 0x1FF, v11) + v55[0];
          nNumber[2] = MulDiv(nNumber[2] - v14, (v3 >> 8) & 0x1FF, v11) + nNumber[0];
          nNumber[3] = MulDiv(nNumber[3] - v52, (v3 >> 8) & 0x1FF, v11) + nNumber[1];
          v8 = qword_1800C9390;
          v3 = v45;
          v9 = v46;
        }
        if ( v5 < nNumber[2] && (int)v6 < nNumber[3] && v5 >= nNumber[0] && (int)v6 >= nNumber[1] )
          return (struct tagMONITOR *)v9;
      }
      v15 = *(_QWORD *)(v9 + 16);
      if ( v15 )
      {
        v9 = v15 + v8;
        goto LABEL_11;
      }
      v9 = 0;
      v46 = 0;
    }
    if ( a2 != 1 )
      return 0;
    return GetPrimaryMonitor();
  }
}

```

## disassembly

```asm
0x180014310  mov     [rsp+arg_8], edx
0x180014314  push    rbx
0x180014315  push    rsi
0x180014316  push    rdi
0x180014317  push    r12
0x180014319  push    r13
0x18001431b  push    r14
0x18001431d  push    r15
0x18001431f  sub     rsp, 0E0h
0x180014326  mov     rax, cs:__security_cookie
0x18001432d  xor     rax, rsp
0x180014330  mov     [rsp+118h+var_48], rax
0x180014338  mov     r15d, r8d
0x18001433b  mov     [rsp+118h+var_EC], r8d
0x180014340  mov     ebx, edx
0x180014342  mov     rdi, rcx
0x180014345  mov     rsi, rcx
0x180014348  shr     rsi, 20h
0x18001434c  mov     r14, cs:qword_1800C9388
0x180014353  cmp     dword ptr [r14], 1
0x180014357  jz      loc_1800145B2
0x18001435d  test    r8d, r8d
0x180014360  jnz     short loc_1800143B9
0x180014362  cmp     cs:gfServerProcess, r8d
0x180014369  jnz     loc_180014A35
0x18001436f  mov     rax, gs:30h
0x180014378  add     rax, 800h
0x18001437e  jz      loc_180014A21
0x180014384  mov     rax, gs:30h
0x18001438d  mov     r12d, 12h
0x180014393  cmp     dword ptr [rax+8E8h], 0
0x18001439a  jnz     loc_1800148A2
0x1800143a0  mov     r15d, cs:gDefaultDpiContext
0x1800143a7  mov     [rsp+118h+var_EC], r15d
0x1800143ac  mov     eax, r15d
0x1800143af  and     al, 0Fh
0x1800143b1  cmp     al, 2
0x1800143b3  jnz     loc_1800148B7
0x1800143b9  cmp     ebx, 2
0x1800143bc  jz      loc_1800145F0
0x1800143c2  test    ebx, ebx
0x1800143c4  jz      short loc_1800143CF
0x1800143c6  cmp     ebx, 1
0x1800143c9  jnz     loc_1800145AE
0x1800143cf  mov     rcx, [r14+10h]
0x1800143d3  mov     r9, cs:qword_1800C9390
0x1800143da  add     rcx, r9
0x1800143dd  xor     eax, eax
0x1800143df  mov     edx, 1FFh
0x1800143e4  mov     [rsp+118h+var_E8], rcx
0x1800143e9  test    rcx, rcx
0x1800143ec  jz      loc_180014596
0x1800143f2  test    byte ptr [rcx+18h], 1
0x1800143f6  jz      loc_180014570
0x1800143fc  mov     r8d, r15d
0x1800143ff  shr     r8d, 8
0x180014403  and     r8w, dx
0x180014407  mov     [rsp+118h+var_F0], r8d
0x18001440c  movzx   r10d, word ptr [rcx+3Eh]
0x180014411  movzx   r13d, word ptr [rcx+3Ch]
0x180014416  movups  xmm0, xmmword ptr [rcx+1Ch]
0x18001441a  movups  xmmword ptr [rsp+118h+nNumber], xmm0
0x18001441f  jz      loc_180014558
0x180014425  mov     rcx, qword ptr [rsp+118h+nNumber]; nNumber
0x18001442a  mov     qword ptr [rsp+118h+var_C0], rcx
0x18001442f  mov     ebx, r10d
0x180014432  movzx   r14d, r8w
0x180014436  mov     r8d, r10d; nDenominator
0x180014439  mov     edx, r14d; nNumerator
0x18001443c  call    cs:__imp_MulDiv
0x180014442  mov     r12d, eax
0x180014445  mov     dword ptr [rsp+118h+var_F8], r12d
0x18001444a  mov     r8d, ebx; nDenominator
0x18001444d  mov     edx, r14d; nNumerator
0x180014450  mov     ecx, [rsp+118h+var_C0+4]; nNumber
0x180014454  call    cs:__imp_MulDiv
0x18001445a  mov     eax, eax
0x18001445c  mov     qword ptr [rsp+118h+var_60], rax
0x180014464  mov     dword ptr [rsp+118h+var_F8+4], eax
0x180014468  mov     edx, eax
0x18001446a  shl     rdx, 20h
0x18001446e  or      rdx, r12
0x180014471  mov     [rsp+118h+var_50], rdx
0x180014479  mov     rbx, qword ptr [rsp+118h+nNumber]
0x18001447e  mov     [rsp+118h+var_C8], rbx
0x180014483  mov     r14, rbx
0x180014486  shr     r14, 20h
0x18001448a  lea     rax, [rsp+118h+nNumber]
0x18001448f  mov     [rsp+118h+var_F8], rax
0x180014494  mov     eax, [rsp+118h+nNumber+4]
0x180014498  mov     [rsp+118h+var_B8], eax
0x18001449c  mov     r15d, [rsp+118h+nNumber+8]
0x1800144a1  mov     eax, [rsp+118h+nNumber+0Ch]
0x1800144a5  mov     dword ptr [rsp+118h+var_C8], eax
0x1800144a9  mov     r8d, r13d; nDenominator
0x1800144ac  mov     eax, [rsp+118h+var_F0]
0x1800144b0  movzx   edx, ax; nNumerator
0x1800144b3  xor     ecx, ecx; nNumber
0x1800144b5  call    cs:__imp_MulDiv
0x1800144bb  lea     ecx, [rax+r12]
0x1800144bf  mov     rax, [rsp+118h+var_F8]
0x1800144c4  mov     [rax], ecx
0x1800144c6  mov     ecx, [rsp+118h+var_B8]
0x1800144ca  sub     ecx, r14d; nNumber
0x1800144cd  mov     r8d, r13d; nDenominator
0x1800144d0  mov     edx, [rsp+118h+var_F0]
0x1800144d4  movzx   edx, dx; nNumerator
0x1800144d7  call    cs:__imp_MulDiv
0x1800144dd  mov     rdx, qword ptr [rsp+118h+var_60]
0x1800144e5  add     edx, eax
0x1800144e7  mov     rax, [rsp+118h+var_F8]
0x1800144ec  mov     [rax+4], edx
0x1800144ef  mov     r14, [rsp+118h+var_F8]
0x1800144f4  sub     r15d, ebx
0x1800144f7  mov     r8d, r13d; nDenominator
0x1800144fa  mov     eax, [rsp+118h+var_F0]
0x1800144fe  movzx   ebx, ax
0x180014501  mov     edx, ebx; nNumerator
0x180014503  mov     ecx, r15d; nNumber
0x180014506  call    cs:__imp_MulDiv
0x18001450c  mov     r10d, [r14]
0x18001450f  add     r10d, eax
0x180014512  mov     rax, [rsp+118h+var_F8]
0x180014517  mov     [rax+8], r10d
0x18001451b  mov     ecx, dword ptr [rsp+118h+var_C8]
0x18001451f  sub     ecx, [rsp+118h+var_B8]; nNumber
0x180014523  mov     r8d, r13d; nDenominator
0x180014526  mov     edx, ebx; nNumerator
0x180014528  call    cs:__imp_MulDiv
0x18001452e  mov     rcx, [rsp+118h+var_F8]
0x180014533  mov     ecx, [rcx+4]
0x180014536  add     ecx, eax
0x180014538  mov     rax, [rsp+118h+var_F8]
0x18001453d  mov     [rax+0Ch], ecx
0x180014540  mov     r9, cs:qword_1800C9390
0x180014547  mov     r15d, [rsp+118h+var_EC]
0x18001454c  xor     eax, eax
0x18001454e  mov     rcx, [rsp+118h+var_E8]
0x180014553  mov     edx, 1FFh
0x180014558  cmp     edi, [rsp+118h+nNumber+8]
0x18001455c  jl      short loc_180014572
0x18001455e  mov     r8, [rcx+10h]
0x180014562  test    r8, r8
0x180014565  jz      short loc_180014589
0x180014567  lea     rcx, [r8+r9]
0x18001456b  jmp     loc_1800143E4
0x180014570  jmp     short loc_18001455E
0x180014572  cmp     esi, [rsp+118h+nNumber+0Ch]
0x180014576  jge     short loc_18001455E
0x180014578  cmp     edi, [rsp+118h+nNumber]
0x18001457c  jl      short loc_18001455E
0x18001457e  cmp     esi, [rsp+118h+nNumber+4]
0x180014582  jl      short loc_18001455E
0x180014584  mov     rax, rcx
0x180014587  jmp     short loc_1800145CD
0x180014589  mov     rcx, rax
0x18001458c  mov     [rsp+118h+var_E8], rax
0x180014591  jmp     loc_1800143E9
0x180014596  mov     ebx, [rsp+118h+arg_8]
0x18001459d  jmp     short loc_1800145A6
0x18001459f  mov     ebx, [rsp+118h+arg_8]
0x1800145a6  test    ebx, ebx
0x1800145a8  jnz     loc_180014A0E
0x1800145ae  xor     eax, eax
0x1800145b0  jmp     short loc_1800145CD
0x1800145b2  test    ebx, ebx
0x1800145b4  jz      loc_18001435D
0x1800145ba  mov     rcx, [r14+8]
0x1800145be  test    rcx, rcx
0x1800145c1  jz      short loc_1800145AE
0x1800145c3  mov     rax, cs:qword_1800C9390
0x1800145ca  add     rax, rcx
0x1800145cd  mov     rcx, [rsp+118h+var_48]
0x1800145d5  xor     rcx, rsp; StackCookie
0x1800145d8  call    __security_check_cookie
0x1800145dd  add     rsp, 0E0h
0x1800145e4  pop     r15
0x1800145e6  pop     r14
0x1800145e8  pop     r13
0x1800145ea  pop     r12
0x1800145ec  pop     rdi
0x1800145ed  pop     rsi
0x1800145ee  pop     rbx
0x1800145ef  retn
0x1800145f0  xor     ebx, ebx
0x1800145f2  mov     r9d, ebx
0x1800145f5  mov     [rsp+118h+var_F8], rbx
0x1800145fa  lea     eax, [rdi+8000h]
0x180014600  cmp     eax, 0FFFFh
0x180014605  ja      loc_1800148CC
0x18001460b  lea     eax, [rsi+8000h]
0x180014611  cmp     eax, 0FFFFh
0x180014616  ja      loc_1800148CC
0x18001461c  mov     [rsp+118h+var_D0], ebx
0x180014620  mov     r8d, 0FFFFFFFFh
0x180014626  mov     [rsp+118h+var_D0], r8d
0x18001462b  mov     rdx, [r14+10h]
0x18001462f  mov     r10, cs:qword_1800C9390
0x180014636  add     rdx, r10
0x180014639  mov     ecx, 1FFh
0x18001463e  mov     qword ptr [rsp+118h+var_C0], rdx
0x180014643  test    rdx, rdx
0x180014646  jz      loc_18001488D
0x18001464c  test    byte ptr [rdx+18h], 1
0x180014650  jz      loc_180014869
0x180014656  mov     eax, r15d
0x180014659  shr     eax, 8
0x18001465c  and     ax, cx
0x18001465f  mov     [rsp+118h+var_F0], eax
0x180014663  movzx   r11d, word ptr [rdx+3Eh]
0x180014668  movzx   r13d, word ptr [rdx+3Ch]
0x18001466d  movups  xmm0, xmmword ptr [rdx+1Ch]
0x180014671  movups  xmmword ptr [rsp+118h+nNumber], xmm0
0x180014676  jz      loc_1800147B7
0x18001467c  mov     rcx, qword ptr [rsp+118h+nNumber]; nNumber
0x180014681  mov     qword ptr [rsp+118h+var_60], rcx
0x180014689  mov     ebx, r11d
0x18001468c  movzx   r14d, ax
0x180014690  mov     r8d, r11d; nDenominator
0x180014693  mov     edx, r14d; nNumerator
0x180014696  call    cs:__imp_MulDiv
0x18001469c  mov     r12d, eax
0x18001469f  mov     dword ptr [rsp+118h+var_E8], r12d
0x1800146a4  mov     r8d, ebx; nDenominator
0x1800146a7  mov     edx, r14d; nNumerator
0x1800146aa  mov     ecx, [rsp+118h+var_60+4]; nNumber
0x1800146b1  call    cs:__imp_MulDiv
0x1800146b7  mov     eax, eax
0x1800146b9  mov     [rsp+118h+var_50], rax
0x1800146c1  mov     dword ptr [rsp+118h+var_E8+4], eax
0x1800146c5  mov     edx, eax
0x1800146c7  shl     rdx, 20h
0x1800146cb  or      rdx, r12
0x1800146ce  mov     [rsp+118h+var_C8], rdx
0x1800146d3  mov     rbx, qword ptr [rsp+118h+nNumber]
0x1800146d8  mov     qword ptr [rsp+118h+var_B8], rbx
0x1800146dd  mov     r14, rbx
0x1800146e0  shr     r14, 20h
0x1800146e4  lea     rax, [rsp+118h+nNumber]
0x1800146e9  mov     [rsp+118h+var_E8], rax
0x1800146ee  mov     eax, [rsp+118h+nNumber+4]
0x1800146f2  mov     dword ptr [rsp+118h+var_C8], eax
0x1800146f6  mov     r15d, [rsp+118h+nNumber+8]
0x1800146fb  mov     eax, [rsp+118h+nNumber+0Ch]
0x1800146ff  mov     [rsp+118h+var_B8], eax
0x180014703  mov     r8d, r13d; nDenominator
0x180014706  mov     eax, [rsp+118h+var_F0]
0x18001470a  movzx   edx, ax; nNumerator
0x18001470d  xor     ecx, ecx; nNumber
0x18001470f  call    cs:__imp_MulDiv
0x180014715  lea     ecx, [rax+r12]
0x180014719  mov     rax, [rsp+118h+var_E8]
0x18001471e  mov     [rax], ecx
0x180014720  mov     ecx, dword ptr [rsp+118h+var_C8]
0x180014724  sub     ecx, r14d; nNumber
0x180014727  mov     r8d, r13d; nDenominator
0x18001472a  mov     edx, [rsp+118h+var_F0]
0x18001472e  movzx   edx, dx; nNumerator
0x180014731  call    cs:__imp_MulDiv
0x180014737  mov     rdx, [rsp+118h+var_50]
0x18001473f  add     edx, eax
0x180014741  mov     rax, [rsp+118h+var_E8]
0x180014746  mov     [rax+4], edx
0x180014749  mov     r14, [rsp+118h+var_E8]
0x18001474e  sub     r15d, ebx
0x180014751  mov     r8d, r13d; nDenominator
0x180014754  mov     eax, [rsp+118h+var_F0]
0x180014758  movzx   ebx, ax
0x18001475b  mov     edx, ebx; nNumerator
0x18001475d  mov     ecx, r15d; nNumber
0x180014760  call    cs:__imp_MulDiv
0x180014766  mov     r10d, [r14]
0x180014769  add     r10d, eax
0x18001476c  mov     rax, [rsp+118h+var_E8]
0x180014771  mov     [rax+8], r10d
0x180014775  mov     ecx, [rsp+118h+var_B8]
0x180014779  sub     ecx, dword ptr [rsp+118h+var_C8]; nNumber
0x18001477d  mov     r8d, r13d; nDenominator
0x180014780  mov     edx, ebx; nNumerator
0x180014782  call    cs:__imp_MulDiv
0x180014788  mov     rcx, [rsp+118h+var_E8]
0x18001478d  mov     ecx, [rcx+4]
0x180014790  add     ecx, eax
0x180014792  mov     rax, [rsp+118h+var_E8]
0x180014797  mov     [rax+0Ch], ecx
0x18001479a  mov     r10, cs:qword_1800C9390
0x1800147a1  mov     rdx, qword ptr [rsp+118h+var_C0]
0x1800147a6  mov     r15d, [rsp+118h+var_EC]
0x1800147ab  xor     ebx, ebx
0x1800147ad  mov     r8d, [rsp+118h+var_D0]
0x1800147b2  mov     r9, [rsp+118h+var_F8]
0x1800147b7  mov     ecx, [rsp+118h+nNumber]
0x1800147bb  cmp     edi, ecx
0x1800147bd  jl      short loc_18001483E
0x1800147bf  mov     eax, [rsp+118h+nNumber+8]
0x1800147c3  cmp     edi, eax
0x1800147c5  jge     short loc_180014842
0x1800147c7  mov     ecx, ebx
0x1800147c9  cmp     ecx, r8d
0x1800147cc  jnb     short loc_18001484D
  ... truncated ...
```
