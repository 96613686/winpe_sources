# WinStationGetAllUserSessions

- ea: `0x180011550`
- end: `0x1800118f0`
- name: `WinStationGetAllUserSessions`
- size: `928`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180004330`
- `0x180004558`
- `0x180005b40`
- `0x1800065f0`
- `0x1800075a0`
- `0x180011550`
- `0x1800249e8`

## import_xrefs

- `ntdll!RtlValidSid` at `0x180011619`
- `ntdll!RtlValidSid` at `0x180011619`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180011896`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800118df`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180011896`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800118df`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001182d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001185f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001182d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001185f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180011778`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180011778`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001180b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001181c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001180b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001181c`
- `RPCRT4!I_RpcExceptionFilter` at `0x1800334e6`
- `RPCRT4!I_RpcExceptionFilter` at `0x1800334e6`
- `RPCRT4!NdrClientCall3` at `0x1800116ac`
- `RPCRT4!NdrClientCall3` at `0x1800116ac`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180011635`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180011635`

## string_xrefs

- `0x180011853`: `Failed to open binding failed: 0x%x in %s`
- `0x1800118b8`: `Invalid SID failed: 0x%x in %s`
- `0x180011885`: `ConvertSidToStringSid failed: 0x%x in %s`

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
    v7.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&stru_180035290, 5u, 0, v12, v11, &hMem, &v21).Pointer;
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
0x180011550  mov     rax, rsp
0x180011553  mov     [rax+8], rbx
0x180011557  mov     [rax+20h], r9
0x18001155b  mov     [rax+18h], r8
0x18001155f  push    r12
0x180011561  push    r14
0x180011563  push    r15
0x180011565  sub     rsp, 80h
0x18001156c  mov     r15, r9
0x18001156f  mov     r14, r8
0x180011572  mov     r12, rdx
0x180011575  mov     ebx, 80004001h
0x18001157a  mov     qword ptr [rax-40h], 0
0x180011582  mov     dword ptr [rax-58h], 0
0x180011589  mov     qword ptr [rax-30h], 0
0x180011591  mov     dword ptr [rax-50h], 0
0x180011598  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001159f  mov     ecx, 40h ; '@'; unsigned __int64
0x1800115a4  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800115a9  test    rax, rax
0x1800115ac  jz      short loc_1800115C0
0x1800115ae  lea     r9, [rsp+98h+var_50]; unsigned int *
0x1800115b3  xor     r8d, r8d; int
0x1800115b6  xor     edx, edx; unsigned __int16 *
0x1800115b8  mov     rcx, rax; this
0x1800115bb  call    ??0CPublicBinding@@QEAA@PEBGHPEAK@Z; CPublicBinding::CPublicBinding(ushort const *,int,ulong *)
0x1800115c0  mov     [rsp+98h+var_28], rax
0x1800115c5  test    rax, rax
0x1800115c8  jz      loc_180011891
0x1800115ce  mov     [rsp+98h+var_2C], 1
0x1800115d6  mov     [rsp+98h+StringSid], 0
0x1800115df  lea     rcx, [rsp+98h+var_30]; unsigned __int16 *
0x1800115e4  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x1800115e9  test    rax, rax
0x1800115ec  jz      loc_18001182D
0x1800115f2  test    r14, r14
0x1800115f5  jnz     short loc_18001160C
0x1800115f7  lea     rdx, aErrorInvalidPa; "ERROR_INVALID_PARAMETER failed: 0x%x in"...
0x1800115fe  mov     r8d, 80070057h
0x180011604  mov     ebx, r8d
0x180011607  jmp     loc_18001170A
0x18001160c  test    r15, r15
0x18001160f  jz      short loc_1800115F7
0x180011611  test    r12, r12
0x180011614  jz      short loc_1800115F7
0x180011616  mov     rcx, r12; Sid
0x180011619  call    cs:__imp_RtlValidSid
0x180011620  nop     dword ptr [rax+rax+00h]
0x180011625  test    al, al
0x180011627  jz      loc_1800118B8
0x18001162d  lea     rdx, [rsp+98h+StringSid]; StringSid
0x180011632  mov     rcx, r12; Sid
0x180011635  call    cs:__imp_ConvertSidToStringSidW
0x18001163c  nop     dword ptr [rax+rax+00h]
0x180011641  test    eax, eax
0x180011643  jz      loc_18001185F
0x180011649  mov     qword ptr [r14], 0
0x180011650  mov     dword ptr [r15], 0
0x180011657  lea     rcx, [rsp+98h+var_30]; unsigned __int16 *
0x18001165c  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x180011661  test    rax, rax
0x180011664  jz      loc_180011767
0x18001166a  mov     rbx, [rsp+98h+StringSid]
0x18001166f  lea     rcx, [rsp+98h+var_30]; unsigned __int16 *
0x180011674  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x180011679  mov     qword ptr [rsp+98h+var_50], 0
0x180011682  lea     rcx, [rsp+98h+var_58]
0x180011687  mov     [rsp+98h+var_68], rcx
0x18001168c  lea     rcx, [rsp+98h+hMem]
0x180011691  mov     [rsp+98h+var_70], rcx
0x180011696  mov     [rsp+98h+var_78], rbx
0x18001169b  mov     r9, rax
0x18001169e  xor     r8d, r8d; pReturnValue
0x1800116a1  lea     edx, [r8+5]; nProcNum
0x1800116a5  lea     rcx, stru_180035290; pProxyInfo
0x1800116ac  call    cs:__imp_NdrClientCall3
0x1800116b3  nop     dword ptr [rax+rax+00h]
0x1800116b8  mov     rbx, rax
0x1800116bb  mov     qword ptr [rsp+98h+var_50], rax
0x1800116c0  mov     [rsp+98h+var_48], eax
0x1800116c4  jmp     short loc_1800116FC
0x1800116c6  test    eax, eax
0x1800116c8  jle     short loc_1800116D2
0x1800116ca  movzx   eax, ax
0x1800116cd  or      eax, 80070000h
0x1800116d2  mov     ebx, eax
0x1800116d4  mov     [rsp+98h+var_48], eax
0x1800116d8  mov     r8d, eax
0x1800116db  lea     rdx, aRpcgetallusers_0; "RpcGetAllUserSessions threw an exceptio"...
0x1800116e2  mov     ecx, 8; int
0x1800116e7  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800116ec  mov     r15, [rsp+98h+arg_18]
0x1800116f4  mov     r14, [rsp+98h+arg_10]
0x1800116fc  test    ebx, ebx
0x1800116fe  jns     short loc_180011767
0x180011700  mov     r8d, ebx
0x180011703  lea     rdx, aRpcgetallusers; "RpcGetAllUserSessions failed: 0x%x in %"...
0x18001170a  lea     r9, aWinstationgeta_6; "WinStationGetAllUserSessions"
0x180011711  mov     ecx, 8; int
0x180011716  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18001171b  mov     rcx, [rsp+98h+StringSid]; hMem
0x180011720  test    rcx, rcx
0x180011723  jnz     loc_18001181C
0x180011729  test    ebx, ebx
0x18001172b  js      loc_1800118D6
0x180011731  mov     rcx, [rsp+98h+hMem]; hMem
0x180011736  test    rcx, rcx
0x180011739  jnz     loc_18001180B
0x18001173f  test    ebx, ebx
0x180011741  setns   bl
0x180011744  lea     rcx, [rsp+98h+var_30]; this
0x180011749  call    ??1CSmartPublicBinding@@QEAA@XZ; CSmartPublicBinding::~CSmartPublicBinding(void)
0x18001174e  mov     al, bl
0x180011750  mov     rbx, [rsp+98h+arg_0]
0x180011758  add     rsp, 80h
0x18001175f  pop     r15
0x180011761  pop     r14
0x180011763  pop     r12
0x180011765  retn
0x180011767  mov     eax, [rsp+98h+var_58]
0x18001176b  lea     rdx, [rax+rax*4]
0x18001176f  shl     rdx, 2; uBytes
0x180011773  mov     ecx, 40h ; '@'; uFlags
0x180011778  call    cs:__imp_LocalAlloc
0x18001177f  nop     dword ptr [rax+rax+00h]
0x180011784  mov     [r14], rax
0x180011787  test    rax, rax
0x18001178a  jz      loc_1800118C4
0x180011790  xor     r10d, r10d
0x180011793  mov     eax, [rsp+98h+var_58]
0x180011797  test    eax, eax
0x180011799  jz      short loc_180011803
0x18001179b  mov     r9d, r10d
0x18001179e  lea     r8, [r10+r10*4]
0x1800117a2  mov     rax, [r14]
0x1800117a5  mov     dword ptr [rax+r8*4], 1
0x1800117ad  add     r9, r9
0x1800117b0  mov     rdx, [r14]
0x1800117b3  mov     rax, [rsp+98h+hMem]
0x1800117b8  mov     ecx, [rax+r9*8]
0x1800117bc  mov     [rdx+r8*4+4], ecx
0x1800117c1  mov     rdx, [r14]
0x1800117c4  mov     rax, [rsp+98h+hMem]
0x1800117c9  mov     ecx, [rax+r9*8+4]
0x1800117ce  mov     [rdx+r8*4+8], ecx
0x1800117d3  mov     rdx, [r14]
0x1800117d6  mov     rax, [rsp+98h+hMem]
0x1800117db  mov     ecx, [rax+r9*8+8]
0x1800117e0  mov     [rdx+r8*4+0Ch], ecx
0x1800117e5  mov     rdx, [r14]
0x1800117e8  mov     rax, [rsp+98h+hMem]
0x1800117ed  mov     ecx, [rax+r9*8+0Ch]
0x1800117f2  mov     [rdx+r8*4+10h], ecx
0x1800117f7  inc     r10d
0x1800117fa  mov     eax, [rsp+98h+var_58]
0x1800117fe  cmp     r10d, eax
0x180011801  jb      short loc_18001179B
0x180011803  mov     [r15], eax
0x180011806  jmp     loc_18001171B
0x18001180b  call    cs:__imp_LocalFree
0x180011812  nop     dword ptr [rax+rax+00h]
0x180011817  jmp     loc_18001173F
0x18001181c  call    cs:__imp_LocalFree
0x180011823  nop     dword ptr [rax+rax+00h]
0x180011828  jmp     loc_180011729
0x18001182d  call    cs:__imp_GetLastError
0x180011834  nop     dword ptr [rax+rax+00h]
0x180011839  mov     ebx, eax
0x18001183b  test    eax, eax
0x18001183d  jle     short loc_180011848
0x18001183f  movzx   ebx, ax
0x180011842  or      ebx, 80070000h
0x180011848  test    ebx, ebx
0x18001184a  jns     loc_1800115F2
0x180011850  mov     r8d, ebx
0x180011853  lea     rdx, aFailedToOpenBi; "Failed to open binding failed: 0x%x in "...
0x18001185a  jmp     loc_18001170A
0x18001185f  call    cs:__imp_GetLastError
0x180011866  nop     dword ptr [rax+rax+00h]
0x18001186b  mov     ebx, eax
0x18001186d  test    eax, eax
0x18001186f  jle     short loc_18001187A
0x180011871  movzx   ebx, ax
0x180011874  or      ebx, 80070000h
0x18001187a  test    ebx, ebx
0x18001187c  jns     loc_180011649
0x180011882  mov     r8d, ebx
0x180011885  lea     rdx, aConvertsidtost_0; "ConvertSidToStringSid failed: 0x%x in %"...
0x18001188c  jmp     loc_18001170A
0x180011891  mov     ecx, 0Eh; dwErrCode
0x180011896  call    cs:__imp_SetLastError
0x18001189d  nop     dword ptr [rax+rax+00h]
0x1800118a2  lea     rdx, aNewCpublicbind; "new CPublicBinding"
0x1800118a9  mov     ecx, 8; int
0x1800118ae  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800118b3  jmp     loc_1800115D6
0x1800118b8  lea     rdx, aInvalidSidFail; "Invalid SID failed: 0x%x in %s"
0x1800118bf  jmp     loc_1800115FE
0x1800118c4  mov     r8d, 8007000Eh
0x1800118ca  lea     rdx, aLocalallocFail; "LocalAlloc failed: 0x%x in %s"
0x1800118d1  jmp     loc_180011604
0x1800118d6  mov     ecx, ebx; int
0x1800118d8  call    ?ConvertHRESULT2WIN32@@YAKJ@Z; ConvertHRESULT2WIN32(long)
0x1800118dd  mov     ecx, eax; dwErrCode
0x1800118df  call    cs:__imp_SetLastError
0x1800118e6  nop     dword ptr [rax+rax+00h]
0x1800118eb  jmp     loc_180011731
0x1800334d8  push    rbp
0x1800334da  sub     rsp, 40h
0x1800334de  mov     rbp, rdx
0x1800334e1  mov     rcx, [rcx]
0x1800334e4  mov     ecx, [rcx]; ExceptionCode
0x1800334e6  call    cs:__imp_I_RpcExceptionFilter
0x1800334ed  nop     dword ptr [rax+rax+00h]
0x1800334f2  nop
0x1800334f3  add     rsp, 40h
0x1800334f7  pop     rbp
0x1800334f8  retn
```
