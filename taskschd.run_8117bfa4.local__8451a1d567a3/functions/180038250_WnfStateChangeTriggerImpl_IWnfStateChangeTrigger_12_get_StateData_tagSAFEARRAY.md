# WnfStateChangeTriggerImpl<IWnfStateChangeTrigger,12>::get_StateData(tagSAFEARRAY * *)

- ea: `0x180038250`
- end: `0x1800382f0`
- name: `?get_StateData@?$WnfStateChangeTriggerImpl@UIWnfStateChangeTrigger@@$0M@@@UEAAJPEAPEAUtagSAFEARRAY@@@Z`
- size: `160`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180038250`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800382c6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800382c6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180038291`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180038291`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x1800382b1`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x1800382b1`

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
0x180038250  mov     [rsp+arg_0], rbx
0x180038255  mov     [rsp+arg_10], rsi
0x18003825a  push    rdi
0x18003825b  push    r14
0x18003825d  push    r15
0x18003825f  sub     rsp, 30h
0x180038263  mov     rdi, rdx
0x180038266  mov     r14, rcx
0x180038269  test    rdx, rdx
0x18003826c  jnz     short loc_180038275
0x18003826e  mov     eax, 80004003h
0x180038273  jmp     short loc_1800382DB
0x180038275  xor     ebx, ebx
0x180038277  mov     [rsp+48h+arg_8], ebx
0x18003827b  mov     rax, r14
0x18003827e  add     rcx, 18h
0x180038282  neg     rax
0x180038285  sbb     rsi, rsi
0x180038288  and     rsi, rcx
0x18003828b  jz      short loc_18003829D
0x18003828d  lea     rcx, [rsi+8]; lpCriticalSection
0x180038291  call    cs:__imp_EnterCriticalSection
0x180038298  nop     dword ptr [rax+rax+00h]
0x18003829d  mov     rcx, [r14+0A0h]; psa
0x1800382a4  test    rcx, rcx
0x1800382a7  jnz     short loc_1800382AE
0x1800382a9  mov     [rdi], rcx
0x1800382ac  jmp     short loc_1800382BD
0x1800382ae  mov     rdx, rdi; ppsaOut
0x1800382b1  call    cs:__imp_SafeArrayCopy
0x1800382b8  nop     dword ptr [rax+rax+00h]
0x1800382bd  test    rsi, rsi
0x1800382c0  jz      short loc_1800382D3
0x1800382c2  lea     rcx, [rsi+8]; lpCriticalSection
0x1800382c6  call    cs:__imp_LeaveCriticalSection
0x1800382cd  nop     dword ptr [rax+rax+00h]
0x1800382d2  nop
0x1800382d3  jmp     short loc_1800382D9
0x1800382d5  mov     ebx, [rsp+48h+arg_8]
0x1800382d9  mov     eax, ebx
0x1800382db  mov     rbx, [rsp+48h+arg_0]
0x1800382e0  mov     rsi, [rsp+48h+arg_10]
0x1800382e5  add     rsp, 30h
0x1800382e9  pop     r15
0x1800382eb  pop     r14
0x1800382ed  pop     rdi
0x1800382ee  retn
```
