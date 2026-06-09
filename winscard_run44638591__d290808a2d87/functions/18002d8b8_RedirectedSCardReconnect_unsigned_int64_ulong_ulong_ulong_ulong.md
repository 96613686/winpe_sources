# RedirectedSCardReconnect(unsigned __int64,ulong,ulong,ulong,ulong *)

- ea: `0x18002d8b8`
- end: `0x18002db56`
- name: `?RedirectedSCardReconnect@@YAJ_KKKKPEAK@Z`
- size: `670`
- prototype: `__int64 __fastcall(unsigned __int64, unsigned int, unsigned int, unsigned int, unsigned int *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180023640`

## callees

- `0x180007bc0`
- `0x18000f270`
- `0x18000ff10`
- `0x180016ca4`
- `0x18001991c`
- `0x180019a14`
- `0x18002d8b8`

## import_xrefs

- `RPCRT4!NdrMesTypeDecode3` at `0x18002da3d`
- `RPCRT4!NdrMesTypeDecode3` at `0x18002da3d`
- `RPCRT4!NdrMesTypeEncode3` at `0x18002d99b`
- `RPCRT4!NdrMesTypeEncode3` at `0x18002d99b`
- `RPCRT4!NdrMesTypeFree3` at `0x18002da83`
- `RPCRT4!NdrMesTypeFree3` at `0x18002da83`
- `RPCRT4!MesEncodeDynBufferHandleCreate` at `0x18002d92a`
- `RPCRT4!MesEncodeDynBufferHandleCreate` at `0x18002d92a`
- `RPCRT4!MesDecodeBufferHandleCreate` at `0x18002da06`
- `RPCRT4!MesDecodeBufferHandleCreate` at `0x18002da06`

## pseudocode

```c
__int64 __fastcall RedirectedSCardReconnect(__int64 a1, unsigned int a2, unsigned int a3, int a4, unsigned int *a5)
{
  unsigned int SCardError; // ebx
  int v11; // eax
  handle_t pHandle; // [rsp+48h] [rbp-80h] BYREF
  __int64 v13; // [rsp+50h] [rbp-78h] BYREF
  char *pBuffer; // [rsp+58h] [rbp-70h] BYREF
  struct _BUFFER_LIST_STRUCT *v15; // [rsp+60h] [rbp-68h] BYREF
  __int128 pObject; // [rsp+68h] [rbp-60h] BYREF
  __int128 v17; // [rsp+78h] [rbp-50h]
  __int128 v18; // [rsp+88h] [rbp-40h]
  unsigned int pEncodedSize; // [rsp+D0h] [rbp+8h] BYREF

  pBuffer = 0;
  pEncodedSize = 0;
  pHandle = 0;
  v15 = 0;
  pObject = 0;
  v17 = 0;
  v18 = 0;
  v13 = 0;
  if ( !a1 )
    return 2148532228LL;
  if ( !MesEncodeDynBufferHandleCreate(&pBuffer, &pEncodedSize, &pHandle) )
  {
    pObject = *(_OWORD *)(a1 + 8);
    v17 = *(_OWORD *)(a1 + 24);
    *(_QWORD *)&v18 = __PAIR64__(a3, a2);
    DWORD2(v18) = a4;
    NdrMesTypeEncode3(pHandle, &pPicklingInfo, &pProxyInfo, (const unsigned int **)&ArrTypeOffset, 0x17u, &pObject);
    v11 = _SendSCardIOCTL(0x900B4u, pBuffer, pEncodedSize, &v15, **(LPCRITICAL_SECTION **)a1, 0xFFFFFFFF, 0x800u);
    if ( v11 )
    {
      SCardError = _MakeSCardError(v11);
      goto LABEL_12;
    }
    SafeMesHandleFree(&pHandle);
    if ( !MesDecodeBufferHandleCreate(*((char **)v15 + 2), *((_DWORD *)v15 + 7), &pHandle) )
    {
      v13 = 0;
      NdrMesTypeDecode3(pHandle, &pPicklingInfo, &pProxyInfo, (const unsigned int **)&ArrTypeOffset, 0x18u, &v13);
      SCardError = v13;
      if ( !(_DWORD)v13 && a5 )
        *a5 = HIDWORD(v13);
      NdrMesTypeFree3(pHandle, &pPicklingInfo, &pProxyInfo, (const unsigned int **)&ArrTypeOffset, 0x18u, &v13);
      goto LABEL_12;
    }
  }
  SCardError = -2146435041;
LABEL_12:
  SafeMesHandleFree(&pHandle);
  MIDL_user_free(pBuffer);
  if ( v15 )
    *((_DWORD *)v15 + 2) = 0;
  return SCardError;
}

```

## disassembly

```asm
0x18002d8b8  mov     rax, rsp
0x18002d8bb  push    rbx
0x18002d8bc  push    rsi
0x18002d8bd  push    rdi
0x18002d8be  push    r14
0x18002d8c0  sub     rsp, 0A8h
0x18002d8c7  mov     edi, r9d
0x18002d8ca  mov     esi, r8d
0x18002d8cd  mov     r14d, edx
0x18002d8d0  mov     rbx, rcx
0x18002d8d3  mov     qword ptr [rax-70h], 0
0x18002d8db  mov     dword ptr [rax+8], 0
0x18002d8e2  mov     qword ptr [rax-80h], 0
0x18002d8ea  mov     qword ptr [rax-68h], 0
0x18002d8f2  xorps   xmm0, xmm0
0x18002d8f5  movups  xmmword ptr [rax-60h], xmm0
0x18002d8f9  movups  xmmword ptr [rax-50h], xmm0
0x18002d8fd  movups  xmmword ptr [rax-40h], xmm0
0x18002d901  mov     qword ptr [rax-78h], 0
0x18002d909  test    rcx, rcx
0x18002d90c  jnz     short loc_18002D918
0x18002d90e  mov     eax, 80100004h
0x18002d913  jmp     loc_18002DB49
0x18002d918  lea     r8, [rsp+0C8h+pHandle]; pHandle
0x18002d91d  lea     rdx, [rsp+0C8h+pEncodedSize]; pEncodedSize
0x18002d925  lea     rcx, [rsp+0C8h+pBuffer]; pBuffer
0x18002d92a  call    cs:__imp_MesEncodeDynBufferHandleCreate
0x18002d930  test    eax, eax
0x18002d932  jz      short loc_18002D93E
0x18002d934  mov     ebx, 8010001Fh
0x18002d939  jmp     loc_18002DB22
0x18002d93e  movups  xmm0, xmmword ptr [rbx+8]
0x18002d942  movups  [rsp+0C8h+var_60], xmm0
0x18002d947  movups  xmm1, xmmword ptr [rbx+18h]
0x18002d94b  movups  [rsp+0C8h+var_50], xmm1
0x18002d950  mov     [rsp+0C8h+var_40], r14d
0x18002d958  mov     [rsp+0C8h+var_3C], esi
0x18002d95f  mov     [rsp+0C8h+var_38], edi
0x18002d966  lea     rax, [rsp+0C8h+var_60]
0x18002d96b  mov     [rsp+0C8h+pObject], rax; pObject
0x18002d970  mov     [rsp+0C8h+nTypeIndex], 17h; nTypeIndex
0x18002d978  lea     rdi, ArrTypeOffset
0x18002d97f  mov     r9, rdi; ArrTypeOffset
0x18002d982  lea     rsi, pProxyInfo
0x18002d989  mov     r8, rsi; pProxyInfo
0x18002d98c  lea     r14, pPicklingInfo
0x18002d993  mov     rdx, r14; pPicklingInfo
0x18002d996  mov     rcx, [rsp+0C8h+pHandle]; Handle
0x18002d99b  call    cs:__imp_NdrMesTypeEncode3
0x18002d9a1  nop
0x18002d9a2  mov     rax, [rbx]
0x18002d9a5  mov     [rsp+0C8h+var_98], 800h; unsigned int
0x18002d9ad  mov     dword ptr [rsp+0C8h+pObject], 0FFFFFFFFh; dwMilliseconds
0x18002d9b5  mov     rax, [rax]
0x18002d9b8  mov     qword ptr [rsp+0C8h+nTypeIndex], rax; lpCriticalSection
0x18002d9bd  lea     r9, [rsp+0C8h+var_68]; struct _BUFFER_LIST_STRUCT **
0x18002d9c2  mov     r8d, [rsp+0C8h+pEncodedSize]; InputBufferLength
0x18002d9ca  mov     rdx, [rsp+0C8h+pBuffer]; InputBuffer
0x18002d9cf  mov     ecx, 900B4h; IoControlCode
0x18002d9d4  call    ?_SendSCardIOCTL@@YAJKPEAXKPEAPEAU_BUFFER_LIST_STRUCT@@PEAU_REDIRECTION_CONTEXT@@KK@Z; _SendSCardIOCTL(ulong,void *,ulong,_BUFFER_LIST_STRUCT * *,_REDIRECTION_CONTEXT *,ulong,ulong)
0x18002d9d9  test    eax, eax
0x18002d9db  jz      short loc_18002D9EB
0x18002d9dd  mov     ecx, eax; int
0x18002d9df  call    ?_MakeSCardError@@YAJJ@Z; _MakeSCardError(long)
0x18002d9e4  mov     ebx, eax
0x18002d9e6  jmp     loc_18002DB22
0x18002d9eb  lea     rcx, [rsp+0C8h+pHandle]; void **
0x18002d9f0  call    ?SafeMesHandleFree@@YAXPEAPEAX@Z; SafeMesHandleFree(void * *)
0x18002d9f5  lea     r8, [rsp+0C8h+pHandle]; pHandle
0x18002d9fa  mov     rcx, [rsp+0C8h+var_68]
0x18002d9ff  mov     edx, [rcx+1Ch]; BufferSize
0x18002da02  mov     rcx, [rcx+10h]; Buffer
0x18002da06  call    cs:__imp_MesDecodeBufferHandleCreate
0x18002da0c  test    eax, eax
0x18002da0e  jnz     loc_18002D934
0x18002da14  mov     [rsp+0C8h+var_78], 0
0x18002da1d  lea     rax, [rsp+0C8h+var_78]
0x18002da22  mov     [rsp+0C8h+pObject], rax; pObject
0x18002da27  mov     [rsp+0C8h+nTypeIndex], 18h; nTypeIndex
0x18002da2f  mov     r9, rdi; ArrTypeOffset
0x18002da32  mov     r8, rsi; pProxyInfo
0x18002da35  mov     rdx, r14; pPicklingInfo
0x18002da38  mov     rcx, [rsp+0C8h+pHandle]; Handle
0x18002da3d  call    cs:__imp_NdrMesTypeDecode3
0x18002da43  nop
0x18002da44  mov     ebx, dword ptr [rsp+0C8h+var_78]
0x18002da48  mov     [rsp+0C8h+var_88], ebx
0x18002da4c  test    ebx, ebx
0x18002da4e  jnz     short loc_18002DA63
0x18002da50  mov     rcx, [rsp+0C8h+arg_20]
0x18002da58  test    rcx, rcx
0x18002da5b  jz      short loc_18002DA63
0x18002da5d  mov     eax, dword ptr [rsp+0C8h+var_78+4]
0x18002da61  mov     [rcx], eax
0x18002da63  lea     rax, [rsp+0C8h+var_78]
0x18002da68  mov     [rsp+0C8h+pObject], rax; pObject
0x18002da6d  mov     [rsp+0C8h+nTypeIndex], 18h; nTypeIndex
0x18002da75  mov     r9, rdi; ArrTypeOffset
0x18002da78  mov     r8, rsi; pProxyInfo
0x18002da7b  mov     rdx, r14; pPicklingInfo
0x18002da7e  mov     rcx, [rsp+0C8h+pHandle]; Handle
0x18002da83  call    cs:__imp_NdrMesTypeFree3
0x18002da89  jmp     loc_18002DB22
0x18002da8e  mov     ebx, [rsp+0C8h+var_88]
0x18002da92  jmp     loc_18002DB22
0x18002da97  mov     ebx, eax
0x18002da99  mov     edx, 2
0x18002da9e  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18002daa3  lea     rax, WPP_GLOBAL_Control
0x18002daaa  mov     rcx, cs:WPP_GLOBAL_Control
0x18002dab1  cmp     rcx, rax
0x18002dab4  jz      short loc_18002DADB
0x18002dab6  test    byte ptr [rcx+1Ch], 8
0x18002daba  jz      short loc_18002DADB
0x18002dabc  cmp     byte ptr [rcx+19h], 2
0x18002dac0  jb      short loc_18002DADB
0x18002dac2  mov     edx, 42h ; 'B'
0x18002dac7  mov     [rsp+0C8h+nTypeIndex], ebx
0x18002dacb  lea     r8, WPP_2af0b27572d33e35ea5753758eafaaae_Traceguids
0x18002dad2  mov     rcx, [rcx+10h]
0x18002dad6  call    WPP_SF_sd
0x18002dadb  jmp     short loc_18002DB22
0x18002dadd  mov     ebx, eax
0x18002dadf  mov     edx, 2
0x18002dae4  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18002dae9  lea     rax, WPP_GLOBAL_Control
0x18002daf0  mov     rcx, cs:WPP_GLOBAL_Control
0x18002daf7  cmp     rcx, rax
0x18002dafa  jz      short loc_18002DB22
0x18002dafc  test    byte ptr [rcx+1Ch], 8
0x18002db00  jz      short loc_18002DB22
0x18002db02  cmp     byte ptr [rcx+19h], 2
0x18002db06  jb      short loc_18002DB22
0x18002db08  mov     edx, 41h ; 'A'
0x18002db0d  mov     [rsp+0C8h+nTypeIndex], ebx
0x18002db11  lea     r8, WPP_2af0b27572d33e35ea5753758eafaaae_Traceguids
0x18002db18  mov     rcx, [rcx+10h]
0x18002db1c  call    WPP_SF_sd
0x18002db21  nop
0x18002db22  lea     rcx, [rsp+0C8h+pHandle]; void **
0x18002db27  call    ?SafeMesHandleFree@@YAXPEAPEAX@Z; SafeMesHandleFree(void * *)
0x18002db2c  mov     rcx, [rsp+0C8h+pBuffer]; void *
0x18002db31  call    MIDL_user_free
0x18002db36  mov     rax, [rsp+0C8h+var_68]
0x18002db3b  test    rax, rax
0x18002db3e  jz      short loc_18002DB47
0x18002db40  mov     dword ptr [rax+8], 0
0x18002db47  mov     eax, ebx
0x18002db49  add     rsp, 0A8h
0x18002db50  pop     r14
0x18002db52  pop     rdi
0x18002db53  pop     rsi
0x18002db54  pop     rbx
0x18002db55  retn
```
