# GetWinStationWd(void *,ulong,_WDCONFIGW *,ulong,ulong *)

- ea: `0x18001369c`
- end: `0x180013830`
- name: `?GetWinStationWd@@YAJPEAXKPEAU_WDCONFIGW@@KPEAK@Z`
- size: `404`
- prototype: `__int64 __usercall@<rax>(void *@<rcx>, unsigned int@<edx>, struct _WDCONFIGW *@<r8>, unsigned int@<r9d>, unsigned int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x180009dec`

## callees

- `0x1800041a0`
- `0x180005b40`
- `0x1800065f0`
- `0x1800075a0`
- `0x18001369c`
- `0x180032be6`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001380c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001380c`
- `RPCRT4!I_RpcExceptionFilter` at `0x1800335fd`
- `RPCRT4!I_RpcExceptionFilter` at `0x1800335fd`
- `RPCRT4!NdrClientCall3` at `0x180013760`
- `RPCRT4!NdrClientCall3` at `0x180013760`

## pseudocode

```c
__int64 __fastcall GetWinStationWd(void *a1, int a2, struct _WDCONFIGW *a3, unsigned int a4, unsigned int *a5)
{
  void *v8; // rax
  CLIENT_CALL_RETURN v9; // rax
  unsigned int Pointer; // ebx
  signed int LastError; // eax
  int v13; // [rsp+20h] [rbp-78h]
  int v14; // [rsp+28h] [rbp-70h]
  int v15; // [rsp+38h] [rbp-60h]
  unsigned int v16; // [rsp+48h] [rbp-50h]
  _DWORD v17[2]; // [rsp+60h] [rbp-38h] BYREF
  CLIENT_CALL_RETURN v18; // [rsp+68h] [rbp-30h]
  unsigned __int16 v19[20]; // [rsp+70h] [rbp-28h] BYREF

  v17[0] = 0;
  CSmartPublicBinding::CSmartPublicBinding((CSmartPublicBinding *)v19, a1, 1);
  if ( CSmartPublicBinding::operator void *(v19) )
  {
    if ( a4 < 0x12C )
    {
      Pointer = -2147024809;
    }
    else
    {
      *a5 = 0;
      v8 = CSmartPublicBinding::operator void *(v19);
      v18.Simple = 0;
      v16 = a4;
      v15 = 0;
      v14 = 1;
      v13 = a2;
      v9.Pointer = NdrClientCall3(
                     (MIDL_STUBLESS_PROXY_INFO *)&stru_180035078,
                     0xBu,
                     0,
                     v8,
                     v13,
                     v14,
                     0,
                     v15,
                     a3,
                     v16,
                     a5,
                     v17).Pointer;
      Pointer = (unsigned int)v9.Pointer;
      v18.Pointer = v9.Pointer;
      v17[1] = v9.Pointer;
      if ( LODWORD(v9.Pointer) == -2147022646
        || LODWORD(v9.Pointer) == -2147023174
        || LODWORD(v9.Pointer) == -2147023179 )
      {
        memset_0(a3, 0, a4);
        *a5 = a4;
        Pointer = 0;
      }
      else
      {
        *a5 = v17[0];
      }
    }
  }
  else
  {
    LastError = GetLastError();
    Pointer = LastError;
    if ( LastError > 0 )
      Pointer = (unsigned __int16)LastError | 0x80070000;
  }
  CSmartPublicBinding::~CSmartPublicBinding((CSmartPublicBinding *)v19);
  return Pointer;
}

```

## disassembly

```asm
0x18001369c  mov     rax, rsp
0x18001369f  mov     [rax+8], rbx
0x1800136a3  mov     [rax+20h], r9d
0x1800136a7  mov     [rax+18h], r8
0x1800136ab  push    rsi
0x1800136ac  push    r14
0x1800136ae  push    r15
0x1800136b0  sub     rsp, 80h
0x1800136b7  mov     r14d, r9d
0x1800136ba  mov     r15, r8
0x1800136bd  mov     ebx, edx
0x1800136bf  mov     dword ptr [rax-38h], 0
0x1800136c6  mov     r8d, 1; int
0x1800136cc  mov     rdx, rcx; void *
0x1800136cf  lea     rcx, [rax-28h]; this
0x1800136d3  call    ??0CSmartPublicBinding@@QEAA@PEAXH@Z; CSmartPublicBinding::CSmartPublicBinding(void *,int)
0x1800136d8  lea     rcx, [rsp+98h+var_28]; unsigned __int16 *
0x1800136dd  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x1800136e2  test    rax, rax
0x1800136e5  jz      loc_18001380C
0x1800136eb  cmp     r14d, 12Ch
0x1800136f2  jb      loc_180013829
0x1800136f8  mov     rsi, [rsp+98h+arg_20]
0x180013700  mov     dword ptr [rsi], 0
0x180013706  lea     rcx, [rsp+98h+var_28]; unsigned __int16 *
0x18001370b  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x180013710  mov     [rsp+98h+var_30], 0
0x180013719  lea     rcx, [rsp+98h+var_38]
0x18001371e  mov     [rsp+98h+var_40], rcx
0x180013723  mov     [rsp+98h+var_48], rsi
0x180013728  mov     [rsp+98h+var_50], r14d
0x18001372d  mov     [rsp+98h+var_58], r15
0x180013732  mov     [rsp+98h+var_60], 0
0x18001373a  mov     [rsp+98h+var_68], 0
0x180013743  mov     [rsp+98h+var_70], 1
0x18001374b  mov     [rsp+98h+var_78], ebx
0x18001374f  mov     r9, rax
0x180013752  xor     r8d, r8d; pReturnValue
0x180013755  lea     edx, [r8+0Bh]; nProcNum
0x180013759  lea     rcx, stru_180035078; pProxyInfo
0x180013760  call    cs:__imp_NdrClientCall3
0x180013767  nop     dword ptr [rax+rax+00h]
0x18001376c  mov     rbx, rax
0x18001376f  mov     [rsp+98h+var_30], rax
0x180013774  mov     [rsp+98h+var_34], eax
0x180013778  jmp     short loc_1800137B8
0x18001377a  test    eax, eax
0x18001377c  jle     short loc_180013786
0x18001377e  movzx   eax, ax
0x180013781  or      eax, 80070000h
0x180013786  mov     ebx, eax
0x180013788  mov     [rsp+98h+var_34], eax
0x18001378c  mov     r8d, eax
0x18001378f  lea     rdx, aRpcquerysessio; "RpcQuerySessionData failed: 0x%x"
0x180013796  mov     ecx, 8; int
0x18001379b  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800137a0  mov     rsi, [rsp+98h+arg_20]
0x1800137a8  mov     r14d, [rsp+98h+arg_18]
0x1800137b0  mov     r15, [rsp+98h+arg_10]
0x1800137b8  cmp     ebx, 800708CAh
0x1800137be  jnz     short loc_1800137F4
0x1800137c0  mov     r8d, r14d; Size
0x1800137c3  xor     edx, edx; Val
0x1800137c5  mov     rcx, r15; void *
0x1800137c8  call    memset_0
0x1800137cd  mov     [rsi], r14d
0x1800137d0  xor     ebx, ebx
0x1800137d2  lea     rcx, [rsp+98h+var_28]; this
0x1800137d7  call    ??1CSmartPublicBinding@@QEAA@XZ; CSmartPublicBinding::~CSmartPublicBinding(void)
0x1800137dc  mov     eax, ebx
0x1800137de  mov     rbx, [rsp+98h+arg_0]
0x1800137e6  add     rsp, 80h
0x1800137ed  pop     r15
0x1800137ef  pop     r14
0x1800137f1  pop     rsi
0x1800137f2  retn
0x1800137f4  cmp     ebx, 800706BAh
0x1800137fa  jz      short loc_1800137C0
0x1800137fc  cmp     ebx, 800706B5h
0x180013802  jz      short loc_1800137C0
0x180013804  mov     eax, [rsp+98h+var_38]
0x180013808  mov     [rsi], eax
0x18001380a  jmp     short loc_1800137D2
0x18001380c  call    cs:__imp_GetLastError
0x180013813  nop     dword ptr [rax+rax+00h]
0x180013818  mov     ebx, eax
0x18001381a  test    eax, eax
0x18001381c  jle     short loc_1800137D2
0x18001381e  movzx   ebx, ax
0x180013821  or      ebx, 80070000h
0x180013827  jmp     short loc_1800137D2
0x180013829  mov     ebx, 80070057h
0x18001382e  jmp     short loc_1800137D2
0x1800335ef  push    rbp
0x1800335f1  sub     rsp, 60h
0x1800335f5  mov     rbp, rdx
0x1800335f8  mov     rcx, [rcx]
0x1800335fb  mov     ecx, [rcx]; ExceptionCode
0x1800335fd  call    cs:__imp_I_RpcExceptionFilter
0x180033604  nop     dword ptr [rax+rax+00h]
0x180033609  nop
0x18003360a  add     rsp, 60h
0x18003360e  pop     rbp
0x18003360f  retn
```
