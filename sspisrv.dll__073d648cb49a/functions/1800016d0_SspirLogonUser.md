# SspirLogonUser

- ea: `0x1800016d0`
- end: `0x1800019a6`
- name: `SspirLogonUser`
- size: `726`
- prototype: `__int64 __fastcall(__int64, _QWORD *, __int64, unsigned int, int, __int64, __int64, unsigned int *, int, __int64, __int64, _QWORD *, __int64, __int64, _QWORD *, _OWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180002d20`

## callees

- `0x1800016d0`
- `0x1800019b0`
- `0x1800033f0`
- `0x180004010`

## pseudocode

```c
__int64 __fastcall SspirLogonUser(
        __int64 a1,
        _QWORD *a2,
        __int64 a3,
        unsigned int a4,
        int a5,
        __int64 a6,
        __int64 a7,
        unsigned int *a8,
        int a9,
        __int64 a10,
        __int64 a11,
        _QWORD *a12,
        __int64 a13,
        __int64 a14,
        _QWORD *a15,
        _OWORD *a16)
{
  __int64 v16; // r10
  __int64 v19; // r8
  __int64 v20; // rcx
  __int64 v21; // r9
  unsigned int i; // eax
  __int64 result; // rax
  __int64 v24; // rax
  __int64 v25; // rdx
  int v26; // [rsp+A0h] [rbp-80h] BYREF
  unsigned int v27; // [rsp+A4h] [rbp-7Ch]
  _QWORD *v28; // [rsp+A8h] [rbp-78h]
  __int64 v29; // [rsp+B0h] [rbp-70h]
  __int64 v30; // [rsp+B8h] [rbp-68h] BYREF
  __int64 v31; // [rsp+C0h] [rbp-60h] BYREF
  __int64 v32; // [rsp+C8h] [rbp-58h]
  __int64 v33; // [rsp+D0h] [rbp-50h]
  __int64 v34; // [rsp+D8h] [rbp-48h]
  __int64 v35; // [rsp+E0h] [rbp-40h]
  __int128 v36; // [rsp+E8h] [rbp-38h] BYREF
  __int128 v37; // [rsp+F8h] [rbp-28h] BYREF
  __int128 v38; // [rsp+108h] [rbp-18h]
  __int128 v39; // [rsp+118h] [rbp-8h]

  v16 = gLsapSspiExtension;
  v19 = a13;
  v34 = a10;
  v20 = a11;
  v27 = a4;
  v21 = a14;
  v29 = a11;
  v28 = a2;
  v35 = a7;
  v32 = a13;
  v33 = a14;
  v30 = 0;
  v31 = 0;
  v26 = 0;
  v36 = 0;
  v37 = 0;
  v38 = 0;
  v39 = 0;
  if ( !gLsapSspiExtension || !*(_QWORD *)(gLsapSspiExtension + 112) )
    return 3221225659LL;
  if ( !a2
    || !a3
    || !a6
    || !a7
    || !a11
    || !a12
    || !a13
    || !a14
    || !a15
    || !a16
    || *(_WORD *)a3 && !*(_QWORD *)(a3 + 8)
    || *(_DWORD *)a6 && !*(_QWORD *)(a6 + 16) )
  {
    return 3221225485LL;
  }
  if ( !a8 )
    goto LABEL_25;
  if ( *a8 && a8 == (unsigned int *)-8LL )
    return 3221225485LL;
  for ( i = 0; i < *a8; ++i )
  {
    if ( !*(_QWORD *)&a8[4 * i + 2] )
      return 3221225485LL;
  }
  a2 = v28;
  v20 = v29;
LABEL_25:
  if ( a1 )
  {
    result = CheckLowboxAccess(&v26, a2);
    if ( (int)result < 0 )
      return result;
    if ( !v26 )
      return 3221225506LL;
    v16 = gLsapSspiExtension;
    a2 = v28;
    v20 = v29;
    v19 = v32;
    v21 = v33;
  }
  *(_QWORD *)&v36 = *a2;
  v24 = a2[1];
  v25 = *(_QWORD *)(a6 + 16);
  *((_QWORD *)&v36 + 1) = v24;
  result = (*(__int64 (__fastcall **)(__int64, __int128 *, __int64, _QWORD, int, _DWORD, _QWORD, __int64, __int64, unsigned int *, int, __int64, __int64, __int64 *, __int64, __int64, __int64 *, __int128 *))(v16 + 112))(
             a1,
             &v36,
             a3,
             v27,
             a5,
             *(_DWORD *)a6,
             *(_QWORD *)(a6 + 8),
             v25,
             v35,
             a8,
             a9,
             v34,
             v20,
             &v30,
             v19,
             v21,
             &v31,
             &v37);
  if ( (int)result >= 0 )
  {
    *a12 = v30;
    *a15 = v31;
    a16[1] = v38;
    *a16 = v37;
    a16[2] = v39;
    return (unsigned int)result;
  }
  return result;
}

```

## disassembly

```asm
0x1800016d0  push    rbp
0x1800016d2  push    rbx
0x1800016d3  push    rsi
0x1800016d4  push    rdi
0x1800016d5  push    r12
0x1800016d7  push    r13
0x1800016d9  push    r14
0x1800016db  push    r15
0x1800016dd  lea     rbp, [rsp-18h]
0x1800016e2  sub     rsp, 138h
0x1800016e9  mov     rax, cs:__security_cookie
0x1800016f0  xor     rax, rsp
0x1800016f3  mov     [rbp+50h+var_48], rax
0x1800016f7  mov     r10, cs:gLsapSspiExtension
0x1800016fe  xor     r11d, r11d
0x180001701  mov     rax, [rbp+50h+arg_30]
0x180001708  xorps   xmm0, xmm0
0x18000170b  mov     r14, [rbp+50h+arg_78]
0x180001712  mov     r13, rcx
0x180001715  mov     rcx, [rbp+50h+arg_48]
0x18000171c  mov     rsi, r8
0x18000171f  mov     r8, [rbp+50h+arg_60]
0x180001726  mov     rbx, [rbp+50h+arg_38]
0x18000172d  mov     rdi, [rbp+50h+arg_28]
0x180001734  mov     r15, [rbp+50h+arg_58]
0x18000173b  mov     r12, [rbp+50h+arg_70]
0x180001742  mov     [rbp+50h+var_98], rcx
0x180001746  mov     rcx, [rbp+50h+arg_50]
0x18000174d  mov     [rbp+50h+var_CC], r9d
0x180001751  mov     r9, [rbp+50h+arg_68]
0x180001758  mov     [rbp+50h+var_C0], rcx
0x18000175c  mov     [rbp+50h+var_C8], rdx
0x180001760  mov     [rbp+50h+var_90], rax
0x180001764  mov     [rbp+50h+var_A8], r8
0x180001768  mov     [rbp+50h+var_A0], r9
0x18000176c  mov     [rbp+50h+var_B8], r11
0x180001770  mov     [rbp+50h+var_B0], r11
0x180001774  mov     [rbp+50h+var_D0], r11d
0x180001778  movups  [rbp+50h+var_88], xmm0
0x18000177c  movups  [rbp+50h+var_78], xmm0
0x180001780  movups  [rbp+50h+var_68], xmm0
0x180001784  movups  [rbp+50h+var_58], xmm0
0x180001788  test    r10, r10
0x18000178b  jz      loc_180001882
0x180001791  cmp     [r10+70h], r11
0x180001795  jz      loc_180001882
0x18000179b  test    rdx, rdx
0x18000179e  jz      loc_180001992
0x1800017a4  test    rsi, rsi
0x1800017a7  jz      loc_180001992
0x1800017ad  test    rdi, rdi
0x1800017b0  jz      loc_180001992
0x1800017b6  test    rax, rax
0x1800017b9  jz      loc_180001992
0x1800017bf  test    rcx, rcx
0x1800017c2  jz      loc_180001992
0x1800017c8  test    r15, r15
0x1800017cb  jz      loc_180001992
0x1800017d1  test    r8, r8
0x1800017d4  jz      loc_180001992
0x1800017da  test    r9, r9
0x1800017dd  jz      loc_180001992
0x1800017e3  test    r12, r12
0x1800017e6  jz      loc_180001992
0x1800017ec  test    r14, r14
0x1800017ef  jz      loc_180001992
0x1800017f5  cmp     [rsi], r11w
0x1800017f9  jbe     short loc_180001805
0x1800017fb  cmp     [rsi+8], r11
0x1800017ff  jz      loc_180001992
0x180001805  cmp     [rdi], r11d
0x180001808  jbe     short loc_180001814
0x18000180a  cmp     [rdi+10h], r11
0x18000180e  jz      loc_180001992
0x180001814  test    rbx, rbx
0x180001817  jz      short loc_18000184F
0x180001819  mov     edx, [rbx]
0x18000181b  test    edx, edx
0x18000181d  jz      short loc_18000182C
0x18000181f  lea     rax, [rbx+8]
0x180001823  test    rax, rax
0x180001826  jz      loc_180001992
0x18000182c  mov     eax, r11d
0x18000182f  cmp     eax, edx
0x180001831  jnb     short loc_180001847
0x180001833  mov     ecx, eax
0x180001835  add     rcx, rcx
0x180001838  cmp     [rbx+rcx*8+8], r11
0x18000183d  jz      loc_180001992
0x180001843  inc     eax
0x180001845  jmp     short loc_18000182F
0x180001847  mov     rdx, [rbp+50h+var_C8]
0x18000184b  mov     rcx, [rbp+50h+var_C0]
0x18000184f  test    r13, r13
0x180001852  jz      short loc_1800018AA
0x180001854  lea     rcx, [rbp+50h+var_D0]
0x180001858  call    CheckLowboxAccess
0x18000185d  test    eax, eax
0x18000185f  jns     short loc_180001889
0x180001861  mov     rcx, [rbp+50h+var_48]
0x180001865  xor     rcx, rsp; StackCookie
0x180001868  call    __security_check_cookie
0x18000186d  add     rsp, 138h
0x180001874  pop     r15
0x180001876  pop     r14
0x180001878  pop     r13
0x18000187a  pop     r12
0x18000187c  pop     rdi
0x18000187d  pop     rsi
0x18000187e  pop     rbx
0x18000187f  pop     rbp
0x180001880  retn
0x180001882  mov     eax, 0C00000BBh
0x180001887  jmp     short loc_180001861
0x180001889  cmp     [rbp+50h+var_D0], 0
0x18000188d  jz      loc_18000199C
0x180001893  mov     r10, cs:gLsapSspiExtension
0x18000189a  mov     rdx, [rbp+50h+var_C8]
0x18000189e  mov     rcx, [rbp+50h+var_C0]
0x1800018a2  mov     r8, [rbp+50h+var_A8]
0x1800018a6  mov     r9, [rbp+50h+var_A0]
0x1800018aa  mov     rax, [rdx]
0x1800018ad  mov     qword ptr [rbp+50h+var_88], rax
0x1800018b1  mov     rax, [rdx+8]
0x1800018b5  mov     rdx, [rdi+10h]
0x1800018b9  mov     qword ptr [rbp+50h+var_88+8], rax
0x1800018bd  lea     rax, [rbp+50h+var_78]
0x1800018c1  mov     [rsp+170h+var_E8], rax
0x1800018c9  lea     rax, [rbp+50h+var_B0]
0x1800018cd  mov     [rsp+170h+var_F0], rax
0x1800018d5  lea     rax, [rbp+50h+var_B8]
0x1800018d9  mov     [rsp+170h+var_F8], r9
0x1800018de  mov     r9d, [rbp+50h+var_CC]
0x1800018e2  mov     [rsp+170h+var_100], r8
0x1800018e7  mov     r8, rsi
0x1800018ea  mov     [rsp+170h+var_108], rax
0x1800018ef  mov     rax, [rbp+50h+var_98]
0x1800018f3  mov     [rsp+170h+var_110], rcx
0x1800018f8  mov     rcx, r13
0x1800018fb  mov     [rsp+170h+var_118], rax
0x180001900  mov     eax, [rbp+50h+arg_40]
0x180001906  mov     [rsp+170h+var_120], eax
0x18000190a  mov     rax, [rbp+50h+var_90]
0x18000190e  mov     [rsp+170h+var_128], rbx
0x180001913  mov     [rsp+170h+var_130], rax
0x180001918  mov     rax, [r10+70h]
0x18000191c  mov     [rsp+170h+var_138], rdx
0x180001921  mov     rdx, [rdi+8]
0x180001925  mov     [rsp+170h+var_140], rdx
0x18000192a  mov     edx, [rdi]
0x18000192c  mov     [rsp+170h+var_148], edx
0x180001930  mov     edx, [rbp+50h+arg_20]
0x180001936  mov     [rsp+170h+var_150], edx
0x18000193a  lea     rdx, [rbp+50h+var_88]
0x18000193e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001943  mov     ecx, eax
0x180001945  test    eax, eax
0x180001947  js      loc_180001861
0x18000194d  mov     rax, [rbp+50h+var_B8]
0x180001951  mov     [r15], rax
0x180001954  mov     rax, [rbp+50h+var_B0]
0x180001958  mov     [r12], rax
0x18000195c  mov     rax, qword ptr [rbp+50h+var_68+8]
0x180001960  mov     [r14+18h], rax
0x180001964  mov     rax, qword ptr [rbp+50h+var_68]
0x180001968  mov     [r14+10h], rax
0x18000196c  mov     rax, qword ptr [rbp+50h+var_78+8]
0x180001970  mov     [r14+8], rax
0x180001974  mov     rax, qword ptr [rbp+50h+var_78]
0x180001978  mov     [r14], rax
0x18000197b  mov     rax, qword ptr [rbp+50h+var_58]
0x18000197f  mov     [r14+20h], rax
0x180001983  mov     rax, qword ptr [rbp+50h+var_58+8]
0x180001987  mov     [r14+28h], rax
0x18000198b  mov     eax, ecx
0x18000198d  jmp     loc_180001861
0x180001992  mov     eax, 0C000000Dh
0x180001997  jmp     loc_180001861
0x18000199c  mov     eax, 0C0000022h
0x1800019a1  jmp     loc_180001861
```
