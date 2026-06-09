# InitKernelRot

- ea: `0x1800f9178`
- end: `0x1800f93c6`
- name: `InitKernelRot`
- size: `590`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800eeb88`

## callees

- `0x180050178`
- `0x1800684b4`
- `0x1800b27e0`
- `0x1800b3128`
- `0x1800f8e38`
- `0x1800f9178`

## import_xrefs

- `ntdll!RtlAllocateAndInitializeSidEx` at `0x1800f92a8`
- `ntdll!RtlAllocateAndInitializeSidEx` at `0x1800f92a8`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800f9341`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800f934c`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800f9357`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800f9388`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800f939a`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800f9341`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800f934c`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800f9357`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800f9388`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800f939a`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800f91f1`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800f923a`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800f91f1`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800f923a`

## pseudocode

```c
__int64 InitKernelRot()
{
  __int64 v0; // rdx
  void *v1; // rax
  __int64 v2; // rdx
  __int64 v3; // r8
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
0x1800f9178  mov     [rsp-8+arg_0], rbx
0x1800f917d  mov     [rsp-8+arg_8], rdi
0x1800f9182  push    rbp
0x1800f9183  lea     rbp, [rsp-60h]
0x1800f9188  sub     rsp, 160h
0x1800f918f  mov     rax, cs:__security_cookie
0x1800f9196  xor     rax, rsp
0x1800f9199  mov     [rbp+60h+var_8], rax
0x1800f919d  xor     edi, edi
0x1800f919f  mov     word ptr [rbp+60h+pIdentifierAuthority.Value+4], 100h
0x1800f91a5  lea     rax, [rsp+160h+var_100]
0x1800f91aa  mov     dword ptr [rbp+60h+pIdentifierAuthority.Value], edi
0x1800f91ad  mov     [rsp+160h+pSid], rax; pSid
0x1800f91b2  lea     rcx, [rbp+60h+pIdentifierAuthority]; pIdentifierAuthority
0x1800f91b6  mov     [rsp+160h+nSubAuthority7], edi; nSubAuthority7
0x1800f91ba  xor     r9d, r9d; nSubAuthority1
0x1800f91bd  mov     [rsp+160h+nSubAuthority6], edi; nSubAuthority6
0x1800f91c1  lea     ebx, [rdi+1]
0x1800f91c4  mov     [rsp+160h+nSubAuthority5], edi; nSubAuthority5
0x1800f91c8  mov     dl, bl; nSubAuthorityCount
0x1800f91ca  mov     dword ptr [rsp+160h+nSubAuthority4], edi; nSubAuthority4
0x1800f91ce  xor     r8d, r8d; nSubAuthority0
0x1800f91d1  mov     [rsp+160h+nSubAuthority3], edi; nSubAuthority3
0x1800f91d5  mov     [rsp+160h+nSubAuthority2], edi; nSubAuthority2
0x1800f91d9  mov     dword ptr [rbp+60h+var_E0.Value], edi
0x1800f91dc  mov     word ptr [rbp+60h+var_E0.Value+4], 0F00h
0x1800f91e2  mov     [rsp+160h+var_100], rdi
0x1800f91e7  mov     [rsp+160h+var_F0], rdi
0x1800f91ec  mov     [rsp+160h+var_E8], rdi
0x1800f91f1  call    cs:__imp_AllocateAndInitializeSid
0x1800f91f7  test    eax, eax
0x1800f91f9  jz      loc_1800F93A0
0x1800f91ff  cmp     [rsp+160h+var_100], rdi
0x1800f9204  jz      loc_1800F93A0
0x1800f920a  lea     rax, [rsp+160h+var_F0]
0x1800f920f  mov     r9d, ebx; nSubAuthority1
0x1800f9212  mov     [rsp+160h+pSid], rax; pSid
0x1800f9217  lea     r8d, [rdi+2]; nSubAuthority0
0x1800f921b  mov     [rsp+160h+nSubAuthority7], edi; nSubAuthority7
0x1800f921f  lea     rcx, [rbp+60h+var_E0]; pIdentifierAuthority
0x1800f9223  mov     [rsp+160h+nSubAuthority6], edi; nSubAuthority6
0x1800f9227  mov     dl, r8b; nSubAuthorityCount
0x1800f922a  mov     [rsp+160h+nSubAuthority5], edi; nSubAuthority5
0x1800f922e  mov     dword ptr [rsp+160h+nSubAuthority4], edi; nSubAuthority4
0x1800f9232  mov     [rsp+160h+nSubAuthority3], edi; nSubAuthority3
0x1800f9236  mov     [rsp+160h+nSubAuthority2], edi; nSubAuthority2
0x1800f923a  call    cs:__imp_AllocateAndInitializeSid
0x1800f9240  test    eax, eax
0x1800f9242  jz      loc_1800F9395
0x1800f9248  cmp     [rsp+160h+var_F0], rdi
0x1800f924d  jz      loc_1800F9395
0x1800f9253  lea     r9, [rsp+160h+var_E8]
0x1800f9258  mov     [rbp+60h+var_30], 3
0x1800f925f  lea     r8, [rbp+60h+var_30]
0x1800f9263  mov     [rbp+60h+var_2C], 400h
0x1800f926a  mov     dl, 0Ah
0x1800f926c  mov     [rbp+60h+var_28], 8F6027A1h
0x1800f9273  lea     rcx, [rbp+60h+var_E0]
0x1800f9277  mov     [rbp+60h+var_24], 3418BB9Ah
0x1800f927e  mov     [rbp+60h+var_20], 0FF77B663h
0x1800f9285  mov     [rbp+60h+var_1C], 6CB6D59Dh
0x1800f928c  mov     [rbp+60h+var_18], 681A32E7h
0x1800f9293  mov     [rbp+60h+var_14], 92435208h
0x1800f929a  mov     [rbp+60h+var_10], 0D81FA686h
0x1800f92a1  mov     [rbp+60h+var_C], 3B1B1798h
0x1800f92a8  call    cs:__imp_RtlAllocateAndInitializeSidEx
0x1800f92ae  test    eax, eax
0x1800f92b0  js      loc_1800F9383
0x1800f92b6  mov     rcx, [rsp+160h+var_E8]
0x1800f92bb  mov     dword ptr [rsp+160h+var_F8], ebx
0x1800f92bf  test    rcx, rcx
0x1800f92c2  jz      loc_1800F9383
0x1800f92c8  mov     rax, [rsp+160h+var_100]
0x1800f92cd  lea     r9d, [rdi+4]
0x1800f92d1  mov     dword ptr [rsp+160h+nSubAuthority4], r9d; void **
0x1800f92d6  lea     edx, [rdi+2]
0x1800f92d9  mov     [rbp+60h+var_D0], rax
0x1800f92dd  xorps   xmm0, xmm0
0x1800f92e0  mov     rax, [rsp+160h+var_F0]
0x1800f92e5  xor     r8d, r8d
0x1800f92e8  mov     [rbp+60h+var_B8], rcx
0x1800f92ec  lea     rcx, [rbp+60h+var_D0]
0x1800f92f0  mov     [rsp+160h+nSubAuthority3], 0F001Fh; unsigned int
0x1800f92f8  mov     [rbp+60h+var_C0], rax
0x1800f92fc  mov     [rbp+60h+var_C8], rdi
0x1800f9300  movdqa  [rbp+60h+var_B0], xmm0
0x1800f9305  mov     [rsp+160h+nSubAuthority2], r9d
0x1800f930a  call    ?IdentifyAccess@CAccessInfo@@QEAAPEAXW4SecurityDescriptorOwner@@KKKKK@Z; CAccessInfo::IdentifyAccess(SecurityDescriptorOwner,ulong,ulong,ulong,ulong,ulong)
0x1800f930f  lea     rcx, [rsp+160h+var_F8]; unsigned __int16 *
0x1800f9314  mov     qword ptr [rsp+160h+nSubAuthority5], rcx; int *
0x1800f9319  mov     qword ptr [rsp+160h+nSubAuthority2], rax; void *
0x1800f931e  call    ?CreateSharedFileMapping@@YAPEAXPEBGKKPEAX1KPEAPEAXPEAH@Z; CreateSharedFileMapping(ushort const *,ulong,ulong,void *,void *,ulong,void * *,int *)
0x1800f9323  mov     cs:?ghKernelRotSm@@3PEAXEA, rax; void * ghKernelRotSm
0x1800f932a  test    rax, rax
0x1800f932d  jz      short loc_1800F9337
0x1800f932f  mov     ebx, edi
0x1800f9331  cmp     dword ptr [rsp+160h+var_F8], edi
0x1800f9335  jnz     short loc_1800F933C
0x1800f9337  mov     ebx, 8007000Eh
0x1800f933c  mov     rcx, [rsp+160h+var_100]; pSid
0x1800f9341  call    cs:__imp_FreeSid
0x1800f9347  mov     rcx, [rsp+160h+var_F0]; pSid
0x1800f934c  call    cs:__imp_FreeSid
0x1800f9352  mov     rcx, [rsp+160h+var_E8]; pSid
0x1800f9357  call    cs:__imp_FreeSid
0x1800f935d  mov     rcx, cs:?gpbKernelHintArray@@3PEAEEA; void *
0x1800f9364  test    rcx, rcx
0x1800f9367  jz      short loc_1800F9376
0x1800f9369  xor     edx, edx; Val
0x1800f936b  mov     r8d, 0FBh; Size
0x1800f9371  call    memset_0
0x1800f9376  lea     rcx, [rbp+60h+var_D0]; this
0x1800f937a  call    ??1CAccessInfo@@QEAA@XZ; CAccessInfo::~CAccessInfo(void)
0x1800f937f  mov     eax, ebx
0x1800f9381  jmp     short loc_1800F93A5
0x1800f9383  mov     rcx, [rsp+160h+var_100]; pSid
0x1800f9388  call    cs:__imp_FreeSid
0x1800f938e  mov     rcx, [rsp+160h+var_F0]
0x1800f9393  jmp     short loc_1800F939A
0x1800f9395  mov     rcx, [rsp+160h+var_100]; pSid
0x1800f939a  call    cs:__imp_FreeSid
0x1800f93a0  mov     eax, 8007000Eh
0x1800f93a5  mov     rcx, [rbp+60h+var_8]
0x1800f93a9  xor     rcx, rsp; StackCookie
0x1800f93ac  call    __security_check_cookie
0x1800f93b1  lea     r11, [rsp+160h+var_s0]
0x1800f93b9  mov     rbx, [r11+10h]
0x1800f93bd  mov     rdi, [r11+18h]
0x1800f93c1  mov     rsp, r11
0x1800f93c4  pop     rbp
0x1800f93c5  retn
```
