# RealDefWindowProcWorker(tagWND *,uint,unsigned __int64,__int64,ulong)

- ea: `0x18000f140`
- end: `0x18001048f`
- name: `?RealDefWindowProcWorker@@YA_JPEAUtagWND@@I_K_JK@Z`
- size: `4943`
- prototype: `__int64 __fastcall(struct tagWND *, unsigned int, unsigned __int64, __int64, unsigned int)`
- caller_count: `5`
- callee_count: `28`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800084f0`
- `0x18000efb0`
- `0x180010950`
- `0x180010980`
- `0x180010c00`

## callees

- `0x1800060e0`
- `0x18000a9f0`
- `0x18000ac60`
- `0x18000acb0`
- `0x18000b620`
- `0x18000be40`
- `0x18000ce70`
- `0x18000cf20`
- `0x18000d9f0`
- `0x18000f140`
- `0x1800111f4`
- `0x180011800`
- `0x180017a5c`
- `0x180020990`
- `0x180020b70`
- `0x1800219d0`
- `0x180021e10`
- `0x1800222b0`
- `0x18003c588`
- `0x18004e41c`
- `0x18004e9b4`
- `0x18004f69c`
- `0x1800533e0`
- `0x18005b31c`
- `0x180074b54`
- `0x180096dad`
- `0x180096e00`
- `0x1800a2010`

## import_xrefs

- `win32u!NtUserSetTaskmanWindow` at `0x18000fcd0`
- `win32u!NtUserSetTaskmanWindow` at `0x18000fcd0`
- `win32u!NtUserGetModernAppWindow` at `0x18000facc`
- `win32u!NtUserGetModernAppWindow` at `0x18000facc`
- `win32u!NtUserPostMessage` at `0x18000fe7d`
- `win32u!NtUserPostMessage` at `0x18000fe7d`
- `win32u!NtUserAutoPromoteMouseInPointer` at `0x18000fa46`
- `win32u!NtUserAutoPromoteMouseInPointer` at `0x18000fa46`
- `win32u!NtUserMessageCall` at `0x18000fea2`
- `win32u!NtUserMessageCall` at `0x180098e4b`
- `win32u!NtUserMessageCall` at `0x18000fea2`
- `win32u!NtUserMessageCall` at `0x180098e4b`
- `win32u!NtUserSetDpiForWindow` at `0x18001008a`
- `win32u!NtUserSetDpiForWindow` at `0x18001008a`
- `ntdll!RtlUnicodeToMultiByteSize` at `0x18000f9b8`
- `ntdll!RtlUnicodeToMultiByteSize` at `0x18000f9b8`
- `ntdll!RtlUnicodeToMultiByteN` at `0x18000f5a9`
- `ntdll!RtlUnicodeToMultiByteN` at `0x18000f5a9`
- `ntdll!RtlFreeHeap` at `0x18000f6a2`
- `ntdll!RtlFreeHeap` at `0x18000f6a2`
- `ntdll!RtlAllocateHeap` at `0x18000f634`
- `ntdll!RtlAllocateHeap` at `0x180098cd9`
- `ntdll!RtlAllocateHeap` at `0x18000f634`
- `ntdll!RtlAllocateHeap` at `0x180098cd9`
- `api-ms-win-core-localization-l1-2-0!IsDBCSLeadByteEx` at `0x18000ffd6`
- `api-ms-win-core-localization-l1-2-0!IsDBCSLeadByteEx` at `0x180098d2b`
- `api-ms-win-core-localization-l1-2-0!IsDBCSLeadByteEx` at `0x18000ffd6`
- `api-ms-win-core-localization-l1-2-0!IsDBCSLeadByteEx` at `0x180098d2b`
- `GDI32!SetBkColor` at `0x18000f3c6`
- `GDI32!SetBkColor` at `0x18000f9e2`
- `GDI32!SetBkColor` at `0x18000f3c6`
- `GDI32!SetBkColor` at `0x18000f9e2`
- `GDI32!SetTextColor` at `0x18000f3dc`
- `GDI32!SetTextColor` at `0x18000f9f5`
- `GDI32!SetTextColor` at `0x18000f3dc`
- `GDI32!SetTextColor` at `0x18000f9f5`

## pseudocode

```c
__int64 __fastcall RealDefWindowProcWorker(
        struct tagWND *a1,
        unsigned int a2,
        unsigned __int64 a3,
        LPARAM a4,
        unsigned int a5)
{
  HWND v5; // r10
  unsigned __int64 v7; // rbx
  unsigned __int64 v8; // r14
  HGESTUREINFO v9; // r12
  WPARAM v10; // r15
  __int64 v11; // rdx
  __int64 result; // rax
  bool v13; // zf
  unsigned int v14; // eax
  __int64 v15; // rcx
  ULONG v16; // r13d
  const WCHAR *v17; // rsi
  unsigned int v18; // eax
  __int64 v19; // r15
  __int64 v20; // rdx
  int v21; // eax
  char v22; // al
  ULONG v23; // eax
  WCHAR *v24; // r13
  __int64 v25; // rax
  int v26; // r15d
  int v27; // edi
  char *v28; // r13
  HWND v29; // rax
  struct tagWND *v30; // rax
  NTSTATUS v31; // eax
  unsigned __int64 v32; // rax
  unsigned __int64 v33; // rdi
  ULONG v34; // eax
  unsigned __int16 *v35; // rax
  unsigned __int16 *v36; // r13
  unsigned __int16 v37; // ax
  HWND i; // rdi
  unsigned __int64 v39; // rdx
  HWND v40; // rcx
  HWND v41; // rax
  struct tagWND *v42; // rax
  struct tagWND *v43; // rsi
  __int64 v44; // rdi
  __int16 v45; // bx
  int v46; // ecx
  struct tagWND *v47; // r13
  char v48; // r10
  __int16 v49; // ax
  __int64 v50; // r8
  __int64 v51; // rax
  int v52; // eax
  int v53; // edx
  __int64 (__fastcall *v54)(HWND, _QWORD); // rax
  HWND v55; // rcx
  __int64 v56; // rcx
  __int64 v57; // rax
  __int64 v58; // rbx
  __int64 v59; // rdi
  __int64 v60; // rax
  __int64 v61; // rax
  char *v62; // rsi
  HWND v63; // r13
  __int64 v64; // rax
  char *v65; // rsi
  HWND v66; // r13
  UINT v67; // edx
  __int64 v68; // rax
  HWND v69; // r13
  HWND *v70; // rsi
  __int64 v71; // rbx
  HWND v72; // rcx
  int v73; // ecx
  __int64 v74; // rdx
  int v75; // ecx
  int v76; // eax
  int v77; // ecx
  __int64 v78; // rbx
  char *v79; // rax
  HWND *v80; // rbx
  __int64 v81; // rax
  char *v82; // rsi
  __int64 v83; // rax
  struct tagWND *v84; // r13
  __int64 v85; // rdi
  UINT v86; // edx
  HWND v87; // rcx
  __int64 v88; // rax
  char *v89; // rsi
  HWND v90; // r13
  ULONG v91; // eax
  HGESTUREINFO Heap; // rax
  HGESTUREINFO v93; // r13
  BYTE v94; // dl
  __int64 v95; // rcx
  __int64 v96; // rax
  __int64 v97; // rcx
  unsigned __int16 MouseKeyState; // ax
  HWND hWnd; // [rsp+40h] [rbp-31h]
  ULONG ResultSize[2]; // [rsp+48h] [rbp-29h] BYREF
  unsigned __int64 v101; // [rsp+50h] [rbp-21h] BYREF
  PVOID P[2]; // [rsp+58h] [rbp-19h] BYREF
  __int64 v103; // [rsp+68h] [rbp-9h]

  v5 = *(HWND *)a1;
  v7 = a2;
  hWnd = *(HWND *)a1;
  v8 = 1;
  v9 = (HGESTUREINFO)a4;
  v10 = a3;
  v11 = (unsigned int)(1 << (a2 & 7));
  if ( (unsigned int)v7 <= dword_1800C9588 && ((unsigned __int8)v11 & *(_BYTE *)((v7 >> 3) + qword_1800C9590)) != 0 )
  {
    if ( (unsigned int)v7 >= 0x400 )
      return NtUserMessageCall(v5, (unsigned int)v7, a3, a4, 0, 670, a5);
    _mm_lfence();
    return ((__int64 (__fastcall *)(HWND, _QWORD))gapfnScSendMessage[(unsigned __int8)MessageTable[v7]])(
             v5,
             (unsigned int)v7);
  }
  if ( (unsigned int)v7 > dword_1800C9598
    || ((unsigned __int8)v11 & *(_BYTE *)(((unsigned __int64)(unsigned int)v7 >> 3) + qword_1800C95A0)) == 0
    || (_DWORD)v7 == 283 )
  {
    return 0;
  }
  if ( (_DWORD)v7 != 13 )
  {
    if ( (_DWORD)v7 == 132 )
      return (int)FindNCHit(a1, (unsigned int)a4);
    if ( (unsigned int)v7 <= 0x109 )
    {
      if ( (_DWORD)v7 != 265 )
      {
        switch ( (int)v7 )
        {
          case 6:
            if ( (_WORD)a3 )
              goto LABEL_109;
            if ( !(unsigned int)IsShellFrameWindow(v5) || !NtUserGetModernAppWindow(hWnd) )
              return 0;
            _mm_lfence();
            v54 = (__int64 (__fastcall *)(HWND, _QWORD))gapfnScSendMessage[(unsigned __int8)MessageTable[(unsigned int)v7]];
            v55 = hWnd;
            return v54(v55, (unsigned int)v7);
          case 14:
            v23 = *((_DWORD *)a1 + 46);
            if ( !v23 )
              return 0;
            v24 = 0;
            ResultSize[0] = 0;
            if ( !a5 )
              return v23 >> 1;
            v56 = *((_QWORD *)a1 + 24);
            if ( v56 )
              v24 = (WCHAR *)((char *)a1 + v56 - *((_QWORD *)a1 + 1));
            RtlUnicodeToMultiByteSize(ResultSize, v24, v23);
            return ResultSize[0];
          case 17:
          case 19:
            return 1;
          case 24:
            if ( a4 )
              goto LABEL_109;
            return 0;
          case 25:
            goto LABEL_130;
          case 33:
            if ( (*((_BYTE *)a1 + 31) & 0xC0) != 0x40
              || (v51 = *((_QWORD *)a1 + 6)) == 0
              || (result = SendMessageWorker(
                             (struct tagWND *)((char *)a1 + v51 - *((_QWORD *)a1 + 1)),
                             0x21u,
                             a3,
                             (HTOUCHINPUT)a4,
                             a5)) == 0 )
            {
              if ( (_DWORD)v9 == 33619970 )
                return 3;
              else
                return 1;
            }
            return result;
          case 46:
          case 47:
            return -1;
          case 70:
            v13 = (*(_BYTE *)(a4 + 32) & 1) == 0;
            goto LABEL_16;
          case 71:
            if ( (*(_DWORD *)(a4 + 32) & 0x1000) == 0 )
            {
              v25 = *((_QWORD *)a1 + 6);
              v26 = *((_DWORD *)a1 + 26);
              v27 = *((_DWORD *)a1 + 27);
              if ( v25 )
                v28 = (char *)a1 + v25 - *((_QWORD *)a1 + 1);
              else
                v28 = 0;
              if ( v28 != (char *)GetCurrentThreadDesktopWindow() )
              {
                v27 -= *((_DWORD *)v28 + 27);
                v26 -= *((_DWORD *)v28 + 26);
              }
              SendMessageWorker(
                a1,
                3u,
                0,
                (HTOUCHINPUT)((unsigned __int16)v26 | (unsigned __int64)(unsigned int)(v27 << 16)),
                a5);
            }
            if ( ((_DWORD)v9[8] & 0x8800) != 0x800 )
            {
              v22 = *((_BYTE *)a1 + 31);
              *(_OWORD *)P = 0;
              if ( (v22 & 0x20) == 0 )
                v8 = 2LL * (v22 & 1);
              GetClientRect(a1, P);
              SendMessageWorker(
                a1,
                5u,
                v8,
                (HTOUCHINPUT)((unsigned __int16)(LOWORD(P[1]) - LOWORD(P[0]))
                            | ((unsigned __int16)(WORD2(P[1]) - WORD2(P[0])) << 16)),
                a5);
            }
            return 0;
          case 83:
            v79 = (char *)a1 + 48;
            if ( (*((_BYTE *)a1 + 31) & 0xC0) != 0x40 )
              v79 = (char *)a1 + 64;
            if ( !*(_QWORD *)v79 )
              return 0;
            v80 = (HWND *)((char *)a1 + *(_QWORD *)v79 - *((_QWORD *)a1 + 1));
            if ( v80 == (HWND *)GetCurrentThreadDesktopWindow() )
              return 0;
            return SendMessageW(*v80, 0x53u, v10, (LPARAM)v9);
          case 85:
            if ( a4 != 3 )
              return 0;
            return 2LL - ((*((_BYTE *)a1 + 19) & 0x20) != 0);
          case 90:
            if ( a4 )
            {
              if ( a4 == 1 )
              {
                result = _GetWindowLong(a1, a3, a5);
              }
              else
              {
                if ( a4 != 2 )
                  return 0;
                result = _GetWindowLongPtr(a1, a3, a5);
              }
            }
            else
            {
              result = _GetWindowWord(a1, a3);
            }
            break;
          case 123:
            if ( (*((_BYTE *)a1 + 31) & 0xC0) != 0x40 )
              return 0;
            v81 = *((_QWORD *)a1 + 6);
            if ( v81 && (v82 = (char *)a1 - *((_QWORD *)a1 + 1), &v82[v81]) )
              v66 = *(HWND *)&v82[v81];
            else
              v66 = 0;
            a3 = *(_QWORD *)a1;
            v67 = 123;
            goto LABEL_151;
          case 139:
            v74 = gpsi;
            v75 = *(unsigned __int16 *)a4 | (*(unsigned __int16 *)(a4 + 4) << 16);
            v103 = 0;
            v76 = *(unsigned __int16 *)(a4 + 8);
            LODWORD(P[1]) = v75;
            v77 = v76 | (*(unsigned __int16 *)(a4 + 12) << 16);
            P[0] = (PVOID)a3;
            HIDWORD(P[1]) = v77;
            if ( !*(_DWORD *)(gpsi + 928) )
            {
              NtUserSetTaskmanWindow(0);
              v74 = gpsi;
            }
            if ( SendMessageWorker(a1, *(_DWORD *)(v74 + 928), 5u, (HTOUCHINPUT)P, a5) )
            {
              *(_DWORD *)v9 = SLOWORD(P[1]);
              *((_DWORD *)v9 + 1) = SWORD1(P[1]);
              *((_DWORD *)v9 + 2) = SWORD2(P[1]);
              *((_DWORD *)v9 + 3) = SHIWORD(P[1]);
            }
            return 0;
          case 172:
            goto LABEL_205;
          case 256:
            if ( a3 == 121 )
              goto LABEL_109;
            goto LABEL_235;
          case 260:
            if ( (a4 & 0x20000000) != 0 || a3 == 121 )
              goto LABEL_109;
LABEL_235:
            v13 = a3 == 27;
LABEL_16:
            if ( v13 )
              goto LABEL_109;
            return 0;
          default:
            return 0;
        }
        return result;
      }
      return 0;
    }
    if ( (unsigned int)v7 > 0x20A )
    {
      if ( (unsigned int)v7 > 0x319 )
      {
        if ( (_DWORD)v7 == 841 && (_WORD)a3 )
        {
LABEL_109:
          _mm_lfence();
          v54 = (__int64 (__fastcall *)(HWND, _QWORD))gapfnScSendMessage[(unsigned __int8)*(__int16 *)((char *)&_ImageBase[(unsigned int)v7] + (_QWORD)(&word_1800A81BC - 3221225478LL))];
          v55 = *(HWND *)a1;
          return v54(v55, (unsigned int)v7);
        }
      }
      else
      {
        if ( (_DWORD)v7 == 793 )
        {
          if ( (*((_BYTE *)a1 + 31) & 0xC0) != 0x40 )
            return NtUserMessageCall(v5, 793, a3, a4, 0, 670, a5);
          v88 = *((_QWORD *)a1 + 6);
          if ( v88 && (v89 = (char *)a1 - *((_QWORD *)a1 + 1), &v89[v88]) )
            v90 = *(HWND *)&v89[v88];
          else
            v90 = 0;
          return SendMessageW(v90, 0x319u, a3, a4);
        }
        switch ( (int)v7 )
        {
          case 524:
LABEL_205:
            if ( WORD1(a3) == 1 )
            {
              v85 = 2147549184LL;
            }
            else
            {
              if ( WORD1(a3) != 2 )
                return 0;
              v85 = 2147614720LL;
            }
            if ( (_DWORD)v7 != 524 )
            {
              MouseKeyState = GetMouseKeyState();
              v5 = hWnd;
              LOWORD(v10) = MouseKeyState;
            }
            SendMessageWorker(a1, 0x319u, (unsigned __int64)v5, (HTOUCHINPUT)(v85 | (unsigned __int16)v10), a5);
            break;
          case 526:
            goto LABEL_146;
          case 536:
          case 537:
            return 1;
          case 554:
            return 1162627398;
          case 571:
          case 572:
          case 577:
          case 578:
          case 579:
          case 581:
          case 582:
          case 583:
          case 588:
          case 590:
          case 591:
            if ( (_WORD)a3 != 1 && (unsigned int)(v7 - 590) > 1 )
              goto LABEL_113;
            NtUserAutoPromoteMouseInPointer((unsigned int)v7);
            return 0;
          case 576:
            CloseTouchInputHandle((HTOUCHINPUT)a4);
            return 0;
          case 587:
            if ( (*((_BYTE *)a1 + 31) & 0xC0) != 0x40 )
              return -1;
            v83 = *((_QWORD *)a1 + 6);
            if ( v83 )
              v84 = (struct tagWND *)((char *)a1 + v83 - *((_QWORD *)a1 + 1));
            else
              v84 = 0;
            v96 = SendMessageWorker(v84, v7, a3, (HTOUCHINPUT)a4, a5);
            v97 = -1;
            if ( v96 )
              return v96;
            return v97;
          case 589:
            return 4293918720LL;
          case 626:
            CallWindowServiceCallback(v5);
            return 0;
          case 641:
            goto LABEL_57;
          case 642:
            goto LABEL_74;
          case 644:
            if ( LODWORD(NtCurrentTeb()->Win32ClientInfo[2]) >= 0x400 )
              return 0;
            return SendMessageWorker(a1, 0x280u, 0x123u, 0, a5);
          case 646:
            if ( a5 )
            {
              if ( IsDBCSLeadByteEx(LOWORD(NtCurrentTeb()->Win32ClientInfo[19]), BYTE1(a3)) )
              {
                PostMessageA(hWnd, 0x102u, BYTE1(v10), 1);
                v10 = (unsigned __int8)v10;
              }
              a4 = 1;
              a3 = v10;
              v86 = 258;
              v87 = hWnd;
LABEL_254:
              PostMessageA(v87, v86, a3, a4);
            }
            else
            {
              NtUserPostMessage(v5, 258, a3, 1);
            }
            return 0;
          case 647:
            if ( a3 == 4 )
              return 0;
            if ( a3 == 3 )
              goto LABEL_74;
LABEL_57:
            v29 = (HWND)((__int64 (__fastcall *)(HWND))off_1800C85D8[0])(v5);
            if ( v29 == hWnd )
              goto LABEL_220;
            v30 = ValidateHwndNoRip(v29);
            if ( !v30 )
              return 0;
            return SendMessageWorker(v30, v7, v10, (HTOUCHINPUT)v9, a5);
          case 648:
            if ( a3 == 6 )
              goto LABEL_74;
            return 0;
          case 656:
            v86 = 256;
            goto LABEL_211;
          case 657:
            v86 = 257;
LABEL_211:
            v87 = *(HWND *)a1;
            if ( a5 )
              goto LABEL_254;
            PostMessageW(v5, v86, a3, a4);
            return 0;
          case 717:
LABEL_113:
            CallNaturalInputHandler(v5, v7, a3, a4, 1);
            return 0;
          case 742:
            NtUserSetDpiForWindow(v5, (unsigned int)a3);
            return 0;
          default:
            return 0;
        }
      }
      return 0;
    }
    if ( (_DWORD)v7 == 522 )
    {
LABEL_146:
      if ( (*((_BYTE *)a1 + 31) & 0xC0) == 0x40 )
      {
        v64 = *((_QWORD *)a1 + 6);
        if ( v64 && (v65 = (char *)a1 - *((_QWORD *)a1 + 1), &v65[v64]) )
          v66 = *(HWND *)&v65[v64];
        else
          v66 = 0;
        v67 = v7;
LABEL_151:
        SendMessageW(v66, v67, a3, a4);
      }
      return 0;
    }
    switch ( (int)v7 )
    {
      case 269:
      case 270:
        goto LABEL_74;
      case 271:
        if ( (a4 & 0x800) == 0 )
          goto LABEL_74;
        v32 = ((__int64 (__fastcall *)(HWND))off_1800C85D0[0])(v5);
        v101 = v32;
        v33 = v32;
        if ( !v32 )
          goto LABEL_73;
        if ( a5 )
        {
          v91 = ((__int64 (__fastcall *)(unsigned __int64, __int64, _QWORD, _QWORD))off_1800C85B8[0])(v32, 2048, 0, 0);
          ResultSize[0] = v91;
          if ( v91 )
          {
            Heap = (HGESTUREINFO)RtlAllocateHeap(pUserHeap, 8u, v91 + 1LL);
            v93 = Heap;
            if ( Heap )
            {
              P[0] = Heap;
              ((void (__fastcall *)(unsigned __int64, __int64, HGESTUREINFO, _QWORD))off_1800C85B8[0])(
                v33,
                2048,
                Heap,
                ResultSize[0]);
              v94 = *(_BYTE *)v93;
              for ( i = hWnd; v94; v93 = (HGESTUREINFO)((char *)v93 + 1) )
              {
                if ( IsDBCSLeadByteEx(LOWORD(NtCurrentTeb()->Win32ClientInfo[19]), v94) )
                {
                  v95 = *((unsigned __int8 *)v93 + 1);
                  *(_QWORD *)ResultSize = (char *)v93 + 1;
                  if ( (_BYTE)v95 )
                  {
                    SendMessageA(hWnd, 0x286u, v95 | ((unsigned __int64)*(_BYTE *)v93 << 8), 1);
                    v93 = *(HGESTUREINFO *)ResultSize;
                  }
                }
                else
                {
                  SendMessageA(hWnd, 0x286u, *(_BYTE *)v93, 1);
                }
                v94 = *((_BYTE *)v93 + 1);
              }
              goto LABEL_71;
            }
          }
        }
        else
        {
          v34 = ((__int64 (__fastcall *)(unsigned __int64, __int64, _QWORD, _QWORD))off_1800C85C0[0])(v32, 2048, 0, 0);
          ResultSize[0] = v34;
          if ( v34 )
          {
            v35 = (unsigned __int16 *)RtlAllocateHeap(pUserHeap, 8u, v34 + 2LL);
            v36 = v35;
            if ( v35 )
            {
              P[0] = v35;
              ((void (__fastcall *)(unsigned __int64, __int64, unsigned __int16 *, _QWORD))off_1800C85C0[0])(
                v33,
                2048,
                v35,
                ResultSize[0]);
              v37 = *v36;
              for ( i = hWnd; *v36; v37 = *v36 )
              {
                ++v36;
                SendMessageW(hWnd, 0x286u, v37, 1);
              }
LABEL_71:
              RtlFreeHeap(pUserHeap, 0, P[0]);
              v39 = v101;
              v40 = i;
              goto LABEL_72;
            }
          }
        }
        v40 = hWnd;
        v39 = v33;
LABEL_72:
        ((void (__fastcall *)(HWND, unsigned __int64))off_1800C85E8[0])(v40, v39);
LABEL_73:
        v5 = hWnd;
LABEL_74:
        if ( (NtCurrentTeb()->Win32ClientInfo[3] & 0x200000000000000LL) == 0 )
        {
          v41 = (HWND)((__int64 (__fastcall *)(HWND))off_1800C85D8[0])(v5);
          if ( v41 == hWnd )
          {
LABEL_220:
            ImeWndProcWorker(a1, v7, v10, (__int64)v9, a5);
          }
          else
          {
            v42 = ValidateHwndNoRip(v41);
            v43 = v42;
            if ( v42 )
            {
              v44 = *(_QWORD *)(**((_QWORD **)v42 + 37) + 8LL);
              if ( v44 == ((__int64 (__fastcall *)(HWND))off_1800C85D0[0])(hWnd) )
                return SendMessageWorker(v43, v7, v10, (HTOUCHINPUT)v9, a5);
            }
          }
        }
        return 0;
      case 281:
        if ( (*((_BYTE *)a1 + 31) & 0xC0) != 0x40 )
          goto LABEL_179;
        v68 = *((_QWORD *)a1 + 6);
        v69 = 0;
        *(_QWORD *)ResultSize = 0;
        if ( v68 )
          v70 = (HWND *)((char *)a1 + v68 - *((_QWORD *)a1 + 1));
        else
          v70 = 0;
        v71 = GETPTI(v70, v11);
        if ( PtiCurrent() == v71 )
        {
          if ( v70 )
            v69 = *v70;
          return SendMessageW(v69, 0x119u, v10, (LPARAM)v9);
        }
        else
        {
          CopyGestureInfoHandle(v9, (HGESTUREINFO *)ResultSize);
          v101 = 0;
          v72 = 0;
          if ( v70 )
            v72 = *v70;
          if ( SendMessageTimeoutWorker(v72, 0x119u, v10, (__int64)v9, 2u, 0x12Cu, &v101, 0) )
          {
            CloseGestureInfoHandle(*(HGESTUREINFO *)ResultSize);
            return v101;
          }
          else
          {
            v9 = *(HGESTUREINFO *)ResultSize;
            v5 = hWnd;
LABEL_179:
            v78 = CallNaturalInputHandler(v5, 0x119u, v10, (__int64)v9, 1);
            CloseGestureInfoHandle(v9);
            return v78;
          }
        }
      case 282:
        if ( (*((_BYTE *)a1 + 31) & 0xC0) != 0x40 )
          return 0;
        v61 = *((_QWORD *)a1 + 6);
        if ( v61 && (v62 = (char *)a1 - *((_QWORD *)a1 + 1), &v62[v61]) )
          v63 = *(HWND *)&v62[v61];
        else
          v63 = 0;
        return SendMessageW(v63, 0x11Au, a3, a4);
      case 295:
        v45 = WORD1(a3);
        if ( (a3 & 0xFFF80000) != 0 || (unsigned __int16)a3 > 3u || a4 )
          return 0;
        if ( (_WORD)a3 == 3 )
        {
          if ( *(char *)gpsi < 0 )
            return 0;
          v46 = *(_DWORD *)(gpsi + 7004);
          if ( (v46 & 0x20) != 0 || v46 >= 0 || (GetAppCompatFlags2(1024) & 2) != 0 )
            return 0;
          v47 = 0;
          v48 = 3;
          HIBYTE(v49) = 0;
          LOBYTE(v49) = (*(_BYTE *)gpsi & 0x40) != 0;
          v50 = (unsigned __int16)(v49 + 1);
          v10 = v50 | 0x30000;
        }
        else
        {
          if ( *(char *)gpsi < 0
            || (v52 = *(_DWORD *)(gpsi + 7004), (v52 & 0x20) != 0)
            || v52 >= 0
            || (GetAppCompatFlags2(1024) & 2) != 0 )
          {
            v45 &= 0xFFFCu;
          }
          if ( !v45 )
            return 0;
          v47 = 0;
          v48 = v45;
          v53 = 0;
          LOWORD(v50) = v10;
          if ( (v45 & 1) == 0 )
          {
LABEL_101:
            if ( (v48 & 2) != 0 )
              v53 |= ((_WORD)v50 == 1) ^ (*((unsigned __int8 *)a1 + 27) >> 6) & 1;
            if ( (v48 & 4) != 0 )
              v53 |= ((_WORD)v50 == 1) ^ (*((unsigned __int8 *)a1 + 27) >> 2) & 1;
            if ( v53 )
            {
              if ( (*((_BYTE *)a1 + 31) & 0xC0) != 0x40 )
                return SendMessageWorker(a1, 0x128u, v10, 0, a5);
              v60 = *((_QWORD *)a1 + 6);
              if ( v60 )
                v47 = (struct tagWND *)((char *)a1 + v60 - *((_QWORD *)a1 + 1));
              return SendMessageWorker(v47, 0x127u, v10, 0, a5);
            }
            return 0;
          }
        }
        v53 = ((_WORD)v50 == 1) ^ (*((unsigned __int8 *)a1 + 27) >> 7);
        goto LABEL_101;
      case 297:
        return *((_BYTE *)a1 + 27) & 4
             | ((((unsigned __int64)*((unsigned __int8 *)a1 + 27) >> 2) | *((_BYTE *)a1 + 27) & 0x40) >> 5);
      case 306:
      case 310:
      case 312:
        v57 = 4628;
        v58 = 4816;
        goto LABEL_118;
      case 307:
      case 308:
LABEL_130:
        v57 = 4588;
        v58 = 4736;
LABEL_118:
        v59 = 4600;
        goto LABEL_119;
      case 309:
        v57 = 4628;
        v59 = 4640;
        v58 = 4816;
LABEL_119:
        v20 = gpsi;
        goto LABEL_120;
      case 311:
        v20 = gpsi;
        if ( *(_WORD *)(gpsi + 6996) < 8u
          || (v21 = *(_DWORD *)(gpsi + 4648), v21 != *(_DWORD *)(gpsi + 4568))
          || v21 == *(_DWORD *)(gpsi + 4588) )
        {
          SetBkColor((HDC)a3, *(_DWORD *)(gpsi + 4648));
          SetTextColor((HDC)v10, *(_DWORD *)(gpsi + 4628));
          return *(_QWORD *)(gpsi + 4944);
        }
        else
        {
          v57 = 4648;
          v59 = 4640;
          v58 = 4856;
LABEL_120:
          SetBkColor((HDC)a3, *(_DWORD *)(v57 + v20));
          SetTextColor((HDC)v10, *(_DWORD *)(v59 + gpsi));
          return *(_QWORD *)(v58 + gpsi);
        }
      case 517:
        if ( (*((_BYTE *)a1 + 26) & 0x40) != 0 )
          v73 = (unsigned __int16)(*((_WORD *)a1 + 56) - a4);
        else
          v73 = (unsigned __int16)(*((_WORD *)a1 + 52) + a4);
        SendMessageWorker(
          a1,
          0x7Bu,
          (unsigned __int64)v5,
          (HTOUCHINPUT)(((unsigned __int16)(*((_WORD *)a1 + 54) + WORD1(a4)) << 16) | v73),
          a5);
        return 0;
      default:
        return 0;
    }
  }
  if ( !a3 )
    return 0;
  v14 = *((_DWORD *)a1 + 46);
  if ( !v14 )
  {
    if ( a5 )
      *(_BYTE *)a4 = 0;
    else
      *(_WORD *)a4 = 0;
    return 0;
  }
  v15 = *((_QWORD *)a1 + 24);
  v16 = 0;
  if ( v15 )
    v17 = (const WCHAR *)((char *)a1 + v15 - *((_QWORD *)a1 + 1));
  else
    v17 = 0;
  v18 = v14 >> 1;
  v19 = (unsigned int)(a3 - 1);
  if ( a5 )
  {
    ResultSize[0] = 0;
    if ( (_DWORD)a3 != 1 )
    {
      if ( v18 )
      {
        if ( v17 )
        {
          if ( (int)v19 >= 0 )
          {
            v31 = RtlUnicodeToMultiByteN((PCHAR)a4, v19, ResultSize, v17, 2 * v18);
            if ( (int)(v31 + 0x80000000) < 0 || v31 == -2147483643 )
              v16 = ResultSize[0];
          }
        }
      }
    }
    *((_BYTE *)v9 + v16) = 0;
    return v16;
  }
  else
  {
    if ( v18 < (unsigned int)v19 )
      v19 = v18;
    memcpy_0((void *)a4, v17, 2 * v19);
    *((_WORD *)v9 + v19) = 0;
    return (unsigned int)v19;
  }
}

```

## disassembly

```asm
0x18000f140  push    rbp
0x18000f142  push    rbx
0x18000f143  push    rsi
0x18000f144  push    rdi
0x18000f145  push    r12
0x18000f147  push    r13
0x18000f149  push    r14
0x18000f14b  push    r15
0x18000f14d  lea     rbp, [rsp-17h]
0x18000f152  sub     rsp, 88h
0x18000f159  mov     rax, cs:__security_cookie
0x18000f160  xor     rax, rsp
0x18000f163  mov     [rbp+4Fh+var_50], rax
0x18000f167  mov     r10, [rcx]
0x18000f16a  mov     rsi, rcx
0x18000f16d  mov     ebx, edx
0x18000f16f  mov     ecx, edx
0x18000f171  and     ecx, 7
0x18000f174  mov     [rbp+4Fh+hWnd], r10
0x18000f178  mov     r14d, 1
0x18000f17e  mov     r12, r9
0x18000f181  mov     edx, r14d
0x18000f184  mov     r15, r8
0x18000f187  shl     edx, cl
0x18000f189  mov     edi, ebx
0x18000f18b  cmp     ebx, cs:dword_1800C9588
0x18000f191  jbe     short loc_18000F1C1
0x18000f193  cmp     ebx, cs:dword_1800C9598
0x18000f199  jbe     loc_18000F221
0x18000f19f  xor     eax, eax; jumptable 000000018000F290 default case, cases 7-13,15,16,18,20-23,26-32,34-45,48-69,72-82,84,86-89,91-122,124-138,140-171,173-255,257-259
0x18000f1a1  mov     rcx, [rbp+4Fh+var_50]
0x18000f1a5  xor     rcx, rsp; StackCookie
0x18000f1a8  call    __security_check_cookie
0x18000f1ad  add     rsp, 88h
0x18000f1b4  pop     r15
0x18000f1b6  pop     r14
0x18000f1b8  pop     r13
0x18000f1ba  pop     r12
0x18000f1bc  pop     rdi
0x18000f1bd  pop     rsi
0x18000f1be  pop     rbx
0x18000f1bf  pop     rbp
0x18000f1c0  retn
0x18000f1c1  mov     rax, cs:qword_1800C9590
0x18000f1c8  mov     rcx, rbx
0x18000f1cb  shr     rcx, 3
0x18000f1cf  test    [rcx+rax], dl
0x18000f1d2  jz      short loc_18000F193
0x18000f1d4  mov     edx, ebx
0x18000f1d6  cmp     ebx, 400h
0x18000f1dc  jnb     loc_18000FE88
0x18000f1e2  lfence
0x18000f1e5  lea     r13, __ImageBase
0x18000f1ec  movzx   eax, ds:(MessageTable - 180000000h)[r13+rbx*2]
0x18000f1f5  movzx   ecx, al
0x18000f1f8  mov     rax, ds:(gapfnScSendMessage - 180000000h)[r13+rcx*8]
0x18000f200  xor     r13d, r13d
0x18000f203  mov     ecx, [rbp+4Fh+arg_20]
0x18000f206  mov     dword ptr [rsp+0C0h+var_90], ecx
0x18000f20a  mov     rcx, r10
0x18000f20d  mov     [rsp+0C0h+var_98], 29Eh
0x18000f215  mov     qword ptr [rsp+0C0h+UnicodeSize], r13
0x18000f21a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f21f  jmp     short loc_18000F1A1
0x18000f221  mov     rax, cs:qword_1800C95A0
0x18000f228  mov     rcx, rdi
0x18000f22b  shr     rcx, 3
0x18000f22f  test    [rcx+rax], dl
0x18000f232  jz      def_18000F290; jumptable 000000018000F290 default case, cases 7-13,15,16,18,20-23,26-32,34-45,48-69,72-82,84,86-89,91-122,124-138,140-171,173-255,257-259
0x18000f238  cmp     ebx, 11Bh
0x18000f23e  jz      def_18000F290; jumptable 000000018000F290 default case, cases 7-13,15,16,18,20-23,26-32,34-45,48-69,72-82,84,86-89,91-122,124-138,140-171,173-255,257-259
0x18000f244  cmp     ebx, 0Dh
0x18000f247  jz      short loc_18000F2A1
0x18000f249  cmp     ebx, 84h
0x18000f24f  jz      loc_18000F306
0x18000f255  cmp     ebx, 109h
0x18000f25b  ja      loc_18000F35A
0x18000f261  jz      def_18000F290; jumptable 000000018000F290 default case, cases 7-13,15,16,18,20-23,26-32,34-45,48-69,72-82,84,86-89,91-122,124-138,140-171,173-255,257-259
0x18000f267  lea     eax, [rbx-6]; switch 255 cases
0x18000f26a  cmp     eax, 0FEh
0x18000f26f  ja      def_18000F290; jumptable 000000018000F290 default case, cases 7-13,15,16,18,20-23,26-32,34-45,48-69,72-82,84,86-89,91-122,124-138,140-171,173-255,257-259
0x18000f275  lea     r13, __ImageBase
0x18000f27c  movzx   eax, ds:(byte_180010138 - 180000000h)[rax+r13]
0x18000f285  mov     ecx, ds:(jpt_18000F290 - 180000000h)[r13+rax*4]
0x18000f28d  add     rcx, r13
0x18000f290  jmp     rcx; switch jump
0x18000f292  test    [r9+20h], r14b; jumptable 000000018000F290 case 70
0x18000f296  jnz     def_18000F290; jumptable 000000018000F290 default case, cases 7-13,15,16,18,20-23,26-32,34-45,48-69,72-82,84,86-89,91-122,124-138,140-171,173-255,257-259
0x18000f29c  jmp     loc_18000F930
0x18000f2a1  test    r15, r15
0x18000f2a4  jz      def_18000F290; jumptable 000000018000F290 default case, cases 7-13,15,16,18,20-23,26-32,34-45,48-69,72-82,84,86-89,91-122,124-138,140-171,173-255,257-259
0x18000f2aa  mov     eax, [rsi+0B8h]
0x18000f2b0  test    eax, eax
0x18000f2b2  jz      loc_18000F344
0x18000f2b8  mov     rcx, [rsi+0C0h]
0x18000f2bf  xor     r13d, r13d
0x18000f2c2  test    rcx, rcx
0x18000f2c5  jz      loc_18000FA66
0x18000f2cb  sub     rsi, [rsi+8]
0x18000f2cf  add     rsi, rcx
0x18000f2d2  shr     eax, 1
0x18000f2d4  dec     r15d
0x18000f2d7  cmp     [rbp+4Fh+arg_20], r13d
0x18000f2db  jnz     short loc_18000F318
0x18000f2dd  cmp     eax, r15d
0x18000f2e0  mov     rdx, rsi; Src
0x18000f2e3  mov     rcx, r12; void *
0x18000f2e6  cmovb   r15d, eax
0x18000f2ea  lea     rbx, [r15+r15]
0x18000f2ee  mov     r8, rbx; Size
0x18000f2f1  call    memcpy_0
0x18000f2f6  mov     [r12+rbx], r13w
0x18000f2fb  mov     r13d, r15d
0x18000f2fe  mov     eax, r15d
0x18000f301  jmp     loc_18000F1A1
0x18000f306  mov     edx, r12d
0x18000f309  mov     rcx, rsi
0x18000f30c  call    FindNCHit
0x18000f311  cdqe
0x18000f313  jmp     loc_18000F1A1
0x18000f318  mov     [rbp+4Fh+ResultSize], r13d
0x18000f31c  test    r15d, r15d
0x18000f31f  jz      short loc_18000F334
0x18000f321  test    eax, eax
0x18000f323  jz      short loc_18000F334
0x18000f325  test    rsi, rsi
0x18000f328  jz      short loc_18000F334
0x18000f32a  cmp     r15d, 0FFFFFFFFh
0x18000f32e  jnz     loc_18000F590
0x18000f334  mov     eax, r13d
0x18000f337  mov     byte ptr [rax+r12], 0
0x18000f33c  mov     eax, r13d
0x18000f33f  jmp     loc_18000F1A1
0x18000f344  cmp     [rbp+4Fh+arg_20], 0
0x18000f348  jnz     loc_18000F49D
0x18000f34e  xor     r13d, r13d
0x18000f351  mov     [r9], r13w
0x18000f355  jmp     def_18000F290; jumptable 000000018000F290 default case, cases 7-13,15,16,18,20-23,26-32,34-45,48-69,72-82,84,86-89,91-122,124-138,140-171,173-255,257-259
0x18000f35a  cmp     ebx, 20Ah
0x18000f360  ja      loc_18000F4FC
0x18000f366  jz      loc_18000FB6A; jumptable 000000018000F53A case 526
0x18000f36c  lea     eax, [rbx-10Dh]; switch 249 cases
0x18000f372  cmp     eax, 0F8h
0x18000f377  ja      def_18000F290; jumptable 000000018000F290 default case, cases 7-13,15,16,18,20-23,26-32,34-45,48-69,72-82,84,86-89,91-122,124-138,140-171,173-255,257-259
0x18000f37d  lea     r13, __ImageBase
0x18000f384  movzx   eax, ds:(byte_180010268 - 180000000h)[rax+r13]
0x18000f38d  mov     ecx, ds:(jpt_18000F398 - 180000000h)[r13+rax*4]
0x18000f395  add     rcx, r13
0x18000f398  jmp     rcx; switch jump
0x18000f39a  mov     rdx, cs:gpsi; jumptable 000000018000F398 case 311
0x18000f3a1  cmp     word ptr [rdx+1B54h], 8
0x18000f3a9  jb      short loc_18000F3BD
0x18000f3ab  mov     eax, [rdx+1228h]
0x18000f3b1  cmp     eax, [rdx+11D8h]
0x18000f3b7  jz      loc_18000FDF4
0x18000f3bd  mov     edx, [rdx+1228h]; color
0x18000f3c3  mov     rcx, r15; hdc
0x18000f3c6  call    cs:__imp_SetBkColor
0x18000f3cc  mov     rdx, cs:gpsi
0x18000f3d3  mov     rcx, r15; hdc
0x18000f3d6  mov     edx, [rdx+1214h]; color
0x18000f3dc  call    cs:__imp_SetTextColor
0x18000f3e2  mov     rax, cs:gpsi
0x18000f3e9  mov     rax, [rax+1350h]
0x18000f3f0  jmp     loc_18000F1A1
0x18000f3f5  test    dword ptr [r9+20h], 1000h; jumptable 000000018000F290 case 71
0x18000f3fd  mov     ebx, [rbp+4Fh+arg_20]
0x18000f400  jz      loc_18000F4A6
0x18000f406  mov     eax, [r12+20h]
0x18000f40b  and     eax, 8800h
0x18000f410  cmp     eax, 800h
0x18000f415  jz      def_18000F290; jumptable 000000018000F290 default case, cases 7-13,15,16,18,20-23,26-32,34-45,48-69,72-82,84,86-89,91-122,124-138,140-171,173-255,257-259
0x18000f41b  movzx   eax, byte ptr [rsi+1Fh]
0x18000f41f  xorps   xmm0, xmm0
0x18000f422  movups  xmmword ptr [rbp+4Fh+P], xmm0
0x18000f426  test    al, 20h
0x18000f428  jnz     short loc_18000F434
0x18000f42a  mov     r14, rax
0x18000f42d  and     r14d, 1
0x18000f431  add     r14, r14
0x18000f434  lea     rdx, [rbp+4Fh+P]
0x18000f438  mov     rcx, rsi
0x18000f43b  call    _GetClientRect
0x18000f440  movzx   eax, word ptr [rbp+4Fh+P+0Ch]
0x18000f444  mov     r8, r14; unsigned __int64
0x18000f447  sub     ax, word ptr [rbp+4Fh+P+4]
0x18000f44b  movzx   edx, ax
0x18000f44e  movzx   eax, word ptr [rbp+4Fh+P+8]
0x18000f452  sub     ax, word ptr [rbp+4Fh+P]
0x18000f456  movzx   ecx, ax
0x18000f459  shl     edx, 10h
0x18000f45c  or      edx, ecx
0x18000f45e  mov     [rsp+0C0h+UnicodeSize], ebx; int
0x18000f462  movsxd  r9, edx; __int64
0x18000f465  mov     rcx, rsi; struct tagWND *
0x18000f468  mov     edx, 5; unsigned int
0x18000f46d  call    ?SendMessageWorker@@YA_JPEAUtagWND@@I_K_JH@Z; SendMessageWorker(tagWND *,uint,unsigned __int64,__int64,int)
0x18000f472  jmp     def_18000F290; jumptable 000000018000F290 default case, cases 7-13,15,16,18,20-23,26-32,34-45,48-69,72-82,84,86-89,91-122,124-138,140-171,173-255,257-259
0x18000f477  mov     eax, [rsi+0B8h]; jumptable 000000018000F290 case 14
0x18000f47d  test    eax, eax
0x18000f47f  jz      def_18000F290; jumptable 000000018000F290 default case, cases 7-13,15,16,18,20-23,26-32,34-45,48-69,72-82,84,86-89,91-122,124-138,140-171,173-255,257-259
0x18000f485  xor     r13d, r13d
0x18000f488  mov     [rbp+4Fh+ResultSize], r13d
0x18000f48c  cmp     [rbp+4Fh+arg_20], r13d
0x18000f490  jnz     loc_18000F99A
0x18000f496  shr     eax, 1
0x18000f498  jmp     loc_18000F1A1
0x18000f49d  mov     byte ptr [r9], 0
0x18000f4a1  jmp     def_18000F290; jumptable 000000018000F290 default case, cases 7-13,15,16,18,20-23,26-32,34-45,48-69,72-82,84,86-89,91-122,124-138,140-171,173-255,257-259
0x18000f4a6  mov     rax, [rsi+30h]
0x18000f4aa  mov     r15d, [rsi+68h]
0x18000f4ae  mov     edi, [rsi+6Ch]
0x18000f4b1  test    rax, rax
0x18000f4b4  jz      loc_18000FA5E
0x18000f4ba  mov     r13, rsi
0x18000f4bd  sub     r13, [rsi+8]
0x18000f4c1  add     r13, rax
0x18000f4c4  call    GetCurrentThreadDesktopWindow
0x18000f4c9  cmp     r13, rax
0x18000f4cc  jz      short loc_18000F4D6
0x18000f4ce  sub     edi, [r13+6Ch]
0x18000f4d2  sub     r15d, [r13+68h]
0x18000f4d6  shl     edi, 10h
0x18000f4d9  xor     r8d, r8d; unsigned __int64
0x18000f4dc  movzx   eax, r15w
0x18000f4e0  mov     edx, 3; unsigned int
0x18000f4e5  mov     r9d, edi
0x18000f4e8  mov     rcx, rsi; struct tagWND *
0x18000f4eb  or      r9, rax; __int64
0x18000f4ee  mov     [rsp+0C0h+UnicodeSize], ebx; int
0x18000f4f2  call    ?SendMessageWorker@@YA_JPEAUtagWND@@I_K_JH@Z; SendMessageWorker(tagWND *,uint,unsigned __int64,__int64,int)
0x18000f4f7  jmp     loc_18000F406
0x18000f4fc  cmp     ebx, 319h
0x18000f502  ja      loc_1800100CA
0x18000f508  jz      loc_180010095
0x18000f50e  lea     eax, [rbx-20Ch]; switch 219 cases
0x18000f514  cmp     eax, 0DAh
0x18000f519  ja      def_18000F290; jumptable 000000018000F290 default case, cases 7-13,15,16,18,20-23,26-32,34-45,48-69,72-82,84,86-89,91-122,124-138,140-171,173-255,257-259
0x18000f51f  lea     r13, __ImageBase
0x18000f526  movzx   eax, ds:(byte_1800103B4 - 180000000h)[rax+r13]
0x18000f52f  mov     ecx, ds:(jpt_18000F53A - 180000000h)[r13+rax*4]
0x18000f537  add     rcx, r13
0x18000f53a  jmp     rcx; switch jump
0x18000f53c  mov     rax, cs:off_1800C85D8; jumptable 000000018000F53A case 641
0x18000f543  mov     rcx, r10
0x18000f546  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f54b  cmp     rax, [rbp+4Fh+hWnd]
0x18000f54f  jz      loc_18001002D
0x18000f555  mov     rcx, rax; HWND
0x18000f558  call    ?ValidateHwndNoRip@@YAPEAUtagWND@@PEAUHWND__@@@Z; ValidateHwndNoRip(HWND__ *)
0x18000f55d  test    rax, rax
0x18000f560  jz      def_18000F290; jumptable 000000018000F290 default case, cases 7-13,15,16,18,20-23,26-32,34-45,48-69,72-82,84,86-89,91-122,124-138,140-171,173-255,257-259
0x18000f566  mov     ecx, [rbp+4Fh+arg_20]
0x18000f569  mov     r9, r12; __int64
0x18000f56c  mov     [rsp+0C0h+UnicodeSize], ecx; int
0x18000f570  mov     r8, r15; unsigned __int64
0x18000f573  mov     rcx, rax; struct tagWND *
0x18000f576  mov     edx, ebx; unsigned int
0x18000f578  call    ?SendMessageWorker@@YA_JPEAUtagWND@@I_K_JH@Z; SendMessageWorker(tagWND *,uint,unsigned __int64,__int64,int)
0x18000f57d  jmp     loc_18000F1A1
0x18000f582  test    r12, r12; jumptable 000000018000F290 case 24
0x18000f585  jz      def_18000F290; jumptable 000000018000F290 default case, cases 7-13,15,16,18,20-23,26-32,34-45,48-69,72-82,84,86-89,91-122,124-138,140-171,173-255,257-259
0x18000f58b  jmp     loc_18000F930
0x18000f590  jl      loc_18000F334
0x18000f596  add     eax, eax
0x18000f598  lea     r8, [rbp+4Fh+ResultSize]; ResultSize
0x18000f59c  mov     r9, rsi; UnicodeString
0x18000f59f  mov     [rsp+0C0h+UnicodeSize], eax; UnicodeSize
0x18000f5a3  mov     edx, r15d; MbSize
0x18000f5a6  mov     rcx, r12; MbString
0x18000f5a9  call    cs:__imp_RtlUnicodeToMultiByteN
0x18000f5af  mov     edx, 80000000h
0x18000f5b4  lea     ecx, [rax+rdx]
0x18000f5b7  test    edx, ecx
0x18000f5b9  jz      loc_18000FA34
0x18000f5bf  mov     r13d, [rbp+4Fh+ResultSize]
0x18000f5c3  jmp     loc_18000F334
0x18000f5c8  bt      r12, 0Bh; jumptable 000000018000F398 case 271
0x18000f5cd  jnb     loc_18000F6BF; jumptable 000000018000F398 cases 269,270
0x18000f5d3  mov     rax, cs:off_1800C85D0
0x18000f5da  mov     rcx, r10
0x18000f5dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f5e2  mov     [rbp+4Fh+var_70], rax
0x18000f5e6  mov     rdi, rax
0x18000f5e9  test    rax, rax
0x18000f5ec  jz      loc_18000F6BB
0x18000f5f2  xor     r9d, r9d
0x18000f5f5  xor     r8d, r8d
0x18000f5f8  mov     edx, 800h
0x18000f5fd  mov     rcx, rax
0x18000f600  cmp     [rbp+4Fh+arg_20], r8d
0x18000f604  jnz     loc_180098CB0
0x18000f60a  mov     rax, cs:off_1800C85C0
0x18000f611  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f616  mov     [rbp+4Fh+ResultSize], eax
0x18000f619  test    eax, eax
0x18000f61b  jz      loc_18000FD63
0x18000f621  mov     rcx, cs:pUserHeap; HeapHandle
0x18000f628  mov     edx, 8; Flags
0x18000f62d  mov     r8d, eax
  ... truncated ...
```
