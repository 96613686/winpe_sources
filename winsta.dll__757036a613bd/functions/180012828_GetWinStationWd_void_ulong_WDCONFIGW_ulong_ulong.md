# GetWinStationWd(void *,ulong,_WDCONFIGW *,ulong,ulong *)

- ea: `0x180012828`
- end: `0x1800129af`
- name: `?GetWinStationWd@@YAJPEAXKPEAU_WDCONFIGW@@KPEAK@Z`
- size: `391`
- prototype: `__int64 __usercall@<rax>(void *@<rcx>, unsigned int@<edx>, struct _WDCONFIGW *@<r8>, unsigned int@<r9d>, unsigned int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x18000ce54`

## callees

- `0x180005c30`
- `0x180007890`
- `0x180008290`
- `0x180008e30`
- `0x180012828`
- `0x18002fe06`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012991`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012991`
- `RPCRT4!I_RpcExceptionFilter` at `0x18003072d`
- `RPCRT4!I_RpcExceptionFilter` at `0x18003072d`
- `RPCRT4!NdrClientCall3` at `0x1800128ec`
- `RPCRT4!NdrClientCall3` at `0x1800128ec`

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
                     (MIDL_STUBLESS_PROXY_INFO *)&stru_1800320E0,
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
0x180012828  mov     rax, rsp
0x18001282b  mov     [rax+8], rbx
0x18001282f  mov     [rax+20h], r9d
0x180012833  mov     [rax+18h], r8
0x180012837  push    rsi
0x180012838  push    r14
0x18001283a  push    r15
0x18001283c  sub     rsp, 80h
0x180012843  mov     r14d, r9d
0x180012846  mov     r15, r8
0x180012849  mov     ebx, edx
0x18001284b  mov     dword ptr [rax-38h], 0
0x180012852  mov     r8d, 1; int
0x180012858  mov     rdx, rcx; void *
0x18001285b  lea     rcx, [rax-28h]; this
0x18001285f  call    ??0CSmartPublicBinding@@QEAA@PEAXH@Z; CSmartPublicBinding::CSmartPublicBinding(void *,int)
0x180012864  lea     rcx, [rsp+98h+var_28]; unsigned __int16 *
0x180012869  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x18001286e  test    rax, rax
0x180012871  jz      loc_180012991
0x180012877  cmp     r14d, 12Ch
0x18001287e  jb      loc_1800129A8
0x180012884  mov     rsi, [rsp+98h+arg_20]
0x18001288c  mov     dword ptr [rsi], 0
0x180012892  lea     rcx, [rsp+98h+var_28]; unsigned __int16 *
0x180012897  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x18001289c  mov     [rsp+98h+var_30], 0
0x1800128a5  lea     rcx, [rsp+98h+var_38]
0x1800128aa  mov     [rsp+98h+var_40], rcx
0x1800128af  mov     [rsp+98h+var_48], rsi
0x1800128b4  mov     [rsp+98h+var_50], r14d
0x1800128b9  mov     [rsp+98h+var_58], r15
0x1800128be  mov     [rsp+98h+var_60], 0
0x1800128c6  mov     [rsp+98h+var_68], 0
0x1800128cf  mov     [rsp+98h+var_70], 1
0x1800128d7  mov     [rsp+98h+var_78], ebx
0x1800128db  mov     r9, rax
0x1800128de  xor     r8d, r8d; pReturnValue
0x1800128e1  lea     edx, [r8+0Bh]; nProcNum
0x1800128e5  lea     rcx, stru_1800320E0; pProxyInfo
0x1800128ec  call    cs:__imp_NdrClientCall3
0x1800128f2  mov     rbx, rax
0x1800128f5  mov     [rsp+98h+var_30], rax
0x1800128fa  mov     [rsp+98h+var_34], eax
0x1800128fe  jmp     short loc_18001293E
0x180012900  test    eax, eax
0x180012902  jle     short loc_18001290C
0x180012904  movzx   eax, ax
0x180012907  or      eax, 80070000h
0x18001290c  mov     ebx, eax
0x18001290e  mov     [rsp+98h+var_34], eax
0x180012912  mov     r8d, eax
0x180012915  lea     rdx, aRpcquerysessio; "RpcQuerySessionData failed: 0x%x"
0x18001291c  mov     ecx, 8; int
0x180012921  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180012926  mov     rsi, [rsp+98h+arg_20]
0x18001292e  mov     r14d, [rsp+98h+arg_18]
0x180012936  mov     r15, [rsp+98h+arg_10]
0x18001293e  cmp     ebx, 800708CAh
0x180012944  jnz     short loc_180012979
0x180012946  mov     r8d, r14d; Size
0x180012949  xor     edx, edx; Val
0x18001294b  mov     rcx, r15; void *
0x18001294e  call    memset_0
0x180012953  mov     [rsi], r14d
0x180012956  xor     ebx, ebx
0x180012958  lea     rcx, [rsp+98h+var_28]; this
0x18001295d  call    ??1CSmartPublicBinding@@QEAA@XZ; CSmartPublicBinding::~CSmartPublicBinding(void)
0x180012962  mov     eax, ebx
0x180012964  mov     rbx, [rsp+98h+arg_0]
0x18001296c  add     rsp, 80h
0x180012973  pop     r15
0x180012975  pop     r14
0x180012977  pop     rsi
0x180012978  retn
0x180012979  cmp     ebx, 800706BAh
0x18001297f  jz      short loc_180012946
0x180012981  cmp     ebx, 800706B5h
0x180012987  jz      short loc_180012946
0x180012989  mov     eax, [rsp+98h+var_38]
0x18001298d  mov     [rsi], eax
0x18001298f  jmp     short loc_180012958
0x180012991  call    cs:__imp_GetLastError
0x180012997  mov     ebx, eax
0x180012999  test    eax, eax
0x18001299b  jle     short loc_180012958
0x18001299d  movzx   ebx, ax
0x1800129a0  or      ebx, 80070000h
0x1800129a6  jmp     short loc_180012958
0x1800129a8  mov     ebx, 80070057h
0x1800129ad  jmp     short loc_180012958
0x18003071f  push    rbp
0x180030721  sub     rsp, 60h
0x180030725  mov     rbp, rdx
0x180030728  mov     rcx, [rcx]
0x18003072b  mov     ecx, [rcx]; ExceptionCode
0x18003072d  call    cs:__imp_I_RpcExceptionFilter
0x180030733  nop
0x180030734  add     rsp, 60h
0x180030738  pop     rbp
0x180030739  retn
```
