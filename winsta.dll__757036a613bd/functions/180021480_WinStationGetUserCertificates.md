# WinStationGetUserCertificates

- ea: `0x180021480`
- end: `0x18002168d`
- name: `WinStationGetUserCertificates`
- size: `525`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `service_task`

## callees

- `0x180005c30`
- `0x180005fcc`
- `0x180007890`
- `0x180008290`
- `0x180008e30`
- `0x180021480`
- `0x180024376`
- `0x180027e50`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002166f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002166f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800214da`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800214da`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800215cd`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800215eb`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800215cd`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800215eb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180021648`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180021648`
- `RPCRT4!NdrClientCall3` at `0x180021556`
- `RPCRT4!NdrClientCall3` at `0x180021556`

## string_xrefs

- `0x18002157f`: `RpcRevertFromServicesSession threw an exception: 0x%x`

## pseudocode

```c
bool __fastcall WinStationGetUserCertificates(HLOCAL *a1)
{
  signed int Pointer; // ebx
  signed int LastError; // eax
  ULONG SessionId; // ebx
  void *v5; // rax
  HLOCAL v6; // rax
  void *v7; // rcx
  bool v8; // sf
  DWORD v9; // eax
  bool v10; // bl
  unsigned __int16 v12[20]; // [rsp+50h] [rbp-28h] BYREF
  SIZE_T uBytes; // [rsp+88h] [rbp+10h] BYREF
  int v14; // [rsp+90h] [rbp+18h] BYREF
  void *Src; // [rsp+98h] [rbp+20h] BYREF

  Src = 0;
  LODWORD(uBytes) = 0;
  v14 = 0;
  CSmartPublicBinding::CSmartPublicBinding((CSmartPublicBinding *)v12, 0, 1);
  if ( a1 )
  {
    *a1 = 0;
    if ( CSmartPublicBinding::operator void *(v12) )
    {
      SessionId = NtCurrentPeb()->SessionId;
      v5 = CSmartPublicBinding::operator void *(v12);
      Pointer = (unsigned int)NdrClientCall3(
                                (MIDL_STUBLESS_PROXY_INFO *)&stru_1800320E0,
                                0xAu,
                                0,
                                v5,
                                SessionId,
                                &v14,
                                &Src,
                                &uBytes).Pointer;
      if ( Pointer >= 0 )
      {
        if ( v14 && Src && (_DWORD)uBytes )
        {
          v6 = LocalAlloc(0x40u, 0x10u);
          *a1 = v6;
          if ( v6
            && (*((_QWORD *)*a1 + 1) = LocalAlloc(0x40u, (unsigned int)uBytes), (v7 = (void *)*((_QWORD *)*a1 + 1)) != 0) )
          {
            memcpy_0(v7, Src, (unsigned int)uBytes);
            *(_DWORD *)*a1 = v14;
            *((_DWORD *)*a1 + 1) = uBytes;
            Pointer = 0;
          }
          else
          {
            Pointer = -2147024882;
          }
        }
        else
        {
          Pointer = -2147023728;
        }
      }
    }
    else
    {
      LastError = GetLastError();
      Pointer = LastError;
      if ( LastError > 0 )
        Pointer = (unsigned __int16)LastError | 0x80070000;
    }
  }
  else
  {
    Pointer = -2147024809;
  }
  if ( Src )
    LocalFree(Src);
  v8 = Pointer < 0;
  if ( Pointer < 0 )
  {
    if ( a1 )
    {
      WinStationFreeUserCertificates(*a1);
      *a1 = 0;
    }
    v9 = ConvertHRESULT2WIN32(Pointer);
    SetLastError(v9);
    v8 = Pointer < 0;
  }
  v10 = !v8;
  CSmartPublicBinding::~CSmartPublicBinding((CSmartPublicBinding *)v12);
  return v10;
}

```

## disassembly

```asm
0x180021480  mov     rax, rsp
0x180021483  mov     [rax+8], rcx
0x180021487  push    rbx
0x180021488  push    rsi
0x180021489  sub     rsp, 68h
0x18002148d  mov     rsi, rcx
0x180021490  mov     qword ptr [rax+20h], 0
0x180021498  mov     dword ptr [rax+10h], 0
0x18002149f  mov     dword ptr [rax+18h], 0
0x1800214a6  xor     edx, edx; void *
0x1800214a8  lea     r8d, [rdx+1]; int
0x1800214ac  lea     rcx, [rax-28h]; this
0x1800214b0  call    ??0CSmartPublicBinding@@QEAA@PEAXH@Z; CSmartPublicBinding::CSmartPublicBinding(void *,int)
0x1800214b5  test    rsi, rsi
0x1800214b8  jnz     short loc_1800214C4
0x1800214ba  mov     ebx, 80070057h
0x1800214bf  jmp     loc_18002163B
0x1800214c4  mov     qword ptr [rsi], 0
0x1800214cb  lea     rcx, [rsp+78h+var_28]; unsigned __int16 *
0x1800214d0  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x1800214d5  test    rax, rax
0x1800214d8  jnz     short loc_1800214F8
0x1800214da  call    cs:__imp_GetLastError
0x1800214e0  mov     ebx, eax
0x1800214e2  test    eax, eax
0x1800214e4  jle     loc_18002163B
0x1800214ea  movzx   ebx, ax
0x1800214ed  or      ebx, 80070000h
0x1800214f3  jmp     loc_18002163B
0x1800214f8  mov     rax, gs:60h
0x180021501  mov     ebx, [rax+2C0h]
0x180021507  lea     rcx, [rsp+78h+var_28]; unsigned __int16 *
0x18002150c  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x180021511  mov     [rsp+78h+var_30], 0
0x18002151a  lea     rcx, [rsp+78h+uBytes]
0x180021522  mov     [rsp+78h+var_40], rcx
0x180021527  lea     rcx, [rsp+78h+Src]
0x18002152f  mov     [rsp+78h+var_48], rcx
0x180021534  lea     rcx, [rsp+78h+arg_10]
0x18002153c  mov     [rsp+78h+var_50], rcx
0x180021541  mov     [rsp+78h+var_58], ebx
0x180021545  mov     r9, rax
0x180021548  xor     r8d, r8d; pReturnValue
0x18002154b  lea     edx, [r8+0Ah]; nProcNum
0x18002154f  lea     rcx, stru_1800320E0; pProxyInfo
0x180021556  call    cs:__imp_NdrClientCall3
0x18002155c  mov     rbx, rax
0x18002155f  mov     [rsp+78h+var_30], rax
0x180021564  mov     [rsp+78h+var_38], eax
0x180021568  jmp     short loc_180021598
0x18002156a  test    eax, eax
0x18002156c  jle     short loc_180021576
0x18002156e  movzx   eax, ax
0x180021571  or      eax, 80070000h
0x180021576  mov     ebx, eax
0x180021578  mov     [rsp+78h+var_38], eax
0x18002157c  mov     r8d, eax
0x18002157f  lea     rdx, aRpcrevertfroms; "RpcRevertFromServicesSession threw an e"...
0x180021586  mov     ecx, 8; int
0x18002158b  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180021590  mov     rsi, [rsp+78h+arg_0]
0x180021598  test    ebx, ebx
0x18002159a  js      loc_18002163B
0x1800215a0  cmp     [rsp+78h+arg_10], 0
0x1800215a8  jz      loc_180021636
0x1800215ae  cmp     [rsp+78h+Src], 0
0x1800215b7  jz      short loc_180021636
0x1800215b9  cmp     dword ptr [rsp+78h+uBytes], 0
0x1800215c1  jz      short loc_180021636
0x1800215c3  mov     edx, 10h; uBytes
0x1800215c8  lea     ebx, [rdx+30h]
0x1800215cb  mov     ecx, ebx; uFlags
0x1800215cd  call    cs:__imp_LocalAlloc
0x1800215d3  mov     [rsi], rax
0x1800215d6  test    rax, rax
0x1800215d9  jnz     short loc_1800215E2
0x1800215db  mov     ebx, 8007000Eh
0x1800215e0  jmp     short loc_18002163B
0x1800215e2  mov     edx, dword ptr [rsp+78h+uBytes]; uBytes
0x1800215e9  mov     ecx, ebx; uFlags
0x1800215eb  call    cs:__imp_LocalAlloc
0x1800215f1  mov     rcx, [rsi]
0x1800215f4  mov     [rcx+8], rax
0x1800215f8  mov     rax, [rsi]
0x1800215fb  mov     rcx, [rax+8]; void *
0x1800215ff  test    rcx, rcx
0x180021602  jz      short loc_1800215DB
0x180021604  mov     r8d, dword ptr [rsp+78h+uBytes]; Size
0x18002160c  mov     rdx, [rsp+78h+Src]; Src
0x180021614  call    memcpy_0
0x180021619  mov     rcx, [rsi]
0x18002161c  mov     eax, [rsp+78h+arg_10]
0x180021623  mov     [rcx], eax
0x180021625  mov     rcx, [rsi]
0x180021628  mov     eax, dword ptr [rsp+78h+uBytes]
0x18002162f  mov     [rcx+4], eax
0x180021632  xor     ebx, ebx
0x180021634  jmp     short loc_18002163B
0x180021636  mov     ebx, 80070490h
0x18002163b  mov     rcx, [rsp+78h+Src]; hMem
0x180021643  test    rcx, rcx
0x180021646  jz      short loc_18002164E
0x180021648  call    cs:__imp_LocalFree
0x18002164e  test    ebx, ebx
0x180021650  jns     short loc_180021677
0x180021652  test    rsi, rsi
0x180021655  jz      short loc_180021666
0x180021657  mov     rcx, [rsi]; hMem
0x18002165a  call    WinStationFreeUserCertificates
0x18002165f  mov     qword ptr [rsi], 0
0x180021666  mov     ecx, ebx; int
0x180021668  call    ?ConvertHRESULT2WIN32@@YAKJ@Z; ConvertHRESULT2WIN32(long)
0x18002166d  mov     ecx, eax; dwErrCode
0x18002166f  call    cs:__imp_SetLastError
0x180021675  test    ebx, ebx
0x180021677  setns   bl
0x18002167a  lea     rcx, [rsp+78h+var_28]; this
0x18002167f  call    ??1CSmartPublicBinding@@QEAA@XZ; CSmartPublicBinding::~CSmartPublicBinding(void)
0x180021684  mov     al, bl
0x180021686  add     rsp, 68h
0x18002168a  pop     rsi
0x18002168b  pop     rbx
0x18002168c  retn
0x180030873  push    rbp
0x180030875  sub     rsp, 40h
0x180030879  mov     rbp, rdx
0x18003087c  mov     rcx, [rcx]
0x18003087f  mov     ecx, [rcx]; ExceptionCode
0x180030881  call    cs:__imp_I_RpcExceptionFilter
0x180030887  nop
0x180030888  add     rsp, 40h
0x18003088c  pop     rbp
0x18003088d  retn
```
