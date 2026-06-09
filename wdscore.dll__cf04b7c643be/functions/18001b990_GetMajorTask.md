# GetMajorTask

- ea: `0x18001b990`
- end: `0x18001b9d9`
- name: `GetMajorTask`
- size: `73`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x18001dc70`

## callees

- `0x18001ab78`
- `0x18001b990`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001b99a`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001b99a`

## pseudocode

```c
const wchar_t *GetMajorTask()
{
  _QWORD *Value; // rax
  __int64 v1; // rcx
  const wchar_t *result; // rax

  Value = TlsGetValue(g_dwMajorTaskStackTLSIndex);
  if ( !Value )
    return L"Def";
  v1 = CStack<CTaskNameCollection *>::Peek(Value);
  if ( !v1 )
    return L"Def";
  result = L"Def";
  if ( *(_QWORD *)v1 )
    return *(const wchar_t **)v1;
  return result;
}

```

## disassembly

```asm
0x18001b990  sub     rsp, 28h
0x18001b994  mov     ecx, cs:?g_dwMajorTaskStackTLSIndex@@3KA; dwTlsIndex
0x18001b99a  call    cs:__imp_TlsGetValue
0x18001b9a1  nop     dword ptr [rax+rax+00h]
0x18001b9a6  test    rax, rax
0x18001b9a9  jz      short loc_18001B9CC
0x18001b9ab  mov     rcx, rax
0x18001b9ae  call    ?Peek@?$CStack@PEAVCTaskNameCollection@@@@QEAAPEAVCTaskNameCollection@@XZ; CStack<CTaskNameCollection *>::Peek(void)
0x18001b9b3  mov     rcx, rax
0x18001b9b6  test    rax, rax
0x18001b9b9  jz      short loc_18001B9CC
0x18001b9bb  cmp     qword ptr [rcx], 0
0x18001b9bf  lea     rax, aDef; "Def"
0x18001b9c6  cmovnz  rax, [rcx]
0x18001b9ca  jmp     short loc_18001B9D3
0x18001b9cc  lea     rax, aDef; "Def"
0x18001b9d3  add     rsp, 28h
0x18001b9d7  retn
```
