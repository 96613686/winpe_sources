# __DllMainCRTStartup

- ea: `0x1800017c4`
- end: `0x1800019d0`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, __int64 fdwReason, void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180001780`

## callees

- `0x180001550`
- `0x1800017c4`
- `0x180001cec`
- `0x180002b34`
- `0x180029930`

## pseudocode

```c
__int64 __fastcall _DllMainCRTStartup(HINSTANCE hinstDLL, __int64 fdwReason, void *a3)
{
  DWORD v3; // edi
  unsigned int v5; // ebx

  v3 = fdwReason;
  v5 = 1;
  if ( (unsigned int)fdwReason <= 1 )
    _native_dllmain_reason = fdwReason;
  if ( (_DWORD)fdwReason || dword_180038428 )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_18003842C = 1;
      v5 = pRawDllMain(hinstDLL, fdwReason, a3);
    }
    if ( v5 )
    {
      v5 = CRT_INIT(hinstDLL, v3, a3);
      if ( v5 )
      {
LABEL_13:
        v5 = DllMain(hinstDLL, v3, a3);
        if ( v3 == 1 && !v5 )
        {
          DllMain(hinstDLL, 0, 0);
          CRT_INIT(hinstDLL, 0, 0);
          if ( pRawDllMain )
            pRawDllMain(hinstDLL, 0, 0);
        }
        if ( !v3 || v3 == 3 )
        {
          v5 = CRT_INIT(hinstDLL, v3, a3);
          if ( pRawDllMain )
          {
            if ( dword_18003842C )
              v5 = pRawDllMain(hinstDLL, v3, a3);
          }
        }
      }
    }
  }
  else
  {
    v5 = 0;
  }
  if ( v3 <= 1 )
    _native_dllmain_reason = -1;
  return v5;
}

```

## disassembly

```asm
0x1800017c4  mov     [rsp+lpvReserved], r8
0x1800017c9  mov     [rsp+arg_8], edx
0x1800017cd  mov     [rsp+arg_0], rcx
0x1800017d2  push    rbx
0x1800017d3  push    rsi
0x1800017d4  push    rdi
0x1800017d5  sub     rsp, 0F0h
0x1800017dc  mov     edi, edx
0x1800017de  mov     rsi, rcx
0x1800017e1  mov     ebx, 1
0x1800017e6  cmp     edx, ebx
0x1800017e8  ja      short loc_1800017F0
0x1800017ea  mov     cs:__native_dllmain_reason, edx
0x1800017f0  test    edx, edx
0x1800017f2  jnz     short loc_180001807
0x1800017f4  cmp     cs:dword_180038428, edx
0x1800017fa  jnz     short loc_180001807
0x1800017fc  xor     ebx, ebx
0x1800017fe  mov     [rsp+108h+var_E8], ebx
0x180001802  jmp     loc_1800019B4
0x180001807  lea     eax, [rdx-1]
0x18000180a  cmp     eax, 1
0x18000180d  ja      loc_180001894
0x180001813  mov     rax, cs:_pRawDllMain
0x18000181a  test    rax, rax
0x18000181d  jz      short loc_180001855
0x18000181f  cmp     edx, 1
0x180001822  jnz     short loc_18000182A
0x180001824  mov     cs:dword_18003842C, edx
0x18000182a  mov     r8, [rsp+108h+lpvReserved]
0x180001832  call    cs:__guard_dispatch_icall_fptr
0x180001838  mov     ebx, eax
0x18000183a  mov     [rsp+108h+var_E8], eax
0x18000183e  jmp     short loc_180001855
0x180001840  xor     ebx, ebx
0x180001842  mov     [rsp+108h+var_E8], ebx
0x180001846  mov     edi, [rsp+108h+arg_8]
0x18000184d  mov     rsi, [rsp+108h+arg_0]
0x180001855  test    ebx, ebx
0x180001857  jz      loc_1800019B4
0x18000185d  mov     r8, [rsp+108h+lpvReserved]
0x180001865  mov     edx, edi
0x180001867  mov     rcx, rsi
0x18000186a  call    _CRT_INIT
0x18000186f  mov     ebx, eax
0x180001871  mov     [rsp+108h+var_E8], eax
0x180001875  jmp     short loc_18000188C
0x180001877  xor     ebx, ebx
0x180001879  mov     [rsp+108h+var_E8], ebx
0x18000187d  mov     edi, [rsp+108h+arg_8]
0x180001884  mov     rsi, [rsp+108h+arg_0]
0x18000188c  test    ebx, ebx
0x18000188e  jz      loc_1800019B4
0x180001894  mov     r8, [rsp+108h+lpvReserved]; lpvReserved
0x18000189c  mov     edx, edi; fdwReason
0x18000189e  mov     rcx, rsi; hinstDLL
0x1800018a1  call    DllMain
0x1800018a6  mov     ebx, eax
0x1800018a8  mov     [rsp+108h+var_E8], eax
0x1800018ac  jmp     short loc_1800018C3
0x1800018ae  xor     ebx, ebx
0x1800018b0  mov     [rsp+108h+var_E8], ebx
0x1800018b4  mov     edi, [rsp+108h+arg_8]
0x1800018bb  mov     rsi, [rsp+108h+arg_0]
0x1800018c3  cmp     edi, 1
0x1800018c6  jnz     short loc_18000193F
0x1800018c8  test    ebx, ebx
0x1800018ca  jnz     short loc_18000193F
0x1800018cc  xor     r8d, r8d; lpvReserved
0x1800018cf  xor     edx, edx; fdwReason
0x1800018d1  mov     rcx, rsi; hinstDLL
0x1800018d4  call    DllMain
0x1800018d9  jmp     short loc_1800018EE
0x1800018db  mov     edi, [rsp+108h+arg_8]
0x1800018e2  mov     rsi, [rsp+108h+arg_0]
0x1800018ea  mov     ebx, [rsp+108h+var_E8]
0x1800018ee  xor     r8d, r8d
0x1800018f1  xor     edx, edx
0x1800018f3  mov     rcx, rsi
0x1800018f6  call    _CRT_INIT
0x1800018fb  jmp     short loc_180001910
0x1800018fd  mov     edi, [rsp+108h+arg_8]
0x180001904  mov     rsi, [rsp+108h+arg_0]
0x18000190c  mov     ebx, [rsp+108h+var_E8]
0x180001910  mov     rax, cs:_pRawDllMain
0x180001917  test    rax, rax
0x18000191a  jz      short loc_18000193F
0x18000191c  xor     r8d, r8d
0x18000191f  xor     edx, edx
0x180001921  mov     rcx, rsi
0x180001924  call    cs:__guard_dispatch_icall_fptr
0x18000192a  jmp     short loc_18000193F
0x18000192c  mov     edi, [rsp+108h+arg_8]
0x180001933  mov     rsi, [rsp+108h+arg_0]
0x18000193b  mov     ebx, [rsp+108h+var_E8]
0x18000193f  test    edi, edi
0x180001941  jz      short loc_180001948
0x180001943  cmp     edi, 3
0x180001946  jnz     short loc_1800019B4
0x180001948  mov     r8, [rsp+108h+lpvReserved]
0x180001950  mov     edx, edi
0x180001952  mov     rcx, rsi
0x180001955  call    _CRT_INIT
0x18000195a  mov     ebx, eax
0x18000195c  mov     [rsp+108h+var_E8], eax
0x180001960  jmp     short loc_180001977
0x180001962  xor     ebx, ebx
0x180001964  mov     [rsp+108h+var_E8], ebx
0x180001968  mov     edi, [rsp+108h+arg_8]
0x18000196f  mov     rsi, [rsp+108h+arg_0]
0x180001977  mov     rax, cs:_pRawDllMain
0x18000197e  test    rax, rax
0x180001981  jz      short loc_1800019B4
0x180001983  cmp     cs:dword_18003842C, 0
0x18000198a  jz      short loc_1800019B4
0x18000198c  mov     r8, [rsp+108h+lpvReserved]
0x180001994  mov     edx, edi
0x180001996  mov     rcx, rsi
0x180001999  call    cs:__guard_dispatch_icall_fptr
0x18000199f  mov     ebx, eax
0x1800019a1  mov     [rsp+108h+var_E8], eax
0x1800019a5  jmp     short loc_1800019B4
0x1800019a7  xor     ebx, ebx
0x1800019a9  mov     [rsp+108h+var_E8], ebx
0x1800019ad  mov     edi, [rsp+108h+arg_8]
0x1800019b4  cmp     edi, 1
0x1800019b7  ja      short loc_1800019C3
0x1800019b9  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x1800019c3  mov     eax, ebx
0x1800019c5  add     rsp, 0F0h
0x1800019cc  pop     rdi
0x1800019cd  pop     rsi
0x1800019ce  pop     rbx
0x1800019cf  retn
0x1800299d3  push    rbp
0x1800299d5  sub     rsp, 20h
0x1800299d9  mov     rbp, rdx
0x1800299dc  mov     rax, [rcx]
0x1800299df  mov     edx, [rax]
0x1800299e1  mov     [rbp+0A8h], rcx
0x1800299e8  mov     [rbp+28h], edx
0x1800299eb  mov     eax, [rbp+28h]
0x1800299ee  cmp     eax, 0E06D7363h
0x1800299f3  jnz     short loc_180029A09
0x1800299f5  mov     rdx, [rbp+0A8h]
0x1800299fc  mov     ecx, [rbp+28h]
0x1800299ff  call    _XcptFilter_0
0x180029a04  mov     [rbp+30h], eax
0x180029a07  jmp     short loc_180029A10
0x180029a09  mov     dword ptr [rbp+30h], 0
0x180029a10  mov     eax, [rbp+30h]
0x180029a13  add     rsp, 20h
0x180029a17  pop     rbp
0x180029a18  retn
0x180029a1a  push    rbp
0x180029a1c  sub     rsp, 20h
0x180029a20  mov     rbp, rdx
0x180029a23  mov     rax, [rcx]
0x180029a26  mov     edx, [rax]
0x180029a28  mov     [rbp+0B0h], rcx
0x180029a2f  mov     [rbp+38h], edx
0x180029a32  mov     eax, [rbp+38h]
0x180029a35  cmp     eax, 0E06D7363h
0x180029a3a  jnz     short loc_180029A50
0x180029a3c  mov     rdx, [rbp+0B0h]
0x180029a43  mov     ecx, [rbp+38h]
0x180029a46  call    _XcptFilter_0
0x180029a4b  mov     [rbp+40h], eax
0x180029a4e  jmp     short loc_180029A57
0x180029a50  mov     dword ptr [rbp+40h], 0
0x180029a57  mov     eax, [rbp+40h]
0x180029a5a  add     rsp, 20h
0x180029a5e  pop     rbp
0x180029a5f  retn
0x180029a61  push    rbp
0x180029a63  sub     rsp, 20h
0x180029a67  mov     rbp, rdx
0x180029a6a  mov     rax, [rcx]
0x180029a6d  mov     edx, [rax]
0x180029a6f  mov     [rbp+0B8h], rcx
0x180029a76  mov     [rbp+48h], edx
0x180029a79  mov     eax, [rbp+48h]
0x180029a7c  cmp     eax, 0E06D7363h
0x180029a81  jnz     short loc_180029A97
0x180029a83  mov     rdx, [rbp+0B8h]
0x180029a8a  mov     ecx, [rbp+48h]
0x180029a8d  call    _XcptFilter_0
0x180029a92  mov     [rbp+50h], eax
0x180029a95  jmp     short loc_180029A9E
0x180029a97  mov     dword ptr [rbp+50h], 0
0x180029a9e  mov     eax, [rbp+50h]
0x180029aa1  add     rsp, 20h
0x180029aa5  pop     rbp
0x180029aa6  retn
0x180029aa8  push    rbp
0x180029aaa  sub     rsp, 20h
0x180029aae  mov     rbp, rdx
0x180029ab1  mov     rax, [rcx]
0x180029ab4  mov     edx, [rax]
0x180029ab6  mov     [rbp+0C0h], rcx
0x180029abd  mov     [rbp+58h], edx
0x180029ac0  mov     eax, [rbp+58h]
0x180029ac3  cmp     eax, 0E06D7363h
0x180029ac8  jnz     short loc_180029ADE
0x180029aca  mov     rdx, [rbp+0C0h]
0x180029ad1  mov     ecx, [rbp+58h]
0x180029ad4  call    _XcptFilter_0
0x180029ad9  mov     [rbp+60h], eax
0x180029adc  jmp     short loc_180029AE5
0x180029ade  mov     dword ptr [rbp+60h], 0
0x180029ae5  mov     eax, [rbp+60h]
0x180029ae8  add     rsp, 20h
0x180029aec  pop     rbp
0x180029aed  retn
0x180029aef  push    rbp
0x180029af1  sub     rsp, 20h
0x180029af5  mov     rbp, rdx
0x180029af8  mov     rax, [rcx]
0x180029afb  mov     edx, [rax]
0x180029afd  mov     [rbp+0C8h], rcx
0x180029b04  mov     [rbp+68h], edx
0x180029b07  mov     eax, [rbp+68h]
0x180029b0a  cmp     eax, 0E06D7363h
0x180029b0f  jnz     short loc_180029B25
0x180029b11  mov     rdx, [rbp+0C8h]
0x180029b18  mov     ecx, [rbp+68h]
0x180029b1b  call    _XcptFilter_0
0x180029b20  mov     [rbp+70h], eax
0x180029b23  jmp     short loc_180029B2C
0x180029b25  mov     dword ptr [rbp+70h], 0
0x180029b2c  mov     eax, [rbp+70h]
0x180029b2f  add     rsp, 20h
0x180029b33  pop     rbp
0x180029b34  retn
0x180029b36  push    rbp
0x180029b38  sub     rsp, 20h
0x180029b3c  mov     rbp, rdx
0x180029b3f  mov     rax, [rcx]
0x180029b42  mov     edx, [rax]
0x180029b44  mov     [rbp+0D0h], rcx
0x180029b4b  mov     [rbp+78h], edx
0x180029b4e  mov     eax, [rbp+78h]
0x180029b51  cmp     eax, 0E06D7363h
0x180029b56  jnz     short loc_180029B6F
0x180029b58  mov     rdx, [rbp+0D0h]
0x180029b5f  mov     ecx, [rbp+78h]
0x180029b62  call    _XcptFilter_0
0x180029b67  mov     [rbp+80h], eax
0x180029b6d  jmp     short loc_180029B79
0x180029b6f  mov     dword ptr [rbp+80h], 0
0x180029b79  mov     eax, [rbp+80h]
0x180029b7f  add     rsp, 20h
0x180029b83  pop     rbp
0x180029b84  retn
0x180029b86  push    rbp
0x180029b88  sub     rsp, 20h
0x180029b8c  mov     rbp, rdx
0x180029b8f  mov     rax, [rcx]
0x180029b92  mov     edx, [rax]
0x180029b94  mov     [rbp+0D8h], rcx
0x180029b9b  mov     [rbp+88h], edx
0x180029ba1  mov     eax, [rbp+88h]
0x180029ba7  cmp     eax, 0E06D7363h
0x180029bac  jnz     short loc_180029BC8
0x180029bae  mov     rdx, [rbp+0D8h]
0x180029bb5  mov     ecx, [rbp+88h]
0x180029bbb  call    _XcptFilter_0
0x180029bc0  mov     [rbp+90h], eax
0x180029bc6  jmp     short loc_180029BD2
0x180029bc8  mov     dword ptr [rbp+90h], 0
0x180029bd2  mov     eax, [rbp+90h]
0x180029bd8  add     rsp, 20h
0x180029bdc  pop     rbp
0x180029bdd  retn
0x180029bdf  push    rbp
0x180029be1  sub     rsp, 20h
0x180029be5  mov     rbp, rdx
0x180029be8  mov     rax, [rcx]
0x180029beb  mov     edx, [rax]
0x180029bed  mov     [rbp+0E0h], rcx
0x180029bf4  mov     [rbp+98h], edx
0x180029bfa  mov     eax, [rbp+98h]
0x180029c00  cmp     eax, 0E06D7363h
0x180029c05  jnz     short loc_180029C21
0x180029c07  mov     rdx, [rbp+0E0h]
0x180029c0e  mov     ecx, [rbp+98h]
0x180029c14  call    _XcptFilter_0
0x180029c19  mov     [rbp+0A0h], eax
0x180029c1f  jmp     short loc_180029C2B
0x180029c21  mov     dword ptr [rbp+0A0h], 0
0x180029c2b  mov     eax, [rbp+0A0h]
0x180029c31  add     rsp, 20h
0x180029c35  pop     rbp
0x180029c36  retn
0x180029c38  push    rbp
0x180029c3a  sub     rsp, 20h
0x180029c3e  mov     rbp, rdx
0x180029c41  cmp     dword ptr [rbp+118h], 1
0x180029c48  ja      short loc_180029C54
0x180029c4a  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
