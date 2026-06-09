# CWMFileSinkV1::CompleteOperations(void)

- ea: `0x180008aa0`
- end: `0x180008ac1`
- name: `?CompleteOperations@CWMFileSinkV1@@UEAAJXZ`
- size: `33`
- prototype: `__int64 __fastcall(CWMFileSinkV1 *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180008aa0`
- `0x18000d2b4`

## pseudocode

```c
__int64 __fastcall CWMFileSinkV1::CompleteOperations(CWMFileSinkV1 *this)
{
  __int64 result; // rax
  HANDLE *v2; // rcx

  result = 0;
  if ( *((_DWORD *)this + 9) )
  {
    v2 = (HANDLE *)*((_QWORD *)this + 1158);
    if ( v2 )
      return CUnbufferedWriter::WaitForOutstandingOperations(v2);
  }
  return result;
}

```

## disassembly

```asm
0x180008aa0  sub     rsp, 28h
0x180008aa4  xor     eax, eax
0x180008aa6  cmp     [rcx+24h], eax
0x180008aa9  jz      short loc_180008ABC
0x180008aab  mov     rcx, [rcx+2430h]; this
0x180008ab2  test    rcx, rcx
0x180008ab5  jz      short loc_180008ABC
0x180008ab7  call    ?WaitForOutstandingOperations@CUnbufferedWriter@@QEAAJXZ; CUnbufferedWriter::WaitForOutstandingOperations(void)
0x180008abc  add     rsp, 28h
0x180008ac0  retn
```
