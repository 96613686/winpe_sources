# CUmRdpPrn::SaveDefaultPrinter(ushort const *)

- ea: `0x180016e70`
- end: `0x180016f30`
- name: `?SaveDefaultPrinter@CUmRdpPrn@@AEAAHPEBG@Z`
- size: `192`
- prototype: `__int64 __fastcall(CUmRdpPrn *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180004680`

## callees

- `0x180006170`
- `0x180016e70`
- `0x1800193e0`
- `0x180047ef0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016eb8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016eb8`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180016edc`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180016edc`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180016eae`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180016eae`
- `WINSPOOL!__imp_GetDefaultPrinterW` at `0x180016ed4`
- `WINSPOOL!__imp_GetDefaultPrinterW` at `0x180016ed4`

## pseudocode

```c
__int64 __fastcall CUmRdpPrn::SaveDefaultPrinter(CUmRdpPrn *this, const unsigned __int16 *a2)
{
  bool v2; // zf
  unsigned int DefaultPrinterW; // ebx
  CRdpDrUtil *v6; // rcx
  DWORD pcchBuffer[4]; // [rsp+20h] [rbp-238h] BYREF
  WCHAR pszBuffer[264]; // [rsp+30h] [rbp-228h] BYREF

  v2 = *((_DWORD *)this + 56) == 0;
  pcchBuffer[0] = 0;
  if ( !v2 )
    return 0;
  if ( ImpersonateLoggedOnUser(*((HANDLE *)this + 23)) )
  {
    pcchBuffer[0] = 261;
    DefaultPrinterW = GetDefaultPrinterW(pszBuffer, pcchBuffer);
    if ( RevertToSelf() )
    {
      if ( DefaultPrinterW )
      {
        if ( !CRdpDrUtil::PrinterIsTS(v6, pszBuffer) )
          DefaultPrinterW = CUmRdpPrn::SendDefaultPrinterToRDPClip((HANDLE *)this, pszBuffer);
      }
      goto LABEL_10;
    }
  }
  else
  {
    GetLastError();
  }
  DefaultPrinterW = 0;
LABEL_10:
  *((_DWORD *)this + 56) = DefaultPrinterW;
  return DefaultPrinterW;
}

```

## disassembly

```asm
0x180016e70  mov     [rsp+arg_8], rbx
0x180016e75  push    rdi
0x180016e76  sub     rsp, 250h
0x180016e7d  mov     rax, cs:__security_cookie
0x180016e84  xor     rax, rsp
0x180016e87  mov     [rsp+258h+var_18], rax
0x180016e8f  cmp     dword ptr [rcx+0E0h], 0
0x180016e96  mov     rdi, rcx
0x180016e99  mov     [rsp+258h+pcchBuffer], 0
0x180016ea1  jz      short loc_180016EA7
0x180016ea3  xor     eax, eax
0x180016ea5  jmp     short loc_180016F0F
0x180016ea7  mov     rcx, [rcx+0B8h]; hToken
0x180016eae  call    cs:__imp_ImpersonateLoggedOnUser
0x180016eb4  test    eax, eax
0x180016eb6  jnz     short loc_180016EC2
0x180016eb8  call    cs:__imp_GetLastError
0x180016ebe  xor     ebx, ebx
0x180016ec0  jmp     short loc_180016F07
0x180016ec2  lea     rdx, [rsp+258h+pcchBuffer]; pcchBuffer
0x180016ec7  mov     [rsp+258h+pcchBuffer], 105h
0x180016ecf  lea     rcx, [rsp+258h+pszBuffer]; pszBuffer
0x180016ed4  call    cs:__imp_GetDefaultPrinterW
0x180016eda  mov     ebx, eax
0x180016edc  call    cs:__imp_RevertToSelf
0x180016ee2  test    eax, eax
0x180016ee4  jz      short loc_180016EBE
0x180016ee6  test    ebx, ebx
0x180016ee8  jz      short loc_180016F07
0x180016eea  lea     rdx, [rsp+258h+pszBuffer]; unsigned __int16 *
0x180016eef  call    ?PrinterIsTS@CRdpDrUtil@@QEAAHPEAG@Z; CRdpDrUtil::PrinterIsTS(ushort *)
0x180016ef4  test    eax, eax
0x180016ef6  jnz     short loc_180016F07
0x180016ef8  lea     rdx, [rsp+258h+pszBuffer]; unsigned __int16 *
0x180016efd  mov     rcx, rdi; this
0x180016f00  call    ?SendDefaultPrinterToRDPClip@CUmRdpPrn@@AEAAHPEBG@Z; CUmRdpPrn::SendDefaultPrinterToRDPClip(ushort const *)
0x180016f05  mov     ebx, eax
0x180016f07  mov     [rdi+0E0h], ebx
0x180016f0d  mov     eax, ebx
0x180016f0f  mov     rcx, [rsp+258h+var_18]
0x180016f17  xor     rcx, rsp; StackCookie
0x180016f1a  call    __security_check_cookie
0x180016f1f  mov     rbx, [rsp+258h+arg_8]
0x180016f27  add     rsp, 250h
0x180016f2e  pop     rdi
0x180016f2f  retn
```
