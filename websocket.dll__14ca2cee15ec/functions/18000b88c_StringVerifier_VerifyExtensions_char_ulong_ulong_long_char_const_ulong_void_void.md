# StringVerifier::VerifyExtensions(char *,ulong,ulong,long (*)(char const *,ulong,void *),void *)

- ea: `0x18000b88c`
- end: `0x18000b8d1`
- name: `?VerifyExtensions@StringVerifier@@SAJPEADKKP6AJPEBDKPEAX@Z2@Z`
- size: `69`
- prototype: `__int64 __fastcall(char *, int, unsigned int, __int64 (__fastcall *)(__int64, unsigned __int64, __int64), void *)`
- caller_count: `4`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800093c4`
- `0x180009780`
- `0x18000a438`
- `0x18000a9a0`

## callees

- `0x18000b8d8`

## pseudocode

```c
__int64 __fastcall StringVerifier::VerifyExtensions(
        char *a1,
        int a2,
        unsigned int a3,
        __int64 (__fastcall *a4)(__int64, unsigned __int64, __int64),
        void *a5)
{
  _QWORD v6[5]; // [rsp+30h] [rbp-28h] BYREF

  v6[0] = a1;
  v6[2] = &a1[a2];
  v6[1] = a1;
  return StringVerifier::VerifyList(
           (StringVerifier *)v6,
           0xD0000036,
           (unsigned int (__fastcall *)(StringVerifier *))StringVerifier::TryDecodeExtension,
           a3,
           a4,
           (__int64)a5);
}

```

## disassembly

```asm
0x18000b88c  mov     r11, rsp
0x18000b88f  sub     rsp, 58h
0x18000b893  mov     eax, edx
0x18000b895  mov     edx, 0D0000036h; uID
0x18000b89a  add     rax, rcx
0x18000b89d  mov     [r11-28h], rcx
0x18000b8a1  mov     [r11-18h], rax
0x18000b8a5  mov     rax, [rsp+58h+arg_20]
0x18000b8ad  mov     [r11-30h], rax
0x18000b8b1  mov     [r11-38h], r9
0x18000b8b5  mov     r9d, r8d
0x18000b8b8  mov     [r11-20h], rcx
0x18000b8bc  lea     r8, ?TryDecodeExtension@StringVerifier@@AEAAHXZ; StringVerifier::TryDecodeExtension(void)
0x18000b8c3  lea     rcx, [r11-28h]; this
0x18000b8c7  call    ?VerifyList@StringVerifier@@AEAAJKP81@EAAHXZKP6AJPEBDKPEAX@Z2@Z; StringVerifier::VerifyList(ulong,int (StringVerifier::*)(void),ulong,long (*)(char const *,ulong,void *),void *)
0x18000b8cc  add     rsp, 58h
0x18000b8d0  retn
```
