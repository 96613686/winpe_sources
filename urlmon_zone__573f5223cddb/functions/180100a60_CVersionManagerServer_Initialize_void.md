# CVersionManagerServer::Initialize(void)

- ea: `0x180100a60`
- end: `0x180100ddd`
- name: `?Initialize@CVersionManagerServer@@QEAAJXZ`
- size: `893`
- prototype: `__int64 __fastcall(CVersionManagerServer *__hidden this)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x1801002b0`

## callees

- `0x18001db50`
- `0x18002fee0`
- `0x180076ae0`
- `0x180082388`
- `0x18010097c`
- `0x180100a60`
- `0x180102e58`
- `0x180103b44`
- `0x180103ed8`
- `0x180107ce0`
- `0x180117fc0`
- `0x1801183a4`
- `0x18011a0e4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180100a95`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180100aab`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180100ac1`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180100ad7`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180100a95`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180100aab`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180100ac1`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180100ad7`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180100c87`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180100c96`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180100ca5`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180100cb4`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180100c87`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180100c96`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180100ca5`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180100cb4`
- `api-ms-win-core-localization-l1-2-0!GetUserGeoID` at `0x180100a79`
- `api-ms-win-core-localization-l1-2-0!GetUserGeoID` at `0x180100a79`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180100db8`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180100db8`

## pseudocode

```c
__int64 __fastcall CVersionManagerServer::Initialize(CVersionManagerServer *this)
{
  struct _RTL_CRITICAL_SECTION *v2; // rbp
  unsigned int v3; // edx
  int RegistrySettings; // ebx
  unsigned int v5; // r8d
  unsigned int v6; // r8d
  CFileInfoCache *v7; // rax
  CByteHashTable *v8; // rax
  unsigned int v9; // r8d
  char v10; // si
  unsigned int v11; // edx
  CByteHashTable *v12; // rax
  unsigned int v13; // r8d
  void *v14; // rcx
  void *v15; // rcx
  CFileInfoCache *v16; // rcx
  PTP_WORK ThreadpoolWork; // rax
  unsigned int v19; // [rsp+20h] [rbp-58h]
  unsigned int v20; // [rsp+20h] [rbp-58h]
  unsigned int (*v21)(const unsigned __int8 *, unsigned int, unsigned int); // [rsp+28h] [rbp-50h]
  unsigned int (*v22)(const unsigned __int8 *, unsigned int, unsigned int); // [rsp+28h] [rbp-50h]
  int v23; // [rsp+80h] [rbp+8h] BYREF

  v2 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 1888);
  *((_DWORD *)this + 499) = GetUserGeoID(0x10u);
  InitializeCriticalSection(v2);
  InitializeCriticalSection((LPCRITICAL_SECTION)((char *)this + 1848));
  InitializeCriticalSection((LPCRITICAL_SECTION)((char *)this + 1928));
  InitializeCriticalSection((LPCRITICAL_SECTION)((char *)this + 1784));
  RegistrySettings = CVersionManagerServer::_ReadRegistrySettings(this);
  if ( RegistrySettings < 0 )
    goto LABEL_24;
  RegistrySettings = MutexUtils::CMutex::Create(
                       (CVersionManagerServer *)((char *)this + 2032),
                       L"Local\\VERMGMTBlockListFileMutex",
                       v5);
  if ( RegistrySettings < 0 )
    goto LABEL_24;
  if ( *((_BYTE *)this + 25) )
  {
    RegistrySettings = MutexUtils::CMutex::Create(
                         (CVersionManagerServer *)((char *)this + 2056),
                         L"Local\\VERMGMTAuditMutex",
                         v6);
    if ( RegistrySettings < 0 )
      goto LABEL_24;
  }
  v7 = (CFileInfoCache *)operator new(0x38u);
  if ( v7 )
  {
    *(_WORD *)v7 = 0;
    *((_QWORD *)v7 + 1) = 0;
  }
  else
  {
    v7 = 0;
  }
  *((_QWORD *)this + 211) = v7;
  if ( v7 )
  {
    RegistrySettings = CFileInfoCache::Initialize(v7, *((_BYTE *)this + 25));
    if ( RegistrySettings < 0 )
      goto LABEL_24;
    v8 = (CByteHashTable *)operator new(0x28u);
    if ( v8 )
    {
      *((_QWORD *)v8 + 4) = 0;
      *((_QWORD *)v8 + 1) = 0;
      *((_QWORD *)v8 + 2) = 0;
      *(_QWORD *)v8 = 0;
      *((_QWORD *)v8 + 3) = 0;
    }
    else
    {
      v8 = 0;
    }
    *((_QWORD *)this + 246) = v8;
    if ( v8 )
    {
      RegistrySettings = CByteHashTable::Create(v8, v3, v9, 2u, v19, v21);
      if ( RegistrySettings < 0 )
        goto LABEL_24;
      v10 = 0;
      RegistrySettings = CVersionManagerServer::_InitializeDomainWhitelist(this);
      if ( RegistrySettings >= 0 )
      {
        v12 = (CByteHashTable *)operator new(0x28u);
        if ( v12 )
        {
          *((_QWORD *)v12 + 4) = 0;
          *((_QWORD *)v12 + 1) = 0;
          *((_QWORD *)v12 + 2) = 0;
          *(_QWORD *)v12 = 0;
          *((_QWORD *)v12 + 3) = 0;
        }
        else
        {
          v12 = 0;
        }
        *((_QWORD *)this + 247) = v12;
        if ( !v12 )
        {
LABEL_21:
          RegistrySettings = -2147024882;
          goto LABEL_22;
        }
        RegistrySettings = CByteHashTable::Create(v12, v11, v13, 2u, v20, v22);
        if ( RegistrySettings >= 0 )
        {
          v10 = 1;
          RegistrySettings = CSharedMem::_InitInternal(
                               (CVersionManagerServer *)((char *)this + 2008),
                               L"Local\\VERMGMTSharedMemory",
                               4u,
                               0,
                               0);
          if ( RegistrySettings >= 0 )
          {
            v23 = 1;
            RegistrySettings = GetBOOL((__int64 *)SettingStore::IEVALUE_urlmon_ExtVerDownloadVersionList[0], &v23);
            if ( RegistrySettings >= 0 )
            {
              if ( !v23 || (RegistrySettings = CVersionManagerServer::_StartDownloadTimer(this), RegistrySettings >= 0) )
              {
                *((_DWORD *)this + 428) = 3;
                *((_QWORD *)this + 215) = 0;
                *((_QWORD *)this + 216) = 0;
                *((_QWORD *)this + 217) = 0;
                *((_QWORD *)this + 218) = 0;
                *((_QWORD *)this + 219) = 0;
                *((_QWORD *)this + 220) = 0;
                *((_DWORD *)this + 442) = 0;
                *((_DWORD *)this + 444) = 72;
                *((_BYTE *)this + 1704) = 1;
                *((_DWORD *)this + 443) = 2;
                ThreadpoolWork = CreateThreadpoolWork(
                                   CVersionManagerServer::s_TelemetryWorkCallback,
                                   this,
                                   (PTP_CALLBACK_ENVIRON)((char *)this + 1712));
                *((_QWORD *)this + 212) = ThreadpoolWork;
                if ( ThreadpoolWork )
                {
                  *((_BYTE *)this + 24) = 1;
                  return (unsigned int)RegistrySettings;
                }
                goto LABEL_21;
              }
            }
          }
        }
      }
LABEL_22:
      CByteHashTable::_RemoveCallback(*((CByteHashTable **)this + 246), v11, 0, 0);
      if ( v10 )
        CByteHashTable::_RemoveCallback(*((CByteHashTable **)this + 247), v3, 0, 0);
      goto LABEL_24;
    }
  }
  RegistrySettings = -2147024882;
LABEL_24:
  v14 = (void *)*((_QWORD *)this + 247);
  if ( v14 )
    operator delete(v14);
  v15 = (void *)*((_QWORD *)this + 246);
  *((_QWORD *)this + 247) = 0;
  if ( v15 )
    operator delete(v15);
  v16 = (CFileInfoCache *)*((_QWORD *)this + 211);
  *((_QWORD *)this + 246) = 0;
  if ( v16 )
    CFileInfoCache::`scalar deleting destructor'(v16, v3);
  *((_QWORD *)this + 211) = 0;
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 1888));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 1848));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 1928));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 1784));
  if ( *((_BYTE *)this + 1704) )
    *((_BYTE *)this + 1704) = 0;
  return (unsigned int)RegistrySettings;
}

```

## disassembly

```asm
0x180100a60  push    rbx
0x180100a62  push    rbp
0x180100a63  push    rsi
0x180100a64  push    rdi
0x180100a65  push    r12
0x180100a67  push    r13
0x180100a69  push    r14
0x180100a6b  push    r15
0x180100a6d  sub     rsp, 38h
0x180100a71  mov     rdi, rcx
0x180100a74  mov     ecx, 10h; GeoClass
0x180100a79  call    cs:__imp_GetUserGeoID
0x180100a80  nop     dword ptr [rax+rax+00h]
0x180100a85  lea     rbp, [rdi+760h]
0x180100a8c  mov     [rdi+7CCh], eax
0x180100a92  mov     rcx, rbp; lpCriticalSection
0x180100a95  call    cs:__imp_InitializeCriticalSection
0x180100a9c  nop     dword ptr [rax+rax+00h]
0x180100aa1  lea     r14, [rdi+738h]
0x180100aa8  mov     rcx, r14; lpCriticalSection
0x180100aab  call    cs:__imp_InitializeCriticalSection
0x180100ab2  nop     dword ptr [rax+rax+00h]
0x180100ab7  lea     r15, [rdi+788h]
0x180100abe  mov     rcx, r15; lpCriticalSection
0x180100ac1  call    cs:__imp_InitializeCriticalSection
0x180100ac8  nop     dword ptr [rax+rax+00h]
0x180100acd  lea     r12, [rdi+6F8h]
0x180100ad4  mov     rcx, r12; lpCriticalSection
0x180100ad7  call    cs:__imp_InitializeCriticalSection
0x180100ade  nop     dword ptr [rax+rax+00h]
0x180100ae3  mov     rcx, rdi; this
0x180100ae6  call    ?_ReadRegistrySettings@CVersionManagerServer@@AEAAJXZ; CVersionManagerServer::_ReadRegistrySettings(void)
0x180100aeb  xor     r13d, r13d
0x180100aee  mov     ebx, eax
0x180100af0  test    eax, eax
0x180100af2  js      loc_180100C3C
0x180100af8  lea     rcx, [rdi+7F0h]; this
0x180100aff  lea     rdx, aLocalVermgmtbl; "Local\\VERMGMTBlockListFileMutex"
0x180100b06  call    ?Create@CMutex@MutexUtils@@QEAAJPEBGK@Z; MutexUtils::CMutex::Create(ushort const *,ulong)
0x180100b0b  mov     ebx, eax
0x180100b0d  test    eax, eax
0x180100b0f  js      loc_180100C3C
0x180100b15  cmp     [rdi+19h], r13b
0x180100b19  jz      short loc_180100B38
0x180100b1b  lea     rcx, [rdi+808h]; this
0x180100b22  lea     rdx, aLocalVermgmtau; "Local\\VERMGMTAuditMutex"
0x180100b29  call    ?Create@CMutex@MutexUtils@@QEAAJPEBGK@Z; MutexUtils::CMutex::Create(ushort const *,ulong)
0x180100b2e  mov     ebx, eax
0x180100b30  test    eax, eax
0x180100b32  js      loc_180100C3C
0x180100b38  mov     ecx, 38h ; '8'; Size
0x180100b3d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180100b42  test    rax, rax
0x180100b45  jz      short loc_180100B51
0x180100b47  mov     [rax], r13w
0x180100b4b  mov     [rax+8], r13
0x180100b4f  jmp     short loc_180100B54
0x180100b51  mov     rax, r13
0x180100b54  mov     [rdi+698h], rax
0x180100b5b  test    rax, rax
0x180100b5e  jnz     short loc_180100B6A
0x180100b60  mov     ebx, 8007000Eh
0x180100b65  jmp     loc_180100C3C
0x180100b6a  mov     dl, [rdi+19h]; bool
0x180100b6d  mov     rcx, rax; this
0x180100b70  call    ?Initialize@CFileInfoCache@@QEAAJ_N@Z; CFileInfoCache::Initialize(bool)
0x180100b75  mov     ebx, eax
0x180100b77  test    eax, eax
0x180100b79  js      loc_180100C3C
0x180100b7f  mov     ecx, 28h ; '('; Size
0x180100b84  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180100b89  test    rax, rax
0x180100b8c  jz      short loc_180100BA3
0x180100b8e  mov     [rax+20h], r13
0x180100b92  mov     [rax+8], r13
0x180100b96  mov     [rax+10h], r13
0x180100b9a  mov     [rax], r13
0x180100b9d  mov     [rax+18h], r13
0x180100ba1  jmp     short loc_180100BA6
0x180100ba3  mov     rax, r13
0x180100ba6  mov     [rdi+7B0h], rax
0x180100bad  test    rax, rax
0x180100bb0  jz      short loc_180100B60
0x180100bb2  mov     r9d, 2; unsigned int
0x180100bb8  mov     rcx, rax; this
0x180100bbb  call    ?Create@CByteHashTable@@QEAAJIIIIP6AIPEBEII@Z@Z; CByteHashTable::Create(uint,uint,uint,uint,uint (*)(uchar const *,uint,uint))
0x180100bc0  mov     ebx, eax
0x180100bc2  test    eax, eax
0x180100bc4  js      short loc_180100C3C
0x180100bc6  mov     rcx, rdi; this
0x180100bc9  mov     sil, r13b
0x180100bcc  call    ?_InitializeDomainWhitelist@CVersionManagerServer@@AEAAJXZ; CVersionManagerServer::_InitializeDomainWhitelist(void)
0x180100bd1  mov     ebx, eax
0x180100bd3  test    eax, eax
0x180100bd5  js      short loc_180100C13
0x180100bd7  mov     ecx, 28h ; '('; Size
0x180100bdc  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180100be1  test    rax, rax
0x180100be4  jz      short loc_180100BFB
0x180100be6  mov     [rax+20h], r13
0x180100bea  mov     [rax+8], r13
0x180100bee  mov     [rax+10h], r13
0x180100bf2  mov     [rax], r13
0x180100bf5  mov     [rax+18h], r13
0x180100bf9  jmp     short loc_180100BFE
0x180100bfb  mov     rax, r13
0x180100bfe  mov     [rdi+7B8h], rax
0x180100c05  test    rax, rax
0x180100c08  jnz     loc_180100CE4
0x180100c0e  mov     ebx, 8007000Eh
0x180100c13  mov     rcx, [rdi+7B0h]; this
0x180100c1a  xor     r9d, r9d; void *
0x180100c1d  xor     r8d, r8d; void (*)(unsigned __int8 *, unsigned int, void *)
0x180100c20  call    ?_RemoveCallback@CByteHashTable@@AEAAXHP6AXPEAEIPEAX@Z1@Z; CByteHashTable::_RemoveCallback(int,void (*)(uchar *,uint,void *),void *)
0x180100c25  test    sil, sil
0x180100c28  jz      short loc_180100C3C
0x180100c2a  mov     rcx, [rdi+7B8h]; this
0x180100c31  xor     r9d, r9d; void *
0x180100c34  xor     r8d, r8d; void (*)(unsigned __int8 *, unsigned int, void *)
0x180100c37  call    ?_RemoveCallback@CByteHashTable@@AEAAXHP6AXPEAEIPEAX@Z1@Z; CByteHashTable::_RemoveCallback(int,void (*)(uchar *,uint,void *),void *)
0x180100c3c  mov     rcx, [rdi+7B8h]; void *
0x180100c43  test    rcx, rcx
0x180100c46  jz      short loc_180100C4D
0x180100c48  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180100c4d  mov     rcx, [rdi+7B0h]; void *
0x180100c54  mov     [rdi+7B8h], r13
0x180100c5b  test    rcx, rcx
0x180100c5e  jz      short loc_180100C65
0x180100c60  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180100c65  mov     rcx, [rdi+698h]; this
0x180100c6c  mov     [rdi+7B0h], r13
0x180100c73  test    rcx, rcx
0x180100c76  jz      short loc_180100C7D
0x180100c78  call    ??_GCFileInfoCache@@QEAAPEAXI@Z; CFileInfoCache::`scalar deleting destructor'(uint)
0x180100c7d  mov     rcx, rbp; lpCriticalSection
0x180100c80  mov     [rdi+698h], r13
0x180100c87  call    cs:__imp_DeleteCriticalSection
0x180100c8e  nop     dword ptr [rax+rax+00h]
0x180100c93  mov     rcx, r14; lpCriticalSection
0x180100c96  call    cs:__imp_DeleteCriticalSection
0x180100c9d  nop     dword ptr [rax+rax+00h]
0x180100ca2  mov     rcx, r15; lpCriticalSection
0x180100ca5  call    cs:__imp_DeleteCriticalSection
0x180100cac  nop     dword ptr [rax+rax+00h]
0x180100cb1  mov     rcx, r12; lpCriticalSection
0x180100cb4  call    cs:__imp_DeleteCriticalSection
0x180100cbb  nop     dword ptr [rax+rax+00h]
0x180100cc0  cmp     [rdi+6A8h], r13b
0x180100cc7  jz      short loc_180100CD0
0x180100cc9  mov     [rdi+6A8h], r13b
0x180100cd0  mov     eax, ebx
0x180100cd2  add     rsp, 38h
0x180100cd6  pop     r15
0x180100cd8  pop     r14
0x180100cda  pop     r13
0x180100cdc  pop     r12
0x180100cde  pop     rdi
0x180100cdf  pop     rsi
0x180100ce0  pop     rbp
0x180100ce1  pop     rbx
0x180100ce2  retn
0x180100ce4  mov     r9d, 2; unsigned int
0x180100cea  mov     rcx, rax; this
0x180100ced  call    ?Create@CByteHashTable@@QEAAJIIIIP6AIPEBEII@Z@Z; CByteHashTable::Create(uint,uint,uint,uint,uint (*)(uchar const *,uint,uint))
0x180100cf2  mov     ebx, eax
0x180100cf4  test    eax, eax
0x180100cf6  js      loc_180100C13
0x180100cfc  mov     esi, 1
0x180100d01  mov     [rsp+78h+var_58], r13d; unsigned int
0x180100d06  lea     rcx, [rdi+7D8h]; this
0x180100d0d  xor     r9d, r9d; int
0x180100d10  lea     rdx, aLocalVermgmtsh; "Local\\VERMGMTSharedMemory"
0x180100d17  lea     r8d, [rsi+3]; unsigned int
0x180100d1b  call    ?_InitInternal@CSharedMem@@AEAAJPEBGKHK@Z; CSharedMem::_InitInternal(ushort const *,ulong,int,ulong)
0x180100d20  mov     ebx, eax
0x180100d22  test    eax, eax
0x180100d24  js      loc_180100C13
0x180100d2a  mov     rcx, cs:?IEVALUE_urlmon_ExtVerDownloadVersionList@SettingStore@@3U?$VALUEID@H@1@B; SettingStore::VALUEID<int> const SettingStore::IEVALUE_urlmon_ExtVerDownloadVersionList
0x180100d31  lea     rdx, [rsp+78h+arg_0]
0x180100d39  mov     [rsp+78h+arg_0], esi
0x180100d40  call    GetBOOL
0x180100d45  mov     ebx, eax
0x180100d47  test    eax, eax
0x180100d49  js      loc_180100C13
0x180100d4f  cmp     [rsp+78h+arg_0], r13d
0x180100d57  jz      short loc_180100D6B
0x180100d59  mov     rcx, rdi; pv
0x180100d5c  call    ?_StartDownloadTimer@CVersionManagerServer@@AEAAJXZ; CVersionManagerServer::_StartDownloadTimer(void)
0x180100d61  mov     ebx, eax
0x180100d63  test    eax, eax
0x180100d65  js      loc_180100C13
0x180100d6b  lea     r8, [rdi+6B0h]; pcbe
0x180100d72  mov     rdx, rdi; pv
0x180100d75  mov     dword ptr [r8], 3
0x180100d7c  lea     rcx, ?s_TelemetryWorkCallback@CVersionManagerServer@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x180100d83  mov     [r8+8], r13
0x180100d87  mov     [r8+10h], r13
0x180100d8b  mov     [r8+18h], r13
0x180100d8f  mov     [r8+20h], r13
0x180100d93  mov     [r8+28h], r13
0x180100d97  mov     [r8+30h], r13
0x180100d9b  mov     [r8+38h], r13d
0x180100d9f  mov     dword ptr [r8+40h], 48h ; 'H'
0x180100da7  mov     [rdi+6A8h], sil
0x180100dae  mov     dword ptr [rdi+6ECh], 2
0x180100db8  call    cs:__imp_CreateThreadpoolWork
0x180100dbf  nop     dword ptr [rax+rax+00h]
0x180100dc4  mov     [rdi+6A0h], rax
0x180100dcb  test    rax, rax
0x180100dce  jz      loc_180100C0E
0x180100dd4  mov     [rdi+18h], sil
0x180100dd8  jmp     loc_180100CD0
```
