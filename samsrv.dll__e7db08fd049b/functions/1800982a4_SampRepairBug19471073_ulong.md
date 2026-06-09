# SampRepairBug19471073(ulong)

- ea: `0x1800982a4`
- end: `0x1800985ea`
- name: `?SampRepairBug19471073@@YAJK@Z`
- size: `838`
- prototype: `__int64 __fastcall(unsigned int)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, loader_planting, installer_update`

## callers

- `0x180098c94`

## callees

- `0x1800066f0`
- `0x180024d6c`
- `0x1800270e0`
- `0x180027e24`
- `0x180027e70`
- `0x18002cd80`
- `0x180037284`
- `0x1800372ac`
- `0x18003cdc0`
- `0x180065b60`
- `0x1800982a4`
- `0x1800985f0`

## import_xrefs

- `ntdll!RtlSubAuthoritySid` at `0x18009838a`
- `ntdll!RtlSubAuthoritySid` at `0x18009838a`
- `ntdll!RtlInitializeSid` at `0x18009837f`
- `ntdll!RtlInitializeSid` at `0x18009837f`
- `ntdll!RtlFreeHeap` at `0x180098578`
- `ntdll!RtlFreeHeap` at `0x180098578`
- `ntdll!RtlAllocateHeap` at `0x18009835c`
- `ntdll!RtlAllocateHeap` at `0x18009835c`
- `ntdll!RtlLengthRequiredSid` at `0x180098344`
- `ntdll!RtlLengthRequiredSid` at `0x180098344`

## pseudocode

```c
__int64 __fastcall SampRepairBug19471073(unsigned int a1)
{
  __int64 v1; // r9
  PUNICODE_STRING v2; // rcx
  int v3; // ebx
  ULONG v4; // eax
  PVOID Heap; // rax
  void *v6; // r15
  __int64 v7; // rbp
  void *v8; // r8
  PUNICODE_STRING v9; // rcx
  int v10; // eax
  int v11; // eax
  __int64 Context; // rax
  struct _SAMP_OBJECT *v13; // rbp
  int v14; // ebx
  PUNICODE_STRING v15; // rcx
  int v17; // [rsp+30h] [rbp-58h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+34h] [rbp-54h] BYREF

  *(_DWORD *)IdentifierAuthority.Value = 0;
  v1 = a1;
  *(_WORD *)&IdentifierAuthority.Value[4] = 1280;
  if ( a1 < 0x10009 )
  {
    if ( (*(_BYTE *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 1) != 0 && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 4u )
      WPP_SF_d(WPP_GLOBAL_Control[3].Buffer, 38, WPP_e294cfc5e5043c283e392179ed50e6b7_Traceguids, a1);
    v4 = RtlLengthRequiredSid(1u);
    Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v4);
    v6 = Heap;
    if ( Heap )
    {
      RtlInitializeSid(Heap, &IdentifierAuthority, 1u);
      v7 = 0;
      *RtlSubAuthoritySid(v6, 0) = 32;
      v9 = WPP_GLOBAL_Control;
      while ( (unsigned int)v7 < 4 )
      {
        v10 = SampRepairBug19471073ForOneAlias(
                *((_QWORD *)SampDefinedDomains + 171),
                qword_1800D2E00[v7],
                v8,
                HIDWORD(qword_1800D2E00[v7]),
                *((PSID *)SampDefinedDomains + 171));
        v3 = 0;
        if ( v10 != -1073741487 )
          v3 = v10;
        if ( v3 < 0 )
        {
          if ( (*(_BYTE *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 1) != 0
            && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 2u )
          {
            WPP_SF_Dd(
              WPP_GLOBAL_Control[3].Buffer,
              39,
              WPP_e294cfc5e5043c283e392179ed50e6b7_Traceguids,
              LODWORD(qword_1800D2E00[v7]),
              v3);
          }
          goto LABEL_42;
        }
        v9 = WPP_GLOBAL_Control;
        if ( (*(_BYTE *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 1) != 0
          && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 4u )
        {
          WPP_SF_d(
            WPP_GLOBAL_Control[3].Buffer,
            40,
            WPP_e294cfc5e5043c283e392179ed50e6b7_Traceguids,
            LODWORD(qword_1800D2E00[v7]));
          v9 = WPP_GLOBAL_Control;
        }
        v7 = (unsigned int)(v7 + 1);
      }
      if ( (*(_BYTE *)(&v9[4].MaximumLength + 1) & 1) != 0 && HIBYTE(v9[4].Length) >= 4u )
        WPP_SF_(v9[3].Buffer, 41, WPP_e294cfc5e5043c283e392179ed50e6b7_Traceguids);
      v11 = SampAcquireWriteLock(*(_QWORD *)SampDefinedDomains);
      v3 = v11;
      if ( v11 >= 0 )
      {
        Context = SampCreateContext(0, 0, 1);
        v13 = (struct _SAMP_OBJECT *)Context;
        if ( Context )
        {
          *(_QWORD *)(Context + 152) = SampKey;
          v17 = 65545;
          v14 = SampSetFixedAttributes(Context, &v17);
          if ( v14 >= 0 )
            v14 = SampStoreObjectAttributes(v13);
          SampDeleteContext(v13);
        }
        else
        {
          v15 = WPP_GLOBAL_Control;
          if ( (*(_BYTE *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 1) != 0
            && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 2u )
          {
            WPP_SF_(WPP_GLOBAL_Control[3].Buffer, 43, WPP_e294cfc5e5043c283e392179ed50e6b7_Traceguids);
          }
          v14 = -1073741670;
        }
        LOBYTE(v15) = v14 >= 0;
        v3 = SampReleaseWriteLock(v15);
        if ( v3 >= 0
          && (*(_BYTE *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 1) != 0
          && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 4u )
        {
          WPP_SF_(WPP_GLOBAL_Control[3].Buffer, 44, WPP_e294cfc5e5043c283e392179ed50e6b7_Traceguids);
        }
      }
      else if ( (*(_BYTE *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 1) != 0
             && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 2u )
      {
        WPP_SF_d(WPP_GLOBAL_Control[3].Buffer, 42, WPP_e294cfc5e5043c283e392179ed50e6b7_Traceguids, (unsigned int)v11);
      }
LABEL_42:
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v6);
    }
    else
    {
      v3 = -1073741670;
    }
    v2 = WPP_GLOBAL_Control;
  }
  else
  {
    v2 = WPP_GLOBAL_Control;
    if ( (*(_BYTE *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 1) != 0 && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 4u )
    {
      WPP_SF_d(WPP_GLOBAL_Control[3].Buffer, 37, WPP_e294cfc5e5043c283e392179ed50e6b7_Traceguids, v1);
      v2 = WPP_GLOBAL_Control;
    }
    v3 = 0;
  }
  if ( (*(_BYTE *)(&v2[4].MaximumLength + 1) & 1) != 0 && HIBYTE(v2[4].Length) >= 4u )
  {
    WPP_SF_d(v2[3].Buffer, 45, WPP_e294cfc5e5043c283e392179ed50e6b7_Traceguids, (unsigned int)v3);
    v2 = WPP_GLOBAL_Control;
  }
  if ( (*(_DWORD *)(&v2[4].MaximumLength + 1) & 0x20000) != 0 )
    WPP_SF_Dd(v2[3].Buffer, 46, WPP_e294cfc5e5043c283e392179ed50e6b7_Traceguids, (unsigned int)v3, v3);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1800982a4  push    rbx
0x1800982a6  push    rbp
0x1800982a7  push    rsi
0x1800982a8  push    r13
0x1800982aa  push    r14
0x1800982ac  push    r15
0x1800982ae  sub     rsp, 58h
0x1800982b2  mov     rax, cs:__security_cookie
0x1800982b9  xor     rax, rsp
0x1800982bc  mov     [rsp+88h+var_48], rax
0x1800982c1  mov     dword ptr [rsp+88h+IdentifierAuthority.Value], 0
0x1800982c9  mov     r9d, ecx
0x1800982cc  mov     word ptr [rsp+88h+IdentifierAuthority.Value+4], 500h
0x1800982d3  cmp     ecx, 10009h
0x1800982d9  jb      short loc_180098314
0x1800982db  mov     rcx, cs:WPP_GLOBAL_Control
0x1800982e2  lea     rsi, WPP_e294cfc5e5043c283e392179ed50e6b7_Traceguids
0x1800982e9  test    byte ptr [rcx+44h], 1
0x1800982ed  jz      short loc_18009830D
0x1800982ef  cmp     byte ptr [rcx+41h], 4
0x1800982f3  jb      short loc_18009830D
0x1800982f5  mov     rcx, [rcx+38h]
0x1800982f9  mov     edx, 25h ; '%'
0x1800982fe  mov     r8, rsi
0x180098301  call    WPP_SF_d
0x180098306  mov     rcx, cs:WPP_GLOBAL_Control
0x18009830d  xor     ebx, ebx
0x18009830f  jmp     loc_180098585
0x180098314  mov     rcx, cs:WPP_GLOBAL_Control
0x18009831b  lea     rsi, WPP_e294cfc5e5043c283e392179ed50e6b7_Traceguids
0x180098322  test    byte ptr [rcx+44h], 1
0x180098326  jz      short loc_18009833F
0x180098328  cmp     byte ptr [rcx+41h], 4
0x18009832c  jb      short loc_18009833F
0x18009832e  mov     rcx, [rcx+38h]
0x180098332  mov     edx, 26h ; '&'
0x180098337  mov     r8, rsi
0x18009833a  call    WPP_SF_d
0x18009833f  mov     ecx, 1; SubAuthorityCount
0x180098344  call    cs:__imp_RtlLengthRequiredSid
0x18009834a  mov     rcx, gs:60h
0x180098353  xor     edx, edx; Flags
0x180098355  mov     r8d, eax; Size
0x180098358  mov     rcx, [rcx+30h]; HeapHandle
0x18009835c  call    cs:__imp_RtlAllocateHeap
0x180098362  mov     r15, rax
0x180098365  test    rax, rax
0x180098368  jnz     short loc_180098374
0x18009836a  mov     ebx, 0C000009Ah
0x18009836f  jmp     loc_18009857E
0x180098374  mov     r8b, 1; SubAuthorityCount
0x180098377  lea     rdx, [rsp+88h+IdentifierAuthority]; IdentifierAuthority
0x18009837c  mov     rcx, r15; Sid
0x18009837f  call    cs:__imp_RtlInitializeSid
0x180098385  xor     edx, edx; SubAuthority
0x180098387  mov     rcx, r15; Sid
0x18009838a  call    cs:__imp_RtlSubAuthoritySid
0x180098390  xor     ebp, ebp
0x180098392  lea     r13, qword_1800D2E00
0x180098399  mov     dword ptr [rax], 20h ; ' '
0x18009839f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800983a6  cmp     ebp, 4
0x1800983a9  jnb     loc_18009844D
0x1800983af  mov     rax, cs:?SampDefinedDomains@@3PEAU_PSAMP_DEFINED_DOMAINS@@EA; _PSAMP_DEFINED_DOMAINS * SampDefinedDomains
0x1800983b6  mov     r9d, [r13+rbp*8+4]; unsigned int
0x1800983bb  mov     edx, [r13+rbp*8+0]; unsigned int
0x1800983c0  mov     rcx, [rax+558h]; unsigned int
0x1800983c7  mov     [rsp+88h+SourceSid], rcx; SourceSid
0x1800983cc  call    ?SampRepairBug19471073ForOneAlias@@YAJKKPEAXK0@Z; SampRepairBug19471073ForOneAlias(ulong,ulong,void *,ulong,void *)
0x1800983d1  xor     ebx, ebx
0x1800983d3  cmp     eax, 0C0000151h
0x1800983d8  cmovnz  ebx, eax
0x1800983db  test    ebx, ebx
0x1800983dd  js      short loc_180098413
0x1800983df  mov     rcx, cs:WPP_GLOBAL_Control
0x1800983e6  test    byte ptr [rcx+44h], 1
0x1800983ea  jz      short loc_18009840F
0x1800983ec  cmp     byte ptr [rcx+41h], 4
0x1800983f0  jb      short loc_18009840F
0x1800983f2  mov     r9d, [r13+rbp*8+0]
0x1800983f7  mov     edx, 28h ; '('
0x1800983fc  mov     rcx, [rcx+38h]
0x180098400  mov     r8, rsi
0x180098403  call    WPP_SF_d
0x180098408  mov     rcx, cs:WPP_GLOBAL_Control
0x18009840f  inc     ebp
0x180098411  jmp     short loc_1800983A6
0x180098413  mov     rcx, cs:WPP_GLOBAL_Control
0x18009841a  test    byte ptr [rcx+44h], 1
0x18009841e  jz      loc_180098566
0x180098424  cmp     byte ptr [rcx+41h], 2
0x180098428  jb      loc_180098566
0x18009842e  mov     r9d, [r13+rbp*8+0]
0x180098433  mov     edx, 27h ; '''
0x180098438  mov     rcx, [rcx+38h]
0x18009843c  mov     r8, rsi
0x18009843f  mov     dword ptr [rsp+88h+SourceSid], ebx
0x180098443  call    WPP_SF_Dd
0x180098448  jmp     loc_180098566
0x18009844d  test    byte ptr [rcx+44h], 1
0x180098451  jz      short loc_18009846A
0x180098453  cmp     byte ptr [rcx+41h], 4
0x180098457  jb      short loc_18009846A
0x180098459  mov     rcx, [rcx+38h]
0x18009845d  mov     edx, 29h ; ')'
0x180098462  mov     r8, rsi
0x180098465  call    WPP_SF_
0x18009846a  mov     rcx, cs:?SampDefinedDomains@@3PEAU_PSAMP_DEFINED_DOMAINS@@EA; _PSAMP_DEFINED_DOMAINS * SampDefinedDomains
0x180098471  mov     rcx, [rcx]
0x180098474  call    SampAcquireWriteLock
0x180098479  mov     ebx, eax
0x18009847b  test    eax, eax
0x18009847d  jns     short loc_1800984B3
0x18009847f  mov     rcx, cs:WPP_GLOBAL_Control
0x180098486  test    byte ptr [rcx+44h], 1
0x18009848a  jz      loc_180098566
0x180098490  cmp     byte ptr [rcx+41h], 2
0x180098494  jb      loc_180098566
0x18009849a  mov     rcx, [rcx+38h]
0x18009849e  mov     edx, 2Ah ; '*'
0x1800984a3  mov     r9d, eax
0x1800984a6  mov     r8, rsi
0x1800984a9  call    WPP_SF_d
0x1800984ae  jmp     loc_180098566
0x1800984b3  mov     r8b, 1
0x1800984b6  xor     edx, edx
0x1800984b8  xor     ecx, ecx
0x1800984ba  call    ?SampCreateContext@@YAPEAU_SAMP_OBJECT@@W4_SAMP_OBJECT_TYPE@@KE@Z; SampCreateContext(_SAMP_OBJECT_TYPE,ulong,uchar)
0x1800984bf  mov     rbp, rax
0x1800984c2  test    rax, rax
0x1800984c5  jz      short loc_180098506
0x1800984c7  mov     rcx, cs:SampKey
0x1800984ce  lea     rdx, [rsp+88h+var_58]
0x1800984d3  mov     [rax+98h], rcx
0x1800984da  mov     rcx, rax
0x1800984dd  mov     [rsp+88h+var_58], 10009h
0x1800984e5  call    SampSetFixedAttributes
0x1800984ea  mov     ebx, eax
0x1800984ec  test    eax, eax
0x1800984ee  js      short loc_1800984FC
0x1800984f0  xor     edx, edx
0x1800984f2  mov     rcx, rbp; struct _SAMP_OBJECT *
0x1800984f5  call    SampStoreObjectAttributes
0x1800984fa  mov     ebx, eax
0x1800984fc  mov     rcx, rbp; HandleId
0x1800984ff  call    SampDeleteContext
0x180098504  jmp     short loc_18009852F
0x180098506  mov     rcx, cs:WPP_GLOBAL_Control
0x18009850d  test    byte ptr [rcx+44h], 1
0x180098511  jz      short loc_18009852A
0x180098513  cmp     byte ptr [rcx+41h], 2
0x180098517  jb      short loc_18009852A
0x180098519  mov     rcx, [rcx+38h]
0x18009851d  mov     edx, 2Bh ; '+'
0x180098522  mov     r8, rsi
0x180098525  call    WPP_SF_
0x18009852a  mov     ebx, 0C000009Ah
0x18009852f  shr     ebx, 1Fh
0x180098532  xor     bl, 1
0x180098535  mov     cl, bl
0x180098537  call    SampReleaseWriteLock
0x18009853c  mov     ebx, eax
0x18009853e  test    eax, eax
0x180098540  js      short loc_180098566
0x180098542  mov     rcx, cs:WPP_GLOBAL_Control
0x180098549  test    byte ptr [rcx+44h], 1
0x18009854d  jz      short loc_180098566
0x18009854f  cmp     byte ptr [rcx+41h], 4
0x180098553  jb      short loc_180098566
0x180098555  mov     rcx, [rcx+38h]
0x180098559  mov     edx, 2Ch ; ','
0x18009855e  mov     r8, rsi
0x180098561  call    WPP_SF_
0x180098566  mov     rcx, gs:60h
0x18009856f  mov     r8, r15; P
0x180098572  xor     edx, edx; Flags
0x180098574  mov     rcx, [rcx+30h]; HeapHandle
0x180098578  call    cs:__imp_RtlFreeHeap
0x18009857e  mov     rcx, cs:WPP_GLOBAL_Control
0x180098585  test    byte ptr [rcx+44h], 1
0x180098589  jz      short loc_1800985AC
0x18009858b  cmp     byte ptr [rcx+41h], 4
0x18009858f  jb      short loc_1800985AC
0x180098591  mov     rcx, [rcx+38h]
0x180098595  mov     edx, 2Dh ; '-'
0x18009859a  mov     r9d, ebx
0x18009859d  mov     r8, rsi
0x1800985a0  call    WPP_SF_d
0x1800985a5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800985ac  test    dword ptr [rcx+44h], 20000h
0x1800985b3  jz      short loc_1800985CD
0x1800985b5  mov     rcx, [rcx+38h]
0x1800985b9  mov     edx, 2Eh ; '.'
0x1800985be  mov     r9d, ebx
0x1800985c1  mov     dword ptr [rsp+88h+SourceSid], ebx
0x1800985c5  mov     r8, rsi
0x1800985c8  call    WPP_SF_Dd
0x1800985cd  mov     eax, ebx
0x1800985cf  mov     rcx, [rsp+88h+var_48]
0x1800985d4  xor     rcx, rsp; StackCookie
0x1800985d7  call    __security_check_cookie
0x1800985dc  add     rsp, 58h
0x1800985e0  pop     r15
0x1800985e2  pop     r14
0x1800985e4  pop     r13
0x1800985e6  pop     rsi
0x1800985e7  pop     rbp
0x1800985e8  pop     rbx
0x1800985e9  retn
```
