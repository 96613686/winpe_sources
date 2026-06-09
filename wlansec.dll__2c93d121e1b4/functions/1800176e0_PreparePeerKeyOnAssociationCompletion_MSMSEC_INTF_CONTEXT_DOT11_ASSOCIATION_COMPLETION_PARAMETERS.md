# PreparePeerKeyOnAssociationCompletion(MSMSEC_INTF_CONTEXT *,DOT11_ASSOCIATION_COMPLETION_PARAMETERS *)

- ea: `0x1800176e0`
- end: `0x180017aa7`
- name: `?PreparePeerKeyOnAssociationCompletion@@YAXPEAUMSMSEC_INTF_CONTEXT@@PEAUDOT11_ASSOCIATION_COMPLETION_PARAMETERS@@@Z`
- size: `967`
- prototype: `void(struct MSMSEC_INTF_CONTEXT *, struct DOT11_ASSOCIATION_COMPLETION_PARAMETERS *)`
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x180015600`

## callees

- `0x18000892c`
- `0x180008998`
- `0x18000c730`
- `0x18000e620`
- `0x1800169c0`
- `0x1800176e0`
- `0x180021fd0`
- `0x180043a30`
- `0x1800583b8`
- `0x180058534`
- `0x180096010`

## import_xrefs

- `MobileNetworking!ReleaseWriteLock` at `0x1800178fb`
- `MobileNetworking!ReleaseWriteLock` at `0x1800178fb`
- `MobileNetworking!AcquireWriteLock` at `0x1800179be`
- `MobileNetworking!AcquireWriteLock` at `0x1800179f1`
- `MobileNetworking!AcquireWriteLock` at `0x1800179be`
- `MobileNetworking!AcquireWriteLock` at `0x1800179f1`

## string_xrefs

- `0x1800178f1`: `PreparePeerKeyOnAssociationCompletion`
- `0x1800179b1`: `PreparePeerKeyOnAssociationCompletion`
- `0x1800179e4`: `PreparePeerKeyOnAssociationCompletion`

## pseudocode

```c
void __fastcall PreparePeerKeyOnAssociationCompletion(
        struct MSMSEC_INTF_CONTEXT *a1,
        struct DOT11_ASSOCIATION_COMPLETION_PARAMETERS *a2)
{
  PVOID *v4; // rcx
  unsigned int v5; // ebx
  __int64 *v6; // rsi
  unsigned int WFDDeviceAddressFromAssociationCompletion; // eax
  int v8; // ecx
  __int64 v9; // rdx
  unsigned int MSMSecMemory; // eax
  struct _AP_PEER_KEY *v11; // rsi
  __int64 v12; // rdx
  __int64 v13; // r9
  unsigned int v14; // eax
  _QWORD *v15; // rcx
  __int64 v16; // rdx
  __int64 v17; // r9
  _DWORD *v18; // [rsp+20h] [rbp-20h] BYREF
  struct _AP_PEER_KEY *v19; // [rsp+28h] [rbp-18h]
  unsigned __int8 v20[6]; // [rsp+30h] [rbp-10h] BYREF

  v19 = 0;
  v4 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 220, &WPP_ae01c481f8653c6245af2cd9b1c5a1a2_Traceguids);
    v4 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( a1 && a2 )
  {
    v5 = 0;
    if ( *((_DWORD *)a1 + 694) != 32 )
      goto LABEL_7;
    v6 = (__int64 *)*((_QWORD *)a1 + 338);
    if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 68) & 2) != 0 )
      WPP_SF_(v4[7], 222, &WPP_ae01c481f8653c6245af2cd9b1c5a1a2_Traceguids);
    WFDDeviceAddressFromAssociationCompletion = GetWFDDeviceAddressFromAssociationCompletion(
                                                  a2,
                                                  (unsigned __int8 (*)[6])v20);
    v5 = WFDDeviceAddressFromAssociationCompletion;
    if ( WFDDeviceAddressFromAssociationCompletion )
    {
      v4 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
      {
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
          goto LABEL_7;
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 7),
          223,
          &WPP_ae01c481f8653c6245af2cd9b1c5a1a2_Traceguids,
          WFDDeviceAddressFromAssociationCompletion);
LABEL_53:
        v4 = (PVOID *)WPP_GLOBAL_Control;
        goto LABEL_7;
      }
      return;
    }
    while ( v6 != (__int64 *)((char *)a1 + 2704) )
    {
      v8 = *((_DWORD *)v6 + 4) - *(_DWORD *)v20;
      if ( !v8 )
        v8 = *((unsigned __int16 *)v6 + 10) - *(unsigned __int16 *)&v20[4];
      if ( !v8 )
      {
        v4 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
          return;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 2) != 0 )
        {
          v9 = 224;
          goto LABEL_52;
        }
        goto LABEL_7;
      }
      v6 = (__int64 *)*v6;
    }
    v18 = 0;
    MSMSecMemory = AllocateMSMSecMemory(0x30u);
    v11 = v19;
    v5 = MSMSecMemory;
    if ( MSMSecMemory )
    {
      v4 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
        goto LABEL_7;
      v12 = 225;
      v13 = MSMSecMemory;
LABEL_46:
      WPP_SF_d(v4[7], v12, &WPP_ae01c481f8653c6245af2cd9b1c5a1a2_Traceguids, v13);
      goto LABEL_47;
    }
    *((_DWORD *)v19 + 4) = *(_DWORD *)v20;
    *((_WORD *)v11 + 10) = *(_WORD *)&v20[4];
    *((_DWORD *)v11 + 6) |= 2u;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 2) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 226, &WPP_ae01c481f8653c6245af2cd9b1c5a1a2_Traceguids);
    TraceAdapterId(*((_DWORD *)a1 + 624), "<<< Unlocking <<<");
    ReleaseWriteLock(a1, (char *)a1 + 2512, "PreparePeerKeyOnAssociationCompletion", 3372);
    v14 = (*((__int64 (__fastcall **)(_QWORD, unsigned __int8 *, _DWORD **))a1 + 288))(*((_QWORD *)a1 + 3), v20, &v18);
    v5 = v14;
    if ( v14 )
    {
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
        goto LABEL_41;
      v16 = 227;
      v17 = v14;
    }
    else
    {
      v5 = CopyKey((*v18 >> 1) & 1, v18 + 2, (char *)v11 + 32);
      (*((void (__fastcall **)(_QWORD, _DWORD *))a1 + 289))(*((_QWORD *)a1 + 3), v18);
      if ( !v5 )
      {
        TraceAdapterId(*((_DWORD *)a1 + 624), ">>> Locking >>>");
        AcquireWriteLock(a1, (char *)a1 + 2512, "PreparePeerKeyOnAssociationCompletion", 3384);
        if ( InsertIntoPeerKeyList(v11, (struct _LIST_ENTRY *)a1 + 169, (unsigned int *)a1 + 680) )
          goto LABEL_53;
        v5 = 5023;
        v4 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
        {
LABEL_7:
          if ( v4 != &WPP_GLOBAL_Control && (*((_DWORD *)v4 + 17) & 0x100) != 0 )
            WPP_SF_d(v4[7], 230, &WPP_ae01c481f8653c6245af2cd9b1c5a1a2_Traceguids, v5);
          return;
        }
        v12 = 229;
        v13 = 5023;
        goto LABEL_46;
      }
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
      {
LABEL_41:
        TraceAdapterId(*((_DWORD *)a1 + 624), ">>> Locking >>>");
        AcquireWriteLock(a1, (char *)a1 + 2512, "PreparePeerKeyOnAssociationCompletion", 3400);
LABEL_47:
        v4 = (PVOID *)WPP_GLOBAL_Control;
        goto LABEL_7;
      }
      v16 = 228;
      v17 = v5;
    }
    WPP_SF_d(v15[7], v16, &WPP_ae01c481f8653c6245af2cd9b1c5a1a2_Traceguids, v17);
    goto LABEL_41;
  }
  if ( v4 != &WPP_GLOBAL_Control )
  {
    v5 = 87;
    if ( (*((_BYTE *)v4 + 68) & 1) == 0 )
      goto LABEL_7;
    v9 = 221;
LABEL_52:
    WPP_SF_(v4[7], v9, &WPP_ae01c481f8653c6245af2cd9b1c5a1a2_Traceguids);
    goto LABEL_53;
  }
}

```

## disassembly

```asm
0x1800176e0  mov     [rsp-38h+arg_10], rbx
0x1800176e5  push    rbp
0x1800176e6  push    rsi
0x1800176e7  push    rdi
0x1800176e8  push    r12
0x1800176ea  push    r13
0x1800176ec  push    r14
0x1800176ee  push    r15
0x1800176f0  mov     rbp, rsp
0x1800176f3  sub     rsp, 40h
0x1800176f7  mov     rax, cs:__security_cookie
0x1800176fe  xor     rax, rsp
0x180017701  mov     [rbp+var_8], rax
0x180017705  mov     r14, rdx
0x180017708  mov     [rbp+var_18], 0
0x180017710  mov     rdi, rcx
0x180017713  mov     rcx, cs:WPP_GLOBAL_Control
0x18001771a  lea     r12, WPP_GLOBAL_Control
0x180017721  lea     r13, WPP_ae01c481f8653c6245af2cd9b1c5a1a2_Traceguids
0x180017728  cmp     rcx, r12
0x18001772b  jz      short loc_180017736
0x18001772d  test    dword ptr [rcx+44h], 100h
0x180017734  jnz     short loc_18001778A
0x180017736  test    rdi, rdi
0x180017739  jz      loc_180017A59
0x18001773f  test    r14, r14
0x180017742  jz      loc_180017A59
0x180017748  xor     ebx, ebx
0x18001774a  cmp     dword ptr [rdi+0AD8h], 20h ; ' '
0x180017751  jz      short loc_1800177A4
0x180017753  cmp     rcx, r12
0x180017756  jz      short loc_180017765
0x180017758  test    dword ptr [rcx+44h], 100h
0x18001775f  jnz     loc_180017A8E
0x180017765  mov     rcx, [rbp+var_8]
0x180017769  xor     rcx, rsp; StackCookie
0x18001776c  call    __security_check_cookie
0x180017771  mov     rbx, [rsp+40h+arg_10]
0x180017779  add     rsp, 40h
0x18001777d  pop     r15
0x18001777f  pop     r14
0x180017781  pop     r13
0x180017783  pop     r12
0x180017785  pop     rdi
0x180017786  pop     rsi
0x180017787  pop     rbp
0x180017788  retn
0x18001778a  mov     rcx, [rcx+38h]
0x18001778e  mov     edx, 0DCh
0x180017793  mov     r8, r13
0x180017796  call    WPP_SF_
0x18001779b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800177a2  jmp     short loc_180017736
0x1800177a4  lea     r15, [rdi+0A90h]
0x1800177ab  mov     rsi, [r15]
0x1800177ae  cmp     rcx, r12
0x1800177b1  jz      short loc_1800177CA
0x1800177b3  test    byte ptr [rcx+44h], 2
0x1800177b7  jz      short loc_1800177CA
0x1800177b9  mov     rcx, [rcx+38h]
0x1800177bd  mov     edx, 0DEh
0x1800177c2  mov     r8, r13
0x1800177c5  call    WPP_SF_
0x1800177ca  lea     rdx, [rbp+var_10]; unsigned __int8 (*)[6]
0x1800177ce  mov     rcx, r14; struct DOT11_ASSOCIATION_COMPLETION_PARAMETERS *
0x1800177d1  call    ?GetWFDDeviceAddressFromAssociationCompletion@@YAKPEAUDOT11_ASSOCIATION_COMPLETION_PARAMETERS@@PEAY05E@Z; GetWFDDeviceAddressFromAssociationCompletion(DOT11_ASSOCIATION_COMPLETION_PARAMETERS *,uchar (*)[6])
0x1800177d6  mov     ebx, eax
0x1800177d8  test    eax, eax
0x1800177da  jz      short loc_18001780F
0x1800177dc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800177e3  cmp     rcx, r12
0x1800177e6  jz      loc_180017765
0x1800177ec  test    byte ptr [rcx+44h], 1
0x1800177f0  jz      loc_180017753
0x1800177f6  mov     rcx, [rcx+38h]
0x1800177fa  mov     edx, 0DFh
0x1800177ff  mov     r9d, eax
0x180017802  mov     r8, r13
0x180017805  call    WPP_SF_d
0x18001780a  jmp     loc_180017A82
0x18001780f  cmp     rsi, r15
0x180017812  jz      short loc_180017853
0x180017814  mov     ecx, [rsi+10h]
0x180017817  sub     ecx, dword ptr [rbp+var_10]
0x18001781a  jnz     short loc_180017826
0x18001781c  movzx   ecx, word ptr [rsi+14h]
0x180017820  movzx   eax, word ptr [rbp+var_10+4]
0x180017824  sub     ecx, eax
0x180017826  test    ecx, ecx
0x180017828  jz      short loc_18001782F
0x18001782a  mov     rsi, [rsi]
0x18001782d  jmp     short loc_18001780F
0x18001782f  mov     rcx, cs:WPP_GLOBAL_Control
0x180017836  cmp     rcx, r12
0x180017839  jz      loc_180017765
0x18001783f  test    byte ptr [rcx+44h], 2
0x180017843  jz      loc_180017753
0x180017849  mov     edx, 0E0h
0x18001784e  jmp     loc_180017A76
0x180017853  lea     rdx, [rbp+var_18]
0x180017857  mov     [rbp+var_20], 0
0x18001785f  mov     ecx, 30h ; '0'; dwBytes
0x180017864  call    AllocateMSMSecMemory
0x180017869  mov     rsi, [rbp+var_18]
0x18001786d  mov     ebx, eax
0x18001786f  test    eax, eax
0x180017871  jz      short loc_18001789A
0x180017873  mov     rcx, cs:WPP_GLOBAL_Control
0x18001787a  cmp     rcx, r12
0x18001787d  jz      loc_180017A45
0x180017883  test    byte ptr [rcx+44h], 1
0x180017887  jz      loc_180017A45
0x18001788d  mov     edx, 0E1h
0x180017892  mov     r9d, eax
0x180017895  jmp     loc_180017A32
0x18001789a  mov     eax, dword ptr [rbp+var_10]
0x18001789d  mov     [rsi+10h], eax
0x1800178a0  movzx   eax, word ptr [rbp+var_10+4]
0x1800178a4  mov     [rsi+14h], ax
0x1800178a8  or      dword ptr [rsi+18h], 2
0x1800178ac  mov     rcx, cs:WPP_GLOBAL_Control
0x1800178b3  cmp     rcx, r12
0x1800178b6  jz      short loc_1800178CF
0x1800178b8  test    byte ptr [rcx+44h], 2
0x1800178bc  jz      short loc_1800178CF
0x1800178be  mov     rcx, [rcx+38h]
0x1800178c2  mov     edx, 0E2h
0x1800178c7  mov     r8, r13
0x1800178ca  call    WPP_SF_
0x1800178cf  mov     ecx, [rdi+9C0h]; unsigned int
0x1800178d5  lea     rdx, aUnlocking; "<<< Unlocking <<<"
0x1800178dc  call    ?TraceAdapterId@@YAXKPEBD@Z; TraceAdapterId(ulong,char const *)
0x1800178e1  lea     r14, [rdi+9D0h]
0x1800178e8  mov     r9d, 0D2Ch
0x1800178ee  mov     rdx, r14
0x1800178f1  lea     r8, aPreparepeerkey; "PreparePeerKeyOnAssociationCompletion"
0x1800178f8  mov     rcx, rdi
0x1800178fb  call    cs:__imp_ReleaseWriteLock
0x180017902  nop     dword ptr [rax+rax+00h]
0x180017907  mov     rcx, [rdi+18h]
0x18001790b  lea     r8, [rbp+var_20]
0x18001790f  mov     rax, [rdi+900h]
0x180017916  lea     rdx, [rbp+var_10]
0x18001791a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001791f  mov     ebx, eax
0x180017921  test    eax, eax
0x180017923  jz      short loc_180017941
0x180017925  mov     rcx, cs:WPP_GLOBAL_Control
0x18001792c  cmp     rcx, r12
0x18001792f  jz      short loc_180017999
0x180017931  test    byte ptr [rcx+44h], 1
0x180017935  jz      short loc_180017999
0x180017937  mov     edx, 0E3h
0x18001793c  mov     r9d, eax
0x18001793f  jmp     short loc_18001798D
0x180017941  mov     rax, [rbp+var_20]
0x180017945  lea     r8, [rsi+20h]
0x180017949  mov     ecx, [rax]
0x18001794b  lea     rdx, [rax+8]
0x18001794f  shr     ecx, 1
0x180017951  and     ecx, 1
0x180017954  call    CopyKey
0x180017959  mov     rdx, [rbp+var_20]
0x18001795d  mov     ebx, eax
0x18001795f  mov     rax, [rdi+908h]
0x180017966  mov     rcx, [rdi+18h]
0x18001796a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001796f  test    ebx, ebx
0x180017971  jz      short loc_1800179CC
0x180017973  mov     rcx, cs:WPP_GLOBAL_Control
0x18001797a  cmp     rcx, r12
0x18001797d  jz      short loc_180017999
0x18001797f  test    byte ptr [rcx+44h], 1
0x180017983  jz      short loc_180017999
0x180017985  mov     edx, 0E4h
0x18001798a  mov     r9d, ebx
0x18001798d  mov     rcx, [rcx+38h]
0x180017991  mov     r8, r13
0x180017994  call    WPP_SF_d
0x180017999  mov     ecx, [rdi+9C0h]; unsigned int
0x18001799f  lea     rdx, aLocking; ">>> Locking >>>"
0x1800179a6  call    ?TraceAdapterId@@YAXKPEBD@Z; TraceAdapterId(ulong,char const *)
0x1800179ab  mov     r9d, 0D48h
0x1800179b1  lea     r8, aPreparepeerkey; "PreparePeerKeyOnAssociationCompletion"
0x1800179b8  mov     rdx, r14
0x1800179bb  mov     rcx, rdi
0x1800179be  call    cs:__imp_AcquireWriteLock
0x1800179c5  nop     dword ptr [rax+rax+00h]
0x1800179ca  jmp     short loc_180017A3E
0x1800179cc  mov     ecx, [rdi+9C0h]; unsigned int
0x1800179d2  lea     rdx, aLocking; ">>> Locking >>>"
0x1800179d9  call    ?TraceAdapterId@@YAXKPEBD@Z; TraceAdapterId(ulong,char const *)
0x1800179de  mov     r9d, 0D38h
0x1800179e4  lea     r8, aPreparepeerkey; "PreparePeerKeyOnAssociationCompletion"
0x1800179eb  mov     rdx, r14
0x1800179ee  mov     rcx, rdi
0x1800179f1  call    cs:__imp_AcquireWriteLock
0x1800179f8  nop     dword ptr [rax+rax+00h]
0x1800179fd  lea     r8, [rdi+0AA0h]; unsigned int *
0x180017a04  mov     rdx, r15; struct _LIST_ENTRY *
0x180017a07  mov     rcx, rsi; struct _AP_PEER_KEY *
0x180017a0a  call    ?InsertIntoPeerKeyList@@YA_NPEAU_AP_PEER_KEY@@PEAU_LIST_ENTRY@@AEAK@Z; InsertIntoPeerKeyList(_AP_PEER_KEY *,_LIST_ENTRY *,ulong &)
0x180017a0f  test    al, al
0x180017a11  jnz     short loc_180017A82
0x180017a13  mov     ebx, 139Fh
0x180017a18  mov     rcx, cs:WPP_GLOBAL_Control
0x180017a1f  cmp     rcx, r12
0x180017a22  jz      short loc_180017A45
0x180017a24  test    byte ptr [rcx+44h], 1
0x180017a28  jz      short loc_180017A45
0x180017a2a  mov     edx, 0E5h
0x180017a2f  mov     r9d, ebx
0x180017a32  mov     rcx, [rcx+38h]
0x180017a36  mov     r8, r13
0x180017a39  call    WPP_SF_d
0x180017a3e  mov     rcx, cs:WPP_GLOBAL_Control
0x180017a45  test    rsi, rsi
0x180017a48  jz      loc_180017753
0x180017a4e  lea     rcx, [rbp+var_18]
0x180017a52  call    FreeMSMSecMemory
0x180017a57  jmp     short loc_180017A82
0x180017a59  cmp     rcx, r12
0x180017a5c  jz      loc_180017765
0x180017a62  test    byte ptr [rcx+44h], 1
0x180017a66  mov     ebx, 57h ; 'W'
0x180017a6b  jz      loc_180017753
0x180017a71  mov     edx, 0DDh
0x180017a76  mov     rcx, [rcx+38h]
0x180017a7a  mov     r8, r13
0x180017a7d  call    WPP_SF_
0x180017a82  mov     rcx, cs:WPP_GLOBAL_Control
0x180017a89  jmp     loc_180017753
0x180017a8e  mov     rcx, [rcx+38h]
0x180017a92  mov     edx, 0E6h
0x180017a97  mov     r9d, ebx
0x180017a9a  mov     r8, r13
0x180017a9d  call    WPP_SF_d
0x180017aa2  jmp     loc_180017765
```
