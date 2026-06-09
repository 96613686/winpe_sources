# RPCSplGetVirtualPrinterFileToken

- ea: `0x14000d6c0`
- end: `0x14000d858`
- name: `RPCSplGetVirtualPrinterFileToken`
- size: `408`
- prototype: `__int64 __usercall@<rax>(PRPC_ASYNC_STATE pAsync@<rcx>, __int64)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140001b9c`
- `0x140006894`
- `0x140007298`
- `0x1400085d8`
- `0x14000cfd0`
- `0x14000d6c0`

## import_xrefs

- `KERNEL32!LocalFree` at `0x14000d801`
- `KERNEL32!LocalFree` at `0x14000d80b`
- `KERNEL32!LocalFree` at `0x14000d801`
- `KERNEL32!LocalFree` at `0x14000d80b`
- `WINSPOOL!GetPrintOutputInfo` at `0x14000d71e`
- `WINSPOOL!GetPrintOutputInfo` at `0x14000d71e`
- `RPCRT4!RpcAsyncCompleteCall` at `0x14000d841`
- `RPCRT4!RpcAsyncCompleteCall` at `0x14000d841`
- `Print.PrintSupport.Source!GetVirtualPrinterTargetFileToken` at `0x14000d75b`
- `Print.PrintSupport.Source!GetVirtualPrinterTargetFileToken` at `0x14000d75b`

## string_xrefs

- `0x14000d82e`: `RPCSplGetVirtualPrinterFileToken`

## pseudocode

```c
RPC_STATUS __fastcall RPCSplGetVirtualPrinterFileToken(
        PRPC_ASYNC_STATE pAsync,
        __int64 a2,
        unsigned int a3,
        __int64 a4,
        _QWORD *a5)
{
  unsigned int v5; // ebx
  _QWORD *v10; // rsi
  __int64 v11; // rax
  unsigned __int64 v12; // rdi
  _WORD *v13; // rax
  _WORD *v14; // rdx
  _WORD *v15; // rcx
  __int64 v16; // rax
  _WORD *v17; // rcx
  HLOCAL hMem; // [rsp+20h] [rbp-18h] BYREF
  HLOCAL v20[2]; // [rsp+28h] [rbp-10h] BYREF
  int Reply; // [rsp+88h] [rbp+50h] BYREF

  v5 = -2147024809;
  Reply = -2147024809;
  if ( !a2 )
    goto LABEL_24;
  v10 = a5;
  if ( !a5 )
    goto LABEL_24;
  TLoad64BitDllsMgr::IncUIRefCnt(pGLdrObj);
  v20[0] = 0;
  Reply = GetPrintOutputInfo(a4, a2, 0, v20);
  if ( Reply >= 0 && v20[0] )
  {
    Reply = CheckClientProcessAndEncryptFile(a3, (unsigned __int16 *)v20[0]);
    hMem = 0;
    if ( Reply >= 0 )
    {
      Reply = GetVirtualPrinterTargetFileToken(v20[0], &hMem);
      if ( Reply >= 0 )
      {
        v11 = -1;
        do
          ++v11;
        while ( *((_WORD *)hMem + v11) );
        v12 = (unsigned int)(v11 + 1);
        v13 = operator new[](2 * v12);
        *v10 = v13;
        v14 = v13;
        if ( v13 )
        {
          if ( v12 )
          {
            if ( v12 > 0x7FFFFFFF )
            {
              *v13 = 0;
            }
            else
            {
              v15 = hMem;
              v16 = 2147483646;
              do
              {
                if ( !v16 )
                  break;
                if ( !*v15 )
                  break;
                *v14++ = *v15++;
                --v16;
                --v12;
              }
              while ( v12 );
              v17 = v14 - 1;
              if ( v12 )
                v17 = v14;
              v5 = v12 == 0 ? 0x8007007A : 0;
              *v17 = 0;
            }
          }
        }
        else
        {
          v5 = -2147024882;
        }
        Reply = v5;
        LocalFree(hMem);
      }
    }
    LocalFree(v20[0]);
  }
  TLoad64BitDllsMgr::DecUIRefCnt(pGLdrObj);
  v5 = Reply;
  if ( Reply < 0 )
LABEL_24:
    SplWow64Telemetry::WriteDbgTraceError("RPCSplGetVirtualPrinterFileToken", L"Failed. hr: 0x%x", v5);
  return RpcAsyncCompleteCall(pAsync, &Reply);
}

```

## disassembly

```asm
0x14000d6c0  push    rbp
0x14000d6c2  push    rbx
0x14000d6c3  push    rsi
0x14000d6c4  push    rdi
0x14000d6c5  push    r12
0x14000d6c7  push    r13
0x14000d6c9  push    r14
0x14000d6cb  push    r15
0x14000d6cd  mov     rbp, rsp
0x14000d6d0  sub     rsp, 38h
0x14000d6d4  xor     r13d, r13d
0x14000d6d7  mov     ebx, 80070057h
0x14000d6dc  mov     [rbp+Reply], ebx
0x14000d6df  mov     r15, r9
0x14000d6e2  mov     r14d, r8d
0x14000d6e5  mov     rdi, rdx
0x14000d6e8  mov     r12, rcx
0x14000d6eb  test    rdx, rdx
0x14000d6ee  jz      loc_14000D824
0x14000d6f4  mov     rsi, [rbp+arg_20]
0x14000d6f8  test    rsi, rsi
0x14000d6fb  jz      loc_14000D824
0x14000d701  mov     rcx, cs:?pGLdrObj@@3PEAVTLoad64BitDllsMgr@@EA; this
0x14000d708  call    ?IncUIRefCnt@TLoad64BitDllsMgr@@QEAAXXZ; TLoad64BitDllsMgr::IncUIRefCnt(void)
0x14000d70d  lea     r9, [rbp+var_10]
0x14000d711  mov     [rbp+var_10], r13
0x14000d715  xor     r8d, r8d
0x14000d718  mov     rdx, rdi
0x14000d71b  mov     rcx, r15
0x14000d71e  call    cs:__imp_GetPrintOutputInfo
0x14000d724  mov     [rbp+Reply], eax
0x14000d727  test    eax, eax
0x14000d729  js      loc_14000D811
0x14000d72f  mov     rdx, [rbp+var_10]; unsigned __int16 *
0x14000d733  test    rdx, rdx
0x14000d736  jz      loc_14000D811
0x14000d73c  mov     ecx, r14d; unsigned int
0x14000d73f  call    ?CheckClientProcessAndEncryptFile@@YAJKPEAG@Z; CheckClientProcessAndEncryptFile(ulong,ushort *)
0x14000d744  mov     [rbp+Reply], eax
0x14000d747  mov     [rbp+hMem], r13
0x14000d74b  test    eax, eax
0x14000d74d  js      loc_14000D807
0x14000d753  mov     rcx, [rbp+var_10]
0x14000d757  lea     rdx, [rbp+hMem]
0x14000d75b  call    cs:__imp_GetVirtualPrinterTargetFileToken
0x14000d761  mov     [rbp+Reply], eax
0x14000d764  test    eax, eax
0x14000d766  js      loc_14000D807
0x14000d76c  mov     rcx, [rbp+hMem]
0x14000d770  or      rax, 0FFFFFFFFFFFFFFFFh
0x14000d774  inc     rax
0x14000d777  cmp     [rcx+rax*2], r13w
0x14000d77c  jnz     short loc_14000D774
0x14000d77e  inc     eax
0x14000d780  mov     edi, eax
0x14000d782  lea     rcx, [rax+rax]; unsigned __int64
0x14000d786  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x14000d78b  mov     [rsi], rax
0x14000d78e  mov     rdx, rax
0x14000d791  test    rax, rax
0x14000d794  jz      short loc_14000D7F5
0x14000d796  test    rdi, rdi
0x14000d799  jz      short loc_14000D7FA
0x14000d79b  cmp     rdi, 7FFFFFFFh
0x14000d7a2  ja      short loc_14000D7EF
0x14000d7a4  mov     rcx, [rbp+hMem]
0x14000d7a8  mov     eax, 7FFFFFFEh
0x14000d7ad  test    rax, rax
0x14000d7b0  jz      short loc_14000D7D1
0x14000d7b2  movzx   r8d, word ptr [rcx]
0x14000d7b6  test    r8w, r8w
0x14000d7ba  jz      short loc_14000D7D1
0x14000d7bc  mov     [rdx], r8w
0x14000d7c0  add     rcx, 2
0x14000d7c4  add     rdx, 2
0x14000d7c8  dec     rax
0x14000d7cb  sub     rdi, 1
0x14000d7cf  jnz     short loc_14000D7AD
0x14000d7d1  test    rdi, rdi
0x14000d7d4  lea     rcx, [rdx-2]
0x14000d7d8  cmovnz  rcx, rdx
0x14000d7dc  neg     rdi
0x14000d7df  sbb     ebx, ebx
0x14000d7e1  not     ebx
0x14000d7e3  and     ebx, 8007007Ah
0x14000d7e9  mov     [rcx], r13w
0x14000d7ed  jmp     short loc_14000D7FA
0x14000d7ef  mov     [rax], r13w
0x14000d7f3  jmp     short loc_14000D7FA
0x14000d7f5  mov     ebx, 8007000Eh
0x14000d7fa  mov     rcx, [rbp+hMem]; hMem
0x14000d7fe  mov     [rbp+Reply], ebx
0x14000d801  call    cs:__imp_LocalFree
0x14000d807  mov     rcx, [rbp+var_10]; hMem
0x14000d80b  call    cs:__imp_LocalFree
0x14000d811  mov     rcx, cs:?pGLdrObj@@3PEAVTLoad64BitDllsMgr@@EA; this
0x14000d818  call    ?DecUIRefCnt@TLoad64BitDllsMgr@@QEAAXXZ; TLoad64BitDllsMgr::DecUIRefCnt(void)
0x14000d81d  mov     ebx, [rbp+Reply]
0x14000d820  test    ebx, ebx
0x14000d822  jns     short loc_14000D83A
0x14000d824  mov     r8d, ebx
0x14000d827  lea     rdx, aFailedHr0xX; "Failed. hr: 0x%x"
0x14000d82e  lea     rcx, aRpcsplgetvirtu; "RPCSplGetVirtualPrinterFileToken"
0x14000d835  call    ?WriteDbgTraceError@SplWow64Telemetry@@SAXPEADPEAGZZ; SplWow64Telemetry::WriteDbgTraceError(char *,ushort *,...)
0x14000d83a  lea     rdx, [rbp+Reply]; Reply
0x14000d83e  mov     rcx, r12; pAsync
0x14000d841  call    cs:__imp_RpcAsyncCompleteCall
0x14000d847  add     rsp, 38h
0x14000d84b  pop     r15
0x14000d84d  pop     r14
0x14000d84f  pop     r13
0x14000d851  pop     r12
0x14000d853  pop     rdi
0x14000d854  pop     rsi
0x14000d855  pop     rbx
0x14000d856  pop     rbp
0x14000d857  retn
```
