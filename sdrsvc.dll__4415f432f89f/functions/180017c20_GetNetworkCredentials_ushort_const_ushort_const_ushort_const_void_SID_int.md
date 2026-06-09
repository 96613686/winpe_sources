# GetNetworkCredentials(ushort const *,ushort const *,ushort const *,void * *,_SID *,int *)

- ea: `0x180017c20`
- end: `0x180017e02`
- name: `?GetNetworkCredentials@@YAJPEBG00PEAPEAXPEAU_SID@@PEAH@Z`
- size: `482`
- prototype: `__int64 __fastcall(const unsigned __int16 *, wchar_t *Str, LPCWSTR lpszPassword, void **, struct _SID *, int *)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1800101c0`
- `0x1800179f4`

## callees

- `0x18001586c`
- `0x180015974`
- `0x180016f68`
- `0x1800171f4`
- `0x18001764c`
- `0x180017c20`
- `0x18001c58c`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180017dd9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180017dd9`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180017d91`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180017d91`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180017d43`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180017d43`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180017dc3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180017dc3`

## pseudocode

```c
__int64 __fastcall GetNetworkCredentials(
        const unsigned __int16 *a1,
        wchar_t *Str,
        LPCWSTR lpszPassword,
        void **a4,
        struct _SID *a5,
        int *a6)
{
  char *v10; // rbx
  void *v11; // rsi
  struct _SID *v12; // rax
  __int64 v13; // rcx
  bool v14; // zf
  __int16 v15; // ax
  int v16; // eax
  bool v17; // sf
  __int64 v18; // rcx
  unsigned int v19; // edi
  int LastFailureAsHRESULT; // [rsp+20h] [rbp-40h] BYREF
  __int16 v22; // [rsp+24h] [rbp-3Ch]
  __int16 v23; // [rsp+26h] [rbp-3Ah]
  HANDLE hToken; // [rsp+A0h] [rbp+40h] BYREF
  LPVOID pv; // [rsp+B8h] [rbp+58h] BYREF

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&LastFailureAsHRESULT, "GetNetworkCredentials", 84, 1);
  pv = 0;
  v10 = 0;
  hToken = 0;
  v11 = 0;
  if ( a6 )
    *a6 = 0;
  if ( a4 )
    *a4 = 0;
  v12 = a5;
  v13 = 68;
  do
  {
    v12->Revision = 0;
    v12 = (struct _SID *)((char *)v12 + 1);
    --v13;
  }
  while ( v13 );
  if ( !a1 || !*a1 )
  {
    v15 = 94;
    goto LABEL_25;
  }
  LastFailureAsHRESULT = 0;
  v22 = 94;
  v14 = (unsigned int)SdIsPathUNC(a1) == 0;
  v15 = 95;
  if ( !v14 )
    goto LABEL_25;
  v22 = 95;
  v15 = 96;
  if ( !a4 )
    goto LABEL_25;
  v22 = 96;
  if ( !Str || !*Str )
  {
    v15 = 97;
    goto LABEL_25;
  }
  v22 = 97;
  if ( !lpszPassword || !*lpszPassword )
  {
    v15 = 98;
LABEL_25:
    LastFailureAsHRESULT = -2147024809;
    goto LABEL_26;
  }
  LastFailureAsHRESULT = 0;
  v22 = 98;
  v16 = CreateNetworkAccessTokenFromCreds(Str, lpszPassword, &hToken);
  v10 = (char *)hToken;
  v17 = v16 < 0;
  LastFailureAsHRESULT = v16;
  v15 = 103;
  if ( v17 )
  {
LABEL_26:
    v23 = v15;
    goto LABEL_27;
  }
  v22 = 103;
  if ( !ImpersonateLoggedOnUser(hToken) )
  {
    LastFailureAsHRESULT = GetLastFailureAsHRESULT(v18);
    v15 = 104;
    goto LABEL_26;
  }
  LastFailureAsHRESULT = 0;
  v22 = 104;
  LastFailureAsHRESULT = GetMachineNameFromUNC(a1, (unsigned __int16 **)&pv);
  if ( LastFailureAsHRESULT >= 0 )
  {
    *a4 = v10;
    v10 = 0;
    v22 = 113;
  }
  else
  {
    v23 = 113;
  }
  RevertToSelf();
  v11 = pv;
LABEL_27:
  if ( v11 )
    CoTaskMemFree(v11);
  v19 = LastFailureAsHRESULT;
  if ( (unsigned __int64)(v10 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v10);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&LastFailureAsHRESULT);
  return v19;
}

```

## disassembly

```asm
0x180017c20  mov     [rsp-38h+arg_8], rbx
0x180017c25  push    rbp
0x180017c26  push    rsi
0x180017c27  push    rdi
0x180017c28  push    r12
0x180017c2a  push    r13
0x180017c2c  push    r14
0x180017c2e  push    r15
0x180017c30  mov     rbp, rsp
0x180017c33  sub     rsp, 60h
0x180017c37  mov     rdi, r9
0x180017c3a  mov     r15, r8
0x180017c3d  mov     r9d, 1; unsigned __int16
0x180017c43  mov     r12, rdx
0x180017c46  mov     r14, rcx
0x180017c49  lea     rdx, aGetnetworkcred; "GetNetworkCredentials"
0x180017c50  lea     rcx, [rbp+var_40]; this
0x180017c54  lea     r8d, [r9+53h]; unsigned __int16
0x180017c58  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x180017c5d  mov     rax, [rbp+arg_28]
0x180017c61  xor     r13d, r13d
0x180017c64  mov     [rbp+pv], r13
0x180017c68  mov     ebx, r13d
0x180017c6b  mov     [rbp+hToken], rbx
0x180017c6f  mov     esi, r13d
0x180017c72  test    rax, rax
0x180017c75  jz      short loc_180017C7A
0x180017c77  mov     [rax], r13d
0x180017c7a  test    rdi, rdi
0x180017c7d  jz      short loc_180017C82
0x180017c7f  mov     [rdi], r13
0x180017c82  mov     rax, [rbp+arg_20]
0x180017c86  mov     ecx, 44h ; 'D'
0x180017c8b  mov     [rax], r13b
0x180017c8e  inc     rax
0x180017c91  sub     rcx, 1
0x180017c95  jnz     short loc_180017C8B
0x180017c97  test    r14, r14
0x180017c9a  jz      loc_180017DAB
0x180017ca0  cmp     [r14], r13w
0x180017ca4  jz      loc_180017DAB
0x180017caa  lea     eax, [rcx+5Eh]
0x180017cad  mov     [rbp+var_40], r13d
0x180017cb1  mov     rcx, r14; unsigned __int16 *
0x180017cb4  mov     [rbp+var_3C], ax
0x180017cb8  call    ?SdIsPathUNC@@YAJPEBG@Z; SdIsPathUNC(ushort const *)
0x180017cbd  test    eax, eax
0x180017cbf  mov     eax, 5Fh ; '_'
0x180017cc4  jnz     loc_180017DB0
0x180017cca  mov     [rbp+var_3C], ax
0x180017cce  mov     eax, 60h ; '`'
0x180017cd3  test    rdi, rdi
0x180017cd6  jz      loc_180017DB0
0x180017cdc  mov     [rbp+var_3C], ax
0x180017ce0  test    r12, r12
0x180017ce3  jz      loc_180017DA4
0x180017ce9  cmp     [r12], r13w
0x180017cee  jz      loc_180017DA4
0x180017cf4  mov     eax, 61h ; 'a'
0x180017cf9  mov     [rbp+var_3C], ax
0x180017cfd  test    r15, r15
0x180017d00  jz      loc_180017D9D
0x180017d06  cmp     [r15], r13w
0x180017d0a  jz      loc_180017D9D
0x180017d10  mov     eax, 62h ; 'b'
0x180017d15  mov     [rbp+var_40], r13d
0x180017d19  lea     r8, [rbp+hToken]; void **
0x180017d1d  mov     [rbp+var_3C], ax
0x180017d21  mov     rdx, r15; lpszPassword
0x180017d24  mov     rcx, r12; Str
0x180017d27  call    ?CreateNetworkAccessTokenFromCreds@@YAJPEBG0PEAPEAX@Z; CreateNetworkAccessTokenFromCreds(ushort const *,ushort const *,void * *)
0x180017d2c  mov     rbx, [rbp+hToken]
0x180017d30  test    eax, eax
0x180017d32  mov     [rbp+var_40], eax
0x180017d35  mov     eax, 67h ; 'g'
0x180017d3a  js      short loc_180017DB7
0x180017d3c  mov     rcx, rbx; hToken
0x180017d3f  mov     [rbp+var_3C], ax
0x180017d43  call    cs:__imp_ImpersonateLoggedOnUser
0x180017d49  test    eax, eax
0x180017d4b  jnz     short loc_180017D5C
0x180017d4d  call    GetLastFailureAsHRESULT
0x180017d52  mov     [rbp+var_40], eax
0x180017d55  mov     eax, 68h ; 'h'
0x180017d5a  jmp     short loc_180017DB7
0x180017d5c  mov     eax, 68h ; 'h'
0x180017d61  mov     [rbp+var_40], r13d
0x180017d65  lea     rdx, [rbp+pv]; unsigned __int16 **
0x180017d69  mov     [rbp+var_3C], ax
0x180017d6d  mov     rcx, r14; unsigned __int16 *
0x180017d70  call    ?GetMachineNameFromUNC@@YAJPEBGPEAPEAG@Z; GetMachineNameFromUNC(ushort const *,ushort * *)
0x180017d75  mov     [rbp+var_40], eax
0x180017d78  test    eax, eax
0x180017d7a  mov     eax, 71h ; 'q'
0x180017d7f  jns     short loc_180017D87
0x180017d81  mov     [rbp+var_3A], ax
0x180017d85  jmp     short loc_180017D91
0x180017d87  mov     [rdi], rbx
0x180017d8a  mov     rbx, r13
0x180017d8d  mov     [rbp+var_3C], ax
0x180017d91  call    cs:__imp_RevertToSelf
0x180017d97  mov     rsi, [rbp+pv]
0x180017d9b  jmp     short loc_180017DBB
0x180017d9d  mov     eax, 62h ; 'b'
0x180017da2  jmp     short loc_180017DB0
0x180017da4  mov     eax, 61h ; 'a'
0x180017da9  jmp     short loc_180017DB0
0x180017dab  mov     eax, 5Eh ; '^'
0x180017db0  mov     [rbp+var_40], 80070057h
0x180017db7  mov     [rbp+var_3A], ax
0x180017dbb  test    rsi, rsi
0x180017dbe  jz      short loc_180017DC9
0x180017dc0  mov     rcx, rsi; pv
0x180017dc3  call    cs:__imp_CoTaskMemFree
0x180017dc9  mov     edi, [rbp+var_40]
0x180017dcc  lea     rcx, [rbx-1]
0x180017dd0  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x180017dd4  ja      short loc_180017DDF
0x180017dd6  mov     rcx, rbx; hObject
0x180017dd9  call    cs:__imp_CloseHandle
0x180017ddf  lea     rcx, [rbp+var_40]; this
0x180017de3  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x180017de8  mov     rbx, [rsp+60h+arg_8]
0x180017df0  mov     eax, edi
0x180017df2  add     rsp, 60h
0x180017df6  pop     r15
0x180017df8  pop     r14
0x180017dfa  pop     r13
0x180017dfc  pop     r12
0x180017dfe  pop     rdi
0x180017dff  pop     rsi
0x180017e00  pop     rbp
0x180017e01  retn
```
