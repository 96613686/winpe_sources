# I_IsRoleAuthenticated(VCHANNEL_DATA const *,_CARD_ROLE)

- ea: `0x18000a110`
- end: `0x18000a1b2`
- name: `?I_IsRoleAuthenticated@@YAHPEBUVCHANNEL_DATA@@W4_CARD_ROLE@@@Z`
- size: `162`
- prototype: `__int64 __fastcall(__int64, int)`
- caller_count: `22`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18000a1b8`
- `0x1800183b8`
- `0x180018ca0`
- `0x1800198a8`
- `0x18001a49c`
- `0x18001f558`
- `0x18001fd8c`
- `0x180021f84`
- `0x180022ad8`
- `0x180023078`
- `0x180023e54`
- `0x180024378`
- `0x180024aac`
- `0x18002cd7c`
- `0x18002d1f4`
- `0x18002d588`
- `0x18002d830`
- `0x18002d9d8`
- `0x18002dbb4`
- `0x18002e600`
- `0x18002ea60`
- `0x18002f100`

## callees

- `0x180001ec0`
- `0x180006794`
- `0x1800074d8`
- `0x18000a110`
- `0x1800348a0`

## pseudocode

```c
__int64 __fastcall I_IsRoleAuthenticated(__int64 a1, int a2)
{
  unsigned int v4; // ebx
  __int64 v5; // rdx
  __int64 v6; // rcx
  int v8; // [rsp+20h] [rbp-58h] BYREF
  unsigned int v9; // [rsp+24h] [rbp-54h] BYREF
  _QWORD *v10; // [rsp+28h] [rbp-50h] BYREF
  _QWORD v11[3]; // [rsp+30h] [rbp-48h] BYREF
  char v12[24]; // [rsp+48h] [rbp-30h] BYREF

  v4 = 0;
  v9 = 0;
  v8 = 0;
  strcpy(v12, "I_IsRoleAuthenticated");
  v11[0] = v12;
  v11[1] = &v8;
  v11[2] = &v9;
  lambda_c322a665e6916afadb7169fe0daa2c42_::operator()(v11);
  v8 = 1;
  v10 = v11;
  if ( !a1 )
    MicrosoftTelemetryAssertTriggeredNoArgs(v6, v5);
  LOBYTE(v4) = a2 == *(_DWORD *)(a1 + 64);
  v9 = v4;
  WppTraceUnwinder__lambda_c322a665e6916afadb7169fe0daa2c42____::_WppTraceUnwinder__lambda_c322a665e6916afadb7169fe0daa2c42____(&v10);
  return v4;
}

```

## disassembly

```asm
0x18000a110  push    rbp
0x18000a112  push    rbx
0x18000a113  push    rsi
0x18000a114  push    rdi
0x18000a115  mov     rbp, rsp
0x18000a118  sub     rsp, 78h
0x18000a11c  mov     rax, cs:__security_cookie
0x18000a123  xor     rax, rsp
0x18000a126  mov     [rbp+var_18], rax
0x18000a12a  mov     esi, edx
0x18000a12c  mov     rdi, rcx
0x18000a12f  xor     ebx, ebx
0x18000a131  mov     [rbp+var_54], ebx
0x18000a134  mov     [rbp+var_58], ebx
0x18000a137  movups  xmm0, xmmword ptr cs:aIIsroleauthent; "I_IsRoleAuthenticated"
0x18000a13e  movups  xmmword ptr [rbp+var_30], xmm0
0x18000a142  movsd   xmm1, qword ptr cs:aIIsroleauthent+0Eh; "ticated"
0x18000a14a  movsd   qword ptr [rbp+var_30+0Eh], xmm1
0x18000a14f  lea     rax, [rbp+var_30]
0x18000a153  mov     [rbp+var_48], rax
0x18000a157  lea     rax, [rbp+var_58]
0x18000a15b  mov     [rbp+var_40], rax
0x18000a15f  lea     rax, [rbp+var_54]
0x18000a163  mov     [rbp+var_38], rax
0x18000a167  lea     rcx, [rbp+var_48]
0x18000a16b  call    _lambda_c322a665e6916afadb7169fe0daa2c42___operator__
0x18000a170  mov     [rbp+var_58], 1
0x18000a177  lea     rax, [rbp+var_48]
0x18000a17b  mov     [rbp+var_50], rax
0x18000a17f  test    rdi, rdi
0x18000a182  jnz     short loc_18000A189
0x18000a184  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000a189  cmp     esi, [rdi+40h]
0x18000a18c  setz    bl
0x18000a18f  mov     [rbp+var_54], ebx
0x18000a192  lea     rcx, [rbp+var_50]
0x18000a196  call    WppTraceUnwinder__lambda_c322a665e6916afadb7169fe0daa2c42_______WppTraceUnwinder__lambda_c322a665e6916afadb7169fe0daa2c42____
0x18000a19b  mov     eax, ebx
0x18000a19d  mov     rcx, [rbp+var_18]
0x18000a1a1  xor     rcx, rsp; StackCookie
0x18000a1a4  call    __security_check_cookie
0x18000a1a9  add     rsp, 78h
0x18000a1ad  pop     rdi
0x18000a1ae  pop     rsi
0x18000a1af  pop     rbx
0x18000a1b0  pop     rbp
0x18000a1b1  retn
```
