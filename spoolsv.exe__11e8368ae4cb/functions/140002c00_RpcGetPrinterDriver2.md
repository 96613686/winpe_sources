# RpcGetPrinterDriver2

- ea: `0x140002c00`
- end: `0x1400030bd`
- name: `RpcGetPrinterDriver2`
- size: `1213`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callees

- `0x1400021f0`
- `0x140002a70`
- `0x140002c00`
- `0x1400037d0`
- `0x1400041c0`
- `0x140013fe8`
- `0x1400140cc`
- `0x1400160a0`
- `0x140079338`
- `0x14007a010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140003012`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140003012`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140002d9f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140002de9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140002ece`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140002ed9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140002f50`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140002faa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140002fc2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140002fcd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140002d9f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140002de9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140002ece`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140002ed9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140002f50`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140002faa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140002fc2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140002fcd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140002d99`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140002f60`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140002f97`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140002fa4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140002fba`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140002d99`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140002f60`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140002f97`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140002fa4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140002fba`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x140002c48`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x140002e01`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x140002c48`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x140002e01`
- `RPCRT4!RpcRevertToSelf` at `0x140002f58`
- `RPCRT4!RpcRevertToSelf` at `0x140002fb2`
- `RPCRT4!RpcRevertToSelf` at `0x140002f58`
- `RPCRT4!RpcRevertToSelf` at `0x140002fb2`
- `RPCRT4!RpcImpersonateClient` at `0x140002d8d`
- `RPCRT4!RpcImpersonateClient` at `0x140002d8d`
- `RPCRT4!RpcServerInqBindingHandle` at `0x140002c2f`
- `RPCRT4!RpcServerInqBindingHandle` at `0x140002c2f`

## string_xrefs

- `0x140002c64`: `Rpc call is access denied.`

## pseudocode

```c
__int64 __fastcall RpcGetPrinterDriver2(
        __int64 a1,
        const wchar_t *a2,
        unsigned int a3,
        unsigned __int8 *a4,
        int a5,
        unsigned int *a6,
        int a7,
        int a8,
        _DWORD *a9,
        _DWORD *a10)
{
  DWORD LastError; // ebx
  RPC_STATUS v16; // eax
  unsigned __int8 *v17; // r15
  unsigned int v18; // r13d
  DWORD v19; // ecx
  __int64 (__fastcall *v20)(_QWORD, const wchar_t *, _QWORD, unsigned __int8 *, unsigned int, unsigned int *, int, int, _DWORD *, _DWORD *); // rax
  int v21; // ebp
  DWORD v22; // eax
  DWORD v23; // ebx
  int v24; // ebx
  DWORD v25; // ebx
  DWORD v26; // eax
  unsigned __int64 v27; // [rsp+60h] [rbp-48h]
  const struct _FieldInfo near *const *v28; // [rsp+68h] [rbp-40h]
  RPC_BINDING_HANDLE Binding; // [rsp+70h] [rbp-38h] BYREF

  Binding = 0;
  LastError = 0;
  if ( RpcServerInqBindingHandle(&Binding) || !TlsSetValue(gdwTlsBindingHandle, Binding) )
    return LastError;
  if ( (unsigned int)RpcApiValidSecurityLevel(Binding) )
  {
    SpoolerServiceTelemetry::WriteDbgTraceError("RpcGetPrinterDriver2", L"Rpc call is access denied.");
    return 5;
  }
  *a6 = 0;
  if ( a3 != 8 )
  {
    switch ( a3 )
    {
      case 1u:
        v27 = 8;
        v28 = &DriverInfo1Fields;
        goto LABEL_16;
      case 2u:
        v27 = 48;
        v28 = &DriverInfo2Fields;
        goto LABEL_16;
      case 3u:
        v27 = 80;
        v28 = &DriverInfo3Fields;
        goto LABEL_16;
      case 4u:
        v27 = 88;
        v28 = &DriverInfo4Fields;
        goto LABEL_16;
      case 5u:
        v27 = 64;
        v28 = &DriverInfo5Fields;
        goto LABEL_16;
      case 6u:
        v27 = 136;
        v28 = &DriverInfo6Fields;
        goto LABEL_16;
      case 0x65u:
        v27 = 112;
        v28 = &DriverInfoVersionFields;
        goto LABEL_16;
      default:
        LastError = 124;
        break;
    }
    goto LABEL_24;
  }
  v27 = 200;
  v28 = &DriverInfo8Fields;
LABEL_16:
  v16 = RpcImpersonateClient(0);
  if ( !v16 )
  {
    v17 = (unsigned __int8 *)((unsigned __int64)(a4 + 7) & 0xFFFFFFFFFFFFFFF8uLL);
    v18 = a5 & 0xFFFFFFF8;
    if ( v17 != a4 )
      v17 = (unsigned __int8 *)DllAllocSplMem(v18);
    if ( a4 && !v17 )
    {
      YRevertToSelf(1);
LABEL_23:
      LastError = GetLastError();
      goto LABEL_24;
    }
    if ( a1 && *(_DWORD *)a1 == 24672 )
    {
      if ( v17 || !v18 )
      {
        if ( !a2 || !*a2 )
          a2 = L"Windows x64";
        v20 = *(__int64 (__fastcall **)(_QWORD, const wchar_t *, _QWORD, unsigned __int8 *, unsigned int, unsigned int *, int, int, _DWORD *, _DWORD *))(*(_QWORD *)(a1 + 8) + 440LL);
        if ( v20 )
        {
          v21 = v20(*(_QWORD *)(a1 + 16), a2, a3, v17, v18, a6, a7, a8, a9, a10);
          if ( !v21 && GetLastError() != 122 )
          {
            v22 = GetLastError();
            PrvSpoolssTelemetry::WriteDbgTraceError(
              "GetPrinterDriverExW",
              L"Failed for printer %ws. Error %d",
              *(_QWORD *)(a1 + 72),
              v22);
          }
        }
        else
        {
          PrvSpoolssTelemetry::WriteDbgTraceInfo("GetPrinterDriverExW", L"Calling the fpGetPrinterDriver function.");
          *a9 = 0;
          *a10 = 0;
          v21 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, _QWORD, unsigned __int8 *, unsigned int, unsigned int *))(*(_QWORD *)(a1 + 8) + 120LL))(
                  *(_QWORD *)(a1 + 16),
                  a2,
                  a3,
                  v17,
                  v18,
                  a6);
        }
        v23 = GetLastError();
        RpcRevertToSelf();
        SetLastError(v23);
        if ( v21 )
        {
          if ( v17 )
          {
            v24 = CustomMarshallDownEntry(v17, v17, (const struct _FieldInfo *)v28, v27, v27);
          }
          else
          {
            v24 = 0;
            SetLastError(0x57u);
          }
          goto LABEL_47;
        }
LABEL_45:
        v24 = 0;
        if ( GetLastError() != 122 )
        {
          v26 = GetLastError();
          SpoolerServiceTelemetry::WriteDbgTraceError("YGetPrinterDriver2", L"Failed. Error %d", v26);
        }
LABEL_47:
        if ( a4 != v17 )
        {
          if ( a4 )
          {
            if ( v17 )
              memcpy_0(a4, v17, v18);
          }
          HeapFree(g_hSpoolssHeap, 0, v17);
        }
        *a6 = (*a6 + 7) & 0xFFFFFFF8;
        if ( v24 )
        {
          LastError = 0;
          goto LABEL_24;
        }
        goto LABEL_23;
      }
      v19 = 1784;
    }
    else
    {
      v19 = 6;
    }
    SetLastError(v19);
    v25 = GetLastError();
    RpcRevertToSelf();
    SetLastError(v25);
    goto LABEL_45;
  }
  SetLastError(v16);
  LastError = GetLastError();
LABEL_24:
  TlsSetValue(gdwTlsBindingHandle, 0);
  return LastError;
}

```

## disassembly

```asm
0x140002c00  mov     [rsp+arg_10], rbx
0x140002c05  push    rbp
0x140002c06  push    rsi
0x140002c07  push    rdi
0x140002c08  push    r14
0x140002c0a  push    r15
0x140002c0c  sub     rsp, 80h
0x140002c13  mov     rsi, rcx
0x140002c16  xor     r15d, r15d
0x140002c19  lea     rcx, [rsp+0A8h+Binding]; Binding
0x140002c1e  mov     [rsp+0A8h+Binding], r15
0x140002c23  mov     ebx, r15d
0x140002c26  mov     rdi, r9
0x140002c29  mov     ebp, r8d
0x140002c2c  mov     r14, rdx
0x140002c2f  call    cs:__imp_RpcServerInqBindingHandle
0x140002c35  test    eax, eax
0x140002c37  jnz     loc_140002E0F
0x140002c3d  mov     rdx, [rsp+0A8h+Binding]; lpTlsValue
0x140002c42  mov     ecx, cs:?gdwTlsBindingHandle@@3KA; dwTlsIndex
0x140002c48  call    cs:__imp_TlsSetValue
0x140002c4e  test    eax, eax
0x140002c50  jz      loc_140002E0F
0x140002c56  mov     rcx, [rsp+0A8h+Binding]; void *
0x140002c5b  call    ?RpcApiValidSecurityLevel@@YAJPEAX@Z; RpcApiValidSecurityLevel(void *)
0x140002c60  test    eax, eax
0x140002c62  jz      short loc_140002C81
0x140002c64  lea     rdx, aRpcCallIsAcces; "Rpc call is access denied."
0x140002c6b  lea     rcx, aRpcgetprinterd_0; "RpcGetPrinterDriver2"
0x140002c72  call    ?WriteDbgTraceError@SpoolerServiceTelemetry@@SAXPEADPEAGZZ; SpoolerServiceTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x140002c77  mov     eax, 5
0x140002c7c  jmp     loc_140002E11
0x140002c81  mov     [rsp+0A8h+arg_0], r12
0x140002c89  mov     r12, [rsp+0A8h+arg_28]
0x140002c91  mov     [r12], r15d
0x140002c95  cmp     ebp, 8
0x140002c98  jz      loc_140002D76
0x140002c9e  lea     eax, [rbp-1]; switch 101 cases
0x140002ca1  cmp     eax, 64h
0x140002ca4  ja      def_140002CC3; jumptable 0000000140002CC3 default case, cases 7-100
0x140002caa  lea     rdx, __ImageBase
0x140002cb1  movzx   eax, ds:(byte_140003058 - 140000000h)[rdx+rax]
0x140002cb9  mov     ecx, ds:(jpt_140002CC3 - 140000000h)[rdx+rax*4]
0x140002cc0  add     rcx, rdx
0x140002cc3  jmp     rcx; switch jump
0x140002cc5  lea     rax, ?DriverInfo1Fields@@3QBU_FieldInfo@@B; jumptable 0000000140002CC3 case 1
0x140002ccc  mov     [rsp+0A8h+var_48], 8
0x140002cd5  mov     [rsp+0A8h+var_40], rax
0x140002cda  jmp     loc_140002D8B
0x140002cdf  lea     rax, ?DriverInfo2Fields@@3QBU_FieldInfo@@B; jumptable 0000000140002CC3 case 2
0x140002ce6  mov     [rsp+0A8h+var_48], 30h ; '0'
0x140002cef  mov     [rsp+0A8h+var_40], rax
0x140002cf4  jmp     loc_140002D8B
0x140002cf9  lea     rax, ?DriverInfo3Fields@@3QBU_FieldInfo@@B; jumptable 0000000140002CC3 case 3
0x140002d00  mov     [rsp+0A8h+var_48], 50h ; 'P'
0x140002d09  mov     [rsp+0A8h+var_40], rax
0x140002d0e  jmp     short loc_140002D8B
0x140002d10  lea     rax, ?DriverInfo4Fields@@3QBU_FieldInfo@@B; jumptable 0000000140002CC3 case 4
0x140002d17  mov     [rsp+0A8h+var_48], 58h ; 'X'
0x140002d20  mov     [rsp+0A8h+var_40], rax
0x140002d25  jmp     short loc_140002D8B
0x140002d27  lea     rax, ?DriverInfo5Fields@@3QBU_FieldInfo@@B; jumptable 0000000140002CC3 case 5
0x140002d2e  mov     [rsp+0A8h+var_48], 40h ; '@'
0x140002d37  mov     [rsp+0A8h+var_40], rax
0x140002d3c  jmp     short loc_140002D8B
0x140002d3e  lea     rax, ?DriverInfo6Fields@@3QBU_FieldInfo@@B; jumptable 0000000140002CC3 case 6
0x140002d45  mov     [rsp+0A8h+var_48], 88h
0x140002d4e  mov     [rsp+0A8h+var_40], rax
0x140002d53  jmp     short loc_140002D8B
0x140002d55  lea     rax, ?DriverInfoVersionFields@@3QBU_FieldInfo@@B; jumptable 0000000140002CC3 case 101
0x140002d5c  mov     [rsp+0A8h+var_48], 70h ; 'p'
0x140002d65  mov     [rsp+0A8h+var_40], rax
0x140002d6a  jmp     short loc_140002D8B
0x140002d6c  mov     ebx, 7Ch ; '|'; jumptable 0000000140002CC3 default case, cases 7-100
0x140002d71  jmp     loc_140002DF9
0x140002d76  lea     rbx, ?DriverInfo8Fields@@3QBU_FieldInfo@@B; _FieldInfo const near * const DriverInfo8Fields
0x140002d7d  mov     [rsp+0A8h+var_48], 0C8h
0x140002d86  mov     [rsp+0A8h+var_40], rbx
0x140002d8b  xor     ecx, ecx; BindingHandle
0x140002d8d  call    cs:__imp_RpcImpersonateClient
0x140002d93  test    eax, eax
0x140002d95  jz      short loc_140002DA9
0x140002d97  mov     ecx, eax; dwErrCode
0x140002d99  call    cs:__imp_SetLastError
0x140002d9f  call    cs:__imp_GetLastError
0x140002da5  mov     ebx, eax
0x140002da7  jmp     short loc_140002DF9
0x140002da9  mov     [rsp+0A8h+arg_8], r13
0x140002db1  lea     r15, [rdi+7]
0x140002db5  mov     r13d, [rsp+0A8h+arg_20]
0x140002dbd  and     r15, 0FFFFFFFFFFFFFFF8h
0x140002dc1  and     r13d, 0FFFFFFF8h
0x140002dc5  cmp     r15, rdi
0x140002dc8  jz      short loc_140002DD5
0x140002dca  mov     ecx, r13d; dwBytes
0x140002dcd  call    DllAllocSplMem
0x140002dd2  mov     r15, rax
0x140002dd5  test    rdi, rdi
0x140002dd8  jz      short loc_140002E28
0x140002dda  test    r15, r15
0x140002ddd  jnz     short loc_140002E28
0x140002ddf  mov     ecx, 1
0x140002de4  call    ?YRevertToSelf@@YAJW4Call_Route@@@Z; YRevertToSelf(Call_Route)
0x140002de9  call    cs:__imp_GetLastError
0x140002def  mov     ebx, eax
0x140002df1  mov     r13, [rsp+0A8h+arg_8]
0x140002df9  mov     ecx, cs:?gdwTlsBindingHandle@@3KA; dwTlsIndex
0x140002dff  xor     edx, edx; lpTlsValue
0x140002e01  call    cs:__imp_TlsSetValue
0x140002e07  mov     r12, [rsp+0A8h+arg_0]
0x140002e0f  mov     eax, ebx
0x140002e11  mov     rbx, [rsp+0A8h+arg_10]
0x140002e19  add     rsp, 80h
0x140002e20  pop     r15
0x140002e22  pop     r14
0x140002e24  pop     rdi
0x140002e25  pop     rsi
0x140002e26  pop     rbp
0x140002e27  retn
0x140002e28  test    rsi, rsi
0x140002e2b  jz      loc_140002F9F
0x140002e31  cmp     dword ptr [rsi], 6060h
0x140002e37  jnz     loc_140002F9F
0x140002e3d  test    r15, r15
0x140002e40  jnz     short loc_140002E51
0x140002e42  test    r13d, r13d
0x140002e45  jz      short loc_140002E51
0x140002e47  mov     ecx, 6F8h
0x140002e4c  jmp     loc_140002FA4
0x140002e51  test    r14, r14
0x140002e54  jz      short loc_140002E5D
0x140002e56  cmp     word ptr [r14], 0
0x140002e5b  jnz     short loc_140002E64
0x140002e5d  lea     r14, szEnvironment; "Windows x64"
0x140002e64  mov     rax, [rsi+8]
0x140002e68  mov     rax, [rax+1B8h]
0x140002e6f  test    rax, rax
0x140002e72  jz      loc_140002EFB
0x140002e78  mov     rcx, [rsp+0A8h+arg_48]
0x140002e80  mov     r9, r15
0x140002e83  mov     [rsp+0A8h+var_60], rcx
0x140002e88  mov     r8d, ebp
0x140002e8b  mov     rcx, [rsp+0A8h+arg_40]
0x140002e93  mov     rdx, r14
0x140002e96  mov     [rsp+0A8h+var_68], rcx
0x140002e9b  mov     ecx, [rsp+0A8h+arg_38]
0x140002ea2  mov     [rsp+0A8h+var_70], ecx
0x140002ea6  mov     ecx, [rsp+0A8h+arg_30]
0x140002ead  mov     [rsp+0A8h+var_78], ecx
0x140002eb1  mov     rcx, [rsi+10h]
0x140002eb5  mov     [rsp+0A8h+var_80], r12
0x140002eba  mov     dword ptr [rsp+0A8h+var_88], r13d
0x140002ebf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002ec4  mov     ebp, eax
0x140002ec6  test    eax, eax
0x140002ec8  jnz     loc_140002F50
0x140002ece  call    cs:__imp_GetLastError
0x140002ed4  cmp     eax, 7Ah ; 'z'
0x140002ed7  jz      short loc_140002F50
0x140002ed9  call    cs:__imp_GetLastError
0x140002edf  mov     r8, [rsi+48h]
0x140002ee3  lea     rdx, aFailedForPrint; "Failed for printer %ws. Error %d"
0x140002eea  mov     r9d, eax
0x140002eed  lea     rcx, aGetprinterdriv_0; "GetPrinterDriverExW"
0x140002ef4  call    ?WriteDbgTraceError@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x140002ef9  jmp     short loc_140002F50
0x140002efb  lea     rdx, aCallingTheFpge; "Calling the fpGetPrinterDriver function"...
0x140002f02  lea     rcx, aGetprinterdriv_0; "GetPrinterDriverExW"
0x140002f09  call    ?WriteDbgTraceInfo@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x140002f0e  mov     rax, [rsp+0A8h+arg_40]
0x140002f16  mov     r9, r15
0x140002f19  mov     [rsp+0A8h+var_80], r12
0x140002f1e  mov     r8d, ebp
0x140002f21  mov     rdx, r14
0x140002f24  mov     dword ptr [rsp+0A8h+var_88], r13d
0x140002f29  mov     dword ptr [rax], 0
0x140002f2f  mov     rax, [rsp+0A8h+arg_48]
0x140002f37  mov     dword ptr [rax], 0
0x140002f3d  mov     rax, [rsi+8]
0x140002f41  mov     rcx, [rsi+10h]
0x140002f45  mov     rax, [rax+78h]
0x140002f49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002f4e  mov     ebp, eax
0x140002f50  call    cs:__imp_GetLastError
0x140002f56  mov     ebx, eax
0x140002f58  call    cs:__imp_RpcRevertToSelf
0x140002f5e  mov     ecx, ebx; dwErrCode
0x140002f60  call    cs:__imp_SetLastError
0x140002f66  test    ebp, ebp
0x140002f68  jz      short loc_140002FC0
0x140002f6a  test    r15, r15
0x140002f6d  jz      short loc_140002F90
0x140002f6f  mov     rax, [rsp+0A8h+var_48]
0x140002f74  mov     rdx, r15; unsigned __int8 *
0x140002f77  mov     r8, [rsp+0A8h+var_40]; struct _FieldInfo *
0x140002f7c  mov     r9, rax; unsigned __int64
0x140002f7f  mov     rcx, r15; Src
0x140002f82  mov     [rsp+0A8h+var_88], rax; unsigned __int64
0x140002f87  call    ?CustomMarshallDownEntry@@YAHPEAE0PEBU_FieldInfo@@_K2@Z; CustomMarshallDownEntry(uchar *,uchar *,_FieldInfo const *,unsigned __int64,unsigned __int64)
0x140002f8c  mov     ebx, eax
0x140002f8e  jmp     short loc_140002FE9
0x140002f90  xor     ebx, ebx
0x140002f92  mov     ecx, 57h ; 'W'; dwErrCode
0x140002f97  call    cs:__imp_SetLastError
0x140002f9d  jmp     short loc_140002FE9
0x140002f9f  mov     ecx, 6; dwErrCode
0x140002fa4  call    cs:__imp_SetLastError
0x140002faa  call    cs:__imp_GetLastError
0x140002fb0  mov     ebx, eax
0x140002fb2  call    cs:__imp_RpcRevertToSelf
0x140002fb8  mov     ecx, ebx; dwErrCode
0x140002fba  call    cs:__imp_SetLastError
0x140002fc0  xor     ebx, ebx
0x140002fc2  call    cs:__imp_GetLastError
0x140002fc8  cmp     eax, 7Ah ; 'z'
0x140002fcb  jz      short loc_140002FE9
0x140002fcd  call    cs:__imp_GetLastError
0x140002fd3  mov     r8d, eax
0x140002fd6  lea     rdx, aFailedErrorD_1; "Failed. Error %d"
0x140002fdd  lea     rcx, aYgetprinterdri_2; "YGetPrinterDriver2"
0x140002fe4  call    ?WriteDbgTraceError@SpoolerServiceTelemetry@@SAXPEADPEAGZZ; SpoolerServiceTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x140002fe9  cmp     rdi, r15
0x140002fec  jz      short loc_140003018
0x140002fee  test    rdi, rdi
0x140002ff1  jz      short loc_140003006
0x140002ff3  test    r15, r15
0x140002ff6  jz      short loc_140003006
0x140002ff8  mov     r8d, r13d; Size
0x140002ffb  mov     rdx, r15; Src
0x140002ffe  mov     rcx, rdi; void *
0x140003001  call    memcpy_0
0x140003006  mov     rcx, cs:?g_hSpoolssHeap@@3PEAXEA; hHeap
0x14000300d  mov     r8, r15; lpMem
0x140003010  xor     edx, edx; dwFlags
0x140003012  call    cs:__imp_HeapFree
0x140003018  mov     eax, [r12]
0x14000301c  add     eax, 7
0x14000301f  and     eax, 0FFFFFFF8h
0x140003022  mov     [r12], eax
0x140003026  test    ebx, ebx
0x140003028  jz      loc_140002DE9
0x14000302e  xor     ebx, ebx
0x140003030  jmp     loc_140002DF1
```
