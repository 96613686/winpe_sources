# RdVhd::Uvhd::CUvhdDiskManager::GetUvhdVolumePath(ushort const *,CPathString *)

- ea: `0x180053090`
- end: `0x1800533a5`
- name: `?GetUvhdVolumePath@CUvhdDiskManager@Uvhd@RdVhd@@AEBAJPEBGPEAVCPathString@@@Z`
- size: `789`
- prototype: `__int64 __fastcall(RdVhd::Uvhd::CUvhdDiskManager *__hidden this, const unsigned __int16 *, struct CPathString *)`
- caller_count: `2`
- callee_count: `13`
- tags: `reparse_path`

## callers

- `0x180052940`
- `0x1800548a0`

## callees

- `0x180004db0`
- `0x1800141e8`
- `0x180019b38`
- `0x18003114c`
- `0x180031204`
- `0x180031448`
- `0x18003146c`
- `0x180032808`
- `0x180035cfc`
- `0x180043df0`
- `0x1800488e4`
- `0x180048b28`
- `0x180053090`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005327e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005327e`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x180053270`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x180053270`

## string_xrefs

- `0x180053124`: `szUvhdMountPoint`
- `0x18005316c`: `pstrUvhdVolumeGuidPath`
- `0x1800532b6`: `GetVolumeNameForVolumeMountPointW("%s") FAILED`

## pseudocode

```c
__int64 __fastcall RdVhd::Uvhd::CUvhdDiskManager::GetUvhdVolumePath(
        RdVhd::Uvhd::CUvhdDiskManager *this,
        const unsigned __int16 *a2,
        struct CPathString *a3)
{
  RdVhd::Uvhd::CUvhdDiskManager *v4; // rcx
  __int64 v5; // rdx
  const wchar_t *v6; // r9
  signed int appended; // ebx
  RdVhd::Uvhd::CUvhdDiskManager *v8; // rcx
  __int64 v9; // rdx
  const WCHAR *v10; // rax
  LPWSTR v11; // r10
  DWORD v12; // r11d
  signed int LastError; // eax
  __int64 v14; // rax
  void **v16; // [rsp+20h] [rbp-50h] BYREF
  __int128 v17; // [rsp+28h] [rbp-48h]
  __int64 v18; // [rsp+38h] [rbp-38h]
  __int64 v19; // [rsp+40h] [rbp-30h]
  void **v20; // [rsp+48h] [rbp-28h] BYREF
  __int128 v21; // [rsp+50h] [rbp-20h]
  __int64 v22; // [rsp+60h] [rbp-10h]
  __int64 v23; // [rsp+68h] [rbp-8h]

  *(_QWORD *)((char *)&v21 + 4) = 128;
  LODWORD(v23) = 0x8000000;
  v20 = &CPathString::`vftable';
  LODWORD(v19) = 0x8000000;
  v16 = &CPathString::`vftable';
  v22 = 0;
  HIDWORD(v21) = 0;
  LODWORD(v21) = 0;
  *(_QWORD *)((char *)&v17 + 4) = 128;
  v18 = 0;
  HIDWORD(v17) = 0;
  LODWORD(v17) = 0;
  if ( !a2 )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_7;
    }
    v5 = 94;
    v6 = L"szUvhdMountPoint";
LABEL_6:
    WPP_SF_S(*((_QWORD *)v4 + 2), v5, WPP_59ca9d798db93fed5e210ee14600c8f5_Traceguids, v6);
LABEL_7:
    appended = -2147024809;
    goto LABEL_50;
  }
  if ( !a3 )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_7;
    }
    v5 = 95;
    v6 = L"pstrUvhdVolumeGuidPath";
    goto LABEL_6;
  }
  appended = CBaseStringT<unsigned short>::Append(&v20, a2);
  if ( appended >= 0 )
  {
    appended = CPathString::AppendBackslash((CPathString *)&v20);
    if ( appended >= 0 )
    {
      appended = CBaseStringT<unsigned short>::EnsureSpace(&v16, 260);
      if ( appended >= 0 )
      {
        CBaseStringT<unsigned short>::GetBufferLength(&v16);
        CBaseStringT<unsigned short>::GetBuffer(&v16);
        v10 = (const WCHAR *)CBaseStringT<unsigned short>::PContents(&v20);
        if ( GetVolumeNameForVolumeMountPointW(v10, v11, v12) )
          goto LABEL_39;
        LastError = GetLastError();
        appended = LastError;
        if ( LastError && (LastError & 0xFFFF0000) == 0 )
        {
          if ( LastError > 0 )
            appended = (unsigned __int16)LastError | 0x80070000;
          appended = appended & 0x8000FFFF | 0x50510000;
        }
        v14 = CBaseStringT<unsigned short>::PContents(&v20);
        _TraceNrmRdvVmEx(
          L"UVHD",
          appended,
          L"GetVolumeNameForVolumeMountPointW(\"%s\") FAILED",
          v14,
          v16,
          v17,
          v18,
          v19,
          v20,
          v21,
          v22,
          v23);
        if ( appended >= 0 )
        {
LABEL_39:
          appended = CBaseStringT<unsigned short>::SetLength(&v16);
          if ( appended >= 0 )
          {
            appended = CBaseStringT<unsigned short>::Set<unsigned short>(a3, &v16);
            if ( appended < 0 )
            {
              v8 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                v9 = 101;
                goto LABEL_49;
              }
            }
          }
          else
          {
            v8 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v9 = 100;
              goto LABEL_49;
            }
          }
        }
        else
        {
          v8 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v9 = 99;
            goto LABEL_49;
          }
        }
      }
      else
      {
        v8 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v9 = 98;
          goto LABEL_49;
        }
      }
    }
    else
    {
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v9 = 97;
        goto LABEL_49;
      }
    }
  }
  else
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v9 = 96;
LABEL_49:
      WPP_SF_d(*((_QWORD *)v8 + 2), v9, WPP_59ca9d798db93fed5e210ee14600c8f5_Traceguids, (unsigned int)appended);
    }
  }
LABEL_50:
  CPathString::~CPathString((CPathString *)&v16);
  CPathString::~CPathString((CPathString *)&v20);
  return (unsigned int)appended;
}

```

## disassembly

```asm
0x180053090  mov     [rsp-8+arg_0], rbx
0x180053095  mov     [rsp-8+arg_8], rdi
0x18005309a  push    rbp
0x18005309b  mov     rbp, rsp
0x18005309e  sub     rsp, 70h
0x1800530a2  mov     ecx, 8000000h
0x1800530a7  mov     qword ptr [rbp+var_20+4], 80h
0x1800530af  lea     rax, ??_7CPathString@@6B@; const CPathString::`vftable'
0x1800530b6  mov     dword ptr [rbp+var_8], ecx
0x1800530b9  mov     [rbp+var_28], rax
0x1800530bd  mov     rdi, r8
0x1800530c0  mov     dword ptr [rbp+var_30], ecx
0x1800530c3  mov     [rbp+var_50], rax
0x1800530c7  mov     [rbp+var_10], 0
0x1800530cf  mov     dword ptr [rbp+var_20+0Ch], 0
0x1800530d6  mov     dword ptr [rbp+var_20], 0
0x1800530dd  mov     qword ptr [rbp+var_48+4], 80h
0x1800530e5  mov     [rbp+var_38], 0
0x1800530ed  mov     dword ptr [rbp+var_48+0Ch], 0
0x1800530f4  mov     dword ptr [rbp+var_48], 0
0x1800530fb  test    rdx, rdx
0x1800530fe  jnz     short loc_180053145
0x180053100  mov     rcx, cs:WPP_GLOBAL_Control
0x180053107  lea     rax, WPP_GLOBAL_Control
0x18005310e  cmp     rcx, rax
0x180053111  jz      short loc_18005313B
0x180053113  test    byte ptr [rcx+1Ch], 4
0x180053117  jz      short loc_18005313B
0x180053119  cmp     byte ptr [rcx+19h], 2
0x18005311d  jb      short loc_18005313B
0x18005311f  mov     edx, 5Eh ; '^'
0x180053124  lea     r9, aSzuvhdmountpoi; "szUvhdMountPoint"
0x18005312b  mov     rcx, [rcx+10h]
0x18005312f  lea     r8, WPP_59ca9d798db93fed5e210ee14600c8f5_Traceguids
0x180053136  call    WPP_SF_S
0x18005313b  mov     ebx, 80070057h
0x180053140  jmp     loc_18005337F
0x180053145  test    rdi, rdi
0x180053148  jnz     short loc_180053175
0x18005314a  mov     rcx, cs:WPP_GLOBAL_Control
0x180053151  lea     rax, WPP_GLOBAL_Control
0x180053158  cmp     rcx, rax
0x18005315b  jz      short loc_18005313B
0x18005315d  test    byte ptr [rcx+1Ch], 4
0x180053161  jz      short loc_18005313B
0x180053163  cmp     byte ptr [rcx+19h], 2
0x180053167  jb      short loc_18005313B
0x180053169  lea     edx, [rdi+5Fh]
0x18005316c  lea     r9, aPstruvhdvolume; "pstrUvhdVolumeGuidPath"
0x180053173  jmp     short loc_18005312B
0x180053175  lea     rcx, [rbp+var_28]
0x180053179  call    ?Append@?$CBaseStringT@G@@QEAAJPEBG@Z; CBaseStringT<ushort>::Append(ushort const *)
0x18005317e  mov     ebx, eax
0x180053180  test    eax, eax
0x180053182  jns     short loc_1800531B9
0x180053184  mov     rcx, cs:WPP_GLOBAL_Control
0x18005318b  lea     rax, WPP_GLOBAL_Control
0x180053192  cmp     rcx, rax
0x180053195  jz      loc_18005337F
0x18005319b  test    byte ptr [rcx+1Ch], 4
0x18005319f  jz      loc_18005337F
0x1800531a5  cmp     byte ptr [rcx+19h], 2
0x1800531a9  jb      loc_18005337F
0x1800531af  mov     edx, 60h ; '`'
0x1800531b4  jmp     loc_18005336C
0x1800531b9  lea     rcx, [rbp+var_28]; this
0x1800531bd  call    ?AppendBackslash@CPathString@@QEAAJXZ; CPathString::AppendBackslash(void)
0x1800531c2  mov     ebx, eax
0x1800531c4  test    eax, eax
0x1800531c6  jns     short loc_1800531FD
0x1800531c8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800531cf  lea     rax, WPP_GLOBAL_Control
0x1800531d6  cmp     rcx, rax
0x1800531d9  jz      loc_18005337F
0x1800531df  test    byte ptr [rcx+1Ch], 4
0x1800531e3  jz      loc_18005337F
0x1800531e9  cmp     byte ptr [rcx+19h], 2
0x1800531ed  jb      loc_18005337F
0x1800531f3  mov     edx, 61h ; 'a'
0x1800531f8  jmp     loc_18005336C
0x1800531fd  mov     edx, 104h
0x180053202  lea     rcx, [rbp+var_50]
0x180053206  call    ?EnsureSpace@?$CBaseStringT@G@@IEAAJK@Z; CBaseStringT<ushort>::EnsureSpace(ulong)
0x18005320b  mov     ebx, eax
0x18005320d  test    eax, eax
0x18005320f  jns     short loc_180053246
0x180053211  mov     rcx, cs:WPP_GLOBAL_Control
0x180053218  lea     rax, WPP_GLOBAL_Control
0x18005321f  cmp     rcx, rax
0x180053222  jz      loc_18005337F
0x180053228  test    byte ptr [rcx+1Ch], 4
0x18005322c  jz      loc_18005337F
0x180053232  cmp     byte ptr [rcx+19h], 2
0x180053236  jb      loc_18005337F
0x18005323c  mov     edx, 62h ; 'b'
0x180053241  jmp     loc_18005336C
0x180053246  lea     rcx, [rbp+var_50]
0x18005324a  call    ?GetBufferLength@?$CBaseStringT@G@@QEBAKXZ; CBaseStringT<ushort>::GetBufferLength(void)
0x18005324f  lea     rcx, [rbp+var_50]
0x180053253  mov     r11d, eax
0x180053256  call    ?GetBuffer@?$CBaseStringT@G@@QEAAPEAGK@Z; CBaseStringT<ushort>::GetBuffer(ulong)
0x18005325b  lea     rcx, [rbp+var_28]
0x18005325f  mov     r10, rax
0x180053262  call    ?PContents@?$CBaseStringT@G@@QEBAPEBGXZ; CBaseStringT<ushort>::PContents(void)
0x180053267  mov     r8d, r11d; cchBufferLength
0x18005326a  mov     rdx, r10; lpszVolumeName
0x18005326d  mov     rcx, rax; lpszVolumeMountPoint
0x180053270  call    cs:__imp_GetVolumeNameForVolumeMountPointW
0x180053276  test    eax, eax
0x180053278  jnz     loc_180053301
0x18005327e  call    cs:__imp_GetLastError
0x180053284  mov     ebx, eax
0x180053286  test    eax, eax
0x180053288  jz      short loc_1800532AA
0x18005328a  test    eax, 0FFFF0000h
0x18005328f  jnz     short loc_1800532AA
0x180053291  test    eax, eax
0x180053293  jle     short loc_18005329E
0x180053295  movzx   ebx, ax
0x180053298  or      ebx, 80070000h
0x18005329e  and     ebx, 0D051FFFFh
0x1800532a4  or      ebx, 50510000h
0x1800532aa  lea     rcx, [rbp+var_28]
0x1800532ae  call    ?PContents@?$CBaseStringT@G@@QEBAPEBGXZ; CBaseStringT<ushort>::PContents(void)
0x1800532b3  mov     r9, rax
0x1800532b6  lea     r8, aGetvolumenamef; "GetVolumeNameForVolumeMountPointW(\"%s"...
0x1800532bd  mov     edx, ebx; int
0x1800532bf  lea     rcx, aUvhd; "UVHD"
0x1800532c6  call    ?_TraceNrmRdvVmEx@@YAXPEBGJ0ZZ; _TraceNrmRdvVmEx(ushort const *,long,ushort const *,...)
0x1800532cb  test    ebx, ebx
0x1800532cd  jns     short loc_180053301
0x1800532cf  mov     rcx, cs:WPP_GLOBAL_Control
0x1800532d6  lea     rax, WPP_GLOBAL_Control
0x1800532dd  cmp     rcx, rax
0x1800532e0  jz      loc_18005337F
0x1800532e6  test    byte ptr [rcx+1Ch], 4
0x1800532ea  jz      loc_18005337F
0x1800532f0  cmp     byte ptr [rcx+19h], 2
0x1800532f4  jb      loc_18005337F
0x1800532fa  mov     edx, 63h ; 'c'
0x1800532ff  jmp     short loc_18005336C
0x180053301  lea     rcx, [rbp+var_50]
0x180053305  call    ?SetLength@?$CBaseStringT@G@@QEAAJXZ; CBaseStringT<ushort>::SetLength(void)
0x18005330a  mov     ebx, eax
0x18005330c  test    eax, eax
0x18005330e  jns     short loc_180053336
0x180053310  mov     rcx, cs:WPP_GLOBAL_Control
0x180053317  lea     rax, WPP_GLOBAL_Control
0x18005331e  cmp     rcx, rax
0x180053321  jz      short loc_18005337F
0x180053323  test    byte ptr [rcx+1Ch], 4
0x180053327  jz      short loc_18005337F
0x180053329  cmp     byte ptr [rcx+19h], 2
0x18005332d  jb      short loc_18005337F
0x18005332f  mov     edx, 64h ; 'd'
0x180053334  jmp     short loc_18005336C
0x180053336  lea     rdx, [rbp+var_50]
0x18005333a  mov     rcx, rdi
0x18005333d  call    ??$Set@G@?$CBaseStringT@G@@QEAAJAEBV0@@Z; CBaseStringT<ushort>::Set<ushort>(CBaseStringT<ushort> const &)
0x180053342  mov     ebx, eax
0x180053344  test    eax, eax
0x180053346  jns     short loc_18005337F
0x180053348  mov     rcx, cs:WPP_GLOBAL_Control
0x18005334f  lea     rax, WPP_GLOBAL_Control
0x180053356  cmp     rcx, rax
0x180053359  jz      short loc_18005337F
0x18005335b  test    byte ptr [rcx+1Ch], 4
0x18005335f  jz      short loc_18005337F
0x180053361  cmp     byte ptr [rcx+19h], 2
0x180053365  jb      short loc_18005337F
0x180053367  mov     edx, 65h ; 'e'
0x18005336c  mov     rcx, [rcx+10h]
0x180053370  lea     r8, WPP_59ca9d798db93fed5e210ee14600c8f5_Traceguids
0x180053377  mov     r9d, ebx
0x18005337a  call    WPP_SF_d
0x18005337f  lea     rcx, [rbp+var_50]; this
0x180053383  call    ??1CPathString@@QEAA@XZ; CPathString::~CPathString(void)
0x180053388  lea     rcx, [rbp+var_28]; this
0x18005338c  call    ??1CPathString@@QEAA@XZ; CPathString::~CPathString(void)
0x180053391  lea     r11, [rsp+70h+var_s0]
0x180053396  mov     eax, ebx
0x180053398  mov     rbx, [r11+10h]
0x18005339c  mov     rdi, [r11+18h]
0x1800533a0  mov     rsp, r11
0x1800533a3  pop     rbp
0x1800533a4  retn
```
