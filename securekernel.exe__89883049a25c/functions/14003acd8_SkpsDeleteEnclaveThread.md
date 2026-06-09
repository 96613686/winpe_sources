# SkpsDeleteEnclaveThread

- ea: `0x14003acd8`
- end: `0x14003adc2`
- name: `SkpsDeleteEnclaveThread`
- size: `234`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `5`
- callee_count: `9`
- tags: ``

## callers

- `0x140014dd0`
- `0x14003aacc`
- `0x140098654`
- `0x140098898`
- `0x1400999cc`

## callees

- `0x1400010f0`
- `0x1400024b0`
- `0x140002e40`
- `0x140034c28`
- `0x14003acd8`
- `0x1400b0b38`
- `0x1400ee8b0`
- `0x1400f3620`
- `0x1400f9a80`

## pseudocode

```c
__int64 __fastcall SkpsDeleteEnclaveThread(__int64 a1)
{
  __int64 v1; // rbp
  __int64 v3; // r14
  char v4; // bl
  __int64 v5; // rdx
  __int64 v6; // rbx
  unsigned int v8; // [rsp+20h] [rbp-98h] BYREF
  __int64 v9; // [rsp+28h] [rbp-90h]

  v1 = *(_QWORD *)(a1 + 72);
  SkpspDeleteThread();
  if ( (*(_DWORD *)(a1 + 172) & 0x800) != 0 )
  {
    v3 = *(_QWORD *)(a1 + 296);
    if ( v3 )
    {
      v4 = SkAcquireSpinLockExclusive(v1 + 4);
      RtlAvlRemoveNode(v1 + 264, v3);
      LOBYTE(v5) = v4;
      SkReleaseSpinLockExclusive(v1 + 4, v5);
      *(_QWORD *)(a1 + 296) = 0;
    }
  }
  if ( !*(_DWORD *)(v1 + 188) )
  {
    v6 = *(_QWORD *)(v1 + 248);
    if ( v6 )
    {
      memset_0(&v8, 0, 0x68u);
      v9 = v6;
      HIWORD(v8) = 37;
      SkCallNormalMode(&v8);
    }
  }
  return SkpspDeleteEnclaveThread(a1);
}

```

## disassembly

```asm
0x14003acd8  mov     [rsp+arg_8], rbx
0x14003acdd  mov     [rsp+arg_10], rbp
0x14003ace2  push    rsi
0x14003ace3  push    rdi
0x14003ace4  push    r14
0x14003ace6  sub     rsp, 0A0h
0x14003aced  mov     rax, cs:__security_cookie
0x14003acf4  xor     rax, rsp
0x14003acf7  mov     [rsp+0B8h+var_28], rax
0x14003acff  mov     rbp, [rcx+48h]
0x14003ad03  mov     rsi, rcx
0x14003ad06  call    SkpspDeleteThread
0x14003ad0b  test    dword ptr [rsi+0ACh], 800h
0x14003ad15  jz      short loc_14003AD53
0x14003ad17  mov     r14, [rsi+128h]
0x14003ad1e  test    r14, r14
0x14003ad21  jz      short loc_14003AD53
0x14003ad23  lea     rcx, [rbp+4]
0x14003ad27  call    SkAcquireSpinLockExclusive
0x14003ad2c  lea     rcx, [rbp+108h]
0x14003ad33  mov     rdx, r14
0x14003ad36  mov     bl, al
0x14003ad38  call    RtlAvlRemoveNode
0x14003ad3d  mov     dl, bl
0x14003ad3f  lea     rcx, [rbp+4]
0x14003ad43  call    SkReleaseSpinLockExclusive
0x14003ad48  mov     qword ptr [rsi+128h], 0
0x14003ad53  cmp     dword ptr [rbp+0BCh], 0
0x14003ad5a  jnz     short loc_14003AD91
0x14003ad5c  mov     rbx, [rbp+0F8h]
0x14003ad63  test    rbx, rbx
0x14003ad66  jz      short loc_14003AD91
0x14003ad68  xor     edx, edx; Val
0x14003ad6a  lea     rcx, [rsp+0B8h+var_98]; void *
0x14003ad6f  lea     r8d, [rdx+68h]; Size
0x14003ad73  call    memset_0
0x14003ad78  mov     eax, 25h ; '%'
0x14003ad7d  mov     [rsp+0B8h+var_90], rbx
0x14003ad82  lea     rcx, [rsp+0B8h+var_98]
0x14003ad87  mov     [rsp+0B8h+var_96], ax
0x14003ad8c  call    SkCallNormalMode
0x14003ad91  mov     rcx, rsi
0x14003ad94  call    SkpspDeleteEnclaveThread
0x14003ad99  mov     rcx, [rsp+0B8h+var_28]
0x14003ada1  xor     rcx, rsp; StackCookie
0x14003ada4  call    __security_check_cookie
0x14003ada9  lea     r11, [rsp+0B8h+var_18]
0x14003adb1  mov     rbx, [r11+28h]
0x14003adb5  mov     rbp, [r11+30h]
0x14003adb9  mov     rsp, r11
0x14003adbc  pop     r14
0x14003adbe  pop     rdi
0x14003adbf  pop     rsi
0x14003adc0  retn
```
