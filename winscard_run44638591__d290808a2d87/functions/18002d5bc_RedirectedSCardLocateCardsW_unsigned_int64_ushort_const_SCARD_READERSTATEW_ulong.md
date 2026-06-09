# RedirectedSCardLocateCardsW(unsigned __int64,ushort const *,SCARD_READERSTATEW *,ulong)

- ea: `0x18002d5bc`
- end: `0x18002d8b2`
- name: `?RedirectedSCardLocateCardsW@@YAJ_KPEBGPEAUSCARD_READERSTATEW@@K@Z`
- size: `758`
- prototype: `int(unsigned __int64, const unsigned __int16 *, struct SCARD_READERSTATEW *, unsigned int)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180028300`

## callees

- `0x180007bc0`
- `0x18000f270`
- `0x18000ff10`
- `0x1800127cc`
- `0x180016ca4`
- `0x18001991c`
- `0x180019a14`
- `0x18002d5bc`
- `0x18002e234`
- `0x18002e29c`

## import_xrefs

- `RPCRT4!NdrMesTypeDecode3` at `0x18002d780`
- `RPCRT4!NdrMesTypeDecode3` at `0x18002d780`
- `RPCRT4!NdrMesTypeEncode3` at `0x18002d6d5`
- `RPCRT4!NdrMesTypeEncode3` at `0x18002d6d5`
- `RPCRT4!NdrMesTypeFree3` at `0x18002d7d5`
- `RPCRT4!NdrMesTypeFree3` at `0x18002d7d5`
- `RPCRT4!MesEncodeDynBufferHandleCreate` at `0x18002d643`
- `RPCRT4!MesEncodeDynBufferHandleCreate` at `0x18002d643`
- `RPCRT4!MesDecodeBufferHandleCreate` at `0x18002d73d`
- `RPCRT4!MesDecodeBufferHandleCreate` at `0x18002d73d`

## pseudocode

```c
__int64 __fastcall RedirectedSCardLocateCardsW(
        __int64 a1,
        const unsigned __int16 *a2,
        struct SCARD_READERSTATEW *a3,
        unsigned int a4)
{
  unsigned int SCardError; // ebx
  int v10; // eax
  handle_t pHandle; // [rsp+40h] [rbp-98h] BYREF
  int v12; // [rsp+48h] [rbp-90h]
  char *pBuffer; // [rsp+50h] [rbp-88h] BYREF
  struct _ReaderStateW *v14; // [rsp+58h] [rbp-80h] BYREF
  struct _BUFFER_LIST_STRUCT *v15; // [rsp+60h] [rbp-78h] BYREF
  struct _ReaderState_Return *v16[2]; // [rsp+68h] [rbp-70h] BYREF
  __int128 pObject; // [rsp+78h] [rbp-60h] BYREF
  __int128 v18; // [rsp+88h] [rbp-50h]
  __int128 v19; // [rsp+98h] [rbp-40h]
  unsigned int pEncodedSize; // [rsp+E0h] [rbp+8h] BYREF

  pBuffer = 0;
  pEncodedSize = 0;
  pHandle = 0;
  pObject = 0;
  v18 = 0;
  v19 = 0;
  *(_OWORD *)v16 = 0;
  v14 = 0;
  v15 = 0;
  if ( !a1 )
    return 2148532228LL;
  if ( !a2 )
    return 2148532241LL;
  if ( !MesEncodeDynBufferHandleCreate(&pBuffer, &pEncodedSize, &pHandle) )
  {
    pObject = *(_OWORD *)(a1 + 8);
    LODWORD(v18) = _CalculateNumBytesInMultiStringW(a2);
    *((_QWORD *)&v18 + 1) = a2;
    LODWORD(v19) = a4;
    if ( (unsigned int)_AllocAndCopyReaderStateWStructsForCall(a4, &v14, a3) )
    {
      SCardError = -2146435066;
      goto LABEL_16;
    }
    *((_QWORD *)&v19 + 1) = v14;
    NdrMesTypeEncode3(pHandle, &pPicklingInfo, &pProxyInfo, (const unsigned int **)&ArrTypeOffset, 0xDu, &pObject);
    v10 = _SendSCardIOCTL(0x9009Cu, pBuffer, pEncodedSize, &v15, *(LPCRITICAL_SECTION *)a1, 0xFFFFFFFF, 0x800u);
    if ( v10 )
    {
      SCardError = _MakeSCardError(v10);
      goto LABEL_16;
    }
    SafeMesHandleFree(&pHandle);
    if ( !MesDecodeBufferHandleCreate(*((char **)v15 + 2), *((_DWORD *)v15 + 7), &pHandle) )
    {
      *(_OWORD *)v16 = 0;
      NdrMesTypeDecode3(pHandle, &pPicklingInfo, &pProxyInfo, (const unsigned int **)&ArrTypeOffset, 0x10u, v16);
      SCardError = (unsigned int)v16[0];
      v12 = (int)v16[0];
      if ( LODWORD(v16[0]) )
      {
LABEL_15:
        NdrMesTypeFree3(pHandle, &pPicklingInfo, &pProxyInfo, (const unsigned int **)&ArrTypeOffset, 0x10u, v16);
        goto LABEL_16;
      }
      if ( a4 == HIDWORD(v16[0]) )
      {
        _CopyReaderStateWStructsForReturn(a4, a3, v16[1]);
        goto LABEL_15;
      }
    }
  }
  SCardError = -2146435041;
LABEL_16:
  SafeMesHandleFree(&pHandle);
  MIDL_user_free(pBuffer);
  MIDL_user_free(v14);
  if ( v15 )
    *((_DWORD *)v15 + 2) = 0;
  return SCardError;
}

```

## disassembly

```asm
0x18002d5bc  mov     rax, rsp
0x18002d5bf  push    rbx
0x18002d5c0  push    rsi
0x18002d5c1  push    rdi
0x18002d5c2  push    r14
0x18002d5c4  sub     rsp, 0B8h
0x18002d5cb  mov     edi, r9d
0x18002d5ce  mov     r14, r8
0x18002d5d1  mov     rbx, rdx
0x18002d5d4  mov     rsi, rcx
0x18002d5d7  mov     [rsp+0D8h+pBuffer], 0
0x18002d5e0  mov     dword ptr [rax+8], 0
0x18002d5e7  mov     [rsp+0D8h+pHandle], 0
0x18002d5f0  xorps   xmm0, xmm0
0x18002d5f3  movups  xmmword ptr [rax-60h], xmm0
0x18002d5f7  movups  xmmword ptr [rax-50h], xmm0
0x18002d5fb  movups  xmmword ptr [rax-40h], xmm0
0x18002d5ff  movups  xmmword ptr [rax-70h], xmm0
0x18002d603  mov     qword ptr [rax-80h], 0
0x18002d60b  mov     qword ptr [rax-78h], 0
0x18002d613  test    rcx, rcx
0x18002d616  jnz     short loc_18002D622
0x18002d618  mov     eax, 80100004h
0x18002d61d  jmp     loc_18002D8A5
0x18002d622  test    rbx, rbx
0x18002d625  jnz     short loc_18002D631
0x18002d627  mov     eax, 80100011h
0x18002d62c  jmp     loc_18002D8A5
0x18002d631  lea     r8, [rsp+0D8h+pHandle]; pHandle
0x18002d636  lea     rdx, [rsp+0D8h+pEncodedSize]; pEncodedSize
0x18002d63e  lea     rcx, [rsp+0D8h+pBuffer]; pBuffer
0x18002d643  call    cs:__imp_MesEncodeDynBufferHandleCreate
0x18002d649  test    eax, eax
0x18002d64b  jz      short loc_18002D657
0x18002d64d  mov     ebx, 8010001Fh
0x18002d652  jmp     loc_18002D874
0x18002d657  movups  xmm0, xmmword ptr [rsi+8]
0x18002d65b  movdqu  [rsp+0D8h+var_60], xmm0
0x18002d661  mov     rcx, rbx; unsigned __int16 *
0x18002d664  call    ?_CalculateNumBytesInMultiStringW@@YAKPEBG@Z; _CalculateNumBytesInMultiStringW(ushort const *)
0x18002d669  mov     [rsp+0D8h+var_50], eax
0x18002d670  mov     [rsp+0D8h+var_48], rbx
0x18002d678  mov     [rsp+0D8h+var_40], edi
0x18002d67f  mov     r8, r14; struct SCARD_READERSTATEW *
0x18002d682  lea     rdx, [rsp+0D8h+var_80]; struct _ReaderStateW **
0x18002d687  mov     ecx, edi; unsigned int
0x18002d689  call    ?_AllocAndCopyReaderStateWStructsForCall@@YAJKPEAPEAU_ReaderStateW@@PEAUSCARD_READERSTATEW@@@Z; _AllocAndCopyReaderStateWStructsForCall(ulong,_ReaderStateW * *,SCARD_READERSTATEW *)
0x18002d68e  test    eax, eax
0x18002d690  jz      short loc_18002D69C
0x18002d692  mov     ebx, 80100006h
0x18002d697  jmp     loc_18002D874
0x18002d69c  mov     rax, [rsp+0D8h+var_80]
0x18002d6a1  mov     [rsp+0D8h+var_38], rax
0x18002d6a9  lea     rax, [rsp+0D8h+var_60]
0x18002d6ae  mov     [rsp+0D8h+pObject], rax; pObject
0x18002d6b3  mov     [rsp+0D8h+nTypeIndex], 0Dh; nTypeIndex
0x18002d6bb  lea     r9, ArrTypeOffset; ArrTypeOffset
0x18002d6c2  lea     r8, pProxyInfo; pProxyInfo
0x18002d6c9  lea     rdx, pPicklingInfo; pPicklingInfo
0x18002d6d0  mov     rcx, [rsp+0D8h+pHandle]; Handle
0x18002d6d5  call    cs:__imp_NdrMesTypeEncode3
0x18002d6db  nop
0x18002d6dc  mov     [rsp+0D8h+var_A8], 800h; unsigned int
0x18002d6e4  mov     dword ptr [rsp+0D8h+pObject], 0FFFFFFFFh; dwMilliseconds
0x18002d6ec  mov     rax, [rsi]
0x18002d6ef  mov     qword ptr [rsp+0D8h+nTypeIndex], rax; lpCriticalSection
0x18002d6f4  lea     r9, [rsp+0D8h+var_78]; struct _BUFFER_LIST_STRUCT **
0x18002d6f9  mov     r8d, [rsp+0D8h+pEncodedSize]; InputBufferLength
0x18002d701  mov     rdx, [rsp+0D8h+pBuffer]; InputBuffer
0x18002d706  mov     ecx, 9009Ch; IoControlCode
0x18002d70b  call    ?_SendSCardIOCTL@@YAJKPEAXKPEAPEAU_BUFFER_LIST_STRUCT@@PEAU_REDIRECTION_CONTEXT@@KK@Z; _SendSCardIOCTL(ulong,void *,ulong,_BUFFER_LIST_STRUCT * *,_REDIRECTION_CONTEXT *,ulong,ulong)
0x18002d710  test    eax, eax
0x18002d712  jz      short loc_18002D722
0x18002d714  mov     ecx, eax; int
0x18002d716  call    ?_MakeSCardError@@YAJJ@Z; _MakeSCardError(long)
0x18002d71b  mov     ebx, eax
0x18002d71d  jmp     loc_18002D874
0x18002d722  lea     rcx, [rsp+0D8h+pHandle]; void **
0x18002d727  call    ?SafeMesHandleFree@@YAXPEAPEAX@Z; SafeMesHandleFree(void * *)
0x18002d72c  lea     r8, [rsp+0D8h+pHandle]; pHandle
0x18002d731  mov     rcx, [rsp+0D8h+var_78]
0x18002d736  mov     edx, [rcx+1Ch]; BufferSize
0x18002d739  mov     rcx, [rcx+10h]; Buffer
0x18002d73d  call    cs:__imp_MesDecodeBufferHandleCreate
0x18002d743  test    eax, eax
0x18002d745  jnz     loc_18002D64D
0x18002d74b  xorps   xmm0, xmm0
0x18002d74e  movups  xmmword ptr [rsp+0D8h+var_70], xmm0
0x18002d753  lea     rax, [rsp+0D8h+var_70]
0x18002d758  mov     [rsp+0D8h+pObject], rax; pObject
0x18002d75d  mov     esi, 10h
0x18002d762  mov     [rsp+0D8h+nTypeIndex], esi; nTypeIndex
0x18002d766  lea     r9, ArrTypeOffset; ArrTypeOffset
0x18002d76d  lea     r8, pProxyInfo; pProxyInfo
0x18002d774  lea     rdx, pPicklingInfo; pPicklingInfo
0x18002d77b  mov     rcx, [rsp+0D8h+pHandle]; Handle
0x18002d780  call    cs:__imp_NdrMesTypeDecode3
0x18002d786  nop
0x18002d787  mov     ebx, dword ptr [rsp+0D8h+var_70]
0x18002d78b  mov     [rsp+0D8h+var_90], ebx
0x18002d78f  test    ebx, ebx
0x18002d791  jnz     short loc_18002D7AD
0x18002d793  cmp     edi, dword ptr [rsp+0D8h+var_70+4]
0x18002d797  jnz     loc_18002D64D
0x18002d79d  mov     r8, [rsp+0D8h+var_70+8]; struct _ReaderState_Return *
0x18002d7a2  mov     rdx, r14; struct SCARD_READERSTATEW *
0x18002d7a5  mov     ecx, edi; unsigned int
0x18002d7a7  call    ?_CopyReaderStateWStructsForReturn@@YAXKPEAUSCARD_READERSTATEW@@PEAU_ReaderState_Return@@@Z; _CopyReaderStateWStructsForReturn(ulong,SCARD_READERSTATEW *,_ReaderState_Return *)
0x18002d7ac  nop
0x18002d7ad  lea     rax, [rsp+0D8h+var_70]
0x18002d7b2  mov     [rsp+0D8h+pObject], rax; pObject
0x18002d7b7  mov     [rsp+0D8h+nTypeIndex], esi; nTypeIndex
0x18002d7bb  lea     r9, ArrTypeOffset; ArrTypeOffset
0x18002d7c2  lea     r8, pProxyInfo; pProxyInfo
0x18002d7c9  lea     rdx, pPicklingInfo; pPicklingInfo
0x18002d7d0  mov     rcx, [rsp+0D8h+pHandle]; Handle
0x18002d7d5  call    cs:__imp_NdrMesTypeFree3
0x18002d7db  jmp     loc_18002D874
0x18002d7e0  mov     ebx, [rsp+0D8h+var_90]
0x18002d7e4  jmp     loc_18002D874
0x18002d7e9  mov     ebx, eax
0x18002d7eb  mov     edx, 2
0x18002d7f0  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18002d7f5  lea     rax, WPP_GLOBAL_Control
0x18002d7fc  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d803  cmp     rcx, rax
0x18002d806  jz      short loc_18002D82D
0x18002d808  test    byte ptr [rcx+1Ch], 8
0x18002d80c  jz      short loc_18002D82D
0x18002d80e  cmp     byte ptr [rcx+19h], 2
0x18002d812  jb      short loc_18002D82D
0x18002d814  mov     edx, 33h ; '3'
0x18002d819  mov     [rsp+0D8h+nTypeIndex], ebx
0x18002d81d  lea     r8, WPP_2af0b27572d33e35ea5753758eafaaae_Traceguids
0x18002d824  mov     rcx, [rcx+10h]
0x18002d828  call    WPP_SF_sd
0x18002d82d  jmp     short loc_18002D874
0x18002d82f  mov     ebx, eax
0x18002d831  mov     edx, 2
0x18002d836  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18002d83b  lea     rax, WPP_GLOBAL_Control
0x18002d842  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d849  cmp     rcx, rax
0x18002d84c  jz      short loc_18002D874
0x18002d84e  test    byte ptr [rcx+1Ch], 8
0x18002d852  jz      short loc_18002D874
0x18002d854  cmp     byte ptr [rcx+19h], 2
0x18002d858  jb      short loc_18002D874
0x18002d85a  mov     edx, 32h ; '2'
0x18002d85f  mov     [rsp+0D8h+nTypeIndex], ebx
0x18002d863  lea     r8, WPP_2af0b27572d33e35ea5753758eafaaae_Traceguids
0x18002d86a  mov     rcx, [rcx+10h]
0x18002d86e  call    WPP_SF_sd
0x18002d873  nop
0x18002d874  lea     rcx, [rsp+0D8h+pHandle]; void **
0x18002d879  call    ?SafeMesHandleFree@@YAXPEAPEAX@Z; SafeMesHandleFree(void * *)
0x18002d87e  mov     rcx, [rsp+0D8h+pBuffer]; void *
0x18002d883  call    MIDL_user_free
0x18002d888  mov     rcx, [rsp+0D8h+var_80]; void *
0x18002d88d  call    MIDL_user_free
0x18002d892  mov     rax, [rsp+0D8h+var_78]
0x18002d897  test    rax, rax
0x18002d89a  jz      short loc_18002D8A3
0x18002d89c  mov     dword ptr [rax+8], 0
0x18002d8a3  mov     eax, ebx
0x18002d8a5  add     rsp, 0B8h
0x18002d8ac  pop     r14
0x18002d8ae  pop     rdi
0x18002d8af  pop     rsi
0x18002d8b0  pop     rbx
0x18002d8b1  retn
```
