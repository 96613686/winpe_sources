# CVaultFileStore::DeleteCredential(ushort const *)

- ea: `0x180023c90`
- end: `0x1800240d0`
- name: `?DeleteCredential@CVaultFileStore@@UEAAKPEBG@Z`
- size: `1088`
- prototype: `__int64 __fastcall(CVaultFileStore *this, unsigned __int16 *Buf1)`
- caller_count: `0`
- callee_count: `14`
- tags: `file_ops, reparse_path, loader_planting, broker_com_uri`

## callees

- `0x180003140`
- `0x18000eb30`
- `0x180011110`
- `0x180020030`
- `0x180023c90`
- `0x1800240e0`
- `0x180024220`
- `0x180024520`
- `0x18003a580`
- `0x18003b7d8`
- `0x18003b8a8`
- `0x18003b9ac`
- `0x1800411e0`
- `0x18004d010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180023fea`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180023fea`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180024042`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180024042`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023ef7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023ef7`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180023e74`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180023e74`
- `ntdll!RtlReleaseResource` at `0x180023d53`
- `ntdll!RtlReleaseResource` at `0x180023df3`
- `ntdll!RtlReleaseResource` at `0x180023e50`
- `ntdll!RtlReleaseResource` at `0x180023ed7`
- `ntdll!RtlReleaseResource` at `0x180023f16`
- `ntdll!RtlReleaseResource` at `0x18002408c`
- `ntdll!RtlReleaseResource` at `0x180023d53`
- `ntdll!RtlReleaseResource` at `0x180023df3`
- `ntdll!RtlReleaseResource` at `0x180023e50`
- `ntdll!RtlReleaseResource` at `0x180023ed7`
- `ntdll!RtlReleaseResource` at `0x180023f16`
- `ntdll!RtlReleaseResource` at `0x18002408c`
- `ntdll!RtlAcquireResourceExclusive` at `0x180023cf2`
- `ntdll!RtlAcquireResourceExclusive` at `0x180023cf2`

## pseudocode

```c
__int64 __fastcall CVaultFileStore::DeleteCredential(CVaultFileStore *this, unsigned __int16 *Buf1)
{
  struct _RTL_RESOURCE *v4; // rdi
  unsigned int v5; // esi
  DWORD CredFromUniqueId; // ebx
  struct IVaultCredential *v8; // r15
  unsigned int v9; // eax
  unsigned int v10; // r12d
  HRESULT v11; // eax
  char v12; // al
  int v13; // r8d
  unsigned int v14; // [rsp+40h] [rbp-69h] BYREF
  __int64 ThreadInformation; // [rsp+48h] [rbp-61h] BYREF
  int v16; // [rsp+50h] [rbp-59h] BYREF
  __int64 v17; // [rsp+58h] [rbp-51h] BYREF
  __int64 v18; // [rsp+60h] [rbp-49h] BYREF
  int v19; // [rsp+68h] [rbp-41h]
  __int64 v20; // [rsp+70h] [rbp-39h] BYREF
  LPCWSTR lpFileName; // [rsp+78h] [rbp-31h] BYREF
  int v22; // [rsp+80h] [rbp-29h]
  __int64 (__fastcall *v23)(); // [rsp+88h] [rbp-21h] BYREF
  struct IVaultCredential *v24; // [rsp+90h] [rbp-19h] BYREF
  int v25; // [rsp+98h] [rbp-11h]
  char *v26; // [rsp+A0h] [rbp-9h]
  char v27; // [rsp+A8h] [rbp-1h]
  __int128 v28; // [rsp+B0h] [rbp+7h] BYREF

  lpFileName = 0;
  v22 = 0;
  v20 = 0;
  v23 = AutoDereference<IVaultKeyManager>;
  v24 = 0;
  v25 = 0;
  v4 = (struct _RTL_RESOURCE *)((char *)this + 192);
  v26 = (char *)this + 192;
  RtlAcquireResourceExclusive((PRTL_RESOURCE)this + 2, 1u);
  v27 = 1;
  ThreadInformation = 0;
  v5 = 0;
  v16 = 0;
  v18 = 0;
  v19 = 0;
  v17 = 0;
  v14 = 0;
  v28 = 0;
  CredFromUniqueId = CVaultMemoryStore::GetCredFromUniqueId(this, Buf1, &v24);
  if ( CredFromUniqueId )
  {
    if ( CredFromUniqueId != 1168 )
    {
      CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v17);
      CVaultIntegrityLevel::~CVaultIntegrityLevel(&ThreadInformation);
      RtlReleaseResource(v4);
      CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v23);
      CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v20);
      return CredFromUniqueId;
    }
    v5 = 1168;
  }
  v8 = v24;
  if ( !v24 || ((*(__int64 (__fastcall **)(struct IVaultCredential *))(*(_QWORD *)v24 + 160LL))(v24) & 0x40) == 0 )
  {
    v9 = CVaultIntegrityLevel::Elevate((CVaultIntegrityLevel *)&ThreadInformation);
    v10 = v9;
    if ( v9 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 41, &WPP_c304bf9ddc9a325b3ef15398c2399f48_Traceguids, v9);
      CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v17);
      CVaultIntegrityLevel::~CVaultIntegrityLevel(&ThreadInformation);
      RtlReleaseResource(v4);
      CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v23);
      CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v20);
      return v10;
    }
    CredFromUniqueId = PathCombineExt(
                         *((wchar_t **)this + 39),
                         Buf1,
                         (wchar_t *)L".vcrd",
                         (unsigned __int16 **)&lpFileName);
    if ( CredFromUniqueId )
    {
LABEL_14:
      CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v17);
      CVaultIntegrityLevel::~CVaultIntegrityLevel(&ThreadInformation);
      RtlReleaseResource(v4);
      CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v23);
      CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v20);
      return CredFromUniqueId;
    }
    if ( !DeleteFileW(lpFileName) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_SD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          42,
          (unsigned int)&WPP_c304bf9ddc9a325b3ef15398c2399f48_Traceguids,
          (_DWORD)lpFileName,
          0);
      CredFromUniqueId = 1168;
      if ( v5 != 1168 )
        CredFromUniqueId = GetLastError();
      goto LABEL_14;
    }
  }
  if ( !v5 )
  {
    v5 = CVaultMemoryStore::DeleteCredential(this, Buf1);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 43, &WPP_c304bf9ddc9a325b3ef15398c2399f48_Traceguids, Buf1);
    if ( !v5 )
    {
      (*(void (__fastcall **)(struct IVaultCredential *, int *))(*(_QWORD *)v8 + 248LL))(v8, &v16);
      if ( v16 )
      {
        (*(void (__fastcall **)(CVaultFileStore *, __int64 *))(*(_QWORD *)this + 176LL))(this, &v18);
        (*(void (__fastcall **)(CVaultFileStore *, unsigned int *, _QWORD))(*(_QWORD *)this + 32LL))(this, &v14, 0);
        (*(void (__fastcall **)(CVaultFileStore *, __int128 *))(*(_QWORD *)this + 24LL))(this, &v28);
        v11 = CoInitializeEx(0, 0);
        if ( v11 < 0 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              45,
              &WPP_c304bf9ddc9a325b3ef15398c2399f48_Traceguids,
              (unsigned int)v11);
        }
        else
        {
          v12 = VaultCDSSaveCredential(Buf1, v18, v14, &v28, 1);
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
            WPP_SF_SSdd(*((_QWORD *)WPP_GLOBAL_Control + 2), 44, v13, (_DWORD)Buf1, v18, v14, v12);
          CoUninitialize();
        }
      }
    }
  }
  CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v17);
  CVaultIntegrityLevel::~CVaultIntegrityLevel(&ThreadInformation);
  RtlReleaseResource(v4);
  CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v23);
  CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v20);
  return v5;
}

```

## disassembly

```asm
0x180023c90  mov     [rsp-8+arg_10], rbx
0x180023c95  push    rbp
0x180023c96  push    rsi
0x180023c97  push    rdi
0x180023c98  push    r12
0x180023c9a  push    r13
0x180023c9c  push    r14
0x180023c9e  push    r15
0x180023ca0  lea     rbp, [rsp-27h]
0x180023ca5  sub     rsp, 0D0h
0x180023cac  mov     rax, cs:__security_cookie
0x180023cb3  xor     rax, rsp
0x180023cb6  mov     [rbp+57h+var_40], rax
0x180023cba  mov     r14, rdx
0x180023cbd  mov     r13, rcx
0x180023cc0  xor     r12d, r12d
0x180023cc3  mov     [rbp+57h+lpFileName], r12
0x180023cc7  mov     [rbp+57h+var_80], r12d
0x180023ccb  mov     [rbp+57h+var_90], r12
0x180023ccf  lea     rax, ??$AutoDereference@UIVaultKeyManager@@@@YAXPEAUIVaultKeyManager@@@Z; AutoDereference<IVaultKeyManager>(IVaultKeyManager *)
0x180023cd6  mov     [rbp+57h+var_78], rax
0x180023cda  mov     [rbp+57h+var_70], r12
0x180023cde  mov     [rbp+57h+var_68], r12d
0x180023ce2  lea     rdi, [rcx+0C0h]
0x180023ce9  mov     [rbp+57h+var_60], rdi
0x180023ced  mov     dl, 1; Wait
0x180023cef  mov     rcx, rdi; Resource
0x180023cf2  call    cs:__imp_RtlAcquireResourceExclusive
0x180023cf8  mov     [rbp+57h+var_58], 1
0x180023cfc  mov     [rbp+57h+ThreadInformation], r12
0x180023d00  mov     esi, r12d
0x180023d03  mov     [rbp+57h+var_B0], r12d
0x180023d07  mov     [rbp+57h+var_A0], r12
0x180023d0b  mov     [rbp+57h+var_98], r12d
0x180023d0f  mov     [rbp+57h+var_A8], r12
0x180023d13  mov     [rbp+57h+var_C0], r12d
0x180023d17  xorps   xmm0, xmm0
0x180023d1a  movups  [rbp+57h+var_50], xmm0
0x180023d1e  lea     r8, [rbp+57h+var_70]; struct IVaultCredential **
0x180023d22  mov     rdx, r14; unsigned __int16 *
0x180023d25  mov     rcx, r13; this
0x180023d28  call    ?GetCredFromUniqueId@CVaultMemoryStore@@UEAAKPEBGPEAPEAUIVaultCredential@@@Z; CVaultMemoryStore::GetCredFromUniqueId(ushort const *,IVaultCredential * *)
0x180023d2d  mov     ebx, eax
0x180023d2f  mov     eax, 490h
0x180023d34  test    ebx, ebx
0x180023d36  jz      short loc_180023D77
0x180023d38  cmp     ebx, eax
0x180023d3a  jz      short loc_180023D75
0x180023d3c  lea     rcx, [rbp+57h+var_A8]
0x180023d40  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180023d45  nop
0x180023d46  lea     rcx, [rbp+57h+ThreadInformation]; ThreadInformation
0x180023d4a  call    ??1CVaultIntegrityLevel@@QEAA@XZ; CVaultIntegrityLevel::~CVaultIntegrityLevel(void)
0x180023d4f  nop
0x180023d50  mov     rcx, rdi; Resource
0x180023d53  call    cs:__imp_RtlReleaseResource
0x180023d59  nop
0x180023d5a  lea     rcx, [rbp+57h+var_78]
0x180023d5e  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180023d63  nop
0x180023d64  lea     rcx, [rbp+57h+var_90]
0x180023d68  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180023d6d  nop
0x180023d6e  mov     eax, ebx
0x180023d70  jmp     loc_1800240A9
0x180023d75  mov     esi, eax
0x180023d77  mov     r15, [rbp+57h+var_70]
0x180023d7b  test    r15, r15
0x180023d7e  jz      short loc_180023D9A
0x180023d80  mov     rax, [r15]
0x180023d83  mov     rcx, r15
0x180023d86  mov     rax, [rax+0A0h]
0x180023d8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023d92  test    al, 40h
0x180023d94  jnz     loc_180023F36
0x180023d9a  lea     rcx, [rbp+57h+ThreadInformation]; this
0x180023d9e  call    ?Elevate@CVaultIntegrityLevel@@QEAAKXZ; CVaultIntegrityLevel::Elevate(void)
0x180023da3  mov     r12d, eax
0x180023da6  test    eax, eax
0x180023da8  jz      short loc_180023E16
0x180023daa  lea     rbx, WPP_GLOBAL_Control
0x180023db1  mov     rcx, cs:WPP_GLOBAL_Control
0x180023db8  cmp     rcx, rbx
0x180023dbb  jz      short loc_180023DDC
0x180023dbd  test    byte ptr [rcx+1Ch], 2
0x180023dc1  jz      short loc_180023DDC
0x180023dc3  mov     edx, 29h ; ')'
0x180023dc8  mov     r9d, eax
0x180023dcb  lea     r8, WPP_c304bf9ddc9a325b3ef15398c2399f48_Traceguids
0x180023dd2  mov     rcx, [rcx+10h]
0x180023dd6  call    WPP_SF_d
0x180023ddb  nop
0x180023ddc  lea     rcx, [rbp+57h+var_A8]
0x180023de0  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180023de5  nop
0x180023de6  lea     rcx, [rbp+57h+ThreadInformation]; ThreadInformation
0x180023dea  call    ??1CVaultIntegrityLevel@@QEAA@XZ; CVaultIntegrityLevel::~CVaultIntegrityLevel(void)
0x180023def  nop
0x180023df0  mov     rcx, rdi; Resource
0x180023df3  call    cs:__imp_RtlReleaseResource
0x180023df9  nop
0x180023dfa  lea     rcx, [rbp+57h+var_78]
0x180023dfe  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180023e03  nop
0x180023e04  lea     rcx, [rbp+57h+var_90]
0x180023e08  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180023e0d  nop
0x180023e0e  mov     eax, r12d
0x180023e11  jmp     loc_1800240A9
0x180023e16  lea     r9, [rbp+57h+lpFileName]; unsigned __int16 **
0x180023e1a  lea     r8, aVcrd_0; ".vcrd"
0x180023e21  mov     rdx, r14; wchar_t *
0x180023e24  mov     rcx, [r13+138h]; Source
0x180023e2b  call    ?PathCombineExt@@YAKPEBG00PEAPEAG@Z; PathCombineExt(ushort const *,ushort const *,ushort const *,ushort * *)
0x180023e30  mov     ebx, eax
0x180023e32  xor     r12d, r12d
0x180023e35  test    eax, eax
0x180023e37  jz      short loc_180023E70
0x180023e39  lea     rcx, [rbp+57h+var_A8]
0x180023e3d  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180023e42  nop
0x180023e43  lea     rcx, [rbp+57h+ThreadInformation]; ThreadInformation
0x180023e47  call    ??1CVaultIntegrityLevel@@QEAA@XZ; CVaultIntegrityLevel::~CVaultIntegrityLevel(void)
0x180023e4c  nop
0x180023e4d  mov     rcx, rdi; Resource
0x180023e50  call    cs:__imp_RtlReleaseResource
0x180023e56  nop
0x180023e57  lea     rcx, [rbp+57h+var_78]
0x180023e5b  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180023e60  nop
0x180023e61  lea     rcx, [rbp+57h+var_90]
0x180023e65  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180023e6a  nop
0x180023e6b  jmp     loc_180023D6E
0x180023e70  mov     rcx, [rbp+57h+lpFileName]; lpFileName
0x180023e74  call    cs:__imp_DeleteFileW
0x180023e7a  test    eax, eax
0x180023e7c  jnz     loc_180023F36
0x180023e82  lea     rbx, WPP_GLOBAL_Control
0x180023e89  mov     rcx, cs:WPP_GLOBAL_Control
0x180023e90  cmp     rcx, rbx
0x180023e93  jz      short loc_180023EB7
0x180023e95  test    byte ptr [rcx+1Ch], 2
0x180023e99  jz      short loc_180023EB7
0x180023e9b  lea     edx, [rax+2Ah]
0x180023e9e  mov     dword ptr [rsp+100h+var_E0], r12d
0x180023ea3  mov     r9, [rbp+57h+lpFileName]
0x180023ea7  lea     r8, WPP_c304bf9ddc9a325b3ef15398c2399f48_Traceguids
0x180023eae  mov     rcx, [rcx+10h]
0x180023eb2  call    WPP_SF_SD
0x180023eb7  mov     ebx, 490h
0x180023ebc  cmp     esi, ebx
0x180023ebe  jnz     short loc_180023EF7
0x180023ec0  lea     rcx, [rbp+57h+var_A8]
0x180023ec4  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180023ec9  nop
0x180023eca  lea     rcx, [rbp+57h+ThreadInformation]; ThreadInformation
0x180023ece  call    ??1CVaultIntegrityLevel@@QEAA@XZ; CVaultIntegrityLevel::~CVaultIntegrityLevel(void)
0x180023ed3  nop
0x180023ed4  mov     rcx, rdi; Resource
0x180023ed7  call    cs:__imp_RtlReleaseResource
0x180023edd  nop
0x180023ede  lea     rcx, [rbp+57h+var_78]
0x180023ee2  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180023ee7  nop
0x180023ee8  lea     rcx, [rbp+57h+var_90]
0x180023eec  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180023ef1  nop
0x180023ef2  jmp     loc_180023D6E
0x180023ef7  call    cs:__imp_GetLastError
0x180023efd  mov     ebx, eax
0x180023eff  lea     rcx, [rbp+57h+var_A8]
0x180023f03  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180023f08  nop
0x180023f09  lea     rcx, [rbp+57h+ThreadInformation]; ThreadInformation
0x180023f0d  call    ??1CVaultIntegrityLevel@@QEAA@XZ; CVaultIntegrityLevel::~CVaultIntegrityLevel(void)
0x180023f12  nop
0x180023f13  mov     rcx, rdi; Resource
0x180023f16  call    cs:__imp_RtlReleaseResource
0x180023f1c  nop
0x180023f1d  lea     rcx, [rbp+57h+var_78]
0x180023f21  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180023f26  nop
0x180023f27  lea     rcx, [rbp+57h+var_90]
0x180023f2b  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180023f30  nop
0x180023f31  jmp     loc_180023D6E
0x180023f36  test    esi, esi
0x180023f38  jnz     loc_180024075
0x180023f3e  mov     rdx, r14; Buf1
0x180023f41  mov     rcx, r13; this
0x180023f44  call    ?DeleteCredential@CVaultMemoryStore@@UEAAKPEBG@Z; CVaultMemoryStore::DeleteCredential(ushort const *)
0x180023f49  mov     esi, eax
0x180023f4b  lea     rbx, WPP_GLOBAL_Control
0x180023f52  mov     rcx, cs:WPP_GLOBAL_Control
0x180023f59  cmp     rcx, rbx
0x180023f5c  jz      short loc_180023F7C
0x180023f5e  test    byte ptr [rcx+1Ch], 8
0x180023f62  jz      short loc_180023F7C
0x180023f64  mov     edx, 2Bh ; '+'
0x180023f69  mov     r9, r14
0x180023f6c  lea     r8, WPP_c304bf9ddc9a325b3ef15398c2399f48_Traceguids
0x180023f73  mov     rcx, [rcx+10h]
0x180023f77  call    WPP_SF_S
0x180023f7c  test    esi, esi
0x180023f7e  jnz     loc_180024075
0x180023f84  mov     rax, [r15]
0x180023f87  lea     rdx, [rbp+57h+var_B0]
0x180023f8b  mov     rcx, r15
0x180023f8e  mov     rax, [rax+0F8h]
0x180023f95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023f9a  cmp     [rbp+57h+var_B0], r12d
0x180023f9e  jz      loc_180024075
0x180023fa4  mov     rax, [r13+0]
0x180023fa8  lea     rdx, [rbp+57h+var_A0]
0x180023fac  mov     rcx, r13
0x180023faf  mov     rax, [rax+0B0h]
0x180023fb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023fbb  mov     rax, [r13+0]
0x180023fbf  xor     r8d, r8d
0x180023fc2  lea     rdx, [rbp+57h+var_C0]
0x180023fc6  mov     rcx, r13
0x180023fc9  mov     rax, [rax+20h]
0x180023fcd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023fd2  mov     rax, [r13+0]
0x180023fd6  lea     rdx, [rbp+57h+var_50]
0x180023fda  mov     rcx, r13
0x180023fdd  mov     rax, [rax+18h]
0x180023fe1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023fe6  xor     edx, edx; dwCoInit
0x180023fe8  xor     ecx, ecx; pvReserved
0x180023fea  call    cs:__imp_CoInitializeEx
0x180023ff0  test    eax, eax
0x180023ff2  js      short loc_18002404A
0x180023ff4  mov     byte ptr [rsp+100h+var_E0], 1
0x180023ff9  lea     r9, [rbp+57h+var_50]
0x180023ffd  mov     r8d, [rbp+57h+var_C0]
0x180024001  mov     rdx, [rbp+57h+var_A0]
0x180024005  mov     rcx, r14
0x180024008  call    ?VaultCDSSaveCredential@@YAJPEBG0W4eVaultType@@PEBU_GUID@@E@Z; VaultCDSSaveCredential(ushort const *,ushort const *,eVaultType,_GUID const *,uchar)
0x18002400d  mov     rcx, cs:WPP_GLOBAL_Control
0x180024014  cmp     rcx, rbx
0x180024017  jz      short loc_180024042
0x180024019  test    byte ptr [rcx+1Ch], 8
0x18002401d  jz      short loc_180024042
0x18002401f  lea     edx, [rsi+2Ch]
0x180024022  mov     [rsp+100h+var_D0], eax
0x180024026  mov     eax, [rbp+57h+var_C0]
0x180024029  mov     [rsp+100h+var_D8], eax
0x18002402d  mov     rax, [rbp+57h+var_A0]
0x180024031  mov     [rsp+100h+var_E0], rax
0x180024036  mov     r9, r14
0x180024039  mov     rcx, [rcx+10h]
0x18002403d  call    WPP_SF_SSdd
0x180024042  call    cs:__imp_CoUninitialize
0x180024048  jmp     short loc_180024075
0x18002404a  mov     rcx, cs:WPP_GLOBAL_Control
0x180024051  cmp     rcx, rbx
0x180024054  jz      short loc_180024075
0x180024056  test    byte ptr [rcx+1Ch], 2
0x18002405a  jz      short loc_180024075
0x18002405c  mov     edx, 2Dh ; '-'
0x180024061  mov     r9d, eax
0x180024064  lea     r8, WPP_c304bf9ddc9a325b3ef15398c2399f48_Traceguids
0x18002406b  mov     rcx, [rcx+10h]
0x18002406f  call    WPP_SF_d
0x180024074  nop
0x180024075  lea     rcx, [rbp+57h+var_A8]
0x180024079  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18002407e  nop
0x18002407f  lea     rcx, [rbp+57h+ThreadInformation]; ThreadInformation
0x180024083  call    ??1CVaultIntegrityLevel@@QEAA@XZ; CVaultIntegrityLevel::~CVaultIntegrityLevel(void)
0x180024088  nop
0x180024089  mov     rcx, rdi; Resource
0x18002408c  call    cs:__imp_RtlReleaseResource
0x180024092  nop
0x180024093  lea     rcx, [rbp+57h+var_78]
0x180024097  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18002409c  nop
0x18002409d  lea     rcx, [rbp+57h+var_90]
0x1800240a1  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x1800240a6  nop
0x1800240a7  mov     eax, esi
0x1800240a9  mov     rcx, [rbp+57h+var_40]
0x1800240ad  xor     rcx, rsp; StackCookie
0x1800240b0  call    __security_check_cookie
0x1800240b5  mov     rbx, [rsp+100h+arg_10]
0x1800240bd  add     rsp, 0D0h
0x1800240c4  pop     r15
0x1800240c6  pop     r14
0x1800240c8  pop     r13
0x1800240ca  pop     r12
0x1800240cc  pop     rdi
0x1800240cd  pop     rsi
0x1800240ce  pop     rbp
0x1800240cf  retn
```
