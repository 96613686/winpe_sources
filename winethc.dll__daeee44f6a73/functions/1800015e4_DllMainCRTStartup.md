# __DllMainCRTStartup

- ea: `0x1800015e4`
- end: `0x1800017f0`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1800015a0`

## callees

- `0x180001370`
- `0x1800015e4`
- `0x180001c68`
- `0x18001174c`
- `0x180012df0`

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
  if ( (_DWORD)fdwReason || dword_18001B6E0 )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_18001B6E4 = 1;
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
            if ( dword_18001B6E4 )
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
0x1800015e4  mov     [rsp+lpvReserved], r8
0x1800015e9  mov     [rsp+arg_8], edx
0x1800015ed  mov     [rsp+arg_0], rcx
0x1800015f2  push    rbx
0x1800015f3  push    rsi
0x1800015f4  push    rdi
0x1800015f5  sub     rsp, 0F0h
0x1800015fc  mov     edi, edx
0x1800015fe  mov     rsi, rcx
0x180001601  mov     ebx, 1
0x180001606  cmp     edx, ebx
0x180001608  ja      short loc_180001610
0x18000160a  mov     cs:__native_dllmain_reason, edx
0x180001610  test    edx, edx
0x180001612  jnz     short loc_180001627
0x180001614  cmp     cs:dword_18001B6E0, edx
0x18000161a  jnz     short loc_180001627
0x18000161c  xor     ebx, ebx
0x18000161e  mov     [rsp+108h+var_E8], ebx
0x180001622  jmp     loc_1800017D4
0x180001627  lea     eax, [rdx-1]
0x18000162a  cmp     eax, 1
0x18000162d  ja      loc_1800016B4
0x180001633  mov     rax, cs:_pRawDllMain
0x18000163a  test    rax, rax
0x18000163d  jz      short loc_180001675
0x18000163f  cmp     edx, 1
0x180001642  jnz     short loc_18000164A
0x180001644  mov     cs:dword_18001B6E4, edx
0x18000164a  mov     r8, [rsp+108h+lpvReserved]
0x180001652  call    cs:__guard_dispatch_icall_fptr
0x180001658  mov     ebx, eax
0x18000165a  mov     [rsp+108h+var_E8], eax
0x18000165e  jmp     short loc_180001675
0x180001660  xor     ebx, ebx
0x180001662  mov     [rsp+108h+var_E8], ebx
0x180001666  mov     edi, [rsp+108h+arg_8]
0x18000166d  mov     rsi, [rsp+108h+arg_0]
0x180001675  test    ebx, ebx
0x180001677  jz      loc_1800017D4
0x18000167d  mov     r8, [rsp+108h+lpvReserved]
0x180001685  mov     edx, edi
0x180001687  mov     rcx, rsi
0x18000168a  call    _CRT_INIT
0x18000168f  mov     ebx, eax
0x180001691  mov     [rsp+108h+var_E8], eax
0x180001695  jmp     short loc_1800016AC
0x180001697  xor     ebx, ebx
0x180001699  mov     [rsp+108h+var_E8], ebx
0x18000169d  mov     edi, [rsp+108h+arg_8]
0x1800016a4  mov     rsi, [rsp+108h+arg_0]
0x1800016ac  test    ebx, ebx
0x1800016ae  jz      loc_1800017D4
0x1800016b4  mov     r8, [rsp+108h+lpvReserved]; lpvReserved
0x1800016bc  mov     edx, edi; fdwReason
0x1800016be  mov     rcx, rsi; hinstDLL
0x1800016c1  call    DllMain
0x1800016c6  mov     ebx, eax
0x1800016c8  mov     [rsp+108h+var_E8], eax
0x1800016cc  jmp     short loc_1800016E3
0x1800016ce  xor     ebx, ebx
0x1800016d0  mov     [rsp+108h+var_E8], ebx
0x1800016d4  mov     edi, [rsp+108h+arg_8]
0x1800016db  mov     rsi, [rsp+108h+arg_0]
0x1800016e3  cmp     edi, 1
0x1800016e6  jnz     short loc_18000175F
0x1800016e8  test    ebx, ebx
0x1800016ea  jnz     short loc_18000175F
0x1800016ec  xor     r8d, r8d; lpvReserved
0x1800016ef  xor     edx, edx; fdwReason
0x1800016f1  mov     rcx, rsi; hinstDLL
0x1800016f4  call    DllMain
0x1800016f9  jmp     short loc_18000170E
0x1800016fb  mov     edi, [rsp+108h+arg_8]
0x180001702  mov     rsi, [rsp+108h+arg_0]
0x18000170a  mov     ebx, [rsp+108h+var_E8]
0x18000170e  xor     r8d, r8d
0x180001711  xor     edx, edx
0x180001713  mov     rcx, rsi
0x180001716  call    _CRT_INIT
0x18000171b  jmp     short loc_180001730
0x18000171d  mov     edi, [rsp+108h+arg_8]
0x180001724  mov     rsi, [rsp+108h+arg_0]
0x18000172c  mov     ebx, [rsp+108h+var_E8]
0x180001730  mov     rax, cs:_pRawDllMain
0x180001737  test    rax, rax
0x18000173a  jz      short loc_18000175F
0x18000173c  xor     r8d, r8d
0x18000173f  xor     edx, edx
0x180001741  mov     rcx, rsi
0x180001744  call    cs:__guard_dispatch_icall_fptr
0x18000174a  jmp     short loc_18000175F
0x18000174c  mov     edi, [rsp+108h+arg_8]
0x180001753  mov     rsi, [rsp+108h+arg_0]
0x18000175b  mov     ebx, [rsp+108h+var_E8]
0x18000175f  test    edi, edi
0x180001761  jz      short loc_180001768
0x180001763  cmp     edi, 3
0x180001766  jnz     short loc_1800017D4
0x180001768  mov     r8, [rsp+108h+lpvReserved]
0x180001770  mov     edx, edi
0x180001772  mov     rcx, rsi
0x180001775  call    _CRT_INIT
0x18000177a  mov     ebx, eax
0x18000177c  mov     [rsp+108h+var_E8], eax
0x180001780  jmp     short loc_180001797
0x180001782  xor     ebx, ebx
0x180001784  mov     [rsp+108h+var_E8], ebx
0x180001788  mov     edi, [rsp+108h+arg_8]
0x18000178f  mov     rsi, [rsp+108h+arg_0]
0x180001797  mov     rax, cs:_pRawDllMain
0x18000179e  test    rax, rax
0x1800017a1  jz      short loc_1800017D4
0x1800017a3  cmp     cs:dword_18001B6E4, 0
0x1800017aa  jz      short loc_1800017D4
0x1800017ac  mov     r8, [rsp+108h+lpvReserved]
0x1800017b4  mov     edx, edi
0x1800017b6  mov     rcx, rsi
0x1800017b9  call    cs:__guard_dispatch_icall_fptr
0x1800017bf  mov     ebx, eax
0x1800017c1  mov     [rsp+108h+var_E8], eax
0x1800017c5  jmp     short loc_1800017D4
0x1800017c7  xor     ebx, ebx
0x1800017c9  mov     [rsp+108h+var_E8], ebx
0x1800017cd  mov     edi, [rsp+108h+arg_8]
0x1800017d4  cmp     edi, 1
0x1800017d7  ja      short loc_1800017E3
0x1800017d9  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x1800017e3  mov     eax, ebx
0x1800017e5  add     rsp, 0F0h
0x1800017ec  pop     rdi
0x1800017ed  pop     rsi
0x1800017ee  pop     rbx
0x1800017ef  retn
0x180012ec0  push    rbp
0x180012ec2  sub     rsp, 20h
0x180012ec6  mov     rbp, rdx
0x180012ec9  mov     rax, [rcx]
0x180012ecc  mov     edx, [rax]
0x180012ece  mov     [rbp+0A8h], rcx
0x180012ed5  mov     [rbp+28h], edx
0x180012ed8  mov     eax, [rbp+28h]
0x180012edb  cmp     eax, 0E06D7363h
0x180012ee0  jnz     short loc_180012EF6
0x180012ee2  mov     rdx, [rbp+0A8h]
0x180012ee9  mov     ecx, [rbp+28h]
0x180012eec  call    _XcptFilter_0
0x180012ef1  mov     [rbp+30h], eax
0x180012ef4  jmp     short loc_180012EFD
0x180012ef6  mov     dword ptr [rbp+30h], 0
0x180012efd  mov     eax, [rbp+30h]
0x180012f00  add     rsp, 20h
0x180012f04  pop     rbp
0x180012f05  retn
0x180012f07  push    rbp
0x180012f09  sub     rsp, 20h
0x180012f0d  mov     rbp, rdx
0x180012f10  mov     rax, [rcx]
0x180012f13  mov     edx, [rax]
0x180012f15  mov     [rbp+0B0h], rcx
0x180012f1c  mov     [rbp+38h], edx
0x180012f1f  mov     eax, [rbp+38h]
0x180012f22  cmp     eax, 0E06D7363h
0x180012f27  jnz     short loc_180012F3D
0x180012f29  mov     rdx, [rbp+0B0h]
0x180012f30  mov     ecx, [rbp+38h]
0x180012f33  call    _XcptFilter_0
0x180012f38  mov     [rbp+40h], eax
0x180012f3b  jmp     short loc_180012F44
0x180012f3d  mov     dword ptr [rbp+40h], 0
0x180012f44  mov     eax, [rbp+40h]
0x180012f47  add     rsp, 20h
0x180012f4b  pop     rbp
0x180012f4c  retn
0x180012f4e  push    rbp
0x180012f50  sub     rsp, 20h
0x180012f54  mov     rbp, rdx
0x180012f57  mov     rax, [rcx]
0x180012f5a  mov     edx, [rax]
0x180012f5c  mov     [rbp+0B8h], rcx
0x180012f63  mov     [rbp+48h], edx
0x180012f66  mov     eax, [rbp+48h]
0x180012f69  cmp     eax, 0E06D7363h
0x180012f6e  jnz     short loc_180012F84
0x180012f70  mov     rdx, [rbp+0B8h]
0x180012f77  mov     ecx, [rbp+48h]
0x180012f7a  call    _XcptFilter_0
0x180012f7f  mov     [rbp+50h], eax
0x180012f82  jmp     short loc_180012F8B
0x180012f84  mov     dword ptr [rbp+50h], 0
0x180012f8b  mov     eax, [rbp+50h]
0x180012f8e  add     rsp, 20h
0x180012f92  pop     rbp
0x180012f93  retn
0x180012f95  push    rbp
0x180012f97  sub     rsp, 20h
0x180012f9b  mov     rbp, rdx
0x180012f9e  mov     rax, [rcx]
0x180012fa1  mov     edx, [rax]
0x180012fa3  mov     [rbp+0C0h], rcx
0x180012faa  mov     [rbp+58h], edx
0x180012fad  mov     eax, [rbp+58h]
0x180012fb0  cmp     eax, 0E06D7363h
0x180012fb5  jnz     short loc_180012FCB
0x180012fb7  mov     rdx, [rbp+0C0h]
0x180012fbe  mov     ecx, [rbp+58h]
0x180012fc1  call    _XcptFilter_0
0x180012fc6  mov     [rbp+60h], eax
0x180012fc9  jmp     short loc_180012FD2
0x180012fcb  mov     dword ptr [rbp+60h], 0
0x180012fd2  mov     eax, [rbp+60h]
0x180012fd5  add     rsp, 20h
0x180012fd9  pop     rbp
0x180012fda  retn
0x180012fdc  push    rbp
0x180012fde  sub     rsp, 20h
0x180012fe2  mov     rbp, rdx
0x180012fe5  mov     rax, [rcx]
0x180012fe8  mov     edx, [rax]
0x180012fea  mov     [rbp+0C8h], rcx
0x180012ff1  mov     [rbp+68h], edx
0x180012ff4  mov     eax, [rbp+68h]
0x180012ff7  cmp     eax, 0E06D7363h
0x180012ffc  jnz     short loc_180013012
0x180012ffe  mov     rdx, [rbp+0C8h]
0x180013005  mov     ecx, [rbp+68h]
0x180013008  call    _XcptFilter_0
0x18001300d  mov     [rbp+70h], eax
0x180013010  jmp     short loc_180013019
0x180013012  mov     dword ptr [rbp+70h], 0
0x180013019  mov     eax, [rbp+70h]
0x18001301c  add     rsp, 20h
0x180013020  pop     rbp
0x180013021  retn
0x180013023  push    rbp
0x180013025  sub     rsp, 20h
0x180013029  mov     rbp, rdx
0x18001302c  mov     rax, [rcx]
0x18001302f  mov     edx, [rax]
0x180013031  mov     [rbp+0D0h], rcx
0x180013038  mov     [rbp+78h], edx
0x18001303b  mov     eax, [rbp+78h]
0x18001303e  cmp     eax, 0E06D7363h
0x180013043  jnz     short loc_18001305C
0x180013045  mov     rdx, [rbp+0D0h]
0x18001304c  mov     ecx, [rbp+78h]
0x18001304f  call    _XcptFilter_0
0x180013054  mov     [rbp+80h], eax
0x18001305a  jmp     short loc_180013066
0x18001305c  mov     dword ptr [rbp+80h], 0
0x180013066  mov     eax, [rbp+80h]
0x18001306c  add     rsp, 20h
0x180013070  pop     rbp
0x180013071  retn
0x180013073  push    rbp
0x180013075  sub     rsp, 20h
0x180013079  mov     rbp, rdx
0x18001307c  mov     rax, [rcx]
0x18001307f  mov     edx, [rax]
0x180013081  mov     [rbp+0D8h], rcx
0x180013088  mov     [rbp+88h], edx
0x18001308e  mov     eax, [rbp+88h]
0x180013094  cmp     eax, 0E06D7363h
0x180013099  jnz     short loc_1800130B5
0x18001309b  mov     rdx, [rbp+0D8h]
0x1800130a2  mov     ecx, [rbp+88h]
0x1800130a8  call    _XcptFilter_0
0x1800130ad  mov     [rbp+90h], eax
0x1800130b3  jmp     short loc_1800130BF
0x1800130b5  mov     dword ptr [rbp+90h], 0
0x1800130bf  mov     eax, [rbp+90h]
0x1800130c5  add     rsp, 20h
0x1800130c9  pop     rbp
0x1800130ca  retn
0x1800130cc  push    rbp
0x1800130ce  sub     rsp, 20h
0x1800130d2  mov     rbp, rdx
0x1800130d5  mov     rax, [rcx]
0x1800130d8  mov     edx, [rax]
0x1800130da  mov     [rbp+0E0h], rcx
0x1800130e1  mov     [rbp+98h], edx
0x1800130e7  mov     eax, [rbp+98h]
0x1800130ed  cmp     eax, 0E06D7363h
0x1800130f2  jnz     short loc_18001310E
0x1800130f4  mov     rdx, [rbp+0E0h]
0x1800130fb  mov     ecx, [rbp+98h]
0x180013101  call    _XcptFilter_0
0x180013106  mov     [rbp+0A0h], eax
0x18001310c  jmp     short loc_180013118
0x18001310e  mov     dword ptr [rbp+0A0h], 0
0x180013118  mov     eax, [rbp+0A0h]
0x18001311e  add     rsp, 20h
0x180013122  pop     rbp
0x180013123  retn
0x180013125  push    rbp
0x180013127  sub     rsp, 20h
0x18001312b  mov     rbp, rdx
0x18001312e  cmp     dword ptr [rbp+118h], 1
0x180013135  ja      short loc_180013141
0x180013137  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
