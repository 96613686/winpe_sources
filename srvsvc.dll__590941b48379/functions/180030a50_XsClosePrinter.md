# XsClosePrinter

- ea: `0x180030a50`
- end: `0x180030c11`
- name: `XsClosePrinter`
- size: `449`
- prototype: `__int64 __fastcall(PRPC_ASYNC_STATE pAsync, RPC_BINDING_HANDLE BindingHandle)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180020dc0`
- `0x180020de8`
- `0x180030a50`
- `0x180030c18`
- `0x180044010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030b5f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030b5f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180030ad7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180030b71`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180030ad7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180030b71`
- `ntdll!RtlAcquireResourceShared` at `0x180030aeb`
- `ntdll!RtlAcquireResourceShared` at `0x180030aeb`
- `ntdll!RtlReleaseResource` at `0x180030b7e`
- `ntdll!RtlReleaseResource` at `0x180030b7e`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180030bbd`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180030bbd`
- `RPCRT4!RpcAsyncAbortCall` at `0x180030a97`
- `RPCRT4!RpcAsyncAbortCall` at `0x180030bca`
- `RPCRT4!RpcAsyncAbortCall` at `0x180030a97`
- `RPCRT4!RpcAsyncAbortCall` at `0x180030bca`
- `RPCRT4!RpcServerTestCancel` at `0x180030a7e`
- `RPCRT4!RpcServerTestCancel` at `0x180030a7e`

## pseudocode

```c
unsigned int __fastcall XsClosePrinter(
        PRPC_ASYNC_STATE pAsync,
        RPC_BINDING_HANDLE BindingHandle,
        _QWORD **a3,
        DWORD *a4)
{
  _QWORD *v7; // rsi
  unsigned int v8; // eax
  unsigned int result; // eax
  DWORD LastError; // edi
  unsigned int (__fastcall *v11)(_QWORD); // rax

  if ( a3 )
  {
    v7 = *a3;
    if ( *a3 )
    {
      if ( !RpcServerTestCancel(BindingHandle) )
      {
        *a3 = 0;
        v8 = RpcAsyncAbortCall(pAsync, 0x71Au);
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
        {
          if ( *((_BYTE *)WPP_GLOBAL_Control + 25) )
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 35, WPP_961f2129f327316bc578c2fdd21cc406_Traceguids, v8);
        }
        return (unsigned int)LocalFree(v7);
      }
      RtlAcquireResourceShared(&stru_18005E3D8, 1u);
      if ( !dword_18005E43C )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, WPP_961f2129f327316bc578c2fdd21cc406_Traceguids);
        }
        LastError = 5;
        goto LABEL_20;
      }
      v11 = (unsigned int (__fastcall *)(_QWORD))pSpoolerClosePrinterFunction;
      if ( !pSpoolerClosePrinterFunction )
      {
        if ( !XsLoadPrintSpoolerFunctions() )
        {
LABEL_19:
          LastError = GetLastError();
LABEL_20:
          *a3 = 0;
          LocalFree(v7);
          RtlReleaseResource(&stru_18005E3D8);
          *a4 = LastError;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              37,
              WPP_961f2129f327316bc578c2fdd21cc406_Traceguids,
              LastError);
          }
          return RpcAsyncCompleteCall(pAsync, a4);
        }
        v11 = (unsigned int (__fastcall *)(_QWORD))pSpoolerClosePrinterFunction;
      }
      LastError = 0;
      if ( v11(*v7) )
        goto LABEL_20;
      goto LABEL_19;
    }
  }
  result = RpcAsyncAbortCall(pAsync, 0x57u);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) )
  {
    return WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, WPP_961f2129f327316bc578c2fdd21cc406_Traceguids);
  }
  return result;
}

```

## disassembly

```asm
0x180030a50  push    rbx
0x180030a52  push    rbp
0x180030a53  push    rsi
0x180030a54  push    rdi
0x180030a55  push    r14
0x180030a57  push    r15
0x180030a59  sub     rsp, 28h
0x180030a5d  mov     r15, r9
0x180030a60  mov     r14, r8
0x180030a63  mov     rbp, rcx
0x180030a66  test    r8, r8
0x180030a69  jz      loc_180030BC5
0x180030a6f  mov     rsi, [r8]
0x180030a72  test    rsi, rsi
0x180030a75  jz      loc_180030BC5
0x180030a7b  mov     rcx, rdx; BindingHandle
0x180030a7e  call    cs:__imp_RpcServerTestCancel
0x180030a84  test    eax, eax
0x180030a86  jnz     short loc_180030AE2
0x180030a88  mov     edx, 71Ah; ExceptionCode
0x180030a8d  mov     qword ptr [r14], 0
0x180030a94  mov     rcx, rbp; pAsync
0x180030a97  call    cs:__imp_RpcAsyncAbortCall
0x180030a9d  mov     rcx, cs:WPP_GLOBAL_Control
0x180030aa4  lea     rbx, WPP_GLOBAL_Control
0x180030aab  cmp     rcx, rbx
0x180030aae  jz      short loc_180030AD4
0x180030ab0  test    byte ptr [rcx+1Ch], 10h
0x180030ab4  jz      short loc_180030AD4
0x180030ab6  cmp     byte ptr [rcx+19h], 1
0x180030aba  jb      short loc_180030AD4
0x180030abc  mov     rcx, [rcx+10h]
0x180030ac0  lea     r8, WPP_961f2129f327316bc578c2fdd21cc406_Traceguids
0x180030ac7  mov     edx, 23h ; '#'
0x180030acc  mov     r9d, eax
0x180030acf  call    WPP_SF_d
0x180030ad4  mov     rcx, rsi; hMem
0x180030ad7  call    cs:__imp_LocalFree
0x180030add  jmp     loc_180030C04
0x180030ae2  mov     dl, 1; Wait
0x180030ae4  lea     rcx, stru_18005E3D8; Resource
0x180030aeb  call    cs:__imp_RtlAcquireResourceShared
0x180030af1  cmp     cs:dword_18005E43C, 0
0x180030af8  lea     rbx, WPP_GLOBAL_Control
0x180030aff  jnz     short loc_180030B35
0x180030b01  mov     rcx, cs:WPP_GLOBAL_Control
0x180030b08  cmp     rcx, rbx
0x180030b0b  jz      short loc_180030B2E
0x180030b0d  test    byte ptr [rcx+1Ch], 10h
0x180030b11  jz      short loc_180030B2E
0x180030b13  cmp     byte ptr [rcx+19h], 1
0x180030b17  jb      short loc_180030B2E
0x180030b19  mov     rcx, [rcx+10h]
0x180030b1d  lea     r8, WPP_961f2129f327316bc578c2fdd21cc406_Traceguids
0x180030b24  mov     edx, 24h ; '$'
0x180030b29  call    WPP_SF_
0x180030b2e  mov     edi, 5
0x180030b33  jmp     short loc_180030B67
0x180030b35  mov     rax, cs:pSpoolerClosePrinterFunction
0x180030b3c  test    rax, rax
0x180030b3f  jnz     short loc_180030B51
0x180030b41  call    XsLoadPrintSpoolerFunctions
0x180030b46  test    al, al
0x180030b48  jz      short loc_180030B5F
0x180030b4a  mov     rax, cs:pSpoolerClosePrinterFunction
0x180030b51  mov     rcx, [rsi]
0x180030b54  xor     edi, edi
0x180030b56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030b5b  test    eax, eax
0x180030b5d  jnz     short loc_180030B67
0x180030b5f  call    cs:__imp_GetLastError
0x180030b65  mov     edi, eax
0x180030b67  mov     rcx, rsi; hMem
0x180030b6a  mov     qword ptr [r14], 0
0x180030b71  call    cs:__imp_LocalFree
0x180030b77  lea     rcx, stru_18005E3D8; Resource
0x180030b7e  call    cs:__imp_RtlReleaseResource
0x180030b84  mov     [r15], edi
0x180030b87  mov     rcx, cs:WPP_GLOBAL_Control
0x180030b8e  cmp     rcx, rbx
0x180030b91  jz      short loc_180030BB7
0x180030b93  test    byte ptr [rcx+1Ch], 10h
0x180030b97  jz      short loc_180030BB7
0x180030b99  cmp     byte ptr [rcx+19h], 2
0x180030b9d  jb      short loc_180030BB7
0x180030b9f  mov     rcx, [rcx+10h]
0x180030ba3  lea     r8, WPP_961f2129f327316bc578c2fdd21cc406_Traceguids
0x180030baa  mov     edx, 25h ; '%'
0x180030baf  mov     r9d, edi
0x180030bb2  call    WPP_SF_d
0x180030bb7  mov     rdx, r15; Reply
0x180030bba  mov     rcx, rbp; pAsync
0x180030bbd  call    cs:__imp_RpcAsyncCompleteCall
0x180030bc3  jmp     short loc_180030C04
0x180030bc5  mov     edx, 57h ; 'W'; ExceptionCode
0x180030bca  call    cs:__imp_RpcAsyncAbortCall
0x180030bd0  mov     rcx, cs:WPP_GLOBAL_Control
0x180030bd7  lea     rbx, WPP_GLOBAL_Control
0x180030bde  cmp     rcx, rbx
0x180030be1  jz      short loc_180030C04
0x180030be3  test    byte ptr [rcx+1Ch], 10h
0x180030be7  jz      short loc_180030C04
0x180030be9  cmp     byte ptr [rcx+19h], 1
0x180030bed  jb      short loc_180030C04
0x180030bef  mov     rcx, [rcx+10h]
0x180030bf3  lea     r8, WPP_961f2129f327316bc578c2fdd21cc406_Traceguids
0x180030bfa  mov     edx, 22h ; '"'
0x180030bff  call    WPP_SF_
0x180030c04  add     rsp, 28h
0x180030c08  pop     r15
0x180030c0a  pop     r14
0x180030c0c  pop     rdi
0x180030c0d  pop     rsi
0x180030c0e  pop     rbp
0x180030c0f  pop     rbx
0x180030c10  retn
```
