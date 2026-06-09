# LineEpilogAsync

- ea: `0x180017adc`
- end: `0x180017b6c`
- name: `LineEpilogAsync`
- size: `144`
- prototype: `__int64 __fastcall(unsigned int *, int, __int64, unsigned int, __int64, unsigned int)`
- caller_count: `49`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180007570`
- `0x180007810`
- `0x180007ba0`
- `0x180007df0`
- `0x180008090`
- `0x1800083a0`
- `0x180008500`
- `0x180008d20`
- `0x180009010`
- `0x180009510`
- `0x180009810`
- `0x180009ab0`
- `0x180009cc0`
- `0x180009e00`
- `0x180009f50`
- `0x18000b170`
- `0x18000b52c`
- `0x18000b734`
- `0x18000d360`
- `0x18000f930`
- `0x180010660`
- `0x180010d40`
- `0x180011d30`
- `0x180011f40`
- `0x180012170`
- `0x180013160`
- `0x180013560`
- `0x180013650`
- `0x180013800`
- `0x180013a80`
- `0x180013bd0`
- `0x180013d60`
- `0x180013f90`
- `0x180014140`
- `0x180014330`
- `0x180014520`
- `0x180014c50`
- `0x1800150f0`
- `0x180015500`
- `0x180015680`
- `0x180015a40`
- `0x1800160e0`
- `0x180016530`
- `0x1800166b0`
- `0x1800171f0`
- `0x180017540`
- `0x180017710`
- `0x180017800`
- `0x1800178f0`

## callees

- `0x180017adc`
- `0x180028300`
- `0x18002ba2c`
- `0x18003dc84`
- `0x18003e15c`

## pseudocode

```c
__int64 __fastcall LineEpilogAsync(unsigned int *a1, int a2, __int64 a3, unsigned int a4, __int64 a5, unsigned int a6)
{
  __int64 v10; // rcx

  DereferenceObject((__int64)a1, a6, 1);
  MyReleaseMutex(a3, a4);
  if ( a2 <= 0 )
  {
    if ( a5 )
      DereferenceObject(v10, *(_DWORD *)(a5 + 72), 1);
  }
  else if ( (int)*a1 <= 0 )
  {
    if ( !*a1 )
      TRACELogPrint(65538, "Error: SP returned 0, not request ID");
    CompletionProcSP(*(unsigned int *)(a5 + 72), *a1);
  }
  *a1 = a2;
  return TRACELogPrint(524290, "LineEpilogAsyc: exit, result=x%lx", a2);
}

```

## disassembly

```asm
0x180017adc  push    rbx
0x180017ade  push    rbp
0x180017adf  push    rsi
0x180017ae0  push    rdi
0x180017ae1  sub     rsp, 28h
0x180017ae5  mov     rdi, r8
0x180017ae8  mov     ebp, edx
0x180017aea  mov     edx, [rsp+48h+arg_28]
0x180017aee  mov     r8d, 1
0x180017af4  mov     ebx, r9d
0x180017af7  mov     rsi, rcx
0x180017afa  call    DereferenceObject
0x180017aff  mov     edx, ebx
0x180017b01  mov     rcx, rdi
0x180017b04  call    MyReleaseMutex
0x180017b09  test    ebp, ebp
0x180017b0b  jle     short loc_180017B36
0x180017b0d  cmp     dword ptr [rsi], 0
0x180017b10  jg      short loc_180017B4E
0x180017b12  jnz     short loc_180017B25
0x180017b14  lea     rdx, aErrorSpReturne; "Error: SP returned 0, not request ID"
0x180017b1b  mov     ecx, 10002h
0x180017b20  call    TRACELogPrint
0x180017b25  mov     rcx, [rsp+48h+arg_20]
0x180017b2a  mov     edx, [rsi]
0x180017b2c  mov     ecx, [rcx+48h]
0x180017b2f  call    CompletionProcSP
0x180017b34  jmp     short loc_180017B4E
0x180017b36  mov     rdx, [rsp+48h+arg_20]
0x180017b3b  test    rdx, rdx
0x180017b3e  jz      short loc_180017B4E
0x180017b40  mov     edx, [rdx+48h]
0x180017b43  mov     r8d, 1
0x180017b49  call    DereferenceObject
0x180017b4e  mov     r8d, ebp
0x180017b51  mov     [rsi], ebp
0x180017b53  lea     rdx, aLineepilogasyc; "LineEpilogAsyc: exit, result=x%lx"
0x180017b5a  mov     ecx, 80002h
0x180017b5f  add     rsp, 28h
0x180017b63  pop     rdi
0x180017b64  pop     rsi
0x180017b65  pop     rbp
0x180017b66  pop     rbx
0x180017b67  jmp     TRACELogPrint
```
