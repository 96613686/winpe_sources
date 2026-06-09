# CUserVaultMgr::InitializeProfilePath(void *)

- ea: `0x18000ff18`
- end: `0x18001050e`
- name: `?InitializeProfilePath@CUserVaultMgr@@AEAAKPEAX@Z`
- size: `1526`
- prototype: `__int64 __fastcall(CUserVaultMgr *this, void *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000cd28`

## callees

- `0x180003140`
- `0x18000eb30`
- `0x18000ff18`
- `0x180011110`
- `0x1800310a0`
- `0x18003b7d8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000ffc8`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180010061`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180010145`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000ffc8`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180010061`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180010145`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010208`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010331`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010397`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010453`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010208`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010331`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010397`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010453`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000ff79`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180010012`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800100f2`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000ff79`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180010012`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800100f2`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180010099`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1800100b2`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1800101eb`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1800101fe`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180010099`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1800100b2`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1800101eb`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1800101fe`
- `profapi!__imp_ExpandEnvStringForUser` at `0x18000ff9f`
- `profapi!__imp_ExpandEnvStringForUser` at `0x180010038`
- `profapi!__imp_ExpandEnvStringForUser` at `0x180010118`
- `profapi!__imp_ExpandEnvStringForUser` at `0x18000ff9f`
- `profapi!__imp_ExpandEnvStringForUser` at `0x180010038`
- `profapi!__imp_ExpandEnvStringForUser` at `0x180010118`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CUserVaultMgr::InitializeProfilePath(CUserVaultMgr *this, void *a2)
{
  unsigned int v4; // edi
  const WCHAR *v5; // rax
  const WCHAR *v6; // rsi
  unsigned int VaultProfilePath; // ebx
  unsigned int v8; // r14d
  const WCHAR *v9; // rax
  const WCHAR *v10; // rdi
  unsigned int v11; // eax
  unsigned int v12; // esi
  HLOCAL v13; // rax
  HLOCAL v14; // rdi
  unsigned int v15; // eax
  DWORD v17; // eax
  DWORD LastError; // eax
  DWORD v19; // eax
  DWORD v20; // eax
  __int64 v21; // [rsp+20h] [rbp-58h] BYREF
  const WCHAR *v22; // [rsp+28h] [rbp-50h]
  __int64 v23; // [rsp+30h] [rbp-48h]
  __int64 v24; // [rsp+38h] [rbp-40h] BYREF
  const WCHAR *v25; // [rsp+40h] [rbp-38h]
  __int64 v26; // [rsp+48h] [rbp-30h]
  __int64 v27; // [rsp+50h] [rbp-28h] BYREF
  const WCHAR *v28; // [rsp+58h] [rbp-20h]
  __int64 v29; // [rsp+60h] [rbp-18h]
  __int64 ThreadInformation; // [rsp+D0h] [rbp+58h] BYREF

  v25 = 0;
  LODWORD(v26) = 0;
  v24 = 0;
  v22 = 0;
  LODWORD(v23) = 0;
  v21 = 0;
  ThreadInformation = 0;
  v28 = 0;
  LODWORD(v29) = 0;
  v27 = 0;
  v4 = 0;
  while ( 1 )
  {
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v27);
    v4 += 260;
    v5 = (const WCHAR *)LocalAlloc(0x40u, 2LL * v4);
    v6 = v5;
    v28 = v5;
    if ( !v5 )
      break;
    VaultProfilePath = ExpandEnvStringForUser(
                         a2,
                         L"%APPDATA%\\Microsoft",
                         v5,
                         v4,
                         v21,
                         v22,
                         v23,
                         v24,
                         v25,
                         v26,
                         v27,
                         v28,
                         v29);
    if ( (VaultProfilePath & 0x1FFF0000) == 0x70000 )
      VaultProfilePath = (unsigned __int16)VaultProfilePath;
    if ( !VaultProfilePath )
    {
      if ( !(unsigned int)_o__wcsicmp(v6, L"%APPDATA%\\Microsoft") )
      {
LABEL_23:
        CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v27);
        VaultProfilePath = 2016;
        goto LABEL_24;
      }
      v28 = 0;
      v25 = v6;
      CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v27);
      v28 = 0;
      LODWORD(v29) = 0;
      v27 = 0;
      v8 = 0;
      while ( 1 )
      {
        CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v27);
        v8 += 260;
        v9 = (const WCHAR *)LocalAlloc(0x40u, 2LL * v8);
        v10 = v9;
        v28 = v9;
        if ( !v9 )
          goto LABEL_40;
        VaultProfilePath = ExpandEnvStringForUser(a2, L"%LOCALAPPDATA%\\Microsoft", v9, v8);
        if ( (VaultProfilePath & 0x1FFF0000) == 0x70000 )
          VaultProfilePath = (unsigned __int16)VaultProfilePath;
        if ( !VaultProfilePath )
        {
          if ( !(unsigned int)_o__wcsicmp(v10, L"%LOCALAPPDATA%\\Microsoft") )
            goto LABEL_23;
          v28 = 0;
          v22 = v10;
          CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v27);
          v11 = CVaultIntegrityLevel::Elevate((CVaultIntegrityLevel *)&ThreadInformation);
          VaultProfilePath = v11;
          if ( v11 )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, &WPP_f1575cf6446936089985711df8c7b212_Traceguids, v11);
            goto LABEL_24;
          }
          if ( !CreateDirectoryW(v6, 0) )
          {
            LastError = GetLastError();
            VaultProfilePath = LastError;
            if ( LastError != 183 )
            {
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
                WPP_SF_d(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  22,
                  &WPP_f1575cf6446936089985711df8c7b212_Traceguids,
                  LastError);
              goto LABEL_24;
            }
          }
          if ( !CreateDirectoryW(v10, 0) )
          {
            v19 = GetLastError();
            VaultProfilePath = v19;
            if ( v19 != 183 )
            {
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
                WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, &WPP_f1575cf6446936089985711df8c7b212_Traceguids, v19);
              goto LABEL_24;
            }
          }
          if ( !*((_QWORD *)this + 6) )
          {
            v28 = 0;
            LODWORD(v29) = 0;
            v27 = 0;
            v12 = 0;
            while ( 1 )
            {
              CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v27);
              v12 += 260;
              v13 = LocalAlloc(0x40u, 2LL * v12);
              v14 = v13;
              v28 = (const WCHAR *)v13;
              if ( !v13 )
                goto LABEL_40;
              v15 = ExpandEnvStringForUser(a2, L"%LOCALAPPDATA%\\Microsoft\\Vault", v13, v12);
              VaultProfilePath = v15;
              if ( (v15 & 0x1FFF0000) == 0x70000 )
                VaultProfilePath = (unsigned __int16)v15;
              if ( !VaultProfilePath )
              {
                if ( !(unsigned int)_o__wcsicmp(v14, L"%LOCALAPPDATA%\\Microsoft\\Vault") )
                  goto LABEL_23;
                v28 = 0;
                *((_QWORD *)this + 6) = v14;
                CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v27);
                break;
              }
              if ( VaultProfilePath != 122 )
                goto LABEL_30;
            }
          }
          if ( *((_QWORD *)this + 7)
            || (VaultProfilePath = LoadVaultProfilePath(
                                     a2,
                                     L"%APPDATA%\\Microsoft\\Vault",
                                     (unsigned __int16 **)this + 7)) == 0 )
          {
            if ( CreateDirectoryW(*((LPCWSTR *)this + 6), 0)
              || (v20 = GetLastError(), VaultProfilePath = v20, v20 == 183) )
            {
              if ( CreateDirectoryW(*((LPCWSTR *)this + 7), 0)
                || (v17 = GetLastError(), VaultProfilePath = v17, v17 == 183) )
              {
                CVaultIntegrityLevel::~CVaultIntegrityLevel(&ThreadInformation);
                CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v21);
                CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v24);
                return 0;
              }
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
                WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, &WPP_f1575cf6446936089985711df8c7b212_Traceguids, v17);
            }
            else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
            {
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, &WPP_f1575cf6446936089985711df8c7b212_Traceguids, v20);
            }
          }
          goto LABEL_24;
        }
        if ( VaultProfilePath != 122 )
          goto LABEL_30;
      }
    }
    if ( VaultProfilePath != 122 )
    {
LABEL_30:
      CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v27);
      goto LABEL_24;
    }
  }
LABEL_40:
  CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v27);
  VaultProfilePath = 14;
LABEL_24:
  CVaultIntegrityLevel::~CVaultIntegrityLevel(&ThreadInformation);
  CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v21);
  CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v24);
  return VaultProfilePath;
}

```

## disassembly

```asm
0x18000ff18  push    rbp
0x18000ff1a  push    rbx
0x18000ff1b  push    rsi
0x18000ff1c  push    rdi
0x18000ff1d  push    r12
0x18000ff1f  push    r13
0x18000ff21  push    r14
0x18000ff23  push    r15
0x18000ff25  mov     rbp, rsp
0x18000ff28  sub     rsp, 78h
0x18000ff2c  mov     r12, rdx
0x18000ff2f  mov     r15, rcx
0x18000ff32  xor     r13d, r13d
0x18000ff35  mov     [rbp+var_38], r13
0x18000ff39  mov     dword ptr [rbp+var_30], r13d
0x18000ff3d  mov     [rbp+var_40], r13
0x18000ff41  mov     [rbp+var_50], r13
0x18000ff45  mov     dword ptr [rbp+var_48], r13d
0x18000ff49  mov     [rbp+var_58], r13
0x18000ff4d  mov     [rbp+ThreadInformation], r13
0x18000ff51  mov     [rbp+var_20], r13
0x18000ff55  mov     dword ptr [rbp+var_18], r13d
0x18000ff59  mov     [rbp+var_28], r13
0x18000ff5d  mov     edi, r13d
0x18000ff60  lea     rcx, [rbp+var_28]
0x18000ff64  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18000ff69  add     edi, 104h
0x18000ff6f  mov     edx, edi
0x18000ff71  add     rdx, rdx; uBytes
0x18000ff74  mov     ecx, 40h ; '@'; uFlags
0x18000ff79  call    cs:__imp_LocalAlloc
0x18000ff7f  mov     rsi, rax
0x18000ff82  mov     [rbp+var_20], rax
0x18000ff86  test    rax, rax
0x18000ff89  jz      loc_1800102EC
0x18000ff8f  mov     r9d, edi
0x18000ff92  mov     r8, rax
0x18000ff95  lea     rdx, aAppdataMicroso; "%APPDATA%\\Microsoft"
0x18000ff9c  mov     rcx, r12
0x18000ff9f  call    cs:__imp_ExpandEnvStringForUser
0x18000ffa5  mov     ebx, eax
0x18000ffa7  and     eax, 1FFF0000h
0x18000ffac  cmp     eax, 70000h
0x18000ffb1  jnz     short loc_18000FFB6
0x18000ffb3  movzx   ebx, bx
0x18000ffb6  test    ebx, ebx
0x18000ffb8  jnz     loc_180010193
0x18000ffbe  lea     rdx, aAppdataMicroso; "%APPDATA%\\Microsoft"
0x18000ffc5  mov     rcx, rsi
0x18000ffc8  call    cs:__imp__o__wcsicmp
0x18000ffce  test    eax, eax
0x18000ffd0  jz      loc_180010270
0x18000ffd6  mov     [rbp+var_20], r13
0x18000ffda  mov     [rbp+var_38], rsi
0x18000ffde  lea     rcx, [rbp+var_28]
0x18000ffe2  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18000ffe7  nop
0x18000ffe8  mov     [rbp+var_20], r13
0x18000ffec  mov     dword ptr [rbp+var_18], r13d
0x18000fff0  mov     [rbp+var_28], r13
0x18000fff4  mov     r14d, r13d
0x18000fff7  lea     rcx, [rbp+var_28]
0x18000fffb  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180010000  add     r14d, 104h
0x180010007  mov     edx, r14d
0x18001000a  add     rdx, rdx; uBytes
0x18001000d  mov     ecx, 40h ; '@'; uFlags
0x180010012  call    cs:__imp_LocalAlloc
0x180010018  mov     rdi, rax
0x18001001b  mov     [rbp+var_20], rax
0x18001001f  test    rax, rax
0x180010022  jz      loc_1800102D8
0x180010028  mov     r9d, r14d
0x18001002b  mov     r8, rax
0x18001002e  lea     rdx, aLocalappdataMi; "%LOCALAPPDATA%\\Microsoft"
0x180010035  mov     rcx, r12
0x180010038  call    cs:__imp_ExpandEnvStringForUser
0x18001003e  mov     ebx, eax
0x180010040  and     eax, 1FFF0000h
0x180010045  cmp     eax, 70000h
0x18001004a  jnz     short loc_18001004F
0x18001004c  movzx   ebx, bx
0x18001004f  test    ebx, ebx
0x180010051  jnz     loc_1800101AB
0x180010057  lea     rdx, aLocalappdataMi; "%LOCALAPPDATA%\\Microsoft"
0x18001005e  mov     rcx, rdi
0x180010061  call    cs:__imp__o__wcsicmp
0x180010067  test    eax, eax
0x180010069  jz      loc_18001023E
0x18001006f  mov     [rbp+var_20], r13
0x180010073  mov     [rbp+var_50], rdi
0x180010077  lea     rcx, [rbp+var_28]
0x18001007b  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180010080  nop
0x180010081  lea     rcx, [rbp+ThreadInformation]; this
0x180010085  call    ?Elevate@CVaultIntegrityLevel@@QEAAKXZ; CVaultIntegrityLevel::Elevate(void)
0x18001008a  mov     ebx, eax
0x18001008c  test    eax, eax
0x18001008e  jnz     loc_1800102A2
0x180010094  xor     edx, edx; lpSecurityAttributes
0x180010096  mov     rcx, rsi; lpPathName
0x180010099  call    cs:__imp_CreateDirectoryW
0x18001009f  mov     r14d, 0B7h
0x1800100a5  test    eax, eax
0x1800100a7  jz      loc_180010331
0x1800100ad  xor     edx, edx; lpSecurityAttributes
0x1800100af  mov     rcx, rdi; lpPathName
0x1800100b2  call    cs:__imp_CreateDirectoryW
0x1800100b8  test    eax, eax
0x1800100ba  jz      loc_180010397
0x1800100c0  cmp     [r15+30h], r13
0x1800100c4  jnz     loc_1800101D8
0x1800100ca  mov     [rbp+var_20], r13
0x1800100ce  mov     dword ptr [rbp+var_18], r13d
0x1800100d2  mov     [rbp+var_28], r13
0x1800100d6  mov     esi, r13d
0x1800100d9  lea     rcx, [rbp+var_28]
0x1800100dd  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x1800100e2  add     esi, 104h
0x1800100e8  mov     edx, esi
0x1800100ea  add     rdx, rdx; uBytes
0x1800100ed  mov     ecx, 40h ; '@'; uFlags
0x1800100f2  call    cs:__imp_LocalAlloc
0x1800100f8  mov     rdi, rax
0x1800100fb  mov     [rbp+var_20], rax
0x1800100ff  test    rax, rax
0x180010102  jz      loc_1800102FD
0x180010108  mov     r9d, esi
0x18001010b  mov     r8, rax
0x18001010e  lea     rdx, aLocalappdataMi_0; "%LOCALAPPDATA%\\Microsoft\\Vault"
0x180010115  mov     rcx, r12
0x180010118  call    cs:__imp_ExpandEnvStringForUser
0x18001011e  mov     ebx, eax
0x180010120  mov     ecx, eax
0x180010122  and     ecx, 1FFF0000h
0x180010128  cmp     ecx, 70000h
0x18001012e  jnz     short loc_180010133
0x180010130  movzx   ebx, ax
0x180010133  test    ebx, ebx
0x180010135  jnz     loc_1800101C3
0x18001013b  lea     rdx, aLocalappdataMi_0; "%LOCALAPPDATA%\\Microsoft\\Vault"
0x180010142  mov     rcx, rdi
0x180010145  call    cs:__imp__o__wcsicmp
0x18001014b  test    eax, eax
0x18001014d  jnz     loc_1800103FD
0x180010153  lea     rcx, [rbp+var_28]
0x180010157  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18001015c  nop
0x18001015d  mov     ebx, 7E0h
0x180010162  lea     rcx, [rbp+ThreadInformation]; ThreadInformation
0x180010166  call    ??1CVaultIntegrityLevel@@QEAA@XZ; CVaultIntegrityLevel::~CVaultIntegrityLevel(void)
0x18001016b  nop
0x18001016c  lea     rcx, [rbp+var_58]
0x180010170  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180010175  nop
0x180010176  lea     rcx, [rbp+var_40]
0x18001017a  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18001017f  nop
0x180010180  mov     eax, ebx
0x180010182  add     rsp, 78h
0x180010186  pop     r15
0x180010188  pop     r14
0x18001018a  pop     r13
0x18001018c  pop     r12
0x18001018e  pop     rdi
0x18001018f  pop     rsi
0x180010190  pop     rbx
0x180010191  pop     rbp
0x180010192  retn
0x180010193  cmp     ebx, 7Ah ; 'z'
0x180010196  jz      loc_18000FF60
0x18001019c  lea     rcx, [rbp+var_28]
0x1800101a0  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x1800101a5  nop
0x1800101a6  jmp     loc_18001027F
0x1800101ab  cmp     ebx, 7Ah ; 'z'
0x1800101ae  jz      loc_18000FFF7
0x1800101b4  lea     rcx, [rbp+var_28]
0x1800101b8  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x1800101bd  nop
0x1800101be  jmp     loc_18001024D
0x1800101c3  cmp     ebx, 7Ah ; 'z'
0x1800101c6  jz      loc_1800100D9
0x1800101cc  lea     rcx, [rbp+var_28]
0x1800101d0  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x1800101d5  nop
0x1800101d6  jmp     short loc_180010162
0x1800101d8  lea     rdi, [r15+38h]
0x1800101dc  cmp     [rdi], r13
0x1800101df  jz      loc_180010414
0x1800101e5  xor     edx, edx; lpSecurityAttributes
0x1800101e7  mov     rcx, [r15+30h]; lpPathName
0x1800101eb  call    cs:__imp_CreateDirectoryW
0x1800101f1  test    eax, eax
0x1800101f3  jz      loc_180010453
0x1800101f9  xor     edx, edx; lpSecurityAttributes
0x1800101fb  mov     rcx, [rdi]; lpPathName
0x1800101fe  call    cs:__imp_CreateDirectoryW
0x180010204  test    eax, eax
0x180010206  jnz     short loc_180010219
0x180010208  call    cs:__imp_GetLastError
0x18001020e  mov     ebx, eax
0x180010210  cmp     eax, r14d
0x180010213  jnz     loc_1800104B9
0x180010219  lea     rcx, [rbp+ThreadInformation]; ThreadInformation
0x18001021d  call    ??1CVaultIntegrityLevel@@QEAA@XZ; CVaultIntegrityLevel::~CVaultIntegrityLevel(void)
0x180010222  nop
0x180010223  lea     rcx, [rbp+var_58]
0x180010227  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18001022c  nop
0x18001022d  lea     rcx, [rbp+var_40]
0x180010231  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180010236  nop
0x180010237  xor     eax, eax
0x180010239  jmp     loc_180010182
0x18001023e  lea     rcx, [rbp+var_28]
0x180010242  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180010247  nop
0x180010248  mov     ebx, 7E0h
0x18001024d  lea     rcx, [rbp+ThreadInformation]; ThreadInformation
0x180010251  call    ??1CVaultIntegrityLevel@@QEAA@XZ; CVaultIntegrityLevel::~CVaultIntegrityLevel(void)
0x180010256  nop
0x180010257  lea     rcx, [rbp+var_58]
0x18001025b  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180010260  nop
0x180010261  lea     rcx, [rbp+var_40]
0x180010265  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18001026a  nop
0x18001026b  jmp     loc_180010180
0x180010270  lea     rcx, [rbp+var_28]
0x180010274  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180010279  nop
0x18001027a  mov     ebx, 7E0h
0x18001027f  lea     rcx, [rbp+ThreadInformation]; ThreadInformation
0x180010283  call    ??1CVaultIntegrityLevel@@QEAA@XZ; CVaultIntegrityLevel::~CVaultIntegrityLevel(void)
0x180010288  nop
0x180010289  lea     rcx, [rbp+var_58]
0x18001028d  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180010292  nop
0x180010293  lea     rcx, [rbp+var_40]
0x180010297  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18001029c  nop
0x18001029d  jmp     loc_180010180
0x1800102a2  lea     rdx, WPP_GLOBAL_Control
0x1800102a9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800102b0  cmp     rcx, rdx
0x1800102b3  jnz     short loc_180010311
0x1800102b5  lea     rcx, [rbp+ThreadInformation]; ThreadInformation
0x1800102b9  call    ??1CVaultIntegrityLevel@@QEAA@XZ; CVaultIntegrityLevel::~CVaultIntegrityLevel(void)
0x1800102be  nop
0x1800102bf  lea     rcx, [rbp+var_58]
0x1800102c3  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x1800102c8  nop
0x1800102c9  lea     rcx, [rbp+var_40]
0x1800102cd  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x1800102d2  nop
0x1800102d3  jmp     loc_180010180
0x1800102d8  lea     rcx, [rbp+var_28]
0x1800102dc  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x1800102e1  nop
0x1800102e2  mov     ebx, 0Eh
0x1800102e7  jmp     loc_18001024D
0x1800102ec  lea     rcx, [rbp+var_28]
0x1800102f0  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x1800102f5  nop
0x1800102f6  mov     ebx, 0Eh
0x1800102fb  jmp     short loc_18001027F
0x1800102fd  lea     rcx, [rbp+var_28]
0x180010301  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180010306  nop
0x180010307  mov     ebx, 0Eh
0x18001030c  jmp     loc_180010162
0x180010311  test    byte ptr [rcx+1Ch], 2
0x180010315  jz      short loc_1800102B5
0x180010317  mov     edx, 15h
0x18001031c  mov     r9d, ebx
0x18001031f  lea     r8, WPP_f1575cf6446936089985711df8c7b212_Traceguids
0x180010326  mov     rcx, [rcx+10h]
0x18001032a  call    WPP_SF_d
0x18001032f  jmp     short loc_1800102B5
0x180010331  call    cs:__imp_GetLastError
0x180010337  mov     ebx, eax
0x180010339  cmp     eax, r14d
0x18001033c  jz      loc_1800100AD
0x180010342  lea     rdx, WPP_GLOBAL_Control
0x180010349  mov     rcx, cs:WPP_GLOBAL_Control
0x180010350  cmp     rcx, rdx
0x180010353  jz      short loc_180010374
0x180010355  test    byte ptr [rcx+1Ch], 2
0x180010359  jz      short loc_180010374
0x18001035b  mov     edx, 16h
0x180010360  mov     r9d, eax
0x180010363  lea     r8, WPP_f1575cf6446936089985711df8c7b212_Traceguids
0x18001036a  mov     rcx, [rcx+10h]
0x18001036e  call    WPP_SF_d
0x180010373  nop
0x180010374  lea     rcx, [rbp+ThreadInformation]; ThreadInformation
0x180010378  call    ??1CVaultIntegrityLevel@@QEAA@XZ; CVaultIntegrityLevel::~CVaultIntegrityLevel(void)
0x18001037d  nop
0x18001037e  lea     rcx, [rbp+var_58]
  ... truncated ...
```
