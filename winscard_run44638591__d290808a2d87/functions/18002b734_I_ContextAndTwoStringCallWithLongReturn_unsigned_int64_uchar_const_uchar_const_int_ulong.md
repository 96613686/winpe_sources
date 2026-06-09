# I_ContextAndTwoStringCallWithLongReturn(unsigned __int64,uchar const *,uchar const *,int,ulong)

- ea: `0x18002b734`
- end: `0x18002ba01`
- name: `?I_ContextAndTwoStringCallWithLongReturn@@YAJ_KPEBE1HK@Z`
- size: `717`
- prototype: `__int64 __fastcall(unsigned __int64, const unsigned __int8 *, const unsigned __int8 *, int, ULONG IoControlCode)`
- caller_count: `6`
- callee_count: `9`
- tags: ``

## callers

- `0x180024f70`
- `0x180025b30`
- `0x180026d80`
- `0x1800272a0`
- `0x180027c50`
- `0x180028790`

## callees

- `0x180006c80`
- `0x180007bc0`
- `0x18000f270`
- `0x18000ff10`
- `0x180012878`
- `0x180016ca4`
- `0x18001991c`
- `0x180019a14`
- `0x18002b734`

## import_xrefs

- `RPCRT4!NdrMesTypeEncode3` at `0x18002b880`
- `RPCRT4!NdrMesTypeEncode3` at `0x18002b913`
- `RPCRT4!NdrMesTypeEncode3` at `0x18002b880`
- `RPCRT4!NdrMesTypeEncode3` at `0x18002b913`
- `RPCRT4!MesEncodeDynBufferHandleCreate` at `0x18002b7ad`
- `RPCRT4!MesEncodeDynBufferHandleCreate` at `0x18002b7ad`
- `RPCRT4!MesHandleFree` at `0x18002b95d`
- `RPCRT4!MesHandleFree` at `0x18002b95d`

## pseudocode

```c
__int64 __fastcall I_ContextAndTwoStringCallWithLongReturn(
        __int64 a1,
        const unsigned __int8 *a2,
        const unsigned __int8 *a3,
        int a4,
        ULONG IoControlCode)
{
  unsigned int v9; // edi
  int v10; // eax
  int v11; // ecx
  unsigned int SCardError; // eax
  int v13; // edi
  handle_t pHandle; // [rsp+40h] [rbp-88h] BYREF
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+48h] [rbp-80h] BYREF
  PVOID InputBuffer; // [rsp+50h] [rbp-78h] BYREF
  struct _BUFFER_LIST_STRUCT *v18; // [rsp+58h] [rbp-70h] BYREF
  __int128 pObject; // [rsp+60h] [rbp-68h] BYREF
  __int128 v20; // [rsp+70h] [rbp-58h]
  __int128 v21; // [rsp+80h] [rbp-48h] BYREF
  __int128 v22; // [rsp+90h] [rbp-38h]
  ULONG InputBufferLength; // [rsp+D8h] [rbp+10h] BYREF

  InputBuffer = 0;
  InputBufferLength = 0;
  pHandle = 0;
  v18 = 0;
  v21 = 0;
  v22 = 0;
  pObject = 0;
  v20 = 0;
  lpCriticalSection = 0;
  if ( !a2 || !a3 )
    return 2148532241LL;
  if ( !MesEncodeDynBufferHandleCreate((char **)&InputBuffer, &InputBufferLength, &pHandle) )
  {
    if ( a1 )
    {
      pObject = *(_OWORD *)(a1 + 8);
      v21 = pObject;
      lpCriticalSection = *(LPCRITICAL_SECTION *)a1;
    }
    else
    {
      *((_QWORD *)&pObject + 1) = 0;
      *((_QWORD *)&v21 + 1) = 0;
      LODWORD(pObject) = 0;
      LODWORD(v21) = 0;
      v10 = RedirectionContextLookup(&lpCriticalSection);
      if ( v10 )
      {
        v11 = v10;
        goto LABEL_9;
      }
    }
    if ( a4 )
    {
      *(_QWORD *)&v20 = a2;
      *((_QWORD *)&v20 + 1) = a3;
      NdrMesTypeEncode3(pHandle, &pPicklingInfo, &pProxyInfo, (const unsigned int **)&ArrTypeOffset, 7u, &pObject);
    }
    else
    {
      *(_QWORD *)&v22 = a2;
      *((_QWORD *)&v22 + 1) = a3;
      NdrMesTypeEncode3(pHandle, &pPicklingInfo, &pProxyInfo, (const unsigned int **)&ArrTypeOffset, 6u, &v21);
    }
    v13 = _SendSCardIOCTL(IoControlCode, InputBuffer, InputBufferLength, &v18, lpCriticalSection, 0xFFFFFFFF, 0x800u);
    if ( !v13 )
    {
      SCardError = I_DecodeLongReturn(*((unsigned __int8 **)v18 + 2), *((_DWORD *)v18 + 7));
      goto LABEL_10;
    }
    MesHandleFree(pHandle);
    v11 = v13;
LABEL_9:
    SCardError = _MakeSCardError(v11);
LABEL_10:
    v9 = SCardError;
    goto LABEL_17;
  }
  v9 = -2146435041;
LABEL_17:
  SafeMesHandleFree(&pHandle);
  MIDL_user_free(InputBuffer);
  if ( v18 )
    *((_DWORD *)v18 + 2) = 0;
  return v9;
}

```

## disassembly

```asm
0x18002b734  mov     rax, rsp
0x18002b737  push    rsi
0x18002b738  push    rdi
0x18002b739  push    r14
0x18002b73b  push    r15
0x18002b73d  sub     rsp, 0A8h
0x18002b744  mov     r15d, r9d
0x18002b747  mov     rdi, r8
0x18002b74a  mov     r14, rdx
0x18002b74d  mov     rsi, rcx
0x18002b750  mov     qword ptr [rax-78h], 0
0x18002b758  mov     dword ptr [rax+10h], 0
0x18002b75f  mov     [rsp+0C8h+pHandle], 0
0x18002b768  mov     qword ptr [rax-70h], 0
0x18002b770  xorps   xmm0, xmm0
0x18002b773  movups  xmmword ptr [rax-48h], xmm0
0x18002b777  movups  xmmword ptr [rax-38h], xmm0
0x18002b77b  xorps   xmm1, xmm1
0x18002b77e  movups  xmmword ptr [rax-68h], xmm1
0x18002b782  movups  xmmword ptr [rax-58h], xmm1
0x18002b786  mov     qword ptr [rax-80h], 0
0x18002b78e  test    rdx, rdx
0x18002b791  jz      loc_18002B9EE
0x18002b797  test    r8, r8
0x18002b79a  jz      loc_18002B9EE
0x18002b7a0  lea     r8, [rsp+0C8h+pHandle]; pHandle
0x18002b7a5  lea     rdx, [rax+10h]; pEncodedSize
0x18002b7a9  lea     rcx, [rax-78h]; pBuffer
0x18002b7ad  call    cs:__imp_MesEncodeDynBufferHandleCreate
0x18002b7b3  test    eax, eax
0x18002b7b5  jz      short loc_18002B7C1
0x18002b7b7  mov     edi, 8010001Fh
0x18002b7bc  jmp     loc_18002B9C5
0x18002b7c1  test    rsi, rsi
0x18002b7c4  jz      short loc_18002B7FD
0x18002b7c6  mov     edx, [rsi+8]
0x18002b7c9  mov     dword ptr [rsp+0C8h+var_68], edx
0x18002b7cd  mov     eax, [rsi+0Ch]
0x18002b7d0  mov     dword ptr [rsp+0C8h+var_68+4], eax
0x18002b7d4  mov     rcx, [rsi+10h]
0x18002b7d8  mov     [rsp+0C8h+var_60], rcx
0x18002b7dd  mov     dword ptr [rsp+0C8h+var_48], edx
0x18002b7e4  mov     dword ptr [rsp+0C8h+var_48+4], eax
0x18002b7eb  mov     [rsp+0C8h+var_40], rcx
0x18002b7f3  mov     rax, [rsi]
0x18002b7f6  mov     [rsp+0C8h+lpCriticalSection], rax
0x18002b7fb  jmp     short loc_18002B841
0x18002b7fd  mov     [rsp+0C8h+var_60], 0
0x18002b806  mov     [rsp+0C8h+var_40], 0
0x18002b812  mov     dword ptr [rsp+0C8h+var_68], 0
0x18002b81a  mov     dword ptr [rsp+0C8h+var_48], 0
0x18002b825  lea     rcx, [rsp+0C8h+lpCriticalSection]; struct _REDIRECTION_CONTEXT **
0x18002b82a  call    ?RedirectionContextLookup@@YAKPEAPEAU_REDIRECTION_CONTEXT@@@Z; RedirectionContextLookup(_REDIRECTION_CONTEXT * *)
0x18002b82f  test    eax, eax
0x18002b831  jz      short loc_18002B841
0x18002b833  mov     ecx, eax; int
0x18002b835  call    ?_MakeSCardError@@YAJJ@Z; _MakeSCardError(long)
0x18002b83a  mov     edi, eax
0x18002b83c  jmp     loc_18002B9C5
0x18002b841  test    r15d, r15d
0x18002b844  jz      loc_18002B8D4
0x18002b84a  mov     [rsp+0C8h+var_58], r14
0x18002b84f  mov     [rsp+0C8h+var_50], rdi
0x18002b854  lea     rax, [rsp+0C8h+var_68]
0x18002b859  mov     [rsp+0C8h+pObject], rax; pObject
0x18002b85e  mov     [rsp+0C8h+nTypeIndex], 7; nTypeIndex
0x18002b866  lea     r9, ArrTypeOffset; ArrTypeOffset
0x18002b86d  lea     r8, pProxyInfo; pProxyInfo
0x18002b874  lea     rdx, pPicklingInfo; pPicklingInfo
0x18002b87b  mov     rcx, [rsp+0C8h+pHandle]; Handle
0x18002b880  call    cs:__imp_NdrMesTypeEncode3
0x18002b886  jmp     loc_18002B91A
0x18002b88b  mov     edi, eax
0x18002b88d  mov     edx, 2
0x18002b892  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18002b897  lea     rax, WPP_GLOBAL_Control
0x18002b89e  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b8a5  cmp     rcx, rax
0x18002b8a8  jz      short loc_18002B8CF
0x18002b8aa  test    byte ptr [rcx+1Ch], 8
0x18002b8ae  jz      short loc_18002B8CF
0x18002b8b0  cmp     byte ptr [rcx+19h], 2
0x18002b8b4  jb      short loc_18002B8CF
0x18002b8b6  mov     edx, 2Eh ; '.'
0x18002b8bb  mov     [rsp+0C8h+nTypeIndex], edi
0x18002b8bf  lea     r8, WPP_2af0b27572d33e35ea5753758eafaaae_Traceguids
0x18002b8c6  mov     rcx, [rcx+10h]
0x18002b8ca  call    WPP_SF_sd
0x18002b8cf  jmp     loc_18002B9C5
0x18002b8d4  mov     [rsp+0C8h+var_38], r14
0x18002b8dc  mov     [rsp+0C8h+var_30], rdi
0x18002b8e4  lea     rax, [rsp+0C8h+var_48]
0x18002b8ec  mov     [rsp+0C8h+pObject], rax; pObject
0x18002b8f1  mov     [rsp+0C8h+nTypeIndex], 6; nTypeIndex
0x18002b8f9  lea     r9, ArrTypeOffset; ArrTypeOffset
0x18002b900  lea     r8, pProxyInfo; pProxyInfo
0x18002b907  lea     rdx, pPicklingInfo; pPicklingInfo
0x18002b90e  mov     rcx, [rsp+0C8h+pHandle]; Handle
0x18002b913  call    cs:__imp_NdrMesTypeEncode3
0x18002b919  nop
0x18002b91a  mov     [rsp+0C8h+var_98], 800h; unsigned int
0x18002b922  mov     dword ptr [rsp+0C8h+pObject], 0FFFFFFFFh; dwMilliseconds
0x18002b92a  mov     rax, [rsp+0C8h+lpCriticalSection]
0x18002b92f  mov     qword ptr [rsp+0C8h+nTypeIndex], rax; lpCriticalSection
0x18002b934  lea     r9, [rsp+0C8h+var_70]; struct _BUFFER_LIST_STRUCT **
0x18002b939  mov     r8d, [rsp+0C8h+InputBufferLength]; InputBufferLength
0x18002b941  mov     rdx, [rsp+0C8h+InputBuffer]; InputBuffer
0x18002b946  mov     ecx, [rsp+0C8h+IoControlCode]; IoControlCode
0x18002b94d  call    ?_SendSCardIOCTL@@YAJKPEAXKPEAPEAU_BUFFER_LIST_STRUCT@@PEAU_REDIRECTION_CONTEXT@@KK@Z; _SendSCardIOCTL(ulong,void *,ulong,_BUFFER_LIST_STRUCT * *,_REDIRECTION_CONTEXT *,ulong,ulong)
0x18002b952  mov     edi, eax
0x18002b954  test    eax, eax
0x18002b956  jz      short loc_18002B96A
0x18002b958  mov     rcx, [rsp+0C8h+pHandle]; Handle
0x18002b95d  call    cs:__imp_MesHandleFree
0x18002b963  mov     ecx, edi
0x18002b965  jmp     loc_18002B835
0x18002b96a  mov     rcx, [rsp+0C8h+var_70]
0x18002b96f  mov     edx, [rcx+1Ch]; unsigned int
0x18002b972  mov     rcx, [rcx+10h]; unsigned __int8 *
0x18002b976  call    ?I_DecodeLongReturn@@YAJPEAEK@Z; I_DecodeLongReturn(uchar *,ulong)
0x18002b97b  jmp     loc_18002B83A
0x18002b980  mov     edi, eax
0x18002b982  mov     edx, 2
0x18002b987  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18002b98c  lea     rax, WPP_GLOBAL_Control
0x18002b993  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b99a  cmp     rcx, rax
0x18002b99d  jz      short loc_18002B9C5
0x18002b99f  test    byte ptr [rcx+1Ch], 8
0x18002b9a3  jz      short loc_18002B9C5
0x18002b9a5  cmp     byte ptr [rcx+19h], 2
0x18002b9a9  jb      short loc_18002B9C5
0x18002b9ab  mov     edx, 2Fh ; '/'
0x18002b9b0  mov     [rsp+0C8h+nTypeIndex], edi
0x18002b9b4  lea     r8, WPP_2af0b27572d33e35ea5753758eafaaae_Traceguids
0x18002b9bb  mov     rcx, [rcx+10h]
0x18002b9bf  call    WPP_SF_sd
0x18002b9c4  nop
0x18002b9c5  lea     rcx, [rsp+0C8h+pHandle]; void **
0x18002b9ca  call    ?SafeMesHandleFree@@YAXPEAPEAX@Z; SafeMesHandleFree(void * *)
0x18002b9cf  mov     rcx, [rsp+0C8h+InputBuffer]; void *
0x18002b9d4  call    MIDL_user_free
0x18002b9d9  mov     rax, [rsp+0C8h+var_70]
0x18002b9de  test    rax, rax
0x18002b9e1  jz      short loc_18002B9EA
0x18002b9e3  mov     dword ptr [rax+8], 0
0x18002b9ea  mov     eax, edi
0x18002b9ec  jmp     short loc_18002B9F3
0x18002b9ee  mov     eax, 80100011h
0x18002b9f3  add     rsp, 0A8h
0x18002b9fa  pop     r15
0x18002b9fc  pop     r14
0x18002b9fe  pop     rdi
0x18002b9ff  pop     rsi
0x18002ba00  retn
```
