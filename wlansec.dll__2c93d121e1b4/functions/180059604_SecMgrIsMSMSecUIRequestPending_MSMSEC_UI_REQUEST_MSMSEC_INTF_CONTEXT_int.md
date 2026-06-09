# SecMgrIsMSMSecUIRequestPending(MSMSEC_UI_REQUEST *,MSMSEC_INTF_CONTEXT *,int *)

- ea: `0x180059604`
- end: `0x18005984b`
- name: `?SecMgrIsMSMSecUIRequestPending@@YAKPEAUMSMSEC_UI_REQUEST@@PEAUMSMSEC_INTF_CONTEXT@@PEAH@Z`
- size: `583`
- prototype: `unsigned int __fastcall(struct MSMSEC_UI_REQUEST *, struct MSMSEC_INTF_CONTEXT *, int *)`
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x1800533f0`

## callees

- `0x18000892c`
- `0x180008998`
- `0x18000a26c`
- `0x180014998`
- `0x1800169c0`
- `0x180016a08`
- `0x18001e6c0`
- `0x18001f35c`
- `0x1800558c0`
- `0x180059604`
- `0x18005a5dc`

## import_xrefs

- `MobileNetworking!ReleaseWriteLock` at `0x1800597fe`
- `MobileNetworking!ReleaseWriteLock` at `0x1800597fe`
- `MobileNetworking!AcquireWriteLock` at `0x18005967b`
- `MobileNetworking!AcquireWriteLock` at `0x18005967b`

## pseudocode

```c
__int64 __fastcall SecMgrIsMSMSecUIRequestPending(
        struct MSMSEC_UI_REQUEST *a1,
        struct MSMSEC_INTF_CONTEXT *a2,
        int *a3)
{
  __int64 v6; // rdx
  int valid; // ebp
  __int64 v8; // r8
  __int64 v9; // r9
  unsigned int v10; // esi
  unsigned int v11; // r15d
  PVOID *v12; // r11
  __int64 v13; // rax
  unsigned int v14; // r10d
  __int64 v15; // rdx
  int v16; // eax
  __int64 v17; // r11
  __int64 v18; // r8
  char v19; // r10
  _DWORD *v20; // r14
  __int64 v21; // r8
  unsigned int *v22; // rax
  unsigned int v23; // edi
  int v24; // eax
  __int64 v25; // rax
  __int64 v26; // r11
  int v27; // edx
  int v28; // r8d
  char v29; // r10

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 136, &WPP_ae01c481f8653c6245af2cd9b1c5a1a2_Traceguids);
  TraceAdapterId(*((_DWORD *)a2 + 624), ">>> Locking >>>");
  AcquireWriteLock(a2, (char *)a2 + 2512, "SecMgrIsMSMSecUIRequestPending", 2161);
  valid = IsValidIntfSecStateForAction(*((unsigned int *)a2 + 681), 8);
  if ( !valid )
  {
    v10 = 1;
    LOBYTE(v11) = 0;
    v12 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 2) != 0 )
    {
      v13 = IntfActionStr(8, v6, v8, v9);
      v16 = IntfSecStateStr(v14, v15, v13);
      WPP_SF_SLSL(
        *(_QWORD *)(v17 + 56),
        137,
        (unsigned int)&WPP_ae01c481f8653c6245af2cd9b1c5a1a2_Traceguids,
        v16,
        v19,
        v18,
        8);
      v12 = (PVOID *)WPP_GLOBAL_Control;
    }
    v20 = (_DWORD *)((char *)a1 + 4);
    goto LABEL_17;
  }
  v21 = *((_QWORD *)a2 + 348);
  v20 = (_DWORD *)((char *)a1 + 4);
  v22 = *(unsigned int **)(v21 + 24);
  v10 = *v22;
  v11 = v22[1];
  if ( *v20 == 1 )
  {
    v24 = AuthCipher1xRequiresWEPKey(v10, v11, *(unsigned int *)(v21 + 32));
    goto LABEL_16;
  }
  if ( *v20 == 2 )
  {
    v24 = AuthCipher1xRequiresPSK(v10);
LABEL_16:
    v12 = (PVOID *)WPP_GLOBAL_Control;
    valid &= v24;
LABEL_17:
    v23 = 0;
    *a3 = valid;
    if ( v12 != &WPP_GLOBAL_Control && (*((_BYTE *)v12 + 68) & 2) != 0 )
    {
      v25 = IntfSecStateStr(*((unsigned int *)a2 + 681), v6, v8);
      WPP_SF_LLSLLL(*(_QWORD *)(v26 + 56), v27, v28, v10, v11, v25, v29, *v20, valid);
    }
    goto LABEL_20;
  }
  v23 = 87;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 7),
      138,
      &WPP_ae01c481f8653c6245af2cd9b1c5a1a2_Traceguids,
      (unsigned int)*v20);
LABEL_20:
  TraceAdapterId(*((_DWORD *)a2 + 624), "<<< Unlocking <<<");
  ReleaseWriteLock(a2, (char *)a2 + 2512, "SecMgrIsMSMSecUIRequestPending", 2218);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 140, &WPP_ae01c481f8653c6245af2cd9b1c5a1a2_Traceguids, v23);
  return v23;
}

```

## disassembly

```asm
0x180059604  push    rbx
0x180059606  push    rbp
0x180059607  push    rsi
0x180059608  push    rdi
0x180059609  push    r12
0x18005960b  push    r13
0x18005960d  push    r14
0x18005960f  push    r15
0x180059611  sub     rsp, 58h
0x180059615  mov     r12, r8
0x180059618  mov     rbx, rdx
0x18005961b  mov     r14, rcx
0x18005961e  mov     rcx, cs:WPP_GLOBAL_Control
0x180059625  lea     rdi, WPP_GLOBAL_Control
0x18005962c  cmp     rcx, rdi
0x18005962f  jz      short loc_18005964F
0x180059631  test    dword ptr [rcx+44h], 100h
0x180059638  jz      short loc_18005964F
0x18005963a  mov     rcx, [rcx+38h]
0x18005963e  lea     r8, WPP_ae01c481f8653c6245af2cd9b1c5a1a2_Traceguids
0x180059645  mov     edx, 88h
0x18005964a  call    WPP_SF_
0x18005964f  mov     ecx, [rbx+9C0h]; unsigned int
0x180059655  lea     rdx, aLocking; ">>> Locking >>>"
0x18005965c  call    ?TraceAdapterId@@YAXKPEBD@Z; TraceAdapterId(ulong,char const *)
0x180059661  lea     r13, [rbx+9D0h]
0x180059668  mov     r9d, 871h
0x18005966e  mov     rdx, r13
0x180059671  lea     r8, aSecmgrismsmsec; "SecMgrIsMSMSecUIRequestPending"
0x180059678  mov     rcx, rbx
0x18005967b  call    cs:__imp_AcquireWriteLock
0x180059682  nop     dword ptr [rax+rax+00h]
0x180059687  mov     ecx, [rbx+0AA4h]
0x18005968d  mov     edx, 8
0x180059692  call    ?IsValidIntfSecStateForAction@@YAHW4MSMSEC_INTF_SEC_STATE@@W4SECMGR_INTF_ACTION@@@Z; IsValidIntfSecStateForAction(MSMSEC_INTF_SEC_STATE,SECMGR_INTF_ACTION)
0x180059697  mov     ebp, eax
0x180059699  test    eax, eax
0x18005969b  jnz     short loc_180059708
0x18005969d  lea     esi, [rax+1]
0x1800596a0  xor     r15d, r15d
0x1800596a3  mov     r11, cs:WPP_GLOBAL_Control
0x1800596aa  cmp     r11, rdi
0x1800596ad  jz      short loc_1800596FF
0x1800596af  test    byte ptr [r11+44h], 2
0x1800596b4  jz      short loc_1800596FF
0x1800596b6  mov     r10d, [rbx+0AA4h]
0x1800596bd  lea     edi, [rax+8]
0x1800596c0  mov     ecx, edi
0x1800596c2  call    ?IntfActionStr@@YAPEBGW4SECMGR_INTF_ACTION@@@Z; IntfActionStr(SECMGR_INTF_ACTION)
0x1800596c7  mov     ecx, r10d
0x1800596ca  mov     r8, rax
0x1800596cd  call    ?IntfSecStateStr@@YAPEBGW4MSMSEC_INTF_SEC_STATE@@@Z; IntfSecStateStr(MSMSEC_INTF_SEC_STATE)
0x1800596d2  mov     rcx, [r11+38h]
0x1800596d6  mov     r9, rax
0x1800596d9  mov     [rsp+98h+var_68], edi
0x1800596dd  mov     edx, 89h
0x1800596e2  mov     [rsp+98h+var_70], r8
0x1800596e7  lea     r8, WPP_ae01c481f8653c6245af2cd9b1c5a1a2_Traceguids
0x1800596ee  mov     [rsp+98h+var_78], r10d
0x1800596f3  call    WPP_SF_SLSL
0x1800596f8  mov     r11, cs:WPP_GLOBAL_Control
0x1800596ff  add     r14, 4
0x180059703  jmp     loc_18005978B
0x180059708  mov     r8, [rbx+0AE0h]
0x18005970f  add     r14, 4
0x180059713  mov     rax, [r8+18h]
0x180059717  mov     r9d, [r14]
0x18005971a  mov     ecx, r9d
0x18005971d  mov     esi, [rax]
0x18005971f  mov     r15d, [rax+4]
0x180059723  sub     ecx, 1
0x180059726  jz      short loc_180059774
0x180059728  cmp     ecx, 1
0x18005972b  jz      short loc_18005976B
0x18005972d  mov     edi, 57h ; 'W'
0x180059732  mov     rcx, cs:WPP_GLOBAL_Control
0x180059739  lea     r12, WPP_GLOBAL_Control
0x180059740  cmp     rcx, r12
0x180059743  jz      loc_1800597D9
0x180059749  lea     esi, [rdi-56h]
0x18005974c  test    [rcx+44h], sil
0x180059750  jz      loc_1800597D9
0x180059756  mov     rcx, [rcx+38h]
0x18005975a  lea     edx, [rdi+33h]
0x18005975d  lea     r8, WPP_ae01c481f8653c6245af2cd9b1c5a1a2_Traceguids
0x180059764  call    WPP_SF_d
0x180059769  jmp     short loc_1800597D9
0x18005976b  mov     ecx, esi
0x18005976d  call    AuthCipher1xRequiresPSK
0x180059772  jmp     short loc_180059782
0x180059774  mov     r8d, [r8+20h]
0x180059778  mov     edx, r15d
0x18005977b  mov     ecx, esi
0x18005977d  call    AuthCipher1xRequiresWEPKey
0x180059782  mov     r11, cs:WPP_GLOBAL_Control
0x180059789  and     ebp, eax
0x18005978b  xor     edi, edi
0x18005978d  mov     [r12], ebp
0x180059791  lea     r12, WPP_GLOBAL_Control
0x180059798  cmp     r11, r12
0x18005979b  jz      short loc_1800597D9
0x18005979d  test    byte ptr [r11+44h], 2
0x1800597a2  jz      short loc_1800597D9
0x1800597a4  mov     r10d, [rbx+0AA4h]
0x1800597ab  mov     ecx, r10d
0x1800597ae  call    ?IntfSecStateStr@@YAPEBGW4MSMSEC_INTF_SEC_STATE@@@Z; IntfSecStateStr(MSMSEC_INTF_SEC_STATE)
0x1800597b3  mov     ecx, [r14]
0x1800597b6  mov     r9d, esi
0x1800597b9  mov     [rsp+98h+var_58], ebp
0x1800597bd  mov     [rsp+98h+var_60], ecx
0x1800597c1  mov     rcx, [r11+38h]
0x1800597c5  mov     [rsp+98h+var_68], r10d
0x1800597ca  mov     [rsp+98h+var_70], rax
0x1800597cf  mov     [rsp+98h+var_78], r15d
0x1800597d4  call    WPP_SF_LLSLLL
0x1800597d9  mov     ecx, [rbx+9C0h]; unsigned int
0x1800597df  lea     rdx, aUnlocking; "<<< Unlocking <<<"
0x1800597e6  call    ?TraceAdapterId@@YAXKPEBD@Z; TraceAdapterId(ulong,char const *)
0x1800597eb  mov     r9d, 8AAh
0x1800597f1  lea     r8, aSecmgrismsmsec; "SecMgrIsMSMSecUIRequestPending"
0x1800597f8  mov     rdx, r13
0x1800597fb  mov     rcx, rbx
0x1800597fe  call    cs:__imp_ReleaseWriteLock
0x180059805  nop     dword ptr [rax+rax+00h]
0x18005980a  mov     rcx, cs:WPP_GLOBAL_Control
0x180059811  cmp     rcx, r12
0x180059814  jz      short loc_180059837
0x180059816  test    dword ptr [rcx+44h], 100h
0x18005981d  jz      short loc_180059837
0x18005981f  mov     rcx, [rcx+38h]
0x180059823  lea     r8, WPP_ae01c481f8653c6245af2cd9b1c5a1a2_Traceguids
0x18005982a  mov     edx, 8Ch
0x18005982f  mov     r9d, edi
0x180059832  call    WPP_SF_d
0x180059837  mov     eax, edi
0x180059839  add     rsp, 58h
0x18005983d  pop     r15
0x18005983f  pop     r14
0x180059841  pop     r13
0x180059843  pop     r12
0x180059845  pop     rdi
0x180059846  pop     rsi
0x180059847  pop     rbp
0x180059848  pop     rbx
0x180059849  retn
```
