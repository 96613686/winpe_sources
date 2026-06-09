# TTLoadEmbeddedFont

- ea: `0x180017f30`
- end: `0x180018626`
- name: `TTLoadEmbeddedFont`
- size: `1782`
- prototype: `LONG __stdcall(HANDLE *phFontReference, ULONG ulFlags, ULONG *pulPrivStatus, ULONG ulPrivs, ULONG *pulStatus, READEMBEDPROC lpfnReadFromStream, LPVOID lpvReadStream, LPWSTR szWinFamilyName, LPSTR szMacFamilyName, TTLOADINFO *pTTLoadInfo)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x180017f30`
- `0x1800190a4`
- `0x180019dc0`
- `0x18001c044`
- `0x18002a542`
- `0x18002a566`
- `0x18002a590`

## import_xrefs

- `KERNEL32!lstrcmpA` at `0x18001805d`
- `KERNEL32!lstrcmpA` at `0x18001805d`
- `KERNEL32!GetACP` at `0x180018015`
- `KERNEL32!GetACP` at `0x18001806b`
- `KERNEL32!GetACP` at `0x180018015`
- `KERNEL32!GetACP` at `0x18001806b`
- `KERNEL32!MultiByteToWideChar` at `0x180018095`
- `KERNEL32!MultiByteToWideChar` at `0x180018095`
- `KERNEL32!WideCharToMultiByte` at `0x18001804a`
- `KERNEL32!WideCharToMultiByte` at `0x18001804a`
- `KERNEL32!HeapAlloc` at `0x180018102`
- `KERNEL32!HeapAlloc` at `0x180018102`
- `KERNEL32!GetProcessHeap` at `0x1800180f1`
- `KERNEL32!GetProcessHeap` at `0x1800180f1`

## pseudocode

```c
LONG __stdcall TTLoadEmbeddedFont(
        HANDLE *phFontReference,
        ULONG ulFlags,
        ULONG *pulPrivStatus,
        ULONG ulPrivs,
        ULONG *pulStatus,
        READEMBEDPROC lpfnReadFromStream,
        LPVOID lpvReadStream,
        LPWSTR szWinFamilyName,
        LPSTR szMacFamilyName,
        TTLOADINFO *pTTLoadInfo)
{
  int v10; // r13d
  LPWSTR v13; // rsi
  LPSTR v14; // rdi
  ULONG v15; // r12d
  UINT ACP; // eax
  int v17; // ebx
  UINT v18; // eax
  int v19; // eax
  HANDLE ProcessHeap; // rax
  LPVOID *v22; // rax
  LPVOID *v23; // rbx
  LPVOID *v24; // r14
  LPVOID *v25; // r15
  unsigned int EmbeddedFont; // esi
  __int64 v27; // r8
  __int64 v28; // r10
  CHAR *v29; // r11
  __int64 v30; // rdx
  __int64 v31; // r9
  CHAR *v32; // rax
  __int64 v33; // rcx
  _BYTE *v34; // rax
  __int64 v35; // r10
  _BYTE *v36; // r11
  __int64 v37; // r9
  __int64 v38; // rcx
  _BYTE *v39; // rax
  __int64 v40; // r9
  _BYTE *v41; // r10
  __int64 v42; // rcx
  _BYTE *v43; // rax
  __int64 v44; // r10
  _BYTE *v45; // r11
  __int64 v46; // rdx
  __int64 v47; // r9
  __int64 v48; // rcx
  _BYTE *v49; // rax
  _BYTE *v50; // r9
  __int64 v51; // rcx
  unsigned int v52; // ebx
  BOOL UsedDefaultChar; // [rsp+64h] [rbp-584h] BYREF
  LONG v54; // [rsp+68h] [rbp-580h]
  int v55; // [rsp+6Ch] [rbp-57Ch]
  int v56; // [rsp+70h] [rbp-578h]
  CHAR *v57; // [rsp+78h] [rbp-570h]
  __int64 v58; // [rsp+80h] [rbp-568h]
  _BYTE *v59; // [rsp+88h] [rbp-560h]
  __int64 v60; // [rsp+90h] [rbp-558h]
  _BYTE *v61; // [rsp+98h] [rbp-550h]
  __int64 v62; // [rsp+A0h] [rbp-548h]
  _BYTE *v63; // [rsp+A8h] [rbp-540h]
  __int64 v64; // [rsp+B0h] [rbp-538h]
  _BYTE *v65; // [rsp+B8h] [rbp-530h]
  __int64 v66; // [rsp+C0h] [rbp-528h]
  int v67[2]; // [rsp+C8h] [rbp-520h]
  LPVOID lpMem; // [rsp+D0h] [rbp-518h]
  __int64 v69; // [rsp+D8h] [rbp-510h]
  __int64 v70; // [rsp+E0h] [rbp-508h]
  __int64 v71; // [rsp+E8h] [rbp-500h]
  CHAR *v72; // [rsp+F0h] [rbp-4F8h]
  __int64 v73; // [rsp+F8h] [rbp-4F0h]
  __int64 v74; // [rsp+100h] [rbp-4E8h]
  _BYTE *v75; // [rsp+108h] [rbp-4E0h]
  __int64 v76; // [rsp+110h] [rbp-4D8h]
  __int64 v77; // [rsp+118h] [rbp-4D0h]
  _BYTE *v78; // [rsp+120h] [rbp-4C8h]
  __int64 v79; // [rsp+128h] [rbp-4C0h]
  __int64 v80; // [rsp+130h] [rbp-4B8h]
  _BYTE *v81; // [rsp+138h] [rbp-4B0h]
  __int64 v82; // [rsp+140h] [rbp-4A8h]
  __int64 v83; // [rsp+148h] [rbp-4A0h]
  _BYTE *v84; // [rsp+150h] [rbp-498h]
  __int64 v85; // [rsp+158h] [rbp-490h]
  __int64 v86; // [rsp+160h] [rbp-488h]
  HANDLE *v87; // [rsp+168h] [rbp-480h]
  LPSTR v88; // [rsp+170h] [rbp-478h]
  CHAR FileName[260]; // [rsp+180h] [rbp-468h] BYREF
  _BYTE v90[260]; // [rsp+284h] [rbp-364h] BYREF
  _BYTE v91[260]; // [rsp+388h] [rbp-260h] BYREF
  _BYTE v92[64]; // [rsp+48Ch] [rbp-15Ch] BYREF
  _BYTE v93[64]; // [rsp+4CCh] [rbp-11Ch] BYREF
  int v94; // [rsp+50Ch] [rbp-DCh]
  int v95; // [rsp+510h] [rbp-D8h]
  void *v96; // [rsp+518h] [rbp-D0h]
  int v97; // [rsp+520h] [rbp-C8h]
  unsigned int v98; // [rsp+530h] [rbp-B8h]
  CHAR MultiByteStr[32]; // [rsp+540h] [rbp-A8h] BYREF
  WCHAR WideCharStr[32]; // [rsp+560h] [rbp-88h] BYREF

  v56 = ulPrivs;
  v10 = (int)pulPrivStatus;
  v87 = phFontReference;
  *(_QWORD *)v67 = pulStatus;
  v71 = (__int64)lpfnReadFromStream;
  v70 = (__int64)lpvReadStream;
  v13 = szWinFamilyName;
  v14 = szMacFamilyName;
  v69 = (__int64)pTTLoadInfo;
  memset_0(FileName, 0, 0x3B8u);
  v54 = 0;
  lpMem = 0;
  v15 = ulFlags | 1;
  if ( szWinFamilyName && *szWinFamilyName && szMacFamilyName && *szMacFamilyName )
  {
    UsedDefaultChar = 0;
    ACP = GetACP();
    v17 = WideCharToMultiByte(ACP, 0, szWinFamilyName, -1, MultiByteStr, 32, 0, &UsedDefaultChar);
    if ( !lstrcmpA(MultiByteStr, szMacFamilyName) )
    {
      if ( UsedDefaultChar )
        v14 = 0;
      v88 = v14;
    }
    v18 = GetACP();
    v19 = MultiByteToWideChar(v18, 0, MultiByteStr, v17, WideCharStr, 32);
    if ( memcmp_0(WideCharStr, szWinFamilyName, 2LL * v19) )
      v13 = 0;
  }
  memset_0(FileName, 0, 0x3B8u);
  v98 = 0;
  if ( !phFontReference )
    return 8;
  v55 = 8;
  ProcessHeap = GetProcessHeap();
  v22 = (LPVOID *)HeapAlloc(ProcessHeap, 8u, 0x3B8u);
  v23 = v22;
  lpMem = v22;
  if ( !v22 )
    return 7;
  v24 = v22 + 117;
  v22[117] = 0;
  v25 = v22 + 118;
  v22[118] = 0;
  EmbeddedFont = T2LoadEmbeddedFont(
                   v15,
                   v10,
                   v56,
                   v67[0],
                   v71,
                   v70,
                   (__int64)v14,
                   (__int64)v13,
                   v69,
                   FileName,
                   (__int64)(v22 + 118),
                   (__int64)(v22 + 117));
  if ( EmbeddedFont )
  {
    T2free(*v25);
    T2free(*v24);
    T2free(v23);
    v52 = v98;
    if ( !v98 )
      v52 = EmbeddedFont;
    LogTTLoadEmbeddedFont(v52);
    return v52;
  }
  else
  {
    v27 = 2147483646;
    v28 = 2147483646;
    v74 = 2147483646;
    v29 = FileName;
    v72 = FileName;
    v30 = 260;
    v31 = 260;
    v73 = 260;
    v32 = (CHAR *)v23;
    v57 = (CHAR *)v23;
    v33 = 0;
    v58 = 0;
    while ( v31 )
    {
      if ( !v28 || !*v29 )
        goto LABEL_18;
      *v32++ = *v29;
      v57 = v32;
      v72 = ++v29;
      v73 = --v31;
      v74 = --v28;
      v58 = ++v33;
    }
    v57 = --v32;
    v58 = v33 - 1;
LABEL_18:
    *v32 = 0;
    v34 = (char *)v23 + 260;
    v35 = 2147483646;
    v77 = 2147483646;
    v36 = v90;
    v75 = v90;
    v37 = 260;
    v76 = 260;
    v59 = (char *)v23 + 260;
    v38 = 0;
    v60 = 0;
    while ( v37 )
    {
      if ( !v35 || !*v36 )
        goto LABEL_24;
      *v34++ = *v36;
      v59 = v34;
      v75 = ++v36;
      v76 = --v37;
      v77 = --v35;
      v60 = ++v38;
    }
    v59 = --v34;
    v60 = v38 - 1;
LABEL_24:
    *v34 = 0;
    v39 = v23 + 65;
    v40 = 2147483646;
    v80 = 2147483646;
    v41 = v91;
    v78 = v91;
    v79 = 260;
    v61 = v23 + 65;
    v42 = 0;
    v62 = 0;
    while ( v30 )
    {
      if ( !v40 || !*v41 )
        goto LABEL_30;
      *v39++ = *v41;
      v61 = v39;
      v78 = ++v41;
      v79 = --v30;
      v80 = --v40;
      v62 = ++v42;
    }
    v61 = --v39;
    v62 = v42 - 1;
LABEL_30:
    *v39 = 0;
    v43 = (char *)v23 + 780;
    v44 = 2147483646;
    v83 = 2147483646;
    v45 = v92;
    v81 = v92;
    v46 = 64;
    v47 = 64;
    v82 = 64;
    v63 = (char *)v23 + 780;
    v48 = 0;
    v64 = 0;
    while ( v47 )
    {
      if ( !v44 || !*v45 )
        goto LABEL_36;
      *v43++ = *v45;
      v63 = v43;
      v81 = ++v45;
      v82 = --v47;
      v83 = --v44;
      v64 = ++v48;
    }
    v63 = --v43;
    v64 = v48 - 1;
LABEL_36:
    *v43 = 0;
    v49 = (char *)v23 + 844;
    v86 = 2147483646;
    v50 = v93;
    v84 = v93;
    v85 = 64;
    v65 = (char *)v23 + 844;
    v51 = 0;
    v66 = 0;
    while ( v46 )
    {
      if ( !v27 || !*v50 )
        goto LABEL_54;
      *v49++ = *v50;
      v65 = v49;
      v84 = ++v50;
      v85 = --v46;
      v86 = --v27;
      v66 = ++v51;
    }
    v65 = --v49;
    v66 = v51 - 1;
LABEL_54:
    *v49 = 0;
    *((_DWORD *)v23 + 227) = v94;
    *((_DWORD *)v23 + 228) = v95;
    v23[115] = v96;
    *((_DWORD *)v23 + 232) = v97;
    *((_DWORD *)v23 + 233) = ((unsigned __int8)**(_BYTE **)v67 >> 1) & 1;
    *v87 = v23;
    LogTTLoadEmbeddedFont(EmbeddedFont);
    return v54;
  }
}

```

## disassembly

```asm
0x180017f30  push    rbx
0x180017f32  push    rsi
0x180017f33  push    rdi
0x180017f34  push    r12
0x180017f36  push    r13
0x180017f38  push    r14
0x180017f3a  push    r15
0x180017f3c  sub     rsp, 5B0h
0x180017f43  mov     rax, cs:__security_cookie
0x180017f4a  xor     rax, rsp
0x180017f4d  mov     [rsp+5E8h+var_48], rax
0x180017f55  mov     [rsp+5E8h+var_578], r9d
0x180017f5a  mov     r13, r8
0x180017f5d  mov     r12d, edx
0x180017f60  mov     r14, rcx
0x180017f63  mov     [rsp+5E8h+var_480], rcx
0x180017f6b  mov     rax, [rsp+5E8h+pulStatus]
0x180017f73  mov     qword ptr [rsp+5E8h+var_520], rax
0x180017f7b  mov     rax, [rsp+5E8h+lpfnReadFromStream]
0x180017f83  mov     [rsp+5E8h+var_500], rax
0x180017f8b  mov     rax, [rsp+5E8h+lpvReadStream]
0x180017f93  mov     [rsp+5E8h+var_508], rax
0x180017f9b  mov     rsi, [rsp+5E8h+szWinFamilyName]
0x180017fa3  mov     rdi, [rsp+5E8h+szMacFamilyName]
0x180017fab  mov     rax, [rsp+5E8h+pTTLoadInfo]
0x180017fb3  mov     [rsp+5E8h+var_510], rax
0x180017fbb  xor     r15d, r15d
0x180017fbe  mov     [rsp+5E8h+var_588], r15d
0x180017fc3  mov     ebx, 3B8h
0x180017fc8  mov     r8d, ebx; Size
0x180017fcb  xor     edx, edx; Val
0x180017fcd  lea     rcx, [rsp+5E8h+FileName]; void *
0x180017fd5  call    memset_0
0x180017fda  mov     [rsp+5E8h+var_580], r15d
0x180017fdf  mov     [rsp+5E8h+lpMem], r15
0x180017fe7  or      r12d, 1
0x180017feb  test    rsi, rsi
0x180017fee  jz      loc_1800180BC
0x180017ff4  cmp     [rsi], r15w
0x180017ff8  jz      loc_1800180BC
0x180017ffe  test    rdi, rdi
0x180018001  jz      loc_1800180BC
0x180018007  cmp     [rdi], r15b
0x18001800a  jz      loc_1800180BC
0x180018010  mov     [rsp+5E8h+UsedDefaultChar], r15d
0x180018015  call    cs:__imp_GetACP
0x18001801b  mov     ecx, eax; CodePage
0x18001801d  lea     rax, [rsp+5E8h+UsedDefaultChar]
0x180018022  mov     [rsp+5E8h+lpUsedDefaultChar], rax; lpUsedDefaultChar
0x180018027  mov     [rsp+5E8h+lpDefaultChar], r15; lpDefaultChar
0x18001802c  mov     [rsp+5E8h+cbMultiByte], 20h ; ' '; cbMultiByte
0x180018034  lea     rax, [rsp+5E8h+MultiByteStr]
0x18001803c  mov     [rsp+5E8h+lpMultiByteStr], rax; lpMultiByteStr
0x180018041  or      r9d, 0FFFFFFFFh; cchWideChar
0x180018045  mov     r8, rsi; lpWideCharStr
0x180018048  xor     edx, edx; dwFlags
0x18001804a  call    cs:__imp_WideCharToMultiByte
0x180018050  mov     ebx, eax
0x180018052  mov     rdx, rdi; lpString2
0x180018055  lea     rcx, [rsp+5E8h+MultiByteStr]; lpString1
0x18001805d  call    cs:__imp_lstrcmpA
0x180018063  test    eax, eax
0x180018065  jz      loc_1800183F0
0x18001806b  call    cs:__imp_GetACP
0x180018071  mov     ecx, eax; CodePage
0x180018073  mov     [rsp+5E8h+cbMultiByte], 20h ; ' '; cchWideChar
0x18001807b  lea     rax, [rsp+5E8h+WideCharStr]
0x180018083  mov     [rsp+5E8h+lpMultiByteStr], rax; lpWideCharStr
0x180018088  mov     r9d, ebx; cbMultiByte
0x18001808b  lea     r8, [rsp+5E8h+MultiByteStr]; lpMultiByteStr
0x180018093  xor     edx, edx; dwFlags
0x180018095  call    cs:__imp_MultiByteToWideChar
0x18001809b  movsxd  r8, eax
0x18001809e  add     r8, r8; Size
0x1800180a1  mov     rdx, rsi; Buf2
0x1800180a4  lea     rcx, [rsp+5E8h+WideCharStr]; Buf1
0x1800180ac  call    memcmp_0
0x1800180b1  test    eax, eax
0x1800180b3  cmovnz  rsi, r15
0x1800180b7  mov     ebx, 3B8h
0x1800180bc  mov     r8, rbx; Size
0x1800180bf  xor     edx, edx; Val
0x1800180c1  lea     rcx, [rsp+5E8h+FileName]; void *
0x1800180c9  call    memset_0
0x1800180ce  mov     [rsp+5E8h+var_B8], r15d
0x1800180d6  test    r14, r14
0x1800180d9  jnz     short loc_1800180E4
0x1800180db  lea     eax, [r14+8]
0x1800180df  jmp     loc_180018603
0x1800180e4  mov     [rsp+5E8h+var_57C], r15d
0x1800180e9  mov     [rsp+5E8h+var_57C], 8
0x1800180f1  call    cs:__imp_GetProcessHeap
0x1800180f7  mov     rcx, rax; hHeap
0x1800180fa  mov     r8, rbx; dwBytes
0x1800180fd  mov     edx, 8; dwFlags
0x180018102  call    cs:__imp_HeapAlloc
0x180018108  mov     rbx, rax
0x18001810b  mov     [rsp+5E8h+lpMem], rax
0x180018113  test    rax, rax
0x180018116  jz      loc_180018406
0x18001811c  lea     r14, [rax+3A8h]
0x180018123  mov     [r14], r15
0x180018126  lea     r15, [rax+3B0h]
0x18001812d  mov     qword ptr [r15], 0
0x180018134  mov     [rsp+5E8h+var_590], r14; __int64
0x180018139  mov     [rsp+5E8h+var_598], r15; __int64
0x18001813e  lea     rax, [rsp+5E8h+FileName]
0x180018146  mov     [rsp+5E8h+lpFileName], rax; lpFileName
0x18001814b  mov     rax, [rsp+5E8h+var_510]
0x180018153  mov     [rsp+5E8h+var_5A8], rax; __int64
0x180018158  mov     [rsp+5E8h+lpUsedDefaultChar], rsi; __int64
0x18001815d  mov     [rsp+5E8h+lpDefaultChar], rdi; __int64
0x180018162  mov     rax, [rsp+5E8h+var_508]
0x18001816a  mov     qword ptr [rsp+5E8h+cbMultiByte], rax; __int64
0x18001816f  mov     rax, [rsp+5E8h+var_500]
0x180018177  mov     [rsp+5E8h+lpMultiByteStr], rax; __int64
0x18001817c  mov     r9, qword ptr [rsp+5E8h+var_520]; int
0x180018184  mov     r8d, [rsp+5E8h+var_578]; int
0x180018189  mov     rdx, r13; int
0x18001818c  mov     ecx, r12d; int
0x18001818f  call    T2LoadEmbeddedFont
0x180018194  mov     esi, eax
0x180018196  mov     [rsp+5E8h+var_588], eax
0x18001819a  xor     r12d, r12d
0x18001819d  test    eax, eax
0x18001819f  jnz     loc_180018410
0x1800181a5  mov     r8d, 7FFFFFFEh
0x1800181ab  mov     r10d, r8d
0x1800181ae  mov     [rsp+5E8h+var_4E8], r8
0x1800181b6  lea     r11, [rsp+5E8h+FileName]
0x1800181be  mov     [rsp+5E8h+var_4F8], r11
0x1800181c6  mov     edx, 104h
0x1800181cb  mov     r9d, edx
0x1800181ce  mov     [rsp+5E8h+var_4F0], rdx
0x1800181d6  mov     rax, rbx
0x1800181d9  mov     [rsp+5E8h+var_570], rbx
0x1800181de  mov     ecx, r12d
0x1800181e1  mov     [rsp+5E8h+var_568], rcx
0x1800181e9  lea     r14d, [rsi+1]
0x1800181ed  test    r9, r9
0x1800181f0  jz      short loc_180018208
0x1800181f2  test    r10, r10
0x1800181f5  jz      short loc_180018203
0x1800181f7  mov     dil, [r11]
0x1800181fa  test    dil, dil
0x1800181fd  jnz     loc_180018446
0x180018203  test    r9, r9
0x180018206  jnz     short loc_18001821B
0x180018208  sub     rax, r14
0x18001820b  mov     [rsp+5E8h+var_570], rax
0x180018210  sub     rcx, r14
0x180018213  mov     [rsp+5E8h+var_568], rcx
0x18001821b  mov     [rax], r12b
0x18001821e  lea     rax, [rbx+104h]
0x180018225  mov     r10, r8
0x180018228  mov     [rsp+5E8h+var_4D0], r8
0x180018230  lea     r11, [rsp+5E8h+var_364]
0x180018238  mov     [rsp+5E8h+var_4E0], r11
0x180018240  mov     r9, rdx
0x180018243  mov     [rsp+5E8h+var_4D8], rdx
0x18001824b  mov     [rsp+5E8h+var_560], rax
0x180018253  mov     rcx, r12
0x180018256  mov     [rsp+5E8h+var_558], rcx
0x18001825e  test    r9, r9
0x180018261  jz      short loc_180018279
0x180018263  test    r10, r10
0x180018266  jz      short loc_180018274
0x180018268  mov     dil, [r11]
0x18001826b  test    dil, dil
0x18001826e  jnz     loc_180018482
0x180018274  test    r9, r9
0x180018277  jnz     short loc_18001828F
0x180018279  sub     rax, r14
0x18001827c  mov     [rsp+5E8h+var_560], rax
0x180018284  sub     rcx, r14
0x180018287  mov     [rsp+5E8h+var_558], rcx
0x18001828f  mov     [rax], r12b
0x180018292  lea     rax, [rbx+208h]
0x180018299  mov     r9, r8
0x18001829c  mov     [rsp+5E8h+var_4B8], r8
0x1800182a4  lea     r10, [rsp+5E8h+var_260]
0x1800182ac  mov     [rsp+5E8h+var_4C8], r10
0x1800182b4  mov     [rsp+5E8h+var_4C0], rdx
0x1800182bc  mov     [rsp+5E8h+var_550], rax
0x1800182c4  mov     rcx, r12
0x1800182c7  mov     [rsp+5E8h+var_548], rcx
0x1800182cf  test    rdx, rdx
0x1800182d2  jz      short loc_1800182EA
0x1800182d4  test    r9, r9
0x1800182d7  jz      short loc_1800182E5
0x1800182d9  mov     r11b, [r10]
0x1800182dc  test    r11b, r11b
0x1800182df  jnz     loc_1800184C1
0x1800182e5  test    rdx, rdx
0x1800182e8  jnz     short loc_180018300
0x1800182ea  sub     rax, r14
0x1800182ed  mov     [rsp+5E8h+var_550], rax
0x1800182f5  sub     rcx, r14
0x1800182f8  mov     [rsp+5E8h+var_548], rcx
0x180018300  mov     [rax], r12b
0x180018303  lea     rax, [rbx+30Ch]
0x18001830a  mov     r10, r8
0x18001830d  mov     [rsp+5E8h+var_4A0], r8
0x180018315  lea     r11, [rsp+5E8h+var_15C]
0x18001831d  mov     [rsp+5E8h+var_4B0], r11
0x180018325  mov     edx, 40h ; '@'
0x18001832a  mov     r9d, edx
0x18001832d  mov     [rsp+5E8h+var_4A8], rdx
0x180018335  mov     [rsp+5E8h+var_540], rax
0x18001833d  mov     rcx, r12
0x180018340  mov     [rsp+5E8h+var_538], rcx
0x180018348  test    r9, r9
0x18001834b  jz      short loc_180018363
0x18001834d  test    r10, r10
0x180018350  jz      short loc_18001835E
0x180018352  mov     dil, [r11]
0x180018355  test    dil, dil
0x180018358  jnz     loc_180018500
0x18001835e  test    r9, r9
0x180018361  jnz     short loc_180018379
0x180018363  sub     rax, r14
0x180018366  mov     [rsp+5E8h+var_540], rax
0x18001836e  sub     rcx, r14
0x180018371  mov     [rsp+5E8h+var_538], rcx
0x180018379  mov     [rax], r12b
0x18001837c  lea     rax, [rbx+34Ch]
0x180018383  mov     [rsp+5E8h+var_488], r8
0x18001838b  lea     r9, [rsp+5E8h+var_11C]
0x180018393  mov     [rsp+5E8h+var_498], r9
0x18001839b  mov     [rsp+5E8h+var_490], rdx
0x1800183a3  mov     [rsp+5E8h+var_530], rax
0x1800183ab  mov     rcx, r12
0x1800183ae  mov     [rsp+5E8h+var_528], rcx
0x1800183b6  test    rdx, rdx
0x1800183b9  jz      short loc_1800183D5
0x1800183bb  test    r8, r8
0x1800183be  jz      short loc_1800183CC
0x1800183c0  mov     r10b, [r9]
0x1800183c3  test    r10b, r10b
0x1800183c6  jnz     loc_18001853F
0x1800183cc  test    rdx, rdx
0x1800183cf  jnz     loc_18001857E
0x1800183d5  sub     rax, r14
0x1800183d8  mov     [rsp+5E8h+var_530], rax
0x1800183e0  sub     rcx, r14
0x1800183e3  mov     [rsp+5E8h+var_528], rcx
0x1800183eb  jmp     loc_18001857E
0x1800183f0  cmp     [rsp+5E8h+UsedDefaultChar], r15d
0x1800183f5  cmovnz  rdi, r15
0x1800183f9  mov     [rsp+5E8h+var_478], rdi
0x180018401  jmp     loc_18001806B
0x180018406  mov     eax, 7
0x18001840b  jmp     loc_180018603
0x180018410  mov     rcx, [r15]; lpMem
0x180018413  call    T2free
0x180018418  mov     rcx, [r14]; lpMem
0x18001841b  call    T2free
0x180018420  mov     rcx, rbx; lpMem
0x180018423  call    T2free
0x180018428  mov     ebx, [rsp+5E8h+var_B8]
0x18001842f  test    ebx, ebx
0x180018431  cmovz   ebx, esi
0x180018434  mov     [rsp+5E8h+var_588], ebx
0x180018438  mov     ecx, ebx
0x18001843a  call    LogTTLoadEmbeddedFont
0x18001843f  mov     eax, ebx
0x180018441  jmp     loc_180018603
0x180018446  mov     [rax], dil
0x180018449  add     rax, r14
0x18001844c  mov     [rsp+5E8h+var_570], rax
0x180018451  add     r11, r14
0x180018454  mov     [rsp+5E8h+var_4F8], r11
0x18001845c  sub     r9, r14
0x18001845f  mov     [rsp+5E8h+var_4F0], r9
0x180018467  sub     r10, r14
0x18001846a  mov     [rsp+5E8h+var_4E8], r10
0x180018472  add     rcx, r14
0x180018475  mov     [rsp+5E8h+var_568], rcx
0x18001847d  jmp     loc_1800181ED
0x180018482  mov     [rax], dil
0x180018485  add     rax, r14
0x180018488  mov     [rsp+5E8h+var_560], rax
0x180018490  add     r11, r14
0x180018493  mov     [rsp+5E8h+var_4E0], r11
0x18001849b  sub     r9, r14
0x18001849e  mov     [rsp+5E8h+var_4D8], r9
0x1800184a6  sub     r10, r14
0x1800184a9  mov     [rsp+5E8h+var_4D0], r10
0x1800184b1  add     rcx, r14
0x1800184b4  mov     [rsp+5E8h+var_558], rcx
0x1800184bc  jmp     loc_18001825E
0x1800184c1  mov     [rax], r11b
0x1800184c4  add     rax, r14
0x1800184c7  mov     [rsp+5E8h+var_550], rax
0x1800184cf  add     r10, r14
0x1800184d2  mov     [rsp+5E8h+var_4C8], r10
0x1800184da  sub     rdx, r14
0x1800184dd  mov     [rsp+5E8h+var_4C0], rdx
0x1800184e5  sub     r9, r14
0x1800184e8  mov     [rsp+5E8h+var_4B8], r9
  ... truncated ...
```
