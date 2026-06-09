# CUmRdpDrv::DeleteDriveConnection(tagDRDEVLSTENTRY *)

- ea: `0x18001830c`
- end: `0x180018388`
- name: `?DeleteDriveConnection@CUmRdpDrv@@QEAAHPEAUtagDRDEVLSTENTRY@@@Z`
- size: `124`
- prototype: `__int64 __fastcall(CUmRdpDrv *__hidden this, struct tagDRDEVLSTENTRY *)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180010848`
- `0x1800117a0`

## callees

- `0x18000a41c`
- `0x18001294c`
- `0x18001830c`
- `0x180018b44`
- `0x180019d30`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18001836a`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18001836a`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180018355`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180018355`

## pseudocode

```c
_BOOL8 __fastcall CUmRdpDrv::DeleteDriveConnection(CUmRdpDrv *this, unsigned __int16 **a2)
{
  CUmRdpRpc *v6; // [rsp+30h] [rbp+8h] BYREF

  v6 = 0;
  if ( !(unsigned int)CUmRdpDr::CreateUmRdpRpc(*(CUmRdpDr **)this, &v6) )
  {
    CUmRdpRpc::WNetCancelConnection2W(v6, a2[3]);
    CUmRdpRpc::Release(v6);
  }
  if ( ImpersonateLoggedOnUser(*((HANDLE *)this + 67)) )
  {
    CUmRdpDrv::DeleteDriveFolder((void **)this, (struct tagDRDEVLSTENTRY *)a2);
    return RevertToSelf();
  }
  else
  {
    return 0;
  }
}

```

## disassembly

```asm
0x18001830c  mov     [rsp+arg_8], rbx
0x180018311  push    rdi
0x180018312  sub     rsp, 20h
0x180018316  mov     rdi, rdx
0x180018319  mov     [rsp+28h+arg_0], 0
0x180018322  mov     rbx, rcx
0x180018325  lea     rdx, [rsp+28h+arg_0]; struct CUmRdpRpc **
0x18001832a  mov     rcx, [rcx]; this
0x18001832d  call    ?CreateUmRdpRpc@CUmRdpDr@@QEAAJAEAPEAVCUmRdpRpc@@@Z; CUmRdpDr::CreateUmRdpRpc(CUmRdpRpc * &)
0x180018332  test    eax, eax
0x180018334  jnz     short loc_18001834E
0x180018336  mov     rdx, [rdi+18h]; unsigned __int16 *
0x18001833a  mov     rcx, [rsp+28h+arg_0]; this
0x18001833f  call    ?WNetCancelConnection2W@CUmRdpRpc@@QEAAIPEAG@Z; CUmRdpRpc::WNetCancelConnection2W(ushort *)
0x180018344  mov     rcx, [rsp+28h+arg_0]; this
0x180018349  call    ?Release@CUmRdpRpc@@QEAAXXZ; CUmRdpRpc::Release(void)
0x18001834e  mov     rcx, [rbx+218h]; hToken
0x180018355  call    cs:__imp_ImpersonateLoggedOnUser
0x18001835b  test    eax, eax
0x18001835d  jz      short loc_180018379
0x18001835f  mov     rdx, rdi; struct tagDRDEVLSTENTRY *
0x180018362  mov     rcx, rbx; this
0x180018365  call    ?DeleteDriveFolder@CUmRdpDrv@@AEAAHPEAUtagDRDEVLSTENTRY@@@Z; CUmRdpDrv::DeleteDriveFolder(tagDRDEVLSTENTRY *)
0x18001836a  call    cs:__imp_RevertToSelf
0x180018370  xor     ecx, ecx
0x180018372  test    eax, eax
0x180018374  setnz   cl
0x180018377  jmp     short loc_18001837B
0x180018379  xor     ecx, ecx
0x18001837b  mov     rbx, [rsp+28h+arg_8]
0x180018380  mov     eax, ecx
0x180018382  add     rsp, 20h
0x180018386  pop     rdi
0x180018387  retn
```
