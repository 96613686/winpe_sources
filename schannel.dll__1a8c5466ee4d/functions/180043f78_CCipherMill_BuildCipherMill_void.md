# CCipherMill::BuildCipherMill(void)

- ea: `0x180043f78`
- end: `0x180044089`
- name: `?BuildCipherMill@CCipherMill@@QEAAKXZ`
- size: `273`
- prototype: `unsigned int __fastcall(CCipherMill *__hidden this)`
- caller_count: `5`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180025c38`
- `0x180043f30`
- `0x1800539f4`
- `0x180069730`
- `0x180069900`

## callees

- `0x180043f78`
- `0x180044090`
- `0x180044390`
- `0x180044528`
- `0x180057ec0`
- `0x180071f30`

## import_xrefs

- `ntdll!RtlAcquireResourceExclusive` at `0x180043fc2`
- `ntdll!RtlAcquireResourceExclusive` at `0x180043fc2`
- `ntdll!RtlReleaseResource` at `0x180043fe6`
- `ntdll!RtlReleaseResource` at `0x180044017`
- `ntdll!RtlReleaseResource` at `0x180043fe6`
- `ntdll!RtlReleaseResource` at `0x180044017`
- `ncrypt!NCryptOpenStorageProvider` at `0x180044074`
- `ncrypt!NCryptOpenStorageProvider` at `0x180044074`

## pseudocode

```c
__int64 __fastcall CCipherMill::BuildCipherMill(CCipherMill *this)
{
  CCipherMill *v1; // rcx
  CCipherMill *v2; // rcx
  unsigned int ProviderList; // ebx
  CCipherMill *v5; // [rsp+40h] [rbp+8h] BYREF

  v5 = this;
  LOBYTE(v5) = 0;
  if ( !g_cCipherMill )
    return 14;
  if ( CSessionCacheManager::m_pSessionCacheManager )
    CSessionCacheManager::PurgeCacheEntries(CSessionCacheManager::m_pSessionCacheManager, 0x30000u, 0, 0, 0);
  RtlAcquireResourceExclusive(&Resource, 1u);
  CCipherMill::ClearCipherMill(v1, 0);
  ProviderList = CCipherMill::LoadProviderList(v2, (unsigned __int8 *)&v5);
  if ( ProviderList
    || !hProvider
    && (ProviderList = NCryptOpenStorageProvider(&hProvider, L"Microsoft Software Key Storage Provider", 0)) != 0
    || (ProviderList = CCipherMill::LoadCipherTables((CCipherMill *)&g_cCipherMill)) != 0 )
  {
    RtlReleaseResource(&Resource);
  }
  else
  {
    RtlReleaseResource(&Resource);
    if ( CSessionCacheManager::m_pSessionCacheManager )
      CSessionCacheManager::PurgeCacheEntries(CSessionCacheManager::m_pSessionCacheManager, 0x30000u, 0, 0, 0);
    if ( (_BYTE)v5 )
    {
      if ( CSslCredManager::m_pCredManager )
        CSslCredManager::NotifyProviderChange(CSslCredManager::m_pCredManager);
    }
  }
  return ProviderList;
}

```

## disassembly

```asm
0x180043f78  mov     [rsp+arg_0], rcx
0x180043f7d  push    rbx
0x180043f7e  sub     rsp, 30h
0x180043f82  cmp     cs:?g_cCipherMill@@3VCCipherMill@@A, 0; CCipherMill g_cCipherMill
0x180043f89  mov     byte ptr [rsp+38h+arg_0], 0
0x180043f8e  jz      loc_18004405C
0x180043f94  mov     rcx, cs:?m_pSessionCacheManager@CSessionCacheManager@@0PEAV1@EA; this
0x180043f9b  test    rcx, rcx
0x180043f9e  jz      short loc_180043FB9
0x180043fa0  xor     r9d, r9d; unsigned int
0x180043fa3  mov     [rsp+38h+var_18], 0; unsigned __int16 *
0x180043fac  xor     r8d, r8d; struct _LUID *
0x180043faf  mov     edx, 30000h; unsigned int
0x180043fb4  call    ?PurgeCacheEntries@CSessionCacheManager@@QEAAKKPEAU_LUID@@KPEBG@Z; CSessionCacheManager::PurgeCacheEntries(ulong,_LUID *,ulong,ushort const *)
0x180043fb9  mov     dl, 1; Wait
0x180043fbb  lea     rcx, Resource; Resource
0x180043fc2  call    cs:__imp_RtlAcquireResourceExclusive
0x180043fc8  xor     edx, edx; unsigned __int8
0x180043fca  call    ?ClearCipherMill@CCipherMill@@AEAAXE@Z; CCipherMill::ClearCipherMill(uchar)
0x180043fcf  lea     rdx, [rsp+38h+arg_0]; unsigned __int8 *
0x180043fd4  call    ?LoadProviderList@CCipherMill@@AEAAKPEAE@Z; CCipherMill::LoadProviderList(uchar *)
0x180043fd9  mov     ebx, eax
0x180043fdb  test    eax, eax
0x180043fdd  jz      short loc_180043FF4
0x180043fdf  lea     rcx, Resource; Resource
0x180043fe6  call    cs:__imp_RtlReleaseResource
0x180043fec  mov     eax, ebx
0x180043fee  add     rsp, 30h
0x180043ff2  pop     rbx
0x180043ff3  retn
0x180043ff4  cmp     cs:hProvider, 0
0x180043ffc  jz      short loc_180044063
0x180043ffe  lea     rcx, ?g_cCipherMill@@3VCCipherMill@@A; this
0x180044005  call    ?LoadCipherTables@CCipherMill@@AEAAKXZ; CCipherMill::LoadCipherTables(void)
0x18004400a  mov     ebx, eax
0x18004400c  test    eax, eax
0x18004400e  jnz     short loc_180043FDF
0x180044010  lea     rcx, Resource; Resource
0x180044017  call    cs:__imp_RtlReleaseResource
0x18004401d  mov     rcx, cs:?m_pSessionCacheManager@CSessionCacheManager@@0PEAV1@EA; this
0x180044024  test    rcx, rcx
0x180044027  jz      short loc_180044042
0x180044029  xor     r9d, r9d; unsigned int
0x18004402c  mov     [rsp+38h+var_18], 0; unsigned __int16 *
0x180044035  xor     r8d, r8d; struct _LUID *
0x180044038  mov     edx, 30000h; unsigned int
0x18004403d  call    ?PurgeCacheEntries@CSessionCacheManager@@QEAAKKPEAU_LUID@@KPEBG@Z; CSessionCacheManager::PurgeCacheEntries(ulong,_LUID *,ulong,ushort const *)
0x180044042  cmp     byte ptr [rsp+38h+arg_0], 0
0x180044047  jz      short loc_180043FEC
0x180044049  mov     rcx, cs:?m_pCredManager@CSslCredManager@@0PEAV1@EA; this
0x180044050  test    rcx, rcx
0x180044053  jz      short loc_180043FEC
0x180044055  call    ?NotifyProviderChange@CSslCredManager@@QEAAKXZ; CSslCredManager::NotifyProviderChange(void)
0x18004405a  jmp     short loc_180043FEC
0x18004405c  mov     eax, 0Eh
0x180044061  jmp     short loc_180043FEE
0x180044063  xor     r8d, r8d; dwFlags
0x180044066  lea     rdx, pszProviderName; "Microsoft Software Key Storage Provider"
0x18004406d  lea     rcx, hProvider; phProvider
0x180044074  call    cs:__imp_NCryptOpenStorageProvider
0x18004407a  mov     ebx, eax
0x18004407c  test    eax, eax
0x18004407e  jnz     loc_180043FDF
0x180044084  jmp     loc_180043FFE
```
