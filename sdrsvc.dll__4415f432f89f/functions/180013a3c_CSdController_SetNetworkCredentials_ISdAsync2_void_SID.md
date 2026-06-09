# CSdController::_SetNetworkCredentials(ISdAsync2 *,void *,_SID *)

- ea: `0x180013a3c`
- end: `0x180013b77`
- name: `?_SetNetworkCredentials@CSdController@@AEAAJPEAUISdAsync2@@PEAXPEAU_SID@@@Z`
- size: `315`
- prototype: `__int64 __fastcall(CSdController *this, __int64 (__fastcall ***)(struct ISdAsync2 *, GUID *, struct _SID **), void *, struct _SID *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180012948`

## callees

- `0x180013a3c`
- `0x18001586c`
- `0x180015974`
- `0x18001c58c`
- `0x180022010`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180013b3e`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180013b3e`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180013ae5`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180013ae5`

## pseudocode

```c
__int64 __fastcall CSdController::_SetNetworkCredentials(
        CSdController *this,
        __int64 (__fastcall ***a2)(struct ISdAsync2 *, GUID *, struct _SID **),
        void *a3,
        struct _SID *a4)
{
  __int16 v6; // ax
  int LastFailureAsHRESULT; // ebx
  __int64 (__fastcall **v8)(struct ISdAsync2 *, GUID *, struct _SID **); // rax
  __int16 v9; // ax
  __int64 v10; // rcx
  int v12; // [rsp+20h] [rbp-40h] BYREF
  __int16 v13; // [rsp+24h] [rbp-3Ch]
  __int16 v14; // [rsp+26h] [rbp-3Ah]
  struct _SID *v15; // [rsp+88h] [rbp+28h] BYREF

  v15 = a4;
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v12, "CSdController::_SetNetworkCredentials", 1852, 1);
  v15 = 0;
  v6 = 1857;
  if ( !a2 || (v13 = 1857, v6 = 1858, !a3) )
  {
    LastFailureAsHRESULT = -2147024809;
    v14 = v6;
    v12 = -2147024809;
    goto LABEL_14;
  }
  v13 = 1858;
  v8 = *a2;
  v12 = 0;
  LastFailureAsHRESULT = (*v8)((struct ISdAsync2 *)a2, &IID_ISdAsyncPriv, &v15);
  v12 = LastFailureAsHRESULT;
  v9 = 1860;
  if ( LastFailureAsHRESULT >= 0 )
  {
    v13 = 1860;
    if ( ImpersonateLoggedOnUser(a3) )
    {
      v13 = 1865;
      v12 = 0;
      v12 = (*(__int64 (__fastcall **)(struct _SID *, _QWORD, _QWORD))(*(_QWORD *)&v15->Revision + 248LL))(v15, 0, 0);
      if ( v12 >= 0 )
        v13 = 1874;
      else
        v14 = 1874;
      RevertToSelf();
      LastFailureAsHRESULT = v12;
      goto LABEL_12;
    }
    LastFailureAsHRESULT = GetLastFailureAsHRESULT(v10);
    v12 = LastFailureAsHRESULT;
    v9 = 1865;
  }
  v14 = v9;
LABEL_12:
  if ( v15 )
    (*(void (__fastcall **)(struct _SID *))(*(_QWORD *)&v15->Revision + 16LL))(v15);
LABEL_14:
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v12);
  return (unsigned int)LastFailureAsHRESULT;
}

```

## disassembly

```asm
0x180013a3c  mov     [rsp-8+arg_0], rbx
0x180013a41  mov     [rsp-8+arg_8], rdi
0x180013a46  mov     [rsp-8+arg_18], r9
0x180013a4b  push    rbp
0x180013a4c  mov     rbp, rsp
0x180013a4f  sub     rsp, 60h
0x180013a53  mov     rdi, r8
0x180013a56  lea     rcx, [rbp+var_40]; this
0x180013a5a  mov     rbx, rdx
0x180013a5d  mov     r8d, 73Ch; unsigned __int16
0x180013a63  lea     rdx, aCsdcontrollerS_3; "CSdController::_SetNetworkCredentials"
0x180013a6a  mov     r9d, 1; unsigned __int16
0x180013a70  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x180013a75  mov     [rbp+arg_18], 0
0x180013a7d  mov     eax, 741h
0x180013a82  test    rbx, rbx
0x180013a85  jnz     short loc_180013A98
0x180013a87  mov     ebx, 80070057h
0x180013a8c  mov     [rbp+var_3A], ax
0x180013a90  mov     [rbp+var_40], ebx
0x180013a93  jmp     loc_180013B5C
0x180013a98  mov     [rbp+var_3C], ax
0x180013a9c  mov     eax, 742h
0x180013aa1  test    rdi, rdi
0x180013aa4  jz      short loc_180013A87
0x180013aa6  mov     [rbp+var_3C], ax
0x180013aaa  lea     r8, [rbp+arg_18]
0x180013aae  mov     rax, [rbx]
0x180013ab1  lea     rdx, IID_ISdAsyncPriv
0x180013ab8  mov     rcx, rbx
0x180013abb  mov     [rbp+var_40], 0
0x180013ac2  mov     rax, [rax]
0x180013ac5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013aca  mov     ebx, eax
0x180013acc  mov     [rbp+var_40], eax
0x180013acf  test    eax, eax
0x180013ad1  mov     eax, 744h
0x180013ad6  jns     short loc_180013ADE
0x180013ad8  mov     [rbp+var_3A], ax
0x180013adc  jmp     short loc_180013B47
0x180013ade  mov     rcx, rdi; hToken
0x180013ae1  mov     [rbp+var_3C], ax
0x180013ae5  call    cs:__imp_ImpersonateLoggedOnUser
0x180013aeb  test    eax, eax
0x180013aed  jnz     short loc_180013B00
0x180013aef  call    GetLastFailureAsHRESULT
0x180013af4  mov     ebx, eax
0x180013af6  mov     [rbp+var_40], eax
0x180013af9  mov     eax, 749h
0x180013afe  jmp     short loc_180013AD8
0x180013b00  mov     rcx, [rbp+arg_18]
0x180013b04  mov     eax, 749h
0x180013b09  mov     [rbp+var_3C], ax
0x180013b0d  xor     r8d, r8d
0x180013b10  mov     [rbp+var_40], 0
0x180013b17  xor     edx, edx
0x180013b19  mov     rax, [rcx]
0x180013b1c  mov     rax, [rax+0F8h]
0x180013b23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013b28  mov     [rbp+var_40], eax
0x180013b2b  test    eax, eax
0x180013b2d  mov     eax, 752h
0x180013b32  jns     short loc_180013B3A
0x180013b34  mov     [rbp+var_3A], ax
0x180013b38  jmp     short loc_180013B3E
0x180013b3a  mov     [rbp+var_3C], ax
0x180013b3e  call    cs:__imp_RevertToSelf
0x180013b44  mov     ebx, [rbp+var_40]
0x180013b47  mov     rcx, [rbp+arg_18]
0x180013b4b  test    rcx, rcx
0x180013b4e  jz      short loc_180013B5C
0x180013b50  mov     rdx, [rcx]
0x180013b53  mov     rax, [rdx+10h]
0x180013b57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013b5c  lea     rcx, [rbp+var_40]; this
0x180013b60  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x180013b65  mov     rdi, [rsp+60h+arg_8]
0x180013b6a  mov     eax, ebx
0x180013b6c  mov     rbx, [rsp+60h+arg_0]
0x180013b71  add     rsp, 60h
0x180013b75  pop     rbp
0x180013b76  retn
```
