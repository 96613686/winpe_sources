# CDbOperationManager::CreateInstance(ushort const *,ushort const *,ulong,int,int,ushort const *,int *,CDbOperationManager * *)

- ea: `0x1800e93ec`
- end: `0x1800e9806`
- name: `?CreateInstance@CDbOperationManager@@SAJPEBG0KHH0PEAHPEAPEAV1@@Z`
- size: `1050`
- prototype: `__int64 __usercall@<rax>(LPCWSTR psz@<rcx>, LPCWSTR@<rdx>, unsigned int@<r8d>, int@<r9d>, int, const unsigned __int16 *Source, int *, struct CDbOperationManager **)`
- caller_count: `1`
- callee_count: `18`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800d6530`

## callees

- `0x180002ab0`
- `0x180003eec`
- `0x180006ed0`
- `0x180006f5c`
- `0x180007aec`
- `0x18001137c`
- `0x18002dad0`
- `0x1800d3488`
- `0x1800d59b4`
- `0x1800d6154`
- `0x1800d6f28`
- `0x1800d7de0`
- `0x1800e8068`
- `0x1800e93ec`
- `0x1800e9a58`
- `0x1800ea120`
- `0x1800eb76c`
- `0x1800ebc5c`

## import_xrefs

- `KERNEL32!GetVolumePathNameW` at `0x1800e966c`
- `KERNEL32!GetVolumePathNameW` at `0x1800e966c`
- `KERNEL32!GetLastError` at `0x1800e9676`
- `KERNEL32!GetLastError` at `0x1800e9676`
- `SHLWAPI!SHStrDupW` at `0x1800e94ee`
- `SHLWAPI!SHStrDupW` at `0x1800e9508`
- `SHLWAPI!SHStrDupW` at `0x1800e94ee`
- `SHLWAPI!SHStrDupW` at `0x1800e9508`

## string_xrefs

- `0x1800e946e`: `CDbOperationManager::CreateInstance`

## pseudocode

```c
__int64 __fastcall CDbOperationManager::CreateInstance(
        __int64 psz,
        LPCWSTR a2,
        int a3,
        int a4,
        int a5,
        const unsigned __int16 *Source,
        int *a7,
        struct CDbOperationManager **a8)
{
  const WCHAR *v10; // r14
  int v11; // edx
  int v12; // ebx
  int v13; // r8d
  int v14; // r9d
  CDbOperationManager *v15; // rax
  CDbOperationManager *v16; // rax
  CDbOperationManager *v17; // rdi
  _QWORD *v18; // r12
  __int64 v19; // rdx
  __int64 v20; // r8
  __int64 v21; // r9
  const unsigned __int16 **v22; // r13
  HRESULT v23; // eax
  int v24; // r15d
  __int64 v25; // rsi
  __int64 v26; // rdx
  const unsigned __int16 *v27; // r8
  __int64 v28; // rcx
  rsize_t v29; // rsi
  int v30; // eax
  _QWORD *v31; // rcx
  __int64 v32; // rdx
  const unsigned __int16 *v33; // rcx
  __int64 v34; // rax
  unsigned __int64 v35; // rsi
  unsigned __int16 **v36; // r14
  int v37; // eax
  int v38; // ecx
  DWORD LastError; // eax
  CDbOperationManager *v44; // [rsp+40h] [rbp-288h] BYREF
  struct CDbOperationManager **v45; // [rsp+48h] [rbp-280h]
  LPCWSTR lpszFileName; // [rsp+50h] [rbp-278h]
  int *v47; // [rsp+58h] [rbp-270h]
  WCHAR szVolumePathName[264]; // [rsp+60h] [rbp-268h] BYREF

  v10 = (const WCHAR *)psz;
  v47 = a7;
  v45 = a8;
  lpszFileName = a2;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_sS(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      16,
      (unsigned int)&WPP_bbf747101dc030c08db8ff9d4150e8cf_Traceguids,
      (unsigned int)"CDbOperationManager::CreateInstance",
      psz);
  v12 = CDbOperationManager::InitializeGlobalContextState();
  if ( v12 >= 0 )
  {
    *a8 = 0;
    *a7 = 0;
    v15 = (CDbOperationManager *)operator new(0xD0u, (const struct std::nothrow_t *)&byte_180166367);
    if ( v15 )
    {
      v16 = CDbOperationManager::CDbOperationManager(v15);
      v44 = v16;
      v17 = v16;
      if ( v16 )
      {
        v18 = (_QWORD *)((char *)v16 + 72);
        *((_DWORD *)v16 + 26) = a4;
        *((_DWORD *)v16 + 27) = a5;
        v12 = SHStrDupW(v10, (LPWSTR *)v16 + 9);
        if ( v12 < 0 )
          goto LABEL_49;
        v22 = (const unsigned __int16 **)((char *)v17 + 80);
        v23 = SHStrDupW(a2, (LPWSTR *)v17 + 10);
        v21 = 0;
        v12 = v23;
        if ( v23 < 0 )
          goto LABEL_49;
        v24 = 1;
        if ( Source )
        {
          v25 = 0;
          v26 = 0;
          v27 = Source;
          do
          {
            v28 = *v27;
            ++v25;
            ++v26;
            ++v27;
            if ( (_WORD)v28 )
              v26 = 0;
          }
          while ( v26 != 2 );
          v29 = 2 * v25;
          v12 = _AllocArray<unsigned short,CTCoAllocPolicy>(v28, 1, v29, (char *)v17 + 96);
          if ( v12 < 0 )
            goto LABEL_49;
          memcpy_s(*((void *const *)v17 + 12), v29, Source, v29);
        }
        v30 = CMetaStoreUtils::OpenThreadTokenForImpersonation((PHANDLE)v17 + 14);
        v12 = v30;
        if ( v30 < 0 )
        {
          if ( v30 != -2147023888 )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              WPP_SF_Sd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                19,
                (unsigned int)&WPP_bbf747101dc030c08db8ff9d4150e8cf_Traceguids,
                *v18,
                v30);
LABEL_30:
            v37 = a4;
            v38 = a3;
            if ( !a4 || a3 == 2 )
            {
              if ( v12 < 0 )
                goto LABEL_48;
              if ( !a4 || a3 == 2 )
                v24 = 0;
            }
            else
            {
              if ( v12 < 0 )
              {
LABEL_48:
                v10 = (const WCHAR *)psz;
LABEL_49:
                CTSmartObj<CDbOperationManager *,CTSmartPtr_PolicyComplete<CTContainer_PolicyNewMem>>::Release(
                  &v44,
                  v19,
                  v20,
                  v21);
                goto LABEL_50;
              }
              if ( !GetVolumePathNameW(lpszFileName, szVolumePathName, 0x104u) )
              {
                LastError = GetLastError();
                if ( LastError - 2 <= 1 || LastError == 123 )
                {
                  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
                    WPP_SF_Sd(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      20,
                      (unsigned int)&WPP_bbf747101dc030c08db8ff9d4150e8cf_Traceguids,
                      *v18,
                      LastError);
                  *((_DWORD *)v17 + 11) = 0;
                  *((_DWORD *)v17 + 13) = ResultFromJetError(-1023);
LABEL_47:
                  v44 = 0;
                  *v45 = v17;
                  goto LABEL_48;
                }
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
                  WPP_SF_Sd(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    21,
                    (unsigned int)&WPP_bbf747101dc030c08db8ff9d4150e8cf_Traceguids,
                    *v18,
                    LastError);
              }
              v37 = a4;
              v38 = a3;
            }
            v12 = CDbOperationManager::InitializeDB(v17, v24, v38, v37, v47);
            if ( v12 < 0 )
              goto LABEL_48;
            goto LABEL_47;
          }
          v31 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          {
            v32 = 18;
            goto LABEL_24;
          }
        }
        else
        {
          v31 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          {
            v32 = 17;
LABEL_24:
            WPP_SF_S(v31[2], v32, &WPP_bbf747101dc030c08db8ff9d4150e8cf_Traceguids, *v18);
          }
        }
        v33 = *v22;
        v34 = -1;
        do
          ++v34;
        while ( v33[v34] );
        v35 = v34 + 16;
        v36 = (unsigned __int16 **)((char *)v17 + 88);
        v12 = _AllocArray<unsigned short,CTCoAllocPolicy>(v33, 1, v34 + 16, (char *)v17 + 88);
        if ( v12 >= 0 && StringCchCopyW(*v36, v35, *v22) >= 0 )
          StringCchCatW(*v36, v35, L"DatabaseCorrupt");
        goto LABEL_30;
      }
    }
    else
    {
      v44 = 0;
    }
    v12 = -2147024882;
    CDbOperationManager::UninitializeGlobalContextState();
    goto LABEL_49;
  }
LABEL_50:
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_sSD(*((_QWORD *)WPP_GLOBAL_Control + 2), v11, v13, v14, (__int64)v10, v12);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x1800e93ec  push    rbx
0x1800e93ee  push    rbp
0x1800e93ef  push    rsi
0x1800e93f0  push    rdi
0x1800e93f1  push    r12
0x1800e93f3  push    r13
0x1800e93f5  push    r14
0x1800e93f7  push    r15
0x1800e93f9  sub     rsp, 288h
0x1800e9400  mov     rax, cs:__security_cookie
0x1800e9407  xor     rax, rsp
0x1800e940a  mov     [rsp+2C8h+var_58], rax
0x1800e9412  mov     r12, [rsp+2C8h+arg_30]
0x1800e941a  mov     esi, r9d
0x1800e941d  mov     rdi, [rsp+2C8h+arg_38]
0x1800e9425  mov     r15, rdx
0x1800e9428  mov     rbp, [rsp+2C8h+Source]
0x1800e9430  mov     r14, rcx
0x1800e9433  mov     [rsp+2C8h+var_270], r12
0x1800e9438  mov     [rsp+2C8h+var_280], rdi
0x1800e943d  mov     [rsp+2C8h+var_294], r9d
0x1800e9442  mov     [rsp+2C8h+var_298], r8d
0x1800e9447  mov     [rsp+2C8h+lpszFileName], rdx
0x1800e944c  mov     [rsp+2C8h+var_290], rcx
0x1800e9451  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e9458  lea     rax, WPP_GLOBAL_Control
0x1800e945f  cmp     rcx, rax
0x1800e9462  jz      short loc_1800E948B
0x1800e9464  test    byte ptr [rcx+1Ch], 4
0x1800e9468  jz      short loc_1800E948B
0x1800e946a  mov     rcx, [rcx+10h]
0x1800e946e  lea     r9, aCdboperationma_4; "CDbOperationManager::CreateInstance"
0x1800e9475  mov     edx, 10h
0x1800e947a  mov     [rsp+2C8h+var_2A8], r14
0x1800e947f  lea     r8, WPP_bbf747101dc030c08db8ff9d4150e8cf_Traceguids
0x1800e9486  call    WPP_SF_sS
0x1800e948b  call    ?InitializeGlobalContextState@CDbOperationManager@@CAJXZ; CDbOperationManager::InitializeGlobalContextState(void)
0x1800e9490  xor     r13d, r13d
0x1800e9493  mov     ebx, eax
0x1800e9495  test    eax, eax
0x1800e9497  js      loc_1800E9767
0x1800e949d  mov     [rdi], r13
0x1800e94a0  lea     rdx, byte_180166367; struct std::nothrow_t *
0x1800e94a7  mov     ecx, 0D0h; unsigned __int64
0x1800e94ac  mov     [r12], r13d
0x1800e94b0  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800e94b5  test    rax, rax
0x1800e94b8  jz      loc_1800E97F2
0x1800e94be  mov     rcx, rax; this
0x1800e94c1  call    ??0CDbOperationManager@@QEAA@XZ; CDbOperationManager::CDbOperationManager(void)
0x1800e94c6  mov     [rsp+2C8h+var_288], rax
0x1800e94cb  mov     rdi, rax
0x1800e94ce  test    rax, rax
0x1800e94d1  jz      loc_1800E97F7
0x1800e94d7  mov     ecx, [rsp+2C8h+arg_20]
0x1800e94de  lea     r12, [rax+48h]
0x1800e94e2  mov     [rax+68h], esi
0x1800e94e5  mov     rdx, r12; ppwsz
0x1800e94e8  mov     [rax+6Ch], ecx
0x1800e94eb  mov     rcx, r14; psz
0x1800e94ee  call    cs:__imp_SHStrDupW
0x1800e94f4  mov     ebx, eax
0x1800e94f6  test    eax, eax
0x1800e94f8  js      loc_1800E975D
0x1800e94fe  lea     r13, [rdi+50h]
0x1800e9502  mov     rcx, r15; psz
0x1800e9505  mov     rdx, r13; ppwsz
0x1800e9508  call    cs:__imp_SHStrDupW
0x1800e950e  xor     r9d, r9d
0x1800e9511  mov     ebx, eax
0x1800e9513  test    eax, eax
0x1800e9515  js      loc_1800E975D
0x1800e951b  lea     r15d, [r9+1]
0x1800e951f  test    rbp, rbp
0x1800e9522  jz      short loc_1800E9576
0x1800e9524  mov     esi, r9d
0x1800e9527  mov     edx, r9d
0x1800e952a  mov     r8, rbp
0x1800e952d  movzx   ecx, word ptr [r8]
0x1800e9531  add     rsi, r15
0x1800e9534  inc     rdx
0x1800e9537  lea     r8, [r8+2]
0x1800e953b  test    cx, cx
0x1800e953e  cmovnz  rdx, r9
0x1800e9542  cmp     rdx, 2
0x1800e9546  jnz     short loc_1800E952D
0x1800e9548  add     rsi, rsi
0x1800e954b  lea     r9, [rdi+60h]
0x1800e954f  mov     r8, rsi
0x1800e9552  mov     edx, r15d
0x1800e9555  call    ??$_AllocArray@GVCTCoAllocPolicy@@@@YAJPEAXK_KPEAPEAG@Z; _AllocArray<ushort,CTCoAllocPolicy>(void *,ulong,unsigned __int64,ushort * *)
0x1800e955a  mov     ebx, eax
0x1800e955c  test    eax, eax
0x1800e955e  js      loc_1800E975D
0x1800e9564  mov     rcx, [rdi+60h]; Destination
0x1800e9568  mov     r9, rsi; SourceSize
0x1800e956b  mov     r8, rbp; Source
0x1800e956e  mov     rdx, rsi; DestinationSize
0x1800e9571  call    memcpy_s
0x1800e9576  lea     rcx, [rdi+70h]; TokenHandle
0x1800e957a  call    ?OpenThreadTokenForImpersonation@CMetaStoreUtils@@SAJPEAPEAX@Z; CMetaStoreUtils::OpenThreadTokenForImpersonation(void * *)
0x1800e957f  xor     ebp, ebp
0x1800e9581  mov     ebx, eax
0x1800e9583  test    eax, eax
0x1800e9585  js      short loc_1800E95A5
0x1800e9587  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e958e  lea     rax, WPP_GLOBAL_Control
0x1800e9595  cmp     rcx, rax
0x1800e9598  jz      short loc_1800E95E2
0x1800e959a  test    byte ptr [rcx+1Ch], 4
0x1800e959e  jz      short loc_1800E95E2
0x1800e95a0  lea     edx, [rbp+11h]
0x1800e95a3  jmp     short loc_1800E95CE
0x1800e95a5  cmp     eax, 800703F0h
0x1800e95aa  jnz     loc_1800E96C9
0x1800e95b0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e95b7  lea     rax, WPP_GLOBAL_Control
0x1800e95be  cmp     rcx, rax
0x1800e95c1  jz      short loc_1800E95E2
0x1800e95c3  test    byte ptr [rcx+1Ch], 4
0x1800e95c7  jz      short loc_1800E95E2
0x1800e95c9  mov     edx, 12h
0x1800e95ce  mov     r9, [r12]
0x1800e95d2  lea     r8, WPP_bbf747101dc030c08db8ff9d4150e8cf_Traceguids
0x1800e95d9  mov     rcx, [rcx+10h]
0x1800e95dd  call    WPP_SF_S
0x1800e95e2  mov     rcx, [r13+0]
0x1800e95e6  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800e95ea  inc     rax
0x1800e95ed  cmp     [rcx+rax*2], bp
0x1800e95f1  jnz     short loc_1800E95EA
0x1800e95f3  lea     rsi, [rax+10h]
0x1800e95f7  mov     edx, r15d
0x1800e95fa  lea     r14, [rdi+58h]
0x1800e95fe  mov     r8, rsi
0x1800e9601  mov     r9, r14
0x1800e9604  call    ??$_AllocArray@GVCTCoAllocPolicy@@@@YAJPEAXK_KPEAPEAG@Z; _AllocArray<ushort,CTCoAllocPolicy>(void *,ulong,unsigned __int64,ushort * *)
0x1800e9609  mov     ebx, eax
0x1800e960b  test    eax, eax
0x1800e960d  js      short loc_1800E9634
0x1800e960f  mov     r8, [r13+0]; unsigned __int16 *
0x1800e9613  mov     rdx, rsi; unsigned __int64
0x1800e9616  mov     rcx, [r14]; unsigned __int16 *
0x1800e9619  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800e961e  test    eax, eax
0x1800e9620  js      short loc_1800E9634
0x1800e9622  mov     rcx, [r14]; unsigned __int16 *
0x1800e9625  lea     r8, aDatabasecorrup; "DatabaseCorrupt"
0x1800e962c  mov     rdx, rsi; unsigned __int64
0x1800e962f  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800e9634  lea     rsi, WPP_GLOBAL_Control
0x1800e963b  mov     eax, [rsp+2C8h+var_294]
0x1800e963f  mov     ecx, [rsp+2C8h+var_298]
0x1800e9643  test    eax, eax
0x1800e9645  jz      loc_1800E97B8
0x1800e964b  cmp     ecx, 2
0x1800e964e  jz      loc_1800E97B8
0x1800e9654  test    ebx, ebx
0x1800e9656  js      loc_1800E9758
0x1800e965c  mov     rcx, [rsp+2C8h+lpszFileName]; lpszFileName
0x1800e9661  lea     rdx, [rsp+2C8h+szVolumePathName]; lpszVolumePathName
0x1800e9666  mov     r8d, 104h; cchBufferLength
0x1800e966c  call    cs:__imp_GetVolumePathNameW
0x1800e9672  test    eax, eax
0x1800e9674  jnz     short loc_1800E96BC
0x1800e9676  call    cs:__imp_GetLastError
0x1800e967c  lea     ecx, [rax-2]
0x1800e967f  cmp     ecx, r15d
0x1800e9682  jbe     loc_1800E970C
0x1800e9688  cmp     eax, 7Bh ; '{'
0x1800e968b  jz      short loc_1800E970C
0x1800e968d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e9694  cmp     rcx, rsi
0x1800e9697  jz      short loc_1800E96BC
0x1800e9699  test    byte ptr [rcx+1Ch], 2
0x1800e969d  jz      short loc_1800E96BC
0x1800e969f  mov     r9, [r12]
0x1800e96a3  lea     r8, WPP_bbf747101dc030c08db8ff9d4150e8cf_Traceguids
0x1800e96aa  mov     rcx, [rcx+10h]
0x1800e96ae  mov     edx, 15h
0x1800e96b3  mov     dword ptr [rsp+2C8h+var_2A8], eax
0x1800e96b7  call    WPP_SF_Sd
0x1800e96bc  mov     eax, [rsp+2C8h+var_294]
0x1800e96c0  mov     ecx, [rsp+2C8h+var_298]
0x1800e96c4  jmp     loc_1800E97C8
0x1800e96c9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e96d0  lea     rsi, WPP_GLOBAL_Control
0x1800e96d7  cmp     rcx, rsi
0x1800e96da  jz      loc_1800E963B
0x1800e96e0  test    [rcx+1Ch], r15b
0x1800e96e4  jz      loc_1800E963B
0x1800e96ea  mov     r9, [r12]
0x1800e96ee  lea     r8, WPP_bbf747101dc030c08db8ff9d4150e8cf_Traceguids
0x1800e96f5  mov     rcx, [rcx+10h]
0x1800e96f9  mov     edx, 13h
0x1800e96fe  mov     dword ptr [rsp+2C8h+var_2A8], eax
0x1800e9702  call    WPP_SF_Sd
0x1800e9707  jmp     loc_1800E963B
0x1800e970c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e9713  cmp     rcx, rsi
0x1800e9716  jz      short loc_1800E973B
0x1800e9718  test    byte ptr [rcx+1Ch], 4
0x1800e971c  jz      short loc_1800E973B
0x1800e971e  mov     r9, [r12]
0x1800e9722  lea     r8, WPP_bbf747101dc030c08db8ff9d4150e8cf_Traceguids
0x1800e9729  mov     rcx, [rcx+10h]
0x1800e972d  mov     edx, 14h
0x1800e9732  mov     dword ptr [rsp+2C8h+var_2A8], eax
0x1800e9736  call    WPP_SF_Sd
0x1800e973b  mov     ecx, 0FFFFFC01h; int
0x1800e9740  mov     [rdi+2Ch], ebp
0x1800e9743  call    ?ResultFromJetError@@YAJJ@Z; ResultFromJetError(long)
0x1800e9748  mov     [rdi+34h], eax
0x1800e974b  mov     rax, [rsp+2C8h+var_280]
0x1800e9750  mov     [rsp+2C8h+var_288], rbp
0x1800e9755  mov     [rax], rdi
0x1800e9758  mov     r14, [rsp+2C8h+var_290]
0x1800e975d  lea     rcx, [rsp+2C8h+var_288]
0x1800e9762  call    ?Release@?$CTSmartObj@PEAVCDbOperationManager@@V?$CTSmartPtr_PolicyComplete@VCTContainer_PolicyNewMem@@@@@@QEAAXXZ; CTSmartObj<CDbOperationManager *,CTSmartPtr_PolicyComplete<CTContainer_PolicyNewMem>>::Release(void)
0x1800e9767  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e976e  lea     rax, WPP_GLOBAL_Control
0x1800e9775  cmp     rcx, rax
0x1800e9778  jz      short loc_1800E9792
0x1800e977a  test    byte ptr [rcx+1Ch], 4
0x1800e977e  jz      short loc_1800E9792
0x1800e9780  mov     rcx, [rcx+10h]
0x1800e9784  mov     [rsp+2C8h+var_2A0], ebx
0x1800e9788  mov     [rsp+2C8h+var_2A8], r14
0x1800e978d  call    WPP_SF_sSD
0x1800e9792  mov     eax, ebx
0x1800e9794  mov     rcx, [rsp+2C8h+var_58]
0x1800e979c  xor     rcx, rsp; StackCookie
0x1800e979f  call    __security_check_cookie
0x1800e97a4  add     rsp, 288h
0x1800e97ab  pop     r15
0x1800e97ad  pop     r14
0x1800e97af  pop     r13
0x1800e97b1  pop     r12
0x1800e97b3  pop     rdi
0x1800e97b4  pop     rsi
0x1800e97b5  pop     rbp
0x1800e97b6  pop     rbx
0x1800e97b7  retn
0x1800e97b8  test    ebx, ebx
0x1800e97ba  js      short loc_1800E9758
0x1800e97bc  test    eax, eax
0x1800e97be  jz      short loc_1800E97C5
0x1800e97c0  cmp     ecx, 2
0x1800e97c3  jnz     short loc_1800E97C8
0x1800e97c5  mov     r15d, ebp
0x1800e97c8  mov     rdx, [rsp+2C8h+var_270]
0x1800e97cd  mov     r8d, ecx; unsigned int
0x1800e97d0  mov     [rsp+2C8h+var_2A8], rdx; int *
0x1800e97d5  mov     r9d, eax; int
0x1800e97d8  mov     edx, r15d; int
0x1800e97db  mov     rcx, rdi; this
0x1800e97de  call    ?InitializeDB@CDbOperationManager@@AEAAJHKHPEAH@Z; CDbOperationManager::InitializeDB(int,ulong,int,int *)
0x1800e97e3  mov     ebx, eax
0x1800e97e5  test    eax, eax
0x1800e97e7  js      loc_1800E9758
0x1800e97ed  jmp     loc_1800E974B
0x1800e97f2  mov     [rsp+2C8h+var_288], r13
0x1800e97f7  mov     ebx, 8007000Eh
0x1800e97fc  call    ?UninitializeGlobalContextState@CDbOperationManager@@CAXXZ; CDbOperationManager::UninitializeGlobalContextState(void)
0x1800e9801  jmp     loc_1800E975D
```
