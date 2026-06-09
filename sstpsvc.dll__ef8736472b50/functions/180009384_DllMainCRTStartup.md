# __DllMainCRTStartup

- ea: `0x180009384`
- end: `0x180009590`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180009340`

## callees

- `0x180009110`
- `0x180009384`
- `0x180009856`
- `0x180009a28`
- `0x18001d250`

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
  if ( (_DWORD)fdwReason || dword_18002E340 )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_18002E344 = 1;
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
            if ( dword_18002E344 )
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
0x180009384  mov     [rsp+lpvReserved], r8
0x180009389  mov     [rsp+arg_8], edx
0x18000938d  mov     [rsp+arg_0], rcx
0x180009392  push    rbx
0x180009393  push    rsi
0x180009394  push    rdi
0x180009395  sub     rsp, 0F0h
0x18000939c  mov     edi, edx
0x18000939e  mov     rsi, rcx
0x1800093a1  mov     ebx, 1
0x1800093a6  cmp     edx, ebx
0x1800093a8  ja      short loc_1800093B0
0x1800093aa  mov     cs:__native_dllmain_reason, edx
0x1800093b0  test    edx, edx
0x1800093b2  jnz     short loc_1800093C7
0x1800093b4  cmp     cs:dword_18002E340, edx
0x1800093ba  jnz     short loc_1800093C7
0x1800093bc  xor     ebx, ebx
0x1800093be  mov     [rsp+108h+var_E8], ebx
0x1800093c2  jmp     loc_180009574
0x1800093c7  lea     eax, [rdx-1]
0x1800093ca  cmp     eax, 1
0x1800093cd  ja      loc_180009454
0x1800093d3  mov     rax, cs:_pRawDllMain
0x1800093da  test    rax, rax
0x1800093dd  jz      short loc_180009415
0x1800093df  cmp     edx, 1
0x1800093e2  jnz     short loc_1800093EA
0x1800093e4  mov     cs:dword_18002E344, edx
0x1800093ea  mov     r8, [rsp+108h+lpvReserved]
0x1800093f2  call    cs:__guard_dispatch_icall_fptr
0x1800093f8  mov     ebx, eax
0x1800093fa  mov     [rsp+108h+var_E8], eax
0x1800093fe  jmp     short loc_180009415
0x180009400  xor     ebx, ebx
0x180009402  mov     [rsp+108h+var_E8], ebx
0x180009406  mov     edi, [rsp+108h+arg_8]
0x18000940d  mov     rsi, [rsp+108h+arg_0]
0x180009415  test    ebx, ebx
0x180009417  jz      loc_180009574
0x18000941d  mov     r8, [rsp+108h+lpvReserved]
0x180009425  mov     edx, edi
0x180009427  mov     rcx, rsi
0x18000942a  call    _CRT_INIT
0x18000942f  mov     ebx, eax
0x180009431  mov     [rsp+108h+var_E8], eax
0x180009435  jmp     short loc_18000944C
0x180009437  xor     ebx, ebx
0x180009439  mov     [rsp+108h+var_E8], ebx
0x18000943d  mov     edi, [rsp+108h+arg_8]
0x180009444  mov     rsi, [rsp+108h+arg_0]
0x18000944c  test    ebx, ebx
0x18000944e  jz      loc_180009574
0x180009454  mov     r8, [rsp+108h+lpvReserved]; lpvReserved
0x18000945c  mov     edx, edi; fdwReason
0x18000945e  mov     rcx, rsi; hinstDLL
0x180009461  call    DllMain
0x180009466  mov     ebx, eax
0x180009468  mov     [rsp+108h+var_E8], eax
0x18000946c  jmp     short loc_180009483
0x18000946e  xor     ebx, ebx
0x180009470  mov     [rsp+108h+var_E8], ebx
0x180009474  mov     edi, [rsp+108h+arg_8]
0x18000947b  mov     rsi, [rsp+108h+arg_0]
0x180009483  cmp     edi, 1
0x180009486  jnz     short loc_1800094FF
0x180009488  test    ebx, ebx
0x18000948a  jnz     short loc_1800094FF
0x18000948c  xor     r8d, r8d; lpvReserved
0x18000948f  xor     edx, edx; fdwReason
0x180009491  mov     rcx, rsi; hinstDLL
0x180009494  call    DllMain
0x180009499  jmp     short loc_1800094AE
0x18000949b  mov     edi, [rsp+108h+arg_8]
0x1800094a2  mov     rsi, [rsp+108h+arg_0]
0x1800094aa  mov     ebx, [rsp+108h+var_E8]
0x1800094ae  xor     r8d, r8d
0x1800094b1  xor     edx, edx
0x1800094b3  mov     rcx, rsi
0x1800094b6  call    _CRT_INIT
0x1800094bb  jmp     short loc_1800094D0
0x1800094bd  mov     edi, [rsp+108h+arg_8]
0x1800094c4  mov     rsi, [rsp+108h+arg_0]
0x1800094cc  mov     ebx, [rsp+108h+var_E8]
0x1800094d0  mov     rax, cs:_pRawDllMain
0x1800094d7  test    rax, rax
0x1800094da  jz      short loc_1800094FF
0x1800094dc  xor     r8d, r8d
0x1800094df  xor     edx, edx
0x1800094e1  mov     rcx, rsi
0x1800094e4  call    cs:__guard_dispatch_icall_fptr
0x1800094ea  jmp     short loc_1800094FF
0x1800094ec  mov     edi, [rsp+108h+arg_8]
0x1800094f3  mov     rsi, [rsp+108h+arg_0]
0x1800094fb  mov     ebx, [rsp+108h+var_E8]
0x1800094ff  test    edi, edi
0x180009501  jz      short loc_180009508
0x180009503  cmp     edi, 3
0x180009506  jnz     short loc_180009574
0x180009508  mov     r8, [rsp+108h+lpvReserved]
0x180009510  mov     edx, edi
0x180009512  mov     rcx, rsi
0x180009515  call    _CRT_INIT
0x18000951a  mov     ebx, eax
0x18000951c  mov     [rsp+108h+var_E8], eax
0x180009520  jmp     short loc_180009537
0x180009522  xor     ebx, ebx
0x180009524  mov     [rsp+108h+var_E8], ebx
0x180009528  mov     edi, [rsp+108h+arg_8]
0x18000952f  mov     rsi, [rsp+108h+arg_0]
0x180009537  mov     rax, cs:_pRawDllMain
0x18000953e  test    rax, rax
0x180009541  jz      short loc_180009574
0x180009543  cmp     cs:dword_18002E344, 0
0x18000954a  jz      short loc_180009574
0x18000954c  mov     r8, [rsp+108h+lpvReserved]
0x180009554  mov     edx, edi
0x180009556  mov     rcx, rsi
0x180009559  call    cs:__guard_dispatch_icall_fptr
0x18000955f  mov     ebx, eax
0x180009561  mov     [rsp+108h+var_E8], eax
0x180009565  jmp     short loc_180009574
0x180009567  xor     ebx, ebx
0x180009569  mov     [rsp+108h+var_E8], ebx
0x18000956d  mov     edi, [rsp+108h+arg_8]
0x180009574  cmp     edi, 1
0x180009577  ja      short loc_180009583
0x180009579  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x180009583  mov     eax, ebx
0x180009585  add     rsp, 0F0h
0x18000958c  pop     rdi
0x18000958d  pop     rsi
0x18000958e  pop     rbx
0x18000958f  retn
0x18001d409  push    rbp
0x18001d40b  sub     rsp, 20h
0x18001d40f  mov     rbp, rdx
0x18001d412  mov     rax, [rcx]
0x18001d415  mov     edx, [rax]
0x18001d417  mov     [rbp+0A8h], rcx
0x18001d41e  mov     [rbp+28h], edx
0x18001d421  mov     eax, [rbp+28h]
0x18001d424  cmp     eax, 0E06D7363h
0x18001d429  jnz     short loc_18001D43F
0x18001d42b  mov     rdx, [rbp+0A8h]
0x18001d432  mov     ecx, [rbp+28h]
0x18001d435  call    _XcptFilter_0
0x18001d43a  mov     [rbp+30h], eax
0x18001d43d  jmp     short loc_18001D446
0x18001d43f  mov     dword ptr [rbp+30h], 0
0x18001d446  mov     eax, [rbp+30h]
0x18001d449  add     rsp, 20h
0x18001d44d  pop     rbp
0x18001d44e  retn
0x18001d450  push    rbp
0x18001d452  sub     rsp, 20h
0x18001d456  mov     rbp, rdx
0x18001d459  mov     rax, [rcx]
0x18001d45c  mov     edx, [rax]
0x18001d45e  mov     [rbp+0B0h], rcx
0x18001d465  mov     [rbp+38h], edx
0x18001d468  mov     eax, [rbp+38h]
0x18001d46b  cmp     eax, 0E06D7363h
0x18001d470  jnz     short loc_18001D486
0x18001d472  mov     rdx, [rbp+0B0h]
0x18001d479  mov     ecx, [rbp+38h]
0x18001d47c  call    _XcptFilter_0
0x18001d481  mov     [rbp+40h], eax
0x18001d484  jmp     short loc_18001D48D
0x18001d486  mov     dword ptr [rbp+40h], 0
0x18001d48d  mov     eax, [rbp+40h]
0x18001d490  add     rsp, 20h
0x18001d494  pop     rbp
0x18001d495  retn
0x18001d497  push    rbp
0x18001d499  sub     rsp, 20h
0x18001d49d  mov     rbp, rdx
0x18001d4a0  mov     rax, [rcx]
0x18001d4a3  mov     edx, [rax]
0x18001d4a5  mov     [rbp+0B8h], rcx
0x18001d4ac  mov     [rbp+48h], edx
0x18001d4af  mov     eax, [rbp+48h]
0x18001d4b2  cmp     eax, 0E06D7363h
0x18001d4b7  jnz     short loc_18001D4CD
0x18001d4b9  mov     rdx, [rbp+0B8h]
0x18001d4c0  mov     ecx, [rbp+48h]
0x18001d4c3  call    _XcptFilter_0
0x18001d4c8  mov     [rbp+50h], eax
0x18001d4cb  jmp     short loc_18001D4D4
0x18001d4cd  mov     dword ptr [rbp+50h], 0
0x18001d4d4  mov     eax, [rbp+50h]
0x18001d4d7  add     rsp, 20h
0x18001d4db  pop     rbp
0x18001d4dc  retn
0x18001d4de  push    rbp
0x18001d4e0  sub     rsp, 20h
0x18001d4e4  mov     rbp, rdx
0x18001d4e7  mov     rax, [rcx]
0x18001d4ea  mov     edx, [rax]
0x18001d4ec  mov     [rbp+0C0h], rcx
0x18001d4f3  mov     [rbp+58h], edx
0x18001d4f6  mov     eax, [rbp+58h]
0x18001d4f9  cmp     eax, 0E06D7363h
0x18001d4fe  jnz     short loc_18001D514
0x18001d500  mov     rdx, [rbp+0C0h]
0x18001d507  mov     ecx, [rbp+58h]
0x18001d50a  call    _XcptFilter_0
0x18001d50f  mov     [rbp+60h], eax
0x18001d512  jmp     short loc_18001D51B
0x18001d514  mov     dword ptr [rbp+60h], 0
0x18001d51b  mov     eax, [rbp+60h]
0x18001d51e  add     rsp, 20h
0x18001d522  pop     rbp
0x18001d523  retn
0x18001d525  push    rbp
0x18001d527  sub     rsp, 20h
0x18001d52b  mov     rbp, rdx
0x18001d52e  mov     rax, [rcx]
0x18001d531  mov     edx, [rax]
0x18001d533  mov     [rbp+0C8h], rcx
0x18001d53a  mov     [rbp+68h], edx
0x18001d53d  mov     eax, [rbp+68h]
0x18001d540  cmp     eax, 0E06D7363h
0x18001d545  jnz     short loc_18001D55B
0x18001d547  mov     rdx, [rbp+0C8h]
0x18001d54e  mov     ecx, [rbp+68h]
0x18001d551  call    _XcptFilter_0
0x18001d556  mov     [rbp+70h], eax
0x18001d559  jmp     short loc_18001D562
0x18001d55b  mov     dword ptr [rbp+70h], 0
0x18001d562  mov     eax, [rbp+70h]
0x18001d565  add     rsp, 20h
0x18001d569  pop     rbp
0x18001d56a  retn
0x18001d56c  push    rbp
0x18001d56e  sub     rsp, 20h
0x18001d572  mov     rbp, rdx
0x18001d575  mov     rax, [rcx]
0x18001d578  mov     edx, [rax]
0x18001d57a  mov     [rbp+0D0h], rcx
0x18001d581  mov     [rbp+78h], edx
0x18001d584  mov     eax, [rbp+78h]
0x18001d587  cmp     eax, 0E06D7363h
0x18001d58c  jnz     short loc_18001D5A5
0x18001d58e  mov     rdx, [rbp+0D0h]
0x18001d595  mov     ecx, [rbp+78h]
0x18001d598  call    _XcptFilter_0
0x18001d59d  mov     [rbp+80h], eax
0x18001d5a3  jmp     short loc_18001D5AF
0x18001d5a5  mov     dword ptr [rbp+80h], 0
0x18001d5af  mov     eax, [rbp+80h]
0x18001d5b5  add     rsp, 20h
0x18001d5b9  pop     rbp
0x18001d5ba  retn
0x18001d5bc  push    rbp
0x18001d5be  sub     rsp, 20h
0x18001d5c2  mov     rbp, rdx
0x18001d5c5  mov     rax, [rcx]
0x18001d5c8  mov     edx, [rax]
0x18001d5ca  mov     [rbp+0D8h], rcx
0x18001d5d1  mov     [rbp+88h], edx
0x18001d5d7  mov     eax, [rbp+88h]
0x18001d5dd  cmp     eax, 0E06D7363h
0x18001d5e2  jnz     short loc_18001D5FE
0x18001d5e4  mov     rdx, [rbp+0D8h]
0x18001d5eb  mov     ecx, [rbp+88h]
0x18001d5f1  call    _XcptFilter_0
0x18001d5f6  mov     [rbp+90h], eax
0x18001d5fc  jmp     short loc_18001D608
0x18001d5fe  mov     dword ptr [rbp+90h], 0
0x18001d608  mov     eax, [rbp+90h]
0x18001d60e  add     rsp, 20h
0x18001d612  pop     rbp
0x18001d613  retn
0x18001d615  push    rbp
0x18001d617  sub     rsp, 20h
0x18001d61b  mov     rbp, rdx
0x18001d61e  mov     rax, [rcx]
0x18001d621  mov     edx, [rax]
0x18001d623  mov     [rbp+0E0h], rcx
0x18001d62a  mov     [rbp+98h], edx
0x18001d630  mov     eax, [rbp+98h]
0x18001d636  cmp     eax, 0E06D7363h
0x18001d63b  jnz     short loc_18001D657
0x18001d63d  mov     rdx, [rbp+0E0h]
0x18001d644  mov     ecx, [rbp+98h]
0x18001d64a  call    _XcptFilter_0
0x18001d64f  mov     [rbp+0A0h], eax
0x18001d655  jmp     short loc_18001D661
0x18001d657  mov     dword ptr [rbp+0A0h], 0
0x18001d661  mov     eax, [rbp+0A0h]
0x18001d667  add     rsp, 20h
0x18001d66b  pop     rbp
0x18001d66c  retn
0x18001d66e  push    rbp
0x18001d670  sub     rsp, 20h
0x18001d674  mov     rbp, rdx
0x18001d677  cmp     dword ptr [rbp+118h], 1
0x18001d67e  ja      short loc_18001D68A
0x18001d680  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
