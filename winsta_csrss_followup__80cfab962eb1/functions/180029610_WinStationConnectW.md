# WinStationConnectW

- ea: `0x180029610`
- end: `0x180029793`
- name: `WinStationConnectW`
- size: `387`
- prototype: `__int64 __fastcall(CPublicBinding *this, unsigned int, unsigned int, unsigned __int16 *, unsigned __int8)`
- caller_count: `0`
- callee_count: `12`
- tags: ``

## callees

- `0x180002014`
- `0x1800041a0`
- `0x180004558`
- `0x180005280`
- `0x180005b40`
- `0x1800065f0`
- `0x1800075a0`
- `0x180020fc0`
- `0x180029610`
- `0x18002e1ec`
- `0x180032be6`
- `0x180032c20`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180029730`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180029730`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800296fa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800296fa`

## string_xrefs

- `0x1800296a2`: `Failed to open binding`
- `0x18002970c`: `Session::Open failed: 0x%x in %s`

## pseudocode

```c
unsigned __int8 __fastcall WinStationConnectW(
        CPublicBinding *this,
        unsigned int a2,
        unsigned int a3,
        unsigned __int16 *a4,
        unsigned __int8 a5)
{
  unsigned __int8 v9; // bl
  void *v10; // rax
  int v11; // ebx
  DWORD v12; // eax
  unsigned __int16 v14[8]; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v15; // [rsp+40h] [rbp-C0h] BYREF
  int v16; // [rsp+48h] [rbp-B8h]
  __int128 v17; // [rsp+50h] [rbp-B0h]
  __int128 v18; // [rsp+60h] [rbp-A0h]
  __int128 v19; // [rsp+70h] [rbp-90h]
  __int64 v20; // [rsp+80h] [rbp-80h]
  _BYTE v21[208]; // [rsp+88h] [rbp-78h] BYREF
  __int64 v22; // [rsp+158h] [rbp+58h]

  v15 = 0;
  v16 = -1;
  v22 = 0;
  v20 = 0;
  v17 = 0;
  v18 = 0;
  v19 = 0;
  memset_0(v21, 0, sizeof(v21));
  CSmartPublicBinding::CSmartPublicBinding((CSmartPublicBinding *)v14, this, 0);
  if ( CSmartPublicBinding::operator void *(v14) )
  {
    v10 = (void *)CSmartPublicBinding::operator void *(v14);
    v11 = CSmartSession::Open((CSmartSession *)&v15, a2, v10);
    if ( v11 == -2147023174 )
    {
      v9 = Legacy_WinStationConnectW(this, a2, a3, a4, a5);
      if ( !v9 )
        GetLastError();
    }
    else
    {
      if ( v11 >= 0 )
      {
        v11 = CSmartSession::Connect((CSmartSession *)&v15, a3, a4);
        if ( v11 >= 0 )
        {
          v9 = 1;
          goto LABEL_12;
        }
        _DbgPrintMessage(8, "Session::Connect failed: 0x%x in %s", (unsigned int)v11, "WinStationConnectW");
      }
      else
      {
        _DbgPrintMessage(8, "Session::Open failed: 0x%x in %s", (unsigned int)v11, "WinStationConnectW");
      }
      v12 = ConvertHRESULT2WIN32(v11);
      SetLastError(v12);
      v9 = 0;
    }
  }
  else
  {
    v9 = 0;
    _DbgPrintMessage(8, "Failed to open binding");
  }
LABEL_12:
  CSmartPublicBinding::~CSmartPublicBinding((CSmartPublicBinding *)v14);
  CSmartSession::~CSmartSession((CSmartSession *)&v15);
  return v9;
}

```

## disassembly

```asm
0x180029610  push    rbp
0x180029612  push    rbx
0x180029613  push    rsi
0x180029614  push    rdi
0x180029615  push    r14
0x180029617  push    r15
0x180029619  lea     rbp, [rsp-78h]
0x18002961e  sub     rsp, 178h
0x180029625  mov     rax, cs:__security_cookie
0x18002962c  xor     rax, rsp
0x18002962f  mov     [rbp+0A0h+var_40], rax
0x180029633  xorps   xmm0, xmm0
0x180029636  mov     [rsp+1A0h+var_160], 0
0x18002963f  mov     edi, r8d
0x180029642  mov     [rsp+1A0h+var_158], 0FFFFFFFFh
0x18002964a  mov     r14d, edx
0x18002964d  mov     [rbp+0A0h+var_48], 0
0x180029655  mov     r15, rcx
0x180029658  xor     eax, eax
0x18002965a  xor     edx, edx; Val
0x18002965c  mov     [rbp+0A0h+var_120], rax
0x180029660  mov     r8d, 0D0h; Size
0x180029666  lea     rcx, [rbp+0A0h+var_118]; void *
0x18002966a  movups  [rsp+1A0h+var_150], xmm0
0x18002966f  mov     rsi, r9
0x180029672  movups  [rsp+1A0h+var_140], xmm0
0x180029677  movups  [rsp+1A0h+var_130], xmm0
0x18002967c  call    memset_0
0x180029681  xor     r8d, r8d; int
0x180029684  lea     rcx, [rsp+1A0h+var_170]; this
0x180029689  mov     rdx, r15; void *
0x18002968c  call    ??0CSmartPublicBinding@@QEAA@PEAXH@Z; CSmartPublicBinding::CSmartPublicBinding(void *,int)
0x180029691  lea     rcx, [rsp+1A0h+var_170]; unsigned __int16 *
0x180029696  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x18002969b  test    rax, rax
0x18002969e  jnz     short loc_1800296B6
0x1800296a0  xor     bl, bl
0x1800296a2  lea     rdx, aFailedToOpenBi_0; "Failed to open binding"
0x1800296a9  lea     ecx, [rax+8]; int
0x1800296ac  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800296b1  jmp     loc_180029760
0x1800296b6  lea     rcx, [rsp+1A0h+var_170]; unsigned __int16 *
0x1800296bb  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x1800296c0  mov     r8, rax; void *
0x1800296c3  lea     rcx, [rsp+1A0h+var_160]; this
0x1800296c8  mov     edx, r14d; unsigned int
0x1800296cb  call    ?Open@CSmartSession@@QEAAJKPEAX@Z; CSmartSession::Open(ulong,void *)
0x1800296d0  mov     ebx, eax
0x1800296d2  cmp     eax, 800706BAh
0x1800296d7  jnz     short loc_180029708
0x1800296d9  mov     al, [rbp+0A0h+arg_20]
0x1800296df  mov     r9, rsi; unsigned __int16 *
0x1800296e2  mov     r8d, edi; unsigned int
0x1800296e5  mov     [rsp+1A0h+var_180], al; unsigned __int8
0x1800296e9  mov     edx, r14d; unsigned int
0x1800296ec  mov     rcx, r15; this
0x1800296ef  call    ?Legacy_WinStationConnectW@@YAEPEAXKKPEAGE@Z; Legacy_WinStationConnectW(void *,ulong,ulong,ushort *,uchar)
0x1800296f4  mov     bl, al
0x1800296f6  test    al, al
0x1800296f8  jnz     short loc_180029760
0x1800296fa  call    cs:__imp_GetLastError
0x180029701  nop     dword ptr [rax+rax+00h]
0x180029706  jmp     short loc_180029760
0x180029708  test    ebx, ebx
0x18002970a  jns     short loc_180029740
0x18002970c  lea     rdx, aSessionOpenFai_0; "Session::Open failed: 0x%x in %s"
0x180029713  mov     r8d, ebx
0x180029716  lea     r9, aWinstationconn_8; "WinStationConnectW"
0x18002971d  mov     ecx, 8; int
0x180029722  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180029727  mov     ecx, ebx; int
0x180029729  call    ?ConvertHRESULT2WIN32@@YAKJ@Z; ConvertHRESULT2WIN32(long)
0x18002972e  mov     ecx, eax; dwErrCode
0x180029730  call    cs:__imp_SetLastError
0x180029737  nop     dword ptr [rax+rax+00h]
0x18002973c  xor     bl, bl
0x18002973e  jmp     short loc_180029760
0x180029740  mov     r8, rsi; unsigned __int16 *
0x180029743  lea     rcx, [rsp+1A0h+var_160]; this
0x180029748  mov     edx, edi; unsigned int
0x18002974a  call    ?Connect@CSmartSession@@QEAAJKPEAG@Z; CSmartSession::Connect(ulong,ushort *)
0x18002974f  mov     ebx, eax
0x180029751  test    eax, eax
0x180029753  jns     short loc_18002975E
0x180029755  lea     rdx, aSessionConnect; "Session::Connect failed: 0x%x in %s"
0x18002975c  jmp     short loc_180029713
0x18002975e  mov     bl, 1
0x180029760  lea     rcx, [rsp+1A0h+var_170]; this
0x180029765  call    ??1CSmartPublicBinding@@QEAA@XZ; CSmartPublicBinding::~CSmartPublicBinding(void)
0x18002976a  lea     rcx, [rsp+1A0h+var_160]; this
0x18002976f  call    ??1CSmartSession@@QEAA@XZ; CSmartSession::~CSmartSession(void)
0x180029774  mov     al, bl
0x180029776  mov     rcx, [rbp+0A0h+var_40]
0x18002977a  xor     rcx, rsp; StackCookie
0x18002977d  call    __security_check_cookie
0x180029782  add     rsp, 178h
0x180029789  pop     r15
0x18002978b  pop     r14
0x18002978d  pop     rdi
0x18002978e  pop     rsi
0x18002978f  pop     rbx
0x180029790  pop     rbp
0x180029791  retn
```
