# CAceList::s_FindAce(CDPA<CAce,CTContainer_PolicyUnOwned<CAce>> &,void *,uchar,CAce const *)

- ea: `0x18000765c`
- end: `0x18000776a`
- name: `?s_FindAce@CAceList@@AEAAPEAVCAce@@AEAV?$CDPA@VCAce@@V?$CTContainer_PolicyUnOwned@VCAce@@@@@@PEAXEPEBV2@@Z`
- size: `270`
- prototype: `PSID *__fastcall(__int64, HDPA *, void *, char, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18000731c`

## callees

- `0x18000765c`
- `0x180007b90`
- `0x180009724`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1800076c3`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18000773c`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1800076c3`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18000773c`

## pseudocode

```c
PSID *__fastcall CAceList::s_FindAce(__int64 a1, HDPA *a2, void *a3, char a4, __int64 a5)
{
  HDPA v5; // rax
  __int64 v6; // rbp
  int v10; // r14d
  int i; // esi
  PSID *Ptr; // rax
  PSID *v13; // rbx
  bool v14; // cl
  BOOL v15; // eax

  v5 = *a2;
  v6 = 0;
  if ( *a2 )
  {
    v10 = *(_DWORD *)v5;
    for ( i = 0; i < v10; ++i )
    {
      Ptr = (PSID *)g_pfn_DPA_GetPtr(*a2, i);
      v13 = Ptr;
      if ( a5 )
      {
        v14 = 0;
        if ( *(int *)(a5 + 28) < 0 && *((int *)Ptr + 7) < 0 )
        {
          v14 = EqualSid(*(PSID *)(a5 + 8), Ptr[1])
             && *(_DWORD *)(a5 + 28) == *((_DWORD *)v13 + 7)
             && *(_DWORD *)(a5 + 4) == *((_DWORD *)v13 + 1)
             && *(_BYTE *)(a5 + 1) == *((_BYTE *)v13 + 1)
             && *(_BYTE *)a5 == *(_BYTE *)v13
             && *(_DWORD *)(a5 + 24) == *((_DWORD *)v13 + 6);
          if ( v13[2] != 0 && v14 )
            v14 = memcmp_0(v13[2], *(const void **)(a5 + 16), *((unsigned int *)v13 + 6)) == 0;
        }
        v15 = v14;
      }
      else
      {
        if ( *((_DWORD *)Ptr + 6) || a4 != -1 && *((_BYTE *)Ptr + 1) != a4 )
          continue;
        v15 = EqualSid(Ptr[1], a3);
      }
      if ( v15 )
        return v13;
    }
  }
  return (PSID *)v6;
}

```

## disassembly

```asm
0x18000765c  push    rbx
0x18000765e  push    rbp
0x18000765f  push    rsi
0x180007660  push    rdi
0x180007661  push    r12
0x180007663  push    r13
0x180007665  push    r14
0x180007667  push    r15
0x180007669  sub     rsp, 28h
0x18000766d  mov     rax, [rdx]
0x180007670  xor     ebp, ebp
0x180007672  mov     r15b, r9b
0x180007675  mov     r13, r8
0x180007678  mov     r12, rdx
0x18000767b  test    rax, rax
0x18000767e  jz      loc_180007756
0x180007684  mov     r14d, [rax]
0x180007687  xor     esi, esi
0x180007689  test    r14d, r14d
0x18000768c  jle     loc_180007756
0x180007692  mov     rdi, [rsp+68h+arg_20]
0x18000769a  mov     rcx, [r12]; hdpa
0x18000769e  movsxd  rdx, esi; i
0x1800076a1  call    cs:g_pfn_DPA_GetPtr
0x1800076a7  mov     rbx, rax
0x1800076aa  test    rdi, rdi
0x1800076ad  jz      short loc_180007724
0x1800076af  xor     cl, cl
0x1800076b1  cmp     [rdi+1Ch], ebp
0x1800076b4  jge     short loc_18000771F
0x1800076b6  cmp     [rax+1Ch], ebp
0x1800076b9  jge     short loc_18000771F
0x1800076bb  mov     rdx, [rax+8]; pSid2
0x1800076bf  mov     rcx, [rdi+8]; pSid1
0x1800076c3  call    cs:__imp_EqualSid
0x1800076c9  test    eax, eax
0x1800076cb  jz      short loc_1800076F7
0x1800076cd  mov     eax, [rbx+1Ch]
0x1800076d0  cmp     [rdi+1Ch], eax
0x1800076d3  jnz     short loc_1800076F7
0x1800076d5  mov     eax, [rbx+4]
0x1800076d8  cmp     [rdi+4], eax
0x1800076db  jnz     short loc_1800076F7
0x1800076dd  mov     al, [rbx+1]
0x1800076e0  cmp     [rdi+1], al
0x1800076e3  jnz     short loc_1800076F7
0x1800076e5  mov     al, [rbx]
0x1800076e7  cmp     [rdi], al
0x1800076e9  jnz     short loc_1800076F7
0x1800076eb  mov     eax, [rbx+18h]
0x1800076ee  cmp     [rdi+18h], eax
0x1800076f1  jnz     short loc_1800076F7
0x1800076f3  mov     cl, 1
0x1800076f5  jmp     short loc_1800076F9
0x1800076f7  xor     cl, cl
0x1800076f9  mov     rax, [rbx+10h]
0x1800076fd  neg     rax
0x180007700  movzx   edx, cl
0x180007703  sbb     eax, eax
0x180007705  test    edx, eax
0x180007707  jz      short loc_18000771F
0x180007709  mov     r8d, [rbx+18h]; Size
0x18000770d  mov     rdx, [rdi+10h]; Buf2
0x180007711  mov     rcx, [rbx+10h]; Buf1
0x180007715  call    memcmp_0
0x18000771a  test    eax, eax
0x18000771c  setz    cl
0x18000771f  movzx   eax, cl
0x180007722  jmp     short loc_180007742
0x180007724  cmp     [rax+18h], ebp
0x180007727  jnz     short loc_180007746
0x180007729  cmp     r15b, 0FFh
0x18000772d  jz      short loc_180007735
0x18000772f  cmp     [rax+1], r15b
0x180007733  jnz     short loc_180007746
0x180007735  mov     rcx, [rax+8]; pSid1
0x180007739  mov     rdx, r13; pSid2
0x18000773c  call    cs:__imp_EqualSid
0x180007742  test    eax, eax
0x180007744  jnz     short loc_180007753
0x180007746  inc     esi
0x180007748  cmp     esi, r14d
0x18000774b  jl      loc_18000769A
0x180007751  jmp     short loc_180007756
0x180007753  mov     rbp, rbx
0x180007756  mov     rax, rbp
0x180007759  add     rsp, 28h
0x18000775d  pop     r15
0x18000775f  pop     r14
0x180007761  pop     r13
0x180007763  pop     r12
0x180007765  pop     rdi
0x180007766  pop     rsi
0x180007767  pop     rbp
0x180007768  pop     rbx
0x180007769  retn
```
