# WinStationRedirectLogonMessage

- ea: `0x18002bd30`
- end: `0x18002be3a`
- name: `WinStationRedirectLogonMessage`
- size: `266`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x1800041a0`
- `0x180005b40`
- `0x1800065f0`
- `0x1800075a0`
- `0x18002bd30`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002bd82`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002bd82`
- `RPCRT4!NdrClientCall3` at `0x18002bdf5`
- `RPCRT4!NdrClientCall3` at `0x18002bdf5`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!GetSystemMetrics` at `0x18002bd4f`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!GetSystemMetrics` at `0x18002bd4f`

## string_xrefs

- `0x18002bdab`: `Failed to open binding failed: 0x%x in %s`

## pseudocode

```c
__int64 __fastcall WinStationRedirectLogonMessage(__int64 a1, __int64 a2, int a3, __int64 a4)
{
  signed int Pointer; // ebx
  signed int LastError; // eax
  void *v10; // rax
  int v12; // [rsp+30h] [rbp-58h]
  unsigned __int16 v13[28]; // [rsp+50h] [rbp-38h] BYREF

  Pointer = 0;
  if ( GetSystemMetrics(4096) )
  {
    CSmartPublicBinding::CSmartPublicBinding((CSmartPublicBinding *)v13, 0, 1);
    if ( CSmartPublicBinding::operator void *(v13) )
      goto LABEL_7;
    LastError = GetLastError();
    Pointer = LastError;
    if ( LastError > 0 )
      Pointer = (unsigned __int16)LastError | 0x80070000;
    if ( Pointer >= 0 )
    {
LABEL_7:
      v10 = CSmartPublicBinding::operator void *(v13);
      v12 = a3;
      Pointer = (unsigned int)NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&stru_1800351A0, 6u, 0, v10, a1, a2, v12, a4).Pointer;
    }
    else
    {
      _DbgPrintMessage(8, "Failed to open binding failed: 0x%x in %s", Pointer, "WinStationRedirectLogonMessage");
    }
    CSmartPublicBinding::~CSmartPublicBinding((CSmartPublicBinding *)v13);
  }
  return (unsigned int)Pointer;
}

```

## disassembly

```asm
0x18002bd30  push    rbx
0x18002bd32  push    rsi
0x18002bd33  push    rdi
0x18002bd34  push    r14
0x18002bd36  push    r15
0x18002bd38  sub     rsp, 60h
0x18002bd3c  mov     rdi, r9
0x18002bd3f  mov     esi, r8d
0x18002bd42  mov     r14, rdx
0x18002bd45  mov     r15, rcx
0x18002bd48  xor     ebx, ebx
0x18002bd4a  mov     ecx, 1000h; nIndex
0x18002bd4f  call    cs:__imp_GetSystemMetrics
0x18002bd56  nop     dword ptr [rax+rax+00h]
0x18002bd5b  test    eax, eax
0x18002bd5d  jz      loc_18002BE2B
0x18002bd63  xor     edx, edx; void *
0x18002bd65  lea     r8d, [rbx+1]; int
0x18002bd69  lea     rcx, [rsp+88h+var_38]; this
0x18002bd6e  call    ??0CSmartPublicBinding@@QEAA@PEAXH@Z; CSmartPublicBinding::CSmartPublicBinding(void *,int)
0x18002bd73  lea     rcx, [rsp+88h+var_38]; unsigned __int16 *
0x18002bd78  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x18002bd7d  test    rax, rax
0x18002bd80  jnz     short loc_18002BDBE
0x18002bd82  call    cs:__imp_GetLastError
0x18002bd89  nop     dword ptr [rax+rax+00h]
0x18002bd8e  mov     ebx, eax
0x18002bd90  test    eax, eax
0x18002bd92  jle     short loc_18002BD9D
0x18002bd94  movzx   ebx, ax
0x18002bd97  or      ebx, 80070000h
0x18002bd9d  test    ebx, ebx
0x18002bd9f  jns     short loc_18002BDBE
0x18002bda1  lea     r9, aWinstationredi_5; "WinStationRedirectLogonMessage"
0x18002bda8  mov     r8d, ebx
0x18002bdab  lea     rdx, aFailedToOpenBi; "Failed to open binding failed: 0x%x in "...
0x18002bdb2  mov     ecx, 8; int
0x18002bdb7  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002bdbc  jmp     short loc_18002BE21
0x18002bdbe  lea     rcx, [rsp+88h+var_38]; unsigned __int16 *
0x18002bdc3  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x18002bdc8  mov     [rsp+88h+var_40], 0
0x18002bdd1  mov     [rsp+88h+var_50], rdi
0x18002bdd6  mov     [rsp+88h+var_58], esi
0x18002bdda  mov     [rsp+88h+var_60], r14
0x18002bddf  mov     [rsp+88h+var_68], r15
0x18002bde4  mov     r9, rax
0x18002bde7  xor     r8d, r8d; pReturnValue
0x18002bdea  lea     edx, [r8+6]; nProcNum
0x18002bdee  lea     rcx, stru_1800351A0; pProxyInfo
0x18002bdf5  call    cs:__imp_NdrClientCall3
0x18002bdfc  nop     dword ptr [rax+rax+00h]
0x18002be01  mov     rbx, rax
0x18002be04  mov     [rsp+88h+var_40], rax
0x18002be09  mov     [rsp+88h+var_48], eax
0x18002be0d  jmp     short loc_18002BE21
0x18002be0f  test    eax, eax
0x18002be11  jle     short loc_18002BE1B
0x18002be13  movzx   eax, ax
0x18002be16  or      eax, 80070000h
0x18002be1b  mov     ebx, eax
0x18002be1d  mov     [rsp+88h+var_48], eax
0x18002be21  lea     rcx, [rsp+88h+var_38]; this
0x18002be26  call    ??1CSmartPublicBinding@@QEAA@XZ; CSmartPublicBinding::~CSmartPublicBinding(void)
0x18002be2b  mov     eax, ebx
0x18002be2d  add     rsp, 60h
0x18002be31  pop     r15
0x18002be33  pop     r14
0x18002be35  pop     rdi
0x18002be36  pop     rsi
0x18002be37  pop     rbx
0x18002be38  retn
0x18003377f  push    rbp
0x180033781  sub     rsp, 40h
0x180033785  mov     rbp, rdx
0x180033788  mov     rcx, [rcx]
0x18003378b  mov     ecx, [rcx]; ExceptionCode
0x18003378d  call    cs:__imp_I_RpcExceptionFilter
0x180033794  nop     dword ptr [rax+rax+00h]
0x180033799  nop
0x18003379a  add     rsp, 40h
0x18003379e  pop     rbp
0x18003379f  retn
```
