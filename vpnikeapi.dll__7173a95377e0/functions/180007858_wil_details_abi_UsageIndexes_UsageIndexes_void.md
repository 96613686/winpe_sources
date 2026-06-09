# wil::details_abi::UsageIndexes::UsageIndexes(void)

- ea: `0x180007858`
- end: `0x1800078c6`
- name: `??0UsageIndexes@details_abi@wil@@QEAA@XZ`
- size: `110`
- prototype: `wil::details_abi::UsageIndexes *__fastcall(wil::details_abi::UsageIndexes *this, __int64, __int64, __int64)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180007730`
- `0x18000a028`
- `0x18000a65c`

## callees

- `0x18000779c`

## pseudocode

```c
wil::details_abi::UsageIndexes *__fastcall wil::details_abi::UsageIndexes::UsageIndexes(
        wil::details_abi::UsageIndexes *this,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  __int64 v5; // r9
  __int64 v6; // r9
  __int16 v7; // r11
  __int16 v9; // [rsp+20h] [rbp-18h]
  int v10; // [rsp+20h] [rbp-18h]
  int v11; // [rsp+20h] [rbp-18h]
  char v12; // [rsp+28h] [rbp-10h]
  int v13; // [rsp+28h] [rbp-10h]
  int v14; // [rsp+28h] [rbp-10h]

  v12 = 0;
  v9 = 4;
  LOBYTE(a4) = 1;
  wil::details_abi::RawUsageIndex::RawUsageIndex(this, 0, 4, a4, v9, v12);
  LOBYTE(v13) = 2;
  LOWORD(v10) = 4;
  wil::details_abi::RawUsageIndex::RawUsageIndex((char *)this + 64, 0, 4, v5, v10, v13);
  LOBYTE(v14) = v6;
  LOWORD(v11) = v7;
  wil::details_abi::RawUsageIndex::RawUsageIndex((char *)this + 128, 0, 4, v6, v11, v14);
  return this;
}

```

## disassembly

```asm
0x180007858  mov     [rsp+arg_0], rbx
0x18000785d  push    rdi
0x18000785e  sub     rsp, 30h
0x180007862  mov     edi, 4
0x180007867  xor     r11d, r11d
0x18000786a  mov     r8d, edi
0x18000786d  mov     byte ptr [rsp+38h+var_10], r11b
0x180007872  xor     edx, edx
0x180007874  mov     [rsp+38h+var_18], di
0x180007879  mov     r9b, 1
0x18000787c  mov     rbx, rcx
0x18000787f  call    ??0RawUsageIndex@details_abi@wil@@QEAA@GGW4CountSize@12@G0@Z; wil::details_abi::RawUsageIndex::RawUsageIndex(ushort,ushort,wil::details_abi::CountSize,ushort,wil::details_abi::CountSize)
0x180007884  mov     r8d, edi
0x180007887  mov     byte ptr [rsp+38h+var_10], 2
0x18000788c  xor     edx, edx
0x18000788e  mov     [rsp+38h+var_18], di
0x180007893  lea     rcx, [rbx+40h]
0x180007897  call    ??0RawUsageIndex@details_abi@wil@@QEAA@GGW4CountSize@12@G0@Z; wil::details_abi::RawUsageIndex::RawUsageIndex(ushort,ushort,wil::details_abi::CountSize,ushort,wil::details_abi::CountSize)
0x18000789c  mov     r8d, edi
0x18000789f  mov     byte ptr [rsp+38h+var_10], r9b
0x1800078a4  xor     edx, edx
0x1800078a6  mov     [rsp+38h+var_18], r11w
0x1800078ac  lea     rcx, [rbx+80h]
0x1800078b3  call    ??0RawUsageIndex@details_abi@wil@@QEAA@GGW4CountSize@12@G0@Z; wil::details_abi::RawUsageIndex::RawUsageIndex(ushort,ushort,wil::details_abi::CountSize,ushort,wil::details_abi::CountSize)
0x1800078b8  mov     rax, rbx
0x1800078bb  mov     rbx, [rsp+38h+arg_0]
0x1800078c0  add     rsp, 30h
0x1800078c4  pop     rdi
0x1800078c5  retn
```
