# MincryptIsEKUInPolicy

- ea: `0x180018a6c`
- end: `0x180018b40`
- name: `MincryptIsEKUInPolicy`
- size: `212`
- prototype: ``
- caller_count: `7`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180012308`
- `0x180045d9c`
- `0x18004784c`
- `0x180047914`
- `0x180047940`
- `0x18004840c`
- `0x18004a364`

## callees

- `0x180018a6c`
- `0x18003391a`
- `0x180033980`
- `0x18004fac0`

## pseudocode

```c
bool __fastcall MincryptIsEKUInPolicy(__int64 a1, __int64 a2)
{
  bool v2; // zf
  __int64 v4; // rax
  unsigned int v5; // ebx
  unsigned int v6; // edi
  __int64 v7; // rsi
  unsigned int v8; // eax
  _DWORD v10[2]; // [rsp+20h] [rbp-A8h] BYREF
  void *Buf1; // [rsp+28h] [rbp-A0h]
  char v12; // [rsp+30h] [rbp-98h] BYREF

  v2 = *(_DWORD *)a1 == 0;
  v10[1] = 0;
  if ( v2 )
    return 0;
  if ( !*(_QWORD *)(a1 + 16) )
    return 0;
  if ( (*(_DWORD *)(a1 + 8) & 0xFFFF0000) != 0 )
    return 0;
  v10[0] = 127;
  Buf1 = &v12;
  if ( (int)MinAsn1StringToOid(a2, v10) < 0 )
    return 0;
  v4 = *(_QWORD *)(a1 + 16);
  v5 = 0;
  v6 = *(_DWORD *)(v4 + 32);
  if ( v6 )
  {
    v7 = *(_QWORD *)(v4 + 24);
    do
    {
      v8 = *(_DWORD *)(v7 + 16LL * v5);
      if ( v8 == v10[0] && !memcmp_0(Buf1, *(const void **)(v7 + 16LL * v5 + 8), v8) )
        break;
      ++v5;
    }
    while ( v5 < v6 );
  }
  return v5 != v6;
}

```

## disassembly

```asm
0x180018a6c  mov     [rsp+arg_0], rbx
0x180018a71  mov     [rsp+arg_10], rsi
0x180018a76  push    rdi
0x180018a77  sub     rsp, 0C0h
0x180018a7e  mov     rax, cs:__security_cookie
0x180018a85  xor     rax, rsp
0x180018a88  mov     [rsp+0C8h+var_18], rax
0x180018a90  cmp     dword ptr [rcx], 0
0x180018a93  mov     r8, rdx
0x180018a96  mov     rdi, rcx
0x180018a99  mov     [rsp+0C8h+var_A4], 0
0x180018aa1  jz      short loc_180018B18
0x180018aa3  cmp     qword ptr [rcx+10h], 0
0x180018aa8  jz      short loc_180018B18
0x180018aaa  test    dword ptr [rcx+8], 0FFFF0000h
0x180018ab1  jnz     short loc_180018B18
0x180018ab3  lea     rax, [rsp+0C8h+var_98]
0x180018ab8  mov     [rsp+0C8h+var_A8], 7Fh
0x180018ac0  lea     rdx, [rsp+0C8h+var_A8]
0x180018ac5  mov     [rsp+0C8h+Buf1], rax
0x180018aca  mov     rcx, r8
0x180018acd  call    MinAsn1StringToOid
0x180018ad2  test    eax, eax
0x180018ad4  js      short loc_180018B18
0x180018ad6  mov     rax, [rdi+10h]
0x180018ada  xor     ebx, ebx
0x180018adc  mov     edi, [rax+20h]
0x180018adf  test    edi, edi
0x180018ae1  jz      short loc_180018B11
0x180018ae3  mov     rsi, [rax+18h]
0x180018ae7  mov     edx, ebx
0x180018ae9  add     rdx, rdx
0x180018aec  mov     eax, [rsi+rdx*8]
0x180018aef  cmp     eax, [rsp+0C8h+var_A8]
0x180018af3  jnz     short loc_180018B0B
0x180018af5  mov     rdx, [rsi+rdx*8+8]; Buf2
0x180018afa  mov     r8d, eax; Size
0x180018afd  mov     rcx, [rsp+0C8h+Buf1]; Buf1
0x180018b02  call    memcmp_0
0x180018b07  test    eax, eax
0x180018b09  jz      short loc_180018B11
0x180018b0b  inc     ebx
0x180018b0d  cmp     ebx, edi
0x180018b0f  jb      short loc_180018AE7
0x180018b11  cmp     ebx, edi
0x180018b13  setnz   al
0x180018b16  jmp     short loc_180018B1A
0x180018b18  xor     al, al
0x180018b1a  mov     rcx, [rsp+0C8h+var_18]
0x180018b22  xor     rcx, rsp; StackCookie
0x180018b25  call    __security_check_cookie
0x180018b2a  lea     r11, [rsp+0C8h+var_8]
0x180018b32  mov     rbx, [r11+10h]
0x180018b36  mov     rsi, [r11+20h]
0x180018b3a  mov     rsp, r11
0x180018b3d  pop     rdi
0x180018b3e  retn
```
