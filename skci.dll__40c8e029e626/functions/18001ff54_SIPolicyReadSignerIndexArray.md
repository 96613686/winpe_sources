# SIPolicyReadSignerIndexArray

- ea: `0x18001ff54`
- end: `0x180020029`
- name: `SIPolicyReadSignerIndexArray`
- size: `213`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x18001e674`

## callees

- `0x180010a88`
- `0x1800187d4`
- `0x18001ff54`
- `0x180020518`
- `0x1800217b0`

## pseudocode

```c
__int64 __fastcall SIPolicyReadSignerIndexArray(__int64 a1, unsigned int a2, unsigned int *a3, __int64 *a4)
{
  __int64 v4; // rdi
  NTSTATUS SecureSettingValueType; // ebx
  unsigned int v9; // esi
  unsigned int i; // ebp
  unsigned int v12; // [rsp+20h] [rbp-58h] BYREF
  ULONG pulResult[21]; // [rsp+24h] [rbp-54h] BYREF

  pulResult[0] = 0;
  v4 = 0;
  v12 = 0;
  SecureSettingValueType = SIPolicyReadSecureSettingValueType(a1, &v12);
  if ( SecureSettingValueType >= 0 )
  {
    v9 = v12;
    if ( v12 )
    {
      SecureSettingValueType = RtlULongLongToULong(4LL * v12, pulResult);
      if ( SecureSettingValueType >= 0 )
      {
        v4 = SIPolicyAlloc(pulResult[0]);
        if ( v4 )
        {
          for ( i = 0; i < v9; ++i )
          {
            SecureSettingValueType = SIPolicyReadSecureSettingValueType(a1, v4 + 4LL * i);
            if ( SecureSettingValueType < 0 )
              goto LABEL_14;
            if ( *(_DWORD *)(v4 + 4LL * i) >= a2 )
            {
              SecureSettingValueType = -1058471933;
              goto LABEL_14;
            }
          }
          *a4 = v4;
          v4 = 0;
          *a3 = v9;
        }
        else
        {
          SecureSettingValueType = -1073741801;
        }
      }
    }
    else
    {
      *a4 = 0;
      *a3 = 0;
    }
  }
LABEL_14:
  SIPolicyFree(v4);
  return (unsigned int)SecureSettingValueType;
}

```

## disassembly

```asm
0x18001ff54  mov     rax, rsp
0x18001ff57  mov     [rax+10h], edx
0x18001ff5a  push    rbx
0x18001ff5b  push    rbp
0x18001ff5c  push    rsi
0x18001ff5d  push    rdi
0x18001ff5e  push    r12
0x18001ff60  push    r13
0x18001ff62  push    r14
0x18001ff64  push    r15
0x18001ff66  sub     rsp, 38h
0x18001ff6a  xor     r12d, r12d
0x18001ff6d  lea     rdx, [rax-58h]
0x18001ff71  mov     [rax-54h], r12d
0x18001ff75  mov     edi, r12d
0x18001ff78  mov     [rax-58h], r12d
0x18001ff7c  mov     r14, r9
0x18001ff7f  mov     r15, r8
0x18001ff82  mov     r13, rcx
0x18001ff85  call    SIPolicyReadSecureSettingValueType
0x18001ff8a  mov     ebx, eax
0x18001ff8c  test    eax, eax
0x18001ff8e  js      short loc_18002000D
0x18001ff90  mov     esi, [rsp+78h+var_58]
0x18001ff94  test    esi, esi
0x18001ff96  jnz     short loc_18001FFA0
0x18001ff98  mov     [r14], r12
0x18001ff9b  mov     [r15], r12d
0x18001ff9e  jmp     short loc_18002000D
0x18001ffa0  mov     rcx, rsi
0x18001ffa3  lea     rdx, [rsp+78h+pulResult]; pulResult
0x18001ffa8  shl     rcx, 2; ullOperand
0x18001ffac  call    RtlULongLongToULong
0x18001ffb1  mov     ebx, eax
0x18001ffb3  test    eax, eax
0x18001ffb5  js      short loc_18002000D
0x18001ffb7  mov     ecx, [rsp+78h+pulResult]; Size
0x18001ffbb  call    SIPolicyAlloc
0x18001ffc0  mov     rdi, rax
0x18001ffc3  test    rax, rax
0x18001ffc6  jnz     short loc_18001FFCF
0x18001ffc8  mov     ebx, 0C0000017h
0x18001ffcd  jmp     short loc_18002000D
0x18001ffcf  mov     ebp, r12d
0x18001ffd2  cmp     ebp, esi
0x18001ffd4  jnb     short loc_180020005
0x18001ffd6  mov     eax, ebp
0x18001ffd8  mov     rcx, r13
0x18001ffdb  lea     r12, [rdi+rax*4]
0x18001ffdf  mov     rdx, r12
0x18001ffe2  call    SIPolicyReadSecureSettingValueType
0x18001ffe7  mov     ebx, eax
0x18001ffe9  test    eax, eax
0x18001ffeb  js      short loc_18002000D
0x18001ffed  mov     eax, [rsp+78h+arg_8]
0x18001fff4  cmp     [r12], eax
0x18001fff8  jnb     short loc_18001FFFE
0x18001fffa  inc     ebp
0x18001fffc  jmp     short loc_18001FFD2
0x18001fffe  mov     ebx, 0C0E90003h
0x180020003  jmp     short loc_18002000D
0x180020005  mov     [r14], rdi
0x180020008  xor     edi, edi
0x18002000a  mov     [r15], esi
0x18002000d  mov     rcx, rdi
0x180020010  call    SIPolicyFree
0x180020015  mov     eax, ebx
0x180020017  add     rsp, 38h
0x18002001b  pop     r15
0x18002001d  pop     r14
0x18002001f  pop     r13
0x180020021  pop     r12
0x180020023  pop     rdi
0x180020024  pop     rsi
0x180020025  pop     rbp
0x180020026  pop     rbx
0x180020027  retn
```
