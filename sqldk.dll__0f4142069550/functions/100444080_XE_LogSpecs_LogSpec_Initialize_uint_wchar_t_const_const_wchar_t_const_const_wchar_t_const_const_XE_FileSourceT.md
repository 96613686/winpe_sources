# XE_LogSpecs::LogSpec::Initialize(uint,wchar_t const * const,wchar_t const * const,wchar_t const * const,XE_FileSourceType,bool,bool)

- ea: `0x100444080`
- end: `0x10044444e`
- name: `?Initialize@LogSpec@XE_LogSpecs@@AEAAHIQEB_W00W4XE_FileSourceType@@_N2@Z`
- size: `974`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x100443a20`

## callees

- `0x100403070`
- `0x100404bf2`
- `0x100444080`
- `0x100444860`

## import_xrefs

- `KERNEL32!GetVolumePathNameW` at `0x1004442f9`
- `KERNEL32!GetVolumePathNameW` at `0x1004442f9`
- `KERNEL32!GetSystemTime` at `0x100444290`
- `KERNEL32!GetSystemTime` at `0x100444290`
- `KERNEL32!GetSystemInfo` at `0x1004442dd`
- `KERNEL32!GetSystemInfo` at `0x1004442dd`
- `KERNEL32!GetDiskFreeSpaceW` at `0x1004443fa`
- `KERNEL32!GetDiskFreeSpaceW` at `0x1004443fa`

## pseudocode

```c
__int64 __fastcall XE_LogSpecs::LogSpec::Initialize(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        int a6,
        char a7,
        char a8)
{
  unsigned int v8; // ebp
  bool v12; // r12
  __int64 v13; // rdx
  _WORD *v14; // rcx
  __int64 v15; // rbx
  __int16 v16; // ax
  bool v17; // zf
  _WORD *v18; // rax
  __int16 *v19; // rsi
  __int64 v20; // rdx
  _WORD *v21; // rcx
  __int64 v22; // rdi
  __int16 v23; // ax
  _WORD *v24; // rax
  __int64 v25; // rdi
  __int64 v26; // rax
  __int64 v27; // rax
  _WORD *v28; // rcx
  _WORD *v29; // rbx
  __int64 v30; // rax
  __int64 v31; // rcx
  __int64 v32; // rdx
  __int16 v33; // ax
  _WORD *v34; // rax
  __int16 v35; // r8
  __int16 *v36; // rdx
  int i; // ecx
  int v38; // eax
  __int16 v39; // r8
  int j; // edx
  int v41; // eax
  unsigned int v42; // ecx
  DWORD TotalNumberOfClusters; // [rsp+40h] [rbp-6B8h] BYREF
  DWORD NumberOfFreeClusters; // [rsp+44h] [rbp-6B4h] BYREF
  DWORD SectorsPerCluster; // [rsp+48h] [rbp-6B0h] BYREF
  _SYSTEM_INFO SystemInfo; // [rsp+50h] [rbp-6A8h] BYREF
  _SYSTEMTIME SystemTime; // [rsp+80h] [rbp-678h] BYREF
  _WORD v49[264]; // [rsp+90h] [rbp-668h] BYREF
  WCHAR szFileName[264]; // [rsp+2A0h] [rbp-458h] BYREF
  WCHAR szVolumePathName[264]; // [rsp+4B0h] [rbp-248h] BYREF

  v8 = 0;
  *(_DWORD *)(a1 + 1568) = a6;
  *(_BYTE *)(a1 + 1577) = a8;
  *(_BYTE *)(a1 + 1576) = a7;
  *(_DWORD *)a1 = a2;
  v12 = qword_100715060 && (unsigned __int8)qword_100715060(a3, 260);
  v13 = 260;
  v14 = (_WORD *)(a1 + 4);
  v15 = a3 - (a1 + 4);
  do
  {
    if ( v13 == -2147483386 )
      break;
    v16 = *(_WORD *)((char *)v14 + v15);
    if ( !v16 )
      break;
    *v14++ = v16;
    --v13;
  }
  while ( v13 );
  v17 = v13 == 0;
  v18 = v14 - 1;
  v19 = (__int16 *)(a1 + 524);
  v20 = 260;
  if ( !v17 )
    v18 = v14;
  v21 = (_WORD *)(a1 + 524);
  v22 = a4 - (_QWORD)v19;
  *v18 = 0;
  do
  {
    if ( v20 == -2147483386 )
      break;
    v23 = *(_WORD *)((char *)v21 + v22);
    if ( !v23 )
      break;
    *v21++ = v23;
    --v20;
  }
  while ( v20 );
  v24 = v21 - 1;
  if ( v20 )
    v24 = v21;
  *v24 = 0;
  qword_1007150C0(a1 + 524, 260);
  v25 = -1;
  if ( v12 )
  {
    v26 = -1;
    do
      ++v26;
    while ( *(_WORD *)(a1 + 4 + 2 * v26) );
    v27 = (unsigned int)(v26 - 1);
    if ( (_DWORD)v27 )
    {
      v28 = (_WORD *)(a1 + 4 + 2LL * (unsigned int)v27);
      do
      {
        if ( *v28 != 47 )
          break;
        --v28;
        --v27;
      }
      while ( v27 );
    }
    *(_DWORD *)(a1 + 2 * v27 + 6) = 47;
  }
  v29 = (_WORD *)(a1 + 1044);
  qword_1007150D0(a1 + 524, a1 + 1044, 260);
  v30 = -1;
  do
    ++v30;
  while ( v29[v30] );
  if ( !(_DWORD)v30 && a5 )
  {
    do
      ++v25;
    while ( *(_WORD *)(a5 + 2 * v25) );
    if ( (_DWORD)v25 )
    {
      v31 = 260;
      v32 = a5 - (_QWORD)v29;
      do
      {
        if ( v31 == -2147483386 )
          break;
        v33 = *(_WORD *)((char *)v29 + v32);
        if ( !v33 )
          break;
        *v29++ = v33;
        --v31;
      }
      while ( v31 );
      v34 = v29 - 1;
      if ( v31 )
        v34 = v29;
      *v34 = 0;
    }
  }
  qword_1007150B8(a1 + 524, 260);
  if ( v12 )
  {
    *(_DWORD *)(a1 + 1564) = 512;
    return 1;
  }
  else
  {
    GetSystemTime(&SystemTime);
    if ( (unsigned int)XE_LogSpecs::LogSpec::CreateFilePathInternal(
                         a1,
                         0x7FFFFFFFFFFFFFFFLL,
                         szFileName,
                         260,
                         &SystemTime,
                         0,
                         1) )
    {
      GetSystemInfo(&SystemInfo);
      if ( GetVolumePathNameW(szFileName, szVolumePathName, 0x104u) )
      {
        memset_0(v49, 0, 0x208u);
        if ( (unsigned int)qword_1007150D8(szFileName, v49, 260) )
        {
          if ( (unsigned int)qword_1007150B8(v49, 260) )
          {
            v35 = v49[0];
            v36 = v49;
            for ( i = 0; *v36; v35 = *v36 )
            {
              v38 = i + 1;
              ++v36;
              if ( v35 != 95 )
                v38 = i;
              i = v38;
            }
            if ( a1 != -524 )
            {
              v39 = *v19;
              for ( j = 0; v39; j = v41 )
              {
                v17 = v39 == 95;
                v41 = j + 1;
                v39 = v19[1];
                ++v19;
                if ( !v17 )
                  v41 = j;
              }
              *(_DWORD *)(a1 + 1572) = i - j - 1;
              if ( GetDiskFreeSpaceW(
                     szVolumePathName,
                     &SectorsPerCluster,
                     (LPDWORD)(a1 + 1564),
                     &NumberOfFreeClusters,
                     &TotalNumberOfClusters) )
              {
                v42 = *(_DWORD *)(a1 + 1564);
                if ( v42 )
                {
                  if ( SystemInfo.dwAllocationGranularity / v42 && !(SystemInfo.dwAllocationGranularity % v42) )
                    return 1;
                }
              }
            }
          }
        }
      }
    }
  }
  return v8;
}

```

## disassembly

```asm
0x100444080  mov     [rsp+arg_8], rbx
0x100444085  mov     [rsp+arg_18], rbp
0x10044408a  push    rsi
0x10044408b  push    rdi
0x10044408c  push    r12
0x10044408e  push    r14
0x100444090  push    r15
0x100444092  sub     rsp, 6D0h
0x100444099  mov     rax, cs:__security_cookie
0x1004440a0  xor     rax, rsp
0x1004440a3  mov     [rsp+6F8h+var_38], rax
0x1004440ab  mov     eax, [rsp+6F8h+arg_28]
0x1004440b2  xor     ebp, ebp
0x1004440b4  mov     [rcx+620h], eax
0x1004440ba  mov     rdi, r9
0x1004440bd  movzx   eax, [rsp+6F8h+arg_38]
0x1004440c5  mov     rbx, r8
0x1004440c8  mov     [rcx+629h], al
0x1004440ce  mov     r15, rcx
0x1004440d1  movzx   eax, [rsp+6F8h+arg_30]
0x1004440d9  mov     [rcx+628h], al
0x1004440df  mov     [rcx], edx
0x1004440e1  mov     rax, cs:qword_100715060
0x1004440e8  test    rax, rax
0x1004440eb  jz      short loc_100444100
0x1004440ed  mov     edx, 104h
0x1004440f2  mov     rcx, rbx
0x1004440f5  call    rax ; qword_100715060
0x1004440f7  test    al, al
0x1004440f9  jz      short loc_100444100
0x1004440fb  mov     r12b, 1
0x1004440fe  jmp     short loc_100444103
0x100444100  xor     r12b, r12b
0x100444103  lea     r14, [r15+4]
0x100444107  mov     edx, 104h
0x10044410c  mov     rcx, r14
0x10044410f  sub     rbx, r14
0x100444112  lea     rax, [rdx+7FFFFEFAh]
0x100444119  test    rax, rax
0x10044411c  jz      short loc_100444134
0x10044411e  movzx   eax, word ptr [rbx+rcx]
0x100444122  test    ax, ax
0x100444125  jz      short loc_100444134
0x100444127  mov     [rcx], ax
0x10044412a  add     rcx, 2
0x10044412e  sub     rdx, 1
0x100444132  jnz     short loc_100444112
0x100444134  test    rdx, rdx
0x100444137  lea     rax, [rcx-2]
0x10044413b  lea     rsi, [r15+20Ch]
0x100444142  mov     edx, 104h
0x100444147  cmovnz  rax, rcx
0x10044414b  mov     rcx, rsi
0x10044414e  sub     rdi, rsi
0x100444151  mov     [rax], bp
0x100444154  lea     rax, [rdx+7FFFFEFAh]
0x10044415b  test    rax, rax
0x10044415e  jz      short loc_100444176
0x100444160  movzx   eax, word ptr [rdi+rcx]
0x100444164  test    ax, ax
0x100444167  jz      short loc_100444176
0x100444169  mov     [rcx], ax
0x10044416c  add     rcx, 2
0x100444170  sub     rdx, 1
0x100444174  jnz     short loc_100444154
0x100444176  test    rdx, rdx
0x100444179  lea     rax, [rcx-2]
0x10044417d  mov     edx, 104h
0x100444182  cmovnz  rax, rcx
0x100444186  mov     rcx, rsi
0x100444189  mov     [rax], bp
0x10044418c  call    cs:qword_1007150C0
0x100444192  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x100444199  test    r12b, r12b
0x10044419c  jz      short loc_1004441D4
0x10044419e  mov     rax, rdi
0x1004441a1  inc     rax
0x1004441a4  cmp     [r14+rax*2], bp
0x1004441a9  jnz     short loc_1004441A1
0x1004441ab  mov     edx, 2Fh ; '/'
0x1004441b0  sub     eax, 1
0x1004441b3  jz      short loc_1004441CF
0x1004441b5  lea     rcx, [r15+4]
0x1004441b9  lea     rcx, [rcx+rax*2]
0x1004441bd  nop     dword ptr [rax]
0x1004441c0  cmp     dx, [rcx]
0x1004441c3  jnz     short loc_1004441CF
0x1004441c5  sub     rcx, 2
0x1004441c9  sub     rax, 1
0x1004441cd  jnz     short loc_1004441C0
0x1004441cf  mov     [r15+rax*2+6], edx
0x1004441d4  lea     rbx, [r15+414h]
0x1004441db  mov     r8d, 104h
0x1004441e1  mov     rdx, rbx
0x1004441e4  mov     rcx, rsi
0x1004441e7  call    cs:qword_1007150D0
0x1004441ed  mov     rax, rdi
0x1004441f0  inc     rax
0x1004441f3  cmp     [rbx+rax*2], bp
0x1004441f7  jnz     short loc_1004441F0
0x1004441f9  test    eax, eax
0x1004441fb  jnz     short loc_100444260
0x1004441fd  mov     rdx, [rsp+6F8h+arg_20]
0x100444205  test    rdx, rdx
0x100444208  jz      short loc_100444260
0x10044420a  nop     word ptr [rax+rax]
0x10044420f  nop
0x100444210  inc     rdi
0x100444213  cmp     [rdx+rdi*2], bp
0x100444217  jnz     short loc_100444210
0x100444219  test    edi, edi
0x10044421b  jz      short loc_100444260
0x10044421d  mov     ecx, 104h
0x100444222  sub     rdx, rbx
0x100444225  nop     word ptr [rax+rax+00000000h]
0x100444230  lea     rax, [rcx+7FFFFEFAh]
0x100444237  test    rax, rax
0x10044423a  jz      short loc_100444252
0x10044423c  movzx   eax, word ptr [rdx+rbx]
0x100444240  test    ax, ax
0x100444243  jz      short loc_100444252
0x100444245  mov     [rbx], ax
0x100444248  add     rbx, 2
0x10044424c  sub     rcx, 1
0x100444250  jnz     short loc_100444230
0x100444252  test    rcx, rcx
0x100444255  lea     rax, [rbx-2]
0x100444259  cmovnz  rax, rbx
0x10044425d  mov     [rax], bp
0x100444260  mov     edx, 104h
0x100444265  mov     rcx, rsi
0x100444268  call    cs:qword_1007150B8
0x10044426e  test    r12b, r12b
0x100444271  jz      short loc_100444288
0x100444273  mov     dword ptr [r15+61Ch], 200h
0x10044427e  mov     ebp, 1
0x100444283  jmp     loc_100444420
0x100444288  lea     rcx, [rsp+6F8h+SystemTime]; lpSystemTime
0x100444290  call    cs:__imp_GetSystemTime
0x100444296  lea     rax, [rsp+6F8h+SystemTime]
0x10044429e  mov     ebx, 1
0x1004442a3  mov     [rsp+6F8h+var_6C8], ebx
0x1004442a7  lea     r8, [rsp+6F8h+szFileName]
0x1004442af  mov     [rsp+6F8h+var_6D0], ebp
0x1004442b3  mov     r9d, 104h
0x1004442b9  mov     rdx, 7FFFFFFFFFFFFFFFh
0x1004442c3  mov     [rsp+6F8h+lpTotalNumberOfClusters], rax
0x1004442c8  mov     rcx, r15
0x1004442cb  call    ?CreateFilePathInternal@LogSpec@XE_LogSpecs@@AEBAH_JQEA_WIAEBU_SYSTEMTIME@@IW4XE_FileSourceType@@@Z; XE_LogSpecs::LogSpec::CreateFilePathInternal(__int64,wchar_t * const,uint,_SYSTEMTIME const &,uint,XE_FileSourceType)
0x1004442d0  test    eax, eax
0x1004442d2  jz      loc_100444420
0x1004442d8  lea     rcx, [rsp+6F8h+SystemInfo]; lpSystemInfo
0x1004442dd  call    cs:__imp_GetSystemInfo
0x1004442e3  mov     r8d, 104h; cchBufferLength
0x1004442e9  lea     rdx, [rsp+6F8h+szVolumePathName]; lpszVolumePathName
0x1004442f1  lea     rcx, [rsp+6F8h+szFileName]; lpszFileName
0x1004442f9  call    cs:__imp_GetVolumePathNameW
0x1004442ff  test    eax, eax
0x100444301  jz      loc_100444420
0x100444307  xor     edx, edx; Val
0x100444309  lea     rcx, [rsp+6F8h+var_668]; void *
0x100444311  mov     r8d, 208h; Size
0x100444317  call    memset_0
0x10044431c  mov     r8d, 104h
0x100444322  lea     rdx, [rsp+6F8h+var_668]
0x10044432a  lea     rcx, [rsp+6F8h+szFileName]
0x100444332  call    cs:qword_1007150D8
0x100444338  test    eax, eax
0x10044433a  jz      loc_100444420
0x100444340  mov     edx, 104h
0x100444345  lea     rcx, [rsp+6F8h+var_668]
0x10044434d  call    cs:qword_1007150B8
0x100444353  test    eax, eax
0x100444355  jz      loc_100444420
0x10044435b  mov     r8, qword ptr [rsp+6F8h+var_668]
0x100444363  lea     rdx, [rsp+6F8h+var_668]
0x10044436b  mov     ecx, ebp
0x10044436d  test    r8w, r8w
0x100444371  jz      short loc_10044439D
0x100444373  nop     dword ptr [rax+00h]
0x100444377  nop     word ptr [rax+rax+00000000h]
0x100444380  cmp     r8w, 5Fh ; '_'
0x100444385  lea     eax, [rcx+1]
0x100444388  lea     rdx, [rdx+2]
0x10044438c  cmovnz  eax, ecx
0x10044438f  mov     ecx, eax
0x100444391  movzx   eax, word ptr [rdx]
0x100444394  movzx   r8d, ax
0x100444398  test    ax, ax
0x10044439b  jnz     short loc_100444380
0x10044439d  test    rsi, rsi
0x1004443a0  jz      short loc_100444420
0x1004443a2  movzx   r8d, word ptr [rsi]
0x1004443a6  mov     edx, ebp
0x1004443a8  test    r8w, r8w
0x1004443ac  jz      short loc_1004443CC
0x1004443ae  nop
0x1004443af  nop
0x1004443b0  cmp     r8w, 5Fh ; '_'
0x1004443b5  lea     eax, [rdx+1]
0x1004443b8  movzx   r8d, word ptr [rsi+2]
0x1004443bd  lea     rsi, [rsi+2]
0x1004443c1  cmovnz  eax, edx
0x1004443c4  mov     edx, eax
0x1004443c6  test    r8w, r8w
0x1004443ca  jnz     short loc_1004443B0
0x1004443cc  sub     ecx, edx
0x1004443ce  lea     rax, [rsp+6F8h+TotalNumberOfClusters]
0x1004443d3  dec     ecx
0x1004443d5  mov     [rsp+6F8h+lpTotalNumberOfClusters], rax; lpTotalNumberOfClusters
0x1004443da  mov     [r15+624h], ecx
0x1004443e1  lea     r9, [rsp+6F8h+NumberOfFreeClusters]; lpNumberOfFreeClusters
0x1004443e6  lea     rcx, [rsp+6F8h+szVolumePathName]; lpRootPathName
0x1004443ee  lea     r8, [r15+61Ch]; lpBytesPerSector
0x1004443f5  lea     rdx, [rsp+6F8h+SectorsPerCluster]; lpSectorsPerCluster
0x1004443fa  call    cs:__imp_GetDiskFreeSpaceW
0x100444400  test    eax, eax
0x100444402  jz      short loc_100444420
0x100444404  mov     ecx, [r15+61Ch]
0x10044440b  test    ecx, ecx
0x10044440d  jz      short loc_100444420
0x10044440f  mov     eax, [rsp+6F8h+SystemInfo.dwAllocationGranularity]
0x100444413  xor     edx, edx
0x100444415  div     ecx
0x100444417  test    eax, eax
0x100444419  jz      short loc_100444420
0x10044441b  test    edx, edx
0x10044441d  cmovz   ebp, ebx
0x100444420  mov     eax, ebp
0x100444422  mov     rcx, [rsp+6F8h+var_38]
0x10044442a  xor     rcx, rsp; StackCookie
0x10044442d  call    __security_check_cookie
0x100444432  lea     r11, [rsp+6F8h+var_28]
0x10044443a  mov     rbx, [r11+38h]
0x10044443e  mov     rbp, [r11+48h]
0x100444442  mov     rsp, r11
0x100444445  pop     r15
0x100444447  pop     r14
0x100444449  pop     r12
0x10044444b  pop     rdi
0x10044444c  pop     rsi
0x10044444d  retn
```
