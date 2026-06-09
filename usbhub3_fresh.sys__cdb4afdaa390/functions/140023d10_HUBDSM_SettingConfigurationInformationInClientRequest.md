# HUBDSM_SettingConfigurationInformationInClientRequest

- ea: `0x140023d10`
- end: `0x140023eae`
- name: `HUBDSM_SettingConfigurationInformationInClientRequest`
- size: `414`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config`

## callees

- `0x1400067ac`
- `0x140023d10`
- `0x140045530`
- `0x140045570`

## pseudocode

```c
__int64 __fastcall HUBDSM_SettingConfigurationInformationInClientRequest(__int64 a1)
{
  __int64 *v1; // r12
  __int64 v2; // rdx
  unsigned __int16 *v3; // rbp
  _QWORD *v4; // r15
  _QWORD *i; // rax
  __int64 v6; // r13
  int v7; // edx
  int v8; // edi
  __int64 v9; // rbx
  _QWORD *v10; // rsi
  __int64 v12; // [rsp+30h] [rbp-98h]
  __int64 v13; // [rsp+38h] [rbp-90h]
  _QWORD *v14; // [rsp+40h] [rbp-88h]
  _OWORD v15[2]; // [rsp+48h] [rbp-80h] BYREF
  __int64 v16; // [rsp+68h] [rbp-60h]

  v1 = *(__int64 **)(a1 + 960);
  memset(v15, 0, sizeof(v15));
  v2 = v1[58];
  v12 = *v1;
  v16 = 0;
  LOWORD(v15[0]) = 40;
  (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, _OWORD *))(WdfFunctions_01015 + 2128))(
    WdfDriverGlobals,
    v2,
    v15);
  v3 = (unsigned __int16 *)(*((_QWORD *)&v15[0] + 1) + 40LL);
  v4 = (_QWORD *)(v1[6] + 16);
  v14 = v4;
  for ( i = (_QWORD *)*v4; ; i = (_QWORD *)v10[1] )
  {
    v10 = i - 1;
    if ( v4 == i )
      break;
    v6 = 0;
    if ( *((_DWORD *)v10 + 6) )
    {
      do
      {
        v13 = (*(__int64 (__fastcall **)(_QWORD))(v12 + 480))(v10[10 * v6 + 5]);
        if ( !v13 && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v7) = 2;
          WPP_RECORDER_SF_(
            *(_QWORD *)(v1[1] + 1432),
            v7,
            5,
            44,
            (__int64)WPP_dde998bf8bb3310d95d4227a99ba80b7_Traceguids);
        }
        v8 = (*(__int64 (__fastcall **)(_QWORD))(v12 + 488))(v10[10 * v6 + 5]);
        v9 = 3 * v6;
        v10[10 * v6 + 7] = v13;
        *(_QWORD *)&v3[12 * v6 + 16] = v13;
        (*(void (__fastcall **)(_QWORD))(v12 + 472))(v10[10 * v6 + 5]);
        v6 = (unsigned int)(v6 + 1);
        *(_DWORD *)&v3[4 * v9 + 20] = v8;
      }
      while ( (unsigned int)v6 < *((_DWORD *)v10 + 6) );
      v4 = v14;
    }
    v3 = (unsigned __int16 *)((char *)v3 + *v3);
  }
  return 4077;
}

```

## disassembly

```asm
0x140023d10  push    rbx
0x140023d12  push    rbp
0x140023d13  push    rsi
0x140023d14  push    rdi
0x140023d15  push    r12
0x140023d17  push    r13
0x140023d19  push    r14
0x140023d1b  push    r15
0x140023d1d  sub     rsp, 88h
0x140023d24  mov     rax, cs:__security_cookie
0x140023d2b  xor     rax, rsp
0x140023d2e  mov     [rsp+0C8h+var_58], rax
0x140023d33  mov     r12, [rcx+3C0h]
0x140023d3a  lea     r8, [rsp+0C8h+var_80]
0x140023d3f  mov     rcx, cs:WdfDriverGlobals
0x140023d46  xorps   xmm0, xmm0
0x140023d49  movups  [rsp+0C8h+var_80], xmm0
0x140023d4e  mov     rax, [r12]
0x140023d52  mov     rdx, [r12+1D0h]
0x140023d5a  mov     [rsp+0C8h+var_98], rax
0x140023d5f  xor     eax, eax
0x140023d61  mov     [rsp+0C8h+var_60], rax
0x140023d66  mov     eax, 28h ; '('
0x140023d6b  mov     word ptr [rsp+0C8h+var_80], ax
0x140023d70  mov     rax, cs:WdfFunctions_01015
0x140023d77  movups  [rsp+0C8h+var_70], xmm0
0x140023d7c  mov     rax, [rax+850h]
0x140023d83  call    _guard_dispatch_icall
0x140023d88  mov     rbp, qword ptr [rsp+0C8h+var_80+8]
0x140023d8d  mov     r15, [r12+30h]
0x140023d92  add     rbp, 28h ; '('
0x140023d96  add     r15, 10h
0x140023d9a  mov     [rsp+0C8h+var_88], r15
0x140023d9f  mov     rax, [r15]
0x140023da2  jmp     loc_140023E7A
0x140023da7  xor     r13d, r13d
0x140023daa  cmp     [rsi+18h], r13d
0x140023dae  jbe     loc_140023E6F
0x140023db4  mov     r15, [rsp+0C8h+var_98]
0x140023db9  mov     rax, [r15+1E0h]
0x140023dc0  lea     r14, ds:0[r13*4]
0x140023dc8  add     r14, r13
0x140023dcb  add     r14, r14
0x140023dce  mov     rcx, [rsi+r14*8+28h]
0x140023dd3  call    _guard_dispatch_icall
0x140023dd8  mov     [rsp+0C8h+var_90], rax
0x140023ddd  test    rax, rax
0x140023de0  jnz     short loc_140023E1B
0x140023de2  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140023de9  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140023df0  jz      short loc_140023E1B
0x140023df2  mov     rcx, [r12+8]
0x140023df7  lea     rax, WPP_dde998bf8bb3310d95d4227a99ba80b7_Traceguids
0x140023dfe  mov     r9d, 2Ch ; ','
0x140023e04  mov     [rsp+0C8h+var_A8], rax
0x140023e09  mov     dl, 2
0x140023e0b  mov     rcx, [rcx+598h]
0x140023e12  lea     r8d, [r9-27h]
0x140023e16  call    WPP_RECORDER_SF_
0x140023e1b  mov     rax, [r15+1E8h]
0x140023e22  mov     rcx, [rsi+r14*8+28h]
0x140023e27  call    _guard_dispatch_icall
0x140023e2c  mov     edi, eax
0x140023e2e  lea     rbx, ds:0[r13*2]
0x140023e36  mov     rax, [rsp+0C8h+var_90]
0x140023e3b  add     rbx, r13
0x140023e3e  mov     [rsi+r14*8+38h], rax
0x140023e43  mov     [rbp+rbx*8+20h], rax
0x140023e48  mov     rax, [r15+1D8h]
0x140023e4f  mov     rcx, [rsi+r14*8+28h]
0x140023e54  call    _guard_dispatch_icall
0x140023e59  inc     r13d
0x140023e5c  mov     [rbp+rbx*8+28h], edi
0x140023e60  cmp     r13d, [rsi+18h]
0x140023e64  jb      loc_140023DB9
0x140023e6a  mov     r15, [rsp+0C8h+var_88]
0x140023e6f  movzx   eax, word ptr [rbp+0]
0x140023e73  add     rbp, rax
0x140023e76  mov     rax, [rsi+8]
0x140023e7a  lea     rsi, [rax-8]
0x140023e7e  cmp     r15, rax
0x140023e81  jnz     loc_140023DA7
0x140023e87  mov     eax, 0FEDh
0x140023e8c  mov     rcx, [rsp+0C8h+var_58]
0x140023e91  xor     rcx, rsp; StackCookie
0x140023e94  call    __security_check_cookie
0x140023e99  add     rsp, 88h
0x140023ea0  pop     r15
0x140023ea2  pop     r14
0x140023ea4  pop     r13
0x140023ea6  pop     r12
0x140023ea8  pop     rdi
0x140023ea9  pop     rsi
0x140023eaa  pop     rbp
0x140023eab  pop     rbx
0x140023eac  retn
```
