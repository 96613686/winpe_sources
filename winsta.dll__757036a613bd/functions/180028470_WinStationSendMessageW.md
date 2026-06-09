# WinStationSendMessageW

- ea: `0x180028470`
- end: `0x180028777`
- name: `WinStationSendMessageW`
- size: `775`
- prototype: `__int64 __usercall@<rax>(CPublicBinding *this@<rcx>, unsigned int@<edx>, __int64, size_t, unsigned int, unsigned int, unsigned int *, unsigned __int8)`
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops`

## callers

- `0x180028360`

## callees

- `0x1800039e8`
- `0x180004554`
- `0x180005c30`
- `0x180005fcc`
- `0x180007030`
- `0x180007890`
- `0x180008290`
- `0x180008e30`
- `0x180020ae4`
- `0x1800230ec`
- `0x180024376`
- `0x180028470`
- `0x18002d06c`
- `0x18002fe06`
- `0x18002fe40`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x18002872c`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18002873a`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18002872c`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18002873a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180028557`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800285f4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800286de`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180028557`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800285f4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800286de`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800286ae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800286ae`

## string_xrefs

- `0x18002851e`: `Failed to open binding`
- `0x1800286ba`: `Session::Open failed: 0x%x in %s`

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
0x180028470  push    rbp
0x180028472  push    rbx
0x180028473  push    rsi
0x180028474  push    rdi
0x180028475  push    r12
0x180028477  push    r13
0x180028479  push    r14
0x18002847b  push    r15
0x18002847d  lea     rbp, [rsp-0C8h]
0x180028485  sub     rsp, 1C8h
0x18002848c  mov     rax, cs:__security_cookie
0x180028493  xor     rax, rsp
0x180028496  mov     [rbp+100h+var_50], rax
0x18002849d  mov     rax, [rbp+100h+arg_20]
0x1800284a4  xorps   xmm0, xmm0
0x1800284a7  mov     r12, [rbp+100h+arg_40]
0x1800284ae  xor     r13d, r13d
0x1800284b1  mov     [rsp+200h+var_1A0], rax
0x1800284b6  mov     esi, edx
0x1800284b8  xor     eax, eax
0x1800284ba  mov     [rsp+200h+Src], r8
0x1800284bf  mov     r15, rcx
0x1800284c2  mov     [rbp+100h+var_130], rax
0x1800284c6  or      r14d, 0FFFFFFFFh
0x1800284ca  mov     [rsp+200h+var_1A8], r9d
0x1800284cf  xor     edx, edx; Val
0x1800284d1  mov     [rbp+100h+var_170], r13
0x1800284d5  mov     r8d, 0D0h; Size
0x1800284db  mov     [rbp+100h+var_168], r14d
0x1800284df  lea     rcx, [rbp+100h+var_128]; void *
0x1800284e3  mov     [rbp+100h+var_58], r13
0x1800284ea  mov     edi, r9d
0x1800284ed  mov     bl, r13b
0x1800284f0  movups  [rbp+100h+var_160], xmm0
0x1800284f4  movups  [rbp+100h+var_150], xmm0
0x1800284f8  movups  [rbp+100h+var_140], xmm0
0x1800284fc  call    memset_0
0x180028501  xor     r8d, r8d; int
0x180028504  lea     rcx, [rbp+100h+var_180]; this
0x180028508  mov     rdx, r15; void *
0x18002850b  call    ??0CSmartPublicBinding@@QEAA@PEAXH@Z; CSmartPublicBinding::CSmartPublicBinding(void *,int)
0x180028510  lea     rcx, [rbp+100h+var_180]; unsigned __int16 *
0x180028514  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x180028519  test    rax, rax
0x18002851c  jnz     short loc_180028532
0x18002851e  lea     rdx, aFailedToOpenBi_0; "Failed to open binding"
0x180028525  lea     ecx, [rax+8]; int
0x180028528  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002852d  jmp     loc_180028740
0x180028532  cmp     esi, r14d
0x180028535  jnz     short loc_180028571
0x180028537  mov     rcx, r15; void *
0x18002853a  call    ?IsLocalServer@@YAHPEAX@Z; IsLocalServer(void *)
0x18002853f  test    eax, eax
0x180028541  jnz     short loc_180028562
0x180028543  lea     rdx, aLogonidCurrent; "LOGONID_CURRENT specified for a remote "...
0x18002854a  lea     ecx, [rax+4]; int
0x18002854d  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180028552  mov     ecx, 57h ; 'W'; dwErrCode
0x180028557  call    cs:__imp_SetLastError
0x18002855d  jmp     loc_180028740
0x180028562  mov     rax, gs:60h
0x18002856b  mov     esi, [rax+2C0h]
0x180028571  mov     eax, edi
0x180028573  mov     edi, 2
0x180028578  shr     eax, 1
0x18002857a  mov     [rsp+200h+var_190], rax
0x18002857f  inc     eax
0x180028581  mov     ecx, eax
0x180028583  mov     [rsp+200h+var_1B0], eax
0x180028587  mov     eax, edi
0x180028589  mul     rcx
0x18002858c  lea     rcx, [rdi-3]
0x180028590  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180028597  cmovb   rax, rcx
0x18002859b  mov     rcx, rax; unsigned __int64
0x18002859e  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800285a3  mov     r14, rax
0x1800285a6  test    rax, rax
0x1800285a9  jnz     short loc_1800285B0
0x1800285ab  lea     ecx, [rdi+6]
0x1800285ae  jmp     short loc_180028557
0x1800285b0  mov     r13d, dword ptr [rbp+100h+arg_28]
0x1800285b7  mov     eax, r13d
0x1800285ba  shr     eax, 1
0x1800285bc  mov     [rsp+200h+var_188], rax
0x1800285c1  inc     eax
0x1800285c3  mov     ecx, eax
0x1800285c5  mov     [rsp+200h+var_1AC], eax
0x1800285c9  mov     rax, rdi
0x1800285cc  mul     rcx
0x1800285cf  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800285d6  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800285dd  cmovb   rax, rcx
0x1800285e1  mov     rcx, rax; unsigned __int64
0x1800285e4  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800285e9  mov     rdi, rax
0x1800285ec  test    rax, rax
0x1800285ef  jnz     short loc_1800285FF
0x1800285f1  lea     ecx, [rax+8]; dwErrCode
0x1800285f4  call    cs:__imp_SetLastError
0x1800285fa  jmp     loc_180028729
0x1800285ff  mov     r8d, dword ptr [rsp+200h+var_190]
0x180028604  mov     rcx, r14; void *
0x180028607  mov     rdx, [rsp+200h+Src]; Src
0x18002860c  add     r8, r8; Size
0x18002860f  call    memcpy_0
0x180028614  mov     ecx, [rsp+200h+var_1B0]
0x180028618  xor     eax, eax
0x18002861a  mov     r8d, dword ptr [rsp+200h+var_188]
0x18002861f  dec     ecx
0x180028621  mov     rdx, [rsp+200h+var_1A0]; Src
0x180028626  add     r8, r8; Size
0x180028629  mov     [r14+rcx*2], ax
0x18002862e  mov     rcx, rdi; void *
0x180028631  call    memcpy_0
0x180028636  mov     ecx, [rsp+200h+var_1AC]
0x18002863a  xor     eax, eax
0x18002863c  dec     ecx
0x18002863e  mov     [rdi+rcx*2], ax
0x180028642  lea     rcx, [rbp+100h+var_180]; unsigned __int16 *
0x180028646  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x18002864b  mov     r8, rax; void *
0x18002864e  lea     rcx, [rbp+100h+var_170]; this
0x180028652  mov     edx, esi; unsigned int
0x180028654  call    ?Open@CSmartSession@@QEAAJKPEAX@Z; CSmartSession::Open(ulong,void *)
0x180028659  mov     ebx, eax
0x18002865b  cmp     eax, 800706BAh
0x180028660  jnz     short loc_1800286B6
0x180028662  mov     al, [rbp+100h+arg_48]
0x180028668  mov     edx, esi; unsigned int
0x18002866a  mov     r9d, [rsp+200h+var_1A8]; unsigned int
0x18002866f  mov     rcx, r15; this
0x180028672  mov     r8, [rsp+200h+Src]; unsigned __int16 *
0x180028677  mov     [rsp+200h+var_1B8], al; unsigned __int8
0x18002867b  mov     eax, [rbp+100h+arg_38]
0x180028681  mov     [rsp+200h+var_1C0], r12; unsigned int *
0x180028686  mov     [rsp+200h+var_1C8], eax; unsigned int
0x18002868a  mov     eax, [rbp+100h+arg_30]
0x180028690  mov     [rsp+200h+var_1D0], eax; unsigned int
0x180028694  mov     rax, [rsp+200h+var_1A0]
0x180028699  mov     dword ptr [rsp+200h+Size], r13d; Size
0x18002869e  mov     [rsp+200h+var_1E0], rax; Src
0x1800286a3  call    ?Legacy_WinStationSendMessageW@@YAEPEAXKPEBGK1KKKPEAKE@Z; Legacy_WinStationSendMessageW(void *,ulong,ushort const *,ulong,ushort const *,ulong,ulong,ulong,ulong *,uchar)
0x1800286a8  mov     bl, al
0x1800286aa  test    al, al
0x1800286ac  jnz     short loc_180028729
0x1800286ae  call    cs:__imp_GetLastError
0x1800286b4  jmp     short loc_180028729
0x1800286b6  test    ebx, ebx
0x1800286b8  jns     short loc_1800286E8
0x1800286ba  lea     rdx, aSessionOpenFai_0; "Session::Open failed: 0x%x in %s"
0x1800286c1  mov     r8d, ebx
0x1800286c4  lea     r9, aWinstationsend_2; "WinStationSendMessageW"
0x1800286cb  mov     ecx, 8; int
0x1800286d0  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800286d5  mov     ecx, ebx; int
0x1800286d7  call    ?ConvertHRESULT2WIN32@@YAKJ@Z; ConvertHRESULT2WIN32(long)
0x1800286dc  mov     ecx, eax; dwErrCode
0x1800286de  call    cs:__imp_SetLastError
0x1800286e4  xor     bl, bl
0x1800286e6  jmp     short loc_180028729
0x1800286e8  movzx   eax, [rbp+100h+arg_48]
0x1800286ef  lea     rcx, [rbp+100h+var_170]; this
0x1800286f3  mov     r9d, [rbp+100h+arg_30]; unsigned int
0x1800286fa  mov     r8, rdi; unsigned __int16 *
0x1800286fd  mov     [rsp+200h+var_1D0], eax; int
0x180028701  mov     rdx, r14; unsigned __int16 *
0x180028704  mov     eax, [rbp+100h+arg_38]
0x18002870a  mov     [rsp+200h+Size], r12; unsigned int *
0x18002870f  mov     dword ptr [rsp+200h+var_1E0], eax; unsigned int
0x180028713  call    ?ShowMessageBox@CSmartSession@@QEAAJPEAG0KKPEAKH@Z; CSmartSession::ShowMessageBox(ushort *,ushort *,ulong,ulong,ulong *,int)
0x180028718  mov     ebx, eax
0x18002871a  test    eax, eax
0x18002871c  jns     short loc_180028727
0x18002871e  lea     rdx, aSessionSendmes; "Session::SendMessage failed: 0x%x in %s"
0x180028725  jmp     short loc_1800286C1
0x180028727  mov     bl, 1
0x180028729  mov     rcx, r14
0x18002872c  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180028732  test    rdi, rdi
0x180028735  jz      short loc_180028740
0x180028737  mov     rcx, rdi
0x18002873a  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180028740  lea     rcx, [rbp+100h+var_180]; this
0x180028744  call    ??1CSmartPublicBinding@@QEAA@XZ; CSmartPublicBinding::~CSmartPublicBinding(void)
0x180028749  lea     rcx, [rbp+100h+var_170]; this
0x18002874d  call    ??1CSmartSession@@QEAA@XZ; CSmartSession::~CSmartSession(void)
0x180028752  mov     al, bl
0x180028754  mov     rcx, [rbp+100h+var_50]
0x18002875b  xor     rcx, rsp; StackCookie
0x18002875e  call    __security_check_cookie
0x180028763  add     rsp, 1C8h
0x18002876a  pop     r15
0x18002876c  pop     r14
0x18002876e  pop     r13
0x180028770  pop     r12
0x180028772  pop     rdi
0x180028773  pop     rsi
0x180028774  pop     rbx
0x180028775  pop     rbp
0x180028776  retn
```
