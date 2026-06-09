# ProcessDDEMLInitiate(tagCL_INSTANCE_INFO *,HWND__ *,ushort,ushort)

- ea: `0x180045fc0`
- end: `0x1800465fb`
- name: `?ProcessDDEMLInitiate@@YAXPEAUtagCL_INSTANCE_INFO@@PEAUHWND__@@GG@Z`
- size: `1595`
- prototype: `void __fastcall(struct tagCL_INSTANCE_INFO *, HWND, unsigned __int16, unsigned __int16)`
- caller_count: `1`
- callee_count: `21`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180019b90`

## callees

- `0x18000b4e0`
- `0x18000bd00`
- `0x18000cf20`
- `0x18000d210`
- `0x180015780`
- `0x180016310`
- `0x1800198dc`
- `0x180019b20`
- `0x18002d6c0`
- `0x18002dd20`
- `0x180045fc0`
- `0x180046dec`
- `0x1800481f4`
- `0x18004825c`
- `0x180057040`
- `0x18006e4b4`
- `0x18007f2e4`
- `0x18007f3a0`
- `0x18007f600`
- `0x18008808c`
- `0x180096e00`

## import_xrefs

- `win32u!NtUserDestroyWindow` at `0x18004658c`
- `win32u!NtUserDestroyWindow` at `0x18004658c`
- `ntdll!RtlEnterCriticalSection` at `0x18004603d`
- `ntdll!RtlEnterCriticalSection` at `0x18004635e`
- `ntdll!RtlEnterCriticalSection` at `0x1800464fc`
- `ntdll!RtlEnterCriticalSection` at `0x18004603d`
- `ntdll!RtlEnterCriticalSection` at `0x18004635e`
- `ntdll!RtlEnterCriticalSection` at `0x1800464fc`
- `ntdll!RtlLeaveCriticalSection` at `0x1800462e9`
- `ntdll!RtlLeaveCriticalSection` at `0x1800464bb`
- `ntdll!RtlLeaveCriticalSection` at `0x1800465d5`
- `ntdll!RtlLeaveCriticalSection` at `0x1800462e9`
- `ntdll!RtlLeaveCriticalSection` at `0x1800464bb`
- `ntdll!RtlLeaveCriticalSection` at `0x1800465d5`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180046263`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18004637b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180046263`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18004637b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180046595`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180046595`
- `api-ms-win-core-heap-l2-1-0!LocalReAlloc` at `0x1800463b9`
- `api-ms-win-core-heap-l2-1-0!LocalReAlloc` at `0x1800463b9`
- `api-ms-win-core-atoms-l1-1-0!DeleteAtom` at `0x1800465be`
- `api-ms-win-core-atoms-l1-1-0!DeleteAtom` at `0x1800465c8`
- `api-ms-win-core-atoms-l1-1-0!DeleteAtom` at `0x1800465be`
- `api-ms-win-core-atoms-l1-1-0!DeleteAtom` at `0x1800465c8`

## pseudocode

```c
void __fastcall ProcessDDEMLInitiate(struct tagCL_INSTANCE_INFO *a1, HWND a2, unsigned __int16 a3, unsigned __int16 a4)
{
  int v4; // ebx
  ATOM v8; // r13
  struct tagWND *v9; // rax
  __int64 v10; // rcx
  __int16 *v11; // rcx
  __int16 v12; // dx
  unsigned int v13; // esi
  __int64 v14; // rbx
  __int64 *v15; // r14
  unsigned int i; // ebx
  LONG WindowLongW; // eax
  unsigned __int16 v18; // ax
  HSZ v19; // r13
  unsigned __int16 v20; // ax
  __int16 *v21; // rcx
  HSZ v22; // rdx
  __int16 v23; // ax
  HDDEDATA v24; // rax
  LPBYTE v25; // r15
  HWND v26; // rbx
  unsigned __int16 *v27; // r12
  int j; // eax
  __int64 v29; // rcx
  HWND v30; // r14
  _QWORD *k; // rax
  HWND Window; // rax
  _WORD *v33; // rax
  unsigned int v34; // eax
  _WORD *v35; // rbx
  HWND v36; // rcx
  __int64 v37; // rbx
  LPARAM v38; // r9
  HWND hWndParent; // [rsp+40h] [rbp-89h]
  unsigned __int16 v41; // [rsp+60h] [rbp-69h]
  unsigned __int16 v42; // [rsp+62h] [rbp-67h]
  ATOM v43; // [rsp+64h] [rbp-65h]
  ATOM v44; // [rsp+68h] [rbp-61h]
  unsigned int uBytes; // [rsp+6Ch] [rbp-5Dh] BYREF
  int uBytes_4; // [rsp+70h] [rbp-59h]
  HWND hWnd; // [rsp+78h] [rbp-51h]
  unsigned __int64 v48; // [rsp+80h] [rbp-49h]
  HDDEDATA hData; // [rsp+88h] [rbp-41h]
  _QWORD v50[2]; // [rsp+90h] [rbp-39h] BYREF
  __int128 v51; // [rsp+A0h] [rbp-29h]
  __int64 v52; // [rsp+B0h] [rbp-19h] BYREF
  int v53; // [rsp+B8h] [rbp-11h]
  __int64 v54; // [rsp+BCh] [rbp-Dh]
  int v55; // [rsp+C4h] [rbp-5h]
  int v56; // [rsp+C8h] [rbp-1h]
  int v57; // [rsp+CCh] [rbp+3h]
  int v58; // [rsp+D0h] [rbp+7h]

  v4 = 0;
  hWnd = a2;
  v52 = 36;
  v53 = 0;
  v54 = 1004;
  v55 = 0;
  v56 = 12;
  v57 = 2;
  v58 = 256;
  if ( a1 )
  {
    v44 = 0;
    v8 = 0;
    RtlEnterCriticalSection(&gcsDDEML);
    if ( (*((_DWORD *)a1 + 14) & 0x2000) != 0 )
      goto LABEL_79;
    if ( !IsWindow(a2) )
      goto LABEL_79;
    v9 = ValidateHwnd(a2);
    if ( !v9 )
      goto LABEL_79;
    v10 = *((_QWORD *)v9 + 16);
    if ( v10 )
      v11 = (__int16 *)((char *)v9 + v10 - *((_QWORD *)v9 + 1));
    else
      v11 = 0;
    v12 = *v11;
    if ( (*((_BYTE *)v9 + 18) & 8) != 0 )
    {
      v13 = 64;
      if ( v12 != *(_WORD *)(gpsi + 890) )
        goto LABEL_23;
      v13 = 68;
    }
    else
    {
      v13 = 68;
      if ( v12 != *(_WORD *)(gpsi + 892) )
        v13 = 64;
      if ( (v13 & 4) == 0 )
        goto LABEL_23;
    }
    v14 = *((_QWORD *)a1 + 1);
    if ( v14 == GetWindowLongPtrW(a2, 48) )
    {
      if ( (*((_DWORD *)a1 + 14) & 0x1000) != 0 )
      {
LABEL_79:
        DeleteAtom(v44);
        DeleteAtom(v8);
        RtlLeaveCriticalSection(&gcsDDEML);
        return;
      }
      v13 |= 0x100u;
    }
    v15 = &v52;
    for ( i = 0; i < 0x24; i += 4 )
    {
      WindowLongW = GetWindowLongW(a2, i + 8);
      *(_DWORD *)v15 = WindowLongW;
      v15 = (__int64 *)((char *)v15 + 4);
    }
    if ( (GetWindowLongW(a2, 44) & 1) != 0 )
      v13 &= ~0x40u;
    v4 = 0;
LABEL_23:
    v18 = GlobalToLocalAtom(a3);
    v19 = (HSZ)v18;
    v44 = v18;
    v20 = GlobalToLocalAtom(a4);
    v21 = (__int16 *)*((_QWORD *)a1 + 10);
    v22 = (HSZ)v20;
    v43 = v20;
    if ( !(_WORD)v19 )
    {
      if ( (*((_BYTE *)a1 + 56) & 0x20) == 0 )
        goto LABEL_32;
      if ( !*v21 )
      {
LABEL_78:
        v8 = v43;
        goto LABEL_79;
      }
    }
    if ( (*((_BYTE *)a1 + 56) & 0x20) != 0 && (_WORD)v19 )
    {
      v23 = *v21;
      if ( !*v21 )
        goto LABEL_78;
      do
      {
        if ( v23 == (_WORD)v19 )
          break;
        v23 = *++v21;
      }
      while ( *v21 );
      if ( !*v21 )
        goto LABEL_78;
    }
LABEL_32:
    v50[0] = v19;
    v50[1] = v22;
    v51 = 0;
    if ( !(_WORD)v19 || !(_WORD)v22 )
      v4 = 1;
    uBytes_4 = v4;
    v48 = (v13 >> 8) & 1;
    v24 = DoCallback(
            a1,
            v4 != 0 ? 8418 : 4194,
            0,
            0,
            v22,
            v19,
            0,
            (unsigned __int64)&v52 & -(__int64)((v13 & 4) != 0),
            v48);
    hData = v24;
    if ( !v24 )
      goto LABEL_78;
    if ( v4 )
    {
      v25 = DdeAccessData(v24, 0);
      if ( !v25 )
        goto LABEL_78;
    }
    else
    {
      v25 = (LPBYTE)v50;
    }
    v26 = hWnd;
    while ( *(_QWORD *)v25 )
    {
      if ( !*((_QWORD *)v25 + 1) )
        break;
      v27 = (unsigned __int16 *)LocalAlloc(0x40u, 0x70u);
      if ( !v27 )
        break;
      v41 = *(_WORD *)v25;
      v42 = *((_WORD *)v25 + 4);
      if ( *((_WORD *)a1 + 52) )
      {
        for ( j = *((__int16 *)a1 + 52); j; --j )
        {
          v29 = *((_QWORD *)a1 + 12);
          if ( *(_WORD *)(v29 + 16LL * j - 16) == *(_WORD *)v25
            && *(_WORD *)(v29 + 16LL * j - 14) == *((_WORD *)v25 + 4) )
          {
            v30 = *(HWND *)(v29 + 16LL * j - 8);
            for ( k = (_QWORD *)GetWindowLongPtrW(v30, 0); k; k = (_QWORD *)*k )
            {
              if ( (HWND)k[5] == v26 )
                goto LABEL_55;
            }
            if ( v30 )
              goto LABEL_66;
            break;
          }
        }
      }
LABEL_55:
      RtlLeaveCriticalSection(&gcsDDEML);
      hWndParent = (HWND)*((_QWORD *)a1 + 4);
      if ( *((__int16 *)a1 + 54) >= 0 )
        Window = CreateWindowExA(
                   0,
                   (LPCSTR)*(unsigned __int16 *)(gpsi + 894),
                   byte_1800AB024,
                   0x40000000u,
                   0,
                   0,
                   0,
                   0,
                   hWndParent,
                   0,
                   0,
                   0);
      else
        Window = CreateWindowExW(
                   0,
                   (LPCWSTR)*(unsigned __int16 *)(gpsi + 896),
                   &pszFormat,
                   0x40000000u,
                   0,
                   0,
                   0,
                   0,
                   hWndParent,
                   0,
                   0,
                   0);
      v30 = Window;
      RtlEnterCriticalSection(&gcsDDEML);
      if ( !v30 )
        goto LABEL_75;
      if ( *((_QWORD *)a1 + 12) )
      {
        v34 = *((__int16 *)a1 + 52);
        if ( v34 + 1 < v34 || (uBytes = v34 + 1, (int)ULongLongToUInt(16LL * (v34 + 1), &uBytes) < 0) )
        {
LABEL_74:
          NtUserDestroyWindow(v30);
LABEL_75:
          LocalFree(v27);
          break;
        }
        v33 = LocalReAlloc(*((HLOCAL *)a1 + 12), uBytes, 0x42u);
      }
      else
      {
        v33 = LocalAlloc(0x40u, 0x10u);
      }
      v35 = v33;
      if ( !v33 )
        goto LABEL_74;
      IncLocalAtomCount(v41);
      v35[8 * *((__int16 *)a1 + 52)] = v41;
      IncLocalAtomCount(v42);
      v35[8 * *((__int16 *)a1 + 52) + 1] = v42;
      *(_QWORD *)&v35[8 * (__int16)(*((_WORD *)a1 + 52))++ + 4] = v30;
      *((_QWORD *)a1 + 12) = v35;
LABEL_66:
      *(_QWORD *)v27 = GetWindowLongPtrW(v30, 0);
      SetWindowLongPtrW(v30, 0, (LONG_PTR)v27);
      *((_QWORD *)v27 + 1) = a1;
      *((_QWORD *)v27 + 3) = CreateHandle((unsigned __int64)v27, 2u, *((_DWORD *)a1 + 4) & 0x7F);
      v27[16] = v41;
      IncLocalAtomCount(v41);
      v27[17] = v42;
      IncLocalAtomCount(v42);
      v36 = hWnd;
      *((_QWORD *)v27 + 5) = hWnd;
      *((_QWORD *)v27 + 6) = v30;
      v27[28] = *((_WORD *)a1 + 53) | v13 | 1;
      SetCommonStateFlags(v36, v30, v27 + 28);
      v27[29] = v44;
      IncLocalAtomCount((unsigned __int16)v19);
      RtlLeaveCriticalSection(&gcsDDEML);
      v37 = LocalToGlobalAtom(v41);
      v38 = v37 | (LocalToGlobalAtom(v42) << 16);
      v26 = hWnd;
      SendMessageW(hWnd, 0x3E4u, (WPARAM)v30, v38);
      RtlEnterCriticalSection(&gcsDDEML);
      if ( (*((_DWORD *)a1 + 14) & 0x40000) == 0 )
        DoCallback(a1, 0x8072u, 0, *((HCONV *)v27 + 3), (HSZ)v42, (HSZ)v41, 0, 0, v48);
      if ( (*(_DWORD *)(*((_QWORD *)v27 + 1) + 24LL) & 0x40000000) != 0 && ((v27[28] & 4) == 0 || (v27[28] & 0x10) != 0) )
        MonitorConv((struct tagCONV_INFO *)v27, 1);
      if ( (v13 & 0x40) == 0 )
        break;
      v25 += 16;
    }
    if ( uBytes_4 )
    {
      DdeUnaccessData(hData);
      InternalFreeDataHandle(hData, 0);
    }
    goto LABEL_78;
  }
}

```

## disassembly

```asm
0x180045fc0  push    rbp
0x180045fc2  push    rbx
0x180045fc3  push    rsi
0x180045fc4  push    rdi
0x180045fc5  push    r12
0x180045fc7  push    r13
0x180045fc9  push    r14
0x180045fcb  push    r15
0x180045fcd  lea     rbp, [rsp-1Fh]
0x180045fd2  sub     rsp, 0E8h
0x180045fd9  mov     rax, cs:__security_cookie
0x180045fe0  xor     rax, rsp
0x180045fe3  mov     [rbp+57h+var_48], rax
0x180045fe7  xor     ebx, ebx
0x180045fe9  mov     [rbp+57h+var_C0], r9w
0x180045fee  mov     [rbp+57h+hWnd], rdx
0x180045ff2  movzx   r12d, r8w
0x180045ff6  mov     [rbp+57h+var_70], 24h ; '$'
0x180045ffe  mov     r15, rdx
0x180046001  mov     [rbp+57h+var_68], ebx
0x180046004  mov     rdi, rcx
0x180046007  mov     [rbp+57h+var_64], 3ECh
0x18004600f  mov     [rbp+57h+var_5C], ebx
0x180046012  mov     [rbp+57h+var_58], 0Ch
0x180046019  mov     [rbp+57h+var_54], 2
0x180046020  mov     [rbp+57h+var_50], 100h
0x180046027  test    rcx, rcx
0x18004602a  jz      loc_1800465DB
0x180046030  lea     rcx, ?gcsDDEML@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x180046037  mov     [rbp+57h+var_B8], ebx
0x18004603a  mov     r13d, ebx
0x18004603d  call    cs:__imp_RtlEnterCriticalSection
0x180046043  test    dword ptr [rdi+38h], 2000h
0x18004604a  jnz     loc_1800465BA
0x180046050  mov     rcx, r15; hWnd
0x180046053  call    IsWindow
0x180046058  test    eax, eax
0x18004605a  jz      loc_1800465BA
0x180046060  mov     rcx, r15; HWND
0x180046063  call    ?ValidateHwnd@@YAPEAUtagWND@@PEAUHWND__@@@Z; ValidateHwnd(HWND__ *)
0x180046068  test    rax, rax
0x18004606b  jz      loc_1800465BA
0x180046071  mov     rcx, [rax+80h]
0x180046078  test    rcx, rcx
0x18004607b  jnz     short loc_180046081
0x18004607d  mov     ecx, ebx
0x18004607f  jmp     short loc_180046088
0x180046081  sub     rcx, [rax+8]
0x180046085  add     rcx, rax
0x180046088  test    byte ptr [rax+12h], 8
0x18004608c  mov     r14d, 40h ; '@'
0x180046092  mov     rax, cs:gpsi
0x180046099  movzx   edx, word ptr [rcx]
0x18004609c  jnz     short loc_1800460B5
0x18004609e  cmp     dx, [rax+37Ch]
0x1800460a5  lea     esi, [r14+4]
0x1800460a9  cmovnz  esi, r14d
0x1800460ad  test    sil, 4
0x1800460b1  jz      short loc_180046129
0x1800460b3  jmp     short loc_1800460C6
0x1800460b5  mov     esi, r14d
0x1800460b8  cmp     dx, [rax+37Ah]
0x1800460bf  jnz     short loc_180046129
0x1800460c1  mov     esi, 44h ; 'D'
0x1800460c6  mov     rbx, [rdi+8]
0x1800460ca  mov     edx, 30h ; '0'; nIndex
0x1800460cf  mov     rcx, r15; hWnd
0x1800460d2  call    GetWindowLongPtrW
0x1800460d7  cmp     rbx, rax
0x1800460da  jnz     short loc_1800460ED
0x1800460dc  test    dword ptr [rdi+38h], 1000h
0x1800460e3  jnz     loc_1800465BA
0x1800460e9  bts     esi, 8
0x1800460ed  lea     r14, [rbp+57h+var_70]
0x1800460f1  xor     ebx, ebx
0x1800460f3  lea     edx, [rbx+8]; nIndex
0x1800460f6  mov     rcx, r15; hWnd
0x1800460f9  call    GetWindowLongW
0x1800460fe  add     ebx, 4
0x180046101  mov     [r14], eax
0x180046104  lea     r14, [r14+4]
0x180046108  cmp     ebx, 24h ; '$'
0x18004610b  jb      short loc_1800460F3
0x18004610d  mov     edx, 2Ch ; ','; nIndex
0x180046112  mov     rcx, r15; hWnd
0x180046115  call    GetWindowLongW
0x18004611a  mov     r14d, 40h ; '@'
0x180046120  test    al, 1
0x180046122  jz      short loc_180046127
0x180046124  and     esi, 0FFFFFFBFh
0x180046127  xor     ebx, ebx
0x180046129  movzx   ecx, r12w; unsigned __int16
0x18004612d  call    ?GlobalToLocalAtom@@YAGG@Z; GlobalToLocalAtom(ushort)
0x180046132  movzx   ecx, [rbp+57h+var_C0]; unsigned __int16
0x180046136  movzx   r13d, ax
0x18004613a  mov     word ptr [rbp+57h+var_B8], r13w
0x18004613f  call    ?GlobalToLocalAtom@@YAGG@Z; GlobalToLocalAtom(ushort)
0x180046144  mov     rcx, [rdi+50h]
0x180046148  movzx   edx, ax
0x18004614b  mov     word ptr [rbp+57h+var_BC], dx
0x18004614f  test    r13w, r13w
0x180046153  jnz     short loc_180046164
0x180046155  test    byte ptr [rdi+38h], 20h
0x180046159  jz      short loc_180046197
0x18004615b  cmp     [rcx], bx
0x18004615e  jz      loc_1800465B6
0x180046164  test    byte ptr [rdi+38h], 20h
0x180046168  jz      short loc_180046197
0x18004616a  test    r13w, r13w
0x18004616e  jz      short loc_180046197
0x180046170  movzx   eax, word ptr [rcx]
0x180046173  test    ax, ax
0x180046176  jz      loc_1800465B6
0x18004617c  cmp     ax, r13w
0x180046180  jz      short loc_18004618E
0x180046182  add     rcx, 2
0x180046186  movzx   eax, word ptr [rcx]
0x180046189  test    ax, ax
0x18004618c  jnz     short loc_18004617C
0x18004618e  cmp     [rcx], bx
0x180046191  jz      loc_1800465B6
0x180046197  mov     [rbp+57h+var_90], r13
0x18004619b  xorps   xmm0, xmm0
0x18004619e  mov     [rbp+57h+var_88], rdx
0x1800461a2  mov     r10, rdx
0x1800461a5  movdqu  [rbp+57h+var_80], xmm0
0x1800461aa  test    r13w, r13w
0x1800461ae  jz      short loc_1800461B5
0x1800461b0  test    dx, dx
0x1800461b3  jnz     short loc_1800461BA
0x1800461b5  mov     ebx, 1
0x1800461ba  mov     eax, esi
0x1800461bc  mov     dword ptr [rbp+57h+uBytes+4], ebx
0x1800461bf  and     al, 4
0x1800461c1  mov     r11d, esi
0x1800461c4  shr     r11, 8
0x1800461c8  and     r11d, 1
0x1800461cc  neg     al
0x1800461ce  mov     [rsp+120h+hWndParent], r11; unsigned __int64
0x1800461d3  lea     rax, [rbp+57h+var_70]
0x1800461d7  mov     [rbp+57h+var_A0], r11
0x1800461db  sbb     rcx, rcx
0x1800461de  xor     r8d, r8d; unsigned __int16
0x1800461e1  and     rcx, rax
0x1800461e4  mov     eax, ebx
0x1800461e6  mov     qword ptr [rsp+120h+nHeight], rcx; unsigned __int64
0x1800461eb  neg     eax
0x1800461ed  mov     qword ptr [rsp+120h+nWidth], r8; hData
0x1800461f2  mov     rcx, rdi; struct tagCL_INSTANCE_INFO *
0x1800461f5  sbb     dx, dx
0x1800461f8  mov     qword ptr [rsp+120h+Y], r13; HSZ
0x1800461fd  and     dx, 1080h
0x180046202  mov     qword ptr [rsp+120h+X], r10; HSZ
0x180046207  add     dx, 1062h; unsigned __int16
0x18004620c  xor     r9d, r9d; HCONV
0x18004620f  call    ?DoCallback@@YAPEAUHDDEDATA__@@PEAUtagCL_INSTANCE_INFO@@GGPEAUHCONV__@@PEAUHSZ__@@2PEAU1@_K4@Z; DoCallback(tagCL_INSTANCE_INFO *,ushort,ushort,HCONV__ *,HSZ__ *,HSZ__ *,HDDEDATA__ *,unsigned __int64,unsigned __int64)
0x180046214  xor     ecx, ecx
0x180046216  mov     [rbp+57h+hData], rax
0x18004621a  test    rax, rax
0x18004621d  jz      loc_1800465B6
0x180046223  test    ebx, ebx
0x180046225  jz      short loc_180046240
0x180046227  xor     edx, edx; pcbDataSize
0x180046229  mov     rcx, rax; hData
0x18004622c  call    DdeAccessData
0x180046231  xor     ecx, ecx
0x180046233  mov     r15, rax
0x180046236  test    rax, rax
0x180046239  jnz     short loc_180046244
0x18004623b  jmp     loc_1800465B6
0x180046240  lea     r15, [rbp+57h+var_90]
0x180046244  mov     rbx, [rbp+57h+hWnd]
0x180046248  cmp     [r15], rcx
0x18004624b  jz      loc_18004659D
0x180046251  cmp     [r15+8], rcx
0x180046255  jz      loc_18004659D
0x18004625b  mov     edx, 70h ; 'p'; uBytes
0x180046260  mov     ecx, r14d; uFlags
0x180046263  call    cs:__imp_LocalAlloc
0x180046269  xor     ecx, ecx
0x18004626b  mov     r12, rax
0x18004626e  test    rax, rax
0x180046271  jz      loc_18004659D
0x180046277  movzx   r8d, word ptr [r15]
0x18004627b  movzx   edx, word ptr [r15+8]
0x180046280  mov     [rbp+57h+var_C0], r8w
0x180046285  mov     [rbp+57h+var_BE], dx
0x180046289  cmp     [rdi+68h], cx
0x18004628d  jz      short loc_1800462E0
0x18004628f  movsx   eax, word ptr [rdi+68h]
0x180046293  test    eax, eax
0x180046295  jz      short loc_1800462E0
0x180046297  mov     rcx, [rdi+60h]
0x18004629b  movsxd  r14, eax
0x18004629e  add     r14, r14
0x1800462a1  cmp     [rcx+r14*8-10h], r8w
0x1800462a7  jnz     short loc_1800462B1
0x1800462a9  cmp     [rcx+r14*8-0Eh], dx
0x1800462af  jz      short loc_1800462B5
0x1800462b1  dec     eax
0x1800462b3  jmp     short loc_180046293
0x1800462b5  mov     r14, [rcx+r14*8-8]
0x1800462ba  xor     edx, edx; nIndex
0x1800462bc  mov     rcx, r14; hWnd
0x1800462bf  call    GetWindowLongPtrW
0x1800462c4  test    rax, rax
0x1800462c7  jz      short loc_1800462D4
0x1800462c9  cmp     [rax+28h], rbx
0x1800462cd  jz      short loc_1800462E0
0x1800462cf  mov     rax, [rax]
0x1800462d2  jmp     short loc_1800462C4
0x1800462d4  xor     ebx, ebx
0x1800462d6  test    r14, r14
0x1800462d9  jz      short loc_1800462E2
0x1800462db  jmp     loc_180046418
0x1800462e0  xor     ebx, ebx
0x1800462e2  lea     rcx, ?gcsDDEML@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x1800462e9  call    cs:__imp_RtlLeaveCriticalSection
0x1800462ef  mov     rcx, [rdi+20h]
0x1800462f3  mov     r9d, 40000000h; dwStyle
0x1800462f9  mov     rax, cs:gpsi
0x180046300  mov     [rsp+120h+lpParam], rbx; lpParam
0x180046305  mov     [rsp+120h+hInstance], rbx; hInstance
0x18004630a  mov     [rsp+120h+hMenu], rbx; hMenu
0x18004630f  mov     [rsp+120h+hWndParent], rcx; hWndParent
0x180046314  xor     ecx, ecx; dwExStyle
0x180046316  mov     [rsp+120h+nHeight], ebx; nHeight
0x18004631a  mov     [rsp+120h+nWidth], ebx; nWidth
0x18004631e  mov     [rsp+120h+Y], ebx; Y
0x180046322  mov     [rsp+120h+X], ebx; X
0x180046326  cmp     [rdi+6Ch], bx
0x18004632a  jge     short loc_180046341
0x18004632c  movzx   edx, word ptr [rax+380h]; lpClassName
0x180046333  lea     r8, pszFormat; lpWindowName
0x18004633a  call    CreateWindowExW
0x18004633f  jmp     short loc_180046354
0x180046341  movzx   edx, word ptr [rax+37Eh]; lpClassName
0x180046348  lea     r8, byte_1800AB024; lpWindowName
0x18004634f  call    CreateWindowExA
0x180046354  lea     rcx, ?gcsDDEML@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x18004635b  mov     r14, rax
0x18004635e  call    cs:__imp_RtlEnterCriticalSection
0x180046364  test    r14, r14
0x180046367  jz      loc_180046592
0x18004636d  cmp     [rdi+60h], rbx
0x180046371  jnz     short loc_180046383
0x180046373  mov     edx, 10h; uBytes
0x180046378  lea     ecx, [rdx+30h]; uFlags
0x18004637b  call    cs:__imp_LocalAlloc
0x180046381  jmp     short loc_1800463BF
0x180046383  movsx   eax, word ptr [rdi+68h]
0x180046387  lea     edx, [rax+1]
0x18004638a  cmp     edx, eax
0x18004638c  jb      loc_180046589
0x180046392  mov     ecx, edx
0x180046394  mov     dword ptr [rbp+57h+uBytes], edx
0x180046397  lea     rdx, [rbp+57h+uBytes]; unsigned int *
0x18004639b  shl     rcx, 4; unsigned __int64
0x18004639f  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x1800463a4  test    eax, eax
0x1800463a6  js      loc_180046589
0x1800463ac  mov     edx, dword ptr [rbp+57h+uBytes]; uBytes
0x1800463af  mov     r8d, 42h ; 'B'; uFlags
0x1800463b5  mov     rcx, [rdi+60h]; hMem
0x1800463b9  call    cs:__imp_LocalReAlloc
0x1800463bf  mov     rbx, rax
0x1800463c2  test    rax, rax
0x1800463c5  jz      loc_180046589
0x1800463cb  movzx   ecx, [rbp+57h+var_C0]; unsigned __int16
0x1800463cf  call    ?IncLocalAtomCount@@YAGG@Z; IncLocalAtomCount(ushort)
0x1800463d4  movsx   rax, word ptr [rdi+68h]
0x1800463d9  movzx   ecx, [rbp+57h+var_C0]
0x1800463dd  add     rax, rax
0x1800463e0  mov     [rbx+rax*8], cx
0x1800463e4  movzx   ecx, [rbp+57h+var_BE]; unsigned __int16
0x1800463e8  call    ?IncLocalAtomCount@@YAGG@Z; IncLocalAtomCount(ushort)
0x1800463ed  movsx   rax, word ptr [rdi+68h]
0x1800463f2  movzx   ecx, [rbp+57h+var_BE]
0x1800463f6  add     rax, rax
0x1800463f9  mov     [rbx+rax*8+2], cx
0x1800463fe  movsx   rax, word ptr [rdi+68h]
0x180046403  add     rax, rax
0x180046406  mov     [rbx+rax*8+8], r14
0x18004640b  mov     eax, 1
0x180046410  add     [rdi+68h], ax
0x180046414  mov     [rdi+60h], rbx
0x180046418  xor     edx, edx; nIndex
0x18004641a  mov     rcx, r14; hWnd
0x18004641d  call    GetWindowLongPtrW
0x180046422  mov     r8, r12; dwNewLong
0x180046425  mov     [r12], rax
0x180046429  xor     edx, edx; nIndex
0x18004642b  mov     rcx, r14; hWnd
0x18004642e  call    SetWindowLongPtrW
0x180046433  mov     [r12+8], rdi
0x180046438  mov     edx, 2; unsigned int
0x18004643d  mov     r8d, [rdi+10h]
0x180046441  mov     rcx, r12; unsigned __int64
0x180046444  and     r8d, 7Fh; unsigned int
0x180046448  call    ?CreateHandle@@YAPEAX_KKK@Z; CreateHandle(unsigned __int64,ulong,ulong)
  ... truncated ...
```
