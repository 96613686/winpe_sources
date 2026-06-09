# Listener_WinStationQueryInformationW(void *,ulong,_WINSTATIONINFOCLASS,void *,ulong,ulong *)

- ea: `0x180003ba8`
- end: `0x180003e21`
- name: `?Listener_WinStationQueryInformationW@@YAEPEAXKW4_WINSTATIONINFOCLASS@@0KPEAK@Z`
- size: `633`
- prototype: `unsigned __int8 __usercall@<al>(CPublicBinding *this@<rcx>, unsigned int@<edx>, enum _WINSTATIONINFOCLASS@<r8d>, void *@<r9>, unsigned int, unsigned int *)`
- caller_count: `1`
- callee_count: `12`
- tags: ``

## callers

- `0x18000c820`

## callees

- `0x1800036e0`
- `0x180003ad4`
- `0x180003b48`
- `0x180003ba8`
- `0x180004450`
- `0x180005c30`
- `0x180005fcc`
- `0x180007890`
- `0x180008290`
- `0x180008e30`
- `0x18000ce54`
- `0x18002fe06`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003d0a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003d35`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003dc4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003d0a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003d35`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003dc4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003d5d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003d5d`

## string_xrefs

- `0x180003ce6`: `Listener.Open failed: 0x%x in %s`

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
0x180003ba8  push    rbp
0x180003baa  push    rbx
0x180003bab  push    rsi
0x180003bac  push    rdi
0x180003bad  push    r12
0x180003baf  push    r13
0x180003bb1  push    r14
0x180003bb3  push    r15
0x180003bb5  mov     rbp, rsp
0x180003bb8  sub     rsp, 68h
0x180003bbc  xor     r15d, r15d
0x180003bbf  mov     r10d, r8d
0x180003bc2  mov     [rbp+arg_10], r15d
0x180003bc6  mov     rdi, r9
0x180003bc9  mov     [rbp+var_34], r15d
0x180003bcd  mov     esi, r8d
0x180003bd0  mov     r13d, edx
0x180003bd3  mov     r12, rcx
0x180003bd6  sub     r10d, 8
0x180003bda  jz      short loc_180003BF0
0x180003bdc  sub     r10d, 1Fh
0x180003be0  jz      loc_180003D84
0x180003be6  cmp     r10d, 1
0x180003bea  jnz     loc_180003D3D
0x180003bf0  mov     ebx, 1
0x180003bf5  lea     rcx, [rbp+var_20]; this
0x180003bf9  mov     r8d, ebx; int
0x180003bfc  mov     rdx, r12; void *
0x180003bff  call    ??0CSmartPublicBinding@@QEAA@PEAXH@Z; CSmartPublicBinding::CSmartPublicBinding(void *,int)
0x180003c04  cmp     esi, 28h ; '('
0x180003c07  mov     [rbp+var_30], r15
0x180003c0b  mov     eax, 4C0h
0x180003c10  lea     r14d, [rbx+3]
0x180003c14  lea     r15d, [rax+8]
0x180003c18  cmovnz  r15d, eax
0x180003c1c  lea     rax, [rdi+0Ch]
0x180003c20  cmovnz  rax, rdi
0x180003c24  mov     [rbp+var_28], rax
0x180003c28  lea     eax, [rbx+13h]
0x180003c2b  cmovnz  eax, r14d
0x180003c2f  cmp     r15d, dword ptr [rbp+Size]
0x180003c33  ja      loc_180003D1D
0x180003c39  mov     r8d, r15d; Size
0x180003c3c  lea     r14, [rax+rdi]
0x180003c40  xor     edx, edx; Val
0x180003c42  mov     rcx, rdi; void *
0x180003c45  call    memset_0
0x180003c4a  cmp     esi, 28h ; '('
0x180003c4d  jz      loc_180003E04
0x180003c53  lea     edx, [r13+10000h]; unsigned int
0x180003c5a  mov     r8, r14; unsigned __int16 *
0x180003c5d  mov     rcx, r12; this
0x180003c60  call    WinStationNameFromLogonIdW
0x180003c65  mov     bl, al
0x180003c67  test    al, al
0x180003c69  jz      loc_180003E0B
0x180003c6f  lea     rcx, [rbp+var_20]; unsigned __int16 *
0x180003c73  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x180003c78  mov     rdx, rax; void *
0x180003c7b  lea     rcx, [rbp+var_30]; this
0x180003c7f  mov     r8, r14; unsigned __int16 *
0x180003c82  call    ?Open@CListener@@QEAAJPEAXPEAG@Z; CListener::Open(void *,ushort *)
0x180003c87  mov     edi, eax
0x180003c89  test    eax, eax
0x180003c8b  js      short loc_180003CE6
0x180003c8d  lea     rdx, [rbp+var_38]; int *
0x180003c91  mov     [rbp+var_38], 0
0x180003c98  lea     rcx, [rbp+var_30]; this
0x180003c9c  call    ?IsListening@CListener@@QEAAJPEAH@Z; CListener::IsListening(int *)
0x180003ca1  mov     edi, eax
0x180003ca3  test    eax, eax
0x180003ca5  js      short loc_180003D14
0x180003ca7  mov     eax, [rbp+var_38]
0x180003caa  neg     eax
0x180003cac  mov     rax, [rbp+var_28]
0x180003cb0  sbb     ecx, ecx
0x180003cb2  and     ecx, 0FFFFFFFEh
0x180003cb5  add     ecx, 8
0x180003cb8  mov     [rax], ecx
0x180003cba  mov     rax, [rbp+arg_28]
0x180003cbe  mov     [rax], r15d
0x180003cc1  lea     rcx, [rbp+var_30]; this
0x180003cc5  call    ??1CListener@@QEAA@XZ; CListener::~CListener(void)
0x180003cca  lea     rcx, [rbp+var_20]; this
0x180003cce  call    ??1CSmartPublicBinding@@QEAA@XZ; CSmartPublicBinding::~CSmartPublicBinding(void)
0x180003cd3  mov     al, bl
0x180003cd5  add     rsp, 68h
0x180003cd9  pop     r15
0x180003cdb  pop     r14
0x180003cdd  pop     r13
0x180003cdf  pop     r12
0x180003ce1  pop     rdi
0x180003ce2  pop     rsi
0x180003ce3  pop     rbx
0x180003ce4  pop     rbp
0x180003ce5  retn
0x180003ce6  lea     rdx, aListenerOpenFa; "Listener.Open failed: 0x%x in %s"
0x180003ced  mov     r8d, edi
0x180003cf0  lea     r9, aListenerWinsta; "Listener_WinStationQueryInformationW"
0x180003cf7  mov     ecx, 8; int
0x180003cfc  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180003d01  mov     ecx, edi; int
0x180003d03  call    ?ConvertHRESULT2WIN32@@YAKJ@Z; ConvertHRESULT2WIN32(long)
0x180003d08  mov     ecx, eax; dwErrCode
0x180003d0a  call    cs:__imp_SetLastError
0x180003d10  xor     bl, bl
0x180003d12  jmp     short loc_180003CC1
0x180003d14  lea     rdx, aListenerIslist; "listener.IsListening failed: 0x%x in %s"
0x180003d1b  jmp     short loc_180003CED
0x180003d1d  lea     rdx, aWinstationinfo; "WINSTATIONINFORMATION (or WINSTATIONINF"...
0x180003d24  mov     ecx, 8; int
0x180003d29  xor     bl, bl
0x180003d2b  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180003d30  mov     ecx, 57h ; 'W'; dwErrCode
0x180003d35  call    cs:__imp_SetLastError
0x180003d3b  jmp     short loc_180003CC1
0x180003d3d  mov     ebx, dword ptr [rbp+Size]
0x180003d40  xor     edx, edx; Val
0x180003d42  mov     r8d, ebx; Size
0x180003d45  mov     rcx, rdi; void *
0x180003d48  call    memset_0
0x180003d4d  mov     rax, [rbp+arg_28]
0x180003d51  mov     [rax], ebx
0x180003d53  mov     ebx, 1
0x180003d58  jmp     loc_180003CD3
0x180003d5d  call    cs:__imp_GetLastError
0x180003d63  mov     ebx, eax
0x180003d65  test    eax, eax
0x180003d67  jle     short loc_180003D72
0x180003d69  movzx   ebx, ax
0x180003d6c  or      ebx, 80070000h
0x180003d72  test    ebx, ebx
0x180003d74  js      short loc_180003DA0
0x180003d76  mov     eax, [rbp+arg_10]
0x180003d79  mov     [rdi], eax
0x180003d7b  mov     rax, [rbp+arg_28]
0x180003d7f  mov     [rax], r14d
0x180003d82  jmp     short loc_180003D53
0x180003d84  mov     eax, dword ptr [rbp+Size]
0x180003d87  mov     r14d, 4
0x180003d8d  cmp     eax, r14d
0x180003d90  jz      short loc_180003DD2
0x180003d92  mov     ebx, 80070057h
0x180003d97  lea     rdx, aWinstationtype_0; "WinStationType - Invalid Size failed: 0"...
0x180003d9e  jmp     short loc_180003DA7
0x180003da0  lea     rdx, aTsrpcquerysess_1; "_tsrpcQuerySessionInfo failed: 0x%x in "...
0x180003da7  mov     r8d, ebx
0x180003daa  lea     r9, aListenerWinsta; "Listener_WinStationQueryInformationW"
0x180003db1  mov     ecx, 8; int
0x180003db6  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180003dbb  mov     ecx, ebx; int
0x180003dbd  call    ?ConvertHRESULT2WIN32@@YAKJ@Z; ConvertHRESULT2WIN32(long)
0x180003dc2  mov     ecx, eax; dwErrCode
0x180003dc4  call    cs:__imp_SetLastError
0x180003dca  mov     bl, r15b
0x180003dcd  jmp     loc_180003CD3
0x180003dd2  lea     rcx, [rbp+var_34]
0x180003dd6  add     edx, 10000h; unsigned int
0x180003ddc  mov     [rsp+68h+var_40], rcx; unsigned int *
0x180003de1  lea     r9, [rbp+arg_10]; void *
0x180003de5  mov     rcx, r12; void *
0x180003de8  mov     [rsp+68h+var_48], eax; unsigned int
0x180003dec  mov     r8d, 27h ; '''; enum _WINSTATIONINFOCLASS
0x180003df2  call    ?_tsrpcQuerySessionInfo@@YAEPEAXKW4_WINSTATIONINFOCLASS@@0KPEAK@Z; _tsrpcQuerySessionInfo(void *,ulong,_WINSTATIONINFOCLASS,void *,ulong,ulong *)
0x180003df7  test    al, al
0x180003df9  jnz     loc_180003D76
0x180003dff  jmp     loc_180003D5D
0x180003e04  mov     [rdi], ebx
0x180003e06  jmp     loc_180003C53
0x180003e0b  lea     rdx, aWinstationname_2; "WinStationNameFromLogonIdW failed"
0x180003e12  mov     ecx, 8; int
0x180003e17  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180003e1c  jmp     loc_180003CC1
```
