# CUserContext::BuildLocalKnownSid(ulong,void * *)

- ea: `0x1800bb7b0`
- end: `0x1800bb8f3`
- name: `?BuildLocalKnownSid@CUserContext@@QEBAJKPEAPEAX@Z`
- size: `323`
- prototype: `int(CUserContext *__hidden this, unsigned int, void **)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800bbe9c`

## callees

- `0x180060dc8`
- `0x180064820`
- `0x180068f60`
- `0x1800bb7b0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bb8b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bb8b3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800bb8cf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800bb8cf`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800bb8a9`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800bb8a9`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x1800bb831`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x1800bb831`
- `api-ms-win-security-base-l1-1-0!GetSidIdentifierAuthority` at `0x1800bb81a`
- `api-ms-win-security-base-l1-1-0!GetSidIdentifierAuthority` at `0x1800bb81a`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x1800bb854`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x1800bb854`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CUserContext::BuildLocalKnownSid(CUserContext *this, DWORD a2, void **a3)
{
  int DomainSid; // ebx
  __int64 v6; // rcx
  unsigned int v7; // esi
  __int64 v8; // rbx
  signed int LastError; // eax
  PSID pSid[2]; // [rsp+60h] [rbp-19h] BYREF
  _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+70h] [rbp-9h] BYREF
  DWORD nSubAuthority0[4]; // [rsp+78h] [rbp-1h]
  DWORD nSubAuthority4[4]; // [rsp+88h] [rbp+Fh]

  *(_DWORD *)pIdentifierAuthority.Value = 0;
  *(_WORD *)&pIdentifierAuthority.Value[4] = 0;
  *(_OWORD *)nSubAuthority0 = 0;
  *(_OWORD *)nSubAuthority4 = 0;
  pSid[0] = 0;
  pSid[1] = pSid;
  if ( !a3 )
    MicrosoftTelemetryAssertTriggeredNoArgs(this);
  DomainSid = CUserContext::GetDomainSid(this, pSid);
  if ( DomainSid >= 0 )
  {
    pIdentifierAuthority = *GetSidIdentifierAuthority(pSid[0]);
    v7 = *GetSidSubAuthorityCount(pSid[0]);
    v8 = 0;
    if ( (unsigned __int8)v7 < 8u )
    {
      if ( (_BYTE)v7 )
      {
        do
        {
          nSubAuthority0[v8] = *GetSidSubAuthority(pSid[0], v8);
          v8 = (unsigned int)(v8 + 1);
        }
        while ( (unsigned int)v8 < v7 );
      }
    }
    else
    {
      MicrosoftTelemetryAssertTriggeredNoArgs(v6);
    }
    nSubAuthority0[v8] = a2;
    if ( AllocateAndInitializeSid(
           &pIdentifierAuthority,
           v7 + 1,
           nSubAuthority0[0],
           nSubAuthority0[1],
           nSubAuthority0[2],
           nSubAuthority0[3],
           nSubAuthority4[0],
           nSubAuthority4[1],
           nSubAuthority4[2],
           nSubAuthority4[3],
           a3) )
    {
      DomainSid = 0;
    }
    else
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      DomainSid = LastError;
    }
  }
  LocalFree(pSid[0]);
  return (unsigned int)DomainSid;
}

```

## disassembly

```asm
0x1800bb7b0  push    rbp
0x1800bb7b2  push    rbx
0x1800bb7b3  push    rsi
0x1800bb7b4  push    rdi
0x1800bb7b5  push    r14
0x1800bb7b7  push    r15
0x1800bb7b9  lea     rbp, [rsp-2Fh]
0x1800bb7be  sub     rsp, 0A8h
0x1800bb7c5  mov     rax, cs:__security_cookie
0x1800bb7cc  xor     rax, rsp
0x1800bb7cf  mov     [rbp+57h+var_38], rax
0x1800bb7d3  mov     r14, r8
0x1800bb7d6  mov     r15d, edx
0x1800bb7d9  xor     eax, eax
0x1800bb7db  mov     dword ptr [rbp+57h+pIdentifierAuthority.Value], eax
0x1800bb7de  mov     word ptr [rbp+57h+pIdentifierAuthority.Value+4], ax
0x1800bb7e2  xorps   xmm0, xmm0
0x1800bb7e5  movups  xmmword ptr [rbp+57h+nSubAuthority0], xmm0
0x1800bb7e9  movups  xmmword ptr [rbp+57h+var_48], xmm0
0x1800bb7ed  mov     [rbp+57h+pSid], rax
0x1800bb7f1  lea     rax, [rbp+57h+pSid]
0x1800bb7f5  mov     [rbp+57h+var_68], rax
0x1800bb7f9  test    r8, r8
0x1800bb7fc  jnz     short loc_1800BB803
0x1800bb7fe  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800bb803  lea     rdx, [rbp+57h+pSid]; void **
0x1800bb807  call    ?GetDomainSid@CUserContext@@QEBAJPEAPEAX@Z; CUserContext::GetDomainSid(void * *)
0x1800bb80c  mov     ebx, eax
0x1800bb80e  test    eax, eax
0x1800bb810  js      loc_1800BB8CB
0x1800bb816  mov     rcx, [rbp+57h+pSid]; pSid
0x1800bb81a  call    cs:__imp_GetSidIdentifierAuthority
0x1800bb820  mov     ecx, [rax]
0x1800bb822  mov     dword ptr [rbp+57h+pIdentifierAuthority.Value], ecx
0x1800bb825  movzx   eax, word ptr [rax+4]
0x1800bb829  mov     word ptr [rbp+57h+pIdentifierAuthority.Value+4], ax
0x1800bb82d  mov     rcx, [rbp+57h+pSid]; pSid
0x1800bb831  call    cs:__imp_GetSidSubAuthorityCount
0x1800bb837  movzx   esi, byte ptr [rax]
0x1800bb83a  xor     ebx, ebx
0x1800bb83c  cmp     sil, 8
0x1800bb840  jb      short loc_1800BB849
0x1800bb842  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800bb847  jmp     short loc_1800BB866
0x1800bb849  test    sil, sil
0x1800bb84c  jz      short loc_1800BB866
0x1800bb84e  mov     edx, ebx; nSubAuthority
0x1800bb850  mov     rcx, [rbp+57h+pSid]; pSid
0x1800bb854  call    cs:__imp_GetSidSubAuthority
0x1800bb85a  mov     eax, [rax]
0x1800bb85c  mov     [rbp+rbx*4+57h+nSubAuthority0], eax
0x1800bb860  inc     ebx
0x1800bb862  cmp     ebx, esi
0x1800bb864  jb      short loc_1800BB84E
0x1800bb866  mov     [rbp+rbx*4+57h+nSubAuthority0], r15d
0x1800bb86b  lea     edx, [rsi+1]; nSubAuthorityCount
0x1800bb86e  mov     [rsp+0D0h+var_80], r14; pSid
0x1800bb873  mov     eax, [rbp+57h+var_48+0Ch]
0x1800bb876  mov     [rsp+0D0h+nSubAuthority7], eax; nSubAuthority7
0x1800bb87a  mov     eax, [rbp+57h+var_48+8]
0x1800bb87d  mov     [rsp+0D0h+nSubAuthority6], eax; nSubAuthority6
0x1800bb881  mov     eax, [rbp+57h+var_48+4]
0x1800bb884  mov     [rsp+0D0h+nSubAuthority5], eax; nSubAuthority5
0x1800bb888  mov     eax, [rbp+57h+var_48]
0x1800bb88b  mov     [rsp+0D0h+nSubAuthority4], eax; nSubAuthority4
0x1800bb88f  mov     eax, [rbp+57h+nSubAuthority0+0Ch]
0x1800bb892  mov     [rsp+0D0h+nSubAuthority3], eax; nSubAuthority3
0x1800bb896  mov     eax, [rbp+57h+nSubAuthority0+8]
0x1800bb899  mov     [rsp+0D0h+nSubAuthority2], eax; nSubAuthority2
0x1800bb89d  mov     r9d, [rbp+57h+nSubAuthority0+4]; nSubAuthority1
0x1800bb8a1  mov     r8d, [rbp+57h+nSubAuthority0]; nSubAuthority0
0x1800bb8a5  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x1800bb8a9  call    cs:__imp_AllocateAndInitializeSid
0x1800bb8af  test    eax, eax
0x1800bb8b1  jnz     short loc_1800BB8C9
0x1800bb8b3  call    cs:__imp_GetLastError
0x1800bb8b9  test    eax, eax
0x1800bb8bb  jle     short loc_1800BB8C5
0x1800bb8bd  movzx   eax, ax
0x1800bb8c0  or      eax, 80070000h
0x1800bb8c5  mov     ebx, eax
0x1800bb8c7  jmp     short loc_1800BB8CB
0x1800bb8c9  xor     ebx, ebx
0x1800bb8cb  mov     rcx, [rbp+57h+pSid]; hMem
0x1800bb8cf  call    cs:__imp_LocalFree
0x1800bb8d5  mov     eax, ebx
0x1800bb8d7  mov     rcx, [rbp+57h+var_38]
0x1800bb8db  xor     rcx, rsp; StackCookie
0x1800bb8de  call    __security_check_cookie
0x1800bb8e3  add     rsp, 0A8h
0x1800bb8ea  pop     r15
0x1800bb8ec  pop     r14
0x1800bb8ee  pop     rdi
0x1800bb8ef  pop     rsi
0x1800bb8f0  pop     rbx
0x1800bb8f1  pop     rbp
0x1800bb8f2  retn
```
