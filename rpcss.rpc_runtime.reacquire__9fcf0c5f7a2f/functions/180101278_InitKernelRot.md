# InitKernelRot

- ea: `0x180101278`
- end: `0x1801014f7`
- name: `InitKernelRot`
- size: `639`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800f6770`

## callees

- `0x180051cac`
- `0x18006d3ec`
- `0x1800b7ac0`
- `0x1800b8428`
- `0x180100ee8`
- `0x180101278`

## import_xrefs

- `ntdll!RtlAllocateAndInitializeSidEx` at `0x1801013b4`
- `ntdll!RtlAllocateAndInitializeSidEx` at `0x1801013b4`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180101453`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180101464`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180101475`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1801014ac`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1801014c4`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180101453`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180101464`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180101475`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1801014ac`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1801014c4`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1801012f1`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180101340`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1801012f1`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180101340`

## pseudocode

```c
__int64 InitKernelRot()
{
  __int64 v0; // rdx
  void *v1; // rax
  unsigned int v2; // edx
  unsigned int v3; // r8d
  void *v4; // r9
  unsigned int v5; // ebx
  PSID v7; // rcx
  void **nSubAuthority4; // [rsp+30h] [rbp-D0h]
  PSID pSid; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 v10[2]; // [rsp+68h] [rbp-98h] BYREF
  PSID v11; // [rsp+70h] [rbp-90h] BYREF
  PSID v12; // [rsp+78h] [rbp-88h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY v13; // [rsp+80h] [rbp-80h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+88h] [rbp-78h] BYREF
  _QWORD v15[4]; // [rsp+90h] [rbp-70h] BYREF
  __int128 v16; // [rsp+B0h] [rbp-50h]
  _DWORD v17[10]; // [rsp+130h] [rbp+30h] BYREF

  *(_WORD *)&pIdentifierAuthority.Value[4] = 256;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  *(_DWORD *)v13.Value = 0;
  *(_WORD *)&v13.Value[4] = 3840;
  pSid = 0;
  v11 = 0;
  v12 = 0;
  if ( !AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 0, 0, 0, 0, 0, 0, 0, 0, &pSid) || !pSid )
    return 2147942414LL;
  if ( !AllocateAndInitializeSid(&v13, 2u, 2u, 1u, 0, 0, 0, 0, 0, 0, &v11) || !v11 )
  {
    v7 = pSid;
    goto LABEL_15;
  }
  v17[0] = 3;
  v17[1] = 1024;
  LOBYTE(v0) = 10;
  v17[2] = -1889523807;
  v17[3] = 874036122;
  v17[4] = -8931741;
  v17[5] = 1823921565;
  v17[6] = 1746547431;
  v17[7] = -1841081848;
  v17[8] = -669014394;
  v17[9] = 991631256;
  if ( (int)RtlAllocateAndInitializeSidEx(&v13, v0, v17, &v12) < 0 || (*(_DWORD *)v10 = 1, !v12) )
  {
    FreeSid(pSid);
    v7 = v11;
LABEL_15:
    FreeSid(v7);
    return 2147942414LL;
  }
  LODWORD(nSubAuthority4) = 4;
  v15[0] = pSid;
  v15[3] = v12;
  v15[2] = v11;
  v15[1] = 0;
  v16 = 0;
  v1 = (void *)CAccessInfo::IdentifyAccess(v15, 2, 0, 4);
  ghKernelRotSm = CreateSharedFileMapping(v10, v2, v3, v4, v1, 0xF001Fu, nSubAuthority4, (int *)v10);
  if ( !ghKernelRotSm || (v5 = 0, !*(_DWORD *)v10) )
    v5 = -2147024882;
  FreeSid(pSid);
  FreeSid(v11);
  FreeSid(v12);
  if ( gpbKernelHintArray )
    memset_0(gpbKernelHintArray, 0, 0xFBu);
  CAccessInfo::~CAccessInfo((CAccessInfo *)v15);
  return v5;
}

```

## disassembly

```asm
0x180101278  mov     [rsp-8+arg_0], rbx
0x18010127d  mov     [rsp-8+arg_8], rdi
0x180101282  push    rbp
0x180101283  lea     rbp, [rsp-60h]
0x180101288  sub     rsp, 160h
0x18010128f  mov     rax, cs:__security_cookie
0x180101296  xor     rax, rsp
0x180101299  mov     [rbp+60h+var_8], rax
0x18010129d  xor     edi, edi
0x18010129f  mov     word ptr [rbp+60h+pIdentifierAuthority.Value+4], 100h
0x1801012a5  lea     rax, [rsp+160h+var_100]
0x1801012aa  mov     dword ptr [rbp+60h+pIdentifierAuthority.Value], edi
0x1801012ad  mov     [rsp+160h+pSid], rax; pSid
0x1801012b2  lea     rcx, [rbp+60h+pIdentifierAuthority]; pIdentifierAuthority
0x1801012b6  mov     [rsp+160h+nSubAuthority7], edi; nSubAuthority7
0x1801012ba  xor     r9d, r9d; nSubAuthority1
0x1801012bd  mov     [rsp+160h+nSubAuthority6], edi; nSubAuthority6
0x1801012c1  lea     ebx, [rdi+1]
0x1801012c4  mov     [rsp+160h+nSubAuthority5], edi; nSubAuthority5
0x1801012c8  mov     dl, bl; nSubAuthorityCount
0x1801012ca  mov     dword ptr [rsp+160h+nSubAuthority4], edi; nSubAuthority4
0x1801012ce  xor     r8d, r8d; nSubAuthority0
0x1801012d1  mov     [rsp+160h+nSubAuthority3], edi; nSubAuthority3
0x1801012d5  mov     [rsp+160h+nSubAuthority2], edi; nSubAuthority2
0x1801012d9  mov     dword ptr [rbp+60h+var_E0.Value], edi
0x1801012dc  mov     word ptr [rbp+60h+var_E0.Value+4], 0F00h
0x1801012e2  mov     [rsp+160h+var_100], rdi
0x1801012e7  mov     [rsp+160h+var_F0], rdi
0x1801012ec  mov     [rsp+160h+var_E8], rdi
0x1801012f1  call    cs:__imp_AllocateAndInitializeSid
0x1801012f8  nop     dword ptr [rax+rax+00h]
0x1801012fd  test    eax, eax
0x1801012ff  jz      loc_1801014D0
0x180101305  cmp     [rsp+160h+var_100], rdi
0x18010130a  jz      loc_1801014D0
0x180101310  lea     rax, [rsp+160h+var_F0]
0x180101315  mov     r9d, ebx; nSubAuthority1
0x180101318  mov     [rsp+160h+pSid], rax; pSid
0x18010131d  lea     r8d, [rdi+2]; nSubAuthority0
0x180101321  mov     [rsp+160h+nSubAuthority7], edi; nSubAuthority7
0x180101325  lea     rcx, [rbp+60h+var_E0]; pIdentifierAuthority
0x180101329  mov     [rsp+160h+nSubAuthority6], edi; nSubAuthority6
0x18010132d  mov     dl, r8b; nSubAuthorityCount
0x180101330  mov     [rsp+160h+nSubAuthority5], edi; nSubAuthority5
0x180101334  mov     dword ptr [rsp+160h+nSubAuthority4], edi; nSubAuthority4
0x180101338  mov     [rsp+160h+nSubAuthority3], edi; nSubAuthority3
0x18010133c  mov     [rsp+160h+nSubAuthority2], edi; nSubAuthority2
0x180101340  call    cs:__imp_AllocateAndInitializeSid
0x180101347  nop     dword ptr [rax+rax+00h]
0x18010134c  test    eax, eax
0x18010134e  jz      loc_1801014BF
0x180101354  cmp     [rsp+160h+var_F0], rdi
0x180101359  jz      loc_1801014BF
0x18010135f  lea     r9, [rsp+160h+var_E8]
0x180101364  mov     [rbp+60h+var_30], 3
0x18010136b  lea     r8, [rbp+60h+var_30]
0x18010136f  mov     [rbp+60h+var_2C], 400h
0x180101376  mov     dl, 0Ah
0x180101378  mov     [rbp+60h+var_28], 8F6027A1h
0x18010137f  lea     rcx, [rbp+60h+var_E0]
0x180101383  mov     [rbp+60h+var_24], 3418BB9Ah
0x18010138a  mov     [rbp+60h+var_20], 0FF77B663h
0x180101391  mov     [rbp+60h+var_1C], 6CB6D59Dh
0x180101398  mov     [rbp+60h+var_18], 681A32E7h
0x18010139f  mov     [rbp+60h+var_14], 92435208h
0x1801013a6  mov     [rbp+60h+var_10], 0D81FA686h
0x1801013ad  mov     [rbp+60h+var_C], 3B1B1798h
0x1801013b4  call    cs:__imp_RtlAllocateAndInitializeSidEx
0x1801013bb  nop     dword ptr [rax+rax+00h]
0x1801013c0  test    eax, eax
0x1801013c2  js      loc_1801014A7
0x1801013c8  mov     rcx, [rsp+160h+var_E8]
0x1801013cd  mov     dword ptr [rsp+160h+var_F8], ebx
0x1801013d1  test    rcx, rcx
0x1801013d4  jz      loc_1801014A7
0x1801013da  mov     rax, [rsp+160h+var_100]
0x1801013df  lea     r9d, [rdi+4]
0x1801013e3  mov     dword ptr [rsp+160h+nSubAuthority4], r9d; void **
0x1801013e8  lea     edx, [rdi+2]
0x1801013eb  mov     [rbp+60h+var_D0], rax
0x1801013ef  xorps   xmm0, xmm0
0x1801013f2  mov     rax, [rsp+160h+var_F0]
0x1801013f7  xor     r8d, r8d
0x1801013fa  mov     [rbp+60h+var_B8], rcx
0x1801013fe  lea     rcx, [rbp+60h+var_D0]
0x180101402  mov     [rsp+160h+nSubAuthority3], 0F001Fh; unsigned int
0x18010140a  mov     [rbp+60h+var_C0], rax
0x18010140e  mov     [rbp+60h+var_C8], rdi
0x180101412  movdqa  [rbp+60h+var_B0], xmm0
0x180101417  mov     [rsp+160h+nSubAuthority2], r9d
0x18010141c  call    ?IdentifyAccess@CAccessInfo@@QEAAPEAXW4SecurityDescriptorOwner@@KKKKK@Z; CAccessInfo::IdentifyAccess(SecurityDescriptorOwner,ulong,ulong,ulong,ulong,ulong)
0x180101421  lea     rcx, [rsp+160h+var_F8]; unsigned __int16 *
0x180101426  mov     qword ptr [rsp+160h+nSubAuthority5], rcx; int *
0x18010142b  mov     qword ptr [rsp+160h+nSubAuthority2], rax; void *
0x180101430  call    ?CreateSharedFileMapping@@YAPEAXPEBGKKPEAX1KPEAPEAXPEAH@Z; CreateSharedFileMapping(ushort const *,ulong,ulong,void *,void *,ulong,void * *,int *)
0x180101435  mov     cs:?ghKernelRotSm@@3PEAXEA, rax; void * ghKernelRotSm
0x18010143c  test    rax, rax
0x18010143f  jz      short loc_180101449
0x180101441  mov     ebx, edi
0x180101443  cmp     dword ptr [rsp+160h+var_F8], edi
0x180101447  jnz     short loc_18010144E
0x180101449  mov     ebx, 8007000Eh
0x18010144e  mov     rcx, [rsp+160h+var_100]; pSid
0x180101453  call    cs:__imp_FreeSid
0x18010145a  nop     dword ptr [rax+rax+00h]
0x18010145f  mov     rcx, [rsp+160h+var_F0]; pSid
0x180101464  call    cs:__imp_FreeSid
0x18010146b  nop     dword ptr [rax+rax+00h]
0x180101470  mov     rcx, [rsp+160h+var_E8]; pSid
0x180101475  call    cs:__imp_FreeSid
0x18010147c  nop     dword ptr [rax+rax+00h]
0x180101481  mov     rcx, cs:?gpbKernelHintArray@@3PEAEEA; void *
0x180101488  test    rcx, rcx
0x18010148b  jz      short loc_18010149A
0x18010148d  xor     edx, edx; Val
0x18010148f  mov     r8d, 0FBh; Size
0x180101495  call    memset_0
0x18010149a  lea     rcx, [rbp+60h+var_D0]; this
0x18010149e  call    ??1CAccessInfo@@QEAA@XZ; CAccessInfo::~CAccessInfo(void)
0x1801014a3  mov     eax, ebx
0x1801014a5  jmp     short loc_1801014D5
0x1801014a7  mov     rcx, [rsp+160h+var_100]; pSid
0x1801014ac  call    cs:__imp_FreeSid
0x1801014b3  nop     dword ptr [rax+rax+00h]
0x1801014b8  mov     rcx, [rsp+160h+var_F0]
0x1801014bd  jmp     short loc_1801014C4
0x1801014bf  mov     rcx, [rsp+160h+var_100]; pSid
0x1801014c4  call    cs:__imp_FreeSid
0x1801014cb  nop     dword ptr [rax+rax+00h]
0x1801014d0  mov     eax, 8007000Eh
0x1801014d5  mov     rcx, [rbp+60h+var_8]
0x1801014d9  xor     rcx, rsp; StackCookie
0x1801014dc  call    __security_check_cookie
0x1801014e1  lea     r11, [rsp+160h+var_s0]
0x1801014e9  mov     rbx, [r11+10h]
0x1801014ed  mov     rdi, [r11+18h]
0x1801014f1  mov     rsp, r11
0x1801014f4  pop     rbp
0x1801014f5  retn
```
