# EncryptBlob(uchar const *,ulong,uchar * *,ulong *)

- ea: `0x18001be3c`
- end: `0x18001bfc6`
- name: `?EncryptBlob@@YAJPEBEKPEAPEAEPEAK@Z`
- size: `394`
- prototype: `__int64 __fastcall(BYTE *, DWORD, unsigned __int8 **, unsigned int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001b640`

## callees

- `0x18001586c`
- `0x180015974`
- `0x18001be3c`
- `0x18001c58c`
- `0x1800216f2`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001bf95`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001bf95`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001bf33`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001bf33`
- `CRYPT32!CryptProtectData` at `0x18001bf07`
- `CRYPT32!CryptProtectData` at `0x18001bf07`

## pseudocode

```c
__int64 __fastcall EncryptBlob(BYTE *a1, DWORD a2, unsigned __int8 **a3, unsigned int *a4)
{
  __int16 v8; // ax
  __int64 v9; // rcx
  void *v10; // rsi
  DWORD cbData; // ebx
  BYTE *pbData; // rcx
  __int64 v13; // rax
  unsigned int v14; // ebx
  DATA_BLOB pDataOut; // [rsp+40h] [rbp-29h] BYREF
  DATA_BLOB pDataIn; // [rsp+50h] [rbp-19h] BYREF
  int LastFailureAsHRESULT; // [rsp+60h] [rbp-9h] BYREF
  __int16 v19; // [rsp+64h] [rbp-5h]
  __int16 v20; // [rsp+66h] [rbp-3h]

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&LastFailureAsHRESULT, "EncryptBlob", 36, 1);
  pDataIn = 0;
  pDataOut = 0;
  if ( a3 )
    *a3 = 0;
  if ( a4 )
    *a4 = 0;
  v8 = 46;
  if ( !a1 || (v19 = 46, v8 = 47, !a3) || (v19 = 47, v8 = 48, !a4) )
  {
    LastFailureAsHRESULT = -2147024809;
LABEL_7:
    v20 = v8;
    goto LABEL_15;
  }
  v19 = 48;
  LastFailureAsHRESULT = 0;
  pDataIn.pbData = a1;
  pDataIn.cbData = a2;
  if ( !CryptProtectData(&pDataIn, 0, 0, 0, 0, 0x11u, &pDataOut) )
  {
    LastFailureAsHRESULT = GetLastFailureAsHRESULT(v9);
    v8 = 53;
    goto LABEL_7;
  }
  v19 = 53;
  LastFailureAsHRESULT = 0;
  v10 = CoTaskMemAlloc(pDataOut.cbData);
  v8 = 56;
  if ( !v10 )
  {
    LastFailureAsHRESULT = -2147024882;
    goto LABEL_7;
  }
  cbData = pDataOut.cbData;
  LastFailureAsHRESULT = 0;
  v19 = 56;
  memcpy_0(v10, pDataOut.pbData, pDataOut.cbData);
  *a3 = (unsigned __int8 *)v10;
  *a4 = cbData;
LABEL_15:
  pbData = pDataOut.pbData;
  if ( pDataOut.pbData )
  {
    v13 = pDataOut.cbData;
    if ( pDataOut.cbData )
    {
      do
      {
        *pbData++ = 0;
        --v13;
      }
      while ( v13 );
      pbData = pDataOut.pbData;
    }
    LocalFree(pbData);
    pDataOut.pbData = 0;
    pDataOut.cbData = 0;
  }
  v14 = LastFailureAsHRESULT;
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&LastFailureAsHRESULT);
  return v14;
}

```

## disassembly

```asm
0x18001be3c  push    rbp
0x18001be3e  push    rbx
0x18001be3f  push    rsi
0x18001be40  push    rdi
0x18001be41  push    r14
0x18001be43  lea     rbp, [rsp-37h]
0x18001be48  sub     rsp, 0A0h
0x18001be4f  mov     rdi, r9
0x18001be52  mov     r14, r8
0x18001be55  mov     r9d, 1; unsigned __int16
0x18001be5b  mov     esi, edx
0x18001be5d  mov     rbx, rcx
0x18001be60  lea     rdx, aEncryptblob; "EncryptBlob"
0x18001be67  lea     rcx, [rbp+57h+var_60]; this
0x18001be6b  lea     r8d, [r9+23h]; unsigned __int16
0x18001be6f  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18001be74  xorps   xmm0, xmm0
0x18001be77  xorps   xmm1, xmm1
0x18001be7a  movups  xmmword ptr [rbp+57h+pDataIn.cbData], xmm0
0x18001be7e  movups  xmmword ptr [rbp+57h+var_80.cbData], xmm1
0x18001be82  test    r14, r14
0x18001be85  jz      short loc_18001BE8E
0x18001be87  mov     qword ptr [r14], 0
0x18001be8e  test    rdi, rdi
0x18001be91  jz      short loc_18001BE99
0x18001be93  mov     dword ptr [rdi], 0
0x18001be99  mov     eax, 2Eh ; '.'
0x18001be9e  test    rbx, rbx
0x18001bea1  jnz     short loc_18001BEB3
0x18001bea3  mov     [rbp+57h+var_60], 80070057h
0x18001beaa  mov     [rbp+57h+var_5A], ax
0x18001beae  jmp     loc_18001BF74
0x18001beb3  mov     [rbp+57h+var_5C], ax
0x18001beb7  mov     eax, 2Fh ; '/'
0x18001bebc  test    r14, r14
0x18001bebf  jz      short loc_18001BEA3
0x18001bec1  mov     [rbp+57h+var_5C], ax
0x18001bec5  mov     eax, 30h ; '0'
0x18001beca  test    rdi, rdi
0x18001becd  jz      short loc_18001BEA3
0x18001becf  mov     [rbp+57h+var_5C], ax
0x18001bed3  lea     rcx, [rbp+57h+pDataIn]; pDataIn
0x18001bed7  lea     rax, [rbp+57h+var_80]
0x18001bedb  mov     [rbp+57h+var_60], 0
0x18001bee2  mov     [rsp+0C0h+pDataOut], rax; pDataOut
0x18001bee7  xor     r9d, r9d; pvReserved
0x18001beea  mov     [rsp+0C0h+dwFlags], 11h; dwFlags
0x18001bef2  xor     r8d, r8d; pOptionalEntropy
0x18001bef5  xor     edx, edx; szDataDescr
0x18001bef7  mov     [rsp+0C0h+pPromptStruct], 0; pPromptStruct
0x18001bf00  mov     [rbp+57h+pDataIn.pbData], rbx
0x18001bf04  mov     [rbp+57h+pDataIn.cbData], esi
0x18001bf07  call    cs:__imp_CryptProtectData
0x18001bf0d  test    eax, eax
0x18001bf0f  jnz     short loc_18001BF20
0x18001bf11  call    GetLastFailureAsHRESULT
0x18001bf16  mov     [rbp+57h+var_60], eax
0x18001bf19  mov     eax, 35h ; '5'
0x18001bf1e  jmp     short loc_18001BEAA
0x18001bf20  mov     ecx, [rbp+57h+var_80.cbData]; cb
0x18001bf23  mov     eax, 35h ; '5'
0x18001bf28  mov     [rbp+57h+var_5C], ax
0x18001bf2c  mov     [rbp+57h+var_60], 0
0x18001bf33  call    cs:__imp_CoTaskMemAlloc
0x18001bf39  mov     rsi, rax
0x18001bf3c  test    rax, rax
0x18001bf3f  mov     eax, 38h ; '8'
0x18001bf44  jnz     short loc_18001BF52
0x18001bf46  mov     [rbp+57h+var_60], 8007000Eh
0x18001bf4d  jmp     loc_18001BEAA
0x18001bf52  mov     ebx, [rbp+57h+var_80.cbData]
0x18001bf55  mov     rcx, rsi; void *
0x18001bf58  mov     rdx, [rbp+57h+var_80.pbData]; Src
0x18001bf5c  mov     r8d, ebx; Size
0x18001bf5f  mov     [rbp+57h+var_60], 0
0x18001bf66  mov     [rbp+57h+var_5C], ax
0x18001bf6a  call    memcpy_0
0x18001bf6f  mov     [r14], rsi
0x18001bf72  mov     [rdi], ebx
0x18001bf74  mov     rcx, [rbp+57h+var_80.pbData]
0x18001bf78  test    rcx, rcx
0x18001bf7b  jz      short loc_18001BFAA
0x18001bf7d  mov     eax, [rbp+57h+var_80.cbData]
0x18001bf80  test    rax, rax
0x18001bf83  jz      short loc_18001BF95
0x18001bf85  mov     byte ptr [rcx], 0
0x18001bf88  inc     rcx
0x18001bf8b  sub     rax, 1
0x18001bf8f  jnz     short loc_18001BF85
0x18001bf91  mov     rcx, [rbp+57h+var_80.pbData]; hMem
0x18001bf95  call    cs:__imp_LocalFree
0x18001bf9b  mov     [rbp+57h+var_80.pbData], 0
0x18001bfa3  mov     [rbp+57h+var_80.cbData], 0
0x18001bfaa  mov     ebx, [rbp+57h+var_60]
0x18001bfad  lea     rcx, [rbp+57h+var_60]; this
0x18001bfb1  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18001bfb6  mov     eax, ebx
0x18001bfb8  add     rsp, 0A0h
0x18001bfbf  pop     r14
0x18001bfc1  pop     rdi
0x18001bfc2  pop     rsi
0x18001bfc3  pop     rbx
0x18001bfc4  pop     rbp
0x18001bfc5  retn
```
