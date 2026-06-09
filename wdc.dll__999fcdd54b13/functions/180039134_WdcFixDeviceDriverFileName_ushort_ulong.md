# WdcFixDeviceDriverFileName(ushort *,ulong)

- ea: `0x180039134`
- end: `0x1800393f5`
- name: `?WdcFixDeviceDriverFileName@@YAJPEAGK@Z`
- size: `705`
- prototype: `__int64 __fastcall(unsigned __int16 *Src, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180029a78`

## callees

- `0x1800071e0`
- `0x180008ab0`
- `0x18000b854`
- `0x180039134`
- `0x180040730`
- `0x180084e1c`
- `0x180084e28`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800392c6`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800392c6`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x1800391e4`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x1800391e4`
- `KERNEL32!GetLastError` at `0x1800391b9`
- `KERNEL32!GetLastError` at `0x1800391b9`
- `KERNEL32!GetSystemWindowsDirectoryW` at `0x1800391af`
- `KERNEL32!GetSystemWindowsDirectoryW` at `0x1800391af`

## string_xrefs

- `0x1800393bc`: `System32\drivers\`

## pseudocode

```c
__int64 __fastcall WdcFixDeviceDriverFileName(unsigned __int16 *Src, const char *a2, wchar_t *a3)
{
  __int64 v3; // rbp
  unsigned int v5; // edi
  WCHAR *v6; // rax
  wchar_t *v7; // rsi
  signed int LastError; // eax
  wchar_t *v9; // rax
  __int64 v10; // rbx
  int v11; // eax
  __int64 v12; // rax
  __int64 v13; // rcx
  __int64 v14; // rcx
  unsigned int i; // ebx
  __int64 v16; // r15
  __int64 v17; // rsi
  __int64 v18; // r12
  __int64 v19; // rbx
  __int64 v20; // rbx

  v3 = -1;
  v5 = 0;
  if ( dword_1800B5780 )
    goto LABEL_20;
  v6 = (WCHAR *)WdcAlloc(0x20Au, a2, (int)a3);
  v7 = v6;
  if ( v6 )
  {
    *v6 = 0;
    if ( GetSystemWindowsDirectoryW(v6, 0x104u) )
      goto LABEL_9;
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError )
    {
      if ( LastError > 0 )
        v5 = (unsigned __int16)LastError | 0x80070000;
      if ( (v5 & 0x80000000) == 0 )
      {
LABEL_9:
        v9 = wcschr(v7, 0x5Cu);
        v10 = (__int64)v9;
        if ( !v9 )
        {
          v5 = -2147418113;
LABEL_33:
          WdcFree(v7, a2, (int)a3);
          return v5;
        }
        if ( !v9[1] || (v11 = StringCchCatW(v7, 0x105u, L"\\"), v5 = v11, v11 >= 0) )
        {
          qword_1800AE780 = v7;
          qword_1800AE7B0 = v10;
          a2 = 0;
          qword_1800AE7C0 = (__int64)v7;
          v12 = 0;
          qword_1800AE7D0 = (__int64)v7;
          qword_1800AE7E0 = (__int64)v7;
          do
          {
            v13 = -1;
            do
              ++v13;
            while ( (&off_1800AE770)[v12][v13] );
            a3 = (&off_1800AE770)[v12 + 1];
            *(&off_1800AE770 + v12 + 1) = (wchar_t *)v13;
            v14 = -1;
            do
              ++v14;
            while ( a3[v14] );
            *(&off_1800AE770 + v12 + 3) = (wchar_t *)v14;
            ++a2;
            v12 += 4;
          }
          while ( a2 != (const char *)4 );
          dword_1800B5780 = 1;
          do
LABEL_20:
            ++v3;
          while ( Src[v3] );
          for ( i = 0; i < 4; ++i )
          {
            v16 = 4LL * i;
            v17 = (__int64)*(&off_1800AE770 + v16 + 1);
            v18 = (__int64)*(&off_1800AE770 + v16 + 3);
            if ( !(unsigned int)_o__wcsnicmp(Src, (&off_1800AE770)[v16], v17) )
            {
              if ( (unsigned __int64)(v3 + v18 - v17 + 1) <= 0x400 )
              {
                memmove_0(&Src[v18], &Src[v17], 2 * (v3 - v17) + 2);
                memmove_0(Src, (&off_1800AE770)[v16 + 1], 2 * v18);
                return 0;
              }
              else
              {
                return (unsigned int)-2147024809;
              }
            }
          }
          v19 = qword_1800AE788;
          v7 = (wchar_t *)qword_1800AE780;
          if ( (unsigned __int64)(v3 + qword_1800AE788 + 18) <= 0x400 )
          {
            memmove_0(&Src[qword_1800AE788 + 17], Src, 2 * v3 + 2);
            v20 = v19;
            memcpy_0(Src, v7, v20 * 2);
            *(_OWORD *)&Src[v20] = *(_OWORD *)L"System32\\drivers\\";
            *(_OWORD *)&Src[v20 + 8] = *(_OWORD *)L"\\drivers\\";
            Src[v20 + 16] = aSystem32Driver[16];
            return v5;
          }
          v5 = -2147024809;
          if ( !qword_1800AE780 )
            return v5;
          goto LABEL_33;
        }
LABEL_27:
        WdcDebugMessage(
          "base\\diagnosis\\pdui\\perfmon\\mon\\module.cpp",
          "WdcFixDeviceDriverFileName",
          0,
          L"FAILURE: 0x%08x",
          v11);
        goto LABEL_33;
      }
    }
    else
    {
      v5 = -2147467259;
    }
    v11 = v5;
    goto LABEL_27;
  }
  v5 = -2147024882;
  WdcDebugMessage(
    "base\\diagnosis\\pdui\\perfmon\\mon\\module.cpp",
    "WdcFixDeviceDriverFileName",
    0,
    L"FAILURE: 0x%08x",
    -2147024882);
  return v5;
}

```

## disassembly

```asm
0x180039134  push    rbx
0x180039136  push    rbp
0x180039137  push    rsi
0x180039138  push    rdi
0x180039139  push    r12
0x18003913b  push    r13
0x18003913d  push    r14
0x18003913f  push    r15
0x180039141  sub     rsp, 38h
0x180039145  xor     r13d, r13d
0x180039148  lea     r9, off_1800AE770; "\\SystemRoot\\"
0x18003914f  or      rbp, 0FFFFFFFFFFFFFFFFh
0x180039153  mov     r14, rcx
0x180039156  cmp     cs:dword_1800B5780, r13d
0x18003915d  mov     edi, r13d
0x180039160  jnz     loc_180039295
0x180039166  mov     ecx, 20Ah; dwBytes
0x18003916b  call    ?WdcAlloc@@YAPEAX_KPEBDH@Z; WdcAlloc(unsigned __int64,char const *,int)
0x180039170  mov     rsi, rax
0x180039173  test    rax, rax
0x180039176  jnz     short loc_1800391A3
0x180039178  mov     edi, 8007000Eh
0x18003917d  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x180039184  xor     r8d, r8d; int
0x180039187  mov     [rsp+78h+var_58], edi
0x18003918b  lea     rdx, aWdcfixdevicedr; "WdcFixDeviceDriverFileName"
0x180039192  lea     rcx, aBaseDiagnosisP_44; "base\\diagnosis\\pdui\\perfmon\\mon\\mo"...
0x180039199  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x18003919e  jmp     loc_1800393E2
0x1800391a3  mov     edx, 104h; uSize
0x1800391a8  mov     [rax], r13w
0x1800391ac  mov     rcx, rsi; lpBuffer
0x1800391af  call    cs:__imp_GetSystemWindowsDirectoryW
0x1800391b5  test    eax, eax
0x1800391b7  jnz     short loc_1800391DC
0x1800391b9  call    cs:__imp_GetLastError
0x1800391bf  mov     edi, eax
0x1800391c1  test    eax, eax
0x1800391c3  jz      loc_1800392DB
0x1800391c9  jle     short loc_1800391D4
0x1800391cb  movzx   edi, ax
0x1800391ce  or      edi, 80070000h
0x1800391d4  test    edi, edi
0x1800391d6  js      loc_1800392E0
0x1800391dc  mov     edx, 5Ch ; '\'; Ch
0x1800391e1  mov     rcx, rsi; Str
0x1800391e4  call    cs:__imp_wcschr
0x1800391ea  mov     rbx, rax
0x1800391ed  test    rax, rax
0x1800391f0  jnz     short loc_1800391FC
0x1800391f2  mov     edi, 8000FFFFh
0x1800391f7  jmp     loc_180039389
0x1800391fc  cmp     r13w, [rax+2]
0x180039201  jz      short loc_180039221
0x180039203  lea     r8, SubBlock; "\\"
0x18003920a  mov     edx, 105h; unsigned __int64
0x18003920f  mov     rcx, rsi; unsigned __int16 *
0x180039212  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180039217  mov     edi, eax
0x180039219  test    eax, eax
0x18003921b  js      loc_1800392E2
0x180039221  mov     cs:qword_1800AE780, rsi
0x180039228  lea     r9, off_1800AE770; "\\SystemRoot\\"
0x18003922f  mov     cs:qword_1800AE7B0, rbx
0x180039236  mov     rdx, r13
0x180039239  mov     cs:qword_1800AE7C0, rsi
0x180039240  mov     rax, r13
0x180039243  mov     cs:qword_1800AE7D0, rsi
0x18003924a  mov     cs:qword_1800AE7E0, rsi
0x180039251  mov     r8, [rax+r9]
0x180039255  mov     rcx, rbp
0x180039258  inc     rcx
0x18003925b  cmp     [r8+rcx*2], r13w
0x180039260  jnz     short loc_180039258
0x180039262  mov     r8, [rax+r9+10h]; int
0x180039267  mov     [rax+r9+8], rcx
0x18003926c  mov     rcx, rbp
0x18003926f  inc     rcx
0x180039272  cmp     [r8+rcx*2], r13w
0x180039277  jnz     short loc_18003926F
0x180039279  mov     [rax+r9+18h], rcx
0x18003927e  inc     rdx; char *
0x180039281  add     rax, 20h ; ' '
0x180039285  cmp     rdx, 4
0x180039289  jnz     short loc_180039251
0x18003928b  mov     cs:dword_1800B5780, 1
0x180039295  inc     rbp
0x180039298  cmp     [r14+rbp*2], r13w
0x18003929d  jnz     short loc_180039295
0x18003929f  mov     ebx, r13d
0x1800392a2  cmp     ebx, 4
0x1800392a5  jnb     loc_180039362
0x1800392ab  mov     r15d, ebx
0x1800392ae  mov     rcx, r14
0x1800392b1  shl     r15, 5
0x1800392b5  mov     rsi, [r15+r9+8]
0x1800392ba  mov     rdx, [r15+r9]
0x1800392be  mov     r8, rsi
0x1800392c1  mov     r12, [r15+r9+18h]
0x1800392c6  call    cs:__imp__o__wcsnicmp
0x1800392cc  test    eax, eax
0x1800392ce  jz      short loc_180039308
0x1800392d0  inc     ebx
0x1800392d2  lea     r9, off_1800AE770; "\\SystemRoot\\"
0x1800392d9  jmp     short loc_1800392A2
0x1800392db  mov     edi, 80004005h
0x1800392e0  mov     eax, edi
0x1800392e2  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x1800392e9  mov     [rsp+78h+var_58], eax
0x1800392ed  xor     r8d, r8d; int
0x1800392f0  lea     rdx, aWdcfixdevicedr; "WdcFixDeviceDriverFileName"
0x1800392f7  lea     rcx, aBaseDiagnosisP_44; "base\\diagnosis\\pdui\\perfmon\\mon\\mo"...
0x1800392fe  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x180039303  jmp     loc_180039389
0x180039308  mov     rcx, r12
0x18003930b  sub     rcx, rsi
0x18003930e  inc     rcx
0x180039311  add     rcx, rbp
0x180039314  cmp     rcx, 400h
0x18003931b  jbe     short loc_180039327
0x18003931d  mov     edi, 80070057h
0x180039322  jmp     loc_1800393E2
0x180039327  sub     rbp, rsi
0x18003932a  lea     rbx, [r12+r12]
0x18003932e  lea     rdx, [r14+rsi*2]; Src
0x180039332  lea     rcx, [rbx+r14]; void *
0x180039336  lea     r8, ds:2[rbp*2]; Size
0x18003933e  call    memmove_0
0x180039343  lea     rdx, off_1800AE770; "\\SystemRoot\\"
0x18003934a  mov     r8, rbx; Size
0x18003934d  mov     rdx, [r15+rdx+10h]; Src
0x180039352  mov     rcx, r14; void *
0x180039355  call    memmove_0
0x18003935a  mov     edi, r13d
0x18003935d  jmp     loc_1800393E2
0x180039362  mov     rbx, cs:qword_1800AE788
0x180039369  mov     rsi, cs:qword_1800AE780
0x180039370  lea     rax, [rbx+12h]
0x180039374  add     rax, rbp
0x180039377  cmp     rax, 400h
0x18003937d  jbe     short loc_180039393
0x18003937f  mov     edi, 80070057h
0x180039384  test    rsi, rsi
0x180039387  jz      short loc_1800393E2
0x180039389  mov     rcx, rsi; void *
0x18003938c  call    ?WdcFree@@YAXPEAXPEBDH@Z; WdcFree(void *,char const *,int)
0x180039391  jmp     short loc_1800393E2
0x180039393  lea     rcx, [rbx+11h]
0x180039397  mov     rdx, r14; Src
0x18003939a  lea     rcx, [r14+rcx*2]; void *
0x18003939e  lea     r8, ds:2[rbp*2]; Size
0x1800393a6  call    memmove_0
0x1800393ab  add     rbx, rbx
0x1800393ae  mov     rdx, rsi; Src
0x1800393b1  mov     r8, rbx; Size
0x1800393b4  mov     rcx, r14; void *
0x1800393b7  call    memcpy_0
0x1800393bc  movups  xmm0, xmmword ptr cs:aSystem32Driver; "System32\\drivers\\"
0x1800393c3  movups  xmmword ptr [rbx+r14], xmm0
0x1800393c8  movups  xmm1, xmmword ptr cs:aSystem32Driver+10h; "\\drivers\\"
0x1800393cf  movups  xmmword ptr [rbx+r14+10h], xmm1
0x1800393d5  movzx   eax, word ptr cs:aSystem32Driver+20h; "\\"
0x1800393dc  mov     [rbx+r14+20h], ax
0x1800393e2  mov     eax, edi
0x1800393e4  add     rsp, 38h
0x1800393e8  pop     r15
0x1800393ea  pop     r14
0x1800393ec  pop     r13
0x1800393ee  pop     r12
0x1800393f0  pop     rdi
0x1800393f1  pop     rsi
0x1800393f2  pop     rbp
0x1800393f3  pop     rbx
0x1800393f4  retn
```
