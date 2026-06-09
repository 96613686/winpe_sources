# CBlbRestoreFilesAsync::Initialize(CBlbEngine *,_GUID,ulong,ushort * *,ushort *,uchar,ushort *,uchar,_BLB_OVERWRITE_OPTION,uchar,_BLB_CLIENT_LAUNCH_TYPE)

- ea: `0x140071b24`
- end: `0x140071f15`
- name: `?Initialize@CBlbRestoreFilesAsync@@QEAAJPEAVCBlbEngine@@U_GUID@@KPEAPEAGPEAGE3EW4_BLB_OVERWRITE_OPTION@@EW4_BLB_CLIENT_LAUNCH_TYPE@@@Z`
- size: `1009`
- prototype: `__int64 __fastcall(__int64, struct CBlbEngine *, __int128 *, unsigned int, unsigned __int16 **, unsigned __int16 *, unsigned __int8, unsigned __int16 *, char, int, char, int)`
- caller_count: `1`
- callee_count: `20`
- tags: `reparse_path, service_task, broker_com_uri`

## callers

- `0x140050d50`

## callees

- `0x14000afd0`
- `0x14000b25c`
- `0x14000b294`
- `0x14000bb24`
- `0x14000bb4c`
- `0x140043ec4`
- `0x140071b24`
- `0x140072690`
- `0x140072980`
- `0x140072c18`
- `0x140073068`
- `0x140074230`
- `0x1400889f0`
- `0x140088d0c`
- `0x14008e440`
- `0x1400ef92c`
- `0x140106e60`
- `0x1401130e4`
- `0x140134d20`
- `0x140137010`

## import_xrefs

- `KERNEL32!SystemTimeToFileTime` at `0x140071d7d`
- `KERNEL32!SystemTimeToFileTime` at `0x140071d7d`
- `KERNEL32!GetSystemTime` at `0x140071d69`
- `KERNEL32!GetSystemTime` at `0x140071d69`
- `KERNEL32!GetLastError` at `0x140071d87`
- `KERNEL32!GetLastError` at `0x140071d87`
- `msvcrt!_wcsicmp` at `0x140071df3`
- `msvcrt!_wcsicmp` at `0x140071df3`
- `ole32!CoTaskMemFree` at `0x140071e57`
- `ole32!CoTaskMemFree` at `0x140071e61`
- `ole32!CoTaskMemFree` at `0x140071e6a`
- `ole32!CoTaskMemFree` at `0x140071e74`
- `ole32!CoTaskMemFree` at `0x140071e57`
- `ole32!CoTaskMemFree` at `0x140071e61`
- `ole32!CoTaskMemFree` at `0x140071e6a`
- `ole32!CoTaskMemFree` at `0x140071e74`

## pseudocode

```c
__int64 __fastcall CBlbRestoreFilesAsync::Initialize(
        __int64 a1,
        struct CBlbEngine *a2,
        __int128 *a3,
        unsigned int a4,
        unsigned __int16 **a5,
        unsigned __int16 *a6,
        unsigned __int8 a7,
        unsigned __int16 *a8,
        char a9,
        int a10,
        char a11,
        int a12)
{
  struct IBLBCatalogSystem *Catalog; // rax
  unsigned __int16 *v16; // r14
  wchar_t *v17; // r15
  struct IBLBCatalogSystem *v18; // rsi
  unsigned __int8 v19; // r8
  int TargetMediaType; // ebx
  __int64 v21; // rax
  unsigned __int16 *v22; // rcx
  int v23; // r12d
  unsigned __int16 **v24; // r12
  unsigned __int16 *v25; // r13
  struct CBlbEngine *v26; // rdx
  signed int LastError; // eax
  int v28; // eax
  int v29; // eax
  unsigned __int16 *v32; // [rsp+58h] [rbp-79h] BYREF
  wchar_t *String2; // [rsp+60h] [rbp-71h] BYREF
  unsigned __int16 *v34; // [rsp+68h] [rbp-69h] BYREF
  wchar_t *String1; // [rsp+70h] [rbp-61h] BYREF
  struct CBlbEngine *v36; // [rsp+78h] [rbp-59h]
  LPVOID pv; // [rsp+80h] [rbp-51h] BYREF
  unsigned __int16 **v38; // [rsp+88h] [rbp-49h]
  unsigned __int16 *v39; // [rsp+90h] [rbp-41h]
  __int128 v40; // [rsp+A0h] [rbp-31h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+B0h] [rbp-21h] BYREF

  v38 = a5;
  v32 = a8;
  v36 = a2;
  v39 = a6;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, WPP_9bc2e6579c4134c7eec8e8241f17499a_Traceguids);
  }
  Catalog = CBlbAsync::GetCatalog((CBlbAsync *)(a1 + 16));
  v16 = 0;
  *(_DWORD *)(a1 + 248) = 1;
  v17 = 0;
  v34 = 0;
  String1 = 0;
  String2 = 0;
  pv = 0;
  v18 = Catalog;
  TargetMediaType = CBlbAsync::Initialize((CBlbAsync *)(a1 + 16), a2, v19);
  if ( TargetMediaType >= 0 )
  {
    v21 = *(_QWORD *)v18;
    v40 = *a3;
    TargetMediaType = (*(__int64 (__fastcall **)(struct IBLBCatalogSystem *, __int128 *, __int64, _QWORD))(v21 + 88))(
                        v18,
                        &v40,
                        a1 + 320,
                        0);
    if ( TargetMediaType >= 0 )
    {
      v22 = v32;
      *(_OWORD *)(a1 + 252) = *a3;
      TargetMediaType = BlbutilDuplicateString(v22, (unsigned __int16 **)(a1 + 296), 0);
      if ( TargetMediaType >= 0 )
      {
        LODWORD(v32) = 0;
        TargetMediaType = CBlbImpersonationHelper::CacheClientTokenIfNeeded((CBlbImpersonationHelper *)(a1 + 32));
        if ( TargetMediaType >= 0 )
        {
          TargetMediaType = BlbQueryTargetMediaType(
                              *(unsigned __int16 **)(a1 + 296),
                              (struct CBlbImpersonationHelper *)(a1 + 32),
                              (enum _BLB_MEDIA_TYPE *)&v32);
          if ( TargetMediaType < 0 )
          {
            CBlbImpersonationHelper::DiscardCachedCOMClientToken((CBlbImpersonationHelper *)(a1 + 32));
            goto LABEL_27;
          }
          v23 = (int)v32;
          if ( (_DWORD)v32 == 4 )
          {
            TargetMediaType = CBlbAsync::CheckValidNetworkShareAndStoreImpersonationToken(
                                (CBlbAsync *)(a1 + 16),
                                *(unsigned __int16 **)(a1 + 296),
                                0);
            if ( TargetMediaType < 0 )
              goto LABEL_27;
          }
          else
          {
            CBlbImpersonationHelper::DiscardCachedCOMClientToken((CBlbImpersonationHelper *)(a1 + 32));
          }
          *(_DWORD *)(a1 + 304) = v23;
          v24 = v38;
          TargetMediaType = CBlbRestoreFilesAsync::InitializeSourceVolumeInfo((CBlbRestoreFilesAsync *)a1, a4, v38);
          if ( TargetMediaType >= 0 )
          {
            TargetMediaType = CBlbRestoreFilesAsync::InitializeMountPath((CBlbRestoreFilesAsync *)a1, v36);
            if ( TargetMediaType >= 0 )
            {
              v25 = v39;
              TargetMediaType = CBlbRestoreFilesAsync::InitializeRestoreFilesContext(
                                  (CBlbRestoreFilesAsync *)a1,
                                  a4,
                                  v24,
                                  v39,
                                  a7);
              if ( TargetMediaType >= 0 )
              {
                TargetMediaType = CBlbRestoreFilesAsync::InitializeTargetPath((CBlbRestoreFilesAsync *)a1, v26, v25);
                if ( TargetMediaType >= 0 )
                {
                  *(_DWORD *)(a1 + 312) = a10;
                  *(_BYTE *)(a1 + 316) = a9;
                  *(_BYTE *)(a1 + 317) = a11;
                  *(_BYTE *)(a1 + 308) = a7;
                  SystemTime = 0;
                  GetSystemTime(&SystemTime);
                  if ( SystemTimeToFileTime(&SystemTime, (LPFILETIME)(a1 + 536)) )
                  {
                    v28 = BlbutilSplitFilePath(*v24, &v34, (unsigned __int16 **)&pv);
                    v16 = v34;
                    TargetMediaType = v28;
                    if ( v28 >= 0 )
                    {
                      TargetMediaType = BlbutilSlashTerminatePath(v34, (LPVOID *)&String1);
                      if ( TargetMediaType >= 0 )
                      {
                        v29 = BlbutilSlashTerminatePath(v25, (LPVOID *)&String2);
                        v17 = String2;
                        TargetMediaType = v29;
                        if ( v29 >= 0 )
                        {
                          if ( _wcsicmp(String1, String2) )
                            *(_BYTE *)(a1 + 628) = 1;
                          TargetMediaType = InitializeRecoverySqmDatapoint(
                                              a1 + 568,
                                              v36,
                                              0,
                                              *(unsigned int *)(a1 + 304),
                                              a12,
                                              *(_QWORD *)(a1 + 296),
                                              *(_QWORD *)(a1 + 420),
                                              *(_QWORD *)(a1 + 536),
                                              *(_BYTE *)(a1 + 628));
                        }
                      }
                    }
                  }
                  else
                  {
                    LastError = GetLastError();
                    TargetMediaType = LastError;
                    if ( LastError > 0 )
                      TargetMediaType = (unsigned __int16)LastError | 0x80070000;
                  }
                }
              }
            }
          }
        }
      }
    }
  }
LABEL_27:
  CoTaskMemFree(v17);
  CoTaskMemFree(String1);
  CoTaskMemFree(v16);
  CoTaskMemFree(pv);
  if ( TargetMediaType < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 35, WPP_9bc2e6579c4134c7eec8e8241f17499a_Traceguids);
    }
    CBlbRestoreFilesAsync::Uninitialize((CBlbRestoreFilesAsync *)a1);
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, WPP_9bc2e6579c4134c7eec8e8241f17499a_Traceguids);
  }
  return (unsigned int)TargetMediaType;
}

```

## disassembly

```asm
0x140071b24  push    rbp
0x140071b26  push    rbx
0x140071b27  push    rsi
0x140071b28  push    rdi
0x140071b29  push    r12
0x140071b2b  push    r13
0x140071b2d  push    r14
0x140071b2f  push    r15
0x140071b31  lea     rbp, [rsp-7]
0x140071b36  sub     rsp, 0D8h
0x140071b3d  mov     rax, cs:__security_cookie
0x140071b44  xor     rax, rsp
0x140071b47  mov     [rbp+3Fh+var_50], rax
0x140071b4b  mov     rax, [rbp+3Fh+arg_20]
0x140071b4f  mov     rdi, rcx
0x140071b52  mov     rcx, [rbp+3Fh+arg_28]
0x140071b56  mov     r12, r8
0x140071b59  mov     [rbp+3Fh+var_88], rax
0x140071b5d  mov     rbx, rdx
0x140071b60  mov     rax, [rbp+3Fh+arg_38]
0x140071b67  mov     [rbp+3Fh+var_B8], rax
0x140071b6b  mov     [rsp+110h+var_C0], r9d
0x140071b70  mov     [rbp+3Fh+var_98], rdx
0x140071b74  mov     [rbp+3Fh+var_80], rcx
0x140071b78  mov     rcx, cs:WPP_GLOBAL_Control
0x140071b7f  lea     rax, WPP_GLOBAL_Control
0x140071b86  cmp     rcx, rax
0x140071b89  jz      short loc_140071BAC
0x140071b8b  test    byte ptr [rcx+1Ch], 1
0x140071b8f  jz      short loc_140071BAC
0x140071b91  cmp     byte ptr [rcx+19h], 4
0x140071b95  jb      short loc_140071BAC
0x140071b97  mov     rcx, [rcx+10h]
0x140071b9b  lea     r8, WPP_9bc2e6579c4134c7eec8e8241f17499a_Traceguids
0x140071ba2  mov     edx, 22h ; '"'
0x140071ba7  call    WPP_SF_
0x140071bac  lea     r13, [rdi+10h]
0x140071bb0  mov     rcx, r13; this
0x140071bb3  call    ?GetCatalog@CBlbAsync@@QEAAPEAUIBLBCatalogSystem@@XZ; CBlbAsync::GetCatalog(void)
0x140071bb8  xor     r14d, r14d
0x140071bbb  mov     dword ptr [rdi+0F8h], 1
0x140071bc5  xor     r15d, r15d
0x140071bc8  mov     [rbp+3Fh+var_A8], r14
0x140071bcc  mov     rdx, rbx; struct CBlbEngine *
0x140071bcf  mov     [rbp+3Fh+String1], r14
0x140071bd3  mov     rcx, r13; this
0x140071bd6  mov     [rbp+3Fh+String2], r15
0x140071bda  mov     [rbp+3Fh+pv], r14
0x140071bde  mov     rsi, rax
0x140071be1  call    ?Initialize@CBlbAsync@@QEAAJPEAVCBlbEngine@@E@Z; CBlbAsync::Initialize(CBlbEngine *,uchar)
0x140071be6  mov     ebx, eax
0x140071be8  test    eax, eax
0x140071bea  js      loc_140071E54
0x140071bf0  mov     rax, [rsi]
0x140071bf3  lea     r8, [rdi+140h]
0x140071bfa  movaps  xmm0, xmmword ptr [r12]
0x140071bff  lea     rdx, [rbp+3Fh+var_70]
0x140071c03  xor     r9d, r9d
0x140071c06  movdqa  [rbp+3Fh+var_70], xmm0
0x140071c0b  mov     rcx, rsi
0x140071c0e  mov     rax, [rax+58h]
0x140071c12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140071c17  mov     ebx, eax
0x140071c19  test    eax, eax
0x140071c1b  js      loc_140071E54
0x140071c21  movaps  xmm0, xmmword ptr [r12]
0x140071c26  xor     r8d, r8d; unsigned __int64
0x140071c29  mov     rcx, [rbp+3Fh+var_B8]; unsigned __int16 *
0x140071c2d  lea     r12, [rdi+128h]
0x140071c34  mov     rdx, r12; unsigned __int16 **
0x140071c37  movdqu  xmmword ptr [rdi+0FCh], xmm0
0x140071c3f  call    ?BlbutilDuplicateString@@YAJPEBGPEAPEAG_K@Z; BlbutilDuplicateString(ushort const *,ushort * *,unsigned __int64)
0x140071c44  mov     ebx, eax
0x140071c46  test    eax, eax
0x140071c48  js      loc_140071E54
0x140071c4e  lea     rsi, [rdi+20h]
0x140071c52  mov     dword ptr [rbp+3Fh+var_B8], r14d
0x140071c56  mov     rcx, rsi; this
0x140071c59  call    ?CacheClientTokenIfNeeded@CBlbImpersonationHelper@@QEAAJXZ; CBlbImpersonationHelper::CacheClientTokenIfNeeded(void)
0x140071c5e  mov     ebx, eax
0x140071c60  test    eax, eax
0x140071c62  js      loc_140071E54
0x140071c68  mov     rcx, [r12]; unsigned __int16 *
0x140071c6c  lea     r8, [rbp+3Fh+var_B8]; enum _BLB_MEDIA_TYPE *
0x140071c70  mov     rdx, rsi; this
0x140071c73  call    ?BlbQueryTargetMediaType@@YAJPEAGPEAVCBlbImpersonationHelper@@PEAW4_BLB_MEDIA_TYPE@@@Z; BlbQueryTargetMediaType(ushort *,CBlbImpersonationHelper *,_BLB_MEDIA_TYPE *)
0x140071c78  mov     ebx, eax
0x140071c7a  test    eax, eax
0x140071c7c  jns     short loc_140071C8B
0x140071c7e  mov     rcx, rsi; this
0x140071c81  call    ?DiscardCachedCOMClientToken@CBlbImpersonationHelper@@QEAAXXZ; CBlbImpersonationHelper::DiscardCachedCOMClientToken(void)
0x140071c86  jmp     loc_140071E54
0x140071c8b  mov     r12d, dword ptr [rbp+3Fh+var_B8]
0x140071c8f  cmp     r12d, 4
0x140071c93  jz      short loc_140071C9F
0x140071c95  mov     rcx, rsi; this
0x140071c98  call    ?DiscardCachedCOMClientToken@CBlbImpersonationHelper@@QEAAXXZ; CBlbImpersonationHelper::DiscardCachedCOMClientToken(void)
0x140071c9d  jmp     short loc_140071CBB
0x140071c9f  mov     rdx, [rdi+128h]; unsigned __int16 *
0x140071ca6  xor     r8d, r8d; unsigned __int8
0x140071ca9  mov     rcx, r13; this
0x140071cac  call    ?CheckValidNetworkShareAndStoreImpersonationToken@CBlbAsync@@QEAAJPEAGE@Z; CBlbAsync::CheckValidNetworkShareAndStoreImpersonationToken(ushort *,uchar)
0x140071cb1  mov     ebx, eax
0x140071cb3  test    eax, eax
0x140071cb5  js      loc_140071E54
0x140071cbb  mov     edx, [rsp+110h+var_C0]; unsigned int
0x140071cbf  mov     rcx, rdi; this
0x140071cc2  mov     [rdi+130h], r12d
0x140071cc9  mov     r12, [rbp+3Fh+var_88]
0x140071ccd  mov     r8, r12; unsigned __int16 **
0x140071cd0  call    ?InitializeSourceVolumeInfo@CBlbRestoreFilesAsync@@AEAAJKPEAPEAG@Z; CBlbRestoreFilesAsync::InitializeSourceVolumeInfo(ulong,ushort * *)
0x140071cd5  mov     ebx, eax
0x140071cd7  test    eax, eax
0x140071cd9  js      loc_140071E54
0x140071cdf  mov     rdx, [rbp+3Fh+var_98]; struct CBlbEngine *
0x140071ce3  mov     rcx, rdi; this
0x140071ce6  call    ?InitializeMountPath@CBlbRestoreFilesAsync@@AEAAJPEAVCBlbEngine@@@Z; CBlbRestoreFilesAsync::InitializeMountPath(CBlbEngine *)
0x140071ceb  mov     ebx, eax
0x140071ced  test    eax, eax
0x140071cef  js      loc_140071E54
0x140071cf5  mov     r13, [rbp+3Fh+var_80]
0x140071cf9  mov     r8, r12; unsigned __int16 **
0x140071cfc  mov     sil, [rbp+3Fh+arg_30]
0x140071d00  mov     r9, r13; unsigned __int16 *
0x140071d03  mov     edx, [rsp+110h+var_C0]; unsigned int
0x140071d07  mov     rcx, rdi; this
0x140071d0a  mov     [rsp+110h+var_F0], sil; unsigned __int8
0x140071d0f  call    ?InitializeRestoreFilesContext@CBlbRestoreFilesAsync@@AEAAJKPEAPEAGPEAGE@Z; CBlbRestoreFilesAsync::InitializeRestoreFilesContext(ulong,ushort * *,ushort *,uchar)
0x140071d14  mov     ebx, eax
0x140071d16  test    eax, eax
0x140071d18  js      loc_140071E54
0x140071d1e  mov     r8, r13; unsigned __int16 *
0x140071d21  mov     rcx, rdi; this
0x140071d24  call    ?InitializeTargetPath@CBlbRestoreFilesAsync@@AEAAJPEAVCBlbEngine@@PEAG@Z; CBlbRestoreFilesAsync::InitializeTargetPath(CBlbEngine *,ushort *)
0x140071d29  mov     ebx, eax
0x140071d2b  test    eax, eax
0x140071d2d  js      loc_140071E54
0x140071d33  mov     eax, [rbp+3Fh+arg_48]
0x140071d39  lea     rcx, [rbp+3Fh+SystemTime]; lpSystemTime
0x140071d3d  mov     [rdi+138h], eax
0x140071d43  xorps   xmm0, xmm0
0x140071d46  mov     al, [rbp+3Fh+arg_40]
0x140071d4c  mov     [rdi+13Ch], al
0x140071d52  mov     al, [rbp+3Fh+arg_50]
0x140071d58  mov     [rdi+13Dh], al
0x140071d5e  mov     [rdi+134h], sil
0x140071d65  movups  xmmword ptr [rbp+3Fh+SystemTime.wYear], xmm0
0x140071d69  call    cs:__imp_GetSystemTime
0x140071d6f  lea     rsi, [rdi+218h]
0x140071d76  mov     rdx, rsi; lpFileTime
0x140071d79  lea     rcx, [rbp+3Fh+SystemTime]; lpSystemTime
0x140071d7d  call    cs:__imp_SystemTimeToFileTime
0x140071d83  test    eax, eax
0x140071d85  jnz     short loc_140071DA5
0x140071d87  call    cs:__imp_GetLastError
0x140071d8d  mov     ebx, eax
0x140071d8f  test    eax, eax
0x140071d91  jle     loc_140071E54
0x140071d97  movzx   ebx, ax
0x140071d9a  or      ebx, 80070000h
0x140071da0  jmp     loc_140071E54
0x140071da5  mov     rcx, [r12]; unsigned __int16 *
0x140071da9  lea     r8, [rbp+3Fh+pv]; unsigned __int16 **
0x140071dad  lea     rdx, [rbp+3Fh+var_A8]; unsigned __int16 **
0x140071db1  call    ?BlbutilSplitFilePath@@YAJPEAGPEAPEAG1@Z; BlbutilSplitFilePath(ushort *,ushort * *,ushort * *)
0x140071db6  mov     r14, [rbp+3Fh+var_A8]
0x140071dba  mov     ebx, eax
0x140071dbc  test    eax, eax
0x140071dbe  js      loc_140071E54
0x140071dc4  lea     rdx, [rbp+3Fh+String1]; unsigned __int16 **
0x140071dc8  mov     rcx, r14; unsigned __int16 *
0x140071dcb  call    ?BlbutilSlashTerminatePath@@YAJPEAGPEAPEAG@Z; BlbutilSlashTerminatePath(ushort *,ushort * *)
0x140071dd0  mov     ebx, eax
0x140071dd2  test    eax, eax
0x140071dd4  js      short loc_140071E54
0x140071dd6  lea     rdx, [rbp+3Fh+String2]; unsigned __int16 **
0x140071dda  mov     rcx, r13; unsigned __int16 *
0x140071ddd  call    ?BlbutilSlashTerminatePath@@YAJPEAGPEAPEAG@Z; BlbutilSlashTerminatePath(ushort *,ushort * *)
0x140071de2  mov     r15, [rbp+3Fh+String2]
0x140071de6  mov     ebx, eax
0x140071de8  test    eax, eax
0x140071dea  js      short loc_140071E54
0x140071dec  mov     rcx, [rbp+3Fh+String1]; String1
0x140071df0  mov     rdx, r15; String2
0x140071df3  call    cs:__imp__wcsicmp
0x140071df9  test    eax, eax
0x140071dfb  jz      short loc_140071E04
0x140071dfd  mov     byte ptr [rdi+274h], 1
0x140071e04  mov     al, [rdi+274h]
0x140071e0a  lea     rcx, [rdi+238h]
0x140071e11  mov     r9d, [rdi+130h]
0x140071e18  xor     r8d, r8d
0x140071e1b  mov     rdx, [rbp+3Fh+var_98]
0x140071e1f  mov     [rsp+110h+var_D0], al
0x140071e23  mov     rax, [rsi]
0x140071e26  mov     [rsp+110h+var_D8], rax
0x140071e2b  mov     rax, [rdi+1A4h]
0x140071e32  mov     [rsp+110h+var_E0], rax
0x140071e37  mov     rax, [rdi+128h]
0x140071e3e  mov     [rsp+110h+var_E8], rax
0x140071e43  mov     eax, [rbp+3Fh+arg_58]
0x140071e49  mov     dword ptr [rsp+110h+var_F0], eax
0x140071e4d  call    ?InitializeRecoverySqmDatapoint@@YAJPEAU_BLB_RECOVERY_SQM_DATAPOINT_INFO@@PEAVCBlbEngine@@W4_BLB_SQM_RECOVERY_ITEM_TYPE@@W4_BLB_MEDIA_TYPE@@W4_BLB_CLIENT_LAUNCH_TYPE@@PEAGU_FILETIME@@6E@Z; InitializeRecoverySqmDatapoint(_BLB_RECOVERY_SQM_DATAPOINT_INFO *,CBlbEngine *,_BLB_SQM_RECOVERY_ITEM_TYPE,_BLB_MEDIA_TYPE,_BLB_CLIENT_LAUNCH_TYPE,ushort *,_FILETIME,_FILETIME,uchar)
0x140071e52  mov     ebx, eax
0x140071e54  mov     rcx, r15; pv
0x140071e57  call    cs:__imp_CoTaskMemFree
0x140071e5d  mov     rcx, [rbp+3Fh+String1]; pv
0x140071e61  call    cs:__imp_CoTaskMemFree
0x140071e67  mov     rcx, r14; pv
0x140071e6a  call    cs:__imp_CoTaskMemFree
0x140071e70  mov     rcx, [rbp+3Fh+pv]; pv
0x140071e74  call    cs:__imp_CoTaskMemFree
0x140071e7a  test    ebx, ebx
0x140071e7c  jns     short loc_140071EBF
0x140071e7e  mov     rcx, cs:WPP_GLOBAL_Control
0x140071e85  lea     rsi, WPP_GLOBAL_Control
0x140071e8c  cmp     rcx, rsi
0x140071e8f  jz      short loc_140071EB5
0x140071e91  test    byte ptr [rcx+1Ch], 1
0x140071e95  jz      short loc_140071EB5
0x140071e97  cmp     byte ptr [rcx+19h], 2
0x140071e9b  jb      short loc_140071EB5
0x140071e9d  mov     rcx, [rcx+10h]
0x140071ea1  lea     r8, WPP_9bc2e6579c4134c7eec8e8241f17499a_Traceguids
0x140071ea8  mov     edx, 23h ; '#'
0x140071ead  mov     r9d, ebx
0x140071eb0  call    WPP_SF_d
0x140071eb5  mov     rcx, rdi; this
0x140071eb8  call    ?Uninitialize@CBlbRestoreFilesAsync@@QEAAXXZ; CBlbRestoreFilesAsync::Uninitialize(void)
0x140071ebd  jmp     short loc_140071EC6
0x140071ebf  lea     rsi, WPP_GLOBAL_Control
0x140071ec6  mov     rcx, cs:WPP_GLOBAL_Control
0x140071ecd  cmp     rcx, rsi
0x140071ed0  jz      short loc_140071EF3
0x140071ed2  test    byte ptr [rcx+1Ch], 1
0x140071ed6  jz      short loc_140071EF3
0x140071ed8  cmp     byte ptr [rcx+19h], 4
0x140071edc  jb      short loc_140071EF3
0x140071ede  mov     rcx, [rcx+10h]
0x140071ee2  lea     r8, WPP_9bc2e6579c4134c7eec8e8241f17499a_Traceguids
0x140071ee9  mov     edx, 24h ; '$'
0x140071eee  call    WPP_SF_
0x140071ef3  mov     eax, ebx
0x140071ef5  mov     rcx, [rbp+3Fh+var_50]
0x140071ef9  xor     rcx, rsp; StackCookie
0x140071efc  call    __security_check_cookie
0x140071f01  add     rsp, 0D8h
0x140071f08  pop     r15
0x140071f0a  pop     r14
0x140071f0c  pop     r13
0x140071f0e  pop     r12
0x140071f10  pop     rdi
0x140071f11  pop     rsi
0x140071f12  pop     rbx
0x140071f13  pop     rbp
0x140071f14  retn
```
