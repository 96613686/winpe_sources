# WnfStateChangeTriggerImpl<IWnfStateChangeTrigger,12>::get_StateData(tagSAFEARRAY * *)

- ea: `0x1800353a0`
- end: `0x18003542d`
- name: `?get_StateData@?$WnfStateChangeTriggerImpl@UIWnfStateChangeTrigger@@$0M@@@UEAAJPEAPEAUtagSAFEARRAY@@@Z`
- size: `141`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1800353a0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003540a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003540a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800353e1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800353e1`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x1800353fb`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x1800353fb`

## pseudocode

```c
__int64 __fastcall WnfStateChangeTriggerImpl<IWnfStateChangeTrigger,12>::get_StateData(__int64 a1, SAFEARRAY **a2)
{
  __int64 v5; // rsi
  SAFEARRAY *v6; // rcx

  if ( !a2 )
    return 2147500035LL;
  v5 = (a1 + 24) & -(__int64)(a1 != 0);
  if ( v5 )
    EnterCriticalSection((LPCRITICAL_SECTION)(v5 + 8));
  v6 = *(SAFEARRAY **)(a1 + 160);
  if ( v6 )
    SafeArrayCopy(v6, a2);
  else
    *a2 = 0;
  if ( v5 )
    LeaveCriticalSection((LPCRITICAL_SECTION)(v5 + 8));
  return 0;
}

```

## disassembly

```asm
0x1800353a0  mov     [rsp+arg_0], rbx
0x1800353a5  mov     [rsp+arg_10], rsi
0x1800353aa  push    rdi
0x1800353ab  push    r14
0x1800353ad  push    r15
0x1800353af  sub     rsp, 30h
0x1800353b3  mov     rdi, rdx
0x1800353b6  mov     r14, rcx
0x1800353b9  test    rdx, rdx
0x1800353bc  jnz     short loc_1800353C5
0x1800353be  mov     eax, 80004003h
0x1800353c3  jmp     short loc_180035419
0x1800353c5  xor     ebx, ebx
0x1800353c7  mov     [rsp+48h+arg_8], ebx
0x1800353cb  mov     rax, r14
0x1800353ce  add     rcx, 18h
0x1800353d2  neg     rax
0x1800353d5  sbb     rsi, rsi
0x1800353d8  and     rsi, rcx
0x1800353db  jz      short loc_1800353E7
0x1800353dd  lea     rcx, [rsi+8]; lpCriticalSection
0x1800353e1  call    cs:__imp_EnterCriticalSection
0x1800353e7  mov     rcx, [r14+0A0h]; psa
0x1800353ee  test    rcx, rcx
0x1800353f1  jnz     short loc_1800353F8
0x1800353f3  mov     [rdi], rcx
0x1800353f6  jmp     short loc_180035401
0x1800353f8  mov     rdx, rdi; ppsaOut
0x1800353fb  call    cs:__imp_SafeArrayCopy
0x180035401  test    rsi, rsi
0x180035404  jz      short loc_180035411
0x180035406  lea     rcx, [rsi+8]; lpCriticalSection
0x18003540a  call    cs:__imp_LeaveCriticalSection
0x180035410  nop
0x180035411  jmp     short loc_180035417
0x180035413  mov     ebx, [rsp+48h+arg_8]
0x180035417  mov     eax, ebx
0x180035419  mov     rbx, [rsp+48h+arg_0]
0x18003541e  mov     rsi, [rsp+48h+arg_10]
0x180035423  add     rsp, 30h
0x180035427  pop     r15
0x180035429  pop     r14
0x18003542b  pop     rdi
0x18003542c  retn
```
