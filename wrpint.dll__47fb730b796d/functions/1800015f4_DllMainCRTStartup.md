# __DllMainCRTStartup

- ea: `0x1800015f4`
- end: `0x180001800`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, __int64 fdwReason, void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1800015b0`

## callees

- `0x180001380`
- `0x1800015f4`
- `0x1800018f9`
- `0x180006b60`
- `0x18001b7f0`

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
  if ( (_DWORD)fdwReason || dword_18002B300 )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_18002B304 = 1;
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
            if ( dword_18002B304 )
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
0x1800015f4  mov     [rsp+lpvReserved], r8
0x1800015f9  mov     [rsp+arg_8], edx
0x1800015fd  mov     [rsp+arg_0], rcx
0x180001602  push    rbx
0x180001603  push    rsi
0x180001604  push    rdi
0x180001605  sub     rsp, 0F0h
0x18000160c  mov     edi, edx
0x18000160e  mov     rsi, rcx
0x180001611  mov     ebx, 1
0x180001616  cmp     edx, ebx
0x180001618  ja      short loc_180001620
0x18000161a  mov     cs:__native_dllmain_reason, edx
0x180001620  test    edx, edx
0x180001622  jnz     short loc_180001637
0x180001624  cmp     cs:dword_18002B300, edx
0x18000162a  jnz     short loc_180001637
0x18000162c  xor     ebx, ebx
0x18000162e  mov     [rsp+108h+var_E8], ebx
0x180001632  jmp     loc_1800017E4
0x180001637  lea     eax, [rdx-1]
0x18000163a  cmp     eax, 1
0x18000163d  ja      loc_1800016C4
0x180001643  mov     rax, cs:_pRawDllMain
0x18000164a  test    rax, rax
0x18000164d  jz      short loc_180001685
0x18000164f  cmp     edx, 1
0x180001652  jnz     short loc_18000165A
0x180001654  mov     cs:dword_18002B304, edx
0x18000165a  mov     r8, [rsp+108h+lpvReserved]
0x180001662  call    cs:__guard_dispatch_icall_fptr
0x180001668  mov     ebx, eax
0x18000166a  mov     [rsp+108h+var_E8], eax
0x18000166e  jmp     short loc_180001685
0x180001670  xor     ebx, ebx
0x180001672  mov     [rsp+108h+var_E8], ebx
0x180001676  mov     edi, [rsp+108h+arg_8]
0x18000167d  mov     rsi, [rsp+108h+arg_0]
0x180001685  test    ebx, ebx
0x180001687  jz      loc_1800017E4
0x18000168d  mov     r8, [rsp+108h+lpvReserved]
0x180001695  mov     edx, edi
0x180001697  mov     rcx, rsi
0x18000169a  call    _CRT_INIT
0x18000169f  mov     ebx, eax
0x1800016a1  mov     [rsp+108h+var_E8], eax
0x1800016a5  jmp     short loc_1800016BC
0x1800016a7  xor     ebx, ebx
0x1800016a9  mov     [rsp+108h+var_E8], ebx
0x1800016ad  mov     edi, [rsp+108h+arg_8]
0x1800016b4  mov     rsi, [rsp+108h+arg_0]
0x1800016bc  test    ebx, ebx
0x1800016be  jz      loc_1800017E4
0x1800016c4  mov     r8, [rsp+108h+lpvReserved]; lpvReserved
0x1800016cc  mov     edx, edi; fdwReason
0x1800016ce  mov     rcx, rsi; hinstDLL
0x1800016d1  call    DllMain
0x1800016d6  mov     ebx, eax
0x1800016d8  mov     [rsp+108h+var_E8], eax
0x1800016dc  jmp     short loc_1800016F3
0x1800016de  xor     ebx, ebx
0x1800016e0  mov     [rsp+108h+var_E8], ebx
0x1800016e4  mov     edi, [rsp+108h+arg_8]
0x1800016eb  mov     rsi, [rsp+108h+arg_0]
0x1800016f3  cmp     edi, 1
0x1800016f6  jnz     short loc_18000176F
0x1800016f8  test    ebx, ebx
0x1800016fa  jnz     short loc_18000176F
0x1800016fc  xor     r8d, r8d; lpvReserved
0x1800016ff  xor     edx, edx; fdwReason
0x180001701  mov     rcx, rsi; hinstDLL
0x180001704  call    DllMain
0x180001709  jmp     short loc_18000171E
0x18000170b  mov     edi, [rsp+108h+arg_8]
0x180001712  mov     rsi, [rsp+108h+arg_0]
0x18000171a  mov     ebx, [rsp+108h+var_E8]
0x18000171e  xor     r8d, r8d
0x180001721  xor     edx, edx
0x180001723  mov     rcx, rsi
0x180001726  call    _CRT_INIT
0x18000172b  jmp     short loc_180001740
0x18000172d  mov     edi, [rsp+108h+arg_8]
0x180001734  mov     rsi, [rsp+108h+arg_0]
0x18000173c  mov     ebx, [rsp+108h+var_E8]
0x180001740  mov     rax, cs:_pRawDllMain
0x180001747  test    rax, rax
0x18000174a  jz      short loc_18000176F
0x18000174c  xor     r8d, r8d
0x18000174f  xor     edx, edx
0x180001751  mov     rcx, rsi
0x180001754  call    cs:__guard_dispatch_icall_fptr
0x18000175a  jmp     short loc_18000176F
0x18000175c  mov     edi, [rsp+108h+arg_8]
0x180001763  mov     rsi, [rsp+108h+arg_0]
0x18000176b  mov     ebx, [rsp+108h+var_E8]
0x18000176f  test    edi, edi
0x180001771  jz      short loc_180001778
0x180001773  cmp     edi, 3
0x180001776  jnz     short loc_1800017E4
0x180001778  mov     r8, [rsp+108h+lpvReserved]
0x180001780  mov     edx, edi
0x180001782  mov     rcx, rsi
0x180001785  call    _CRT_INIT
0x18000178a  mov     ebx, eax
0x18000178c  mov     [rsp+108h+var_E8], eax
0x180001790  jmp     short loc_1800017A7
0x180001792  xor     ebx, ebx
0x180001794  mov     [rsp+108h+var_E8], ebx
0x180001798  mov     edi, [rsp+108h+arg_8]
0x18000179f  mov     rsi, [rsp+108h+arg_0]
0x1800017a7  mov     rax, cs:_pRawDllMain
0x1800017ae  test    rax, rax
0x1800017b1  jz      short loc_1800017E4
0x1800017b3  cmp     cs:dword_18002B304, 0
0x1800017ba  jz      short loc_1800017E4
0x1800017bc  mov     r8, [rsp+108h+lpvReserved]
0x1800017c4  mov     edx, edi
0x1800017c6  mov     rcx, rsi
0x1800017c9  call    cs:__guard_dispatch_icall_fptr
0x1800017cf  mov     ebx, eax
0x1800017d1  mov     [rsp+108h+var_E8], eax
0x1800017d5  jmp     short loc_1800017E4
0x1800017d7  xor     ebx, ebx
0x1800017d9  mov     [rsp+108h+var_E8], ebx
0x1800017dd  mov     edi, [rsp+108h+arg_8]
0x1800017e4  cmp     edi, 1
0x1800017e7  ja      short loc_1800017F3
0x1800017e9  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x1800017f3  mov     eax, ebx
0x1800017f5  add     rsp, 0F0h
0x1800017fc  pop     rdi
0x1800017fd  pop     rsi
0x1800017fe  pop     rbx
0x1800017ff  retn
0x18001b8c0  push    rbp
0x18001b8c2  sub     rsp, 20h
0x18001b8c6  mov     rbp, rdx
0x18001b8c9  mov     rax, [rcx]
0x18001b8cc  mov     edx, [rax]
0x18001b8ce  mov     [rbp+0A8h], rcx
0x18001b8d5  mov     [rbp+28h], edx
0x18001b8d8  mov     eax, [rbp+28h]
0x18001b8db  cmp     eax, 0E06D7363h
0x18001b8e0  jnz     short loc_18001B8F6
0x18001b8e2  mov     rdx, [rbp+0A8h]
0x18001b8e9  mov     ecx, [rbp+28h]
0x18001b8ec  call    _XcptFilter_0
0x18001b8f1  mov     [rbp+30h], eax
0x18001b8f4  jmp     short loc_18001B8FD
0x18001b8f6  mov     dword ptr [rbp+30h], 0
0x18001b8fd  mov     eax, [rbp+30h]
0x18001b900  add     rsp, 20h
0x18001b904  pop     rbp
0x18001b905  retn
0x18001b907  push    rbp
0x18001b909  sub     rsp, 20h
0x18001b90d  mov     rbp, rdx
0x18001b910  mov     rax, [rcx]
0x18001b913  mov     edx, [rax]
0x18001b915  mov     [rbp+0B0h], rcx
0x18001b91c  mov     [rbp+38h], edx
0x18001b91f  mov     eax, [rbp+38h]
0x18001b922  cmp     eax, 0E06D7363h
0x18001b927  jnz     short loc_18001B93D
0x18001b929  mov     rdx, [rbp+0B0h]
0x18001b930  mov     ecx, [rbp+38h]
0x18001b933  call    _XcptFilter_0
0x18001b938  mov     [rbp+40h], eax
0x18001b93b  jmp     short loc_18001B944
0x18001b93d  mov     dword ptr [rbp+40h], 0
0x18001b944  mov     eax, [rbp+40h]
0x18001b947  add     rsp, 20h
0x18001b94b  pop     rbp
0x18001b94c  retn
0x18001b94e  push    rbp
0x18001b950  sub     rsp, 20h
0x18001b954  mov     rbp, rdx
0x18001b957  mov     rax, [rcx]
0x18001b95a  mov     edx, [rax]
0x18001b95c  mov     [rbp+0B8h], rcx
0x18001b963  mov     [rbp+48h], edx
0x18001b966  mov     eax, [rbp+48h]
0x18001b969  cmp     eax, 0E06D7363h
0x18001b96e  jnz     short loc_18001B984
0x18001b970  mov     rdx, [rbp+0B8h]
0x18001b977  mov     ecx, [rbp+48h]
0x18001b97a  call    _XcptFilter_0
0x18001b97f  mov     [rbp+50h], eax
0x18001b982  jmp     short loc_18001B98B
0x18001b984  mov     dword ptr [rbp+50h], 0
0x18001b98b  mov     eax, [rbp+50h]
0x18001b98e  add     rsp, 20h
0x18001b992  pop     rbp
0x18001b993  retn
0x18001b995  push    rbp
0x18001b997  sub     rsp, 20h
0x18001b99b  mov     rbp, rdx
0x18001b99e  mov     rax, [rcx]
0x18001b9a1  mov     edx, [rax]
0x18001b9a3  mov     [rbp+0C0h], rcx
0x18001b9aa  mov     [rbp+58h], edx
0x18001b9ad  mov     eax, [rbp+58h]
0x18001b9b0  cmp     eax, 0E06D7363h
0x18001b9b5  jnz     short loc_18001B9CB
0x18001b9b7  mov     rdx, [rbp+0C0h]
0x18001b9be  mov     ecx, [rbp+58h]
0x18001b9c1  call    _XcptFilter_0
0x18001b9c6  mov     [rbp+60h], eax
0x18001b9c9  jmp     short loc_18001B9D2
0x18001b9cb  mov     dword ptr [rbp+60h], 0
0x18001b9d2  mov     eax, [rbp+60h]
0x18001b9d5  add     rsp, 20h
0x18001b9d9  pop     rbp
0x18001b9da  retn
0x18001b9dc  push    rbp
0x18001b9de  sub     rsp, 20h
0x18001b9e2  mov     rbp, rdx
0x18001b9e5  mov     rax, [rcx]
0x18001b9e8  mov     edx, [rax]
0x18001b9ea  mov     [rbp+0C8h], rcx
0x18001b9f1  mov     [rbp+68h], edx
0x18001b9f4  mov     eax, [rbp+68h]
0x18001b9f7  cmp     eax, 0E06D7363h
0x18001b9fc  jnz     short loc_18001BA12
0x18001b9fe  mov     rdx, [rbp+0C8h]
0x18001ba05  mov     ecx, [rbp+68h]
0x18001ba08  call    _XcptFilter_0
0x18001ba0d  mov     [rbp+70h], eax
0x18001ba10  jmp     short loc_18001BA19
0x18001ba12  mov     dword ptr [rbp+70h], 0
0x18001ba19  mov     eax, [rbp+70h]
0x18001ba1c  add     rsp, 20h
0x18001ba20  pop     rbp
0x18001ba21  retn
0x18001ba23  push    rbp
0x18001ba25  sub     rsp, 20h
0x18001ba29  mov     rbp, rdx
0x18001ba2c  mov     rax, [rcx]
0x18001ba2f  mov     edx, [rax]
0x18001ba31  mov     [rbp+0D0h], rcx
0x18001ba38  mov     [rbp+78h], edx
0x18001ba3b  mov     eax, [rbp+78h]
0x18001ba3e  cmp     eax, 0E06D7363h
0x18001ba43  jnz     short loc_18001BA5C
0x18001ba45  mov     rdx, [rbp+0D0h]
0x18001ba4c  mov     ecx, [rbp+78h]
0x18001ba4f  call    _XcptFilter_0
0x18001ba54  mov     [rbp+80h], eax
0x18001ba5a  jmp     short loc_18001BA66
0x18001ba5c  mov     dword ptr [rbp+80h], 0
0x18001ba66  mov     eax, [rbp+80h]
0x18001ba6c  add     rsp, 20h
0x18001ba70  pop     rbp
0x18001ba71  retn
0x18001ba73  push    rbp
0x18001ba75  sub     rsp, 20h
0x18001ba79  mov     rbp, rdx
0x18001ba7c  mov     rax, [rcx]
0x18001ba7f  mov     edx, [rax]
0x18001ba81  mov     [rbp+0D8h], rcx
0x18001ba88  mov     [rbp+88h], edx
0x18001ba8e  mov     eax, [rbp+88h]
0x18001ba94  cmp     eax, 0E06D7363h
0x18001ba99  jnz     short loc_18001BAB5
0x18001ba9b  mov     rdx, [rbp+0D8h]
0x18001baa2  mov     ecx, [rbp+88h]
0x18001baa8  call    _XcptFilter_0
0x18001baad  mov     [rbp+90h], eax
0x18001bab3  jmp     short loc_18001BABF
0x18001bab5  mov     dword ptr [rbp+90h], 0
0x18001babf  mov     eax, [rbp+90h]
0x18001bac5  add     rsp, 20h
0x18001bac9  pop     rbp
0x18001baca  retn
0x18001bacc  push    rbp
0x18001bace  sub     rsp, 20h
0x18001bad2  mov     rbp, rdx
0x18001bad5  mov     rax, [rcx]
0x18001bad8  mov     edx, [rax]
0x18001bada  mov     [rbp+0E0h], rcx
0x18001bae1  mov     [rbp+98h], edx
0x18001bae7  mov     eax, [rbp+98h]
0x18001baed  cmp     eax, 0E06D7363h
0x18001baf2  jnz     short loc_18001BB0E
0x18001baf4  mov     rdx, [rbp+0E0h]
0x18001bafb  mov     ecx, [rbp+98h]
0x18001bb01  call    _XcptFilter_0
0x18001bb06  mov     [rbp+0A0h], eax
0x18001bb0c  jmp     short loc_18001BB18
0x18001bb0e  mov     dword ptr [rbp+0A0h], 0
0x18001bb18  mov     eax, [rbp+0A0h]
0x18001bb1e  add     rsp, 20h
0x18001bb22  pop     rbp
0x18001bb23  retn
0x18001bb25  push    rbp
0x18001bb27  sub     rsp, 20h
0x18001bb2b  mov     rbp, rdx
0x18001bb2e  cmp     dword ptr [rbp+118h], 1
0x18001bb35  ja      short loc_18001BB41
0x18001bb37  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
