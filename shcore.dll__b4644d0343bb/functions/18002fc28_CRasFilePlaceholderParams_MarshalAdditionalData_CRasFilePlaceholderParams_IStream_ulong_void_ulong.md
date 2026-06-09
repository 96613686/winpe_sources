# CRasFilePlaceholderParams::MarshalAdditionalData(CRasFilePlaceholderParams *,IStream *,ulong,void *,ulong)

- ea: `0x18002fc28`
- end: `0x18002fdb2`
- name: `?MarshalAdditionalData@CRasFilePlaceholderParams@@SAJPEAV1@PEAUIStream@@KPEAXK@Z`
- size: `394`
- prototype: `static int(struct CRasFilePlaceholderParams *, struct IStream *, unsigned int, void *, unsigned int)`
- caller_count: `2`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18002f810`
- `0x18007b0a0`

## callees

- `0x18000ddd4`
- `0x18002fa60`
- `0x18002fc28`
- `0x18002ffd0`
- `0x180064f08`
- `0x180064f9c`
- `0x180095010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x18002fd09`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x18002fd2f`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x18002fd55`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x18002fd09`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x18002fd2f`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x18002fd55`

## pseudocode

```c
__int64 __fastcall CRasFilePlaceholderParams::MarshalAdditionalData(
        struct CRasFilePlaceholderParams *a1,
        struct IStream *a2,
        DWORD a3,
        void *a4,
        DWORD mshlflags)
{
  __int64 ParamsUnderLock; // rax
  __int64 v9; // rax
  HRESULT v10; // ebx
  DWORD v11; // esi
  LPUNKNOWN pUnk[2]; // [rsp+30h] [rbp-50h] BYREF
  LPUNKNOWN v14[2]; // [rsp+40h] [rbp-40h] BYREF
  int pv; // [rsp+50h] [rbp-30h] BYREF
  _BYTE v16[40]; // [rsp+58h] [rbp-28h] BYREF
  int v17; // [rsp+B0h] [rbp+30h] BYREF
  int v18; // [rsp+B8h] [rbp+38h] BYREF

  v17 = 0;
  pv = 0;
  *(_OWORD *)pUnk = 0;
  *(_OWORD *)v14 = 0;
  if ( a1 )
  {
    ParamsUnderLock = CRasFilePlaceholderParams::_GetParamsUnderLock(a1, v16, 0, 0);
    RAS_FILE_PLACEHOLDER_PARAMS::operator=(pUnk, ParamsUnderLock);
    RAS_FILE_PLACEHOLDER_PARAMS::~RAS_FILE_PLACEHOLDER_PARAMS((RAS_FILE_PLACEHOLDER_PARAMS *)v16);
    if ( pUnk[0] )
      v17 = 1;
  }
  v9 = *(_QWORD *)a2;
  v18 = 0;
  v10 = (*(__int64 (__fastcall **)(struct IStream *, int *, __int64, int *))(v9 + 32))(a2, &v17, 4, &v18);
  if ( v10 >= 0 )
  {
    if ( v18 == 4 )
    {
      if ( v17 )
      {
        v11 = mshlflags;
        v10 = CoMarshalInterface(a2, &GUID_ae9d26fb_2297_4a4a_9930_5e4d91f29882, pUnk[0], a3, a4, mshlflags);
        if ( v10 >= 0 )
        {
          v10 = CoMarshalInterface(a2, &GUID_0095a475_f357_475c_a5b7_cb183e48a1be, pUnk[1], a3, a4, v11);
          if ( v10 >= 0 )
          {
            v10 = CoMarshalInterface(a2, &GUID_c8b34e60_6ee3_4881_9138_6b4fb6bfb461, v14[0], a3, a4, v11);
            if ( v10 >= 0 )
              v10 = IStream_Write(a2, &pv, 4u);
          }
        }
      }
    }
    else
    {
      v10 = -2147467259;
    }
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationCompletedHandler<bool>>::InternalRelease(&v14[1]);
  Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationCompletedHandler<bool>>::InternalRelease(v14);
  Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationCompletedHandler<bool>>::InternalRelease(&pUnk[1]);
  Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationCompletedHandler<bool>>::InternalRelease(pUnk);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18002fc28  mov     [rsp-28h+arg_10], rbx
0x18002fc2d  push    rbp
0x18002fc2e  push    rsi
0x18002fc2f  push    rdi
0x18002fc30  push    r14
0x18002fc32  push    r15
0x18002fc34  mov     rbp, rsp
0x18002fc37  sub     rsp, 80h
0x18002fc3e  mov     [rbp+arg_0], 0
0x18002fc45  xorps   xmm0, xmm0
0x18002fc48  mov     [rbp+pv], 0
0x18002fc4f  xorps   xmm1, xmm1
0x18002fc52  mov     r14, r9
0x18002fc55  mov     r15d, r8d
0x18002fc58  mov     rdi, rdx
0x18002fc5b  movdqu  xmmword ptr [rbp+pUnk], xmm0
0x18002fc60  movdqu  xmmword ptr [rbp+var_40], xmm1
0x18002fc65  test    rcx, rcx
0x18002fc68  jz      short loc_18002FC9C
0x18002fc6a  xor     r9d, r9d
0x18002fc6d  lea     rdx, [rbp+var_28]
0x18002fc71  xor     r8d, r8d
0x18002fc74  call    ?_GetParamsUnderLock@CRasFilePlaceholderParams@@AEAA?AURAS_FILE_PLACEHOLDER_PARAMS@@PEA_K0@Z; CRasFilePlaceholderParams::_GetParamsUnderLock(unsigned __int64 *,unsigned __int64 *)
0x18002fc79  mov     rdx, rax
0x18002fc7c  lea     rcx, [rbp+pUnk]
0x18002fc80  call    ??4RAS_FILE_PLACEHOLDER_PARAMS@@QEAAAEAU0@AEBU0@@Z; RAS_FILE_PLACEHOLDER_PARAMS::operator=(RAS_FILE_PLACEHOLDER_PARAMS const &)
0x18002fc85  lea     rcx, [rbp+var_28]; this
0x18002fc89  call    ??1RAS_FILE_PLACEHOLDER_PARAMS@@QEAA@XZ; RAS_FILE_PLACEHOLDER_PARAMS::~RAS_FILE_PLACEHOLDER_PARAMS(void)
0x18002fc8e  cmp     [rbp+pUnk], 0
0x18002fc93  jz      short loc_18002FC9C
0x18002fc95  mov     [rbp+arg_0], 1
0x18002fc9c  mov     rax, [rdi]
0x18002fc9f  lea     r9, [rbp+arg_8]
0x18002fca3  mov     r8d, 4
0x18002fca9  mov     [rbp+arg_8], 0
0x18002fcb0  lea     rdx, [rbp+arg_0]
0x18002fcb4  mov     rcx, rdi
0x18002fcb7  mov     rax, [rax+20h]
0x18002fcbb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fcc0  mov     ebx, eax
0x18002fcc2  test    eax, eax
0x18002fcc4  js      loc_18002FD75
0x18002fcca  cmp     [rbp+arg_8], 4
0x18002fcce  jz      short loc_18002FCDA
0x18002fcd0  mov     ebx, 80004005h
0x18002fcd5  jmp     loc_18002FD75
0x18002fcda  test    eax, eax
0x18002fcdc  js      loc_18002FD75
0x18002fce2  cmp     [rbp+arg_0], 0
0x18002fce6  jz      loc_18002FD75
0x18002fcec  mov     esi, [rbp+arg_20]
0x18002fcef  lea     rdx, _GUID_ae9d26fb_2297_4a4a_9930_5e4d91f29882; riid
0x18002fcf6  mov     r8, [rbp+pUnk]; pUnk
0x18002fcfa  mov     r9d, r15d; dwDestContext
0x18002fcfd  mov     [rsp+80h+mshlflags], esi; mshlflags
0x18002fd01  mov     rcx, rdi; pStm
0x18002fd04  mov     [rsp+80h+pvDestContext], r14; pvDestContext
0x18002fd09  call    cs:__imp_CoMarshalInterface
0x18002fd0f  mov     ebx, eax
0x18002fd11  test    eax, eax
0x18002fd13  js      short loc_18002FD75
0x18002fd15  mov     r8, [rbp+pUnk+8]; pUnk
0x18002fd19  lea     rdx, _GUID_0095a475_f357_475c_a5b7_cb183e48a1be; riid
0x18002fd20  mov     [rsp+80h+mshlflags], esi; mshlflags
0x18002fd24  mov     r9d, r15d; dwDestContext
0x18002fd27  mov     rcx, rdi; pStm
0x18002fd2a  mov     [rsp+80h+pvDestContext], r14; pvDestContext
0x18002fd2f  call    cs:__imp_CoMarshalInterface
0x18002fd35  mov     ebx, eax
0x18002fd37  test    eax, eax
0x18002fd39  js      short loc_18002FD75
0x18002fd3b  mov     r8, [rbp+var_40]; pUnk
0x18002fd3f  lea     rdx, _GUID_c8b34e60_6ee3_4881_9138_6b4fb6bfb461; riid
0x18002fd46  mov     [rsp+80h+mshlflags], esi; mshlflags
0x18002fd4a  mov     r9d, r15d; dwDestContext
0x18002fd4d  mov     rcx, rdi; pStm
0x18002fd50  mov     [rsp+80h+pvDestContext], r14; pvDestContext
0x18002fd55  call    cs:__imp_CoMarshalInterface
0x18002fd5b  mov     ebx, eax
0x18002fd5d  test    eax, eax
0x18002fd5f  js      short loc_18002FD75
0x18002fd61  mov     r8d, 4; cb
0x18002fd67  lea     rdx, [rbp+pv]; pv
0x18002fd6b  mov     rcx, rdi; pstm
0x18002fd6e  call    IStream_Write
0x18002fd73  mov     ebx, eax
0x18002fd75  lea     rcx, [rbp+var_40+8]
0x18002fd79  call    ?InternalRelease@?$ComPtr@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationCompletedHandler<bool>>::InternalRelease(void)
0x18002fd7e  lea     rcx, [rbp+var_40]
0x18002fd82  call    ?InternalRelease@?$ComPtr@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationCompletedHandler<bool>>::InternalRelease(void)
0x18002fd87  lea     rcx, [rbp+pUnk+8]
0x18002fd8b  call    ?InternalRelease@?$ComPtr@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationCompletedHandler<bool>>::InternalRelease(void)
0x18002fd90  lea     rcx, [rbp+pUnk]
0x18002fd94  call    ?InternalRelease@?$ComPtr@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationCompletedHandler<bool>>::InternalRelease(void)
0x18002fd99  mov     eax, ebx
0x18002fd9b  mov     rbx, [rsp+80h+arg_10]
0x18002fda3  add     rsp, 80h
0x18002fdaa  pop     r15
0x18002fdac  pop     r14
0x18002fdae  pop     rdi
0x18002fdaf  pop     rsi
0x18002fdb0  pop     rbp
0x18002fdb1  retn
```
