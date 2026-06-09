# CSslCredManager::FreeCredentialManager(void)

- ea: `0x180071e90`
- end: `0x180071f2a`
- name: `?FreeCredentialManager@CSslCredManager@@QEAAXXZ`
- size: `154`
- prototype: `void __fastcall(CSslCredManager *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180054884`

## callees

- `0x180071e90`
- `0x180091010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180071eb9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180071ee4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180071eb9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180071ee4`
- `ntdll!RtlDeleteCriticalSection` at `0x180071efa`
- `ntdll!RtlDeleteCriticalSection` at `0x180071efa`
- `CRYPT32!CertCloseStore` at `0x180071ef0`
- `CRYPT32!CertCloseStore` at `0x180071ef0`
- `CRYPT32!CertControlStore` at `0x180071edb`
- `CRYPT32!CertControlStore` at `0x180071edb`
- `USERENV!UnregisterGPNotification` at `0x180071eaf`
- `USERENV!UnregisterGPNotification` at `0x180071eaf`

## pseudocode

```c
void __fastcall CSslCredManager::FreeCredentialManager(CSslCredManager *this)
{
  CSslCredManager *v1; // rbx
  void *v2; // rcx
  void *v3; // rcx
  __int64 v4; // rax

  v1 = CSslCredManager::m_pCredManager;
  if ( CSslCredManager::m_pCredManager )
  {
    v2 = (void *)*((_QWORD *)CSslCredManager::m_pCredManager + 8);
    if ( v2 )
    {
      UnregisterGPNotification(v2);
      CloseHandle(*((HANDLE *)v1 + 8));
    }
    v3 = (void *)*((_QWORD *)v1 + 9);
    if ( v3 )
    {
      if ( *((_QWORD *)v1 + 10) )
      {
        CertControlStore(v3, 0, 5u, (char *)v1 + 80);
        CloseHandle(*((HANDLE *)v1 + 10));
      }
      CertCloseStore(*((HCERTSTORE *)v1 + 9), 0);
    }
    RtlDeleteCriticalSection((PRTL_CRITICAL_SECTION)((char *)v1 + 8));
    v4 = *(_QWORD *)v1;
    CSslCredManager::m_pCredManager = 0;
    (*(void (__fastcall **)(CSslCredManager *, __int64))(v4 + 8))(v1, 1);
  }
}

```

## disassembly

```asm
0x180071e90  mov     [rsp+arg_0], rbx
0x180071e95  push    rdi
0x180071e96  sub     rsp, 20h
0x180071e9a  mov     rbx, cs:?m_pCredManager@CSslCredManager@@0PEAV1@EA; CSslCredManager * CSslCredManager::m_pCredManager
0x180071ea1  test    rbx, rbx
0x180071ea4  jz      short loc_180071F1F
0x180071ea6  mov     rcx, [rbx+40h]; hEvent
0x180071eaa  test    rcx, rcx
0x180071ead  jz      short loc_180071EBF
0x180071eaf  call    cs:__imp_UnregisterGPNotification
0x180071eb5  mov     rcx, [rbx+40h]; hObject
0x180071eb9  call    cs:__imp_CloseHandle
0x180071ebf  mov     rcx, [rbx+48h]; hCertStore
0x180071ec3  test    rcx, rcx
0x180071ec6  jz      short loc_180071EF6
0x180071ec8  lea     rdi, [rbx+50h]
0x180071ecc  cmp     qword ptr [rdi], 0
0x180071ed0  jz      short loc_180071EEA
0x180071ed2  xor     edx, edx; dwFlags
0x180071ed4  mov     r9, rdi; pvCtrlPara
0x180071ed7  lea     r8d, [rdx+5]; dwCtrlType
0x180071edb  call    cs:__imp_CertControlStore
0x180071ee1  mov     rcx, [rdi]; hObject
0x180071ee4  call    cs:__imp_CloseHandle
0x180071eea  mov     rcx, [rbx+48h]; hCertStore
0x180071eee  xor     edx, edx; dwFlags
0x180071ef0  call    cs:__imp_CertCloseStore
0x180071ef6  lea     rcx, [rbx+8]; CriticalSection
0x180071efa  call    cs:__imp_RtlDeleteCriticalSection
0x180071f00  mov     rax, [rbx]
0x180071f03  mov     edx, 1
0x180071f08  mov     rcx, rbx
0x180071f0b  mov     cs:?m_pCredManager@CSslCredManager@@0PEAV1@EA, 0; CSslCredManager * CSslCredManager::m_pCredManager
0x180071f16  mov     rax, [rax+8]
0x180071f1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180071f1f  mov     rbx, [rsp+28h+arg_0]
0x180071f24  add     rsp, 20h
0x180071f28  pop     rdi
0x180071f29  retn
```
