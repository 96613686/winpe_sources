# XsOpenPrinter

- ea: `0x180030d70`
- end: `0x180031098`
- name: `XsOpenPrinter`
- size: `808`
- prototype: `__int64 __usercall@<rax>(PRPC_ASYNC_STATE pAsync@<rcx>, RPC_BINDING_HANDLE BindingHandle@<rdx>, __int64)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180020dc0`
- `0x180020de8`
- `0x180030c18`
- `0x180030d70`
- `0x180044010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030e85`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030ffe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030e85`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030ffe`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180030edc`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180030f34`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180030edc`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180030f34`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180030fef`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180030ff8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003101a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180030fef`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180030ff8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003101a`
- `ntdll!RtlAcquireResourceShared` at `0x180030e2d`
- `ntdll!RtlAcquireResourceShared` at `0x180030e2d`
- `ntdll!RtlReleaseResource` at `0x18003102e`
- `ntdll!RtlReleaseResource` at `0x18003102e`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180031077`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180031077`
- `RPCRT4!RpcAsyncAbortCall` at `0x180030ddd`
- `RPCRT4!RpcAsyncAbortCall` at `0x180031081`
- `RPCRT4!RpcAsyncAbortCall` at `0x180030ddd`
- `RPCRT4!RpcAsyncAbortCall` at `0x180031081`
- `RPCRT4!RpcServerTestCancel` at `0x180030dcb`
- `RPCRT4!RpcServerTestCancel` at `0x180030dcb`

## pseudocode

```c
unsigned int __fastcall XsOpenPrinter(
        PRPC_ASYNC_STATE pAsync,
        RPC_BINDING_HANDLE BindingHandle,
        unsigned __int16 *a3,
        _QWORD *a4,
        DWORD *a5)
{
  unsigned int result; // eax
  DWORD LastError; // ebx
  DWORD v11; // eax
  _QWORD *v12; // rsi
  SIZE_T v13; // rdi
  _WORD *v14; // r14
  void *v15; // rcx
  SIZE_T v16; // rdi
  _WORD *v17; // rdx
  _WORD *v18; // rcx
  unsigned __int64 v19; // rax
  _WORD *v20; // rcx
  unsigned int (__fastcall *v21)(_WORD *, _QWORD *, _QWORD); // rax
  _QWORD v22[11]; // [rsp+20h] [rbp-58h] BYREF

  v22[0] = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_961f2129f327316bc578c2fdd21cc406_Traceguids);
  }
  if ( !RpcServerTestCancel(BindingHandle) )
  {
    result = RpcAsyncAbortCall(pAsync, 0x71Au);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      if ( *((_BYTE *)WPP_GLOBAL_Control + 25) )
        return WPP_SF_d(
                 *((_QWORD *)WPP_GLOBAL_Control + 2),
                 11,
                 WPP_961f2129f327316bc578c2fdd21cc406_Traceguids,
                 result);
    }
    return result;
  }
  RtlAcquireResourceShared(&stru_18005E3D8, 1u);
  if ( dword_18005E43C )
  {
    if ( pSpoolerOpenPrinterFunction || XsLoadPrintSpoolerFunctions() )
    {
      LastError = 8;
      v12 = LocalAlloc(0x40u, 8u);
      if ( v12 )
      {
        v13 = *a3 + 2LL;
        v14 = LocalAlloc(0x40u, v13);
        if ( v14 )
        {
          v16 = v13 >> 1;
          if ( v16 )
          {
            v17 = v14;
            v18 = (_WORD *)*((_QWORD *)a3 + 1);
            v19 = (unsigned __int64)*a3 >> 1;
            do
            {
              if ( !v19 )
                break;
              if ( !*v18 )
                break;
              *v17++ = *v18++;
              --v19;
              --v16;
            }
            while ( v16 );
            v20 = v17 - 1;
            if ( v16 )
              v20 = v17;
            *v20 = 0;
          }
          v21 = (unsigned int (__fastcall *)(_WORD *, _QWORD *, _QWORD))pSpoolerOpenPrinterFunction;
          v14[(unsigned __int64)*a3 >> 1] = 0;
          if ( !v21(v14, v22, 0) )
          {
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) )
            {
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_961f2129f327316bc578c2fdd21cc406_Traceguids, 0);
            }
            LocalFree(v12);
            LocalFree(v14);
            LastError = GetLastError();
            goto LABEL_45;
          }
          LastError = 0;
          *v12 = v22[0];
          v15 = v14;
          *a4 = v12;
        }
        else
        {
          v15 = v12;
        }
        LocalFree(v15);
      }
      else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
             && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
             && *((_BYTE *)WPP_GLOBAL_Control + 25) )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_961f2129f327316bc578c2fdd21cc406_Traceguids);
      }
    }
    else
    {
      v11 = GetLastError();
      LastError = v11;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_961f2129f327316bc578c2fdd21cc406_Traceguids, v11);
      }
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_961f2129f327316bc578c2fdd21cc406_Traceguids);
    }
    LastError = 5;
  }
LABEL_45:
  RtlReleaseResource(&stru_18005E3D8);
  *a5 = LastError;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_961f2129f327316bc578c2fdd21cc406_Traceguids, LastError);
  }
  if ( LastError )
    return RpcAsyncAbortCall(pAsync, LastError);
  else
    return RpcAsyncCompleteCall(pAsync, 0);
}

```

## disassembly

```asm
0x180030d70  push    rbx
0x180030d72  push    rbp
0x180030d73  push    rsi
0x180030d74  push    rdi
0x180030d75  push    r12
0x180030d77  push    r13
0x180030d79  push    r14
0x180030d7b  push    r15
0x180030d7d  sub     rsp, 38h
0x180030d81  xor     r13d, r13d
0x180030d84  mov     r12, r9
0x180030d87  mov     [rsp+78h+var_58], r13
0x180030d8c  mov     rbp, r8
0x180030d8f  mov     rbx, rdx
0x180030d92  mov     r15, rcx
0x180030d95  mov     rcx, cs:WPP_GLOBAL_Control
0x180030d9c  lea     rdi, WPP_GLOBAL_Control
0x180030da3  cmp     rcx, rdi
0x180030da6  jz      short loc_180030DC8
0x180030da8  test    byte ptr [rcx+1Ch], 10h
0x180030dac  jz      short loc_180030DC8
0x180030dae  cmp     byte ptr [rcx+19h], 2
0x180030db2  jb      short loc_180030DC8
0x180030db4  mov     rcx, [rcx+10h]
0x180030db8  lea     edx, [r13+0Ah]
0x180030dbc  lea     r8, WPP_961f2129f327316bc578c2fdd21cc406_Traceguids
0x180030dc3  call    WPP_SF_
0x180030dc8  mov     rcx, rbx; BindingHandle
0x180030dcb  call    cs:__imp_RpcServerTestCancel
0x180030dd1  test    eax, eax
0x180030dd3  jnz     short loc_180030E24
0x180030dd5  mov     edx, 71Ah; ExceptionCode
0x180030dda  mov     rcx, r15; pAsync
0x180030ddd  call    cs:__imp_RpcAsyncAbortCall
0x180030de3  mov     rcx, cs:WPP_GLOBAL_Control
0x180030dea  cmp     rcx, rdi
0x180030ded  jz      loc_180031087
0x180030df3  test    byte ptr [rcx+1Ch], 10h
0x180030df7  jz      loc_180031087
0x180030dfd  cmp     byte ptr [rcx+19h], 1
0x180030e01  jb      loc_180031087
0x180030e07  mov     rcx, [rcx+10h]
0x180030e0b  lea     r8, WPP_961f2129f327316bc578c2fdd21cc406_Traceguids
0x180030e12  mov     edx, 0Bh
0x180030e17  mov     r9d, eax
0x180030e1a  call    WPP_SF_d
0x180030e1f  jmp     loc_180031087
0x180030e24  mov     dl, 1; Wait
0x180030e26  lea     rcx, stru_18005E3D8; Resource
0x180030e2d  call    cs:__imp_RtlAcquireResourceShared
0x180030e33  cmp     cs:dword_18005E43C, r13d
0x180030e3a  jnz     short loc_180030E73
0x180030e3c  mov     rcx, cs:WPP_GLOBAL_Control
0x180030e43  cmp     rcx, rdi
0x180030e46  jz      short loc_180030E69
0x180030e48  test    byte ptr [rcx+1Ch], 10h
0x180030e4c  jz      short loc_180030E69
0x180030e4e  cmp     byte ptr [rcx+19h], 1
0x180030e52  jb      short loc_180030E69
0x180030e54  mov     rcx, [rcx+10h]
0x180030e58  lea     r8, WPP_961f2129f327316bc578c2fdd21cc406_Traceguids
0x180030e5f  mov     edx, 0Ch
0x180030e64  call    WPP_SF_
0x180030e69  mov     ebx, 5
0x180030e6e  jmp     loc_180031027
0x180030e73  cmp     cs:pSpoolerOpenPrinterFunction, r13
0x180030e7a  jnz     short loc_180030ECE
0x180030e7c  call    XsLoadPrintSpoolerFunctions
0x180030e81  test    al, al
0x180030e83  jnz     short loc_180030ECE
0x180030e85  call    cs:__imp_GetLastError
0x180030e8b  mov     ebx, eax
0x180030e8d  mov     rcx, cs:WPP_GLOBAL_Control
0x180030e94  cmp     rcx, rdi
0x180030e97  jz      loc_180031027
0x180030e9d  test    byte ptr [rcx+1Ch], 10h
0x180030ea1  jz      loc_180031027
0x180030ea7  cmp     byte ptr [rcx+19h], 1
0x180030eab  jb      loc_180031027
0x180030eb1  mov     rcx, [rcx+10h]
0x180030eb5  lea     r8, WPP_961f2129f327316bc578c2fdd21cc406_Traceguids
0x180030ebc  mov     edx, 0Dh
0x180030ec1  mov     r9d, eax
0x180030ec4  call    WPP_SF_d
0x180030ec9  jmp     loc_180031027
0x180030ece  mov     ebx, 8
0x180030ed3  mov     edx, ebx; uBytes
0x180030ed5  lea     r14d, [rbx+38h]
0x180030ed9  mov     ecx, r14d; uFlags
0x180030edc  call    cs:__imp_LocalAlloc
0x180030ee2  mov     rsi, rax
0x180030ee5  test    rax, rax
0x180030ee8  jnz     short loc_180030F26
0x180030eea  mov     rcx, cs:WPP_GLOBAL_Control
0x180030ef1  cmp     rcx, rdi
0x180030ef4  jz      loc_180031027
0x180030efa  test    byte ptr [rcx+1Ch], 10h
0x180030efe  jz      loc_180031027
0x180030f04  cmp     byte ptr [rcx+19h], 1
0x180030f08  jb      loc_180031027
0x180030f0e  mov     rcx, [rcx+10h]
0x180030f12  lea     edx, [rbx+6]
0x180030f15  lea     r8, WPP_961f2129f327316bc578c2fdd21cc406_Traceguids
0x180030f1c  call    WPP_SF_
0x180030f21  jmp     loc_180031027
0x180030f26  movzx   edi, word ptr [rbp+0]
0x180030f2a  mov     ecx, r14d; uFlags
0x180030f2d  add     rdi, 2
0x180030f31  mov     rdx, rdi; uBytes
0x180030f34  call    cs:__imp_LocalAlloc
0x180030f3a  mov     r14, rax
0x180030f3d  test    rax, rax
0x180030f40  jnz     short loc_180030F4A
0x180030f42  mov     rcx, rsi
0x180030f45  jmp     loc_18003101A
0x180030f4a  shr     rdi, 1
0x180030f4d  jz      short loc_180030F90
0x180030f4f  movzx   eax, word ptr [rbp+0]
0x180030f53  mov     rdx, r14
0x180030f56  mov     rcx, [rbp+8]
0x180030f5a  shr     rax, 1
0x180030f5d  test    rax, rax
0x180030f60  jz      short loc_180030F81
0x180030f62  movzx   r8d, word ptr [rcx]
0x180030f66  test    r8w, r8w
0x180030f6a  jz      short loc_180030F81
0x180030f6c  mov     [rdx], r8w
0x180030f70  add     rcx, 2
0x180030f74  add     rdx, 2
0x180030f78  dec     rax
0x180030f7b  sub     rdi, 1
0x180030f7f  jnz     short loc_180030F5D
0x180030f81  test    rdi, rdi
0x180030f84  lea     rcx, [rdx-2]
0x180030f88  cmovnz  rcx, rdx
0x180030f8c  mov     [rcx], r13w
0x180030f90  movzx   ecx, word ptr [rbp+0]
0x180030f94  lea     rdx, [rsp+78h+var_58]
0x180030f99  mov     rax, cs:pSpoolerOpenPrinterFunction
0x180030fa0  xor     r8d, r8d
0x180030fa3  shr     rcx, 1
0x180030fa6  mov     [r14+rcx*2], r13w
0x180030fab  mov     rcx, r14
0x180030fae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030fb3  test    eax, eax
0x180030fb5  jnz     short loc_180031008
0x180030fb7  mov     rcx, cs:WPP_GLOBAL_Control
0x180030fbe  lea     rdi, WPP_GLOBAL_Control
0x180030fc5  cmp     rcx, rdi
0x180030fc8  jz      short loc_180030FEC
0x180030fca  test    byte ptr [rcx+1Ch], 10h
0x180030fce  jz      short loc_180030FEC
0x180030fd0  cmp     byte ptr [rcx+19h], 1
0x180030fd4  jb      short loc_180030FEC
0x180030fd6  mov     rcx, [rcx+10h]
0x180030fda  lea     edx, [rax+0Fh]
0x180030fdd  xor     r9d, r9d
0x180030fe0  lea     r8, WPP_961f2129f327316bc578c2fdd21cc406_Traceguids
0x180030fe7  call    WPP_SF_d
0x180030fec  mov     rcx, rsi; hMem
0x180030fef  call    cs:__imp_LocalFree
0x180030ff5  mov     rcx, r14; hMem
0x180030ff8  call    cs:__imp_LocalFree
0x180030ffe  call    cs:__imp_GetLastError
0x180031004  mov     ebx, eax
0x180031006  jmp     short loc_180031027
0x180031008  mov     rax, [rsp+78h+var_58]
0x18003100d  mov     ebx, r13d
0x180031010  mov     [rsi], rax
0x180031013  mov     rcx, r14; hMem
0x180031016  mov     [r12], rsi
0x18003101a  call    cs:__imp_LocalFree
0x180031020  lea     rdi, WPP_GLOBAL_Control
0x180031027  lea     rcx, stru_18005E3D8; Resource
0x18003102e  call    cs:__imp_RtlReleaseResource
0x180031034  mov     rax, [rsp+78h+arg_20]
0x18003103c  mov     [rax], ebx
0x18003103e  mov     rcx, cs:WPP_GLOBAL_Control
0x180031045  cmp     rcx, rdi
0x180031048  jz      short loc_18003106E
0x18003104a  test    byte ptr [rcx+1Ch], 10h
0x18003104e  jz      short loc_18003106E
0x180031050  cmp     byte ptr [rcx+19h], 2
0x180031054  jb      short loc_18003106E
0x180031056  mov     rcx, [rcx+10h]
0x18003105a  lea     r8, WPP_961f2129f327316bc578c2fdd21cc406_Traceguids
0x180031061  mov     edx, 10h
0x180031066  mov     r9d, ebx
0x180031069  call    WPP_SF_d
0x18003106e  mov     rcx, r15; pAsync
0x180031071  test    ebx, ebx
0x180031073  jnz     short loc_18003107F
0x180031075  xor     edx, edx; Reply
0x180031077  call    cs:__imp_RpcAsyncCompleteCall
0x18003107d  jmp     short loc_180031087
0x18003107f  mov     edx, ebx; ExceptionCode
0x180031081  call    cs:__imp_RpcAsyncAbortCall
0x180031087  add     rsp, 38h
0x18003108b  pop     r15
0x18003108d  pop     r14
0x18003108f  pop     r13
0x180031091  pop     r12
0x180031093  pop     rdi
0x180031094  pop     rsi
0x180031095  pop     rbp
0x180031096  pop     rbx
0x180031097  retn
```
