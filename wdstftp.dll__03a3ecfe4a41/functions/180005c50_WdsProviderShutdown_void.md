# WdsProviderShutdown(void *)

- ea: `0x180005c50`
- end: `0x180005d3c`
- name: `?WdsProviderShutdown@@YAKPEAX@Z`
- size: `236`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, authz_impersonation`

## callees

- `0x180001754`
- `0x180002ccc`
- `0x18000362c`
- `0x180005c50`
- `0x1800094bc`
- `0x18000a960`
- `0x18000a9a8`
- `0x18003a628`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180005cc5`
- `KERNEL32!DeleteCriticalSection` at `0x180005cef`
- `KERNEL32!DeleteCriticalSection` at `0x180005d0b`
- `KERNEL32!DeleteCriticalSection` at `0x180005cc5`
- `KERNEL32!DeleteCriticalSection` at `0x180005cef`
- `KERNEL32!DeleteCriticalSection` at `0x180005d0b`
- `WDSCSL!WdsClientFreeLibrary` at `0x180005c7b`
- `WDSCSL!WdsClientFreeLibrary` at `0x180005c7b`
- `WS2_32!__imp_WSACleanup` at `0x180005c97`
- `WS2_32!__imp_WSACleanup` at `0x180005c97`

## pseudocode

```c
__int64 __fastcall WdsProviderShutdown(void *a1)
{
  LPCRITICAL_SECTION v1; // rdi

  v1 = lpCriticalSection;
  if ( lpCriticalSection )
  {
    CTftpServer::Shutdown((CTftpServer *)lpCriticalSection);
    if ( HIDWORD(v1[85].LockSemaphore) )
    {
      WdsClientFreeLibrary();
      HIDWORD(v1[85].LockSemaphore) = 0;
    }
    if ( LODWORD(v1[85].LockSemaphore) )
    {
      WSACleanup();
      LODWORD(v1[85].LockSemaphore) = 0;
    }
    CTftpReadFileManager::Shutdown((LPCRITICAL_SECTION)((char *)v1 + 576));
    CTimer<CTftpSession>::Delete(&v1[16]);
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)v1 + 576));
    CClientContext::~CClientContext((CClientContext *)&v1[8]);
    CFolderFilter::Shutdown((LPCRITICAL_SECTION)((char *)v1 + 264));
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)v1 + 264));
    CTimer<CTftpSession>::Delete(&v1[5]);
    DeleteCriticalSection(v1 + 3);
    CMRSWLock::~CMRSWLock((CMRSWLock *)v1);
    operator delete(v1);
    lpCriticalSection = 0;
  }
  return 0;
}

```

## disassembly

```asm
0x180005c50  mov     [rsp+arg_0], rbx
0x180005c55  push    rdi
0x180005c56  sub     rsp, 20h
0x180005c5a  mov     rdi, cs:lpCriticalSection
0x180005c61  test    rdi, rdi
0x180005c64  jz      loc_180005D2F
0x180005c6a  mov     rcx, rdi; this
0x180005c6d  call    ?Shutdown@CTftpServer@@QEAAKXZ; CTftpServer::Shutdown(void)
0x180005c72  cmp     dword ptr [rdi+0D64h], 0
0x180005c79  jz      short loc_180005C8E
0x180005c7b  call    cs:__imp_WdsClientFreeLibrary
0x180005c82  nop     dword ptr [rax+rax+00h]
0x180005c87  and     dword ptr [rdi+0D64h], 0
0x180005c8e  cmp     dword ptr [rdi+0D60h], 0
0x180005c95  jz      short loc_180005CAA
0x180005c97  call    cs:__imp_WSACleanup
0x180005c9e  nop     dword ptr [rax+rax+00h]
0x180005ca3  and     dword ptr [rdi+0D60h], 0
0x180005caa  lea     rbx, [rdi+240h]
0x180005cb1  mov     rcx, rbx; lpCriticalSection
0x180005cb4  call    ?Shutdown@CTftpReadFileManager@@QEAAKXZ; CTftpReadFileManager::Shutdown(void)
0x180005cb9  lea     rcx, [rbx+40h]
0x180005cbd  call    ?Delete@?$CTimer@VCTftpSession@@@@AEAAXXZ; CTimer<CTftpSession>::Delete(void)
0x180005cc2  mov     rcx, rbx; lpCriticalSection
0x180005cc5  call    cs:__imp_DeleteCriticalSection
0x180005ccc  nop     dword ptr [rax+rax+00h]
0x180005cd1  lea     rcx, [rdi+140h]; this
0x180005cd8  call    ??1CClientContext@@QEAA@XZ; CClientContext::~CClientContext(void)
0x180005cdd  lea     rbx, [rdi+108h]
0x180005ce4  mov     rcx, rbx; lpCriticalSection
0x180005ce7  call    ?Shutdown@CFolderFilter@@QEAAKXZ; CFolderFilter::Shutdown(void)
0x180005cec  mov     rcx, rbx; lpCriticalSection
0x180005cef  call    cs:__imp_DeleteCriticalSection
0x180005cf6  nop     dword ptr [rax+rax+00h]
0x180005cfb  lea     rcx, [rdi+0C8h]
0x180005d02  call    ?Delete@?$CTimer@VCTftpSession@@@@AEAAXXZ; CTimer<CTftpSession>::Delete(void)
0x180005d07  lea     rcx, [rdi+78h]; lpCriticalSection
0x180005d0b  call    cs:__imp_DeleteCriticalSection
0x180005d12  nop     dword ptr [rax+rax+00h]
0x180005d17  mov     rcx, rdi; this
0x180005d1a  call    ??1CMRSWLock@@QEAA@XZ; CMRSWLock::~CMRSWLock(void)
0x180005d1f  mov     rcx, rdi; void *
0x180005d22  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180005d27  and     cs:lpCriticalSection, 0
0x180005d2f  mov     rbx, [rsp+28h+arg_0]
0x180005d34  xor     eax, eax
0x180005d36  add     rsp, 20h
0x180005d3a  pop     rdi
0x180005d3b  retn
```
