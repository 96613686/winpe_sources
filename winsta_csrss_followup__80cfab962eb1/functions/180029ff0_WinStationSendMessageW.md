# WinStationSendMessageW

- ea: `0x180029ff0`
- end: `0x18002a320`
- name: `WinStationSendMessageW`
- size: `816`
- prototype: `__int64 __usercall@<rax>(CPublicBinding *this@<rcx>, unsigned int@<edx>, __int64, size_t, unsigned int, unsigned int, unsigned int *, unsigned __int8)`
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops`

## callers

- `0x180029ec0`

## callees

- `0x180002014`
- `0x1800041a0`
- `0x180004558`
- `0x180005280`
- `0x180005b40`
- `0x1800065f0`
- `0x1800075a0`
- `0x18000a784`
- `0x1800222a0`
- `0x180024a1c`
- `0x180025cc6`
- `0x180029ff0`
- `0x18002f460`
- `0x180032be6`
- `0x180032c20`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x18002a2c8`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18002a2dc`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18002a2c8`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18002a2dc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002a0d7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002a17a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002a274`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002a0d7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002a17a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002a274`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a23e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a23e`

## string_xrefs

- `0x18002a09e`: `Failed to open binding`
- `0x18002a250`: `Session::Open failed: 0x%x in %s`

## pseudocode

```c
unsigned __int8 __fastcall WinStationSendMessageW(
        CPublicBinding *this,
        ULONG SessionId,
        const void *a3,
        unsigned int a4,
        const void *a5,
        size_t a6,
        unsigned int a7,
        unsigned int a8,
        unsigned int *a9,
        unsigned __int8 a10)
{
  unsigned __int8 v13; // bl
  DWORD v14; // ecx
  unsigned __int64 v15; // rax
  void *v16; // r14
  unsigned __int64 v17; // rax
  void *v18; // rdi
  void *v19; // rax
  int v20; // ebx
  DWORD v21; // eax
  size_t Size; // [rsp+28h] [rbp-D8h]
  unsigned int v24; // [rsp+50h] [rbp-B0h]
  unsigned int v27; // [rsp+70h] [rbp-90h]
  unsigned __int16 v28[8]; // [rsp+80h] [rbp-80h] BYREF
  __int64 v29; // [rsp+90h] [rbp-70h] BYREF
  int v30; // [rsp+98h] [rbp-68h]
  __int128 v31; // [rsp+A0h] [rbp-60h]
  __int128 v32; // [rsp+B0h] [rbp-50h]
  __int128 v33; // [rsp+C0h] [rbp-40h]
  __int64 v34; // [rsp+D0h] [rbp-30h]
  _BYTE v35[208]; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v36; // [rsp+1A8h] [rbp+A8h]

  v34 = 0;
  v29 = 0;
  v30 = -1;
  v36 = 0;
  v13 = 0;
  v31 = 0;
  v32 = 0;
  v33 = 0;
  memset_0(v35, 0, sizeof(v35));
  CSmartPublicBinding::CSmartPublicBinding((CSmartPublicBinding *)v28, this, 0);
  if ( !CSmartPublicBinding::operator void *(v28) )
  {
    _DbgPrintMessage(8, "Failed to open binding");
    goto LABEL_27;
  }
  if ( SessionId == -1 )
  {
    if ( !(unsigned int)IsLocalServer(this) )
    {
      _DbgPrintMessage(4, "LOGONID_CURRENT specified for a remote server!");
      v14 = 87;
LABEL_6:
      SetLastError(v14);
      goto LABEL_27;
    }
    SessionId = NtCurrentPeb()->SessionId;
  }
  v27 = a4 >> 1;
  v24 = (a4 >> 1) + 1;
  v15 = 2LL * v24;
  if ( !is_mul_ok(v24, 2u) )
    v15 = -1;
  v16 = operator new[](v15, (const struct std::nothrow_t *)&std::nothrow);
  if ( !v16 )
  {
    v14 = 8;
    goto LABEL_6;
  }
  v17 = 2LL * (((unsigned int)a6 >> 1) + 1);
  if ( !is_mul_ok(((unsigned int)a6 >> 1) + 1, 2u) )
    v17 = -1;
  v18 = operator new[](v17, (const struct std::nothrow_t *)&std::nothrow);
  if ( !v18 )
  {
    SetLastError(8u);
    goto LABEL_25;
  }
  memcpy_0(v16, a3, 2LL * v27);
  *((_WORD *)v16 + v24 - 1) = 0;
  memcpy_0(v18, a5, 2LL * ((unsigned int)a6 >> 1));
  *((_WORD *)v18 + ((unsigned int)a6 >> 1)) = 0;
  v19 = (void *)CSmartPublicBinding::operator void *(v28);
  v20 = CSmartSession::Open((CSmartSession *)&v29, SessionId, v19);
  if ( v20 == -2147023174 )
  {
    LODWORD(Size) = a6;
    v13 = Legacy_WinStationSendMessageW(
            this,
            SessionId,
            (const unsigned __int16 *)a3,
            a4,
            (const unsigned __int16 *)a5,
            Size,
            a7,
            a8,
            a9,
            a10);
    if ( !v13 )
      GetLastError();
    goto LABEL_25;
  }
  if ( v20 < 0 )
  {
    _DbgPrintMessage(8, "Session::Open failed: 0x%x in %s", (unsigned int)v20, "WinStationSendMessageW");
LABEL_21:
    v21 = ConvertHRESULT2WIN32(v20);
    SetLastError(v21);
    v13 = 0;
    goto LABEL_25;
  }
  v20 = CSmartSession::ShowMessageBox(
          (CSmartSession *)&v29,
          (unsigned __int16 *)v16,
          (unsigned __int16 *)v18,
          a7,
          a8,
          a9,
          a10);
  if ( v20 < 0 )
  {
    _DbgPrintMessage(8, "Session::SendMessage failed: 0x%x in %s", (unsigned int)v20, "WinStationSendMessageW");
    goto LABEL_21;
  }
  v13 = 1;
LABEL_25:
  operator delete[](v16);
  if ( v18 )
    operator delete[](v18);
LABEL_27:
  CSmartPublicBinding::~CSmartPublicBinding((CSmartPublicBinding *)v28);
  CSmartSession::~CSmartSession((CSmartSession *)&v29);
  return v13;
}

```

## disassembly

```asm
0x180029ff0  push    rbp
0x180029ff2  push    rbx
0x180029ff3  push    rsi
0x180029ff4  push    rdi
0x180029ff5  push    r12
0x180029ff7  push    r13
0x180029ff9  push    r14
0x180029ffb  push    r15
0x180029ffd  lea     rbp, [rsp-0C8h]
0x18002a005  sub     rsp, 1C8h
0x18002a00c  mov     rax, cs:__security_cookie
0x18002a013  xor     rax, rsp
0x18002a016  mov     [rbp+100h+var_50], rax
0x18002a01d  mov     rax, [rbp+100h+arg_20]
0x18002a024  xorps   xmm0, xmm0
0x18002a027  mov     r12, [rbp+100h+arg_40]
0x18002a02e  xor     r13d, r13d
0x18002a031  mov     [rsp+200h+var_1A0], rax
0x18002a036  mov     esi, edx
0x18002a038  xor     eax, eax
0x18002a03a  mov     [rsp+200h+Src], r8
0x18002a03f  mov     r15, rcx
0x18002a042  mov     [rbp+100h+var_130], rax
0x18002a046  or      r14d, 0FFFFFFFFh
0x18002a04a  mov     [rsp+200h+var_1A8], r9d
0x18002a04f  xor     edx, edx; Val
0x18002a051  mov     [rbp+100h+var_170], r13
0x18002a055  mov     r8d, 0D0h; Size
0x18002a05b  mov     [rbp+100h+var_168], r14d
0x18002a05f  lea     rcx, [rbp+100h+var_128]; void *
0x18002a063  mov     [rbp+100h+var_58], r13
0x18002a06a  mov     edi, r9d
0x18002a06d  mov     bl, r13b
0x18002a070  movups  [rbp+100h+var_160], xmm0
0x18002a074  movups  [rbp+100h+var_150], xmm0
0x18002a078  movups  [rbp+100h+var_140], xmm0
0x18002a07c  call    memset_0
0x18002a081  xor     r8d, r8d; int
0x18002a084  lea     rcx, [rbp+100h+var_180]; this
0x18002a088  mov     rdx, r15; void *
0x18002a08b  call    ??0CSmartPublicBinding@@QEAA@PEAXH@Z; CSmartPublicBinding::CSmartPublicBinding(void *,int)
0x18002a090  lea     rcx, [rbp+100h+var_180]; unsigned __int16 *
0x18002a094  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x18002a099  test    rax, rax
0x18002a09c  jnz     short loc_18002A0B2
0x18002a09e  lea     rdx, aFailedToOpenBi_0; "Failed to open binding"
0x18002a0a5  lea     ecx, [rax+8]; int
0x18002a0a8  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002a0ad  jmp     loc_18002A2E8
0x18002a0b2  cmp     esi, r14d
0x18002a0b5  jnz     short loc_18002A0F7
0x18002a0b7  mov     rcx, r15; void *
0x18002a0ba  call    ?IsLocalServer@@YAHPEAX@Z; IsLocalServer(void *)
0x18002a0bf  test    eax, eax
0x18002a0c1  jnz     short loc_18002A0E8
0x18002a0c3  lea     rdx, aLogonidCurrent; "LOGONID_CURRENT specified for a remote "...
0x18002a0ca  lea     ecx, [rax+4]; int
0x18002a0cd  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002a0d2  mov     ecx, 57h ; 'W'; dwErrCode
0x18002a0d7  call    cs:__imp_SetLastError
0x18002a0de  nop     dword ptr [rax+rax+00h]
0x18002a0e3  jmp     loc_18002A2E8
0x18002a0e8  mov     rax, gs:60h
0x18002a0f1  mov     esi, [rax+2C0h]
0x18002a0f7  mov     eax, edi
0x18002a0f9  mov     edi, 2
0x18002a0fe  shr     eax, 1
0x18002a100  mov     [rsp+200h+var_190], rax
0x18002a105  inc     eax
0x18002a107  mov     ecx, eax
0x18002a109  mov     [rsp+200h+var_1B0], eax
0x18002a10d  mov     eax, edi
0x18002a10f  mul     rcx
0x18002a112  lea     rcx, [rdi-3]
0x18002a116  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18002a11d  cmovb   rax, rcx
0x18002a121  mov     rcx, rax; unsigned __int64
0x18002a124  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18002a129  mov     r14, rax
0x18002a12c  test    rax, rax
0x18002a12f  jnz     short loc_18002A136
0x18002a131  lea     ecx, [rdi+6]
0x18002a134  jmp     short loc_18002A0D7
0x18002a136  mov     r13d, dword ptr [rbp+100h+arg_28]
0x18002a13d  mov     eax, r13d
0x18002a140  shr     eax, 1
0x18002a142  mov     [rsp+200h+var_188], rax
0x18002a147  inc     eax
0x18002a149  mov     ecx, eax
0x18002a14b  mov     [rsp+200h+var_1AC], eax
0x18002a14f  mov     rax, rdi
0x18002a152  mul     rcx
0x18002a155  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18002a15c  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18002a163  cmovb   rax, rcx
0x18002a167  mov     rcx, rax; unsigned __int64
0x18002a16a  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18002a16f  mov     rdi, rax
0x18002a172  test    rax, rax
0x18002a175  jnz     short loc_18002A18B
0x18002a177  lea     ecx, [rax+8]; dwErrCode
0x18002a17a  call    cs:__imp_SetLastError
0x18002a181  nop     dword ptr [rax+rax+00h]
0x18002a186  jmp     loc_18002A2C5
0x18002a18b  mov     r8d, dword ptr [rsp+200h+var_190]
0x18002a190  mov     rcx, r14; void *
0x18002a193  mov     rdx, [rsp+200h+Src]; Src
0x18002a198  add     r8, r8; Size
0x18002a19b  call    memcpy_0
0x18002a1a0  mov     ecx, [rsp+200h+var_1B0]
0x18002a1a4  xor     eax, eax
0x18002a1a6  mov     r8d, dword ptr [rsp+200h+var_188]
0x18002a1ab  dec     ecx
0x18002a1ad  mov     rdx, [rsp+200h+var_1A0]; Src
0x18002a1b2  add     r8, r8; Size
0x18002a1b5  mov     [r14+rcx*2], ax
0x18002a1ba  mov     rcx, rdi; void *
0x18002a1bd  call    memcpy_0
0x18002a1c2  mov     ecx, [rsp+200h+var_1AC]
0x18002a1c6  xor     eax, eax
0x18002a1c8  dec     ecx
0x18002a1ca  mov     [rdi+rcx*2], ax
0x18002a1ce  lea     rcx, [rbp+100h+var_180]; unsigned __int16 *
0x18002a1d2  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x18002a1d7  mov     r8, rax; void *
0x18002a1da  lea     rcx, [rbp+100h+var_170]; this
0x18002a1de  mov     edx, esi; unsigned int
0x18002a1e0  call    ?Open@CSmartSession@@QEAAJKPEAX@Z; CSmartSession::Open(ulong,void *)
0x18002a1e5  mov     ebx, eax
0x18002a1e7  cmp     eax, 800706BAh
0x18002a1ec  jnz     short loc_18002A24C
0x18002a1ee  mov     al, [rbp+100h+arg_48]
0x18002a1f4  mov     edx, esi; unsigned int
0x18002a1f6  mov     r9d, [rsp+200h+var_1A8]; unsigned int
0x18002a1fb  mov     rcx, r15; this
0x18002a1fe  mov     r8, [rsp+200h+Src]; unsigned __int16 *
0x18002a203  mov     [rsp+200h+var_1B8], al; unsigned __int8
0x18002a207  mov     eax, [rbp+100h+arg_38]
0x18002a20d  mov     [rsp+200h+var_1C0], r12; unsigned int *
0x18002a212  mov     [rsp+200h+var_1C8], eax; unsigned int
0x18002a216  mov     eax, [rbp+100h+arg_30]
0x18002a21c  mov     [rsp+200h+var_1D0], eax; unsigned int
0x18002a220  mov     rax, [rsp+200h+var_1A0]
0x18002a225  mov     dword ptr [rsp+200h+Size], r13d; Size
0x18002a22a  mov     [rsp+200h+var_1E0], rax; Src
0x18002a22f  call    ?Legacy_WinStationSendMessageW@@YAEPEAXKPEBGK1KKKPEAKE@Z; Legacy_WinStationSendMessageW(void *,ulong,ushort const *,ulong,ushort const *,ulong,ulong,ulong,ulong *,uchar)
0x18002a234  mov     bl, al
0x18002a236  test    al, al
0x18002a238  jnz     loc_18002A2C5
0x18002a23e  call    cs:__imp_GetLastError
0x18002a245  nop     dword ptr [rax+rax+00h]
0x18002a24a  jmp     short loc_18002A2C5
0x18002a24c  test    ebx, ebx
0x18002a24e  jns     short loc_18002A284
0x18002a250  lea     rdx, aSessionOpenFai_0; "Session::Open failed: 0x%x in %s"
0x18002a257  mov     r8d, ebx
0x18002a25a  lea     r9, aWinstationsend_2; "WinStationSendMessageW"
0x18002a261  mov     ecx, 8; int
0x18002a266  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002a26b  mov     ecx, ebx; int
0x18002a26d  call    ?ConvertHRESULT2WIN32@@YAKJ@Z; ConvertHRESULT2WIN32(long)
0x18002a272  mov     ecx, eax; dwErrCode
0x18002a274  call    cs:__imp_SetLastError
0x18002a27b  nop     dword ptr [rax+rax+00h]
0x18002a280  xor     bl, bl
0x18002a282  jmp     short loc_18002A2C5
0x18002a284  movzx   eax, [rbp+100h+arg_48]
0x18002a28b  lea     rcx, [rbp+100h+var_170]; this
0x18002a28f  mov     r9d, [rbp+100h+arg_30]; unsigned int
0x18002a296  mov     r8, rdi; unsigned __int16 *
0x18002a299  mov     [rsp+200h+var_1D0], eax; int
0x18002a29d  mov     rdx, r14; unsigned __int16 *
0x18002a2a0  mov     eax, [rbp+100h+arg_38]
0x18002a2a6  mov     [rsp+200h+Size], r12; unsigned int *
0x18002a2ab  mov     dword ptr [rsp+200h+var_1E0], eax; unsigned int
0x18002a2af  call    ?ShowMessageBox@CSmartSession@@QEAAJPEAG0KKPEAKH@Z; CSmartSession::ShowMessageBox(ushort *,ushort *,ulong,ulong,ulong *,int)
0x18002a2b4  mov     ebx, eax
0x18002a2b6  test    eax, eax
0x18002a2b8  jns     short loc_18002A2C3
0x18002a2ba  lea     rdx, aSessionSendmes; "Session::SendMessage failed: 0x%x in %s"
0x18002a2c1  jmp     short loc_18002A257
0x18002a2c3  mov     bl, 1
0x18002a2c5  mov     rcx, r14
0x18002a2c8  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18002a2cf  nop     dword ptr [rax+rax+00h]
0x18002a2d4  test    rdi, rdi
0x18002a2d7  jz      short loc_18002A2E8
0x18002a2d9  mov     rcx, rdi
0x18002a2dc  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18002a2e3  nop     dword ptr [rax+rax+00h]
0x18002a2e8  lea     rcx, [rbp+100h+var_180]; this
0x18002a2ec  call    ??1CSmartPublicBinding@@QEAA@XZ; CSmartPublicBinding::~CSmartPublicBinding(void)
0x18002a2f1  lea     rcx, [rbp+100h+var_170]; this
0x18002a2f5  call    ??1CSmartSession@@QEAA@XZ; CSmartSession::~CSmartSession(void)
0x18002a2fa  mov     al, bl
0x18002a2fc  mov     rcx, [rbp+100h+var_50]
0x18002a303  xor     rcx, rsp; StackCookie
0x18002a306  call    __security_check_cookie
0x18002a30b  add     rsp, 1C8h
0x18002a312  pop     r15
0x18002a314  pop     r14
0x18002a316  pop     r13
0x18002a318  pop     r12
0x18002a31a  pop     rdi
0x18002a31b  pop     rsi
0x18002a31c  pop     rbx
0x18002a31d  pop     rbp
0x18002a31e  retn
```
