# SampIncrementActiveContextCount(_SAMP_OBJECT *)

- ea: `0x18001e900`
- end: `0x18001eb5a`
- name: `?SampIncrementActiveContextCount@@YAJPEAU_SAMP_OBJECT@@@Z`
- size: `602`
- prototype: `__int64 __fastcall(struct _SAMP_OBJECT *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180006800`

## callees

- `0x18001ce50`
- `0x18001e900`
- `0x180025b1c`
- `0x180027e24`
- `0x18004e28c`
- `0x1800bb788`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x18001eaef`
- `ntdll!RtlLeaveCriticalSection` at `0x18001eaef`
- `ntdll!RtlEnterCriticalSection` at `0x18001ea88`
- `ntdll!RtlEnterCriticalSection` at `0x18001ea88`
- `ntdll!RtlLengthSid` at `0x18001e994`
- `ntdll!RtlLengthSid` at `0x18001e994`
- `ntdll!RtlEqualSid` at `0x18001ea2a`
- `ntdll!RtlEqualSid` at `0x18001ea51`
- `ntdll!RtlEqualSid` at `0x18001ea2a`
- `ntdll!RtlEqualSid` at `0x18001ea51`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001e9a4`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001e9a4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001e9d4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001eb09`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001eb17`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001e9d4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001eb09`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001eb17`
- `LSASRV!LsaIRetrieveCurrentUserSid` at `0x18001e940`
- `LSASRV!LsaIRetrieveCurrentUserSid` at `0x18001e940`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x18001e9e6`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x18001e9e6`

## pseudocode

```c
__int64 __fastcall SampIncrementActiveContextCount(struct _SAMP_OBJECT *a1)
{
  struct SAMP_ACTIVE_CONTEXT_TABLE_ELEMENT *v2; // r15
  struct _TOKEN_USER *v3; // rdi
  int v4; // esi
  void *v5; // rbp
  int active; // ebx
  int CurrentUser; // eax
  SIZE_T v8; // r12
  HLOCAL v9; // rax
  __int64 v10; // rax
  __int64 v11; // rcx
  unsigned int v12; // eax
  struct SAMP_ACTIVE_CONTEXT_TABLE_ELEMENT *v14; // [rsp+30h] [rbp-48h] BYREF
  int v15; // [rsp+88h] [rbp+10h] BYREF
  PSID Sid; // [rsp+90h] [rbp+18h] BYREF
  struct _TOKEN_USER *v17; // [rsp+98h] [rbp+20h] BYREF

  *((_QWORD *)a1 + 23) = 0;
  v14 = 0;
  v2 = 0;
  Sid = 0;
  v3 = 0;
  v17 = 0;
  v4 = 1;
  v5 = 0;
  active = LsaIRetrieveCurrentUserSid(&Sid);
  if ( active < 0 )
  {
    v15 = 0;
    CurrentUser = SampGetCurrentUser(0, &v17, &v15);
    v3 = v17;
    active = CurrentUser;
    if ( CurrentUser >= 0 )
    {
      v4 = 0;
      Sid = v17->User.Sid;
    }
  }
  if ( Sid )
  {
    v8 = RtlLengthSid(Sid);
    v9 = LocalAlloc(0x40u, v8);
    v5 = v9;
    if ( v9 )
      memcpy_0(v9, Sid, v8);
    else
      active = -1073741670;
  }
  if ( v3 )
    LocalFree(v3);
  if ( v4 )
    LsaFreeMemory(Sid);
  if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
    WPP_SF_Dd(
      WPP_GLOBAL_Control[3].Buffer,
      75,
      WPP_5505de3e48bd33375e96ca021b170945_Traceguids,
      (unsigned int)active,
      active);
  if ( active >= 0 )
  {
    if ( RtlEqualSid(v5, SampLocalSystemSid) )
    {
      *((_QWORD *)a1 + 23) = &LocalSystemContextTableElement;
    }
    else if ( RtlEqualSid(v5, SampAdministratorUserSid) )
    {
      *((_QWORD *)a1 + 23) = &AdministratorContextTableElement;
    }
    else
    {
      active = SampCreateActiveContextTableElement(v5, &v14);
      if ( active < 0 )
      {
        v2 = v14;
      }
      else
      {
        RtlEnterCriticalSection(&SampActiveContextTableLock);
        v2 = v14;
        v10 = SampLookupElementInTable((struct _RTL_GENERIC_TABLE2 *)&SampActiveContextTable, v14);
        v11 = v10;
        if ( v10 )
        {
          v12 = *(_DWORD *)(v10 + 8);
          if ( v12 < 0x800 )
          {
            *(_DWORD *)(v11 + 8) = v12 + 1;
            *((_QWORD *)a1 + 23) = v11;
          }
          else
          {
            active = -1073741670;
          }
        }
        else
        {
          active = -1073741670;
        }
        RtlLeaveCriticalSection(&SampActiveContextTableLock);
      }
    }
  }
  if ( v5 )
    LocalFree(v5);
  if ( v2 )
    LocalFree(v2);
  if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
    WPP_SF_Dd(
      WPP_GLOBAL_Control[3].Buffer,
      55,
      WPP_16cad3e18f1834c4d3a59fb2d3abb5df_Traceguids,
      (unsigned int)active,
      active);
  return (unsigned int)active;
}

```

## disassembly

```asm
0x18001e900  mov     rax, rsp
0x18001e903  push    rbx
0x18001e904  push    rbp
0x18001e905  push    rsi
0x18001e906  push    rdi
0x18001e907  push    r12
0x18001e909  push    r14
0x18001e90b  push    r15
0x18001e90d  sub     rsp, 40h
0x18001e911  xor     r12d, r12d
0x18001e914  mov     byte ptr [rax+8], 0
0x18001e918  mov     [rcx+0B8h], r12
0x18001e91f  mov     r14, rcx
0x18001e922  lea     rcx, [rax+18h]
0x18001e926  mov     [rax-48h], r12
0x18001e92a  mov     r15d, r12d
0x18001e92d  mov     [rax+18h], r12
0x18001e931  mov     edi, r12d
0x18001e934  mov     [rax+20h], r12
0x18001e938  mov     esi, 1
0x18001e93d  mov     ebp, r12d
0x18001e940  call    cs:__imp_LsaIRetrieveCurrentUserSid
0x18001e946  mov     ebx, eax
0x18001e948  test    eax, eax
0x18001e94a  jns     short loc_18001E987
0x18001e94c  lea     r8, [rsp+78h+arg_8]; int *
0x18001e954  mov     [rsp+78h+arg_8], r12d
0x18001e95c  lea     rdx, [rsp+78h+arg_18]; struct _TOKEN_USER **
0x18001e964  xor     ecx, ecx; TokenHandle
0x18001e966  call    ?SampGetCurrentUser@@YAJPEAXPEAPEAU_TOKEN_USER@@PEAH@Z; SampGetCurrentUser(void *,_TOKEN_USER * *,int *)
0x18001e96b  mov     rdi, [rsp+78h+arg_18]
0x18001e973  mov     ebx, eax
0x18001e975  test    eax, eax
0x18001e977  js      short loc_18001E987
0x18001e979  mov     rax, [rdi]
0x18001e97c  mov     esi, r12d
0x18001e97f  mov     [rsp+78h+Sid], rax
0x18001e987  mov     rcx, [rsp+78h+Sid]; Sid
0x18001e98f  test    rcx, rcx
0x18001e992  jz      short loc_18001E9CC
0x18001e994  call    cs:__imp_RtlLengthSid
0x18001e99a  mov     edx, eax; uBytes
0x18001e99c  mov     ecx, 40h ; '@'; uFlags
0x18001e9a1  mov     r12d, eax
0x18001e9a4  call    cs:__imp_LocalAlloc
0x18001e9aa  mov     rbp, rax
0x18001e9ad  test    rax, rax
0x18001e9b0  jnz     short loc_18001E9B9
0x18001e9b2  mov     ebx, 0C000009Ah
0x18001e9b7  jmp     short loc_18001E9CC
0x18001e9b9  mov     rdx, [rsp+78h+Sid]; Src
0x18001e9c1  mov     r8, r12; Size
0x18001e9c4  mov     rcx, rax; void *
0x18001e9c7  call    memcpy_0
0x18001e9cc  test    rdi, rdi
0x18001e9cf  jz      short loc_18001E9DA
0x18001e9d1  mov     rcx, rdi; hMem
0x18001e9d4  call    cs:__imp_LocalFree
0x18001e9da  test    esi, esi
0x18001e9dc  jz      short loc_18001E9EC
0x18001e9de  mov     rcx, [rsp+78h+Sid]; Buffer
0x18001e9e6  call    cs:__imp_LsaFreeMemory
0x18001e9ec  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e9f3  test    dword ptr [rcx+44h], 20000h
0x18001e9fa  jz      short loc_18001EA18
0x18001e9fc  mov     rcx, [rcx+38h]
0x18001ea00  lea     r8, WPP_5505de3e48bd33375e96ca021b170945_Traceguids
0x18001ea07  mov     edx, 4Bh ; 'K'
0x18001ea0c  mov     [rsp+78h+var_58], ebx
0x18001ea10  mov     r9d, ebx
0x18001ea13  call    WPP_SF_Dd
0x18001ea18  test    ebx, ebx
0x18001ea1a  js      loc_18001EB01
0x18001ea20  mov     rdx, cs:SampLocalSystemSid; Sid2
0x18001ea27  mov     rcx, rbp; Sid1
0x18001ea2a  call    cs:__imp_RtlEqualSid
0x18001ea30  test    al, al
0x18001ea32  jz      short loc_18001EA47
0x18001ea34  lea     rax, ?LocalSystemContextTableElement@@3USAMP_ACTIVE_CONTEXT_TABLE_ELEMENT@@A; SAMP_ACTIVE_CONTEXT_TABLE_ELEMENT LocalSystemContextTableElement
0x18001ea3b  mov     [r14+0B8h], rax
0x18001ea42  jmp     loc_18001EB01
0x18001ea47  mov     rdx, cs:SampAdministratorUserSid; Sid2
0x18001ea4e  mov     rcx, rbp; Sid1
0x18001ea51  call    cs:__imp_RtlEqualSid
0x18001ea57  test    al, al
0x18001ea59  jz      short loc_18001EA6E
0x18001ea5b  lea     rax, ?AdministratorContextTableElement@@3USAMP_ACTIVE_CONTEXT_TABLE_ELEMENT@@A; SAMP_ACTIVE_CONTEXT_TABLE_ELEMENT AdministratorContextTableElement
0x18001ea62  mov     [r14+0B8h], rax
0x18001ea69  jmp     loc_18001EB01
0x18001ea6e  lea     rdx, [rsp+78h+var_48]; struct SAMP_ACTIVE_CONTEXT_TABLE_ELEMENT **
0x18001ea73  mov     rcx, rbp; void *
0x18001ea76  call    ?SampCreateActiveContextTableElement@@YAJPEAXPEAPEAUSAMP_ACTIVE_CONTEXT_TABLE_ELEMENT@@@Z; SampCreateActiveContextTableElement(void *,SAMP_ACTIVE_CONTEXT_TABLE_ELEMENT * *)
0x18001ea7b  mov     ebx, eax
0x18001ea7d  test    eax, eax
0x18001ea7f  js      short loc_18001EAFC
0x18001ea81  lea     rcx, ?SampActiveContextTableLock@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x18001ea88  call    cs:__imp_RtlEnterCriticalSection
0x18001ea8e  mov     r15, [rsp+78h+var_48]
0x18001ea93  lea     r9, [rsp+78h+arg_0]
0x18001ea9b  mov     r8d, cs:?SampMaxSamConnections@@3KA; ulong SampMaxSamConnections
0x18001eaa2  lea     rcx, ?SampActiveContextTable@@3U_RTL_GENERIC_TABLE2@@A; struct _RTL_GENERIC_TABLE2 *
0x18001eaa9  mov     rdx, r15; void *
0x18001eaac  call    SampLookupElementInTable
0x18001eab1  mov     rcx, rax
0x18001eab4  test    rax, rax
0x18001eab7  jnz     short loc_18001EAC3
0x18001eab9  mov     ebx, 0C000009Ah
0x18001eabe  xor     dil, dil
0x18001eac1  jmp     short loc_18001EAE8
0x18001eac3  mov     eax, [rax+8]
0x18001eac6  movzx   edi, [rsp+78h+arg_0]
0x18001eace  cmp     eax, 800h
0x18001ead3  jb      short loc_18001EADC
0x18001ead5  mov     ebx, 0C000009Ah
0x18001eada  jmp     short loc_18001EAE8
0x18001eadc  inc     eax
0x18001eade  mov     [rcx+8], eax
0x18001eae1  mov     [r14+0B8h], rcx
0x18001eae8  lea     rcx, ?SampActiveContextTableLock@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x18001eaef  call    cs:__imp_RtlLeaveCriticalSection
0x18001eaf5  test    dil, dil
0x18001eaf8  jz      short loc_18001EB01
0x18001eafa  jmp     short loc_18001EB1D
0x18001eafc  mov     r15, [rsp+78h+var_48]
0x18001eb01  test    rbp, rbp
0x18001eb04  jz      short loc_18001EB0F
0x18001eb06  mov     rcx, rbp; hMem
0x18001eb09  call    cs:__imp_LocalFree
0x18001eb0f  test    r15, r15
0x18001eb12  jz      short loc_18001EB1D
0x18001eb14  mov     rcx, r15; hMem
0x18001eb17  call    cs:__imp_LocalFree
0x18001eb1d  mov     rcx, cs:WPP_GLOBAL_Control
0x18001eb24  test    dword ptr [rcx+44h], 20000h
0x18001eb2b  jz      short loc_18001EB49
0x18001eb2d  mov     rcx, [rcx+38h]
0x18001eb31  lea     r8, WPP_16cad3e18f1834c4d3a59fb2d3abb5df_Traceguids
0x18001eb38  mov     edx, 37h ; '7'
0x18001eb3d  mov     [rsp+78h+var_58], ebx
0x18001eb41  mov     r9d, ebx
0x18001eb44  call    WPP_SF_Dd
0x18001eb49  mov     eax, ebx
0x18001eb4b  add     rsp, 40h
0x18001eb4f  pop     r15
0x18001eb51  pop     r14
0x18001eb53  pop     r12
0x18001eb55  pop     rdi
0x18001eb56  pop     rsi
0x18001eb57  pop     rbp
0x18001eb58  pop     rbx
0x18001eb59  retn
```
