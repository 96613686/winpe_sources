# RedirectedSCardGetTransmitCount(unsigned __int64,ulong *)

- ea: `0x18002c9ac`
- end: `0x18002cc61`
- name: `?RedirectedSCardGetTransmitCount@@YAJ_KPEAK@Z`
- size: `693`
- prototype: `__int64 __fastcall(unsigned __int64, unsigned int *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180023520`

## callees

- `0x180007bc0`
- `0x18000f270`
- `0x18000ff10`
- `0x180016ca4`
- `0x18001991c`
- `0x180019a14`
- `0x18002c9ac`

## import_xrefs

- `RPCRT4!NdrMesTypeDecode3` at `0x18002cb39`
- `RPCRT4!NdrMesTypeDecode3` at `0x18002cb39`
- `RPCRT4!NdrMesTypeEncode3` at `0x18002ca82`
- `RPCRT4!NdrMesTypeEncode3` at `0x18002ca82`
- `RPCRT4!NdrMesTypeFree3` at `0x18002cb84`
- `RPCRT4!NdrMesTypeFree3` at `0x18002cb84`
- `RPCRT4!MesEncodeDynBufferHandleCreate` at `0x18002ca2d`
- `RPCRT4!MesEncodeDynBufferHandleCreate` at `0x18002ca2d`
- `RPCRT4!MesDecodeBufferHandleCreate` at `0x18002caf3`
- `RPCRT4!MesDecodeBufferHandleCreate` at `0x18002caf3`

## pseudocode

```c
__int64 __fastcall RedirectedSCardGetTransmitCount(LPCRITICAL_SECTION **a1, unsigned int *a2)
{
  unsigned int SCardError; // ebx
  int v6; // eax
  __int64 v7; // [rsp+40h] [rbp-48h] BYREF
  char *pBuffer; // [rsp+48h] [rbp-40h] BYREF
  struct _BUFFER_LIST_STRUCT *v9; // [rsp+50h] [rbp-38h] BYREF
  __int128 pObject; // [rsp+58h] [rbp-30h] BYREF
  __int128 v11; // [rsp+68h] [rbp-20h]
  unsigned int pEncodedSize; // [rsp+90h] [rbp+8h] BYREF
  int v13; // [rsp+A0h] [rbp+18h]
  handle_t pHandle; // [rsp+A8h] [rbp+20h] BYREF

  pBuffer = 0;
  pEncodedSize = 0;
  pHandle = 0;
  v9 = 0;
  pObject = 0;
  v11 = 0;
  v7 = 0;
  if ( !a1 )
    return 2148532228LL;
  if ( HIDWORD((**a1)[1].LockSemaphore) < 2 )
    return 120;
  if ( !MesEncodeDynBufferHandleCreate(&pBuffer, &pEncodedSize, &pHandle) )
  {
    pObject = *(_OWORD *)(a1 + 1);
    v11 = *(_OWORD *)(a1 + 3);
    NdrMesTypeEncode3(pHandle, &pPicklingInfo, &pProxyInfo, (const unsigned int **)&ArrTypeOffset, 0x20u, &pObject);
    v6 = _SendSCardIOCTL(0x90100u, pBuffer, pEncodedSize, &v9, **a1, 0xFFFFFFFF, 0x800u);
    if ( v6 )
    {
      SCardError = _MakeSCardError(v6);
      goto LABEL_13;
    }
    SafeMesHandleFree(&pHandle);
    if ( !MesDecodeBufferHandleCreate(*((char **)v9 + 2), *((_DWORD *)v9 + 7), &pHandle) )
    {
      v7 = 0;
      NdrMesTypeDecode3(pHandle, &pPicklingInfo, &pProxyInfo, (const unsigned int **)&ArrTypeOffset, 0x21u, &v7);
      SCardError = v7;
      v13 = v7;
      if ( !(_DWORD)v7 )
        *a2 = HIDWORD(v7);
      NdrMesTypeFree3(pHandle, &pPicklingInfo, &pProxyInfo, (const unsigned int **)&ArrTypeOffset, 0x21u, &v7);
      goto LABEL_13;
    }
  }
  SCardError = -2146435041;
LABEL_13:
  SafeMesHandleFree(&pHandle);
  MIDL_user_free(pBuffer);
  if ( v9 )
    *((_DWORD *)v9 + 2) = 0;
  return SCardError;
}

```

## disassembly

```asm
0x18002c9ac  mov     rax, rsp
0x18002c9af  mov     [rax+10h], rbx
0x18002c9b3  push    rdi
0x18002c9b4  sub     rsp, 80h
0x18002c9bb  mov     rdi, rdx
0x18002c9be  mov     rbx, rcx
0x18002c9c1  mov     qword ptr [rax-40h], 0
0x18002c9c9  mov     dword ptr [rax+8], 0
0x18002c9d0  mov     qword ptr [rax+20h], 0
0x18002c9d8  mov     qword ptr [rax-38h], 0
0x18002c9e0  xorps   xmm0, xmm0
0x18002c9e3  movups  xmmword ptr [rax-30h], xmm0
0x18002c9e7  movups  xmmword ptr [rax-20h], xmm0
0x18002c9eb  mov     qword ptr [rax-48h], 0
0x18002c9f3  test    rcx, rcx
0x18002c9f6  jnz     short loc_18002CA02
0x18002c9f8  mov     eax, 80100004h
0x18002c9fd  jmp     loc_18002CC50
0x18002ca02  mov     rax, [rcx]
0x18002ca05  mov     rcx, [rax]
0x18002ca08  cmp     dword ptr [rcx+44h], 2
0x18002ca0c  jnb     short loc_18002CA18
0x18002ca0e  mov     eax, 78h ; 'x'
0x18002ca13  jmp     loc_18002CC50
0x18002ca18  lea     r8, [rsp+88h+pHandle]; pHandle
0x18002ca20  lea     rdx, [rsp+88h+pEncodedSize]; pEncodedSize
0x18002ca28  lea     rcx, [rsp+88h+pBuffer]; pBuffer
0x18002ca2d  call    cs:__imp_MesEncodeDynBufferHandleCreate
0x18002ca33  test    eax, eax
0x18002ca35  jz      short loc_18002CA41
0x18002ca37  mov     ebx, 8010001Fh
0x18002ca3c  jmp     loc_18002CC26
0x18002ca41  movups  xmm0, xmmword ptr [rbx+8]
0x18002ca45  movups  [rsp+88h+var_30], xmm0
0x18002ca4a  movups  xmm1, xmmword ptr [rbx+18h]
0x18002ca4e  movups  [rsp+88h+var_20], xmm1
0x18002ca53  lea     rax, [rsp+88h+var_30]
0x18002ca58  mov     [rsp+88h+pObject], rax; pObject
0x18002ca5d  mov     [rsp+88h+nTypeIndex], 20h ; ' '; nTypeIndex
0x18002ca65  lea     r9, ArrTypeOffset; ArrTypeOffset
0x18002ca6c  lea     r8, pProxyInfo; pProxyInfo
0x18002ca73  lea     rdx, pPicklingInfo; pPicklingInfo
0x18002ca7a  mov     rcx, [rsp+88h+pHandle]; Handle
0x18002ca82  call    cs:__imp_NdrMesTypeEncode3
0x18002ca88  nop
0x18002ca89  mov     rax, [rbx]
0x18002ca8c  mov     [rsp+88h+var_58], 800h; unsigned int
0x18002ca94  mov     dword ptr [rsp+88h+pObject], 0FFFFFFFFh; dwMilliseconds
0x18002ca9c  mov     rax, [rax]
0x18002ca9f  mov     qword ptr [rsp+88h+nTypeIndex], rax; lpCriticalSection
0x18002caa4  lea     r9, [rsp+88h+var_38]; struct _BUFFER_LIST_STRUCT **
0x18002caa9  mov     r8d, [rsp+88h+pEncodedSize]; InputBufferLength
0x18002cab1  mov     rdx, [rsp+88h+pBuffer]; InputBuffer
0x18002cab6  mov     ecx, 90100h; IoControlCode
0x18002cabb  call    ?_SendSCardIOCTL@@YAJKPEAXKPEAPEAU_BUFFER_LIST_STRUCT@@PEAU_REDIRECTION_CONTEXT@@KK@Z; _SendSCardIOCTL(ulong,void *,ulong,_BUFFER_LIST_STRUCT * *,_REDIRECTION_CONTEXT *,ulong,ulong)
0x18002cac0  test    eax, eax
0x18002cac2  jz      short loc_18002CAD2
0x18002cac4  mov     ecx, eax; int
0x18002cac6  call    ?_MakeSCardError@@YAJJ@Z; _MakeSCardError(long)
0x18002cacb  mov     ebx, eax
0x18002cacd  jmp     loc_18002CC26
0x18002cad2  lea     rcx, [rsp+88h+pHandle]; void **
0x18002cada  call    ?SafeMesHandleFree@@YAXPEAPEAX@Z; SafeMesHandleFree(void * *)
0x18002cadf  lea     r8, [rsp+88h+pHandle]; pHandle
0x18002cae7  mov     rcx, [rsp+88h+var_38]
0x18002caec  mov     edx, [rcx+1Ch]; BufferSize
0x18002caef  mov     rcx, [rcx+10h]; Buffer
0x18002caf3  call    cs:__imp_MesDecodeBufferHandleCreate
0x18002caf9  test    eax, eax
0x18002cafb  jnz     loc_18002CA37
0x18002cb01  mov     [rsp+88h+var_48], 0
0x18002cb0a  lea     rax, [rsp+88h+var_48]
0x18002cb0f  mov     [rsp+88h+pObject], rax; pObject
0x18002cb14  mov     [rsp+88h+nTypeIndex], 21h ; '!'; nTypeIndex
0x18002cb1c  lea     r9, ArrTypeOffset; ArrTypeOffset
0x18002cb23  lea     r8, pProxyInfo; pProxyInfo
0x18002cb2a  lea     rdx, pPicklingInfo; pPicklingInfo
0x18002cb31  mov     rcx, [rsp+88h+pHandle]; Handle
0x18002cb39  call    cs:__imp_NdrMesTypeDecode3
0x18002cb3f  nop
0x18002cb40  mov     ebx, dword ptr [rsp+88h+var_48]
0x18002cb44  mov     [rsp+88h+arg_10], ebx
0x18002cb4b  test    ebx, ebx
0x18002cb4d  jnz     short loc_18002CB55
0x18002cb4f  mov     eax, dword ptr [rsp+88h+var_48+4]
0x18002cb53  mov     [rdi], eax
0x18002cb55  lea     rax, [rsp+88h+var_48]
0x18002cb5a  mov     [rsp+88h+pObject], rax; pObject
0x18002cb5f  mov     [rsp+88h+nTypeIndex], 21h ; '!'; nTypeIndex
0x18002cb67  lea     r9, ArrTypeOffset; ArrTypeOffset
0x18002cb6e  lea     r8, pProxyInfo; pProxyInfo
0x18002cb75  lea     rdx, pPicklingInfo; pPicklingInfo
0x18002cb7c  mov     rcx, [rsp+88h+pHandle]; Handle
0x18002cb84  call    cs:__imp_NdrMesTypeFree3
0x18002cb8a  jmp     loc_18002CC26
0x18002cb8f  mov     ebx, [rsp+88h+arg_10]
0x18002cb96  jmp     loc_18002CC26
0x18002cb9b  mov     ebx, eax
0x18002cb9d  mov     edx, 2
0x18002cba2  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18002cba7  lea     rax, WPP_GLOBAL_Control
0x18002cbae  mov     rcx, cs:WPP_GLOBAL_Control
0x18002cbb5  cmp     rcx, rax
0x18002cbb8  jz      short loc_18002CBDF
0x18002cbba  test    byte ptr [rcx+1Ch], 8
0x18002cbbe  jz      short loc_18002CBDF
0x18002cbc0  cmp     byte ptr [rcx+19h], 2
0x18002cbc4  jb      short loc_18002CBDF
0x18002cbc6  mov     edx, 4Bh ; 'K'
0x18002cbcb  mov     [rsp+88h+nTypeIndex], ebx
0x18002cbcf  lea     r8, WPP_2af0b27572d33e35ea5753758eafaaae_Traceguids
0x18002cbd6  mov     rcx, [rcx+10h]
0x18002cbda  call    WPP_SF_sd
0x18002cbdf  jmp     short loc_18002CC26
0x18002cbe1  mov     ebx, eax
0x18002cbe3  mov     edx, 2
0x18002cbe8  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18002cbed  lea     rax, WPP_GLOBAL_Control
0x18002cbf4  mov     rcx, cs:WPP_GLOBAL_Control
0x18002cbfb  cmp     rcx, rax
0x18002cbfe  jz      short loc_18002CC26
0x18002cc00  test    byte ptr [rcx+1Ch], 8
0x18002cc04  jz      short loc_18002CC26
0x18002cc06  cmp     byte ptr [rcx+19h], 2
0x18002cc0a  jb      short loc_18002CC26
0x18002cc0c  mov     edx, 4Ah ; 'J'
0x18002cc11  mov     [rsp+88h+nTypeIndex], ebx
0x18002cc15  lea     r8, WPP_2af0b27572d33e35ea5753758eafaaae_Traceguids
0x18002cc1c  mov     rcx, [rcx+10h]
0x18002cc20  call    WPP_SF_sd
0x18002cc25  nop
0x18002cc26  lea     rcx, [rsp+88h+pHandle]; void **
0x18002cc2e  call    ?SafeMesHandleFree@@YAXPEAPEAX@Z; SafeMesHandleFree(void * *)
0x18002cc33  mov     rcx, [rsp+88h+pBuffer]; void *
0x18002cc38  call    MIDL_user_free
0x18002cc3d  mov     rax, [rsp+88h+var_38]
0x18002cc42  test    rax, rax
0x18002cc45  jz      short loc_18002CC4E
0x18002cc47  mov     dword ptr [rax+8], 0
0x18002cc4e  mov     eax, ebx
0x18002cc50  mov     rbx, [rsp+88h+arg_8]
0x18002cc58  add     rsp, 80h
0x18002cc5f  pop     rdi
0x18002cc60  retn
```
