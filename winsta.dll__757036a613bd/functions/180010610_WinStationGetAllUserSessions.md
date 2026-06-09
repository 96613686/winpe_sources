# WinStationGetAllUserSessions

- ea: `0x180010610`
- end: `0x180010973`
- name: `WinStationGetAllUserSessions`
- size: `867`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180005db0`
- `0x180005fcc`
- `0x180007890`
- `0x180008290`
- `0x180008e30`
- `0x180010610`
- `0x1800230b8`

## import_xrefs

- `ntdll!RtlValidSid` at `0x1800106d9`
- `ntdll!RtlValidSid` at `0x1800106d9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180010925`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180010968`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180010925`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180010968`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800108c8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800108f4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800108c8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800108f4`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180010825`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180010825`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800108b2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800108bd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800108b2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800108bd`
- `RPCRT4!I_RpcExceptionFilter` at `0x180030618`
- `RPCRT4!I_RpcExceptionFilter` at `0x180030618`
- `RPCRT4!NdrClientCall3` at `0x180010760`
- `RPCRT4!NdrClientCall3` at `0x180010760`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800106ef`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800106ef`

## string_xrefs

- `0x1800108e8`: `Failed to open binding failed: 0x%x in %s`
- `0x180010941`: `Invalid SID failed: 0x%x in %s`
- `0x180010914`: `ConvertSidToStringSid failed: 0x%x in %s`

## pseudocode

```c
bool __fastcall WinStationGetAllUserSessions(__int64 a1, void *a2, _QWORD *a3, unsigned int *a4)
{
  CLIENT_CALL_RETURN v7; // rbx
  CPublicBinding *v8; // rax
  const char *v9; // rdx
  __int64 Pointer_low; // r8
  LPWSTR v11; // rbx
  __int64 v12; // rax
  HLOCAL v14; // rax
  __int64 v15; // r10
  unsigned int i; // eax
  __int64 v17; // r8
  signed int LastError; // eax
  signed int v19; // eax
  DWORD v20; // eax
  unsigned int v21; // [rsp+40h] [rbp-58h] BYREF
  unsigned int v22[2]; // [rsp+48h] [rbp-50h] BYREF
  int Pointer; // [rsp+50h] [rbp-48h]
  HLOCAL hMem; // [rsp+58h] [rbp-40h] BYREF
  LPWSTR StringSid; // [rsp+60h] [rbp-38h] BYREF
  __int64 v26; // [rsp+68h] [rbp-30h] BYREF
  CPublicBinding *v27; // [rsp+70h] [rbp-28h]

  LODWORD(v7.Pointer) = -2147467263;
  hMem = 0;
  v21 = 0;
  v26 = 0;
  v22[0] = 0;
  v8 = (CPublicBinding *)operator new(0x40u, (const struct std::nothrow_t *)&std::nothrow);
  if ( v8 )
    v8 = CPublicBinding::CPublicBinding(v8, 0, 0, v22);
  v27 = v8;
  if ( v8 )
  {
    HIDWORD(v26) = 1;
  }
  else
  {
    SetLastError(0xEu);
    _DbgPrintMessage(8, "new CPublicBinding");
  }
  StringSid = 0;
  if ( !CSmartPublicBinding::operator void *((unsigned __int16 *)&v26) )
  {
    LastError = GetLastError();
    LODWORD(v7.Pointer) = LastError;
    if ( LastError > 0 )
      LODWORD(v7.Pointer) = (unsigned __int16)LastError | 0x80070000;
    if ( SLODWORD(v7.Simple) < 0 )
    {
      _DbgPrintMessage(
        8,
        "Failed to open binding failed: 0x%x in %s",
        LODWORD(v7.Pointer),
        "WinStationGetAllUserSessions");
      goto LABEL_18;
    }
  }
  if ( !a3 || !a4 || !a2 )
  {
    v9 = "ERROR_INVALID_PARAMETER failed: 0x%x in %s";
LABEL_8:
    Pointer_low = 2147942487LL;
LABEL_9:
    LODWORD(v7.Pointer) = Pointer_low;
LABEL_17:
    _DbgPrintMessage(8, v9, Pointer_low, "WinStationGetAllUserSessions");
    goto LABEL_18;
  }
  if ( !RtlValidSid(a2) )
  {
    v9 = "Invalid SID failed: 0x%x in %s";
    goto LABEL_8;
  }
  if ( !ConvertSidToStringSidW(a2, &StringSid) )
  {
    v19 = GetLastError();
    LODWORD(v7.Pointer) = v19;
    if ( v19 > 0 )
      LODWORD(v7.Pointer) = (unsigned __int16)v19 | 0x80070000;
    if ( SLODWORD(v7.Simple) < 0 )
    {
      _DbgPrintMessage(
        8,
        "ConvertSidToStringSid failed: 0x%x in %s",
        LODWORD(v7.Pointer),
        "WinStationGetAllUserSessions");
      goto LABEL_18;
    }
  }
  *a3 = 0;
  *a4 = 0;
  if ( CSmartPublicBinding::operator void *((unsigned __int16 *)&v26) )
  {
    v11 = StringSid;
    v12 = CSmartPublicBinding::operator void *((unsigned __int16 *)&v26);
    *(_QWORD *)v22 = 0;
    v7.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&stru_180032290, 5u, 0, v12, v11, &hMem, &v21).Pointer;
    *(CLIENT_CALL_RETURN *)v22 = v7;
    Pointer = (int)v7.Pointer;
    if ( SLODWORD(v7.Simple) < 0 )
    {
      Pointer_low = LODWORD(v7.Pointer);
      v9 = "RpcGetAllUserSessions failed: 0x%x in %s";
      goto LABEL_17;
    }
  }
  v14 = LocalAlloc(0x40u, 20LL * v21);
  *a3 = v14;
  if ( !v14 )
  {
    Pointer_low = 2147942414LL;
    v9 = "LocalAlloc failed: 0x%x in %s";
    goto LABEL_9;
  }
  v15 = 0;
  for ( i = v21; (unsigned int)v15 < v21; i = v21 )
  {
    v17 = 5 * v15;
    *(_DWORD *)(*a3 + 4 * v17) = 1;
    *(_DWORD *)(*a3 + 4 * v17 + 4) = *((_DWORD *)hMem + 4 * (unsigned int)v15);
    *(_DWORD *)(*a3 + 4 * v17 + 8) = *((_DWORD *)hMem + 4 * (unsigned int)v15 + 1);
    *(_DWORD *)(*a3 + 4 * v17 + 12) = *((_DWORD *)hMem + 4 * (unsigned int)v15 + 2);
    *(_DWORD *)(*a3 + 4 * v17 + 16) = *((_DWORD *)hMem + 4 * (unsigned int)v15 + 3);
    v15 = (unsigned int)(v15 + 1);
  }
  *a4 = i;
LABEL_18:
  if ( StringSid )
    LocalFree(StringSid);
  if ( SLODWORD(v7.Simple) < 0 )
  {
    v20 = ConvertHRESULT2WIN32(v7.Simple);
    SetLastError(v20);
  }
  if ( hMem )
    LocalFree(hMem);
  CSmartPublicBinding::~CSmartPublicBinding((CSmartPublicBinding *)&v26);
  return SLODWORD(v7.Pointer) >= 0;
}

```

## disassembly

```asm
0x180010610  mov     rax, rsp
0x180010613  mov     [rax+8], rbx
0x180010617  mov     [rax+20h], r9
0x18001061b  mov     [rax+18h], r8
0x18001061f  push    r12
0x180010621  push    r14
0x180010623  push    r15
0x180010625  sub     rsp, 80h
0x18001062c  mov     r15, r9
0x18001062f  mov     r14, r8
0x180010632  mov     r12, rdx
0x180010635  mov     ebx, 80004001h
0x18001063a  mov     qword ptr [rax-40h], 0
0x180010642  mov     dword ptr [rax-58h], 0
0x180010649  mov     qword ptr [rax-30h], 0
0x180010651  mov     dword ptr [rax-50h], 0
0x180010658  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001065f  mov     ecx, 40h ; '@'; unsigned __int64
0x180010664  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180010669  test    rax, rax
0x18001066c  jz      short loc_180010680
0x18001066e  lea     r9, [rsp+98h+var_50]; unsigned int *
0x180010673  xor     r8d, r8d; int
0x180010676  xor     edx, edx; unsigned __int16 *
0x180010678  mov     rcx, rax; this
0x18001067b  call    ??0CPublicBinding@@QEAA@PEBGHPEAK@Z; CPublicBinding::CPublicBinding(ushort const *,int,ulong *)
0x180010680  mov     [rsp+98h+var_28], rax
0x180010685  test    rax, rax
0x180010688  jz      loc_180010920
0x18001068e  mov     [rsp+98h+var_2C], 1
0x180010696  mov     [rsp+98h+StringSid], 0
0x18001069f  lea     rcx, [rsp+98h+var_30]; unsigned __int16 *
0x1800106a4  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x1800106a9  test    rax, rax
0x1800106ac  jz      loc_1800108C8
0x1800106b2  test    r14, r14
0x1800106b5  jnz     short loc_1800106CC
0x1800106b7  lea     rdx, aErrorInvalidPa; "ERROR_INVALID_PARAMETER failed: 0x%x in"...
0x1800106be  mov     r8d, 80070057h
0x1800106c4  mov     ebx, r8d
0x1800106c7  jmp     loc_1800107B8
0x1800106cc  test    r15, r15
0x1800106cf  jz      short loc_1800106B7
0x1800106d1  test    r12, r12
0x1800106d4  jz      short loc_1800106B7
0x1800106d6  mov     rcx, r12; Sid
0x1800106d9  call    cs:__imp_RtlValidSid
0x1800106df  test    al, al
0x1800106e1  jz      loc_180010941
0x1800106e7  lea     rdx, [rsp+98h+StringSid]; StringSid
0x1800106ec  mov     rcx, r12; Sid
0x1800106ef  call    cs:__imp_ConvertSidToStringSidW
0x1800106f5  test    eax, eax
0x1800106f7  jz      loc_1800108F4
0x1800106fd  mov     qword ptr [r14], 0
0x180010704  mov     dword ptr [r15], 0
0x18001070b  lea     rcx, [rsp+98h+var_30]; unsigned __int16 *
0x180010710  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x180010715  test    rax, rax
0x180010718  jz      loc_180010814
0x18001071e  mov     rbx, [rsp+98h+StringSid]
0x180010723  lea     rcx, [rsp+98h+var_30]; unsigned __int16 *
0x180010728  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x18001072d  mov     qword ptr [rsp+98h+var_50], 0
0x180010736  lea     rcx, [rsp+98h+var_58]
0x18001073b  mov     [rsp+98h+var_68], rcx
0x180010740  lea     rcx, [rsp+98h+hMem]
0x180010745  mov     [rsp+98h+var_70], rcx
0x18001074a  mov     [rsp+98h+var_78], rbx
0x18001074f  mov     r9, rax
0x180010752  xor     r8d, r8d; pReturnValue
0x180010755  lea     edx, [r8+5]; nProcNum
0x180010759  lea     rcx, stru_180032290; pProxyInfo
0x180010760  call    cs:__imp_NdrClientCall3
0x180010766  mov     rbx, rax
0x180010769  mov     qword ptr [rsp+98h+var_50], rax
0x18001076e  mov     [rsp+98h+var_48], eax
0x180010772  jmp     short loc_1800107AA
0x180010774  test    eax, eax
0x180010776  jle     short loc_180010780
0x180010778  movzx   eax, ax
0x18001077b  or      eax, 80070000h
0x180010780  mov     ebx, eax
0x180010782  mov     [rsp+98h+var_48], eax
0x180010786  mov     r8d, eax
0x180010789  lea     rdx, aRpcgetallusers_0; "RpcGetAllUserSessions threw an exceptio"...
0x180010790  mov     ecx, 8; int
0x180010795  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18001079a  mov     r15, [rsp+98h+arg_18]
0x1800107a2  mov     r14, [rsp+98h+arg_10]
0x1800107aa  test    ebx, ebx
0x1800107ac  jns     short loc_180010814
0x1800107ae  mov     r8d, ebx
0x1800107b1  lea     rdx, aRpcgetallusers; "RpcGetAllUserSessions failed: 0x%x in %"...
0x1800107b8  lea     r9, aWinstationgeta_6; "WinStationGetAllUserSessions"
0x1800107bf  mov     ecx, 8; int
0x1800107c4  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800107c9  mov     rcx, [rsp+98h+StringSid]; hMem
0x1800107ce  test    rcx, rcx
0x1800107d1  jnz     loc_1800108BD
0x1800107d7  test    ebx, ebx
0x1800107d9  js      loc_18001095F
0x1800107df  mov     rcx, [rsp+98h+hMem]; hMem
0x1800107e4  test    rcx, rcx
0x1800107e7  jnz     loc_1800108B2
0x1800107ed  test    ebx, ebx
0x1800107ef  setns   bl
0x1800107f2  lea     rcx, [rsp+98h+var_30]; this
0x1800107f7  call    ??1CSmartPublicBinding@@QEAA@XZ; CSmartPublicBinding::~CSmartPublicBinding(void)
0x1800107fc  mov     al, bl
0x1800107fe  mov     rbx, [rsp+98h+arg_0]
0x180010806  add     rsp, 80h
0x18001080d  pop     r15
0x18001080f  pop     r14
0x180010811  pop     r12
0x180010813  retn
0x180010814  mov     eax, [rsp+98h+var_58]
0x180010818  lea     rdx, [rax+rax*4]
0x18001081c  shl     rdx, 2; uBytes
0x180010820  mov     ecx, 40h ; '@'; uFlags
0x180010825  call    cs:__imp_LocalAlloc
0x18001082b  mov     [r14], rax
0x18001082e  test    rax, rax
0x180010831  jz      loc_18001094D
0x180010837  xor     r10d, r10d
0x18001083a  mov     eax, [rsp+98h+var_58]
0x18001083e  test    eax, eax
0x180010840  jz      short loc_1800108AA
0x180010842  mov     r9d, r10d
0x180010845  lea     r8, [r10+r10*4]
0x180010849  mov     rax, [r14]
0x18001084c  mov     dword ptr [rax+r8*4], 1
0x180010854  add     r9, r9
0x180010857  mov     rdx, [r14]
0x18001085a  mov     rax, [rsp+98h+hMem]
0x18001085f  mov     ecx, [rax+r9*8]
0x180010863  mov     [rdx+r8*4+4], ecx
0x180010868  mov     rdx, [r14]
0x18001086b  mov     rax, [rsp+98h+hMem]
0x180010870  mov     ecx, [rax+r9*8+4]
0x180010875  mov     [rdx+r8*4+8], ecx
0x18001087a  mov     rdx, [r14]
0x18001087d  mov     rax, [rsp+98h+hMem]
0x180010882  mov     ecx, [rax+r9*8+8]
0x180010887  mov     [rdx+r8*4+0Ch], ecx
0x18001088c  mov     rdx, [r14]
0x18001088f  mov     rax, [rsp+98h+hMem]
0x180010894  mov     ecx, [rax+r9*8+0Ch]
0x180010899  mov     [rdx+r8*4+10h], ecx
0x18001089e  inc     r10d
0x1800108a1  mov     eax, [rsp+98h+var_58]
0x1800108a5  cmp     r10d, eax
0x1800108a8  jb      short loc_180010842
0x1800108aa  mov     [r15], eax
0x1800108ad  jmp     loc_1800107C9
0x1800108b2  call    cs:__imp_LocalFree
0x1800108b8  jmp     loc_1800107ED
0x1800108bd  call    cs:__imp_LocalFree
0x1800108c3  jmp     loc_1800107D7
0x1800108c8  call    cs:__imp_GetLastError
0x1800108ce  mov     ebx, eax
0x1800108d0  test    eax, eax
0x1800108d2  jle     short loc_1800108DD
0x1800108d4  movzx   ebx, ax
0x1800108d7  or      ebx, 80070000h
0x1800108dd  test    ebx, ebx
0x1800108df  jns     loc_1800106B2
0x1800108e5  mov     r8d, ebx
0x1800108e8  lea     rdx, aFailedToOpenBi; "Failed to open binding failed: 0x%x in "...
0x1800108ef  jmp     loc_1800107B8
0x1800108f4  call    cs:__imp_GetLastError
0x1800108fa  mov     ebx, eax
0x1800108fc  test    eax, eax
0x1800108fe  jle     short loc_180010909
0x180010900  movzx   ebx, ax
0x180010903  or      ebx, 80070000h
0x180010909  test    ebx, ebx
0x18001090b  jns     loc_1800106FD
0x180010911  mov     r8d, ebx
0x180010914  lea     rdx, aConvertsidtost_0; "ConvertSidToStringSid failed: 0x%x in %"...
0x18001091b  jmp     loc_1800107B8
0x180010920  mov     ecx, 0Eh; dwErrCode
0x180010925  call    cs:__imp_SetLastError
0x18001092b  lea     rdx, aNewCpublicbind; "new CPublicBinding"
0x180010932  mov     ecx, 8; int
0x180010937  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18001093c  jmp     loc_180010696
0x180010941  lea     rdx, aInvalidSidFail; "Invalid SID failed: 0x%x in %s"
0x180010948  jmp     loc_1800106BE
0x18001094d  mov     r8d, 8007000Eh
0x180010953  lea     rdx, aLocalallocFail; "LocalAlloc failed: 0x%x in %s"
0x18001095a  jmp     loc_1800106C4
0x18001095f  mov     ecx, ebx; int
0x180010961  call    ?ConvertHRESULT2WIN32@@YAKJ@Z; ConvertHRESULT2WIN32(long)
0x180010966  mov     ecx, eax; dwErrCode
0x180010968  call    cs:__imp_SetLastError
0x18001096e  jmp     loc_1800107DF
0x18003060a  push    rbp
0x18003060c  sub     rsp, 40h
0x180030610  mov     rbp, rdx
0x180030613  mov     rcx, [rcx]
0x180030616  mov     ecx, [rcx]; ExceptionCode
0x180030618  call    cs:__imp_I_RpcExceptionFilter
0x18003061e  nop
0x18003061f  add     rsp, 40h
0x180030623  pop     rbp
0x180030624  retn
```
