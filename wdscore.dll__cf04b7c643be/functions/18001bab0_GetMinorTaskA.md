# GetMinorTaskA

- ea: `0x18001bab0`
- end: `0x18001bb0f`
- name: `GetMinorTaskA`
- size: `95`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x18001d920`

## callees

- `0x18001ab78`
- `0x18001bab0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001baba`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001baba`

## pseudocode

```c
const char *GetMinorTaskA()
{
  _QWORD *Value; // rax
  __int64 v1; // rax
  __int64 v2; // rcx
  __int64 v3; // rdx
  const char *result; // rax

  Value = TlsGetValue(g_dwMajorTaskStackTLSIndex);
  if ( !Value )
    return "Def";
  v1 = CStack<CTaskNameCollection *>::Peek(Value);
  if ( !v1 )
    return "Def";
  v2 = *(_QWORD *)(v1 + 24);
  if ( !v2 )
    return "Def";
  v3 = *(_QWORD *)(*(_QWORD *)(v1 + 16) + 8 * v2 - 8);
  if ( !v3 )
    return "Def";
  result = "Def";
  if ( *(_QWORD *)(v3 + 8) )
    return *(const char **)(v3 + 8);
  return result;
}

```

## disassembly

```asm
0x18001bab0  sub     rsp, 28h
0x18001bab4  mov     ecx, cs:?g_dwMajorTaskStackTLSIndex@@3KA; dwTlsIndex
0x18001baba  call    cs:__imp_TlsGetValue
0x18001bac1  nop     dword ptr [rax+rax+00h]
0x18001bac6  test    rax, rax
0x18001bac9  jz      short loc_18001BB02
0x18001bacb  mov     rcx, rax
0x18001bace  call    ?Peek@?$CStack@PEAVCTaskNameCollection@@@@QEAAPEAVCTaskNameCollection@@XZ; CStack<CTaskNameCollection *>::Peek(void)
0x18001bad3  test    rax, rax
0x18001bad6  jz      short loc_18001BB02
0x18001bad8  mov     rcx, [rax+18h]
0x18001badc  test    rcx, rcx
0x18001badf  jz      short loc_18001BB02
0x18001bae1  mov     rax, [rax+10h]
0x18001bae5  mov     rdx, [rax+rcx*8-8]
0x18001baea  test    rdx, rdx
0x18001baed  jz      short loc_18001BB02
0x18001baef  cmp     qword ptr [rdx+8], 0
0x18001baf4  lea     rax, aDef_0; "Def"
0x18001bafb  cmovnz  rax, [rdx+8]
0x18001bb00  jmp     short loc_18001BB09
0x18001bb02  lea     rax, aDef_0; "Def"
0x18001bb09  add     rsp, 28h
0x18001bb0d  retn
```
