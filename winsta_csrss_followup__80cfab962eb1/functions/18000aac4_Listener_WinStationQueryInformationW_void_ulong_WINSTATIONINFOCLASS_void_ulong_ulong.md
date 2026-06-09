# Listener_WinStationQueryInformationW(void *,ulong,_WINSTATIONINFOCLASS,void *,ulong,ulong *)

- ea: `0x18000aac4`
- end: `0x18000ad59`
- name: `?Listener_WinStationQueryInformationW@@YAEPEAXKW4_WINSTATIONINFOCLASS@@0KPEAK@Z`
- size: `661`
- prototype: `unsigned __int8 __usercall@<al>(CPublicBinding *this@<rcx>, unsigned int@<edx>, enum _WINSTATIONINFOCLASS@<r8d>, void *@<r9>, unsigned int, unsigned int *)`
- caller_count: `1`
- callee_count: `12`
- tags: ``

## callers

- `0x1800096c0`

## callees

- `0x1800041a0`
- `0x180004558`
- `0x180005b40`
- `0x1800065f0`
- `0x1800075a0`
- `0x180009dec`
- `0x18000a670`
- `0x18000aac4`
- `0x18000ad60`
- `0x18000adc4`
- `0x18000ae3c`
- `0x180032be6`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ac27`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ac58`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000acf6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ac27`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ac58`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000acf6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ac89`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ac89`

## string_xrefs

- `0x18000ac03`: `Listener.Open failed: 0x%x in %s`

## pseudocode

```c
char __fastcall Listener_WinStationQueryInformationW(
        CPublicBinding *this,
        int a2,
        enum _WINSTATIONINFOCLASS a3,
        char *a4,
        size_t Size,
        unsigned int *a6)
{
  unsigned int v10; // r15d
  char *v11; // rax
  __int64 v12; // rax
  unsigned __int16 *v13; // r14
  char v14; // bl
  void *v15; // rax
  int IsListening; // edi
  DWORD v18; // eax
  unsigned int v19; // ebx
  signed int LastError; // eax
  signed int v21; // ebx
  DWORD v22; // eax
  int v23; // [rsp+30h] [rbp-38h] BYREF
  unsigned int v24; // [rsp+34h] [rbp-34h] BYREF
  __int64 v25; // [rsp+38h] [rbp-30h] BYREF
  char *v26; // [rsp+40h] [rbp-28h]
  unsigned __int16 v27[16]; // [rsp+48h] [rbp-20h] BYREF
  int v28; // [rsp+C0h] [rbp+58h] BYREF

  v28 = 0;
  v24 = 0;
  if ( a3 != WinStationInformation )
  {
    if ( a3 != 39 )
    {
      if ( a3 == 40 )
        goto LABEL_4;
      v19 = Size;
      memset_0(a4, 0, (unsigned int)Size);
      *a6 = v19;
      return 1;
    }
    if ( (_DWORD)Size == 4 )
    {
      if ( _tsrpcQuerySessionInfo(this, a2 + 0x10000, 39, (struct _WINSTATIONINFORMATIONW *)&v28, 4u, &v24) )
        goto LABEL_28;
      LastError = GetLastError();
      v21 = LastError;
      if ( LastError > 0 )
        v21 = (unsigned __int16)LastError | 0x80070000;
      if ( v21 >= 0 )
      {
LABEL_28:
        *(_DWORD *)a4 = v28;
        *a6 = 4;
        return 1;
      }
      _DbgPrintMessage(
        8,
        "_tsrpcQuerySessionInfo failed: 0x%x in %s",
        (unsigned int)v21,
        "Listener_WinStationQueryInformationW");
    }
    else
    {
      v21 = -2147024809;
      _DbgPrintMessage(
        8,
        "WinStationType - Invalid Size failed: 0x%x in %s",
        2147942487LL,
        "Listener_WinStationQueryInformationW");
    }
    v22 = ConvertHRESULT2WIN32(v21);
    SetLastError(v22);
    return 0;
  }
LABEL_4:
  CSmartPublicBinding::CSmartPublicBinding((CSmartPublicBinding *)v27, this, 1);
  v25 = 0;
  v10 = 1224;
  if ( a3 != 40 )
    v10 = 1216;
  v11 = a4 + 12;
  if ( a3 != 40 )
    v11 = a4;
  v26 = v11;
  v12 = 20;
  if ( a3 != 40 )
    v12 = 4;
  if ( v10 > (unsigned int)Size )
  {
    v14 = 0;
    _DbgPrintMessage(8, "WINSTATIONINFORMATION (or WINSTATIONINFORMATIONEX) size too small");
    SetLastError(0x57u);
    goto LABEL_17;
  }
  v13 = (unsigned __int16 *)&a4[v12];
  memset_0(a4, 0, v10);
  if ( a3 == 40 )
    *(_DWORD *)a4 = 1;
  v14 = WinStationNameFromLogonIdW(this, a2 + 0x10000, v13);
  if ( !v14 )
  {
    _DbgPrintMessage(8, "WinStationNameFromLogonIdW failed");
    goto LABEL_17;
  }
  v15 = CSmartPublicBinding::operator void *(v27);
  IsListening = CListener::Open((CListener *)&v25, v15, v13);
  if ( IsListening < 0 )
  {
    _DbgPrintMessage(
      8,
      "Listener.Open failed: 0x%x in %s",
      (unsigned int)IsListening,
      "Listener_WinStationQueryInformationW");
LABEL_20:
    v18 = ConvertHRESULT2WIN32(IsListening);
    SetLastError(v18);
    v14 = 0;
    goto LABEL_17;
  }
  v23 = 0;
  IsListening = CListener::IsListening((CListener *)&v25, &v23);
  if ( IsListening < 0 )
  {
    _DbgPrintMessage(
      8,
      "listener.IsListening failed: 0x%x in %s",
      (unsigned int)IsListening,
      "Listener_WinStationQueryInformationW");
    goto LABEL_20;
  }
  *(_DWORD *)v26 = v23 != 0 ? 6 : 8;
  *a6 = v10;
LABEL_17:
  CListener::~CListener((CListener *)&v25);
  CSmartPublicBinding::~CSmartPublicBinding((CSmartPublicBinding *)v27);
  return v14;
}

```

## disassembly

```asm
0x18000aac4  push    rbp
0x18000aac6  push    rbx
0x18000aac7  push    rsi
0x18000aac8  push    rdi
0x18000aac9  push    r12
0x18000aacb  push    r13
0x18000aacd  push    r14
0x18000aacf  push    r15
0x18000aad1  mov     rbp, rsp
0x18000aad4  sub     rsp, 68h
0x18000aad8  xor     r15d, r15d
0x18000aadb  mov     r10d, r8d
0x18000aade  mov     [rbp+arg_10], r15d
0x18000aae2  mov     rdi, r9
0x18000aae5  mov     [rbp+var_34], r15d
0x18000aae9  mov     esi, r8d
0x18000aaec  mov     r13d, edx
0x18000aaef  mov     r12, rcx
0x18000aaf2  sub     r10d, 8
0x18000aaf6  jz      short loc_18000AB0C
0x18000aaf8  sub     r10d, 1Fh
0x18000aafc  jz      loc_18000ACB6
0x18000ab02  cmp     r10d, 1
0x18000ab06  jnz     loc_18000AC69
0x18000ab0c  mov     ebx, 1
0x18000ab11  lea     rcx, [rbp+var_20]; this
0x18000ab15  mov     r8d, ebx; int
0x18000ab18  mov     rdx, r12; void *
0x18000ab1b  call    ??0CSmartPublicBinding@@QEAA@PEAXH@Z; CSmartPublicBinding::CSmartPublicBinding(void *,int)
0x18000ab20  cmp     esi, 28h ; '('
0x18000ab23  mov     [rbp+var_30], r15
0x18000ab27  mov     eax, 4C0h
0x18000ab2c  lea     r14d, [rbx+3]
0x18000ab30  lea     r15d, [rax+8]
0x18000ab34  cmovnz  r15d, eax
0x18000ab38  lea     rax, [rdi+0Ch]
0x18000ab3c  cmovnz  rax, rdi
0x18000ab40  mov     [rbp+var_28], rax
0x18000ab44  lea     eax, [rbx+13h]
0x18000ab47  cmovnz  eax, r14d
0x18000ab4b  cmp     r15d, dword ptr [rbp+Size]
0x18000ab4f  ja      loc_18000AC40
0x18000ab55  mov     r8d, r15d; Size
0x18000ab58  lea     r14, [rax+rdi]
0x18000ab5c  xor     edx, edx; Val
0x18000ab5e  mov     rcx, rdi; void *
0x18000ab61  call    memset_0
0x18000ab66  cmp     esi, 28h ; '('
0x18000ab69  jz      loc_18000AD3C
0x18000ab6f  lea     edx, [r13+10000h]; unsigned int
0x18000ab76  mov     r8, r14; unsigned __int16 *
0x18000ab79  mov     rcx, r12; this
0x18000ab7c  call    WinStationNameFromLogonIdW
0x18000ab81  mov     bl, al
0x18000ab83  test    al, al
0x18000ab85  jz      loc_18000AD43
0x18000ab8b  lea     rcx, [rbp+var_20]; unsigned __int16 *
0x18000ab8f  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x18000ab94  mov     rdx, rax; void *
0x18000ab97  lea     rcx, [rbp+var_30]; this
0x18000ab9b  mov     r8, r14; unsigned __int16 *
0x18000ab9e  call    ?Open@CListener@@QEAAJPEAXPEAG@Z; CListener::Open(void *,ushort *)
0x18000aba3  mov     edi, eax
0x18000aba5  test    eax, eax
0x18000aba7  js      short loc_18000AC03
0x18000aba9  lea     rdx, [rbp+var_38]; int *
0x18000abad  mov     [rbp+var_38], 0
0x18000abb4  lea     rcx, [rbp+var_30]; this
0x18000abb8  call    ?IsListening@CListener@@QEAAJPEAH@Z; CListener::IsListening(int *)
0x18000abbd  mov     edi, eax
0x18000abbf  test    eax, eax
0x18000abc1  js      short loc_18000AC37
0x18000abc3  mov     eax, [rbp+var_38]
0x18000abc6  neg     eax
0x18000abc8  mov     rax, [rbp+var_28]
0x18000abcc  sbb     ecx, ecx
0x18000abce  and     ecx, 0FFFFFFFEh
0x18000abd1  add     ecx, 8
0x18000abd4  mov     [rax], ecx
0x18000abd6  mov     rax, [rbp+arg_28]
0x18000abda  mov     [rax], r15d
0x18000abdd  lea     rcx, [rbp+var_30]; this
0x18000abe1  call    ??1CListener@@QEAA@XZ; CListener::~CListener(void)
0x18000abe6  lea     rcx, [rbp+var_20]; this
0x18000abea  call    ??1CSmartPublicBinding@@QEAA@XZ; CSmartPublicBinding::~CSmartPublicBinding(void)
0x18000abef  mov     al, bl
0x18000abf1  add     rsp, 68h
0x18000abf5  pop     r15
0x18000abf7  pop     r14
0x18000abf9  pop     r13
0x18000abfb  pop     r12
0x18000abfd  pop     rdi
0x18000abfe  pop     rsi
0x18000abff  pop     rbx
0x18000ac00  pop     rbp
0x18000ac01  retn
0x18000ac03  lea     rdx, aListenerOpenFa; "Listener.Open failed: 0x%x in %s"
0x18000ac0a  mov     r8d, edi
0x18000ac0d  lea     r9, aListenerWinsta; "Listener_WinStationQueryInformationW"
0x18000ac14  mov     ecx, 8; int
0x18000ac19  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000ac1e  mov     ecx, edi; int
0x18000ac20  call    ?ConvertHRESULT2WIN32@@YAKJ@Z; ConvertHRESULT2WIN32(long)
0x18000ac25  mov     ecx, eax; dwErrCode
0x18000ac27  call    cs:__imp_SetLastError
0x18000ac2e  nop     dword ptr [rax+rax+00h]
0x18000ac33  xor     bl, bl
0x18000ac35  jmp     short loc_18000ABDD
0x18000ac37  lea     rdx, aListenerIslist; "listener.IsListening failed: 0x%x in %s"
0x18000ac3e  jmp     short loc_18000AC0A
0x18000ac40  lea     rdx, aWinstationinfo; "WINSTATIONINFORMATION (or WINSTATIONINF"...
0x18000ac47  mov     ecx, 8; int
0x18000ac4c  xor     bl, bl
0x18000ac4e  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000ac53  mov     ecx, 57h ; 'W'; dwErrCode
0x18000ac58  call    cs:__imp_SetLastError
0x18000ac5f  nop     dword ptr [rax+rax+00h]
0x18000ac64  jmp     loc_18000ABDD
0x18000ac69  mov     ebx, dword ptr [rbp+Size]
0x18000ac6c  xor     edx, edx; Val
0x18000ac6e  mov     r8d, ebx; Size
0x18000ac71  mov     rcx, rdi; void *
0x18000ac74  call    memset_0
0x18000ac79  mov     rax, [rbp+arg_28]
0x18000ac7d  mov     [rax], ebx
0x18000ac7f  mov     ebx, 1
0x18000ac84  jmp     loc_18000ABEF
0x18000ac89  call    cs:__imp_GetLastError
0x18000ac90  nop     dword ptr [rax+rax+00h]
0x18000ac95  mov     ebx, eax
0x18000ac97  test    eax, eax
0x18000ac99  jle     short loc_18000ACA4
0x18000ac9b  movzx   ebx, ax
0x18000ac9e  or      ebx, 80070000h
0x18000aca4  test    ebx, ebx
0x18000aca6  js      short loc_18000ACD2
0x18000aca8  mov     eax, [rbp+arg_10]
0x18000acab  mov     [rdi], eax
0x18000acad  mov     rax, [rbp+arg_28]
0x18000acb1  mov     [rax], r14d
0x18000acb4  jmp     short loc_18000AC7F
0x18000acb6  mov     eax, dword ptr [rbp+Size]
0x18000acb9  mov     r14d, 4
0x18000acbf  cmp     eax, r14d
0x18000acc2  jz      short loc_18000AD0A
0x18000acc4  mov     ebx, 80070057h
0x18000acc9  lea     rdx, aWinstationtype_0; "WinStationType - Invalid Size failed: 0"...
0x18000acd0  jmp     short loc_18000ACD9
0x18000acd2  lea     rdx, aTsrpcquerysess_1; "_tsrpcQuerySessionInfo failed: 0x%x in "...
0x18000acd9  mov     r8d, ebx
0x18000acdc  lea     r9, aListenerWinsta; "Listener_WinStationQueryInformationW"
0x18000ace3  mov     ecx, 8; int
0x18000ace8  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000aced  mov     ecx, ebx; int
0x18000acef  call    ?ConvertHRESULT2WIN32@@YAKJ@Z; ConvertHRESULT2WIN32(long)
0x18000acf4  mov     ecx, eax; dwErrCode
0x18000acf6  call    cs:__imp_SetLastError
0x18000acfd  nop     dword ptr [rax+rax+00h]
0x18000ad02  mov     bl, r15b
0x18000ad05  jmp     loc_18000ABEF
0x18000ad0a  lea     rcx, [rbp+var_34]
0x18000ad0e  add     edx, 10000h; unsigned int
0x18000ad14  mov     [rsp+68h+var_40], rcx; unsigned int *
0x18000ad19  lea     r9, [rbp+arg_10]; void *
0x18000ad1d  mov     rcx, r12; this
0x18000ad20  mov     [rsp+68h+var_48], eax; unsigned int
0x18000ad24  mov     r8d, 27h ; '''; enum _WINSTATIONINFOCLASS
0x18000ad2a  call    ?_tsrpcQuerySessionInfo@@YAEPEAXKW4_WINSTATIONINFOCLASS@@0KPEAK@Z; _tsrpcQuerySessionInfo(void *,ulong,_WINSTATIONINFOCLASS,void *,ulong,ulong *)
0x18000ad2f  test    al, al
0x18000ad31  jnz     loc_18000ACA8
0x18000ad37  jmp     loc_18000AC89
0x18000ad3c  mov     [rdi], ebx
0x18000ad3e  jmp     loc_18000AB6F
0x18000ad43  lea     rdx, aWinstationname_2; "WinStationNameFromLogonIdW failed"
0x18000ad4a  mov     ecx, 8; int
0x18000ad4f  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000ad54  jmp     loc_18000ABDD
```
