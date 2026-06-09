# CUPnPEventingManager::OnStateChanged(ulong,long * const)

- ea: `0x180045570`
- end: `0x180045788`
- name: `?OnStateChanged@CUPnPEventingManager@@UEAAJKQEAJ@Z`
- size: `536`
- prototype: `__int64 __fastcall(CUPnPEventingManager *__hidden this, unsigned int, int *const)`
- caller_count: `0`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000db4c`
- `0x180013180`
- `0x18001ebf8`
- `0x180035094`
- `0x180045570`
- `0x180050790`
- `0x180055010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180045682`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180045682`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180045697`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800456a5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800456c7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800456d1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800456db`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180045697`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800456a5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800456c7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800456d1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800456db`

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
0x180045570  push    rbp
0x180045572  push    rbx
0x180045573  push    rsi
0x180045574  push    rdi
0x180045575  push    r13
0x180045577  push    r14
0x180045579  mov     rbp, rsp
0x18004557c  sub     rsp, 68h
0x180045580  mov     rbx, rcx
0x180045583  mov     [rbp+Block], 0
0x18004558b  mov     ecx, 1
0x180045590  mov     [rbp+arg_18], 0
0x180045597  mov     rsi, r8
0x18004559a  mov     [rbp+var_18], 0
0x1800455a2  mov     r14d, edx
0x1800455a5  mov     [rbp+var_20], 0
0x1800455ad  mov     [rbp+pv], 0
0x1800455b5  call    ?HrIsAllowedCOMCallLocality@@YAJW4CALL_LOCALITY@@@Z; HrIsAllowedCOMCallLocality(CALL_LOCALITY)
0x1800455ba  lea     r13, WPP_GLOBAL_Control
0x1800455c1  mov     edi, eax
0x1800455c3  test    eax, eax
0x1800455c5  js      loc_1800456E1
0x1800455cb  mov     eax, [rbx+58h]
0x1800455ce  cmp     eax, 2
0x1800455d1  jnz     loc_18004575F
0x1800455d7  cmp     qword ptr [rbx+40h], 0
0x1800455dc  jz      loc_18004575F
0x1800455e2  mov     rcx, [rbx+50h]
0x1800455e6  test    rcx, rcx
0x1800455e9  jz      loc_18004575F
0x1800455ef  cmp     qword ptr [rbx+48h], 0
0x1800455f4  jz      loc_18004575F
0x1800455fa  test    r14d, r14d
0x1800455fd  jz      loc_180045726
0x180045603  test    rsi, rsi
0x180045606  jz      loc_180045726
0x18004560c  mov     rax, [rcx]
0x18004560f  lea     rdx, [rbp+var_20]
0x180045613  mov     [rsp+68h+var_38], rdx
0x180045618  lea     r9, [rbp+arg_18]
0x18004561c  lea     rdx, [rbp+pv]
0x180045620  mov     r8, rsi
0x180045623  mov     [rsp+68h+pbstr], rdx
0x180045628  lea     rdx, [rbp+var_18]
0x18004562c  mov     rax, [rax+28h]
0x180045630  mov     [rsp+68h+var_48], rdx
0x180045635  mov     edx, r14d
0x180045638  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004563d  mov     edi, eax
0x18004563f  test    eax, eax
0x180045641  js      loc_1800456E1
0x180045647  mov     r9, [rbp+var_20]; unsigned __int16 **
0x18004564b  lea     rax, [rbp+Block]
0x18004564f  mov     r8, [rbp+var_18]; unsigned __int16 **
0x180045653  mov     edx, [rbp+arg_18]; unsigned int
0x180045656  mov     [rsp+68h+pbstr], rax; pbstr
0x18004565b  mov     rax, [rbp+pv]
0x18004565f  mov     [rsp+68h+var_48], rax; struct tagVARIANT *
0x180045664  call    ?HrComposeEventBody@@YAJPEAUIUPnPAutomationProxy@@KPEAPEAG1PEAUtagVARIANT@@1@Z; HrComposeEventBody(IUPnPAutomationProxy *,ulong,ushort * *,ushort * *,tagVARIANT *,ushort * *)
0x180045669  mov     edi, eax
0x18004566b  test    eax, eax
0x18004566d  js      short loc_180045688
0x18004566f  mov     rdx, [rbp+Block]; pszSrc
0x180045673  mov     rcx, [rbx+40h]; unsigned __int16 *
0x180045677  call    ?HrSubmitEvent@@YAJPEBG0@Z; HrSubmitEvent(ushort const *,ushort const *)
0x18004567c  mov     rcx, [rbp+Block]; Block
0x180045680  mov     edi, eax
0x180045682  call    cs:__imp_free
0x180045688  xor     esi, esi
0x18004568a  cmp     [rbp+arg_18], esi
0x18004568d  jbe     short loc_1800456C3
0x18004568f  mov     rcx, [rbp+var_20]
0x180045693  mov     rcx, [rcx+rsi*8]; pv
0x180045697  call    cs:__imp_CoTaskMemFree
0x18004569d  mov     rcx, [rbp+var_18]
0x1800456a1  mov     rcx, [rcx+rsi*8]; pv
0x1800456a5  call    cs:__imp_CoTaskMemFree
0x1800456ab  mov     rax, [rbp+pv]
0x1800456af  lea     rcx, [rsi+rsi*2]
0x1800456b3  lea     rcx, [rax+rcx*8]; VARIANT *
0x1800456b7  call    ?SafeClearVariant@@YAXPEAUtagVARIANT@@@Z; SafeClearVariant(tagVARIANT *)
0x1800456bc  inc     esi
0x1800456be  cmp     esi, [rbp+arg_18]
0x1800456c1  jb      short loc_18004568F
0x1800456c3  mov     rcx, [rbp+pv]; pv
0x1800456c7  call    cs:__imp_CoTaskMemFree
0x1800456cd  mov     rcx, [rbp+var_20]; pv
0x1800456d1  call    cs:__imp_CoTaskMemFree
0x1800456d7  mov     rcx, [rbp+var_18]; pv
0x1800456db  call    cs:__imp_CoTaskMemFree
0x1800456e1  test    edi, edi
0x1800456e3  jz      short loc_180045717
0x1800456e5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800456ec  cmp     rcx, r13
0x1800456ef  jz      short loc_180045717
0x1800456f1  test    byte ptr [rcx+1Ch], 1
0x1800456f5  jz      short loc_180045717
0x1800456f7  mov     rcx, [rcx+10h]
0x1800456fb  lea     r9, aCupnpeventingm_7; "CUPnPEventingManager::OnStateChanged"
0x180045702  mov     edx, 15h
0x180045707  mov     dword ptr [rsp+68h+var_48], edi
0x18004570b  lea     r8, WPP_26899187c1a539900c7f96418485818e_Traceguids
0x180045712  call    WPP_SF_sd
0x180045717  mov     eax, edi
0x180045719  add     rsp, 68h
0x18004571d  pop     r14
0x18004571f  pop     r13
0x180045721  pop     rdi
0x180045722  pop     rsi
0x180045723  pop     rbx
0x180045724  pop     rbp
0x180045725  retn
0x180045726  mov     edi, 80070057h
0x18004572b  mov     rcx, cs:WPP_GLOBAL_Control
0x180045732  cmp     rcx, r13
0x180045735  jz      short loc_180045717
0x180045737  test    byte ptr [rcx+1Ch], 1
0x18004573b  jz      short loc_1800456EC
0x18004573d  mov     edx, 14h
0x180045742  lea     r9, aOnstatechanged; "OnStateChanged() called, but nothing to"...
0x180045749  mov     rcx, [rcx+10h]
0x18004574d  lea     r8, WPP_26899187c1a539900c7f96418485818e_Traceguids
0x180045754  mov     dword ptr [rsp+68h+var_48], edi
0x180045758  call    WPP_SF_sd
0x18004575d  jmp     short loc_1800456E5
0x18004575f  mov     edi, 8000FFFFh
0x180045764  mov     rcx, cs:WPP_GLOBAL_Control
0x18004576b  cmp     rcx, r13
0x18004576e  jz      short loc_180045717
0x180045770  test    byte ptr [rcx+1Ch], 1
0x180045774  jz      loc_1800456EC
0x18004577a  mov     edx, 13h
0x18004577f  lea     r9, aOnstatechanged_0; "OnStateChanged failed, CUPnPEventingMan"...
0x180045786  jmp     short loc_180045749
```
