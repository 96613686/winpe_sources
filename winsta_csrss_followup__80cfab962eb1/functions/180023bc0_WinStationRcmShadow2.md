# WinStationRcmShadow2

- ea: `0x180023bc0`
- end: `0x180023d18`
- name: `WinStationRcmShadow2`
- size: `344`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x1800041a0`
- `0x180004558`
- `0x180005b40`
- `0x1800065f0`
- `0x1800075a0`
- `0x180023bc0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180023cdd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180023cdd`
- `RPCRT4!NdrClientCall3` at `0x180023c6b`
- `RPCRT4!NdrClientCall3` at `0x180023c6b`

## string_xrefs

- `0x180023c07`: `Failed to open binding`

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
    v12.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&stru_180035140, 8u, 0, v11, v15, v16, v17, v19, a5, a6).Pointer;
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
0x180023bc0  mov     rax, rsp
0x180023bc3  mov     [rax+8], rbx
0x180023bc7  mov     [rax+10h], rsi
0x180023bcb  mov     [rax+20h], r9
0x180023bcf  push    rdi
0x180023bd0  push    r14
0x180023bd2  push    r15
0x180023bd4  sub     rsp, 70h
0x180023bd8  mov     rsi, r9
0x180023bdb  mov     ebx, r8d
0x180023bde  mov     r14d, edx
0x180023be1  mov     r15d, ecx
0x180023be4  xor     edi, edi
0x180023be6  mov     [rax-38h], edi
0x180023be9  xor     edx, edx; void *
0x180023beb  lea     r8d, [rdi+1]; int
0x180023bef  lea     rcx, [rax-28h]; this
0x180023bf3  call    ??0CSmartPublicBinding@@QEAA@PEAXH@Z; CSmartPublicBinding::CSmartPublicBinding(void *,int)
0x180023bf8  lea     rcx, [rsp+88h+var_28]; unsigned __int16 *
0x180023bfd  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x180023c02  test    rax, rax
0x180023c05  jnz     short loc_180023C1B
0x180023c07  lea     rdx, aFailedToOpenBi_0; "Failed to open binding"
0x180023c0e  lea     ecx, [rdi+8]; int
0x180023c11  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180023c16  jmp     loc_180023CF4
0x180023c1b  lea     rcx, [rsp+88h+var_28]; unsigned __int16 *
0x180023c20  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x180023c25  mov     [rsp+88h+var_30], rdi
0x180023c2a  mov     ecx, [rsp+88h+arg_28]
0x180023c31  mov     [rsp+88h+var_40], ecx
0x180023c35  mov     rcx, [rsp+88h+arg_20]
0x180023c3d  mov     [rsp+88h+var_48], rcx
0x180023c42  lea     rcx, [rsp+88h+var_38]
0x180023c47  mov     [rsp+88h+var_50], rcx
0x180023c4c  mov     [rsp+88h+var_58], ebx
0x180023c50  mov     [rsp+88h+var_60], r14d
0x180023c55  mov     [rsp+88h+var_68], r15d
0x180023c5a  mov     r9, rax
0x180023c5d  xor     r8d, r8d; pReturnValue
0x180023c60  lea     edx, [r8+8]; nProcNum
0x180023c64  lea     rcx, stru_180035140; pProxyInfo
0x180023c6b  call    cs:__imp_NdrClientCall3
0x180023c72  nop     dword ptr [rax+rax+00h]
0x180023c77  mov     rbx, rax
0x180023c7a  mov     [rsp+88h+var_30], rax
0x180023c7f  mov     [rsp+88h+var_34], eax
0x180023c83  jmp     short loc_180023CB5
0x180023c85  test    eax, eax
0x180023c87  jle     short loc_180023C91
0x180023c89  movzx   eax, ax
0x180023c8c  or      eax, 80070000h
0x180023c91  mov     ebx, eax
0x180023c93  mov     [rsp+88h+var_34], eax
0x180023c97  mov     r8d, eax
0x180023c9a  lea     rdx, aRpcrcmshadow2T; "RpcRcmShadow2 threw an exception: 0x%x"
0x180023ca1  mov     ecx, 8; int
0x180023ca6  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180023cab  xor     edi, edi
0x180023cad  mov     rsi, [rsp+88h+arg_18]
0x180023cb5  test    ebx, ebx
0x180023cb7  jns     short loc_180023CEB
0x180023cb9  lea     r9, aWinstationrcms_0; "WinStationRcmShadow2"
0x180023cc0  mov     r8d, ebx
0x180023cc3  lea     rdx, aRpcrcmshadow2F; "RpcRcmShadow2 failed: 0x%x in %s"
0x180023cca  mov     ecx, 8; int
0x180023ccf  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180023cd4  mov     ecx, ebx; int
0x180023cd6  call    ?ConvertHRESULT2WIN32@@YAKJ@Z; ConvertHRESULT2WIN32(long)
0x180023cdb  mov     ecx, eax; dwErrCode
0x180023cdd  call    cs:__imp_SetLastError
0x180023ce4  nop     dword ptr [rax+rax+00h]
0x180023ce9  jmp     short loc_180023CF4
0x180023ceb  mov     dil, 1
0x180023cee  mov     ecx, [rsp+88h+var_38]
0x180023cf2  mov     [rsi], ecx
0x180023cf4  lea     rcx, [rsp+88h+var_28]; this
0x180023cf9  call    ??1CSmartPublicBinding@@QEAA@XZ; CSmartPublicBinding::~CSmartPublicBinding(void)
0x180023cfe  mov     al, dil
0x180023d01  lea     r11, [rsp+88h+var_18]
0x180023d06  mov     rbx, [r11+20h]
0x180023d0a  mov     rsi, [r11+28h]
0x180023d0e  mov     rsp, r11
0x180023d11  pop     r15
0x180023d13  pop     r14
0x180023d15  pop     rdi
0x180023d16  retn
0x1800337cf  push    rbp
0x1800337d1  sub     rsp, 50h
0x1800337d5  mov     rbp, rdx
0x1800337d8  mov     rcx, [rcx]
0x1800337db  mov     ecx, [rcx]; ExceptionCode
0x1800337dd  call    cs:__imp_I_RpcExceptionFilter
0x1800337e4  nop     dword ptr [rax+rax+00h]
0x1800337e9  nop
0x1800337ea  add     rsp, 50h
0x1800337ee  pop     rbp
0x1800337ef  retn
```
