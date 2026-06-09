# WinStationConnectW

- ea: `0x180027b30`
- end: `0x180027ca6`
- name: `WinStationConnectW`
- size: `374`
- prototype: `__int64 __fastcall(CPublicBinding *this, unsigned int, unsigned int, unsigned __int16 *, unsigned __int8)`
- caller_count: `0`
- callee_count: `12`
- tags: ``

## callees

- `0x1800039e8`
- `0x180005c30`
- `0x180005fcc`
- `0x180007030`
- `0x180007890`
- `0x180008290`
- `0x180008e30`
- `0x18001f8e8`
- `0x180027b30`
- `0x18002bf90`
- `0x18002fe06`
- `0x18002fe40`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180027c4a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180027c4a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027c1a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027c1a`

## string_xrefs

- `0x180027bc2`: `Failed to open binding`
- `0x180027c26`: `Session::Open failed: 0x%x in %s`

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
0x180027b30  push    rbp
0x180027b32  push    rbx
0x180027b33  push    rsi
0x180027b34  push    rdi
0x180027b35  push    r14
0x180027b37  push    r15
0x180027b39  lea     rbp, [rsp-78h]
0x180027b3e  sub     rsp, 178h
0x180027b45  mov     rax, cs:__security_cookie
0x180027b4c  xor     rax, rsp
0x180027b4f  mov     [rbp+0A0h+var_40], rax
0x180027b53  xorps   xmm0, xmm0
0x180027b56  mov     [rsp+1A0h+var_160], 0
0x180027b5f  mov     edi, r8d
0x180027b62  mov     [rsp+1A0h+var_158], 0FFFFFFFFh
0x180027b6a  mov     r14d, edx
0x180027b6d  mov     [rbp+0A0h+var_48], 0
0x180027b75  mov     r15, rcx
0x180027b78  xor     eax, eax
0x180027b7a  xor     edx, edx; Val
0x180027b7c  mov     [rbp+0A0h+var_120], rax
0x180027b80  mov     r8d, 0D0h; Size
0x180027b86  lea     rcx, [rbp+0A0h+var_118]; void *
0x180027b8a  movups  [rsp+1A0h+var_150], xmm0
0x180027b8f  mov     rsi, r9
0x180027b92  movups  [rsp+1A0h+var_140], xmm0
0x180027b97  movups  [rsp+1A0h+var_130], xmm0
0x180027b9c  call    memset_0
0x180027ba1  xor     r8d, r8d; int
0x180027ba4  lea     rcx, [rsp+1A0h+var_170]; this
0x180027ba9  mov     rdx, r15; void *
0x180027bac  call    ??0CSmartPublicBinding@@QEAA@PEAXH@Z; CSmartPublicBinding::CSmartPublicBinding(void *,int)
0x180027bb1  lea     rcx, [rsp+1A0h+var_170]; unsigned __int16 *
0x180027bb6  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x180027bbb  test    rax, rax
0x180027bbe  jnz     short loc_180027BD6
0x180027bc0  xor     bl, bl
0x180027bc2  lea     rdx, aFailedToOpenBi_0; "Failed to open binding"
0x180027bc9  lea     ecx, [rax+8]; int
0x180027bcc  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180027bd1  jmp     loc_180027C74
0x180027bd6  lea     rcx, [rsp+1A0h+var_170]; unsigned __int16 *
0x180027bdb  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x180027be0  mov     r8, rax; void *
0x180027be3  lea     rcx, [rsp+1A0h+var_160]; this
0x180027be8  mov     edx, r14d; unsigned int
0x180027beb  call    ?Open@CSmartSession@@QEAAJKPEAX@Z; CSmartSession::Open(ulong,void *)
0x180027bf0  mov     ebx, eax
0x180027bf2  cmp     eax, 800706BAh
0x180027bf7  jnz     short loc_180027C22
0x180027bf9  mov     al, [rbp+0A0h+arg_20]
0x180027bff  mov     r9, rsi; unsigned __int16 *
0x180027c02  mov     r8d, edi; unsigned int
0x180027c05  mov     [rsp+1A0h+var_180], al; unsigned __int8
0x180027c09  mov     edx, r14d; unsigned int
0x180027c0c  mov     rcx, r15; this
0x180027c0f  call    ?Legacy_WinStationConnectW@@YAEPEAXKKPEAGE@Z; Legacy_WinStationConnectW(void *,ulong,ulong,ushort *,uchar)
0x180027c14  mov     bl, al
0x180027c16  test    al, al
0x180027c18  jnz     short loc_180027C74
0x180027c1a  call    cs:__imp_GetLastError
0x180027c20  jmp     short loc_180027C74
0x180027c22  test    ebx, ebx
0x180027c24  jns     short loc_180027C54
0x180027c26  lea     rdx, aSessionOpenFai_0; "Session::Open failed: 0x%x in %s"
0x180027c2d  mov     r8d, ebx
0x180027c30  lea     r9, aWinstationconn_8; "WinStationConnectW"
0x180027c37  mov     ecx, 8; int
0x180027c3c  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180027c41  mov     ecx, ebx; int
0x180027c43  call    ?ConvertHRESULT2WIN32@@YAKJ@Z; ConvertHRESULT2WIN32(long)
0x180027c48  mov     ecx, eax; dwErrCode
0x180027c4a  call    cs:__imp_SetLastError
0x180027c50  xor     bl, bl
0x180027c52  jmp     short loc_180027C74
0x180027c54  mov     r8, rsi; unsigned __int16 *
0x180027c57  lea     rcx, [rsp+1A0h+var_160]; this
0x180027c5c  mov     edx, edi; unsigned int
0x180027c5e  call    ?Connect@CSmartSession@@QEAAJKPEAG@Z; CSmartSession::Connect(ulong,ushort *)
0x180027c63  mov     ebx, eax
0x180027c65  test    eax, eax
0x180027c67  jns     short loc_180027C72
0x180027c69  lea     rdx, aSessionConnect; "Session::Connect failed: 0x%x in %s"
0x180027c70  jmp     short loc_180027C2D
0x180027c72  mov     bl, 1
0x180027c74  lea     rcx, [rsp+1A0h+var_170]; this
0x180027c79  call    ??1CSmartPublicBinding@@QEAA@XZ; CSmartPublicBinding::~CSmartPublicBinding(void)
0x180027c7e  lea     rcx, [rsp+1A0h+var_160]; this
0x180027c83  call    ??1CSmartSession@@QEAA@XZ; CSmartSession::~CSmartSession(void)
0x180027c88  mov     al, bl
0x180027c8a  mov     rcx, [rbp+0A0h+var_40]
0x180027c8e  xor     rcx, rsp; StackCookie
0x180027c91  call    __security_check_cookie
0x180027c96  add     rsp, 178h
0x180027c9d  pop     r15
0x180027c9f  pop     r14
0x180027ca1  pop     rdi
0x180027ca2  pop     rsi
0x180027ca3  pop     rbx
0x180027ca4  pop     rbp
0x180027ca5  retn
```
