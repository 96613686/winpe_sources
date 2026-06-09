# CUmRdpPrn::SetPrinterConfigInfo(ushort const *,void *,ulong)

- ea: `0x180017494`
- end: `0x180017670`
- name: `?SetPrinterConfigInfo@CUmRdpPrn@@AEAAKPEBGPEAXK@Z`
- size: `476`
- prototype: `__int64 __fastcall(CUmRdpPrn *this, const unsigned __int16 *, void *, DWORD)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180004680`

## callees

- `0x18000a41c`
- `0x18001294c`
- `0x1800146a0`
- `0x180015094`
- `0x180017494`
- `0x180019bd8`
- `0x180047ebe`
- `0x180047ef0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017595`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017619`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017638`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017595`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017619`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017638`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800175c9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180017624`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800175c9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180017624`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800175d3`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18001762e`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800175d3`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18001762e`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180017556`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180017556`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180017645`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180017645`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180017586`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180017586`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800175b5`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800175b5`

## pseudocode

```c
__int64 __fastcall CUmRdpPrn::SetPrinterConfigInfo(CUmRdpPrn *this, const unsigned __int16 *a2, void *a3, DWORD a4)
{
  void *v8; // rcx
  unsigned int v9; // edx
  unsigned int UserAcledTempPath; // eax
  unsigned int v11; // r9d
  unsigned __int16 *v12; // rcx
  DWORD LastError; // ebx
  BOOL v14; // edi
  HANDLE v15; // rax
  void *v16; // rsi
  CUmRdpDr *v17; // rcx
  DWORD NumberOfBytesWritten; // [rsp+40h] [rbp-C0h] BYREF
  CUmRdpRpc *v20; // [rsp+48h] [rbp-B8h] BYREF
  WCHAR FileName; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v22[526]; // [rsp+52h] [rbp-AEh] BYREF
  unsigned __int16 v23; // [rsp+260h] [rbp+160h] BYREF
  _BYTE v24[526]; // [rsp+262h] [rbp+162h] BYREF

  FileName = 0;
  memset_0(v22, 0, 0x206u);
  v23 = 0;
  memset_0(v24, 0, 0x206u);
  v8 = (void *)*((_QWORD *)this + 23);
  NumberOfBytesWritten = 0;
  UserAcledTempPath = GetUserAcledTempPath(v8, v9, &v23);
  v12 = &v23;
  if ( UserAcledTempPath - 1 > 0x103 )
    v12 = L".";
  LastError = CreateTempFile(v12, *((void **)this + 23), &FileName, v11);
  if ( !LastError )
  {
    v14 = ImpersonateLoggedOnUser(*((HANDLE *)this + 23));
    v15 = CreateFileW(&FileName, 0x40000000u, 3u, 0, 2u, 0x80u, 0);
    v16 = v15;
    if ( v15 == (HANDLE)-1LL )
    {
      LastError = GetLastError();
    }
    else if ( WriteFile(v15, a3, a4, &NumberOfBytesWritten, 0) && NumberOfBytesWritten >= a4 )
    {
      CloseHandle(v16);
      if ( v14 )
        v14 = !RevertToSelf();
      v17 = *(CUmRdpDr **)this;
      v20 = 0;
      LastError = CUmRdpDr::CreateUmRdpRpc(v17, &v20);
      if ( !LastError )
      {
        LastError = CUmRdpRpc::StorePrinterConfig(v20, a2, &FileName);
        CUmRdpRpc::Release(v20);
      }
    }
    else
    {
      LastError = GetLastError();
      CloseHandle(v16);
    }
    if ( v14 && !RevertToSelf() )
      LastError = GetLastError();
  }
  DeleteFileW(&FileName);
  return LastError;
}

```

## disassembly

```asm
0x180017494  push    rbp
0x180017496  push    rbx
0x180017497  push    rsi
0x180017498  push    rdi
0x180017499  push    r12
0x18001749b  push    r13
0x18001749d  push    r14
0x18001749f  push    r15
0x1800174a1  lea     rbp, [rsp-388h]
0x1800174a9  sub     rsp, 488h
0x1800174b0  mov     rax, cs:__security_cookie
0x1800174b7  xor     rax, rsp
0x1800174ba  mov     [rbp+3C0h+var_50], rax
0x1800174c1  mov     r12, r8
0x1800174c4  mov     r13, rdx
0x1800174c7  mov     r14, rcx
0x1800174ca  xor     eax, eax
0x1800174cc  mov     ebx, 206h
0x1800174d1  mov     [rsp+4C0h+FileName], ax
0x1800174d6  mov     r8d, ebx; Size
0x1800174d9  lea     rcx, [rsp+4C0h+var_46E]; void *
0x1800174de  xor     edx, edx; Val
0x1800174e0  mov     r15d, r9d
0x1800174e3  call    memset_0
0x1800174e8  xor     eax, eax
0x1800174ea  lea     rcx, [rbp+3C0h+var_25E]; void *
0x1800174f1  mov     r8d, ebx; Size
0x1800174f4  mov     [rbp+3C0h+var_260], ax
0x1800174fb  xor     edx, edx; Val
0x1800174fd  call    memset_0
0x180017502  mov     rcx, [r14+0B8h]; void *
0x180017509  lea     r8, [rbp+3C0h+var_260]; unsigned __int16 *
0x180017510  mov     [rsp+4C0h+NumberOfBytesWritten], 0
0x180017518  call    ?GetUserAcledTempPath@@YAKPEAXKPEAG@Z; GetUserAcledTempPath(void *,ulong,ushort *)
0x18001751d  mov     rdx, [r14+0B8h]; void *
0x180017524  lea     r8, [rsp+4C0h+FileName]; unsigned __int16 *
0x180017529  dec     eax
0x18001752b  lea     rcx, [rbp+3C0h+var_260]
0x180017532  cmp     eax, 103h
0x180017537  jbe     short loc_180017540
0x180017539  lea     rcx, asc_18004E468; "."
0x180017540  call    ?CreateTempFile@@YAKPEAGPEAX0K@Z; CreateTempFile(ushort *,void *,ushort *,ulong)
0x180017545  mov     ebx, eax
0x180017547  test    eax, eax
0x180017549  jnz     loc_180017640
0x18001754f  mov     rcx, [r14+0B8h]; hToken
0x180017556  call    cs:__imp_ImpersonateLoggedOnUser
0x18001755c  xor     ebx, ebx
0x18001755e  lea     rcx, [rsp+4C0h+FileName]; lpFileName
0x180017563  mov     [rsp+4C0h+hTemplateFile], rbx; hTemplateFile
0x180017568  xor     r9d, r9d; lpSecurityAttributes
0x18001756b  mov     [rsp+4C0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180017573  mov     edx, 40000000h; dwDesiredAccess
0x180017578  mov     edi, eax
0x18001757a  mov     [rsp+4C0h+dwCreationDisposition], 2; dwCreationDisposition
0x180017582  lea     r8d, [rbx+3]; dwShareMode
0x180017586  call    cs:__imp_CreateFileW
0x18001758c  mov     rsi, rax
0x18001758f  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180017593  jnz     short loc_1800175A2
0x180017595  call    cs:__imp_GetLastError
0x18001759b  mov     ebx, eax
0x18001759d  jmp     loc_18001762A
0x1800175a2  lea     r9, [rsp+4C0h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800175a7  mov     qword ptr [rsp+4C0h+dwCreationDisposition], rbx; lpOverlapped
0x1800175ac  mov     r8d, r15d; nNumberOfBytesToWrite
0x1800175af  mov     rdx, r12; lpBuffer
0x1800175b2  mov     rcx, rsi; hFile
0x1800175b5  call    cs:__imp_WriteFile
0x1800175bb  test    eax, eax
0x1800175bd  jz      short loc_180017619
0x1800175bf  cmp     [rsp+4C0h+NumberOfBytesWritten], r15d
0x1800175c4  jb      short loc_180017619
0x1800175c6  mov     rcx, rsi; hObject
0x1800175c9  call    cs:__imp_CloseHandle
0x1800175cf  test    edi, edi
0x1800175d1  jz      short loc_1800175E1
0x1800175d3  call    cs:__imp_RevertToSelf
0x1800175d9  test    eax, eax
0x1800175db  mov     edi, ebx
0x1800175dd  setz    dil
0x1800175e1  mov     rcx, [r14]; this
0x1800175e4  lea     rdx, [rsp+4C0h+var_478]; struct CUmRdpRpc **
0x1800175e9  mov     [rsp+4C0h+var_478], rbx
0x1800175ee  call    ?CreateUmRdpRpc@CUmRdpDr@@QEAAJAEAPEAVCUmRdpRpc@@@Z; CUmRdpDr::CreateUmRdpRpc(CUmRdpRpc * &)
0x1800175f3  mov     ebx, eax
0x1800175f5  test    eax, eax
0x1800175f7  jnz     short loc_18001762A
0x1800175f9  mov     rcx, [rsp+4C0h+var_478]; this
0x1800175fe  lea     r8, [rsp+4C0h+FileName]; unsigned __int16 *
0x180017603  mov     rdx, r13; unsigned __int16 *
0x180017606  call    ?StorePrinterConfig@CUmRdpRpc@@QEAAIPEBG0@Z; CUmRdpRpc::StorePrinterConfig(ushort const *,ushort const *)
0x18001760b  mov     rcx, [rsp+4C0h+var_478]; this
0x180017610  mov     ebx, eax
0x180017612  call    ?Release@CUmRdpRpc@@QEAAXXZ; CUmRdpRpc::Release(void)
0x180017617  jmp     short loc_18001762A
0x180017619  call    cs:__imp_GetLastError
0x18001761f  mov     rcx, rsi; hObject
0x180017622  mov     ebx, eax
0x180017624  call    cs:__imp_CloseHandle
0x18001762a  test    edi, edi
0x18001762c  jz      short loc_180017640
0x18001762e  call    cs:__imp_RevertToSelf
0x180017634  test    eax, eax
0x180017636  jnz     short loc_180017640
0x180017638  call    cs:__imp_GetLastError
0x18001763e  mov     ebx, eax
0x180017640  lea     rcx, [rsp+4C0h+FileName]; lpFileName
0x180017645  call    cs:__imp_DeleteFileW
0x18001764b  mov     eax, ebx
0x18001764d  mov     rcx, [rbp+3C0h+var_50]
0x180017654  xor     rcx, rsp; StackCookie
0x180017657  call    __security_check_cookie
0x18001765c  add     rsp, 488h
0x180017663  pop     r15
0x180017665  pop     r14
0x180017667  pop     r13
0x180017669  pop     r12
0x18001766b  pop     rdi
0x18001766c  pop     rsi
0x18001766d  pop     rbx
0x18001766e  pop     rbp
0x18001766f  retn
```
