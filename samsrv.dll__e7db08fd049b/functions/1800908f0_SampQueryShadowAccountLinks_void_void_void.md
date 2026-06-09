# SampQueryShadowAccountLinks(void *,void * *,void * *)

- ea: `0x1800908f0`
- end: `0x180090b15`
- name: `?SampQueryShadowAccountLinks@@YAJPEAXPEAPEAX1@Z`
- size: `549`
- prototype: `__int64 __fastcall(void *, void **, void **)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180093818`

## callees

- `0x180003760`
- `0x180003860`
- `0x1800066f0`
- `0x180011810`
- `0x180021460`
- `0x180022440`
- `0x180027e24`
- `0x1800372ac`
- `0x180078fb4`
- `0x180090664`
- `0x1800908f0`

## import_xrefs

- `ntdll!RtlEqualSid` at `0x180090994`
- `ntdll!RtlEqualSid` at `0x180090994`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180090a9e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180090aa7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180090ac9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180090a9e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180090aa7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180090ac9`

## pseudocode

```c
__int64 __fastcall SampQueryShadowAccountLinks(void *a1, void **a2, void **a3)
{
  PVOID **v6; // rdi
  void *v7; // rsi
  void *v8; // r14
  int v9; // eax
  unsigned int v10; // ebx
  __int64 v11; // r8
  __int64 v12; // r9
  int AccountContext; // eax
  int v14; // eax
  __int64 v16; // [rsp+20h] [rbp-30h]
  void *v17; // [rsp+30h] [rbp-20h] BYREF
  void *v18; // [rsp+38h] [rbp-18h] BYREF
  PSID Sid1; // [rsp+40h] [rbp-10h] BYREF
  int v20; // [rsp+98h] [rbp+48h] BYREF
  int v21; // [rsp+A0h] [rbp+50h]
  struct _SAMP_OBJECT *v22; // [rsp+A8h] [rbp+58h] BYREF

  *a2 = 0;
  *a3 = 0;
  Sid1 = 0;
  v20 = 0;
  v21 = 0;
  v6 = 0;
  v22 = 0;
  v7 = 0;
  v17 = 0;
  v8 = 0;
  v18 = 0;
  v9 = SampSplitSid(a1, &Sid1, (ULONG *)&v20);
  v10 = v9;
  if ( v9 >= 0 )
  {
    if ( RtlEqualSid(Sid1, *((PSID *)SampDefinedDomains + 171)) )
    {
      SampAcquireReadLock();
      v21 = 1;
      SampSetTransactionDomain(1);
      AccountContext = SampCreateAccountContext(4, v20, v11, v12, v16, (__int64)&v22);
      v10 = AccountContext;
      if ( AccountContext >= 0 )
      {
        v6 = (PVOID **)v22;
        v14 = SampQueryShadowAccountLinks(v22, &v17, &v18);
        v10 = v14;
        if ( v14 >= 0 )
        {
          *a2 = v17;
          *a3 = v18;
        }
        else
        {
          if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x400) != 0
            && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 2u )
          {
            WPP_SF_d(
              WPP_GLOBAL_Control[3].Buffer,
              60,
              WPP_93028685eca730797a8a21ecee3f4be1_Traceguids,
              (unsigned int)v14);
          }
          v7 = v17;
          v8 = v18;
        }
      }
      else
      {
        if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x400) != 0
          && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 2u )
        {
          WPP_SF_d(
            WPP_GLOBAL_Control[3].Buffer,
            59,
            WPP_93028685eca730797a8a21ecee3f4be1_Traceguids,
            (unsigned int)AccountContext);
        }
        v6 = (PVOID **)v22;
      }
    }
    else
    {
      if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x400) != 0
        && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 3u )
      {
        WPP_SF__sid_(
          (__int64)WPP_GLOBAL_Control[3].Buffer,
          0x3Au,
          (__int64)WPP_93028685eca730797a8a21ecee3f4be1_Traceguids,
          (char *)a1);
      }
      v10 = -1073741724;
    }
  }
  else if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x400) != 0
         && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 2u )
  {
    WPP_SF_d(WPP_GLOBAL_Control[3].Buffer, 57, WPP_93028685eca730797a8a21ecee3f4be1_Traceguids, (unsigned int)v9);
  }
  LocalFree(v7);
  LocalFree(v8);
  if ( v21 )
    SampReleaseReadLock();
  if ( v6 )
    SampDeleteContext(v6);
  LocalFree(Sid1);
  if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
    WPP_SF_Dd(WPP_GLOBAL_Control[3].Buffer, 61, WPP_93028685eca730797a8a21ecee3f4be1_Traceguids, v10, v10);
  return v10;
}

```

## disassembly

```asm
0x1800908f0  mov     [rsp-38h+arg_0], rbx
0x1800908f5  push    rbp
0x1800908f6  push    rsi
0x1800908f7  push    rdi
0x1800908f8  push    r12
0x1800908fa  push    r13
0x1800908fc  push    r14
0x1800908fe  push    r15
0x180090900  mov     rbp, rsp
0x180090903  sub     rsp, 50h
0x180090907  xor     eax, eax
0x180090909  mov     r15, r8
0x18009090c  mov     [rdx], rax
0x18009090f  mov     r12, rdx
0x180090912  mov     [r8], rax
0x180090915  lea     rdx, [rbp+Sid1]
0x180090919  lea     r8, [rbp+arg_8]
0x18009091d  mov     [rbp+Sid1], rax
0x180090921  mov     r13, rcx
0x180090924  mov     [rbp+arg_8], eax
0x180090927  mov     [rbp+arg_10], eax
0x18009092a  mov     edi, eax
0x18009092c  mov     [rbp+arg_18], rax
0x180090930  mov     esi, eax
0x180090932  mov     [rbp+var_20], rax
0x180090936  mov     r14d, eax
0x180090939  mov     [rbp+var_18], rax
0x18009093d  call    SampSplitSid
0x180090942  mov     ebx, eax
0x180090944  test    eax, eax
0x180090946  jns     short loc_180090982
0x180090948  mov     rcx, cs:WPP_GLOBAL_Control
0x18009094f  test    dword ptr [rcx+44h], 400h
0x180090956  jz      loc_180090A9B
0x18009095c  cmp     byte ptr [rcx+41h], 2
0x180090960  jb      loc_180090A9B
0x180090966  mov     rcx, [rcx+38h]
0x18009096a  lea     edx, [r14+39h]
0x18009096e  mov     r9d, eax
0x180090971  lea     r8, WPP_93028685eca730797a8a21ecee3f4be1_Traceguids
0x180090978  call    WPP_SF_d
0x18009097d  jmp     loc_180090A9B
0x180090982  mov     rdx, cs:?SampDefinedDomains@@3PEAU_PSAMP_DEFINED_DOMAINS@@EA; _PSAMP_DEFINED_DOMAINS * SampDefinedDomains
0x180090989  mov     rcx, [rbp+Sid1]; Sid1
0x18009098d  mov     rdx, [rdx+558h]; Sid2
0x180090994  call    cs:__imp_RtlEqualSid
0x18009099a  test    al, al
0x18009099c  jnz     short loc_1800909D6
0x18009099e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800909a5  test    dword ptr [rcx+44h], 400h
0x1800909ac  jz      short loc_1800909CC
0x1800909ae  cmp     byte ptr [rcx+41h], 3
0x1800909b2  jb      short loc_1800909CC
0x1800909b4  mov     rcx, [rcx+38h]
0x1800909b8  lea     r8, WPP_93028685eca730797a8a21ecee3f4be1_Traceguids
0x1800909bf  mov     edx, 3Ah ; ':'
0x1800909c4  mov     r9, r13
0x1800909c7  call    WPP_SF__sid_
0x1800909cc  mov     ebx, 0C0000064h
0x1800909d1  jmp     loc_180090A9B
0x1800909d6  call    SampAcquireReadLock
0x1800909db  mov     eax, 1
0x1800909e0  mov     ecx, eax
0x1800909e2  mov     [rbp+arg_10], eax
0x1800909e5  call    SampSetTransactionDomain
0x1800909ea  mov     edx, [rbp+arg_8]
0x1800909ed  lea     rax, [rbp+arg_18]
0x1800909f1  mov     ecx, 4
0x1800909f6  mov     [rsp+50h+var_28], rax
0x1800909fb  call    ?SampCreateAccountContext@@YAJW4_SAMP_OBJECT_TYPE@@KEEEPEAPEAU_SAMP_OBJECT@@@Z; SampCreateAccountContext(_SAMP_OBJECT_TYPE,ulong,uchar,uchar,uchar,_SAMP_OBJECT * *)
0x180090a00  mov     ebx, eax
0x180090a02  test    eax, eax
0x180090a04  jns     short loc_180090A3A
0x180090a06  mov     rcx, cs:WPP_GLOBAL_Control
0x180090a0d  test    dword ptr [rcx+44h], 400h
0x180090a14  jz      short loc_180090A34
0x180090a16  cmp     byte ptr [rcx+41h], 2
0x180090a1a  jb      short loc_180090A34
0x180090a1c  mov     rcx, [rcx+38h]
0x180090a20  lea     r8, WPP_93028685eca730797a8a21ecee3f4be1_Traceguids
0x180090a27  mov     edx, 3Bh ; ';'
0x180090a2c  mov     r9d, eax
0x180090a2f  call    WPP_SF_d
0x180090a34  mov     rdi, [rbp+arg_18]
0x180090a38  jmp     short loc_180090A9B
0x180090a3a  mov     rdi, [rbp+arg_18]
0x180090a3e  lea     r8, [rbp+var_18]; void **
0x180090a42  mov     rcx, rdi; struct _SAMP_OBJECT *
0x180090a45  lea     rdx, [rbp+var_20]; void **
0x180090a49  call    ?SampQueryShadowAccountLinks@@YAJPEAU_SAMP_OBJECT@@PEAPEAX1@Z; SampQueryShadowAccountLinks(_SAMP_OBJECT *,void * *,void * *)
0x180090a4e  mov     ebx, eax
0x180090a50  test    eax, eax
0x180090a52  jns     short loc_180090A8C
0x180090a54  mov     rcx, cs:WPP_GLOBAL_Control
0x180090a5b  test    dword ptr [rcx+44h], 400h
0x180090a62  jz      short loc_180090A82
0x180090a64  cmp     byte ptr [rcx+41h], 2
0x180090a68  jb      short loc_180090A82
0x180090a6a  mov     rcx, [rcx+38h]
0x180090a6e  lea     r8, WPP_93028685eca730797a8a21ecee3f4be1_Traceguids
0x180090a75  mov     edx, 3Ch ; '<'
0x180090a7a  mov     r9d, eax
0x180090a7d  call    WPP_SF_d
0x180090a82  mov     rsi, [rbp+var_20]
0x180090a86  mov     r14, [rbp+var_18]
0x180090a8a  jmp     short loc_180090A9B
0x180090a8c  mov     rax, [rbp+var_20]
0x180090a90  mov     [r12], rax
0x180090a94  mov     rax, [rbp+var_18]
0x180090a98  mov     [r15], rax
0x180090a9b  mov     rcx, rsi; hMem
0x180090a9e  call    cs:__imp_LocalFree
0x180090aa4  mov     rcx, r14; hMem
0x180090aa7  call    cs:__imp_LocalFree
0x180090aad  cmp     [rbp+arg_10], 0
0x180090ab1  jz      short loc_180090AB8
0x180090ab3  call    SampReleaseReadLock
0x180090ab8  test    rdi, rdi
0x180090abb  jz      short loc_180090AC5
0x180090abd  mov     rcx, rdi; HandleId
0x180090ac0  call    SampDeleteContext
0x180090ac5  mov     rcx, [rbp+Sid1]; hMem
0x180090ac9  call    cs:__imp_LocalFree
0x180090acf  mov     rcx, cs:WPP_GLOBAL_Control
0x180090ad6  test    dword ptr [rcx+44h], 20000h
0x180090add  jz      short loc_180090AFB
0x180090adf  mov     rcx, [rcx+38h]
0x180090ae3  lea     r8, WPP_93028685eca730797a8a21ecee3f4be1_Traceguids
0x180090aea  mov     edx, 3Dh ; '='
0x180090aef  mov     dword ptr [rsp+50h+var_30], ebx
0x180090af3  mov     r9d, ebx
0x180090af6  call    WPP_SF_Dd
0x180090afb  mov     eax, ebx
0x180090afd  mov     rbx, [rsp+50h+arg_0]
0x180090b05  add     rsp, 50h
0x180090b09  pop     r15
0x180090b0b  pop     r14
0x180090b0d  pop     r13
0x180090b0f  pop     r12
0x180090b11  pop     rdi
0x180090b12  pop     rsi
0x180090b13  pop     rbp
0x180090b14  retn
```
