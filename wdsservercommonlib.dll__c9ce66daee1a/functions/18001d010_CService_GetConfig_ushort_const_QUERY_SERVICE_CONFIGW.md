# CService::GetConfig(ushort const *,_QUERY_SERVICE_CONFIGW * *)

- ea: `0x18001d010`
- end: `0x18001d106`
- name: `?GetConfig@CService@@QEAAKPEBGPEAPEAU_QUERY_SERVICE_CONFIGW@@@Z`
- size: `246`
- prototype: `unsigned int __fastcall(CService *__hidden this, const unsigned __int16 *, struct _QUERY_SERVICE_CONFIGW **)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, registry_config, service_task`

## callees

- `0x18000179c`
- `0x18001d010`
- `0x18002e468`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18001d04d`
- `KERNEL32!GetLastError` at `0x18001d07e`
- `KERNEL32!GetLastError` at `0x18001d04d`
- `KERNEL32!GetLastError` at `0x18001d07e`
- `ADVAPI32!QueryServiceConfigW` at `0x18001d06a`
- `ADVAPI32!QueryServiceConfigW` at `0x18001d0ba`
- `ADVAPI32!QueryServiceConfigW` at `0x18001d06a`
- `ADVAPI32!QueryServiceConfigW` at `0x18001d0ba`
- `ADVAPI32!OpenServiceW` at `0x18001d039`
- `ADVAPI32!OpenServiceW` at `0x18001d039`
- `ADVAPI32!CloseServiceHandle` at `0x18001d0d0`
- `ADVAPI32!CloseServiceHandle` at `0x18001d0d0`

## pseudocode

```c
__int64 __fastcall CService::GetConfig(
        SC_HANDLE **this,
        const unsigned __int16 *a2,
        struct _QUERY_SERVICE_CONFIGW **a3)
{
  SC_HANDLE *v3; // rcx
  DWORD LastError; // ebx
  struct _QUERY_SERVICE_CONFIGW *v6; // rdi
  SC_HANDLE v7; // rax
  SC_HANDLE v8; // rsi
  struct _QUERY_SERVICE_CONFIGW *v9; // rax
  DWORD pcbBytesNeeded; // [rsp+30h] [rbp+8h] BYREF

  v3 = *this;
  LastError = 0;
  pcbBytesNeeded = 0;
  v6 = 0;
  v7 = OpenServiceW(*v3, a2, 1u);
  v8 = v7;
  if ( v7 )
  {
    QueryServiceConfigW(v7, 0, 0, &pcbBytesNeeded);
    if ( pcbBytesNeeded )
    {
      v9 = (struct _QUERY_SERVICE_CONFIGW *)operator new[](pcbBytesNeeded, (const struct std::nothrow_t *)&std::nothrow);
      v6 = v9;
      if ( !v9 )
      {
        LastError = 8;
        goto LABEL_9;
      }
      if ( QueryServiceConfigW(v8, v9, pcbBytesNeeded, &pcbBytesNeeded) )
      {
        *a3 = v6;
        goto LABEL_9;
      }
    }
    LastError = GetLastError();
LABEL_9:
    CloseServiceHandle(v8);
    goto LABEL_10;
  }
  LastError = GetLastError();
LABEL_10:
  if ( LastError && v6 )
    operator delete(v6);
  return LastError;
}

```

## disassembly

```asm
0x18001d010  mov     rax, rsp
0x18001d013  mov     [rax+10h], rbx
0x18001d017  mov     [rax+18h], rsi
0x18001d01b  mov     [rax+20h], rdi
0x18001d01f  push    r14
0x18001d021  sub     rsp, 20h
0x18001d025  mov     rcx, [rcx]
0x18001d028  xor     ebx, ebx
0x18001d02a  and     [rax+8], ebx
0x18001d02d  mov     r14, r8
0x18001d030  xor     edi, edi
0x18001d032  mov     rcx, [rcx]; hSCManager
0x18001d035  lea     r8d, [rbx+1]; dwDesiredAccess
0x18001d039  call    cs:__imp_OpenServiceW
0x18001d040  nop     dword ptr [rax+rax+00h]
0x18001d045  mov     rsi, rax
0x18001d048  test    rax, rax
0x18001d04b  jnz     short loc_18001D05D
0x18001d04d  call    cs:__imp_GetLastError
0x18001d054  nop     dword ptr [rax+rax+00h]
0x18001d059  mov     ebx, eax
0x18001d05b  jmp     short loc_18001D0DC
0x18001d05d  lea     r9, [rsp+28h+pcbBytesNeeded]; pcbBytesNeeded
0x18001d062  xor     r8d, r8d; cbBufSize
0x18001d065  xor     edx, edx; lpServiceConfig
0x18001d067  mov     rcx, rsi; hService
0x18001d06a  call    cs:__imp_QueryServiceConfigW
0x18001d071  nop     dword ptr [rax+rax+00h]
0x18001d076  mov     eax, [rsp+28h+pcbBytesNeeded]
0x18001d07a  test    eax, eax
0x18001d07c  jnz     short loc_18001D08E
0x18001d07e  call    cs:__imp_GetLastError
0x18001d085  nop     dword ptr [rax+rax+00h]
0x18001d08a  mov     ebx, eax
0x18001d08c  jmp     short loc_18001D0CD
0x18001d08e  mov     rcx, rax; unsigned __int64
0x18001d091  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001d098  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18001d09d  mov     rdi, rax
0x18001d0a0  test    rax, rax
0x18001d0a3  jnz     short loc_18001D0AA
0x18001d0a5  lea     ebx, [rax+8]
0x18001d0a8  jmp     short loc_18001D0CD
0x18001d0aa  mov     r8d, [rsp+28h+pcbBytesNeeded]; cbBufSize
0x18001d0af  lea     r9, [rsp+28h+pcbBytesNeeded]; pcbBytesNeeded
0x18001d0b4  mov     rdx, rdi; lpServiceConfig
0x18001d0b7  mov     rcx, rsi; hService
0x18001d0ba  call    cs:__imp_QueryServiceConfigW
0x18001d0c1  nop     dword ptr [rax+rax+00h]
0x18001d0c6  test    eax, eax
0x18001d0c8  jz      short loc_18001D07E
0x18001d0ca  mov     [r14], rdi
0x18001d0cd  mov     rcx, rsi; hSCObject
0x18001d0d0  call    cs:__imp_CloseServiceHandle
0x18001d0d7  nop     dword ptr [rax+rax+00h]
0x18001d0dc  test    ebx, ebx
0x18001d0de  jz      short loc_18001D0ED
0x18001d0e0  test    rdi, rdi
0x18001d0e3  jz      short loc_18001D0ED
0x18001d0e5  mov     rcx, rdi; lpMem
0x18001d0e8  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001d0ed  mov     rsi, [rsp+28h+arg_10]
0x18001d0f2  mov     eax, ebx
0x18001d0f4  mov     rbx, [rsp+28h+arg_8]
0x18001d0f9  mov     rdi, [rsp+28h+arg_18]
0x18001d0fe  add     rsp, 20h
0x18001d102  pop     r14
0x18001d104  retn
```
