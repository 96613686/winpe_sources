# mciLoadDevice(ulong,tagMCI_OPEN_PARMSW *,MCI_INTERNAL_OPEN_INFO *,int)

- ea: `0x180013f64`
- end: `0x1800146c6`
- name: `?mciLoadDevice@@YAKKPEAUtagMCI_OPEN_PARMSW@@PEAUMCI_INTERNAL_OPEN_INFO@@H@Z`
- size: `1890`
- prototype: `__int64 __fastcall(unsigned int, struct tagMCI_OPEN_PARMSW *, void **, int)`
- caller_count: `1`
- callee_count: `19`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x180015480`

## callees

- `0x180003a2c`
- `0x180004700`
- `0x180009a90`
- `0x18000a02c`
- `0x18000b1f8`
- `0x18000b6d4`
- `0x18000c990`
- `0x180011020`
- `0x180012f30`
- `0x180013c34`
- `0x180013e9c`
- `0x180013f64`
- `0x1800146cc`
- `0x18001490c`
- `0x180014a54`
- `0x180014b54`
- `0x180014f74`
- `0x180015848`
- `0x18001a408`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180014362`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180014362`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180014152`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001467d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180014694`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180014152`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001467d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180014694`
- `api-ms-win-core-privateprofile-l1-1-0!GetPrivateProfileStringW` at `0x180014009`
- `api-ms-win-core-privateprofile-l1-1-0!GetPrivateProfileStringW` at `0x1800140d0`
- `api-ms-win-core-privateprofile-l1-1-0!GetPrivateProfileStringW` at `0x180014009`
- `api-ms-win-core-privateprofile-l1-1-0!GetPrivateProfileStringW` at `0x1800140d0`
- `api-ms-win-core-privateprofile-l1-1-0!GetProfileStringW` at `0x18001423e`
- `api-ms-win-core-privateprofile-l1-1-0!GetProfileStringW` at `0x18001423e`
- `WINMMBASE!OpenDriver` at `0x1800143b1`
- `WINMMBASE!OpenDriver` at `0x1800143b1`
- `WINMMBASE!DrvGetModuleHandle` at `0x180014408`
- `WINMMBASE!DrvGetModuleHandle` at `0x180014408`

## pseudocode

```c
__int64 __fastcall mciLoadDevice(unsigned int a1, struct tagMCI_OPEN_PARMSW *a2, void **a3, int a4)
{
  const unsigned __int16 *lpstrDeviceType; // r15
  unsigned int v5; // ebx
  struct tagMCI_OPEN_PARMSW *v8; // rdi
  struct tagMCI_OPEN_PARMSW *v9; // rsi
  WCHAR *v11; // r12
  __int64 v12; // rdi
  unsigned __int16 *v13; // rax
  LPCWSTR v14; // rcx
  __int64 v15; // rdx
  int i; // ebx
  WCHAR v17; // ax
  WCHAR *v18; // r8
  unsigned __int16 *v19; // rax
  unsigned int v20; // r8d
  unsigned int DriverName; // ebx
  int v22; // edx
  int v23; // r8d
  LPCWSTR lpstrElementName; // rdx
  MCIDEVICEID v25; // edi
  void *CurrentThreadId; // rax
  __int64 v27; // rbx
  HDRVR v28; // rax
  HDRVR v29; // r14
  HMODULE ModuleHandle; // rax
  UINT CommandResource; // edx
  UINT v32; // eax
  __int64 v33; // rax
  unsigned __int64 v34; // r14
  unsigned __int16 *v35; // rax
  LPCWSTR v36; // rcx
  __int64 v37; // rdx
  unsigned int v38; // eax
  unsigned __int16 v39; // ax
  unsigned int nSize; // [rsp+20h] [rbp-E0h]
  DWORD_PTR dwParam1; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v42; // [rsp+38h] [rbp-C8h]
  LPARAM lParam2[2]; // [rsp+40h] [rbp-C0h] BYREF
  UINT wType; // [rsp+50h] [rbp-B0h]
  __int64 v45; // [rsp+58h] [rbp-A8h] BYREF
  struct tagMCI_OPEN_PARMSW *v46; // [rsp+60h] [rbp-A0h]
  DWORD_PTR dwParam2; // [rsp+68h] [rbp-98h] BYREF
  WCHAR ReturnedString[256]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR v49[128]; // [rsp+270h] [rbp+170h] BYREF

  v42 = a1;
  wType = 0;
  *(_OWORD *)lParam2 = 0;
  lpstrDeviceType = a2->lpstrDeviceType;
  v5 = a1;
  LODWORD(dwParam1) = a1;
  v46 = a2;
  dwParam2 = (DWORD_PTR)a2;
  v45 = 0;
  v8 = a2;
  v9 = a2;
  if ( !lpstrDeviceType )
    return 263;
  v11 = 0;
  if ( !GetPrivateProfileStringW(L"MCI32", lpstrDeviceType, &wszNull, ReturnedString, 0xFFu, L"system.ini") )
  {
    v12 = -1;
    do
      ++v12;
    while ( lpstrDeviceType[v12] );
    v13 = (unsigned __int16 *)winmmAlloc((unsigned int)(2 * v12 + 4));
    v11 = v13;
    if ( !v13 )
    {
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (LPCWSTR)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) == 0
        || !*((_BYTE *)WPP_GLOBAL_Control + 25) )
      {
        return 264;
      }
      v15 = 24;
      goto LABEL_11;
    }
    if ( (int)StringCbCopyW(v13, 2 * v12 + 4, lpstrDeviceType) < 0 )
      return 264;
    for ( i = 1; i <= 9; ++i )
    {
      v11[v12] = i + 48;
      if ( GetPrivateProfileStringW(L"MCI32", v11, &wszNull, ReturnedString, 0xFFu, L"system.ini") )
      {
        if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_SS(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            25,
            (unsigned int)WPP_cea7a9ba714133be50a5a9dd0a573e7f_Traceguids,
            (_DWORD)v11,
            (__int64)ReturnedString);
        }
        goto LABEL_22;
      }
    }
    HeapFree(hHeap, 0, v11);
    v19 = (unsigned __int16 *)winmmAlloc(0xA0u);
    v11 = v19;
    if ( !v19 )
    {
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (LPCWSTR)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) == 0
        || !*((_BYTE *)WPP_GLOBAL_Control + 25) )
      {
        return 264;
      }
      v15 = 26;
LABEL_11:
      WPP_SF_(*((_QWORD *)v14 + 2), v15, WPP_cea7a9ba714133be50a5a9dd0a573e7f_Traceguids);
      return 264;
    }
    DriverName = mciFindDriverName(lpstrDeviceType, v19, v20, ReturnedString, nSize);
    if ( !DriverName )
    {
LABEL_22:
      v5 = v42;
      lpstrDeviceType = v11;
      v8 = v9;
      goto LABEL_23;
    }
    if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      WPP_SF_S(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        27,
        WPP_cea7a9ba714133be50a5a9dd0a573e7f_Traceguids,
        lpstrDeviceType);
    }
    goto LABEL_114;
  }
LABEL_23:
  v17 = ReturnedString[0];
  v18 = ReturnedString;
  while ( v17 != 32 && v17 )
    v17 = *++v18;
  if ( *v18 == 32 )
    *v18++ = 0;
  GetProfileStringW(ReturnedString, lpstrDeviceType, v18, v49, 0x80u);
  if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
  {
    WPP_SF_SSS(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v22,
      v23,
      (_DWORD)lpstrDeviceType,
      (__int64)ReturnedString,
      (__int64)v49);
  }
  if ( (v5 & 0xA00) != 0 )
    lpstrElementName = v9->lpstrElementName;
  else
    lpstrElementName = v8->lpstrDeviceType;
  if ( (v5 & 0x400) != 0 )
  {
    if ( !a4 && mciGetDeviceIDInternal(v9->lpstrAlias, a3[2]) )
    {
      DriverName = 289;
      if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, WPP_cea7a9ba714133be50a5a9dd0a573e7f_Traceguids);
      }
      goto LABEL_113;
    }
    lpstrElementName = v9->lpstrAlias;
  }
  v25 = mciAllocateNode(v5, lpstrElementName, &v45);
  if ( !v25 )
  {
    if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), v25 + 30, WPP_cea7a9ba714133be50a5a9dd0a573e7f_Traceguids);
    }
LABEL_59:
    DriverName = 266;
    goto LABEL_113;
  }
  CurrentThreadId = a3[2];
  if ( !CurrentThreadId )
    CurrentThreadId = (void *)GetCurrentThreadId();
  v27 = v45;
  *(_QWORD *)(v45 + 88) = CurrentThreadId;
  if ( *(_QWORD *)(v27 + 88) != *(_QWORD *)(v27 + 80) )
    *(_DWORD *)(v27 + 104) |= 0x20000u;
  wType = 0;
  *(LPARAM *)((char *)lParam2 + 4) = (LPARAM)v49;
  HIDWORD(lParam2[1]) = -1;
  LODWORD(lParam2[0]) = v25;
  v28 = OpenDriver(ReturnedString, L"MCI32", (LPARAM)lParam2);
  v29 = v28;
  if ( !v28 )
  {
    if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, WPP_cea7a9ba714133be50a5a9dd0a573e7f_Traceguids);
    }
    mciFreeDevice(v27);
    goto LABEL_59;
  }
  v9->wDeviceID = v25;
  ModuleHandle = DrvGetModuleHandle(v28);
  *(_QWORD *)(v27 + 96) = v29;
  *(_QWORD *)(v27 + 72) = ModuleHandle;
  CommandResource = 0;
  *(_DWORD *)(v27 + 64) = HIDWORD(lParam2[1]);
  *(_DWORD *)(v27 + 56) = wType;
  while ( CommandResource < number_of_command_tables )
  {
    if ( LODWORD(qword_180025C30[5 * CommandResource]) == wType )
      goto LABEL_77;
    ++CommandResource;
  }
  if ( wType - 513 > 0xA )
    CommandResource = -1;
  else
    CommandResource = mciLoadCommandResource(ghInst, (LPCWSTR)(unsigned __int16)wType, wType);
LABEL_77:
  *(_DWORD *)(v27 + 60) = CommandResource;
  if ( CommandResource == -1 )
  {
    v32 = mciLoadCommandResource(ghInst, v9->lpstrDeviceType, wType);
    *(_DWORD *)(v27 + 60) = v32;
    if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, WPP_cea7a9ba714133be50a5a9dd0a573e7f_Traceguids, v32);
    }
  }
  v33 = -1;
  do
    ++v33;
  while ( lpstrDeviceType[v33] );
  v34 = 2 * v33 + 2;
  v35 = (unsigned __int16 *)winmmAlloc((unsigned int)(2 * v33 + 2));
  *(_QWORD *)(v27 + 8) = v35;
  if ( !v35 )
  {
    mciCloseDevice(v25, 0, 0);
    v36 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (LPCWSTR)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) == 0
      || !*((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      goto LABEL_90;
    }
    v37 = 33;
LABEL_89:
    WPP_SF_(*((_QWORD *)v36 + 2), v37, WPP_cea7a9ba714133be50a5a9dd0a573e7f_Traceguids);
LABEL_90:
    DriverName = 264;
    goto LABEL_113;
  }
  if ( StringCchCopyW(v35, v34, lpstrDeviceType) < 0 )
  {
    mciCloseDevice(v25, 0, 0);
    v36 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (LPCWSTR)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) == 0
      || !*((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      goto LABEL_90;
    }
    v37 = 34;
    goto LABEL_89;
  }
  if ( *a3 )
  {
    DriverName = mciReparseOpen(
                   (struct MCI_INTERNAL_OPEN_INFO *)a3,
                   *(_DWORD *)(v27 + 64),
                   *(_DWORD *)(v27 + 60),
                   (unsigned int *)&dwParam1,
                   (struct tagMCI_OPEN_PARMSW **)&dwParam2,
                   v25);
    if ( DriverName )
    {
      if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 35, WPP_cea7a9ba714133be50a5a9dd0a573e7f_Traceguids);
      }
      mciCloseDevice(v25, 0, 0);
      goto LABEL_113;
    }
    v38 = dwParam1;
    v9 = (struct tagMCI_OPEN_PARMSW *)dwParam2;
  }
  else
  {
    if ( *((_DWORD *)a3 + 6) )
    {
      mciCloseDevice(v25, 0, 0);
      DriverName = *((_DWORD *)a3 + 6);
      goto LABEL_113;
    }
    v38 = v42;
  }
  v39 = mciSendCommandW(v25, 0x801u, v38, (DWORD_PTR)v9);
  DriverName = v39;
  if ( v39 )
    mciCloseDevice(v25, 0, 0);
  else
    mciSetBreakKey(v25, 3);
  if ( v46 != v9 && v9 )
    HeapFree(hHeap, 0, v9);
LABEL_113:
  if ( v11 )
LABEL_114:
    HeapFree(hHeap, 0, v11);
  return DriverName;
}

```

## disassembly

```asm
0x180013f64  mov     [rsp-8+arg_18], rbx
0x180013f69  push    rbp
0x180013f6a  push    rsi
0x180013f6b  push    rdi
0x180013f6c  push    r12
0x180013f6e  push    r13
0x180013f70  push    r14
0x180013f72  push    r15
0x180013f74  lea     rbp, [rsp-280h]
0x180013f7c  sub     rsp, 380h
0x180013f83  mov     rax, cs:__security_cookie
0x180013f8a  xor     rax, rsp
0x180013f8d  mov     [rbp+2B0h+var_40], rax
0x180013f94  xor     eax, eax
0x180013f96  mov     [rsp+3B0h+var_378], ecx
0x180013f9a  xorps   xmm0, xmm0
0x180013f9d  mov     [rsp+3B0h+wType], eax
0x180013fa1  movups  xmmword ptr [rsp+3B0h+lParam2], xmm0
0x180013fa6  mov     r15, [rdx+0Ch]
0x180013faa  mov     ebx, ecx
0x180013fac  mov     dword ptr [rsp+3B0h+dwParam1], ecx
0x180013fb0  mov     r14d, r9d
0x180013fb3  xor     ecx, ecx
0x180013fb5  mov     [rsp+3B0h+var_350], rdx
0x180013fba  mov     [rsp+3B0h+dwParam2], rdx
0x180013fbf  mov     r13, r8
0x180013fc2  mov     [rsp+3B0h+var_358], rcx
0x180013fc7  mov     rdi, rdx
0x180013fca  mov     rsi, rdx
0x180013fcd  test    r15, r15
0x180013fd0  jnz     short loc_180013FDC
0x180013fd2  mov     eax, 107h
0x180013fd7  jmp     loc_18001469C
0x180013fdc  lea     rax, FileName; "system.ini"
0x180013fe3  mov     r12, rcx
0x180013fe6  mov     [rsp+3B0h+lpFileName], rax; lpFileName
0x180013feb  lea     r9, [rsp+3B0h+ReturnedString]; lpReturnedString
0x180013ff0  lea     r8, wszNull; lpDefault
0x180013ff7  mov     [rsp+3B0h+nSize], 0FFh; unsigned int
0x180013fff  mov     rdx, r15; lpKeyName
0x180014002  lea     rcx, AppName; "MCI32"
0x180014009  call    cs:__imp_GetPrivateProfileStringW
0x18001400f  xor     r10d, r10d
0x180014012  test    eax, eax
0x180014014  jnz     loc_180014132
0x18001401a  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18001401e  inc     rdi
0x180014021  cmp     [r15+rdi*2], r10w
0x180014026  jnz     short loc_18001401E
0x180014028  lea     rbx, ds:4[rdi*2]
0x180014030  mov     ecx, ebx; Size
0x180014032  call    winmmAlloc
0x180014037  mov     r12, rax
0x18001403a  test    rax, rax
0x18001403d  jnz     short loc_18001407E
0x18001403f  mov     rcx, cs:WPP_GLOBAL_Control
0x180014046  lea     rdx, WPP_GLOBAL_Control
0x18001404d  cmp     rcx, rdx
0x180014050  jz      short loc_180014074
0x180014052  test    dword ptr [rcx+1Ch], 400000h
0x180014059  jz      short loc_180014074
0x18001405b  cmp     byte ptr [rcx+19h], 1
0x18001405f  jb      short loc_180014074
0x180014061  lea     edx, [rax+18h]
0x180014064  mov     rcx, [rcx+10h]
0x180014068  lea     r8, WPP_cea7a9ba714133be50a5a9dd0a573e7f_Traceguids
0x18001406f  call    WPP_SF_
0x180014074  mov     eax, 108h
0x180014079  jmp     loc_18001469C
0x18001407e  mov     r8, r15; unsigned __int16 *
0x180014081  mov     rdx, rbx; unsigned __int64
0x180014084  mov     rcx, r12; unsigned __int16 *
0x180014087  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x18001408c  test    eax, eax
0x18001408e  js      short loc_180014074
0x180014090  mov     ebx, 1
0x180014095  cmp     ebx, 9
0x180014098  jg      loc_180014146
0x18001409e  lea     eax, [rbx+30h]
0x1800140a1  mov     rdx, r12; lpKeyName
0x1800140a4  mov     [r12+rdi*2], ax
0x1800140a9  lea     r9, [rsp+3B0h+ReturnedString]; lpReturnedString
0x1800140ae  lea     rax, FileName; "system.ini"
0x1800140b5  mov     [rsp+3B0h+lpFileName], rax; lpFileName
0x1800140ba  lea     r8, wszNull; lpDefault
0x1800140c1  lea     rcx, AppName; "MCI32"
0x1800140c8  mov     [rsp+3B0h+nSize], 0FFh; nSize
0x1800140d0  call    cs:__imp_GetPrivateProfileStringW
0x1800140d6  xor     r10d, r10d
0x1800140d9  test    eax, eax
0x1800140db  jnz     short loc_1800140E1
0x1800140dd  inc     ebx
0x1800140df  jmp     short loc_180014095
0x1800140e1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800140e8  lea     rdx, WPP_GLOBAL_Control
0x1800140ef  cmp     rcx, rdx
0x1800140f2  jz      short loc_180014128
0x1800140f4  test    dword ptr [rcx+1Ch], 400000h
0x1800140fb  jz      short loc_180014128
0x1800140fd  cmp     byte ptr [rcx+19h], 2
0x180014101  jb      short loc_180014128
0x180014103  mov     rcx, [rcx+10h]
0x180014107  lea     rax, [rsp+3B0h+ReturnedString]
0x18001410c  mov     edx, 19h
0x180014111  mov     qword ptr [rsp+3B0h+nSize], rax
0x180014116  mov     r9, r12
0x180014119  lea     r8, WPP_cea7a9ba714133be50a5a9dd0a573e7f_Traceguids
0x180014120  call    WPP_SF_SS
0x180014125  xor     r10d, r10d
0x180014128  mov     ebx, [rsp+3B0h+var_378]
0x18001412c  mov     r15, r12
0x18001412f  mov     rdi, rsi
0x180014132  movzx   eax, [rsp+3B0h+ReturnedString]
0x180014137  lea     r8, [rsp+3B0h+ReturnedString]
0x18001413c  mov     ecx, 20h ; ' '
0x180014141  jmp     loc_180014214
0x180014146  mov     rcx, cs:hHeap; hHeap
0x18001414d  mov     r8, r12; lpMem
0x180014150  xor     edx, edx; dwFlags
0x180014152  call    cs:__imp_HeapFree
0x180014158  mov     ecx, 0A0h; Size
0x18001415d  call    winmmAlloc
0x180014162  mov     r12, rax
0x180014165  test    rax, rax
0x180014168  jnz     short loc_1800141A0
0x18001416a  mov     rcx, cs:WPP_GLOBAL_Control
0x180014171  lea     rdx, WPP_GLOBAL_Control
0x180014178  cmp     rcx, rdx
0x18001417b  jz      loc_180014074
0x180014181  test    dword ptr [rcx+1Ch], 400000h
0x180014188  jz      loc_180014074
0x18001418e  cmp     byte ptr [rcx+19h], 1
0x180014192  jb      loc_180014074
0x180014198  lea     edx, [rax+1Ah]
0x18001419b  jmp     loc_180014064
0x1800141a0  lea     r9, [rsp+3B0h+ReturnedString]; unsigned __int16 *
0x1800141a5  mov     rdx, rax; unsigned __int16 *
0x1800141a8  mov     rcx, r15; unsigned __int16 *
0x1800141ab  call    ?mciFindDriverName@@YAKPEBGPEAGK1I@Z; mciFindDriverName(ushort const *,ushort *,ulong,ushort *,uint)
0x1800141b0  xor     r10d, r10d
0x1800141b3  mov     ebx, eax
0x1800141b5  test    eax, eax
0x1800141b7  jz      loc_180014128
0x1800141bd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800141c4  lea     rdx, WPP_GLOBAL_Control
0x1800141cb  cmp     rcx, rdx
0x1800141ce  jz      loc_180014688
0x1800141d4  test    dword ptr [rcx+1Ch], 400000h
0x1800141db  jz      loc_180014688
0x1800141e1  cmp     byte ptr [rcx+19h], 1
0x1800141e5  jb      loc_180014688
0x1800141eb  mov     rcx, [rcx+10h]
0x1800141ef  lea     edx, [r10+1Bh]
0x1800141f3  mov     r9, r15
0x1800141f6  lea     r8, WPP_cea7a9ba714133be50a5a9dd0a573e7f_Traceguids
0x1800141fd  call    WPP_SF_S
0x180014202  jmp     loc_180014688
0x180014207  test    ax, ax
0x18001420a  jz      short loc_180014219
0x18001420c  add     r8, 2
0x180014210  movzx   eax, word ptr [r8]
0x180014214  cmp     ax, cx
0x180014217  jnz     short loc_180014207
0x180014219  cmp     [r8], cx
0x18001421d  jnz     short loc_180014227
0x18001421f  mov     [r8], r10w
0x180014223  add     r8, 2; lpDefault
0x180014227  lea     r9, [rbp+2B0h+var_140]; lpReturnedString
0x18001422e  mov     [rsp+3B0h+nSize], 80h; nSize
0x180014236  mov     rdx, r15; lpKeyName
0x180014239  lea     rcx, [rsp+3B0h+ReturnedString]; lpAppName
0x18001423e  call    cs:__imp_GetProfileStringW
0x180014244  mov     rcx, cs:WPP_GLOBAL_Control
0x18001424b  lea     rax, WPP_GLOBAL_Control
0x180014252  cmp     rcx, rax
0x180014255  jz      short loc_180014288
0x180014257  test    dword ptr [rcx+1Ch], 400000h
0x18001425e  jz      short loc_180014288
0x180014260  cmp     byte ptr [rcx+19h], 3
0x180014264  jb      short loc_180014288
0x180014266  mov     rcx, [rcx+10h]
0x18001426a  lea     rax, [rbp+2B0h+var_140]
0x180014271  mov     [rsp+3B0h+lpFileName], rax
0x180014276  mov     r9, r15
0x180014279  lea     rax, [rsp+3B0h+ReturnedString]
0x18001427e  mov     qword ptr [rsp+3B0h+nSize], rax
0x180014283  call    WPP_SF_SSS
0x180014288  test    ebx, 0A00h
0x18001428e  jz      short loc_180014296
0x180014290  mov     rdx, [rsi+14h]
0x180014294  jmp     short loc_18001429A
0x180014296  mov     rdx, [rdi+0Ch]
0x18001429a  bt      ebx, 0Ah
0x18001429e  jnb     short loc_180014306
0x1800142a0  test    r14d, r14d
0x1800142a3  jnz     short loc_180014302
0x1800142a5  mov     rdx, [r13+10h]; void *
0x1800142a9  mov     rcx, [rsi+1Ch]; lpString2
0x1800142ad  call    ?mciGetDeviceIDInternal@@YAIPEBGPEAX@Z; mciGetDeviceIDInternal(ushort const *,void *)
0x1800142b2  test    eax, eax
0x1800142b4  jz      short loc_180014302
0x1800142b6  mov     ebx, 121h
0x1800142bb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800142c2  lea     rax, WPP_GLOBAL_Control
0x1800142c9  cmp     rcx, rax
0x1800142cc  jz      loc_180014683
0x1800142d2  test    dword ptr [rcx+1Ch], 400000h
0x1800142d9  jz      loc_180014683
0x1800142df  cmp     byte ptr [rcx+19h], 1
0x1800142e3  jb      loc_180014683
0x1800142e9  mov     rcx, [rcx+10h]
0x1800142ed  lea     edx, [r14+1Dh]
0x1800142f1  lea     r8, WPP_cea7a9ba714133be50a5a9dd0a573e7f_Traceguids
0x1800142f8  call    WPP_SF_
0x1800142fd  jmp     loc_180014683
0x180014302  mov     rdx, [rsi+1Ch]
0x180014306  lea     r8, [rsp+3B0h+var_358]
0x18001430b  mov     ecx, ebx
0x18001430d  call    mciAllocateNode
0x180014312  xor     ecx, ecx
0x180014314  mov     edi, eax
0x180014316  test    eax, eax
0x180014318  jnz     short loc_180014359
0x18001431a  mov     rcx, cs:WPP_GLOBAL_Control
0x180014321  lea     rax, WPP_GLOBAL_Control
0x180014328  cmp     rcx, rax
0x18001432b  jz      short loc_18001434F
0x18001432d  test    dword ptr [rcx+1Ch], 400000h
0x180014334  jz      short loc_18001434F
0x180014336  cmp     byte ptr [rcx+19h], 1
0x18001433a  jb      short loc_18001434F
0x18001433c  mov     rcx, [rcx+10h]
0x180014340  lea     edx, [rdi+1Eh]
0x180014343  lea     r8, WPP_cea7a9ba714133be50a5a9dd0a573e7f_Traceguids
0x18001434a  call    WPP_SF_
0x18001434f  mov     ebx, 10Ah
0x180014354  jmp     loc_180014683
0x180014359  mov     rax, [r13+10h]
0x18001435d  test    rax, rax
0x180014360  jnz     short loc_18001436C
0x180014362  call    cs:__imp_GetCurrentThreadId
0x180014368  mov     eax, eax
0x18001436a  xor     ecx, ecx
0x18001436c  mov     rbx, [rsp+3B0h+var_358]
0x180014371  mov     [rbx+58h], rax
0x180014375  mov     rax, [rbx+50h]
0x180014379  cmp     [rbx+58h], rax
0x18001437d  jz      short loc_180014384
0x18001437f  bts     dword ptr [rbx+68h], 11h
0x180014384  lea     rax, [rbp+2B0h+var_140]
0x18001438b  mov     [rsp+3B0h+wType], ecx
0x18001438f  lea     rcx, [rsp+3B0h+ReturnedString]; szDriverName
0x180014394  mov     [rsp+3B0h+lParam2+4], rax
0x180014399  lea     r8, [rsp+3B0h+lParam2]; lParam2
0x18001439e  mov     dword ptr [rsp+3B0h+lParam2+0Ch], 0FFFFFFFFh
0x1800143a6  lea     rdx, AppName; "MCI32"
0x1800143ad  mov     dword ptr [rsp+3B0h+lParam2], edi
0x1800143b1  call    cs:__imp_OpenDriver
0x1800143b7  mov     r14, rax
0x1800143ba  test    rax, rax
0x1800143bd  jnz     short loc_180014402
0x1800143bf  mov     rcx, cs:WPP_GLOBAL_Control
0x1800143c6  lea     rax, WPP_GLOBAL_Control
0x1800143cd  cmp     rcx, rax
0x1800143d0  jz      short loc_1800143F5
0x1800143d2  test    dword ptr [rcx+1Ch], 400000h
0x1800143d9  jz      short loc_1800143F5
0x1800143db  cmp     byte ptr [rcx+19h], 1
0x1800143df  jb      short loc_1800143F5
0x1800143e1  mov     rcx, [rcx+10h]
0x1800143e5  lea     edx, [r14+1Fh]
0x1800143e9  lea     r8, WPP_cea7a9ba714133be50a5a9dd0a573e7f_Traceguids
0x1800143f0  call    WPP_SF_
0x1800143f5  mov     rcx, rbx
0x1800143f8  call    mciFreeDevice
0x1800143fd  jmp     loc_18001434F
0x180014402  mov     rcx, r14; hDriver
0x180014405  mov     [rsi+8], edi
0x180014408  call    cs:__imp_DrvGetModuleHandle
0x18001440e  mov     [rbx+60h], r14
0x180014412  xor     r14d, r14d
0x180014415  mov     [rbx+48h], rax
0x180014419  mov     edx, r14d
0x18001441c  mov     eax, dword ptr [rsp+3B0h+lParam2+0Ch]
0x180014420  mov     [rbx+40h], eax
0x180014423  mov     eax, [rsp+3B0h+wType]
0x180014427  mov     [rbx+38h], eax
0x18001442a  mov     r8d, [rsp+3B0h+wType]; wType
0x18001442f  cmp     edx, cs:?number_of_command_tables@@3IA; uint number_of_command_tables
0x180014435  jnb     short loc_18001444E
0x180014437  mov     eax, edx
0x180014439  lea     rcx, [rax+rax*4]
0x18001443d  lea     rax, qword_180025C30
0x180014444  cmp     [rax+rcx*8], r8d
0x180014448  jz      short loc_180014471
0x18001444a  inc     edx
0x18001444c  jmp     short loc_18001442F
0x18001444e  lea     eax, [r8-201h]
0x180014455  cmp     eax, 0Ah
0x180014458  ja      short loc_18001446E
  ... truncated ...
```
