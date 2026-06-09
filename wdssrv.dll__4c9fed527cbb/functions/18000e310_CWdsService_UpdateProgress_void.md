# CWdsService::UpdateProgress(void)

- ea: `0x18000e310`
- end: `0x18000e357`
- name: `?UpdateProgress@CWdsService@@QEAAKXZ`
- size: `71`
- prototype: `unsigned int __fastcall(CWdsService *__hidden this)`
- caller_count: `4`
- callee_count: `2`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1800042f0`
- `0x180009da4`
- `0x18000d380`
- `0x180011dc0`

## callees

- `0x18000e310`
- `0x18000f0dc`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000e333`
- `KERNEL32!GetLastError` at `0x18000e333`
- `WdsServerCommonLib!?SetServiceStatus@CService@@SAHPEAUSERVICE_STATUS_HANDLE__@@PEAU_SERVICE_STATUS@@@Z` at `0x18000e323`
- `WdsServerCommonLib!?SetServiceStatus@CService@@SAHPEAUSERVICE_STATUS_HANDLE__@@PEAU_SERVICE_STATUS@@@Z` at `0x18000e323`

## pseudocode

```c
__int64 __fastcall CWdsService::UpdateProgress(CWdsService *this)
{
  unsigned int v1; // ebx
  DWORD LastError; // eax
  __int64 v3; // rdx
  __int64 v4; // r8

  ++*((_DWORD *)this + 7);
  v1 = 0;
  if ( !CService::SetServiceStatus(
          *((struct SERVICE_STATUS_HANDLE__ **)this + 5),
          (struct _SERVICE_STATUS *)((char *)this + 8)) )
  {
    LastError = GetLastError();
    return (unsigned int)ElValidateWin32_0(LastError, v3, v4, 430);
  }
  return v1;
}

```

## disassembly

```asm
0x18000e310  push    rbx
0x18000e312  sub     rsp, 20h
0x18000e316  inc     dword ptr [rcx+1Ch]
0x18000e319  lea     rdx, [rcx+8]
0x18000e31d  mov     rcx, [rcx+28h]
0x18000e321  xor     ebx, ebx
0x18000e323  call    cs:__imp_?SetServiceStatus@CService@@SAHPEAUSERVICE_STATUS_HANDLE__@@PEAU_SERVICE_STATUS@@@Z; CService::SetServiceStatus(SERVICE_STATUS_HANDLE__ *,_SERVICE_STATUS *)
0x18000e32a  nop     dword ptr [rax+rax+00h]
0x18000e32f  test    eax, eax
0x18000e331  jnz     short loc_18000E34E
0x18000e333  call    cs:__imp_GetLastError
0x18000e33a  nop     dword ptr [rax+rax+00h]
0x18000e33f  mov     ecx, eax
0x18000e341  mov     r9d, 1AEh
0x18000e347  call    ElValidateWin32_0
0x18000e34c  mov     ebx, eax
0x18000e34e  mov     eax, ebx
0x18000e350  add     rsp, 20h
0x18000e354  pop     rbx
0x18000e355  retn
```
