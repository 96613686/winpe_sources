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
- `0x1800029a8`
- `0x18000aec0`

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
  if ( (_DWORD)fdwReason || dword_1800140E0 )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_1800140E4 = 1;
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
            if ( dword_1800140E4 )
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
0x1800012f4  cmp     cs:dword_1800140E0, edx
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
0x180001324  mov     cs:dword_1800140E4, edx
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
0x180001483  cmp     cs:dword_1800140E4, 0
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
0x18000af90  push    rbp
0x18000af92  sub     rsp, 20h
0x18000af96  mov     rbp, rdx
0x18000af99  mov     rax, [rcx]
0x18000af9c  mov     edx, [rax]
0x18000af9e  mov     [rbp+0A8h], rcx
0x18000afa5  mov     [rbp+28h], edx
0x18000afa8  mov     eax, [rbp+28h]
0x18000afab  cmp     eax, 0E06D7363h
0x18000afb0  jnz     short loc_18000AFC6
0x18000afb2  mov     rdx, [rbp+0A8h]
0x18000afb9  mov     ecx, [rbp+28h]
0x18000afbc  call    _XcptFilter_0
0x18000afc1  mov     [rbp+30h], eax
0x18000afc4  jmp     short loc_18000AFCD
0x18000afc6  mov     dword ptr [rbp+30h], 0
0x18000afcd  mov     eax, [rbp+30h]
0x18000afd0  add     rsp, 20h
0x18000afd4  pop     rbp
0x18000afd5  retn
0x18000afd7  push    rbp
0x18000afd9  sub     rsp, 20h
0x18000afdd  mov     rbp, rdx
0x18000afe0  mov     rax, [rcx]
0x18000afe3  mov     edx, [rax]
0x18000afe5  mov     [rbp+0B0h], rcx
0x18000afec  mov     [rbp+38h], edx
0x18000afef  mov     eax, [rbp+38h]
0x18000aff2  cmp     eax, 0E06D7363h
0x18000aff7  jnz     short loc_18000B00D
0x18000aff9  mov     rdx, [rbp+0B0h]
0x18000b000  mov     ecx, [rbp+38h]
0x18000b003  call    _XcptFilter_0
0x18000b008  mov     [rbp+40h], eax
0x18000b00b  jmp     short loc_18000B014
0x18000b00d  mov     dword ptr [rbp+40h], 0
0x18000b014  mov     eax, [rbp+40h]
0x18000b017  add     rsp, 20h
0x18000b01b  pop     rbp
0x18000b01c  retn
0x18000b01e  push    rbp
0x18000b020  sub     rsp, 20h
0x18000b024  mov     rbp, rdx
0x18000b027  mov     rax, [rcx]
0x18000b02a  mov     edx, [rax]
0x18000b02c  mov     [rbp+0B8h], rcx
0x18000b033  mov     [rbp+48h], edx
0x18000b036  mov     eax, [rbp+48h]
0x18000b039  cmp     eax, 0E06D7363h
0x18000b03e  jnz     short loc_18000B054
0x18000b040  mov     rdx, [rbp+0B8h]
0x18000b047  mov     ecx, [rbp+48h]
0x18000b04a  call    _XcptFilter_0
0x18000b04f  mov     [rbp+50h], eax
0x18000b052  jmp     short loc_18000B05B
0x18000b054  mov     dword ptr [rbp+50h], 0
0x18000b05b  mov     eax, [rbp+50h]
0x18000b05e  add     rsp, 20h
0x18000b062  pop     rbp
0x18000b063  retn
0x18000b065  push    rbp
0x18000b067  sub     rsp, 20h
0x18000b06b  mov     rbp, rdx
0x18000b06e  mov     rax, [rcx]
0x18000b071  mov     edx, [rax]
0x18000b073  mov     [rbp+0C0h], rcx
0x18000b07a  mov     [rbp+58h], edx
0x18000b07d  mov     eax, [rbp+58h]
0x18000b080  cmp     eax, 0E06D7363h
0x18000b085  jnz     short loc_18000B09B
0x18000b087  mov     rdx, [rbp+0C0h]
0x18000b08e  mov     ecx, [rbp+58h]
0x18000b091  call    _XcptFilter_0
0x18000b096  mov     [rbp+60h], eax
0x18000b099  jmp     short loc_18000B0A2
0x18000b09b  mov     dword ptr [rbp+60h], 0
0x18000b0a2  mov     eax, [rbp+60h]
0x18000b0a5  add     rsp, 20h
0x18000b0a9  pop     rbp
0x18000b0aa  retn
0x18000b0ac  push    rbp
0x18000b0ae  sub     rsp, 20h
0x18000b0b2  mov     rbp, rdx
0x18000b0b5  mov     rax, [rcx]
0x18000b0b8  mov     edx, [rax]
0x18000b0ba  mov     [rbp+0C8h], rcx
0x18000b0c1  mov     [rbp+68h], edx
0x18000b0c4  mov     eax, [rbp+68h]
0x18000b0c7  cmp     eax, 0E06D7363h
0x18000b0cc  jnz     short loc_18000B0E2
0x18000b0ce  mov     rdx, [rbp+0C8h]
0x18000b0d5  mov     ecx, [rbp+68h]
0x18000b0d8  call    _XcptFilter_0
0x18000b0dd  mov     [rbp+70h], eax
0x18000b0e0  jmp     short loc_18000B0E9
0x18000b0e2  mov     dword ptr [rbp+70h], 0
0x18000b0e9  mov     eax, [rbp+70h]
0x18000b0ec  add     rsp, 20h
0x18000b0f0  pop     rbp
0x18000b0f1  retn
0x18000b0f3  push    rbp
0x18000b0f5  sub     rsp, 20h
0x18000b0f9  mov     rbp, rdx
0x18000b0fc  mov     rax, [rcx]
0x18000b0ff  mov     edx, [rax]
0x18000b101  mov     [rbp+0D0h], rcx
0x18000b108  mov     [rbp+78h], edx
0x18000b10b  mov     eax, [rbp+78h]
0x18000b10e  cmp     eax, 0E06D7363h
0x18000b113  jnz     short loc_18000B12C
0x18000b115  mov     rdx, [rbp+0D0h]
0x18000b11c  mov     ecx, [rbp+78h]
0x18000b11f  call    _XcptFilter_0
0x18000b124  mov     [rbp+80h], eax
0x18000b12a  jmp     short loc_18000B136
0x18000b12c  mov     dword ptr [rbp+80h], 0
0x18000b136  mov     eax, [rbp+80h]
0x18000b13c  add     rsp, 20h
0x18000b140  pop     rbp
0x18000b141  retn
0x18000b143  push    rbp
0x18000b145  sub     rsp, 20h
0x18000b149  mov     rbp, rdx
0x18000b14c  mov     rax, [rcx]
0x18000b14f  mov     edx, [rax]
0x18000b151  mov     [rbp+0D8h], rcx
0x18000b158  mov     [rbp+88h], edx
0x18000b15e  mov     eax, [rbp+88h]
0x18000b164  cmp     eax, 0E06D7363h
0x18000b169  jnz     short loc_18000B185
0x18000b16b  mov     rdx, [rbp+0D8h]
0x18000b172  mov     ecx, [rbp+88h]
0x18000b178  call    _XcptFilter_0
0x18000b17d  mov     [rbp+90h], eax
0x18000b183  jmp     short loc_18000B18F
0x18000b185  mov     dword ptr [rbp+90h], 0
0x18000b18f  mov     eax, [rbp+90h]
0x18000b195  add     rsp, 20h
0x18000b199  pop     rbp
0x18000b19a  retn
0x18000b19c  push    rbp
0x18000b19e  sub     rsp, 20h
0x18000b1a2  mov     rbp, rdx
0x18000b1a5  mov     rax, [rcx]
0x18000b1a8  mov     edx, [rax]
0x18000b1aa  mov     [rbp+0E0h], rcx
0x18000b1b1  mov     [rbp+98h], edx
0x18000b1b7  mov     eax, [rbp+98h]
0x18000b1bd  cmp     eax, 0E06D7363h
0x18000b1c2  jnz     short loc_18000B1DE
0x18000b1c4  mov     rdx, [rbp+0E0h]
0x18000b1cb  mov     ecx, [rbp+98h]
0x18000b1d1  call    _XcptFilter_0
0x18000b1d6  mov     [rbp+0A0h], eax
0x18000b1dc  jmp     short loc_18000B1E8
0x18000b1de  mov     dword ptr [rbp+0A0h], 0
0x18000b1e8  mov     eax, [rbp+0A0h]
0x18000b1ee  add     rsp, 20h
0x18000b1f2  pop     rbp
0x18000b1f3  retn
0x18000b1f5  push    rbp
0x18000b1f7  sub     rsp, 20h
0x18000b1fb  mov     rbp, rdx
0x18000b1fe  cmp     dword ptr [rbp+118h], 1
0x18000b205  ja      short loc_18000B211
0x18000b207  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
