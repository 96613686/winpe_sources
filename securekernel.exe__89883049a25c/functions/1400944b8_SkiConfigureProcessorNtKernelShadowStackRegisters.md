# SkiConfigureProcessorNtKernelShadowStackRegisters

- ea: `0x1400944b8`
- end: `0x140094666`
- name: `SkiConfigureProcessorNtKernelShadowStackRegisters`
- size: `430`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x140092184`
- `0x140094e50`

## callees

- `0x140012380`
- `0x1400139c0`
- `0x1400944b8`
- `0x140095718`
- `0x1400957ac`
- `0x1400f3620`

## pseudocode

```c
__int64 __fastcall SkiConfigureProcessorNtKernelShadowStackRegisters(
        unsigned __int64 a1,
        __int64 a2,
        int a3,
        __int64 a4)
{
  __int64 result; // rax
  struct _EXCEPTION_REGISTRATION_RECORD *ExceptionList; // rbx
  __int128 v9; // [rsp+20h] [rbp-20h] BYREF

  v9 = 0;
  if ( (SkmiFlags & 0x80000) != 0 )
  {
    if ( a3 )
    {
      SkiSetRegister(524429, a4 + 448);
      *(_QWORD *)&v9 = a1;
      ((void (__fastcall *)(__int64, _QWORD, __int64, __int128 *))ShvlSetVpRegister)(4294967294LL, 0, 524430, &v9);
      SkiSetRegisterRaw(524431, a4 + 472, a1 + 8);
      SkiSetRegisterRaw(524435, a4 + 544, a2);
      SkiSetRegister(524432, a4 + 496);
      result = SkiSetRegister(524433, a4 + 520);
      if ( SkiNtFredEnabled )
      {
        ExceptionList = KeGetPcr()->NtTib.ExceptionList;
        SkiSetRegisterRaw(589925, a4 + 688, ExceptionList[188].Handler);
        SkiSetRegisterRaw(589926, a4 + 712, ExceptionList[187].Handler);
        return SkiSetRegister(589927, a4 + 736);
      }
    }
    else
    {
      ShvlGetVpRegister(4294967294LL, 0, 0x40000, &v9);
      *(_QWORD *)&v9 = v9 | 0x10000;
      ((void (__fastcall *)(__int64, _QWORD, __int64, __int128 *))ShvlSetVpRegister)(4294967294LL, 0, 0x40000, &v9);
      ShvlGetVpRegister(4294967294LL, 0, 262147, &v9);
      *(_QWORD *)&v9 = v9 | 0x800000;
      ((void (__fastcall *)(__int64, _QWORD, __int64, __int128 *))ShvlSetVpRegister)(4294967294LL, 0, 262147, &v9);
      __writemsr(0x6A4u, a1);
      *(_QWORD *)&v9 = a2;
      return ((__int64 (__fastcall *)(__int64, _QWORD, __int64, __int128 *))ShvlSetVpRegister)(
               4294967294LL,
               0,
               524435,
               &v9);
    }
  }
  return result;
}

```

## disassembly

```asm
0x1400944b8  push    rbp
0x1400944ba  push    rbx
0x1400944bb  push    rsi
0x1400944bc  push    rdi
0x1400944bd  push    r14
0x1400944bf  mov     rbp, rsp
0x1400944c2  sub     rsp, 40h
0x1400944c6  mov     rax, cs:__security_cookie
0x1400944cd  xor     rax, rsp
0x1400944d0  mov     [rbp+var_10], rax
0x1400944d4  test    cs:SkmiFlags, 80000h
0x1400944de  xorps   xmm0, xmm0
0x1400944e1  movups  [rbp+var_20], xmm0
0x1400944e5  mov     rdi, r9
0x1400944e8  mov     r14, rdx
0x1400944eb  mov     rsi, rcx
0x1400944ee  jz      loc_14009464E
0x1400944f4  test    r8d, r8d
0x1400944f7  jnz     loc_140094585
0x1400944fd  mov     edi, 40000h
0x140094502  lea     r9, [rbp+var_20]
0x140094506  mov     ebx, 0FFFFFFFEh
0x14009450b  mov     r8d, edi
0x14009450e  mov     ecx, ebx
0x140094510  xor     edx, edx
0x140094512  call    ShvlGetVpRegister
0x140094517  bts     qword ptr [rbp+var_20], 10h
0x14009451d  lea     r9, [rbp+var_20]
0x140094521  mov     r8d, edi
0x140094524  xor     edx, edx
0x140094526  mov     ecx, ebx
0x140094528  call    ShvlSetVpRegister
0x14009452d  mov     edi, 40003h
0x140094532  lea     r9, [rbp+var_20]
0x140094536  mov     r8d, edi
0x140094539  xor     edx, edx
0x14009453b  mov     ecx, ebx
0x14009453d  call    ShvlGetVpRegister
0x140094542  bts     qword ptr [rbp+var_20], 17h
0x140094548  lea     r9, [rbp+var_20]
0x14009454c  mov     r8d, edi
0x14009454f  xor     edx, edx
0x140094551  mov     ecx, ebx
0x140094553  call    ShvlSetVpRegister
0x140094558  mov     rdx, rsi
0x14009455b  mov     rax, rsi
0x14009455e  shr     rdx, 20h
0x140094562  mov     ecx, 6A4h
0x140094567  wrmsr
0x140094569  lea     r9, [rbp+var_20]
0x14009456d  mov     qword ptr [rbp+var_20], r14
0x140094571  xor     edx, edx
0x140094573  mov     r8d, 80093h
0x140094579  mov     ecx, ebx
0x14009457b  call    ShvlSetVpRegister
0x140094580  jmp     loc_14009464E
0x140094585  lea     rdx, [r9+1C0h]
0x14009458c  mov     ecx, 8008Dh
0x140094591  call    SkiSetRegister
0x140094596  lea     r9, [rbp+var_20]
0x14009459a  mov     qword ptr [rbp+var_20], rsi
0x14009459e  xor     edx, edx
0x1400945a0  mov     ecx, 0FFFFFFFEh
0x1400945a5  mov     r8d, 8008Eh
0x1400945ab  call    ShvlSetVpRegister
0x1400945b0  lea     r8, [rsi+8]
0x1400945b4  mov     ecx, 8008Fh
0x1400945b9  lea     rdx, [rdi+1D8h]
0x1400945c0  call    SkiSetRegisterRaw
0x1400945c5  lea     rdx, [rdi+220h]
0x1400945cc  mov     r8, r14
0x1400945cf  mov     ecx, 80093h
0x1400945d4  call    SkiSetRegisterRaw
0x1400945d9  lea     rdx, [rdi+1F0h]
0x1400945e0  mov     ecx, 80090h
0x1400945e5  call    SkiSetRegister
0x1400945ea  lea     rdx, [rdi+208h]
0x1400945f1  mov     ecx, 80091h
0x1400945f6  call    SkiSetRegister
0x1400945fb  cmp     cs:SkiNtFredEnabled, 0
0x140094602  jz      short loc_14009464E
0x140094604  mov     rbx, gs:0
0x14009460d  lea     rdx, [rdi+2B0h]
0x140094614  mov     ecx, 90065h
0x140094619  mov     r8, [rbx+0BC8h]
0x140094620  call    SkiSetRegisterRaw
0x140094625  mov     r8, [rbx+0BB8h]
0x14009462c  lea     rdx, [rdi+2C8h]
0x140094633  mov     ecx, 90066h
0x140094638  call    SkiSetRegisterRaw
0x14009463d  lea     rdx, [rdi+2E0h]
0x140094644  mov     ecx, 90067h
0x140094649  call    SkiSetRegister
0x14009464e  mov     rcx, [rbp+var_10]
0x140094652  xor     rcx, rsp; StackCookie
0x140094655  call    __security_check_cookie
0x14009465a  add     rsp, 40h
0x14009465e  pop     r14
0x140094660  pop     rdi
0x140094661  pop     rsi
0x140094662  pop     rbx
0x140094663  pop     rbp
0x140094664  retn
```
