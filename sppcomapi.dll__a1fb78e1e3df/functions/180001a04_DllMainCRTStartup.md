# __DllMainCRTStartup

- ea: `0x180001a04`
- end: `0x180001c10`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1800019c0`

## callees

- `0x180001790`
- `0x180001a04`
- `0x180001fc6`
- `0x18001df6c`
- `0x18003c5a0`

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
  if ( (_DWORD)fdwReason || dword_1800468A0 )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_1800468A4 = 1;
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
            if ( dword_1800468A4 )
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
0x180001a04  mov     [rsp+lpvReserved], r8
0x180001a09  mov     [rsp+arg_8], edx
0x180001a0d  mov     [rsp+arg_0], rcx
0x180001a12  push    rbx
0x180001a13  push    rsi
0x180001a14  push    rdi
0x180001a15  sub     rsp, 0F0h
0x180001a1c  mov     edi, edx
0x180001a1e  mov     rsi, rcx
0x180001a21  mov     ebx, 1
0x180001a26  cmp     edx, ebx
0x180001a28  ja      short loc_180001A30
0x180001a2a  mov     cs:__native_dllmain_reason, edx
0x180001a30  test    edx, edx
0x180001a32  jnz     short loc_180001A47
0x180001a34  cmp     cs:dword_1800468A0, edx
0x180001a3a  jnz     short loc_180001A47
0x180001a3c  xor     ebx, ebx
0x180001a3e  mov     [rsp+108h+var_E8], ebx
0x180001a42  jmp     loc_180001BF4
0x180001a47  lea     eax, [rdx-1]
0x180001a4a  cmp     eax, 1
0x180001a4d  ja      loc_180001AD4
0x180001a53  mov     rax, cs:_pRawDllMain
0x180001a5a  test    rax, rax
0x180001a5d  jz      short loc_180001A95
0x180001a5f  cmp     edx, 1
0x180001a62  jnz     short loc_180001A6A
0x180001a64  mov     cs:dword_1800468A4, edx
0x180001a6a  mov     r8, [rsp+108h+lpvReserved]
0x180001a72  call    cs:__guard_dispatch_icall_fptr
0x180001a78  mov     ebx, eax
0x180001a7a  mov     [rsp+108h+var_E8], eax
0x180001a7e  jmp     short loc_180001A95
0x180001a80  xor     ebx, ebx
0x180001a82  mov     [rsp+108h+var_E8], ebx
0x180001a86  mov     edi, [rsp+108h+arg_8]
0x180001a8d  mov     rsi, [rsp+108h+arg_0]
0x180001a95  test    ebx, ebx
0x180001a97  jz      loc_180001BF4
0x180001a9d  mov     r8, [rsp+108h+lpvReserved]
0x180001aa5  mov     edx, edi
0x180001aa7  mov     rcx, rsi
0x180001aaa  call    _CRT_INIT
0x180001aaf  mov     ebx, eax
0x180001ab1  mov     [rsp+108h+var_E8], eax
0x180001ab5  jmp     short loc_180001ACC
0x180001ab7  xor     ebx, ebx
0x180001ab9  mov     [rsp+108h+var_E8], ebx
0x180001abd  mov     edi, [rsp+108h+arg_8]
0x180001ac4  mov     rsi, [rsp+108h+arg_0]
0x180001acc  test    ebx, ebx
0x180001ace  jz      loc_180001BF4
0x180001ad4  mov     r8, [rsp+108h+lpvReserved]; lpvReserved
0x180001adc  mov     edx, edi; fdwReason
0x180001ade  mov     rcx, rsi; hinstDLL
0x180001ae1  call    DllMain
0x180001ae6  mov     ebx, eax
0x180001ae8  mov     [rsp+108h+var_E8], eax
0x180001aec  jmp     short loc_180001B03
0x180001aee  xor     ebx, ebx
0x180001af0  mov     [rsp+108h+var_E8], ebx
0x180001af4  mov     edi, [rsp+108h+arg_8]
0x180001afb  mov     rsi, [rsp+108h+arg_0]
0x180001b03  cmp     edi, 1
0x180001b06  jnz     short loc_180001B7F
0x180001b08  test    ebx, ebx
0x180001b0a  jnz     short loc_180001B7F
0x180001b0c  xor     r8d, r8d; lpvReserved
0x180001b0f  xor     edx, edx; fdwReason
0x180001b11  mov     rcx, rsi; hinstDLL
0x180001b14  call    DllMain
0x180001b19  jmp     short loc_180001B2E
0x180001b1b  mov     edi, [rsp+108h+arg_8]
0x180001b22  mov     rsi, [rsp+108h+arg_0]
0x180001b2a  mov     ebx, [rsp+108h+var_E8]
0x180001b2e  xor     r8d, r8d
0x180001b31  xor     edx, edx
0x180001b33  mov     rcx, rsi
0x180001b36  call    _CRT_INIT
0x180001b3b  jmp     short loc_180001B50
0x180001b3d  mov     edi, [rsp+108h+arg_8]
0x180001b44  mov     rsi, [rsp+108h+arg_0]
0x180001b4c  mov     ebx, [rsp+108h+var_E8]
0x180001b50  mov     rax, cs:_pRawDllMain
0x180001b57  test    rax, rax
0x180001b5a  jz      short loc_180001B7F
0x180001b5c  xor     r8d, r8d
0x180001b5f  xor     edx, edx
0x180001b61  mov     rcx, rsi
0x180001b64  call    cs:__guard_dispatch_icall_fptr
0x180001b6a  jmp     short loc_180001B7F
0x180001b6c  mov     edi, [rsp+108h+arg_8]
0x180001b73  mov     rsi, [rsp+108h+arg_0]
0x180001b7b  mov     ebx, [rsp+108h+var_E8]
0x180001b7f  test    edi, edi
0x180001b81  jz      short loc_180001B88
0x180001b83  cmp     edi, 3
0x180001b86  jnz     short loc_180001BF4
0x180001b88  mov     r8, [rsp+108h+lpvReserved]
0x180001b90  mov     edx, edi
0x180001b92  mov     rcx, rsi
0x180001b95  call    _CRT_INIT
0x180001b9a  mov     ebx, eax
0x180001b9c  mov     [rsp+108h+var_E8], eax
0x180001ba0  jmp     short loc_180001BB7
0x180001ba2  xor     ebx, ebx
0x180001ba4  mov     [rsp+108h+var_E8], ebx
0x180001ba8  mov     edi, [rsp+108h+arg_8]
0x180001baf  mov     rsi, [rsp+108h+arg_0]
0x180001bb7  mov     rax, cs:_pRawDllMain
0x180001bbe  test    rax, rax
0x180001bc1  jz      short loc_180001BF4
0x180001bc3  cmp     cs:dword_1800468A4, 0
0x180001bca  jz      short loc_180001BF4
0x180001bcc  mov     r8, [rsp+108h+lpvReserved]
0x180001bd4  mov     edx, edi
0x180001bd6  mov     rcx, rsi
0x180001bd9  call    cs:__guard_dispatch_icall_fptr
0x180001bdf  mov     ebx, eax
0x180001be1  mov     [rsp+108h+var_E8], eax
0x180001be5  jmp     short loc_180001BF4
0x180001be7  xor     ebx, ebx
0x180001be9  mov     [rsp+108h+var_E8], ebx
0x180001bed  mov     edi, [rsp+108h+arg_8]
0x180001bf4  cmp     edi, 1
0x180001bf7  ja      short loc_180001C03
0x180001bf9  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x180001c03  mov     eax, ebx
0x180001c05  add     rsp, 0F0h
0x180001c0c  pop     rdi
0x180001c0d  pop     rsi
0x180001c0e  pop     rbx
0x180001c0f  retn
0x18003c670  push    rbp
0x18003c672  sub     rsp, 20h
0x18003c676  mov     rbp, rdx
0x18003c679  mov     rax, [rcx]
0x18003c67c  mov     edx, [rax]
0x18003c67e  mov     [rbp+0A8h], rcx
0x18003c685  mov     [rbp+28h], edx
0x18003c688  mov     eax, [rbp+28h]
0x18003c68b  cmp     eax, 0E06D7363h
0x18003c690  jnz     short loc_18003C6A6
0x18003c692  mov     rdx, [rbp+0A8h]
0x18003c699  mov     ecx, [rbp+28h]
0x18003c69c  call    _XcptFilter_0
0x18003c6a1  mov     [rbp+30h], eax
0x18003c6a4  jmp     short loc_18003C6AD
0x18003c6a6  mov     dword ptr [rbp+30h], 0
0x18003c6ad  mov     eax, [rbp+30h]
0x18003c6b0  add     rsp, 20h
0x18003c6b4  pop     rbp
0x18003c6b5  retn
0x18003c6b7  push    rbp
0x18003c6b9  sub     rsp, 20h
0x18003c6bd  mov     rbp, rdx
0x18003c6c0  mov     rax, [rcx]
0x18003c6c3  mov     edx, [rax]
0x18003c6c5  mov     [rbp+0B0h], rcx
0x18003c6cc  mov     [rbp+38h], edx
0x18003c6cf  mov     eax, [rbp+38h]
0x18003c6d2  cmp     eax, 0E06D7363h
0x18003c6d7  jnz     short loc_18003C6ED
0x18003c6d9  mov     rdx, [rbp+0B0h]
0x18003c6e0  mov     ecx, [rbp+38h]
0x18003c6e3  call    _XcptFilter_0
0x18003c6e8  mov     [rbp+40h], eax
0x18003c6eb  jmp     short loc_18003C6F4
0x18003c6ed  mov     dword ptr [rbp+40h], 0
0x18003c6f4  mov     eax, [rbp+40h]
0x18003c6f7  add     rsp, 20h
0x18003c6fb  pop     rbp
0x18003c6fc  retn
0x18003c6fe  push    rbp
0x18003c700  sub     rsp, 20h
0x18003c704  mov     rbp, rdx
0x18003c707  mov     rax, [rcx]
0x18003c70a  mov     edx, [rax]
0x18003c70c  mov     [rbp+0B8h], rcx
0x18003c713  mov     [rbp+48h], edx
0x18003c716  mov     eax, [rbp+48h]
0x18003c719  cmp     eax, 0E06D7363h
0x18003c71e  jnz     short loc_18003C734
0x18003c720  mov     rdx, [rbp+0B8h]
0x18003c727  mov     ecx, [rbp+48h]
0x18003c72a  call    _XcptFilter_0
0x18003c72f  mov     [rbp+50h], eax
0x18003c732  jmp     short loc_18003C73B
0x18003c734  mov     dword ptr [rbp+50h], 0
0x18003c73b  mov     eax, [rbp+50h]
0x18003c73e  add     rsp, 20h
0x18003c742  pop     rbp
0x18003c743  retn
0x18003c745  push    rbp
0x18003c747  sub     rsp, 20h
0x18003c74b  mov     rbp, rdx
0x18003c74e  mov     rax, [rcx]
0x18003c751  mov     edx, [rax]
0x18003c753  mov     [rbp+0C0h], rcx
0x18003c75a  mov     [rbp+58h], edx
0x18003c75d  mov     eax, [rbp+58h]
0x18003c760  cmp     eax, 0E06D7363h
0x18003c765  jnz     short loc_18003C77B
0x18003c767  mov     rdx, [rbp+0C0h]
0x18003c76e  mov     ecx, [rbp+58h]
0x18003c771  call    _XcptFilter_0
0x18003c776  mov     [rbp+60h], eax
0x18003c779  jmp     short loc_18003C782
0x18003c77b  mov     dword ptr [rbp+60h], 0
0x18003c782  mov     eax, [rbp+60h]
0x18003c785  add     rsp, 20h
0x18003c789  pop     rbp
0x18003c78a  retn
0x18003c78c  push    rbp
0x18003c78e  sub     rsp, 20h
0x18003c792  mov     rbp, rdx
0x18003c795  mov     rax, [rcx]
0x18003c798  mov     edx, [rax]
0x18003c79a  mov     [rbp+0C8h], rcx
0x18003c7a1  mov     [rbp+68h], edx
0x18003c7a4  mov     eax, [rbp+68h]
0x18003c7a7  cmp     eax, 0E06D7363h
0x18003c7ac  jnz     short loc_18003C7C2
0x18003c7ae  mov     rdx, [rbp+0C8h]
0x18003c7b5  mov     ecx, [rbp+68h]
0x18003c7b8  call    _XcptFilter_0
0x18003c7bd  mov     [rbp+70h], eax
0x18003c7c0  jmp     short loc_18003C7C9
0x18003c7c2  mov     dword ptr [rbp+70h], 0
0x18003c7c9  mov     eax, [rbp+70h]
0x18003c7cc  add     rsp, 20h
0x18003c7d0  pop     rbp
0x18003c7d1  retn
0x18003c7d3  push    rbp
0x18003c7d5  sub     rsp, 20h
0x18003c7d9  mov     rbp, rdx
0x18003c7dc  mov     rax, [rcx]
0x18003c7df  mov     edx, [rax]
0x18003c7e1  mov     [rbp+0D0h], rcx
0x18003c7e8  mov     [rbp+78h], edx
0x18003c7eb  mov     eax, [rbp+78h]
0x18003c7ee  cmp     eax, 0E06D7363h
0x18003c7f3  jnz     short loc_18003C80C
0x18003c7f5  mov     rdx, [rbp+0D0h]
0x18003c7fc  mov     ecx, [rbp+78h]
0x18003c7ff  call    _XcptFilter_0
0x18003c804  mov     [rbp+80h], eax
0x18003c80a  jmp     short loc_18003C816
0x18003c80c  mov     dword ptr [rbp+80h], 0
0x18003c816  mov     eax, [rbp+80h]
0x18003c81c  add     rsp, 20h
0x18003c820  pop     rbp
0x18003c821  retn
0x18003c823  push    rbp
0x18003c825  sub     rsp, 20h
0x18003c829  mov     rbp, rdx
0x18003c82c  mov     rax, [rcx]
0x18003c82f  mov     edx, [rax]
0x18003c831  mov     [rbp+0D8h], rcx
0x18003c838  mov     [rbp+88h], edx
0x18003c83e  mov     eax, [rbp+88h]
0x18003c844  cmp     eax, 0E06D7363h
0x18003c849  jnz     short loc_18003C865
0x18003c84b  mov     rdx, [rbp+0D8h]
0x18003c852  mov     ecx, [rbp+88h]
0x18003c858  call    _XcptFilter_0
0x18003c85d  mov     [rbp+90h], eax
0x18003c863  jmp     short loc_18003C86F
0x18003c865  mov     dword ptr [rbp+90h], 0
0x18003c86f  mov     eax, [rbp+90h]
0x18003c875  add     rsp, 20h
0x18003c879  pop     rbp
0x18003c87a  retn
0x18003c87c  push    rbp
0x18003c87e  sub     rsp, 20h
0x18003c882  mov     rbp, rdx
0x18003c885  mov     rax, [rcx]
0x18003c888  mov     edx, [rax]
0x18003c88a  mov     [rbp+0E0h], rcx
0x18003c891  mov     [rbp+98h], edx
0x18003c897  mov     eax, [rbp+98h]
0x18003c89d  cmp     eax, 0E06D7363h
0x18003c8a2  jnz     short loc_18003C8BE
0x18003c8a4  mov     rdx, [rbp+0E0h]
0x18003c8ab  mov     ecx, [rbp+98h]
0x18003c8b1  call    _XcptFilter_0
0x18003c8b6  mov     [rbp+0A0h], eax
0x18003c8bc  jmp     short loc_18003C8C8
0x18003c8be  mov     dword ptr [rbp+0A0h], 0
0x18003c8c8  mov     eax, [rbp+0A0h]
0x18003c8ce  add     rsp, 20h
0x18003c8d2  pop     rbp
0x18003c8d3  retn
0x18003c8d5  push    rbp
0x18003c8d7  sub     rsp, 20h
0x18003c8db  mov     rbp, rdx
0x18003c8de  cmp     dword ptr [rbp+118h], 1
0x18003c8e5  ja      short loc_18003C8F1
0x18003c8e7  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
