# GetMajorTaskA

- ea: `0x18001b9e0`
- end: `0x18001ba2b`
- name: `GetMajorTaskA`
- size: `75`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x18001d920`

## callees

- `0x18001ab78`
- `0x18001b9e0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001b9ea`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001b9ea`

## pseudocode

```c
const char *GetMajorTaskA()
{
  _QWORD *Value; // rax
  __int64 v1; // rcx
  const char *result; // rax

  Value = TlsGetValue(g_dwMajorTaskStackTLSIndex);
  if ( !Value )
    return "Def";
  v1 = CStack<CTaskNameCollection *>::Peek(Value);
  if ( !v1 )
    return "Def";
  result = "Def";
  if ( *(_QWORD *)(v1 + 8) )
    return *(const char **)(v1 + 8);
  return result;
}

```

## disassembly

```asm
0x18001b9e0  sub     rsp, 28h
0x18001b9e4  mov     ecx, cs:?g_dwMajorTaskStackTLSIndex@@3KA; dwTlsIndex
0x18001b9ea  call    cs:__imp_TlsGetValue
0x18001b9f1  nop     dword ptr [rax+rax+00h]
0x18001b9f6  test    rax, rax
0x18001b9f9  jz      short loc_18001BA1E
0x18001b9fb  mov     rcx, rax
0x18001b9fe  call    ?Peek@?$CStack@PEAVCTaskNameCollection@@@@QEAAPEAVCTaskNameCollection@@XZ; CStack<CTaskNameCollection *>::Peek(void)
0x18001ba03  mov     rcx, rax
0x18001ba06  test    rax, rax
0x18001ba09  jz      short loc_18001BA1E
0x18001ba0b  cmp     qword ptr [rcx+8], 0
0x18001ba10  lea     rax, aDef_0; "Def"
0x18001ba17  cmovnz  rax, [rcx+8]
0x18001ba1c  jmp     short loc_18001BA25
0x18001ba1e  lea     rax, aDef_0; "Def"
0x18001ba25  add     rsp, 28h
0x18001ba29  retn
```
