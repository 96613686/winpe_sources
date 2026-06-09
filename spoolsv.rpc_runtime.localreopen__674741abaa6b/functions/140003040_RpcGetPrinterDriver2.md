# RpcGetPrinterDriver2

- ea: `0x140003040`
- end: `0x14000357d`
- name: `RpcGetPrinterDriver2`
- size: `1341`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callees

- `0x1400028e0`
- `0x140002e20`
- `0x140003040`
- `0x140003d60`
- `0x140004790`
- `0x140015290`
- `0x140015378`
- `0x14001748c`
- `0x140080828`
- `0x140081010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400034cc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400034cc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400031fb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000324b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000333d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000334e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400033cb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140003446`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140003470`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140003481`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400031fb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000324b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000333d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000334e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400033cb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140003446`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140003470`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140003481`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400031ef`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400033e7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140003427`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000343a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140003462`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400031ef`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400033e7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140003427`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000343a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140003462`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x14000308e`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x140003269`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x14000308e`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x140003269`
- `RPCRT4!RpcRevertToSelf` at `0x1400033d9`
- `RPCRT4!RpcRevertToSelf` at `0x140003454`
- `RPCRT4!RpcRevertToSelf` at `0x1400033d9`
- `RPCRT4!RpcRevertToSelf` at `0x140003454`
- `RPCRT4!RpcImpersonateClient` at `0x1400031dd`
- `RPCRT4!RpcImpersonateClient` at `0x1400031dd`
- `RPCRT4!RpcServerInqBindingHandle` at `0x14000306f`
- `RPCRT4!RpcServerInqBindingHandle` at `0x14000306f`

## string_xrefs

- `0x1400030b0`: `Rpc call is access denied.`

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
0x140003040  mov     [rsp+arg_10], rbx
0x140003045  push    rbp
0x140003046  push    rsi
0x140003047  push    rdi
0x140003048  push    r14
0x14000304a  push    r15
0x14000304c  sub     rsp, 80h
0x140003053  mov     rsi, rcx
0x140003056  xor     r15d, r15d
0x140003059  lea     rcx, [rsp+0A8h+Binding]; Binding
0x14000305e  mov     [rsp+0A8h+Binding], r15
0x140003063  mov     ebx, r15d
0x140003066  mov     rdi, r9
0x140003069  mov     ebp, r8d
0x14000306c  mov     r14, rdx
0x14000306f  call    cs:__imp_RpcServerInqBindingHandle
0x140003076  nop     dword ptr [rax+rax+00h]
0x14000307b  test    eax, eax
0x14000307d  jnz     loc_14000327D
0x140003083  mov     rdx, [rsp+0A8h+Binding]; lpTlsValue
0x140003088  mov     ecx, cs:?gdwTlsBindingHandle@@3KA; dwTlsIndex
0x14000308e  call    cs:__imp_TlsSetValue
0x140003095  nop     dword ptr [rax+rax+00h]
0x14000309a  test    eax, eax
0x14000309c  jz      loc_14000327D
0x1400030a2  mov     rcx, [rsp+0A8h+Binding]; void *
0x1400030a7  call    ?RpcApiValidSecurityLevel@@YAJPEAX@Z; RpcApiValidSecurityLevel(void *)
0x1400030ac  test    eax, eax
0x1400030ae  jz      short loc_1400030CD
0x1400030b0  lea     rdx, aRpcCallIsAcces; "Rpc call is access denied."
0x1400030b7  lea     rcx, aRpcgetprinterd_0; "RpcGetPrinterDriver2"
0x1400030be  call    ?WriteDbgTraceError@SpoolerServiceTelemetry@@SAXPEADPEAGZZ; SpoolerServiceTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x1400030c3  mov     eax, 5
0x1400030c8  jmp     loc_14000327F
0x1400030cd  mov     [rsp+0A8h+arg_0], r12
0x1400030d5  mov     r12, [rsp+0A8h+arg_28]
0x1400030dd  mov     [r12], r15d
0x1400030e1  cmp     ebp, 8
0x1400030e4  jz      loc_1400031C6
0x1400030ea  lea     eax, [rbp-1]; switch 101 cases
0x1400030ed  cmp     eax, 64h
0x1400030f0  ja      def_14000310F; jumptable 000000014000310F default case, cases 7-100
0x1400030f6  lea     rdx, __ImageBase
0x1400030fd  movzx   eax, ds:(byte_140003518 - 140000000h)[rdx+rax]
0x140003105  mov     ecx, ds:(jpt_14000310F - 140000000h)[rdx+rax*4]
0x14000310c  add     rcx, rdx
0x14000310f  jmp     rcx; switch jump
0x140003115  lea     rax, ?DriverInfo1Fields@@3QBU_FieldInfo@@B; jumptable 000000014000310F case 1
0x14000311c  mov     [rsp+0A8h+var_48], 8
0x140003125  mov     [rsp+0A8h+var_40], rax
0x14000312a  jmp     loc_1400031DB
0x14000312f  lea     rax, ?DriverInfo2Fields@@3QBU_FieldInfo@@B; jumptable 000000014000310F case 2
0x140003136  mov     [rsp+0A8h+var_48], 30h ; '0'
0x14000313f  mov     [rsp+0A8h+var_40], rax
0x140003144  jmp     loc_1400031DB
0x140003149  lea     rax, ?DriverInfo3Fields@@3QBU_FieldInfo@@B; jumptable 000000014000310F case 3
0x140003150  mov     [rsp+0A8h+var_48], 50h ; 'P'
0x140003159  mov     [rsp+0A8h+var_40], rax
0x14000315e  jmp     short loc_1400031DB
0x140003160  lea     rax, ?DriverInfo4Fields@@3QBU_FieldInfo@@B; jumptable 000000014000310F case 4
0x140003167  mov     [rsp+0A8h+var_48], 58h ; 'X'
0x140003170  mov     [rsp+0A8h+var_40], rax
0x140003175  jmp     short loc_1400031DB
0x140003177  lea     rax, ?DriverInfo5Fields@@3QBU_FieldInfo@@B; jumptable 000000014000310F case 5
0x14000317e  mov     [rsp+0A8h+var_48], 40h ; '@'
0x140003187  mov     [rsp+0A8h+var_40], rax
0x14000318c  jmp     short loc_1400031DB
0x14000318e  lea     rax, ?DriverInfo6Fields@@3QBU_FieldInfo@@B; jumptable 000000014000310F case 6
0x140003195  mov     [rsp+0A8h+var_48], 88h
0x14000319e  mov     [rsp+0A8h+var_40], rax
0x1400031a3  jmp     short loc_1400031DB
0x1400031a5  lea     rax, ?DriverInfoVersionFields@@3QBU_FieldInfo@@B; jumptable 000000014000310F case 101
0x1400031ac  mov     [rsp+0A8h+var_48], 70h ; 'p'
0x1400031b5  mov     [rsp+0A8h+var_40], rax
0x1400031ba  jmp     short loc_1400031DB
0x1400031bc  mov     ebx, 7Ch ; '|'; jumptable 000000014000310F default case, cases 7-100
0x1400031c1  jmp     loc_140003261
0x1400031c6  lea     rbx, ?DriverInfo8Fields@@3QBU_FieldInfo@@B; _FieldInfo const near * const DriverInfo8Fields
0x1400031cd  mov     [rsp+0A8h+var_48], 0C8h
0x1400031d6  mov     [rsp+0A8h+var_40], rbx
0x1400031db  xor     ecx, ecx; BindingHandle
0x1400031dd  call    cs:__imp_RpcImpersonateClient
0x1400031e4  nop     dword ptr [rax+rax+00h]
0x1400031e9  test    eax, eax
0x1400031eb  jz      short loc_14000320B
0x1400031ed  mov     ecx, eax; dwErrCode
0x1400031ef  call    cs:__imp_SetLastError
0x1400031f6  nop     dword ptr [rax+rax+00h]
0x1400031fb  call    cs:__imp_GetLastError
0x140003202  nop     dword ptr [rax+rax+00h]
0x140003207  mov     ebx, eax
0x140003209  jmp     short loc_140003261
0x14000320b  mov     [rsp+0A8h+arg_8], r13
0x140003213  lea     r15, [rdi+7]
0x140003217  mov     r13d, [rsp+0A8h+arg_20]
0x14000321f  and     r15, 0FFFFFFFFFFFFFFF8h
0x140003223  and     r13d, 0FFFFFFF8h
0x140003227  cmp     r15, rdi
0x14000322a  jz      short loc_140003237
0x14000322c  mov     ecx, r13d; dwBytes
0x14000322f  call    DllAllocSplMem
0x140003234  mov     r15, rax
0x140003237  test    rdi, rdi
0x14000323a  jz      short loc_140003297
0x14000323c  test    r15, r15
0x14000323f  jnz     short loc_140003297
0x140003241  mov     ecx, 1
0x140003246  call    ?YRevertToSelf@@YAJW4Call_Route@@@Z; YRevertToSelf(Call_Route)
0x14000324b  call    cs:__imp_GetLastError
0x140003252  nop     dword ptr [rax+rax+00h]
0x140003257  mov     ebx, eax
0x140003259  mov     r13, [rsp+0A8h+arg_8]
0x140003261  mov     ecx, cs:?gdwTlsBindingHandle@@3KA; dwTlsIndex
0x140003267  xor     edx, edx; lpTlsValue
0x140003269  call    cs:__imp_TlsSetValue
0x140003270  nop     dword ptr [rax+rax+00h]
0x140003275  mov     r12, [rsp+0A8h+arg_0]
0x14000327d  mov     eax, ebx
0x14000327f  mov     rbx, [rsp+0A8h+arg_10]
0x140003287  add     rsp, 80h
0x14000328e  pop     r15
0x140003290  pop     r14
0x140003292  pop     rdi
0x140003293  pop     rsi
0x140003294  pop     rbp
0x140003295  retn
0x140003297  test    rsi, rsi
0x14000329a  jz      loc_140003435
0x1400032a0  cmp     dword ptr [rsi], 6060h
0x1400032a6  jnz     loc_140003435
0x1400032ac  test    r15, r15
0x1400032af  jnz     short loc_1400032C0
0x1400032b1  test    r13d, r13d
0x1400032b4  jz      short loc_1400032C0
0x1400032b6  mov     ecx, 6F8h
0x1400032bb  jmp     loc_14000343A
0x1400032c0  test    r14, r14
0x1400032c3  jz      short loc_1400032CC
0x1400032c5  cmp     word ptr [r14], 0
0x1400032ca  jnz     short loc_1400032D3
0x1400032cc  lea     r14, szEnvironment; "Windows x64"
0x1400032d3  mov     rax, [rsi+8]
0x1400032d7  mov     rax, [rax+1B8h]
0x1400032de  test    rax, rax
0x1400032e1  jz      loc_140003376
0x1400032e7  mov     rcx, [rsp+0A8h+arg_48]
0x1400032ef  mov     r9, r15
0x1400032f2  mov     [rsp+0A8h+var_60], rcx
0x1400032f7  mov     r8d, ebp
0x1400032fa  mov     rcx, [rsp+0A8h+arg_40]
0x140003302  mov     rdx, r14
0x140003305  mov     [rsp+0A8h+var_68], rcx
0x14000330a  mov     ecx, [rsp+0A8h+arg_38]
0x140003311  mov     [rsp+0A8h+var_70], ecx
0x140003315  mov     ecx, [rsp+0A8h+arg_30]
0x14000331c  mov     [rsp+0A8h+var_78], ecx
0x140003320  mov     rcx, [rsi+10h]
0x140003324  mov     [rsp+0A8h+var_80], r12
0x140003329  mov     dword ptr [rsp+0A8h+var_88], r13d
0x14000332e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003333  mov     ebp, eax
0x140003335  test    eax, eax
0x140003337  jnz     loc_1400033CB
0x14000333d  call    cs:__imp_GetLastError
0x140003344  nop     dword ptr [rax+rax+00h]
0x140003349  cmp     eax, 7Ah ; 'z'
0x14000334c  jz      short loc_1400033CB
0x14000334e  call    cs:__imp_GetLastError
0x140003355  nop     dword ptr [rax+rax+00h]
0x14000335a  mov     r8, [rsi+48h]
0x14000335e  lea     rdx, aFailedForPrint; "Failed for printer %ws. Error %d"
0x140003365  mov     r9d, eax
0x140003368  lea     rcx, aGetprinterdriv_0; "GetPrinterDriverExW"
0x14000336f  call    ?WriteDbgTraceError@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x140003374  jmp     short loc_1400033CB
0x140003376  lea     rdx, aCallingTheFpge; "Calling the fpGetPrinterDriver function"...
0x14000337d  lea     rcx, aGetprinterdriv_0; "GetPrinterDriverExW"
0x140003384  call    ?WriteDbgTraceInfo@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x140003389  mov     rax, [rsp+0A8h+arg_40]
0x140003391  mov     r9, r15
0x140003394  mov     [rsp+0A8h+var_80], r12
0x140003399  mov     r8d, ebp
0x14000339c  mov     rdx, r14
0x14000339f  mov     dword ptr [rsp+0A8h+var_88], r13d
0x1400033a4  mov     dword ptr [rax], 0
0x1400033aa  mov     rax, [rsp+0A8h+arg_48]
0x1400033b2  mov     dword ptr [rax], 0
0x1400033b8  mov     rax, [rsi+8]
0x1400033bc  mov     rcx, [rsi+10h]
0x1400033c0  mov     rax, [rax+78h]
0x1400033c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400033c9  mov     ebp, eax
0x1400033cb  call    cs:__imp_GetLastError
0x1400033d2  nop     dword ptr [rax+rax+00h]
0x1400033d7  mov     ebx, eax
0x1400033d9  call    cs:__imp_RpcRevertToSelf
0x1400033e0  nop     dword ptr [rax+rax+00h]
0x1400033e5  mov     ecx, ebx; dwErrCode
0x1400033e7  call    cs:__imp_SetLastError
0x1400033ee  nop     dword ptr [rax+rax+00h]
0x1400033f3  test    ebp, ebp
0x1400033f5  jz      short loc_14000346E
0x1400033f7  test    r15, r15
0x1400033fa  jz      short loc_140003420
0x1400033fc  mov     rax, [rsp+0A8h+var_48]
0x140003401  mov     rdx, r15; unsigned __int8 *
0x140003404  mov     r8, [rsp+0A8h+var_40]; struct _FieldInfo *
0x140003409  mov     r9, rax; unsigned __int64
0x14000340c  mov     rcx, r15; Src
0x14000340f  mov     [rsp+0A8h+var_88], rax; unsigned __int64
0x140003414  call    ?CustomMarshallDownEntry@@YAHPEAE0PEBU_FieldInfo@@_K2@Z; CustomMarshallDownEntry(uchar *,uchar *,_FieldInfo const *,unsigned __int64,unsigned __int64)
0x140003419  mov     ebx, eax
0x14000341b  jmp     loc_1400034A3
0x140003420  xor     ebx, ebx
0x140003422  mov     ecx, 57h ; 'W'; dwErrCode
0x140003427  call    cs:__imp_SetLastError
0x14000342e  nop     dword ptr [rax+rax+00h]
0x140003433  jmp     short loc_1400034A3
0x140003435  mov     ecx, 6; dwErrCode
0x14000343a  call    cs:__imp_SetLastError
0x140003441  nop     dword ptr [rax+rax+00h]
0x140003446  call    cs:__imp_GetLastError
0x14000344d  nop     dword ptr [rax+rax+00h]
0x140003452  mov     ebx, eax
0x140003454  call    cs:__imp_RpcRevertToSelf
0x14000345b  nop     dword ptr [rax+rax+00h]
0x140003460  mov     ecx, ebx; dwErrCode
0x140003462  call    cs:__imp_SetLastError
0x140003469  nop     dword ptr [rax+rax+00h]
0x14000346e  xor     ebx, ebx
0x140003470  call    cs:__imp_GetLastError
0x140003477  nop     dword ptr [rax+rax+00h]
0x14000347c  cmp     eax, 7Ah ; 'z'
0x14000347f  jz      short loc_1400034A3
0x140003481  call    cs:__imp_GetLastError
0x140003488  nop     dword ptr [rax+rax+00h]
0x14000348d  mov     r8d, eax
0x140003490  lea     rdx, aFailedErrorD_1; "Failed. Error %d"
0x140003497  lea     rcx, aYgetprinterdri_2; "YGetPrinterDriver2"
0x14000349e  call    ?WriteDbgTraceError@SpoolerServiceTelemetry@@SAXPEADPEAGZZ; SpoolerServiceTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x1400034a3  cmp     rdi, r15
0x1400034a6  jz      short loc_1400034D8
0x1400034a8  test    rdi, rdi
0x1400034ab  jz      short loc_1400034C0
0x1400034ad  test    r15, r15
0x1400034b0  jz      short loc_1400034C0
0x1400034b2  mov     r8d, r13d; Size
0x1400034b5  mov     rdx, r15; Src
0x1400034b8  mov     rcx, rdi; void *
0x1400034bb  call    memcpy_0
0x1400034c0  mov     rcx, cs:?g_hSpoolssHeap@@3PEAXEA; hHeap
0x1400034c7  mov     r8, r15; lpMem
0x1400034ca  xor     edx, edx; dwFlags
0x1400034cc  call    cs:__imp_HeapFree
0x1400034d3  nop     dword ptr [rax+rax+00h]
0x1400034d8  mov     eax, [r12]
0x1400034dc  add     eax, 7
0x1400034df  and     eax, 0FFFFFFF8h
0x1400034e2  mov     [r12], eax
0x1400034e6  test    ebx, ebx
0x1400034e8  jz      loc_14000324B
0x1400034ee  xor     ebx, ebx
0x1400034f0  jmp     loc_140003259
```
