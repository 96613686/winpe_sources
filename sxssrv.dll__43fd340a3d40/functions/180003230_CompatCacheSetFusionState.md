# CompatCacheSetFusionState

- ea: `0x180003230`
- end: `0x180003301`
- name: `CompatCacheSetFusionState`
- size: `209`
- prototype: `__int64 __fastcall(PCWSTR SourceString)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180002d40`

## callees

- `0x180003230`
- `0x180006ccd`
- `0x180008010`

## import_xrefs

- `ntdll!RtlInitUnicodeStringEx` at `0x180003297`
- `ntdll!RtlInitUnicodeStringEx` at `0x180003297`

## pseudocode

```c
NTSTATUS __fastcall CompatCacheSetFusionState(PCWSTR SourceString, __int64 a2, int a3, int a4)
{
  int v8; // eax
  __int64 v9; // rax
  NTSTATUS result; // eax
  _BYTE v11[96]; // [rsp+20h] [rbp-1B8h] BYREF
  int v12; // [rsp+80h] [rbp-158h]
  __int64 v13; // [rsp+98h] [rbp-140h]
  struct _UNICODE_STRING DestinationString; // [rsp+A0h] [rbp-138h] BYREF
  int *v15; // [rsp+B0h] [rbp-128h]
  int v16; // [rsp+B8h] [rbp-120h]
  int v17; // [rsp+1F0h] [rbp+18h] BYREF

  v17 = 0;
  memset_0(v11, 0, 0x188u);
  v8 = 0;
  if ( a3 )
  {
    v8 = 1;
    v17 = 1;
  }
  if ( a4 )
    v17 = v8 | 2;
  v9 = 0;
  v12 = 32;
  if ( a2 != -1 )
    v9 = a2;
  v13 = v9;
  result = RtlInitUnicodeStringEx(&DestinationString, SourceString);
  if ( result >= 0 )
  {
    v16 = 4;
    v15 = &v17;
    return ((__int64 (__fastcall *)(__int64, _BYTE *))g_CompatCacheServiceApi)(2, v11);
  }
  return result;
}

```

## disassembly

```asm
0x180003230  push    rbx
0x180003232  push    rbp
0x180003233  push    rsi
0x180003234  push    rdi
0x180003235  sub     rsp, 1B8h
0x18000323c  mov     ebx, r8d
0x18000323f  mov     [rsp+1D8h+arg_10], 0
0x18000324a  mov     rdi, rdx
0x18000324d  mov     rbp, rcx
0x180003250  xor     edx, edx; Val
0x180003252  lea     rcx, [rsp+1D8h+var_1B8]; void *
0x180003257  mov     r8d, 188h; Size
0x18000325d  mov     esi, r9d
0x180003260  call    memset_0
0x180003265  xor     eax, eax
0x180003267  test    ebx, ebx
0x180003269  jnz     short loc_1800032B4
0x18000326b  test    esi, esi
0x18000326d  jnz     short loc_1800032C2
0x18000326f  xor     eax, eax
0x180003271  mov     [rsp+1D8h+var_158], 20h ; ' '
0x18000327c  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x180003280  lea     rcx, [rsp+1D8h+DestinationString]; DestinationString
0x180003288  mov     rdx, rbp; SourceString
0x18000328b  cmovnz  rax, rdi
0x18000328f  mov     [rsp+1D8h+var_140], rax
0x180003297  call    cs:__imp_RtlInitUnicodeStringEx
0x18000329e  nop     dword ptr [rax+rax+00h]
0x1800032a3  test    eax, eax
0x1800032a5  jns     short loc_1800032CE
0x1800032a7  add     rsp, 1B8h
0x1800032ae  pop     rdi
0x1800032af  pop     rsi
0x1800032b0  pop     rbp
0x1800032b1  pop     rbx
0x1800032b2  retn
0x1800032b4  mov     eax, 1
0x1800032b9  mov     [rsp+1D8h+arg_10], eax
0x1800032c0  jmp     short loc_18000326B
0x1800032c2  or      eax, 2
0x1800032c5  mov     [rsp+1D8h+arg_10], eax
0x1800032cc  jmp     short loc_18000326F
0x1800032ce  lea     rax, [rsp+1D8h+arg_10]
0x1800032d6  mov     [rsp+1D8h+var_120], 4
0x1800032e1  mov     [rsp+1D8h+var_128], rax
0x1800032e9  lea     rdx, [rsp+1D8h+var_1B8]
0x1800032ee  mov     rax, cs:g_CompatCacheServiceApi
0x1800032f5  mov     ecx, 2
0x1800032fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800032ff  jmp     short loc_1800032A7
```
