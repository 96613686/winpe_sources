# CCredentialGroup::SubscribeCertStoreChangeNotification(void *,void * *)

- ea: `0x180073658`
- end: `0x1800736ed`
- name: `?SubscribeCertStoreChangeNotification@CCredentialGroup@@AEAAKPEAXPEAPEAX@Z`
- size: `149`
- prototype: `unsigned int(CCredentialGroup *__hidden this, void *, void **)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180072e04`

## callees

- `0x180073658`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007369a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800736ba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007369a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800736ba`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x18007368a`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x18007368a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800736c7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800736c7`
- `CRYPT32!CertControlStore` at `0x1800736b0`
- `CRYPT32!CertControlStore` at `0x1800736b0`

## pseudocode

```c
DWORD __fastcall CCredentialGroup::SubscribeCertStoreChangeNotification(CCredentialGroup *this, void *a2, void **a3)
{
  DWORD LastError; // ebx
  HANDLE pvCtrlPara; // [rsp+30h] [rbp+8h] BYREF

  pvCtrlPara = 0;
  if ( !a2 || !a3 )
    return 87;
  pvCtrlPara = CreateEventA(0, 0, 0, 0);
  if ( !pvCtrlPara )
    return GetLastError();
  if ( CertControlStore(a2, 0, 2u, &pvCtrlPara) )
  {
    *a3 = pvCtrlPara;
    return 0;
  }
  else
  {
    LastError = GetLastError();
    CloseHandle(pvCtrlPara);
    return LastError;
  }
}

```

## disassembly

```asm
0x180073658  mov     [rsp+arg_8], rbx
0x18007365d  mov     [rsp+pvCtrlPara], rcx
0x180073662  push    rdi
0x180073663  sub     rsp, 20h
0x180073667  mov     [rsp+28h+pvCtrlPara], 0
0x180073670  mov     rbx, r8
0x180073673  mov     rdi, rdx
0x180073676  test    rdx, rdx
0x180073679  jz      short loc_1800736DD
0x18007367b  test    rbx, rbx
0x18007367e  jz      short loc_1800736DD
0x180073680  xor     r9d, r9d; lpName
0x180073683  xor     r8d, r8d; bInitialState
0x180073686  xor     edx, edx; bManualReset
0x180073688  xor     ecx, ecx; lpEventAttributes
0x18007368a  call    cs:__imp_CreateEventA
0x180073690  mov     [rsp+28h+pvCtrlPara], rax
0x180073695  test    rax, rax
0x180073698  jnz     short loc_1800736A2
0x18007369a  call    cs:__imp_GetLastError
0x1800736a0  jmp     short loc_1800736E2
0x1800736a2  xor     edx, edx; dwFlags
0x1800736a4  lea     r9, [rsp+28h+pvCtrlPara]; pvCtrlPara
0x1800736a9  mov     rcx, rdi; hCertStore
0x1800736ac  lea     r8d, [rdx+2]; dwCtrlType
0x1800736b0  call    cs:__imp_CertControlStore
0x1800736b6  test    eax, eax
0x1800736b8  jnz     short loc_1800736D1
0x1800736ba  call    cs:__imp_GetLastError
0x1800736c0  mov     rcx, [rsp+28h+pvCtrlPara]; hObject
0x1800736c5  mov     ebx, eax
0x1800736c7  call    cs:__imp_CloseHandle
0x1800736cd  mov     eax, ebx
0x1800736cf  jmp     short loc_1800736E2
0x1800736d1  mov     rax, [rsp+28h+pvCtrlPara]
0x1800736d6  mov     [rbx], rax
0x1800736d9  xor     eax, eax
0x1800736db  jmp     short loc_1800736E2
0x1800736dd  mov     eax, 57h ; 'W'
0x1800736e2  mov     rbx, [rsp+28h+arg_8]
0x1800736e7  add     rsp, 20h
0x1800736eb  pop     rdi
0x1800736ec  retn
```
