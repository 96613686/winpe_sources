# __DllMainCRTStartup

- ea: `0x180001d64`
- end: `0x180001f70`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180001d20`

## callees

- `0x180001af0`
- `0x180001d64`
- `0x180001f76`
- `0x180003258`
- `0x180016c90`

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
  if ( (_DWORD)fdwReason || dword_180022240 )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_180022244 = 1;
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
            if ( dword_180022244 )
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
0x180001d64  mov     [rsp+lpvReserved], r8
0x180001d69  mov     [rsp+arg_8], edx
0x180001d6d  mov     [rsp+arg_0], rcx
0x180001d72  push    rbx
0x180001d73  push    rsi
0x180001d74  push    rdi
0x180001d75  sub     rsp, 0F0h
0x180001d7c  mov     edi, edx
0x180001d7e  mov     rsi, rcx
0x180001d81  mov     ebx, 1
0x180001d86  cmp     edx, ebx
0x180001d88  ja      short loc_180001D90
0x180001d8a  mov     cs:__native_dllmain_reason, edx
0x180001d90  test    edx, edx
0x180001d92  jnz     short loc_180001DA7
0x180001d94  cmp     cs:dword_180022240, edx
0x180001d9a  jnz     short loc_180001DA7
0x180001d9c  xor     ebx, ebx
0x180001d9e  mov     [rsp+108h+var_E8], ebx
0x180001da2  jmp     loc_180001F54
0x180001da7  lea     eax, [rdx-1]
0x180001daa  cmp     eax, 1
0x180001dad  ja      loc_180001E34
0x180001db3  mov     rax, cs:_pRawDllMain
0x180001dba  test    rax, rax
0x180001dbd  jz      short loc_180001DF5
0x180001dbf  cmp     edx, 1
0x180001dc2  jnz     short loc_180001DCA
0x180001dc4  mov     cs:dword_180022244, edx
0x180001dca  mov     r8, [rsp+108h+lpvReserved]
0x180001dd2  call    cs:__guard_dispatch_icall_fptr
0x180001dd8  mov     ebx, eax
0x180001dda  mov     [rsp+108h+var_E8], eax
0x180001dde  jmp     short loc_180001DF5
0x180001de0  xor     ebx, ebx
0x180001de2  mov     [rsp+108h+var_E8], ebx
0x180001de6  mov     edi, [rsp+108h+arg_8]
0x180001ded  mov     rsi, [rsp+108h+arg_0]
0x180001df5  test    ebx, ebx
0x180001df7  jz      loc_180001F54
0x180001dfd  mov     r8, [rsp+108h+lpvReserved]
0x180001e05  mov     edx, edi
0x180001e07  mov     rcx, rsi
0x180001e0a  call    _CRT_INIT
0x180001e0f  mov     ebx, eax
0x180001e11  mov     [rsp+108h+var_E8], eax
0x180001e15  jmp     short loc_180001E2C
0x180001e17  xor     ebx, ebx
0x180001e19  mov     [rsp+108h+var_E8], ebx
0x180001e1d  mov     edi, [rsp+108h+arg_8]
0x180001e24  mov     rsi, [rsp+108h+arg_0]
0x180001e2c  test    ebx, ebx
0x180001e2e  jz      loc_180001F54
0x180001e34  mov     r8, [rsp+108h+lpvReserved]; lpvReserved
0x180001e3c  mov     edx, edi; fdwReason
0x180001e3e  mov     rcx, rsi; hinstDLL
0x180001e41  call    DllMain
0x180001e46  mov     ebx, eax
0x180001e48  mov     [rsp+108h+var_E8], eax
0x180001e4c  jmp     short loc_180001E63
0x180001e4e  xor     ebx, ebx
0x180001e50  mov     [rsp+108h+var_E8], ebx
0x180001e54  mov     edi, [rsp+108h+arg_8]
0x180001e5b  mov     rsi, [rsp+108h+arg_0]
0x180001e63  cmp     edi, 1
0x180001e66  jnz     short loc_180001EDF
0x180001e68  test    ebx, ebx
0x180001e6a  jnz     short loc_180001EDF
0x180001e6c  xor     r8d, r8d; lpvReserved
0x180001e6f  xor     edx, edx; fdwReason
0x180001e71  mov     rcx, rsi; hinstDLL
0x180001e74  call    DllMain
0x180001e79  jmp     short loc_180001E8E
0x180001e7b  mov     edi, [rsp+108h+arg_8]
0x180001e82  mov     rsi, [rsp+108h+arg_0]
0x180001e8a  mov     ebx, [rsp+108h+var_E8]
0x180001e8e  xor     r8d, r8d
0x180001e91  xor     edx, edx
0x180001e93  mov     rcx, rsi
0x180001e96  call    _CRT_INIT
0x180001e9b  jmp     short loc_180001EB0
0x180001e9d  mov     edi, [rsp+108h+arg_8]
0x180001ea4  mov     rsi, [rsp+108h+arg_0]
0x180001eac  mov     ebx, [rsp+108h+var_E8]
0x180001eb0  mov     rax, cs:_pRawDllMain
0x180001eb7  test    rax, rax
0x180001eba  jz      short loc_180001EDF
0x180001ebc  xor     r8d, r8d
0x180001ebf  xor     edx, edx
0x180001ec1  mov     rcx, rsi
0x180001ec4  call    cs:__guard_dispatch_icall_fptr
0x180001eca  jmp     short loc_180001EDF
0x180001ecc  mov     edi, [rsp+108h+arg_8]
0x180001ed3  mov     rsi, [rsp+108h+arg_0]
0x180001edb  mov     ebx, [rsp+108h+var_E8]
0x180001edf  test    edi, edi
0x180001ee1  jz      short loc_180001EE8
0x180001ee3  cmp     edi, 3
0x180001ee6  jnz     short loc_180001F54
0x180001ee8  mov     r8, [rsp+108h+lpvReserved]
0x180001ef0  mov     edx, edi
0x180001ef2  mov     rcx, rsi
0x180001ef5  call    _CRT_INIT
0x180001efa  mov     ebx, eax
0x180001efc  mov     [rsp+108h+var_E8], eax
0x180001f00  jmp     short loc_180001F17
0x180001f02  xor     ebx, ebx
0x180001f04  mov     [rsp+108h+var_E8], ebx
0x180001f08  mov     edi, [rsp+108h+arg_8]
0x180001f0f  mov     rsi, [rsp+108h+arg_0]
0x180001f17  mov     rax, cs:_pRawDllMain
0x180001f1e  test    rax, rax
0x180001f21  jz      short loc_180001F54
0x180001f23  cmp     cs:dword_180022244, 0
0x180001f2a  jz      short loc_180001F54
0x180001f2c  mov     r8, [rsp+108h+lpvReserved]
0x180001f34  mov     edx, edi
0x180001f36  mov     rcx, rsi
0x180001f39  call    cs:__guard_dispatch_icall_fptr
0x180001f3f  mov     ebx, eax
0x180001f41  mov     [rsp+108h+var_E8], eax
0x180001f45  jmp     short loc_180001F54
0x180001f47  xor     ebx, ebx
0x180001f49  mov     [rsp+108h+var_E8], ebx
0x180001f4d  mov     edi, [rsp+108h+arg_8]
0x180001f54  cmp     edi, 1
0x180001f57  ja      short loc_180001F63
0x180001f59  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x180001f63  mov     eax, ebx
0x180001f65  add     rsp, 0F0h
0x180001f6c  pop     rdi
0x180001f6d  pop     rsi
0x180001f6e  pop     rbx
0x180001f6f  retn
0x180016d63  push    rbp
0x180016d65  sub     rsp, 20h
0x180016d69  mov     rbp, rdx
0x180016d6c  mov     rax, [rcx]
0x180016d6f  mov     edx, [rax]
0x180016d71  mov     [rbp+0A8h], rcx
0x180016d78  mov     [rbp+28h], edx
0x180016d7b  mov     eax, [rbp+28h]
0x180016d7e  cmp     eax, 0E06D7363h
0x180016d83  jnz     short loc_180016D99
0x180016d85  mov     rdx, [rbp+0A8h]
0x180016d8c  mov     ecx, [rbp+28h]
0x180016d8f  call    _XcptFilter_0
0x180016d94  mov     [rbp+30h], eax
0x180016d97  jmp     short loc_180016DA0
0x180016d99  mov     dword ptr [rbp+30h], 0
0x180016da0  mov     eax, [rbp+30h]
0x180016da3  add     rsp, 20h
0x180016da7  pop     rbp
0x180016da8  retn
0x180016daa  push    rbp
0x180016dac  sub     rsp, 20h
0x180016db0  mov     rbp, rdx
0x180016db3  mov     rax, [rcx]
0x180016db6  mov     edx, [rax]
0x180016db8  mov     [rbp+0B0h], rcx
0x180016dbf  mov     [rbp+38h], edx
0x180016dc2  mov     eax, [rbp+38h]
0x180016dc5  cmp     eax, 0E06D7363h
0x180016dca  jnz     short loc_180016DE0
0x180016dcc  mov     rdx, [rbp+0B0h]
0x180016dd3  mov     ecx, [rbp+38h]
0x180016dd6  call    _XcptFilter_0
0x180016ddb  mov     [rbp+40h], eax
0x180016dde  jmp     short loc_180016DE7
0x180016de0  mov     dword ptr [rbp+40h], 0
0x180016de7  mov     eax, [rbp+40h]
0x180016dea  add     rsp, 20h
0x180016dee  pop     rbp
0x180016def  retn
0x180016df1  push    rbp
0x180016df3  sub     rsp, 20h
0x180016df7  mov     rbp, rdx
0x180016dfa  mov     rax, [rcx]
0x180016dfd  mov     edx, [rax]
0x180016dff  mov     [rbp+0B8h], rcx
0x180016e06  mov     [rbp+48h], edx
0x180016e09  mov     eax, [rbp+48h]
0x180016e0c  cmp     eax, 0E06D7363h
0x180016e11  jnz     short loc_180016E27
0x180016e13  mov     rdx, [rbp+0B8h]
0x180016e1a  mov     ecx, [rbp+48h]
0x180016e1d  call    _XcptFilter_0
0x180016e22  mov     [rbp+50h], eax
0x180016e25  jmp     short loc_180016E2E
0x180016e27  mov     dword ptr [rbp+50h], 0
0x180016e2e  mov     eax, [rbp+50h]
0x180016e31  add     rsp, 20h
0x180016e35  pop     rbp
0x180016e36  retn
0x180016e38  push    rbp
0x180016e3a  sub     rsp, 20h
0x180016e3e  mov     rbp, rdx
0x180016e41  mov     rax, [rcx]
0x180016e44  mov     edx, [rax]
0x180016e46  mov     [rbp+0C0h], rcx
0x180016e4d  mov     [rbp+58h], edx
0x180016e50  mov     eax, [rbp+58h]
0x180016e53  cmp     eax, 0E06D7363h
0x180016e58  jnz     short loc_180016E6E
0x180016e5a  mov     rdx, [rbp+0C0h]
0x180016e61  mov     ecx, [rbp+58h]
0x180016e64  call    _XcptFilter_0
0x180016e69  mov     [rbp+60h], eax
0x180016e6c  jmp     short loc_180016E75
0x180016e6e  mov     dword ptr [rbp+60h], 0
0x180016e75  mov     eax, [rbp+60h]
0x180016e78  add     rsp, 20h
0x180016e7c  pop     rbp
0x180016e7d  retn
0x180016e7f  push    rbp
0x180016e81  sub     rsp, 20h
0x180016e85  mov     rbp, rdx
0x180016e88  mov     rax, [rcx]
0x180016e8b  mov     edx, [rax]
0x180016e8d  mov     [rbp+0C8h], rcx
0x180016e94  mov     [rbp+68h], edx
0x180016e97  mov     eax, [rbp+68h]
0x180016e9a  cmp     eax, 0E06D7363h
0x180016e9f  jnz     short loc_180016EB5
0x180016ea1  mov     rdx, [rbp+0C8h]
0x180016ea8  mov     ecx, [rbp+68h]
0x180016eab  call    _XcptFilter_0
0x180016eb0  mov     [rbp+70h], eax
0x180016eb3  jmp     short loc_180016EBC
0x180016eb5  mov     dword ptr [rbp+70h], 0
0x180016ebc  mov     eax, [rbp+70h]
0x180016ebf  add     rsp, 20h
0x180016ec3  pop     rbp
0x180016ec4  retn
0x180016ec6  push    rbp
0x180016ec8  sub     rsp, 20h
0x180016ecc  mov     rbp, rdx
0x180016ecf  mov     rax, [rcx]
0x180016ed2  mov     edx, [rax]
0x180016ed4  mov     [rbp+0D0h], rcx
0x180016edb  mov     [rbp+78h], edx
0x180016ede  mov     eax, [rbp+78h]
0x180016ee1  cmp     eax, 0E06D7363h
0x180016ee6  jnz     short loc_180016EFF
0x180016ee8  mov     rdx, [rbp+0D0h]
0x180016eef  mov     ecx, [rbp+78h]
0x180016ef2  call    _XcptFilter_0
0x180016ef7  mov     [rbp+80h], eax
0x180016efd  jmp     short loc_180016F09
0x180016eff  mov     dword ptr [rbp+80h], 0
0x180016f09  mov     eax, [rbp+80h]
0x180016f0f  add     rsp, 20h
0x180016f13  pop     rbp
0x180016f14  retn
0x180016f16  push    rbp
0x180016f18  sub     rsp, 20h
0x180016f1c  mov     rbp, rdx
0x180016f1f  mov     rax, [rcx]
0x180016f22  mov     edx, [rax]
0x180016f24  mov     [rbp+0D8h], rcx
0x180016f2b  mov     [rbp+88h], edx
0x180016f31  mov     eax, [rbp+88h]
0x180016f37  cmp     eax, 0E06D7363h
0x180016f3c  jnz     short loc_180016F58
0x180016f3e  mov     rdx, [rbp+0D8h]
0x180016f45  mov     ecx, [rbp+88h]
0x180016f4b  call    _XcptFilter_0
0x180016f50  mov     [rbp+90h], eax
0x180016f56  jmp     short loc_180016F62
0x180016f58  mov     dword ptr [rbp+90h], 0
0x180016f62  mov     eax, [rbp+90h]
0x180016f68  add     rsp, 20h
0x180016f6c  pop     rbp
0x180016f6d  retn
0x180016f6f  push    rbp
0x180016f71  sub     rsp, 20h
0x180016f75  mov     rbp, rdx
0x180016f78  mov     rax, [rcx]
0x180016f7b  mov     edx, [rax]
0x180016f7d  mov     [rbp+0E0h], rcx
0x180016f84  mov     [rbp+98h], edx
0x180016f8a  mov     eax, [rbp+98h]
0x180016f90  cmp     eax, 0E06D7363h
0x180016f95  jnz     short loc_180016FB1
0x180016f97  mov     rdx, [rbp+0E0h]
0x180016f9e  mov     ecx, [rbp+98h]
0x180016fa4  call    _XcptFilter_0
0x180016fa9  mov     [rbp+0A0h], eax
0x180016faf  jmp     short loc_180016FBB
0x180016fb1  mov     dword ptr [rbp+0A0h], 0
0x180016fbb  mov     eax, [rbp+0A0h]
0x180016fc1  add     rsp, 20h
0x180016fc5  pop     rbp
0x180016fc6  retn
0x180016fc8  push    rbp
0x180016fca  sub     rsp, 20h
0x180016fce  mov     rbp, rdx
0x180016fd1  cmp     dword ptr [rbp+118h], 1
0x180016fd8  ja      short loc_180016FE4
0x180016fda  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
