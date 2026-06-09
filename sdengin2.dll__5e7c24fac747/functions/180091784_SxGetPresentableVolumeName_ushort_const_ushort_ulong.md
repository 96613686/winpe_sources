# SxGetPresentableVolumeName(ushort const *,ushort *,ulong)

- ea: `0x180091784`
- end: `0x1800919e2`
- name: `?SxGetPresentableVolumeName@@YAJPEBGPEAGK@Z`
- size: `606`
- prototype: `__int64 __fastcall(LPCWSTR lpszVolumeName, unsigned __int16 *, unsigned int)`
- caller_count: `2`
- callee_count: `7`
- tags: `service_task`

## callers

- `0x1800205e0`
- `0x180091678`

## callees

- `0x180009ac8`
- `0x1800145f4`
- `0x18006fe84`
- `0x18006ff8c`
- `0x180091784`
- `0x1800937d4`
- `0x1800938fc`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180091875`
- `KERNEL32!GetLastError` at `0x180091875`
- `KERNEL32!GetVolumePathNamesForVolumeNameW` at `0x180091867`
- `KERNEL32!GetVolumePathNamesForVolumeNameW` at `0x180091867`
- `ole32!CoTaskMemFree` at `0x1800919ba`
- `ole32!CoTaskMemFree` at `0x1800919ba`
- `ole32!CoTaskMemRealloc` at `0x18009183e`
- `ole32!CoTaskMemRealloc` at `0x18009183e`

## pseudocode

```c
__int64 __fastcall SxGetPresentableVolumeName(LPCWSTR lpszVolumeName, unsigned __int16 *a2, unsigned int a3)
{
  unsigned __int64 v3; // r14
  WCHAR *v6; // rbx
  __int16 v7; // ax
  DWORD v8; // eax
  WCHAR *v9; // rax
  signed int LastError; // eax
  unsigned int v11; // r9d
  WCHAR *v12; // r8
  const unsigned __int16 *i; // r11
  __int64 v14; // rdx
  const unsigned __int16 *v15; // rax
  __int64 v16; // rax
  int v17; // eax
  int v18; // r8d
  int v19; // r9d
  __int64 v20; // r11
  unsigned int v21; // ebx
  __int64 v23; // [rsp+28h] [rbp-41h]
  int v24; // [rsp+40h] [rbp-29h] BYREF
  __int16 v25; // [rsp+44h] [rbp-25h]
  __int16 v26; // [rsp+46h] [rbp-23h]
  DWORD cchReturnLength; // [rsp+D0h] [rbp+67h] BYREF

  v3 = a3;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
    WPP_SF_Sqd(*((_QWORD *)WPP_GLOBAL_Control + 2), (_DWORD)a2, a3, (_DWORD)lpszVolumeName, (char)a2, a3);
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v24, "SxGetPresentableVolumeName", 50, 1);
  cchReturnLength = 0;
  v6 = 0;
  v7 = 61;
  if ( !lpszVolumeName )
    goto LABEL_34;
  v25 = 61;
  if ( !a2 )
  {
    v7 = 62;
LABEL_34:
    v26 = v7;
    v24 = -2147024809;
    goto LABEL_35;
  }
  v24 = 0;
  v25 = 63;
  v8 = 261;
  *a2 = 0;
  cchReturnLength = 261;
  while ( 1 )
  {
    v9 = (WCHAR *)CoTaskMemRealloc(v6, 2LL * v8);
    v6 = v9;
    if ( !v9 )
    {
      v24 = -2147024882;
      v26 = 74;
      goto LABEL_35;
    }
    v24 = 0;
    v25 = 74;
    if ( GetVolumePathNamesForVolumeNameW(lpszVolumeName, v9, cchReturnLength, &cchReturnLength) )
      break;
    LastError = GetLastError();
    if ( LastError == 122 || LastError == 234 )
    {
      LastError = 0;
    }
    else if ( LastError > 0 )
    {
      LastError = (unsigned __int16)LastError | 0x80070000;
    }
    v24 = LastError;
    if ( LastError < 0 )
    {
      v26 = 84;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000000) != 0 )
      {
        LODWORD(v23) = LastError;
        WPP_SF_sSd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          11,
          (unsigned int)WPP_05ac73db944e38c734cd0ea2eac4b7ce_Traceguids,
          (unsigned int)"dwErr",
          (__int64)lpszVolumeName,
          v23);
      }
      goto LABEL_35;
    }
    v8 = cchReturnLength;
    v25 = 84;
  }
  v11 = -1;
  v12 = v6;
  for ( i = v6; *v12; v12 += v16 )
  {
    v14 = -1;
    do
      ++v14;
    while ( v12[v14] );
    v15 = v12;
    if ( (unsigned int)v14 >= v11 )
      v15 = i;
    i = v15;
    v16 = (unsigned int)(v14 + 1);
    if ( (unsigned int)v14 >= v11 )
      LODWORD(v14) = v11;
    v11 = v14;
  }
  v17 = StringCchCopyW(a2, v3, i);
  v24 = v17;
  if ( v17 >= 0 )
  {
    v25 = 112;
  }
  else
  {
    v26 = 112;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000000) != 0 )
      WPP_SF_sSSdd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        (unsigned int)&WPP_GLOBAL_Control,
        v18,
        v19,
        (__int64)lpszVolumeName,
        v20,
        v3,
        v17);
  }
LABEL_35:
  CoTaskMemFree(v6);
  v21 = v24;
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v24);
  return v21;
}

```

## disassembly

```asm
0x180091784  push    rbp
0x180091786  push    rbx
0x180091787  push    rsi
0x180091788  push    rdi
0x180091789  push    r12
0x18009178b  push    r13
0x18009178d  push    r14
0x18009178f  push    r15
0x180091791  lea     rbp, [rsp-1Fh]
0x180091796  sub     rsp, 88h
0x18009179d  mov     r14d, r8d
0x1800917a0  mov     rsi, rdx
0x1800917a3  mov     rdi, rcx
0x1800917a6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800917ad  lea     rax, WPP_GLOBAL_Control
0x1800917b4  cmp     rcx, rax
0x1800917b7  jz      short loc_1800917D8
0x1800917b9  test    dword ptr [rcx+1Ch], 20000000h
0x1800917c0  jz      short loc_1800917D8
0x1800917c2  mov     rcx, [rcx+10h]
0x1800917c6  mov     r9, rdi
0x1800917c9  mov     dword ptr [rsp+0C0h+var_98], r14d
0x1800917ce  mov     [rsp+0C0h+var_A0], rdx
0x1800917d3  call    WPP_SF_Sqd
0x1800917d8  mov     r9d, 1; unsigned __int16
0x1800917de  lea     rdx, aSxgetpresentab; "SxGetPresentableVolumeName"
0x1800917e5  lea     rcx, [rbp+57h+var_80]; this
0x1800917e9  lea     r8d, [r9+31h]; unsigned __int16
0x1800917ed  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x1800917f2  xor     r15d, r15d
0x1800917f5  mov     [rbp+57h+cchReturnLength], r15d
0x1800917f9  mov     ebx, r15d
0x1800917fc  lea     eax, [r15+3Dh]
0x180091800  test    rdi, rdi
0x180091803  jz      loc_1800919AC
0x180091809  mov     [rbp+57h+var_7C], ax
0x18009180d  test    rsi, rsi
0x180091810  jz      loc_1800919A7
0x180091816  lea     eax, [r15+3Fh]
0x18009181a  mov     [rbp+57h+var_80], r15d
0x18009181e  mov     [rbp+57h+var_7C], ax
0x180091822  lea     r12d, [r15+4Ah]
0x180091826  mov     eax, 105h
0x18009182b  mov     [rsi], r15w
0x18009182f  mov     [rbp+57h+cchReturnLength], eax
0x180091832  lea     r13d, [r15+54h]
0x180091836  mov     edx, eax
0x180091838  mov     rcx, rbx; pv
0x18009183b  add     rdx, rdx; cb
0x18009183e  call    cs:__imp_CoTaskMemRealloc
0x180091844  mov     rbx, rax
0x180091847  test    rax, rax
0x18009184a  jz      loc_180091999
0x180091850  mov     r8d, [rbp+57h+cchReturnLength]; cchBufferLength
0x180091854  lea     r9, [rbp+57h+cchReturnLength]; lpcchReturnLength
0x180091858  mov     rdx, rax; lpszVolumePathNames
0x18009185b  mov     [rbp+57h+var_80], r15d
0x18009185f  mov     rcx, rdi; lpszVolumeName
0x180091862  mov     [rbp+57h+var_7C], r12w
0x180091867  call    cs:__imp_GetVolumePathNamesForVolumeNameW
0x18009186d  test    eax, eax
0x18009186f  jnz     loc_1800918FC
0x180091875  call    cs:__imp_GetLastError
0x18009187b  cmp     eax, 7Ah ; 'z'
0x18009187e  jz      short loc_180091895
0x180091880  cmp     eax, 0EAh
0x180091885  jz      short loc_180091895
0x180091887  test    eax, eax
0x180091889  jle     short loc_180091898
0x18009188b  movzx   eax, ax
0x18009188e  or      eax, 80070000h
0x180091893  jmp     short loc_180091898
0x180091895  mov     eax, r15d
0x180091898  mov     [rbp+57h+var_80], eax
0x18009189b  test    eax, eax
0x18009189d  js      short loc_1800918A9
0x18009189f  mov     eax, [rbp+57h+cchReturnLength]
0x1800918a2  mov     [rbp+57h+var_7C], r13w
0x1800918a7  jmp     short loc_180091836
0x1800918a9  mov     [rbp+57h+var_7A], r13w
0x1800918ae  mov     rcx, cs:WPP_GLOBAL_Control
0x1800918b5  lea     rdx, WPP_GLOBAL_Control
0x1800918bc  cmp     rcx, rdx
0x1800918bf  jz      loc_1800919B7
0x1800918c5  test    dword ptr [rcx+1Ch], 2000000h
0x1800918cc  jz      loc_1800919B7
0x1800918d2  mov     rcx, [rcx+10h]
0x1800918d6  lea     r9, aDwerr; "dwErr"
0x1800918dd  mov     dword ptr [rsp+0C0h+var_98], eax
0x1800918e1  lea     r8, WPP_05ac73db944e38c734cd0ea2eac4b7ce_Traceguids
0x1800918e8  mov     edx, 0Bh
0x1800918ed  mov     [rsp+0C0h+var_A0], rdi
0x1800918f2  call    WPP_SF_sSd
0x1800918f7  jmp     loc_1800919B7
0x1800918fc  or      r9d, 0FFFFFFFFh
0x180091900  mov     r8, rbx
0x180091903  mov     r11, rbx
0x180091906  cmp     [rbx], r15w
0x18009190a  jz      short loc_18009193B
0x18009190c  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180091910  inc     rdx
0x180091913  cmp     [r8+rdx*2], r15w
0x180091918  jnz     short loc_180091910
0x18009191a  cmp     edx, r9d
0x18009191d  mov     rax, r8
0x180091920  cmovnb  rax, r11
0x180091924  mov     r11, rax
0x180091927  lea     eax, [rdx+1]
0x18009192a  cmovnb  edx, r9d
0x18009192e  mov     r9d, edx
0x180091931  lea     r8, [r8+rax*2]
0x180091935  cmp     [r8], r15w
0x180091939  jnz     short loc_18009190C
0x18009193b  mov     rdx, r14; unsigned __int64
0x18009193e  mov     r8, r11; unsigned __int16 *
0x180091941  mov     rcx, rsi; unsigned __int16 *
0x180091944  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180091949  mov     [rbp+57h+var_80], eax
0x18009194c  mov     ecx, 70h ; 'p'
0x180091951  test    eax, eax
0x180091953  jns     short loc_180091993
0x180091955  mov     [rbp+57h+var_7A], cx
0x180091959  mov     rcx, cs:WPP_GLOBAL_Control
0x180091960  lea     rdx, WPP_GLOBAL_Control
0x180091967  cmp     rcx, rdx
0x18009196a  jz      short loc_1800919B7
0x18009196c  test    dword ptr [rcx+1Ch], 2000000h
0x180091973  jz      short loc_1800919B7
0x180091975  mov     rcx, [rcx+10h]
0x180091979  mov     [rsp+0C0h+var_88], eax
0x18009197d  mov     [rsp+0C0h+var_90], r14d
0x180091982  mov     [rsp+0C0h+var_98], r11
0x180091987  mov     [rsp+0C0h+var_A0], rdi
0x18009198c  call    WPP_SF_sSSdd
0x180091991  jmp     short loc_1800919B7
0x180091993  mov     [rbp+57h+var_7C], cx
0x180091997  jmp     short loc_1800919B7
0x180091999  mov     [rbp+57h+var_80], 8007000Eh
0x1800919a0  mov     [rbp+57h+var_7A], r12w
0x1800919a5  jmp     short loc_1800919B7
0x1800919a7  mov     eax, 3Eh ; '>'
0x1800919ac  mov     [rbp+57h+var_7A], ax
0x1800919b0  mov     [rbp+57h+var_80], 80070057h
0x1800919b7  mov     rcx, rbx; pv
0x1800919ba  call    cs:__imp_CoTaskMemFree
0x1800919c0  mov     ebx, [rbp+57h+var_80]
0x1800919c3  lea     rcx, [rbp+57h+var_80]; this
0x1800919c7  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x1800919cc  mov     eax, ebx
0x1800919ce  add     rsp, 88h
0x1800919d5  pop     r15
0x1800919d7  pop     r14
0x1800919d9  pop     r13
0x1800919db  pop     r12
0x1800919dd  pop     rdi
0x1800919de  pop     rsi
0x1800919df  pop     rbx
0x1800919e0  pop     rbp
0x1800919e1  retn
```
