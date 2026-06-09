# WinStationRcmShadow2

- ea: `0x1800222d0`
- end: `0x18002241b`
- name: `WinStationRcmShadow2`
- size: `331`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180005c30`
- `0x180005fcc`
- `0x180007890`
- `0x180008290`
- `0x180008e30`
- `0x1800222d0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800223e7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800223e7`
- `RPCRT4!NdrClientCall3` at `0x18002237b`
- `RPCRT4!NdrClientCall3` at `0x18002237b`

## string_xrefs

- `0x180022317`: `Failed to open binding`

## pseudocode

```c
char __fastcall WinStationRcmShadow2(int a1, int a2, int a3, _DWORD *a4, __int64 a5, int a6)
{
  char v10; // di
  void *v11; // rax
  CLIENT_CALL_RETURN v12; // rbx
  DWORD v13; // eax
  int v15; // [rsp+20h] [rbp-68h]
  int v16; // [rsp+28h] [rbp-60h]
  int v17; // [rsp+30h] [rbp-58h]
  _DWORD v19[2]; // [rsp+50h] [rbp-38h] BYREF
  CLIENT_CALL_RETURN v20; // [rsp+58h] [rbp-30h]
  unsigned __int16 v21[8]; // [rsp+60h] [rbp-28h] BYREF

  v10 = 0;
  v19[0] = 0;
  CSmartPublicBinding::CSmartPublicBinding((CSmartPublicBinding *)v21, 0, 1);
  if ( CSmartPublicBinding::operator void *(v21) )
  {
    v11 = CSmartPublicBinding::operator void *(v21);
    v20.Simple = 0;
    v17 = a3;
    v16 = a2;
    v15 = a1;
    v12.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&stru_180032140, 8u, 0, v11, v15, v16, v17, v19, a5, a6).Pointer;
    v20.Pointer = v12.Pointer;
    v19[1] = v12.Pointer;
    if ( SLODWORD(v12.Simple) >= 0 )
    {
      v10 = 1;
      *a4 = v19[0];
    }
    else
    {
      _DbgPrintMessage(8, "RpcRcmShadow2 failed: 0x%x in %s", LODWORD(v12.Pointer), "WinStationRcmShadow2");
      v13 = ConvertHRESULT2WIN32(v12.Simple);
      SetLastError(v13);
    }
  }
  else
  {
    _DbgPrintMessage(8, "Failed to open binding");
  }
  CSmartPublicBinding::~CSmartPublicBinding((CSmartPublicBinding *)v21);
  return v10;
}

```

## disassembly

```asm
0x1800222d0  mov     rax, rsp
0x1800222d3  mov     [rax+8], rbx
0x1800222d7  mov     [rax+10h], rsi
0x1800222db  mov     [rax+20h], r9
0x1800222df  push    rdi
0x1800222e0  push    r14
0x1800222e2  push    r15
0x1800222e4  sub     rsp, 70h
0x1800222e8  mov     rsi, r9
0x1800222eb  mov     ebx, r8d
0x1800222ee  mov     r14d, edx
0x1800222f1  mov     r15d, ecx
0x1800222f4  xor     edi, edi
0x1800222f6  mov     [rax-38h], edi
0x1800222f9  xor     edx, edx; void *
0x1800222fb  lea     r8d, [rdi+1]; int
0x1800222ff  lea     rcx, [rax-28h]; this
0x180022303  call    ??0CSmartPublicBinding@@QEAA@PEAXH@Z; CSmartPublicBinding::CSmartPublicBinding(void *,int)
0x180022308  lea     rcx, [rsp+88h+var_28]; unsigned __int16 *
0x18002230d  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x180022312  test    rax, rax
0x180022315  jnz     short loc_18002232B
0x180022317  lea     rdx, aFailedToOpenBi_0; "Failed to open binding"
0x18002231e  lea     ecx, [rdi+8]; int
0x180022321  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180022326  jmp     loc_1800223F8
0x18002232b  lea     rcx, [rsp+88h+var_28]; unsigned __int16 *
0x180022330  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x180022335  mov     [rsp+88h+var_30], rdi
0x18002233a  mov     ecx, [rsp+88h+arg_28]
0x180022341  mov     [rsp+88h+var_40], ecx
0x180022345  mov     rcx, [rsp+88h+arg_20]
0x18002234d  mov     [rsp+88h+var_48], rcx
0x180022352  lea     rcx, [rsp+88h+var_38]
0x180022357  mov     [rsp+88h+var_50], rcx
0x18002235c  mov     [rsp+88h+var_58], ebx
0x180022360  mov     [rsp+88h+var_60], r14d
0x180022365  mov     [rsp+88h+var_68], r15d
0x18002236a  mov     r9, rax
0x18002236d  xor     r8d, r8d; pReturnValue
0x180022370  lea     edx, [r8+8]; nProcNum
0x180022374  lea     rcx, stru_180032140; pProxyInfo
0x18002237b  call    cs:__imp_NdrClientCall3
0x180022381  mov     rbx, rax
0x180022384  mov     [rsp+88h+var_30], rax
0x180022389  mov     [rsp+88h+var_34], eax
0x18002238d  jmp     short loc_1800223BF
0x18002238f  test    eax, eax
0x180022391  jle     short loc_18002239B
0x180022393  movzx   eax, ax
0x180022396  or      eax, 80070000h
0x18002239b  mov     ebx, eax
0x18002239d  mov     [rsp+88h+var_34], eax
0x1800223a1  mov     r8d, eax
0x1800223a4  lea     rdx, aRpcrcmshadow2T; "RpcRcmShadow2 threw an exception: 0x%x"
0x1800223ab  mov     ecx, 8; int
0x1800223b0  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800223b5  xor     edi, edi
0x1800223b7  mov     rsi, [rsp+88h+arg_18]
0x1800223bf  test    ebx, ebx
0x1800223c1  jns     short loc_1800223EF
0x1800223c3  lea     r9, aWinstationrcms_0; "WinStationRcmShadow2"
0x1800223ca  mov     r8d, ebx
0x1800223cd  lea     rdx, aRpcrcmshadow2F; "RpcRcmShadow2 failed: 0x%x in %s"
0x1800223d4  mov     ecx, 8; int
0x1800223d9  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800223de  mov     ecx, ebx; int
0x1800223e0  call    ?ConvertHRESULT2WIN32@@YAKJ@Z; ConvertHRESULT2WIN32(long)
0x1800223e5  mov     ecx, eax; dwErrCode
0x1800223e7  call    cs:__imp_SetLastError
0x1800223ed  jmp     short loc_1800223F8
0x1800223ef  mov     dil, 1
0x1800223f2  mov     ecx, [rsp+88h+var_38]
0x1800223f6  mov     [rsi], ecx
0x1800223f8  lea     rcx, [rsp+88h+var_28]; this
0x1800223fd  call    ??1CSmartPublicBinding@@QEAA@XZ; CSmartPublicBinding::~CSmartPublicBinding(void)
0x180022402  mov     al, dil
0x180022405  lea     r11, [rsp+88h+var_18]
0x18002240a  mov     rbx, [r11+20h]
0x18002240e  mov     rsi, [r11+28h]
0x180022412  mov     rsp, r11
0x180022415  pop     r15
0x180022417  pop     r14
0x180022419  pop     rdi
0x18002241a  retn
0x1800308b7  push    rbp
0x1800308b9  sub     rsp, 50h
0x1800308bd  mov     rbp, rdx
0x1800308c0  mov     rcx, [rcx]
0x1800308c3  mov     ecx, [rcx]; ExceptionCode
0x1800308c5  call    cs:__imp_I_RpcExceptionFilter
0x1800308cb  nop
0x1800308cc  add     rsp, 50h
0x1800308d0  pop     rbp
0x1800308d1  retn
```
