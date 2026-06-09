# CWdsService::ChangeState(ulong,int,ulong)

- ea: `0x180008214`
- end: `0x180008280`
- name: `?ChangeState@CWdsService@@AEAAKKHK@Z`
- size: `108`
- prototype: `unsigned int __fastcall(CWdsService *__hidden this, unsigned int, int, unsigned int)`
- caller_count: `3`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000aa50`
- `0x18000cc30`
- `0x18000d380`

## callees

- `0x180008214`
- `0x18000f0dc`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000825c`
- `KERNEL32!GetLastError` at `0x18000825c`
- `WdsServerCommonLib!?SetServiceStatus@CService@@SAHPEAUSERVICE_STATUS_HANDLE__@@PEAU_SERVICE_STATUS@@@Z` at `0x18000824c`
- `WdsServerCommonLib!?SetServiceStatus@CService@@SAHPEAUSERVICE_STATUS_HANDLE__@@PEAU_SERVICE_STATUS@@@Z` at `0x18000824c`

## pseudocode

```c
__int64 __fastcall CWdsService::ChangeState(CWdsService *this, int a2, int a3, int a4)
{
  unsigned int v4; // ebx
  DWORD LastError; // eax
  __int64 v6; // rdx
  __int64 v7; // r8

  v4 = 0;
  *((_DWORD *)this + 3) = a2;
  *((_DWORD *)this + 7) = 0;
  *((_DWORD *)this + 8) = 240000;
  if ( a3 )
  {
    if ( a4 )
    {
      *((_DWORD *)this + 5) = 1066;
      *((_DWORD *)this + 6) = a4;
    }
    else
    {
      *(_QWORD *)((char *)this + 20) = 0;
    }
  }
  if ( !CService::SetServiceStatus(
          *((struct SERVICE_STATUS_HANDLE__ **)this + 5),
          (struct _SERVICE_STATUS *)((char *)this + 8)) )
  {
    LastError = GetLastError();
    return (unsigned int)ElValidateWin32_0(LastError, v6, v7, 486);
  }
  return v4;
}

```

## disassembly

```asm
0x180008214  push    rbx
0x180008216  sub     rsp, 20h
0x18000821a  xor     ebx, ebx
0x18000821c  mov     [rcx+0Ch], edx
0x18000821f  mov     [rcx+1Ch], ebx
0x180008222  mov     dword ptr [rcx+20h], 3A980h
0x180008229  test    r8d, r8d
0x18000822c  jz      short loc_180008244
0x18000822e  test    r9d, r9d
0x180008231  jnz     short loc_180008239
0x180008233  mov     [rcx+14h], rbx
0x180008237  jmp     short loc_180008244
0x180008239  mov     dword ptr [rcx+14h], 42Ah
0x180008240  mov     [rcx+18h], r9d
0x180008244  lea     rdx, [rcx+8]
0x180008248  mov     rcx, [rcx+28h]
0x18000824c  call    cs:__imp_?SetServiceStatus@CService@@SAHPEAUSERVICE_STATUS_HANDLE__@@PEAU_SERVICE_STATUS@@@Z; CService::SetServiceStatus(SERVICE_STATUS_HANDLE__ *,_SERVICE_STATUS *)
0x180008253  nop     dword ptr [rax+rax+00h]
0x180008258  test    eax, eax
0x18000825a  jnz     short loc_180008277
0x18000825c  call    cs:__imp_GetLastError
0x180008263  nop     dword ptr [rax+rax+00h]
0x180008268  mov     ecx, eax
0x18000826a  mov     r9d, 1E6h
0x180008270  call    ElValidateWin32_0
0x180008275  mov     ebx, eax
0x180008277  mov     eax, ebx
0x180008279  add     rsp, 20h
0x18000827d  pop     rbx
0x18000827e  retn
```
