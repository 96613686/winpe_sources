# CWdsMetadata::ComputeMatch(CWdsMetadata const *,int,int *)

- ea: `0x1800093e0`
- end: `0x18000954d`
- name: `?ComputeMatch@CWdsMetadata@@AEBAKPEBV1@HPEAH@Z`
- size: `365`
- prototype: `unsigned int __fastcall(CWdsMetadata *__hidden this, const struct CWdsMetadata *, int, int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180009fd0`

## callees

- `0x1800093e0`
- `0x180009684`
- `0x18000a6a0`
- `0x18000c274`

## pseudocode

```c
__int64 __fastcall CWdsMetadata::ComputeMatch(CWdsMetadata *this, const struct CWdsMetadata *a2, __int64 a3, int *a4)
{
  int v5; // edi
  int v6; // ecx
  unsigned int matched; // ebx
  __int64 v8; // rbp
  unsigned int v10; // eax
  struct CWdsMetadata::CEntryGroup *v12; // r14
  struct CWdsMetadata::CEntryGroup *v13; // r15
  __int64 v14; // rcx
  int GroupIndex; // eax
  __int64 v16; // r8
  __int64 v17; // rdx
  __int64 v18; // r8
  int v20; // [rsp+30h] [rbp-48h]
  int v21; // [rsp+80h] [rbp+8h] BYREF
  int v22; // [rsp+90h] [rbp+18h]

  v22 = a3;
  v5 = 0;
  v6 = 0;
  v21 = 0;
  matched = 0;
  v20 = 0;
  v8 = 0;
  v10 = *((_DWORD *)this + 3);
  if ( v10 )
  {
    while ( 1 )
    {
      v12 = 0;
      v13 = 0;
      matched = 0;
      if ( (unsigned int)v8 < v10 )
        v12 = *(struct CWdsMetadata::CEntryGroup **)(*(_QWORD *)this + 8 * v8);
      else
        matched = 1413;
      if ( (unsigned int)ElValidateWin32_1(matched, a2, a3, 5826) )
        break;
      GroupIndex = CWdsMetadata::FindGroupIndex(v14, a2, *(_QWORD *)v12);
      if ( GroupIndex < 0 )
        goto LABEL_19;
      matched = 0;
      if ( (unsigned int)GroupIndex < *((_DWORD *)a2 + 3) )
      {
        _mm_lfence();
        v13 = *(struct CWdsMetadata::CEntryGroup **)(*(_QWORD *)a2 + 8LL * (unsigned int)GroupIndex);
      }
      else
      {
        matched = 1413;
      }
      if ( (unsigned int)ElValidateWin32_1(matched, a2, v16, 5835) )
        return matched;
      if ( *((_DWORD *)v12 + 5) )
      {
        a3 = (unsigned int)v22;
        if ( *((_DWORD *)v13 + 5) )
        {
          v20 = 1;
          matched = CWdsMetadata::MatchTag(this, a2, v22, v12, v13, &v21);
          if ( (unsigned int)ElValidateWin32_1(matched, v17, v18, 5848) )
            return matched;
          a3 = (unsigned int)v22;
          v5 = v21;
          if ( v22 )
          {
            if ( !v21 )
            {
              *a4 = 0;
              return matched;
            }
          }
          else if ( v21 )
          {
            goto LABEL_25;
          }
        }
      }
      else
      {
LABEL_19:
        a3 = (unsigned int)v22;
      }
      v10 = *((_DWORD *)this + 3);
      v8 = (unsigned int)(v8 + 1);
      if ( (unsigned int)v8 >= v10 )
      {
        v6 = v20;
        goto LABEL_22;
      }
    }
  }
  else
  {
LABEL_22:
    if ( (_DWORD)a3 || !v6 )
      *a4 = 1;
    else
LABEL_25:
      *a4 = v5;
  }
  return matched;
}

```

## disassembly

```asm
0x1800093e0  mov     rax, rsp
0x1800093e3  mov     [rax+10h], rbx
0x1800093e7  mov     [rax+18h], r8d
0x1800093eb  push    rbp
0x1800093ec  push    rsi
0x1800093ed  push    rdi
0x1800093ee  push    r12
0x1800093f0  push    r13
0x1800093f2  push    r14
0x1800093f4  push    r15
0x1800093f6  sub     rsp, 40h
0x1800093fa  mov     r12, rcx
0x1800093fd  xor     edi, edi
0x1800093ff  xor     ecx, ecx
0x180009401  mov     [rax+8], edi
0x180009404  xor     ebx, ebx
0x180009406  mov     [rsp+78h+var_48], ecx
0x18000940a  xor     ebp, ebp
0x18000940c  mov     rsi, r9
0x18000940f  mov     eax, [r12+0Ch]
0x180009414  mov     r13, rdx
0x180009417  test    eax, eax
0x180009419  jz      loc_18000951F
0x18000941f  xor     r14d, r14d
0x180009422  xor     r15d, r15d
0x180009425  xor     ebx, ebx
0x180009427  cmp     ebp, eax
0x180009429  jb      short loc_180009432
0x18000942b  mov     ebx, 585h
0x180009430  jmp     short loc_18000943A
0x180009432  mov     rax, [r12]
0x180009436  mov     r14, [rax+rbp*8]
0x18000943a  mov     r9d, 16C2h
0x180009440  mov     ecx, ebx
0x180009442  call    ElValidateWin32_1
0x180009447  test    eax, eax
0x180009449  jnz     loc_180009532
0x18000944f  mov     r8, [r14]
0x180009452  mov     rdx, r13
0x180009455  call    ?FindGroupIndex@CWdsMetadata@@AEBAHPEAV?$CDynArray@PEAUCEntryGroup@CWdsMetadata@@VCDeallocatePointer@@@@PEBG@Z; CWdsMetadata::FindGroupIndex(CDynArray<CWdsMetadata::CEntryGroup *,CDeallocatePointer> *,ushort const *)
0x18000945a  test    eax, eax
0x18000945c  js      loc_180009504
0x180009462  xor     ebx, ebx
0x180009464  cmp     eax, [r13+0Ch]
0x180009468  jb      short loc_180009471
0x18000946a  mov     ebx, 585h
0x18000946f  jmp     short loc_18000947E
0x180009471  lfence
0x180009474  mov     ecx, eax
0x180009476  mov     rax, [r13+0]
0x18000947a  mov     r15, [rax+rcx*8]
0x18000947e  mov     r9d, 16CBh
0x180009484  mov     ecx, ebx
0x180009486  call    ElValidateWin32_1
0x18000948b  test    eax, eax
0x18000948d  jnz     loc_180009532
0x180009493  cmp     [r14+14h], eax
0x180009497  jz      short loc_180009504
0x180009499  mov     r8d, [rsp+78h+arg_10]; int
0x1800094a1  cmp     [r15+14h], eax
0x1800094a5  jz      short loc_18000950C
0x1800094a7  lea     rax, [rsp+78h+arg_0]
0x1800094af  mov     [rsp+78h+var_48], 1
0x1800094b7  mov     [rsp+78h+var_50], rax; int *
0x1800094bc  mov     r9, r14; struct CWdsMetadata::CEntryGroup *
0x1800094bf  mov     rdx, r13; struct CWdsMetadata *
0x1800094c2  mov     [rsp+78h+var_58], r15; struct CWdsMetadata::CEntryGroup *
0x1800094c7  mov     rcx, r12; this
0x1800094ca  call    ?MatchTag@CWdsMetadata@@AEBAKPEBV1@HPEAUCEntryGroup@1@1PEAH@Z; CWdsMetadata::MatchTag(CWdsMetadata const *,int,CWdsMetadata::CEntryGroup *,CWdsMetadata::CEntryGroup *,int *)
0x1800094cf  mov     r9d, 16D8h
0x1800094d5  mov     ecx, eax
0x1800094d7  mov     ebx, eax
0x1800094d9  call    ElValidateWin32_1
0x1800094de  test    eax, eax
0x1800094e0  jnz     short loc_180009532
0x1800094e2  mov     r8d, [rsp+78h+arg_10]
0x1800094ea  mov     edi, [rsp+78h+arg_0]
0x1800094f1  test    r8d, r8d
0x1800094f4  jz      short loc_1800094FE
0x1800094f6  test    edi, edi
0x1800094f8  jnz     short loc_18000950C
0x1800094fa  mov     [rsi], edi
0x1800094fc  jmp     short loc_180009532
0x1800094fe  test    edi, edi
0x180009500  jnz     short loc_180009530
0x180009502  jmp     short loc_18000950C
0x180009504  mov     r8d, [rsp+78h+arg_10]
0x18000950c  mov     eax, [r12+0Ch]
0x180009511  inc     ebp
0x180009513  cmp     ebp, eax
0x180009515  jb      loc_18000941F
0x18000951b  mov     ecx, [rsp+78h+var_48]
0x18000951f  test    r8d, r8d
0x180009522  jz      short loc_18000952C
0x180009524  mov     dword ptr [rsi], 1
0x18000952a  jmp     short loc_180009532
0x18000952c  test    ecx, ecx
0x18000952e  jz      short loc_180009524
0x180009530  mov     [rsi], edi
0x180009532  mov     eax, ebx
0x180009534  mov     rbx, [rsp+78h+arg_8]
0x18000953c  add     rsp, 40h
0x180009540  pop     r15
0x180009542  pop     r14
0x180009544  pop     r13
0x180009546  pop     r12
0x180009548  pop     rdi
0x180009549  pop     rsi
0x18000954a  pop     rbp
0x18000954b  retn
```
