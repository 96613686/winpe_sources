# WdsProviderShutdown(void *)

- ea: `0x180009130`
- end: `0x180009257`
- name: `?WdsProviderShutdown@@YAKPEAX@Z`
- size: `295`
- prototype: `unsigned int __fastcall(void *)`
- caller_count: `0`
- callee_count: `11`
- tags: `file_ops, authz_impersonation, loader_planting`

## callees

- `0x180005a4c`
- `0x180008738`
- `0x1800088f0`
- `0x180009130`
- `0x18000a97c`
- `0x18000aed0`
- `0x180018120`
- `0x18001a9a8`
- `0x180024840`
- `0x180025850`
- `0x180025c44`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800091db`
- `KERNEL32!GetLastError` at `0x1800091db`
- `KERNEL32!DeleteCriticalSection` at `0x1800091bd`
- `KERNEL32!DeleteCriticalSection` at `0x180009228`
- `KERNEL32!DeleteCriticalSection` at `0x1800091bd`
- `KERNEL32!DeleteCriticalSection` at `0x180009228`
- `ADVAPI32!CryptReleaseContext` at `0x1800091d1`
- `ADVAPI32!CryptReleaseContext` at `0x1800091d1`
- `WS2_32!__imp_WSACleanup` at `0x18000916d`
- `WS2_32!__imp_WSACleanup` at `0x18000916d`
- `WDSCSL!WdsClientFreeLibrary` at `0x180009157`
- `WDSCSL!WdsClientFreeLibrary` at `0x180009157`

## pseudocode

```c
__int64 __fastcall WdsProviderShutdown(void *a1)
{
  CMRSWLock *v1; // rbx
  HCRYPTPROV v2; // rcx
  DWORD LastError; // eax
  const char *v4; // rdx

  v1 = qword_1800336E8;
  if ( qword_1800336E8 )
  {
    CMulticastServer::Shutdown(qword_1800336E8);
    if ( *((_DWORD *)v1 + 283) )
    {
      WdsClientFreeLibrary();
      *((_DWORD *)v1 + 283) = 0;
    }
    if ( *((_DWORD *)v1 + 282) )
    {
      WSACleanup();
      *((_DWORD *)v1 + 282) = 0;
    }
    CDynArray<unsigned short *,CDeallocateString>::Clear((char *)v1 + 1104);
    *((_QWORD *)v1 + 135) = &CCryptSignKey::`vftable';
    CCryptKey::DestroyKey((CMRSWLock *)((char *)v1 + 1080));
    *((_QWORD *)v1 + 108) = &CMulticastNotification::`vftable';
    CChildCount<CMulticastNotification>::~CChildCount<CMulticastNotification>((char *)v1 + 944);
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)v1 + 872));
    v2 = *((_QWORD *)v1 + 107);
    if ( v2 )
    {
      if ( !CryptReleaseContext(v2, 0) )
      {
        LastError = GetLastError();
        ElValidateWin32(LastError, v4, "base\\eco\\wds\\wdslib\\crypt\\lib\\cryptstore.cpp", 0xBBu);
      }
      *((_QWORD *)v1 + 107) = 0;
    }
    CBandwidthManager::~CBandwidthManager((CMRSWLock *)((char *)v1 + 560));
    CContentProvidersHandler::Shutdown((CMRSWLock *)((char *)v1 + 536));
    CTimer<CMulticastServer>::~CTimer<CMulticastServer>((__int64)v1 + 480);
    DeleteCriticalSection((LPCRITICAL_SECTION)v1 + 6);
    CMRSWLock::~CMRSWLock((CMRSWLock *)((char *)v1 + 120));
    CMRSWLock::~CMRSWLock(v1);
    operator delete(v1);
    qword_1800336E8 = 0;
  }
  return 0;
}

```

## disassembly

```asm
0x180009130  push    rbx
0x180009132  sub     rsp, 20h
0x180009136  mov     rbx, cs:qword_1800336E8
0x18000913d  test    rbx, rbx
0x180009140  jz      loc_18000924F
0x180009146  mov     rcx, rbx; this
0x180009149  call    ?Shutdown@CMulticastServer@@QEAAKXZ; CMulticastServer::Shutdown(void)
0x18000914e  cmp     dword ptr [rbx+46Ch], 0
0x180009155  jz      short loc_180009164
0x180009157  call    cs:__imp_WdsClientFreeLibrary
0x18000915d  and     dword ptr [rbx+46Ch], 0
0x180009164  cmp     dword ptr [rbx+468h], 0
0x18000916b  jz      short loc_18000917A
0x18000916d  call    cs:__imp_WSACleanup
0x180009173  and     dword ptr [rbx+468h], 0
0x18000917a  lea     rcx, [rbx+450h]
0x180009181  call    ?Clear@?$CDynArray@PEAGVCDeallocateString@@@@QEAAXXZ; CDynArray<ushort *,CDeallocateString>::Clear(void)
0x180009186  lea     rcx, [rbx+438h]; this
0x18000918d  lea     rax, ??_7CCryptSignKey@@6B@; const CCryptSignKey::`vftable'
0x180009194  mov     [rcx], rax
0x180009197  call    ?DestroyKey@CCryptKey@@QEAAKXZ; CCryptKey::DestroyKey(void)
0x18000919c  lea     rax, ??_7CMulticastNotification@@6B@; const CMulticastNotification::`vftable'
0x1800091a3  lea     rcx, [rbx+3B0h]
0x1800091aa  mov     [rbx+360h], rax
0x1800091b1  call    ??1?$CChildCount@VCMulticastNotification@@@@QEAA@XZ; CChildCount<CMulticastNotification>::~CChildCount<CMulticastNotification>(void)
0x1800091b6  lea     rcx, [rbx+368h]; lpCriticalSection
0x1800091bd  call    cs:__imp_DeleteCriticalSection
0x1800091c3  mov     rcx, [rbx+358h]; hProv
0x1800091ca  test    rcx, rcx
0x1800091cd  jz      short loc_1800091FD
0x1800091cf  xor     edx, edx; dwFlags
0x1800091d1  call    cs:__imp_CryptReleaseContext
0x1800091d7  test    eax, eax
0x1800091d9  jnz     short loc_1800091F5
0x1800091db  call    cs:__imp_GetLastError
0x1800091e1  mov     r9d, 0BBh; unsigned int
0x1800091e7  lea     r8, aBaseEcoWdsWdsl_3; "base\\eco\\wds\\wdslib\\crypt\\lib\\cry"...
0x1800091ee  mov     ecx, eax; unsigned int
0x1800091f0  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x1800091f5  and     qword ptr [rbx+358h], 0
0x1800091fd  lea     rcx, [rbx+230h]; this
0x180009204  call    ??1CBandwidthManager@@QEAA@XZ; CBandwidthManager::~CBandwidthManager(void)
0x180009209  lea     rcx, [rbx+218h]; this
0x180009210  call    ?Shutdown@CContentProvidersHandler@@QEAAKXZ; CContentProvidersHandler::Shutdown(void)
0x180009215  lea     rcx, [rbx+1E0h]
0x18000921c  call    ??1?$CTimer@VCMulticastServer@@@@QEAA@XZ; CTimer<CMulticastServer>::~CTimer<CMulticastServer>(void)
0x180009221  lea     rcx, [rbx+0F0h]; lpCriticalSection
0x180009228  call    cs:__imp_DeleteCriticalSection
0x18000922e  lea     rcx, [rbx+78h]; this
0x180009232  call    ??1CMRSWLock@@QEAA@XZ; CMRSWLock::~CMRSWLock(void)
0x180009237  mov     rcx, rbx; this
0x18000923a  call    ??1CMRSWLock@@QEAA@XZ; CMRSWLock::~CMRSWLock(void)
0x18000923f  mov     rcx, rbx; void *
0x180009242  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180009247  and     cs:qword_1800336E8, 0
0x18000924f  xor     eax, eax
0x180009251  add     rsp, 20h
0x180009255  pop     rbx
0x180009256  retn
```
