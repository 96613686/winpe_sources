# __DllMainCRTStartup

- ea: `0x1800012c4`
- end: `0x1800014d0`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180001280`

## callees

- `0x180001050`
- `0x1800012c4`
- `0x1800014d6`
- `0x180001774`
- `0x180001880`

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
  if ( (_DWORD)fdwReason || dword_1800100E0 )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_1800100E4 = 1;
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
            if ( dword_1800100E4 )
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
0x1800012c4  mov     [rsp+lpvReserved], r8
0x1800012c9  mov     [rsp+arg_8], edx
0x1800012cd  mov     [rsp+arg_0], rcx
0x1800012d2  push    rbx
0x1800012d3  push    rsi
0x1800012d4  push    rdi
0x1800012d5  sub     rsp, 0F0h
0x1800012dc  mov     edi, edx
0x1800012de  mov     rsi, rcx
0x1800012e1  mov     ebx, 1
0x1800012e6  cmp     edx, ebx
0x1800012e8  ja      short loc_1800012F0
0x1800012ea  mov     cs:__native_dllmain_reason, edx
0x1800012f0  test    edx, edx
0x1800012f2  jnz     short loc_180001307
0x1800012f4  cmp     cs:dword_1800100E0, edx
0x1800012fa  jnz     short loc_180001307
0x1800012fc  xor     ebx, ebx
0x1800012fe  mov     [rsp+108h+var_E8], ebx
0x180001302  jmp     loc_1800014B4
0x180001307  lea     eax, [rdx-1]
0x18000130a  cmp     eax, 1
0x18000130d  ja      loc_180001394
0x180001313  mov     rax, cs:_pRawDllMain
0x18000131a  test    rax, rax
0x18000131d  jz      short loc_180001355
0x18000131f  cmp     edx, 1
0x180001322  jnz     short loc_18000132A
0x180001324  mov     cs:dword_1800100E4, edx
0x18000132a  mov     r8, [rsp+108h+lpvReserved]
0x180001332  call    cs:__guard_dispatch_icall_fptr
0x180001338  mov     ebx, eax
0x18000133a  mov     [rsp+108h+var_E8], eax
0x18000133e  jmp     short loc_180001355
0x180001340  xor     ebx, ebx
0x180001342  mov     [rsp+108h+var_E8], ebx
0x180001346  mov     edi, [rsp+108h+arg_8]
0x18000134d  mov     rsi, [rsp+108h+arg_0]
0x180001355  test    ebx, ebx
0x180001357  jz      loc_1800014B4
0x18000135d  mov     r8, [rsp+108h+lpvReserved]
0x180001365  mov     edx, edi
0x180001367  mov     rcx, rsi
0x18000136a  call    _CRT_INIT
0x18000136f  mov     ebx, eax
0x180001371  mov     [rsp+108h+var_E8], eax
0x180001375  jmp     short loc_18000138C
0x180001377  xor     ebx, ebx
0x180001379  mov     [rsp+108h+var_E8], ebx
0x18000137d  mov     edi, [rsp+108h+arg_8]
0x180001384  mov     rsi, [rsp+108h+arg_0]
0x18000138c  test    ebx, ebx
0x18000138e  jz      loc_1800014B4
0x180001394  mov     r8, [rsp+108h+lpvReserved]; lpvReserved
0x18000139c  mov     edx, edi; fdwReason
0x18000139e  mov     rcx, rsi; hinstDLL
0x1800013a1  call    DllMain
0x1800013a6  mov     ebx, eax
0x1800013a8  mov     [rsp+108h+var_E8], eax
0x1800013ac  jmp     short loc_1800013C3
0x1800013ae  xor     ebx, ebx
0x1800013b0  mov     [rsp+108h+var_E8], ebx
0x1800013b4  mov     edi, [rsp+108h+arg_8]
0x1800013bb  mov     rsi, [rsp+108h+arg_0]
0x1800013c3  cmp     edi, 1
0x1800013c6  jnz     short loc_18000143F
0x1800013c8  test    ebx, ebx
0x1800013ca  jnz     short loc_18000143F
0x1800013cc  xor     r8d, r8d; lpvReserved
0x1800013cf  xor     edx, edx; fdwReason
0x1800013d1  mov     rcx, rsi; hinstDLL
0x1800013d4  call    DllMain
0x1800013d9  jmp     short loc_1800013EE
0x1800013db  mov     edi, [rsp+108h+arg_8]
0x1800013e2  mov     rsi, [rsp+108h+arg_0]
0x1800013ea  mov     ebx, [rsp+108h+var_E8]
0x1800013ee  xor     r8d, r8d
0x1800013f1  xor     edx, edx
0x1800013f3  mov     rcx, rsi
0x1800013f6  call    _CRT_INIT
0x1800013fb  jmp     short loc_180001410
0x1800013fd  mov     edi, [rsp+108h+arg_8]
0x180001404  mov     rsi, [rsp+108h+arg_0]
0x18000140c  mov     ebx, [rsp+108h+var_E8]
0x180001410  mov     rax, cs:_pRawDllMain
0x180001417  test    rax, rax
0x18000141a  jz      short loc_18000143F
0x18000141c  xor     r8d, r8d
0x18000141f  xor     edx, edx
0x180001421  mov     rcx, rsi
0x180001424  call    cs:__guard_dispatch_icall_fptr
0x18000142a  jmp     short loc_18000143F
0x18000142c  mov     edi, [rsp+108h+arg_8]
0x180001433  mov     rsi, [rsp+108h+arg_0]
0x18000143b  mov     ebx, [rsp+108h+var_E8]
0x18000143f  test    edi, edi
0x180001441  jz      short loc_180001448
0x180001443  cmp     edi, 3
0x180001446  jnz     short loc_1800014B4
0x180001448  mov     r8, [rsp+108h+lpvReserved]
0x180001450  mov     edx, edi
0x180001452  mov     rcx, rsi
0x180001455  call    _CRT_INIT
0x18000145a  mov     ebx, eax
0x18000145c  mov     [rsp+108h+var_E8], eax
0x180001460  jmp     short loc_180001477
0x180001462  xor     ebx, ebx
0x180001464  mov     [rsp+108h+var_E8], ebx
0x180001468  mov     edi, [rsp+108h+arg_8]
0x18000146f  mov     rsi, [rsp+108h+arg_0]
0x180001477  mov     rax, cs:_pRawDllMain
0x18000147e  test    rax, rax
0x180001481  jz      short loc_1800014B4
0x180001483  cmp     cs:dword_1800100E4, 0
0x18000148a  jz      short loc_1800014B4
0x18000148c  mov     r8, [rsp+108h+lpvReserved]
0x180001494  mov     edx, edi
0x180001496  mov     rcx, rsi
0x180001499  call    cs:__guard_dispatch_icall_fptr
0x18000149f  mov     ebx, eax
0x1800014a1  mov     [rsp+108h+var_E8], eax
0x1800014a5  jmp     short loc_1800014B4
0x1800014a7  xor     ebx, ebx
0x1800014a9  mov     [rsp+108h+var_E8], ebx
0x1800014ad  mov     edi, [rsp+108h+arg_8]
0x1800014b4  cmp     edi, 1
0x1800014b7  ja      short loc_1800014C3
0x1800014b9  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x1800014c3  mov     eax, ebx
0x1800014c5  add     rsp, 0F0h
0x1800014cc  pop     rdi
0x1800014cd  pop     rsi
0x1800014ce  pop     rbx
0x1800014cf  retn
0x1800018c0  push    rbp
0x1800018c2  sub     rsp, 20h
0x1800018c6  mov     rbp, rdx
0x1800018c9  mov     rax, [rcx]
0x1800018cc  mov     edx, [rax]
0x1800018ce  mov     [rbp+0A8h], rcx
0x1800018d5  mov     [rbp+28h], edx
0x1800018d8  mov     eax, [rbp+28h]
0x1800018db  cmp     eax, 0E06D7363h
0x1800018e0  jnz     short loc_1800018F6
0x1800018e2  mov     rdx, [rbp+0A8h]
0x1800018e9  mov     ecx, [rbp+28h]
0x1800018ec  call    _XcptFilter_0
0x1800018f1  mov     [rbp+30h], eax
0x1800018f4  jmp     short loc_1800018FD
0x1800018f6  mov     dword ptr [rbp+30h], 0
0x1800018fd  mov     eax, [rbp+30h]
0x180001900  add     rsp, 20h
0x180001904  pop     rbp
0x180001905  retn
0x180001907  push    rbp
0x180001909  sub     rsp, 20h
0x18000190d  mov     rbp, rdx
0x180001910  mov     rax, [rcx]
0x180001913  mov     edx, [rax]
0x180001915  mov     [rbp+0B0h], rcx
0x18000191c  mov     [rbp+38h], edx
0x18000191f  mov     eax, [rbp+38h]
0x180001922  cmp     eax, 0E06D7363h
0x180001927  jnz     short loc_18000193D
0x180001929  mov     rdx, [rbp+0B0h]
0x180001930  mov     ecx, [rbp+38h]
0x180001933  call    _XcptFilter_0
0x180001938  mov     [rbp+40h], eax
0x18000193b  jmp     short loc_180001944
0x18000193d  mov     dword ptr [rbp+40h], 0
0x180001944  mov     eax, [rbp+40h]
0x180001947  add     rsp, 20h
0x18000194b  pop     rbp
0x18000194c  retn
0x18000194e  push    rbp
0x180001950  sub     rsp, 20h
0x180001954  mov     rbp, rdx
0x180001957  mov     rax, [rcx]
0x18000195a  mov     edx, [rax]
0x18000195c  mov     [rbp+0B8h], rcx
0x180001963  mov     [rbp+48h], edx
0x180001966  mov     eax, [rbp+48h]
0x180001969  cmp     eax, 0E06D7363h
0x18000196e  jnz     short loc_180001984
0x180001970  mov     rdx, [rbp+0B8h]
0x180001977  mov     ecx, [rbp+48h]
0x18000197a  call    _XcptFilter_0
0x18000197f  mov     [rbp+50h], eax
0x180001982  jmp     short loc_18000198B
0x180001984  mov     dword ptr [rbp+50h], 0
0x18000198b  mov     eax, [rbp+50h]
0x18000198e  add     rsp, 20h
0x180001992  pop     rbp
0x180001993  retn
0x180001995  push    rbp
0x180001997  sub     rsp, 20h
0x18000199b  mov     rbp, rdx
0x18000199e  mov     rax, [rcx]
0x1800019a1  mov     edx, [rax]
0x1800019a3  mov     [rbp+0C0h], rcx
0x1800019aa  mov     [rbp+58h], edx
0x1800019ad  mov     eax, [rbp+58h]
0x1800019b0  cmp     eax, 0E06D7363h
0x1800019b5  jnz     short loc_1800019CB
0x1800019b7  mov     rdx, [rbp+0C0h]
0x1800019be  mov     ecx, [rbp+58h]
0x1800019c1  call    _XcptFilter_0
0x1800019c6  mov     [rbp+60h], eax
0x1800019c9  jmp     short loc_1800019D2
0x1800019cb  mov     dword ptr [rbp+60h], 0
0x1800019d2  mov     eax, [rbp+60h]
0x1800019d5  add     rsp, 20h
0x1800019d9  pop     rbp
0x1800019da  retn
0x1800019dc  push    rbp
0x1800019de  sub     rsp, 20h
0x1800019e2  mov     rbp, rdx
0x1800019e5  mov     rax, [rcx]
0x1800019e8  mov     edx, [rax]
0x1800019ea  mov     [rbp+0C8h], rcx
0x1800019f1  mov     [rbp+68h], edx
0x1800019f4  mov     eax, [rbp+68h]
0x1800019f7  cmp     eax, 0E06D7363h
0x1800019fc  jnz     short loc_180001A12
0x1800019fe  mov     rdx, [rbp+0C8h]
0x180001a05  mov     ecx, [rbp+68h]
0x180001a08  call    _XcptFilter_0
0x180001a0d  mov     [rbp+70h], eax
0x180001a10  jmp     short loc_180001A19
0x180001a12  mov     dword ptr [rbp+70h], 0
0x180001a19  mov     eax, [rbp+70h]
0x180001a1c  add     rsp, 20h
0x180001a20  pop     rbp
0x180001a21  retn
0x180001a23  push    rbp
0x180001a25  sub     rsp, 20h
0x180001a29  mov     rbp, rdx
0x180001a2c  mov     rax, [rcx]
0x180001a2f  mov     edx, [rax]
0x180001a31  mov     [rbp+0D0h], rcx
0x180001a38  mov     [rbp+78h], edx
0x180001a3b  mov     eax, [rbp+78h]
0x180001a3e  cmp     eax, 0E06D7363h
0x180001a43  jnz     short loc_180001A5C
0x180001a45  mov     rdx, [rbp+0D0h]
0x180001a4c  mov     ecx, [rbp+78h]
0x180001a4f  call    _XcptFilter_0
0x180001a54  mov     [rbp+80h], eax
0x180001a5a  jmp     short loc_180001A66
0x180001a5c  mov     dword ptr [rbp+80h], 0
0x180001a66  mov     eax, [rbp+80h]
0x180001a6c  add     rsp, 20h
0x180001a70  pop     rbp
0x180001a71  retn
0x180001a73  push    rbp
0x180001a75  sub     rsp, 20h
0x180001a79  mov     rbp, rdx
0x180001a7c  mov     rax, [rcx]
0x180001a7f  mov     edx, [rax]
0x180001a81  mov     [rbp+0D8h], rcx
0x180001a88  mov     [rbp+88h], edx
0x180001a8e  mov     eax, [rbp+88h]
0x180001a94  cmp     eax, 0E06D7363h
0x180001a99  jnz     short loc_180001AB5
0x180001a9b  mov     rdx, [rbp+0D8h]
0x180001aa2  mov     ecx, [rbp+88h]
0x180001aa8  call    _XcptFilter_0
0x180001aad  mov     [rbp+90h], eax
0x180001ab3  jmp     short loc_180001ABF
0x180001ab5  mov     dword ptr [rbp+90h], 0
0x180001abf  mov     eax, [rbp+90h]
0x180001ac5  add     rsp, 20h
0x180001ac9  pop     rbp
0x180001aca  retn
0x180001acc  push    rbp
0x180001ace  sub     rsp, 20h
0x180001ad2  mov     rbp, rdx
0x180001ad5  mov     rax, [rcx]
0x180001ad8  mov     edx, [rax]
0x180001ada  mov     [rbp+0E0h], rcx
0x180001ae1  mov     [rbp+98h], edx
0x180001ae7  mov     eax, [rbp+98h]
0x180001aed  cmp     eax, 0E06D7363h
0x180001af2  jnz     short loc_180001B0E
0x180001af4  mov     rdx, [rbp+0E0h]
0x180001afb  mov     ecx, [rbp+98h]
0x180001b01  call    _XcptFilter_0
0x180001b06  mov     [rbp+0A0h], eax
0x180001b0c  jmp     short loc_180001B18
0x180001b0e  mov     dword ptr [rbp+0A0h], 0
0x180001b18  mov     eax, [rbp+0A0h]
0x180001b1e  add     rsp, 20h
0x180001b22  pop     rbp
0x180001b23  retn
0x180001b25  push    rbp
0x180001b27  sub     rsp, 20h
0x180001b2b  mov     rbp, rdx
0x180001b2e  cmp     dword ptr [rbp+118h], 1
0x180001b35  ja      short loc_180001B41
0x180001b37  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
