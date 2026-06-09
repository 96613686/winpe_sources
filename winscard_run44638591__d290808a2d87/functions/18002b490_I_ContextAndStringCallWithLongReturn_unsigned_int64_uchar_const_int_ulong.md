# I_ContextAndStringCallWithLongReturn(unsigned __int64,uchar const *,int,ulong)

- ea: `0x18002b490`
- end: `0x18002b72b`
- name: `?I_ContextAndStringCallWithLongReturn@@YAJ_KPEBEHK@Z`
- size: `667`
- prototype: `int(unsigned __int64, const unsigned __int8 *, int, unsigned int)`
- caller_count: `6`
- callee_count: `9`
- tags: ``

## callers

- `0x180025170`
- `0x180025300`
- `0x180025d30`
- `0x1800274a0`
- `0x180027630`
- `0x180027ad0`

## callees

- `0x180006c80`
- `0x180007bc0`
- `0x18000f270`
- `0x18000ff10`
- `0x180012878`
- `0x180016ca4`
- `0x18001991c`
- `0x180019a14`
- `0x18002b490`

## import_xrefs

- `RPCRT4!NdrMesTypeEncode3` at `0x18002b5d0`
- `RPCRT4!NdrMesTypeEncode3` at `0x18002b658`
- `RPCRT4!NdrMesTypeEncode3` at `0x18002b5d0`
- `RPCRT4!NdrMesTypeEncode3` at `0x18002b658`
- `RPCRT4!MesEncodeDynBufferHandleCreate` at `0x18002b50b`
- `RPCRT4!MesEncodeDynBufferHandleCreate` at `0x18002b50b`

## pseudocode

```c
__int64 __fastcall I_ContextAndStringCallWithLongReturn(__int64 a1, const unsigned __int8 *a2, int a3, unsigned int a4)
{
  unsigned int v9; // edi
  int v10; // eax
  unsigned int SCardError; // eax
  handle_t pHandle; // [rsp+40h] [rbp-78h] BYREF
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+48h] [rbp-70h] BYREF
  char *pBuffer; // [rsp+50h] [rbp-68h] BYREF
  struct _BUFFER_LIST_STRUCT *v15; // [rsp+58h] [rbp-60h] BYREF
  __int128 pObject; // [rsp+60h] [rbp-58h] BYREF
  const unsigned __int8 *v17; // [rsp+70h] [rbp-48h]
  __int128 v18; // [rsp+78h] [rbp-40h] BYREF
  const unsigned __int8 *v19; // [rsp+88h] [rbp-30h]
  unsigned int pEncodedSize; // [rsp+C8h] [rbp+10h] BYREF

  pBuffer = 0;
  pEncodedSize = 0;
  pHandle = 0;
  v15 = 0;
  v18 = 0;
  v19 = 0;
  pObject = 0;
  v17 = 0;
  lpCriticalSection = 0;
  if ( !a2 )
    return 2148532241LL;
  if ( !MesEncodeDynBufferHandleCreate(&pBuffer, &pEncodedSize, &pHandle) )
  {
    if ( a1 )
    {
      pObject = *(_OWORD *)(a1 + 8);
      v18 = pObject;
      lpCriticalSection = *(LPCRITICAL_SECTION *)a1;
    }
    else
    {
      *((_QWORD *)&pObject + 1) = 0;
      *((_QWORD *)&v18 + 1) = 0;
      LODWORD(pObject) = 0;
      LODWORD(v18) = 0;
      v10 = RedirectionContextLookup(&lpCriticalSection);
      if ( v10 )
        goto LABEL_8;
    }
    if ( a3 )
    {
      v17 = a2;
      NdrMesTypeEncode3(pHandle, &pPicklingInfo, &pProxyInfo, (const unsigned int **)&ArrTypeOffset, 5u, &pObject);
    }
    else
    {
      v19 = a2;
      NdrMesTypeEncode3(pHandle, &pPicklingInfo, &pProxyInfo, (const unsigned int **)&ArrTypeOffset, 4u, &v18);
    }
    v10 = _SendSCardIOCTL(a4, pBuffer, pEncodedSize, &v15, lpCriticalSection, 0xFFFFFFFF, 0x800u);
    if ( !v10 )
    {
      SCardError = I_DecodeLongReturn(*((unsigned __int8 **)v15 + 2), *((_DWORD *)v15 + 7));
      goto LABEL_9;
    }
LABEL_8:
    SCardError = _MakeSCardError(v10);
LABEL_9:
    v9 = SCardError;
    goto LABEL_15;
  }
  v9 = -2146435041;
LABEL_15:
  SafeMesHandleFree(&pHandle);
  MIDL_user_free(pBuffer);
  if ( v15 )
    *((_DWORD *)v15 + 2) = 0;
  return v9;
}

```

## disassembly

```asm
0x18002b490  mov     r11, rsp
0x18002b493  push    rsi
0x18002b494  push    rdi
0x18002b495  push    r14
0x18002b497  push    r15
0x18002b499  sub     rsp, 98h
0x18002b4a0  mov     r15d, r9d
0x18002b4a3  mov     r14d, r8d
0x18002b4a6  mov     rsi, rdx
0x18002b4a9  mov     rdi, rcx
0x18002b4ac  mov     qword ptr [r11-68h], 0
0x18002b4b4  mov     dword ptr [r11+10h], 0
0x18002b4bc  mov     qword ptr [r11-78h], 0
0x18002b4c4  mov     qword ptr [r11-60h], 0
0x18002b4cc  xorps   xmm0, xmm0
0x18002b4cf  xor     eax, eax
0x18002b4d1  movups  [rsp+0B8h+var_40], xmm0
0x18002b4d6  mov     [r11-30h], rax
0x18002b4da  xorps   xmm1, xmm1
0x18002b4dd  movups  [rsp+0B8h+var_58], xmm1
0x18002b4e2  mov     [r11-48h], rax
0x18002b4e6  mov     [r11-70h], rax
0x18002b4ea  test    rdx, rdx
0x18002b4ed  jnz     short loc_18002B4F9
0x18002b4ef  mov     eax, 80100011h
0x18002b4f4  jmp     loc_18002B71D
0x18002b4f9  lea     r8, [rsp+0B8h+pHandle]; pHandle
0x18002b4fe  lea     rdx, [rsp+0B8h+pEncodedSize]; pEncodedSize
0x18002b506  lea     rcx, [rsp+0B8h+pBuffer]; pBuffer
0x18002b50b  call    cs:__imp_MesEncodeDynBufferHandleCreate
0x18002b511  test    eax, eax
0x18002b513  jz      short loc_18002B51F
0x18002b515  mov     edi, 8010001Fh
0x18002b51a  jmp     loc_18002B6F6
0x18002b51f  test    rdi, rdi
0x18002b522  jz      short loc_18002B555
0x18002b524  mov     edx, [rdi+8]
0x18002b527  mov     dword ptr [rsp+0B8h+var_58], edx
0x18002b52b  mov     eax, [rdi+0Ch]
0x18002b52e  mov     dword ptr [rsp+0B8h+var_58+4], eax
0x18002b532  mov     rcx, [rdi+10h]
0x18002b536  mov     qword ptr [rsp+0B8h+var_58+8], rcx
0x18002b53b  mov     dword ptr [rsp+0B8h+var_40], edx
0x18002b53f  mov     dword ptr [rsp+0B8h+var_40+4], eax
0x18002b543  mov     qword ptr [rsp+0B8h+var_40+8], rcx
0x18002b54b  mov     rax, [rdi]
0x18002b54e  mov     [rsp+0B8h+lpCriticalSection], rax
0x18002b553  jmp     short loc_18002B596
0x18002b555  mov     qword ptr [rsp+0B8h+var_58+8], 0
0x18002b55e  mov     qword ptr [rsp+0B8h+var_40+8], 0
0x18002b56a  mov     dword ptr [rsp+0B8h+var_58], 0
0x18002b572  mov     dword ptr [rsp+0B8h+var_40], 0
0x18002b57a  lea     rcx, [rsp+0B8h+lpCriticalSection]; struct _REDIRECTION_CONTEXT **
0x18002b57f  call    ?RedirectionContextLookup@@YAKPEAPEAU_REDIRECTION_CONTEXT@@@Z; RedirectionContextLookup(_REDIRECTION_CONTEXT * *)
0x18002b584  test    eax, eax
0x18002b586  jz      short loc_18002B596
0x18002b588  mov     ecx, eax; int
0x18002b58a  call    ?_MakeSCardError@@YAJJ@Z; _MakeSCardError(long)
0x18002b58f  mov     edi, eax
0x18002b591  jmp     loc_18002B6F6
0x18002b596  test    r14d, r14d
0x18002b599  jz      loc_18002B624
0x18002b59f  mov     [rsp+0B8h+var_48], rsi
0x18002b5a4  lea     rax, [rsp+0B8h+var_58]
0x18002b5a9  mov     [rsp+0B8h+pObject], rax; pObject
0x18002b5ae  mov     [rsp+0B8h+nTypeIndex], 5; nTypeIndex
0x18002b5b6  lea     r9, ArrTypeOffset; ArrTypeOffset
0x18002b5bd  lea     r8, pProxyInfo; pProxyInfo
0x18002b5c4  lea     rdx, pPicklingInfo; pPicklingInfo
0x18002b5cb  mov     rcx, [rsp+0B8h+pHandle]; Handle
0x18002b5d0  call    cs:__imp_NdrMesTypeEncode3
0x18002b5d6  jmp     loc_18002B65F
0x18002b5db  mov     edi, eax
0x18002b5dd  mov     edx, 2
0x18002b5e2  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18002b5e7  lea     rax, WPP_GLOBAL_Control
0x18002b5ee  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b5f5  cmp     rcx, rax
0x18002b5f8  jz      short loc_18002B61F
0x18002b5fa  test    byte ptr [rcx+1Ch], 8
0x18002b5fe  jz      short loc_18002B61F
0x18002b600  cmp     byte ptr [rcx+19h], 2
0x18002b604  jb      short loc_18002B61F
0x18002b606  mov     edx, 2Ch ; ','
0x18002b60b  mov     [rsp+0B8h+nTypeIndex], edi
0x18002b60f  lea     r8, WPP_2af0b27572d33e35ea5753758eafaaae_Traceguids
0x18002b616  mov     rcx, [rcx+10h]
0x18002b61a  call    WPP_SF_sd
0x18002b61f  jmp     loc_18002B6F6
0x18002b624  mov     [rsp+0B8h+var_30], rsi
0x18002b62c  lea     rax, [rsp+0B8h+var_40]
0x18002b631  mov     [rsp+0B8h+pObject], rax; pObject
0x18002b636  mov     [rsp+0B8h+nTypeIndex], 4; nTypeIndex
0x18002b63e  lea     r9, ArrTypeOffset; ArrTypeOffset
0x18002b645  lea     r8, pProxyInfo; pProxyInfo
0x18002b64c  lea     rdx, pPicklingInfo; pPicklingInfo
0x18002b653  mov     rcx, [rsp+0B8h+pHandle]; Handle
0x18002b658  call    cs:__imp_NdrMesTypeEncode3
0x18002b65e  nop
0x18002b65f  mov     [rsp+0B8h+var_88], 800h; unsigned int
0x18002b667  mov     dword ptr [rsp+0B8h+pObject], 0FFFFFFFFh; dwMilliseconds
0x18002b66f  mov     rax, [rsp+0B8h+lpCriticalSection]
0x18002b674  mov     qword ptr [rsp+0B8h+nTypeIndex], rax; lpCriticalSection
0x18002b679  lea     r9, [rsp+0B8h+var_60]; struct _BUFFER_LIST_STRUCT **
0x18002b67e  mov     r8d, [rsp+0B8h+pEncodedSize]; InputBufferLength
0x18002b686  mov     rdx, [rsp+0B8h+pBuffer]; InputBuffer
0x18002b68b  mov     ecx, r15d; IoControlCode
0x18002b68e  call    ?_SendSCardIOCTL@@YAJKPEAXKPEAPEAU_BUFFER_LIST_STRUCT@@PEAU_REDIRECTION_CONTEXT@@KK@Z; _SendSCardIOCTL(ulong,void *,ulong,_BUFFER_LIST_STRUCT * *,_REDIRECTION_CONTEXT *,ulong,ulong)
0x18002b693  test    eax, eax
0x18002b695  jnz     loc_18002B588
0x18002b69b  mov     rcx, [rsp+0B8h+var_60]
0x18002b6a0  mov     edx, [rcx+1Ch]; unsigned int
0x18002b6a3  mov     rcx, [rcx+10h]; unsigned __int8 *
0x18002b6a7  call    ?I_DecodeLongReturn@@YAJPEAEK@Z; I_DecodeLongReturn(uchar *,ulong)
0x18002b6ac  jmp     loc_18002B58F
0x18002b6b1  mov     edi, eax
0x18002b6b3  mov     edx, 2
0x18002b6b8  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18002b6bd  lea     rax, WPP_GLOBAL_Control
0x18002b6c4  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b6cb  cmp     rcx, rax
0x18002b6ce  jz      short loc_18002B6F6
0x18002b6d0  test    byte ptr [rcx+1Ch], 8
0x18002b6d4  jz      short loc_18002B6F6
0x18002b6d6  cmp     byte ptr [rcx+19h], 2
0x18002b6da  jb      short loc_18002B6F6
0x18002b6dc  mov     edx, 2Dh ; '-'
0x18002b6e1  mov     [rsp+0B8h+nTypeIndex], edi
0x18002b6e5  lea     r8, WPP_2af0b27572d33e35ea5753758eafaaae_Traceguids
0x18002b6ec  mov     rcx, [rcx+10h]
0x18002b6f0  call    WPP_SF_sd
0x18002b6f5  nop
0x18002b6f6  lea     rcx, [rsp+0B8h+pHandle]; void **
0x18002b6fb  call    ?SafeMesHandleFree@@YAXPEAPEAX@Z; SafeMesHandleFree(void * *)
0x18002b700  mov     rcx, [rsp+0B8h+pBuffer]; void *
0x18002b705  call    MIDL_user_free
0x18002b70a  mov     rax, [rsp+0B8h+var_60]
0x18002b70f  test    rax, rax
0x18002b712  jz      short loc_18002B71B
0x18002b714  mov     dword ptr [rax+8], 0
0x18002b71b  mov     eax, edi
0x18002b71d  add     rsp, 98h
0x18002b724  pop     r15
0x18002b726  pop     r14
0x18002b728  pop     rdi
0x18002b729  pop     rsi
0x18002b72a  retn
```
