# RtlImageDirectoryEntryToData

- ea: `0x1400d64a4`
- end: `0x1400d64d6`
- name: `RtlImageDirectoryEntryToData`
- size: `50`
- prototype: ``
- caller_count: `15`
- callee_count: `1`
- tags: ``

## callers

- `0x14003ffbc`
- `0x14006c84c`
- `0x140079c60`
- `0x14007a358`
- `0x14007c13c`
- `0x1400a3ef0`
- `0x1400d9788`
- `0x1400d998c`
- `0x1400dcac4`
- `0x1400fcc24`
- `0x1400fe3f0`
- `0x1400fe7e0`
- `0x1400ff484`
- `0x1400ff518`
- `0x1400ff73c`

## callees

- `0x1400d67c0`

## pseudocode

```c
__int64 __fastcall RtlImageDirectoryEntryToData(int a1, int a2, int a3, int a4)
{
  int v4; // eax
  __int64 v5; // rdx
  _QWORD v7[3]; // [rsp+30h] [rbp-18h] BYREF

  v7[0] = 0;
  v4 = RtlpImageDirectoryEntryToDataEx(a1, a2, a3, a4, (__int64)v7);
  v5 = v7[0];
  if ( v4 < 0 )
    return 0;
  return v5;
}

```

## disassembly

```asm
0x1400d64a4  sub     rsp, 48h
0x1400d64a8  lea     rax, [rsp+48h+var_18]
0x1400d64ad  mov     [rsp+48h+var_18], 0
0x1400d64b6  mov     [rsp+48h+var_28], rax
0x1400d64bb  call    RtlpImageDirectoryEntryToDataEx
0x1400d64c0  mov     rdx, [rsp+48h+var_18]
0x1400d64c5  xor     ecx, ecx
0x1400d64c7  test    eax, eax
0x1400d64c9  cmovs   rdx, rcx
0x1400d64cd  mov     rax, rdx
0x1400d64d0  add     rsp, 48h
0x1400d64d4  retn
```
