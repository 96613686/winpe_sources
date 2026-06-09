# WinStationGetCurrentSessionTerminalName

- ea: `0x18000a7b0`
- end: `0x18000a9cc`
- name: `WinStationGetCurrentSessionTerminalName`
- size: `540`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `service_task`

## callers

- `0x18000a670`

## callees

- `0x180004330`
- `0x180004558`
- `0x180005b40`
- `0x1800065f0`
- `0x1800075a0`
- `0x180008590`
- `0x18000a7b0`
- `0x1800249e8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a94a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a97c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a9a1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a94a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a97c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a9a1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000a92e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000a92e`
- `RPCRT4!I_RpcExceptionFilter` at `0x180033280`
- `RPCRT4!I_RpcExceptionFilter` at `0x180033280`
- `RPCRT4!NdrClientCall3` at `0x18000a86c`
- `RPCRT4!NdrClientCall3` at `0x18000a86c`

## string_xrefs

- `0x18000a9c3`: `StringCchCopy failed: 0x%x in %s`

## pseudocode

```c
char __fastcall WinStationGetCurrentSessionTerminalName(_WORD *a1)
{
  _WORD *v1; // rsi
  char v2; // bl
  CPublicBinding *v3; // rax
  CPublicBinding *v4; // rax
  void *v5; // rax
  CLIENT_CALL_RETURN v6; // rbx
  __int64 v7; // rax
  __int16 *v8; // rcx
  __int64 v9; // rdx
  __int16 v10; // r8
  _WORD *v11; // rax
  DWORD v13; // ecx
  DWORD v14; // eax
  unsigned __int16 v15[4]; // [rsp+38h] [rbp-30h] BYREF
  CPublicBinding *v16; // [rsp+40h] [rbp-28h]
  CLIENT_CALL_RETURN v17; // [rsp+78h] [rbp+10h] BYREF
  HLOCAL hMem; // [rsp+80h] [rbp+18h] BYREF

  v1 = a1;
  v2 = 0;
  hMem = 0;
  if ( a1 )
  {
    *a1 = 0;
    if ( TestServiceStarted() )
    {
      *(_QWORD *)v15 = 0;
      LODWORD(v17.Pointer) = 0;
      v3 = (CPublicBinding *)operator new(0x40u, (const struct std::nothrow_t *)&std::nothrow);
      if ( v3 )
        v4 = CPublicBinding::CPublicBinding(v3, 0, 0, (unsigned int *)&v17);
      else
        v4 = 0;
      v16 = v4;
      if ( v4 )
      {
        *(_DWORD *)&v15[2] = 1;
      }
      else
      {
        SetLastError(0xEu);
        _DbgPrintMessage(8, "new CPublicBinding");
      }
      if ( !CSmartPublicBinding::operator void *(v15) )
        goto LABEL_17;
      v5 = CSmartPublicBinding::operator void *(v15);
      v17.Simple = 0;
      v6.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&stru_180035230, 1u, 0, v5, &hMem).Pointer;
      v17.Pointer = v6.Pointer;
      if ( SLODWORD(v6.Simple) < 0 )
      {
        _DbgPrintMessage(
          8,
          "RpcGetCurrentSessionTerminalName failed: 0x%x in %s",
          LODWORD(v6.Pointer),
          "WinStationGetCurrentSessionTerminalName");
      }
      else
      {
        v7 = 2147483646;
        v8 = (__int16 *)hMem;
        v9 = 32;
        do
        {
          if ( !v7 )
            break;
          v10 = *v8;
          if ( !*v8 )
            break;
          ++v8;
          *v1++ = v10;
          --v7;
          --v9;
        }
        while ( v9 );
        LODWORD(v6.Pointer) = v9 == 0 ? 0x8007007A : 0;
        v11 = v1 - 1;
        if ( v9 )
          v11 = v1;
        *v11 = 0;
        if ( v9 )
        {
          v2 = 1;
LABEL_17:
          CSmartPublicBinding::~CSmartPublicBinding((CSmartPublicBinding *)v15);
          goto LABEL_18;
        }
        _DbgPrintMessage(
          8,
          "StringCchCopy failed: 0x%x in %s",
          LODWORD(v6.Pointer),
          "WinStationGetCurrentSessionTerminalName");
      }
      v14 = ConvertHRESULT2WIN32(v6.Simple);
      SetLastError(v14);
      v2 = 0;
      goto LABEL_17;
    }
    v13 = 1352;
  }
  else
  {
    v13 = 87;
  }
  SetLastError(v13);
LABEL_18:
  if ( hMem )
    LocalFree(hMem);
  return v2;
}

```

## disassembly

```asm
0x18000a7b0  mov     rax, rsp
0x18000a7b3  mov     [rax+8], rcx
0x18000a7b7  push    rbx
0x18000a7b8  push    rsi
0x18000a7b9  push    rdi
0x18000a7ba  sub     rsp, 50h
0x18000a7be  mov     rsi, rcx
0x18000a7c1  xor     edi, edi
0x18000a7c3  mov     bl, dil
0x18000a7c6  mov     [rax+18h], rdi
0x18000a7ca  test    rcx, rcx
0x18000a7cd  jz      loc_18000A945
0x18000a7d3  mov     [rcx], di
0x18000a7d6  call    ?TestServiceStarted@@YAHK@Z; TestServiceStarted(ulong)
0x18000a7db  test    eax, eax
0x18000a7dd  jz      loc_18000A98D
0x18000a7e3  mov     qword ptr [rsp+68h+var_30], rdi
0x18000a7e8  mov     dword ptr [rsp+68h+arg_8], edi
0x18000a7ec  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000a7f3  lea     ecx, [rdi+40h]; unsigned __int64
0x18000a7f6  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000a7fb  test    rax, rax
0x18000a7fe  jz      loc_18000A994
0x18000a804  lea     r9, [rsp+68h+arg_8]; unsigned int *
0x18000a809  xor     r8d, r8d; int
0x18000a80c  xor     edx, edx; unsigned __int16 *
0x18000a80e  mov     rcx, rax; this
0x18000a811  call    ??0CPublicBinding@@QEAA@PEBGHPEAK@Z; CPublicBinding::CPublicBinding(ushort const *,int,ulong *)
0x18000a816  mov     [rsp+68h+var_28], rax
0x18000a81b  test    rax, rax
0x18000a81e  jz      loc_18000A99C
0x18000a824  mov     dword ptr [rsp+68h+var_30+4], 1
0x18000a82c  lea     rcx, [rsp+68h+var_30]; unsigned __int16 *
0x18000a831  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x18000a836  test    rax, rax
0x18000a839  jz      loc_18000A917
0x18000a83f  lea     rcx, [rsp+68h+var_30]; unsigned __int16 *
0x18000a844  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x18000a849  mov     [rsp+68h+arg_8], rdi
0x18000a84e  lea     rcx, [rsp+68h+hMem]
0x18000a856  mov     [rsp+68h+var_48], rcx
0x18000a85b  mov     r9, rax
0x18000a85e  xor     r8d, r8d; pReturnValue
0x18000a861  lea     edx, [r8+1]; nProcNum
0x18000a865  lea     rcx, stru_180035230; pProxyInfo
0x18000a86c  call    cs:__imp_NdrClientCall3
0x18000a873  nop     dword ptr [rax+rax+00h]
0x18000a878  mov     rbx, rax
0x18000a87b  mov     [rsp+68h+arg_8], rax
0x18000a880  mov     [rsp+68h+var_38], eax
0x18000a884  jmp     short loc_18000A8B3
0x18000a886  test    eax, eax
0x18000a888  jle     short loc_18000A892
0x18000a88a  movzx   eax, ax
0x18000a88d  or      eax, 80070000h
0x18000a892  mov     ebx, eax
0x18000a894  mov     [rsp+68h+var_38], eax
0x18000a898  mov     r8d, eax
0x18000a89b  lea     rdx, aRpcgetcurrents_3; "RpcGetCurrentSessionTerminalName threw "...
0x18000a8a2  mov     ecx, 8; int
0x18000a8a7  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000a8ac  xor     edi, edi
0x18000a8ae  mov     rsi, [rsp+68h+arg_0]
0x18000a8b3  test    ebx, ebx
0x18000a8b5  js      loc_18000A958
0x18000a8bb  mov     eax, 7FFFFFFEh
0x18000a8c0  mov     rcx, [rsp+68h+hMem]
0x18000a8c8  mov     edx, 20h ; ' '
0x18000a8cd  test    rax, rax
0x18000a8d0  jz      short loc_18000A8F1
0x18000a8d2  movzx   r8d, word ptr [rcx]
0x18000a8d6  test    r8w, r8w
0x18000a8da  jz      short loc_18000A8F1
0x18000a8dc  add     rcx, 2
0x18000a8e0  mov     [rsi], r8w
0x18000a8e4  add     rsi, 2
0x18000a8e8  dec     rax
0x18000a8eb  sub     rdx, 1
0x18000a8ef  jnz     short loc_18000A8CD
0x18000a8f1  mov     rax, rdx
0x18000a8f4  neg     rax
0x18000a8f7  sbb     ebx, ebx
0x18000a8f9  not     ebx
0x18000a8fb  and     ebx, 8007007Ah
0x18000a901  lea     rax, [rsi-2]
0x18000a905  test    rdx, rdx
0x18000a908  cmovnz  rax, rsi
0x18000a90c  mov     [rax], di
0x18000a90f  jz      loc_18000A9C3
0x18000a915  mov     bl, 1
0x18000a917  lea     rcx, [rsp+68h+var_30]; this
0x18000a91c  call    ??1CSmartPublicBinding@@QEAA@XZ; CSmartPublicBinding::~CSmartPublicBinding(void)
0x18000a921  mov     rcx, [rsp+68h+hMem]; hMem
0x18000a929  test    rcx, rcx
0x18000a92c  jz      short loc_18000A93A
0x18000a92e  call    cs:__imp_LocalFree
0x18000a935  nop     dword ptr [rax+rax+00h]
0x18000a93a  mov     al, bl
0x18000a93c  add     rsp, 50h
0x18000a940  pop     rdi
0x18000a941  pop     rsi
0x18000a942  pop     rbx
0x18000a943  retn
0x18000a945  mov     ecx, 57h ; 'W'; dwErrCode
0x18000a94a  call    cs:__imp_SetLastError
0x18000a951  nop     dword ptr [rax+rax+00h]
0x18000a956  jmp     short loc_18000A921
0x18000a958  lea     rdx, aRpcgetcurrents_0; "RpcGetCurrentSessionTerminalName failed"...
0x18000a95f  mov     r8d, ebx
0x18000a962  lea     r9, aWinstationgetc_5; "WinStationGetCurrentSessionTerminalName"
0x18000a969  mov     ecx, 8; int
0x18000a96e  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000a973  mov     ecx, ebx; int
0x18000a975  call    ?ConvertHRESULT2WIN32@@YAKJ@Z; ConvertHRESULT2WIN32(long)
0x18000a97a  mov     ecx, eax; dwErrCode
0x18000a97c  call    cs:__imp_SetLastError
0x18000a983  nop     dword ptr [rax+rax+00h]
0x18000a988  mov     bl, dil
0x18000a98b  jmp     short loc_18000A917
0x18000a98d  mov     ecx, 548h
0x18000a992  jmp     short loc_18000A94A
0x18000a994  mov     rax, rdi
0x18000a997  jmp     loc_18000A816
0x18000a99c  mov     ecx, 0Eh; dwErrCode
0x18000a9a1  call    cs:__imp_SetLastError
0x18000a9a8  nop     dword ptr [rax+rax+00h]
0x18000a9ad  lea     rdx, aNewCpublicbind; "new CPublicBinding"
0x18000a9b4  mov     ecx, 8; int
0x18000a9b9  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000a9be  jmp     loc_18000A82C
0x18000a9c3  lea     rdx, aStringcchcopyF_0; "StringCchCopy failed: 0x%x in %s"
0x18000a9ca  jmp     short loc_18000A95F
0x180033272  push    rbp
0x180033274  sub     rsp, 30h
0x180033278  mov     rbp, rdx
0x18003327b  mov     rcx, [rcx]
0x18003327e  mov     ecx, [rcx]; ExceptionCode
0x180033280  call    cs:__imp_I_RpcExceptionFilter
0x180033287  nop     dword ptr [rax+rax+00h]
0x18003328c  nop
0x18003328d  add     rsp, 30h
0x180033291  pop     rbp
0x180033292  retn
```
