# GetWinStationInformationEx(void *,ulong,_WINSTATIONINFORMATIONEX *,ulong,ulong *)

- ea: `0x180003480`
- end: `0x1800038b7`
- name: `?GetWinStationInformationEx@@YAJPEAXKPEAU_WINSTATIONINFORMATIONEX@@KPEAK@Z`
- size: `1079`
- prototype: `__int64 __usercall@<rax>(void *@<rcx>, unsigned int@<edx>, struct _WINSTATIONINFORMATIONEX *@<r8>, unsigned int@<r9d>, unsigned int *)`
- caller_count: `1`
- callee_count: `17`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180009dec`

## callees

- `0x180002df0`
- `0x1800032b4`
- `0x180003338`
- `0x180003480`
- `0x180004558`
- `0x180005280`
- `0x180005b40`
- `0x1800065f0`
- `0x1800066d0`
- `0x1800075a0`
- `0x180007fe0`
- `0x180022bb8`
- `0x180023768`
- `0x1800249e8`
- `0x180024a1c`
- `0x180032be6`
- `0x180032c20`

## import_xrefs

- `ntdll!NtQuerySystemTime` at `0x1800036a1`
- `ntdll!NtQuerySystemTime` at `0x1800036a1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800037c3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800037c3`

## string_xrefs

- `0x18000372a`: `StringCchCopy failed: %x`
- `0x18000379a`: `CopySessionExInfo failed: 0x%x in %s`
- `0x18000380f`: `GetProtocolStatus failed: 0x%x`
- `0x18000387c`: `_GetSessionProtocolLastInputTime`
- `0x180003886`: `GetSessionProtocolLastInputTime failed: 0x%x in %s`
- `0x1800038a1`: `_GetSessionProtocolLastInputTime failed: 0x%x in %s`

## pseudocode

```c
__int64 __fastcall GetWinStationInformationEx(
        void *a1,
        unsigned int a2,
        struct _WINSTATIONINFORMATIONEX *a3,
        unsigned int a4,
        unsigned int *a5)
{
  _QWORD *v9; // rax
  _QWORD *v10; // rbx
  _WORD *v11; // rax
  _WORD *v12; // r9
  __int64 v13; // rcx
  int *v14; // rdx
  __int64 v15; // r10
  _WORD *v16; // rcx
  int v17; // edi
  void *v18; // rax
  int SessionInformation; // eax
  unsigned int ProtocolStatus; // edi
  int v21; // eax
  union _LARGE_INTEGER *v22; // rbx
  union _LARGE_INTEGER v23; // r14
  unsigned int v24; // r15d
  int SessionProtocolLastInputTime; // eax
  int LastInputTime; // eax
  unsigned __int16 v28[4]; // [rsp+20h] [rbp-188h] BYREF
  void *v29; // [rsp+28h] [rbp-180h]
  __int64 v30; // [rsp+30h] [rbp-178h] BYREF
  unsigned int v31; // [rsp+38h] [rbp-170h]
  __int128 v32; // [rsp+40h] [rbp-168h]
  __int128 v33; // [rsp+50h] [rbp-158h]
  __int128 v34; // [rsp+60h] [rbp-148h]
  __int64 v35; // [rsp+70h] [rbp-138h]
  _BYTE v36[208]; // [rsp+78h] [rbp-130h] BYREF
  __int64 v37; // [rsp+148h] [rbp-60h]

  v31 = -1;
  v30 = 0;
  v37 = 0;
  v35 = 0;
  v32 = 0;
  v33 = 0;
  v34 = 0;
  memset_0(v36, 0, sizeof(v36));
  *(_QWORD *)v28 = 0;
  if ( a1 )
  {
    v29 = a1;
  }
  else
  {
    v9 = operator new(0x40u, (const struct std::nothrow_t *)&std::nothrow);
    v10 = v9;
    if ( v9 )
    {
      *v9 = 0;
      v9[1] = 0;
      v9[2] = 0;
      v9[3] = 0;
      v9[4] = 0;
      v9[5] = 0;
      v9[6] = 1;
      v9[7] = 0;
      v11 = operator new[](2u, (const struct std::nothrow_t *)&std::nothrow);
      v10[5] = v11;
      v12 = v11;
      if ( v11 )
      {
        v13 = 2147483646;
        v14 = &dword_18003FF34;
        v15 = 1;
        do
        {
          if ( !v13 )
            break;
          if ( !*(_WORD *)v14 )
            break;
          *v12 = *(_WORD *)v14;
          v14 = (int *)((char *)v14 + 2);
          ++v12;
          --v13;
          --v15;
        }
        while ( v15 );
        v16 = v12 - 1;
        v17 = -2147024774;
        if ( v15 )
        {
          v16 = v12;
          v17 = 0;
        }
        *v16 = 0;
        if ( v15 )
        {
          if ( !v10[3] && !*((_DWORD *)v10 + 12) )
          {
            if ( (unsigned int)CPublicBinding::OpenSessionContextHandle((CPublicBinding *)v10) == -2147023174 )
              *((_DWORD *)v10 + 13) = 1;
            CPublicBinding::CloseSessionContextHandle((CPublicBinding *)v10);
          }
        }
        else
        {
          ConvertHRESULT2WIN32(v17);
          _DbgPrintMessage(8, "StringCchCopy failed: %x", v17);
        }
      }
      v29 = v10;
      *(_DWORD *)&v28[2] = 1;
    }
    else
    {
      v29 = 0;
      SetLastError(0xEu);
      _DbgPrintMessage(8, "new CPublicBinding");
    }
  }
  if ( a4 < 0x4C8 )
  {
    ProtocolStatus = -2147024809;
    goto LABEL_25;
  }
  v18 = (void *)CSmartPublicBinding::operator void *(v28);
  SessionInformation = CSmartSession::GetSessionInformationEx((CSmartSession *)&v30, a2, v18);
  ProtocolStatus = SessionInformation;
  if ( SessionInformation < 0 )
  {
    _DbgPrintMessage(8, "GetSessionInformationEx failed: 0x%x in %s", SessionInformation, "GetWinStationInformationEx");
    goto LABEL_25;
  }
  if ( HIDWORD(v37) == 1 )
  {
    v21 = CSmartSession::CopySessionExInfo((CSmartSession *)&v30, a2, a3);
    ProtocolStatus = v21;
    if ( v21 < 0 )
    {
      _DbgPrintMessage(8, "CopySessionExInfo failed: 0x%x in %s", v21, "GetWinStationInformationEx");
      goto LABEL_25;
    }
  }
  v22 = 0;
  if ( *(_DWORD *)a3 )
    v22 = (union _LARGE_INTEGER *)((char *)a3 + 8);
  v23 = v22[22];
  if ( v22->HighPart == 4 )
  {
LABEL_23:
    memset_0(&v22[25], 0, 0x3F4u);
    v22[23] = v23;
    goto LABEL_24;
  }
  v24 = v31;
  SessionProtocolLastInputTime = GetSessionProtocolLastInputTime(a1, v31, (struct _PROTOCOLSTATUS *)&v22[25], v22 + 23);
  ProtocolStatus = SessionProtocolLastInputTime;
  if ( SessionProtocolLastInputTime != -2147023151 )
  {
    if ( SessionProtocolLastInputTime != -2147467262
      && SessionProtocolLastInputTime != -2147022646
      && SessionProtocolLastInputTime != -2147023174
      && SessionProtocolLastInputTime != -2147023179 )
    {
      if ( SessionProtocolLastInputTime >= 0 )
        goto LABEL_24;
      _DbgPrintMessage(
        8,
        "GetSessionProtocolLastInputTime failed: 0x%x in %s",
        SessionProtocolLastInputTime,
        "_GetSessionProtocolLastInputTime");
LABEL_51:
      _DbgPrintMessage(
        8,
        "_GetSessionProtocolLastInputTime failed: 0x%x in %s",
        ProtocolStatus,
        "GetWinStationInformationEx");
      goto LABEL_25;
    }
    goto LABEL_23;
  }
  ProtocolStatus = GetProtocolStatus(a1, v24, (struct _PROTOCOLSTATUS *)&v22[25]);
  if ( (int)(ProtocolStatus + 0x80000000) >= 0 && ProtocolStatus != -2147467262 )
  {
    _DbgPrintMessage(8, "GetProtocolStatus failed: 0x%x", ProtocolStatus);
    goto LABEL_51;
  }
  LastInputTime = GetLastInputTime(a1, v24, v22 + 23);
  ProtocolStatus = LastInputTime;
  if ( LastInputTime >= 0 )
    goto LABEL_24;
  if ( LastInputTime != -2147467262
    && LastInputTime != -2147022646
    && LastInputTime != -2147023174
    && LastInputTime != -2147023179 )
  {
    _DbgPrintMessage(8, "GetLastInputTime failed: 0x%x", LastInputTime);
    goto LABEL_51;
  }
  v22[23] = v23;
LABEL_24:
  NtQuerySystemTime(v22 + 24);
  *a5 = 1224;
  ProtocolStatus = 0;
LABEL_25:
  CSmartPublicBinding::~CSmartPublicBinding((CSmartPublicBinding *)v28);
  CSmartSession::~CSmartSession((CSmartSession *)&v30);
  return ProtocolStatus;
}

```

## disassembly

```asm
0x180003480  push    rbx
0x180003482  push    rbp
0x180003483  push    rsi
0x180003484  push    rdi
0x180003485  push    r12
0x180003487  push    r13
0x180003489  push    r14
0x18000348b  push    r15
0x18000348d  sub     rsp, 168h
0x180003494  mov     rax, cs:__security_cookie
0x18000349b  xor     rax, rsp
0x18000349e  mov     [rsp+1A8h+var_58], rax
0x1800034a6  mov     r12, [rsp+1A8h+arg_20]
0x1800034ae  xorps   xmm0, xmm0
0x1800034b1  mov     rsi, r8
0x1800034b4  mov     [rsp+1A8h+var_170], 0FFFFFFFFh
0x1800034bc  mov     r14d, edx
0x1800034bf  mov     r13, rcx
0x1800034c2  xor     r15d, r15d
0x1800034c5  lea     rcx, [rsp+1A8h+var_130]; void *
0x1800034ca  xor     eax, eax
0x1800034cc  mov     [rsp+1A8h+var_178], r15
0x1800034d1  xor     edx, edx; Val
0x1800034d3  mov     [rsp+1A8h+var_60], r15
0x1800034db  mov     r8d, 0D0h; Size
0x1800034e1  mov     [rsp+1A8h+var_138], rax
0x1800034e6  movups  [rsp+1A8h+var_168], xmm0
0x1800034eb  mov     ebp, r9d
0x1800034ee  movups  [rsp+1A8h+var_158], xmm0
0x1800034f3  movups  [rsp+1A8h+var_148], xmm0
0x1800034f8  call    memset_0
0x1800034fd  mov     qword ptr [rsp+1A8h+var_188], r15
0x180003502  test    r13, r13
0x180003505  jnz     loc_180003786
0x18000350b  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180003512  mov     ecx, 40h ; '@'; unsigned __int64
0x180003517  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000351c  mov     rbx, rax
0x18000351f  test    rax, rax
0x180003522  jz      loc_1800037B9
0x180003528  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000352f  mov     [rax], r15
0x180003532  mov     ecx, 2; unsigned __int64
0x180003537  mov     [rax+8], r15
0x18000353b  mov     [rax+10h], r15
0x18000353f  mov     [rax+18h], r15
0x180003543  mov     [rax+20h], r15
0x180003547  mov     [rax+28h], r15
0x18000354b  mov     qword ptr [rax+30h], 1
0x180003553  mov     [rax+38h], r15
0x180003557  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18000355c  mov     [rbx+28h], rax
0x180003560  mov     r9, rax
0x180003563  test    rax, rax
0x180003566  jz      short loc_1800035D0
0x180003568  mov     ecx, 7FFFFFFEh
0x18000356d  lea     rdx, dword_18003FF34
0x180003574  mov     r10d, 1
0x18000357a  nop     word ptr [rax+rax+00h]
0x180003580  test    rcx, rcx
0x180003583  jz      short loc_1800035A2
0x180003585  movzx   eax, word ptr [rdx]
0x180003588  test    ax, ax
0x18000358b  jz      short loc_1800035A2
0x18000358d  mov     [r9], ax
0x180003591  add     rdx, 2
0x180003595  add     r9, 2
0x180003599  dec     rcx
0x18000359c  sub     r10, 1
0x1800035a0  jnz     short loc_180003580
0x1800035a2  test    r10, r10
0x1800035a5  lea     rcx, [r9-2]
0x1800035a9  mov     edi, 8007007Ah
0x1800035ae  cmovnz  rcx, r9
0x1800035b2  cmovnz  edi, r15d
0x1800035b6  mov     [rcx], r15w
0x1800035ba  jz      loc_180003720
0x1800035c0  cmp     [rbx+18h], r15
0x1800035c4  jnz     short loc_1800035D0
0x1800035c6  cmp     [rbx+30h], r15d
0x1800035ca  jz      loc_180003760
0x1800035d0  mov     [rsp+1A8h+var_180], rbx
0x1800035d5  mov     dword ptr [rsp+1A8h+var_188+4], 1
0x1800035dd  cmp     ebp, 4C8h
0x1800035e3  jb      loc_18000377C
0x1800035e9  lea     rcx, [rsp+1A8h+var_188]; unsigned __int16 *
0x1800035ee  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x1800035f3  mov     r8, rax; void *
0x1800035f6  lea     rcx, [rsp+1A8h+var_178]; this
0x1800035fb  mov     edx, r14d; unsigned int
0x1800035fe  call    ?GetSessionInformationEx@CSmartSession@@QEAAJKPEAX@Z; CSmartSession::GetSessionInformationEx(ulong,void *)
0x180003603  mov     edi, eax
0x180003605  test    eax, eax
0x180003607  js      loc_180003740
0x18000360d  cmp     dword ptr [rsp+1A8h+var_60+4], 1
0x180003615  jnz     short loc_180003631
0x180003617  mov     r8, rsi; struct _WINSTATIONINFORMATIONEX *
0x18000361a  lea     rcx, [rsp+1A8h+var_178]; this
0x18000361f  mov     edx, r14d; unsigned int
0x180003622  call    ?CopySessionExInfo@CSmartSession@@QEAAJKPEAU_WINSTATIONINFORMATIONEX@@K@Z; CSmartSession::CopySessionExInfo(ulong,_WINSTATIONINFORMATIONEX *,ulong)
0x180003627  mov     edi, eax
0x180003629  test    eax, eax
0x18000362b  js      loc_180003790
0x180003631  cmp     dword ptr [rsi], 1
0x180003634  mov     rbx, r15
0x180003637  jb      short loc_18000363D
0x180003639  lea     rbx, [rsi+8]
0x18000363d  cmp     dword ptr [rbx+4], 4
0x180003641  mov     r14, [rbx+0B0h]
0x180003648  jz      short loc_18000367F
0x18000364a  mov     r15d, [rsp+1A8h+var_170]
0x18000364f  lea     r9, [rbx+0B8h]; union _LARGE_INTEGER *
0x180003656  mov     edx, r15d; unsigned int
0x180003659  lea     r8, [rbx+0C8h]; struct _PROTOCOLSTATUS *
0x180003660  mov     rcx, r13; void *
0x180003663  call    ?GetSessionProtocolLastInputTime@@YAJPEAXKPEAU_PROTOCOLSTATUS@@PEAT_LARGE_INTEGER@@@Z; GetSessionProtocolLastInputTime(void *,ulong,_PROTOCOLSTATUS *,_LARGE_INTEGER *)
0x180003668  mov     edi, eax
0x18000366a  cmp     eax, 800706D1h
0x18000366f  jz      loc_1800037E5
0x180003675  cmp     eax, 80004002h
0x18000367a  jnz     short loc_1800036F3
0x18000367c  xor     r15d, r15d
0x18000367f  xor     edx, edx; Val
0x180003681  lea     rcx, [rbx+0C8h]; void *
0x180003688  mov     r8d, 3F4h; Size
0x18000368e  call    memset_0
0x180003693  mov     [rbx+0B8h], r14
0x18000369a  lea     rcx, [rbx+0C0h]; SystemTime
0x1800036a1  call    cs:__imp_NtQuerySystemTime
0x1800036a8  nop     dword ptr [rax+rax+00h]
0x1800036ad  mov     dword ptr [r12], 4C8h
0x1800036b5  mov     edi, r15d
0x1800036b8  lea     rcx, [rsp+1A8h+var_188]; this
0x1800036bd  call    ??1CSmartPublicBinding@@QEAA@XZ; CSmartPublicBinding::~CSmartPublicBinding(void)
0x1800036c2  lea     rcx, [rsp+1A8h+var_178]; this
0x1800036c7  call    ??1CSmartSession@@QEAA@XZ; CSmartSession::~CSmartSession(void)
0x1800036cc  mov     eax, edi
0x1800036ce  mov     rcx, [rsp+1A8h+var_58]
0x1800036d6  xor     rcx, rsp; StackCookie
0x1800036d9  call    __security_check_cookie
0x1800036de  add     rsp, 168h
0x1800036e5  pop     r15
0x1800036e7  pop     r14
0x1800036e9  pop     r13
0x1800036eb  pop     r12
0x1800036ed  pop     rdi
0x1800036ee  pop     rsi
0x1800036ef  pop     rbp
0x1800036f0  pop     rbx
0x1800036f1  retn
0x1800036f3  cmp     eax, 800708CAh
0x1800036f8  jz      short loc_18000367C
0x1800036fa  cmp     eax, 800706BAh
0x1800036ff  jz      loc_18000367C
0x180003705  cmp     eax, 800706B5h
0x18000370a  jz      loc_18000367C
0x180003710  test    eax, eax
0x180003712  js      loc_18000387C
0x180003718  xor     r15d, r15d
0x18000371b  jmp     loc_18000369A
0x180003720  mov     ecx, edi; int
0x180003722  call    ?ConvertHRESULT2WIN32@@YAKJ@Z; ConvertHRESULT2WIN32(long)
0x180003727  mov     r8d, edi
0x18000372a  lea     rdx, aStringcchcopyF; "StringCchCopy failed: %x"
0x180003731  mov     ecx, 8; int
0x180003736  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000373b  jmp     loc_1800035D0
0x180003740  lea     r9, aGetwinstationi_1; "GetWinStationInformationEx"
0x180003747  mov     r8d, eax
0x18000374a  lea     rdx, aGetsessioninfo; "GetSessionInformationEx failed: 0x%x in"...
0x180003751  mov     ecx, 8; int
0x180003756  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000375b  jmp     loc_1800036B8
0x180003760  mov     rcx, rbx; this
0x180003763  call    ?OpenSessionContextHandle@CPublicBinding@@AEAAJXZ; CPublicBinding::OpenSessionContextHandle(void)
0x180003768  cmp     eax, 800706BAh
0x18000376d  jz      short loc_1800037B0
0x18000376f  mov     rcx, rbx; this
0x180003772  call    ?CloseSessionContextHandle@CPublicBinding@@AEAAJXZ; CPublicBinding::CloseSessionContextHandle(void)
0x180003777  jmp     loc_1800035D0
0x18000377c  mov     edi, 80070057h
0x180003781  jmp     loc_1800036B8
0x180003786  mov     [rsp+1A8h+var_180], r13
0x18000378b  jmp     loc_1800035DD
0x180003790  lea     r9, aGetwinstationi_1; "GetWinStationInformationEx"
0x180003797  mov     r8d, eax
0x18000379a  lea     rdx, aCopysessionexi; "CopySessionExInfo failed: 0x%x in %s"
0x1800037a1  mov     ecx, 8; int
0x1800037a6  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800037ab  jmp     loc_1800036B8
0x1800037b0  mov     dword ptr [rbx+34h], 1
0x1800037b7  jmp     short loc_18000376F
0x1800037b9  mov     ecx, 0Eh; dwErrCode
0x1800037be  mov     [rsp+1A8h+var_180], r15
0x1800037c3  call    cs:__imp_SetLastError
0x1800037ca  nop     dword ptr [rax+rax+00h]
0x1800037cf  lea     rdx, aNewCpublicbind; "new CPublicBinding"
0x1800037d6  mov     ecx, 8; int
0x1800037db  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800037e0  jmp     loc_1800035DD
0x1800037e5  lea     r8, [rbx+0C8h]; struct _PROTOCOLSTATUS *
0x1800037ec  mov     edx, r15d; unsigned int
0x1800037ef  mov     rcx, r13; void *
0x1800037f2  call    ?GetProtocolStatus@@YAJPEAXKPEAU_PROTOCOLSTATUS@@@Z; GetProtocolStatus(void *,ulong,_PROTOCOLSTATUS *)
0x1800037f7  mov     ecx, 80000000h
0x1800037fc  mov     edi, eax
0x1800037fe  add     eax, ecx
0x180003800  test    ecx, eax
0x180003802  jnz     short loc_180003822
0x180003804  cmp     edi, 80004002h
0x18000380a  jz      short loc_180003822
0x18000380c  mov     r8d, edi
0x18000380f  lea     rdx, aGetprotocolsta; "GetProtocolStatus failed: 0x%x"
0x180003816  mov     ecx, 8; int
0x18000381b  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180003820  jmp     short loc_180003897
0x180003822  lea     r8, [rbx+0B8h]; union _LARGE_INTEGER *
0x180003829  mov     edx, r15d; unsigned int
0x18000382c  mov     rcx, r13; void *
0x18000382f  call    ?GetLastInputTime@@YAJPEAXKPEAT_LARGE_INTEGER@@@Z; GetLastInputTime(void *,ulong,_LARGE_INTEGER *)
0x180003834  mov     edi, eax
0x180003836  test    eax, eax
0x180003838  jns     loc_180003718
0x18000383e  cmp     eax, 80004002h
0x180003843  jz      short loc_180003870
0x180003845  cmp     eax, 800708CAh
0x18000384a  jz      short loc_180003870
0x18000384c  cmp     eax, 800706BAh
0x180003851  jz      short loc_180003870
0x180003853  cmp     eax, 800706B5h
0x180003858  jz      short loc_180003870
0x18000385a  mov     r8d, eax
0x18000385d  lea     rdx, aGetlastinputti; "GetLastInputTime failed: 0x%x"
0x180003864  mov     ecx, 8; int
0x180003869  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000386e  jmp     short loc_180003897
0x180003870  mov     [rbx+0B8h], r14
0x180003877  jmp     loc_180003718
0x18000387c  lea     r9, aGetsessionprot_0; "_GetSessionProtocolLastInputTime"
0x180003883  mov     r8d, eax
0x180003886  lea     rdx, aGetsessionprot; "GetSessionProtocolLastInputTime failed:"...
0x18000388d  mov     ecx, 8; int
0x180003892  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180003897  lea     r9, aGetwinstationi_1; "GetWinStationInformationEx"
0x18000389e  mov     r8d, edi
0x1800038a1  lea     rdx, aGetsessionprot_1; "_GetSessionProtocolLastInputTime failed"...
0x1800038a8  mov     ecx, 8; int
0x1800038ad  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800038b2  jmp     loc_1800036B8
```
