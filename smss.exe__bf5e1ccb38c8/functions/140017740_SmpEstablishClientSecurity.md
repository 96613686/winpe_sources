# SmpEstablishClientSecurity

- ea: `0x140017740`
- end: `0x1400178a4`
- name: `SmpEstablishClientSecurity`
- size: `356`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x140001880`

## callees

- `0x140017740`
- `0x14001cc40`

## import_xrefs

- `ntdll!NtClose` at `0x140017833`
- `ntdll!NtClose` at `0x140017833`
- `ntdll!RtlReleaseSRWLockShared` at `0x1400177ad`
- `ntdll!RtlReleaseSRWLockShared` at `0x1400177ad`
- `ntdll!RtlAcquireSRWLockShared` at `0x1400177a3`
- `ntdll!RtlAcquireSRWLockShared` at `0x1400177a3`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x14001785c`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x14001785c`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x140017878`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x140017878`
- `ntdll!NtAlpcImpersonateClientOfPort` at `0x1400177bd`
- `ntdll!NtAlpcImpersonateClientOfPort` at `0x1400177bd`
- `ntdll!NtOpenThreadToken` at `0x1400177df`
- `ntdll!NtOpenThreadToken` at `0x1400177df`
- `ntdll!NtQueryInformationToken` at `0x140017804`
- `ntdll!NtQueryInformationToken` at `0x140017804`
- `ntdll!NtSetInformationThread` at `0x140017852`
- `ntdll!NtSetInformationThread` at `0x140017852`

## pseudocode

```c
__int64 __fastcall SmpEstablishClientSecurity(__int64 a1, __int64 a2)
{
  int v4; // edi
  NTSTATUS v5; // ebx
  ULONG ReturnLength; // [rsp+30h] [rbp-19h] BYREF
  void *TokenHandle; // [rsp+38h] [rbp-11h] BYREF
  __int64 ThreadInformation; // [rsp+40h] [rbp-9h] BYREF
  __int128 TokenInformation; // [rsp+48h] [rbp-1h] BYREF
  __int128 v11; // [rsp+58h] [rbp+Fh]
  __int128 v12; // [rsp+68h] [rbp+1Fh]
  __int64 v13; // [rsp+78h] [rbp+2Fh]

  ThreadInformation = 0;
  TokenHandle = 0;
  TokenInformation = 0;
  v4 = 2;
  v13 = 0;
  v11 = 0;
  ReturnLength = 0;
  v12 = 0;
  if ( !*(_QWORD *)(a2 + 16) )
  {
    RtlAcquireSRWLockShared(a2 + 24);
    RtlReleaseSRWLockShared(a2 + 24);
  }
  v5 = NtAlpcImpersonateClientOfPort(*(_QWORD *)(a2 + 16), a1, 0);
  if ( v5 >= 0 )
  {
    v5 = NtOpenThreadToken((HANDLE)0xFFFFFFFFFFFFFFFELL, 0xCu, 0, &TokenHandle);
    if ( v5 >= 0 )
    {
      v5 = NtQueryInformationToken(TokenHandle, TokenStatistics, &TokenInformation, 0x38u, &ReturnLength);
      if ( v5 >= 0 && (DWORD2(v11) != 2 || SHIDWORD(v11) >= 2) && *((_QWORD *)&TokenInformation + 1) == 999 )
        v4 = 4;
      NtClose(TokenHandle);
    }
    ThreadInformation = 0;
    NtSetInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadImpersonationToken, &ThreadInformation, 8u);
  }
  RtlAcquireSRWLockExclusive(a2 + 24);
  if ( (*(_DWORD *)a2 & 6) != 0 )
  {
    v5 = 0;
  }
  else if ( v5 >= 0 )
  {
    *(_DWORD *)a2 |= v4;
  }
  RtlReleaseSRWLockExclusive(a2 + 24);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x140017740  mov     [rsp-8+arg_10], rbx
0x140017745  mov     [rsp-8+arg_18], rsi
0x14001774a  push    rbp
0x14001774b  push    rdi
0x14001774c  push    r14
0x14001774e  lea     rbp, [rsp-47h]
0x140017753  sub     rsp, 90h
0x14001775a  mov     rax, cs:__security_cookie
0x140017761  xor     rax, rsp
0x140017764  mov     [rbp+57h+var_20], rax
0x140017768  xor     eax, eax
0x14001776a  mov     [rbp+57h+ThreadInformation], 0
0x140017772  xorps   xmm0, xmm0
0x140017775  mov     rsi, rdx
0x140017778  mov     r14, rcx
0x14001777b  mov     [rbp+57h+TokenHandle], 0
0x140017783  movups  [rbp+57h+TokenInformation], xmm0
0x140017787  lea     edi, [rax+2]
0x14001778a  mov     [rbp+57h+var_28], rax
0x14001778e  movups  [rbp+57h+var_48], xmm0
0x140017792  mov     [rbp+57h+var_70], eax
0x140017795  movups  [rbp+57h+var_38], xmm0
0x140017799  cmp     [rdx+10h], rax
0x14001779d  jnz     short loc_1400177B3
0x14001779f  lea     rcx, [rdx+18h]
0x1400177a3  call    cs:__imp_RtlAcquireSRWLockShared
0x1400177a9  lea     rcx, [rsi+18h]
0x1400177ad  call    cs:__imp_RtlReleaseSRWLockShared
0x1400177b3  mov     rcx, [rsi+10h]
0x1400177b7  xor     r8d, r8d
0x1400177ba  mov     rdx, r14
0x1400177bd  call    cs:__imp_NtAlpcImpersonateClientOfPort
0x1400177c3  mov     ebx, eax
0x1400177c5  test    eax, eax
0x1400177c7  js      loc_140017858
0x1400177cd  xor     r8d, r8d; OpenAsSelf
0x1400177d0  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x1400177d4  lea     r14, [r8-2]
0x1400177d8  mov     rcx, r14; ThreadHandle
0x1400177db  lea     edx, [r8+0Ch]; DesiredAccess
0x1400177df  call    cs:__imp_NtOpenThreadToken
0x1400177e5  mov     ebx, eax
0x1400177e7  test    eax, eax
0x1400177e9  js      short loc_140017839
0x1400177eb  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x1400177ef  lea     rax, [rbp+57h+var_70]
0x1400177f3  lea     r9d, [r14+3Ah]; TokenInformationLength
0x1400177f7  mov     [rsp+0A0h+ReturnLength], rax; ReturnLength
0x1400177fc  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x140017800  lea     edx, [r14+0Ch]; TokenInformationClass
0x140017804  call    cs:__imp_NtQueryInformationToken
0x14001780a  mov     ebx, eax
0x14001780c  test    eax, eax
0x14001780e  js      short loc_14001782F
0x140017810  cmp     dword ptr [rbp+57h+var_48+8], edi
0x140017813  jnz     short loc_14001781A
0x140017815  cmp     dword ptr [rbp+57h+var_48+0Ch], edi
0x140017818  jl      short loc_14001782F
0x14001781a  cmp     dword ptr [rbp+57h+TokenInformation+8], 3E7h
0x140017821  jnz     short loc_14001782F
0x140017823  cmp     dword ptr [rbp+57h+TokenInformation+0Ch], 0
0x140017827  mov     eax, 4
0x14001782c  cmovz   edi, eax
0x14001782f  mov     rcx, [rbp+57h+TokenHandle]; Handle
0x140017833  call    cs:__imp_NtClose
0x140017839  mov     r9d, 8; ThreadInformationLength
0x14001783f  mov     [rbp+57h+ThreadInformation], 0
0x140017847  lea     r8, [rbp+57h+ThreadInformation]; ThreadInformation
0x14001784b  mov     rcx, r14; ThreadHandle
0x14001784e  lea     edx, [r9-3]; ThreadInformationClass
0x140017852  call    cs:__imp_NtSetInformationThread
0x140017858  lea     rcx, [rsi+18h]
0x14001785c  call    cs:__imp_RtlAcquireSRWLockExclusive
0x140017862  mov     eax, [rsi]
0x140017864  test    al, 6
0x140017866  jnz     short loc_140017872
0x140017868  test    ebx, ebx
0x14001786a  js      short loc_140017874
0x14001786c  or      eax, edi
0x14001786e  mov     [rsi], eax
0x140017870  jmp     short loc_140017874
0x140017872  xor     ebx, ebx
0x140017874  lea     rcx, [rsi+18h]
0x140017878  call    cs:__imp_RtlReleaseSRWLockExclusive
0x14001787e  mov     eax, ebx
0x140017880  mov     rcx, [rbp+57h+var_20]
0x140017884  xor     rcx, rsp; StackCookie
0x140017887  call    __security_check_cookie
0x14001788c  lea     r11, [rsp+0A0h+var_10]
0x140017894  mov     rbx, [r11+30h]
0x140017898  mov     rsi, [r11+38h]
0x14001789c  mov     rsp, r11
0x14001789f  pop     r14
0x1400178a1  pop     rdi
0x1400178a2  pop     rbp
0x1400178a3  retn
```
