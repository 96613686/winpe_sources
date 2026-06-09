# _WinStationShadowTarget2

- ea: `0x1800200c0`
- end: `0x180020378`
- name: `_WinStationShadowTarget2`
- size: `696`
- prototype: `__int64 __usercall@<rax>(CPublicBinding *this@<rcx>, unsigned int@<edx>, struct _WINSTATIONCONFIG2W *@<r8>, struct _ICA_STACK_ADDRESS *, int, void *, unsigned int, void *, unsigned int, void *, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180028a10`

## callees

- `0x180004554`
- `0x180005c30`
- `0x180005fcc`
- `0x180007890`
- `0x180008290`
- `0x180008e30`
- `0x1800200c0`
- `0x18002d2a0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002018b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180020350`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002018b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180020350`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020143`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020143`
- `RPCRT4!NdrClientCall3` at `0x180020230`
- `RPCRT4!NdrClientCall3` at `0x180020230`

## string_xrefs

- `0x180020134`: `Failed to open binding`

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
    v17 = &dword_18003D0CC;
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
                            (MIDL_STUBLESS_PROXY_INFO *)&stru_1800320E0,
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
0x1800200c0  mov     r11, rsp
0x1800200c3  mov     [r11+20h], r9d
0x1800200c7  mov     [r11+18h], r8
0x1800200cb  mov     [rsp+arg_8], edx
0x1800200cf  mov     [r11+8], rcx
0x1800200d3  push    rbx
0x1800200d4  push    rsi
0x1800200d5  push    rdi
0x1800200d6  push    r12
0x1800200d8  push    r13
0x1800200da  push    r14
0x1800200dc  push    r15
0x1800200de  sub     rsp, 90h
0x1800200e5  mov     r15d, r9d
0x1800200e8  mov     r13, r8
0x1800200eb  mov     edi, edx
0x1800200ed  mov     r14, rcx
0x1800200f0  mov     esi, 0C00A0030h
0x1800200f5  lea     rax, dword_18003D0CC
0x1800200fc  mov     rbx, [rsp+0C8h+arg_50]
0x180020104  mov     r8d, 1; int
0x18002010a  cmp     [rsp+0C8h+arg_58], r8d
0x180020112  cmovbe  rbx, rax
0x180020116  mov     rdx, rcx; void *
0x180020119  lea     rcx, [r11-48h]; this
0x18002011d  call    ??0CSmartPublicBinding@@QEAA@PEAXH@Z; CSmartPublicBinding::CSmartPublicBinding(void *,int)
0x180020122  lea     rcx, [rsp+0C8h+var_48]; unsigned __int16 *
0x18002012a  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x18002012f  test    rax, rax
0x180020132  jnz     short loc_180020161
0x180020134  lea     rdx, aFailedToOpenBi_0; "Failed to open binding"
0x18002013b  lea     ecx, [rax+8]; int
0x18002013e  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180020143  call    cs:__imp_GetLastError
0x180020149  mov     ebx, eax
0x18002014b  test    eax, eax
0x18002014d  jle     loc_180020343
0x180020153  movzx   ebx, ax
0x180020156  or      ebx, 80070000h
0x18002015c  jmp     loc_180020343
0x180020161  cmp     edi, 0FFFFFFFFh
0x180020164  jnz     short loc_1800201AC
0x180020166  mov     rcx, r14; void *
0x180020169  call    ?IsLocalServer@@YAHPEAX@Z; IsLocalServer(void *)
0x18002016e  test    eax, eax
0x180020170  jnz     short loc_180020196
0x180020172  mov     ebx, 80004001h
0x180020177  lea     rdx, aLogonidCurrent; "LOGONID_CURRENT specified for a remote "...
0x18002017e  lea     ecx, [rax+4]; int
0x180020181  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180020186  mov     ecx, 57h ; 'W'; dwErrCode
0x18002018b  call    cs:__imp_SetLastError
0x180020191  jmp     loc_180020343
0x180020196  mov     rax, gs:60h
0x18002019f  mov     edi, [rax+2C0h]
0x1800201a5  mov     [rsp+0C8h+arg_8], edi
0x1800201ac  lea     rcx, [rsp+0C8h+var_48]; unsigned __int16 *
0x1800201b4  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x1800201b9  mov     [rsp+0C8h+var_50], 0
0x1800201c2  mov     [rsp+0C8h+var_60], rbx
0x1800201c7  mov     ecx, [rsp+0C8h+arg_48]
0x1800201ce  mov     [rsp+0C8h+var_68], ecx
0x1800201d2  mov     rcx, [rsp+0C8h+arg_40]
0x1800201da  mov     [rsp+0C8h+var_70], rcx
0x1800201df  mov     ecx, [rsp+0C8h+arg_38]
0x1800201e6  mov     [rsp+0C8h+var_78], ecx
0x1800201ea  mov     rcx, [rsp+0C8h+arg_30]
0x1800201f2  mov     qword ptr [rsp+0C8h+var_80], rcx
0x1800201f7  mov     r12d, [rsp+0C8h+arg_28]
0x1800201ff  mov     dword ptr [rsp+0C8h+var_88], r12d
0x180020204  mov     rcx, [rsp+0C8h+arg_20]
0x18002020c  mov     qword ptr [rsp+0C8h+var_90], rcx
0x180020211  mov     dword ptr [rsp+0C8h+var_98], r15d
0x180020216  mov     qword ptr [rsp+0C8h+var_A0], r13
0x18002021b  mov     dword ptr [rsp+0C8h+var_A8], edi
0x18002021f  mov     r9, rax
0x180020222  xor     r8d, r8d; pReturnValue
0x180020225  lea     edx, [r8+6]; nProcNum
0x180020229  lea     rcx, stru_1800320E0; pProxyInfo
0x180020230  call    cs:__imp_NdrClientCall3
0x180020236  mov     rbx, rax
0x180020239  mov     [rsp+0C8h+var_50], rax
0x18002023e  mov     [rsp+0C8h+var_58], eax
0x180020242  jmp     short loc_180020291
0x180020244  test    eax, eax
0x180020246  jle     short loc_180020250
0x180020248  movzx   eax, ax
0x18002024b  or      eax, 80070000h
0x180020250  mov     ebx, eax
0x180020252  mov     [rsp+0C8h+var_58], eax
0x180020256  mov     r8d, eax
0x180020259  lea     rdx, aRpcshadowtarge; "RpcShadowTarget threw an exception: 0x%"...
0x180020260  mov     ecx, 8; int
0x180020265  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002026a  mov     r12d, [rsp+0C8h+arg_28]
0x180020272  mov     r15d, [rsp+0C8h+arg_18]
0x18002027a  mov     r13, [rsp+0C8h+arg_10]
0x180020282  mov     edi, [rsp+0C8h+arg_8]
0x180020289  mov     r14, [rsp+0C8h+arg_0]
0x180020291  mov     esi, ebx
0x180020293  btr     esi, 1Ch
0x180020297  cmp     ebx, 800706BAh
0x18002029d  jnz     loc_180020324
0x1800202a3  cmp     r15d, 28E8h
0x1800202aa  jb      loc_180020186
0x1800202b0  cmp     r12d, 80h
0x1800202b7  jb      loc_180020186
0x1800202bd  mov     eax, [rsp+0C8h+arg_58]
0x1800202c4  mov     [rsp+0C8h+var_80], eax; unsigned int
0x1800202c8  mov     rax, [rsp+0C8h+arg_50]
0x1800202d0  mov     [rsp+0C8h+var_88], rax; void *
0x1800202d5  mov     eax, [rsp+0C8h+arg_48]
0x1800202dc  mov     [rsp+0C8h+var_90], eax; unsigned int
0x1800202e0  mov     rax, [rsp+0C8h+arg_40]
0x1800202e8  mov     [rsp+0C8h+var_98], rax; void *
0x1800202ed  mov     eax, [rsp+0C8h+arg_38]
0x1800202f4  mov     [rsp+0C8h+var_A0], eax; unsigned int
0x1800202f8  mov     rax, [rsp+0C8h+arg_30]
0x180020300  mov     [rsp+0C8h+var_A8], rax; void *
0x180020305  mov     r9, [rsp+0C8h+arg_20]; struct _ICA_STACK_ADDRESS *
0x18002030d  mov     r8, r13; struct _WINSTATIONCONFIG2W *
0x180020310  mov     edx, edi; unsigned int
0x180020312  mov     rcx, r14; this
0x180020315  call    ?Legacy_WinStationShadowTarget@@YAJPEAXKPEAU_WINSTATIONCONFIG2W@@PEAU_ICA_STACK_ADDRESS@@0K0K0K@Z; Legacy_WinStationShadowTarget(void *,ulong,_WINSTATIONCONFIG2W *,_ICA_STACK_ADDRESS *,void *,ulong,void *,ulong,void *,ulong)
0x18002031a  mov     esi, eax
0x18002031c  mov     ebx, eax
0x18002031e  bts     ebx, 1Ch
0x180020322  jmp     short loc_180020343
0x180020324  test    ebx, ebx
0x180020326  jns     short loc_180020356
0x180020328  lea     r9, aWinstationshad_8; "_WinStationShadowTarget2"
0x18002032f  mov     r8d, ebx
0x180020332  lea     rdx, aRpcshadowtarge_0; "RpcShadowTarget failed: 0x%x in %s"
0x180020339  mov     ecx, 8; int
0x18002033e  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180020343  test    ebx, ebx
0x180020345  jns     short loc_180020356
0x180020347  mov     ecx, ebx; int
0x180020349  call    ?ConvertHRESULT2WIN32@@YAKJ@Z; ConvertHRESULT2WIN32(long)
0x18002034e  mov     ecx, eax; dwErrCode
0x180020350  call    cs:__imp_SetLastError
0x180020356  lea     rcx, [rsp+0C8h+var_48]; this
0x18002035e  call    ??1CSmartPublicBinding@@QEAA@XZ; CSmartPublicBinding::~CSmartPublicBinding(void)
0x180020363  mov     eax, esi
0x180020365  add     rsp, 90h
0x18002036c  pop     r15
0x18002036e  pop     r14
0x180020370  pop     r13
0x180020372  pop     r12
0x180020374  pop     rdi
0x180020375  pop     rsi
0x180020376  pop     rbx
0x180020377  retn
0x180030895  push    rbp
0x180030897  sub     rsp, 70h
0x18003089b  mov     rbp, rdx
0x18003089e  mov     rcx, [rcx]
0x1800308a1  mov     ecx, [rcx]; ExceptionCode
0x1800308a3  call    cs:__imp_I_RpcExceptionFilter
0x1800308a9  nop
0x1800308aa  add     rsp, 70h
0x1800308ae  pop     rbp
0x1800308af  retn
```
