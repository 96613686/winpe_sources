# CSdBackupImpl::_CheckIfLocalSid(void * const,ulong *,int *)

- ea: `0x1800184f0`
- end: `0x1800186e3`
- name: `?_CheckIfLocalSid@CSdBackupImpl@@AEAAJQEAXPEAKPEAH@Z`
- size: `499`
- prototype: `int(CSdBackupImpl *__hidden this, void *const, unsigned int *, int *)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001ee44`
- `0x180021eb8`

## callees

- `0x1800184f0`
- `0x180072e08`
- `0x180072f14`
- `0x1800935fc`
- `0x1800cf56a`
- `0x1800cf5c0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180018625`
- `KERNEL32!GetLastError` at `0x180018625`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1800186ac`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1800186ac`
- `api-ms-win-security-base-l1-1-0!GetWindowsAccountDomainSid` at `0x180018615`
- `api-ms-win-security-base-l1-1-0!GetWindowsAccountDomainSid` at `0x180018615`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800185de`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800185de`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1800185aa`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180018657`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1800185aa`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180018657`

## string_xrefs

- `0x180018529`: `CSdBackupImpl::_CheckIfLocalSid`

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

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v17, "CSdBackupImpl::_CheckIfLocalSid", 0xBA6u, 1u);
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
0x1800184f0  push    rbp
0x1800184f2  push    rbx
0x1800184f3  push    rsi
0x1800184f4  push    rdi
0x1800184f5  push    r14
0x1800184f7  lea     rbp, [rsp-37h]
0x1800184fc  sub     rsp, 0C0h
0x180018503  mov     rax, cs:__security_cookie
0x18001850a  xor     rax, rsp
0x18001850d  mov     [rbp+57h+var_30], rax
0x180018511  mov     rdi, r9
0x180018514  mov     rbx, r8
0x180018517  mov     rsi, rdx
0x18001851a  mov     r14, rcx
0x18001851d  mov     r9d, 1; unsigned __int16
0x180018523  mov     r8d, 0BA6h; unsigned __int16
0x180018529  lea     rdx, aCsdbackupimplC_5; "CSdBackupImpl::_CheckIfLocalSid"
0x180018530  lea     rcx, [rbp+57h+var_B8]; this
0x180018534  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x180018539  xor     edx, edx; Val
0x18001853b  lea     r8d, [rdx+48h]; Size
0x18001853f  lea     rcx, [rbp+57h+pDomainSid]; void *
0x180018543  call    memset_0
0x180018548  mov     [rbp+57h+cbDomainSid], 44h ; 'D'
0x18001854f  test    rdi, rdi
0x180018552  jz      short loc_18001855A
0x180018554  mov     dword ptr [rdi], 0
0x18001855a  test    rbx, rbx
0x18001855d  jz      short loc_180018565
0x18001855f  mov     dword ptr [rbx], 0
0x180018565  mov     eax, 0BB0h
0x18001856a  test    rsi, rsi
0x18001856d  jnz     short loc_180018580
0x18001856f  mov     ebx, 80070057h
0x180018574  mov     [rbp+57h+var_B8], ebx
0x180018577  mov     [rbp+57h+var_B2], ax
0x18001857b  jmp     loc_1800186BD
0x180018580  mov     [rbp+57h+var_B4], ax
0x180018584  mov     eax, 0BB1h
0x180018589  test    rbx, rbx
0x18001858c  jz      short loc_18001856F
0x18001858e  mov     [rbp+57h+var_B4], ax
0x180018592  mov     eax, 0BB2h
0x180018597  test    rdi, rdi
0x18001859a  jz      short loc_18001856F
0x18001859c  mov     [rbp+57h+var_B8], 0
0x1800185a3  mov     [rbp+57h+var_B4], ax
0x1800185a7  mov     rcx, rsi; pSid
0x1800185aa  call    cs:__imp_IsValidSid
0x1800185b1  nop     dword ptr [rax+rax+00h]
0x1800185b6  test    eax, eax
0x1800185b8  jnz     short loc_1800185CB
0x1800185ba  call    GetLastFailureAsHRESULT
0x1800185bf  mov     ebx, eax
0x1800185c1  mov     [rbp+57h+var_B8], eax
0x1800185c4  mov     eax, 0BB4h
0x1800185c9  jmp     short loc_180018577
0x1800185cb  mov     [rbp+57h+var_B8], 0
0x1800185d2  mov     eax, 0BB4h
0x1800185d7  mov     [rbp+57h+var_B4], ax
0x1800185db  mov     rcx, rsi; pSid
0x1800185de  call    cs:__imp_GetLengthSid
0x1800185e5  nop     dword ptr [rax+rax+00h]
0x1800185ea  mov     [rbx], eax
0x1800185ec  cmp     [r14+110h], eax
0x1800185f3  jb      short loc_18001860A
0x1800185f5  mov     eax, 0BBCh
0x1800185fa  xor     ebx, ebx
0x1800185fc  mov     [rbp+57h+var_B8], ebx
0x1800185ff  mov     [rdi], ebx
0x180018601  mov     [rbp+57h+var_B4], ax
0x180018605  jmp     loc_1800186BD
0x18001860a  lea     r8, [rbp+57h+cbDomainSid]; cbDomainSid
0x18001860e  lea     rdx, [rbp+57h+pDomainSid]; pDomainSid
0x180018612  mov     rcx, rsi; pSid
0x180018615  call    cs:__imp_GetWindowsAccountDomainSid
0x18001861c  nop     dword ptr [rax+rax+00h]
0x180018621  test    eax, eax
0x180018623  jnz     short loc_180018653
0x180018625  call    cs:__imp_GetLastError
0x18001862c  nop     dword ptr [rax+rax+00h]
0x180018631  cmp     eax, 4E9h
0x180018636  jz      short loc_18001864C
0x180018638  call    GetLastFailureAsHRESULT
0x18001863d  mov     ebx, eax
0x18001863f  mov     [rbp+57h+var_B8], eax
0x180018642  mov     eax, 0BC2h
0x180018647  jmp     loc_180018577
0x18001864c  mov     eax, 0BC4h
0x180018651  jmp     short loc_1800185FA
0x180018653  lea     rcx, [rbp+57h+pDomainSid]; pSid
0x180018657  call    cs:__imp_IsValidSid
0x18001865e  nop     dword ptr [rax+rax+00h]
0x180018663  test    eax, eax
0x180018665  jnz     short loc_18001867B
0x180018667  call    GetLastFailureAsHRESULT
0x18001866c  mov     ebx, eax
0x18001866e  mov     [rbp+57h+var_B8], eax
0x180018671  mov     eax, 0BC7h
0x180018676  jmp     loc_180018577
0x18001867b  xor     ebx, ebx
0x18001867d  mov     [rbp+57h+var_B8], ebx
0x180018680  mov     eax, 0BC7h
0x180018685  mov     [rbp+57h+var_B4], ax
0x180018689  mov     eax, [rbp+57h+cbDomainSid]
0x18001868c  cmp     [r14+110h], eax
0x180018693  jz      short loc_1800186A1
0x180018695  mov     [rdi], ebx
0x180018697  mov     eax, 0BCCh
0x18001869c  jmp     loc_180018601
0x1800186a1  lea     rdx, [rbp+57h+pDomainSid]; pSid2
0x1800186a5  mov     rcx, [r14+108h]; pSid1
0x1800186ac  call    cs:__imp_EqualSid
0x1800186b3  nop     dword ptr [rax+rax+00h]
0x1800186b8  mov     [rdi], eax
0x1800186ba  mov     ebx, [rbp+57h+var_B8]
0x1800186bd  lea     rcx, [rbp+57h+var_B8]; this
0x1800186c1  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x1800186c6  mov     eax, ebx
0x1800186c8  mov     rcx, [rbp+57h+var_30]
0x1800186cc  xor     rcx, rsp; StackCookie
0x1800186cf  call    __security_check_cookie
0x1800186d4  add     rsp, 0C0h
0x1800186db  pop     r14
0x1800186dd  pop     rdi
0x1800186de  pop     rsi
0x1800186df  pop     rbx
0x1800186e0  pop     rbp
0x1800186e1  retn
```
