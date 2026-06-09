# MpPreQueryOpen

- ea: `0x140069c80`
- end: `0x140069d9f`
- name: `MpPreQueryOpen`
- size: `287`
- prototype: `__int64 __fastcall(PFLT_CALLBACK_DATA CallbackData)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x1400118d0`
- `0x140069c80`
- `0x14007ab88`

## import_xrefs

- `FLTMGR!FltIsEcpFromUserMode` at `0x140069d58`
- `FLTMGR!FltIsEcpFromUserMode` at `0x140069d58`
- `FLTMGR!FltGetEcpListFromCallbackData` at `0x140069d00`
- `FLTMGR!FltGetEcpListFromCallbackData` at `0x140069d00`
- `FLTMGR!FltFindExtraCreateParameter` at `0x140069d39`
- `FLTMGR!FltFindExtraCreateParameter` at `0x140069d39`
- `FLTMGR!FltAcknowledgeEcp` at `0x140069d8e`
- `FLTMGR!FltAcknowledgeEcp` at `0x140069d8e`

## pseudocode

```c
__int64 __fastcall MpPreQueryOpen(PFLT_CALLBACK_DATA CallbackData, __int64 a2)
{
  struct _FLT_FILTER *v5; // rdi
  PVOID v6; // rdx
  PECP_LIST EcpList; // [rsp+30h] [rbp-28h] BYREF
  PVOID EcpContext; // [rsp+38h] [rbp-20h] BYREF
  ULONG EcpContextSize; // [rsp+40h] [rbp-18h] BYREF

  if ( *(_DWORD *)(MpData + 4080) )
  {
    v5 = *(struct _FLT_FILTER **)(MpData + 16);
    EcpList = 0;
    EcpContext = 0;
    EcpContextSize = 0;
    if ( FltGetEcpListFromCallbackData(v5, CallbackData, &EcpList) >= 0 )
    {
      if ( EcpList )
      {
        _mm_lfence();
        if ( FltFindExtraCreateParameter(v5, EcpList, &ECP_TYPE_VETO_BINDING, &EcpContext, &EcpContextSize) >= 0 )
        {
          _mm_lfence();
          if ( !FltIsEcpFromUserMode(v5, EcpContext) && (unsigned int)MpHardenBindFltBind(CallbackData, a2) == 1835009 )
          {
            v6 = EcpContext;
            *(_BYTE *)EcpContext = 1;
            FltAcknowledgeEcp(*(PFLT_FILTER *)(a2 + 8), v6);
          }
        }
      }
    }
  }
  return 1;
}

```

## disassembly

```asm
0x140069c80  mov     [rsp+arg_10], rbx
0x140069c85  mov     [rsp+arg_18], rsi
0x140069c8a  push    rdi
0x140069c8b  sub     rsp, 50h
0x140069c8f  mov     rax, cs:__security_cookie
0x140069c96  xor     rax, rsp
0x140069c99  mov     [rsp+58h+var_10], rax
0x140069c9e  mov     rdi, cs:MpData
0x140069ca5  mov     rbx, rdx
0x140069ca8  mov     rsi, rcx
0x140069cab  cmp     dword ptr [rdi+0FF0h], 0
0x140069cb2  jnz     short loc_140069CD7
0x140069cb4  mov     eax, 1
0x140069cb9  mov     rcx, [rsp+58h+var_10]
0x140069cbe  xor     rcx, rsp; StackCookie
0x140069cc1  call    __security_check_cookie
0x140069cc6  mov     rbx, [rsp+58h+arg_10]
0x140069ccb  mov     rsi, [rsp+58h+arg_18]
0x140069cd0  add     rsp, 50h
0x140069cd4  pop     rdi
0x140069cd5  retn
0x140069cd7  mov     rdi, [rdi+10h]
0x140069cdb  lea     r8, [rsp+58h+EcpList]; EcpList
0x140069ce0  mov     rcx, rdi; Filter
0x140069ce3  mov     [rsp+58h+EcpList], 0
0x140069cec  mov     rdx, rsi; CallbackData
0x140069cef  mov     [rsp+58h+EcpContext], 0
0x140069cf8  mov     [rsp+58h+var_18], 0
0x140069d00  call    cs:__imp_FltGetEcpListFromCallbackData
0x140069d07  nop     dword ptr [rax+rax+00h]
0x140069d0c  test    eax, eax
0x140069d0e  js      short loc_140069CB4
0x140069d10  cmp     [rsp+58h+EcpList], 0
0x140069d16  jz      short loc_140069CB4
0x140069d18  lfence
0x140069d1b  mov     rdx, [rsp+58h+EcpList]; EcpList
0x140069d20  lea     rax, [rsp+58h+var_18]
0x140069d25  lea     r9, [rsp+58h+EcpContext]; EcpContext
0x140069d2a  mov     [rsp+58h+EcpContextSize], rax; EcpContextSize
0x140069d2f  lea     r8, ECP_TYPE_VETO_BINDING; EcpType
0x140069d36  mov     rcx, rdi; Filter
0x140069d39  call    cs:__imp_FltFindExtraCreateParameter
0x140069d40  nop     dword ptr [rax+rax+00h]
0x140069d45  test    eax, eax
0x140069d47  js      loc_140069CB4
0x140069d4d  lfence
0x140069d50  mov     rdx, [rsp+58h+EcpContext]; EcpContext
0x140069d55  mov     rcx, rdi; Filter
0x140069d58  call    cs:__imp_FltIsEcpFromUserMode
0x140069d5f  nop     dword ptr [rax+rax+00h]
0x140069d64  test    al, al
0x140069d66  jnz     loc_140069CB4
0x140069d6c  mov     rdx, rbx
0x140069d6f  mov     rcx, rsi; CallbackData
0x140069d72  call    MpHardenBindFltBind
0x140069d77  cmp     eax, 1C0001h
0x140069d7c  jnz     loc_140069CB4
0x140069d82  mov     rdx, [rsp+58h+EcpContext]; EcpContext
0x140069d87  mov     byte ptr [rdx], 1
0x140069d8a  mov     rcx, [rbx+8]; Filter
0x140069d8e  call    cs:__imp_FltAcknowledgeEcp
0x140069d95  nop     dword ptr [rax+rax+00h]
0x140069d9a  jmp     loc_140069CB4
```
