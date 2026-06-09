# PfApUserChanged

- ea: `0x180039a44`
- end: `0x180039c88`
- name: `PfApUserChanged`
- size: `580`
- prototype: ``
- caller_count: `3`
- callee_count: `15`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180051ec4`
- `0x180052260`
- `0x1800a8bfc`

## callees

- `0x180038a10`
- `0x180039490`
- `0x18003952c`
- `0x180039598`
- `0x180039a44`
- `0x18003babc`
- `0x18003cbe4`
- `0x18003cffc`
- `0x18003eaa0`
- `0x18003eb44`
- `0x18005b9a8`
- `0x18005d53c`
- `0x180065a50`
- `0x18006d124`
- `0x1800739c0`

## import_xrefs

- `ntdll!RtlAcquireSRWLockExclusive` at `0x180039ace`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180039ace`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180039c4d`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180039c4d`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180039b0f`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180039b0f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180039c68`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180039c68`

## pseudocode

```c
__int64 __fastcall PfApUserChanged(__int64 a1, void *a2, __int64 a3, int a4)
{
  _QWORD *v4; // r12
  __int64 v6; // r14
  int v7; // ebx
  __int64 v8; // r13
  int v10; // r15d
  unsigned int v11; // edi
  PSID v12; // r14
  DWORD LengthSid; // eax
  __int64 v14; // rdx
  __int64 v15; // rcx
  __int64 v16; // r8
  __int64 v17; // rbx
  __int64 v18; // rcx
  struct _RTL_CRITICAL_SECTION *v19; // r10
  __int64 v21; // [rsp+20h] [rbp-20h]
  PSID pSid[2]; // [rsp+28h] [rbp-18h] BYREF
  __int64 v23; // [rsp+80h] [rbp+40h] BYREF
  int v24; // [rsp+98h] [rbp+58h]

  v24 = a4;
  v4 = (_QWORD *)(a1 + 168);
  *(_OWORD *)pSid = 0;
  LODWORD(pSid[1]) = -1;
  v6 = *(_QWORD *)(*(_QWORD *)&PfSvcGlobals + 4072LL);
  v7 = a3;
  v8 = *(_QWORD *)(*(_QWORD *)&PfSvcGlobals + 4064LL);
  v21 = v6;
  v10 = 0;
  if ( (unsigned int)PfApUserInfoEqual(a1 + 168, a2, a3) )
  {
LABEL_14:
    v11 = 0;
    goto LABEL_15;
  }
  v11 = PfApUserInfoStart((__int64)pSid, a2, v7);
  if ( v11 )
  {
LABEL_15:
    v12 = pSid[0];
    goto LABEL_16;
  }
  v10 = 1;
  RtlAcquireSRWLockExclusive(a1 + 160);
  if ( *v4 )
  {
    PfApUserTimeGet(a1 + 184);
    PfApUserContextReset(a1, v8, v6, v24);
  }
  v12 = pSid[0];
  if ( !pSid[0] )
  {
    v11 = 0;
    goto LABEL_16;
  }
  LengthSid = GetLengthSid(pSid[0]);
  LODWORD(v23) = PfsGetSidHash(v12, LengthSid);
  v11 = PfApUserTimeCtxStart(a1 + 184, (unsigned int)v23);
  if ( !v11 )
  {
    v14 = LODWORD(pSid[1]);
    v15 = *(_QWORD *)&PfSvcGlobals;
    v16 = 3 - (unsigned int)(LODWORD(pSid[1]) != 0);
    *(_QWORD *)(*(_QWORD *)&PfSvcGlobals + 4080LL) = a1 + 184;
    v11 = PfSvPowerNotifyRegister(v15, v14, v16);
    if ( !v11 )
    {
      *(_WORD *)(a1 + 216) |= 4u;
      v17 = PfApUserTimeGet(a1 + 184);
      v11 = PfPreContextStart(a1 + 16, (unsigned int)v23, v17);
      if ( !v11 )
      {
        v11 = PfApComponentsRestart(a1, pSid, v8, v21);
        if ( !v11 )
        {
          PfApUserInfoCopy(v4, pSid, 1);
          if ( (v24 & 1) != 0 )
            PfPreAddEvent(a1 + 16, 0, 10, v17);
          PfPreAddEvent(a1 + 16, 0, 8, v17);
          PfApUserActivitySync(a1, 1);
          v23 = PfsActionItemGetCurrentTime(v18) + 36000000000LL;
          PfsActionItemQueueEx(v19 + 43, 0x2Du, (unsigned __int64 *)&v23, 0);
          goto LABEL_14;
        }
        goto LABEL_15;
      }
    }
  }
LABEL_16:
  if ( !*v4 )
    PfApUserContextReset(a1, v8, v21, 0);
  if ( v10 )
    RtlReleaseSRWLockExclusive(a1 + 160);
  if ( v12 )
    HeapFree(*(HANDLE *)(*(_QWORD *)&PfSvcGlobals + 88LL), 0, v12);
  return v11;
}

```

## disassembly

```asm
0x180039a44  mov     [rsp-38h+arg_8], rbx
0x180039a49  mov     [rsp-38h+arg_18], r9d
0x180039a4e  push    rbp
0x180039a4f  push    rsi
0x180039a50  push    rdi
0x180039a51  push    r12
0x180039a53  push    r13
0x180039a55  push    r14
0x180039a57  push    r15
0x180039a59  mov     rbp, rsp
0x180039a5c  sub     rsp, 40h
0x180039a60  mov     rax, cs:PfSvcGlobals
0x180039a67  lea     r12, [rcx+0A8h]
0x180039a6e  xorps   xmm0, xmm0
0x180039a71  mov     rsi, rcx
0x180039a74  movups  xmmword ptr [rbp+pSid], xmm0
0x180039a78  mov     rcx, r12
0x180039a7b  mov     dword ptr [rbp+pSid+8], 0FFFFFFFFh
0x180039a82  mov     r14, [rax+0FE8h]
0x180039a89  mov     ebx, r8d
0x180039a8c  mov     r13, [rax+0FE0h]
0x180039a93  mov     rdi, rdx
0x180039a96  mov     [rbp+var_20], r14
0x180039a9a  xor     r15d, r15d
0x180039a9d  call    PfApUserInfoEqual
0x180039aa2  test    eax, eax
0x180039aa4  jnz     loc_180039C22
0x180039aaa  mov     r8d, ebx
0x180039aad  lea     rcx, [rbp+pSid]
0x180039ab1  mov     rdx, rdi
0x180039ab4  call    PfApUserInfoStart
0x180039ab9  mov     edi, eax
0x180039abb  test    eax, eax
0x180039abd  jnz     loc_180039C24
0x180039ac3  lea     rcx, [rsi+0A0h]
0x180039aca  lea     r15d, [rax+1]
0x180039ace  call    cs:__imp_RtlAcquireSRWLockExclusive
0x180039ad4  cmp     qword ptr [r12], 0
0x180039ad9  lea     rbx, [rsi+0B8h]
0x180039ae0  jz      short loc_180039AFC
0x180039ae2  mov     rcx, rbx
0x180039ae5  call    PfApUserTimeGet
0x180039aea  mov     r9d, [rbp+arg_18]
0x180039aee  mov     r8, r14
0x180039af1  mov     rdx, r13
0x180039af4  mov     rcx, rsi
0x180039af7  call    PfApUserContextReset
0x180039afc  mov     r14, [rbp+pSid]
0x180039b00  test    r14, r14
0x180039b03  jnz     short loc_180039B0C
0x180039b05  xor     edi, edi
0x180039b07  jmp     loc_180039C28
0x180039b0c  mov     rcx, r14; pSid
0x180039b0f  call    cs:__imp_GetLengthSid
0x180039b15  mov     edx, eax
0x180039b17  mov     rcx, r14
0x180039b1a  call    PfsGetSidHash
0x180039b1f  mov     edx, eax
0x180039b21  mov     dword ptr [rbp+arg_0], eax
0x180039b24  mov     rcx, rbx
0x180039b27  call    PfApUserTimeCtxStart
0x180039b2c  mov     edi, eax
0x180039b2e  test    eax, eax
0x180039b30  jnz     loc_180039C28
0x180039b36  mov     edx, dword ptr [rbp+pSid+8]
0x180039b39  mov     r8d, edx
0x180039b3c  mov     rcx, cs:PfSvcGlobals
0x180039b43  neg     r8d
0x180039b46  sbb     r8d, r8d
0x180039b49  add     r8d, 3
0x180039b4d  mov     [rcx+0FF0h], rbx
0x180039b54  call    PfSvPowerNotifyRegister
0x180039b59  mov     edi, eax
0x180039b5b  test    eax, eax
0x180039b5d  jnz     loc_180039C28
0x180039b63  or      word ptr [rsi+0D8h], 4
0x180039b6b  mov     rcx, rbx
0x180039b6e  call    PfApUserTimeGet
0x180039b73  mov     edx, dword ptr [rbp+arg_0]
0x180039b76  lea     rcx, [rsi+10h]
0x180039b7a  mov     r8, rax
0x180039b7d  mov     rbx, rax
0x180039b80  call    PfPreContextStart
0x180039b85  mov     edi, eax
0x180039b87  test    eax, eax
0x180039b89  jnz     loc_180039C28
0x180039b8f  mov     r9, [rbp+var_20]
0x180039b93  lea     rdx, [rbp+pSid]
0x180039b97  mov     r8, r13
0x180039b9a  mov     rcx, rsi
0x180039b9d  call    PfApComponentsRestart
0x180039ba2  mov     edi, eax
0x180039ba4  test    eax, eax
0x180039ba6  jnz     short loc_180039C24
0x180039ba8  mov     r8d, r15d
0x180039bab  lea     rdx, [rbp+pSid]
0x180039baf  mov     rcx, r12
0x180039bb2  call    PfApUserInfoCopy
0x180039bb7  lea     rdi, [rsi+10h]
0x180039bbb  test    byte ptr [rbp+arg_18], r15b
0x180039bbf  jz      short loc_180039BD2
0x180039bc1  xor     edx, edx
0x180039bc3  mov     r9, rbx
0x180039bc6  mov     rcx, rdi
0x180039bc9  lea     r8d, [rdx+0Ah]
0x180039bcd  call    PfPreAddEvent
0x180039bd2  xor     edx, edx
0x180039bd4  mov     r9, rbx
0x180039bd7  mov     rcx, rdi
0x180039bda  lea     r8d, [rdx+8]
0x180039bde  call    PfPreAddEvent
0x180039be3  mov     edx, r15d
0x180039be6  mov     rcx, rsi
0x180039be9  call    PfApUserActivitySync
0x180039bee  mov     r10, cs:PfSvcGlobals
0x180039bf5  call    PfsActionItemGetCurrentTime
0x180039bfa  xor     r9d, r9d
0x180039bfd  lea     r8, [rbp+arg_0]
0x180039c01  mov     rcx, 861C46800h
0x180039c0b  add     rax, rcx
0x180039c0e  lea     rcx, [r10+6B8h]; lpCriticalSection
0x180039c15  mov     [rbp+arg_0], rax
0x180039c19  lea     edx, [r9+2Dh]
0x180039c1d  call    PfsActionItemQueueEx
0x180039c22  xor     edi, edi
0x180039c24  mov     r14, [rbp+pSid]
0x180039c28  cmp     qword ptr [r12], 0
0x180039c2d  jnz     short loc_180039C41
0x180039c2f  mov     r8, [rbp+var_20]
0x180039c33  xor     r9d, r9d
0x180039c36  mov     rdx, r13
0x180039c39  mov     rcx, rsi
0x180039c3c  call    PfApUserContextReset
0x180039c41  test    r15d, r15d
0x180039c44  jz      short loc_180039C53
0x180039c46  lea     rcx, [rsi+0A0h]
0x180039c4d  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180039c53  test    r14, r14
0x180039c56  jz      short loc_180039C6E
0x180039c58  mov     rcx, cs:PfSvcGlobals
0x180039c5f  mov     r8, r14; lpMem
0x180039c62  xor     edx, edx; dwFlags
0x180039c64  mov     rcx, [rcx+58h]; hHeap
0x180039c68  call    cs:__imp_HeapFree
0x180039c6e  mov     rbx, [rsp+40h+arg_8]
0x180039c76  mov     eax, edi
0x180039c78  add     rsp, 40h
0x180039c7c  pop     r15
0x180039c7e  pop     r14
0x180039c80  pop     r13
0x180039c82  pop     r12
0x180039c84  pop     rdi
0x180039c85  pop     rsi
0x180039c86  pop     rbp
0x180039c87  retn
```
