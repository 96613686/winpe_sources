# HashKComputeMemoryHashExcludeRanges

- ea: `0x18004be0c`
- end: `0x18004becb`
- name: `HashKComputeMemoryHashExcludeRanges`
- size: `191`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180046d9c`

## callees

- `0x180033950`
- `0x180033980`
- `0x18004be0c`
- `0x18004c00c`
- `0x18004c0c8`
- `0x18004c1ac`
- `0x18004c254`

## pseudocode

```c
__int64 __fastcall HashKComputeMemoryHashExcludeRanges(
        int a1,
        int a2,
        unsigned int a3,
        __int64 a4,
        __int64 a5,
        int a6,
        __int64 a7)
{
  __int64 result; // rax
  int v11; // [rsp+30h] [rbp-128h] BYREF
  _BYTE v12[236]; // [rsp+34h] [rbp-124h] BYREF

  memset_0(v12, 0, sizeof(v12));
  v11 = a1;
  result = HashpInitHash(&v11, 0);
  if ( (int)result >= 0 )
  {
    HashpEmitExcludeRange((unsigned int)&v11, a5, a6, a2, a3);
    if ( a3 != 4096 )
      HashpPadHash(&v11, a3, 4096);
    HashpFinalizeHash(&v11, a7);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x18004be0c  push    rbx
0x18004be0e  push    rbp
0x18004be0f  push    rsi
0x18004be10  push    rdi
0x18004be11  push    r14
0x18004be13  sub     rsp, 130h
0x18004be1a  mov     rax, cs:__security_cookie
0x18004be21  xor     rax, rsp
0x18004be24  mov     [rsp+158h+var_38], rax
0x18004be2c  mov     r14, [rsp+158h+arg_20]
0x18004be34  mov     rbp, rdx
0x18004be37  mov     rsi, [rsp+158h+arg_30]
0x18004be3f  mov     ebx, ecx
0x18004be41  mov     edi, r8d
0x18004be44  lea     rcx, [rsp+158h+var_124]; void *
0x18004be49  xor     edx, edx; Val
0x18004be4b  mov     r8d, 0ECh; Size
0x18004be51  call    memset_0
0x18004be56  xor     edx, edx
0x18004be58  mov     [rsp+158h+var_128], ebx
0x18004be5c  lea     rcx, [rsp+158h+var_128]
0x18004be61  call    HashpInitHash
0x18004be66  test    eax, eax
0x18004be68  js      short loc_18004BEAC
0x18004be6a  mov     r8d, [rsp+158h+arg_28]
0x18004be72  lea     rcx, [rsp+158h+var_128]
0x18004be77  mov     r9, rbp
0x18004be7a  mov     [rsp+158h+var_138], edi
0x18004be7e  mov     rdx, r14
0x18004be81  call    HashpEmitExcludeRange
0x18004be86  mov     r8d, 1000h
0x18004be8c  cmp     edi, r8d
0x18004be8f  jz      short loc_18004BE9D
0x18004be91  mov     edx, edi
0x18004be93  lea     rcx, [rsp+158h+var_128]
0x18004be98  call    HashpPadHash
0x18004be9d  mov     rdx, rsi
0x18004bea0  lea     rcx, [rsp+158h+var_128]
0x18004bea5  call    HashpFinalizeHash
0x18004beaa  xor     eax, eax
0x18004beac  mov     rcx, [rsp+158h+var_38]
0x18004beb4  xor     rcx, rsp; StackCookie
0x18004beb7  call    __security_check_cookie
0x18004bebc  add     rsp, 130h
0x18004bec3  pop     r14
0x18004bec5  pop     rdi
0x18004bec6  pop     rsi
0x18004bec7  pop     rbp
0x18004bec8  pop     rbx
0x18004bec9  retn
```
