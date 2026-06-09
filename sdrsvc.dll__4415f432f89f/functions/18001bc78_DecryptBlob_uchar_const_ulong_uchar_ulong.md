# DecryptBlob(uchar const *,ulong,uchar * *,ulong *)

- ea: `0x18001bc78`
- end: `0x18001be34`
- name: `?DecryptBlob@@YAJPEBEKPEAPEAEPEAK@Z`
- size: `444`
- prototype: `__int64 __fastcall(BYTE *, DWORD, unsigned __int8 **, unsigned int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001aeb4`

## callees

- `0x18001586c`
- `0x180015974`
- `0x18001bc78`
- `0x18001c58c`
- `0x1800216f2`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001bdca`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001bdf9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001bdca`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001bdf9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001bd80`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001bd80`
- `CRYPT32!CryptUnprotectData` at `0x18001bd54`
- `CRYPT32!CryptUnprotectData` at `0x18001bd54`

## pseudocode

```c
__int64 __fastcall DecryptBlob(BYTE *a1, DWORD a2, unsigned __int8 **a3, unsigned int *a4)
{
  __int16 v8; // ax
  __int64 v9; // rcx
  void *v10; // rsi
  DWORD cbData; // ebx
  BYTE *pbData; // rcx
  __int64 v13; // rax
  unsigned int v14; // ebx
  DATA_BLOB pDataOut; // [rsp+40h] [rbp-19h] BYREF
  DATA_BLOB pDataIn; // [rsp+50h] [rbp-9h] BYREF
  int LastFailureAsHRESULT; // [rsp+60h] [rbp+7h] BYREF
  __int16 v19; // [rsp+64h] [rbp+Bh]
  __int16 v20; // [rsp+66h] [rbp+Dh]
  LPWSTR ppszDataDescr; // [rsp+C0h] [rbp+67h] BYREF

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&LastFailureAsHRESULT, "DecryptBlob", 95, 1);
  ppszDataDescr = 0;
  pDataIn = 0;
  pDataOut = 0;
  if ( a3 )
    *a3 = 0;
  if ( a4 )
    *a4 = 0;
  v8 = 106;
  if ( !a1 || (v19 = 106, v8 = 107, !a3) || (v19 = 107, v8 = 108, !a4) )
  {
    LastFailureAsHRESULT = -2147024809;
LABEL_7:
    v20 = v8;
    goto LABEL_15;
  }
  v19 = 108;
  LastFailureAsHRESULT = 0;
  pDataIn.pbData = a1;
  pDataIn.cbData = a2;
  if ( !CryptUnprotectData(&pDataIn, &ppszDataDescr, 0, 0, 0, 1u, &pDataOut) )
  {
    LastFailureAsHRESULT = GetLastFailureAsHRESULT(v9);
    v8 = 117;
    goto LABEL_7;
  }
  v19 = 117;
  LastFailureAsHRESULT = 0;
  v10 = CoTaskMemAlloc(pDataOut.cbData);
  v8 = 120;
  if ( !v10 )
  {
    LastFailureAsHRESULT = -2147024882;
    goto LABEL_7;
  }
  cbData = pDataOut.cbData;
  LastFailureAsHRESULT = 0;
  v19 = 120;
  memcpy_0(v10, pDataOut.pbData, pDataOut.cbData);
  *a3 = (unsigned __int8 *)v10;
  *a4 = cbData;
LABEL_15:
  if ( ppszDataDescr )
  {
    LocalFree(ppszDataDescr);
    ppszDataDescr = 0;
  }
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
0x18001bc78  mov     [rsp-8+arg_8], rbx
0x18001bc7d  mov     [rsp-8+arg_10], rsi
0x18001bc82  push    rbp
0x18001bc83  push    rdi
0x18001bc84  push    r14
0x18001bc86  lea     rbp, [rsp-47h]
0x18001bc8b  sub     rsp, 0A0h
0x18001bc92  mov     rdi, r9
0x18001bc95  mov     r14, r8
0x18001bc98  mov     r9d, 1; unsigned __int16
0x18001bc9e  mov     esi, edx
0x18001bca0  mov     rbx, rcx
0x18001bca3  lea     rdx, aDecryptblob; "DecryptBlob"
0x18001bcaa  lea     rcx, [rbp+57h+var_50]; this
0x18001bcae  lea     r8d, [r9+5Eh]; unsigned __int16
0x18001bcb2  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18001bcb7  mov     [rbp+57h+ppszDataDescr], 0
0x18001bcbf  xorps   xmm0, xmm0
0x18001bcc2  xorps   xmm1, xmm1
0x18001bcc5  movups  xmmword ptr [rbp+57h+pDataIn.cbData], xmm0
0x18001bcc9  movups  xmmword ptr [rbp+57h+var_70.cbData], xmm1
0x18001bccd  test    r14, r14
0x18001bcd0  jz      short loc_18001BCD9
0x18001bcd2  mov     qword ptr [r14], 0
0x18001bcd9  test    rdi, rdi
0x18001bcdc  jz      short loc_18001BCE4
0x18001bcde  mov     dword ptr [rdi], 0
0x18001bce4  mov     eax, 6Ah ; 'j'
0x18001bce9  test    rbx, rbx
0x18001bcec  jnz     short loc_18001BCFE
0x18001bcee  mov     [rbp+57h+var_50], 80070057h
0x18001bcf5  mov     [rbp+57h+var_4A], ax
0x18001bcf9  jmp     loc_18001BDC1
0x18001bcfe  mov     [rbp+57h+var_4C], ax
0x18001bd02  mov     eax, 6Bh ; 'k'
0x18001bd07  test    r14, r14
0x18001bd0a  jz      short loc_18001BCEE
0x18001bd0c  mov     [rbp+57h+var_4C], ax
0x18001bd10  mov     eax, 6Ch ; 'l'
0x18001bd15  test    rdi, rdi
0x18001bd18  jz      short loc_18001BCEE
0x18001bd1a  mov     [rbp+57h+var_4C], ax
0x18001bd1e  lea     rdx, [rbp+57h+ppszDataDescr]; ppszDataDescr
0x18001bd22  lea     rax, [rbp+57h+var_70]
0x18001bd26  mov     [rbp+57h+var_50], 0
0x18001bd2d  mov     [rsp+0B0h+pDataOut], rax; pDataOut
0x18001bd32  lea     rcx, [rbp+57h+pDataIn]; pDataIn
0x18001bd36  mov     [rsp+0B0h+dwFlags], 1; dwFlags
0x18001bd3e  xor     r9d, r9d; pvReserved
0x18001bd41  xor     r8d, r8d; pOptionalEntropy
0x18001bd44  mov     [rsp+0B0h+pPromptStruct], 0; pPromptStruct
0x18001bd4d  mov     [rbp+57h+pDataIn.pbData], rbx
0x18001bd51  mov     [rbp+57h+pDataIn.cbData], esi
0x18001bd54  call    cs:__imp_CryptUnprotectData
0x18001bd5a  test    eax, eax
0x18001bd5c  jnz     short loc_18001BD6D
0x18001bd5e  call    GetLastFailureAsHRESULT
0x18001bd63  mov     [rbp+57h+var_50], eax
0x18001bd66  mov     eax, 75h ; 'u'
0x18001bd6b  jmp     short loc_18001BCF5
0x18001bd6d  mov     ecx, [rbp+57h+var_70.cbData]; cb
0x18001bd70  mov     eax, 75h ; 'u'
0x18001bd75  mov     [rbp+57h+var_4C], ax
0x18001bd79  mov     [rbp+57h+var_50], 0
0x18001bd80  call    cs:__imp_CoTaskMemAlloc
0x18001bd86  mov     rsi, rax
0x18001bd89  test    rax, rax
0x18001bd8c  mov     eax, 78h ; 'x'
0x18001bd91  jnz     short loc_18001BD9F
0x18001bd93  mov     [rbp+57h+var_50], 8007000Eh
0x18001bd9a  jmp     loc_18001BCF5
0x18001bd9f  mov     ebx, [rbp+57h+var_70.cbData]
0x18001bda2  mov     rcx, rsi; void *
0x18001bda5  mov     rdx, [rbp+57h+var_70.pbData]; Src
0x18001bda9  mov     r8d, ebx; Size
0x18001bdac  mov     [rbp+57h+var_50], 0
0x18001bdb3  mov     [rbp+57h+var_4C], ax
0x18001bdb7  call    memcpy_0
0x18001bdbc  mov     [r14], rsi
0x18001bdbf  mov     [rdi], ebx
0x18001bdc1  mov     rcx, [rbp+57h+ppszDataDescr]; hMem
0x18001bdc5  test    rcx, rcx
0x18001bdc8  jz      short loc_18001BDD8
0x18001bdca  call    cs:__imp_LocalFree
0x18001bdd0  mov     [rbp+57h+ppszDataDescr], 0
0x18001bdd8  mov     rcx, [rbp+57h+var_70.pbData]
0x18001bddc  test    rcx, rcx
0x18001bddf  jz      short loc_18001BE0E
0x18001bde1  mov     eax, [rbp+57h+var_70.cbData]
0x18001bde4  test    rax, rax
0x18001bde7  jz      short loc_18001BDF9
0x18001bde9  mov     byte ptr [rcx], 0
0x18001bdec  inc     rcx
0x18001bdef  sub     rax, 1
0x18001bdf3  jnz     short loc_18001BDE9
0x18001bdf5  mov     rcx, [rbp+57h+var_70.pbData]; hMem
0x18001bdf9  call    cs:__imp_LocalFree
0x18001bdff  mov     [rbp+57h+var_70.pbData], 0
0x18001be07  mov     [rbp+57h+var_70.cbData], 0
0x18001be0e  mov     ebx, [rbp+57h+var_50]
0x18001be11  lea     rcx, [rbp+57h+var_50]; this
0x18001be15  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18001be1a  lea     r11, [rsp+0B0h+var_10]
0x18001be22  mov     eax, ebx
0x18001be24  mov     rbx, [r11+28h]
0x18001be28  mov     rsi, [r11+30h]
0x18001be2c  mov     rsp, r11
0x18001be2f  pop     r14
0x18001be31  pop     rdi
0x18001be32  pop     rbp
0x18001be33  retn
```
