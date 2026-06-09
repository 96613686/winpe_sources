# CService::GetConfig(ushort const *,_QUERY_SERVICE_CONFIGW * *)

- ea: `0x18001df70`
- end: `0x18001e06d`
- name: `?GetConfig@CService@@QEAAKPEBGPEAPEAU_QUERY_SERVICE_CONFIGW@@@Z`
- size: `253`
- prototype: `unsigned int __fastcall(CService *__hidden this, const unsigned __int16 *, struct _QUERY_SERVICE_CONFIGW **)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, registry_config, service_task`

## callees

- `0x18000214c`
- `0x18001df70`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18001e048`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001e048`
- `KERNEL32!GetLastError` at `0x18001dfad`
- `KERNEL32!GetLastError` at `0x18001dfde`
- `KERNEL32!GetLastError` at `0x18001dfad`
- `KERNEL32!GetLastError` at `0x18001dfde`
- `ADVAPI32!CloseServiceHandle` at `0x18001e030`
- `ADVAPI32!CloseServiceHandle` at `0x18001e030`
- `ADVAPI32!OpenServiceW` at `0x18001df99`
- `ADVAPI32!OpenServiceW` at `0x18001df99`
- `ADVAPI32!QueryServiceConfigW` at `0x18001dfca`
- `ADVAPI32!QueryServiceConfigW` at `0x18001e01a`
- `ADVAPI32!QueryServiceConfigW` at `0x18001dfca`
- `ADVAPI32!QueryServiceConfigW` at `0x18001e01a`

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
0x18001df70  mov     rax, rsp
0x18001df73  mov     [rax+10h], rbx
0x18001df77  mov     [rax+18h], rsi
0x18001df7b  mov     [rax+20h], rdi
0x18001df7f  push    r14
0x18001df81  sub     rsp, 20h
0x18001df85  mov     rcx, [rcx]
0x18001df88  xor     ebx, ebx
0x18001df8a  and     [rax+8], ebx
0x18001df8d  mov     r14, r8
0x18001df90  xor     edi, edi
0x18001df92  mov     rcx, [rcx]; hSCManager
0x18001df95  lea     r8d, [rbx+1]; dwDesiredAccess
0x18001df99  call    cs:__imp_OpenServiceW
0x18001dfa0  nop     dword ptr [rax+rax+00h]
0x18001dfa5  mov     rsi, rax
0x18001dfa8  test    rax, rax
0x18001dfab  jnz     short loc_18001DFBD
0x18001dfad  call    cs:__imp_GetLastError
0x18001dfb4  nop     dword ptr [rax+rax+00h]
0x18001dfb9  mov     ebx, eax
0x18001dfbb  jmp     short loc_18001E03C
0x18001dfbd  lea     r9, [rsp+28h+pcbBytesNeeded]; pcbBytesNeeded
0x18001dfc2  xor     r8d, r8d; cbBufSize
0x18001dfc5  xor     edx, edx; lpServiceConfig
0x18001dfc7  mov     rcx, rsi; hService
0x18001dfca  call    cs:__imp_QueryServiceConfigW
0x18001dfd1  nop     dword ptr [rax+rax+00h]
0x18001dfd6  mov     eax, [rsp+28h+pcbBytesNeeded]
0x18001dfda  test    eax, eax
0x18001dfdc  jnz     short loc_18001DFEE
0x18001dfde  call    cs:__imp_GetLastError
0x18001dfe5  nop     dword ptr [rax+rax+00h]
0x18001dfea  mov     ebx, eax
0x18001dfec  jmp     short loc_18001E02D
0x18001dfee  mov     rcx, rax; unsigned __int64
0x18001dff1  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001dff8  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18001dffd  mov     rdi, rax
0x18001e000  test    rax, rax
0x18001e003  jnz     short loc_18001E00A
0x18001e005  lea     ebx, [rax+8]
0x18001e008  jmp     short loc_18001E02D
0x18001e00a  mov     r8d, [rsp+28h+pcbBytesNeeded]; cbBufSize
0x18001e00f  lea     r9, [rsp+28h+pcbBytesNeeded]; pcbBytesNeeded
0x18001e014  mov     rdx, rdi; lpServiceConfig
0x18001e017  mov     rcx, rsi; hService
0x18001e01a  call    cs:__imp_QueryServiceConfigW
0x18001e021  nop     dword ptr [rax+rax+00h]
0x18001e026  test    eax, eax
0x18001e028  jz      short loc_18001DFDE
0x18001e02a  mov     [r14], rdi
0x18001e02d  mov     rcx, rsi; hSCObject
0x18001e030  call    cs:__imp_CloseServiceHandle
0x18001e037  nop     dword ptr [rax+rax+00h]
0x18001e03c  test    ebx, ebx
0x18001e03e  jz      short loc_18001E054
0x18001e040  test    rdi, rdi
0x18001e043  jz      short loc_18001E054
0x18001e045  mov     rcx, rdi
0x18001e048  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001e04f  nop     dword ptr [rax+rax+00h]
0x18001e054  mov     rsi, [rsp+28h+arg_10]
0x18001e059  mov     eax, ebx
0x18001e05b  mov     rbx, [rsp+28h+arg_8]
0x18001e060  mov     rdi, [rsp+28h+arg_18]
0x18001e065  add     rsp, 20h
0x18001e069  pop     r14
0x18001e06b  retn
```
