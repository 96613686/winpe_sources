# CUmRdpPrn::SendDefaultPrinterToRDPClip(ushort const *)

- ea: `0x180006170`
- end: `0x18000645e`
- name: `?SendDefaultPrinterToRDPClip@CUmRdpPrn@@AEAAHPEBG@Z`
- size: `750`
- prototype: `int(CUmRdpPrn *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180016e70`

## callees

- `0x180004d40`
- `0x180006170`
- `0x180009e50`
- `0x18000a01c`
- `0x18000ab3c`
- `0x18000bd04`
- `0x18001294c`
- `0x180047ebe`
- `0x180047ef0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800061fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006213`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006397`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800061fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006213`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006397`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006238`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006238`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1800061e5`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1800061e5`
- `api-ms-win-security-base-l1-1-0!GetSidIdentifierAuthority` at `0x1800061f4`
- `api-ms-win-security-base-l1-1-0!GetSidIdentifierAuthority` at `0x1800061f4`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18000620a`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18000620a`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18000638e`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18000638e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006252`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000644b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006252`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000644b`

## pseudocode

```c
__int64 __fastcall CUmRdpPrn::SendDefaultPrinterToRDPClip(HANDLE *this, const unsigned __int16 *a2)
{
  void *UserSid; // rax
  void *v5; // rsi
  unsigned int valid; // ebx
  PSID_IDENTIFIER_AUTHORITY SidIdentifierAuthority; // rdi
  PUCHAR SidSubAuthorityCount; // rbx
  DWORD v9; // r12d
  __int64 v11; // rcx
  __int64 v12; // rdi
  DWORD i; // r15d
  PDWORD SidSubAuthority; // r13
  _DWORD *v15; // r14
  CUmRdpRpc *v16; // rax
  CUmRdpRpc *v17; // rdi
  unsigned int Pointer; // eax
  PVOID ProcessHeap; // rcx
  unsigned __int16 v20[264]; // [rsp+50h] [rbp-258h] BYREF

  memset_0(v20, 0, 0x208u);
  UserSid = TSNUTL_GetUserSid(this[23]);
  v5 = UserSid;
  if ( !UserSid )
    return 0;
  valid = IsValidSid(UserSid);
  if ( !valid )
  {
LABEL_9:
    HeapFree(NtCurrentPeb()->ProcessHeap, 0, v5);
    return valid;
  }
  SidIdentifierAuthority = GetSidIdentifierAuthority(v5);
  if ( GetLastError() || (SidSubAuthorityCount = GetSidSubAuthorityCount(v5), GetLastError()) )
  {
LABEL_8:
    valid = 0;
    goto LABEL_9;
  }
  v9 = *SidSubAuthorityCount;
  if ( 12 * v9 + 30 > 0x104 )
  {
    SetLastError(0x7Au);
    goto LABEL_8;
  }
  StringCchPrintfW(v20, 0x104u, L"S-%lu-", 1);
  v11 = -1;
  do
    ++v11;
  while ( v20[v11] );
  if ( *(_WORD *)SidIdentifierAuthority->Value )
    StringCchPrintfW(
      &v20[(unsigned int)v11],
      (unsigned int)(260 - v11),
      L"0x%02hx%02hx%02hx%02hx%02hx%02hx",
      SidIdentifierAuthority->Value[0],
      SidIdentifierAuthority->Value[1],
      SidIdentifierAuthority->Value[2],
      SidIdentifierAuthority->Value[3],
      SidIdentifierAuthority->Value[4],
      SidIdentifierAuthority->Value[5]);
  else
    StringCchPrintfW(
      &v20[(unsigned int)v11],
      (unsigned int)(260 - v11),
      L"%lu",
      SidIdentifierAuthority->Value[5]
    + (SidIdentifierAuthority->Value[4] << 8)
    + (SidIdentifierAuthority->Value[3] << 16)
    + (SidIdentifierAuthority->Value[2] << 24));
  v12 = -1;
  do
    ++v12;
  while ( v20[v12] );
  valid = 0;
  for ( i = 0; i < v9; ++i )
  {
    SidSubAuthority = GetSidSubAuthority(v5, i);
    if ( GetLastError() )
      goto LABEL_9;
    StringCchPrintfW(&v20[(unsigned int)v12], (unsigned int)(260 - v12), L"-%lu", *SidSubAuthority);
    v12 = -1;
    do
      ++v12;
    while ( v20[v12] );
  }
  v15 = *this;
  v16 = (CUmRdpRpc *)operator new(0x10u);
  v17 = v16;
  if ( !v16 )
    goto LABEL_9;
  *(_QWORD *)v16 = 0;
  *((_DWORD *)v16 + 2) = -1;
  *((_DWORD *)v16 + 2) = *v15;
  if ( (unsigned int)CUmRdpRpc::CreateBinding((RPC_BINDING_HANDLE *)v16) )
  {
    CUmRdpRpc::Release(v17);
    goto LABEL_9;
  }
  Pointer = (unsigned int)CUmRdpRpc::StoreDefaultPrinter(v17, v20, a2).Pointer;
  ProcessHeap = NtCurrentPeb()->ProcessHeap;
  if ( !Pointer )
    valid = 1;
  HeapFree(ProcessHeap, 0, v5);
  CUmRdpRpc::Release(v17);
  return valid;
}

```

## disassembly

```asm
0x180006170  push    rbx
0x180006172  push    rbp
0x180006173  push    rsi
0x180006174  push    r14
0x180006176  sub     rsp, 288h
0x18000617d  mov     rax, cs:__security_cookie
0x180006184  xor     rax, rsp
0x180006187  mov     [rsp+2A8h+var_48], rax
0x18000618f  mov     rbp, rdx
0x180006192  mov     r14, rcx
0x180006195  xor     edx, edx; Val
0x180006197  lea     rcx, [rsp+2A8h+var_258]; void *
0x18000619c  mov     r8d, 208h; Size
0x1800061a2  call    memset_0
0x1800061a7  mov     rcx, [r14+0B8h]; TokenHandle
0x1800061ae  call    ?TSNUTL_GetUserSid@@YAPEAXPEAX@Z; TSNUTL_GetUserSid(void *)
0x1800061b3  mov     rsi, rax
0x1800061b6  test    rax, rax
0x1800061b9  jnz     short loc_1800061C2
0x1800061bb  xor     ebx, ebx
0x1800061bd  jmp     loc_180006278
0x1800061c2  mov     [rsp+2A8h+arg_10], rdi
0x1800061ca  mov     rcx, rsi; pSid
0x1800061cd  mov     [rsp+2A8h+var_28], r12
0x1800061d5  mov     [rsp+2A8h+var_30], r13
0x1800061dd  mov     [rsp+2A8h+var_38], r15
0x1800061e5  call    cs:__imp_IsValidSid
0x1800061eb  mov     ebx, eax
0x1800061ed  test    eax, eax
0x1800061ef  jz      short loc_180006240
0x1800061f1  mov     rcx, rsi; pSid
0x1800061f4  call    cs:__imp_GetSidIdentifierAuthority
0x1800061fa  mov     rdi, rax
0x1800061fd  call    cs:__imp_GetLastError
0x180006203  test    eax, eax
0x180006205  jnz     short loc_18000623E
0x180006207  mov     rcx, rsi; pSid
0x18000620a  call    cs:__imp_GetSidSubAuthorityCount
0x180006210  mov     rbx, rax
0x180006213  call    cs:__imp_GetLastError
0x180006219  test    eax, eax
0x18000621b  jnz     short loc_18000623E
0x18000621d  movzx   r12d, byte ptr [rbx]
0x180006221  lea     eax, [r12+r12*2]
0x180006225  lea     eax, ds:1Eh[rax*4]
0x18000622c  cmp     eax, 104h
0x180006231  jbe     short loc_180006297
0x180006233  mov     ecx, 7Ah ; 'z'; dwErrCode
0x180006238  call    cs:__imp_SetLastError
0x18000623e  xor     ebx, ebx
0x180006240  mov     rcx, gs:60h
0x180006249  mov     r8, rsi; lpMem
0x18000624c  xor     edx, edx; dwFlags
0x18000624e  mov     rcx, [rcx+30h]; hHeap
0x180006252  call    cs:__imp_HeapFree
0x180006258  mov     r13, [rsp+2A8h+var_30]
0x180006260  mov     r12, [rsp+2A8h+var_28]
0x180006268  mov     rdi, [rsp+2A8h+arg_10]
0x180006270  mov     r15, [rsp+2A8h+var_38]
0x180006278  mov     eax, ebx
0x18000627a  mov     rcx, [rsp+2A8h+var_48]
0x180006282  xor     rcx, rsp; StackCookie
0x180006285  call    __security_check_cookie
0x18000628a  add     rsp, 288h
0x180006291  pop     r14
0x180006293  pop     rsi
0x180006294  pop     rbp
0x180006295  pop     rbx
0x180006296  retn
0x180006297  mov     r9d, 1
0x18000629d  lea     r8, aSLu; "S-%lu-"
0x1800062a4  mov     edx, 104h; unsigned __int64
0x1800062a9  lea     rcx, [rsp+2A8h+var_258]; unsigned __int16 *
0x1800062ae  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800062b3  lea     rax, [rsp+2A8h+var_258]
0x1800062b8  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800062bf  inc     rcx
0x1800062c2  cmp     word ptr [rax+rcx*2], 0
0x1800062c7  jnz     short loc_1800062BF
0x1800062c9  movzx   eax, byte ptr [rdi]
0x1800062cc  test    al, al
0x1800062ce  jnz     short loc_180006319
0x1800062d0  cmp     [rdi+1], al
0x1800062d3  jnz     short loc_180006319
0x1800062d5  movzx   eax, byte ptr [rdi+3]
0x1800062d9  lea     r8, aLu_0; "%lu"
0x1800062e0  movzx   r9d, byte ptr [rdi+2]
0x1800062e5  mov     edx, 104h
0x1800062ea  shl     eax, 10h
0x1800062ed  sub     edx, ecx; unsigned __int64
0x1800062ef  shl     r9d, 18h
0x1800062f3  add     r9d, eax
0x1800062f6  movzx   eax, byte ptr [rdi+4]
0x1800062fa  shl     eax, 8
0x1800062fd  add     r9d, eax
0x180006300  movzx   eax, byte ptr [rdi+5]
0x180006304  add     r9d, eax
0x180006307  mov     eax, ecx
0x180006309  lea     rcx, [rsp+2A8h+var_258]
0x18000630e  lea     rcx, [rcx+rax*2]; unsigned __int16 *
0x180006312  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180006317  jmp     short loc_180006368
0x180006319  movzx   r8d, byte ptr [rdi+5]
0x18000631e  mov     r9d, eax
0x180006321  movzx   r10d, byte ptr [rdi+4]
0x180006326  mov     edx, 104h
0x18000632b  movzx   r11d, byte ptr [rdi+3]
0x180006330  sub     edx, ecx; unsigned __int64
0x180006332  movzx   ebx, byte ptr [rdi+2]
0x180006336  movzx   edi, byte ptr [rdi+1]
0x18000633a  mov     [rsp+2A8h+var_268], r8d
0x18000633f  lea     r8, a0x02hx02hx02hx; "0x%02hx%02hx%02hx%02hx%02hx%02hx"
0x180006346  mov     [rsp+2A8h+var_270], r10d
0x18000634b  mov     eax, ecx
0x18000634d  lea     rcx, [rsp+2A8h+var_258]
0x180006352  mov     [rsp+2A8h+var_278], r11d
0x180006357  mov     [rsp+2A8h+var_280], ebx
0x18000635b  mov     [rsp+2A8h+var_288], edi
0x18000635f  lea     rcx, [rcx+rax*2]; unsigned __int16 *
0x180006363  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180006368  lea     rax, [rsp+2A8h+var_258]
0x18000636d  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x180006374  inc     rdi
0x180006377  cmp     word ptr [rax+rdi*2], 0
0x18000637c  jnz     short loc_180006374
0x18000637e  xor     ebx, ebx
0x180006380  mov     r15d, ebx
0x180006383  cmp     r15d, r12d
0x180006386  jnb     short loc_1800063E1
0x180006388  mov     edx, r15d; nSubAuthority
0x18000638b  mov     rcx, rsi; pSid
0x18000638e  call    cs:__imp_GetSidSubAuthority
0x180006394  mov     r13, rax
0x180006397  call    cs:__imp_GetLastError
0x18000639d  test    eax, eax
0x18000639f  jnz     loc_180006240
0x1800063a5  mov     r9d, [r13+0]
0x1800063a9  lea     rax, [rsp+2A8h+var_258]
0x1800063ae  mov     edx, 104h
0x1800063b3  mov     ecx, edi
0x1800063b5  sub     edx, edi; unsigned __int64
0x1800063b7  lea     r8, aLu; "-%lu"
0x1800063be  lea     rcx, [rax+rcx*2]; unsigned __int16 *
0x1800063c2  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800063c7  lea     rax, [rsp+2A8h+var_258]
0x1800063cc  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x1800063d3  inc     rdi
0x1800063d6  cmp     [rax+rdi*2], bx
0x1800063da  jnz     short loc_1800063D3
0x1800063dc  inc     r15d
0x1800063df  jmp     short loc_180006383
0x1800063e1  mov     r14, [r14]
0x1800063e4  mov     ecx, 10h; Size
0x1800063e9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800063ee  mov     rdi, rax
0x1800063f1  test    rax, rax
0x1800063f4  jz      loc_180006240
0x1800063fa  mov     [rax], rbx
0x1800063fd  mov     rcx, rdi; Binding
0x180006400  mov     dword ptr [rax+8], 0FFFFFFFFh
0x180006407  mov     eax, [r14]
0x18000640a  mov     [rdi+8], eax
0x18000640d  call    ?CreateBinding@CUmRdpRpc@@IEAAJXZ; CUmRdpRpc::CreateBinding(void)
0x180006412  mov     rcx, rdi; this
0x180006415  test    eax, eax
0x180006417  jz      short loc_180006423
0x180006419  call    ?Release@CUmRdpRpc@@QEAAXXZ; CUmRdpRpc::Release(void)
0x18000641e  jmp     loc_180006240
0x180006423  mov     r8, rbp; unsigned __int16 *
0x180006426  lea     rdx, [rsp+2A8h+var_258]; unsigned __int16 *
0x18000642b  call    ?StoreDefaultPrinter@CUmRdpRpc@@QEAAIPEBG0@Z; CUmRdpRpc::StoreDefaultPrinter(ushort const *,ushort const *)
0x180006430  mov     rcx, gs:60h
0x180006439  xor     edx, edx; dwFlags
0x18000643b  mov     r8, rsi; lpMem
0x18000643e  mov     rcx, [rcx+30h]; hHeap
0x180006442  test    eax, eax
0x180006444  jnz     short loc_18000644B
0x180006446  mov     ebx, 1
0x18000644b  call    cs:__imp_HeapFree
0x180006451  mov     rcx, rdi; this
0x180006454  call    ?Release@CUmRdpRpc@@QEAAXXZ; CUmRdpRpc::Release(void)
0x180006459  jmp     loc_180006258
```
