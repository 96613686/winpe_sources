# CElsServiceInstance::Initialize(_GUID)

- ea: `0x18007ae9c`
- end: `0x18007af67`
- name: `?Initialize@CElsServiceInstance@@IEAAJU_GUID@@@Z`
- size: `203`
- prototype: `__int64 __fastcall(PMAPPING_SERVICE_INFO *prgServices, struct _GUID *__struct_ptr)`
- caller_count: `2`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x180078c80`
- `0x18007a948`

## callees

- `0x18002b1b0`
- `0x18002bc68`
- `0x18007ae9c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18007aedb`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18007aedb`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18007af3a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18007af3a`
- `ext-ms-win-els-elscore-l1-1-0!MappingGetServices` at `0x18007af16`
- `ext-ms-win-els-elscore-l1-1-0!MappingGetServices` at `0x18007af16`

## pseudocode

```c
__int64 __fastcall CElsServiceInstance::Initialize(PMAPPING_SERVICE_INFO *prgServices, struct _GUID *a2)
{
  HRESULT Services; // edi
  _MAPPING_ENUM_OPTIONS pOptions; // [rsp+20h] [rbp-78h] BYREF
  __int128 v6; // [rsp+70h] [rbp-28h] BYREF

  Services = 0;
  v6 = (__int128)*a2;
  if ( !*((_BYTE *)prgServices + 12) )
  {
    AcquireSRWLockExclusive(&s_srwElsServiceLock);
    if ( !*((_BYTE *)prgServices + 12) )
    {
      memset_0(&pOptions, 0, sizeof(pOptions));
      pOptions.Size = 80;
      pOptions.pGuid = (GUID *)&v6;
      Services = MappingGetServices(&pOptions, prgServices, (DWORD *)prgServices + 2);
      if ( Services >= 0 )
      {
        if ( *((_DWORD *)prgServices + 2) )
          *((_BYTE *)prgServices + 12) = 1;
        else
          Services = -2147467259;
      }
    }
    ReleaseSRWLockExclusive(&s_srwElsServiceLock);
  }
  return (unsigned int)Services;
}

```

## disassembly

```asm
0x18007ae9c  mov     [rsp+arg_10], rbx
0x18007aea1  mov     [rsp+arg_18], rsi
0x18007aea6  push    rdi
0x18007aea7  sub     rsp, 90h
0x18007aeae  mov     rax, cs:__security_cookie
0x18007aeb5  xor     rax, rsp
0x18007aeb8  mov     [rsp+98h+var_18], rax
0x18007aec0  movups  xmm0, xmmword ptr [rdx]
0x18007aec3  xor     edi, edi
0x18007aec5  mov     rbx, rcx
0x18007aec8  movdqu  [rsp+98h+var_28], xmm0
0x18007aece  cmp     [rcx+0Ch], dil
0x18007aed2  jnz     short loc_18007AF40
0x18007aed4  lea     rcx, ?s_srwElsServiceLock@@3U_RTL_SRWLOCK@@A; SRWLock
0x18007aedb  call    cs:__imp_AcquireSRWLockExclusive
0x18007aee1  cmp     [rbx+0Ch], dil
0x18007aee5  jnz     short loc_18007AF33
0x18007aee7  mov     edi, 50h ; 'P'
0x18007aeec  lea     rcx, [rsp+98h+pOptions]; void *
0x18007aef1  mov     r8d, edi; Size
0x18007aef4  xor     edx, edx; Val
0x18007aef6  call    memset_0
0x18007aefb  lea     rax, [rsp+98h+var_28]
0x18007af00  mov     [rsp+98h+pOptions.Size], rdi
0x18007af05  lea     r8, [rbx+8]; pdwServicesCount
0x18007af09  mov     [rsp+98h+pOptions.pGuid], rax
0x18007af0e  mov     rdx, rbx; prgServices
0x18007af11  lea     rcx, [rsp+98h+pOptions]; pOptions
0x18007af16  call    cs:__imp_MappingGetServices
0x18007af1c  mov     edi, eax
0x18007af1e  test    eax, eax
0x18007af20  js      short loc_18007AF33
0x18007af22  cmp     dword ptr [rbx+8], 0
0x18007af26  jbe     short loc_18007AF2E
0x18007af28  mov     byte ptr [rbx+0Ch], 1
0x18007af2c  jmp     short loc_18007AF33
0x18007af2e  mov     edi, 80004005h
0x18007af33  lea     rcx, ?s_srwElsServiceLock@@3U_RTL_SRWLOCK@@A; SRWLock
0x18007af3a  call    cs:__imp_ReleaseSRWLockExclusive
0x18007af40  mov     eax, edi
0x18007af42  mov     rcx, [rsp+98h+var_18]
0x18007af4a  xor     rcx, rsp; StackCookie
0x18007af4d  call    __security_check_cookie
0x18007af52  lea     r11, [rsp+98h+var_8]
0x18007af5a  mov     rbx, [r11+20h]
0x18007af5e  mov     rsi, [r11+28h]
0x18007af62  mov     rsp, r11
0x18007af65  pop     rdi
0x18007af66  retn
```
