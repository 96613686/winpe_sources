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
- `0x1800016c6`
- `0x180007840`
- `0x18001f9c0`

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
  if ( (_DWORD)fdwReason || dword_18002B240 )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_18002B244 = 1;
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
            if ( dword_18002B244 )
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
0x1800012f4  cmp     cs:dword_18002B240, edx
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
0x180001324  mov     cs:dword_18002B244, edx
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
0x180001483  cmp     cs:dword_18002B244, 0
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
0x18001fa90  push    rbp
0x18001fa92  sub     rsp, 20h
0x18001fa96  mov     rbp, rdx
0x18001fa99  mov     rax, [rcx]
0x18001fa9c  mov     edx, [rax]
0x18001fa9e  mov     [rbp+0A8h], rcx
0x18001faa5  mov     [rbp+28h], edx
0x18001faa8  mov     eax, [rbp+28h]
0x18001faab  cmp     eax, 0E06D7363h
0x18001fab0  jnz     short loc_18001FAC6
0x18001fab2  mov     rdx, [rbp+0A8h]
0x18001fab9  mov     ecx, [rbp+28h]
0x18001fabc  call    _XcptFilter_0
0x18001fac1  mov     [rbp+30h], eax
0x18001fac4  jmp     short loc_18001FACD
0x18001fac6  mov     dword ptr [rbp+30h], 0
0x18001facd  mov     eax, [rbp+30h]
0x18001fad0  add     rsp, 20h
0x18001fad4  pop     rbp
0x18001fad5  retn
0x18001fad7  push    rbp
0x18001fad9  sub     rsp, 20h
0x18001fadd  mov     rbp, rdx
0x18001fae0  mov     rax, [rcx]
0x18001fae3  mov     edx, [rax]
0x18001fae5  mov     [rbp+0B0h], rcx
0x18001faec  mov     [rbp+38h], edx
0x18001faef  mov     eax, [rbp+38h]
0x18001faf2  cmp     eax, 0E06D7363h
0x18001faf7  jnz     short loc_18001FB0D
0x18001faf9  mov     rdx, [rbp+0B0h]
0x18001fb00  mov     ecx, [rbp+38h]
0x18001fb03  call    _XcptFilter_0
0x18001fb08  mov     [rbp+40h], eax
0x18001fb0b  jmp     short loc_18001FB14
0x18001fb0d  mov     dword ptr [rbp+40h], 0
0x18001fb14  mov     eax, [rbp+40h]
0x18001fb17  add     rsp, 20h
0x18001fb1b  pop     rbp
0x18001fb1c  retn
0x18001fb1e  push    rbp
0x18001fb20  sub     rsp, 20h
0x18001fb24  mov     rbp, rdx
0x18001fb27  mov     rax, [rcx]
0x18001fb2a  mov     edx, [rax]
0x18001fb2c  mov     [rbp+0B8h], rcx
0x18001fb33  mov     [rbp+48h], edx
0x18001fb36  mov     eax, [rbp+48h]
0x18001fb39  cmp     eax, 0E06D7363h
0x18001fb3e  jnz     short loc_18001FB54
0x18001fb40  mov     rdx, [rbp+0B8h]
0x18001fb47  mov     ecx, [rbp+48h]
0x18001fb4a  call    _XcptFilter_0
0x18001fb4f  mov     [rbp+50h], eax
0x18001fb52  jmp     short loc_18001FB5B
0x18001fb54  mov     dword ptr [rbp+50h], 0
0x18001fb5b  mov     eax, [rbp+50h]
0x18001fb5e  add     rsp, 20h
0x18001fb62  pop     rbp
0x18001fb63  retn
0x18001fb65  push    rbp
0x18001fb67  sub     rsp, 20h
0x18001fb6b  mov     rbp, rdx
0x18001fb6e  mov     rax, [rcx]
0x18001fb71  mov     edx, [rax]
0x18001fb73  mov     [rbp+0C0h], rcx
0x18001fb7a  mov     [rbp+58h], edx
0x18001fb7d  mov     eax, [rbp+58h]
0x18001fb80  cmp     eax, 0E06D7363h
0x18001fb85  jnz     short loc_18001FB9B
0x18001fb87  mov     rdx, [rbp+0C0h]
0x18001fb8e  mov     ecx, [rbp+58h]
0x18001fb91  call    _XcptFilter_0
0x18001fb96  mov     [rbp+60h], eax
0x18001fb99  jmp     short loc_18001FBA2
0x18001fb9b  mov     dword ptr [rbp+60h], 0
0x18001fba2  mov     eax, [rbp+60h]
0x18001fba5  add     rsp, 20h
0x18001fba9  pop     rbp
0x18001fbaa  retn
0x18001fbac  push    rbp
0x18001fbae  sub     rsp, 20h
0x18001fbb2  mov     rbp, rdx
0x18001fbb5  mov     rax, [rcx]
0x18001fbb8  mov     edx, [rax]
0x18001fbba  mov     [rbp+0C8h], rcx
0x18001fbc1  mov     [rbp+68h], edx
0x18001fbc4  mov     eax, [rbp+68h]
0x18001fbc7  cmp     eax, 0E06D7363h
0x18001fbcc  jnz     short loc_18001FBE2
0x18001fbce  mov     rdx, [rbp+0C8h]
0x18001fbd5  mov     ecx, [rbp+68h]
0x18001fbd8  call    _XcptFilter_0
0x18001fbdd  mov     [rbp+70h], eax
0x18001fbe0  jmp     short loc_18001FBE9
0x18001fbe2  mov     dword ptr [rbp+70h], 0
0x18001fbe9  mov     eax, [rbp+70h]
0x18001fbec  add     rsp, 20h
0x18001fbf0  pop     rbp
0x18001fbf1  retn
0x18001fbf3  push    rbp
0x18001fbf5  sub     rsp, 20h
0x18001fbf9  mov     rbp, rdx
0x18001fbfc  mov     rax, [rcx]
0x18001fbff  mov     edx, [rax]
0x18001fc01  mov     [rbp+0D0h], rcx
0x18001fc08  mov     [rbp+78h], edx
0x18001fc0b  mov     eax, [rbp+78h]
0x18001fc0e  cmp     eax, 0E06D7363h
0x18001fc13  jnz     short loc_18001FC2C
0x18001fc15  mov     rdx, [rbp+0D0h]
0x18001fc1c  mov     ecx, [rbp+78h]
0x18001fc1f  call    _XcptFilter_0
0x18001fc24  mov     [rbp+80h], eax
0x18001fc2a  jmp     short loc_18001FC36
0x18001fc2c  mov     dword ptr [rbp+80h], 0
0x18001fc36  mov     eax, [rbp+80h]
0x18001fc3c  add     rsp, 20h
0x18001fc40  pop     rbp
0x18001fc41  retn
0x18001fc43  push    rbp
0x18001fc45  sub     rsp, 20h
0x18001fc49  mov     rbp, rdx
0x18001fc4c  mov     rax, [rcx]
0x18001fc4f  mov     edx, [rax]
0x18001fc51  mov     [rbp+0D8h], rcx
0x18001fc58  mov     [rbp+88h], edx
0x18001fc5e  mov     eax, [rbp+88h]
0x18001fc64  cmp     eax, 0E06D7363h
0x18001fc69  jnz     short loc_18001FC85
0x18001fc6b  mov     rdx, [rbp+0D8h]
0x18001fc72  mov     ecx, [rbp+88h]
0x18001fc78  call    _XcptFilter_0
0x18001fc7d  mov     [rbp+90h], eax
0x18001fc83  jmp     short loc_18001FC8F
0x18001fc85  mov     dword ptr [rbp+90h], 0
0x18001fc8f  mov     eax, [rbp+90h]
0x18001fc95  add     rsp, 20h
0x18001fc99  pop     rbp
0x18001fc9a  retn
0x18001fc9c  push    rbp
0x18001fc9e  sub     rsp, 20h
0x18001fca2  mov     rbp, rdx
0x18001fca5  mov     rax, [rcx]
0x18001fca8  mov     edx, [rax]
0x18001fcaa  mov     [rbp+0E0h], rcx
0x18001fcb1  mov     [rbp+98h], edx
0x18001fcb7  mov     eax, [rbp+98h]
0x18001fcbd  cmp     eax, 0E06D7363h
0x18001fcc2  jnz     short loc_18001FCDE
0x18001fcc4  mov     rdx, [rbp+0E0h]
0x18001fccb  mov     ecx, [rbp+98h]
0x18001fcd1  call    _XcptFilter_0
0x18001fcd6  mov     [rbp+0A0h], eax
0x18001fcdc  jmp     short loc_18001FCE8
0x18001fcde  mov     dword ptr [rbp+0A0h], 0
0x18001fce8  mov     eax, [rbp+0A0h]
0x18001fcee  add     rsp, 20h
0x18001fcf2  pop     rbp
0x18001fcf3  retn
0x18001fcf5  push    rbp
0x18001fcf7  sub     rsp, 20h
0x18001fcfb  mov     rbp, rdx
0x18001fcfe  cmp     dword ptr [rbp+118h], 1
0x18001fd05  ja      short loc_18001FD11
0x18001fd07  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
