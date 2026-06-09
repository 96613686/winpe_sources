# SsIsCallerClusterAccount

- ea: `0x1800289a4`
- end: `0x180028b01`
- name: `SsIsCallerClusterAccount`
- size: `349`
- prototype: `__int64(void)`
- caller_count: `7`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180021ad0`
- `0x180021b30`
- `0x180021c60`
- `0x180028d50`
- `0x180028db0`
- `0x180028ed0`
- `0x18002d300`

## callees

- `0x18000a460`
- `0x18001deb0`
- `0x18001def0`
- `0x1800284b4`
- `0x1800289a4`
- `0x180044010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180028a6f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180028ac3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180028a6f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180028ac3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180028aa6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180028aa6`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180028a7e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180028a7e`

## string_xrefs

- `0x180028a8a`: `ClusterAccountSecurityObject`

## pseudocode

```c
char SsIsCallerClusterAccount()
{
  __int64 v0; // rax
  __int64 v1; // rdi
  DWORD v2; // eax
  unsigned int v3; // ecx
  __int64 v4; // rax
  unsigned __int64 v5; // rcx
  DWORD ClusterAccountSecurityObjectIfNeccesary; // eax
  DWORD v7; // ecx
  char v8; // bl
  int v9; // ebx
  unsigned int v11[4]; // [rsp+30h] [rbp-238h] BYREF
  wchar_t pszSrc[264]; // [rsp+40h] [rbp-228h] BYREF

  v11[0] = 262;
  if ( qword_18005E5A8 )
  {
    if ( qword_18005E620 )
    {
      v0 = qword_18005E5A8(0);
      v1 = v0;
      if ( v0 )
      {
        v2 = ((__int64 (__fastcall *)(__int64, wchar_t *, unsigned int *, _QWORD))qword_18005E620)(v0, pszSrc, v11, 0);
        if ( v2 || (v3 = v11[0], 262 - v11[0] < 2) )
        {
          SetLastError(v2);
          v8 = 0;
          goto LABEL_17;
        }
        if ( v11[0] > 0xF )
        {
          v3 = 15;
          v11[0] = 15;
        }
        v4 = v3;
        v5 = v3 + 1;
        pszSrc[v4] = 36;
        if ( v5 >= 262 )
          _report_rangecheckfailure();
        pszSrc[v5] = 0;
        ClusterAccountSecurityObjectIfNeccesary = SsCreateClusterAccountSecurityObjectIfNeccesary(pszSrc);
        if ( ClusterAccountSecurityObjectIfNeccesary )
        {
          v7 = ClusterAccountSecurityObjectIfNeccesary;
        }
        else
        {
          AcquireSRWLockShared(&SsClusterAccountSDRWLock);
          v9 = SsCheckAccess((__int64)SsClusterAccountSecurityObject, L"ClusterAccountSecurityObject", 0x20000u);
          ReleaseSRWLockShared(&SsClusterAccountSDRWLock);
          if ( !v9 )
          {
            v8 = 1;
            goto LABEL_17;
          }
          v7 = 5;
        }
        v8 = 0;
        SetLastError(v7);
LABEL_17:
        ((void (__fastcall *)(__int64))qword_18005E5B0)(v1);
        return v8;
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1800289a4  mov     [rsp+arg_0], rbx
0x1800289a9  push    rdi
0x1800289aa  sub     rsp, 260h
0x1800289b1  mov     rax, cs:__security_cookie
0x1800289b8  xor     rax, rsp
0x1800289bb  mov     [rsp+268h+var_18], rax
0x1800289c3  mov     rax, cs:qword_18005E5A8
0x1800289ca  mov     ebx, 106h
0x1800289cf  mov     [rsp+268h+var_238], ebx
0x1800289d3  test    rax, rax
0x1800289d6  jz      loc_180028ADE
0x1800289dc  cmp     cs:qword_18005E620, 0
0x1800289e4  jz      loc_180028ADE
0x1800289ea  xor     ecx, ecx
0x1800289ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800289f1  mov     rdi, rax
0x1800289f4  test    rax, rax
0x1800289f7  jz      loc_180028ADE
0x1800289fd  mov     rcx, rax
0x180028a00  lea     r8, [rsp+268h+var_238]
0x180028a05  mov     rax, cs:qword_18005E620
0x180028a0c  lea     rdx, [rsp+268h+pszSrc]
0x180028a11  xor     r9d, r9d
0x180028a14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028a19  test    eax, eax
0x180028a1b  jnz     loc_180028AC1
0x180028a21  mov     ecx, [rsp+268h+var_238]
0x180028a25  sub     ebx, ecx
0x180028a27  cmp     ebx, 2
0x180028a2a  jb      loc_180028AC1
0x180028a30  cmp     ecx, 0Fh
0x180028a33  jbe     short loc_180028A3C
0x180028a35  lea     ecx, [rax+0Fh]
0x180028a38  mov     [rsp+268h+var_238], ecx
0x180028a3c  mov     eax, ecx
0x180028a3e  mov     edx, 24h ; '$'
0x180028a43  inc     ecx
0x180028a45  add     rcx, rcx
0x180028a48  mov     [rsp+rax*2+268h+pszSrc], dx
0x180028a4d  cmp     rcx, 20Ch
0x180028a54  jnb     short loc_180028ABB
0x180028a56  xor     eax, eax
0x180028a58  mov     [rsp+rcx+268h+pszSrc], ax
0x180028a5d  lea     rcx, [rsp+268h+pszSrc]; pszSrc
0x180028a62  call    SsCreateClusterAccountSecurityObjectIfNeccesary
0x180028a67  test    eax, eax
0x180028a69  jz      short loc_180028A77
0x180028a6b  mov     ecx, eax; dwErrCode
0x180028a6d  xor     bl, bl
0x180028a6f  call    cs:__imp_SetLastError
0x180028a75  jmp     short loc_180028ACB
0x180028a77  lea     rcx, SsClusterAccountSDRWLock; SRWLock
0x180028a7e  call    cs:__imp_AcquireSRWLockShared
0x180028a84  mov     r8d, 20000h
0x180028a8a  lea     rdx, aClusteraccount; "ClusterAccountSecurityObject"
0x180028a91  lea     rcx, SsClusterAccountSecurityObject
0x180028a98  call    SsCheckAccess
0x180028a9d  lea     rcx, SsClusterAccountSDRWLock; SRWLock
0x180028aa4  mov     ebx, eax
0x180028aa6  call    cs:__imp_ReleaseSRWLockShared
0x180028aac  test    ebx, ebx
0x180028aae  jz      short loc_180028AB7
0x180028ab0  mov     ecx, 5
0x180028ab5  jmp     short loc_180028A6D
0x180028ab7  mov     bl, 1
0x180028ab9  jmp     short loc_180028ACB
0x180028abb  call    __report_rangecheckfailure
0x180028ac1  mov     ecx, eax; dwErrCode
0x180028ac3  call    cs:__imp_SetLastError
0x180028ac9  xor     bl, bl
0x180028acb  mov     rax, cs:qword_18005E5B0
0x180028ad2  mov     rcx, rdi
0x180028ad5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028ada  mov     al, bl
0x180028adc  jmp     short loc_180028AE0
0x180028ade  xor     al, al
0x180028ae0  mov     rcx, [rsp+268h+var_18]
0x180028ae8  xor     rcx, rsp; StackCookie
0x180028aeb  call    __security_check_cookie
0x180028af0  mov     rbx, [rsp+268h+arg_0]
0x180028af8  add     rsp, 260h
0x180028aff  pop     rdi
0x180028b00  retn
```
