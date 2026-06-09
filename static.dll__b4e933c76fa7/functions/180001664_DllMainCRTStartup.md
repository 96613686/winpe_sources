# __DllMainCRTStartup

- ea: `0x180001664`
- end: `0x180001870`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180001620`

## callees

- `0x1800013f0`
- `0x180001664`
- `0x18000189a`
- `0x180001a78`
- `0x180006850`

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
  if ( (_DWORD)fdwReason || dword_18000B0A0 )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_18000B0A4 = 1;
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
            if ( dword_18000B0A4 )
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
0x180001664  mov     [rsp+lpvReserved], r8
0x180001669  mov     [rsp+arg_8], edx
0x18000166d  mov     [rsp+arg_0], rcx
0x180001672  push    rbx
0x180001673  push    rsi
0x180001674  push    rdi
0x180001675  sub     rsp, 0F0h
0x18000167c  mov     edi, edx
0x18000167e  mov     rsi, rcx
0x180001681  mov     ebx, 1
0x180001686  cmp     edx, ebx
0x180001688  ja      short loc_180001690
0x18000168a  mov     cs:__native_dllmain_reason, edx
0x180001690  test    edx, edx
0x180001692  jnz     short loc_1800016A7
0x180001694  cmp     cs:dword_18000B0A0, edx
0x18000169a  jnz     short loc_1800016A7
0x18000169c  xor     ebx, ebx
0x18000169e  mov     [rsp+108h+var_E8], ebx
0x1800016a2  jmp     loc_180001854
0x1800016a7  lea     eax, [rdx-1]
0x1800016aa  cmp     eax, 1
0x1800016ad  ja      loc_180001734
0x1800016b3  mov     rax, cs:_pRawDllMain
0x1800016ba  test    rax, rax
0x1800016bd  jz      short loc_1800016F5
0x1800016bf  cmp     edx, 1
0x1800016c2  jnz     short loc_1800016CA
0x1800016c4  mov     cs:dword_18000B0A4, edx
0x1800016ca  mov     r8, [rsp+108h+lpvReserved]
0x1800016d2  call    cs:__guard_dispatch_icall_fptr
0x1800016d8  mov     ebx, eax
0x1800016da  mov     [rsp+108h+var_E8], eax
0x1800016de  jmp     short loc_1800016F5
0x1800016e0  xor     ebx, ebx
0x1800016e2  mov     [rsp+108h+var_E8], ebx
0x1800016e6  mov     edi, [rsp+108h+arg_8]
0x1800016ed  mov     rsi, [rsp+108h+arg_0]
0x1800016f5  test    ebx, ebx
0x1800016f7  jz      loc_180001854
0x1800016fd  mov     r8, [rsp+108h+lpvReserved]
0x180001705  mov     edx, edi
0x180001707  mov     rcx, rsi
0x18000170a  call    _CRT_INIT
0x18000170f  mov     ebx, eax
0x180001711  mov     [rsp+108h+var_E8], eax
0x180001715  jmp     short loc_18000172C
0x180001717  xor     ebx, ebx
0x180001719  mov     [rsp+108h+var_E8], ebx
0x18000171d  mov     edi, [rsp+108h+arg_8]
0x180001724  mov     rsi, [rsp+108h+arg_0]
0x18000172c  test    ebx, ebx
0x18000172e  jz      loc_180001854
0x180001734  mov     r8, [rsp+108h+lpvReserved]; lpvReserved
0x18000173c  mov     edx, edi; fdwReason
0x18000173e  mov     rcx, rsi; hinstDLL
0x180001741  call    DllMain
0x180001746  mov     ebx, eax
0x180001748  mov     [rsp+108h+var_E8], eax
0x18000174c  jmp     short loc_180001763
0x18000174e  xor     ebx, ebx
0x180001750  mov     [rsp+108h+var_E8], ebx
0x180001754  mov     edi, [rsp+108h+arg_8]
0x18000175b  mov     rsi, [rsp+108h+arg_0]
0x180001763  cmp     edi, 1
0x180001766  jnz     short loc_1800017DF
0x180001768  test    ebx, ebx
0x18000176a  jnz     short loc_1800017DF
0x18000176c  xor     r8d, r8d; lpvReserved
0x18000176f  xor     edx, edx; fdwReason
0x180001771  mov     rcx, rsi; hinstDLL
0x180001774  call    DllMain
0x180001779  jmp     short loc_18000178E
0x18000177b  mov     edi, [rsp+108h+arg_8]
0x180001782  mov     rsi, [rsp+108h+arg_0]
0x18000178a  mov     ebx, [rsp+108h+var_E8]
0x18000178e  xor     r8d, r8d
0x180001791  xor     edx, edx
0x180001793  mov     rcx, rsi
0x180001796  call    _CRT_INIT
0x18000179b  jmp     short loc_1800017B0
0x18000179d  mov     edi, [rsp+108h+arg_8]
0x1800017a4  mov     rsi, [rsp+108h+arg_0]
0x1800017ac  mov     ebx, [rsp+108h+var_E8]
0x1800017b0  mov     rax, cs:_pRawDllMain
0x1800017b7  test    rax, rax
0x1800017ba  jz      short loc_1800017DF
0x1800017bc  xor     r8d, r8d
0x1800017bf  xor     edx, edx
0x1800017c1  mov     rcx, rsi
0x1800017c4  call    cs:__guard_dispatch_icall_fptr
0x1800017ca  jmp     short loc_1800017DF
0x1800017cc  mov     edi, [rsp+108h+arg_8]
0x1800017d3  mov     rsi, [rsp+108h+arg_0]
0x1800017db  mov     ebx, [rsp+108h+var_E8]
0x1800017df  test    edi, edi
0x1800017e1  jz      short loc_1800017E8
0x1800017e3  cmp     edi, 3
0x1800017e6  jnz     short loc_180001854
0x1800017e8  mov     r8, [rsp+108h+lpvReserved]
0x1800017f0  mov     edx, edi
0x1800017f2  mov     rcx, rsi
0x1800017f5  call    _CRT_INIT
0x1800017fa  mov     ebx, eax
0x1800017fc  mov     [rsp+108h+var_E8], eax
0x180001800  jmp     short loc_180001817
0x180001802  xor     ebx, ebx
0x180001804  mov     [rsp+108h+var_E8], ebx
0x180001808  mov     edi, [rsp+108h+arg_8]
0x18000180f  mov     rsi, [rsp+108h+arg_0]
0x180001817  mov     rax, cs:_pRawDllMain
0x18000181e  test    rax, rax
0x180001821  jz      short loc_180001854
0x180001823  cmp     cs:dword_18000B0A4, 0
0x18000182a  jz      short loc_180001854
0x18000182c  mov     r8, [rsp+108h+lpvReserved]
0x180001834  mov     edx, edi
0x180001836  mov     rcx, rsi
0x180001839  call    cs:__guard_dispatch_icall_fptr
0x18000183f  mov     ebx, eax
0x180001841  mov     [rsp+108h+var_E8], eax
0x180001845  jmp     short loc_180001854
0x180001847  xor     ebx, ebx
0x180001849  mov     [rsp+108h+var_E8], ebx
0x18000184d  mov     edi, [rsp+108h+arg_8]
0x180001854  cmp     edi, 1
0x180001857  ja      short loc_180001863
0x180001859  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x180001863  mov     eax, ebx
0x180001865  add     rsp, 0F0h
0x18000186c  pop     rdi
0x18000186d  pop     rsi
0x18000186e  pop     rbx
0x18000186f  retn
0x1800068c0  push    rbp
0x1800068c2  sub     rsp, 20h
0x1800068c6  mov     rbp, rdx
0x1800068c9  mov     rax, [rcx]
0x1800068cc  mov     edx, [rax]
0x1800068ce  mov     [rbp+0A8h], rcx
0x1800068d5  mov     [rbp+28h], edx
0x1800068d8  mov     eax, [rbp+28h]
0x1800068db  cmp     eax, 0E06D7363h
0x1800068e0  jnz     short loc_1800068F6
0x1800068e2  mov     rdx, [rbp+0A8h]
0x1800068e9  mov     ecx, [rbp+28h]
0x1800068ec  call    _XcptFilter_0
0x1800068f1  mov     [rbp+30h], eax
0x1800068f4  jmp     short loc_1800068FD
0x1800068f6  mov     dword ptr [rbp+30h], 0
0x1800068fd  mov     eax, [rbp+30h]
0x180006900  add     rsp, 20h
0x180006904  pop     rbp
0x180006905  retn
0x180006907  push    rbp
0x180006909  sub     rsp, 20h
0x18000690d  mov     rbp, rdx
0x180006910  mov     rax, [rcx]
0x180006913  mov     edx, [rax]
0x180006915  mov     [rbp+0B0h], rcx
0x18000691c  mov     [rbp+38h], edx
0x18000691f  mov     eax, [rbp+38h]
0x180006922  cmp     eax, 0E06D7363h
0x180006927  jnz     short loc_18000693D
0x180006929  mov     rdx, [rbp+0B0h]
0x180006930  mov     ecx, [rbp+38h]
0x180006933  call    _XcptFilter_0
0x180006938  mov     [rbp+40h], eax
0x18000693b  jmp     short loc_180006944
0x18000693d  mov     dword ptr [rbp+40h], 0
0x180006944  mov     eax, [rbp+40h]
0x180006947  add     rsp, 20h
0x18000694b  pop     rbp
0x18000694c  retn
0x18000694e  push    rbp
0x180006950  sub     rsp, 20h
0x180006954  mov     rbp, rdx
0x180006957  mov     rax, [rcx]
0x18000695a  mov     edx, [rax]
0x18000695c  mov     [rbp+0B8h], rcx
0x180006963  mov     [rbp+48h], edx
0x180006966  mov     eax, [rbp+48h]
0x180006969  cmp     eax, 0E06D7363h
0x18000696e  jnz     short loc_180006984
0x180006970  mov     rdx, [rbp+0B8h]
0x180006977  mov     ecx, [rbp+48h]
0x18000697a  call    _XcptFilter_0
0x18000697f  mov     [rbp+50h], eax
0x180006982  jmp     short loc_18000698B
0x180006984  mov     dword ptr [rbp+50h], 0
0x18000698b  mov     eax, [rbp+50h]
0x18000698e  add     rsp, 20h
0x180006992  pop     rbp
0x180006993  retn
0x180006995  push    rbp
0x180006997  sub     rsp, 20h
0x18000699b  mov     rbp, rdx
0x18000699e  mov     rax, [rcx]
0x1800069a1  mov     edx, [rax]
0x1800069a3  mov     [rbp+0C0h], rcx
0x1800069aa  mov     [rbp+58h], edx
0x1800069ad  mov     eax, [rbp+58h]
0x1800069b0  cmp     eax, 0E06D7363h
0x1800069b5  jnz     short loc_1800069CB
0x1800069b7  mov     rdx, [rbp+0C0h]
0x1800069be  mov     ecx, [rbp+58h]
0x1800069c1  call    _XcptFilter_0
0x1800069c6  mov     [rbp+60h], eax
0x1800069c9  jmp     short loc_1800069D2
0x1800069cb  mov     dword ptr [rbp+60h], 0
0x1800069d2  mov     eax, [rbp+60h]
0x1800069d5  add     rsp, 20h
0x1800069d9  pop     rbp
0x1800069da  retn
0x1800069dc  push    rbp
0x1800069de  sub     rsp, 20h
0x1800069e2  mov     rbp, rdx
0x1800069e5  mov     rax, [rcx]
0x1800069e8  mov     edx, [rax]
0x1800069ea  mov     [rbp+0C8h], rcx
0x1800069f1  mov     [rbp+68h], edx
0x1800069f4  mov     eax, [rbp+68h]
0x1800069f7  cmp     eax, 0E06D7363h
0x1800069fc  jnz     short loc_180006A12
0x1800069fe  mov     rdx, [rbp+0C8h]
0x180006a05  mov     ecx, [rbp+68h]
0x180006a08  call    _XcptFilter_0
0x180006a0d  mov     [rbp+70h], eax
0x180006a10  jmp     short loc_180006A19
0x180006a12  mov     dword ptr [rbp+70h], 0
0x180006a19  mov     eax, [rbp+70h]
0x180006a1c  add     rsp, 20h
0x180006a20  pop     rbp
0x180006a21  retn
0x180006a23  push    rbp
0x180006a25  sub     rsp, 20h
0x180006a29  mov     rbp, rdx
0x180006a2c  mov     rax, [rcx]
0x180006a2f  mov     edx, [rax]
0x180006a31  mov     [rbp+0D0h], rcx
0x180006a38  mov     [rbp+78h], edx
0x180006a3b  mov     eax, [rbp+78h]
0x180006a3e  cmp     eax, 0E06D7363h
0x180006a43  jnz     short loc_180006A5C
0x180006a45  mov     rdx, [rbp+0D0h]
0x180006a4c  mov     ecx, [rbp+78h]
0x180006a4f  call    _XcptFilter_0
0x180006a54  mov     [rbp+80h], eax
0x180006a5a  jmp     short loc_180006A66
0x180006a5c  mov     dword ptr [rbp+80h], 0
0x180006a66  mov     eax, [rbp+80h]
0x180006a6c  add     rsp, 20h
0x180006a70  pop     rbp
0x180006a71  retn
0x180006a73  push    rbp
0x180006a75  sub     rsp, 20h
0x180006a79  mov     rbp, rdx
0x180006a7c  mov     rax, [rcx]
0x180006a7f  mov     edx, [rax]
0x180006a81  mov     [rbp+0D8h], rcx
0x180006a88  mov     [rbp+88h], edx
0x180006a8e  mov     eax, [rbp+88h]
0x180006a94  cmp     eax, 0E06D7363h
0x180006a99  jnz     short loc_180006AB5
0x180006a9b  mov     rdx, [rbp+0D8h]
0x180006aa2  mov     ecx, [rbp+88h]
0x180006aa8  call    _XcptFilter_0
0x180006aad  mov     [rbp+90h], eax
0x180006ab3  jmp     short loc_180006ABF
0x180006ab5  mov     dword ptr [rbp+90h], 0
0x180006abf  mov     eax, [rbp+90h]
0x180006ac5  add     rsp, 20h
0x180006ac9  pop     rbp
0x180006aca  retn
0x180006acc  push    rbp
0x180006ace  sub     rsp, 20h
0x180006ad2  mov     rbp, rdx
0x180006ad5  mov     rax, [rcx]
0x180006ad8  mov     edx, [rax]
0x180006ada  mov     [rbp+0E0h], rcx
0x180006ae1  mov     [rbp+98h], edx
0x180006ae7  mov     eax, [rbp+98h]
0x180006aed  cmp     eax, 0E06D7363h
0x180006af2  jnz     short loc_180006B0E
0x180006af4  mov     rdx, [rbp+0E0h]
0x180006afb  mov     ecx, [rbp+98h]
0x180006b01  call    _XcptFilter_0
0x180006b06  mov     [rbp+0A0h], eax
0x180006b0c  jmp     short loc_180006B18
0x180006b0e  mov     dword ptr [rbp+0A0h], 0
0x180006b18  mov     eax, [rbp+0A0h]
0x180006b1e  add     rsp, 20h
0x180006b22  pop     rbp
0x180006b23  retn
0x180006b25  push    rbp
0x180006b27  sub     rsp, 20h
0x180006b2b  mov     rbp, rdx
0x180006b2e  cmp     dword ptr [rbp+118h], 1
0x180006b35  ja      short loc_180006B41
0x180006b37  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
