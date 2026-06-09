# GetWinStationInformation(void *,ulong,_WINSTATIONINFORMATIONW *,ulong,ulong *)

- ea: `0x1800067b0`
- end: `0x180006e25`
- name: `?GetWinStationInformation@@YAJPEAXKPEAU_WINSTATIONINFORMATIONW@@KPEAK@Z`
- size: `1653`
- prototype: `__int64 __usercall@<rax>(CPublicBinding *this@<rcx>, unsigned int@<edx>, struct _WINSTATIONINFORMATIONW *@<r8>, unsigned int@<r9d>, unsigned int *)`
- caller_count: `1`
- callee_count: `23`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x18000ce54`

## callees

- `0x1800039e8`
- `0x180005374`
- `0x180005834`
- `0x180005974`
- `0x180005fcc`
- `0x180006040`
- `0x1800067b0`
- `0x180006e30`
- `0x180006f3c`
- `0x180007030`
- `0x180007890`
- `0x180008340`
- `0x180008e30`
- `0x180008f10`
- `0x1800097b0`
- `0x18001f5f8`
- `0x18002139c`
- `0x180021eb4`
- `0x1800230b8`
- `0x1800230ec`
- `0x18002bf2c`
- `0x18002fe06`
- `0x18002fe40`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180006afb`
- `msvcrt!??3@YAXPEAX@Z` at `0x180006afb`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180006aa7`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180006aa7`
- `ntdll!NtQuerySystemTime` at `0x180006c0a`
- `ntdll!NtQuerySystemTime` at `0x180006c0a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006d1d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006d1d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006a76`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006a86`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006a76`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006a86`
- `RPCRT4!RpcBindingFree` at `0x180006ab6`
- `RPCRT4!RpcBindingFree` at `0x180006ac7`
- `RPCRT4!RpcBindingFree` at `0x180006e05`
- `RPCRT4!RpcBindingFree` at `0x180006e10`
- `RPCRT4!RpcBindingFree` at `0x180006ab6`
- `RPCRT4!RpcBindingFree` at `0x180006ac7`
- `RPCRT4!RpcBindingFree` at `0x180006e05`
- `RPCRT4!RpcBindingFree` at `0x180006e10`

## string_xrefs

- `0x180006c35`: `StringCchCopy failed: %x`
- `0x180006a51`: `StringCchCopy failed: 0x%x in %s`
- `0x180006cf1`: `Session.Open failed: 0x%x in %s`
- `0x180006d79`: `GetProtocolStatus failed: 0x%x`
- `0x180006dde`: `_GetSessionProtocolLastInputTime`
- `0x180006de8`: `GetSessionProtocolLastInputTime failed: 0x%x in %s`
- `0x180006df9`: `_GetSessionProtocolLastInputTime failed: 0x%x in %s`

## pseudocode

```c
__int64 __fastcall GetWinStationInformation(
        CPublicBinding *this,
        unsigned int a2,
        struct _WINSTATIONINFORMATIONW *a3,
        unsigned int a4,
        unsigned int *a5)
{
  struct _WINSTATIONINFORMATIONW *v5; // r12
  unsigned int v6; // edi
  CPublicBinding *v7; // rbx
  int v9; // r13d
  __int64 v10; // rsi
  CPublicBinding *v11; // rax
  _WORD *v12; // rax
  _WORD *v13; // r9
  __int64 v14; // rcx
  int *v15; // rdx
  __int64 v16; // r10
  _WORD *v17; // rcx
  int v18; // edi
  void *UnifiedRpcBinding; // rax
  _WORD *v20; // rcx
  _WORD *v21; // r8
  __int64 v22; // rdx
  BYTE *v23; // r10
  __int64 v24; // r9
  BYTE *v25; // rcx
  unsigned int ProtocolStatus; // edi
  __int64 v27; // rdx
  BYTE *v28; // r9
  BYTE *v29; // rcx
  const char *v30; // rdx
  void *v31; // rcx
  void *v32; // rcx
  int State; // eax
  int Times; // eax
  union _LARGE_INTEGER *v36; // rsi
  LONGLONG v37; // r15
  struct _PROTOCOLSTATUS *v38; // r14
  unsigned int v39; // r12d
  int SessionProtocolLastInputTime; // eax
  void *v41; // rax
  int v42; // eax
  struct _PROTOCOLSTATUS *v43; // r8
  void *v44; // r14
  int LastInputTime; // eax
  HLOCAL hMem; // [rsp+30h] [rbp-D0h] BYREF
  HLOCAL v49; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int16 v50[4]; // [rsp+40h] [rbp-C0h] BYREF
  CPublicBinding *v51; // [rsp+48h] [rbp-B8h]
  void *v52; // [rsp+50h] [rbp-B0h]
  unsigned int *v53; // [rsp+58h] [rbp-A8h]
  __int64 v54; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v55; // [rsp+68h] [rbp-98h]
  __int128 v56; // [rsp+70h] [rbp-90h]
  __int128 v57; // [rsp+80h] [rbp-80h]
  __int128 v58; // [rsp+90h] [rbp-70h]
  __int64 v59; // [rsp+A0h] [rbp-60h]
  char v60[208]; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v61; // [rsp+178h] [rbp+78h]

  v53 = a5;
  v5 = a3;
  v6 = a2;
  v52 = this;
  v7 = this;
  v59 = 0;
  hMem = 0;
  v49 = 0;
  v54 = 0;
  v55 = -1;
  v61 = 0;
  v56 = 0;
  v57 = 0;
  v58 = 0;
  memset_0(v60, 0, sizeof(v60));
  *(_QWORD *)v50 = 0;
  v9 = 0;
  v10 = 2147483646;
  if ( v7 )
  {
LABEL_15:
    v51 = v7;
    goto LABEL_16;
  }
  v11 = (CPublicBinding *)operator new(0x40u, (const struct std::nothrow_t *)&std::nothrow);
  v7 = v11;
  if ( v11 )
  {
    *(_QWORD *)v11 = 0;
    *((_QWORD *)v11 + 1) = 0;
    *((_QWORD *)v11 + 2) = 0;
    v9 = 1;
    *((_QWORD *)v11 + 3) = 0;
    *((_QWORD *)v11 + 4) = 0;
    *((_QWORD *)v11 + 5) = 0;
    *((_QWORD *)v11 + 6) = 1;
    *((_QWORD *)v11 + 7) = 0;
    v12 = operator new[](2u, (const struct std::nothrow_t *)&std::nothrow);
    *((_QWORD *)v7 + 5) = v12;
    v13 = v12;
    if ( v12 )
    {
      v14 = 2147483646;
      v15 = &dword_18003D0CC;
      v16 = 1;
      do
      {
        if ( !v14 )
          break;
        if ( !*(_WORD *)v15 )
          break;
        *v13 = *(_WORD *)v15;
        v15 = (int *)((char *)v15 + 2);
        ++v13;
        --v14;
        --v16;
      }
      while ( v16 );
      v17 = v13 - 1;
      v18 = -2147024774;
      if ( v16 )
      {
        v17 = v13;
        v18 = 0;
      }
      *v17 = 0;
      if ( v16 )
      {
        if ( !*((_QWORD *)v7 + 3) && !*((_DWORD *)v7 + 12) )
        {
          if ( (unsigned int)CPublicBinding::OpenSessionContextHandle((RPC_BINDING_HANDLE *)v7) == -2147023174 )
            *((_DWORD *)v7 + 13) = 1;
          CPublicBinding::CloseSessionContextHandle(v7);
        }
      }
      else
      {
        ConvertHRESULT2WIN32(v18);
        _DbgPrintMessage(8, "StringCchCopy failed: %x", v18);
      }
      v6 = a2;
    }
    *(_DWORD *)&v50[2] = 1;
    goto LABEL_15;
  }
  v7 = 0;
  v51 = 0;
  SetLastError(0xEu);
  _DbgPrintMessage(8, "new CPublicBinding");
LABEL_16:
  if ( a4 >= 0x4C0 )
  {
    memset_0(v5, 0, sizeof(struct _WINSTATIONINFORMATIONW));
    if ( v7 )
    {
      if ( *((_QWORD *)v7 + 3) )
        UnifiedRpcBinding = CPublicBinding::GetUnifiedRpcBinding(v7);
      else
        UnifiedRpcBinding = CPublicBinding::GetLSMBinding((RPC_BINDING_HANDLE *)v7);
    }
    else
    {
      UnifiedRpcBinding = 0;
    }
    if ( (int)CSmartSession::GetSessionInformation((CSmartSession *)&v54, v6, UnifiedRpcBinding) < 0 )
    {
      v41 = (void *)CSmartPublicBinding::operator void *(v50);
      v42 = CSmartSession::Open((CSmartSession *)&v54, v6, v41);
      ProtocolStatus = v42;
      if ( v42 < 0 )
      {
        _DbgPrintMessage(8, "Session.Open failed: 0x%x in %s", v42, "GetWinStationInformation");
        goto LABEL_40;
      }
    }
    if ( (int)CSmartSession::GetUserNameW((CSmartSession *)&v54, (unsigned __int16 **)&hMem, (unsigned __int16 **)&v49) >= 0
      && (v20 = hMem) != 0
      && (v21 = v49) != 0 )
    {
      v22 = 2147483646;
      v23 = &v5->Reserved3[1084];
      v24 = 21;
      do
      {
        if ( !v22 )
          break;
        if ( !*v20 )
          break;
        *(_WORD *)v23 = *v20++;
        v23 += 2;
        --v22;
        --v24;
      }
      while ( v24 );
      v25 = v23 - 2;
      ProtocolStatus = -2147024774;
      if ( v24 )
      {
        v25 = v23;
        ProtocolStatus = 0;
      }
      *(_WORD *)v25 = 0;
      if ( !v24 )
        goto LABEL_38;
      v27 = 18;
      v28 = &v5->Reserved3[1048];
      do
      {
        if ( !v10 )
          break;
        if ( !*v21 )
          break;
        *(_WORD *)v28 = *v21++;
        v28 += 2;
        --v10;
        --v27;
      }
      while ( v27 );
      v29 = v28 - 2;
      ProtocolStatus = -2147024774;
      if ( v27 )
      {
        v29 = v28;
        ProtocolStatus = 0;
      }
      *(_WORD *)v29 = 0;
      if ( !v27 )
      {
LABEL_38:
        v30 = "StringCchCopy failed: 0x%x in %s";
LABEL_39:
        _DbgPrintMessage(8, v30, ProtocolStatus, "GetWinStationInformation", a2);
        goto LABEL_40;
      }
    }
    else
    {
      *(_WORD *)&v5->Reserved3[1084] = 0;
      *(_WORD *)&v5->Reserved3[1048] = 0;
    }
    State = CSmartSession::GetState((CSmartSession *)&v54, (int *)v5);
    ProtocolStatus = State;
    if ( State < 0 )
    {
      _DbgPrintMessage(8, "GetState failed: 0x%x in %s", (unsigned int)State, "GetWinStationInformation");
      goto LABEL_40;
    }
    if ( (int)CSmartSession::GetTerminalName((CSmartSession *)&v54, (unsigned __int16 *)&v5->Reserved2[4]) < 0 )
      *(_WORD *)&v5->Reserved2[4] = 0;
    Times = CSmartSession::GetTimes(
              (CSmartSession *)&v54,
              (union _LARGE_INTEGER *)&v5->Reserved3[4],
              (union _LARGE_INTEGER *)&v5->Reserved3[12],
              (union _LARGE_INTEGER *)&v5->Reserved3[28]);
    ProtocolStatus = Times;
    if ( Times < 0 )
    {
      _DbgPrintMessage(8, "GetTimes failed: 0x%x in %s", (unsigned int)Times, "GetWinStationInformation");
      goto LABEL_40;
    }
    v36 = (union _LARGE_INTEGER *)&v5->Reserved3[20];
    v37 = *(_QWORD *)&v5->Reserved3[12];
    v38 = (struct _PROTOCOLSTATUS *)&v5->Reserved3[36];
    if ( *(_DWORD *)v5->Reserved2 != 4 )
    {
      v39 = v55;
      SessionProtocolLastInputTime = GetSessionProtocolLastInputTime(v52, v55, v38, v36);
      ProtocolStatus = SessionProtocolLastInputTime;
      if ( SessionProtocolLastInputTime == -2147023151 )
      {
        v43 = v38;
        v44 = v52;
        ProtocolStatus = GetProtocolStatus(v52, v39, v43);
        if ( (int)(ProtocolStatus + 0x80000000) < 0 || ProtocolStatus == -2147467262 )
        {
          LastInputTime = GetLastInputTime(v44, v39, v36);
          ProtocolStatus = LastInputTime;
          if ( LastInputTime >= 0 )
            goto LABEL_80;
          if ( LastInputTime == -2147467262
            || LastInputTime == -2147022646
            || LastInputTime == -2147023174
            || LastInputTime == -2147023179 )
          {
            v36->QuadPart = v37;
            goto LABEL_80;
          }
          _DbgPrintMessage(8, "GetLastInputTime failed: 0x%x", LastInputTime);
        }
        else
        {
          _DbgPrintMessage(8, "GetProtocolStatus failed: 0x%x", ProtocolStatus);
        }
        goto LABEL_99;
      }
      if ( SessionProtocolLastInputTime != -2147467262
        && SessionProtocolLastInputTime != -2147022646
        && SessionProtocolLastInputTime != -2147023174
        && SessionProtocolLastInputTime != -2147023179 )
      {
        if ( SessionProtocolLastInputTime >= 0 )
        {
LABEL_80:
          v5 = a3;
          goto LABEL_71;
        }
        _DbgPrintMessage(
          8,
          "GetSessionProtocolLastInputTime failed: 0x%x in %s",
          SessionProtocolLastInputTime,
          "_GetSessionProtocolLastInputTime");
LABEL_99:
        v30 = "_GetSessionProtocolLastInputTime failed: 0x%x in %s";
        goto LABEL_39;
      }
      v5 = a3;
    }
    memset_0(v38, 0, 0x3F4u);
    v36->QuadPart = v37;
LABEL_71:
    NtQuerySystemTime((PLARGE_INTEGER)&v5->Reserved3[1132]);
    ProtocolStatus = 0;
    v5->LogonId = a2;
    *v53 = 1216;
    goto LABEL_40;
  }
  ProtocolStatus = -2147024809;
LABEL_40:
  if ( hMem )
    LocalFree(hMem);
  if ( v49 )
    LocalFree(v49);
  if ( v9 && v7 )
  {
    CPublicBinding::CloseSessionContextHandle(v7);
    v31 = (void *)*((_QWORD *)v7 + 5);
    if ( v31 )
      operator delete[](v31);
    if ( *(_QWORD *)v7 )
      RpcBindingFree((RPC_BINDING_HANDLE *)v7);
    if ( *((_QWORD *)v7 + 1) )
      RpcBindingFree((RPC_BINDING_HANDLE *)v7 + 1);
    if ( *((_QWORD *)v7 + 2) )
      RpcBindingFree((RPC_BINDING_HANDLE *)v7 + 2);
    if ( *((_QWORD *)v7 + 3) )
      RpcBindingFree((RPC_BINDING_HANDLE *)v7 + 3);
    v32 = (void *)*((_QWORD *)v7 + 4);
    if ( v32 )
      Legacy_WinStationCloseServer(v32);
    operator delete(v7);
  }
  CSmartSession::~CSmartSession((CSmartSession *)&v54);
  return ProtocolStatus;
}

```

## disassembly

```asm
0x1800067b0  mov     [rsp-8+arg_18], rbx
0x1800067b5  push    rbp
0x1800067b6  push    rsi
0x1800067b7  push    rdi
0x1800067b8  push    r12
0x1800067ba  push    r13
0x1800067bc  push    r14
0x1800067be  push    r15
0x1800067c0  lea     rbp, [rsp-90h]
0x1800067c8  sub     rsp, 190h
0x1800067cf  mov     rax, cs:__security_cookie
0x1800067d6  xor     rax, rsp
0x1800067d9  mov     [rbp+0C0h+var_40], rax
0x1800067e0  mov     rax, [rbp+0C0h+arg_20]
0x1800067e7  xor     r15d, r15d
0x1800067ea  xorps   xmm0, xmm0
0x1800067ed  mov     [rsp+1C0h+var_168], rax
0x1800067f2  xor     eax, eax
0x1800067f4  mov     [rsp+1C0h+var_198], r8
0x1800067f9  mov     r12, r8
0x1800067fc  mov     [rsp+1C0h+var_1A0], edx
0x180006800  mov     edi, edx
0x180006802  mov     [rsp+1C0h+var_170], rcx
0x180006807  mov     rbx, rcx
0x18000680a  mov     [rbp+0C0h+var_120], rax
0x18000680e  xor     edx, edx; Val
0x180006810  mov     [rsp+1C0h+hMem], r15
0x180006815  mov     r8d, 0D0h; Size
0x18000681b  mov     [rsp+1C0h+var_188], r15
0x180006820  lea     rcx, [rbp+0C0h+var_118]; void *
0x180006824  mov     [rsp+1C0h+var_160], r15
0x180006829  mov     r14d, r9d
0x18000682c  mov     [rsp+1C0h+var_158], 0FFFFFFFFh
0x180006834  mov     [rbp+0C0h+var_48], r15
0x180006838  movups  [rsp+1C0h+var_150], xmm0
0x18000683d  movups  [rbp+0C0h+var_140], xmm0
0x180006841  movups  [rbp+0C0h+var_130], xmm0
0x180006845  call    memset_0
0x18000684a  mov     qword ptr [rsp+1C0h+var_180], r15
0x18000684f  mov     r13d, r15d
0x180006852  mov     esi, 7FFFFFFEh
0x180006857  test    rbx, rbx
0x18000685a  jnz     loc_180006928
0x180006860  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180006867  mov     ecx, 40h ; '@'; unsigned __int64
0x18000686c  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180006871  mov     rbx, rax
0x180006874  test    rax, rax
0x180006877  jz      loc_180006D10
0x18000687d  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180006884  mov     [rax], r15
0x180006887  mov     ecx, 2; unsigned __int64
0x18000688c  mov     [rax+8], r15
0x180006890  mov     [rax+10h], r15
0x180006894  mov     r13d, 1
0x18000689a  mov     [rax+18h], r15
0x18000689e  mov     [rax+20h], r15
0x1800068a2  mov     [rax+28h], r15
0x1800068a6  mov     qword ptr [rax+30h], 1
0x1800068ae  mov     [rax+38h], r15
0x1800068b2  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800068b7  mov     [rbx+28h], rax
0x1800068bb  mov     r9, rax
0x1800068be  test    rax, rax
0x1800068c1  jz      short loc_180006923
0x1800068c3  mov     ecx, esi
0x1800068c5  lea     rdx, dword_18003D0CC
0x1800068cc  mov     r10d, r13d
0x1800068cf  nop
0x1800068d0  test    rcx, rcx
0x1800068d3  jz      short loc_1800068F1
0x1800068d5  movzx   eax, word ptr [rdx]
0x1800068d8  test    ax, ax
0x1800068db  jz      short loc_1800068F1
0x1800068dd  mov     [r9], ax
0x1800068e1  add     rdx, 2
0x1800068e5  add     r9, 2
0x1800068e9  dec     rcx
0x1800068ec  sub     r10, r13
0x1800068ef  jnz     short loc_1800068D0
0x1800068f1  test    r10, r10
0x1800068f4  lea     rcx, [r9-2]
0x1800068f8  mov     edi, 8007007Ah
0x1800068fd  cmovnz  rcx, r9
0x180006901  cmovnz  edi, r15d
0x180006905  mov     [rcx], r15w
0x180006909  jz      loc_180006C2B
0x18000690f  cmp     [rbx+18h], r15
0x180006913  jnz     short loc_18000691F
0x180006915  cmp     [rbx+30h], r15d
0x180006919  jz      loc_180006C4B
0x18000691f  mov     edi, [rsp+1C0h+var_1A0]
0x180006923  mov     dword ptr [rsp+1C0h+var_180+4], r13d
0x180006928  mov     [rsp+1C0h+var_178], rbx
0x18000692d  cmp     r14d, 4C0h
0x180006934  jb      loc_180006D39
0x18000693a  xor     edx, edx; Val
0x18000693c  mov     r8d, 4C0h; Size
0x180006942  mov     rcx, r12; void *
0x180006945  call    memset_0
0x18000694a  test    rbx, rbx
0x18000694d  jz      loc_180006CBC
0x180006953  mov     rcx, rbx; Binding
0x180006956  cmp     [rbx+18h], r15
0x18000695a  jz      loc_180006B37
0x180006960  call    ?GetUnifiedRpcBinding@CPublicBinding@@QEAAPEAXXZ; CPublicBinding::GetUnifiedRpcBinding(void)
0x180006965  mov     r8, rax; void *
0x180006968  lea     rcx, [rsp+1C0h+var_160]; this
0x18000696d  mov     edx, edi; unsigned int
0x18000696f  call    ?GetSessionInformation@CSmartSession@@QEAAJKPEAX@Z; CSmartSession::GetSessionInformation(ulong,void *)
0x180006974  test    eax, eax
0x180006976  js      loc_180006CC4
0x18000697c  lea     r8, [rsp+1C0h+var_188]; unsigned __int16 **
0x180006981  lea     rdx, [rsp+1C0h+hMem]; unsigned __int16 **
0x180006986  lea     rcx, [rsp+1C0h+var_160]; this
0x18000698b  call    ?GetUserNameW@CSmartSession@@QEAAJPEAPEAG0@Z; CSmartSession::GetUserNameW(ushort * *,ushort * *)
0x180006990  test    eax, eax
0x180006992  js      loc_180006B41
0x180006998  mov     rcx, [rsp+1C0h+hMem]
0x18000699d  test    rcx, rcx
0x1800069a0  jz      loc_180006B41
0x1800069a6  mov     r8, [rsp+1C0h+var_188]
0x1800069ab  test    r8, r8
0x1800069ae  jz      loc_180006B41
0x1800069b4  mov     rdx, rsi
0x1800069b7  lea     r10, [r12+488h]
0x1800069bf  mov     r9d, 15h
0x1800069c5  test    rdx, rdx
0x1800069c8  jz      short loc_1800069E7
0x1800069ca  movzx   eax, word ptr [rcx]
0x1800069cd  test    ax, ax
0x1800069d0  jz      short loc_1800069E7
0x1800069d2  mov     [r10], ax
0x1800069d6  add     rcx, 2
0x1800069da  add     r10, 2
0x1800069de  dec     rdx
0x1800069e1  sub     r9, 1
0x1800069e5  jnz     short loc_1800069C5
0x1800069e7  test    r9, r9
0x1800069ea  lea     rcx, [r10-2]
0x1800069ee  mov     edi, 8007007Ah
0x1800069f3  cmovnz  rcx, r10
0x1800069f7  cmovnz  edi, r15d
0x1800069fb  mov     [rcx], r15w
0x1800069ff  jz      short loc_180006A51
0x180006a01  mov     edx, 12h
0x180006a06  lea     r9, [r12+464h]
0x180006a0e  xchg    ax, ax
0x180006a10  test    rsi, rsi
0x180006a13  jz      short loc_180006A33
0x180006a15  movzx   eax, word ptr [r8]
0x180006a19  test    ax, ax
0x180006a1c  jz      short loc_180006A33
0x180006a1e  mov     [r9], ax
0x180006a22  add     r8, 2
0x180006a26  add     r9, 2
0x180006a2a  dec     rsi
0x180006a2d  sub     rdx, 1
0x180006a31  jnz     short loc_180006A10
0x180006a33  test    rdx, rdx
0x180006a36  lea     rcx, [r9-2]
0x180006a3a  mov     edi, 8007007Ah
0x180006a3f  cmovnz  rcx, r9
0x180006a43  cmovnz  edi, r15d
0x180006a47  mov     [rcx], r15w
0x180006a4b  jnz     loc_180006B53
0x180006a51  lea     rdx, aStringcchcopyF_0; "StringCchCopy failed: 0x%x in %s"
0x180006a58  mov     r8d, edi
0x180006a5b  lea     r9, aGetwinstationi; "GetWinStationInformation"
0x180006a62  mov     ecx, 8; int
0x180006a67  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180006a6c  mov     rcx, [rsp+1C0h+hMem]; hMem
0x180006a71  test    rcx, rcx
0x180006a74  jz      short loc_180006A7C
0x180006a76  call    cs:__imp_LocalFree
0x180006a7c  mov     rcx, [rsp+1C0h+var_188]; hMem
0x180006a81  test    rcx, rcx
0x180006a84  jz      short loc_180006A8C
0x180006a86  call    cs:__imp_LocalFree
0x180006a8c  test    r13d, r13d
0x180006a8f  jz      short loc_180006B01
0x180006a91  test    rbx, rbx
0x180006a94  jz      short loc_180006B01
0x180006a96  mov     rcx, rbx; this
0x180006a99  call    ?CloseSessionContextHandle@CPublicBinding@@AEAAJXZ; CPublicBinding::CloseSessionContextHandle(void)
0x180006a9e  mov     rcx, [rbx+28h]
0x180006aa2  test    rcx, rcx
0x180006aa5  jz      short loc_180006AAD
0x180006aa7  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180006aad  cmp     qword ptr [rbx], 0
0x180006ab1  jz      short loc_180006ABC
0x180006ab3  mov     rcx, rbx; Binding
0x180006ab6  call    cs:__imp_RpcBindingFree
0x180006abc  cmp     qword ptr [rbx+8], 0
0x180006ac1  lea     rcx, [rbx+8]; Binding
0x180006ac5  jz      short loc_180006ACD
0x180006ac7  call    cs:__imp_RpcBindingFree
0x180006acd  cmp     qword ptr [rbx+10h], 0
0x180006ad2  lea     rcx, [rbx+10h]; Binding
0x180006ad6  jnz     loc_180006E05
0x180006adc  cmp     qword ptr [rbx+18h], 0
0x180006ae1  lea     rcx, [rbx+18h]; Binding
0x180006ae5  jnz     loc_180006E10
0x180006aeb  mov     rcx, [rbx+20h]; void *
0x180006aef  test    rcx, rcx
0x180006af2  jnz     loc_180006E1B
0x180006af8  mov     rcx, rbx
0x180006afb  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180006b01  lea     rcx, [rsp+1C0h+var_160]; this
0x180006b06  call    ??1CSmartSession@@QEAA@XZ; CSmartSession::~CSmartSession(void)
0x180006b0b  mov     eax, edi
0x180006b0d  mov     rcx, [rbp+0C0h+var_40]
0x180006b14  xor     rcx, rsp; StackCookie
0x180006b17  call    __security_check_cookie
0x180006b1c  mov     rbx, [rsp+1C0h+arg_18]
0x180006b24  add     rsp, 190h
0x180006b2b  pop     r15
0x180006b2d  pop     r14
0x180006b2f  pop     r13
0x180006b31  pop     r12
0x180006b33  pop     rdi
0x180006b34  pop     rsi
0x180006b35  pop     rbp
0x180006b36  retn
0x180006b37  call    ?GetLSMBinding@CPublicBinding@@QEAAPEAXXZ; CPublicBinding::GetLSMBinding(void)
0x180006b3c  jmp     loc_180006965
0x180006b41  mov     [r12+488h], r15w
0x180006b4a  mov     [r12+464h], r15w
0x180006b53  mov     rdx, r12; int *
0x180006b56  lea     rcx, [rsp+1C0h+var_160]; this
0x180006b5b  call    ?GetState@CSmartSession@@QEAAJPEAJ@Z; CSmartSession::GetState(long *)
0x180006b60  mov     edi, eax
0x180006b62  test    eax, eax
0x180006b64  js      loc_180006CAD
0x180006b6a  lea     rdx, [r12+4]; unsigned __int16 *
0x180006b6f  lea     rcx, [rsp+1C0h+var_160]; this
0x180006b74  call    ?GetTerminalName@CSmartSession@@QEAAJPEAG@Z; CSmartSession::GetTerminalName(ushort *)
0x180006b79  test    eax, eax
0x180006b7b  js      loc_180006D43
0x180006b81  lea     r9, [r12+68h]; union _LARGE_INTEGER *
0x180006b86  lea     rdx, [r12+50h]; union _LARGE_INTEGER *
0x180006b8b  lea     r8, [r12+58h]; union _LARGE_INTEGER *
0x180006b90  lea     rcx, [rsp+1C0h+var_160]; this
0x180006b95  call    ?GetTimes@CSmartSession@@QEAAJPEAT_LARGE_INTEGER@@00@Z; CSmartSession::GetTimes(_LARGE_INTEGER *,_LARGE_INTEGER *,_LARGE_INTEGER *)
0x180006b9a  mov     edi, eax
0x180006b9c  test    eax, eax
0x180006b9e  js      loc_180006C9E
0x180006ba4  cmp     dword ptr [r12], 4
0x180006ba9  lea     rsi, [r12+60h]
0x180006bae  mov     r15, [r12+58h]
0x180006bb3  lea     r14, [r12+70h]
0x180006bb8  jz      short loc_180006BEF
0x180006bba  mov     r12d, [rsp+1C0h+var_158]
0x180006bbf  mov     r9, rsi; union _LARGE_INTEGER *
0x180006bc2  mov     rcx, [rsp+1C0h+var_170]; void *
0x180006bc7  mov     edx, r12d; unsigned int
0x180006bca  mov     r8, r14; struct _PROTOCOLSTATUS *
0x180006bcd  call    ?GetSessionProtocolLastInputTime@@YAJPEAXKPEAU_PROTOCOLSTATUS@@PEAT_LARGE_INTEGER@@@Z; GetSessionProtocolLastInputTime(void *,ulong,_PROTOCOLSTATUS *,_LARGE_INTEGER *)
0x180006bd2  mov     edi, eax
0x180006bd4  cmp     eax, 800706D1h
0x180006bd9  jz      loc_180006D4E
0x180006bdf  cmp     eax, 80004002h
0x180006be4  jnz     loc_180006C6B
0x180006bea  mov     r12, [rsp+1C0h+var_198]
0x180006bef  xor     edx, edx; Val
0x180006bf1  mov     r8d, 3F4h; Size
0x180006bf7  mov     rcx, r14; void *
0x180006bfa  call    memset_0
0x180006bff  mov     [rsi], r15
0x180006c02  lea     rcx, [r12+4B8h]; SystemTime
0x180006c0a  call    cs:__imp_NtQuerySystemTime
0x180006c10  mov     eax, [rsp+1C0h+var_1A0]
0x180006c14  xor     edi, edi
0x180006c16  mov     [r12+48h], eax
0x180006c1b  mov     rax, [rsp+1C0h+var_168]
0x180006c20  mov     dword ptr [rax], 4C0h
0x180006c26  jmp     loc_180006A6C
0x180006c2b  mov     ecx, edi; int
0x180006c2d  call    ?ConvertHRESULT2WIN32@@YAKJ@Z; ConvertHRESULT2WIN32(long)
0x180006c32  mov     r8d, edi
0x180006c35  lea     rdx, aStringcchcopyF; "StringCchCopy failed: %x"
0x180006c3c  mov     ecx, 8; int
0x180006c41  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180006c46  jmp     loc_18000691F
0x180006c4b  mov     rcx, rbx; this
0x180006c4e  call    ?OpenSessionContextHandle@CPublicBinding@@AEAAJXZ; CPublicBinding::OpenSessionContextHandle(void)
0x180006c53  cmp     eax, 800706BAh
0x180006c58  jz      loc_180006D07
0x180006c5e  mov     rcx, rbx; this
0x180006c61  call    ?CloseSessionContextHandle@CPublicBinding@@AEAAJXZ; CPublicBinding::CloseSessionContextHandle(void)
0x180006c66  jmp     loc_18000691F
0x180006c6b  cmp     eax, 800708CAh
0x180006c70  jz      loc_180006BEA
0x180006c76  cmp     eax, 800706BAh
0x180006c7b  jz      loc_180006BEA
0x180006c81  cmp     eax, 800706B5h
0x180006c86  jz      loc_180006BEA
0x180006c8c  test    eax, eax
0x180006c8e  js      loc_180006DDE
0x180006c94  mov     r12, [rsp+1C0h+var_198]
  ... truncated ...
```
