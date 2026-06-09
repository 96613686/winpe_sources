# CVaultFileStore::CreateNewVault(_GUID const *,uchar *,ulong,ushort const *,uchar,ushort const *,eVaultType,VaultPolicy *,CVaultFileStore * *)

- ea: `0x180040944`
- end: `0x180040cb7`
- name: `?CreateNewVault@CVaultFileStore@@SAKPEBU_GUID@@PEAEKPEBGE2W4eVaultType@@PEAUVaultPolicy@@PEAPEAV1@@Z`
- size: `883`
- prototype: `static unsigned int __high(const struct _GUID *, unsigned __int8 *, unsigned int, const unsigned __int16 *, unsigned __int8, const unsigned __int16 *, enum eVaultType, struct VaultPolicy *, struct CVaultFileStore **)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18003d960`

## callees

- `0x180003140`
- `0x180004e6c`
- `0x18000eb30`
- `0x180011110`
- `0x180019db8`
- `0x180019ef0`
- `0x1800311f4`
- `0x1800389bc`
- `0x180039ea8`
- `0x18003b7d8`
- `0x180040944`
- `0x180041524`
- `0x18004d010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180040ad7`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180040ad7`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CVaultFileStore::CreateNewVault(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        WCHAR *a4,
        unsigned int a5,
        __int64 a6,
        int a7,
        __int64 a8,
        CVaultFileStore **a9)
{
  ULONG v13; // ebx
  unsigned int v15; // edi
  __int64 v16; // rcx
  struct IVaultFileSystem *v17; // rsi
  ULONG v18; // eax
  HLOCAL v19; // rax
  CVaultFileStore *v20; // rbx
  unsigned int Policy; // edi
  HANDLE ThreadInformation; // [rsp+40h] [rbp-78h] BYREF
  HLOCAL v23; // [rsp+48h] [rbp-70h]
  __int64 (__fastcall *v24)(_QWORD); // [rsp+50h] [rbp-68h] BYREF
  CVaultFileStore *v25; // [rsp+58h] [rbp-60h]
  int v26; // [rsp+60h] [rbp-58h]
  __int64 (__fastcall *v27)(_QWORD); // [rsp+68h] [rbp-50h] BYREF
  struct IVaultFileSystem *v28; // [rsp+70h] [rbp-48h] BYREF
  int v29; // [rsp+78h] [rbp-40h]

  v24 = AutoDereference<IVaultKeyManager>;
  v25 = 0;
  v26 = 0;
  v27 = AutoDereference<IVaultKeyManager>;
  v28 = 0;
  v29 = 0;
  a5 = 0;
  ThreadInformation = 0;
  v13 = CVaultIntegrityLevel::Elevate((CVaultIntegrityLevel *)&ThreadInformation);
  if ( v13 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 47, &WPP_c304bf9ddc9a325b3ef15398c2399f48_Traceguids, v13);
    goto LABEL_5;
  }
  GetFileSystemType(a4, (enum eFileSystemType *)&a5);
  v15 = a5;
  v13 = CVaultFactory::CreateVaultFileSystem(v16, a5, &v28);
  if ( v13
    || (v17 = v28, (v13 = (*(__int64 (__fastcall **)(struct IVaultFileSystem *))(*(_QWORD *)v28 + 16LL))(v28)) != 0)
    || (v18 = (*(__int64 (__fastcall **)(struct IVaultFileSystem *, WCHAR *))(*(_QWORD *)v17 + 40LL))(v17, a4),
        (v13 = v18) != 0)
    && v18 != 183 )
  {
LABEL_5:
    CVaultIntegrityLevel::~CVaultIntegrityLevel(&ThreadInformation);
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete((__int64)&v27);
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete((__int64)&v24);
    return v13;
  }
  v19 = LocalAlloc(0x40u, 0x140u);
  v23 = v19;
  if ( !v19 )
  {
    CVaultIntegrityLevel::~CVaultIntegrityLevel(&ThreadInformation);
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete((__int64)&v27);
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete((__int64)&v24);
    return 14;
  }
  try
  {
    v20 = CVaultFileStore::CVaultFileStore((CVaultFileStore *)v19);
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete((__int64)&v24);
    v25 = v20;
  }
  catch ( std::bad_alloc )
  {
    VaultFreeInternal(v23);
    v25 = 0;
    CVaultIntegrityLevel::~CVaultIntegrityLevel(&ThreadInformation);
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete((__int64)&v27);
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete((__int64)&v24);
    return 14;
  }
  *((_DWORD *)v20 + 76) = v15;
  Policy = CVaultMemoryStore::InitializeStore(v20);
  if ( Policy
    || (Policy = CVaultFileStore::InitializeVaultStorePath(v20, a4)) != 0
    || (Policy = CVaultMemoryStore::CreatePolicy(v20, a1, a2, a3, a6, a7, a8)) != 0
    || (Policy = CVaultFileStore::SubmitPolicyToStore(v20, v17)) != 0
    || (Policy = (*(__int64 (__fastcall **)(struct IVaultFileSystem *))(*(_QWORD *)v17 + 24LL))(v17)) != 0 )
  {
    CVaultIntegrityLevel::~CVaultIntegrityLevel(&ThreadInformation);
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete((__int64)&v27);
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete((__int64)&v24);
    return Policy;
  }
  else
  {
    v25 = 0;
    *a9 = v20;
    CVaultIntegrityLevel::~CVaultIntegrityLevel(&ThreadInformation);
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete((__int64)&v27);
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete((__int64)&v24);
    return 0;
  }
}

```

## disassembly

```asm
0x180040944  mov     r11, rsp
0x180040947  push    rbx
0x180040948  push    rsi
0x180040949  push    rdi
0x18004094a  push    r12
0x18004094c  push    r13
0x18004094e  push    r14
0x180040950  push    r15
0x180040952  sub     rsp, 80h
0x180040959  mov     r14, r9
0x18004095c  mov     r15d, r8d
0x18004095f  mov     r12, rdx
0x180040962  mov     r13, rcx
0x180040965  lea     rax, ??$AutoDereference@UIVaultKeyManager@@@@YAXPEAUIVaultKeyManager@@@Z; AutoDereference<IVaultKeyManager>(IVaultKeyManager *)
0x18004096c  mov     [r11-68h], rax
0x180040970  xor     esi, esi
0x180040972  mov     [r11-60h], rsi
0x180040976  mov     [rsp+0B8h+var_58], esi
0x18004097a  lea     rax, ??$AutoDereference@UIVaultKeyManager@@@@YAXPEAUIVaultKeyManager@@@Z; AutoDereference<IVaultKeyManager>(IVaultKeyManager *)
0x180040981  mov     [r11-50h], rax
0x180040985  mov     [r11-48h], rsi
0x180040989  mov     [rsp+0B8h+var_40], esi
0x18004098d  mov     [r11+28h], esi
0x180040991  mov     [r11-78h], rsi
0x180040995  lea     rcx, [r11-78h]; this
0x180040999  call    ?Elevate@CVaultIntegrityLevel@@QEAAKXZ; CVaultIntegrityLevel::Elevate(void)
0x18004099e  mov     ebx, eax
0x1800409a0  test    eax, eax
0x1800409a2  jz      short loc_1800409FC
0x1800409a4  lea     rax, WPP_GLOBAL_Control
0x1800409ab  mov     rcx, cs:WPP_GLOBAL_Control
0x1800409b2  cmp     rcx, rax
0x1800409b5  jz      short loc_1800409D4
0x1800409b7  test    byte ptr [rcx+1Ch], 2
0x1800409bb  jz      short loc_1800409D4
0x1800409bd  lea     edx, [rsi+2Fh]
0x1800409c0  mov     r9d, ebx
0x1800409c3  lea     r8, WPP_c304bf9ddc9a325b3ef15398c2399f48_Traceguids
0x1800409ca  mov     rcx, [rcx+10h]
0x1800409ce  call    WPP_SF_d
0x1800409d3  nop
0x1800409d4  lea     rcx, [rsp+0B8h+ThreadInformation]; ThreadInformation
0x1800409d9  call    ??1CVaultIntegrityLevel@@QEAA@XZ; CVaultIntegrityLevel::~CVaultIntegrityLevel(void)
0x1800409de  nop
0x1800409df  lea     rcx, [rsp+0B8h+var_50]
0x1800409e4  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x1800409e9  nop
0x1800409ea  lea     rcx, [rsp+0B8h+var_68]
0x1800409ef  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x1800409f4  nop
0x1800409f5  mov     eax, ebx
0x1800409f7  jmp     loc_180040CA4
0x1800409fc  lea     rdx, [rsp+0B8h+arg_20]; enum eFileSystemType *
0x180040a04  mov     rcx, r14; Src
0x180040a07  call    ?GetFileSystemType@@YAXPEBGPEAW4eFileSystemType@@@Z; GetFileSystemType(ushort const *,eFileSystemType *)
0x180040a0c  lea     r8, [rsp+0B8h+var_48]
0x180040a11  mov     edi, [rsp+0B8h+arg_20]
0x180040a18  mov     edx, edi
0x180040a1a  call    ?CreateVaultFileSystem@CVaultFactory@@QEAAKW4eFileSystemType@@PEAPEAUIVaultFileSystem@@@Z; CVaultFactory::CreateVaultFileSystem(eFileSystemType,IVaultFileSystem * *)
0x180040a1f  mov     ebx, eax
0x180040a21  test    eax, eax
0x180040a23  jz      short loc_180040A48
0x180040a25  lea     rcx, [rsp+0B8h+ThreadInformation]; ThreadInformation
0x180040a2a  call    ??1CVaultIntegrityLevel@@QEAA@XZ; CVaultIntegrityLevel::~CVaultIntegrityLevel(void)
0x180040a2f  nop
0x180040a30  lea     rcx, [rsp+0B8h+var_50]
0x180040a35  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180040a3a  nop
0x180040a3b  lea     rcx, [rsp+0B8h+var_68]
0x180040a40  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180040a45  nop
0x180040a46  jmp     short loc_1800409F5
0x180040a48  mov     rsi, [rsp+0B8h+var_48]
0x180040a4d  mov     rax, [rsi]
0x180040a50  mov     rcx, rsi
0x180040a53  mov     rax, [rax+10h]
0x180040a57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040a5c  mov     ebx, eax
0x180040a5e  test    eax, eax
0x180040a60  jz      short loc_180040A88
0x180040a62  lea     rcx, [rsp+0B8h+ThreadInformation]; ThreadInformation
0x180040a67  call    ??1CVaultIntegrityLevel@@QEAA@XZ; CVaultIntegrityLevel::~CVaultIntegrityLevel(void)
0x180040a6c  nop
0x180040a6d  lea     rcx, [rsp+0B8h+var_50]
0x180040a72  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180040a77  nop
0x180040a78  lea     rcx, [rsp+0B8h+var_68]
0x180040a7d  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180040a82  nop
0x180040a83  jmp     loc_1800409F5
0x180040a88  mov     rax, [rsi]
0x180040a8b  mov     rdx, r14
0x180040a8e  mov     rcx, rsi
0x180040a91  mov     rax, [rax+28h]
0x180040a95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040a9a  mov     ebx, eax
0x180040a9c  test    eax, eax
0x180040a9e  jz      short loc_180040ACD
0x180040aa0  cmp     eax, 0B7h
0x180040aa5  jz      short loc_180040ACD
0x180040aa7  lea     rcx, [rsp+0B8h+ThreadInformation]; ThreadInformation
0x180040aac  call    ??1CVaultIntegrityLevel@@QEAA@XZ; CVaultIntegrityLevel::~CVaultIntegrityLevel(void)
0x180040ab1  nop
0x180040ab2  lea     rcx, [rsp+0B8h+var_50]
0x180040ab7  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180040abc  nop
0x180040abd  lea     rcx, [rsp+0B8h+var_68]
0x180040ac2  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180040ac7  nop
0x180040ac8  jmp     loc_1800409F5
0x180040acd  mov     edx, 140h; uBytes
0x180040ad2  mov     ecx, 40h ; '@'; uFlags
0x180040ad7  call    cs:__imp_LocalAlloc
0x180040add  mov     [rsp+0B8h+var_70], rax
0x180040ae2  test    rax, rax
0x180040ae5  jnz     short loc_180040B0D
0x180040ae7  lea     rcx, [rsp+0B8h+ThreadInformation]; ThreadInformation
0x180040aec  call    ??1CVaultIntegrityLevel@@QEAA@XZ; CVaultIntegrityLevel::~CVaultIntegrityLevel(void)
0x180040af1  nop
0x180040af2  lea     rcx, [rsp+0B8h+var_50]
0x180040af7  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180040afc  nop
0x180040afd  lea     rcx, [rsp+0B8h+var_68]
0x180040b02  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180040b07  nop
0x180040b08  jmp     loc_180040C9F
0x180040b0d  mov     rcx, rax; this
0x180040b10  call    ??0CVaultFileStore@@AEAA@XZ; CVaultFileStore::CVaultFileStore(void)
0x180040b15  mov     rbx, rax
0x180040b18  lea     rcx, [rsp+0B8h+var_68]
0x180040b1d  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180040b22  mov     [rsp+0B8h+var_60], rbx
0x180040b27  mov     [rbx+130h], edi
0x180040b2d  mov     rcx, rbx; this
0x180040b30  call    ?InitializeStore@CVaultMemoryStore@@IEAAKXZ; CVaultMemoryStore::InitializeStore(void)
0x180040b35  mov     edi, eax
0x180040b37  test    eax, eax
0x180040b39  jz      short loc_180040B63
0x180040b3b  lea     rcx, [rsp+0B8h+ThreadInformation]; ThreadInformation
0x180040b40  call    ??1CVaultIntegrityLevel@@QEAA@XZ; CVaultIntegrityLevel::~CVaultIntegrityLevel(void)
0x180040b45  nop
0x180040b46  lea     rcx, [rsp+0B8h+var_50]
0x180040b4b  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180040b50  nop
0x180040b51  lea     rcx, [rsp+0B8h+var_68]
0x180040b56  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180040b5b  nop
0x180040b5c  mov     eax, edi
0x180040b5e  jmp     loc_180040CA4
0x180040b63  mov     rdx, r14; unsigned __int16 *
0x180040b66  mov     rcx, rbx; this
0x180040b69  call    ?InitializeVaultStorePath@CVaultFileStore@@AEAAKPEBG@Z; CVaultFileStore::InitializeVaultStorePath(ushort const *)
0x180040b6e  mov     edi, eax
0x180040b70  test    eax, eax
0x180040b72  jz      short loc_180040B97
0x180040b74  lea     rcx, [rsp+0B8h+ThreadInformation]; ThreadInformation
0x180040b79  call    ??1CVaultIntegrityLevel@@QEAA@XZ; CVaultIntegrityLevel::~CVaultIntegrityLevel(void)
0x180040b7e  nop
0x180040b7f  lea     rcx, [rsp+0B8h+var_50]
0x180040b84  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180040b89  nop
0x180040b8a  lea     rcx, [rsp+0B8h+var_68]
0x180040b8f  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180040b94  nop
0x180040b95  jmp     short loc_180040B5C
0x180040b97  mov     rax, [rsp+0B8h+arg_38]
0x180040b9f  mov     [rsp+0B8h+var_88], rax
0x180040ba4  mov     eax, [rsp+0B8h+arg_30]
0x180040bab  mov     [rsp+0B8h+var_90], eax
0x180040baf  mov     rax, [rsp+0B8h+arg_28]
0x180040bb7  mov     [rsp+0B8h+var_98], rax
0x180040bbc  mov     r9d, r15d
0x180040bbf  mov     r8, r12
0x180040bc2  mov     rdx, r13
0x180040bc5  mov     rcx, rbx
0x180040bc8  call    ?CreatePolicy@CVaultMemoryStore@@IEAAKPEBU_GUID@@PEAEKPEBGW4eVaultType@@PEAUVaultPolicy@@@Z; CVaultMemoryStore::CreatePolicy(_GUID const *,uchar *,ulong,ushort const *,eVaultType,VaultPolicy *)
0x180040bcd  mov     edi, eax
0x180040bcf  test    eax, eax
0x180040bd1  jnz     short loc_180040BE4
0x180040bd3  mov     rdx, rsi; struct IVaultFileSystem *
0x180040bd6  mov     rcx, rbx; this
0x180040bd9  call    ?SubmitPolicyToStore@CVaultFileStore@@AEAAKPEAUIVaultFileSystem@@@Z; CVaultFileStore::SubmitPolicyToStore(IVaultFileSystem *)
0x180040bde  mov     edi, eax
0x180040be0  test    eax, eax
0x180040be2  jz      short loc_180040C0A
0x180040be4  lea     rcx, [rsp+0B8h+ThreadInformation]; ThreadInformation
0x180040be9  call    ??1CVaultIntegrityLevel@@QEAA@XZ; CVaultIntegrityLevel::~CVaultIntegrityLevel(void)
0x180040bee  nop
0x180040bef  lea     rcx, [rsp+0B8h+var_50]
0x180040bf4  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180040bf9  nop
0x180040bfa  lea     rcx, [rsp+0B8h+var_68]
0x180040bff  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180040c04  nop
0x180040c05  jmp     loc_180040B5C
0x180040c0a  mov     rax, [rsi]
0x180040c0d  mov     rcx, rsi
0x180040c10  mov     rax, [rax+18h]
0x180040c14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040c19  mov     edi, eax
0x180040c1b  test    eax, eax
0x180040c1d  jz      short loc_180040C45
0x180040c1f  lea     rcx, [rsp+0B8h+ThreadInformation]; ThreadInformation
0x180040c24  call    ??1CVaultIntegrityLevel@@QEAA@XZ; CVaultIntegrityLevel::~CVaultIntegrityLevel(void)
0x180040c29  nop
0x180040c2a  lea     rcx, [rsp+0B8h+var_50]
0x180040c2f  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180040c34  nop
0x180040c35  lea     rcx, [rsp+0B8h+var_68]
0x180040c3a  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180040c3f  nop
0x180040c40  jmp     loc_180040B5C
0x180040c45  mov     [rsp+0B8h+var_60], 0
0x180040c4e  mov     rax, [rsp+0B8h+arg_40]
0x180040c56  mov     [rax], rbx
0x180040c59  lea     rcx, [rsp+0B8h+ThreadInformation]; ThreadInformation
0x180040c5e  call    ??1CVaultIntegrityLevel@@QEAA@XZ; CVaultIntegrityLevel::~CVaultIntegrityLevel(void)
0x180040c63  nop
0x180040c64  lea     rcx, [rsp+0B8h+var_50]
0x180040c69  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180040c6e  nop
0x180040c6f  lea     rcx, [rsp+0B8h+var_68]
0x180040c74  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180040c79  nop
0x180040c7a  xor     eax, eax
0x180040c7c  jmp     short loc_180040CA4
0x180040c7e  lea     rcx, [rsp+0B8h+ThreadInformation]; ThreadInformation
0x180040c83  call    ??1CVaultIntegrityLevel@@QEAA@XZ; CVaultIntegrityLevel::~CVaultIntegrityLevel(void)
0x180040c88  nop
0x180040c89  lea     rcx, [rsp+0B8h+var_50]
0x180040c8e  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180040c93  nop
0x180040c94  lea     rcx, [rsp+0B8h+var_68]
0x180040c99  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180040c9e  nop
0x180040c9f  mov     eax, 0Eh
0x180040ca4  add     rsp, 80h
0x180040cab  pop     r15
0x180040cad  pop     r14
0x180040caf  pop     r13
0x180040cb1  pop     r12
0x180040cb3  pop     rdi
0x180040cb4  pop     rsi
0x180040cb5  pop     rbx
0x180040cb6  retn
```
