# CUPnPEventingManager::OnStateChanged(ulong,long * const)

- ea: `0x180048170`
- end: `0x1800483ad`
- name: `?OnStateChanged@CUPnPEventingManager@@UEAAJKQEAJ@Z`
- size: `573`
- prototype: `__int64 __fastcall(CUPnPEventingManager *__hidden this, unsigned int, int *const)`
- caller_count: `0`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800071c0`
- `0x180013cd0`
- `0x1800200f4`
- `0x180037134`
- `0x180048170`
- `0x180053e18`
- `0x180059010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180048282`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180048282`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004829d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800482b1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800482d9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800482e9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800482f9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004829d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800482b1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800482d9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800482e9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800482f9`

## pseudocode

```c
__int64 __fastcall CUPnPEventingManager::OnStateChanged(const unsigned __int16 **this, unsigned int a2, int *const a3)
{
  int IsAllowedCOMCallLocality; // edi
  const unsigned __int16 *v7; // rcx
  struct IUPnPAutomationProxy *v8; // rcx
  __int64 i; // rsi
  STRSAFE_PCNZWCH v10; // rcx
  int v12; // edx
  const char *v13; // r9
  LPVOID pv; // [rsp+40h] [rbp-28h] BYREF
  unsigned __int16 **v15; // [rsp+48h] [rbp-20h] BYREF
  unsigned __int16 **v16; // [rsp+50h] [rbp-18h] BYREF
  void *Block; // [rsp+58h] [rbp-10h] BYREF
  unsigned int v18; // [rsp+B8h] [rbp+50h] BYREF

  Block = 0;
  v18 = 0;
  v16 = 0;
  v15 = 0;
  pv = 0;
  IsAllowedCOMCallLocality = HrIsAllowedCOMCallLocality(1);
  if ( IsAllowedCOMCallLocality < 0 )
    goto LABEL_14;
  if ( *((_DWORD *)this + 22) == 2 && this[8] && (v7 = this[10]) != 0 && this[9] )
  {
    if ( a2 && a3 )
    {
      IsAllowedCOMCallLocality = (*(__int64 (__fastcall **)(const unsigned __int16 *, _QWORD, int *const, unsigned int *, unsigned __int16 ***, LPVOID *, unsigned __int16 ***))(*(_QWORD *)v7 + 40LL))(
                                   v7,
                                   a2,
                                   a3,
                                   &v18,
                                   &v16,
                                   &pv,
                                   &v15);
      if ( IsAllowedCOMCallLocality >= 0 )
      {
        IsAllowedCOMCallLocality = HrComposeEventBody(v8, v18, v16, v15, (struct tagVARIANT *)pv, (BSTR)&Block);
        if ( IsAllowedCOMCallLocality >= 0 )
        {
          IsAllowedCOMCallLocality = HrSubmitEvent(this[8], (STRSAFE_PCNZWCH)Block);
          free(Block);
        }
        for ( i = 0; (unsigned int)i < v18; i = (unsigned int)(i + 1) )
        {
          CoTaskMemFree(v15[i]);
          CoTaskMemFree(v16[i]);
          SafeClearVariant((VARIANT *)pv + i);
        }
        CoTaskMemFree(pv);
        CoTaskMemFree(v15);
        CoTaskMemFree(v16);
      }
LABEL_14:
      if ( !IsAllowedCOMCallLocality )
        return (unsigned int)IsAllowedCOMCallLocality;
      goto LABEL_15;
    }
    IsAllowedCOMCallLocality = -2147024809;
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control )
      return (unsigned int)IsAllowedCOMCallLocality;
    if ( (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_16;
    v12 = 20;
    v13 = "OnStateChanged() called, but nothing to do.";
  }
  else
  {
    IsAllowedCOMCallLocality = -2147418113;
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control )
      return (unsigned int)IsAllowedCOMCallLocality;
    if ( (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_16;
    v12 = 19;
    v13 = "OnStateChanged failed, CUPnPEventingManager is not initialized!";
  }
  WPP_SF_sd(
    *((_QWORD *)v10 + 2),
    v12,
    (unsigned int)WPP_26899187c1a539900c7f96418485818e_Traceguids,
    (_DWORD)v13,
    IsAllowedCOMCallLocality);
LABEL_15:
  v10 = WPP_GLOBAL_Control;
LABEL_16:
  if ( v10 != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (v10[14] & 1) != 0 )
    WPP_SF_sd(
      *((_QWORD *)v10 + 2),
      21,
      (unsigned int)WPP_26899187c1a539900c7f96418485818e_Traceguids,
      (unsigned int)"CUPnPEventingManager::OnStateChanged",
      IsAllowedCOMCallLocality);
  return (unsigned int)IsAllowedCOMCallLocality;
}

```

## disassembly

```asm
0x180048170  push    rbp
0x180048172  push    rbx
0x180048173  push    rsi
0x180048174  push    rdi
0x180048175  push    r13
0x180048177  push    r14
0x180048179  mov     rbp, rsp
0x18004817c  sub     rsp, 68h
0x180048180  mov     rbx, rcx
0x180048183  mov     [rbp+Block], 0
0x18004818b  mov     ecx, 1
0x180048190  mov     [rbp+arg_18], 0
0x180048197  mov     rsi, r8
0x18004819a  mov     [rbp+var_18], 0
0x1800481a2  mov     r14d, edx
0x1800481a5  mov     [rbp+var_20], 0
0x1800481ad  mov     [rbp+pv], 0
0x1800481b5  call    ?HrIsAllowedCOMCallLocality@@YAJW4CALL_LOCALITY@@@Z; HrIsAllowedCOMCallLocality(CALL_LOCALITY)
0x1800481ba  lea     r13, WPP_GLOBAL_Control
0x1800481c1  mov     edi, eax
0x1800481c3  test    eax, eax
0x1800481c5  js      loc_180048305
0x1800481cb  mov     eax, [rbx+58h]
0x1800481ce  cmp     eax, 2
0x1800481d1  jnz     loc_180048384
0x1800481d7  cmp     qword ptr [rbx+40h], 0
0x1800481dc  jz      loc_180048384
0x1800481e2  mov     rcx, [rbx+50h]
0x1800481e6  test    rcx, rcx
0x1800481e9  jz      loc_180048384
0x1800481ef  cmp     qword ptr [rbx+48h], 0
0x1800481f4  jz      loc_180048384
0x1800481fa  test    r14d, r14d
0x1800481fd  jz      loc_18004834B
0x180048203  test    rsi, rsi
0x180048206  jz      loc_18004834B
0x18004820c  mov     rax, [rcx]
0x18004820f  lea     rdx, [rbp+var_20]
0x180048213  mov     [rsp+68h+var_38], rdx
0x180048218  lea     r9, [rbp+arg_18]
0x18004821c  lea     rdx, [rbp+pv]
0x180048220  mov     r8, rsi
0x180048223  mov     [rsp+68h+pbstr], rdx
0x180048228  lea     rdx, [rbp+var_18]
0x18004822c  mov     rax, [rax+28h]
0x180048230  mov     [rsp+68h+var_48], rdx
0x180048235  mov     edx, r14d
0x180048238  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004823d  mov     edi, eax
0x18004823f  test    eax, eax
0x180048241  js      loc_180048305
0x180048247  mov     r9, [rbp+var_20]; unsigned __int16 **
0x18004824b  lea     rax, [rbp+Block]
0x18004824f  mov     r8, [rbp+var_18]; unsigned __int16 **
0x180048253  mov     edx, [rbp+arg_18]; unsigned int
0x180048256  mov     [rsp+68h+pbstr], rax; pbstr
0x18004825b  mov     rax, [rbp+pv]
0x18004825f  mov     [rsp+68h+var_48], rax; struct tagVARIANT *
0x180048264  call    ?HrComposeEventBody@@YAJPEAUIUPnPAutomationProxy@@KPEAPEAG1PEAUtagVARIANT@@1@Z; HrComposeEventBody(IUPnPAutomationProxy *,ulong,ushort * *,ushort * *,tagVARIANT *,ushort * *)
0x180048269  mov     edi, eax
0x18004826b  test    eax, eax
0x18004826d  js      short loc_18004828E
0x18004826f  mov     rdx, [rbp+Block]; pszSrc
0x180048273  mov     rcx, [rbx+40h]; unsigned __int16 *
0x180048277  call    ?HrSubmitEvent@@YAJPEBG0@Z; HrSubmitEvent(ushort const *,ushort const *)
0x18004827c  mov     rcx, [rbp+Block]; Block
0x180048280  mov     edi, eax
0x180048282  call    cs:__imp_free
0x180048289  nop     dword ptr [rax+rax+00h]
0x18004828e  xor     esi, esi
0x180048290  cmp     [rbp+arg_18], esi
0x180048293  jbe     short loc_1800482D5
0x180048295  mov     rcx, [rbp+var_20]
0x180048299  mov     rcx, [rcx+rsi*8]; pv
0x18004829d  call    cs:__imp_CoTaskMemFree
0x1800482a4  nop     dword ptr [rax+rax+00h]
0x1800482a9  mov     rcx, [rbp+var_18]
0x1800482ad  mov     rcx, [rcx+rsi*8]; pv
0x1800482b1  call    cs:__imp_CoTaskMemFree
0x1800482b8  nop     dword ptr [rax+rax+00h]
0x1800482bd  mov     rax, [rbp+pv]
0x1800482c1  lea     rcx, [rsi+rsi*2]
0x1800482c5  lea     rcx, [rax+rcx*8]; VARIANT *
0x1800482c9  call    ?SafeClearVariant@@YAXPEAUtagVARIANT@@@Z; SafeClearVariant(tagVARIANT *)
0x1800482ce  inc     esi
0x1800482d0  cmp     esi, [rbp+arg_18]
0x1800482d3  jb      short loc_180048295
0x1800482d5  mov     rcx, [rbp+pv]; pv
0x1800482d9  call    cs:__imp_CoTaskMemFree
0x1800482e0  nop     dword ptr [rax+rax+00h]
0x1800482e5  mov     rcx, [rbp+var_20]; pv
0x1800482e9  call    cs:__imp_CoTaskMemFree
0x1800482f0  nop     dword ptr [rax+rax+00h]
0x1800482f5  mov     rcx, [rbp+var_18]; pv
0x1800482f9  call    cs:__imp_CoTaskMemFree
0x180048300  nop     dword ptr [rax+rax+00h]
0x180048305  test    edi, edi
0x180048307  jz      short loc_18004833B
0x180048309  mov     rcx, cs:WPP_GLOBAL_Control
0x180048310  cmp     rcx, r13
0x180048313  jz      short loc_18004833B
0x180048315  test    byte ptr [rcx+1Ch], 1
0x180048319  jz      short loc_18004833B
0x18004831b  mov     rcx, [rcx+10h]
0x18004831f  lea     r9, aCupnpeventingm_7; "CUPnPEventingManager::OnStateChanged"
0x180048326  mov     edx, 15h
0x18004832b  mov     dword ptr [rsp+68h+var_48], edi
0x18004832f  lea     r8, WPP_26899187c1a539900c7f96418485818e_Traceguids
0x180048336  call    WPP_SF_sd
0x18004833b  mov     eax, edi
0x18004833d  add     rsp, 68h
0x180048341  pop     r14
0x180048343  pop     r13
0x180048345  pop     rdi
0x180048346  pop     rsi
0x180048347  pop     rbx
0x180048348  pop     rbp
0x180048349  retn
0x18004834b  mov     edi, 80070057h
0x180048350  mov     rcx, cs:WPP_GLOBAL_Control
0x180048357  cmp     rcx, r13
0x18004835a  jz      short loc_18004833B
0x18004835c  test    byte ptr [rcx+1Ch], 1
0x180048360  jz      short loc_180048310
0x180048362  mov     edx, 14h
0x180048367  lea     r9, aOnstatechanged; "OnStateChanged() called, but nothing to"...
0x18004836e  mov     rcx, [rcx+10h]
0x180048372  lea     r8, WPP_26899187c1a539900c7f96418485818e_Traceguids
0x180048379  mov     dword ptr [rsp+68h+var_48], edi
0x18004837d  call    WPP_SF_sd
0x180048382  jmp     short loc_180048309
0x180048384  mov     edi, 8000FFFFh
0x180048389  mov     rcx, cs:WPP_GLOBAL_Control
0x180048390  cmp     rcx, r13
0x180048393  jz      short loc_18004833B
0x180048395  test    byte ptr [rcx+1Ch], 1
0x180048399  jz      loc_180048310
0x18004839f  mov     edx, 13h
0x1800483a4  lea     r9, aOnstatechanged_0; "OnStateChanged failed, CUPnPEventingMan"...
0x1800483ab  jmp     short loc_18004836E
```
