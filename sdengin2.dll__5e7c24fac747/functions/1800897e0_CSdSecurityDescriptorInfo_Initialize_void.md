# CSdSecurityDescriptorInfo::Initialize(void *)

- ea: `0x1800897e0`
- end: `0x18008995f`
- name: `?Initialize@CSdSecurityDescriptorInfo@@QEAAJPEAX@Z`
- size: `383`
- prototype: `__int64 __fastcall(PSID *pOwner, void *Src)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180086220`

## callees

- `0x18006fe84`
- `0x18006ff8c`
- `0x1800897e0`
- `0x18008f5d0`
- `0x1800c97c2`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x18008987d`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x18008987d`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x180089831`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x180089831`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x180089901`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x180089901`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorOwner` at `0x1800898c6`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorOwner` at `0x1800898c6`
- `ole32!CoTaskMemFree` at `0x180089936`
- `ole32!CoTaskMemFree` at `0x180089936`
- `ole32!CoTaskMemAlloc` at `0x180089887`
- `ole32!CoTaskMemAlloc` at `0x180089887`

## string_xrefs

- `0x1800897fb`: `CSdSecurityDescriptorInfo::Initialize`

## pseudocode

```c
__int64 __fastcall CSdSecurityDescriptorInfo::Initialize(PSID *pOwner, void *Src)
{
  void *v4; // rbx
  __int64 v5; // rcx
  __int16 v6; // ax
  SIZE_T SecurityDescriptorLength; // rsi
  __int64 v8; // rcx
  __int64 v9; // rcx
  unsigned int v10; // ebx
  int LastFailureAsHRESULT; // [rsp+20h] [rbp-40h] BYREF
  __int16 v13; // [rsp+24h] [rbp-3Ch]
  __int16 v14; // [rsp+26h] [rbp-3Ah]
  WORD pControl; // [rsp+90h] [rbp+30h] BYREF
  DWORD dwRevision; // [rsp+98h] [rbp+38h] BYREF

  CSxFunctionTracer::CSxFunctionTracer(
    (CSxFunctionTracer *)&LastFailureAsHRESULT,
    "CSdSecurityDescriptorInfo::Initialize",
    513,
    1);
  dwRevision = 0;
  pControl = 0;
  v4 = 0;
  if ( GetSecurityDescriptorControl(Src, &pControl, &dwRevision) )
  {
    v13 = 520;
    v6 = 524;
    if ( (pControl & 0x8000u) != 0 )
    {
      LastFailureAsHRESULT = 0;
      v13 = 524;
      SecurityDescriptorLength = GetSecurityDescriptorLength(Src);
      v4 = CoTaskMemAlloc(SecurityDescriptorLength);
      v6 = 528;
      if ( v4 )
      {
        LastFailureAsHRESULT = 0;
        v13 = 528;
        memcpy_0(v4, Src, SecurityDescriptorLength);
        if ( GetSecurityDescriptorOwner(v4, pOwner, (LPBOOL)pOwner + 2) )
        {
          LastFailureAsHRESULT = 0;
          v13 = 532;
          if ( GetSecurityDescriptorDacl(v4, (LPBOOL)pOwner + 7, (PACL *)pOwner + 2, (LPBOOL)pOwner + 6) )
          {
            pOwner[4] = v4;
            v13 = 534;
            v4 = 0;
            LastFailureAsHRESULT = 0;
            goto LABEL_13;
          }
          LastFailureAsHRESULT = GetLastFailureAsHRESULT(v9);
          v6 = 534;
        }
        else
        {
          LastFailureAsHRESULT = GetLastFailureAsHRESULT(v8);
          v6 = 532;
        }
      }
      else
      {
        LastFailureAsHRESULT = -2147024882;
      }
    }
    else
    {
      LastFailureAsHRESULT = -2147024809;
    }
  }
  else
  {
    LastFailureAsHRESULT = GetLastFailureAsHRESULT(v5);
    v6 = 520;
  }
  v14 = v6;
LABEL_13:
  CoTaskMemFree(v4);
  v10 = LastFailureAsHRESULT;
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&LastFailureAsHRESULT);
  return v10;
}

```

## disassembly

```asm
0x1800897e0  mov     [rsp-18h+arg_0], rbx
0x1800897e5  mov     [rsp-18h+arg_8], rsi
0x1800897ea  push    rbp
0x1800897eb  push    rdi
0x1800897ec  push    r14
0x1800897ee  mov     rbp, rsp
0x1800897f1  sub     rsp, 60h
0x1800897f5  mov     r14, rdx
0x1800897f8  mov     rdi, rcx
0x1800897fb  lea     rdx, aCsdsecuritydes; "CSdSecurityDescriptorInfo::Initialize"
0x180089802  mov     r9d, 1; unsigned __int16
0x180089808  lea     rcx, [rbp+var_40]; this
0x18008980c  mov     r8d, 201h; unsigned __int16
0x180089812  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x180089817  xor     eax, eax
0x180089819  mov     [rbp+dwRevision], 0
0x180089820  lea     r8, [rbp+dwRevision]; lpdwRevision
0x180089824  mov     [rbp+pControl], ax
0x180089828  lea     rdx, [rbp+pControl]; pControl
0x18008982c  mov     rcx, r14; pSecurityDescriptor
0x18008982f  xor     ebx, ebx
0x180089831  call    cs:__imp_GetSecurityDescriptorControl
0x180089837  test    eax, eax
0x180089839  jnz     short loc_180089851
0x18008983b  call    GetLastFailureAsHRESULT
0x180089840  mov     [rbp+var_40], eax
0x180089843  mov     eax, 208h
0x180089848  mov     [rbp+var_3A], ax
0x18008984c  jmp     loc_180089933
0x180089851  mov     eax, 208h
0x180089856  mov     [rbp+var_3C], ax
0x18008985a  mov     eax, 8000h
0x18008985f  test    [rbp+pControl], ax
0x180089863  mov     eax, 20Ch
0x180089868  jnz     short loc_180089873
0x18008986a  mov     [rbp+var_40], 80070057h
0x180089871  jmp     short loc_180089848
0x180089873  mov     rcx, r14; pSecurityDescriptor
0x180089876  mov     [rbp+var_40], ebx
0x180089879  mov     [rbp+var_3C], ax
0x18008987d  call    cs:__imp_GetSecurityDescriptorLength
0x180089883  mov     ecx, eax; cb
0x180089885  mov     esi, eax
0x180089887  call    cs:__imp_CoTaskMemAlloc
0x18008988d  mov     rbx, rax
0x180089890  test    rax, rax
0x180089893  mov     eax, 210h
0x180089898  jnz     short loc_1800898A3
0x18008989a  mov     [rbp+var_40], 8007000Eh
0x1800898a1  jmp     short loc_180089848
0x1800898a3  mov     r8, rsi; Size
0x1800898a6  mov     [rbp+var_40], 0
0x1800898ad  mov     rdx, r14; Src
0x1800898b0  mov     [rbp+var_3C], ax
0x1800898b4  mov     rcx, rbx; void *
0x1800898b7  call    memcpy_0
0x1800898bc  lea     r8, [rdi+8]; lpbOwnerDefaulted
0x1800898c0  mov     rdx, rdi; pOwner
0x1800898c3  mov     rcx, rbx; pSecurityDescriptor
0x1800898c6  call    cs:__imp_GetSecurityDescriptorOwner
0x1800898cc  test    eax, eax
0x1800898ce  jnz     short loc_1800898E2
0x1800898d0  call    GetLastFailureAsHRESULT
0x1800898d5  mov     [rbp+var_40], eax
0x1800898d8  mov     eax, 214h
0x1800898dd  jmp     loc_180089848
0x1800898e2  mov     eax, 214h
0x1800898e7  mov     [rbp+var_40], 0
0x1800898ee  lea     r9, [rdi+18h]; lpbDaclDefaulted
0x1800898f2  mov     [rbp+var_3C], ax
0x1800898f6  lea     r8, [rdi+10h]; pDacl
0x1800898fa  mov     rcx, rbx; pSecurityDescriptor
0x1800898fd  lea     rdx, [rdi+1Ch]; lpbDaclPresent
0x180089901  call    cs:__imp_GetSecurityDescriptorDacl
0x180089907  test    eax, eax
0x180089909  jnz     short loc_18008991D
0x18008990b  call    GetLastFailureAsHRESULT
0x180089910  mov     [rbp+var_40], eax
0x180089913  mov     eax, 216h
0x180089918  jmp     loc_180089848
0x18008991d  mov     eax, 216h
0x180089922  mov     [rdi+20h], rbx
0x180089926  mov     [rbp+var_3C], ax
0x18008992a  xor     ebx, ebx
0x18008992c  mov     [rbp+var_40], 0
0x180089933  mov     rcx, rbx; pv
0x180089936  call    cs:__imp_CoTaskMemFree
0x18008993c  mov     ebx, [rbp+var_40]
0x18008993f  lea     rcx, [rbp+var_40]; this
0x180089943  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x180089948  lea     r11, [rsp+60h+var_s0]
0x18008994d  mov     eax, ebx
0x18008994f  mov     rbx, [r11+20h]
0x180089953  mov     rsi, [r11+28h]
0x180089957  mov     rsp, r11
0x18008995a  pop     r14
0x18008995c  pop     rdi
0x18008995d  pop     rbp
0x18008995e  retn
```
