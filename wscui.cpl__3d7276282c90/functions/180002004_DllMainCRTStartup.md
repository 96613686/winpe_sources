# __DllMainCRTStartup

- ea: `0x180002004`
- end: `0x180002210`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180001fc0`

## callees

- `0x1800012e0`
- `0x180001d90`
- `0x180002004`
- `0x180002854`
- `0x18000a6b0`

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
  if ( (_DWORD)fdwReason || dword_180014320 )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_180014324 = 1;
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
            if ( dword_180014324 )
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
0x180002004  mov     [rsp+lpvReserved], r8
0x180002009  mov     [rsp+arg_8], edx
0x18000200d  mov     [rsp+arg_0], rcx
0x180002012  push    rbx
0x180002013  push    rsi
0x180002014  push    rdi
0x180002015  sub     rsp, 0F0h
0x18000201c  mov     edi, edx
0x18000201e  mov     rsi, rcx
0x180002021  mov     ebx, 1
0x180002026  cmp     edx, ebx
0x180002028  ja      short loc_180002030
0x18000202a  mov     cs:__native_dllmain_reason, edx
0x180002030  test    edx, edx
0x180002032  jnz     short loc_180002047
0x180002034  cmp     cs:dword_180014320, edx
0x18000203a  jnz     short loc_180002047
0x18000203c  xor     ebx, ebx
0x18000203e  mov     [rsp+108h+var_E8], ebx
0x180002042  jmp     loc_1800021F4
0x180002047  lea     eax, [rdx-1]
0x18000204a  cmp     eax, 1
0x18000204d  ja      loc_1800020D4
0x180002053  mov     rax, cs:_pRawDllMain
0x18000205a  test    rax, rax
0x18000205d  jz      short loc_180002095
0x18000205f  cmp     edx, 1
0x180002062  jnz     short loc_18000206A
0x180002064  mov     cs:dword_180014324, edx
0x18000206a  mov     r8, [rsp+108h+lpvReserved]
0x180002072  call    cs:__guard_dispatch_icall_fptr
0x180002078  mov     ebx, eax
0x18000207a  mov     [rsp+108h+var_E8], eax
0x18000207e  jmp     short loc_180002095
0x180002080  xor     ebx, ebx
0x180002082  mov     [rsp+108h+var_E8], ebx
0x180002086  mov     edi, [rsp+108h+arg_8]
0x18000208d  mov     rsi, [rsp+108h+arg_0]
0x180002095  test    ebx, ebx
0x180002097  jz      loc_1800021F4
0x18000209d  mov     r8, [rsp+108h+lpvReserved]
0x1800020a5  mov     edx, edi
0x1800020a7  mov     rcx, rsi
0x1800020aa  call    _CRT_INIT
0x1800020af  mov     ebx, eax
0x1800020b1  mov     [rsp+108h+var_E8], eax
0x1800020b5  jmp     short loc_1800020CC
0x1800020b7  xor     ebx, ebx
0x1800020b9  mov     [rsp+108h+var_E8], ebx
0x1800020bd  mov     edi, [rsp+108h+arg_8]
0x1800020c4  mov     rsi, [rsp+108h+arg_0]
0x1800020cc  test    ebx, ebx
0x1800020ce  jz      loc_1800021F4
0x1800020d4  mov     r8, [rsp+108h+lpvReserved]; lpvReserved
0x1800020dc  mov     edx, edi; fdwReason
0x1800020de  mov     rcx, rsi; hinstDLL
0x1800020e1  call    DllMain
0x1800020e6  mov     ebx, eax
0x1800020e8  mov     [rsp+108h+var_E8], eax
0x1800020ec  jmp     short loc_180002103
0x1800020ee  xor     ebx, ebx
0x1800020f0  mov     [rsp+108h+var_E8], ebx
0x1800020f4  mov     edi, [rsp+108h+arg_8]
0x1800020fb  mov     rsi, [rsp+108h+arg_0]
0x180002103  cmp     edi, 1
0x180002106  jnz     short loc_18000217F
0x180002108  test    ebx, ebx
0x18000210a  jnz     short loc_18000217F
0x18000210c  xor     r8d, r8d; lpvReserved
0x18000210f  xor     edx, edx; fdwReason
0x180002111  mov     rcx, rsi; hinstDLL
0x180002114  call    DllMain
0x180002119  jmp     short loc_18000212E
0x18000211b  mov     edi, [rsp+108h+arg_8]
0x180002122  mov     rsi, [rsp+108h+arg_0]
0x18000212a  mov     ebx, [rsp+108h+var_E8]
0x18000212e  xor     r8d, r8d
0x180002131  xor     edx, edx
0x180002133  mov     rcx, rsi
0x180002136  call    _CRT_INIT
0x18000213b  jmp     short loc_180002150
0x18000213d  mov     edi, [rsp+108h+arg_8]
0x180002144  mov     rsi, [rsp+108h+arg_0]
0x18000214c  mov     ebx, [rsp+108h+var_E8]
0x180002150  mov     rax, cs:_pRawDllMain
0x180002157  test    rax, rax
0x18000215a  jz      short loc_18000217F
0x18000215c  xor     r8d, r8d
0x18000215f  xor     edx, edx
0x180002161  mov     rcx, rsi
0x180002164  call    cs:__guard_dispatch_icall_fptr
0x18000216a  jmp     short loc_18000217F
0x18000216c  mov     edi, [rsp+108h+arg_8]
0x180002173  mov     rsi, [rsp+108h+arg_0]
0x18000217b  mov     ebx, [rsp+108h+var_E8]
0x18000217f  test    edi, edi
0x180002181  jz      short loc_180002188
0x180002183  cmp     edi, 3
0x180002186  jnz     short loc_1800021F4
0x180002188  mov     r8, [rsp+108h+lpvReserved]
0x180002190  mov     edx, edi
0x180002192  mov     rcx, rsi
0x180002195  call    _CRT_INIT
0x18000219a  mov     ebx, eax
0x18000219c  mov     [rsp+108h+var_E8], eax
0x1800021a0  jmp     short loc_1800021B7
0x1800021a2  xor     ebx, ebx
0x1800021a4  mov     [rsp+108h+var_E8], ebx
0x1800021a8  mov     edi, [rsp+108h+arg_8]
0x1800021af  mov     rsi, [rsp+108h+arg_0]
0x1800021b7  mov     rax, cs:_pRawDllMain
0x1800021be  test    rax, rax
0x1800021c1  jz      short loc_1800021F4
0x1800021c3  cmp     cs:dword_180014324, 0
0x1800021ca  jz      short loc_1800021F4
0x1800021cc  mov     r8, [rsp+108h+lpvReserved]
0x1800021d4  mov     edx, edi
0x1800021d6  mov     rcx, rsi
0x1800021d9  call    cs:__guard_dispatch_icall_fptr
0x1800021df  mov     ebx, eax
0x1800021e1  mov     [rsp+108h+var_E8], eax
0x1800021e5  jmp     short loc_1800021F4
0x1800021e7  xor     ebx, ebx
0x1800021e9  mov     [rsp+108h+var_E8], ebx
0x1800021ed  mov     edi, [rsp+108h+arg_8]
0x1800021f4  cmp     edi, 1
0x1800021f7  ja      short loc_180002203
0x1800021f9  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x180002203  mov     eax, ebx
0x180002205  add     rsp, 0F0h
0x18000220c  pop     rdi
0x18000220d  pop     rsi
0x18000220e  pop     rbx
0x18000220f  retn
0x18000a786  push    rbp
0x18000a788  sub     rsp, 20h
0x18000a78c  mov     rbp, rdx
0x18000a78f  mov     rax, [rcx]
0x18000a792  mov     edx, [rax]
0x18000a794  mov     [rbp+0A8h], rcx
0x18000a79b  mov     [rbp+28h], edx
0x18000a79e  mov     eax, [rbp+28h]
0x18000a7a1  cmp     eax, 0E06D7363h
0x18000a7a6  jnz     short loc_18000A7BC
0x18000a7a8  mov     rdx, [rbp+0A8h]
0x18000a7af  mov     ecx, [rbp+28h]
0x18000a7b2  call    _XcptFilter_0
0x18000a7b7  mov     [rbp+30h], eax
0x18000a7ba  jmp     short loc_18000A7C3
0x18000a7bc  mov     dword ptr [rbp+30h], 0
0x18000a7c3  mov     eax, [rbp+30h]
0x18000a7c6  add     rsp, 20h
0x18000a7ca  pop     rbp
0x18000a7cb  retn
0x18000a7cd  push    rbp
0x18000a7cf  sub     rsp, 20h
0x18000a7d3  mov     rbp, rdx
0x18000a7d6  mov     rax, [rcx]
0x18000a7d9  mov     edx, [rax]
0x18000a7db  mov     [rbp+0B0h], rcx
0x18000a7e2  mov     [rbp+38h], edx
0x18000a7e5  mov     eax, [rbp+38h]
0x18000a7e8  cmp     eax, 0E06D7363h
0x18000a7ed  jnz     short loc_18000A803
0x18000a7ef  mov     rdx, [rbp+0B0h]
0x18000a7f6  mov     ecx, [rbp+38h]
0x18000a7f9  call    _XcptFilter_0
0x18000a7fe  mov     [rbp+40h], eax
0x18000a801  jmp     short loc_18000A80A
0x18000a803  mov     dword ptr [rbp+40h], 0
0x18000a80a  mov     eax, [rbp+40h]
0x18000a80d  add     rsp, 20h
0x18000a811  pop     rbp
0x18000a812  retn
0x18000a814  push    rbp
0x18000a816  sub     rsp, 20h
0x18000a81a  mov     rbp, rdx
0x18000a81d  mov     rax, [rcx]
0x18000a820  mov     edx, [rax]
0x18000a822  mov     [rbp+0B8h], rcx
0x18000a829  mov     [rbp+48h], edx
0x18000a82c  mov     eax, [rbp+48h]
0x18000a82f  cmp     eax, 0E06D7363h
0x18000a834  jnz     short loc_18000A84A
0x18000a836  mov     rdx, [rbp+0B8h]
0x18000a83d  mov     ecx, [rbp+48h]
0x18000a840  call    _XcptFilter_0
0x18000a845  mov     [rbp+50h], eax
0x18000a848  jmp     short loc_18000A851
0x18000a84a  mov     dword ptr [rbp+50h], 0
0x18000a851  mov     eax, [rbp+50h]
0x18000a854  add     rsp, 20h
0x18000a858  pop     rbp
0x18000a859  retn
0x18000a85b  push    rbp
0x18000a85d  sub     rsp, 20h
0x18000a861  mov     rbp, rdx
0x18000a864  mov     rax, [rcx]
0x18000a867  mov     edx, [rax]
0x18000a869  mov     [rbp+0C0h], rcx
0x18000a870  mov     [rbp+58h], edx
0x18000a873  mov     eax, [rbp+58h]
0x18000a876  cmp     eax, 0E06D7363h
0x18000a87b  jnz     short loc_18000A891
0x18000a87d  mov     rdx, [rbp+0C0h]
0x18000a884  mov     ecx, [rbp+58h]
0x18000a887  call    _XcptFilter_0
0x18000a88c  mov     [rbp+60h], eax
0x18000a88f  jmp     short loc_18000A898
0x18000a891  mov     dword ptr [rbp+60h], 0
0x18000a898  mov     eax, [rbp+60h]
0x18000a89b  add     rsp, 20h
0x18000a89f  pop     rbp
0x18000a8a0  retn
0x18000a8a2  push    rbp
0x18000a8a4  sub     rsp, 20h
0x18000a8a8  mov     rbp, rdx
0x18000a8ab  mov     rax, [rcx]
0x18000a8ae  mov     edx, [rax]
0x18000a8b0  mov     [rbp+0C8h], rcx
0x18000a8b7  mov     [rbp+68h], edx
0x18000a8ba  mov     eax, [rbp+68h]
0x18000a8bd  cmp     eax, 0E06D7363h
0x18000a8c2  jnz     short loc_18000A8D8
0x18000a8c4  mov     rdx, [rbp+0C8h]
0x18000a8cb  mov     ecx, [rbp+68h]
0x18000a8ce  call    _XcptFilter_0
0x18000a8d3  mov     [rbp+70h], eax
0x18000a8d6  jmp     short loc_18000A8DF
0x18000a8d8  mov     dword ptr [rbp+70h], 0
0x18000a8df  mov     eax, [rbp+70h]
0x18000a8e2  add     rsp, 20h
0x18000a8e6  pop     rbp
0x18000a8e7  retn
0x18000a8e9  push    rbp
0x18000a8eb  sub     rsp, 20h
0x18000a8ef  mov     rbp, rdx
0x18000a8f2  mov     rax, [rcx]
0x18000a8f5  mov     edx, [rax]
0x18000a8f7  mov     [rbp+0D0h], rcx
0x18000a8fe  mov     [rbp+78h], edx
0x18000a901  mov     eax, [rbp+78h]
0x18000a904  cmp     eax, 0E06D7363h
0x18000a909  jnz     short loc_18000A922
0x18000a90b  mov     rdx, [rbp+0D0h]
0x18000a912  mov     ecx, [rbp+78h]
0x18000a915  call    _XcptFilter_0
0x18000a91a  mov     [rbp+80h], eax
0x18000a920  jmp     short loc_18000A92C
0x18000a922  mov     dword ptr [rbp+80h], 0
0x18000a92c  mov     eax, [rbp+80h]
0x18000a932  add     rsp, 20h
0x18000a936  pop     rbp
0x18000a937  retn
0x18000a939  push    rbp
0x18000a93b  sub     rsp, 20h
0x18000a93f  mov     rbp, rdx
0x18000a942  mov     rax, [rcx]
0x18000a945  mov     edx, [rax]
0x18000a947  mov     [rbp+0D8h], rcx
0x18000a94e  mov     [rbp+88h], edx
0x18000a954  mov     eax, [rbp+88h]
0x18000a95a  cmp     eax, 0E06D7363h
0x18000a95f  jnz     short loc_18000A97B
0x18000a961  mov     rdx, [rbp+0D8h]
0x18000a968  mov     ecx, [rbp+88h]
0x18000a96e  call    _XcptFilter_0
0x18000a973  mov     [rbp+90h], eax
0x18000a979  jmp     short loc_18000A985
0x18000a97b  mov     dword ptr [rbp+90h], 0
0x18000a985  mov     eax, [rbp+90h]
0x18000a98b  add     rsp, 20h
0x18000a98f  pop     rbp
0x18000a990  retn
0x18000a992  push    rbp
0x18000a994  sub     rsp, 20h
0x18000a998  mov     rbp, rdx
0x18000a99b  mov     rax, [rcx]
0x18000a99e  mov     edx, [rax]
0x18000a9a0  mov     [rbp+0E0h], rcx
0x18000a9a7  mov     [rbp+98h], edx
0x18000a9ad  mov     eax, [rbp+98h]
0x18000a9b3  cmp     eax, 0E06D7363h
0x18000a9b8  jnz     short loc_18000A9D4
0x18000a9ba  mov     rdx, [rbp+0E0h]
0x18000a9c1  mov     ecx, [rbp+98h]
0x18000a9c7  call    _XcptFilter_0
0x18000a9cc  mov     [rbp+0A0h], eax
0x18000a9d2  jmp     short loc_18000A9DE
0x18000a9d4  mov     dword ptr [rbp+0A0h], 0
0x18000a9de  mov     eax, [rbp+0A0h]
0x18000a9e4  add     rsp, 20h
0x18000a9e8  pop     rbp
0x18000a9e9  retn
0x18000a9eb  push    rbp
0x18000a9ed  sub     rsp, 20h
0x18000a9f1  mov     rbp, rdx
0x18000a9f4  cmp     dword ptr [rbp+118h], 1
0x18000a9fb  ja      short loc_18000AA07
0x18000a9fd  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
