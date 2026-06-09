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
- `0x180001560`
- `0x180001998`
- `0x1800034d0`

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
  if ( (_DWORD)fdwReason || dword_1800070A0 )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_1800070A4 = 1;
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
            if ( dword_1800070A4 )
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
0x180001344  cmp     cs:dword_1800070A0, edx
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
0x180001374  mov     cs:dword_1800070A4, edx
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
0x1800014d3  cmp     cs:dword_1800070A4, 0
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
0x180003540  push    rbp
0x180003542  sub     rsp, 20h
0x180003546  mov     rbp, rdx
0x180003549  mov     rax, [rcx]
0x18000354c  mov     edx, [rax]
0x18000354e  mov     [rbp+0A8h], rcx
0x180003555  mov     [rbp+28h], edx
0x180003558  mov     eax, [rbp+28h]
0x18000355b  cmp     eax, 0E06D7363h
0x180003560  jnz     short loc_180003576
0x180003562  mov     rdx, [rbp+0A8h]
0x180003569  mov     ecx, [rbp+28h]
0x18000356c  call    _XcptFilter_0
0x180003571  mov     [rbp+30h], eax
0x180003574  jmp     short loc_18000357D
0x180003576  mov     dword ptr [rbp+30h], 0
0x18000357d  mov     eax, [rbp+30h]
0x180003580  add     rsp, 20h
0x180003584  pop     rbp
0x180003585  retn
0x180003587  push    rbp
0x180003589  sub     rsp, 20h
0x18000358d  mov     rbp, rdx
0x180003590  mov     rax, [rcx]
0x180003593  mov     edx, [rax]
0x180003595  mov     [rbp+0B0h], rcx
0x18000359c  mov     [rbp+38h], edx
0x18000359f  mov     eax, [rbp+38h]
0x1800035a2  cmp     eax, 0E06D7363h
0x1800035a7  jnz     short loc_1800035BD
0x1800035a9  mov     rdx, [rbp+0B0h]
0x1800035b0  mov     ecx, [rbp+38h]
0x1800035b3  call    _XcptFilter_0
0x1800035b8  mov     [rbp+40h], eax
0x1800035bb  jmp     short loc_1800035C4
0x1800035bd  mov     dword ptr [rbp+40h], 0
0x1800035c4  mov     eax, [rbp+40h]
0x1800035c7  add     rsp, 20h
0x1800035cb  pop     rbp
0x1800035cc  retn
0x1800035ce  push    rbp
0x1800035d0  sub     rsp, 20h
0x1800035d4  mov     rbp, rdx
0x1800035d7  mov     rax, [rcx]
0x1800035da  mov     edx, [rax]
0x1800035dc  mov     [rbp+0B8h], rcx
0x1800035e3  mov     [rbp+48h], edx
0x1800035e6  mov     eax, [rbp+48h]
0x1800035e9  cmp     eax, 0E06D7363h
0x1800035ee  jnz     short loc_180003604
0x1800035f0  mov     rdx, [rbp+0B8h]
0x1800035f7  mov     ecx, [rbp+48h]
0x1800035fa  call    _XcptFilter_0
0x1800035ff  mov     [rbp+50h], eax
0x180003602  jmp     short loc_18000360B
0x180003604  mov     dword ptr [rbp+50h], 0
0x18000360b  mov     eax, [rbp+50h]
0x18000360e  add     rsp, 20h
0x180003612  pop     rbp
0x180003613  retn
0x180003615  push    rbp
0x180003617  sub     rsp, 20h
0x18000361b  mov     rbp, rdx
0x18000361e  mov     rax, [rcx]
0x180003621  mov     edx, [rax]
0x180003623  mov     [rbp+0C0h], rcx
0x18000362a  mov     [rbp+58h], edx
0x18000362d  mov     eax, [rbp+58h]
0x180003630  cmp     eax, 0E06D7363h
0x180003635  jnz     short loc_18000364B
0x180003637  mov     rdx, [rbp+0C0h]
0x18000363e  mov     ecx, [rbp+58h]
0x180003641  call    _XcptFilter_0
0x180003646  mov     [rbp+60h], eax
0x180003649  jmp     short loc_180003652
0x18000364b  mov     dword ptr [rbp+60h], 0
0x180003652  mov     eax, [rbp+60h]
0x180003655  add     rsp, 20h
0x180003659  pop     rbp
0x18000365a  retn
0x18000365c  push    rbp
0x18000365e  sub     rsp, 20h
0x180003662  mov     rbp, rdx
0x180003665  mov     rax, [rcx]
0x180003668  mov     edx, [rax]
0x18000366a  mov     [rbp+0C8h], rcx
0x180003671  mov     [rbp+68h], edx
0x180003674  mov     eax, [rbp+68h]
0x180003677  cmp     eax, 0E06D7363h
0x18000367c  jnz     short loc_180003692
0x18000367e  mov     rdx, [rbp+0C8h]
0x180003685  mov     ecx, [rbp+68h]
0x180003688  call    _XcptFilter_0
0x18000368d  mov     [rbp+70h], eax
0x180003690  jmp     short loc_180003699
0x180003692  mov     dword ptr [rbp+70h], 0
0x180003699  mov     eax, [rbp+70h]
0x18000369c  add     rsp, 20h
0x1800036a0  pop     rbp
0x1800036a1  retn
0x1800036a3  push    rbp
0x1800036a5  sub     rsp, 20h
0x1800036a9  mov     rbp, rdx
0x1800036ac  mov     rax, [rcx]
0x1800036af  mov     edx, [rax]
0x1800036b1  mov     [rbp+0D0h], rcx
0x1800036b8  mov     [rbp+78h], edx
0x1800036bb  mov     eax, [rbp+78h]
0x1800036be  cmp     eax, 0E06D7363h
0x1800036c3  jnz     short loc_1800036DC
0x1800036c5  mov     rdx, [rbp+0D0h]
0x1800036cc  mov     ecx, [rbp+78h]
0x1800036cf  call    _XcptFilter_0
0x1800036d4  mov     [rbp+80h], eax
0x1800036da  jmp     short loc_1800036E6
0x1800036dc  mov     dword ptr [rbp+80h], 0
0x1800036e6  mov     eax, [rbp+80h]
0x1800036ec  add     rsp, 20h
0x1800036f0  pop     rbp
0x1800036f1  retn
0x1800036f3  push    rbp
0x1800036f5  sub     rsp, 20h
0x1800036f9  mov     rbp, rdx
0x1800036fc  mov     rax, [rcx]
0x1800036ff  mov     edx, [rax]
0x180003701  mov     [rbp+0D8h], rcx
0x180003708  mov     [rbp+88h], edx
0x18000370e  mov     eax, [rbp+88h]
0x180003714  cmp     eax, 0E06D7363h
0x180003719  jnz     short loc_180003735
0x18000371b  mov     rdx, [rbp+0D8h]
0x180003722  mov     ecx, [rbp+88h]
0x180003728  call    _XcptFilter_0
0x18000372d  mov     [rbp+90h], eax
0x180003733  jmp     short loc_18000373F
0x180003735  mov     dword ptr [rbp+90h], 0
0x18000373f  mov     eax, [rbp+90h]
0x180003745  add     rsp, 20h
0x180003749  pop     rbp
0x18000374a  retn
0x18000374c  push    rbp
0x18000374e  sub     rsp, 20h
0x180003752  mov     rbp, rdx
0x180003755  mov     rax, [rcx]
0x180003758  mov     edx, [rax]
0x18000375a  mov     [rbp+0E0h], rcx
0x180003761  mov     [rbp+98h], edx
0x180003767  mov     eax, [rbp+98h]
0x18000376d  cmp     eax, 0E06D7363h
0x180003772  jnz     short loc_18000378E
0x180003774  mov     rdx, [rbp+0E0h]
0x18000377b  mov     ecx, [rbp+98h]
0x180003781  call    _XcptFilter_0
0x180003786  mov     [rbp+0A0h], eax
0x18000378c  jmp     short loc_180003798
0x18000378e  mov     dword ptr [rbp+0A0h], 0
0x180003798  mov     eax, [rbp+0A0h]
0x18000379e  add     rsp, 20h
0x1800037a2  pop     rbp
0x1800037a3  retn
0x1800037a5  push    rbp
0x1800037a7  sub     rsp, 20h
0x1800037ab  mov     rbp, rdx
0x1800037ae  cmp     dword ptr [rbp+118h], 1
0x1800037b5  ja      short loc_1800037C1
0x1800037b7  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
