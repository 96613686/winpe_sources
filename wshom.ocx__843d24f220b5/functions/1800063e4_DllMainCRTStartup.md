# __DllMainCRTStartup

- ea: `0x1800063e4`
- end: `0x1800065f0`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1800063a0`

## callees

- `0x180002c00`
- `0x180006170`
- `0x1800063e4`
- `0x180006938`
- `0x180010290`

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
  if ( (_DWORD)fdwReason || dword_180018620 )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_180018624 = 1;
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
            if ( dword_180018624 )
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
0x1800063e4  mov     [rsp+lpvReserved], r8
0x1800063e9  mov     [rsp+arg_8], edx
0x1800063ed  mov     [rsp+arg_0], rcx
0x1800063f2  push    rbx
0x1800063f3  push    rsi
0x1800063f4  push    rdi
0x1800063f5  sub     rsp, 0F0h
0x1800063fc  mov     edi, edx
0x1800063fe  mov     rsi, rcx
0x180006401  mov     ebx, 1
0x180006406  cmp     edx, ebx
0x180006408  ja      short loc_180006410
0x18000640a  mov     cs:__native_dllmain_reason, edx
0x180006410  test    edx, edx
0x180006412  jnz     short loc_180006427
0x180006414  cmp     cs:dword_180018620, edx
0x18000641a  jnz     short loc_180006427
0x18000641c  xor     ebx, ebx
0x18000641e  mov     [rsp+108h+var_E8], ebx
0x180006422  jmp     loc_1800065D4
0x180006427  lea     eax, [rdx-1]
0x18000642a  cmp     eax, 1
0x18000642d  ja      loc_1800064B4
0x180006433  mov     rax, cs:_pRawDllMain
0x18000643a  test    rax, rax
0x18000643d  jz      short loc_180006475
0x18000643f  cmp     edx, 1
0x180006442  jnz     short loc_18000644A
0x180006444  mov     cs:dword_180018624, edx
0x18000644a  mov     r8, [rsp+108h+lpvReserved]
0x180006452  call    cs:__guard_dispatch_icall_fptr
0x180006458  mov     ebx, eax
0x18000645a  mov     [rsp+108h+var_E8], eax
0x18000645e  jmp     short loc_180006475
0x180006460  xor     ebx, ebx
0x180006462  mov     [rsp+108h+var_E8], ebx
0x180006466  mov     edi, [rsp+108h+arg_8]
0x18000646d  mov     rsi, [rsp+108h+arg_0]
0x180006475  test    ebx, ebx
0x180006477  jz      loc_1800065D4
0x18000647d  mov     r8, [rsp+108h+lpvReserved]
0x180006485  mov     edx, edi
0x180006487  mov     rcx, rsi
0x18000648a  call    _CRT_INIT
0x18000648f  mov     ebx, eax
0x180006491  mov     [rsp+108h+var_E8], eax
0x180006495  jmp     short loc_1800064AC
0x180006497  xor     ebx, ebx
0x180006499  mov     [rsp+108h+var_E8], ebx
0x18000649d  mov     edi, [rsp+108h+arg_8]
0x1800064a4  mov     rsi, [rsp+108h+arg_0]
0x1800064ac  test    ebx, ebx
0x1800064ae  jz      loc_1800065D4
0x1800064b4  mov     r8, [rsp+108h+lpvReserved]; lpvReserved
0x1800064bc  mov     edx, edi; fdwReason
0x1800064be  mov     rcx, rsi; hinstDLL
0x1800064c1  call    DllMain
0x1800064c6  mov     ebx, eax
0x1800064c8  mov     [rsp+108h+var_E8], eax
0x1800064cc  jmp     short loc_1800064E3
0x1800064ce  xor     ebx, ebx
0x1800064d0  mov     [rsp+108h+var_E8], ebx
0x1800064d4  mov     edi, [rsp+108h+arg_8]
0x1800064db  mov     rsi, [rsp+108h+arg_0]
0x1800064e3  cmp     edi, 1
0x1800064e6  jnz     short loc_18000655F
0x1800064e8  test    ebx, ebx
0x1800064ea  jnz     short loc_18000655F
0x1800064ec  xor     r8d, r8d; lpvReserved
0x1800064ef  xor     edx, edx; fdwReason
0x1800064f1  mov     rcx, rsi; hinstDLL
0x1800064f4  call    DllMain
0x1800064f9  jmp     short loc_18000650E
0x1800064fb  mov     edi, [rsp+108h+arg_8]
0x180006502  mov     rsi, [rsp+108h+arg_0]
0x18000650a  mov     ebx, [rsp+108h+var_E8]
0x18000650e  xor     r8d, r8d
0x180006511  xor     edx, edx
0x180006513  mov     rcx, rsi
0x180006516  call    _CRT_INIT
0x18000651b  jmp     short loc_180006530
0x18000651d  mov     edi, [rsp+108h+arg_8]
0x180006524  mov     rsi, [rsp+108h+arg_0]
0x18000652c  mov     ebx, [rsp+108h+var_E8]
0x180006530  mov     rax, cs:_pRawDllMain
0x180006537  test    rax, rax
0x18000653a  jz      short loc_18000655F
0x18000653c  xor     r8d, r8d
0x18000653f  xor     edx, edx
0x180006541  mov     rcx, rsi
0x180006544  call    cs:__guard_dispatch_icall_fptr
0x18000654a  jmp     short loc_18000655F
0x18000654c  mov     edi, [rsp+108h+arg_8]
0x180006553  mov     rsi, [rsp+108h+arg_0]
0x18000655b  mov     ebx, [rsp+108h+var_E8]
0x18000655f  test    edi, edi
0x180006561  jz      short loc_180006568
0x180006563  cmp     edi, 3
0x180006566  jnz     short loc_1800065D4
0x180006568  mov     r8, [rsp+108h+lpvReserved]
0x180006570  mov     edx, edi
0x180006572  mov     rcx, rsi
0x180006575  call    _CRT_INIT
0x18000657a  mov     ebx, eax
0x18000657c  mov     [rsp+108h+var_E8], eax
0x180006580  jmp     short loc_180006597
0x180006582  xor     ebx, ebx
0x180006584  mov     [rsp+108h+var_E8], ebx
0x180006588  mov     edi, [rsp+108h+arg_8]
0x18000658f  mov     rsi, [rsp+108h+arg_0]
0x180006597  mov     rax, cs:_pRawDllMain
0x18000659e  test    rax, rax
0x1800065a1  jz      short loc_1800065D4
0x1800065a3  cmp     cs:dword_180018624, 0
0x1800065aa  jz      short loc_1800065D4
0x1800065ac  mov     r8, [rsp+108h+lpvReserved]
0x1800065b4  mov     edx, edi
0x1800065b6  mov     rcx, rsi
0x1800065b9  call    cs:__guard_dispatch_icall_fptr
0x1800065bf  mov     ebx, eax
0x1800065c1  mov     [rsp+108h+var_E8], eax
0x1800065c5  jmp     short loc_1800065D4
0x1800065c7  xor     ebx, ebx
0x1800065c9  mov     [rsp+108h+var_E8], ebx
0x1800065cd  mov     edi, [rsp+108h+arg_8]
0x1800065d4  cmp     edi, 1
0x1800065d7  ja      short loc_1800065E3
0x1800065d9  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x1800065e3  mov     eax, ebx
0x1800065e5  add     rsp, 0F0h
0x1800065ec  pop     rdi
0x1800065ed  pop     rsi
0x1800065ee  pop     rbx
0x1800065ef  retn
0x180010360  push    rbp
0x180010362  sub     rsp, 20h
0x180010366  mov     rbp, rdx
0x180010369  mov     rax, [rcx]
0x18001036c  mov     edx, [rax]
0x18001036e  mov     [rbp+0A8h], rcx
0x180010375  mov     [rbp+28h], edx
0x180010378  mov     eax, [rbp+28h]
0x18001037b  cmp     eax, 0E06D7363h
0x180010380  jnz     short loc_180010396
0x180010382  mov     rdx, [rbp+0A8h]
0x180010389  mov     ecx, [rbp+28h]
0x18001038c  call    _XcptFilter_0
0x180010391  mov     [rbp+30h], eax
0x180010394  jmp     short loc_18001039D
0x180010396  mov     dword ptr [rbp+30h], 0
0x18001039d  mov     eax, [rbp+30h]
0x1800103a0  add     rsp, 20h
0x1800103a4  pop     rbp
0x1800103a5  retn
0x1800103a7  push    rbp
0x1800103a9  sub     rsp, 20h
0x1800103ad  mov     rbp, rdx
0x1800103b0  mov     rax, [rcx]
0x1800103b3  mov     edx, [rax]
0x1800103b5  mov     [rbp+0B0h], rcx
0x1800103bc  mov     [rbp+38h], edx
0x1800103bf  mov     eax, [rbp+38h]
0x1800103c2  cmp     eax, 0E06D7363h
0x1800103c7  jnz     short loc_1800103DD
0x1800103c9  mov     rdx, [rbp+0B0h]
0x1800103d0  mov     ecx, [rbp+38h]
0x1800103d3  call    _XcptFilter_0
0x1800103d8  mov     [rbp+40h], eax
0x1800103db  jmp     short loc_1800103E4
0x1800103dd  mov     dword ptr [rbp+40h], 0
0x1800103e4  mov     eax, [rbp+40h]
0x1800103e7  add     rsp, 20h
0x1800103eb  pop     rbp
0x1800103ec  retn
0x1800103ee  push    rbp
0x1800103f0  sub     rsp, 20h
0x1800103f4  mov     rbp, rdx
0x1800103f7  mov     rax, [rcx]
0x1800103fa  mov     edx, [rax]
0x1800103fc  mov     [rbp+0B8h], rcx
0x180010403  mov     [rbp+48h], edx
0x180010406  mov     eax, [rbp+48h]
0x180010409  cmp     eax, 0E06D7363h
0x18001040e  jnz     short loc_180010424
0x180010410  mov     rdx, [rbp+0B8h]
0x180010417  mov     ecx, [rbp+48h]
0x18001041a  call    _XcptFilter_0
0x18001041f  mov     [rbp+50h], eax
0x180010422  jmp     short loc_18001042B
0x180010424  mov     dword ptr [rbp+50h], 0
0x18001042b  mov     eax, [rbp+50h]
0x18001042e  add     rsp, 20h
0x180010432  pop     rbp
0x180010433  retn
0x180010435  push    rbp
0x180010437  sub     rsp, 20h
0x18001043b  mov     rbp, rdx
0x18001043e  mov     rax, [rcx]
0x180010441  mov     edx, [rax]
0x180010443  mov     [rbp+0C0h], rcx
0x18001044a  mov     [rbp+58h], edx
0x18001044d  mov     eax, [rbp+58h]
0x180010450  cmp     eax, 0E06D7363h
0x180010455  jnz     short loc_18001046B
0x180010457  mov     rdx, [rbp+0C0h]
0x18001045e  mov     ecx, [rbp+58h]
0x180010461  call    _XcptFilter_0
0x180010466  mov     [rbp+60h], eax
0x180010469  jmp     short loc_180010472
0x18001046b  mov     dword ptr [rbp+60h], 0
0x180010472  mov     eax, [rbp+60h]
0x180010475  add     rsp, 20h
0x180010479  pop     rbp
0x18001047a  retn
0x18001047c  push    rbp
0x18001047e  sub     rsp, 20h
0x180010482  mov     rbp, rdx
0x180010485  mov     rax, [rcx]
0x180010488  mov     edx, [rax]
0x18001048a  mov     [rbp+0C8h], rcx
0x180010491  mov     [rbp+68h], edx
0x180010494  mov     eax, [rbp+68h]
0x180010497  cmp     eax, 0E06D7363h
0x18001049c  jnz     short loc_1800104B2
0x18001049e  mov     rdx, [rbp+0C8h]
0x1800104a5  mov     ecx, [rbp+68h]
0x1800104a8  call    _XcptFilter_0
0x1800104ad  mov     [rbp+70h], eax
0x1800104b0  jmp     short loc_1800104B9
0x1800104b2  mov     dword ptr [rbp+70h], 0
0x1800104b9  mov     eax, [rbp+70h]
0x1800104bc  add     rsp, 20h
0x1800104c0  pop     rbp
0x1800104c1  retn
0x1800104c3  push    rbp
0x1800104c5  sub     rsp, 20h
0x1800104c9  mov     rbp, rdx
0x1800104cc  mov     rax, [rcx]
0x1800104cf  mov     edx, [rax]
0x1800104d1  mov     [rbp+0D0h], rcx
0x1800104d8  mov     [rbp+78h], edx
0x1800104db  mov     eax, [rbp+78h]
0x1800104de  cmp     eax, 0E06D7363h
0x1800104e3  jnz     short loc_1800104FC
0x1800104e5  mov     rdx, [rbp+0D0h]
0x1800104ec  mov     ecx, [rbp+78h]
0x1800104ef  call    _XcptFilter_0
0x1800104f4  mov     [rbp+80h], eax
0x1800104fa  jmp     short loc_180010506
0x1800104fc  mov     dword ptr [rbp+80h], 0
0x180010506  mov     eax, [rbp+80h]
0x18001050c  add     rsp, 20h
0x180010510  pop     rbp
0x180010511  retn
0x180010513  push    rbp
0x180010515  sub     rsp, 20h
0x180010519  mov     rbp, rdx
0x18001051c  mov     rax, [rcx]
0x18001051f  mov     edx, [rax]
0x180010521  mov     [rbp+0D8h], rcx
0x180010528  mov     [rbp+88h], edx
0x18001052e  mov     eax, [rbp+88h]
0x180010534  cmp     eax, 0E06D7363h
0x180010539  jnz     short loc_180010555
0x18001053b  mov     rdx, [rbp+0D8h]
0x180010542  mov     ecx, [rbp+88h]
0x180010548  call    _XcptFilter_0
0x18001054d  mov     [rbp+90h], eax
0x180010553  jmp     short loc_18001055F
0x180010555  mov     dword ptr [rbp+90h], 0
0x18001055f  mov     eax, [rbp+90h]
0x180010565  add     rsp, 20h
0x180010569  pop     rbp
0x18001056a  retn
0x18001056c  push    rbp
0x18001056e  sub     rsp, 20h
0x180010572  mov     rbp, rdx
0x180010575  mov     rax, [rcx]
0x180010578  mov     edx, [rax]
0x18001057a  mov     [rbp+0E0h], rcx
0x180010581  mov     [rbp+98h], edx
0x180010587  mov     eax, [rbp+98h]
0x18001058d  cmp     eax, 0E06D7363h
0x180010592  jnz     short loc_1800105AE
0x180010594  mov     rdx, [rbp+0E0h]
0x18001059b  mov     ecx, [rbp+98h]
0x1800105a1  call    _XcptFilter_0
0x1800105a6  mov     [rbp+0A0h], eax
0x1800105ac  jmp     short loc_1800105B8
0x1800105ae  mov     dword ptr [rbp+0A0h], 0
0x1800105b8  mov     eax, [rbp+0A0h]
0x1800105be  add     rsp, 20h
0x1800105c2  pop     rbp
0x1800105c3  retn
0x1800105c5  push    rbp
0x1800105c7  sub     rsp, 20h
0x1800105cb  mov     rbp, rdx
0x1800105ce  cmp     dword ptr [rbp+118h], 1
0x1800105d5  ja      short loc_1800105E1
0x1800105d7  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
