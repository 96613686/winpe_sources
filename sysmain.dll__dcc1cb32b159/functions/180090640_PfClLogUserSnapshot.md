# PfClLogUserSnapshot

- ea: `0x180090640`
- end: `0x180090886`
- name: `PfClLogUserSnapshot`
- size: `582`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180080bec`

## callees

- `0x180052364`
- `0x180079644`
- `0x180090640`
- `0x1800b645a`
- `0x1800b7010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800906a7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800906a7`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18009074d`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18009074d`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180090799`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180090799`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800907b7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180090852`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18009086d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800907b7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180090852`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18009086d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800906df`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800906df`
- `api-ms-win-core-kernel32-legacy-l1-1-0!WTSGetActiveConsoleSessionId` at `0x1800906b2`
- `api-ms-win-core-kernel32-legacy-l1-1-0!WTSGetActiveConsoleSessionId` at `0x1800906b2`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSEnumerateSessionsW` at `0x18009069d`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSEnumerateSessionsW` at `0x18009069d`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSFreeMemory` at `0x180090837`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSFreeMemory` at `0x180090837`

## pseudocode

```c
__int64 __fastcall PfClLogUserSnapshot(__int64 *a1)
{
  __int64 *v1; // r12
  _DWORD *v2; // rbx
  unsigned int v3; // esi
  DWORD LastError; // eax
  SIZE_T v5; // rsi
  _DWORD *v6; // rax
  DWORD *v7; // rsi
  int v8; // r15d
  DWORD v9; // r14d
  PWTS_SESSION_INFOW v10; // r13
  int SessionUserInfo; // eax
  PSID *v12; // rdi
  DWORD LengthSid; // r9d
  DWORD v14; // eax
  BOOL v15; // ecx
  __int64 v16; // rax
  int v17; // eax
  __int64 v18; // rcx
  LPVOID lpMem[3]; // [rsp+30h] [rbp-18h] BYREF
  DWORD pCount; // [rsp+98h] [rbp+50h] BYREF
  DWORD active; // [rsp+A0h] [rbp+58h]
  PWTS_SESSION_INFOW ppSessionInfo; // [rsp+A8h] [rbp+60h] BYREF

  v1 = a1;
  pCount = 0;
  v2 = 0;
  lpMem[0] = 0;
  ppSessionInfo = 0;
  if ( (unsigned __int8)IsWTSFreeMemoryPresent() )
  {
    if ( WTSEnumerateSessionsW(0, 0, 1u, &ppSessionInfo, &pCount) )
    {
      active = WTSGetActiveConsoleSessionId();
      v5 = (80 * pCount + 43) & 0xFFFFFFF0;
      v6 = HeapAlloc(*(HANDLE *)(*(_QWORD *)&PfSvcGlobals + 88LL), 0, v5);
      v2 = v6;
      if ( !v6 )
      {
        v3 = 8;
        goto LABEL_19;
      }
      memset_0(v6, 0, v5);
      v2[4] = 1;
      v7 = v2 + 7;
      v2[6] = 0;
      v8 = 12;
      v9 = 0;
      if ( pCount )
      {
        do
        {
          v10 = ppSessionInfo;
          SessionUserInfo = PfSvGetSessionUserInfo(ppSessionInfo[v9].SessionId, lpMem);
          v12 = (PSID *)lpMem[0];
          if ( SessionUserInfo )
            LengthSid = 12;
          else
            LengthSid = GetLengthSid(*(PSID *)lpMem[0]);
          v14 = active;
          *v7 = (LengthSid + 15) & 0xFFFFFFFC;
          v7[1] = v10[v9].SessionId;
          v15 = v14 == v10[v9].SessionId;
          v7[2] &= ~1u;
          v7[2] |= v15;
          v7[2] = v15 | (2 * v10[v9].State);
          if ( v12 )
            CopySid(LengthSid, v7 + 3, *v12);
          ++v2[6];
          if ( v12 )
          {
            HeapFree(*(HANDLE *)(*(_QWORD *)&PfSvcGlobals + 88LL), 0, v12);
            lpMem[0] = 0;
          }
          v16 = *v7;
          ++v9;
          v8 += v16;
          v7 = (DWORD *)((char *)v7 + v16);
        }
        while ( v9 < pCount );
        v1 = a1;
      }
      v2[5] = v8;
      *((_QWORD *)v2 + 1) = 0;
      *(_QWORD *)v2 = (((_WORD)v8 + 31) & 0x3FF0 | 0x5800CuLL) >> 2;
      v17 = ((__int64 (*)(void))v1[2])();
      *(_QWORD *)v2 |= 0x20000uLL;
      v18 = *v1;
      v2[2] = v17;
      LastError = ((__int64 (__fastcall *)(__int64, _DWORD *))v1[1])(v18, v2);
    }
    else
    {
      LastError = GetLastError();
    }
    v3 = LastError;
    goto LABEL_19;
  }
  v3 = 259;
LABEL_19:
  if ( ppSessionInfo && (unsigned __int8)IsWTSFreeMemoryPresent() )
    WTSFreeMemory(ppSessionInfo);
  if ( v2 )
    HeapFree(*(HANDLE *)(*(_QWORD *)&PfSvcGlobals + 88LL), 0, v2);
  return v3;
}

```

## disassembly

```asm
0x180090640  mov     [rsp-40h+arg_0], rcx
0x180090645  push    rbp
0x180090646  push    rbx
0x180090647  push    rsi
0x180090648  push    rdi
0x180090649  push    r12
0x18009064b  push    r13
0x18009064d  push    r14
0x18009064f  push    r15
0x180090651  mov     rbp, rsp
0x180090654  sub     rsp, 48h
0x180090658  xor     r13d, r13d
0x18009065b  mov     r12, rcx
0x18009065e  mov     [rbp+arg_8], r13d
0x180090662  mov     ebx, r13d
0x180090665  mov     edi, r13d
0x180090668  mov     [rbp+lpMem], r13
0x18009066c  mov     [rbp+ppSessionInfo], r13
0x180090670  call    IsWTSFreeMemoryPresent
0x180090675  test    al, al
0x180090677  jnz     short loc_180090683
0x180090679  mov     esi, 103h
0x18009067e  jmp     loc_180090824
0x180090683  lea     rax, [rbp+arg_8]
0x180090687  mov     r14d, 1
0x18009068d  mov     r8d, r14d; Version
0x180090690  mov     [rsp+48h+pCount], rax; pCount
0x180090695  lea     r9, [rbp+ppSessionInfo]; ppSessionInfo
0x180090699  xor     edx, edx; Reserved
0x18009069b  xor     ecx, ecx; hServer
0x18009069d  call    cs:__imp_WTSEnumerateSessionsW
0x1800906a3  test    eax, eax
0x1800906a5  jnz     short loc_1800906B2
0x1800906a7  call    cs:__imp_GetLastError
0x1800906ad  jmp     loc_180090822
0x1800906b2  call    cs:__imp_WTSGetActiveConsoleSessionId
0x1800906b8  mov     ecx, [rbp+arg_8]
0x1800906bb  xor     edx, edx; dwFlags
0x1800906bd  mov     [rbp+arg_10], eax
0x1800906c0  mov     eax, 0FFFFFFF0h
0x1800906c5  lea     esi, [rcx+rcx*4]
0x1800906c8  mov     rcx, cs:PfSvcGlobals
0x1800906cf  shl     esi, 4
0x1800906d2  add     esi, 2Bh ; '+'
0x1800906d5  and     rsi, rax
0x1800906d8  mov     rcx, [rcx+58h]; hHeap
0x1800906dc  mov     r8, rsi; dwBytes
0x1800906df  call    cs:__imp_HeapAlloc
0x1800906e5  mov     rbx, rax
0x1800906e8  test    rax, rax
0x1800906eb  jnz     short loc_1800906F5
0x1800906ed  lea     esi, [rax+8]
0x1800906f0  jmp     loc_180090824
0x1800906f5  mov     r8, rsi; Size
0x1800906f8  xor     edx, edx; Val
0x1800906fa  mov     rcx, rbx; void *
0x1800906fd  call    memset_0
0x180090702  mov     [rbx+10h], r14d
0x180090706  lea     rsi, [rbx+1Ch]
0x18009070a  mov     [rbx+18h], r13d
0x18009070e  mov     r15d, 0Ch
0x180090714  mov     r14d, r13d
0x180090717  cmp     [rbp+arg_8], r13d
0x18009071b  jbe     loc_1800907DD
0x180090721  mov     r13, [rbp+ppSessionInfo]
0x180090725  lea     rdx, [rbp+lpMem]
0x180090729  mov     eax, r14d
0x18009072c  lea     r12, [rax+rax*2]
0x180090730  mov     ecx, [r13+r12*8+0]
0x180090735  call    PfSvGetSessionUserInfo
0x18009073a  mov     rdi, [rbp+lpMem]
0x18009073e  test    eax, eax
0x180090740  jz      short loc_18009074A
0x180090742  mov     r9d, 0Ch
0x180090748  jmp     short loc_180090756
0x18009074a  mov     rcx, [rdi]; pSid
0x18009074d  call    cs:__imp_GetLengthSid
0x180090753  mov     r9d, eax
0x180090756  mov     eax, [rbp+arg_10]
0x180090759  lea     ecx, [r9+0Fh]
0x18009075d  and     ecx, 0FFFFFFFCh
0x180090760  mov     [rsi], ecx
0x180090762  mov     ecx, [r13+r12*8+0]
0x180090767  mov     [rsi+4], ecx
0x18009076a  xor     ecx, ecx
0x18009076c  cmp     eax, [r13+r12*8+0]
0x180090771  setz    cl
0x180090774  and     dword ptr [rsi+8], 0FFFFFFFEh
0x180090778  or      [rsi+8], ecx
0x18009077b  mov     eax, [r13+r12*8+10h]
0x180090780  xor     r13d, r13d
0x180090783  add     eax, eax
0x180090785  or      eax, ecx
0x180090787  mov     [rsi+8], eax
0x18009078a  test    rdi, rdi
0x18009078d  jz      short loc_18009079F
0x18009078f  mov     r8, [rdi]; pSourceSid
0x180090792  lea     rdx, [rsi+0Ch]; pDestinationSid
0x180090796  mov     ecx, r9d; nDestinationSidLength
0x180090799  call    cs:__imp_CopySid
0x18009079f  inc     dword ptr [rbx+18h]
0x1800907a2  test    rdi, rdi
0x1800907a5  jz      short loc_1800907C4
0x1800907a7  mov     rcx, cs:PfSvcGlobals
0x1800907ae  mov     r8, rdi; lpMem
0x1800907b1  xor     edx, edx; dwFlags
0x1800907b3  mov     rcx, [rcx+58h]; hHeap
0x1800907b7  call    cs:__imp_HeapFree
0x1800907bd  mov     rdi, r13
0x1800907c0  mov     [rbp+lpMem], r13
0x1800907c4  mov     eax, [rsi]
0x1800907c6  inc     r14d
0x1800907c9  add     r15d, eax
0x1800907cc  add     rsi, rax
0x1800907cf  cmp     r14d, [rbp+arg_8]
0x1800907d3  jb      loc_180090721
0x1800907d9  mov     r12, [rbp+arg_0]
0x1800907dd  mov     [rbx+14h], r15d
0x1800907e1  lea     eax, [r15+10h]
0x1800907e5  add     rax, 0Fh
0x1800907e9  mov     [rbx+8], r13
0x1800907ed  and     eax, 3FF0h
0x1800907f2  or      rax, 5800Ch
0x1800907f8  shr     rax, 2
0x1800907fc  mov     [rbx], rax
0x1800907ff  mov     rax, [r12+10h]
0x180090804  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180090809  bts     qword ptr [rbx], 11h
0x18009080e  mov     rdx, rbx
0x180090811  mov     rcx, [r12]
0x180090815  mov     [rbx+8], eax
0x180090818  mov     rax, [r12+8]
0x18009081d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180090822  mov     esi, eax
0x180090824  cmp     [rbp+ppSessionInfo], r13
0x180090828  jz      short loc_18009083D
0x18009082a  call    IsWTSFreeMemoryPresent
0x18009082f  test    al, al
0x180090831  jz      short loc_18009083D
0x180090833  mov     rcx, [rbp+ppSessionInfo]; pMemory
0x180090837  call    cs:__imp_WTSFreeMemory
0x18009083d  test    rbx, rbx
0x180090840  jz      short loc_180090858
0x180090842  mov     rcx, cs:PfSvcGlobals
0x180090849  mov     r8, rbx; lpMem
0x18009084c  xor     edx, edx; dwFlags
0x18009084e  mov     rcx, [rcx+58h]; hHeap
0x180090852  call    cs:__imp_HeapFree
0x180090858  test    rdi, rdi
0x18009085b  jz      short loc_180090873
0x18009085d  mov     rcx, cs:PfSvcGlobals
0x180090864  mov     r8, rdi; lpMem
0x180090867  xor     edx, edx; dwFlags
0x180090869  mov     rcx, [rcx+58h]; hHeap
0x18009086d  call    cs:__imp_HeapFree
0x180090873  mov     eax, esi
0x180090875  add     rsp, 48h
0x180090879  pop     r15
0x18009087b  pop     r14
0x18009087d  pop     r13
0x18009087f  pop     r12
0x180090881  pop     rdi
0x180090882  pop     rsi
0x180090883  pop     rbx
0x180090884  pop     rbp
0x180090885  retn
```
