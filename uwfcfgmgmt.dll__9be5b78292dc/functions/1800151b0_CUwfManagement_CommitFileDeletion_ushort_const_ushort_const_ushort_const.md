# CUwfManagement::CommitFileDeletion(ushort const *,ushort const *,ushort const *)

- ea: `0x1800151b0`
- end: `0x1800155e4`
- name: `?CommitFileDeletion@CUwfManagement@@QEAAJPEBG00@Z`
- size: `1076`
- prototype: `__int64 __fastcall(HKEY *this, const unsigned __int16 *, unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180018080`

## callees

- `0x1800054d0`
- `0x180008cf0`
- `0x18000b6b0`
- `0x18000e320`
- `0x180012b00`
- `0x180013100`
- `0x1800139f0`
- `0x1800147d0`
- `0x1800151b0`
- `0x180016468`
- `0x18001afe2`
- `0x18001b020`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x18001537d`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18001537d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800152f1`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001540d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800152f1`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001540d`

## pseudocode

```c
__int64 __fastcall CUwfManagement::CommitFileDeletion(
        HKEY *this,
        const unsigned __int16 *a2,
        unsigned __int16 *a3,
        const unsigned __int16 *a4)
{
  __int64 v8; // rsi
  unsigned __int16 *v9; // r12
  CUwfStaticConfiguration *v10; // r15
  __int64 v11; // rcx
  __int64 v12; // rax
  __int64 v13; // rax
  __int64 v14; // rax
  int v15; // eax
  HKEY v16; // rcx
  LSTATUS v17; // eax
  signed int StaticVolumeConfiguration; // ebx
  CUwfStaticConfiguration *v19; // rbx
  struct CUwfStaticVolumeConfiguration *v21; // r15
  LSTATUS v22; // eax
  bool v23; // dl
  char *v24; // r8
  __int64 v25; // rdx
  __int64 v26; // rax
  char *v27; // rcx
  bool v28; // [rsp+40h] [rbp-C0h] BYREF
  CUwfStaticConfiguration *v29; // [rsp+48h] [rbp-B8h]
  DWORD Type; // [rsp+50h] [rbp-B0h] BYREF
  DWORD cbData; // [rsp+54h] [rbp-ACh] BYREF
  BYTE Data[4]; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int16 *v33; // [rsp+60h] [rbp-A0h] BYREF
  struct CUwfStaticVolumeConfiguration *v34; // [rsp+68h] [rbp-98h] BYREF
  CUwfManagement *v35; // [rsp+70h] [rbp-90h]
  _QWORD v36[2]; // [rsp+78h] [rbp-88h] BYREF
  char v37; // [rsp+88h] [rbp-78h]
  __int128 v38; // [rsp+90h] [rbp-70h] BYREF
  int v39; // [rsp+A0h] [rbp-60h] BYREF
  char v40; // [rsp+A4h] [rbp-5Ch] BYREF
  WCHAR FileName[56]; // [rsp+8B0h] [rbp+7B0h] BYREF

  v35 = (CUwfManagement *)this;
  memset_0(FileName, 0, 0x64u);
  v36[0] = &CDevice::`vftable';
  v8 = -1;
  v33 = 0;
  v34 = 0;
  v36[1] = -1;
  v37 = 0;
  v9 = 0;
  v10 = 0;
  v38 = 0;
  memset_0(&v39, 0, 0x804u);
  v11 = 0;
  if ( !a2 )
    goto LABEL_8;
  v12 = -1;
  do
    ++v12;
  while ( a2[v12] );
  if ( !v12 )
  {
LABEL_8:
    if ( !a3 )
      goto LABEL_60;
    v13 = -1;
    do
      ++v13;
    while ( a3[v13] );
    if ( !v13 )
      goto LABEL_60;
  }
  if ( !a4 )
    goto LABEL_60;
  v14 = -1;
  do
    ++v14;
  while ( a4[v14] );
  if ( !v14 || (LOBYTE(v11) = 1, (v15 = ValidateFileNameToBeCommitted(v11, a2, a3, a4)) != 0) && v15 != 3 )
  {
LABEL_60:
    StaticVolumeConfiguration = -2147024809;
    goto LABEL_29;
  }
  *(_DWORD *)Data = 0;
  Type = 0;
  v16 = this[17];
  cbData = 4;
  v17 = RegQueryValueExW(v16, L"UWFEnabled", 0, &Type, Data, &cbData);
  StaticVolumeConfiguration = v17;
  if ( !v17 )
  {
    if ( Type != 4 )
    {
      StaticVolumeConfiguration = -2147023267;
      goto LABEL_29;
    }
    if ( cbData != 4 )
    {
      StaticVolumeConfiguration = -2147024883;
      goto LABEL_29;
    }
LABEL_24:
    if ( !*(_DWORD *)Data )
    {
      StaticVolumeConfiguration = -2147483634;
      goto LABEL_29;
    }
    v19 = (CUwfManagement *)((char *)v35 + 120);
    v29 = (CUwfManagement *)((char *)v35 + 120);
    CUwfStaticConfiguration::ReleaseStaticVolumeConfiguration((CUwfManagement *)((char *)v35 + 120));
    StaticVolumeConfiguration = CUwfStaticConfiguration::get_StaticVolumeConfiguration(v19, a2, a3, &v34);
    if ( StaticVolumeConfiguration != -2147024894 )
    {
      if ( StaticVolumeConfiguration < 0 )
        goto LABEL_28;
      v21 = v34;
      Type = 0;
      *(_DWORD *)Data = 0;
      cbData = 4;
      v22 = RegQueryValueExW(*((HKEY *)v34 + 2), L"VolumeEnabled", 0, (LPDWORD)Data, (LPBYTE)&Type, &cbData);
      StaticVolumeConfiguration = v22;
      if ( v22 )
      {
        if ( v22 > 0 )
          StaticVolumeConfiguration = (unsigned __int16)v22 | 0x80070000;
        if ( StaticVolumeConfiguration < 0 )
          goto LABEL_28;
      }
      else
      {
        if ( *(_DWORD *)Data != 4 )
        {
          StaticVolumeConfiguration = -2147023267;
          goto LABEL_28;
        }
        if ( cbData != 4 )
        {
          StaticVolumeConfiguration = -2147024883;
          goto LABEL_28;
        }
      }
      if ( Type )
      {
        if ( !a3 )
          goto LABEL_41;
        do
          ++v8;
        while ( a3[v8] );
        if ( !v8 )
        {
LABEL_41:
          StaticVolumeConfiguration = CUwfRegKey::QuerySzValue(
                                        (struct CUwfStaticVolumeConfiguration *)((char *)v21 + 16),
                                        L"VolumeName",
                                        &v33);
          v9 = v33;
          if ( StaticVolumeConfiguration < 0 )
            goto LABEL_28;
          a3 = v33;
        }
        v28 = 0;
        StaticVolumeConfiguration = CUwfManagement::IsFileExcluded(v35, v23, a2, a3, a4, &v28);
        if ( StaticVolumeConfiguration < 0 )
          goto LABEL_28;
        if ( !v28 )
        {
          StaticVolumeConfiguration = StringCchPrintfW(FileName, 0x32u, L"\\\\?\\%s", a3);
          if ( StaticVolumeConfiguration >= 0 )
          {
            StaticVolumeConfiguration = CDevice::Initialize((CDevice *)v36, FileName);
            if ( StaticVolumeConfiguration >= 0 )
            {
              StaticVolumeConfiguration = CDevice::SendIOCTL((CDevice *)v36, 0x22496Cu, 0, 0, &v38, 0x10u, 0);
              if ( StaticVolumeConfiguration >= 0 )
              {
                v24 = &v40;
                v39 = DWORD1(v38);
                v25 = 1024;
                v26 = 2147483646;
                do
                {
                  if ( !v26 )
                    break;
                  if ( !*a4 )
                    break;
                  *(_WORD *)v24 = *a4++;
                  v24 += 2;
                  --v26;
                  --v25;
                }
                while ( v25 );
                v27 = v24 - 2;
                StaticVolumeConfiguration = v25 == 0 ? 0x8007007A : 0;
                if ( v25 )
                  v27 = v24;
                *(_WORD *)v27 = 0;
                if ( v25 )
                  StaticVolumeConfiguration = CDevice::SendIOCTL((CDevice *)v36, 0x2289D0u, &v39, 0x804u, 0, 0, 0);
              }
            }
          }
          goto LABEL_28;
        }
      }
    }
    StaticVolumeConfiguration = -2147483634;
LABEL_28:
    v10 = v29;
    goto LABEL_29;
  }
  if ( v17 > 0 )
    StaticVolumeConfiguration = (unsigned __int16)v17 | 0x80070000;
  if ( StaticVolumeConfiguration >= 0 )
    goto LABEL_24;
LABEL_29:
  operator delete[](v9);
  if ( v10 )
    CUwfStaticConfiguration::ReleaseStaticVolumeConfiguration(v10);
  v36[0] = &CDevice::`vftable';
  CDevice::Close((CDevice *)v36);
  return (unsigned int)StaticVolumeConfiguration;
}

```

## disassembly

```asm
0x1800151b0  push    rbp
0x1800151b2  push    rbx
0x1800151b3  push    rsi
0x1800151b4  push    rdi
0x1800151b5  push    r12
0x1800151b7  push    r13
0x1800151b9  push    r14
0x1800151bb  push    r15
0x1800151bd  lea     rbp, [rsp-838h]
0x1800151c5  sub     rsp, 938h
0x1800151cc  mov     rax, cs:__security_cookie
0x1800151d3  xor     rax, rsp
0x1800151d6  mov     [rbp+870h+var_50], rax
0x1800151dd  mov     r13, rdx
0x1800151e0  mov     [rsp+970h+var_900], rcx
0x1800151e5  xor     edx, edx; Val
0x1800151e7  mov     rdi, r8
0x1800151ea  mov     rbx, rcx
0x1800151ed  mov     r14, r9
0x1800151f0  lea     rcx, [rbp+870h+FileName]; void *
0x1800151f7  lea     r8d, [rdx+64h]; Size
0x1800151fb  call    memset_0
0x180015200  xor     eax, eax
0x180015202  lea     rcx, ??_7CDevice@@6B@; const CDevice::`vftable'
0x180015209  mov     [rsp+970h+var_8F8], rcx
0x18001520e  xorps   xmm0, xmm0
0x180015211  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180015215  mov     [rsp+970h+var_910], rax
0x18001521a  lea     rcx, [rbp+870h+var_8D0]; void *
0x18001521e  mov     [rsp+970h+var_908], rax
0x180015223  xor     edx, edx; Val
0x180015225  mov     [rbp+870h+var_8F0], rsi
0x180015229  mov     r8d, 804h; Size
0x18001522f  mov     [rbp+870h+var_8E8], al
0x180015232  mov     r12d, eax
0x180015235  mov     r15d, eax
0x180015238  movups  [rbp+870h+var_8E0], xmm0
0x18001523c  call    memset_0
0x180015241  xor     ecx, ecx
0x180015243  test    r13, r13
0x180015246  jz      short loc_18001525B
0x180015248  mov     rax, rsi
0x18001524b  inc     rax
0x18001524e  cmp     [r13+rax*2+0], cx
0x180015254  jnz     short loc_18001524B
0x180015256  test    rax, rax
0x180015259  jnz     short loc_180015279
0x18001525b  test    rdi, rdi
0x18001525e  jz      loc_1800155DA
0x180015264  mov     rax, rsi
0x180015267  inc     rax
0x18001526a  cmp     [rdi+rax*2], cx
0x18001526e  jnz     short loc_180015267
0x180015270  test    rax, rax
0x180015273  jz      loc_1800155DA
0x180015279  test    r14, r14
0x18001527c  jz      loc_1800155DA
0x180015282  mov     rax, rsi
0x180015285  inc     rax
0x180015288  cmp     [r14+rax*2], cx
0x18001528d  jnz     short loc_180015285
0x18001528f  test    rax, rax
0x180015292  jz      loc_1800155DA
0x180015298  mov     r9, r14
0x18001529b  mov     r8, rdi
0x18001529e  mov     rdx, r13
0x1800152a1  mov     cl, 1
0x1800152a3  call    ?ValidateFileNameToBeCommitted@@YA?AW4FILE_COMMIT_VALIDATE_RESULT@@_NPEBG11@Z; ValidateFileNameToBeCommitted(bool,ushort const *,ushort const *,ushort const *)
0x1800152a8  xor     ecx, ecx
0x1800152aa  test    eax, eax
0x1800152ac  jz      short loc_1800152B7
0x1800152ae  cmp     eax, 3
0x1800152b1  jnz     loc_1800155DA
0x1800152b7  lea     rax, [rsp+970h+cbData]
0x1800152bc  mov     dword ptr [rsp+970h+Data], ecx
0x1800152c0  mov     [rsp+970h+lpcbData], rax; lpcbData
0x1800152c5  lea     r9, [rsp+970h+Type]; lpType
0x1800152ca  lea     rax, [rsp+970h+Data]
0x1800152cf  mov     [rsp+970h+Type], ecx
0x1800152d3  mov     rcx, [rbx+88h]; hKey
0x1800152da  lea     rdx, aUwfenabled; "UWFEnabled"
0x1800152e1  xor     r8d, r8d; lpReserved
0x1800152e4  mov     [rsp+970h+lpData], rax; lpData
0x1800152e9  mov     [rsp+970h+cbData], 4
0x1800152f1  call    cs:__imp_RegQueryValueExW
0x1800152f7  xor     ecx, ecx
0x1800152f9  mov     ebx, eax
0x1800152fb  test    eax, eax
0x1800152fd  jz      short loc_180015310
0x1800152ff  jle     short loc_18001530A
0x180015301  movzx   ebx, ax
0x180015304  or      ebx, 80070000h
0x18001530a  test    ebx, ebx
0x18001530c  jns     short loc_18001532C
0x18001530e  jmp     short loc_18001537A
0x180015310  cmp     [rsp+970h+Type], 4
0x180015315  jz      short loc_18001531E
0x180015317  mov     ebx, 8007065Dh
0x18001531c  jmp     short loc_18001537A
0x18001531e  cmp     [rsp+970h+cbData], 4
0x180015323  jz      short loc_18001532C
0x180015325  mov     ebx, 8007000Dh
0x18001532a  jmp     short loc_18001537A
0x18001532c  cmp     dword ptr [rsp+970h+Data], ecx
0x180015330  setnz   al
0x180015333  test    al, al
0x180015335  jnz     short loc_18001533E
0x180015337  mov     ebx, 8000000Eh
0x18001533c  jmp     short loc_18001537A
0x18001533e  mov     rbx, [rsp+970h+var_900]
0x180015343  add     rbx, 78h ; 'x'
0x180015347  mov     rcx, rbx; this
0x18001534a  mov     [rsp+970h+var_928], rbx
0x18001534f  call    ?ReleaseStaticVolumeConfiguration@CUwfStaticConfiguration@@QEAAXXZ; CUwfStaticConfiguration::ReleaseStaticVolumeConfiguration(void)
0x180015354  lea     r9, [rsp+970h+var_908]; struct CUwfStaticVolumeConfiguration **
0x180015359  mov     r8, rdi; String2
0x18001535c  mov     rdx, r13; unsigned __int16 *
0x18001535f  mov     rcx, rbx; this
0x180015362  call    ?get_StaticVolumeConfiguration@CUwfStaticConfiguration@@QEAAJPEBG0PEAPEAVCUwfStaticVolumeConfiguration@@@Z; CUwfStaticConfiguration::get_StaticVolumeConfiguration(ushort const *,ushort const *,CUwfStaticVolumeConfiguration * *)
0x180015367  mov     ebx, eax
0x180015369  cmp     eax, 80070002h
0x18001536e  jnz     short loc_1800153CB
0x180015370  mov     ebx, 8000000Eh
0x180015375  mov     r15, [rsp+970h+var_928]
0x18001537a  mov     rcx, r12
0x18001537d  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180015383  test    r15, r15
0x180015386  jz      short loc_180015390
0x180015388  mov     rcx, r15; this
0x18001538b  call    ?ReleaseStaticVolumeConfiguration@CUwfStaticConfiguration@@QEAAXXZ; CUwfStaticConfiguration::ReleaseStaticVolumeConfiguration(void)
0x180015390  lea     rax, ??_7CDevice@@6B@; const CDevice::`vftable'
0x180015397  lea     rcx, [rsp+970h+var_8F8]; this
0x18001539c  mov     [rsp+970h+var_8F8], rax
0x1800153a1  call    ?Close@CDevice@@QEAAXXZ; CDevice::Close(void)
0x1800153a6  mov     eax, ebx
0x1800153a8  mov     rcx, [rbp+870h+var_50]
0x1800153af  xor     rcx, rsp; StackCookie
0x1800153b2  call    __security_check_cookie
0x1800153b7  add     rsp, 938h
0x1800153be  pop     r15
0x1800153c0  pop     r14
0x1800153c2  pop     r13
0x1800153c4  pop     r12
0x1800153c6  pop     rdi
0x1800153c7  pop     rsi
0x1800153c8  pop     rbx
0x1800153c9  pop     rbp
0x1800153ca  retn
0x1800153cb  xor     eax, eax
0x1800153cd  test    ebx, ebx
0x1800153cf  js      short loc_180015375
0x1800153d1  mov     r15, [rsp+970h+var_908]
0x1800153d6  lea     r9, [rsp+970h+Data]; lpType
0x1800153db  mov     [rsp+970h+Type], eax
0x1800153df  lea     rdx, ValueName; "VolumeEnabled"
0x1800153e6  mov     dword ptr [rsp+970h+Data], eax
0x1800153ea  xor     r8d, r8d; lpReserved
0x1800153ed  lea     rax, [rsp+970h+cbData]
0x1800153f2  mov     [rsp+970h+cbData], 4
0x1800153fa  mov     rcx, [r15+10h]; hKey
0x1800153fe  mov     [rsp+970h+lpcbData], rax; lpcbData
0x180015403  lea     rax, [rsp+970h+Type]
0x180015408  mov     [rsp+970h+lpData], rax; lpData
0x18001540d  call    cs:__imp_RegQueryValueExW
0x180015413  xor     ecx, ecx
0x180015415  mov     ebx, eax
0x180015417  test    eax, eax
0x180015419  jz      short loc_18001547C
0x18001541b  jle     short loc_180015426
0x18001541d  movzx   ebx, ax
0x180015420  or      ebx, 80070000h
0x180015426  test    ebx, ebx
0x180015428  js      loc_180015375
0x18001542e  cmp     [rsp+970h+Type], ecx
0x180015432  setnz   al
0x180015435  test    al, al
0x180015437  jz      loc_180015370
0x18001543d  test    rdi, rdi
0x180015440  jz      short loc_180015450
0x180015442  inc     rsi
0x180015445  cmp     [rdi+rsi*2], cx
0x180015449  jnz     short loc_180015442
0x18001544b  test    rsi, rsi
0x18001544e  jnz     short loc_18001549E
0x180015450  lea     r8, [rsp+970h+var_910]; unsigned __int16 **
0x180015455  lea     rdx, aVolumename; "VolumeName"
0x18001545c  lea     rcx, [r15+10h]; this
0x180015460  call    ?QuerySzValue@CUwfRegKey@@QEAAJPEBGPEAPEAG@Z; CUwfRegKey::QuerySzValue(ushort const *,ushort * *)
0x180015465  mov     ebx, eax
0x180015467  mov     r12, [rsp+970h+var_910]
0x18001546c  xor     r15d, r15d
0x18001546f  test    eax, eax
0x180015471  js      loc_180015375
0x180015477  mov     rdi, r12
0x18001547a  jmp     short loc_1800154A1
0x18001547c  cmp     dword ptr [rsp+970h+Data], 4
0x180015481  jz      short loc_18001548D
0x180015483  mov     ebx, 8007065Dh
0x180015488  jmp     loc_180015375
0x18001548d  cmp     [rsp+970h+cbData], 4
0x180015492  jz      short loc_18001542E
0x180015494  mov     ebx, 8007000Dh
0x180015499  jmp     loc_180015375
0x18001549e  xor     r15d, r15d
0x1800154a1  mov     rcx, [rsp+970h+var_900]; this
0x1800154a6  lea     rax, [rsp+970h+var_930]
0x1800154ab  mov     [rsp+970h+lpcbData], rax; bool *
0x1800154b0  mov     r9, rdi; unsigned __int16 *
0x1800154b3  mov     r8, r13; unsigned __int16 *
0x1800154b6  mov     [rsp+970h+lpData], r14; unsigned __int16 *
0x1800154bb  mov     [rsp+970h+var_930], r15b
0x1800154c0  call    ?IsFileExcluded@CUwfManagement@@AEAAJ_NPEBG11PEA_N@Z; CUwfManagement::IsFileExcluded(bool,ushort const *,ushort const *,ushort const *,bool *)
0x1800154c5  mov     ebx, eax
0x1800154c7  test    eax, eax
0x1800154c9  js      loc_180015375
0x1800154cf  cmp     [rsp+970h+var_930], r15b
0x1800154d4  jnz     loc_180015370
0x1800154da  mov     r9, rdi
0x1800154dd  lea     r8, aS; "\\\\?\\%s"
0x1800154e4  mov     edx, 32h ; '2'; unsigned __int64
0x1800154e9  lea     rcx, [rbp+870h+FileName]; unsigned __int16 *
0x1800154f0  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800154f5  mov     ebx, eax
0x1800154f7  test    eax, eax
0x1800154f9  js      loc_180015375
0x1800154ff  lea     rdx, [rbp+870h+FileName]; lpFileName
0x180015506  lea     rcx, [rsp+970h+var_8F8]; this
0x18001550b  call    ?Initialize@CDevice@@QEAAJPEBG@Z; CDevice::Initialize(ushort const *)
0x180015510  mov     ebx, eax
0x180015512  test    eax, eax
0x180015514  js      loc_180015375
0x18001551a  mov     [rsp+970h+var_940], r15; unsigned int *
0x18001551f  lea     rax, [rbp+870h+var_8E0]
0x180015523  mov     dword ptr [rsp+970h+lpcbData], 10h; DWORD
0x18001552b  lea     rcx, [rsp+970h+var_8F8]; this
0x180015530  xor     r9d, r9d; unsigned int
0x180015533  mov     [rsp+970h+lpData], rax; void *
0x180015538  xor     r8d, r8d; void *
0x18001553b  mov     edx, 22496Ch; unsigned int
0x180015540  call    ?SendIOCTL@CDevice@@QEAAJKPEAXK0KPEAK@Z; CDevice::SendIOCTL(ulong,void *,ulong,void *,ulong,ulong *)
0x180015545  mov     ebx, eax
0x180015547  test    eax, eax
0x180015549  js      loc_180015375
0x18001554f  mov     eax, dword ptr [rbp+870h+var_8E0+4]
0x180015552  lea     r8, [rbp+870h+var_8CC]
0x180015556  mov     [rbp+870h+var_8D0], eax
0x180015559  mov     edx, 400h
0x18001555e  mov     eax, 7FFFFFFEh
0x180015563  test    rax, rax
0x180015566  jz      short loc_180015586
0x180015568  movzx   ecx, word ptr [r14]
0x18001556c  test    cx, cx
0x18001556f  jz      short loc_180015586
0x180015571  mov     [r8], cx
0x180015575  add     r14, 2
0x180015579  add     r8, 2
0x18001557d  dec     rax
0x180015580  sub     rdx, 1
0x180015584  jnz     short loc_180015563
0x180015586  mov     rax, rdx
0x180015589  lea     rcx, [r8-2]
0x18001558d  neg     rax
0x180015590  sbb     ebx, ebx
0x180015592  not     ebx
0x180015594  and     ebx, 8007007Ah
0x18001559a  test    rdx, rdx
0x18001559d  cmovnz  rcx, r8
0x1800155a1  mov     [rcx], r15w
0x1800155a5  jz      loc_180015375
0x1800155ab  mov     [rsp+970h+var_940], r15; unsigned int *
0x1800155b0  lea     r8, [rbp+870h+var_8D0]; void *
0x1800155b4  mov     dword ptr [rsp+970h+lpcbData], r15d; DWORD
0x1800155b9  lea     rcx, [rsp+970h+var_8F8]; this
0x1800155be  mov     r9d, 804h; unsigned int
0x1800155c4  mov     [rsp+970h+lpData], r15; void *
0x1800155c9  mov     edx, 2289D0h; unsigned int
0x1800155ce  call    ?SendIOCTL@CDevice@@QEAAJKPEAXK0KPEAK@Z; CDevice::SendIOCTL(ulong,void *,ulong,void *,ulong,ulong *)
0x1800155d3  mov     ebx, eax
0x1800155d5  jmp     loc_180015375
0x1800155da  mov     ebx, 80070057h
0x1800155df  jmp     loc_18001537A
```
