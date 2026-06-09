# CSdSecurityDescriptorInfo::Initialize(void *)

- ea: `0x18008d33c`
- end: `0x18008d4e0`
- name: `?Initialize@CSdSecurityDescriptorInfo@@QEAAJPEAX@Z`
- size: `420`
- prototype: `__int64 __fastcall(PSID *pOwner, void *Src)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180089b20`

## callees

- `0x180072e08`
- `0x180072f14`
- `0x18008d33c`
- `0x1800935fc`
- `0x1800cf552`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x18008d3df`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x18008d3df`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x18008d38d`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x18008d38d`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x18008d475`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x18008d475`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorOwner` at `0x18008d434`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorOwner` at `0x18008d434`
- `ole32!CoTaskMemFree` at `0x18008d4b0`
- `ole32!CoTaskMemFree` at `0x18008d4b0`
- `ole32!CoTaskMemAlloc` at `0x18008d3ef`
- `ole32!CoTaskMemAlloc` at `0x18008d3ef`

## string_xrefs

- `0x18008d357`: `CSdSecurityDescriptorInfo::Initialize`

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
    0x201u,
    1u);
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
0x18008d33c  mov     [rsp-18h+arg_0], rbx
0x18008d341  mov     [rsp-18h+arg_8], rsi
0x18008d346  push    rbp
0x18008d347  push    rdi
0x18008d348  push    r14
0x18008d34a  mov     rbp, rsp
0x18008d34d  sub     rsp, 60h
0x18008d351  mov     r14, rdx
0x18008d354  mov     rdi, rcx
0x18008d357  lea     rdx, aCsdsecuritydes; "CSdSecurityDescriptorInfo::Initialize"
0x18008d35e  mov     r9d, 1; unsigned __int16
0x18008d364  lea     rcx, [rbp+var_40]; this
0x18008d368  mov     r8d, 201h; unsigned __int16
0x18008d36e  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18008d373  xor     eax, eax
0x18008d375  mov     [rbp+dwRevision], 0
0x18008d37c  lea     r8, [rbp+dwRevision]; lpdwRevision
0x18008d380  mov     [rbp+pControl], ax
0x18008d384  lea     rdx, [rbp+pControl]; pControl
0x18008d388  mov     rcx, r14; pSecurityDescriptor
0x18008d38b  xor     ebx, ebx
0x18008d38d  call    cs:__imp_GetSecurityDescriptorControl
0x18008d394  nop     dword ptr [rax+rax+00h]
0x18008d399  test    eax, eax
0x18008d39b  jnz     short loc_18008D3B3
0x18008d39d  call    GetLastFailureAsHRESULT
0x18008d3a2  mov     [rbp+var_40], eax
0x18008d3a5  mov     eax, 208h
0x18008d3aa  mov     [rbp+var_3A], ax
0x18008d3ae  jmp     loc_18008D4AD
0x18008d3b3  mov     eax, 208h
0x18008d3b8  mov     [rbp+var_3C], ax
0x18008d3bc  mov     eax, 8000h
0x18008d3c1  test    [rbp+pControl], ax
0x18008d3c5  mov     eax, 20Ch
0x18008d3ca  jnz     short loc_18008D3D5
0x18008d3cc  mov     [rbp+var_40], 80070057h
0x18008d3d3  jmp     short loc_18008D3AA
0x18008d3d5  mov     rcx, r14; pSecurityDescriptor
0x18008d3d8  mov     [rbp+var_40], ebx
0x18008d3db  mov     [rbp+var_3C], ax
0x18008d3df  call    cs:__imp_GetSecurityDescriptorLength
0x18008d3e6  nop     dword ptr [rax+rax+00h]
0x18008d3eb  mov     ecx, eax; cb
0x18008d3ed  mov     esi, eax
0x18008d3ef  call    cs:__imp_CoTaskMemAlloc
0x18008d3f6  nop     dword ptr [rax+rax+00h]
0x18008d3fb  mov     rbx, rax
0x18008d3fe  test    rax, rax
0x18008d401  mov     eax, 210h
0x18008d406  jnz     short loc_18008D411
0x18008d408  mov     [rbp+var_40], 8007000Eh
0x18008d40f  jmp     short loc_18008D3AA
0x18008d411  mov     r8, rsi; Size
0x18008d414  mov     [rbp+var_40], 0
0x18008d41b  mov     rdx, r14; Src
0x18008d41e  mov     [rbp+var_3C], ax
0x18008d422  mov     rcx, rbx; void *
0x18008d425  call    memcpy_0
0x18008d42a  lea     r8, [rdi+8]; lpbOwnerDefaulted
0x18008d42e  mov     rdx, rdi; pOwner
0x18008d431  mov     rcx, rbx; pSecurityDescriptor
0x18008d434  call    cs:__imp_GetSecurityDescriptorOwner
0x18008d43b  nop     dword ptr [rax+rax+00h]
0x18008d440  test    eax, eax
0x18008d442  jnz     short loc_18008D456
0x18008d444  call    GetLastFailureAsHRESULT
0x18008d449  mov     [rbp+var_40], eax
0x18008d44c  mov     eax, 214h
0x18008d451  jmp     loc_18008D3AA
0x18008d456  mov     eax, 214h
0x18008d45b  mov     [rbp+var_40], 0
0x18008d462  lea     r9, [rdi+18h]; lpbDaclDefaulted
0x18008d466  mov     [rbp+var_3C], ax
0x18008d46a  lea     r8, [rdi+10h]; pDacl
0x18008d46e  mov     rcx, rbx; pSecurityDescriptor
0x18008d471  lea     rdx, [rdi+1Ch]; lpbDaclPresent
0x18008d475  call    cs:__imp_GetSecurityDescriptorDacl
0x18008d47c  nop     dword ptr [rax+rax+00h]
0x18008d481  test    eax, eax
0x18008d483  jnz     short loc_18008D497
0x18008d485  call    GetLastFailureAsHRESULT
0x18008d48a  mov     [rbp+var_40], eax
0x18008d48d  mov     eax, 216h
0x18008d492  jmp     loc_18008D3AA
0x18008d497  mov     eax, 216h
0x18008d49c  mov     [rdi+20h], rbx
0x18008d4a0  mov     [rbp+var_3C], ax
0x18008d4a4  xor     ebx, ebx
0x18008d4a6  mov     [rbp+var_40], 0
0x18008d4ad  mov     rcx, rbx; pv
0x18008d4b0  call    cs:__imp_CoTaskMemFree
0x18008d4b7  nop     dword ptr [rax+rax+00h]
0x18008d4bc  mov     ebx, [rbp+var_40]
0x18008d4bf  lea     rcx, [rbp+var_40]; this
0x18008d4c3  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18008d4c8  lea     r11, [rsp+60h+var_s0]
0x18008d4cd  mov     eax, ebx
0x18008d4cf  mov     rbx, [r11+20h]
0x18008d4d3  mov     rsi, [r11+28h]
0x18008d4d7  mov     rsp, r11
0x18008d4da  pop     r14
0x18008d4dc  pop     rdi
0x18008d4dd  pop     rbp
0x18008d4de  retn
```
