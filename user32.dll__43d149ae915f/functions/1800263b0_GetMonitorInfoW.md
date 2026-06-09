# GetMonitorInfoW

- ea: `0x1800263b0`
- end: `0x1800268fd`
- name: `GetMonitorInfoW`
- size: `1357`
- prototype: `BOOL __stdcall(HMONITOR hMonitor, LPMONITORINFO lpmi)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800263b0`

## import_xrefs

- `win32u!NtUserGetHDevName` at `0x18002646a`
- `win32u!NtUserGetHDevName` at `0x18002646a`
- `win32u!NtUserGetThreadState` at `0x180026873`
- `win32u!NtUserGetThreadState` at `0x180026891`
- `win32u!NtUserGetThreadState` at `0x1800268d0`
- `win32u!NtUserGetThreadState` at `0x1800268e9`
- `win32u!NtUserGetThreadState` at `0x180026873`
- `win32u!NtUserGetThreadState` at `0x180026891`
- `win32u!NtUserGetThreadState` at `0x1800268d0`
- `win32u!NtUserGetThreadState` at `0x1800268e9`
- `ntdll!RtlSetLastWin32Error` at `0x1800266e3`
- `ntdll!RtlSetLastWin32Error` at `0x1800268be`
- `ntdll!RtlSetLastWin32Error` at `0x1800266e3`
- `ntdll!RtlSetLastWin32Error` at `0x1800268be`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x18002655b`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x18002656c`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x1800265a6`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x1800265c7`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x1800265e9`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x180026609`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x180026707`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x180026717`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x180026755`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x180026770`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x180026791`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x1800267b2`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x18002655b`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x18002656c`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x1800265a6`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x1800265c7`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x1800265e9`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x180026609`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x180026707`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x180026717`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x180026755`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x180026770`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x180026791`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x1800267b2`

## pseudocode

```c
BOOL __stdcall GetMonitorInfoW(HMONITOR hMonitor, LPMONITORINFO lpmi)
{
  __int64 v2; // rax
  __int64 v3; // r8
  __int64 v4; // r12
  __int64 v5; // rcx
  __int64 v6; // r9
  unsigned int v7; // edi
  RECT v8; // xmm0
  unsigned __int16 v9; // di
  int v10; // ebx
  int v11; // ebp
  int v12; // esi
  int v13; // r15d
  unsigned int v14; // edi
  RECT v15; // xmm0
  unsigned __int16 v16; // di
  int v18; // ebx
  int v19; // esi
  int v20; // r15d
  int v21; // eax
  int v22; // edx
  int v23; // edi
  int v24; // ebx
  int v25; // r12d
  SIZE_T v26; // rcx
  SIZE_T v27; // rcx
  unsigned __int16 v28; // [rsp+20h] [rbp-78h]
  int nNumber[4]; // [rsp+38h] [rbp-60h]
  int nNumbera[4]; // [rsp+38h] [rbp-60h]
  LPMONITORINFO v31; // [rsp+48h] [rbp-50h]

  v31 = lpmi;
  if ( (unsigned __int64)(unsigned __int16)hMonitor >= *(_QWORD *)(gpsi + 8)
    || (unsigned __int64)(unsigned __int16)hMonitor >= *(_QWORD *)(gSharedInfo + 8)
    || (v2 = dword_1800C9380 * (unsigned int)(unsigned __int16)hMonitor + qword_1800C9378, !*(_BYTE *)(v2 + 24))
    || !v2
    || (WORD1(hMonitor) & 0x7FFF) != *(_WORD *)(v2 + 26) && (WORD1(hMonitor) & 0x7FFF) != 0x7FFF
    || (*(_BYTE *)(v2 + 25) & 1) != 0
    || *(_BYTE *)(v2 + 24) != 12
    || (v3 = qword_1800C9390, (v4 = qword_1800C9390 + *(_QWORD *)v2) == 0) )
  {
    RtlSetLastWin32Error(0x5B5u);
    return 0;
  }
  if ( lpmi->cbSize != 40 )
  {
    if ( lpmi->cbSize != 104 )
    {
      RtlSetLastWin32Error(0x57u);
      return 0;
    }
    if ( (unsigned int)NtUserGetHDevName(hMonitor, &lpmi[1]) )
    {
      v3 = qword_1800C9390;
      lpmi = v31;
      goto LABEL_13;
    }
    return 0;
  }
LABEL_13:
  v5 = *(_QWORD *)(qword_1800C9388 + 8);
  if ( v5 )
    v6 = v5 + v3;
  else
    v6 = 0;
  lpmi->dwFlags = v4 == v6;
  if ( *(_DWORD *)&gfServerProcess
    || NtCurrentTeb() == (struct _TEB *)-2048LL && !NtUserGetThreadState(14)
    || (LODWORD(NtCurrentTeb()->Win32ClientInfo[29])
      ? (v7 = NtCurrentTeb()->Win32ClientInfo[29])
      : (v7 = gDefaultDpiContext),
        (v7 & 0xF) != 2
     && (NtCurrentTeb()->Win32ThreadInfo || NtUserGetThreadState(14))
     && ((v26 = NtCurrentTeb()->Win32ClientInfo[4]) == 0 || (*(_BYTE *)(v26 + 64) & 1) == 0)) )
  {
    v7 = 18;
  }
  v8 = *(RECT *)(v4 + 28);
  v9 = (v7 >> 8) & 0x1FF;
  if ( v9 )
  {
    v10 = *(unsigned __int16 *)(v4 + 62);
    v11 = *(unsigned __int16 *)(v4 + 60);
    v12 = MulDiv(v8.left, v9, v10);
    v13 = MulDiv(v8.top, v9, v10);
    nNumber[0] = MulDiv(0, v9, v11) + v12;
    nNumber[1] = MulDiv(0, v9, v11) + v13;
    nNumber[2] = MulDiv(v8.right - v8.left, v9, v11) + nNumber[0];
    nNumber[3] = MulDiv(v8.bottom - v8.top, v9, v11) + nNumber[1];
    v8 = *(RECT *)nNumber;
  }
  v31->rcMonitor = v8;
  if ( *(_DWORD *)&gfServerProcess
    || NtCurrentTeb() == (struct _TEB *)-2048LL && !NtUserGetThreadState(14)
    || (LODWORD(NtCurrentTeb()->Win32ClientInfo[29])
      ? (v14 = NtCurrentTeb()->Win32ClientInfo[29])
      : (v14 = gDefaultDpiContext),
        (v14 & 0xF) != 2
     && (NtCurrentTeb()->Win32ThreadInfo || NtUserGetThreadState(14))
     && ((v27 = NtCurrentTeb()->Win32ClientInfo[4]) == 0 || (*(_BYTE *)(v27 + 64) & 1) == 0)) )
  {
    v14 = 18;
  }
  v15 = *(RECT *)(v4 + 44);
  v16 = (v14 >> 8) & 0x1FF;
  v28 = v16;
  if ( v16 )
  {
    v18 = *(unsigned __int16 *)(v4 + 62);
    v19 = *(_DWORD *)(v4 + 28);
    v20 = *(_DWORD *)(v4 + 32);
    v21 = MulDiv(v19, v16, v18);
    v22 = v16;
    v23 = v21;
    v24 = MulDiv(v20, v22, v18);
    v25 = *(unsigned __int16 *)(v4 + 60);
    nNumbera[0] = MulDiv(v15.left - v19, v28, v25) + v23;
    nNumbera[1] = MulDiv(v15.top - v20, v28, v25) + v24;
    nNumbera[2] = MulDiv(v15.right - v15.left, v28, v25) + nNumbera[0];
    nNumbera[3] = MulDiv(v15.bottom - v15.top, v28, v25) + nNumbera[1];
    v15 = *(RECT *)nNumbera;
  }
  v31->rcWork = v15;
  return 1;
}

```

## disassembly

```asm
0x1800263b0  push    r12
0x1800263b2  sub     rsp, 90h
0x1800263b9  movzx   eax, cx
0x1800263bc  mov     r9, rcx
0x1800263bf  mov     rcx, cs:gpsi
0x1800263c6  mov     [rsp+98h+var_50], rdx
0x1800263cb  cmp     rax, [rcx+8]
0x1800263cf  jnb     loc_1800266DE
0x1800263d5  mov     rcx, cs:gSharedInfo
0x1800263dc  cmp     rax, [rcx+8]
0x1800263e0  jnb     loc_1800266DE
0x1800263e6  imul    eax, cs:dword_1800C9380
0x1800263ed  mov     ecx, eax
0x1800263ef  mov     rax, cs:qword_1800C9378
0x1800263f6  add     rax, rcx
0x1800263f9  cmp     byte ptr [rax+18h], 0
0x1800263fd  jz      loc_1800266DE
0x180026403  test    rax, rax
0x180026406  jz      loc_1800266DE
0x18002640c  mov     rcx, r9
0x18002640f  mov     r8d, 7FFFh
0x180026415  shr     rcx, 10h
0x180026419  and     cx, r8w
0x18002641d  cmp     cx, [rax+1Ah]
0x180026421  jnz     loc_1800268AA
0x180026427  test    byte ptr [rax+19h], 1
0x18002642b  jnz     loc_1800266DE
0x180026431  cmp     byte ptr [rax+18h], 0Ch
0x180026435  jnz     loc_1800266DE
0x18002643b  mov     r12, [rax]
0x18002643e  mov     r8, cs:qword_1800C9390
0x180026445  add     r12, r8
0x180026448  mov     [rsp+98h+var_48], r12
0x18002644d  jz      loc_1800266DE
0x180026453  mov     eax, [rdx]
0x180026455  cmp     eax, 28h ; '('
0x180026458  jz      short loc_180026484
0x18002645a  cmp     eax, 68h ; 'h'
0x18002645d  jnz     loc_1800268B9
0x180026463  add     rdx, 28h ; '('
0x180026467  mov     rcx, r9
0x18002646a  call    cs:__imp_NtUserGetHDevName
0x180026470  test    eax, eax
0x180026472  jz      loc_1800266E9
0x180026478  mov     r8, cs:qword_1800C9390
0x18002647f  mov     rdx, [rsp+98h+var_50]
0x180026484  mov     rax, cs:qword_1800C9388
0x18002648b  mov     [rsp+98h+arg_10], rbx
0x180026493  mov     [rsp+98h+var_20], rdi
0x180026498  mov     rcx, [rax+8]
0x18002649c  test    rcx, rcx
0x18002649f  jz      loc_1800267FC
0x1800264a5  lea     r9, [rcx+r8]
0x1800264a9  xor     eax, eax
0x1800264ab  cmp     r12, r9
0x1800264ae  setz    al
0x1800264b1  mov     [rdx+24h], eax
0x1800264b4  cmp     cs:gfServerProcess, 0
0x1800264bb  jnz     loc_180026882
0x1800264c1  mov     rax, gs:30h
0x1800264ca  add     rax, 800h
0x1800264d0  jz      loc_18002686E
0x1800264d6  mov     rax, gs:30h
0x1800264df  cmp     dword ptr [rax+8E8h], 0
0x1800264e6  jnz     loc_1800267D4
0x1800264ec  mov     edi, cs:gDefaultDpiContext
0x1800264f2  mov     eax, edi
0x1800264f4  and     al, 0Fh
0x1800264f6  cmp     al, 2
0x1800264f8  jnz     loc_180026804
0x1800264fe  movups  xmm0, xmmword ptr [r12+1Ch]
0x180026504  mov     [rsp+98h+var_10], rbp
0x18002650c  mov     ebx, 1FFh
0x180026511  mov     [rsp+98h+var_18], rsi
0x180026519  shr     edi, 8
0x18002651c  mov     [rsp+98h+var_28], r13
0x180026521  and     di, bx
0x180026524  mov     [rsp+98h+var_30], r14
0x180026529  mov     [rsp+98h+var_38], r15
0x18002652e  mov     dword ptr [rsp+98h+var_78], edi
0x180026532  movups  xmmword ptr [rsp+98h+nNumber], xmm0
0x180026537  jz      loc_180026630
0x18002653d  movzx   ebx, word ptr [r12+3Eh]
0x180026543  mov     rcx, qword ptr [rsp+98h+nNumber]; nNumber
0x180026548  mov     r8d, ebx; nDenominator
0x18002654b  movzx   ebp, word ptr [r12+3Ch]
0x180026551  movzx   edi, di
0x180026554  mov     edx, edi; nNumerator
0x180026556  mov     qword ptr [rsp+98h+var_68], rcx
0x18002655b  call    cs:__imp_MulDiv
0x180026561  mov     ecx, [rsp+98h+var_68+4]; nNumber
0x180026565  mov     r8d, ebx; nDenominator
0x180026568  mov     edx, edi; nNumerator
0x18002656a  mov     esi, eax
0x18002656c  call    cs:__imp_MulDiv
0x180026572  mov     rbx, qword ptr [rsp+98h+nNumber]
0x180026577  mov     r8d, ebp; nDenominator
0x18002657a  mov     r12d, [rsp+98h+nNumber+4]
0x18002657f  mov     r15d, eax
0x180026582  mov     r14d, [rsp+98h+nNumber+8]
0x180026587  lea     rax, [rsp+98h+nNumber]
0x18002658c  mov     r13d, [rsp+98h+nNumber+0Ch]
0x180026591  mov     rdi, rbx
0x180026594  mov     [rsp+98h+var_70], rax
0x180026599  xor     ecx, ecx; nNumber
0x18002659b  mov     eax, dword ptr [rsp+98h+var_78]
0x18002659f  movzx   edx, ax; nNumerator
0x1800265a2  shr     rdi, 20h
0x1800265a6  call    cs:__imp_MulDiv
0x1800265ac  mov     r8d, ebp; nDenominator
0x1800265af  lea     ecx, [rax+rsi]
0x1800265b2  mov     rax, [rsp+98h+var_70]
0x1800265b7  mov     [rax], ecx
0x1800265b9  mov     ecx, r12d
0x1800265bc  mov     eax, dword ptr [rsp+98h+var_78]
0x1800265c0  sub     ecx, edi; nNumber
0x1800265c2  movzx   esi, ax
0x1800265c5  mov     edx, esi; nNumerator
0x1800265c7  call    cs:__imp_MulDiv
0x1800265cd  sub     r14d, ebx
0x1800265d0  mov     r8d, ebp; nDenominator
0x1800265d3  mov     ecx, r14d; nNumber
0x1800265d6  lea     edx, [rax+r15]
0x1800265da  mov     rax, [rsp+98h+var_70]
0x1800265df  mov     rdi, [rsp+98h+var_70]
0x1800265e4  mov     [rax+4], edx
0x1800265e7  mov     edx, esi; nNumerator
0x1800265e9  call    cs:__imp_MulDiv
0x1800265ef  mov     r10d, [rdi]
0x1800265f2  sub     r13d, r12d
0x1800265f5  add     r10d, eax
0x1800265f8  mov     r8d, ebp; nDenominator
0x1800265fb  mov     rax, [rsp+98h+var_70]
0x180026600  mov     edx, esi; nNumerator
0x180026602  mov     ecx, r13d; nNumber
0x180026605  mov     [rax+8], r10d
0x180026609  call    cs:__imp_MulDiv
0x18002660f  mov     rcx, [rsp+98h+var_70]
0x180026614  mov     ebx, 1FFh
0x180026619  mov     r12, [rsp+98h+var_48]
0x18002661e  mov     ecx, [rcx+4]
0x180026621  add     ecx, eax
0x180026623  mov     rax, [rsp+98h+var_70]
0x180026628  mov     [rax+0Ch], ecx
0x18002662b  movups  xmm0, xmmword ptr [rsp+98h+nNumber]
0x180026630  mov     rax, [rsp+98h+var_50]
0x180026635  movups  xmmword ptr [rax+4], xmm0
0x180026639  cmp     cs:gfServerProcess, 0
0x180026640  jnz     loc_1800268A0
0x180026646  mov     rax, gs:30h
0x18002664f  add     rax, 800h
0x180026655  jz      loc_18002688C
0x18002665b  mov     rax, gs:30h
0x180026664  cmp     dword ptr [rax+8E8h], 0
0x18002666b  jnz     loc_1800267E8
0x180026671  mov     edi, cs:gDefaultDpiContext
0x180026677  mov     eax, edi
0x180026679  and     al, 0Fh
0x18002667b  cmp     al, 2
0x18002667d  jnz     loc_180026839
0x180026683  movups  xmm0, xmmword ptr [r12+2Ch]
0x180026689  shr     edi, 8
0x18002668c  and     di, bx
0x18002668f  mov     dword ptr [rsp+98h+var_78], edi
0x180026693  movups  xmmword ptr [rsp+98h+nNumber], xmm0
0x180026698  jnz     short loc_1800266ED
0x18002669a  mov     rax, [rsp+98h+var_50]
0x18002669f  mov     r15, [rsp+98h+var_38]
0x1800266a4  mov     r14, [rsp+98h+var_30]
0x1800266a9  mov     r13, [rsp+98h+var_28]
0x1800266ae  mov     rdi, [rsp+98h+var_20]
0x1800266b3  mov     rsi, [rsp+98h+var_18]
0x1800266bb  mov     rbp, [rsp+98h+var_10]
0x1800266c3  mov     rbx, [rsp+98h+arg_10]
0x1800266cb  movups  xmmword ptr [rax+14h], xmm0
0x1800266cf  mov     eax, 1
0x1800266d4  add     rsp, 90h
0x1800266db  pop     r12
0x1800266dd  retn
0x1800266de  mov     ecx, 5B5h; LastError
0x1800266e3  call    cs:__imp_RtlSetLastWin32Error
0x1800266e9  xor     eax, eax
0x1800266eb  jmp     short loc_1800266D4
0x1800266ed  movzx   ebx, word ptr [r12+3Eh]
0x1800266f3  mov     esi, [r12+1Ch]
0x1800266f8  mov     r8d, ebx; nDenominator
0x1800266fb  mov     r15d, [r12+20h]
0x180026700  mov     ecx, esi; nNumber
0x180026702  movzx   ebp, di
0x180026705  mov     edx, ebp; nNumerator
0x180026707  call    cs:__imp_MulDiv
0x18002670d  mov     r8d, ebx; nDenominator
0x180026710  mov     edx, ebp; nNumerator
0x180026712  mov     ecx, r15d; nNumber
0x180026715  mov     edi, eax
0x180026717  call    cs:__imp_MulDiv
0x18002671d  mov     edx, dword ptr [rsp+98h+var_78]
0x180026721  mov     ebx, eax
0x180026723  mov     ebp, [rsp+98h+nNumber]
0x180026727  lea     rax, [rsp+98h+nNumber]
0x18002672c  movzx   r12d, word ptr [r12+3Ch]
0x180026732  mov     ecx, ebp
0x180026734  mov     r13d, [rsp+98h+nNumber+4]
0x180026739  sub     ecx, esi; nNumber
0x18002673b  mov     r14d, [rsp+98h+nNumber+8]
0x180026740  mov     r8d, r12d; nDenominator
0x180026743  movzx   esi, dx
0x180026746  mov     qword ptr [rsp+98h+var_68], rax
0x18002674b  mov     edx, esi; nNumerator
0x18002674d  mov     eax, [rsp+98h+nNumber+0Ch]
0x180026751  mov     dword ptr [rsp+98h+var_70], eax
0x180026755  call    cs:__imp_MulDiv
0x18002675b  mov     r8d, r12d; nDenominator
0x18002675e  mov     edx, esi; nNumerator
0x180026760  lea     ecx, [rax+rdi]
0x180026763  mov     rax, qword ptr [rsp+98h+var_68]
0x180026768  mov     [rax], ecx
0x18002676a  mov     ecx, r13d
0x18002676d  sub     ecx, r15d; nNumber
0x180026770  call    cs:__imp_MulDiv
0x180026776  sub     r14d, ebp
0x180026779  mov     r8d, r12d; nDenominator
0x18002677c  mov     ecx, r14d; nNumber
0x18002677f  lea     edx, [rax+rbx]
0x180026782  mov     rax, qword ptr [rsp+98h+var_68]
0x180026787  mov     rbx, qword ptr [rsp+98h+var_68]
0x18002678c  mov     [rax+4], edx
0x18002678f  mov     edx, esi; nNumerator
0x180026791  call    cs:__imp_MulDiv
0x180026797  mov     r10d, [rbx]
0x18002679a  mov     r8d, r12d; nDenominator
0x18002679d  mov     ecx, dword ptr [rsp+98h+var_70]
0x1800267a1  add     r10d, eax
0x1800267a4  mov     rax, qword ptr [rsp+98h+var_68]
0x1800267a9  sub     ecx, r13d; nNumber
0x1800267ac  mov     edx, esi; nNumerator
0x1800267ae  mov     [rax+8], r10d
0x1800267b2  call    cs:__imp_MulDiv
0x1800267b8  mov     rcx, qword ptr [rsp+98h+var_68]
0x1800267bd  mov     ecx, [rcx+4]
0x1800267c0  add     ecx, eax
0x1800267c2  mov     rax, qword ptr [rsp+98h+var_68]
0x1800267c7  mov     [rax+0Ch], ecx
0x1800267ca  movups  xmm0, xmmword ptr [rsp+98h+nNumber]
0x1800267cf  jmp     loc_18002669A
0x1800267d4  mov     rax, gs:30h
0x1800267dd  mov     edi, [rax+8E8h]
0x1800267e3  jmp     loc_1800264F2
0x1800267e8  mov     rax, gs:30h
0x1800267f1  mov     edi, [rax+8E8h]
0x1800267f7  jmp     loc_180026677
0x1800267fc  xor     r9d, r9d
0x1800267ff  jmp     loc_1800264A9
0x180026804  mov     rax, gs:30h
0x18002680d  cmp     qword ptr [rax+78h], 0
0x180026812  jz      loc_1800268CB
0x180026818  mov     rax, gs:30h
0x180026821  mov     rcx, [rax+820h]
0x180026828  test    rcx, rcx
0x18002682b  jz      short loc_180026882
0x18002682d  test    byte ptr [rcx+40h], 1
0x180026831  jnz     loc_1800264FE
0x180026837  jmp     short loc_180026882
0x180026839  mov     rax, gs:30h
0x180026842  cmp     qword ptr [rax+78h], 0
0x180026847  jz      loc_1800268E4
0x18002684d  mov     rax, gs:30h
0x180026856  mov     rcx, [rax+820h]
0x18002685d  test    rcx, rcx
0x180026860  jz      short loc_1800268A0
0x180026862  test    byte ptr [rcx+40h], 1
0x180026866  jnz     loc_180026683
0x18002686c  jmp     short loc_1800268A0
0x18002686e  mov     ecx, 0Eh
0x180026873  call    cs:__imp_NtUserGetThreadState
0x180026879  test    rax, rax
0x18002687c  jnz     loc_1800264D6
0x180026882  mov     edi, 12h
0x180026887  jmp     loc_1800264FE
0x18002688c  mov     ecx, 0Eh
0x180026891  call    cs:__imp_NtUserGetThreadState
0x180026897  test    rax, rax
0x18002689a  jnz     loc_18002665B
0x1800268a0  mov     edi, 12h
0x1800268a5  jmp     loc_180026683
0x1800268aa  cmp     cx, r8w
0x1800268ae  jz      loc_180026427
0x1800268b4  jmp     loc_1800266DE
0x1800268b9  mov     ecx, 57h ; 'W'; LastError
0x1800268be  call    cs:__imp_RtlSetLastWin32Error
0x1800268c4  xor     eax, eax
0x1800268c6  jmp     loc_1800266D4
0x1800268cb  mov     ecx, 0Eh
0x1800268d0  call    cs:__imp_NtUserGetThreadState
0x1800268d6  test    rax, rax
0x1800268d9  jnz     loc_180026818
0x1800268df  jmp     loc_1800264FE
0x1800268e4  mov     ecx, 0Eh
0x1800268e9  call    cs:__imp_NtUserGetThreadState
0x1800268ef  test    rax, rax
  ... truncated ...
```
