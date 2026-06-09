# GetWinStationInformationEx(void *,ulong,_WINSTATIONINFORMATIONEX *,ulong,ulong *)

- ea: `0x18000ad50`
- end: `0x18000b173`
- name: `?GetWinStationInformationEx@@YAJPEAXKPEAU_WINSTATIONINFORMATIONEX@@KPEAK@Z`
- size: `1059`
- prototype: `__int64 __usercall@<rax>(void *@<rcx>, unsigned int@<edx>, struct _WINSTATIONINFORMATIONEX *@<r8>, unsigned int@<r9d>, unsigned int *)`
- caller_count: `1`
- callee_count: `17`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000ce54`

## callees

- `0x180005374`
- `0x180005fcc`
- `0x180007030`
- `0x180007890`
- `0x180008290`
- `0x180008340`
- `0x180008e30`
- `0x1800097b0`
- `0x18000ad50`
- `0x18000b17c`
- `0x18000b3b0`
- `0x18002139c`
- `0x180021eb4`
- `0x1800230b8`
- `0x1800230ec`
- `0x18002fe06`
- `0x18002fe40`

## import_xrefs

- `ntdll!NtQuerySystemTime` at `0x18000af71`
- `ntdll!NtQuerySystemTime` at `0x18000af71`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b085`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b085`

## string_xrefs

- `0x18000afec`: `StringCchCopy failed: %x`
- `0x18000b05c`: `CopySessionExInfo failed: 0x%x in %s`
- `0x18000b0cb`: `GetProtocolStatus failed: 0x%x`
- `0x18000b138`: `_GetSessionProtocolLastInputTime`
- `0x18000b142`: `GetSessionProtocolLastInputTime failed: 0x%x in %s`
- `0x18000b15d`: `_GetSessionProtocolLastInputTime failed: 0x%x in %s`

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
        v14 = &dword_18003D0CC;
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
            if ( (unsigned int)CPublicBinding::OpenSessionContextHandle((RPC_BINDING_HANDLE *)v10) == -2147023174 )
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
0x18000ad50  push    rbx
0x18000ad52  push    rbp
0x18000ad53  push    rsi
0x18000ad54  push    rdi
0x18000ad55  push    r12
0x18000ad57  push    r13
0x18000ad59  push    r14
0x18000ad5b  push    r15
0x18000ad5d  sub     rsp, 168h
0x18000ad64  mov     rax, cs:__security_cookie
0x18000ad6b  xor     rax, rsp
0x18000ad6e  mov     [rsp+1A8h+var_58], rax
0x18000ad76  mov     r12, [rsp+1A8h+arg_20]
0x18000ad7e  xorps   xmm0, xmm0
0x18000ad81  mov     rsi, r8
0x18000ad84  mov     [rsp+1A8h+var_170], 0FFFFFFFFh
0x18000ad8c  mov     r14d, edx
0x18000ad8f  mov     r13, rcx
0x18000ad92  xor     r15d, r15d
0x18000ad95  lea     rcx, [rsp+1A8h+var_130]; void *
0x18000ad9a  xor     eax, eax
0x18000ad9c  mov     [rsp+1A8h+var_178], r15
0x18000ada1  xor     edx, edx; Val
0x18000ada3  mov     [rsp+1A8h+var_60], r15
0x18000adab  mov     r8d, 0D0h; Size
0x18000adb1  mov     [rsp+1A8h+var_138], rax
0x18000adb6  movups  [rsp+1A8h+var_168], xmm0
0x18000adbb  mov     ebp, r9d
0x18000adbe  movups  [rsp+1A8h+var_158], xmm0
0x18000adc3  movups  [rsp+1A8h+var_148], xmm0
0x18000adc8  call    memset_0
0x18000adcd  mov     qword ptr [rsp+1A8h+var_188], r15
0x18000add2  test    r13, r13
0x18000add5  jnz     loc_18000B048
0x18000addb  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000ade2  mov     ecx, 40h ; '@'; unsigned __int64
0x18000ade7  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000adec  mov     rbx, rax
0x18000adef  test    rax, rax
0x18000adf2  jz      loc_18000B07B
0x18000adf8  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000adff  mov     [rax], r15
0x18000ae02  mov     ecx, 2; unsigned __int64
0x18000ae07  mov     [rax+8], r15
0x18000ae0b  mov     [rax+10h], r15
0x18000ae0f  mov     [rax+18h], r15
0x18000ae13  mov     [rax+20h], r15
0x18000ae17  mov     [rax+28h], r15
0x18000ae1b  mov     qword ptr [rax+30h], 1
0x18000ae23  mov     [rax+38h], r15
0x18000ae27  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18000ae2c  mov     [rbx+28h], rax
0x18000ae30  mov     r9, rax
0x18000ae33  test    rax, rax
0x18000ae36  jz      short loc_18000AEA0
0x18000ae38  mov     ecx, 7FFFFFFEh
0x18000ae3d  lea     rdx, dword_18003D0CC
0x18000ae44  mov     r10d, 1
0x18000ae4a  nop     word ptr [rax+rax+00h]
0x18000ae50  test    rcx, rcx
0x18000ae53  jz      short loc_18000AE72
0x18000ae55  movzx   eax, word ptr [rdx]
0x18000ae58  test    ax, ax
0x18000ae5b  jz      short loc_18000AE72
0x18000ae5d  mov     [r9], ax
0x18000ae61  add     rdx, 2
0x18000ae65  add     r9, 2
0x18000ae69  dec     rcx
0x18000ae6c  sub     r10, 1
0x18000ae70  jnz     short loc_18000AE50
0x18000ae72  test    r10, r10
0x18000ae75  lea     rcx, [r9-2]
0x18000ae79  mov     edi, 8007007Ah
0x18000ae7e  cmovnz  rcx, r9
0x18000ae82  cmovnz  edi, r15d
0x18000ae86  mov     [rcx], r15w
0x18000ae8a  jz      loc_18000AFE2
0x18000ae90  cmp     [rbx+18h], r15
0x18000ae94  jnz     short loc_18000AEA0
0x18000ae96  cmp     [rbx+30h], r15d
0x18000ae9a  jz      loc_18000B022
0x18000aea0  mov     [rsp+1A8h+var_180], rbx
0x18000aea5  mov     dword ptr [rsp+1A8h+var_188+4], 1
0x18000aead  cmp     ebp, 4C8h
0x18000aeb3  jb      loc_18000B03E
0x18000aeb9  lea     rcx, [rsp+1A8h+var_188]; unsigned __int16 *
0x18000aebe  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x18000aec3  mov     r8, rax; void *
0x18000aec6  lea     rcx, [rsp+1A8h+var_178]; this
0x18000aecb  mov     edx, r14d; unsigned int
0x18000aece  call    ?GetSessionInformationEx@CSmartSession@@QEAAJKPEAX@Z; CSmartSession::GetSessionInformationEx(ulong,void *)
0x18000aed3  mov     edi, eax
0x18000aed5  test    eax, eax
0x18000aed7  js      loc_18000B002
0x18000aedd  cmp     dword ptr [rsp+1A8h+var_60+4], 1
0x18000aee5  jnz     short loc_18000AF01
0x18000aee7  mov     r8, rsi; struct _WINSTATIONINFORMATIONEX *
0x18000aeea  lea     rcx, [rsp+1A8h+var_178]; this
0x18000aeef  mov     edx, r14d; unsigned int
0x18000aef2  call    ?CopySessionExInfo@CSmartSession@@QEAAJKPEAU_WINSTATIONINFORMATIONEX@@K@Z; CSmartSession::CopySessionExInfo(ulong,_WINSTATIONINFORMATIONEX *,ulong)
0x18000aef7  mov     edi, eax
0x18000aef9  test    eax, eax
0x18000aefb  js      loc_18000B052
0x18000af01  cmp     dword ptr [rsi], 1
0x18000af04  mov     rbx, r15
0x18000af07  jb      short loc_18000AF0D
0x18000af09  lea     rbx, [rsi+8]
0x18000af0d  cmp     dword ptr [rbx+4], 4
0x18000af11  mov     r14, [rbx+0B0h]
0x18000af18  jz      short loc_18000AF4F
0x18000af1a  mov     r15d, [rsp+1A8h+var_170]
0x18000af1f  lea     r9, [rbx+0B8h]; union _LARGE_INTEGER *
0x18000af26  mov     edx, r15d; unsigned int
0x18000af29  lea     r8, [rbx+0C8h]; struct _PROTOCOLSTATUS *
0x18000af30  mov     rcx, r13; void *
0x18000af33  call    ?GetSessionProtocolLastInputTime@@YAJPEAXKPEAU_PROTOCOLSTATUS@@PEAT_LARGE_INTEGER@@@Z; GetSessionProtocolLastInputTime(void *,ulong,_PROTOCOLSTATUS *,_LARGE_INTEGER *)
0x18000af38  mov     edi, eax
0x18000af3a  cmp     eax, 800706D1h
0x18000af3f  jz      loc_18000B0A1
0x18000af45  cmp     eax, 80004002h
0x18000af4a  jnz     short loc_18000AFBC
0x18000af4c  xor     r15d, r15d
0x18000af4f  xor     edx, edx; Val
0x18000af51  lea     rcx, [rbx+0C8h]; void *
0x18000af58  mov     r8d, 3F4h; Size
0x18000af5e  call    memset_0
0x18000af63  mov     [rbx+0B8h], r14
0x18000af6a  lea     rcx, [rbx+0C0h]; SystemTime
0x18000af71  call    cs:__imp_NtQuerySystemTime
0x18000af77  mov     dword ptr [r12], 4C8h
0x18000af7f  mov     edi, r15d
0x18000af82  lea     rcx, [rsp+1A8h+var_188]; this
0x18000af87  call    ??1CSmartPublicBinding@@QEAA@XZ; CSmartPublicBinding::~CSmartPublicBinding(void)
0x18000af8c  lea     rcx, [rsp+1A8h+var_178]; this
0x18000af91  call    ??1CSmartSession@@QEAA@XZ; CSmartSession::~CSmartSession(void)
0x18000af96  mov     eax, edi
0x18000af98  mov     rcx, [rsp+1A8h+var_58]
0x18000afa0  xor     rcx, rsp; StackCookie
0x18000afa3  call    __security_check_cookie
0x18000afa8  add     rsp, 168h
0x18000afaf  pop     r15
0x18000afb1  pop     r14
0x18000afb3  pop     r13
0x18000afb5  pop     r12
0x18000afb7  pop     rdi
0x18000afb8  pop     rsi
0x18000afb9  pop     rbp
0x18000afba  pop     rbx
0x18000afbb  retn
0x18000afbc  cmp     eax, 800708CAh
0x18000afc1  jz      short loc_18000AF4C
0x18000afc3  cmp     eax, 800706BAh
0x18000afc8  jz      short loc_18000AF4C
0x18000afca  cmp     eax, 800706B5h
0x18000afcf  jz      loc_18000AF4C
0x18000afd5  test    eax, eax
0x18000afd7  js      loc_18000B138
0x18000afdd  xor     r15d, r15d
0x18000afe0  jmp     short loc_18000AF6A
0x18000afe2  mov     ecx, edi; int
0x18000afe4  call    ?ConvertHRESULT2WIN32@@YAKJ@Z; ConvertHRESULT2WIN32(long)
0x18000afe9  mov     r8d, edi
0x18000afec  lea     rdx, aStringcchcopyF; "StringCchCopy failed: %x"
0x18000aff3  mov     ecx, 8; int
0x18000aff8  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000affd  jmp     loc_18000AEA0
0x18000b002  lea     r9, aGetwinstationi_1; "GetWinStationInformationEx"
0x18000b009  mov     r8d, eax
0x18000b00c  lea     rdx, aGetsessioninfo; "GetSessionInformationEx failed: 0x%x in"...
0x18000b013  mov     ecx, 8; int
0x18000b018  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000b01d  jmp     loc_18000AF82
0x18000b022  mov     rcx, rbx; this
0x18000b025  call    ?OpenSessionContextHandle@CPublicBinding@@AEAAJXZ; CPublicBinding::OpenSessionContextHandle(void)
0x18000b02a  cmp     eax, 800706BAh
0x18000b02f  jz      short loc_18000B072
0x18000b031  mov     rcx, rbx; this
0x18000b034  call    ?CloseSessionContextHandle@CPublicBinding@@AEAAJXZ; CPublicBinding::CloseSessionContextHandle(void)
0x18000b039  jmp     loc_18000AEA0
0x18000b03e  mov     edi, 80070057h
0x18000b043  jmp     loc_18000AF82
0x18000b048  mov     [rsp+1A8h+var_180], r13
0x18000b04d  jmp     loc_18000AEAD
0x18000b052  lea     r9, aGetwinstationi_1; "GetWinStationInformationEx"
0x18000b059  mov     r8d, eax
0x18000b05c  lea     rdx, aCopysessionexi; "CopySessionExInfo failed: 0x%x in %s"
0x18000b063  mov     ecx, 8; int
0x18000b068  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000b06d  jmp     loc_18000AF82
0x18000b072  mov     dword ptr [rbx+34h], 1
0x18000b079  jmp     short loc_18000B031
0x18000b07b  mov     ecx, 0Eh; dwErrCode
0x18000b080  mov     [rsp+1A8h+var_180], r15
0x18000b085  call    cs:__imp_SetLastError
0x18000b08b  lea     rdx, aNewCpublicbind; "new CPublicBinding"
0x18000b092  mov     ecx, 8; int
0x18000b097  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000b09c  jmp     loc_18000AEAD
0x18000b0a1  lea     r8, [rbx+0C8h]; struct _PROTOCOLSTATUS *
0x18000b0a8  mov     edx, r15d; unsigned int
0x18000b0ab  mov     rcx, r13; void *
0x18000b0ae  call    ?GetProtocolStatus@@YAJPEAXKPEAU_PROTOCOLSTATUS@@@Z; GetProtocolStatus(void *,ulong,_PROTOCOLSTATUS *)
0x18000b0b3  mov     ecx, 80000000h
0x18000b0b8  mov     edi, eax
0x18000b0ba  add     eax, ecx
0x18000b0bc  test    ecx, eax
0x18000b0be  jnz     short loc_18000B0DE
0x18000b0c0  cmp     edi, 80004002h
0x18000b0c6  jz      short loc_18000B0DE
0x18000b0c8  mov     r8d, edi
0x18000b0cb  lea     rdx, aGetprotocolsta; "GetProtocolStatus failed: 0x%x"
0x18000b0d2  mov     ecx, 8; int
0x18000b0d7  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000b0dc  jmp     short loc_18000B153
0x18000b0de  lea     r8, [rbx+0B8h]; union _LARGE_INTEGER *
0x18000b0e5  mov     edx, r15d; unsigned int
0x18000b0e8  mov     rcx, r13; void *
0x18000b0eb  call    ?GetLastInputTime@@YAJPEAXKPEAT_LARGE_INTEGER@@@Z; GetLastInputTime(void *,ulong,_LARGE_INTEGER *)
0x18000b0f0  mov     edi, eax
0x18000b0f2  test    eax, eax
0x18000b0f4  jns     loc_18000AFDD
0x18000b0fa  cmp     eax, 80004002h
0x18000b0ff  jz      short loc_18000B12C
0x18000b101  cmp     eax, 800708CAh
0x18000b106  jz      short loc_18000B12C
0x18000b108  cmp     eax, 800706BAh
0x18000b10d  jz      short loc_18000B12C
0x18000b10f  cmp     eax, 800706B5h
0x18000b114  jz      short loc_18000B12C
0x18000b116  mov     r8d, eax
0x18000b119  lea     rdx, aGetlastinputti; "GetLastInputTime failed: 0x%x"
0x18000b120  mov     ecx, 8; int
0x18000b125  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000b12a  jmp     short loc_18000B153
0x18000b12c  mov     [rbx+0B8h], r14
0x18000b133  jmp     loc_18000AFDD
0x18000b138  lea     r9, aGetsessionprot_0; "_GetSessionProtocolLastInputTime"
0x18000b13f  mov     r8d, eax
0x18000b142  lea     rdx, aGetsessionprot; "GetSessionProtocolLastInputTime failed:"...
0x18000b149  mov     ecx, 8; int
0x18000b14e  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000b153  lea     r9, aGetwinstationi_1; "GetWinStationInformationEx"
0x18000b15a  mov     r8d, edi
0x18000b15d  lea     rdx, aGetsessionprot_1; "_GetSessionProtocolLastInputTime failed"...
0x18000b164  mov     ecx, 8; int
0x18000b169  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000b16e  jmp     loc_18000AF82
```
