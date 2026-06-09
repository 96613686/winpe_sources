# __DllMainCRTStartup

- ea: `0x180001314`
- end: `0x180001520`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1800012d0`

## callees

- `0x1800010a0`
- `0x180001314`
- `0x180001875`
- `0x1800022f4`
- `0x18002cfe0`

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
  if ( (_DWORD)fdwReason || dword_180036920 )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_180036924 = 1;
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
            if ( dword_180036924 )
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
0x180001314  mov     [rsp+lpvReserved], r8
0x180001319  mov     [rsp+arg_8], edx
0x18000131d  mov     [rsp+arg_0], rcx
0x180001322  push    rbx
0x180001323  push    rsi
0x180001324  push    rdi
0x180001325  sub     rsp, 0F0h
0x18000132c  mov     edi, edx
0x18000132e  mov     rsi, rcx
0x180001331  mov     ebx, 1
0x180001336  cmp     edx, ebx
0x180001338  ja      short loc_180001340
0x18000133a  mov     cs:__native_dllmain_reason, edx
0x180001340  test    edx, edx
0x180001342  jnz     short loc_180001357
0x180001344  cmp     cs:dword_180036920, edx
0x18000134a  jnz     short loc_180001357
0x18000134c  xor     ebx, ebx
0x18000134e  mov     [rsp+108h+var_E8], ebx
0x180001352  jmp     loc_180001504
0x180001357  lea     eax, [rdx-1]
0x18000135a  cmp     eax, 1
0x18000135d  ja      loc_1800013E4
0x180001363  mov     rax, cs:_pRawDllMain
0x18000136a  test    rax, rax
0x18000136d  jz      short loc_1800013A5
0x18000136f  cmp     edx, 1
0x180001372  jnz     short loc_18000137A
0x180001374  mov     cs:dword_180036924, edx
0x18000137a  mov     r8, [rsp+108h+lpvReserved]
0x180001382  call    cs:__guard_dispatch_icall_fptr
0x180001388  mov     ebx, eax
0x18000138a  mov     [rsp+108h+var_E8], eax
0x18000138e  jmp     short loc_1800013A5
0x180001390  xor     ebx, ebx
0x180001392  mov     [rsp+108h+var_E8], ebx
0x180001396  mov     edi, [rsp+108h+arg_8]
0x18000139d  mov     rsi, [rsp+108h+arg_0]
0x1800013a5  test    ebx, ebx
0x1800013a7  jz      loc_180001504
0x1800013ad  mov     r8, [rsp+108h+lpvReserved]
0x1800013b5  mov     edx, edi
0x1800013b7  mov     rcx, rsi
0x1800013ba  call    _CRT_INIT
0x1800013bf  mov     ebx, eax
0x1800013c1  mov     [rsp+108h+var_E8], eax
0x1800013c5  jmp     short loc_1800013DC
0x1800013c7  xor     ebx, ebx
0x1800013c9  mov     [rsp+108h+var_E8], ebx
0x1800013cd  mov     edi, [rsp+108h+arg_8]
0x1800013d4  mov     rsi, [rsp+108h+arg_0]
0x1800013dc  test    ebx, ebx
0x1800013de  jz      loc_180001504
0x1800013e4  mov     r8, [rsp+108h+lpvReserved]; lpvReserved
0x1800013ec  mov     edx, edi; fdwReason
0x1800013ee  mov     rcx, rsi; hinstDLL
0x1800013f1  call    DllMain
0x1800013f6  mov     ebx, eax
0x1800013f8  mov     [rsp+108h+var_E8], eax
0x1800013fc  jmp     short loc_180001413
0x1800013fe  xor     ebx, ebx
0x180001400  mov     [rsp+108h+var_E8], ebx
0x180001404  mov     edi, [rsp+108h+arg_8]
0x18000140b  mov     rsi, [rsp+108h+arg_0]
0x180001413  cmp     edi, 1
0x180001416  jnz     short loc_18000148F
0x180001418  test    ebx, ebx
0x18000141a  jnz     short loc_18000148F
0x18000141c  xor     r8d, r8d; lpvReserved
0x18000141f  xor     edx, edx; fdwReason
0x180001421  mov     rcx, rsi; hinstDLL
0x180001424  call    DllMain
0x180001429  jmp     short loc_18000143E
0x18000142b  mov     edi, [rsp+108h+arg_8]
0x180001432  mov     rsi, [rsp+108h+arg_0]
0x18000143a  mov     ebx, [rsp+108h+var_E8]
0x18000143e  xor     r8d, r8d
0x180001441  xor     edx, edx
0x180001443  mov     rcx, rsi
0x180001446  call    _CRT_INIT
0x18000144b  jmp     short loc_180001460
0x18000144d  mov     edi, [rsp+108h+arg_8]
0x180001454  mov     rsi, [rsp+108h+arg_0]
0x18000145c  mov     ebx, [rsp+108h+var_E8]
0x180001460  mov     rax, cs:_pRawDllMain
0x180001467  test    rax, rax
0x18000146a  jz      short loc_18000148F
0x18000146c  xor     r8d, r8d
0x18000146f  xor     edx, edx
0x180001471  mov     rcx, rsi
0x180001474  call    cs:__guard_dispatch_icall_fptr
0x18000147a  jmp     short loc_18000148F
0x18000147c  mov     edi, [rsp+108h+arg_8]
0x180001483  mov     rsi, [rsp+108h+arg_0]
0x18000148b  mov     ebx, [rsp+108h+var_E8]
0x18000148f  test    edi, edi
0x180001491  jz      short loc_180001498
0x180001493  cmp     edi, 3
0x180001496  jnz     short loc_180001504
0x180001498  mov     r8, [rsp+108h+lpvReserved]
0x1800014a0  mov     edx, edi
0x1800014a2  mov     rcx, rsi
0x1800014a5  call    _CRT_INIT
0x1800014aa  mov     ebx, eax
0x1800014ac  mov     [rsp+108h+var_E8], eax
0x1800014b0  jmp     short loc_1800014C7
0x1800014b2  xor     ebx, ebx
0x1800014b4  mov     [rsp+108h+var_E8], ebx
0x1800014b8  mov     edi, [rsp+108h+arg_8]
0x1800014bf  mov     rsi, [rsp+108h+arg_0]
0x1800014c7  mov     rax, cs:_pRawDllMain
0x1800014ce  test    rax, rax
0x1800014d1  jz      short loc_180001504
0x1800014d3  cmp     cs:dword_180036924, 0
0x1800014da  jz      short loc_180001504
0x1800014dc  mov     r8, [rsp+108h+lpvReserved]
0x1800014e4  mov     edx, edi
0x1800014e6  mov     rcx, rsi
0x1800014e9  call    cs:__guard_dispatch_icall_fptr
0x1800014ef  mov     ebx, eax
0x1800014f1  mov     [rsp+108h+var_E8], eax
0x1800014f5  jmp     short loc_180001504
0x1800014f7  xor     ebx, ebx
0x1800014f9  mov     [rsp+108h+var_E8], ebx
0x1800014fd  mov     edi, [rsp+108h+arg_8]
0x180001504  cmp     edi, 1
0x180001507  ja      short loc_180001513
0x180001509  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x180001513  mov     eax, ebx
0x180001515  add     rsp, 0F0h
0x18000151c  pop     rdi
0x18000151d  pop     rsi
0x18000151e  pop     rbx
0x18000151f  retn
0x18002d050  push    rbp
0x18002d052  sub     rsp, 20h
0x18002d056  mov     rbp, rdx
0x18002d059  mov     rax, [rcx]
0x18002d05c  mov     edx, [rax]
0x18002d05e  mov     [rbp+0A8h], rcx
0x18002d065  mov     [rbp+28h], edx
0x18002d068  mov     eax, [rbp+28h]
0x18002d06b  cmp     eax, 0E06D7363h
0x18002d070  jnz     short loc_18002D086
0x18002d072  mov     rdx, [rbp+0A8h]
0x18002d079  mov     ecx, [rbp+28h]
0x18002d07c  call    _XcptFilter_0
0x18002d081  mov     [rbp+30h], eax
0x18002d084  jmp     short loc_18002D08D
0x18002d086  mov     dword ptr [rbp+30h], 0
0x18002d08d  mov     eax, [rbp+30h]
0x18002d090  add     rsp, 20h
0x18002d094  pop     rbp
0x18002d095  retn
0x18002d097  push    rbp
0x18002d099  sub     rsp, 20h
0x18002d09d  mov     rbp, rdx
0x18002d0a0  mov     rax, [rcx]
0x18002d0a3  mov     edx, [rax]
0x18002d0a5  mov     [rbp+0B0h], rcx
0x18002d0ac  mov     [rbp+38h], edx
0x18002d0af  mov     eax, [rbp+38h]
0x18002d0b2  cmp     eax, 0E06D7363h
0x18002d0b7  jnz     short loc_18002D0CD
0x18002d0b9  mov     rdx, [rbp+0B0h]
0x18002d0c0  mov     ecx, [rbp+38h]
0x18002d0c3  call    _XcptFilter_0
0x18002d0c8  mov     [rbp+40h], eax
0x18002d0cb  jmp     short loc_18002D0D4
0x18002d0cd  mov     dword ptr [rbp+40h], 0
0x18002d0d4  mov     eax, [rbp+40h]
0x18002d0d7  add     rsp, 20h
0x18002d0db  pop     rbp
0x18002d0dc  retn
0x18002d0de  push    rbp
0x18002d0e0  sub     rsp, 20h
0x18002d0e4  mov     rbp, rdx
0x18002d0e7  mov     rax, [rcx]
0x18002d0ea  mov     edx, [rax]
0x18002d0ec  mov     [rbp+0B8h], rcx
0x18002d0f3  mov     [rbp+48h], edx
0x18002d0f6  mov     eax, [rbp+48h]
0x18002d0f9  cmp     eax, 0E06D7363h
0x18002d0fe  jnz     short loc_18002D114
0x18002d100  mov     rdx, [rbp+0B8h]
0x18002d107  mov     ecx, [rbp+48h]
0x18002d10a  call    _XcptFilter_0
0x18002d10f  mov     [rbp+50h], eax
0x18002d112  jmp     short loc_18002D11B
0x18002d114  mov     dword ptr [rbp+50h], 0
0x18002d11b  mov     eax, [rbp+50h]
0x18002d11e  add     rsp, 20h
0x18002d122  pop     rbp
0x18002d123  retn
0x18002d125  push    rbp
0x18002d127  sub     rsp, 20h
0x18002d12b  mov     rbp, rdx
0x18002d12e  mov     rax, [rcx]
0x18002d131  mov     edx, [rax]
0x18002d133  mov     [rbp+0C0h], rcx
0x18002d13a  mov     [rbp+58h], edx
0x18002d13d  mov     eax, [rbp+58h]
0x18002d140  cmp     eax, 0E06D7363h
0x18002d145  jnz     short loc_18002D15B
0x18002d147  mov     rdx, [rbp+0C0h]
0x18002d14e  mov     ecx, [rbp+58h]
0x18002d151  call    _XcptFilter_0
0x18002d156  mov     [rbp+60h], eax
0x18002d159  jmp     short loc_18002D162
0x18002d15b  mov     dword ptr [rbp+60h], 0
0x18002d162  mov     eax, [rbp+60h]
0x18002d165  add     rsp, 20h
0x18002d169  pop     rbp
0x18002d16a  retn
0x18002d16c  push    rbp
0x18002d16e  sub     rsp, 20h
0x18002d172  mov     rbp, rdx
0x18002d175  mov     rax, [rcx]
0x18002d178  mov     edx, [rax]
0x18002d17a  mov     [rbp+0C8h], rcx
0x18002d181  mov     [rbp+68h], edx
0x18002d184  mov     eax, [rbp+68h]
0x18002d187  cmp     eax, 0E06D7363h
0x18002d18c  jnz     short loc_18002D1A2
0x18002d18e  mov     rdx, [rbp+0C8h]
0x18002d195  mov     ecx, [rbp+68h]
0x18002d198  call    _XcptFilter_0
0x18002d19d  mov     [rbp+70h], eax
0x18002d1a0  jmp     short loc_18002D1A9
0x18002d1a2  mov     dword ptr [rbp+70h], 0
0x18002d1a9  mov     eax, [rbp+70h]
0x18002d1ac  add     rsp, 20h
0x18002d1b0  pop     rbp
0x18002d1b1  retn
0x18002d1b3  push    rbp
0x18002d1b5  sub     rsp, 20h
0x18002d1b9  mov     rbp, rdx
0x18002d1bc  mov     rax, [rcx]
0x18002d1bf  mov     edx, [rax]
0x18002d1c1  mov     [rbp+0D0h], rcx
0x18002d1c8  mov     [rbp+78h], edx
0x18002d1cb  mov     eax, [rbp+78h]
0x18002d1ce  cmp     eax, 0E06D7363h
0x18002d1d3  jnz     short loc_18002D1EC
0x18002d1d5  mov     rdx, [rbp+0D0h]
0x18002d1dc  mov     ecx, [rbp+78h]
0x18002d1df  call    _XcptFilter_0
0x18002d1e4  mov     [rbp+80h], eax
0x18002d1ea  jmp     short loc_18002D1F6
0x18002d1ec  mov     dword ptr [rbp+80h], 0
0x18002d1f6  mov     eax, [rbp+80h]
0x18002d1fc  add     rsp, 20h
0x18002d200  pop     rbp
0x18002d201  retn
0x18002d203  push    rbp
0x18002d205  sub     rsp, 20h
0x18002d209  mov     rbp, rdx
0x18002d20c  mov     rax, [rcx]
0x18002d20f  mov     edx, [rax]
0x18002d211  mov     [rbp+0D8h], rcx
0x18002d218  mov     [rbp+88h], edx
0x18002d21e  mov     eax, [rbp+88h]
0x18002d224  cmp     eax, 0E06D7363h
0x18002d229  jnz     short loc_18002D245
0x18002d22b  mov     rdx, [rbp+0D8h]
0x18002d232  mov     ecx, [rbp+88h]
0x18002d238  call    _XcptFilter_0
0x18002d23d  mov     [rbp+90h], eax
0x18002d243  jmp     short loc_18002D24F
0x18002d245  mov     dword ptr [rbp+90h], 0
0x18002d24f  mov     eax, [rbp+90h]
0x18002d255  add     rsp, 20h
0x18002d259  pop     rbp
0x18002d25a  retn
0x18002d25c  push    rbp
0x18002d25e  sub     rsp, 20h
0x18002d262  mov     rbp, rdx
0x18002d265  mov     rax, [rcx]
0x18002d268  mov     edx, [rax]
0x18002d26a  mov     [rbp+0E0h], rcx
0x18002d271  mov     [rbp+98h], edx
0x18002d277  mov     eax, [rbp+98h]
0x18002d27d  cmp     eax, 0E06D7363h
0x18002d282  jnz     short loc_18002D29E
0x18002d284  mov     rdx, [rbp+0E0h]
0x18002d28b  mov     ecx, [rbp+98h]
0x18002d291  call    _XcptFilter_0
0x18002d296  mov     [rbp+0A0h], eax
0x18002d29c  jmp     short loc_18002D2A8
0x18002d29e  mov     dword ptr [rbp+0A0h], 0
0x18002d2a8  mov     eax, [rbp+0A0h]
0x18002d2ae  add     rsp, 20h
0x18002d2b2  pop     rbp
0x18002d2b3  retn
0x18002d2b5  push    rbp
0x18002d2b7  sub     rsp, 20h
0x18002d2bb  mov     rbp, rdx
0x18002d2be  cmp     dword ptr [rbp+118h], 1
0x18002d2c5  ja      short loc_18002D2D1
0x18002d2c7  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
