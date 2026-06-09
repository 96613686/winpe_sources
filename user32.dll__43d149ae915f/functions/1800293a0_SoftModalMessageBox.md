# SoftModalMessageBox

- ea: `0x1800293a0`
- end: `0x180029aa4`
- name: `SoftModalMessageBox`
- size: `1796`
- prototype: `__int64 __fastcall(struct _MSGBOXDATA *)`
- caller_count: `1`
- callee_count: `17`
- tags: `loader_planting, installer_update`

## callers

- `0x180027334`

## callees

- `0x180006dd8`
- `0x1800070e0`
- `0x180007640`
- `0x180008828`
- `0x180014a4c`
- `0x180022bac`
- `0x18002787c`
- `0x180028f0c`
- `0x18002904c`
- `0x1800291dc`
- `0x1800292d4`
- `0x1800293a0`
- `0x180029aac`
- `0x18002a230`
- `0x18002aafc`
- `0x180035ae8`
- `0x1800968f4`

## import_xrefs

- `win32u!NtUserSetCursor` at `0x18002989d`
- `win32u!NtUserSetCursor` at `0x180029953`
- `win32u!NtUserSetCursor` at `0x18002989d`
- `win32u!NtUserSetCursor` at `0x180029953`
- `win32u!NtUserMessageBeep` at `0x1800298c0`
- `win32u!NtUserMessageBeep` at `0x1800298c0`
- `win32u!NtUserReleaseDC` at `0x180029676`
- `win32u!NtUserReleaseDC` at `0x1800299c8`
- `win32u!NtUserReleaseDC` at `0x180029676`
- `win32u!NtUserReleaseDC` at `0x1800299c8`
- `win32u!NtUserGetThreadState` at `0x180029984`
- `win32u!NtUserGetThreadState` at `0x180029984`
- `win32u!NtUserGetDCEx` at `0x180029497`
- `win32u!NtUserGetDCEx` at `0x180029965`
- `win32u!NtUserGetDCEx` at `0x180029497`
- `win32u!NtUserGetDCEx` at `0x180029965`
- `ntdll!RtlFreeHeap` at `0x180029914`
- `ntdll!RtlFreeHeap` at `0x180029a82`
- `ntdll!RtlFreeHeap` at `0x180029a99`
- `ntdll!RtlFreeHeap` at `0x180029914`
- `ntdll!RtlFreeHeap` at `0x180029a82`
- `ntdll!RtlFreeHeap` at `0x180029a99`
- `ntdll!RtlAllocateHeap` at `0x180029779`
- `ntdll!RtlAllocateHeap` at `0x18009a8f4`
- `ntdll!RtlAllocateHeap` at `0x18009a94e`
- `ntdll!RtlAllocateHeap` at `0x180029779`
- `ntdll!RtlAllocateHeap` at `0x18009a8f4`
- `ntdll!RtlAllocateHeap` at `0x18009a94e`
- `KERNELBASE!LoadStringBaseExW` at `0x18009a91c`
- `KERNELBASE!LoadStringBaseExW` at `0x18009a975`
- `KERNELBASE!LoadStringBaseExW` at `0x18009a91c`
- `KERNELBASE!LoadStringBaseExW` at `0x18009a975`
- `GDI32!SelectObject` at `0x1800294bf`
- `GDI32!SelectObject` at `0x1800295c1`
- `GDI32!SelectObject` at `0x18002960d`
- `GDI32!SelectObject` at `0x180029a10`
- `GDI32!SelectObject` at `0x1800294bf`
- `GDI32!SelectObject` at `0x1800295c1`
- `GDI32!SelectObject` at `0x18002960d`
- `GDI32!SelectObject` at `0x180029a10`
- `GDI32!GetTextExtentPointW` at `0x1800295e6`
- `GDI32!GetTextExtentPointW` at `0x1800295e6`
- `GDI32!DeleteObject` at `0x18002966d`
- `GDI32!DeleteObject` at `0x1800299bf`
- `GDI32!DeleteObject` at `0x18002966d`
- `GDI32!DeleteObject` at `0x1800299bf`

## pseudocode

```c
__int64 __fastcall SoftModalMessageBox(struct _MSGBOXDATA *a1)
{
  HINSTANCE v2; // rcx
  unsigned int v3; // r12d
  int *v4; // rbx
  BOOL v5; // r14d
  int v6; // r15d
  int *v7; // rdi
  int *v8; // r13
  HINSTANCE v9; // rdi
  int v10; // ebx
  HDC DCEx; // rdi
  unsigned int v12; // eax
  unsigned __int16 CharDimensions; // dx
  __int16 v14; // ax
  unsigned __int16 MaxButtonSize; // ax
  int v16; // r14d
  int v17; // edx
  int v18; // ebx
  unsigned int v19; // eax
  unsigned int v20; // eax
  int v21; // r14d
  int *MonitorWorkRect; // rax
  __int64 v23; // rcx
  __int64 DpiServerInfoForCurrentThread; // rax
  const WCHAR *v25; // rdx
  __int64 v26; // rax
  unsigned int v27; // eax
  int v28; // ebx
  int v29; // ecx
  int v30; // r8d
  int v31; // edi
  int v32; // r14d
  unsigned int v33; // edx
  SIZE_T v34; // rcx
  int v35; // ebx
  __int64 v36; // rdx
  __int64 v37; // rcx
  int v38; // eax
  unsigned int DpiForSystem; // eax
  int v40; // ebx
  unsigned int DlgTemplateSize; // eax
  int v42; // r8d
  unsigned __int8 *updated; // rax
  __int64 v44; // rcx
  struct DLGITEMTEMPLATE *v45; // rdi
  __int64 v46; // rdx
  unsigned int v47; // ebx
  unsigned int v48; // eax
  int v49; // eax
  unsigned __int8 *v50; // rbx
  __int16 v51; // ax
  unsigned __int16 *Src; // r8
  HICON v53; // rax
  __int64 v54; // rax
  bool v55; // zf
  __int64 v56; // rbx
  PVOID v57; // rdi
  int v58; // eax
  __int64 result; // rax
  int v60; // ebx
  int v61; // ebx
  int v62; // ebx
  int v63; // r11d
  int *Heap; // rax
  int *v65; // rax
  int *v66; // rax
  int v67; // r8d
  int v68; // edx
  int v69; // r9d
  int v70; // r14d
  __int64 v71; // rdx
  int v72; // [rsp+20h] [rbp-A9h]
  int v73; // [rsp+60h] [rbp-69h]
  int v74; // [rsp+64h] [rbp-65h]
  int v75; // [rsp+64h] [rbp-65h]
  LONG v76; // [rsp+68h] [rbp-61h] BYREF
  int v77; // [rsp+6Ch] [rbp-5Dh]
  int v78; // [rsp+70h] [rbp-59h]
  int v79; // [rsp+74h] [rbp-55h]
  int v80; // [rsp+78h] [rbp-51h]
  int v81; // [rsp+7Ch] [rbp-4Dh] BYREF
  int DpiDependentMetric; // [rsp+80h] [rbp-49h]
  HGDIOBJ h; // [rsp+88h] [rbp-41h]
  int v84; // [rsp+90h] [rbp-39h]
  BOOL v85; // [rsp+94h] [rbp-35h]
  PVOID v86; // [rsp+98h] [rbp-31h]
  struct tagSIZE sz; // [rsp+A0h] [rbp-29h] BYREF
  struct tagMONITOR *DialogMonitor; // [rsp+A8h] [rbp-21h]
  HICON IcoCur; // [rsp+B0h] [rbp-19h]
  HWND v90; // [rsp+B8h] [rbp-11h]
  PVOID P[2]; // [rsp+C0h] [rbp-9h] BYREF
  unsigned int v92[20]; // [rsp+D0h] [rbp+7h] BYREF
  HINSTANCE hModule; // [rsp+130h] [rbp+67h] BYREF
  int v94; // [rsp+138h] [rbp+6Fh] BYREF
  int v95; // [rsp+140h] [rbp+77h] BYREF
  int v96; // [rsp+148h] [rbp+7Fh] BYREF

  v2 = (HINSTANCE)*((_QWORD *)a1 + 2);
  sz = 0;
  v81 = 0;
  v96 = 0;
  v94 = 0;
  v95 = 0;
  hModule = v2;
  if ( !NtCurrentTeb()->Win32ThreadInfo )
  {
    result = NtUserGetThreadState(14);
    if ( !result )
      return result;
    v2 = hModule;
  }
  v3 = *((_DWORD *)a1 + 10);
  v4 = &dword_1800AA33C;
  v85 = 0;
  v5 = 0;
  v6 = (v3 >> 7) & 0x1000;
  v86 = 0;
  v7 = 0;
  v8 = 0;
  if ( (*((_QWORD *)a1 + 4) & 0xFFFFFFFFFFFF0000uLL) == 0 )
  {
    if ( v2 && (Heap = (int *)RtlAllocateHeap(pUserHeap, 8u, 0x200u), (v7 = Heap) != 0) )
    {
      LoadStringBaseExW(hModule, *((unsigned __int16 *)a1 + 16), Heap, 256, 0);
      v65 = v7;
    }
    else
    {
      v65 = &dword_1800AA33C;
    }
    v86 = v7;
    *((_QWORD *)a1 + 4) = v65;
  }
  v9 = hModule;
  if ( (*((_QWORD *)a1 + 3) & 0xFFFFFFFFFFFF0000uLL) != 0 )
  {
    v4 = (int *)*((_QWORD *)a1 + 3);
  }
  else
  {
    if ( hModule )
    {
      v66 = (int *)RtlAllocateHeap(pUserHeap, 8u, 0x200u);
      v8 = v66;
      if ( v66 )
      {
        LOWORD(v72) = 0;
        LoadStringBaseExW(v9, *((unsigned __int16 *)a1 + 12), v66, 256, v72);
        v4 = v8;
      }
    }
    *((_QWORD *)a1 + 3) = v4;
  }
  if ( (v3 & 0x100000) != 0 || v4 && *(_WORD *)v4 == 8207 && *((_WORD *)v4 + 1) == 8207 )
  {
    v6 = 0x400000;
    if ( (v3 & 0x100000) != 0 )
      v3 ^= 0x80000u;
  }
  v10 = v3 & 0xF0;
  if ( v10 == 128 )
    IcoCur = LoadIcoCur(v9, *((PCWSTR *)a1 + 6), (unsigned __int16 *)3, 0, 0, 0x8040u);
  else
    IcoCur = 0;
  v90 = (HWND)*((_QWORD *)a1 + 1);
  DCEx = (HDC)NtUserGetDCEx(0, 0, 3);
  if ( DCEx || (DCEx = (HDC)NtUserGetDCEx(v90, 0, 3)) != 0 )
  {
    v12 = ((__int64 (*)(void))GetDpiForSystem)();
    h = GetMessageBoxFontForDpi(v12);
    v76 = 0;
    P[0] = SelectObject(DCEx, h);
    CharDimensions = UserGetCharDimensionsEx(DCEx, 0, 0, &v76);
    if ( !CharDimensions )
    {
      DeleteObject(h);
      NtUserReleaseDC(DCEx);
      goto LABEL_45;
    }
    v14 = v76;
    *((_WORD *)a1 + 76) = CharDimensions;
    *((_WORD *)a1 + 77) = v14;
    MaxButtonSize = MB_GetMaxButtonSize(DCEx, CharDimensions);
    v16 = *((unsigned __int16 *)a1 + 76);
    v17 = *((_DWORD *)a1 + 28);
    *((_WORD *)a1 + 45) = MaxButtonSize;
    v79 = v17 * MaxButtonSize + ((unsigned int)(v16 + 4 * v16 + 2) >> 2) * (v17 - 1);
    v18 = v10 - 16;
    if ( v18 )
    {
      v60 = v18 - 16;
      if ( !v60 )
      {
        LODWORD(hModule) = 32514;
        goto LABEL_13;
      }
      v61 = v60 - 16;
      if ( !v61 )
      {
        LODWORD(hModule) = 32515;
        goto LABEL_13;
      }
      v62 = v61 - 16;
      if ( !v62 )
      {
        LODWORD(hModule) = 32516;
        goto LABEL_13;
      }
      if ( v62 != 64 )
      {
        LODWORD(hModule) = 0;
        v21 = 0;
        v80 = 0;
        v73 = 0;
LABEL_14:
        DialogMonitor = GetDialogMonitor(*((HWND *)a1 + 1), 1u);
        MonitorWorkRect = (int *)GetMonitorWorkRect(v92, DialogMonitor);
        v74 = *MonitorWorkRect;
        v84 = MonitorWorkRect[1];
        v23 = (unsigned int)MonitorWorkRect[2];
        v78 = MonitorWorkRect[3];
        v77 = v23;
        DpiServerInfoForCurrentThread = GetDpiServerInfoForCurrentThread(v23);
        SelectObject(DCEx, *(HGDIOBJ *)(DpiServerInfoForCurrentThread + 8));
        v25 = (const WCHAR *)*((_QWORD *)a1 + 4);
        v26 = -1;
        do
          ++v26;
        while ( v25[v26] );
        *(_QWORD *)v92 = v26;
        GetTextExtentPointW(DCEx, v25, v26, &sz);
        v27 = ((__int64 (*)(void))GetDpiForSystem)();
        DpiDependentMetric = GetDpiDependentMetric(12, v27);
        v28 = sz.cx + 2 * DpiDependentMetric;
        SelectObject(DCEx, h);
        MB_CalcDialogSize(DialogMonitor, DCEx, a1, v73, v21, v79, v28, &v94, &v95, &v81, &v96);
        if ( P[0] )
          SelectObject(DCEx, P[0]);
        DeleteObject(h);
        NtUserReleaseDC(DCEx);
        v29 = *((unsigned __int16 *)a1 + 77);
        v30 = v96;
        v31 = v95;
        if ( v21 > v96 )
          v30 = v21;
        *((_DWORD *)a1 + 34) = 0;
        v32 = v94;
        *((_DWORD *)a1 + 36) = v94;
        v33 = (unsigned int)(14 * v29 + 4) >> 3;
        *((_DWORD *)a1 + 35) = v30 + 2 * v33;
        *((_DWORD *)a1 + 37) = v33 + v30 + 2 * (v33 + ((unsigned int)(v29 + 8 * v29 + 4) >> 3));
        v34 = NtCurrentTeb()->Win32ClientInfo[4];
        LODWORD(h) = v77 - v32;
        v35 = *(_DWORD *)(v34 + 48);
        v36 = (unsigned int)((v74 + v77 - v32) >> 31);
        LODWORD(v36) = (v74 + v77 - v32) % 2;
        v37 = (unsigned int)(v35 * DpiDependentMetric);
        v38 = v37 + (v74 + v77 - v32) / 2;
        if ( v38 <= v74 )
          v38 = v74;
        v94 = v38;
        v75 = v78 - v31;
        DpiForSystem = GetDpiForSystem(v37, v36);
        v40 = (v84 + v75) / 2 + GetDpiDependentMetric(13, DpiForSystem) * v35;
        if ( v40 <= v84 )
          v40 = v84;
        if ( v32 + v94 > v77 )
          v94 = (_DWORD)h - 2;
        if ( v40 + v31 > v78 )
        {
          v40 = v75 - 2;
          if ( v75 - 2 < v84 )
            v40 = *(_DWORD *)(GetMonitorRect(P, DialogMonitor) + 12) - v31 - 2;
        }
        DlgTemplateSize = MB_FindDlgTemplateSize(a1);
        P[0] = RtlAllocateHeap(pUserHeap, 8u, DlgTemplateSize);
        if ( P[0] )
        {
          v42 = -2134375609;
          if ( (v3 & 0x3000) != 0x1000 )
            v42 = -2134375995;
          if ( (v3 & 0x10000) != 0 )
            v42 |= 0x200u;
          updated = MB_UpdateDlgHdr(
                      (struct DLGTEMPLATE *)P[0],
                      a1,
                      v42,
                      v6,
                      *((_BYTE *)a1 + 112) + (*((_QWORD *)a1 + 3) != 0) + ((_DWORD)hModule != 0),
                      v94,
                      v40,
                      v32,
                      v31,
                      *((unsigned __int16 **)a1 + 4),
                      v92[0]);
          v44 = *((unsigned __int16 *)a1 + 76);
          v45 = (struct DLGITEMTEMPLATE *)updated;
          v46 = (unsigned int)(14 * v44 + 2) >> 2;
          v47 = v32 - v46 - v79;
          v48 = GetDpiForSystem(v44, v46);
          v49 = GetDpiDependentMetric(2, v48);
          v50 = MB_AddPushButtons(
                  v45,
                  a1,
                  v47,
                  v95
                - ((*((unsigned __int16 *)a1 + 77) + 8 * (unsigned int)*((unsigned __int16 *)a1 + 77) + 4) >> 3)
                - v49);
          v51 = (__int16)hModule;
          if ( (_DWORD)hModule )
          {
            LOWORD(hModule) = -1;
            v67 = 14 * *((unsigned __int16 *)a1 + 77);
            v68 = 14 * *((unsigned __int16 *)a1 + 76);
            WORD1(hModule) = v51;
            v50 = MB_UpdateDlgItem(
                    (struct DLGITEMTEMPLATE *)v50,
                    a1,
                    20,
                    1342308355,
                    0,
                    (unsigned int)(v68 + 2) >> 2,
                    (unsigned int)(v67 + 4) >> 3,
                    0,
                    0,
                    (unsigned __int16 *)&hModule,
                    2u,
                    130);
          }
          Src = (unsigned __int16 *)*((_QWORD *)a1 + 3);
          if ( Src )
          {
            if ( v96 < v80 )
              v63 = (v80 - v96) / 2;
            else
              v63 = 0;
            if ( (v3 & 0x80000) != 0 )
            {
              v69 = 1342316674;
              v70 = v32 - DpiDependentMetric - v81;
            }
            else
            {
              v69 = 1342316672;
              v70 = v73 + ((7 * (unsigned int)*((unsigned __int16 *)a1 + 76) + 2) >> 2);
            }
            v71 = -1;
            do
              ++v71;
            while ( Src[v71] );
            MB_UpdateDlgItem(
              (struct DLGITEMTEMPLATE *)v50,
              a1,
              -1,
              v69,
              v6,
              v70,
              v63 + ((14 * (unsigned int)*((unsigned __int16 *)a1 + 77) + 4) >> 3),
              v81,
              v96,
              Src,
              v71,
              130);
          }
          v53 = LoadIcoCur(0, (PCWSTR)0x7F00, (unsigned __int16 *)1, 0, 0, 0x8040u);
          v54 = NtUserSetCursor(v53);
          v55 = *((_BYTE *)a1 + 40) >= 0;
          v56 = v54;
          *((_QWORD *)a1 + 6) = IcoCur;
          if ( v55 && (*((_WORD *)a1 + 20) & 0xF0) != 0 )
            NtUserMessageBeep(*((_WORD *)a1 + 20) & 0xF0);
          v57 = P[0];
          v58 = InternalDialogBox(
                  hmodUser,
                  (struct DLGTEMPLATE *)P[0],
                  v90,
                  (__int64 (*)(HWND, unsigned int, unsigned __int64, __int64))MB_DlgProc,
                  (__int64)a1,
                  0);
          v5 = 0;
          if ( v58 != -1 )
            v5 = v58;
          if ( (v3 & 0xF) == 0 )
            v5 = v5;
          if ( v56 )
            NtUserSetCursor(v56);
          RtlFreeHeap(pUserHeap, 0, v57);
        }
        else
        {
          v5 = v85;
        }
        goto LABEL_45;
      }
    }
    LODWORD(hModule) = 32513;
LABEL_13:
    v19 = ((__int64 (*)(void))GetDpiForSystem)();
    v73 = 3 * v16 + GetDpiDependentMetric(5, v19);
    v20 = ((__int64 (*)(void))GetDpiForSystem)();
    v21 = GetDpiDependentMetric(6, v20);
    v80 = v21;
    goto LABEL_14;
  }
LABEL_45:
  if ( v86 )
    RtlFreeHeap(pUserHeap, 0, v86);
  if ( v8 )
    RtlFreeHeap(pUserHeap, 0, v8);
  return v5;
}

```

## disassembly

```asm
0x1800293a0  push    rbp
0x1800293a2  push    rbx
0x1800293a3  push    rsi
0x1800293a4  push    rdi
0x1800293a5  push    r12
0x1800293a7  push    r13
0x1800293a9  push    r14
0x1800293ab  push    r15
0x1800293ad  lea     rbp, [rsp-1Fh]
0x1800293b2  sub     rsp, 0E8h
0x1800293b9  xor     edx, edx
0x1800293bb  mov     rsi, rcx
0x1800293be  mov     rcx, [rcx+10h]
0x1800293c2  mov     qword ptr [rbp+57h+sz.cx], rdx
0x1800293c6  mov     rax, gs:30h
0x1800293cf  mov     [rbp+57h+var_A4], edx
0x1800293d2  mov     [rbp+57h+arg_18], edx
0x1800293d5  mov     [rbp+57h+arg_8], edx
0x1800293d8  mov     [rbp+57h+arg_10], edx
0x1800293db  mov     [rbp+57h+hModule], rcx
0x1800293df  cmp     [rax+78h], rdx
0x1800293e3  jz      loc_18002997F
0x1800293e9  mov     r12d, [rsi+28h]
0x1800293ed  lea     rbx, dword_1800AA33C
0x1800293f4  mov     r15d, r12d
0x1800293f7  mov     [rbp+57h+var_8C], edx
0x1800293fa  shr     r15d, 7
0x1800293fe  mov     r14d, edx
0x180029401  and     r15d, 1000h
0x180029408  mov     [rbp+57h+var_88], rdx
0x18002940c  test    qword ptr [rsi+20h], 0FFFFFFFFFFFF0000h
0x180029414  mov     rdi, rdx
0x180029417  mov     r13, rdx
0x18002941a  jz      loc_18009A8DD
0x180029420  test    qword ptr [rsi+18h], 0FFFFFFFFFFFF0000h
0x180029428  mov     rdi, [rbp+57h+hModule]
0x18002942c  jz      loc_18009A937
0x180029432  mov     rbx, [rsi+18h]
0x180029436  mov     eax, r12d
0x180029439  and     eax, 100000h
0x18002943e  jnz     loc_1800299B4
0x180029444  xor     ecx, ecx
0x180029446  test    rbx, rbx
0x180029449  jnz     loc_180029997
0x18002944f  mov     ebx, r12d
0x180029452  and     ebx, 0F0h
0x180029458  cmp     ebx, 80h
0x18002945e  jnz     loc_180029947
0x180029464  mov     rdx, [rsi+30h]; SourceString
0x180029468  lea     r8d, [rbx-7Dh]; unsigned __int16 *
0x18002946c  mov     [rsp+120h+var_F8], 8040h; unsigned int
0x180029474  xor     r9d, r9d; unsigned int
0x180029477  mov     dword ptr [rsp+120h+var_100], ecx; unsigned int
0x18002947b  mov     rcx, rdi; hModule
0x18002947e  call    ?LoadIcoCur@@YAPEAUHICON__@@PEAUHINSTANCE__@@PEBGPEAGKKI@Z; LoadIcoCur(HINSTANCE__ *,ushort const *,ushort *,ulong,ulong,uint)
0x180029483  mov     [rbp+57h+var_70], rax
0x180029487  mov     rax, [rsi+8]
0x18002948b  xor     edx, edx
0x18002948d  xor     ecx, ecx
0x18002948f  mov     [rbp+57h+var_68], rax
0x180029493  lea     r8d, [rdx+3]
0x180029497  call    cs:__imp_NtUserGetDCEx
0x18002949d  mov     rdi, rax
0x1800294a0  test    rax, rax
0x1800294a3  jz      loc_18002995B
0x1800294a9  call    GetDpiForSystem
0x1800294ae  mov     ecx, eax; unsigned int
0x1800294b0  call    ?GetMessageBoxFontForDpi@@YAPEAUHFONT__@@I@Z; GetMessageBoxFontForDpi(uint)
0x1800294b5  mov     rdx, rax; h
0x1800294b8  mov     [rbp+57h+h], rax
0x1800294bc  mov     rcx, rdi; hdc
0x1800294bf  call    cs:__imp_SelectObject
0x1800294c5  lea     r9, [rbp+57h+var_B8]; LONG *
0x1800294c9  mov     [rbp+57h+var_B8], 0
0x1800294d0  xor     r8d, r8d; lptm
0x1800294d3  mov     [rbp+57h+P], rax
0x1800294d7  xor     edx, edx; h
0x1800294d9  mov     rcx, rdi; hdc
0x1800294dc  call    ?UserGetCharDimensionsEx@@YAHPEAUHDC__@@PEAUHFONT__@@PEAUtagTEXTMETRICW@@PEAH@Z; UserGetCharDimensionsEx(HDC__ *,HFONT__ *,tagTEXTMETRICW *,int *)
0x1800294e1  xor     ecx, ecx
0x1800294e3  mov     edx, eax
0x1800294e5  cmp     cx, ax
0x1800294e8  jz      loc_1800299BB
0x1800294ee  movzx   eax, word ptr [rbp+57h+var_B8]
0x1800294f2  mov     rcx, rdi; hdc
0x1800294f5  mov     [rsi+98h], dx
0x1800294fc  movzx   edx, dx; unsigned int
0x1800294ff  mov     [rsi+9Ah], ax
0x180029506  call    ?MB_GetMaxButtonSize@@YAGPEAUHDC__@@I@Z; MB_GetMaxButtonSize(HDC__ *,uint)
0x18002950b  movzx   r14d, word ptr [rsi+98h]
0x180029513  mov     edx, [rsi+70h]
0x180029516  movzx   r8d, ax
0x18002951a  mov     [rsi+5Ah], r8w
0x18002951f  imul    r8d, edx
0x180029523  lea     ecx, ds:2[r14*4]
0x18002952b  add     ecx, r14d
0x18002952e  lea     eax, [rdx-1]
0x180029531  shr     ecx, 2
0x180029534  imul    eax, ecx
0x180029537  add     eax, r8d
0x18002953a  mov     [rbp+57h+var_AC], eax
0x18002953d  sub     ebx, 10h
0x180029540  jnz     loc_1800299D3
0x180029546  mov     dword ptr [rbp+57h+hModule], 7F01h
0x18002954d  call    GetDpiForSystem
0x180029552  mov     edx, eax
0x180029554  mov     ecx, 5
0x180029559  call    GetDpiDependentMetric
0x18002955e  lea     ecx, [r14+r14*2]
0x180029562  add     eax, ecx
0x180029564  mov     [rbp+57h+var_C0], eax
0x180029567  call    GetDpiForSystem
0x18002956c  mov     edx, eax
0x18002956e  mov     ecx, 6
0x180029573  call    GetDpiDependentMetric
0x180029578  mov     r14d, eax
0x18002957b  mov     [rbp+57h+var_A8], eax
0x18002957e  xor     ebx, ebx
0x180029580  mov     rcx, [rsi+8]; HWND
0x180029584  mov     edx, 1; unsigned int
0x180029589  call    ?GetDialogMonitor@@YAPEAUtagMONITOR@@PEAUHWND__@@K@Z; GetDialogMonitor(HWND__ *,ulong)
0x18002958e  mov     rdx, rax
0x180029591  mov     [rbp+57h+var_78], rax
0x180029595  lea     rcx, [rbp+57h+var_50]
0x180029599  call    GetMonitorWorkRect
0x18002959e  mov     ecx, [rax]
0x1800295a0  mov     [rbp+57h+var_BC], ecx
0x1800295a3  mov     ecx, [rax+4]
0x1800295a6  mov     [rbp+57h+var_90], ecx
0x1800295a9  mov     ecx, [rax+8]
0x1800295ac  mov     eax, [rax+0Ch]
0x1800295af  mov     [rbp+57h+var_B0], eax
0x1800295b2  mov     [rbp+57h+var_B4], ecx
0x1800295b5  call    GetDpiServerInfoForCurrentThread
0x1800295ba  mov     rcx, rdi; hdc
0x1800295bd  mov     rdx, [rax+8]; h
0x1800295c1  call    cs:__imp_SelectObject
0x1800295c7  mov     rdx, [rsi+20h]; lpString
0x1800295cb  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800295cf  inc     rax
0x1800295d2  cmp     [rdx+rax*2], bx
0x1800295d6  jnz     short loc_1800295CF
0x1800295d8  lea     r9, [rbp+57h+sz]; lpsz
0x1800295dc  mov     qword ptr [rbp+57h+var_50], rax
0x1800295e0  mov     r8d, eax; c
0x1800295e3  mov     rcx, rdi; hdc
0x1800295e6  call    cs:__imp_GetTextExtentPointW
0x1800295ec  call    GetDpiForSystem
0x1800295f1  mov     edx, eax
0x1800295f3  mov     ecx, 0Ch
0x1800295f8  call    GetDpiDependentMetric
0x1800295fd  mov     ecx, [rbp+57h+sz.cx]
0x180029600  mov     rdx, [rbp+57h+h]; h
0x180029604  mov     [rbp+57h+var_A0], eax
0x180029607  lea     ebx, [rcx+rax*2]
0x18002960a  mov     rcx, rdi; hdc
0x18002960d  call    cs:__imp_SelectObject
0x180029613  mov     r9d, [rbp+57h+var_C0]; int
0x180029617  lea     rax, [rbp+57h+arg_18]
0x18002961b  mov     rcx, [rbp+57h+var_78]; struct tagMONITOR *
0x18002961f  mov     r8, rsi; struct _MSGBOXDATA *
0x180029622  mov     [rsp+120h+var_D0], rax; int *
0x180029627  mov     rdx, rdi; HDC
0x18002962a  lea     rax, [rbp+57h+var_A4]
0x18002962e  mov     [rsp+120h+Src], rax; int *
0x180029633  lea     rax, [rbp+57h+arg_10]
0x180029637  mov     [rsp+120h+var_E0], rax; int *
0x18002963c  lea     rax, [rbp+57h+arg_8]
0x180029640  mov     [rsp+120h+var_E8], rax; int *
0x180029645  mov     eax, [rbp+57h+var_AC]
0x180029648  mov     [rsp+120h+var_F0], ebx; int
0x18002964c  mov     [rsp+120h+var_F8], eax; int
0x180029650  mov     dword ptr [rsp+120h+var_100], r14d; int
0x180029655  call    ?MB_CalcDialogSize@@YAXPEAUtagMONITOR@@PEAUHDC__@@PEAU_MSGBOXDATA@@HHHHPEAH333@Z; MB_CalcDialogSize(tagMONITOR *,HDC__ *,_MSGBOXDATA *,int,int,int,int,int *,int *,int *,int *)
0x18002965a  mov     rax, [rbp+57h+P]
0x18002965e  xor     ebx, ebx
0x180029660  test    rax, rax
0x180029663  jnz     loc_180029A0A
0x180029669  mov     rcx, [rbp+57h+h]; ho
0x18002966d  call    cs:__imp_DeleteObject
0x180029673  mov     rcx, rdi
0x180029676  call    cs:__imp_NtUserReleaseDC
0x18002967c  movzx   ecx, word ptr [rsi+9Ah]
0x180029683  mov     r8d, [rbp+57h+arg_18]
0x180029687  cmp     r14d, r8d
0x18002968a  mov     edi, [rbp+57h+arg_10]
0x18002968d  cmovg   r8d, r14d
0x180029691  mov     [rsi+88h], ebx
0x180029697  mov     r14d, [rbp+57h+arg_8]
0x18002969b  imul    edx, ecx, 0Eh
0x18002969e  mov     [rsi+90h], r14d
0x1800296a5  add     edx, 4
0x1800296a8  shr     edx, 3
0x1800296ab  lea     eax, [r8+rdx*2]
0x1800296af  mov     [rsi+8Ch], eax
0x1800296b5  lea     eax, ds:4[rcx*8]
0x1800296bc  add     eax, ecx
0x1800296be  shr     eax, 3
0x1800296c1  add     eax, edx
0x1800296c3  lea     eax, [r8+rax*2]
0x1800296c7  mov     r8d, [rbp+57h+var_BC]
0x1800296cb  add     eax, edx
0x1800296cd  mov     [rsi+94h], eax
0x1800296d3  mov     rax, gs:30h
0x1800296dc  mov     rcx, [rax+820h]
0x1800296e3  mov     eax, [rbp+57h+var_B4]
0x1800296e6  sub     eax, r14d
0x1800296e9  mov     dword ptr [rbp+57h+h], eax
0x1800296ec  add     eax, r8d
0x1800296ef  mov     ebx, [rcx+30h]
0x1800296f2  cdq
0x1800296f3  mov     ecx, 2
0x1800296f8  idiv    ecx
0x1800296fa  mov     ecx, [rbp+57h+var_A0]
0x1800296fd  imul    ecx, ebx
0x180029700  add     eax, ecx
0x180029702  cmp     eax, r8d
0x180029705  cmovle  eax, r8d
0x180029709  mov     [rbp+57h+arg_8], eax
0x18002970c  mov     eax, [rbp+57h+var_B0]
0x18002970f  sub     eax, edi
0x180029711  mov     [rbp+57h+var_BC], eax
0x180029714  call    GetDpiForSystem
0x180029719  mov     edx, eax
0x18002971b  mov     ecx, 0Dh
0x180029720  call    GetDpiDependentMetric
0x180029725  mov     r8d, [rbp+57h+var_90]
0x180029729  mov     r10d, 2
0x18002972f  mov     r9d, [rbp+57h+var_BC]
0x180029733  imul    ebx, eax
0x180029736  lea     eax, [r8+r9]
0x18002973a  cdq
0x18002973b  idiv    r10d
0x18002973e  add     ebx, eax
0x180029740  mov     eax, [rbp+57h+arg_8]
0x180029743  cmp     ebx, r8d
0x180029746  cmovle  ebx, r8d
0x18002974a  add     eax, r14d
0x18002974d  cmp     eax, [rbp+57h+var_B4]
0x180029750  jg      loc_180029A1B
0x180029756  lea     eax, [rbx+rdi]
0x180029759  cmp     eax, [rbp+57h+var_B0]
0x18002975c  jg      loc_180029A29
0x180029762  mov     rcx, rsi; struct _MSGBOXDATA *
0x180029765  call    ?MB_FindDlgTemplateSize@@YAIPEAU_MSGBOXDATA@@@Z; MB_FindDlgTemplateSize(_MSGBOXDATA *)
0x18002976a  mov     rcx, cs:pUserHeap; HeapHandle
0x180029771  mov     edx, 8; Flags
0x180029776  mov     r8d, eax; Size
0x180029779  call    cs:__imp_RtlAllocateHeap
0x18002977f  mov     [rbp+57h+P], rax
0x180029783  mov     r10, rax
0x180029786  test    rax, rax
0x180029789  jz      loc_180029979
0x18002978f  mov     ecx, r12d
0x180029792  mov     eax, 80C801C5h
0x180029797  and     ecx, 3000h
0x18002979d  mov     r8d, 80C80347h
0x1800297a3  cmp     ecx, 1000h
0x1800297a9  cmovnz  r8d, eax
0x1800297ad  bt      r12d, 10h
0x1800297b2  jnb     short loc_1800297B9
0x1800297b4  bts     r8d, 9; int
0x1800297b9  xor     eax, eax
0x1800297bb  mov     r9d, r15d; int
0x1800297be  cmp     dword ptr [rbp+57h+hModule], eax
0x1800297c1  mov     rdx, rsi; struct _MSGBOXDATA *
0x1800297c4  setnz   cl
0x1800297c7  cmp     [rsi+18h], rax
0x1800297cb  setnz   al
0x1800297ce  add     cl, al
0x1800297d0  mov     rax, qword ptr [rbp+57h+var_50]
0x1800297d4  add     cl, [rsi+70h]
0x1800297d7  mov     dword ptr [rsp+120h+var_D0], eax; unsigned int
0x1800297db  mov     rax, [rsi+20h]
0x1800297df  mov     [rsp+120h+Src], rax; Src
0x1800297e4  mov     eax, [rbp+57h+arg_8]
0x1800297e7  mov     dword ptr [rsp+120h+var_E0], edi; int
0x1800297eb  mov     dword ptr [rsp+120h+var_E8], r14d; int
0x1800297f0  mov     [rsp+120h+var_F0], ebx; int
0x1800297f4  mov     [rsp+120h+var_F8], eax; int
0x1800297f8  mov     [rsp+120h+var_100], cl; char
0x1800297fc  mov     rcx, r10; struct DLGTEMPLATE *
0x1800297ff  call    ?MB_UpdateDlgHdr@@YAPEAEPEAUDLGTEMPLATE@@PEAU_MSGBOXDATA@@JJEHHHHPEAGI@Z; MB_UpdateDlgHdr(DLGTEMPLATE *,_MSGBOXDATA *,long,long,uchar,int,int,int,int,ushort *,uint)
0x180029804  movzx   ecx, word ptr [rsi+98h]
0x18002980b  mov     ebx, r14d
0x18002980e  imul    edx, ecx, 0Eh
0x180029811  mov     rdi, rax
0x180029814  add     edx, 2
0x180029817  shr     edx, 2
0x18002981a  sub     ebx, edx
0x18002981c  sub     ebx, [rbp+57h+var_AC]
0x18002981f  call    GetDpiForSystem
0x180029824  mov     edx, eax
0x180029826  mov     ecx, 2
0x18002982b  call    GetDpiDependentMetric
0x180029830  movzx   ecx, word ptr [rsi+9Ah]
0x180029837  mov     r8d, ebx; unsigned int
0x18002983a  mov     r9d, [rbp+57h+arg_10]
0x18002983e  lea     edx, ds:4[rcx*8]
0x180029845  add     edx, ecx
  ... truncated ...
```
