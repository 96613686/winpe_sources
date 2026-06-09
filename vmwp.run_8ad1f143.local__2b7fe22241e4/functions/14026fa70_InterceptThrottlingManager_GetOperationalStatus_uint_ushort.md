# InterceptThrottlingManager::GetOperationalStatus(uint *,ushort * *)

- ea: `0x14026fa70`
- end: `0x14026fc49`
- name: `?GetOperationalStatus@InterceptThrottlingManager@@QEBAXPEAIPEAPEAG@Z`
- size: `473`
- prototype: `void __fastcall(InterceptThrottlingManager *__hidden this, unsigned int *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x14026bb30`

## callees

- `0x140023f94`
- `0x14006af58`
- `0x140132960`
- `0x14026fa70`
- `0x14026fc50`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14026fad4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14026fb1b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14026fb71`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14026fad4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14026fb1b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14026fb71`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14026fc02`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14026fc02`

## string_xrefs

- `0x14026faf2`: `onecore\vm\common\vml\VmMemory.h`
- `0x14026fb39`: `onecore\vm\common\vml\VmMemory.h`
- `0x14026fb8f`: `onecore\vm\common\vml\VmMemory.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall InterceptThrottlingManager::GetOperationalStatus(
        InterceptThrottlingManager *this,
        unsigned int *a2,
        unsigned __int16 **a3)
{
  unsigned int v5; // edi
  unsigned __int16 *v6; // rax
  unsigned __int16 *v7; // rdx
  unsigned __int16 *v8; // rax
  int v9; // ebx
  unsigned int v10; // eax
  unsigned int v11; // esi
  unsigned __int16 *v12; // rax
  unsigned int v13; // r8d
  unsigned __int64 v14; // r9
  __int64 i; // rcx
  int v16; // [rsp+20h] [rbp-40h] BYREF
  __int128 v17; // [rsp+28h] [rbp-38h]
  __int128 v18; // [rsp+38h] [rbp-28h] BYREF
  __int64 v19; // [rsp+48h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+28h]

  v16 = 0;
  v18 = 0;
  v19 = 0;
  v17 = 0u;
  InterceptThrottlingManager::GetThrottlingState(this, &v16, &v18);
  v5 = 1;
  if ( (v16 & 1) != 0 )
  {
    if ( (v16 & 0xFFFFFFFB) == 3 )
    {
      v8 = (unsigned __int16 *)CoTaskMemAlloc(2u);
      v7 = v8;
      if ( !v8 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x5FF,
          (unsigned int)"onecore\\vm\\common\\vml\\VmMemory.h",
          (const char *)0x8007000ELL,
          v16);
      *v8 = -25535;
    }
    else
    {
      v9 = v16 & 2;
      v10 = ((__int64)(*((_QWORD *)&v18 + 1) - v18) >> 2) + 1;
      if ( (v16 & 2) != 0 )
        v10 = (__int64)(*((_QWORD *)&v18 + 1) - v18) >> 2;
      v11 = v10;
      v12 = (unsigned __int16 *)CoTaskMemAlloc(2LL * v10);
      v7 = v12;
      if ( !v12 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x5FF,
          (unsigned int)"onecore\\vm\\common\\vml\\VmMemory.h",
          (const char *)0x8007000ELL,
          v16);
      v13 = 0;
      if ( !v9 )
      {
        *v12 = -25533;
        v13 = 1;
      }
      v14 = 0;
      for ( i = v18; v14 < (__int64)(*((_QWORD *)&v18 + 1) - v18) >> 2; i = v18 )
        v12[v13++] = *((_WORD *)qword_140323A90 + *(int *)(i + 4 * v14++));
      v5 = v11;
    }
  }
  else
  {
    v6 = (unsigned __int16 *)CoTaskMemAlloc(2u);
    v7 = v6;
    if ( !v6 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x5FF,
        (unsigned int)"onecore\\vm\\common\\vml\\VmMemory.h",
        (const char *)0x8007000ELL,
        v16);
    *v6 = -25534;
  }
  *a2 = v5;
  *a3 = v7;
  CoTaskMemFree(0);
  if ( (_QWORD)v18 )
    std::_Deallocate<16>(v18, (v19 - v18) & 0xFFFFFFFFFFFFFFFCuLL);
}

```

## disassembly

```asm
0x14026fa70  mov     [rsp-28h+arg_18], rbx
0x14026fa75  push    rbp
0x14026fa76  push    rsi
0x14026fa77  push    rdi
0x14026fa78  push    r14
0x14026fa7a  push    r15
0x14026fa7c  mov     rbp, rsp
0x14026fa7f  sub     rsp, 60h
0x14026fa83  mov     rax, cs:__security_cookie
0x14026fa8a  xor     rax, rsp
0x14026fa8d  mov     [rbp+var_10], rax
0x14026fa91  mov     r15, r8
0x14026fa94  mov     r14, rdx
0x14026fa97  mov     [rbp+var_40], 0
0x14026fa9e  xorps   xmm0, xmm0
0x14026faa1  xor     eax, eax
0x14026faa3  xorps   xmm1, xmm1
0x14026faa6  movdqu  [rbp+var_28], xmm1
0x14026faab  mov     [rbp+var_18], rax
0x14026faaf  movups  [rbp+var_38], xmm0
0x14026fab3  mov     qword ptr [rbp+var_38], rax
0x14026fab7  lea     r8, [rbp+var_28]
0x14026fabb  lea     rdx, [rbp+var_40]
0x14026fabf  call    ?GetThrottlingState@InterceptThrottlingManager@@QEBAXPEAUThrottleState@1@AEAV?$vector@W4__MIDL___MIDL_itf_vmbservices_0000_0011_0001@@V?$allocator@W4__MIDL___MIDL_itf_vmbservices_0000_0011_0001@@@std@@@std@@@Z; InterceptThrottlingManager::GetThrottlingState(InterceptThrottlingManager::ThrottleState *,std::vector<__MIDL___MIDL_itf_vmbservices_0000_0011_0001> &)
0x14026fac4  mov     ebx, [rbp+var_40]
0x14026fac7  mov     edi, 1
0x14026facc  test    dil, bl
0x14026facf  jnz     short loc_14026FB0E
0x14026fad1  lea     ecx, [rdi+1]; cb
0x14026fad4  call    cs:__imp_CoTaskMemAlloc
0x14026fadb  nop     dword ptr [rax+rax+00h]
0x14026fae0  mov     rdx, rax
0x14026fae3  test    rax, rax
0x14026fae6  jnz     short loc_14026FB04
0x14026fae8  mov     rcx, [rbp+28h]; this
0x14026faec  mov     r9d, 8007000Eh; char *
0x14026faf2  lea     r8, aOnecoreVmCommo_36; "onecore\\vm\\common\\vml\\VmMemory.h"
0x14026faf9  mov     edx, 5FFh; void *
0x14026fafe  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14026fb04  mov     word ptr [rax], 9C42h
0x14026fb09  jmp     loc_14026FBFA
0x14026fb0e  mov     eax, ebx
0x14026fb10  and     eax, 0FFFFFFFBh
0x14026fb13  cmp     eax, 3
0x14026fb16  jnz     short loc_14026FB55
0x14026fb18  lea     ecx, [rax-1]; cb
0x14026fb1b  call    cs:__imp_CoTaskMemAlloc
0x14026fb22  nop     dword ptr [rax+rax+00h]
0x14026fb27  mov     rdx, rax
0x14026fb2a  test    rax, rax
0x14026fb2d  jnz     short loc_14026FB4B
0x14026fb2f  mov     rcx, [rbp+28h]; this
0x14026fb33  mov     r9d, 8007000Eh; char *
0x14026fb39  lea     r8, aOnecoreVmCommo_36; "onecore\\vm\\common\\vml\\VmMemory.h"
0x14026fb40  mov     edx, 5FFh; void *
0x14026fb45  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14026fb4b  mov     word ptr [rax], 9C41h
0x14026fb50  jmp     loc_14026FBFA
0x14026fb55  mov     rcx, qword ptr [rbp+var_28+8]
0x14026fb59  sub     rcx, qword ptr [rbp+var_28]
0x14026fb5d  sar     rcx, 2
0x14026fb61  and     ebx, 2
0x14026fb64  lea     eax, [rcx+1]
0x14026fb67  cmovnz  eax, ecx
0x14026fb6a  mov     esi, eax
0x14026fb6c  mov     ecx, eax
0x14026fb6e  add     rcx, rcx; cb
0x14026fb71  call    cs:__imp_CoTaskMemAlloc
0x14026fb78  nop     dword ptr [rax+rax+00h]
0x14026fb7d  mov     rdx, rax
0x14026fb80  test    rax, rax
0x14026fb83  jnz     short loc_14026FBA1
0x14026fb85  mov     rcx, [rbp+28h]; this
0x14026fb89  mov     r9d, 8007000Eh; char *
0x14026fb8f  lea     r8, aOnecoreVmCommo_36; "onecore\\vm\\common\\vml\\VmMemory.h"
0x14026fb96  mov     edx, 5FFh; void *
0x14026fb9b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14026fba1  xor     r8d, r8d
0x14026fba4  test    ebx, ebx
0x14026fba6  jnz     short loc_14026FBB0
0x14026fba8  mov     word ptr [rax], 9C43h
0x14026fbad  mov     r8d, edi
0x14026fbb0  xor     r9d, r9d
0x14026fbb3  mov     rax, qword ptr [rbp+var_28+8]
0x14026fbb7  mov     rcx, qword ptr [rbp+var_28]
0x14026fbbb  sub     rax, rcx
0x14026fbbe  sar     rax, 2
0x14026fbc2  test    rax, rax
0x14026fbc5  jz      short loc_14026FBF8
0x14026fbc7  movsxd  rax, dword ptr [rcx+r9*4]
0x14026fbcb  lea     r10, qword_140323A90
0x14026fbd2  mov     ecx, r8d
0x14026fbd5  movzx   eax, word ptr [r10+rax*2]
0x14026fbda  mov     [rdx+rcx*2], ax
0x14026fbde  add     r8d, edi
0x14026fbe1  add     r9, rdi
0x14026fbe4  mov     rax, qword ptr [rbp+var_28+8]
0x14026fbe8  mov     rcx, qword ptr [rbp+var_28]
0x14026fbec  sub     rax, rcx
0x14026fbef  sar     rax, 2
0x14026fbf3  cmp     r9, rax
0x14026fbf6  jb      short loc_14026FBC7
0x14026fbf8  mov     edi, esi
0x14026fbfa  mov     [r14], edi
0x14026fbfd  mov     [r15], rdx
0x14026fc00  xor     ecx, ecx; pv
0x14026fc02  call    cs:__imp_CoTaskMemFree
0x14026fc09  nop     dword ptr [rax+rax+00h]
0x14026fc0e  nop
0x14026fc0f  mov     rcx, qword ptr [rbp+var_28]
0x14026fc13  test    rcx, rcx
0x14026fc16  jz      short loc_14026FC28
0x14026fc18  mov     rdx, [rbp+var_18]
0x14026fc1c  sub     rdx, rcx
0x14026fc1f  and     rdx, 0FFFFFFFFFFFFFFFCh
0x14026fc23  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x14026fc28  mov     rcx, [rbp+var_10]
0x14026fc2c  xor     rcx, rsp; StackCookie
0x14026fc2f  call    __security_check_cookie
0x14026fc34  mov     rbx, [rsp+60h+arg_18]
0x14026fc3c  add     rsp, 60h
0x14026fc40  pop     r15
0x14026fc42  pop     r14
0x14026fc44  pop     rdi
0x14026fc45  pop     rsi
0x14026fc46  pop     rbp
0x14026fc47  retn
```
