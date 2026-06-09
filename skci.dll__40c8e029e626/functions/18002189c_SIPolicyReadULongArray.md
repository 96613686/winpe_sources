# SIPolicyReadULongArray

- ea: `0x18002189c`
- end: `0x180021919`
- name: `SIPolicyReadULongArray`
- size: `125`
- prototype: `int __fastcall(__int64 *, _DWORD *, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18001f1c0`

## callees

- `0x180020e5c`
- `0x180021710`
- `0x180021748`
- `0x18002189c`

## pseudocode

```c
int __fastcall SIPolicyReadULongArray(__int64 *a1, _DWORD *a2, _QWORD *a3)
{
  int result; // eax
  int v7; // r11d
  ULONGLONG pullResult[3]; // [rsp+20h] [rbp-18h] BYREF
  ULONGLONG ullMultiplier; // [rsp+58h] [rbp+20h] BYREF

  pullResult[0] = 0;
  LODWORD(ullMultiplier) = 0;
  result = SIPolicyReadPrimitive(a1, 4u, &ullMultiplier);
  if ( result >= 0 )
  {
    result = RtlULongLongMult(4u, (unsigned int)ullMultiplier, pullResult);
    if ( result >= 0 )
    {
      result = SIPolicyReadBytes(a1, pullResult[0], a3);
      if ( result >= 0 )
        *a2 = v7;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18002189c  mov     rax, rsp
0x18002189f  mov     [rax+8], rbx
0x1800218a3  mov     [rax+10h], rsi
0x1800218a7  push    rdi
0x1800218a8  sub     rsp, 30h
0x1800218ac  mov     rsi, r8
0x1800218af  mov     qword ptr [rax-18h], 0
0x1800218b7  mov     rbx, rdx
0x1800218ba  mov     dword ptr [rax+20h], 0
0x1800218c1  lea     r8, [rax+20h]
0x1800218c5  mov     edx, 4
0x1800218ca  mov     rdi, rcx
0x1800218cd  call    SIPolicyReadPrimitive
0x1800218d2  test    eax, eax
0x1800218d4  js      short loc_180021908
0x1800218d6  mov     r11d, dword ptr [rsp+38h+ullMultiplier]
0x1800218db  lea     r8, [rsp+38h+pullResult]; pullResult
0x1800218e0  mov     edx, r11d; ullMultiplier
0x1800218e3  mov     ecx, 4; ullMultiplicand
0x1800218e8  call    RtlULongLongMult
0x1800218ed  test    eax, eax
0x1800218ef  js      short loc_180021908
0x1800218f1  mov     rdx, [rsp+38h+pullResult]
0x1800218f6  mov     r8, rsi
0x1800218f9  mov     rcx, rdi
0x1800218fc  call    SIPolicyReadBytes
0x180021901  test    eax, eax
0x180021903  js      short loc_180021908
0x180021905  mov     [rbx], r11d
0x180021908  mov     rbx, [rsp+38h+arg_0]
0x18002190d  mov     rsi, [rsp+38h+arg_8]
0x180021912  add     rsp, 30h
0x180021916  pop     rdi
0x180021917  retn
```
