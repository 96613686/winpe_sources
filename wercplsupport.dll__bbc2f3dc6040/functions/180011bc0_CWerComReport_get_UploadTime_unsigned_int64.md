# CWerComReport::get_UploadTime(unsigned __int64 *)

- ea: `0x180011bc0`
- end: `0x180011c16`
- name: `?get_UploadTime@CWerComReport@@UEAAJPEA_K@Z`
- size: `86`
- prototype: `int(CWerComReport *__hidden this, unsigned __int64 *)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180007d20`
- `0x180007fe0`
- `0x180010f58`
- `0x180011bc0`

## pseudocode

```c
__int64 __fastcall CWerComReport::get_UploadTime(CWerComReport *this, unsigned __int64 *a2)
{
  int UploadTime; // ebx
  int v6; // [rsp+40h] [rbp+18h] BYREF

  v6 = 2;
  UploadTime = CAutoImpersonate::ImpersonateUserHighestPrivs((CAutoImpersonate *)&v6);
  if ( UploadTime >= 0 )
    UploadTime = CWerComReport::_get_UploadTime((CWerComReport *)((char *)this - 24), a2);
  CAutoImpersonate::~CAutoImpersonate((CAutoImpersonate *)&v6);
  return (unsigned int)UploadTime;
}

```

## disassembly

```asm
0x180011bc0  mov     rax, rsp
0x180011bc3  mov     [rax+8], rbx
0x180011bc7  mov     [rax+10h], rsi
0x180011bcb  push    rdi
0x180011bcc  sub     rsp, 20h
0x180011bd0  mov     rsi, rcx
0x180011bd3  mov     dword ptr [rax+18h], 2
0x180011bda  lea     rcx, [rax+18h]; this
0x180011bde  mov     rdi, rdx
0x180011be1  call    ?ImpersonateUserHighestPrivs@CAutoImpersonate@@QEAAJXZ; CAutoImpersonate::ImpersonateUserHighestPrivs(void)
0x180011be6  mov     ebx, eax
0x180011be8  test    eax, eax
0x180011bea  js      short loc_180011BFA
0x180011bec  lea     rcx, [rsi-18h]; this
0x180011bf0  mov     rdx, rdi; unsigned __int64 *
0x180011bf3  call    ?_get_UploadTime@CWerComReport@@QEAAJPEA_K@Z; CWerComReport::_get_UploadTime(unsigned __int64 *)
0x180011bf8  mov     ebx, eax
0x180011bfa  lea     rcx, [rsp+28h+arg_10]; this
0x180011bff  call    ??1CAutoImpersonate@@QEAA@XZ; CAutoImpersonate::~CAutoImpersonate(void)
0x180011c04  mov     rsi, [rsp+28h+arg_8]
0x180011c09  mov     eax, ebx
0x180011c0b  mov     rbx, [rsp+28h+arg_0]
0x180011c10  add     rsp, 20h
0x180011c14  pop     rdi
0x180011c15  retn
```
