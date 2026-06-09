# InterceptThrottlingManager::GetOperationalStatus(uint *,ushort * *)

- ea: `0x140275920`
- end: `0x140275af9`
- name: `?GetOperationalStatus@InterceptThrottlingManager@@QEBAXPEAIPEAPEAG@Z`
- size: `473`
- prototype: `void __fastcall(InterceptThrottlingManager *__hidden this, unsigned int *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x1402719e0`

## callees

- `0x140024504`
- `0x140078628`
- `0x14011ea40`
- `0x140275920`
- `0x140275b00`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140275ab2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140275ab2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x140275984`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1402759cb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x140275a21`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x140275984`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1402759cb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x140275a21`

## string_xrefs

- `0x1402759a2`: `onecore\vm\common\vml\VmMemory.h`
- `0x1402759e9`: `onecore\vm\common\vml\VmMemory.h`
- `0x140275a3f`: `onecore\vm\common\vml\VmMemory.h`

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
        v12[v13++] = *((_WORD *)qword_14032DE20 + *(int *)(i + 4 * v14++));
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
0x140275920  mov     [rsp-28h+arg_18], rbx
0x140275925  push    rbp
0x140275926  push    rsi
0x140275927  push    rdi
0x140275928  push    r14
0x14027592a  push    r15
0x14027592c  mov     rbp, rsp
0x14027592f  sub     rsp, 60h
0x140275933  mov     rax, cs:__security_cookie
0x14027593a  xor     rax, rsp
0x14027593d  mov     [rbp+var_10], rax
0x140275941  mov     r15, r8
0x140275944  mov     r14, rdx
0x140275947  mov     [rbp+var_40], 0
0x14027594e  xorps   xmm0, xmm0
0x140275951  xor     eax, eax
0x140275953  xorps   xmm1, xmm1
0x140275956  movdqu  [rbp+var_28], xmm1
0x14027595b  mov     [rbp+var_18], rax
0x14027595f  movups  [rbp+var_38], xmm0
0x140275963  mov     qword ptr [rbp+var_38], rax
0x140275967  lea     r8, [rbp+var_28]
0x14027596b  lea     rdx, [rbp+var_40]
0x14027596f  call    ?GetThrottlingState@InterceptThrottlingManager@@QEBAXPEAUThrottleState@1@AEAV?$vector@W4__MIDL___MIDL_itf_vmbservices_0000_0011_0001@@V?$allocator@W4__MIDL___MIDL_itf_vmbservices_0000_0011_0001@@@std@@@std@@@Z; InterceptThrottlingManager::GetThrottlingState(InterceptThrottlingManager::ThrottleState *,std::vector<__MIDL___MIDL_itf_vmbservices_0000_0011_0001> &)
0x140275974  mov     ebx, [rbp+var_40]
0x140275977  mov     edi, 1
0x14027597c  test    dil, bl
0x14027597f  jnz     short loc_1402759BE
0x140275981  lea     ecx, [rdi+1]; cb
0x140275984  call    cs:__imp_CoTaskMemAlloc
0x14027598b  nop     dword ptr [rax+rax+00h]
0x140275990  mov     rdx, rax
0x140275993  test    rax, rax
0x140275996  jnz     short loc_1402759B4
0x140275998  mov     rcx, [rbp+28h]; this
0x14027599c  mov     r9d, 8007000Eh; char *
0x1402759a2  lea     r8, aOnecoreVmCommo_35; "onecore\\vm\\common\\vml\\VmMemory.h"
0x1402759a9  mov     edx, 5FFh; void *
0x1402759ae  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1402759b4  mov     word ptr [rax], 9C42h
0x1402759b9  jmp     loc_140275AAA
0x1402759be  mov     eax, ebx
0x1402759c0  and     eax, 0FFFFFFFBh
0x1402759c3  cmp     eax, 3
0x1402759c6  jnz     short loc_140275A05
0x1402759c8  lea     ecx, [rax-1]; cb
0x1402759cb  call    cs:__imp_CoTaskMemAlloc
0x1402759d2  nop     dword ptr [rax+rax+00h]
0x1402759d7  mov     rdx, rax
0x1402759da  test    rax, rax
0x1402759dd  jnz     short loc_1402759FB
0x1402759df  mov     rcx, [rbp+28h]; this
0x1402759e3  mov     r9d, 8007000Eh; char *
0x1402759e9  lea     r8, aOnecoreVmCommo_35; "onecore\\vm\\common\\vml\\VmMemory.h"
0x1402759f0  mov     edx, 5FFh; void *
0x1402759f5  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1402759fb  mov     word ptr [rax], 9C41h
0x140275a00  jmp     loc_140275AAA
0x140275a05  mov     rcx, qword ptr [rbp+var_28+8]
0x140275a09  sub     rcx, qword ptr [rbp+var_28]
0x140275a0d  sar     rcx, 2
0x140275a11  and     ebx, 2
0x140275a14  lea     eax, [rcx+1]
0x140275a17  cmovnz  eax, ecx
0x140275a1a  mov     esi, eax
0x140275a1c  mov     ecx, eax
0x140275a1e  add     rcx, rcx; cb
0x140275a21  call    cs:__imp_CoTaskMemAlloc
0x140275a28  nop     dword ptr [rax+rax+00h]
0x140275a2d  mov     rdx, rax
0x140275a30  test    rax, rax
0x140275a33  jnz     short loc_140275A51
0x140275a35  mov     rcx, [rbp+28h]; this
0x140275a39  mov     r9d, 8007000Eh; char *
0x140275a3f  lea     r8, aOnecoreVmCommo_35; "onecore\\vm\\common\\vml\\VmMemory.h"
0x140275a46  mov     edx, 5FFh; void *
0x140275a4b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140275a51  xor     r8d, r8d
0x140275a54  test    ebx, ebx
0x140275a56  jnz     short loc_140275A60
0x140275a58  mov     word ptr [rax], 9C43h
0x140275a5d  mov     r8d, edi
0x140275a60  xor     r9d, r9d
0x140275a63  mov     rax, qword ptr [rbp+var_28+8]
0x140275a67  mov     rcx, qword ptr [rbp+var_28]
0x140275a6b  sub     rax, rcx
0x140275a6e  sar     rax, 2
0x140275a72  test    rax, rax
0x140275a75  jz      short loc_140275AA8
0x140275a77  movsxd  rax, dword ptr [rcx+r9*4]
0x140275a7b  lea     r10, qword_14032DE20
0x140275a82  mov     ecx, r8d
0x140275a85  movzx   eax, word ptr [r10+rax*2]
0x140275a8a  mov     [rdx+rcx*2], ax
0x140275a8e  add     r8d, edi
0x140275a91  add     r9, rdi
0x140275a94  mov     rax, qword ptr [rbp+var_28+8]
0x140275a98  mov     rcx, qword ptr [rbp+var_28]
0x140275a9c  sub     rax, rcx
0x140275a9f  sar     rax, 2
0x140275aa3  cmp     r9, rax
0x140275aa6  jb      short loc_140275A77
0x140275aa8  mov     edi, esi
0x140275aaa  mov     [r14], edi
0x140275aad  mov     [r15], rdx
0x140275ab0  xor     ecx, ecx; pv
0x140275ab2  call    cs:__imp_CoTaskMemFree
0x140275ab9  nop     dword ptr [rax+rax+00h]
0x140275abe  nop
0x140275abf  mov     rcx, qword ptr [rbp+var_28]
0x140275ac3  test    rcx, rcx
0x140275ac6  jz      short loc_140275AD8
0x140275ac8  mov     rdx, [rbp+var_18]
0x140275acc  sub     rdx, rcx
0x140275acf  and     rdx, 0FFFFFFFFFFFFFFFCh
0x140275ad3  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x140275ad8  mov     rcx, [rbp+var_10]
0x140275adc  xor     rcx, rsp; StackCookie
0x140275adf  call    __security_check_cookie
0x140275ae4  mov     rbx, [rsp+60h+arg_18]
0x140275aec  add     rsp, 60h
0x140275af0  pop     r15
0x140275af2  pop     r14
0x140275af4  pop     rdi
0x140275af5  pop     rsi
0x140275af6  pop     rbp
0x140275af7  retn
```
