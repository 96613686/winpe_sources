# SampDecodeIntoClaimsSet(void *,void *,ulong,void * *,_SAM_CLAIMS_SET * *)

- ea: `0x18004bb90`
- end: `0x18004bead`
- name: `?SampDecodeIntoClaimsSet@@YAXPEAX0KPEAPEAXPEAPEAU_SAM_CLAIMS_SET@@@Z`
- size: `797`
- prototype: `void __fastcall(void *, char *Buffer, unsigned int BufferSize, handle_t *pHandle, struct _SAM_CLAIMS_SET **)`
- caller_count: `3`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18003d430`
- `0x18004c4ec`
- `0x18004d6b0`

## callees

- `0x18004bb90`
- `0x18004ca1c`
- `0x18004d088`
- `0x18004d840`

## import_xrefs

- `ntdll!RtlDecompressBufferEx` at `0x18004bd2d`
- `ntdll!RtlDecompressBufferEx` at `0x18004bd2d`
- `ntdll!RtlGetCompressionWorkSpaceSize` at `0x18004bca9`
- `ntdll!RtlGetCompressionWorkSpaceSize` at `0x18004bca9`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18004bcc7`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18004bcf2`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18004bcc7`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18004bcf2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004bdf0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004be47`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004bdf0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004be47`
- `RPCRT4!I_RpcExceptionFilter` at `0x1800bb8e5`
- `RPCRT4!I_RpcExceptionFilter` at `0x1800bb901`
- `RPCRT4!I_RpcExceptionFilter` at `0x1800bb8e5`
- `RPCRT4!I_RpcExceptionFilter` at `0x1800bb901`
- `RPCRT4!MesDecodeBufferHandleCreate` at `0x18004bc15`
- `RPCRT4!MesDecodeBufferHandleCreate` at `0x18004bd51`
- `RPCRT4!MesDecodeBufferHandleCreate` at `0x18004bc15`
- `RPCRT4!MesDecodeBufferHandleCreate` at `0x18004bd51`
- `RPCRT4!NdrMesTypeDecode3` at `0x18004bc57`
- `RPCRT4!NdrMesTypeDecode3` at `0x18004bd87`
- `RPCRT4!NdrMesTypeDecode3` at `0x18004bc57`
- `RPCRT4!NdrMesTypeDecode3` at `0x18004bd87`
- `RPCRT4!NdrMesTypeFree3` at `0x18004be2e`
- `RPCRT4!NdrMesTypeFree3` at `0x18004be2e`
- `RPCRT4!MesHandleFree` at `0x18004be39`
- `RPCRT4!MesHandleFree` at `0x18004be39`

## pseudocode

```c
void __fastcall SampDecodeIntoClaimsSet(
        void *a1,
        char *Buffer,
        unsigned int BufferSize,
        handle_t *pHandle,
        struct _SAM_CLAIMS_SET **a5)
{
  struct _SAM_CLAIMS_SET **v7; // rax
  HLOCAL v8; // r15
  char *v9; // r14
  NTSTATUS CompressionWorkSpaceSize; // edi
  USHORT v11; // cx
  unsigned int v12; // r12d
  handle_t v13; // rcx
  int v14; // [rsp+40h] [rbp-68h] BYREF
  ULONG CompressBufferWorkSpaceSize; // [rsp+44h] [rbp-64h] BYREF
  _DWORD *pObject; // [rsp+48h] [rbp-60h] BYREF
  struct _SAM_CLAIMS_SET *v17; // [rsp+50h] [rbp-58h] BYREF
  char *v18; // [rsp+58h] [rbp-50h]
  handle_t pHandlea; // [rsp+60h] [rbp-48h] BYREF
  HLOCAL v20; // [rsp+68h] [rbp-40h]
  ULONG CompressFragmentWorkSpaceSize; // [rsp+B8h] [rbp+10h] BYREF
  handle_t *v22; // [rsp+C8h] [rbp+20h]

  v22 = pHandle;
  pHandlea = 0;
  pObject = 0;
  v14 = 0;
  CompressBufferWorkSpaceSize = 0;
  CompressFragmentWorkSpaceSize = 0;
  v17 = 0;
  if ( !Buffer || !BufferSize )
  {
LABEL_33:
    if ( pHandle )
      *pHandle = 0;
    goto LABEL_35;
  }
  if ( pHandle )
  {
    v7 = a5;
    if ( a5 )
    {
      v8 = 0;
      v20 = 0;
      v9 = 0;
      *pHandle = 0;
      *v7 = 0;
      if ( MesDecodeBufferHandleCreate(Buffer, BufferSize, &pHandlea) )
      {
LABEL_6:
        CompressionWorkSpaceSize = -1073741811;
        goto LABEL_20;
      }
      NdrMesTypeDecode3(
        pHandlea,
        &pPicklingInfo,
        &claims_private_ProxyInfo,
        (const unsigned int **)&ArrTypeOffset,
        1u,
        &pObject);
      v11 = *((_WORD *)pObject + 8);
      if ( !v11 )
      {
        v12 = *pObject;
        v9 = (char *)*((_QWORD *)pObject + 1);
        v18 = v9;
        goto LABEL_16;
      }
      CompressionWorkSpaceSize = RtlGetCompressionWorkSpaceSize(
                                   v11,
                                   &CompressBufferWorkSpaceSize,
                                   &CompressFragmentWorkSpaceSize);
      if ( CompressionWorkSpaceSize >= 0 )
      {
        v8 = LocalAlloc(0x40u, CompressFragmentWorkSpaceSize);
        v20 = v8;
        if ( v8 && (v12 = pObject[5], v9 = (char *)LocalAlloc(0x40u, v12), (v18 = v9) != 0) )
        {
          CompressionWorkSpaceSize = RtlDecompressBufferEx(
                                       *((unsigned __int16 *)pObject + 8),
                                       v9,
                                       v12,
                                       *((_QWORD *)pObject + 1),
                                       *pObject,
                                       &v14,
                                       v8);
          if ( CompressionWorkSpaceSize >= 0 )
          {
            if ( v14 != v12 )
              goto LABEL_6;
LABEL_16:
            if ( !MesDecodeBufferHandleCreate(v9, v12, pHandle) )
            {
              NdrMesTypeDecode3(
                *pHandle,
                &pPicklingInfo,
                &claims_private_ProxyInfo,
                (const unsigned int **)&ArrTypeOffset,
                0,
                &v17);
              CompressionWorkSpaceSize = SampValidateAndFilterClaimsSetInPlace(a1, v17);
              if ( !CompressionWorkSpaceSize )
              {
                *a5 = v17;
                v17 = 0;
              }
              goto LABEL_20;
            }
            goto LABEL_6;
          }
        }
        else
        {
          CompressionWorkSpaceSize = -1073741801;
        }
      }
LABEL_20:
      if ( v9 && v9 != *((char **)pObject + 1) )
        LocalFree(v9);
      v13 = pHandlea;
      if ( pHandlea )
      {
        if ( pObject )
        {
          NdrMesTypeFree3(
            pHandlea,
            &pPicklingInfo,
            &claims_private_ProxyInfo,
            (const unsigned int **)&ArrTypeOffset,
            1u,
            &pObject);
          v13 = pHandlea;
        }
        MesHandleFree(v13);
      }
      if ( v8 )
        LocalFree(v8);
      if ( CompressionWorkSpaceSize < 0 )
      {
        if ( *pHandle )
          SamIFreeDecodedClaimsSet(*pHandle);
        v17 = 0;
        *pHandle = 0;
        *a5 = 0;
        SampLogNDRError(a1, CompressionWorkSpaceSize, 0);
      }
      return;
    }
    goto LABEL_33;
  }
LABEL_35:
  if ( a5 )
    *a5 = 0;
}

```

## disassembly

```asm
0x18004bb90  mov     rax, rsp
0x18004bb93  mov     [rax+20h], r9
0x18004bb97  mov     [rax+8], rcx
0x18004bb9b  push    rbx
0x18004bb9c  push    rsi
0x18004bb9d  push    rdi
0x18004bb9e  push    r12
0x18004bba0  push    r13
0x18004bba2  push    r14
0x18004bba4  push    r15
0x18004bba6  sub     rsp, 70h
0x18004bbaa  mov     rsi, r9
0x18004bbad  mov     r9d, r8d
0x18004bbb0  mov     r10, rdx
0x18004bbb3  mov     r13, rcx
0x18004bbb6  xor     ebx, ebx
0x18004bbb8  mov     [rax-48h], rbx
0x18004bbbc  mov     [rax-60h], rbx
0x18004bbc0  mov     [rax-68h], ebx
0x18004bbc3  mov     [rax-64h], ebx
0x18004bbc6  mov     [rax+10h], ebx
0x18004bbc9  mov     [rax-58h], rbx
0x18004bbcd  test    rdx, rdx
0x18004bbd0  jz      loc_18004BE85
0x18004bbd6  test    r8d, r8d
0x18004bbd9  jz      loc_18004BE85
0x18004bbdf  test    rsi, rsi
0x18004bbe2  jz      loc_18004BE8D
0x18004bbe8  mov     rax, [rsp+0A8h+arg_20]
0x18004bbf0  test    rax, rax
0x18004bbf3  jz      loc_18004BE85
0x18004bbf9  mov     r15d, ebx
0x18004bbfc  mov     [rsp+0A8h+var_40], rbx
0x18004bc01  mov     r14d, ebx
0x18004bc04  mov     [rsi], rbx
0x18004bc07  mov     [rax], rbx
0x18004bc0a  lea     r8, [rsp+0A8h+pHandle]; pHandle
0x18004bc0f  mov     edx, r9d; BufferSize
0x18004bc12  mov     rcx, r10; Buffer
0x18004bc15  call    cs:__imp_MesDecodeBufferHandleCreate
0x18004bc1b  mov     edi, eax
0x18004bc1d  test    eax, eax
0x18004bc1f  jz      short loc_18004BC2B
0x18004bc21  mov     edi, 0C000000Dh
0x18004bc26  jmp     loc_18004BDDD
0x18004bc2b  lea     rax, [rsp+0A8h+var_60]
0x18004bc30  mov     [rsp+0A8h+pObject], rax; pObject
0x18004bc35  mov     [rsp+0A8h+nTypeIndex], 1; nTypeIndex
0x18004bc3d  lea     r9, ArrTypeOffset; ArrTypeOffset
0x18004bc44  lea     r8, ?claims_private_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x18004bc4b  lea     rdx, pPicklingInfo; pPicklingInfo
0x18004bc52  mov     rcx, [rsp+0A8h+pHandle]; Handle
0x18004bc57  call    cs:__imp_NdrMesTypeDecode3
0x18004bc5d  jmp     short loc_18004BC79
0x18004bc5f  mov     edi, eax
0x18004bc61  xor     ebx, ebx
0x18004bc63  mov     rsi, [rsp+0A8h+arg_18]
0x18004bc6b  mov     r13, [rsp+0A8h+arg_0]
0x18004bc73  mov     r15d, ebx
0x18004bc76  mov     r14d, ebx
0x18004bc79  test    edi, edi
0x18004bc7b  jnz     short loc_18004BC21
0x18004bc7d  mov     rax, [rsp+0A8h+var_60]
0x18004bc82  movzx   ecx, word ptr [rax+10h]; CompressionFormatAndEngine
0x18004bc86  test    cx, cx
0x18004bc89  jnz     short loc_18004BC9C
0x18004bc8b  mov     r12d, [rax]
0x18004bc8e  mov     r14, [rax+8]
0x18004bc92  mov     [rsp+0A8h+var_50], r14
0x18004bc97  jmp     loc_18004BD48
0x18004bc9c  lea     r8, [rsp+0A8h+CompressFragmentWorkSpaceSize]; CompressFragmentWorkSpaceSize
0x18004bca4  lea     rdx, [rsp+0A8h+CompressBufferWorkSpaceSize]; CompressBufferWorkSpaceSize
0x18004bca9  call    cs:__imp_RtlGetCompressionWorkSpaceSize
0x18004bcaf  mov     edi, eax
0x18004bcb1  test    eax, eax
0x18004bcb3  js      loc_18004BDDD
0x18004bcb9  mov     edx, [rsp+0A8h+CompressFragmentWorkSpaceSize]; uBytes
0x18004bcc0  mov     edi, 40h ; '@'
0x18004bcc5  mov     ecx, edi; uFlags
0x18004bcc7  call    cs:__imp_LocalAlloc
0x18004bccd  mov     r15, rax
0x18004bcd0  mov     [rsp+0A8h+var_40], rax
0x18004bcd5  test    rax, rax
0x18004bcd8  jnz     short loc_18004BCE4
0x18004bcda  mov     edi, 0C0000017h
0x18004bcdf  jmp     loc_18004BDDD
0x18004bce4  mov     rax, [rsp+0A8h+var_60]
0x18004bce9  mov     r12d, [rax+14h]
0x18004bced  mov     edx, r12d; uBytes
0x18004bcf0  mov     ecx, edi; uFlags
0x18004bcf2  call    cs:__imp_LocalAlloc
0x18004bcf8  mov     r14, rax
0x18004bcfb  mov     [rsp+0A8h+var_50], rax
0x18004bd00  test    rax, rax
0x18004bd03  jz      short loc_18004BCDA
0x18004bd05  mov     [rsp+0A8h+var_78], r15
0x18004bd0a  lea     rax, [rsp+0A8h+var_68]
0x18004bd0f  mov     [rsp+0A8h+pObject], rax
0x18004bd14  mov     rcx, [rsp+0A8h+var_60]
0x18004bd19  mov     eax, [rcx]
0x18004bd1b  mov     [rsp+0A8h+nTypeIndex], eax
0x18004bd1f  mov     r9, [rcx+8]
0x18004bd23  mov     r8d, r12d
0x18004bd26  mov     rdx, r14
0x18004bd29  movzx   ecx, word ptr [rcx+10h]
0x18004bd2d  call    cs:__imp_RtlDecompressBufferEx
0x18004bd33  mov     edi, eax
0x18004bd35  test    eax, eax
0x18004bd37  js      loc_18004BDDD
0x18004bd3d  cmp     [rsp+0A8h+var_68], r12d
0x18004bd42  jnz     loc_18004BC21
0x18004bd48  mov     r8, rsi; pHandle
0x18004bd4b  mov     edx, r12d; BufferSize
0x18004bd4e  mov     rcx, r14; Buffer
0x18004bd51  call    cs:__imp_MesDecodeBufferHandleCreate
0x18004bd57  mov     edi, eax
0x18004bd59  test    eax, eax
0x18004bd5b  jnz     loc_18004BC21
0x18004bd61  lea     rax, [rsp+0A8h+var_58]
0x18004bd66  mov     [rsp+0A8h+pObject], rax; pObject
0x18004bd6b  mov     [rsp+0A8h+nTypeIndex], ebx; nTypeIndex
0x18004bd6f  lea     r9, ArrTypeOffset; ArrTypeOffset
0x18004bd76  lea     r8, ?claims_private_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x18004bd7d  lea     rdx, pPicklingInfo; pPicklingInfo
0x18004bd84  mov     rcx, [rsi]; Handle
0x18004bd87  call    cs:__imp_NdrMesTypeDecode3
0x18004bd8d  jmp     short loc_18004BDAD
0x18004bd8f  mov     edi, eax
0x18004bd91  xor     ebx, ebx
0x18004bd93  mov     rsi, [rsp+0A8h+arg_18]
0x18004bd9b  mov     r13, [rsp+0A8h+arg_0]
0x18004bda3  mov     r15, [rsp+0A8h+var_40]
0x18004bda8  mov     r14, [rsp+0A8h+var_50]
0x18004bdad  test    edi, edi
0x18004bdaf  jnz     loc_18004BC21
0x18004bdb5  mov     rdx, [rsp+0A8h+var_58]; struct _SAM_CLAIMS_SET *
0x18004bdba  mov     rcx, r13; void *
0x18004bdbd  call    ?SampValidateAndFilterClaimsSetInPlace@@YAJPEAXPEAU_SAM_CLAIMS_SET@@@Z; SampValidateAndFilterClaimsSetInPlace(void *,_SAM_CLAIMS_SET *)
0x18004bdc2  mov     edi, eax
0x18004bdc4  test    eax, eax
0x18004bdc6  jnz     short loc_18004BDDD
0x18004bdc8  mov     rcx, [rsp+0A8h+var_58]
0x18004bdcd  mov     rax, [rsp+0A8h+arg_20]
0x18004bdd5  mov     [rax], rcx
0x18004bdd8  mov     [rsp+0A8h+var_58], rbx
0x18004bddd  test    r14, r14
0x18004bde0  jz      short loc_18004BDF6
0x18004bde2  mov     rax, [rsp+0A8h+var_60]
0x18004bde7  cmp     r14, [rax+8]
0x18004bdeb  jz      short loc_18004BDF6
0x18004bded  mov     rcx, r14; hMem
0x18004bdf0  call    cs:__imp_LocalFree
0x18004bdf6  mov     rcx, [rsp+0A8h+pHandle]; Handle
0x18004bdfb  test    rcx, rcx
0x18004bdfe  jz      short loc_18004BE3F
0x18004be00  cmp     [rsp+0A8h+var_60], rbx
0x18004be05  jz      short loc_18004BE39
0x18004be07  lea     rax, [rsp+0A8h+var_60]
0x18004be0c  mov     [rsp+0A8h+pObject], rax; pObject
0x18004be11  mov     [rsp+0A8h+nTypeIndex], 1; nTypeIndex
0x18004be19  lea     r9, ArrTypeOffset; ArrTypeOffset
0x18004be20  lea     r8, ?claims_private_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x18004be27  lea     rdx, pPicklingInfo; pPicklingInfo
0x18004be2e  call    cs:__imp_NdrMesTypeFree3
0x18004be34  mov     rcx, [rsp+0A8h+pHandle]; Handle
0x18004be39  call    cs:__imp_MesHandleFree
0x18004be3f  test    r15, r15
0x18004be42  jz      short loc_18004BE4D
0x18004be44  mov     rcx, r15; hMem
0x18004be47  call    cs:__imp_LocalFree
0x18004be4d  test    edi, edi
0x18004be4f  jns     short loc_18004BE9D
0x18004be51  cmp     [rsi], rbx
0x18004be54  jz      short loc_18004BE63
0x18004be56  mov     rdx, [rsp+0A8h+var_58]
0x18004be5b  mov     rcx, [rsi]; Handle
0x18004be5e  call    SamIFreeDecodedClaimsSet
0x18004be63  mov     [rsp+0A8h+var_58], rbx
0x18004be68  mov     [rsi], rbx
0x18004be6b  mov     rax, [rsp+0A8h+arg_20]
0x18004be73  mov     [rax], rbx
0x18004be76  xor     r8d, r8d; unsigned __int8
0x18004be79  mov     edx, edi; int
0x18004be7b  mov     rcx, r13; void *
0x18004be7e  call    ?SampLogNDRError@@YAXPEAXJE@Z; SampLogNDRError(void *,long,uchar)
0x18004be83  jmp     short loc_18004BE9D
0x18004be85  test    rsi, rsi
0x18004be88  jz      short loc_18004BE8D
0x18004be8a  mov     [rsi], rbx
0x18004be8d  mov     rax, [rsp+0A8h+arg_20]
0x18004be95  test    rax, rax
0x18004be98  jz      short loc_18004BE9D
0x18004be9a  mov     [rax], rbx
0x18004be9d  add     rsp, 70h
0x18004bea1  pop     r15
0x18004bea3  pop     r14
0x18004bea5  pop     r13
0x18004bea7  pop     r12
0x18004bea9  pop     rdi
0x18004beaa  pop     rsi
0x18004beab  pop     rbx
0x18004beac  retn
0x1800bb8d7  push    rbp
0x1800bb8d9  sub     rsp, 40h
0x1800bb8dd  mov     rbp, rdx
0x1800bb8e0  mov     rcx, [rcx]
0x1800bb8e3  mov     ecx, [rcx]; ExceptionCode
0x1800bb8e5  call    cs:__imp_I_RpcExceptionFilter
0x1800bb8eb  nop
0x1800bb8ec  add     rsp, 40h
0x1800bb8f0  pop     rbp
0x1800bb8f1  retn
0x1800bb8f3  push    rbp
0x1800bb8f5  sub     rsp, 40h
0x1800bb8f9  mov     rbp, rdx
0x1800bb8fc  mov     rcx, [rcx]
0x1800bb8ff  mov     ecx, [rcx]; ExceptionCode
0x1800bb901  call    cs:__imp_I_RpcExceptionFilter
0x1800bb907  nop
0x1800bb908  add     rsp, 40h
0x1800bb90c  pop     rbp
0x1800bb90d  retn
```
