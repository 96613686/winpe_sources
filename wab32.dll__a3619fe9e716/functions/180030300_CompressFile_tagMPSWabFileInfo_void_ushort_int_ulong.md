# CompressFile(_tagMPSWabFileInfo *,void *,ushort *,int,ulong)

- ea: `0x180030300`
- end: `0x1800309fb`
- name: `?CompressFile@@YAHPEAU_tagMPSWabFileInfo@@PEAXPEAGHK@Z`
- size: `1787`
- prototype: `void __noreturn(struct _tagMPSWabFileInfo *, void *, unsigned __int16 *, int, unsigned int)`
- caller_count: `3`
- callee_count: `12`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180040760`
- `0x180040930`
- `0x180043df0`

## callees

- `0x180030300`
- `0x180030a04`
- `0x180030b38`
- `0x180030e18`
- `0x180032200`
- `0x180032588`
- `0x180032704`
- `0x180032fd8`
- `0x180033040`
- `0x180033ae0`
- `0x180091eaa`
- `0x180091ef0`

## import_xrefs

- `KERNEL32!CopyFileW` at `0x18003097d`
- `KERNEL32!CopyFileW` at `0x18003097d`
- `KERNEL32!SetFilePointer` at `0x18003056b`
- `KERNEL32!SetFilePointer` at `0x18003058a`
- `KERNEL32!SetFilePointer` at `0x18003064d`
- `KERNEL32!SetFilePointer` at `0x18003066d`
- `KERNEL32!SetFilePointer` at `0x18003056b`
- `KERNEL32!SetFilePointer` at `0x18003058a`
- `KERNEL32!SetFilePointer` at `0x18003064d`
- `KERNEL32!SetFilePointer` at `0x18003066d`
- `KERNEL32!lstrcmpiW` at `0x1800303a7`
- `KERNEL32!lstrcmpiW` at `0x1800303a7`
- `KERNEL32!LocalAlloc` at `0x180030540`
- `KERNEL32!LocalAlloc` at `0x18003061e`
- `KERNEL32!LocalAlloc` at `0x1800307aa`
- `KERNEL32!LocalAlloc` at `0x180030803`
- `KERNEL32!LocalAlloc` at `0x180030540`
- `KERNEL32!LocalAlloc` at `0x18003061e`
- `KERNEL32!LocalAlloc` at `0x1800307aa`
- `KERNEL32!LocalAlloc` at `0x180030803`
- `KERNEL32!CreateFileW` at `0x180030483`
- `KERNEL32!CreateFileW` at `0x180030483`
- `KERNEL32!WriteFile` at `0x1800305da`
- `KERNEL32!WriteFile` at `0x1800306c7`
- `KERNEL32!WriteFile` at `0x180030883`
- `KERNEL32!WriteFile` at `0x1800308a8`
- `KERNEL32!WriteFile` at `0x1800305da`
- `KERNEL32!WriteFile` at `0x1800306c7`
- `KERNEL32!WriteFile` at `0x180030883`
- `KERNEL32!WriteFile` at `0x1800308a8`
- `KERNEL32!CloseHandle` at `0x180030956`
- `KERNEL32!CloseHandle` at `0x180030966`
- `KERNEL32!CloseHandle` at `0x180030956`
- `KERNEL32!CloseHandle` at `0x180030966`
- `KERNEL32!GetFileSize` at `0x18003049b`
- `KERNEL32!GetFileSize` at `0x18003049b`
- `KERNEL32!ReadFile` at `0x1800305ad`
- `KERNEL32!ReadFile` at `0x180030695`
- `KERNEL32!ReadFile` at `0x1800307d9`
- `KERNEL32!ReadFile` at `0x180030832`
- `KERNEL32!ReadFile` at `0x1800305ad`
- `KERNEL32!ReadFile` at `0x180030695`
- `KERNEL32!ReadFile` at `0x1800307d9`
- `KERNEL32!ReadFile` at `0x180030832`
- `KERNEL32!DeleteFileW` at `0x1800309ab`
- `KERNEL32!DeleteFileW` at `0x1800309ab`

## pseudocode

```c
void __fastcall __noreturn CompressFile(LPCWSTR *a1, void *a2, unsigned __int16 *a3, int a4, char a5)
{
  unsigned int v9; // edx
  _DWORD *v10; // r9
  int v11; // r8d
  unsigned int v12; // ecx
  signed int i; // edx
  unsigned int v14; // r9d
  unsigned int v15; // r8d
  HANDLE FileW; // rbx
  DWORD FileSize; // eax
  _DWORD *v18; // rdx
  __int64 v19; // r8
  __int64 v20; // rcx
  void *v21; // rdi
  unsigned int j; // r14d
  void *v23; // r15
  DWORD v24; // r8d
  unsigned int v25; // r14d
  unsigned int v26; // r13d
  __int64 v27; // r15
  LPCWSTR v28; // rdx
  __int64 v29; // r8
  __int64 v30; // rdx
  HLOCAL v31; // rax
  const void *v32; // r14
  HLOCAL v33; // rax
  const void *v34; // rdi
  unsigned int v35; // edx
  unsigned int v36; // r9d
  DWORD NumberOfBytesRead; // [rsp+44h] [rbp-BCh] BYREF
  void *v38; // [rsp+48h] [rbp-B8h] BYREF
  int v39; // [rsp+50h] [rbp-B0h]
  __int64 v40; // [rsp+58h] [rbp-A8h] BYREF
  void *v41; // [rsp+60h] [rbp-A0h] BYREF
  void *v42; // [rsp+68h] [rbp-98h] BYREF
  DWORD v43; // [rsp+70h] [rbp-90h]
  void *v44; // [rsp+78h] [rbp-88h] BYREF
  LPCWSTR lpNewFileName; // [rsp+80h] [rbp-80h]
  _OWORD v46[2]; // [rsp+90h] [rbp-70h] BYREF
  __int128 v47; // [rsp+B0h] [rbp-50h] BYREF
  SIZE_T v48[2]; // [rsp+C0h] [rbp-40h]
  int Buffer; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v50[12]; // [rsp+D4h] [rbp-2Ch] BYREF
  int v51; // [rsp+E0h] [rbp-20h]
  int v52; // [rsp+E4h] [rbp-1Ch]
  SIZE_T v53; // [rsp+ECh] [rbp-14h]
  _DWORD v54[17]; // [rsp+F4h] [rbp-Ch]
  int v55; // [rsp+138h] [rbp+38h]
  int v56; // [rsp+140h] [rbp+40h]
  int v57; // [rsp+148h] [rbp+48h]
  int v58; // [rsp+150h] [rbp+50h]
  DWORD uBytes; // [rsp+158h] [rbp+58h]
  LONG uBytes_4; // [rsp+15Ch] [rbp+5Ch]
  int v61; // [rsp+160h] [rbp+60h]
  int v62; // [rsp+164h] [rbp+64h]
  int v63; // [rsp+168h] [rbp+68h]
  int v64; // [rsp+16Ch] [rbp+6Ch]
  int v65; // [rsp+170h] [rbp+70h]
  WCHAR FileName[264]; // [rsp+180h] [rbp+80h] BYREF

  lpNewFileName = a3;
  Buffer = 0;
  memset_0(v50, 0, 0xA0u);
  NumberOfBytesRead = 0;
  v38 = 0;
  v40 = 0;
  v41 = 0;
  v47 = 0;
  v42 = 0;
  *(_OWORD *)v48 = 0;
  v44 = 0;
  memset_0(FileName, 0, 0x208u);
  if ( a3 )
  {
    if ( !lstrcmpiW(a3, a1[2]) )
      goto LABEL_67;
    v39 = 1;
  }
  else
  {
    v39 = 0;
  }
  GetWABTempFileName(FileName, v9);
  v10 = a1[3];
  v11 = 0;
  v12 = v10[31];
  for ( i = v12 / 0x1F4; i >= 0; --i )
  {
    if ( v10[30] >= (unsigned int)(500 * i) )
    {
      v11 = 500 * i + 500;
      break;
    }
  }
  v14 = v10[33];
  if ( v11 )
    v12 = v11;
  if ( a4 )
  {
    v15 = v12 + 500;
    if ( (a5 & 1) == 0 )
      v15 = v12;
    if ( (a5 & 0x10) != 0 )
      v14 += 2048;
  }
  else
  {
    v15 = v12;
  }
  if ( (unsigned int)CreateMPSWabFile(&Buffer, FileName, v15, v14) && a2 != (void *)-1LL )
  {
    FileW = CreateFileW(FileName, 0xC0000000, 3u, 0, 3u, 0x10000000u, 0);
    if ( FileW == (HANDLE)-1LL )
      goto LABEL_60;
    FileSize = GetFileSize(a2, 0);
    v18 = a1[3];
    v19 = 0;
    v43 = FileSize;
    v57 = v18[30];
    v51 = 0;
    v52 = v18[5];
    v20 = 0;
    v58 = v18[32];
    uBytes = v18[34];
    v61 = v18[36];
    v62 = v18[37];
    v63 = v18[38];
    v64 = v18[39];
    v65 = v18[40];
    do
    {
      ++v19;
      v54[v20 - 2] = v18[v20 + 7];
      v54[v20] = v18[v20 + 9];
      v20 += 4;
    }
    while ( v19 != 6 );
    if ( !(unsigned int)WriteDataToWABFile(FileW, 0, &Buffer, 0xA4u) )
      goto LABEL_60;
    v44 = LocalAlloc(0x40u, uBytes);
    v21 = v44;
    if ( !v44
      || SetFilePointer(a2, *((_DWORD *)a1[3] + 35), 0, 0) == -1
      || SetFilePointer(FileW, uBytes_4, 0, 0) == -1
      || !ReadFile(a2, v44, uBytes, &NumberOfBytesRead, 0)
      || NumberOfBytesRead != uBytes
      || !WriteFile(FileW, v21, uBytes, &NumberOfBytesRead, 0) )
    {
      goto LABEL_60;
    }
    LocalFreeAndNull(&v44);
    for ( j = 1; j < 6; ++j )
    {
      LocalFreeAndNull(&v38);
      v38 = LocalAlloc(0x40u, (unsigned int)v54[4 * j - 2]);
      v23 = v38;
      if ( !v38 )
        goto LABEL_60;
      if ( SetFilePointer(a2, *(_DWORD *)&a1[3][8 * j + 16], 0, 0) == -1 )
        goto LABEL_60;
      if ( SetFilePointer(FileW, v54[4 * j - 1], 0, 0) == -1 )
        goto LABEL_60;
      if ( !ReadFile(a2, v23, v54[4 * j - 2], &NumberOfBytesRead, 0) )
        goto LABEL_60;
      v24 = v54[4 * j - 2];
      if ( NumberOfBytesRead != v24 || !WriteFile(FileW, v23, v24, &NumberOfBytesRead, 0) )
        goto LABEL_60;
      LocalFreeAndNull(&v38);
    }
    if ( !LoadIndex((struct _tagMPSWabFileInfo *)a1, 0, a2) )
      goto LABEL_60;
    v25 = v56 + v55;
    v26 = HIDWORD(v53);
    v27 = 0;
    v38 = (void *)(unsigned int)(v56 + v55);
    while ( (unsigned int)v27 < v54[0] )
    {
      v28 = a1[5];
      LODWORD(v40) = *(_DWORD *)&v28[4 * v27];
      HIDWORD(v40) = v25;
      if ( !(unsigned int)ReadDataFromWABFile(a2, *(_DWORD *)&v28[4 * v27 + 2], &v47, 0x20u) )
        goto LABEL_60;
      v29 = *(unsigned int *)&a1[5][4 * v27 + 2];
      v30 = *((unsigned int *)a1[3] + 5);
      v46[0] = v47;
      v46[1] = *(_OWORD *)v48;
      if ( (unsigned int)bIsValidRecord(v46, v30, v29, v43, 1, v40) )
      {
        LocalFreeAndNull(&v41);
        v31 = LocalAlloc(0x40u, HIDWORD(v48[0]));
        v41 = v31;
        v32 = v31;
        if ( !v31 )
          goto LABEL_60;
        if ( !ReadFile(a2, v31, HIDWORD(v48[0]), &NumberOfBytesRead, 0) )
          goto LABEL_60;
        if ( NumberOfBytesRead != HIDWORD(v48[0]) )
          goto LABEL_60;
        LocalFreeAndNull(&v42);
        v33 = LocalAlloc(0x40u, HIDWORD(v48[1]));
        v42 = v33;
        v34 = v33;
        if ( !v33 )
          goto LABEL_60;
        if ( !ReadFile(a2, v33, HIDWORD(v48[1]), &NumberOfBytesRead, 0) )
          goto LABEL_60;
        if ( HIDWORD(v48[1]) != NumberOfBytesRead )
          goto LABEL_60;
        if ( !(unsigned int)WriteDataToWABFile(FileW, (unsigned int)v38, &v47, 0x20u) )
          goto LABEL_60;
        if ( !WriteFile(FileW, v32, HIDWORD(v48[0]), &NumberOfBytesRead, 0) )
          goto LABEL_60;
        if ( !WriteFile(FileW, v34, HIDWORD(v48[1]), &NumberOfBytesRead, 0) )
          goto LABEL_60;
        v25 = HIDWORD(v48[1]) + HIDWORD(v48[0]) + (_DWORD)v38 + 32;
        v38 = (void *)v25;
        LocalFreeAndNull(&v41);
        LocalFreeAndNull(&v42);
        if ( !(unsigned int)WriteDataToWABFile(FileW, v26, &v40, 8u) )
          goto LABEL_60;
        v26 += 8;
      }
      v27 = (unsigned int)(v27 + 1);
    }
    if ( !v39 )
    {
      if ( (unsigned int)WriteDataToWABFile(FileW, 0, &Buffer, 0xA4u)
        && (unsigned int)CopySrcFileToDestFile(FileW, v35, a2, v36) )
      {
        ReloadMPSWabFileInfo((struct _tagMPSWabFileInfo *)a1, a2);
      }
LABEL_60:
      if ( FileW )
        CloseHandle(FileW);
      goto LABEL_67;
    }
    if ( FileW )
    {
      CloseHandle(FileW);
      FileW = 0;
    }
    if ( CopyFileW(FileName, lpNewFileName, 0) )
      goto LABEL_60;
  }
LABEL_67:
  if ( FileName[0] )
    DeleteFileW(FileName);
  LocalFreeAndNull(&v44);
  LocalFreeAndNull(&v41);
  LocalFreeAndNull(&v42);
}

```

## disassembly

```asm
0x180030300  mov     [rsp-8+arg_18], rbx
0x180030305  push    rbp
0x180030306  push    rsi
0x180030307  push    rdi
0x180030308  push    r12
0x18003030a  push    r13
0x18003030c  push    r14
0x18003030e  push    r15
0x180030310  lea     rbp, [rsp-2A0h]
0x180030318  sub     rsp, 3A0h
0x18003031f  mov     rax, cs:__security_cookie
0x180030326  xor     rax, rsp
0x180030329  mov     [rbp+2D0h+var_40], rax
0x180030330  mov     rdi, r8
0x180030333  mov     [rbp+2D0h+lpNewFileName], r8
0x180030337  mov     rsi, rdx
0x18003033a  mov     r12, rcx
0x18003033d  xor     r14d, r14d
0x180030340  lea     rcx, [rbp+2D0h+var_2FC]; void *
0x180030344  xor     edx, edx; Val
0x180030346  mov     [rsp+3D0h+var_390], r14d
0x18003034b  mov     r8d, 0A0h; Size
0x180030351  mov     [rbp+2D0h+Buffer], r14d
0x180030355  mov     ebx, r9d
0x180030358  call    memset_0
0x18003035d  xorps   xmm0, xmm0
0x180030360  mov     [rsp+3D0h+NumberOfBytesRead], r14d
0x180030365  xor     edx, edx; Val
0x180030367  mov     [rsp+3D0h+var_388], r14
0x18003036c  mov     r8d, 208h; Size
0x180030372  mov     [rsp+3D0h+var_378], r14
0x180030377  lea     rcx, [rbp+2D0h+FileName]; void *
0x18003037e  mov     [rsp+3D0h+var_370], r14
0x180030383  movups  [rbp+2D0h+var_320], xmm0
0x180030387  mov     [rsp+3D0h+var_368], r14
0x18003038c  movups  xmmword ptr [rbp+2D0h+var_310], xmm0
0x180030390  mov     [rsp+3D0h+var_358], r14
0x180030395  call    memset_0
0x18003039a  test    rdi, rdi
0x18003039d  jz      short loc_1800303BF
0x18003039f  mov     rdx, [r12+10h]; lpString2
0x1800303a4  mov     rcx, rdi; lpString1
0x1800303a7  call    cs:__imp_lstrcmpiW
0x1800303ad  test    eax, eax
0x1800303af  jz      loc_180030997
0x1800303b5  mov     [rsp+3D0h+var_380], 1
0x1800303bd  jmp     short loc_1800303C4
0x1800303bf  mov     [rsp+3D0h+var_380], r14d
0x1800303c4  lea     rcx, [rbp+2D0h+FileName]; unsigned __int16 *
0x1800303cb  call    ?GetWABTempFileName@@YAXPEAGK@Z
0x1800303d0  mov     r9, [r12+18h]
0x1800303d5  mov     eax, 10624DD3h
0x1800303da  mov     r8d, r14d
0x1800303dd  mov     ecx, [r9+7Ch]
0x1800303e1  mul     ecx
0x1800303e3  shr     edx, 5
0x1800303e6  test    edx, edx
0x1800303e8  js      short loc_180030401
0x1800303ea  imul    eax, edx, 1F4h
0x1800303f0  cmp     [r9+78h], eax
0x1800303f4  jnb     short loc_1800303FA
0x1800303f6  dec     edx
0x1800303f8  jmp     short loc_1800303E6
0x1800303fa  lea     r8d, [rax+1F4h]
0x180030401  mov     r9d, [r9+84h]; unsigned int
0x180030408  test    r8d, r8d
0x18003040b  cmovnz  ecx, r8d
0x18003040f  test    ebx, ebx
0x180030411  jz      short loc_180030437
0x180030413  test    byte ptr [rbp+2D0h+arg_20], 1
0x18003041a  lea     r8d, [rcx+1F4h]
0x180030421  cmovz   r8d, ecx
0x180030425  test    byte ptr [rbp+2D0h+arg_20], 10h
0x18003042c  jz      short loc_18003043A
0x18003042e  add     r9d, 800h
0x180030435  jmp     short loc_18003043A
0x180030437  mov     r8d, ecx; unsigned int
0x18003043a  lea     rdx, [rbp+2D0h+FileName]; lpFileName
0x180030441  lea     rcx, [rbp+2D0h+Buffer]; lpBuffer
0x180030445  call    ?CreateMPSWabFile@@YAHPEAU_tagMPSWabFileHeader@@PEAGKK@Z
0x18003044a  test    eax, eax
0x18003044c  jz      loc_180030997
0x180030452  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x180030456  jz      loc_180030997
0x18003045c  mov     [rsp+3D0h+hTemplateFile], r14; hTemplateFile
0x180030461  lea     rcx, [rbp+2D0h+FileName]; lpFileName
0x180030468  mov     r8d, 3; dwShareMode
0x18003046e  mov     [rsp+3D0h+dwFlagsAndAttributes], 10000000h; dwFlagsAndAttributes
0x180030476  xor     r9d, r9d; lpSecurityAttributes
0x180030479  mov     [rsp+3D0h+dwCreationDisposition], r8d; dwCreationDisposition
0x18003047e  mov     edx, 0C0000000h; dwDesiredAccess
0x180030483  call    cs:__imp_CreateFileW
0x180030489  mov     rbx, rax
0x18003048c  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180030490  jz      loc_18003094B
0x180030496  xor     edx, edx; lpFileSizeHigh
0x180030498  mov     rcx, rsi; hFile
0x18003049b  call    cs:__imp_GetFileSize
0x1800304a1  mov     rdx, [r12+18h]
0x1800304a6  mov     r8, r14
0x1800304a9  mov     [rsp+3D0h+var_360], eax
0x1800304ad  mov     ecx, [rdx+78h]
0x1800304b0  mov     [rbp+2D0h+var_288], ecx
0x1800304b3  mov     [rbp+2D0h+var_2F0], r14d
0x1800304b7  mov     ecx, [rdx+14h]
0x1800304ba  mov     [rbp+2D0h+var_2EC], ecx
0x1800304bd  mov     rcx, r14
0x1800304c0  mov     eax, [rdx+80h]
0x1800304c6  mov     [rbp+2D0h+var_280], eax
0x1800304c9  mov     eax, [rdx+88h]
0x1800304cf  mov     dword ptr [rbp+2D0h+uBytes], eax
0x1800304d2  mov     eax, [rdx+90h]
0x1800304d8  mov     [rbp+2D0h+var_270], eax
0x1800304db  mov     eax, [rdx+94h]
0x1800304e1  mov     [rbp+2D0h+var_26C], eax
0x1800304e4  mov     eax, [rdx+98h]
0x1800304ea  mov     [rbp+2D0h+var_268], eax
0x1800304ed  mov     eax, [rdx+9Ch]
0x1800304f3  mov     [rbp+2D0h+var_264], eax
0x1800304f6  mov     eax, [rdx+0A0h]
0x1800304fc  mov     [rbp+2D0h+var_260], eax
0x1800304ff  mov     eax, [rdx+rcx+1Ch]
0x180030503  inc     r8
0x180030506  mov     dword ptr [rbp+rcx+2D0h+var_2E4], eax
0x18003050a  mov     eax, [rdx+rcx+24h]
0x18003050e  mov     [rbp+rcx+2D0h+var_2DC], eax
0x180030512  lea     rcx, [rcx+10h]
0x180030516  cmp     r8, 6
0x18003051a  jnz     short loc_1800304FF
0x18003051c  mov     r9d, 0A4h; unsigned int
0x180030522  lea     r8, [rbp+2D0h+Buffer]; void *
0x180030526  xor     edx, edx; unsigned int
0x180030528  mov     rcx, rbx; hFile
0x18003052b  call    ?WriteDataToWABFile@@YAHPEAXK0K@Z
0x180030530  test    eax, eax
0x180030532  jz      loc_18003094B
0x180030538  mov     edx, dword ptr [rbp+2D0h+uBytes]; uBytes
0x18003053b  mov     ecx, 40h ; '@'; uFlags
0x180030540  call    cs:__imp_LocalAlloc
0x180030546  mov     [rsp+3D0h+var_358], rax
0x18003054b  mov     rdi, rax
0x18003054e  test    rax, rax
0x180030551  jz      loc_18003094B
0x180030557  mov     rdx, [r12+18h]
0x18003055c  xor     r9d, r9d; dwMoveMethod
0x18003055f  xor     r8d, r8d; lpDistanceToMoveHigh
0x180030562  mov     rcx, rsi; hFile
0x180030565  mov     edx, [rdx+8Ch]; lDistanceToMove
0x18003056b  call    cs:__imp_SetFilePointer
0x180030571  or      r13d, 0FFFFFFFFh
0x180030575  cmp     eax, r13d
0x180030578  jz      loc_18003094B
0x18003057e  mov     edx, dword ptr [rbp+2D0h+uBytes+4]; lDistanceToMove
0x180030581  xor     r9d, r9d; dwMoveMethod
0x180030584  xor     r8d, r8d; lpDistanceToMoveHigh
0x180030587  mov     rcx, rbx; hFile
0x18003058a  call    cs:__imp_SetFilePointer
0x180030590  cmp     eax, r13d
0x180030593  jz      loc_18003094B
0x180030599  mov     r8d, dword ptr [rbp+2D0h+uBytes]; nNumberOfBytesToRead
0x18003059d  lea     r9, [rsp+3D0h+NumberOfBytesRead]; lpNumberOfBytesRead
0x1800305a2  mov     rdx, rdi; lpBuffer
0x1800305a5  mov     qword ptr [rsp+3D0h+dwCreationDisposition], r14; lpOverlapped
0x1800305aa  mov     rcx, rsi; hFile
0x1800305ad  call    cs:__imp_ReadFile
0x1800305b3  test    eax, eax
0x1800305b5  jz      loc_18003094B
0x1800305bb  mov     r8d, dword ptr [rbp+2D0h+uBytes]; nNumberOfBytesToWrite
0x1800305bf  cmp     [rsp+3D0h+NumberOfBytesRead], r8d
0x1800305c4  jnz     loc_18003094B
0x1800305ca  lea     r9, [rsp+3D0h+NumberOfBytesRead]; lpNumberOfBytesWritten
0x1800305cf  mov     qword ptr [rsp+3D0h+dwCreationDisposition], r14; lpOverlapped
0x1800305d4  mov     rdx, rdi; lpBuffer
0x1800305d7  mov     rcx, rbx; hFile
0x1800305da  call    cs:__imp_WriteFile
0x1800305e0  test    eax, eax
0x1800305e2  jz      loc_18003094B
0x1800305e8  lea     rcx, [rsp+3D0h+var_358]; void **
0x1800305ed  call    ?LocalFreeAndNull@@YAXPEAPEAX@Z
0x1800305f2  mov     r14d, 1
0x1800305f8  cmp     r14d, 6
0x1800305fc  jnb     loc_1800306E7
0x180030602  lea     rcx, [rsp+3D0h+var_388]; void **
0x180030607  call    ?LocalFreeAndNull@@YAXPEAPEAX@Z
0x18003060c  mov     edi, r14d
0x18003060f  mov     ecx, 40h ; '@'; uFlags
0x180030614  add     rdi, rdi
0x180030617  mov     r13d, r14d
0x18003061a  mov     edx, dword ptr [rbp+rdi*8+2D0h+var_2E4]; uBytes
0x18003061e  call    cs:__imp_LocalAlloc
0x180030624  mov     [rsp+3D0h+var_388], rax
0x180030629  mov     r15, rax
0x18003062c  test    rax, rax
0x18003062f  jz      loc_18003098E
0x180030635  mov     rdx, [r12+18h]
0x18003063a  lea     rax, [r13+2]
0x18003063e  add     rax, rax
0x180030641  xor     r9d, r9d; dwMoveMethod
0x180030644  xor     r8d, r8d; lpDistanceToMoveHigh
0x180030647  mov     rcx, rsi; hFile
0x18003064a  mov     edx, [rdx+rax*8]; lDistanceToMove
0x18003064d  call    cs:__imp_SetFilePointer
0x180030653  or      r13d, 0FFFFFFFFh
0x180030657  cmp     eax, r13d
0x18003065a  jz      loc_18003098E
0x180030660  mov     edx, dword ptr [rbp+rdi*8+2D0h+var_2E4+4]; lDistanceToMove
0x180030664  xor     r9d, r9d; dwMoveMethod
0x180030667  xor     r8d, r8d; lpDistanceToMoveHigh
0x18003066a  mov     rcx, rbx; hFile
0x18003066d  call    cs:__imp_SetFilePointer
0x180030673  cmp     eax, r13d
0x180030676  jz      loc_18003098E
0x18003067c  mov     r8d, dword ptr [rbp+rdi*8+2D0h+var_2E4]; nNumberOfBytesToRead
0x180030681  lea     r9, [rsp+3D0h+NumberOfBytesRead]; lpNumberOfBytesRead
0x180030686  mov     rdx, r15; lpBuffer
0x180030689  mov     qword ptr [rsp+3D0h+dwCreationDisposition], 0; lpOverlapped
0x180030692  mov     rcx, rsi; hFile
0x180030695  call    cs:__imp_ReadFile
0x18003069b  test    eax, eax
0x18003069d  jz      loc_18003098E
0x1800306a3  mov     r8d, dword ptr [rbp+rdi*8+2D0h+var_2E4]; nNumberOfBytesToWrite
0x1800306a8  cmp     [rsp+3D0h+NumberOfBytesRead], r8d
0x1800306ad  jnz     loc_18003098E
0x1800306b3  lea     r9, [rsp+3D0h+NumberOfBytesRead]; lpNumberOfBytesWritten
0x1800306b8  mov     qword ptr [rsp+3D0h+dwCreationDisposition], 0; lpOverlapped
0x1800306c1  mov     rdx, r15; lpBuffer
0x1800306c4  mov     rcx, rbx; hFile
0x1800306c7  call    cs:__imp_WriteFile
0x1800306cd  test    eax, eax
0x1800306cf  jz      loc_18003098E
0x1800306d5  lea     rcx, [rsp+3D0h+var_388]; void **
0x1800306da  call    ?LocalFreeAndNull@@YAXPEAPEAX@Z
0x1800306df  inc     r14d
0x1800306e2  jmp     loc_1800305F8
0x1800306e7  mov     r8, rsi; void *
0x1800306ea  xor     edx, edx; unsigned int
0x1800306ec  mov     rcx, r12; struct _tagMPSWabFileInfo *
0x1800306ef  call    ?LoadIndex@@YAHPEAU_tagMPSWabFileInfo@@KPEAX@Z
0x1800306f4  xor     r14d, r14d
0x1800306f7  test    eax, eax
0x1800306f9  jz      loc_18003094B
0x1800306ff  mov     r14d, [rbp+2D0h+var_298]
0x180030703  add     r14d, [rbp+2D0h+var_290]
0x180030707  mov     r13d, dword ptr [rbp+2D0h+var_2E4+4]
0x18003070b  xor     r15d, r15d
0x18003070e  mov     [rsp+3D0h+var_388], r14
0x180030713  cmp     r15d, [rbp+2D0h+var_2DC]
0x180030717  jnb     loc_18003090B
0x18003071d  mov     rdx, [r12+28h]
0x180030722  lea     r8, [rbp+2D0h+var_320]; void *
0x180030726  mov     r9d, 20h ; ' '; unsigned int
0x18003072c  mov     rcx, rsi; hFile
0x18003072f  mov     eax, [rdx+r15*8]
0x180030733  mov     dword ptr [rsp+3D0h+var_378], eax
0x180030737  mov     dword ptr [rsp+3D0h+var_378+4], r14d
0x18003073c  mov     edx, [rdx+r15*8+4]; unsigned int
0x180030741  call    ?ReadDataFromWABFile@@YAHPEAXK0K@Z
0x180030746  test    eax, eax
0x180030748  jz      loc_18003098E
0x18003074e  mov     r8, [r12+28h]
0x180030753  lea     rcx, [rbp+2D0h+var_340]
0x180030757  mov     rdx, [r12+18h]
0x18003075c  mov     eax, dword ptr [rsp+3D0h+var_378]
0x180030760  movups  xmm0, [rbp+2D0h+var_320]
0x180030764  mov     r8d, [r8+r15*8+4]
0x180030769  movups  xmm1, xmmword ptr [rbp+2D0h+var_310]
0x18003076d  mov     edx, [rdx+14h]
0x180030770  mov     r9d, [rsp+3D0h+var_360]
0x180030775  mov     [rsp+3D0h+dwFlagsAndAttributes], eax
0x180030779  movaps  [rbp+2D0h+var_340], xmm0
0x18003077d  movaps  [rbp+2D0h+var_330], xmm1
0x180030781  mov     [rsp+3D0h+dwCreationDisposition], 1
0x180030789  call    ?bIsValidRecord@@YAHU_tagMPSWabRecordHeader@@KKKHK@Z
0x18003078e  test    eax, eax
0x180030790  jz      loc_180030903
0x180030796  lea     rcx, [rsp+3D0h+var_370]; void **
0x18003079b  call    ?LocalFreeAndNull@@YAXPEAPEAX@Z
0x1800307a0  mov     edx, dword ptr [rbp+2D0h+var_310+4]; uBytes
0x1800307a3  mov     edi, 40h ; '@'
0x1800307a8  mov     ecx, edi; uFlags
0x1800307aa  call    cs:__imp_LocalAlloc
0x1800307b0  mov     [rsp+3D0h+var_370], rax
0x1800307b5  mov     r14, rax
0x1800307b8  test    rax, rax
0x1800307bb  jz      loc_18003098E
0x1800307c1  mov     r8d, dword ptr [rbp+2D0h+var_310+4]; nNumberOfBytesToRead
0x1800307c5  lea     r9, [rsp+3D0h+NumberOfBytesRead]; lpNumberOfBytesRead
0x1800307ca  mov     rdx, rax; lpBuffer
0x1800307cd  mov     qword ptr [rsp+3D0h+dwCreationDisposition], 0; lpOverlapped
0x1800307d6  mov     rcx, rsi; hFile
0x1800307d9  call    cs:__imp_ReadFile
0x1800307df  test    eax, eax
0x1800307e1  jz      loc_18003098E
0x1800307e7  mov     eax, dword ptr [rbp+2D0h+var_310+4]
0x1800307ea  cmp     [rsp+3D0h+NumberOfBytesRead], eax
0x1800307ee  jnz     loc_18003098E
0x1800307f4  lea     rcx, [rsp+3D0h+var_368]; void **
0x1800307f9  call    ?LocalFreeAndNull@@YAXPEAPEAX@Z
0x1800307fe  mov     edx, dword ptr [rbp+2D0h+var_310+0Ch]; uBytes
0x180030801  mov     ecx, edi; uFlags
  ... truncated ...
```
