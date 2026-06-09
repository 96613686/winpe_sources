# CompletionProcSP

- ea: `0x180028300`
- end: `0x180028395`
- name: `CompletionProcSP`
- size: `149`
- prototype: `__int64 __fastcall(__int64, unsigned int)`
- caller_count: `3`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180012a90`
- `0x180017adc`
- `0x180024f08`

## callees

- `0x1800281f0`
- `0x180028300`
- `0x18002bbd4`
- `0x18003dc84`
- `0x18003e15c`
- `0x18003e3b4`

## string_xrefs

- `0x18002832e`: `CompletionProcSP: enter, dwReqID=x%x, lResult=x%x`
- `0x180028374`: `CompletionProcSP: bad dwRequestID=x%x`

## pseudocode

```c
__int64 __fastcall CompletionProcSP(__int64 a1, unsigned int a2)
{
  unsigned int v3; // ebx
  __int64 v4; // rdi
  __int64 v5; // rcx
  __int64 result; // rax
  __int64 v7; // rcx

  v3 = a1;
  v4 = ReferenceObject(a1, (unsigned int)a1, 1129927489);
  if ( !v4 )
    return TRACELogPrint(65538, "CompletionProcSP: bad dwRequestID=x%x", v3);
  TRACELogPrint(524290, "CompletionProcSP: enter, dwReqID=x%x, lResult=x%x", v3, a2);
  *(_DWORD *)(v4 + 40) = a2;
  DereferenceObject(v5, v3, 1);
  result = QueueSPEvent(v4);
  if ( !(_DWORD)result )
  {
    CompletionProc(v4, a2);
    return DereferenceObject(v7, v3, 1);
  }
  return result;
}

```

## disassembly

```asm
0x180028300  mov     [rsp+arg_0], rbx
0x180028305  mov     [rsp+arg_8], rsi
0x18002830a  push    rdi
0x18002830b  sub     rsp, 20h
0x18002830f  mov     esi, edx
0x180028311  mov     r8d, 43595341h
0x180028317  mov     edx, ecx
0x180028319  mov     ebx, ecx
0x18002831b  call    ReferenceObject
0x180028320  mov     rdi, rax
0x180028323  mov     r8d, ebx
0x180028326  test    rax, rax
0x180028329  jz      short loc_180028374
0x18002832b  mov     r9d, esi
0x18002832e  lea     rdx, aCompletionproc_0; "CompletionProcSP: enter, dwReqID=x%x, l"...
0x180028335  mov     ecx, 80002h
0x18002833a  call    TRACELogPrint
0x18002833f  mov     r8d, 1
0x180028345  mov     [rdi+28h], esi
0x180028348  mov     edx, ebx
0x18002834a  call    DereferenceObject
0x18002834f  mov     rcx, rdi
0x180028352  call    QueueSPEvent
0x180028357  test    eax, eax
0x180028359  jnz     short loc_180028385
0x18002835b  mov     edx, esi
0x18002835d  mov     rcx, rdi
0x180028360  call    CompletionProc
0x180028365  mov     r8d, 1
0x18002836b  mov     edx, ebx
0x18002836d  call    DereferenceObject
0x180028372  jmp     short loc_180028385
0x180028374  lea     rdx, aCompletionproc_1; "CompletionProcSP: bad dwRequestID=x%x"
0x18002837b  mov     ecx, 10002h
0x180028380  call    TRACELogPrint
0x180028385  mov     rbx, [rsp+28h+arg_0]
0x18002838a  mov     rsi, [rsp+28h+arg_8]
0x18002838f  add     rsp, 20h
0x180028393  pop     rdi
0x180028394  retn
```
