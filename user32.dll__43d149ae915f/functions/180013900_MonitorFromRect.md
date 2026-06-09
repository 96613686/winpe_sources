# _MonitorFromRect

- ea: `0x180013900`
- end: `0x1800142c3`
- name: `_MonitorFromRect`
- size: `2499`
- prototype: ``
- caller_count: `5`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180008ab0`
- `0x1800134c0`
- `0x180013500`
- `0x180013670`
- `0x18002b854`

## callees

- `0x1800089f0`
- `0x180013900`
- `0x180014310`
- `0x180014c10`
- `0x180014f50`
- `0x180015090`
- `0x180096e00`

## import_xrefs

- `win32u!NtUserGetThreadState` at `0x1800142a1`
- `win32u!NtUserGetThreadState` at `0x1800142a1`
- `ntdll!RtlSetLastWin32Error` at `0x1800974cc`
- `ntdll!RtlSetLastWin32Error` at `0x180097515`
- `ntdll!RtlSetLastWin32Error` at `0x18009755e`
- `ntdll!RtlSetLastWin32Error` at `0x1800974cc`
- `ntdll!RtlSetLastWin32Error` at `0x180097515`
- `ntdll!RtlSetLastWin32Error` at `0x18009755e`
- `ntdll!RtlNtStatusToDosError` at `0x1800974ba`
- `ntdll!RtlNtStatusToDosError` at `0x180097503`
- `ntdll!RtlNtStatusToDosError` at `0x18009754c`
- `ntdll!RtlNtStatusToDosError` at `0x1800974ba`
- `ntdll!RtlNtStatusToDosError` at `0x180097503`
- `ntdll!RtlNtStatusToDosError` at `0x18009754c`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x180013a80`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x180013a9d`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x180013afa`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x180013b1e`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x180013b3f`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x180013b64`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x180013e48`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x180013e5a`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x180013e83`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x180013e9b`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x180013ebd`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x180013ee2`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x180013a80`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x180013a9d`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x180013afa`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x180013b1e`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x180013b3f`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x180013b64`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x180013e48`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x180013e5a`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x180013e83`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x180013e9b`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x180013ebd`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x180013ee2`

## pseudocode

```c
struct tagMONITOR *__fastcall MonitorFromRect(int *a1, __int64 a2, unsigned int a3)
{
  unsigned int v3; // edi
  int *v4; // rbx
  __int64 v5; // r13
  int *v6; // r14
  int *v7; // rcx
  int *v8; // r15
  unsigned int v9; // r8d
  unsigned __int16 v10; // di
  int v11; // r9d
  int v12; // r10d
  int v13; // r11d
  int v14; // edx
  int v15; // r11d
  __int64 v16; // rdx
  int v17; // eax
  int v18; // r15d
  int v19; // ebx
  int v20; // r14d
  int v21; // r12d
  int v22; // ebx
  int v23; // edi
  int v24; // r13d
  int v25; // esi
  int v26; // r14d
  int v27; // r10d
  int v28; // eax
  int v29; // r9d
  int v30; // ecx
  __int64 v31; // r8
  int v32; // ecx
  __int64 v33; // rcx
  unsigned int v35; // edi
  int *v36; // r14
  int *v37; // r15
  __int64 v38; // r12
  __int64 v39; // rcx
  bool v40; // zf
  __int64 v41; // rax
  int v42; // esi
  int v43; // ebx
  int v44; // r13d
  int v45; // edi
  int v46; // ebx
  __int64 v47; // r12
  int v48; // eax
  __int64 v49; // rcx
  __int64 v50; // rdx
  __int64 v51; // rcx
  __int64 v52; // rcx
  __int64 i; // r13
  int *MonitorRectForDpiContext; // r9
  int v55; // ecx
  int v56; // eax
  unsigned int v57; // ecx
  int v58; // edx
  int v59; // edx
  int v60; // edx
  unsigned int v61; // ecx
  int v62; // eax
  __int64 v63; // rcx
  __int64 j; // r13
  int *v65; // r9
  int v66; // ecx
  int v67; // eax
  int v68; // ecx
  __int64 v69; // rdx
  int v70; // ecx
  int v71; // eax
  int v72; // ecx
  int v73; // ecx
  unsigned __int64 v74; // rdx
  __int64 v75; // r9
  int nNumber[4]; // [rsp+38h] [rbp-150h] BYREF
  unsigned int v77; // [rsp+48h] [rbp-140h]
  unsigned int v78; // [rsp+50h] [rbp-138h]
  int v79; // [rsp+58h] [rbp-130h]
  int v80; // [rsp+5Ch] [rbp-12Ch]
  __int64 v81; // [rsp+60h] [rbp-128h]
  int v82; // [rsp+68h] [rbp-120h]
  unsigned int v83; // [rsp+6Ch] [rbp-11Ch]
  int *v84; // [rsp+70h] [rbp-118h]
  int v85; // [rsp+78h] [rbp-110h]
  int v86; // [rsp+7Ch] [rbp-10Ch]
  int v87; // [rsp+80h] [rbp-108h]
  int v88; // [rsp+88h] [rbp-100h]
  int v89; // [rsp+8Ch] [rbp-FCh]
  __int64 v90; // [rsp+90h] [rbp-F8h]
  _OWORD v91[4]; // [rsp+98h] [rbp-F0h] BYREF
  unsigned __int64 v92; // [rsp+E0h] [rbp-A8h]
  int *v93; // [rsp+E8h] [rbp-A0h]
  int v94[2]; // [rsp+F0h] [rbp-98h]
  int *v95; // [rsp+108h] [rbp-80h]
  __int64 v96; // [rsp+110h] [rbp-78h]
  __int64 v97; // [rsp+118h] [rbp-70h]
  __int64 v98; // [rsp+120h] [rbp-68h]
  int *v99; // [rsp+128h] [rbp-60h]
  int *v100; // [rsp+130h] [rbp-58h]
  int *v101; // [rsp+138h] [rbp-50h]
  int *v102; // [rsp+140h] [rbp-48h]
  int v103; // [rsp+198h] [rbp+10h]

  v103 = a2;
  v3 = a3;
  v77 = a3;
  v4 = a1;
  v95 = a1;
  v100 = a1;
  v78 = a3;
  v91[0] = 0;
  v5 = qword_1800C9388;
  v97 = qword_1800C9388;
  v98 = qword_1800C9388;
  if ( *(_DWORD *)qword_1800C9388 != 1 || !(_DWORD)a2 )
  {
    v6 = a1 + 2;
    v93 = a1 + 2;
    if ( *a1 >= a1[2] )
      return (struct tagMONITOR *)MonitorFromPoint(*(_QWORD *)v4, a2);
    v7 = a1 + 3;
    v84 = v7;
    v8 = v4 + 1;
    *(_QWORD *)v94 = v4 + 1;
    if ( v4[1] >= *v7 )
      return (struct tagMONITOR *)MonitorFromPoint(*(_QWORD *)v4, a2);
    v101 = v6;
    v99 = v7;
    v102 = v4 + 1;
    v96 = 0;
    v80 = 0;
    if ( !a3 )
    {
      if ( *(_DWORD *)&gfServerProcess || NtCurrentTeb() == (struct _TEB *)-2048LL && !NtUserGetThreadState(14) )
        v3 = 18;
      else
        v3 = LODWORD(NtCurrentTeb()->Win32ClientInfo[29])
           ? LODWORD(NtCurrentTeb()->Win32ClientInfo[29])
           : gDefaultDpiContext;
      v77 = v3;
      v78 = v3;
      if ( (v3 & 0xF) != 2 )
      {
        if ( !(unsigned int)IsThreadDesktopComposited() )
          v3 = 18;
        v77 = v3;
        v78 = v3;
      }
    }
    v9 = v3 >> 8;
    LOWORD(v9) = (v3 >> 8) & 0x1FF;
    v88 = v9;
    v10 = v9;
    v79 = (unsigned __int16)v9;
    if ( (_WORD)v9 )
    {
      if ( *(_DWORD *)qword_1800C9388 == 1 )
      {
        v50 = *(_QWORD *)(qword_1800C9388 + 8);
        if ( v50 )
          v51 = v50 + qword_1800C9390;
        else
          v51 = 0;
        CalculateLogicalMonitorRect(
          (unsigned int)nNumber,
          v51 + 28,
          *(unsigned __int16 *)(v51 + 60),
          (unsigned __int16)v9,
          *(_WORD *)(v51 + 62));
        v11 = nNumber[0];
        v12 = nNumber[1];
        v13 = nNumber[2];
        v14 = nNumber[3];
      }
      else
      {
        v11 = 0;
        v82 = 0;
        v12 = 0;
        v85 = 0;
        v13 = 0;
        v86 = 0;
        v14 = 0;
        v87 = 0;
        v40 = *(_QWORD *)(qword_1800C9388 + 16) + qword_1800C9390 == 0;
        v41 = *(_QWORD *)(qword_1800C9388 + 16) + qword_1800C9390;
        v81 = v41;
        if ( !v40 )
        {
          do
          {
            if ( (*(_BYTE *)(v41 + 24) & 1) != 0 )
            {
              *(_OWORD *)nNumber = *(_OWORD *)(v41 + 28);
              v42 = *(unsigned __int16 *)(v41 + 60);
              v43 = *(unsigned __int16 *)(v41 + 62);
              v44 = (unsigned __int16)v9;
              v45 = MulDiv(nNumber[0], (unsigned __int16)v9, v43);
              v46 = MulDiv(nNumber[1], v44, v43);
              v47 = *(_QWORD *)nNumber;
              nNumber[0] = MulDiv(0, v44, v42) + v45;
              nNumber[1] = MulDiv(0, v44, v42) + v46;
              nNumber[2] = MulDiv(nNumber[2] - v47, v44, v42) + nNumber[0];
              nNumber[3] = MulDiv(nNumber[3] - HIDWORD(v47), v44, v42) + nNumber[1];
              v48 = nNumber[0];
              if ( v82 < nNumber[0] )
                v48 = v82;
              v11 = v48;
              v82 = v48;
              v12 = v85;
              if ( v85 >= nNumber[1] )
                v12 = nNumber[1];
              v85 = v12;
              v13 = v86;
              if ( v86 <= nNumber[2] )
                v13 = nNumber[2];
              v86 = v13;
              v14 = v87;
              if ( v87 > nNumber[3] )
              {
                v82 = v48;
              }
              else
              {
                v14 = nNumber[3];
                v87 = nNumber[3];
              }
              v41 = v81;
              LOWORD(v9) = v88;
            }
            v49 = *(_QWORD *)(v41 + 16);
            if ( v49 )
              v41 = v49 + qword_1800C9390;
            else
              v41 = 0;
            v81 = v41;
          }
          while ( v41 );
          v4 = v95;
          v6 = v93;
          v8 = *(int **)v94;
          v5 = v97;
          v10 = v79;
        }
      }
    }
    else
    {
      v11 = *(_DWORD *)(qword_1800C9388 + 24);
      v12 = *(_DWORD *)(qword_1800C9388 + 28);
      v13 = *(_DWORD *)(qword_1800C9388 + 32);
      v14 = *(_DWORD *)(qword_1800C9388 + 36);
    }
    if ( *v4 <= v11 && *v8 <= v12 && *v6 >= v13 && *v84 >= v14 )
      return GetPrimaryMonitor();
    v15 = 0;
    v80 = 0;
    v16 = *(_QWORD *)(v5 + 16) + qword_1800C9390;
    while ( 1 )
    {
      v81 = v16;
      if ( !v16 )
        break;
      if ( (*(_BYTE *)(v16 + 24) & 1) != 0 )
      {
        v17 = *(unsigned __int16 *)(v16 + 62);
        v18 = *(unsigned __int16 *)(v16 + 60);
        *(_OWORD *)nNumber = *(_OWORD *)(v16 + 28);
        if ( v10 )
        {
          *(_QWORD *)v94 = *(_QWORD *)nNumber;
          v19 = v17;
          v20 = MulDiv(nNumber[0], v10, v17);
          LODWORD(v93) = v20;
          v21 = MulDiv(v94[1], v10, v19);
          HIDWORD(v93) = v21;
          v22 = nNumber[0];
          v89 = nNumber[1];
          v23 = nNumber[1];
          v24 = nNumber[1];
          v25 = nNumber[2];
          v88 = nNumber[3];
          nNumber[0] = MulDiv(0, (unsigned __int16)v79, v18) + v20;
          v26 = (unsigned __int16)v79;
          nNumber[1] = MulDiv(v24 - v23, (unsigned __int16)v79, v18) + v21;
          nNumber[2] = MulDiv(v25 - v22, v26, v18) + nNumber[0];
          nNumber[3] = MulDiv(v88 - v24, v26, v18) + nNumber[1];
          v16 = v81;
          v4 = v95;
          v15 = v80;
        }
        if ( v4 )
        {
          v27 = *v4;
          if ( *v4 <= nNumber[0] )
            v27 = nNumber[0];
          LODWORD(v91[0]) = v27;
          v28 = v4[2];
          if ( v28 >= nNumber[2] )
            v28 = nNumber[2];
          DWORD2(v91[0]) = v28;
          if ( v27 >= v28 )
            goto LABEL_33;
          v29 = v4[1];
          if ( v29 <= nNumber[1] )
            v29 = nNumber[1];
          DWORD1(v91[0]) = v29;
          v30 = *v84;
          if ( *v84 >= nNumber[3] )
            v30 = nNumber[3];
          HIDWORD(v91[0]) = v30;
          if ( v29 >= v30 )
          {
LABEL_33:
            v91[0] = 0;
          }
          else
          {
            v31 = *(_QWORD *)&v91[0] - *(_QWORD *)v4;
            if ( *(_QWORD *)&v91[0] == *(_QWORD *)v4 )
              v31 = *((_QWORD *)&v91[0] + 1) - *((_QWORD *)v4 + 1);
            if ( !v31 )
              return (struct tagMONITOR *)v16;
            v32 = (v28 - v27) * (v30 - v29);
            if ( v32 > v15 )
            {
              v15 = v32;
              v80 = v32;
              v96 = v16;
              v90 = v16;
            }
          }
        }
      }
      v33 = *(_QWORD *)(v16 + 16);
      if ( v33 )
        v16 = v33 + qword_1800C9390;
      else
        v16 = 0;
      v10 = v79;
    }
    v35 = v77;
    v36 = v4 + 2;
    v37 = v4 + 1;
    v38 = v96;
    if ( v15 > 0 )
      return (struct tagMONITOR *)v38;
    if ( v103 != 2 )
    {
      if ( !v103 || v103 != 1 )
        return 0;
      return GetPrimaryMonitor();
    }
    if ( (unsigned int)(*v4 + 0x8000) <= 0xFFFF
      && (unsigned int)(*v37 + 0x8000) <= 0xFFFF
      && (unsigned int)(*v36 + 0x8000) <= 0xFFFF
      && (unsigned int)(*v84 + 0x8000) <= 0xFFFF )
    {
      v83 = -1;
      v52 = *(_QWORD *)(v97 + 16);
LABEL_81:
      for ( i = v52 + qword_1800C9390; ; i = 0 )
      {
        if ( !i )
          return (struct tagMONITOR *)v38;
        if ( (*(_BYTE *)(i + 24) & 1) != 0 )
        {
          MonitorRectForDpiContext = (int *)GetMonitorRectForDpiContext(v91, i, v35);
          v55 = *MonitorRectForDpiContext;
          v56 = *v36;
          if ( *v36 <= *MonitorRectForDpiContext || (v56 = MonitorRectForDpiContext[2], v55 = *v4, *v4 >= v56) )
            v57 = v55 - v56 + 1;
          else
            v57 = 0;
          if ( v57 < v83 )
            break;
        }
LABEL_94:
        v52 = *(_QWORD *)(i + 16);
        if ( v52 )
          goto LABEL_81;
      }
      v58 = MonitorRectForDpiContext[1];
      if ( *v84 > v58 )
      {
        v62 = MonitorRectForDpiContext[3];
        if ( *v37 < v62 )
        {
          v60 = 0;
          goto LABEL_90;
        }
        v59 = *v37 - v62;
      }
      else
      {
        v59 = v58 - *v84;
      }
      v60 = v59 + 1;
LABEL_90:
      v61 = v57 * v57;
      if ( v61 < v83 && v61 + v60 < v83 && v60 * v60 + v61 < v83 )
      {
        v83 = v60 * v60 + v61;
        v38 = i;
        v90 = i;
      }
      goto LABEL_94;
    }
    v92 = -1;
    v63 = *(_QWORD *)(v97 + 16);
LABEL_112:
    for ( j = v63 + qword_1800C9390; ; j = 0 )
    {
      if ( !j )
        return (struct tagMONITOR *)v38;
      if ( (*(_BYTE *)(j + 24) & 1) != 0 )
      {
        v65 = (int *)GetMonitorRectForDpiContext(v91, j, v35);
        v66 = *v65;
        v67 = *v36;
        if ( *v36 > *v65 && (v67 = v65[2], v66 = *v4, *v4 < v67) )
          v68 = 0;
        else
          v68 = v66 - v67 + 1;
        v69 = v68;
        if ( v68 < v92 )
          break;
      }
LABEL_127:
      v63 = *(_QWORD *)(j + 16);
      if ( v63 )
        goto LABEL_112;
    }
    v70 = v65[1];
    if ( *v84 <= v70 )
    {
      v72 = v70 - *v84;
    }
    else
    {
      v71 = v65[3];
      if ( *v37 < v71 )
      {
        v73 = 0;
        goto LABEL_123;
      }
      v72 = *v37 - v71;
    }
    v73 = v72 + 1;
LABEL_123:
    v74 = v69 * v69;
    if ( v74 < v92 && v73 + v74 < v92 )
    {
      v75 = v73 * (__int64)v73;
      if ( v75 + v74 < v92 )
      {
        v92 = v75 + v74;
        v38 = j;
        v90 = j;
      }
    }
    goto LABEL_127;
  }
  v39 = *(_QWORD *)(qword_1800C9388 + 8);
  if ( v39 )
    return (struct tagMONITOR *)(v39 + qword_1800C9390);
  return 0;
}

```

## disassembly

```asm
0x180013900  mov     [rsp+arg_8], edx
0x180013904  push    rbx
0x180013905  push    rsi
0x180013906  push    rdi
0x180013907  push    r12
0x180013909  push    r13
0x18001390b  push    r14
0x18001390d  push    r15
0x18001390f  sub     rsp, 150h
0x180013916  mov     rax, cs:__security_cookie
0x18001391d  xor     rax, rsp
0x180013920  mov     [rsp+188h+var_40], rax
0x180013928  mov     edi, r8d
0x18001392b  mov     [rsp+188h+var_140], r8d
0x180013930  mov     rbx, rcx
0x180013933  mov     [rsp+188h+var_80], rcx
0x18001393b  mov     [rsp+188h+var_58], rcx
0x180013943  mov     [rsp+188h+var_138], r8d
0x180013948  xorps   xmm0, xmm0
0x18001394b  movups  [rsp+188h+var_F0], xmm0
0x180013953  mov     r13, cs:qword_1800C9388
0x18001395a  mov     [rsp+188h+var_70], r13
0x180013962  mov     [rsp+188h+var_68], r13
0x18001396a  cmp     dword ptr [r13+0], 1
0x18001396f  jz      loc_180013D4D
0x180013975  lea     r14, [rcx+8]
0x180013979  mov     [rsp+188h+var_A0], r14
0x180013981  mov     eax, [r14]
0x180013984  cmp     [rcx], eax
0x180013986  jge     loc_180013D43
0x18001398c  add     rcx, 0Ch
0x180013990  mov     [rsp+188h+var_118], rcx
0x180013995  lea     r15, [rbx+4]
0x180013999  mov     qword ptr [rsp+188h+var_98], r15
0x1800139a1  mov     eax, [rcx]
0x1800139a3  cmp     [r15], eax
0x1800139a6  jge     loc_180013D43
0x1800139ac  mov     [rsp+188h+var_50], r14
0x1800139b4  mov     [rsp+188h+var_60], rcx
0x1800139bc  mov     [rsp+188h+var_48], r15
0x1800139c4  xor     esi, esi
0x1800139c6  mov     [rsp+188h+var_78], rsi
0x1800139ce  mov     [rsp+188h+var_12C], esi
0x1800139d2  test    r8d, r8d
0x1800139d5  jz      loc_180013D6E
0x1800139db  mov     r8d, edi
0x1800139de  shr     r8d, 8
0x1800139e2  mov     eax, 1FFh
0x1800139e7  and     r8w, ax
0x1800139eb  mov     dword ptr [rsp+188h+var_100], r8d
0x1800139f3  movzx   edi, r8w
0x1800139f7  mov     [rsp+188h+var_130], edi
0x1800139fb  mov     rcx, cs:qword_1800C9388
0x180013a02  test    r8w, r8w
0x180013a06  jnz     loc_180013DDC
0x180013a0c  mov     r9d, [rcx+18h]
0x180013a10  mov     r10d, [rcx+1Ch]
0x180013a14  mov     r11d, [rcx+20h]
0x180013a18  mov     edx, [rcx+24h]
0x180013a1b  cmp     [rbx], r9d
0x180013a1e  jle     loc_180013D1D
0x180013a24  mov     r11d, esi
0x180013a27  mov     [rsp+188h+var_12C], esi
0x180013a2b  mov     rdx, cs:qword_1800C9390
0x180013a32  add     rdx, [r13+10h]
0x180013a36  mov     [rsp+188h+var_128], rdx
0x180013a3b  test    rdx, rdx
0x180013a3e  jz      loc_180013C7A
0x180013a44  test    byte ptr [rdx+18h], 1
0x180013a48  jz      loc_180013C73
0x180013a4e  movzx   eax, word ptr [rdx+3Eh]
0x180013a52  movzx   r15d, word ptr [rdx+3Ch]
0x180013a57  movups  xmm0, xmmword ptr [rdx+1Ch]
0x180013a5b  movups  xmmword ptr [rsp+188h+nNumber], xmm0
0x180013a60  test    di, di
0x180013a63  jz      loc_180013B90
0x180013a69  mov     rcx, qword ptr [rsp+188h+nNumber]; nNumber
0x180013a6e  mov     qword ptr [rsp+188h+var_98], rcx
0x180013a76  mov     ebx, eax
0x180013a78  movzx   edi, di
0x180013a7b  mov     r8d, eax; nDenominator
0x180013a7e  mov     edx, edi; nNumerator
0x180013a80  call    cs:__imp_MulDiv
0x180013a86  mov     r14d, eax
0x180013a89  mov     dword ptr [rsp+188h+var_A0], r14d
0x180013a91  mov     r8d, ebx; nDenominator
0x180013a94  mov     edx, edi; nNumerator
0x180013a96  mov     ecx, [rsp+188h+var_98+4]; nNumber
0x180013a9d  call    cs:__imp_MulDiv
0x180013aa3  mov     r12d, eax
0x180013aa6  mov     dword ptr [rsp+188h+var_A0+4], r12d
0x180013aae  mov     edx, eax
0x180013ab0  shl     rdx, 20h
0x180013ab4  or      rdx, r14
0x180013ab7  mov     qword ptr [rsp+188h+var_158], rdx
0x180013abc  mov     rbx, qword ptr [rsp+188h+nNumber]
0x180013ac1  mov     [rsp+188h+var_100], rbx
0x180013ac9  mov     rdi, rbx
0x180013acc  shr     rdi, 20h
0x180013ad0  lea     rax, [rsp+188h+nNumber]
0x180013ad5  mov     qword ptr [rsp+188h+var_158], rax
0x180013ada  mov     r13d, [rsp+188h+nNumber+4]
0x180013adf  mov     esi, [rsp+188h+nNumber+8]
0x180013ae3  mov     eax, [rsp+188h+nNumber+0Ch]
0x180013ae7  mov     dword ptr [rsp+188h+var_100], eax
0x180013aee  mov     r8d, r15d; nDenominator
0x180013af1  mov     eax, [rsp+188h+var_130]
0x180013af5  movzx   edx, ax; nNumerator
0x180013af8  xor     ecx, ecx; nNumber
0x180013afa  call    cs:__imp_MulDiv
0x180013b00  lea     ecx, [rax+r14]
0x180013b04  mov     rax, qword ptr [rsp+188h+var_158]
0x180013b09  mov     [rax], ecx
0x180013b0b  mov     ecx, r13d
0x180013b0e  sub     ecx, edi; nNumber
0x180013b10  mov     r8d, r15d; nDenominator
0x180013b13  mov     eax, [rsp+188h+var_130]
0x180013b17  movzx   r14d, ax
0x180013b1b  mov     edx, r14d; nNumerator
0x180013b1e  call    cs:__imp_MulDiv
0x180013b24  lea     edx, [rax+r12]
0x180013b28  mov     rax, qword ptr [rsp+188h+var_158]
0x180013b2d  mov     [rax+4], edx
0x180013b30  mov     rdi, qword ptr [rsp+188h+var_158]
0x180013b35  sub     esi, ebx
0x180013b37  mov     r8d, r15d; nDenominator
0x180013b3a  mov     edx, r14d; nNumerator
0x180013b3d  mov     ecx, esi; nNumber
0x180013b3f  call    cs:__imp_MulDiv
0x180013b45  mov     r9d, [rdi]
0x180013b48  add     r9d, eax
0x180013b4b  mov     rax, qword ptr [rsp+188h+var_158]
0x180013b50  mov     [rax+8], r9d
0x180013b54  mov     ecx, dword ptr [rsp+188h+var_100]
0x180013b5b  sub     ecx, r13d; nNumber
0x180013b5e  mov     r8d, r15d; nDenominator
0x180013b61  mov     edx, r14d; nNumerator
0x180013b64  call    cs:__imp_MulDiv
0x180013b6a  mov     rcx, qword ptr [rsp+188h+var_158]
0x180013b6f  mov     ecx, [rcx+4]
0x180013b72  add     ecx, eax
0x180013b74  mov     rax, qword ptr [rsp+188h+var_158]
0x180013b79  mov     [rax+0Ch], ecx
0x180013b7c  mov     rdx, [rsp+188h+var_128]
0x180013b81  mov     rbx, [rsp+188h+var_80]
0x180013b89  mov     r11d, [rsp+188h+var_12C]
0x180013b8e  xor     esi, esi
0x180013b90  test    rbx, rbx
0x180013b93  jz      loc_180013C42
0x180013b99  mov     r8d, [rsp+188h+nNumber+4]
0x180013b9e  mov     edi, [rsp+188h+nNumber+0Ch]
0x180013ba2  mov     r10d, [rbx]
0x180013ba5  cmp     r10d, [rsp+188h+nNumber]
0x180013baa  cmovle  r10d, [rsp+188h+nNumber]
0x180013bb0  mov     dword ptr [rsp+188h+var_F0], r10d
0x180013bb8  mov     eax, [rbx+8]
0x180013bbb  cmp     eax, [rsp+188h+nNumber+8]
0x180013bbf  cmovge  eax, [rsp+188h+nNumber+8]
0x180013bc4  mov     dword ptr [rsp+188h+var_F0+8], eax
0x180013bcb  cmp     r10d, eax
0x180013bce  jge     loc_180013C66
0x180013bd4  mov     r9d, [rbx+4]
0x180013bd8  cmp     r9d, r8d
0x180013bdb  cmovle  r9d, r8d
0x180013bdf  mov     dword ptr [rsp+188h+var_F0+4], r9d
0x180013be7  mov     rcx, [rsp+188h+var_118]
0x180013bec  mov     ecx, [rcx]
0x180013bee  cmp     ecx, edi
0x180013bf0  cmovge  ecx, edi
0x180013bf3  mov     dword ptr [rsp+188h+var_F0+0Ch], ecx
0x180013bfa  cmp     r9d, ecx
0x180013bfd  jge     short loc_180013C66
0x180013bff  mov     r8, qword ptr [rsp+188h+var_F0]
0x180013c07  sub     r8, [rbx]
0x180013c0a  jnz     short loc_180013C18
0x180013c0c  mov     r8, qword ptr [rsp+188h+var_F0+8]
0x180013c14  sub     r8, [rbx+8]
0x180013c18  test    r8, r8
0x180013c1b  jz      short loc_180013C5E
0x180013c1d  sub     ecx, r9d
0x180013c20  sub     eax, r10d
0x180013c23  imul    ecx, eax
0x180013c26  cmp     ecx, r11d
0x180013c29  jle     short loc_180013C42
0x180013c2b  mov     r11d, ecx
0x180013c2e  mov     [rsp+188h+var_12C], ecx
0x180013c32  mov     [rsp+188h+var_78], rdx
0x180013c3a  mov     [rsp+188h+var_F8], rdx
0x180013c42  mov     rcx, [rdx+10h]
0x180013c46  test    rcx, rcx
0x180013c49  jz      short loc_180013C75
0x180013c4b  mov     rdx, cs:qword_1800C9390
0x180013c52  add     rdx, rcx
0x180013c55  mov     edi, [rsp+188h+var_130]
0x180013c59  jmp     loc_180013A36
0x180013c5e  mov     rax, rdx
0x180013c61  jmp     loc_180013CFA
0x180013c66  xorps   xmm0, xmm0
0x180013c69  movups  [rsp+188h+var_F0], xmm0
0x180013c71  jmp     short loc_180013C42
0x180013c73  jmp     short loc_180013C42
0x180013c75  mov     rdx, rsi
0x180013c78  jmp     short loc_180013C55
0x180013c7a  mov     edi, [rsp+188h+var_140]
0x180013c7e  lea     r14, [rbx+8]
0x180013c82  lea     r15, [rbx+4]
0x180013c86  mov     r12, [rsp+188h+var_78]
0x180013c8e  mov     r13, [rsp+188h+var_70]
0x180013c96  mov     rcx, [rsp+188h+var_118]
0x180013c9b  mov     eax, [rsp+188h+arg_8]
0x180013ca2  jmp     short loc_180013CEE
0x180013ca4  xor     r12d, r12d
0x180013ca7  mov     [rsp+188h+var_F8], r12
0x180013caf  xor     esi, esi
0x180013cb1  mov     eax, [rsp+188h+arg_8]
0x180013cb8  mov     r13, [rsp+188h+var_68]
0x180013cc0  mov     rcx, [rsp+188h+var_60]
0x180013cc8  mov     [rsp+188h+var_118], rcx
0x180013ccd  mov     edi, [rsp+188h+var_138]
0x180013cd1  mov     rbx, [rsp+188h+var_58]
0x180013cd9  mov     r14, [rsp+188h+var_50]
0x180013ce1  mov     r15, [rsp+188h+var_48]
0x180013ce9  mov     r11d, [rsp+188h+var_12C]
0x180013cee  test    r11d, r11d
0x180013cf1  jle     loc_180014013
0x180013cf7  mov     rax, r12
0x180013cfa  mov     rcx, [rsp+188h+var_40]
0x180013d02  xor     rcx, rsp; StackCookie
0x180013d05  call    __security_check_cookie
0x180013d0a  add     rsp, 150h
0x180013d11  pop     r15
0x180013d13  pop     r14
0x180013d15  pop     r13
0x180013d17  pop     r12
0x180013d19  pop     rdi
0x180013d1a  pop     rsi
0x180013d1b  pop     rbx
0x180013d1c  retn
0x180013d1d  cmp     [r15], r10d
0x180013d20  jg      loc_180013A24
0x180013d26  cmp     [r14], r11d
0x180013d29  jl      loc_180013A24
0x180013d2f  mov     rax, [rsp+188h+var_118]
0x180013d34  cmp     [rax], edx
0x180013d36  jl      loc_180013A24
0x180013d3c  call    ?GetPrimaryMonitor@@YAPEAUtagMONITOR@@XZ; GetPrimaryMonitor(void)
0x180013d41  jmp     short loc_180013CFA
0x180013d43  mov     rcx, [rbx]
0x180013d46  call    _MonitorFromPoint
0x180013d4b  jmp     short loc_180013CFA
0x180013d4d  test    edx, edx
0x180013d4f  jz      loc_180013975
0x180013d55  mov     rcx, [r13+8]
0x180013d59  test    rcx, rcx
0x180013d5c  jz      loc_18001417D
0x180013d62  mov     rax, cs:qword_1800C9390
0x180013d69  add     rax, rcx
0x180013d6c  jmp     short loc_180013CFA
0x180013d6e  cmp     cs:gfServerProcess, esi
0x180013d74  jnz     loc_180014005
0x180013d7a  mov     rax, gs:30h
0x180013d83  add     rax, 800h
0x180013d89  jz      loc_18001429C
0x180013d8f  mov     rax, gs:30h
0x180013d98  mov     r12d, 12h
0x180013d9e  cmp     [rax+8E8h], esi
0x180013da4  jnz     loc_180014161
0x180013daa  mov     edi, cs:gDefaultDpiContext
0x180013db0  mov     [rsp+188h+var_140], edi
0x180013db4  mov     [rsp+188h+var_138], edi
0x180013db8  mov     eax, edi
0x180013dba  and     al, 0Fh
0x180013dbc  cmp     al, 2
0x180013dbe  jz      loc_1800139DB
0x180013dc4  call    IsThreadDesktopComposited
0x180013dc9  test    eax, eax
0x180013dcb  cmovz   edi, r12d
0x180013dcf  mov     [rsp+188h+var_140], edi
0x180013dd3  mov     [rsp+188h+var_138], edi
0x180013dd7  jmp     loc_1800139DB
0x180013ddc  cmp     dword ptr [rcx], 1
0x180013ddf  jz      loc_180013FB6
0x180013de5  mov     r9d, esi
0x180013de8  mov     [rsp+188h+var_120], esi
0x180013dec  mov     r10d, esi
0x180013def  mov     [rsp+188h+var_110], esi
0x180013df3  mov     r11d, esi
0x180013df6  mov     [rsp+188h+var_10C], esi
0x180013dfa  mov     edx, esi
0x180013dfc  mov     [rsp+188h+var_108], edx
0x180013e03  mov     rax, cs:qword_1800C9390
0x180013e0a  add     rax, [rcx+10h]
0x180013e0e  mov     [rsp+188h+var_128], rax
0x180013e13  jz      loc_180013A1B
0x180013e19  test    byte ptr [rax+18h], 1
0x180013e1d  jz      loc_180013F62
0x180013e23  movups  xmm0, xmmword ptr [rax+1Ch]
0x180013e27  movups  xmmword ptr [rsp+188h+nNumber], xmm0
0x180013e2c  movzx   esi, word ptr [rax+3Ch]
0x180013e30  mov     rcx, qword ptr [rsp+188h+nNumber]; nNumber
  ... truncated ...
```
