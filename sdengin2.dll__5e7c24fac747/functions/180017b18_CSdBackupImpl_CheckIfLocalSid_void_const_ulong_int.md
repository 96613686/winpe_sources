# CSdBackupImpl::_CheckIfLocalSid(void * const,ulong *,int *)

- ea: `0x180017b18`
- end: `0x180017ce6`
- name: `?_CheckIfLocalSid@CSdBackupImpl@@AEAAJQEAXPEAKPEAH@Z`
- size: `462`
- prototype: `int(CSdBackupImpl *__hidden this, void *const, unsigned int *, int *)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001e33c`
- `0x1800212c4`

## callees

- `0x180017b18`
- `0x18006fe84`
- `0x18006ff8c`
- `0x18008f5d0`
- `0x1800c97da`
- `0x1800c9830`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180017c3b`
- `KERNEL32!GetLastError` at `0x180017c3b`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180017cb6`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180017cb6`
- `api-ms-win-security-base-l1-1-0!GetWindowsAccountDomainSid` at `0x180017c31`
- `api-ms-win-security-base-l1-1-0!GetWindowsAccountDomainSid` at `0x180017c31`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180017c00`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180017c00`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180017bd2`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180017c67`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180017bd2`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180017c67`

## string_xrefs

- `0x180017b51`: `CSdBackupImpl::_CheckIfLocalSid`

## pseudocode

```c
__int64 __fastcall CSdBackupImpl::_CheckIfLocalSid(PSID *this, void *const a2, unsigned int *a3, int *a4)
{
  __int16 v8; // ax
  unsigned int LastFailureAsHRESULT; // ebx
  __int64 v10; // rcx
  DWORD LengthSid; // eax
  __int16 v12; // ax
  __int64 v13; // rcx
  __int64 v14; // rcx
  DWORD cbDomainSid; // [rsp+20h] [rbp-69h] BYREF
  int v17; // [rsp+28h] [rbp-61h] BYREF
  __int16 v18; // [rsp+2Ch] [rbp-5Dh]
  __int16 v19; // [rsp+2Eh] [rbp-5Bh]
  _BYTE pDomainSid[80]; // [rsp+60h] [rbp-29h] BYREF

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v17, "CSdBackupImpl::_CheckIfLocalSid", 2982, 1);
  memset_0(pDomainSid, 0, 0x48u);
  cbDomainSid = 68;
  if ( a4 )
    *a4 = 0;
  if ( a3 )
    *a3 = 0;
  v8 = 2992;
  if ( a2 )
  {
    v18 = 2992;
    v8 = 2993;
    if ( a3 )
    {
      v18 = 2993;
      v8 = 2994;
      if ( a4 )
      {
        v17 = 0;
        v18 = 2994;
        if ( !IsValidSid(a2) )
        {
          LastFailureAsHRESULT = GetLastFailureAsHRESULT(v10);
          v17 = LastFailureAsHRESULT;
          v8 = 2996;
          goto LABEL_7;
        }
        v17 = 0;
        v18 = 2996;
        LengthSid = GetLengthSid(a2);
        *a3 = LengthSid;
        if ( *((_DWORD *)this + 68) < LengthSid )
        {
          if ( GetWindowsAccountDomainSid(a2, pDomainSid, &cbDomainSid) )
          {
            if ( !IsValidSid(pDomainSid) )
            {
              LastFailureAsHRESULT = GetLastFailureAsHRESULT(v14);
              v17 = LastFailureAsHRESULT;
              v8 = 3015;
              goto LABEL_7;
            }
            LastFailureAsHRESULT = 0;
            v17 = 0;
            v18 = 3015;
            if ( *((_DWORD *)this + 68) == cbDomainSid )
            {
              *a4 = EqualSid(this[33], pDomainSid);
              LastFailureAsHRESULT = v17;
              goto LABEL_25;
            }
            *a4 = 0;
            v12 = 3020;
LABEL_15:
            v18 = v12;
            goto LABEL_25;
          }
          if ( GetLastError() != 1257 )
          {
            LastFailureAsHRESULT = GetLastFailureAsHRESULT(v13);
            v17 = LastFailureAsHRESULT;
            v8 = 3010;
            goto LABEL_7;
          }
          v12 = 3012;
        }
        else
        {
          v12 = 3004;
        }
        LastFailureAsHRESULT = 0;
        v17 = 0;
        *a4 = 0;
        goto LABEL_15;
      }
    }
  }
  LastFailureAsHRESULT = -2147024809;
  v17 = -2147024809;
LABEL_7:
  v19 = v8;
LABEL_25:
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v17);
  return LastFailureAsHRESULT;
}

```

## disassembly

```asm
0x180017b18  push    rbp
0x180017b1a  push    rbx
0x180017b1b  push    rsi
0x180017b1c  push    rdi
0x180017b1d  push    r14
0x180017b1f  lea     rbp, [rsp-37h]
0x180017b24  sub     rsp, 0C0h
0x180017b2b  mov     rax, cs:__security_cookie
0x180017b32  xor     rax, rsp
0x180017b35  mov     [rbp+57h+var_30], rax
0x180017b39  mov     rdi, r9
0x180017b3c  mov     rbx, r8
0x180017b3f  mov     rsi, rdx
0x180017b42  mov     r14, rcx
0x180017b45  mov     r9d, 1; unsigned __int16
0x180017b4b  mov     r8d, 0BA6h; unsigned __int16
0x180017b51  lea     rdx, aCsdbackupimplC_5; "CSdBackupImpl::_CheckIfLocalSid"
0x180017b58  lea     rcx, [rbp+57h+var_B8]; this
0x180017b5c  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x180017b61  xor     edx, edx; Val
0x180017b63  lea     r8d, [rdx+48h]; Size
0x180017b67  lea     rcx, [rbp+57h+pDomainSid]; void *
0x180017b6b  call    memset_0
0x180017b70  mov     [rbp+57h+cbDomainSid], 44h ; 'D'
0x180017b77  test    rdi, rdi
0x180017b7a  jz      short loc_180017B82
0x180017b7c  mov     dword ptr [rdi], 0
0x180017b82  test    rbx, rbx
0x180017b85  jz      short loc_180017B8D
0x180017b87  mov     dword ptr [rbx], 0
0x180017b8d  mov     eax, 0BB0h
0x180017b92  test    rsi, rsi
0x180017b95  jnz     short loc_180017BA8
0x180017b97  mov     ebx, 80070057h
0x180017b9c  mov     [rbp+57h+var_B8], ebx
0x180017b9f  mov     [rbp+57h+var_B2], ax
0x180017ba3  jmp     loc_180017CC1
0x180017ba8  mov     [rbp+57h+var_B4], ax
0x180017bac  mov     eax, 0BB1h
0x180017bb1  test    rbx, rbx
0x180017bb4  jz      short loc_180017B97
0x180017bb6  mov     [rbp+57h+var_B4], ax
0x180017bba  mov     eax, 0BB2h
0x180017bbf  test    rdi, rdi
0x180017bc2  jz      short loc_180017B97
0x180017bc4  mov     [rbp+57h+var_B8], 0
0x180017bcb  mov     [rbp+57h+var_B4], ax
0x180017bcf  mov     rcx, rsi; pSid
0x180017bd2  call    cs:__imp_IsValidSid
0x180017bd8  test    eax, eax
0x180017bda  jnz     short loc_180017BED
0x180017bdc  call    GetLastFailureAsHRESULT
0x180017be1  mov     ebx, eax
0x180017be3  mov     [rbp+57h+var_B8], eax
0x180017be6  mov     eax, 0BB4h
0x180017beb  jmp     short loc_180017B9F
0x180017bed  mov     [rbp+57h+var_B8], 0
0x180017bf4  mov     eax, 0BB4h
0x180017bf9  mov     [rbp+57h+var_B4], ax
0x180017bfd  mov     rcx, rsi; pSid
0x180017c00  call    cs:__imp_GetLengthSid
0x180017c06  mov     [rbx], eax
0x180017c08  cmp     [r14+110h], eax
0x180017c0f  jb      short loc_180017C26
0x180017c11  mov     eax, 0BBCh
0x180017c16  xor     ebx, ebx
0x180017c18  mov     [rbp+57h+var_B8], ebx
0x180017c1b  mov     [rdi], ebx
0x180017c1d  mov     [rbp+57h+var_B4], ax
0x180017c21  jmp     loc_180017CC1
0x180017c26  lea     r8, [rbp+57h+cbDomainSid]; cbDomainSid
0x180017c2a  lea     rdx, [rbp+57h+pDomainSid]; pDomainSid
0x180017c2e  mov     rcx, rsi; pSid
0x180017c31  call    cs:__imp_GetWindowsAccountDomainSid
0x180017c37  test    eax, eax
0x180017c39  jnz     short loc_180017C63
0x180017c3b  call    cs:__imp_GetLastError
0x180017c41  cmp     eax, 4E9h
0x180017c46  jz      short loc_180017C5C
0x180017c48  call    GetLastFailureAsHRESULT
0x180017c4d  mov     ebx, eax
0x180017c4f  mov     [rbp+57h+var_B8], eax
0x180017c52  mov     eax, 0BC2h
0x180017c57  jmp     loc_180017B9F
0x180017c5c  mov     eax, 0BC4h
0x180017c61  jmp     short loc_180017C16
0x180017c63  lea     rcx, [rbp+57h+pDomainSid]; pSid
0x180017c67  call    cs:__imp_IsValidSid
0x180017c6d  test    eax, eax
0x180017c6f  jnz     short loc_180017C85
0x180017c71  call    GetLastFailureAsHRESULT
0x180017c76  mov     ebx, eax
0x180017c78  mov     [rbp+57h+var_B8], eax
0x180017c7b  mov     eax, 0BC7h
0x180017c80  jmp     loc_180017B9F
0x180017c85  xor     ebx, ebx
0x180017c87  mov     [rbp+57h+var_B8], ebx
0x180017c8a  mov     eax, 0BC7h
0x180017c8f  mov     [rbp+57h+var_B4], ax
0x180017c93  mov     eax, [rbp+57h+cbDomainSid]
0x180017c96  cmp     [r14+110h], eax
0x180017c9d  jz      short loc_180017CAB
0x180017c9f  mov     [rdi], ebx
0x180017ca1  mov     eax, 0BCCh
0x180017ca6  jmp     loc_180017C1D
0x180017cab  lea     rdx, [rbp+57h+pDomainSid]; pSid2
0x180017caf  mov     rcx, [r14+108h]; pSid1
0x180017cb6  call    cs:__imp_EqualSid
0x180017cbc  mov     [rdi], eax
0x180017cbe  mov     ebx, [rbp+57h+var_B8]
0x180017cc1  lea     rcx, [rbp+57h+var_B8]; this
0x180017cc5  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x180017cca  mov     eax, ebx
0x180017ccc  mov     rcx, [rbp+57h+var_30]
0x180017cd0  xor     rcx, rsp; StackCookie
0x180017cd3  call    __security_check_cookie
0x180017cd8  add     rsp, 0C0h
0x180017cdf  pop     r14
0x180017ce1  pop     rdi
0x180017ce2  pop     rsi
0x180017ce3  pop     rbx
0x180017ce4  pop     rbp
0x180017ce5  retn
```
