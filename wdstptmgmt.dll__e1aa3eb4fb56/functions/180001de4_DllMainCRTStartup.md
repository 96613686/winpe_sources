# __DllMainCRTStartup

- ea: `0x180001de4`
- end: `0x180001ff1`
- name: `__DllMainCRTStartup`
- size: `525`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180001da0`

## callees

- `0x180001b5c`
- `0x180001de4`
- `0x18000269e`
- `0x180005cd4`
- `0x180020010`

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
  if ( (_DWORD)fdwReason || dword_18003B18C )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_18003B190 = 1;
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
            if ( dword_18003B190 )
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
0x180001de4  mov     [rsp+lpvReserved], r8
0x180001de9  mov     [rsp+arg_8], edx
0x180001ded  mov     [rsp+arg_0], rcx
0x180001df2  push    rbx
0x180001df3  push    rsi
0x180001df4  push    rdi
0x180001df5  sub     rsp, 150h
0x180001dfc  mov     edi, edx
0x180001dfe  mov     rsi, rcx
0x180001e01  mov     ebx, 1
0x180001e06  mov     [rsp+168h+var_148], ebx
0x180001e0a  cmp     edx, ebx
0x180001e0c  ja      short loc_180001E14
0x180001e0e  mov     cs:__native_dllmain_reason, edx
0x180001e14  test    edx, edx
0x180001e16  jnz     short loc_180001E2B
0x180001e18  cmp     cs:dword_18003B18C, edx
0x180001e1e  jnz     short loc_180001E2B
0x180001e20  xor     ebx, ebx
0x180001e22  mov     [rsp+168h+var_148], ebx
0x180001e26  jmp     loc_180001FD5
0x180001e2b  lea     eax, [rdx-1]
0x180001e2e  cmp     eax, 1
0x180001e31  ja      loc_180001EB7
0x180001e37  mov     rax, cs:_pRawDllMain
0x180001e3e  test    rax, rax
0x180001e41  jz      short loc_180001E78
0x180001e43  cmp     edx, 1
0x180001e46  jnz     short loc_180001E4E
0x180001e48  mov     cs:dword_18003B190, edx
0x180001e4e  mov     r8, [rsp+168h+lpvReserved]
0x180001e56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001e5b  mov     ebx, eax
0x180001e5d  mov     [rsp+168h+var_148], eax
0x180001e61  jmp     short loc_180001E78
0x180001e63  xor     ebx, ebx
0x180001e65  mov     [rsp+168h+var_148], ebx
0x180001e69  mov     edi, [rsp+168h+arg_8]
0x180001e70  mov     rsi, [rsp+168h+arg_0]
0x180001e78  test    ebx, ebx
0x180001e7a  jz      loc_180001FD5
0x180001e80  mov     r8, [rsp+168h+lpvReserved]
0x180001e88  mov     edx, edi
0x180001e8a  mov     rcx, rsi
0x180001e8d  call    _CRT_INIT
0x180001e92  mov     ebx, eax
0x180001e94  mov     [rsp+168h+var_148], eax
0x180001e98  jmp     short loc_180001EAF
0x180001e9a  xor     ebx, ebx
0x180001e9c  mov     [rsp+168h+var_148], ebx
0x180001ea0  mov     edi, [rsp+168h+arg_8]
0x180001ea7  mov     rsi, [rsp+168h+arg_0]
0x180001eaf  test    ebx, ebx
0x180001eb1  jz      loc_180001FD5
0x180001eb7  mov     r8, [rsp+168h+lpvReserved]; lpvReserved
0x180001ebf  mov     edx, edi; fdwReason
0x180001ec1  mov     rcx, rsi; hinstDLL
0x180001ec4  call    DllMain
0x180001ec9  mov     ebx, eax
0x180001ecb  mov     [rsp+168h+var_148], eax
0x180001ecf  jmp     short loc_180001EE6
0x180001ed1  xor     ebx, ebx
0x180001ed3  mov     [rsp+168h+var_148], ebx
0x180001ed7  mov     edi, [rsp+168h+arg_8]
0x180001ede  mov     rsi, [rsp+168h+arg_0]
0x180001ee6  cmp     edi, 1
0x180001ee9  jnz     short loc_180001F61
0x180001eeb  test    ebx, ebx
0x180001eed  jnz     short loc_180001F61
0x180001eef  xor     r8d, r8d; lpvReserved
0x180001ef2  xor     edx, edx; fdwReason
0x180001ef4  mov     rcx, rsi; hinstDLL
0x180001ef7  call    DllMain
0x180001efc  jmp     short loc_180001F11
0x180001efe  mov     edi, [rsp+168h+arg_8]
0x180001f05  mov     rsi, [rsp+168h+arg_0]
0x180001f0d  mov     ebx, [rsp+168h+var_148]
0x180001f11  xor     r8d, r8d
0x180001f14  xor     edx, edx
0x180001f16  mov     rcx, rsi
0x180001f19  call    _CRT_INIT
0x180001f1e  jmp     short loc_180001F33
0x180001f20  mov     edi, [rsp+168h+arg_8]
0x180001f27  mov     rsi, [rsp+168h+arg_0]
0x180001f2f  mov     ebx, [rsp+168h+var_148]
0x180001f33  mov     rax, cs:_pRawDllMain
0x180001f3a  test    rax, rax
0x180001f3d  jz      short loc_180001F61
0x180001f3f  xor     r8d, r8d
0x180001f42  xor     edx, edx
0x180001f44  mov     rcx, rsi
0x180001f47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001f4c  jmp     short loc_180001F61
0x180001f4e  mov     edi, [rsp+168h+arg_8]
0x180001f55  mov     rsi, [rsp+168h+arg_0]
0x180001f5d  mov     ebx, [rsp+168h+var_148]
0x180001f61  test    edi, edi
0x180001f63  jz      short loc_180001F6A
0x180001f65  cmp     edi, 3
0x180001f68  jnz     short loc_180001FD5
0x180001f6a  mov     r8, [rsp+168h+lpvReserved]
0x180001f72  mov     edx, edi
0x180001f74  mov     rcx, rsi
0x180001f77  call    _CRT_INIT
0x180001f7c  mov     ebx, eax
0x180001f7e  mov     [rsp+168h+var_148], eax
0x180001f82  jmp     short loc_180001F99
0x180001f84  xor     ebx, ebx
0x180001f86  mov     [rsp+168h+var_148], ebx
0x180001f8a  mov     edi, [rsp+168h+arg_8]
0x180001f91  mov     rsi, [rsp+168h+arg_0]
0x180001f99  mov     rax, cs:_pRawDllMain
0x180001fa0  test    rax, rax
0x180001fa3  jz      short loc_180001FD5
0x180001fa5  cmp     cs:dword_18003B190, 0
0x180001fac  jz      short loc_180001FD5
0x180001fae  mov     r8, [rsp+168h+lpvReserved]
0x180001fb6  mov     edx, edi
0x180001fb8  mov     rcx, rsi
0x180001fbb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001fc0  mov     ebx, eax
0x180001fc2  mov     [rsp+168h+var_148], eax
0x180001fc6  jmp     short loc_180001FD5
0x180001fc8  xor     ebx, ebx
0x180001fca  mov     [rsp+168h+var_148], ebx
0x180001fce  mov     edi, [rsp+168h+arg_8]
0x180001fd5  cmp     edi, 1
0x180001fd8  ja      short loc_180001FE4
0x180001fda  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x180001fe4  mov     eax, ebx
0x180001fe6  add     rsp, 150h
0x180001fed  pop     rdi
0x180001fee  pop     rsi
0x180001fef  pop     rbx
0x180001ff0  retn
0x18001eb72  push    rbp
0x18001eb74  sub     rsp, 20h
0x18001eb78  mov     rbp, rdx
0x18001eb7b  mov     [rbp+108h], rcx
0x18001eb82  mov     rax, [rcx]
0x18001eb85  mov     edx, [rax]
0x18001eb87  mov     [rbp+0A4h], edx
0x18001eb8d  mov     [rbp+0C8h], rcx
0x18001eb94  mov     [rbp+28h], edx
0x18001eb97  mov     eax, [rbp+28h]
0x18001eb9a  cmp     eax, 0E06D7363h
0x18001eb9f  jnz     short loc_18001EBB5
0x18001eba1  mov     rdx, [rbp+0C8h]
0x18001eba8  mov     ecx, [rbp+28h]
0x18001ebab  call    _XcptFilter_0
0x18001ebb0  mov     [rbp+30h], eax
0x18001ebb3  jmp     short loc_18001EBBC
0x18001ebb5  mov     dword ptr [rbp+30h], 0
0x18001ebbc  mov     eax, [rbp+30h]
0x18001ebbf  add     rsp, 20h
0x18001ebc3  pop     rbp
0x18001ebc4  retn
0x18001ebc6  push    rbp
0x18001ebc8  sub     rsp, 20h
0x18001ebcc  mov     rbp, rdx
0x18001ebcf  mov     [rbp+110h], rcx
0x18001ebd6  mov     rax, [rcx]
0x18001ebd9  mov     edx, [rax]
0x18001ebdb  mov     [rbp+0A8h], edx
0x18001ebe1  mov     [rbp+0D0h], rcx
0x18001ebe8  mov     [rbp+38h], edx
0x18001ebeb  mov     eax, [rbp+38h]
0x18001ebee  cmp     eax, 0E06D7363h
0x18001ebf3  jnz     short loc_18001EC09
0x18001ebf5  mov     rdx, [rbp+0D0h]
0x18001ebfc  mov     ecx, [rbp+38h]
0x18001ebff  call    _XcptFilter_0
0x18001ec04  mov     [rbp+40h], eax
0x18001ec07  jmp     short loc_18001EC10
0x18001ec09  mov     dword ptr [rbp+40h], 0
0x18001ec10  mov     eax, [rbp+40h]
0x18001ec13  add     rsp, 20h
0x18001ec17  pop     rbp
0x18001ec18  retn
0x18001ec1a  push    rbp
0x18001ec1c  sub     rsp, 20h
0x18001ec20  mov     rbp, rdx
0x18001ec23  mov     [rbp+118h], rcx
0x18001ec2a  mov     rax, [rcx]
0x18001ec2d  mov     edx, [rax]
0x18001ec2f  mov     [rbp+0ACh], edx
0x18001ec35  mov     [rbp+0D8h], rcx
0x18001ec3c  mov     [rbp+48h], edx
0x18001ec3f  mov     eax, [rbp+48h]
0x18001ec42  cmp     eax, 0E06D7363h
0x18001ec47  jnz     short loc_18001EC5D
0x18001ec49  mov     rdx, [rbp+0D8h]
0x18001ec50  mov     ecx, [rbp+48h]
0x18001ec53  call    _XcptFilter_0
0x18001ec58  mov     [rbp+50h], eax
0x18001ec5b  jmp     short loc_18001EC64
0x18001ec5d  mov     dword ptr [rbp+50h], 0
0x18001ec64  mov     eax, [rbp+50h]
0x18001ec67  add     rsp, 20h
0x18001ec6b  pop     rbp
0x18001ec6c  retn
0x18001ec6e  push    rbp
0x18001ec70  sub     rsp, 20h
0x18001ec74  mov     rbp, rdx
0x18001ec77  mov     [rbp+120h], rcx
0x18001ec7e  mov     rax, [rcx]
0x18001ec81  mov     edx, [rax]
0x18001ec83  mov     [rbp+0B0h], edx
0x18001ec89  mov     [rbp+0E0h], rcx
0x18001ec90  mov     [rbp+58h], edx
0x18001ec93  mov     eax, [rbp+58h]
0x18001ec96  cmp     eax, 0E06D7363h
0x18001ec9b  jnz     short loc_18001ECB1
0x18001ec9d  mov     rdx, [rbp+0E0h]
0x18001eca4  mov     ecx, [rbp+58h]
0x18001eca7  call    _XcptFilter_0
0x18001ecac  mov     [rbp+60h], eax
0x18001ecaf  jmp     short loc_18001ECB8
0x18001ecb1  mov     dword ptr [rbp+60h], 0
0x18001ecb8  mov     eax, [rbp+60h]
0x18001ecbb  add     rsp, 20h
0x18001ecbf  pop     rbp
0x18001ecc0  retn
0x18001ecc2  push    rbp
0x18001ecc4  sub     rsp, 20h
0x18001ecc8  mov     rbp, rdx
0x18001eccb  mov     [rbp+128h], rcx
0x18001ecd2  mov     rax, [rcx]
0x18001ecd5  mov     edx, [rax]
0x18001ecd7  mov     [rbp+0B4h], edx
0x18001ecdd  mov     [rbp+0E8h], rcx
0x18001ece4  mov     [rbp+68h], edx
0x18001ece7  mov     eax, [rbp+68h]
0x18001ecea  cmp     eax, 0E06D7363h
0x18001ecef  jnz     short loc_18001ED05
0x18001ecf1  mov     rdx, [rbp+0E8h]
0x18001ecf8  mov     ecx, [rbp+68h]
0x18001ecfb  call    _XcptFilter_0
0x18001ed00  mov     [rbp+70h], eax
0x18001ed03  jmp     short loc_18001ED0C
0x18001ed05  mov     dword ptr [rbp+70h], 0
0x18001ed0c  mov     eax, [rbp+70h]
0x18001ed0f  add     rsp, 20h
0x18001ed13  pop     rbp
0x18001ed14  retn
0x18001ed16  push    rbp
0x18001ed18  sub     rsp, 20h
0x18001ed1c  mov     rbp, rdx
0x18001ed1f  mov     [rbp+130h], rcx
0x18001ed26  mov     rax, [rcx]
0x18001ed29  mov     edx, [rax]
0x18001ed2b  mov     [rbp+0B8h], edx
0x18001ed31  mov     [rbp+0F0h], rcx
0x18001ed38  mov     [rbp+78h], edx
0x18001ed3b  mov     eax, [rbp+78h]
0x18001ed3e  cmp     eax, 0E06D7363h
0x18001ed43  jnz     short loc_18001ED5C
0x18001ed45  mov     rdx, [rbp+0F0h]
0x18001ed4c  mov     ecx, [rbp+78h]
0x18001ed4f  call    _XcptFilter_0
0x18001ed54  mov     [rbp+80h], eax
0x18001ed5a  jmp     short loc_18001ED66
0x18001ed5c  mov     dword ptr [rbp+80h], 0
0x18001ed66  mov     eax, [rbp+80h]
0x18001ed6c  add     rsp, 20h
0x18001ed70  pop     rbp
0x18001ed71  retn
0x18001ed73  push    rbp
0x18001ed75  sub     rsp, 20h
0x18001ed79  mov     rbp, rdx
0x18001ed7c  mov     [rbp+138h], rcx
0x18001ed83  mov     rax, [rcx]
0x18001ed86  mov     edx, [rax]
0x18001ed88  mov     [rbp+0BCh], edx
0x18001ed8e  mov     [rbp+0F8h], rcx
0x18001ed95  mov     [rbp+88h], edx
0x18001ed9b  mov     eax, [rbp+88h]
0x18001eda1  cmp     eax, 0E06D7363h
0x18001eda6  jnz     short loc_18001EDC2
0x18001eda8  mov     rdx, [rbp+0F8h]
0x18001edaf  mov     ecx, [rbp+88h]
0x18001edb5  call    _XcptFilter_0
0x18001edba  mov     [rbp+90h], eax
0x18001edc0  jmp     short loc_18001EDCC
0x18001edc2  mov     dword ptr [rbp+90h], 0
0x18001edcc  mov     eax, [rbp+90h]
0x18001edd2  add     rsp, 20h
0x18001edd6  pop     rbp
0x18001edd7  retn
0x18001edd9  push    rbp
0x18001eddb  sub     rsp, 20h
0x18001eddf  mov     rbp, rdx
0x18001ede2  mov     [rbp+140h], rcx
0x18001ede9  mov     rax, [rcx]
0x18001edec  mov     edx, [rax]
0x18001edee  mov     [rbp+0C0h], edx
0x18001edf4  mov     [rbp+100h], rcx
0x18001edfb  mov     [rbp+98h], edx
0x18001ee01  mov     eax, [rbp+98h]
0x18001ee07  cmp     eax, 0E06D7363h
  ... truncated ...
```
