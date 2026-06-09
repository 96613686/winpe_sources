# CFirewallManager::GetSvchostPath(ushort * *)

- ea: `0x1800131a4`
- end: `0x18001346f`
- name: `?GetSvchostPath@CFirewallManager@@AEAAKPEAPEAG@Z`
- size: `715`
- prototype: `unsigned int __fastcall(CFirewallManager *__hidden this, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x1800121b0`

## callees

- `0x18000a9ac`
- `0x1800131a4`
- `0x18001db80`
- `0x1800271fc`
- `0x180034a48`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180013242`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180013242`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x1800131c8`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x18001328a`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x1800131c8`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x18001328a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800131d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001329a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800131d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001329a`

## string_xrefs

- `0x1800133c2`: `system32\svchost.exe`

## pseudocode

```c
__int64 __fastcall CFirewallManager::GetSvchostPath(CFirewallManager *this, unsigned __int16 **a2)
{
  UINT SystemWindowsDirectoryW; // eax
  DWORD LastError; // eax
  unsigned int v6; // ebx
  LPCSTR v7; // rcx
  __int64 v8; // rdx
  __int64 v9; // r9
  UINT v10; // ebx
  unsigned __int64 v11; // rdi
  WCHAR *v12; // rax
  WCHAR *v13; // rsi
  UINT v14; // eax
  DWORD v15; // eax
  LPCSTR v16; // rcx
  __int64 v17; // rdx
  __int64 v18; // r9
  unsigned int v19; // ebx
  LPCSTR v20; // rcx
  __int64 v21; // rdx
  __int64 v22; // r8
  unsigned __int64 v23; // rcx
  WCHAR *v24; // rax
  unsigned __int64 v25; // rdx
  unsigned __int64 v26; // rdi
  const wchar_t *v27; // rax
  WCHAR *i; // rdx
  WCHAR *v29; // rcx

  if ( !a2 )
    return 87;
  *a2 = 0;
  SystemWindowsDirectoryW = GetSystemWindowsDirectoryW(0, 0);
  if ( !SystemWindowsDirectoryW )
  {
    LastError = GetLastError();
    v6 = LastError;
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (LPCSTR)&WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) == 0 )
      return v6;
    v8 = 14;
    v9 = LastError;
    goto LABEL_7;
  }
  v10 = SystemWindowsDirectoryW + 23;
  v11 = SystemWindowsDirectoryW + 23;
  v12 = (WCHAR *)malloc(saturated_mul(v11, 2u));
  v13 = v12;
  if ( v12 )
  {
    v14 = GetSystemWindowsDirectoryW(v12, v10);
    if ( !v14 )
    {
      v15 = GetLastError();
      v6 = v15;
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (LPCSTR)&WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) == 0 )
        goto LABEL_48;
      v17 = 16;
      v18 = v15;
      goto LABEL_16;
    }
    if ( v14 >= v10 )
    {
      v6 = 122;
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (LPCSTR)&WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) == 0 )
        goto LABEL_48;
      v17 = 17;
      v18 = 122;
LABEL_16:
      WPP_SF_d(*((_QWORD *)v16 + 2), v17, WPP_db283a32a0f73fa63383008e81c323d4_Traceguids, v18);
LABEL_48:
      operator delete(v13);
      return v6;
    }
    if ( v13[v14 - 1] == 92 || (v19 = StringCchCatW(v13, v11, L"\\")) == 0 )
    {
      v22 = 2147483646;
      if ( v11 - 1 > 0x7FFFFFFE )
      {
        v19 = -2147024809;
      }
      else
      {
        v23 = v11;
        v24 = v13;
        do
        {
          if ( !*v24 )
            break;
          ++v24;
          --v23;
        }
        while ( v23 );
        v19 = v23 == 0 ? 0x80070057 : 0;
        if ( v23 )
          v25 = v11 - v23;
        else
          v25 = 0;
        if ( v23 )
        {
          v26 = v11 - v25;
          v27 = L"system32\\svchost.exe";
          for ( i = &v13[v25]; v26; --v26 )
          {
            if ( !v22 )
              break;
            if ( !*v27 )
              break;
            *i++ = *v27++;
            --v22;
          }
          v29 = i - 1;
          v19 = v26 == 0 ? 0x8007007A : 0;
          if ( v26 )
            v29 = i;
          *v29 = 0;
          if ( v26 )
          {
            v6 = 0;
            *a2 = v13;
            return v6;
          }
        }
      }
      v20 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (LPCSTR)&WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) == 0 )
        goto LABEL_47;
      v21 = 19;
    }
    else
    {
      v20 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (LPCSTR)&WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) == 0 )
        goto LABEL_47;
      v21 = 18;
    }
    WPP_SF_d(*((_QWORD *)v20 + 2), v21, WPP_db283a32a0f73fa63383008e81c323d4_Traceguids, v19);
LABEL_47:
    v6 = DwWin32ErrorFromHr(v19);
    goto LABEL_48;
  }
  v6 = 8;
  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (LPCSTR)&WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) == 0 )
    return v6;
  v8 = 15;
  v9 = 8;
LABEL_7:
  WPP_SF_d(*((_QWORD *)v7 + 2), v8, WPP_db283a32a0f73fa63383008e81c323d4_Traceguids, v9);
  return v6;
}

```

## disassembly

```asm
0x1800131a4  push    rbx
0x1800131a6  push    rbp
0x1800131a7  push    rsi
0x1800131a8  push    rdi
0x1800131a9  push    r14
0x1800131ab  sub     rsp, 20h
0x1800131af  xor     ebp, ebp
0x1800131b1  mov     r14, rdx
0x1800131b4  test    rdx, rdx
0x1800131b7  jnz     short loc_1800131C1
0x1800131b9  lea     eax, [rdx+57h]
0x1800131bc  jmp     loc_180013463
0x1800131c1  mov     [rdx], rbp
0x1800131c4  xor     ecx, ecx; lpBuffer
0x1800131c6  xor     edx, edx; uSize
0x1800131c8  call    cs:__imp_GetSystemWindowsDirectoryW
0x1800131cf  nop     dword ptr [rax+rax+00h]
0x1800131d4  test    eax, eax
0x1800131d6  jnz     short loc_180013227
0x1800131d8  call    cs:__imp_GetLastError
0x1800131df  nop     dword ptr [rax+rax+00h]
0x1800131e4  mov     ebx, eax
0x1800131e6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800131ed  lea     rdx, WPP_GLOBAL_Control
0x1800131f4  cmp     rcx, rdx
0x1800131f7  jz      loc_180013461
0x1800131fd  test    dword ptr [rcx+1Ch], 200h
0x180013204  jz      loc_180013461
0x18001320a  mov     edx, 0Eh
0x18001320f  mov     r9d, eax
0x180013212  mov     rcx, [rcx+10h]
0x180013216  lea     r8, WPP_db283a32a0f73fa63383008e81c323d4_Traceguids
0x18001321d  call    WPP_SF_d
0x180013222  jmp     loc_180013461
0x180013227  lea     ebx, [rax+17h]
0x18001322a  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180013231  mov     edi, ebx
0x180013233  mov     eax, 2
0x180013238  mul     rdi
0x18001323b  cmovb   rax, rcx
0x18001323f  mov     rcx, rax; Size
0x180013242  call    cs:__imp_malloc
0x180013249  nop     dword ptr [rax+rax+00h]
0x18001324e  mov     rsi, rax
0x180013251  test    rax, rax
0x180013254  jnz     short loc_180013285
0x180013256  lea     ebx, [rax+8]
0x180013259  mov     rcx, cs:WPP_GLOBAL_Control
0x180013260  lea     rdx, WPP_GLOBAL_Control
0x180013267  cmp     rcx, rdx
0x18001326a  jz      loc_180013461
0x180013270  test    dword ptr [rcx+1Ch], 200h
0x180013277  jz      loc_180013461
0x18001327d  lea     edx, [rax+0Fh]
0x180013280  mov     r9d, ebx
0x180013283  jmp     short loc_180013212
0x180013285  mov     edx, ebx; uSize
0x180013287  mov     rcx, rsi; lpBuffer
0x18001328a  call    cs:__imp_GetSystemWindowsDirectoryW
0x180013291  nop     dword ptr [rax+rax+00h]
0x180013296  test    eax, eax
0x180013298  jnz     short loc_1800132E9
0x18001329a  call    cs:__imp_GetLastError
0x1800132a1  nop     dword ptr [rax+rax+00h]
0x1800132a6  mov     ebx, eax
0x1800132a8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800132af  lea     rdx, WPP_GLOBAL_Control
0x1800132b6  cmp     rcx, rdx
0x1800132b9  jz      loc_180013459
0x1800132bf  test    dword ptr [rcx+1Ch], 200h
0x1800132c6  jz      loc_180013459
0x1800132cc  mov     edx, 10h
0x1800132d1  mov     r9d, eax
0x1800132d4  mov     rcx, [rcx+10h]
0x1800132d8  lea     r8, WPP_db283a32a0f73fa63383008e81c323d4_Traceguids
0x1800132df  call    WPP_SF_d
0x1800132e4  jmp     loc_180013459
0x1800132e9  cmp     eax, ebx
0x1800132eb  jb      short loc_18001331E
0x1800132ed  mov     ebx, 7Ah ; 'z'
0x1800132f2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800132f9  lea     rdx, WPP_GLOBAL_Control
0x180013300  cmp     rcx, rdx
0x180013303  jz      loc_180013459
0x180013309  test    dword ptr [rcx+1Ch], 200h
0x180013310  jz      loc_180013459
0x180013316  lea     edx, [rbx-69h]
0x180013319  mov     r9d, ebx
0x18001331c  jmp     short loc_1800132D4
0x18001331e  lea     ecx, [rax-1]
0x180013321  mov     eax, 5Ch ; '\'
0x180013326  cmp     ax, [rsi+rcx*2]
0x18001332a  jz      short loc_180013372
0x18001332c  lea     r8, asc_18003C518; "\\"
0x180013333  mov     rdx, rdi; unsigned __int64
0x180013336  mov     rcx, rsi; unsigned __int16 *
0x180013339  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18001333e  mov     ebx, eax
0x180013340  test    eax, eax
0x180013342  jz      short loc_180013372
0x180013344  mov     rcx, cs:WPP_GLOBAL_Control
0x18001334b  lea     rdx, WPP_GLOBAL_Control
0x180013352  cmp     rcx, rdx
0x180013355  jz      loc_180013450
0x18001335b  test    dword ptr [rcx+1Ch], 200h
0x180013362  jz      loc_180013450
0x180013368  mov     edx, 12h
0x18001336d  jmp     loc_18001343D
0x180013372  lea     rax, [rdi-1]
0x180013376  mov     r8d, 7FFFFFFEh
0x18001337c  cmp     rax, r8
0x18001337f  ja      loc_180013417
0x180013385  mov     rcx, rdi
0x180013388  mov     rax, rsi
0x18001338b  mov     rdx, rdi
0x18001338e  cmp     [rax], bp
0x180013391  jz      short loc_18001339D
0x180013393  add     rax, 2
0x180013397  sub     rcx, 1
0x18001339b  jnz     short loc_18001338E
0x18001339d  mov     rax, rcx
0x1800133a0  neg     rax
0x1800133a3  sbb     ebx, ebx
0x1800133a5  not     ebx
0x1800133a7  and     ebx, 80070057h
0x1800133ad  test    rcx, rcx
0x1800133b0  jz      short loc_1800133B7
0x1800133b2  sub     rdx, rcx
0x1800133b5  jmp     short loc_1800133BA
0x1800133b7  mov     rdx, rbp
0x1800133ba  test    rcx, rcx
0x1800133bd  jz      short loc_18001341C
0x1800133bf  sub     rdi, rdx
0x1800133c2  lea     rax, aSystem32Svchos; "system32\\svchost.exe"
0x1800133c9  lea     rdx, [rsi+rdx*2]
0x1800133cd  jz      short loc_1800133F0
0x1800133cf  test    r8, r8
0x1800133d2  jz      short loc_1800133F0
0x1800133d4  movzx   ecx, word ptr [rax]
0x1800133d7  test    cx, cx
0x1800133da  jz      short loc_1800133F0
0x1800133dc  mov     [rdx], cx
0x1800133df  add     rax, 2
0x1800133e3  add     rdx, 2
0x1800133e7  dec     r8
0x1800133ea  sub     rdi, 1
0x1800133ee  jnz     short loc_1800133CF
0x1800133f0  mov     rax, rdi
0x1800133f3  lea     rcx, [rdx-2]
0x1800133f7  neg     rax
0x1800133fa  sbb     ebx, ebx
0x1800133fc  not     ebx
0x1800133fe  and     ebx, 8007007Ah
0x180013404  test    rdi, rdi
0x180013407  cmovnz  rcx, rdx
0x18001340b  mov     [rcx], bp
0x18001340e  jz      short loc_18001341C
0x180013410  mov     ebx, ebp
0x180013412  mov     [r14], rsi
0x180013415  jmp     short loc_180013461
0x180013417  mov     ebx, 80070057h
0x18001341c  mov     rcx, cs:WPP_GLOBAL_Control
0x180013423  lea     rdx, WPP_GLOBAL_Control
0x18001342a  cmp     rcx, rdx
0x18001342d  jz      short loc_180013450
0x18001342f  test    dword ptr [rcx+1Ch], 200h
0x180013436  jz      short loc_180013450
0x180013438  mov     edx, 13h
0x18001343d  mov     rcx, [rcx+10h]
0x180013441  lea     r8, WPP_db283a32a0f73fa63383008e81c323d4_Traceguids
0x180013448  mov     r9d, ebx
0x18001344b  call    WPP_SF_d
0x180013450  mov     ecx, ebx; int
0x180013452  call    ?DwWin32ErrorFromHr@@YAKJ@Z; DwWin32ErrorFromHr(long)
0x180013457  mov     ebx, eax
0x180013459  mov     rcx, rsi; void *
0x18001345c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180013461  mov     eax, ebx
0x180013463  add     rsp, 20h
0x180013467  pop     r14
0x180013469  pop     rdi
0x18001346a  pop     rsi
0x18001346b  pop     rbp
0x18001346c  pop     rbx
0x18001346d  retn
```
