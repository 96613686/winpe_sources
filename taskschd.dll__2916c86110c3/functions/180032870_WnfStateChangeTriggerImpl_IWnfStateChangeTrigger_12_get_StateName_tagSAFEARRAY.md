# WnfStateChangeTriggerImpl<IWnfStateChangeTrigger,12>::get_StateName(tagSAFEARRAY * *)

- ea: `0x180032870`
- end: `0x180032901`
- name: `?get_StateName@?$WnfStateChangeTriggerImpl@UIWnfStateChangeTrigger@@$0M@@@UEAAJPEAPEAUtagSAFEARRAY@@@Z`
- size: `145`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180032870`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800328ce`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800328ce`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800328aa`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800328aa`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x1800328bf`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x1800328bf`

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
0x180032870  mov     [rsp+arg_0], rbx
0x180032875  mov     [rsp+arg_10], rsi
0x18003287a  push    rdi
0x18003287b  push    r14
0x18003287d  push    r15
0x18003287f  sub     rsp, 30h
0x180032883  mov     rdi, rdx
0x180032886  mov     r14, rcx
0x180032889  test    rdx, rdx
0x18003288c  jz      short loc_1800328EB
0x18003288e  xor     ebx, ebx
0x180032890  mov     [rsp+48h+arg_8], ebx
0x180032894  mov     rax, rcx
0x180032897  add     rcx, 18h
0x18003289b  neg     rax
0x18003289e  sbb     rsi, rsi
0x1800328a1  and     rsi, rcx
0x1800328a4  jz      short loc_1800328B0
0x1800328a6  lea     rcx, [rsi+8]; lpCriticalSection
0x1800328aa  call    cs:__imp_EnterCriticalSection
0x1800328b0  mov     rcx, [r14+98h]; psa
0x1800328b7  test    rcx, rcx
0x1800328ba  jz      short loc_1800328F2
0x1800328bc  mov     rdx, rdi; ppsaOut
0x1800328bf  call    cs:__imp_SafeArrayCopy
0x1800328c5  test    rsi, rsi
0x1800328c8  jz      short loc_1800328D5
0x1800328ca  lea     rcx, [rsi+8]; lpCriticalSection
0x1800328ce  call    cs:__imp_LeaveCriticalSection
0x1800328d4  nop
0x1800328d5  mov     eax, ebx
0x1800328d7  mov     rbx, [rsp+48h+arg_0]
0x1800328dc  mov     rsi, [rsp+48h+arg_10]
0x1800328e1  add     rsp, 30h
0x1800328e5  pop     r15
0x1800328e7  pop     r14
0x1800328e9  pop     rdi
0x1800328ea  retn
0x1800328eb  mov     eax, 80004003h
0x1800328f0  jmp     short loc_1800328D7
0x1800328f2  mov     qword ptr [rdi], 0
0x1800328f9  jmp     short loc_1800328C5
0x1800328fb  mov     ebx, [rsp+48h+arg_8]
0x1800328ff  jmp     short loc_1800328D5
```
