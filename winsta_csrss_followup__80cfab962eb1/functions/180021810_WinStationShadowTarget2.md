# _WinStationShadowTarget2

- ea: `0x180021810`
- end: `0x180021ae1`
- name: `_WinStationShadowTarget2`
- size: `721`
- prototype: `__int64 __usercall@<rax>(CPublicBinding *this@<rcx>, unsigned int@<edx>, struct _WINSTATIONCONFIG2W *@<r8>, struct _ICA_STACK_ADDRESS *, int, void *, unsigned int, void *, unsigned int, void *, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18002a5e0`

## callees

- `0x1800041a0`
- `0x180004558`
- `0x180005b40`
- `0x1800065f0`
- `0x1800075a0`
- `0x18000a784`
- `0x180021810`
- `0x18002f6c8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800218e1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180021ab2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800218e1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180021ab2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021893`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021893`
- `RPCRT4!NdrClientCall3` at `0x18002198c`
- `RPCRT4!NdrClientCall3` at `0x18002198c`

## string_xrefs

- `0x180021884`: `Failed to open binding`

## pseudocode

```c
__int64 __fastcall WinStationShadowTarget2(
        CPublicBinding *this,
        ULONG SessionId,
        struct _WINSTATIONCONFIG2W *a3,
        unsigned int a4,
        struct _ICA_STACK_ADDRESS *a5,
        unsigned int a6,
        void *a7,
        unsigned int a8,
        void *a9,
        unsigned int a10,
        int *a11,
        unsigned int a12)
{
  unsigned int v16; // esi
  int *v17; // rbx
  signed int LastError; // eax
  int Pointer; // ebx
  __int64 v20; // rax
  DWORD v21; // eax
  unsigned __int16 v23[36]; // [rsp+80h] [rbp-48h] BYREF

  v16 = -1073086416;
  v17 = a11;
  if ( a12 <= 1 )
    v17 = &dword_18003FF34;
  CSmartPublicBinding::CSmartPublicBinding((CSmartPublicBinding *)v23, this, 1);
  if ( !CSmartPublicBinding::operator void *(v23) )
  {
    _DbgPrintMessage(8, "Failed to open binding");
    LastError = GetLastError();
    Pointer = LastError;
    if ( LastError > 0 )
      Pointer = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_17;
  }
  if ( SessionId == -1 )
  {
    if ( !(unsigned int)IsLocalServer(this) )
    {
      Pointer = -2147467263;
      _DbgPrintMessage(4, "LOGONID_CURRENT specified for a remote server!");
LABEL_9:
      SetLastError(0x57u);
      goto LABEL_17;
    }
    SessionId = NtCurrentPeb()->SessionId;
  }
  v20 = CSmartPublicBinding::operator void *(v23);
  Pointer = (unsigned int)NdrClientCall3(
                            (MIDL_STUBLESS_PROXY_INFO *)&stru_180035078,
                            6u,
                            0,
                            v20,
                            SessionId,
                            a3,
                            a4,
                            a5,
                            a6,
                            a7,
                            a8,
                            a9,
                            a10,
                            v17).Pointer;
  v16 = Pointer & 0xEFFFFFFF;
  if ( Pointer == -2147023174 )
  {
    if ( a4 < 0x28E8 || a6 < 0x80 )
      goto LABEL_9;
    v16 = Legacy_WinStationShadowTarget(this, SessionId, a3, a5, a7, a8, a9, a10, a11, a12);
    Pointer = v16 | 0x10000000;
  }
  else
  {
    if ( Pointer >= 0 )
      goto LABEL_19;
    _DbgPrintMessage(8, "RpcShadowTarget failed: 0x%x in %s", Pointer, "_WinStationShadowTarget2");
  }
LABEL_17:
  if ( Pointer < 0 )
  {
    v21 = ConvertHRESULT2WIN32(Pointer);
    SetLastError(v21);
  }
LABEL_19:
  CSmartPublicBinding::~CSmartPublicBinding((CSmartPublicBinding *)v23);
  return v16;
}

```

## disassembly

```asm
0x180021810  mov     r11, rsp
0x180021813  mov     [r11+20h], r9d
0x180021817  mov     [r11+18h], r8
0x18002181b  mov     [rsp+arg_8], edx
0x18002181f  mov     [r11+8], rcx
0x180021823  push    rbx
0x180021824  push    rsi
0x180021825  push    rdi
0x180021826  push    r12
0x180021828  push    r13
0x18002182a  push    r14
0x18002182c  push    r15
0x18002182e  sub     rsp, 90h
0x180021835  mov     r15d, r9d
0x180021838  mov     r13, r8
0x18002183b  mov     edi, edx
0x18002183d  mov     r14, rcx
0x180021840  mov     esi, 0C00A0030h
0x180021845  lea     rax, dword_18003FF34
0x18002184c  mov     rbx, [rsp+0C8h+arg_50]
0x180021854  mov     r8d, 1; int
0x18002185a  cmp     [rsp+0C8h+arg_58], r8d
0x180021862  cmovbe  rbx, rax
0x180021866  mov     rdx, rcx; void *
0x180021869  lea     rcx, [r11-48h]; this
0x18002186d  call    ??0CSmartPublicBinding@@QEAA@PEAXH@Z; CSmartPublicBinding::CSmartPublicBinding(void *,int)
0x180021872  lea     rcx, [rsp+0C8h+var_48]; unsigned __int16 *
0x18002187a  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x18002187f  test    rax, rax
0x180021882  jnz     short loc_1800218B7
0x180021884  lea     rdx, aFailedToOpenBi_0; "Failed to open binding"
0x18002188b  lea     ecx, [rax+8]; int
0x18002188e  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180021893  call    cs:__imp_GetLastError
0x18002189a  nop     dword ptr [rax+rax+00h]
0x18002189f  mov     ebx, eax
0x1800218a1  test    eax, eax
0x1800218a3  jle     loc_180021AA5
0x1800218a9  movzx   ebx, ax
0x1800218ac  or      ebx, 80070000h
0x1800218b2  jmp     loc_180021AA5
0x1800218b7  cmp     edi, 0FFFFFFFFh
0x1800218ba  jnz     short loc_180021908
0x1800218bc  mov     rcx, r14; void *
0x1800218bf  call    ?IsLocalServer@@YAHPEAX@Z; IsLocalServer(void *)
0x1800218c4  test    eax, eax
0x1800218c6  jnz     short loc_1800218F2
0x1800218c8  mov     ebx, 80004001h
0x1800218cd  lea     rdx, aLogonidCurrent; "LOGONID_CURRENT specified for a remote "...
0x1800218d4  lea     ecx, [rax+4]; int
0x1800218d7  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800218dc  mov     ecx, 57h ; 'W'; dwErrCode
0x1800218e1  call    cs:__imp_SetLastError
0x1800218e8  nop     dword ptr [rax+rax+00h]
0x1800218ed  jmp     loc_180021AA5
0x1800218f2  mov     rax, gs:60h
0x1800218fb  mov     edi, [rax+2C0h]
0x180021901  mov     [rsp+0C8h+arg_8], edi
0x180021908  lea     rcx, [rsp+0C8h+var_48]; unsigned __int16 *
0x180021910  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x180021915  mov     [rsp+0C8h+var_50], 0
0x18002191e  mov     [rsp+0C8h+var_60], rbx
0x180021923  mov     ecx, [rsp+0C8h+arg_48]
0x18002192a  mov     [rsp+0C8h+var_68], ecx
0x18002192e  mov     rcx, [rsp+0C8h+arg_40]
0x180021936  mov     [rsp+0C8h+var_70], rcx
0x18002193b  mov     ecx, [rsp+0C8h+arg_38]
0x180021942  mov     [rsp+0C8h+var_78], ecx
0x180021946  mov     rcx, [rsp+0C8h+arg_30]
0x18002194e  mov     qword ptr [rsp+0C8h+var_80], rcx
0x180021953  mov     r12d, [rsp+0C8h+arg_28]
0x18002195b  mov     dword ptr [rsp+0C8h+var_88], r12d
0x180021960  mov     rcx, [rsp+0C8h+arg_20]
0x180021968  mov     qword ptr [rsp+0C8h+var_90], rcx
0x18002196d  mov     dword ptr [rsp+0C8h+var_98], r15d
0x180021972  mov     qword ptr [rsp+0C8h+var_A0], r13
0x180021977  mov     dword ptr [rsp+0C8h+var_A8], edi
0x18002197b  mov     r9, rax
0x18002197e  xor     r8d, r8d; pReturnValue
0x180021981  lea     edx, [r8+6]; nProcNum
0x180021985  lea     rcx, stru_180035078; pProxyInfo
0x18002198c  call    cs:__imp_NdrClientCall3
0x180021993  nop     dword ptr [rax+rax+00h]
0x180021998  mov     rbx, rax
0x18002199b  mov     [rsp+0C8h+var_50], rax
0x1800219a0  mov     [rsp+0C8h+var_58], eax
0x1800219a4  jmp     short loc_1800219F3
0x1800219a6  test    eax, eax
0x1800219a8  jle     short loc_1800219B2
0x1800219aa  movzx   eax, ax
0x1800219ad  or      eax, 80070000h
0x1800219b2  mov     ebx, eax
0x1800219b4  mov     [rsp+0C8h+var_58], eax
0x1800219b8  mov     r8d, eax
0x1800219bb  lea     rdx, aRpcshadowtarge; "RpcShadowTarget threw an exception: 0x%"...
0x1800219c2  mov     ecx, 8; int
0x1800219c7  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800219cc  mov     r12d, [rsp+0C8h+arg_28]
0x1800219d4  mov     r15d, [rsp+0C8h+arg_18]
0x1800219dc  mov     r13, [rsp+0C8h+arg_10]
0x1800219e4  mov     edi, [rsp+0C8h+arg_8]
0x1800219eb  mov     r14, [rsp+0C8h+arg_0]
0x1800219f3  mov     esi, ebx
0x1800219f5  btr     esi, 1Ch
0x1800219f9  cmp     ebx, 800706BAh
0x1800219ff  jnz     loc_180021A86
0x180021a05  cmp     r15d, 28E8h
0x180021a0c  jb      loc_1800218DC
0x180021a12  cmp     r12d, 80h
0x180021a19  jb      loc_1800218DC
0x180021a1f  mov     eax, [rsp+0C8h+arg_58]
0x180021a26  mov     [rsp+0C8h+var_80], eax; unsigned int
0x180021a2a  mov     rax, [rsp+0C8h+arg_50]
0x180021a32  mov     [rsp+0C8h+var_88], rax; void *
0x180021a37  mov     eax, [rsp+0C8h+arg_48]
0x180021a3e  mov     [rsp+0C8h+var_90], eax; unsigned int
0x180021a42  mov     rax, [rsp+0C8h+arg_40]
0x180021a4a  mov     [rsp+0C8h+var_98], rax; void *
0x180021a4f  mov     eax, [rsp+0C8h+arg_38]
0x180021a56  mov     [rsp+0C8h+var_A0], eax; unsigned int
0x180021a5a  mov     rax, [rsp+0C8h+arg_30]
0x180021a62  mov     [rsp+0C8h+var_A8], rax; void *
0x180021a67  mov     r9, [rsp+0C8h+arg_20]; struct _ICA_STACK_ADDRESS *
0x180021a6f  mov     r8, r13; struct _WINSTATIONCONFIG2W *
0x180021a72  mov     edx, edi; unsigned int
0x180021a74  mov     rcx, r14; this
0x180021a77  call    ?Legacy_WinStationShadowTarget@@YAJPEAXKPEAU_WINSTATIONCONFIG2W@@PEAU_ICA_STACK_ADDRESS@@0K0K0K@Z; Legacy_WinStationShadowTarget(void *,ulong,_WINSTATIONCONFIG2W *,_ICA_STACK_ADDRESS *,void *,ulong,void *,ulong,void *,ulong)
0x180021a7c  mov     esi, eax
0x180021a7e  mov     ebx, eax
0x180021a80  bts     ebx, 1Ch
0x180021a84  jmp     short loc_180021AA5
0x180021a86  test    ebx, ebx
0x180021a88  jns     short loc_180021ABE
0x180021a8a  lea     r9, aWinstationshad_8; "_WinStationShadowTarget2"
0x180021a91  mov     r8d, ebx
0x180021a94  lea     rdx, aRpcshadowtarge_0; "RpcShadowTarget failed: 0x%x in %s"
0x180021a9b  mov     ecx, 8; int
0x180021aa0  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180021aa5  test    ebx, ebx
0x180021aa7  jns     short loc_180021ABE
0x180021aa9  mov     ecx, ebx; int
0x180021aab  call    ?ConvertHRESULT2WIN32@@YAKJ@Z; ConvertHRESULT2WIN32(long)
0x180021ab0  mov     ecx, eax; dwErrCode
0x180021ab2  call    cs:__imp_SetLastError
0x180021ab9  nop     dword ptr [rax+rax+00h]
0x180021abe  lea     rcx, [rsp+0C8h+var_48]; this
0x180021ac6  call    ??1CSmartPublicBinding@@QEAA@XZ; CSmartPublicBinding::~CSmartPublicBinding(void)
0x180021acb  mov     eax, esi
0x180021acd  add     rsp, 90h
0x180021ad4  pop     r15
0x180021ad6  pop     r14
0x180021ad8  pop     r13
0x180021ada  pop     r12
0x180021adc  pop     rdi
0x180021add  pop     rsi
0x180021ade  pop     rbx
0x180021adf  retn
0x1800337a7  push    rbp
0x1800337a9  sub     rsp, 70h
0x1800337ad  mov     rbp, rdx
0x1800337b0  mov     rcx, [rcx]
0x1800337b3  mov     ecx, [rcx]; ExceptionCode
0x1800337b5  call    cs:__imp_I_RpcExceptionFilter
0x1800337bc  nop     dword ptr [rax+rax+00h]
0x1800337c1  nop
0x1800337c2  add     rsp, 70h
0x1800337c6  pop     rbp
0x1800337c7  retn
```
