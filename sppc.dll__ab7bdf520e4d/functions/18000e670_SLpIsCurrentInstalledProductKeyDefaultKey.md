# SLpIsCurrentInstalledProductKeyDefaultKey

- ea: `0x18000e670`
- end: `0x18000e770`
- name: `SLpIsCurrentInstalledProductKeyDefaultKey`
- size: `256`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `9`
- tags: `installer_update`

## callees

- `0x180001760`
- `0x180001ec0`
- `0x180002bf0`
- `0x1800044dc`
- `0x180005208`
- `0x180006844`
- `0x180008b88`
- `0x18000a8d0`
- `0x18000e670`

## pseudocode

```c
__int64 __fastcall SLpIsCurrentInstalledProductKeyDefaultKey(__int64 a1, __int64 a2)
{
  __int64 v3; // rcx
  int v4; // ebx
  __int64 v6; // [rsp+30h] [rbp-28h] BYREF
  __int128 *v7; // [rsp+38h] [rbp-20h]
  __int128 v8; // [rsp+40h] [rbp-18h] BYREF

  v8 = 0;
  v6 = (__int64)&v8 + 8;
  v7 = &v8;
  if ( !a1 )
  {
    v3 = 2147942487LL;
    v4 = -2147024809;
LABEL_10:
    sub_180006844(v3);
    goto LABEL_11;
  }
  if ( a2 )
  {
    v4 = sub_1800044DC(&v6, a1, 0x36u, 1, 1);
    sub_180001760(qword_1800187D8, &dword_18001E9DC);
    if ( v4 < 0 )
      goto LABEL_9;
    v4 = sub_180008B88(v7, 1, 4, a2);
    sub_180001EC0(qword_180019108, qword_18001E798);
    if ( v4 < 0 )
      sub_180006844((unsigned int)v4);
    sub_18000A8D0((unsigned int)v4);
    if ( v4 < 0 )
    {
LABEL_9:
      v3 = (unsigned int)v4;
      goto LABEL_10;
    }
  }
  else
  {
    v4 = -2147024809;
    sub_180006844(2147942487LL);
    sub_180002BF0(&dword_180018444, qword_18001E630);
  }
LABEL_11:
  sub_18000A8D0((unsigned int)v4);
  sub_180005208(&v6);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18000e670  mov     r11, rsp
0x18000e673  mov     [r11+8], rbx
0x18000e677  push    rdi
0x18000e678  sub     rsp, 50h
0x18000e67c  lea     rax, [r11-10h]
0x18000e680  xorps   xmm0, xmm0
0x18000e683  mov     rdi, rdx
0x18000e686  movdqu  [rsp+58h+var_18], xmm0
0x18000e68c  mov     [r11-28h], rax
0x18000e690  lea     rax, [r11-18h]
0x18000e694  mov     [r11-20h], rax
0x18000e698  test    rcx, rcx
0x18000e69b  jnz     short loc_18000E6A9
0x18000e69d  mov     ecx, 80070057h
0x18000e6a2  mov     ebx, ecx
0x18000e6a4  jmp     loc_18000E74D
0x18000e6a9  test    rdi, rdi
0x18000e6ac  jnz     short loc_18000E6D2
0x18000e6ae  mov     ecx, 80070057h
0x18000e6b3  mov     ebx, ecx
0x18000e6b5  call    sub_180006844
0x18000e6ba  lea     rdx, qword_18001E630
0x18000e6c1  lea     rcx, dword_180018444
0x18000e6c8  call    sub_180002BF0
0x18000e6cd  jmp     loc_18000E752
0x18000e6d2  mov     r9d, 1
0x18000e6d8  mov     [rsp+58h+var_38], 1
0x18000e6e0  mov     rdx, rcx
0x18000e6e3  lea     rcx, [rsp+58h+var_28]
0x18000e6e8  lea     r8d, [r9+35h]
0x18000e6ec  call    sub_1800044DC
0x18000e6f1  lea     rdx, dword_18001E9DC
0x18000e6f8  mov     ebx, eax
0x18000e6fa  lea     rcx, qword_1800187D8
0x18000e701  call    sub_180001760
0x18000e706  test    ebx, ebx
0x18000e708  js      short loc_18000E74B
0x18000e70a  mov     rcx, [rsp+58h+var_20]
0x18000e70f  mov     edx, 1
0x18000e714  mov     r9, rdi
0x18000e717  lea     r8d, [rdx+3]
0x18000e71b  call    sub_180008B88
0x18000e720  lea     rdx, qword_18001E798
0x18000e727  mov     ebx, eax
0x18000e729  lea     rcx, qword_180019108
0x18000e730  call    sub_180001EC0
0x18000e735  test    ebx, ebx
0x18000e737  jns     short loc_18000E740
0x18000e739  mov     ecx, ebx
0x18000e73b  call    sub_180006844
0x18000e740  mov     ecx, ebx
0x18000e742  call    sub_18000A8D0
0x18000e747  test    ebx, ebx
0x18000e749  jns     short loc_18000E752
0x18000e74b  mov     ecx, ebx
0x18000e74d  call    sub_180006844
0x18000e752  mov     ecx, ebx
0x18000e754  call    sub_18000A8D0
0x18000e759  lea     rcx, [rsp+58h+var_28]
0x18000e75e  call    sub_180005208
0x18000e763  mov     eax, ebx
0x18000e765  mov     rbx, [rsp+58h+arg_0]
0x18000e76a  add     rsp, 50h
0x18000e76e  pop     rdi
0x18000e76f  retn
```
