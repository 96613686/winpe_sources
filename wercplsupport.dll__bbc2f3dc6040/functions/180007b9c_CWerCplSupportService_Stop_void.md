# CWerCplSupportService::Stop(void)

- ea: `0x180007b9c`
- end: `0x180007c95`
- name: `?Stop@CWerCplSupportService@@AEAAXXZ`
- size: `249`
- prototype: `void __fastcall(CWerCplSupportService *__hidden this)`
- caller_count: `2`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000773c`
- `0x180007b90`

## callees

- `0x180002850`
- `0x180006c9c`
- `0x180007498`
- `0x180007b9c`
- `0x180007c9c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoDisconnectObject` at `0x180007c10`
- `api-ms-win-core-com-l1-1-0!CoDisconnectObject` at `0x180007c10`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180007bf7`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180007bf7`
- `api-ms-win-core-com-l1-1-0!CoRevokeClassObject` at `0x180007c18`
- `api-ms-win-core-com-l1-1-0!CoRevokeClassObject` at `0x180007c18`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180007c58`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180007c58`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007ba9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007ba9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007bed`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007bed`

## pseudocode

```c
void __fastcall CWerCplSupportService::Stop(struct _RTL_CRITICAL_SECTION *this)
{
  HRESULT v2; // eax
  ULONG_PTR SpinCount; // rcx
  DWORD v4; // ebx
  HRESULT v5; // eax

  EnterCriticalSection(this);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_e2c3f9fb2f8c3c7f26251029e3f227c5_Traceguids);
  CWerCplSupportService::_SetServiceStatus((CWerCplSupportService *)this, 3u);
  LeaveCriticalSection(this);
  v2 = CoInitializeEx(0, 0);
  if ( v2 < 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        11,
        WPP_e2c3f9fb2f8c3c7f26251029e3f227c5_Traceguids,
        (unsigned int)v2);
  }
  else
  {
    SpinCount = this[1].SpinCount;
    v4 = _InterlockedExchange((volatile __int32 *)(SpinCount + 8), 0);
    if ( v4 )
    {
      CoDisconnectObject((LPUNKNOWN)SpinCount, 0);
      v5 = CoRevokeClassObject(v4);
      if ( v5 < 0
        && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          15,
          WPP_01f8fd716d603d43032f2a74c7bf788f_Traceguids,
          (unsigned int)v5);
      }
    }
    CObjectManager::DisconnectObjects((CObjectManager *)&CObjectManager::ms_instance);
    CoUninitialize();
  }
}

```

## disassembly

```asm
0x180007b9c  mov     [rsp+arg_0], rbx
0x180007ba1  push    rdi
0x180007ba2  sub     rsp, 20h
0x180007ba6  mov     rbx, rcx
0x180007ba9  call    cs:__imp_EnterCriticalSection
0x180007baf  mov     rcx, cs:WPP_GLOBAL_Control
0x180007bb6  lea     rdi, WPP_GLOBAL_Control
0x180007bbd  cmp     rcx, rdi
0x180007bc0  jz      short loc_180007BDD
0x180007bc2  test    byte ptr [rcx+1Ch], 4
0x180007bc6  jz      short loc_180007BDD
0x180007bc8  mov     rcx, [rcx+10h]
0x180007bcc  lea     r8, WPP_e2c3f9fb2f8c3c7f26251029e3f227c5_Traceguids
0x180007bd3  mov     edx, 0Ah
0x180007bd8  call    WPP_SF_
0x180007bdd  mov     edx, 3; unsigned int
0x180007be2  mov     rcx, rbx; this
0x180007be5  call    ?_SetServiceStatus@CWerCplSupportService@@AEAAXKK@Z; CWerCplSupportService::_SetServiceStatus(ulong,ulong)
0x180007bea  mov     rcx, rbx; lpCriticalSection
0x180007bed  call    cs:__imp_LeaveCriticalSection
0x180007bf3  xor     edx, edx; dwCoInit
0x180007bf5  xor     ecx, ecx; pvReserved
0x180007bf7  call    cs:__imp_CoInitializeEx
0x180007bfd  test    eax, eax
0x180007bff  js      short loc_180007C60
0x180007c01  mov     rcx, [rbx+48h]; pUnk
0x180007c05  xor     ebx, ebx
0x180007c07  xchg    ebx, [rcx+8]
0x180007c0a  test    ebx, ebx
0x180007c0c  jz      short loc_180007C4C
0x180007c0e  xor     edx, edx; dwReserved
0x180007c10  call    cs:__imp_CoDisconnectObject
0x180007c16  mov     ecx, ebx; dwRegister
0x180007c18  call    cs:__imp_CoRevokeClassObject
0x180007c1e  test    eax, eax
0x180007c20  jns     short loc_180007C4C
0x180007c22  mov     rcx, cs:WPP_GLOBAL_Control
0x180007c29  cmp     rcx, rdi
0x180007c2c  jz      short loc_180007C4C
0x180007c2e  test    byte ptr [rcx+1Ch], 1
0x180007c32  jz      short loc_180007C4C
0x180007c34  mov     rcx, [rcx+10h]
0x180007c38  lea     r8, WPP_01f8fd716d603d43032f2a74c7bf788f_Traceguids
0x180007c3f  mov     edx, 0Fh
0x180007c44  mov     r9d, eax
0x180007c47  call    WPP_SF_d
0x180007c4c  lea     rcx, ?ms_instance@CObjectManager@@1V1@A; this
0x180007c53  call    ?DisconnectObjects@CObjectManager@@QEAAXXZ; CObjectManager::DisconnectObjects(void)
0x180007c58  call    cs:__imp_CoUninitialize
0x180007c5e  jmp     short loc_180007C8A
0x180007c60  mov     rcx, cs:WPP_GLOBAL_Control
0x180007c67  cmp     rcx, rdi
0x180007c6a  jz      short loc_180007C8A
0x180007c6c  test    byte ptr [rcx+1Ch], 1
0x180007c70  jz      short loc_180007C8A
0x180007c72  mov     rcx, [rcx+10h]
0x180007c76  lea     r8, WPP_e2c3f9fb2f8c3c7f26251029e3f227c5_Traceguids
0x180007c7d  mov     edx, 0Bh
0x180007c82  mov     r9d, eax
0x180007c85  call    WPP_SF_d
0x180007c8a  mov     rbx, [rsp+28h+arg_0]
0x180007c8f  add     rsp, 20h
0x180007c93  pop     rdi
0x180007c94  retn
```
