# IsUserManagerServiceAvailable(void)

- ea: `0x140015720`
- end: `0x14001580e`
- name: `?IsUserManagerServiceAvailable@@YAHXZ`
- size: `238`
- prototype: `__int64(void)`
- caller_count: `3`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x140011490`
- `0x140014250`
- `0x140045ec4`

## callees

- `0x140015720`
- `0x140053720`

## import_xrefs

- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x140015773`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x140015773`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1400157de`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1400157ec`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x14009d712`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x14009d722`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1400157de`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1400157ec`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x14009d712`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x14009d722`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x140015796`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x140015796`
- `api-ms-win-service-management-l2-1-0!QueryServiceStatusEx` at `0x1400157c3`
- `api-ms-win-service-management-l2-1-0!QueryServiceStatusEx` at `0x1400157c3`

## string_xrefs

- `0x14001576a`: `ServicesActive`

## pseudocode

```c
_BOOL8 IsUserManagerServiceAvailable(void)
{
  BOOL v0; // esi
  SC_HANDLE v1; // rbx
  SC_HANDLE v2; // rax
  SC_HANDLE v3; // rdi
  DWORD pcbBytesNeeded; // [rsp+30h] [rbp-78h] BYREF
  SC_HANDLE v6; // [rsp+38h] [rbp-70h]
  SC_HANDLE v7; // [rsp+40h] [rbp-68h]
  BYTE Buffer[16]; // [rsp+48h] [rbp-60h] BYREF
  __int128 v9; // [rsp+58h] [rbp-50h]
  int v10; // [rsp+68h] [rbp-40h]

  v0 = 0;
  v1 = 0;
  v6 = 0;
  *(_OWORD *)Buffer = 0;
  v9 = 0;
  v10 = 0;
  pcbBytesNeeded = 0;
  v2 = OpenSCManagerW(0, L"ServicesActive", 1u);
  v3 = v2;
  v7 = v2;
  if ( v2 )
  {
    v1 = OpenServiceW(v2, L"UserManager", 4u);
    v6 = v1;
    if ( v1 )
    {
      if ( QueryServiceStatusEx(v1, SC_STATUS_PROCESS_INFO, Buffer, 0x24u, &pcbBytesNeeded) )
        v0 = *(_DWORD *)&Buffer[4] == 4;
    }
  }
  if ( v1 )
    CloseServiceHandle(v1);
  if ( v3 )
    CloseServiceHandle(v3);
  return v0;
}

```

## disassembly

```asm
0x140015720  push    rbx
0x140015722  push    rsi
0x140015723  push    rdi
0x140015724  push    r14
0x140015726  sub     rsp, 88h
0x14001572d  mov     rax, cs:__security_cookie
0x140015734  xor     rax, rsp
0x140015737  mov     [rsp+0A8h+var_38], rax
0x14001573c  xor     esi, esi
0x14001573e  mov     [rsp+0A8h+var_68], rsi
0x140015743  mov     ebx, esi
0x140015745  mov     [rsp+0A8h+var_70], rbx
0x14001574a  xorps   xmm0, xmm0
0x14001574d  xor     eax, eax
0x14001574f  movups  xmmword ptr [rsp+0A8h+Buffer], xmm0
0x140015754  movups  [rsp+0A8h+var_50], xmm0
0x140015759  mov     [rsp+0A8h+var_40], eax
0x14001575d  mov     [rsp+0A8h+var_78], esi
0x140015761  mov     r14d, 1
0x140015767  mov     r8d, r14d; dwDesiredAccess
0x14001576a  lea     rdx, DatabaseName; "ServicesActive"
0x140015771  xor     ecx, ecx; lpMachineName
0x140015773  call    cs:__imp_OpenSCManagerW
0x140015779  mov     rdi, rax
0x14001577c  mov     [rsp+0A8h+var_68], rax
0x140015781  test    rax, rax
0x140015784  jz      short loc_1400157D6
0x140015786  mov     r8d, 4; dwDesiredAccess
0x14001578c  lea     rdx, ServiceName; "UserManager"
0x140015793  mov     rcx, rax; hSCManager
0x140015796  call    cs:__imp_OpenServiceW
0x14001579c  mov     rbx, rax
0x14001579f  mov     [rsp+0A8h+var_70], rax
0x1400157a4  test    rax, rax
0x1400157a7  jz      short loc_1400157D6
0x1400157a9  lea     rax, [rsp+0A8h+var_78]
0x1400157ae  mov     [rsp+0A8h+pcbBytesNeeded], rax; pcbBytesNeeded
0x1400157b3  mov     r9d, 24h ; '$'; cbBufSize
0x1400157b9  lea     r8, [rsp+0A8h+Buffer]; lpBuffer
0x1400157be  xor     edx, edx; InfoLevel
0x1400157c0  mov     rcx, rbx; hService
0x1400157c3  call    cs:__imp_QueryServiceStatusEx
0x1400157c9  test    eax, eax
0x1400157cb  jz      short loc_1400157D6
0x1400157cd  cmp     dword ptr [rsp+0A8h+Buffer+4], 4
0x1400157d2  cmovz   esi, r14d
0x1400157d6  test    rbx, rbx
0x1400157d9  jz      short loc_1400157E4
0x1400157db  mov     rcx, rbx; hSCObject
0x1400157de  call    cs:__imp_CloseServiceHandle
0x1400157e4  test    rdi, rdi
0x1400157e7  jz      short loc_1400157F2
0x1400157e9  mov     rcx, rdi; hSCObject
0x1400157ec  call    cs:__imp_CloseServiceHandle
0x1400157f2  mov     eax, esi
0x1400157f4  mov     rcx, [rsp+0A8h+var_38]
0x1400157f9  xor     rcx, rsp; StackCookie
0x1400157fc  call    __security_check_cookie
0x140015801  add     rsp, 88h
0x140015808  pop     r14
0x14001580a  pop     rdi
0x14001580b  pop     rsi
0x14001580c  pop     rbx
0x14001580d  retn
0x14009d700  push    rbp
0x14009d702  sub     rsp, 30h
0x14009d706  mov     rbp, rdx
0x14009d709  mov     rcx, [rbp+38h]; hSCObject
0x14009d70d  test    rcx, rcx
0x14009d710  jz      short loc_14009D719
0x14009d712  call    cs:__imp_CloseServiceHandle
0x14009d718  nop
0x14009d719  mov     rcx, [rbp+40h]; hSCObject
0x14009d71d  test    rcx, rcx
0x14009d720  jz      short loc_14009D729
0x14009d722  call    cs:__imp_CloseServiceHandle
0x14009d728  nop
0x14009d729  add     rsp, 30h
0x14009d72d  pop     rbp
0x14009d72e  retn
```
