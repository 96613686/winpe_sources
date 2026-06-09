# WnfStateChangeTriggerImpl<IWnfStateChangeTrigger,12>::get_StateName(tagSAFEARRAY * *)

- ea: `0x180035800`
- end: `0x1800358a4`
- name: `?get_StateName@?$WnfStateChangeTriggerImpl@UIWnfStateChangeTrigger@@$0M@@@UEAAJPEAPEAUtagSAFEARRAY@@@Z`
- size: `164`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180035800`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003586a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003586a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003583a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003583a`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x180035855`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x180035855`

## pseudocode

```c
__int64 __fastcall WnfStateChangeTriggerImpl<IWnfStateChangeTrigger,12>::get_StateName(__int64 a1, SAFEARRAY **a2)
{
  __int64 v4; // rsi
  SAFEARRAY *v5; // rcx

  if ( !a2 )
    return 2147500035LL;
  v4 = (a1 + 24) & -(__int64)(a1 != 0);
  if ( v4 )
    EnterCriticalSection((LPCRITICAL_SECTION)(v4 + 8));
  v5 = *(SAFEARRAY **)(a1 + 152);
  if ( v5 )
    SafeArrayCopy(v5, a2);
  else
    *a2 = 0;
  if ( v4 )
    LeaveCriticalSection((LPCRITICAL_SECTION)(v4 + 8));
  return 0;
}

```

## disassembly

```asm
0x180035800  mov     [rsp+arg_0], rbx
0x180035805  mov     [rsp+arg_10], rsi
0x18003580a  push    rdi
0x18003580b  push    r14
0x18003580d  push    r15
0x18003580f  sub     rsp, 30h
0x180035813  mov     rdi, rdx
0x180035816  mov     r14, rcx
0x180035819  test    rdx, rdx
0x18003581c  jz      short loc_18003588E
0x18003581e  xor     ebx, ebx
0x180035820  mov     [rsp+48h+arg_8], ebx
0x180035824  mov     rax, rcx
0x180035827  add     rcx, 18h
0x18003582b  neg     rax
0x18003582e  sbb     rsi, rsi
0x180035831  and     rsi, rcx
0x180035834  jz      short loc_180035846
0x180035836  lea     rcx, [rsi+8]; lpCriticalSection
0x18003583a  call    cs:__imp_EnterCriticalSection
0x180035841  nop     dword ptr [rax+rax+00h]
0x180035846  mov     rcx, [r14+98h]; psa
0x18003584d  test    rcx, rcx
0x180035850  jz      short loc_180035895
0x180035852  mov     rdx, rdi; ppsaOut
0x180035855  call    cs:__imp_SafeArrayCopy
0x18003585c  nop     dword ptr [rax+rax+00h]
0x180035861  test    rsi, rsi
0x180035864  jz      short loc_180035877
0x180035866  lea     rcx, [rsi+8]; lpCriticalSection
0x18003586a  call    cs:__imp_LeaveCriticalSection
0x180035871  nop     dword ptr [rax+rax+00h]
0x180035876  nop
0x180035877  mov     eax, ebx
0x180035879  mov     rbx, [rsp+48h+arg_0]
0x18003587e  mov     rsi, [rsp+48h+arg_10]
0x180035883  add     rsp, 30h
0x180035887  pop     r15
0x180035889  pop     r14
0x18003588b  pop     rdi
0x18003588c  retn
0x18003588e  mov     eax, 80004003h
0x180035893  jmp     short loc_180035879
0x180035895  mov     qword ptr [rdi], 0
0x18003589c  jmp     short loc_180035861
0x18003589e  mov     ebx, [rsp+48h+arg_8]
0x1800358a2  jmp     short loc_180035877
```
