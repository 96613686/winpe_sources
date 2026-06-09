# WTSCloudAuthOpen

- ea: `0x18000ee50`
- end: `0x18000ee8d`
- name: `WTSCloudAuthOpen`
- size: `61`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000c010`
- `0x18000ea88`

## pseudocode

```c
__int64 __fastcall WTSCloudAuthOpen(__int64 a1)
{
  unsigned int v1; // eax
  _QWORD v3[3]; // [rsp+20h] [rbp-18h] BYREF
  __int64 v4; // [rsp+40h] [rbp+8h] BYREF
  __int64 v5; // [rsp+48h] [rbp+10h] BYREF

  v4 = a1;
  v5 = 0;
  v3[0] = &v4;
  v3[1] = &v5;
  v1 = lambda_82a4302735505f8ac93229f8917a4a7e_::operator()(v3);
  WTSCloudAuthSetLastError(v1);
  return v5;
}

```

## disassembly

```asm
0x18000ee50  mov     r11, rsp
0x18000ee53  mov     [r11+8], rcx
0x18000ee57  sub     rsp, 38h
0x18000ee5b  lea     rax, [r11+8]
0x18000ee5f  mov     qword ptr [r11+10h], 0
0x18000ee67  mov     [r11-18h], rax
0x18000ee6b  lea     rcx, [r11-18h]
0x18000ee6f  lea     rax, [r11+10h]
0x18000ee73  mov     [r11-10h], rax
0x18000ee77  call    _lambda_82a4302735505f8ac93229f8917a4a7e___operator__
0x18000ee7c  mov     ecx, eax
0x18000ee7e  call    _WTSCloudAuthSetLastError
0x18000ee83  mov     rax, [rsp+38h+arg_8]
0x18000ee88  add     rsp, 38h
0x18000ee8c  retn
```
