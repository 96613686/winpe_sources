# WinStationGetCurrentSessionTerminalName

- ea: `0x180003f10`
- end: `0x18000410d`
- name: `WinStationGetCurrentSessionTerminalName`
- size: `509`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `service_task`

## callers

- `0x180004450`

## callees

- `0x180003f10`
- `0x180005db0`
- `0x180005fcc`
- `0x180007890`
- `0x180008290`
- `0x180008e30`
- `0x180009d10`
- `0x1800230b8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000409d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800040c9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800040e8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000409d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800040c9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800040e8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004088`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004088`
- `RPCRT4!I_RpcExceptionFilter` at `0x1800300cc`
- `RPCRT4!I_RpcExceptionFilter` at `0x1800300cc`
- `RPCRT4!NdrClientCall3` at `0x180003fcc`
- `RPCRT4!NdrClientCall3` at `0x180003fcc`

## string_xrefs

- `0x180004104`: `StringCchCopy failed: 0x%x in %s`

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
      v6.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&stru_180032230, 1u, 0, v5, &hMem).Pointer;
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
0x180003f10  mov     rax, rsp
0x180003f13  mov     [rax+8], rcx
0x180003f17  push    rbx
0x180003f18  push    rsi
0x180003f19  push    rdi
0x180003f1a  sub     rsp, 50h
0x180003f1e  mov     rsi, rcx
0x180003f21  xor     edi, edi
0x180003f23  mov     bl, dil
0x180003f26  mov     [rax+18h], rdi
0x180003f2a  test    rcx, rcx
0x180003f2d  jz      loc_180004098
0x180003f33  mov     [rcx], di
0x180003f36  call    ?TestServiceStarted@@YAHK@Z; TestServiceStarted(ulong)
0x180003f3b  test    eax, eax
0x180003f3d  jz      loc_1800040D4
0x180003f43  mov     qword ptr [rsp+68h+var_30], rdi
0x180003f48  mov     dword ptr [rsp+68h+arg_8], edi
0x180003f4c  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180003f53  lea     ecx, [rdi+40h]; unsigned __int64
0x180003f56  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180003f5b  test    rax, rax
0x180003f5e  jz      loc_1800040DB
0x180003f64  lea     r9, [rsp+68h+arg_8]; unsigned int *
0x180003f69  xor     r8d, r8d; int
0x180003f6c  xor     edx, edx; unsigned __int16 *
0x180003f6e  mov     rcx, rax; this
0x180003f71  call    ??0CPublicBinding@@QEAA@PEBGHPEAK@Z; CPublicBinding::CPublicBinding(ushort const *,int,ulong *)
0x180003f76  mov     [rsp+68h+var_28], rax
0x180003f7b  test    rax, rax
0x180003f7e  jz      loc_1800040E3
0x180003f84  mov     dword ptr [rsp+68h+var_30+4], 1
0x180003f8c  lea     rcx, [rsp+68h+var_30]; unsigned __int16 *
0x180003f91  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x180003f96  test    rax, rax
0x180003f99  jz      loc_180004071
0x180003f9f  lea     rcx, [rsp+68h+var_30]; unsigned __int16 *
0x180003fa4  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x180003fa9  mov     [rsp+68h+arg_8], rdi
0x180003fae  lea     rcx, [rsp+68h+hMem]
0x180003fb6  mov     [rsp+68h+var_48], rcx
0x180003fbb  mov     r9, rax
0x180003fbe  xor     r8d, r8d; pReturnValue
0x180003fc1  lea     edx, [r8+1]; nProcNum
0x180003fc5  lea     rcx, stru_180032230; pProxyInfo
0x180003fcc  call    cs:__imp_NdrClientCall3
0x180003fd2  mov     rbx, rax
0x180003fd5  mov     [rsp+68h+arg_8], rax
0x180003fda  mov     [rsp+68h+var_38], eax
0x180003fde  jmp     short loc_18000400D
0x180003fe0  test    eax, eax
0x180003fe2  jle     short loc_180003FEC
0x180003fe4  movzx   eax, ax
0x180003fe7  or      eax, 80070000h
0x180003fec  mov     ebx, eax
0x180003fee  mov     [rsp+68h+var_38], eax
0x180003ff2  mov     r8d, eax
0x180003ff5  lea     rdx, aRpcgetcurrents_3; "RpcGetCurrentSessionTerminalName threw "...
0x180003ffc  mov     ecx, 8; int
0x180004001  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180004006  xor     edi, edi
0x180004008  mov     rsi, [rsp+68h+arg_0]
0x18000400d  test    ebx, ebx
0x18000400f  js      loc_1800040A5
0x180004015  mov     eax, 7FFFFFFEh
0x18000401a  mov     rcx, [rsp+68h+hMem]
0x180004022  mov     edx, 20h ; ' '
0x180004027  test    rax, rax
0x18000402a  jz      short loc_18000404B
0x18000402c  movzx   r8d, word ptr [rcx]
0x180004030  test    r8w, r8w
0x180004034  jz      short loc_18000404B
0x180004036  add     rcx, 2
0x18000403a  mov     [rsi], r8w
0x18000403e  add     rsi, 2
0x180004042  dec     rax
0x180004045  sub     rdx, 1
0x180004049  jnz     short loc_180004027
0x18000404b  mov     rax, rdx
0x18000404e  neg     rax
0x180004051  sbb     ebx, ebx
0x180004053  not     ebx
0x180004055  and     ebx, 8007007Ah
0x18000405b  lea     rax, [rsi-2]
0x18000405f  test    rdx, rdx
0x180004062  cmovnz  rax, rsi
0x180004066  mov     [rax], di
0x180004069  jz      loc_180004104
0x18000406f  mov     bl, 1
0x180004071  lea     rcx, [rsp+68h+var_30]; this
0x180004076  call    ??1CSmartPublicBinding@@QEAA@XZ; CSmartPublicBinding::~CSmartPublicBinding(void)
0x18000407b  mov     rcx, [rsp+68h+hMem]; hMem
0x180004083  test    rcx, rcx
0x180004086  jz      short loc_18000408E
0x180004088  call    cs:__imp_LocalFree
0x18000408e  mov     al, bl
0x180004090  add     rsp, 50h
0x180004094  pop     rdi
0x180004095  pop     rsi
0x180004096  pop     rbx
0x180004097  retn
0x180004098  mov     ecx, 57h ; 'W'; dwErrCode
0x18000409d  call    cs:__imp_SetLastError
0x1800040a3  jmp     short loc_18000407B
0x1800040a5  lea     rdx, aRpcgetcurrents_0; "RpcGetCurrentSessionTerminalName failed"...
0x1800040ac  mov     r8d, ebx
0x1800040af  lea     r9, aWinstationgetc_5; "WinStationGetCurrentSessionTerminalName"
0x1800040b6  mov     ecx, 8; int
0x1800040bb  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800040c0  mov     ecx, ebx; int
0x1800040c2  call    ?ConvertHRESULT2WIN32@@YAKJ@Z; ConvertHRESULT2WIN32(long)
0x1800040c7  mov     ecx, eax; dwErrCode
0x1800040c9  call    cs:__imp_SetLastError
0x1800040cf  mov     bl, dil
0x1800040d2  jmp     short loc_180004071
0x1800040d4  mov     ecx, 548h
0x1800040d9  jmp     short loc_18000409D
0x1800040db  mov     rax, rdi
0x1800040de  jmp     loc_180003F76
0x1800040e3  mov     ecx, 0Eh; dwErrCode
0x1800040e8  call    cs:__imp_SetLastError
0x1800040ee  lea     rdx, aNewCpublicbind; "new CPublicBinding"
0x1800040f5  mov     ecx, 8; int
0x1800040fa  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800040ff  jmp     loc_180003F8C
0x180004104  lea     rdx, aStringcchcopyF_0; "StringCchCopy failed: 0x%x in %s"
0x18000410b  jmp     short loc_1800040AC
0x1800300be  push    rbp
0x1800300c0  sub     rsp, 30h
0x1800300c4  mov     rbp, rdx
0x1800300c7  mov     rcx, [rcx]
0x1800300ca  mov     ecx, [rcx]; ExceptionCode
0x1800300cc  call    cs:__imp_I_RpcExceptionFilter
0x1800300d2  nop
0x1800300d3  add     rsp, 30h
0x1800300d7  pop     rbp
0x1800300d8  retn
```
