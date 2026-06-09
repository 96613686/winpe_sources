# GetMinorTask

- ea: `0x18001ba40`
- end: `0x18001ba9d`
- name: `GetMinorTask`
- size: `93`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x18001dc70`

## callees

- `0x18001ab78`
- `0x18001ba40`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001ba4a`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001ba4a`

## pseudocode

```c
const wchar_t *GetMinorTask()
{
  _QWORD *Value; // rax
  __int64 v1; // rax
  __int64 v2; // rcx
  __int64 v3; // rdx
  const wchar_t *result; // rax

  Value = TlsGetValue(g_dwMajorTaskStackTLSIndex);
  if ( !Value )
    return L"Def";
  v1 = CStack<CTaskNameCollection *>::Peek(Value);
  if ( !v1 )
    return L"Def";
  v2 = *(_QWORD *)(v1 + 24);
  if ( !v2 )
    return L"Def";
  v3 = *(_QWORD *)(*(_QWORD *)(v1 + 16) + 8 * v2 - 8);
  if ( !v3 )
    return L"Def";
  result = L"Def";
  if ( *(_QWORD *)v3 )
    return *(const wchar_t **)v3;
  return result;
}

```

## disassembly

```asm
0x18001ba40  sub     rsp, 28h
0x18001ba44  mov     ecx, cs:?g_dwMajorTaskStackTLSIndex@@3KA; dwTlsIndex
0x18001ba4a  call    cs:__imp_TlsGetValue
0x18001ba51  nop     dword ptr [rax+rax+00h]
0x18001ba56  test    rax, rax
0x18001ba59  jz      short loc_18001BA90
0x18001ba5b  mov     rcx, rax
0x18001ba5e  call    ?Peek@?$CStack@PEAVCTaskNameCollection@@@@QEAAPEAVCTaskNameCollection@@XZ; CStack<CTaskNameCollection *>::Peek(void)
0x18001ba63  test    rax, rax
0x18001ba66  jz      short loc_18001BA90
0x18001ba68  mov     rcx, [rax+18h]
0x18001ba6c  test    rcx, rcx
0x18001ba6f  jz      short loc_18001BA90
0x18001ba71  mov     rax, [rax+10h]
0x18001ba75  mov     rdx, [rax+rcx*8-8]
0x18001ba7a  test    rdx, rdx
0x18001ba7d  jz      short loc_18001BA90
0x18001ba7f  cmp     qword ptr [rdx], 0
0x18001ba83  lea     rax, aDef; "Def"
0x18001ba8a  cmovnz  rax, [rdx]
0x18001ba8e  jmp     short loc_18001BA97
0x18001ba90  lea     rax, aDef; "Def"
0x18001ba97  add     rsp, 28h
0x18001ba9b  retn
```
