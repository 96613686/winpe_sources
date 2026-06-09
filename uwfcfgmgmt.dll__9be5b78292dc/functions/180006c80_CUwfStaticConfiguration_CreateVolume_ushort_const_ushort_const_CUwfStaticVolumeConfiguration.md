# CUwfStaticConfiguration::CreateVolume(ushort const *,ushort const *,CUwfStaticVolumeConfiguration * *)

- ea: `0x180006c80`
- end: `0x18000710c`
- name: `?CreateVolume@CUwfStaticConfiguration@@QEAAJPEBG0PEAPEAVCUwfStaticVolumeConfiguration@@@Z`
- size: `1164`
- prototype: `__int64 __fastcall(CUwfStaticConfiguration *this, wchar_t *, unsigned __int16 *, struct CUwfStaticVolumeConfiguration **)`
- caller_count: `1`
- callee_count: `25`
- tags: `file_ops, registry_config, installer_update`

## callers

- `0x180017e90`

## callees

- `0x180001390`
- `0x180002468`
- `0x1800054d0`
- `0x180006b20`
- `0x180006c80`
- `0x1800079a0`
- `0x180008300`
- `0x180009170`
- `0x18000bc90`
- `0x18000bfa0`
- `0x18000c0f0`
- `0x18000d130`
- `0x18000d5f0`
- `0x18000dc40`
- `0x18000e0f0`
- `0x18000e480`
- `0x18000e660`
- `0x180011738`
- `0x180011870`
- `0x1800124d0`
- `0x180012640`
- `0x18001afe2`
- `0x18001afee`
- `0x18001b020`
- `0x18001c010`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x180007083`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180007083`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x1800070cd`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x1800070cd`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180006e20`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180006e20`

## pseudocode

```c
__int64 __fastcall CUwfStaticConfiguration::CreateVolume(
        CUwfStaticConfiguration *this,
        wchar_t *a2,
        unsigned __int16 *a3,
        struct CUwfStaticVolumeConfiguration **a4)
{
  CUwfStaticVolumeConfiguration *v8; // rdi
  const unsigned __int16 *v9; // rcx
  int VolumeGuid; // ebx
  __int64 v11; // rsi
  __int64 v12; // r14
  __int64 v13; // rdx
  __int64 v14; // rcx
  HKEY v15; // rcx
  bool v16; // sf
  unsigned __int16 *v17; // rbx
  unsigned __int64 v18; // rax
  __int64 v19; // rax
  HKEY *v20; // r12
  char *v21; // rax
  struct CUwfStaticVolumeConfiguration **v22; // rax
  HKEY *v23; // rcx
  void *v24; // r8
  bool v26; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v27; // [rsp+44h] [rbp-BCh] BYREF
  DWORD Type; // [rsp+48h] [rbp-B8h] BYREF
  DWORD cbData; // [rsp+4Ch] [rbp-B4h] BYREF
  BYTE Data[4]; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v31; // [rsp+54h] [rbp-ACh] BYREF
  unsigned __int16 *v32; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v33; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 *v34; // [rsp+68h] [rbp-98h]
  struct CUwfStaticVolumeConfiguration **v35; // [rsp+70h] [rbp-90h]
  WCHAR SubKey[12]; // [rsp+78h] [rbp-88h] BYREF
  wchar_t String1[4]; // [rsp+90h] [rbp-70h] BYREF
  char v38; // [rsp+98h] [rbp-68h] BYREF

  v34 = a3;
  v33 = 0;
  v35 = a4;
  v31 = 0;
  v27 = 0;
  v8 = 0;
  memset_0(String1, 0, 0x64u);
  v32 = 0;
  v26 = 0;
  if ( !a2 && !a3 || !a4 )
  {
    VolumeGuid = -2147467261;
    goto LABEL_65;
  }
  if ( *((_QWORD *)this + 5) )
  {
    VolumeGuid = -2147024891;
    goto LABEL_65;
  }
  LODWORD(v11) = 0;
  if ( a2 )
  {
    v11 = -1;
    do
      ++v11;
    while ( a2[v11] );
    if ( (_DWORD)v11 && !IsGuidMatch(v9, a2) )
      goto LABEL_12;
  }
  LODWORD(v12) = 0;
  if ( a3 )
  {
    v12 = -1;
    do
      ++v12;
    while ( a3[v12] );
    if ( (_DWORD)v12 && !IsValidDriveLetter(a3) )
    {
LABEL_12:
      VolumeGuid = -2147024809;
      goto LABEL_65;
    }
  }
  if ( !(_DWORD)v11 )
  {
    VolumeGuid = VolumeGetVolumeGuid(a3, String1, 0x32u);
    if ( VolumeGuid < 0 )
      goto LABEL_65;
    v11 = -1;
    do
      ++v11;
    while ( String1[v11] );
    v13 = (unsigned int)(v11 - 1);
    if ( String1[v13] == 92 )
    {
      if ( (unsigned __int64)(2 * v13) >= 0x64 )
        _report_rangecheckfailure();
      String1[v13] = 0;
      LODWORD(v11) = v11 - 1;
    }
    if ( !wcsncmp_0(String1, L"\\\\?\\", 4u) )
    {
      a2 = (wchar_t *)&v38;
      LODWORD(v11) = v11 - 4;
    }
    else
    {
      a2 = String1;
    }
  }
  v14 = *((_QWORD *)this + 4);
  *(_DWORD *)Data = 0;
  Type = 0;
  v15 = *(HKEY *)(v14 + 56);
  cbData = 4;
  VolumeGuid = RegQueryValueExW(v15, L"UWFEnabled", 0, &Type, Data, &cbData);
  v16 = VolumeGuid < 0;
  if ( !VolumeGuid )
  {
    if ( Type != 4 )
    {
      VolumeGuid = -2147023267;
      goto LABEL_65;
    }
    if ( cbData != 4 )
    {
      VolumeGuid = -2147024883;
      goto LABEL_65;
    }
    goto LABEL_32;
  }
  if ( VolumeGuid > 0 )
  {
    VolumeGuid = (unsigned __int16)VolumeGuid | 0x80070000;
    v16 = VolumeGuid < 0;
  }
  if ( !v16 )
  {
LABEL_32:
    VolumeGuid = CanVolumeBeProtected(a2, *(_DWORD *)Data != 0, &v26);
    if ( VolumeGuid >= 0 )
    {
      if ( v26 )
      {
        if ( !(_DWORD)v12 && (int)VolumeGetVolumeDriverLetter(a2, &v32) >= 0 )
        {
          v17 = v32;
          if ( v32 )
          {
            v18 = -1;
            do
              ++v18;
            while ( v32[v18] );
            if ( v18 > 2 )
            {
              v32[2] = 0;
              if ( IsValidDriveLetter(v17) )
              {
                v34 = v17;
                v19 = -1;
                do
                  ++v19;
                while ( v17[v19] );
                LODWORD(v12) = v19;
              }
            }
          }
        }
        VolumeGuid = CUwfConfiguration::FixupUpdatedSettings(*((CUwfConfiguration **)this + 4));
        if ( VolumeGuid >= 0 )
        {
          v20 = (HKEY *)((char *)this + 24);
          VolumeGuid = CUwfRegKey::QueryDWORDValue((CUwfStaticConfiguration *)((char *)this + 24), L"NumVolumes", &v27);
          if ( VolumeGuid >= 0 )
          {
            VolumeGuid = StringCchPrintfW(SubKey, 0xCu, L"%i", v27);
            if ( VolumeGuid >= 0 )
            {
              VolumeGuid = CUwfConfiguration::CreateKey(
                             *((CUwfConfiguration **)this + 4),
                             *v20,
                             SubKey,
                             0x2001Fu,
                             0,
                             &v31,
                             (struct CUwfRegKey *)&v33);
              if ( VolumeGuid >= 0 )
              {
                v21 = (char *)operator new(0x28u);
                v8 = (CUwfStaticVolumeConfiguration *)v21;
                if ( v21 )
                {
                  *((_QWORD *)v21 + 2) = 0;
                  *((_QWORD *)v21 + 3) = 0;
                  *((_QWORD *)v21 + 4) = 0;
                  *(_QWORD *)v21 = &CUwfStaticVolumeConfiguration::`vftable';
                  *(_WORD *)(v21 + 9) = 1;
                  *((_DWORD *)v21 + 3) = -1;
                  VolumeGuid = CUwfStaticVolumeConfiguration::Initialize(
                                 (CUwfStaticVolumeConfiguration *)v21,
                                 *v20,
                                 v27,
                                 0,
                                 *((struct CUwfConfiguration **)this + 4),
                                 this);
                  if ( VolumeGuid >= 0 )
                  {
                    if ( !(_DWORD)v11
                      || (VolumeGuid = CUwfStaticVolumeConfiguration::set_VolumeGuid(v8, a2), VolumeGuid >= 0) )
                    {
                      if ( !(_DWORD)v12
                        || (VolumeGuid = CUwfStaticVolumeConfiguration::set_DriveLetter(v8, v34), VolumeGuid >= 0) )
                      {
                        VolumeGuid = CUwfRegKey::SetDWORDValue((CUwfRegKey *)&v33, L"VolumeEnabled", 0);
                        if ( VolumeGuid >= 0 )
                        {
                          VolumeGuid = CUwfStaticVolumeConfiguration::set_BindingType(v8, 1u);
                          if ( VolumeGuid >= 0 )
                          {
                            VolumeGuid = CUwfStaticVolumeConfiguration::ResetFileExclusions(v8);
                            if ( VolumeGuid >= 0 )
                            {
                              VolumeGuid = CUwfStaticConfiguration::set_NumVolumes(this, v27 + 1);
                              if ( VolumeGuid >= 0 )
                              {
                                v22 = v35;
                                *((_QWORD *)this + 5) = v8;
                                *v22 = v8;
                              }
                            }
                          }
                        }
                      }
                    }
                  }
                }
                else
                {
                  VolumeGuid = -2147024882;
                  v8 = 0;
                }
              }
            }
          }
        }
      }
      else
      {
        VolumeGuid = -2147024846;
      }
    }
  }
LABEL_65:
  operator delete[](v32);
  if ( VolumeGuid < 0 )
  {
    if ( v8 )
      (**(void (__fastcall ***)(CUwfStaticVolumeConfiguration *, __int64))v8)(v8, 1);
    if ( v31 == 1 )
    {
      v23 = (HKEY *)((char *)this + 24);
      v24 = *(void **)(*((_QWORD *)this + 4) + 8LL);
      if ( v24 == (void *)-1LL )
        RegDeleteTreeW(*v23, SubKey);
      else
        CUwfRegKey::DeleteTreeTransacted((CUwfRegKey *)v23, SubKey, v24);
    }
    *(_DWORD *)(*((_QWORD *)this + 4) + 16LL) = VolumeGuid;
  }
  CUwfRegKey::Close((CUwfRegKey *)&v33);
  return (unsigned int)VolumeGuid;
}

```

## disassembly

```asm
0x180006c80  push    rbp
0x180006c82  push    rbx
0x180006c83  push    rsi
0x180006c84  push    rdi
0x180006c85  push    r12
0x180006c87  push    r13
0x180006c89  push    r14
0x180006c8b  push    r15
0x180006c8d  lea     rbp, [rsp-18h]
0x180006c92  sub     rsp, 118h
0x180006c99  mov     rax, cs:__security_cookie
0x180006ca0  xor     rax, rsp
0x180006ca3  mov     [rbp+50h+var_50], rax
0x180006ca7  xor     eax, eax
0x180006ca9  mov     [rsp+150h+var_E8], r8
0x180006cae  mov     rbx, r9
0x180006cb1  mov     [rsp+150h+var_F0], rax
0x180006cb6  mov     r12, r8
0x180006cb9  mov     [rsp+150h+var_E0], rbx
0x180006cbe  mov     r15, rdx
0x180006cc1  mov     [rsp+150h+var_FC], eax
0x180006cc5  mov     r13, rcx
0x180006cc8  mov     [rsp+150h+var_10C], eax
0x180006ccc  lea     r8d, [rax+64h]; Size
0x180006cd0  xor     edx, edx; Val
0x180006cd2  lea     rcx, [rbp+50h+String1]; void *
0x180006cd6  mov     edi, eax
0x180006cd8  call    memset_0
0x180006cdd  xor     eax, eax
0x180006cdf  mov     [rsp+150h+var_F8], rax
0x180006ce4  mov     [rsp+150h+var_110], al
0x180006ce8  test    r15, r15
0x180006ceb  jnz     short loc_180006CFC
0x180006ced  test    r12, r12
0x180006cf0  jnz     short loc_180006CFC
0x180006cf2  mov     ebx, 80004003h
0x180006cf7  jmp     loc_18000707E
0x180006cfc  test    rbx, rbx
0x180006cff  jz      short loc_180006CF2
0x180006d01  xor     ebx, ebx
0x180006d03  cmp     [r13+28h], rbx
0x180006d07  jz      short loc_180006D13
0x180006d09  mov     ebx, 80070005h
0x180006d0e  jmp     loc_18000707E
0x180006d13  mov     esi, ebx
0x180006d15  test    r15, r15
0x180006d18  jz      short loc_180006D42
0x180006d1a  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180006d1e  inc     rsi
0x180006d21  cmp     [r15+rsi*2], bx
0x180006d26  jnz     short loc_180006D1E
0x180006d28  test    esi, esi
0x180006d2a  jz      short loc_180006D42
0x180006d2c  mov     rdx, r15; unsigned __int16 *
0x180006d2f  call    ?IsGuidMatch@@YA_NPEBG0@Z; IsGuidMatch(ushort const *,ushort const *)
0x180006d34  test    al, al
0x180006d36  jnz     short loc_180006D42
0x180006d38  mov     ebx, 80070057h
0x180006d3d  jmp     loc_18000707E
0x180006d42  mov     r14d, ebx
0x180006d45  test    r12, r12
0x180006d48  jz      short loc_180006D69
0x180006d4a  or      r14, 0FFFFFFFFFFFFFFFFh
0x180006d4e  inc     r14
0x180006d51  cmp     [r12+r14*2], bx
0x180006d56  jnz     short loc_180006D4E
0x180006d58  test    r14d, r14d
0x180006d5b  jz      short loc_180006D69
0x180006d5d  mov     rcx, r12; unsigned __int16 *
0x180006d60  call    ?IsValidDriveLetter@@YA_NPEBG@Z; IsValidDriveLetter(ushort const *)
0x180006d65  test    al, al
0x180006d67  jz      short loc_180006D38
0x180006d69  test    esi, esi
0x180006d6b  jnz     short loc_180006DE5
0x180006d6d  lea     r8d, [rsi+32h]; unsigned int
0x180006d71  mov     rcx, r12; unsigned __int16 *
0x180006d74  lea     rdx, [rbp+50h+String1]; unsigned __int16 *
0x180006d78  call    ?VolumeGetVolumeGuid@@YAJPEBGPEAGK@Z; VolumeGetVolumeGuid(ushort const *,ushort *,ulong)
0x180006d7d  mov     ebx, eax
0x180006d7f  test    eax, eax
0x180006d81  js      loc_18000707E
0x180006d87  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180006d8b  lea     rax, [rbp+50h+String1]
0x180006d8f  xor     ebx, ebx
0x180006d91  inc     rsi
0x180006d94  cmp     [rax+rsi*2], bx
0x180006d98  jnz     short loc_180006D91
0x180006d9a  lea     edx, [rsi-1]
0x180006d9d  mov     eax, 5Ch ; '\'
0x180006da2  lea     rcx, [rdx+rdx]
0x180006da6  cmp     ax, [rbp+rcx+50h+String1]
0x180006dab  jnz     short loc_180006DBE
0x180006dad  cmp     rcx, 64h ; 'd'
0x180006db1  jnb     loc_180007106
0x180006db7  mov     [rbp+rcx+50h+String1], bx
0x180006dbc  mov     esi, edx
0x180006dbe  mov     r8d, 4; MaxCount
0x180006dc4  lea     rdx, String2; "\\\\?\\"
0x180006dcb  lea     rcx, [rbp+50h+String1]; String1
0x180006dcf  call    wcsncmp_0
0x180006dd4  test    eax, eax
0x180006dd6  jnz     short loc_180006DE1
0x180006dd8  lea     r15, [rbp+50h+var_B8]
0x180006ddc  add     esi, 0FFFFFFFCh
0x180006ddf  jmp     short loc_180006DE5
0x180006de1  lea     r15, [rbp+50h+String1]
0x180006de5  mov     rcx, [r13+20h]
0x180006de9  lea     rax, [rsp+150h+cbData]
0x180006dee  mov     [rsp+150h+lpcbData], rax; lpcbData
0x180006df3  lea     r9, [rsp+150h+Type]; lpType
0x180006df8  lea     rax, [rsp+150h+Data]
0x180006dfd  mov     dword ptr [rsp+150h+Data], ebx
0x180006e01  xor     r8d, r8d; lpReserved
0x180006e04  mov     [rsp+150h+Type], ebx
0x180006e08  mov     rcx, [rcx+38h]; hKey
0x180006e0c  lea     rdx, aUwfenabled; "UWFEnabled"
0x180006e13  mov     [rsp+150h+cbData], 4
0x180006e1b  mov     [rsp+150h+lpData], rax; lpData
0x180006e20  call    cs:__imp_RegQueryValueExW
0x180006e26  mov     ebx, eax
0x180006e28  xor     eax, eax
0x180006e2a  test    ebx, ebx
0x180006e2c  jz      short loc_180006E71
0x180006e2e  jle     short loc_180006E3B
0x180006e30  movzx   ebx, bx
0x180006e33  or      ebx, 80070000h
0x180006e39  test    ebx, ebx
0x180006e3b  js      loc_18000707E
0x180006e41  cmp     dword ptr [rsp+150h+Data], eax
0x180006e45  lea     r8, [rsp+150h+var_110]; bool *
0x180006e4a  mov     rcx, r15; unsigned __int16 *
0x180006e4d  setnz   dl; bool
0x180006e50  call    ?CanVolumeBeProtected@@YAJPEBG_NPEA_N@Z; CanVolumeBeProtected(ushort const *,bool,bool *)
0x180006e55  mov     ebx, eax
0x180006e57  xor     eax, eax
0x180006e59  test    ebx, ebx
0x180006e5b  js      loc_18000707E
0x180006e61  cmp     [rsp+150h+var_110], al
0x180006e65  jnz     short loc_180006E93
0x180006e67  mov     ebx, 80070032h
0x180006e6c  jmp     loc_18000707E
0x180006e71  cmp     [rsp+150h+Type], 4
0x180006e76  jz      short loc_180006E82
0x180006e78  mov     ebx, 8007065Dh
0x180006e7d  jmp     loc_18000707E
0x180006e82  cmp     [rsp+150h+cbData], 4
0x180006e87  jz      short loc_180006E41
0x180006e89  mov     ebx, 8007000Dh
0x180006e8e  jmp     loc_18000707E
0x180006e93  test    r14d, r14d
0x180006e96  jnz     short loc_180006EEF
0x180006e98  lea     rdx, [rsp+150h+var_F8]; unsigned __int16 **
0x180006e9d  mov     rcx, r15; unsigned __int16 *
0x180006ea0  call    ?VolumeGetVolumeDriverLetter@@YAJPEBGPEAPEAG@Z; VolumeGetVolumeDriverLetter(ushort const *,ushort * *)
0x180006ea5  xor     ecx, ecx
0x180006ea7  test    eax, eax
0x180006ea9  js      short loc_180006EEF
0x180006eab  mov     rbx, [rsp+150h+var_F8]
0x180006eb0  test    rbx, rbx
0x180006eb3  jz      short loc_180006EEF
0x180006eb5  or      rax, 0FFFFFFFFFFFFFFFFh
0x180006eb9  inc     rax
0x180006ebc  cmp     [rbx+rax*2], cx
0x180006ec0  jnz     short loc_180006EB9
0x180006ec2  cmp     rax, 2
0x180006ec6  jbe     short loc_180006EEF
0x180006ec8  mov     [rbx+4], cx
0x180006ecc  mov     rcx, rbx; unsigned __int16 *
0x180006ecf  call    ?IsValidDriveLetter@@YA_NPEBG@Z; IsValidDriveLetter(ushort const *)
0x180006ed4  xor     ecx, ecx
0x180006ed6  test    al, al
0x180006ed8  jz      short loc_180006EEF
0x180006eda  mov     [rsp+150h+var_E8], rbx
0x180006edf  or      rax, 0FFFFFFFFFFFFFFFFh
0x180006ee3  inc     rax
0x180006ee6  cmp     [rbx+rax*2], cx
0x180006eea  jnz     short loc_180006EE3
0x180006eec  mov     r14d, eax
0x180006eef  mov     rcx, [r13+20h]; this
0x180006ef3  call    ?FixupUpdatedSettings@CUwfConfiguration@@QEAAJXZ; CUwfConfiguration::FixupUpdatedSettings(void)
0x180006ef8  mov     ebx, eax
0x180006efa  test    eax, eax
0x180006efc  js      loc_18000707E
0x180006f02  lea     r12, [r13+18h]
0x180006f06  mov     rcx, r12; this
0x180006f09  lea     r8, [rsp+150h+var_10C]; unsigned int *
0x180006f0e  lea     rdx, aNumvolumes; "NumVolumes"
0x180006f15  call    ?QueryDWORDValue@CUwfRegKey@@QEAAJPEBGPEAK@Z; CUwfRegKey::QueryDWORDValue(ushort const *,ulong *)
0x180006f1a  mov     ebx, eax
0x180006f1c  test    eax, eax
0x180006f1e  js      loc_18000707E
0x180006f24  mov     r9d, [rsp+150h+var_10C]
0x180006f29  lea     r8, aI; "%i"
0x180006f30  mov     edx, 0Ch; unsigned __int64
0x180006f35  lea     rcx, [rsp+150h+SubKey]; unsigned __int16 *
0x180006f3a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180006f3f  xor     ecx, ecx
0x180006f41  mov     ebx, eax
0x180006f43  test    eax, eax
0x180006f45  js      loc_18000707E
0x180006f4b  mov     rdx, [r12]; HKEY
0x180006f4f  lea     rax, [rsp+150h+var_F0]
0x180006f54  mov     [rsp+150h+var_120], rax; struct CUwfRegKey *
0x180006f59  lea     r8, [rsp+150h+SubKey]; unsigned __int16 *
0x180006f5e  lea     rax, [rsp+150h+var_FC]
0x180006f63  mov     r9d, 2001Fh; unsigned int
0x180006f69  mov     [rsp+150h+lpcbData], rax; unsigned int *
0x180006f6e  mov     dword ptr [rsp+150h+lpData], ecx; unsigned int
0x180006f72  mov     rcx, [r13+20h]; this
0x180006f76  call    ?CreateKey@CUwfConfiguration@@QEAAJPEAUHKEY__@@PEBGKKPEAKAEAVCUwfRegKey@@@Z; CUwfConfiguration::CreateKey(HKEY__ *,ushort const *,ulong,ulong,ulong *,CUwfRegKey &)
0x180006f7b  mov     ebx, eax
0x180006f7d  test    eax, eax
0x180006f7f  js      loc_18000707E
0x180006f85  mov     ecx, 28h ; '('; Size
0x180006f8a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180006f8f  xor     ecx, ecx
0x180006f91  mov     rdi, rax
0x180006f94  test    rax, rax
0x180006f97  jz      loc_180007076
0x180006f9d  mov     [rdi+10h], rcx
0x180006fa1  lea     rax, ??_7CUwfStaticVolumeConfiguration@@6B@; const CUwfStaticVolumeConfiguration::`vftable'
0x180006fa8  mov     [rdi+18h], rcx
0x180006fac  xor     r9d, r9d; bool
0x180006faf  mov     [rdi+20h], rcx
0x180006fb3  mov     rcx, rdi; this
0x180006fb6  mov     [rdi], rax
0x180006fb9  mov     word ptr [rdi+9], 1
0x180006fbf  mov     dword ptr [rdi+0Ch], 0FFFFFFFFh
0x180006fc6  mov     rax, [r13+20h]
0x180006fca  mov     r8d, [rsp+150h+var_10C]; unsigned int
0x180006fcf  mov     rdx, [r12]; HKEY
0x180006fd3  mov     [rsp+150h+lpcbData], r13; struct CUwfStaticConfiguration *
0x180006fd8  mov     [rsp+150h+lpData], rax; struct CUwfConfiguration *
0x180006fdd  call    ?Initialize@CUwfStaticVolumeConfiguration@@QEAAJPEAUHKEY__@@K_NPEAVCUwfConfiguration@@PEAVCUwfStaticConfiguration@@@Z; CUwfStaticVolumeConfiguration::Initialize(HKEY__ *,ulong,bool,CUwfConfiguration *,CUwfStaticConfiguration *)
0x180006fe2  mov     ebx, eax
0x180006fe4  test    eax, eax
0x180006fe6  js      loc_18000707E
0x180006fec  test    esi, esi
0x180006fee  jz      short loc_180007001
0x180006ff0  mov     rdx, r15; unsigned __int16 *
0x180006ff3  mov     rcx, rdi; this
0x180006ff6  call    ?set_VolumeGuid@CUwfStaticVolumeConfiguration@@QEAAJPEBG@Z; CUwfStaticVolumeConfiguration::set_VolumeGuid(ushort const *)
0x180006ffb  mov     ebx, eax
0x180006ffd  test    eax, eax
0x180006fff  js      short loc_18000707E
0x180007001  test    r14d, r14d
0x180007004  jz      short loc_180007019
0x180007006  mov     rdx, [rsp+150h+var_E8]; unsigned __int16 *
0x18000700b  mov     rcx, rdi; this
0x18000700e  call    ?set_DriveLetter@CUwfStaticVolumeConfiguration@@QEAAJPEBG@Z; CUwfStaticVolumeConfiguration::set_DriveLetter(ushort const *)
0x180007013  mov     ebx, eax
0x180007015  test    eax, eax
0x180007017  js      short loc_18000707E
0x180007019  xor     r8d, r8d; unsigned int
0x18000701c  lea     rdx, ValueName; "VolumeEnabled"
0x180007023  lea     rcx, [rsp+150h+var_F0]; this
0x180007028  call    ?SetDWORDValue@CUwfRegKey@@QEAAJPEBGK@Z; CUwfRegKey::SetDWORDValue(ushort const *,ulong)
0x18000702d  mov     ebx, eax
0x18000702f  test    eax, eax
0x180007031  js      short loc_18000707E
0x180007033  mov     edx, 1; unsigned int
0x180007038  mov     rcx, rdi; this
0x18000703b  call    ?set_BindingType@CUwfStaticVolumeConfiguration@@QEAAJK@Z; CUwfStaticVolumeConfiguration::set_BindingType(ulong)
0x180007040  mov     ebx, eax
0x180007042  test    eax, eax
0x180007044  js      short loc_18000707E
0x180007046  mov     rcx, rdi; this
0x180007049  call    ?ResetFileExclusions@CUwfStaticVolumeConfiguration@@QEAAJXZ; CUwfStaticVolumeConfiguration::ResetFileExclusions(void)
0x18000704e  mov     ebx, eax
0x180007050  test    eax, eax
0x180007052  js      short loc_18000707E
0x180007054  mov     edx, [rsp+150h+var_10C]
0x180007058  mov     rcx, r13; this
0x18000705b  inc     edx; unsigned int
0x18000705d  call    ?set_NumVolumes@CUwfStaticConfiguration@@QEAAJK@Z; CUwfStaticConfiguration::set_NumVolumes(ulong)
0x180007062  mov     ebx, eax
0x180007064  test    eax, eax
0x180007066  js      short loc_18000707E
0x180007068  mov     rax, [rsp+150h+var_E0]
0x18000706d  mov     [r13+28h], rdi
0x180007071  mov     [rax], rdi
0x180007074  jmp     short loc_18000707E
0x180007076  mov     ebx, 8007000Eh
0x18000707b  mov     rdi, rcx
0x18000707e  mov     rcx, [rsp+150h+var_F8]
0x180007083  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180007089  test    ebx, ebx
0x18000708b  jns     short loc_1800070DA
0x18000708d  test    rdi, rdi
0x180007090  jz      short loc_1800070A5
0x180007092  mov     rax, [rdi]
0x180007095  mov     edx, 1
0x18000709a  mov     rcx, rdi
0x18000709d  mov     rax, [rax]
0x1800070a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800070a5  cmp     [rsp+150h+var_FC], 1
0x1800070aa  jnz     short loc_1800070D3
0x1800070ac  mov     rax, [r13+20h]
0x1800070b0  lea     rcx, [r13+18h]; this
0x1800070b4  lea     rdx, [rsp+150h+SubKey]; unsigned __int16 *
  ... truncated ...
```
