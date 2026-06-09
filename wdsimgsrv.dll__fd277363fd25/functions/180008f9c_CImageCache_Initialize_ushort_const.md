# CImageCache::Initialize(ushort const *)

- ea: `0x180008f9c`
- end: `0x1800092e6`
- name: `?Initialize@CImageCache@@QEAAKPEBG@Z`
- size: `842`
- prototype: `unsigned int __fastcall(CImageCache *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `13`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180007120`

## callees

- `0x1800026f8`
- `0x180002918`
- `0x180006a58`
- `0x180006e20`
- `0x180008de8`
- `0x180008f9c`
- `0x180009490`
- `0x18000aeac`
- `0x18000d100`
- `0x18000d638`
- `0x180012890`
- `0x180012b5c`
- `0x180012d80`

## import_xrefs

- `WdsCommonLib!?GetValueDwordWithDefault@CRegKey@@QEAAKPEBGKPEAK@Z` at `0x180009271`
- `WdsCommonLib!?GetValueDwordWithDefault@CRegKey@@QEAAKPEBGKPEAK@Z` at `0x180009271`
- `WdsCommonLib!?DuplicateStringW@@YAKPEBGPEAPEAG@Z` at `0x180008fe9`
- `WdsCommonLib!?DuplicateStringW@@YAKPEBGPEAPEAG@Z` at `0x180008fe9`

## string_xrefs

- `0x180008ff5`: `base\eco\wds\wdssrv\wdsimgsrv\src\imagecache.cpp`
- `0x1800091ae`: `AllInstallImages`
- `0x18000922d`: `System\CurrentControlSet\Services\WDSServer\Providers\WdsImgSrv`
- `0x180009263`: `DefaultInstallImagePriority`

## pseudocode

```c
__int64 __fastcall CImageCache::Initialize(CImageCache *this, const unsigned __int16 *a2)
{
  unsigned int appended; // ebx
  __int64 v5; // rdx
  __int64 v6; // rdx
  __int64 v7; // rdx
  __int64 v8; // rdx
  HKEY v9; // rdx
  __int64 v10; // rdx
  __int64 v11; // rdx
  unsigned int i; // edi
  __int64 v13; // rdx
  __int64 v14; // rdx
  __int64 v15; // rdx
  __int64 v16; // rdx
  __int64 v17; // rdx
  int v18; // r8d
  __int64 v19; // rdx
  struct _GUID v21; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD v22[10]; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD v23[10]; // [rsp+B0h] [rbp-50h] BYREF
  _QWORD v24[10]; // [rsp+100h] [rbp+0h] BYREF
  struct _GUID v25; // [rsp+150h] [rbp+50h] BYREF
  _BYTE v26[32]; // [rsp+160h] [rbp+60h] BYREF
  int v27; // [rsp+1B0h] [rbp+B0h] BYREF
  HKEY phkResult; // [rsp+1C0h] [rbp+C0h] BYREF

  phkResult = 0;
  v27 = 0;
  CAutoWriterLock::CAutoWriterLock((CAutoWriterLock *)v26, this);
  appended = DuplicateStringW(a2, (unsigned __int16 **)this + 15);
  if ( !(unsigned int)ElValidateWin32_0(appended, v5, "base\\eco\\wds\\wdssrv\\wdsimgsrv\\src\\imagecache.cpp", 75) )
  {
    appended = CDirectoryMonitor<CImageCache,&public: unsigned long CImageCache::OnDirectoryChange(void)>::Initialize((char *)this + 176);
    if ( !(unsigned int)ElValidateWin32_0(appended, v6, "base\\eco\\wds\\wdssrv\\wdsimgsrv\\src\\imagecache.cpp", 85) )
    {
      appended = CWdsMetadataStoreManagementClient::Initialize((CImageCache *)((char *)this + 160));
      if ( !(unsigned int)ElValidateWin32_0(appended, v7, "base\\eco\\wds\\wdssrv\\wdsimgsrv\\src\\imagecache.cpp", 91) )
      {
        v21 = (struct _GUID)xmmword_18001CD10;
        appended = CWdsMetadataStoreManagementClient::CheckRegistration((CImageCache *)((char *)this + 160), &v21, &v27);
        if ( !(unsigned int)ElValidateWin32_0(
                              appended,
                              v8,
                              "base\\eco\\wds\\wdssrv\\wdsimgsrv\\src\\imagecache.cpp",
                              95) )
        {
          if ( !v27 )
          {
            v23[0] = 0;
            v23[1] = 0;
            v23[3] = 0;
            v23[4] = 0;
            v23[6] = 0;
            v23[7] = 0;
            v22[0] = 0;
            v22[1] = 0;
            v22[3] = 0;
            v22[4] = 0;
            v22[6] = 0;
            v22[7] = 0;
            v24[0] = 0;
            v24[1] = 0;
            v24[3] = 0;
            v24[4] = 0;
            v24[6] = 0;
            v24[7] = 0;
            appended = CWdsMetadata::AppendExclusionFilter((CWdsMetadata *)v22, L"WDS.Object.Type");
            if ( (unsigned int)ElValidateWin32_0(
                                 appended,
                                 v10,
                                 "base\\eco\\wds\\wdssrv\\wdsimgsrv\\src\\imagecache.cpp",
                                 110) )
              goto LABEL_7;
            appended = CWdsMetadata::AppendExclusionFilter((CWdsMetadata *)v22, L"WDS.Image.Priority");
            if ( (unsigned int)ElValidateWin32_0(
                                 appended,
                                 v11,
                                 "base\\eco\\wds\\wdssrv\\wdsimgsrv\\src\\imagecache.cpp",
                                 113) )
              goto LABEL_7;
            for ( i = 0; i < 0x13; ++i )
            {
              appended = CWdsMetadata::AppendExclusionFilter((CWdsMetadata *)v22, off_180018D10[i]);
              if ( (unsigned int)ElValidateWin32_0(
                                   appended,
                                   v13,
                                   "base\\eco\\wds\\wdssrv\\wdsimgsrv\\src\\imagecache.cpp",
                                   118) )
                goto LABEL_7;
            }
            v21 = 0;
            v25 = (struct _GUID)xmmword_18001CD10;
            appended = CWdsMetadataStoreManagementClient::Register(
                         (CImageCache *)((char *)this + 160),
                         &v25,
                         L"AllInstallImages",
                         0,
                         &v21,
                         (const struct CWdsMetadata *)v23,
                         (const struct CWdsMetadata *)v23,
                         (const struct CWdsMetadata *)v22,
                         (const struct CWdsMetadata *)v24);
            if ( (unsigned int)ElValidateWin32_0(
                                 appended,
                                 v14,
                                 "base\\eco\\wds\\wdssrv\\wdsimgsrv\\src\\imagecache.cpp",
                                 129) )
            {
LABEL_7:
              CWdsMetadata::~CWdsMetadata((CWdsMetadata *)v24);
              CWdsMetadata::~CWdsMetadata((CWdsMetadata *)v22);
              CWdsMetadata::~CWdsMetadata((CWdsMetadata *)v23);
              goto LABEL_18;
            }
            CWdsMetadata::~CWdsMetadata((CWdsMetadata *)v24);
            CWdsMetadata::~CWdsMetadata((CWdsMetadata *)v22);
            CWdsMetadata::~CWdsMetadata((CWdsMetadata *)v23);
          }
          appended = CRegKey::Open(
                       (CRegKey *)&phkResult,
                       v9,
                       L"System\\CurrentControlSet\\Services\\WDSServer\\Providers\\WdsImgSrv");
          if ( !(unsigned int)ElValidateWin32_0(
                                appended,
                                v15,
                                "base\\eco\\wds\\wdssrv\\wdsimgsrv\\src\\imagecache.cpp",
                                143) )
          {
            appended = CRegKey::GetValueDwordWithDefault(
                         (CRegKey *)&phkResult,
                         L"DefaultInstallImagePriority",
                         0x7A120u,
                         (unsigned int *)this + 38);
            if ( !(unsigned int)ElValidateWin32_0(
                                  appended,
                                  v16,
                                  "base\\eco\\wds\\wdssrv\\wdsimgsrv\\src\\imagecache.cpp",
                                  152) )
            {
              appended = CImageCache::OnChange(this, v17, v18);
              ElValidateWin32_0(appended, v19, "base\\eco\\wds\\wdssrv\\wdsimgsrv\\src\\imagecache.cpp", 158);
            }
          }
        }
      }
    }
  }
LABEL_18:
  CAutoWriterLock::Unlock((CAutoWriterLock *)v26);
  CRegKey::Close((CRegKey *)&phkResult);
  return appended;
}

```

## disassembly

```asm
0x180008f9c  mov     rax, rsp
0x180008f9f  mov     [rax+10h], rbx
0x180008fa3  mov     [rax+20h], rsi
0x180008fa7  push    rbp
0x180008fa8  push    rdi
0x180008fa9  push    r12
0x180008fab  push    r14
0x180008fad  push    r15
0x180008faf  lea     rbp, [rsp-80h]
0x180008fb4  sub     rsp, 180h
0x180008fbb  mov     rbx, rdx
0x180008fbe  movaps  xmmword ptr [rax-38h], xmm6
0x180008fc2  mov     rdx, rcx; struct CMRSWLock *
0x180008fc5  mov     rsi, rcx
0x180008fc8  xor     r15d, r15d
0x180008fcb  lea     rcx, [rbp+0A0h+var_40]; this
0x180008fcf  mov     [rbp+0A0h+phkResult], r15
0x180008fd6  mov     [rbp+0A0h+arg_0], r15d
0x180008fdd  call    ??0CAutoWriterLock@@QEAA@PEAVCMRSWLock@@H@Z; CAutoWriterLock::CAutoWriterLock(CMRSWLock *,int)
0x180008fe2  lea     rdx, [rsi+78h]
0x180008fe6  mov     rcx, rbx
0x180008fe9  call    cs:__imp_?DuplicateStringW@@YAKPEBGPEAPEAG@Z; DuplicateStringW(ushort const *,ushort * *)
0x180008ff0  nop     dword ptr [rax+rax+00h]
0x180008ff5  lea     r12, aBaseEcoWdsWdss_0; "base\\eco\\wds\\wdssrv\\wdsimgsrv\\src"...
0x180008ffc  mov     ecx, eax
0x180008ffe  mov     r8, r12
0x180009001  lea     r9d, [r15+4Bh]
0x180009005  mov     ebx, eax
0x180009007  call    ElValidateWin32_0
0x18000900c  test    eax, eax
0x18000900e  jnz     loc_1800092AD
0x180009014  mov     r9, [rsi+78h]
0x180009018  lea     rcx, [rsi+0B0h]; Context
0x18000901f  mov     rdx, rsi
0x180009022  call    ?Initialize@?$CDirectoryMonitor@VCImageCache@@$1?OnDirectoryChange@1@QEAAKXZ@@QEAAKPEAVCImageCache@@KPEBGHK@Z; CDirectoryMonitor<CImageCache,&CImageCache::OnDirectoryChange(void)>::Initialize(CImageCache *,ulong,ushort const *,int,ulong)
0x180009027  lea     r9d, [r15+55h]
0x18000902b  mov     r8, r12
0x18000902e  mov     ecx, eax
0x180009030  mov     ebx, eax
0x180009032  call    ElValidateWin32_0
0x180009037  test    eax, eax
0x180009039  jnz     loc_1800092AD
0x18000903f  lea     r14, [rsi+0A0h]
0x180009046  mov     rcx, r14; this
0x180009049  call    ?Initialize@CWdsMetadataStoreManagementClient@@QEAAKXZ; CWdsMetadataStoreManagementClient::Initialize(void)
0x18000904e  lea     r9d, [r15+5Bh]
0x180009052  mov     r8, r12
0x180009055  mov     ecx, eax
0x180009057  mov     ebx, eax
0x180009059  call    ElValidateWin32_0
0x18000905e  test    eax, eax
0x180009060  jnz     loc_1800092AD
0x180009066  movups  xmm0, cs:xmmword_18001CD10
0x18000906d  lea     r8, [rbp+0A0h+arg_0]; int *
0x180009074  mov     rcx, r14; this
0x180009077  lea     rdx, [rsp+1A0h+var_150]; struct _GUID
0x18000907c  movdqu  xmmword ptr [rsp+1A0h+var_150.Data1], xmm0
0x180009082  call    ?CheckRegistration@CWdsMetadataStoreManagementClient@@QEAAKU_GUID@@PEAH@Z; CWdsMetadataStoreManagementClient::CheckRegistration(_GUID,int *)
0x180009087  lea     r9d, [r15+5Fh]
0x18000908b  mov     r8, r12
0x18000908e  mov     ecx, eax
0x180009090  mov     ebx, eax
0x180009092  call    ElValidateWin32_0
0x180009097  test    eax, eax
0x180009099  jnz     loc_1800092AD
0x18000909f  cmp     [rbp+0A0h+arg_0], r15d
0x1800090a6  jnz     loc_18000922D
0x1800090ac  lea     rdx, aWdsObjectType; "WDS.Object.Type"
0x1800090b3  mov     [rbp+0A0h+var_F0], r15
0x1800090b7  lea     rcx, [rsp+1A0h+var_140]; this
0x1800090bc  mov     [rbp+0A0h+var_E8], r15
0x1800090c0  xorps   xmm6, xmm6
0x1800090c3  mov     [rbp+0A0h+var_D8], r15
0x1800090c7  mov     [rbp+0A0h+var_D0], r15
0x1800090cb  mov     [rbp+0A0h+var_C0], r15
0x1800090cf  mov     [rbp+0A0h+var_B8], r15
0x1800090d3  mov     [rsp+1A0h+var_140], r15
0x1800090d8  mov     [rsp+1A0h+var_138], r15
0x1800090dd  mov     [rsp+1A0h+var_128], r15
0x1800090e2  mov     [rbp+0A0h+var_120], r15
0x1800090e6  mov     [rbp+0A0h+var_110], r15
0x1800090ea  mov     [rbp+0A0h+var_108], r15
0x1800090ee  mov     [rbp+0A0h+var_A0], r15
0x1800090f2  mov     [rbp+0A0h+var_98], r15
0x1800090f6  mov     [rbp+0A0h+var_88], r15
0x1800090fa  mov     [rbp+0A0h+var_80], r15
0x1800090fe  mov     [rbp+0A0h+var_70], r15
0x180009102  mov     [rbp+0A0h+var_68], r15
0x180009106  call    ?AppendExclusionFilter@CWdsMetadata@@QEAAKPEBG@Z; CWdsMetadata::AppendExclusionFilter(ushort const *)
0x18000910b  lea     r9d, [r15+6Eh]
0x18000910f  mov     r8, r12
0x180009112  mov     ecx, eax
0x180009114  mov     ebx, eax
0x180009116  call    ElValidateWin32_0
0x18000911b  test    eax, eax
0x18000911d  jz      short loc_180009140
0x18000911f  lea     rcx, [rbp+0A0h+var_A0]; this
0x180009123  call    ??1CWdsMetadata@@QEAA@XZ; CWdsMetadata::~CWdsMetadata(void)
0x180009128  lea     rcx, [rsp+1A0h+var_140]; this
0x18000912d  call    ??1CWdsMetadata@@QEAA@XZ; CWdsMetadata::~CWdsMetadata(void)
0x180009132  lea     rcx, [rbp+0A0h+var_F0]; this
0x180009136  call    ??1CWdsMetadata@@QEAA@XZ; CWdsMetadata::~CWdsMetadata(void)
0x18000913b  jmp     loc_1800092AD
0x180009140  lea     rdx, aWdsImagePriori; "WDS.Image.Priority"
0x180009147  lea     rcx, [rsp+1A0h+var_140]; this
0x18000914c  call    ?AppendExclusionFilter@CWdsMetadata@@QEAAKPEBG@Z; CWdsMetadata::AppendExclusionFilter(ushort const *)
0x180009151  mov     r9d, 71h ; 'q'
0x180009157  mov     r8, r12
0x18000915a  mov     ecx, eax
0x18000915c  mov     ebx, eax
0x18000915e  call    ElValidateWin32_0
0x180009163  test    eax, eax
0x180009165  jnz     short loc_18000911F
0x180009167  mov     edi, r15d
0x18000916a  cmp     edi, 13h
0x18000916d  jnb     short loc_1800091A0
0x18000916f  lea     rax, off_180018D10; "WDS.Object.Type"
0x180009176  mov     edx, edi
0x180009178  lea     rcx, [rsp+1A0h+var_140]; this
0x18000917d  mov     rdx, [rax+rdx*8]; unsigned __int16 *
0x180009181  call    ?AppendExclusionFilter@CWdsMetadata@@QEAAKPEBG@Z; CWdsMetadata::AppendExclusionFilter(ushort const *)
0x180009186  mov     r9d, 76h ; 'v'
0x18000918c  mov     r8, r12
0x18000918f  mov     ecx, eax
0x180009191  mov     ebx, eax
0x180009193  call    ElValidateWin32_0
0x180009198  test    eax, eax
0x18000919a  jnz     short loc_18000911F
0x18000919c  inc     edi
0x18000919e  jmp     short loc_18000916A
0x1800091a0  movups  xmm0, cs:xmmword_18001CD10
0x1800091a7  lea     rax, [rbp+0A0h+var_A0]
0x1800091ab  xor     r9d, r9d; int
0x1800091ae  lea     r8, aAllinstallimag; "AllInstallImages"
0x1800091b5  movdqa  xmmword ptr [rsp+1A0h+var_150.Data1], xmm6
0x1800091bb  mov     [rsp+1A0h+var_160], rax; struct CWdsMetadata *
0x1800091c0  lea     rdx, [rbp+0A0h+var_50]; struct _GUID
0x1800091c4  lea     rax, [rsp+1A0h+var_140]
0x1800091c9  mov     rcx, r14; this
0x1800091cc  mov     [rsp+1A0h+var_168], rax; struct CWdsMetadata *
0x1800091d1  lea     rax, [rbp+0A0h+var_F0]
0x1800091d5  mov     [rsp+1A0h+var_170], rax; struct CWdsMetadata *
0x1800091da  lea     rax, [rbp+0A0h+var_F0]
0x1800091de  mov     [rsp+1A0h+var_178], rax; struct CWdsMetadata *
0x1800091e3  lea     rax, [rsp+1A0h+var_150]
0x1800091e8  mov     [rsp+1A0h+var_180], rax; struct _GUID
0x1800091ed  movdqu  xmmword ptr [rbp+0A0h+var_50.Data1], xmm0
0x1800091f2  call    ?Register@CWdsMetadataStoreManagementClient@@QEAAKU_GUID@@PEBGH0PEBVCWdsMetadata@@222@Z; CWdsMetadataStoreManagementClient::Register(_GUID,ushort const *,int,_GUID,CWdsMetadata const *,CWdsMetadata const *,CWdsMetadata const *,CWdsMetadata const *)
0x1800091f7  mov     r9d, 81h
0x1800091fd  mov     r8, r12
0x180009200  mov     ecx, eax
0x180009202  mov     ebx, eax
0x180009204  call    ElValidateWin32_0
0x180009209  lea     rcx, [rbp+0A0h+var_A0]; this
0x18000920d  test    eax, eax
0x18000920f  jnz     loc_180009123
0x180009215  call    ??1CWdsMetadata@@QEAA@XZ; CWdsMetadata::~CWdsMetadata(void)
0x18000921a  lea     rcx, [rsp+1A0h+var_140]; this
0x18000921f  call    ??1CWdsMetadata@@QEAA@XZ; CWdsMetadata::~CWdsMetadata(void)
0x180009224  lea     rcx, [rbp+0A0h+var_F0]; this
0x180009228  call    ??1CWdsMetadata@@QEAA@XZ; CWdsMetadata::~CWdsMetadata(void)
0x18000922d  lea     r8, aSystemCurrentc_0; "System\\CurrentControlSet\\Services\\WD"...
0x180009234  lea     rcx, [rbp+0A0h+phkResult]; phkResult
0x18000923b  call    ?Open@CRegKey@@QEAAKPEAUHKEY__@@PEBGK@Z; CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x180009240  mov     r9d, 8Fh
0x180009246  mov     r8, r12
0x180009249  mov     ecx, eax
0x18000924b  mov     ebx, eax
0x18000924d  call    ElValidateWin32_0
0x180009252  test    eax, eax
0x180009254  jnz     short loc_1800092AD
0x180009256  lea     r9, [rsi+98h]
0x18000925d  mov     r8d, 7A120h
0x180009263  lea     rdx, aDefaultinstall; "DefaultInstallImagePriority"
0x18000926a  lea     rcx, [rbp+0A0h+phkResult]
0x180009271  call    cs:__imp_?GetValueDwordWithDefault@CRegKey@@QEAAKPEBGKPEAK@Z; CRegKey::GetValueDwordWithDefault(ushort const *,ulong,ulong *)
0x180009278  nop     dword ptr [rax+rax+00h]
0x18000927d  mov     r9d, 98h
0x180009283  mov     r8, r12
0x180009286  mov     ecx, eax
0x180009288  mov     ebx, eax
0x18000928a  call    ElValidateWin32_0
0x18000928f  test    eax, eax
0x180009291  jnz     short loc_1800092AD
0x180009293  mov     rcx, rsi; this
0x180009296  call    ?OnChange@CImageCache@@QEAAKXZ; CImageCache::OnChange(void)
0x18000929b  mov     r9d, 9Eh
0x1800092a1  mov     r8, r12
0x1800092a4  mov     ecx, eax
0x1800092a6  mov     ebx, eax
0x1800092a8  call    ElValidateWin32_0
0x1800092ad  lea     rcx, [rbp+0A0h+var_40]; this
0x1800092b1  call    ?Unlock@CAutoWriterLock@@QEAAXXZ; CAutoWriterLock::Unlock(void)
0x1800092b6  lea     rcx, [rbp+0A0h+phkResult]; this
0x1800092bd  call    ?Close@CRegKey@@QEAAXXZ; CRegKey::Close(void)
0x1800092c2  lea     r11, [rsp+1A0h+var_20]
0x1800092ca  mov     eax, ebx
0x1800092cc  mov     rbx, [r11+38h]
0x1800092d0  mov     rsi, [r11+48h]
0x1800092d4  movaps  xmm6, xmmword ptr [r11-10h]
0x1800092d9  mov     rsp, r11
0x1800092dc  pop     r15
0x1800092de  pop     r14
0x1800092e0  pop     r12
0x1800092e2  pop     rdi
0x1800092e3  pop     rbp
0x1800092e4  retn
```
