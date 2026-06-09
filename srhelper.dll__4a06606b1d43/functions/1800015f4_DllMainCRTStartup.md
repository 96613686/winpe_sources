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
- `0x180001c78`
- `0x18000a1bc`
- `0x180015830`

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
  if ( (_DWORD)fdwReason || dword_18001D3E0 )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_18001D3E4 = 1;
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
            if ( dword_18001D3E4 )
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
0x180001624  cmp     cs:dword_18001D3E0, edx
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
0x180001654  mov     cs:dword_18001D3E4, edx
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
0x1800017b3  cmp     cs:dword_18001D3E4, 0
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
0x180015900  push    rbp
0x180015902  sub     rsp, 20h
0x180015906  mov     rbp, rdx
0x180015909  mov     rax, [rcx]
0x18001590c  mov     edx, [rax]
0x18001590e  mov     [rbp+0A8h], rcx
0x180015915  mov     [rbp+28h], edx
0x180015918  mov     eax, [rbp+28h]
0x18001591b  cmp     eax, 0E06D7363h
0x180015920  jnz     short loc_180015936
0x180015922  mov     rdx, [rbp+0A8h]
0x180015929  mov     ecx, [rbp+28h]
0x18001592c  call    _XcptFilter_0
0x180015931  mov     [rbp+30h], eax
0x180015934  jmp     short loc_18001593D
0x180015936  mov     dword ptr [rbp+30h], 0
0x18001593d  mov     eax, [rbp+30h]
0x180015940  add     rsp, 20h
0x180015944  pop     rbp
0x180015945  retn
0x180015947  push    rbp
0x180015949  sub     rsp, 20h
0x18001594d  mov     rbp, rdx
0x180015950  mov     rax, [rcx]
0x180015953  mov     edx, [rax]
0x180015955  mov     [rbp+0B0h], rcx
0x18001595c  mov     [rbp+38h], edx
0x18001595f  mov     eax, [rbp+38h]
0x180015962  cmp     eax, 0E06D7363h
0x180015967  jnz     short loc_18001597D
0x180015969  mov     rdx, [rbp+0B0h]
0x180015970  mov     ecx, [rbp+38h]
0x180015973  call    _XcptFilter_0
0x180015978  mov     [rbp+40h], eax
0x18001597b  jmp     short loc_180015984
0x18001597d  mov     dword ptr [rbp+40h], 0
0x180015984  mov     eax, [rbp+40h]
0x180015987  add     rsp, 20h
0x18001598b  pop     rbp
0x18001598c  retn
0x18001598e  push    rbp
0x180015990  sub     rsp, 20h
0x180015994  mov     rbp, rdx
0x180015997  mov     rax, [rcx]
0x18001599a  mov     edx, [rax]
0x18001599c  mov     [rbp+0B8h], rcx
0x1800159a3  mov     [rbp+48h], edx
0x1800159a6  mov     eax, [rbp+48h]
0x1800159a9  cmp     eax, 0E06D7363h
0x1800159ae  jnz     short loc_1800159C4
0x1800159b0  mov     rdx, [rbp+0B8h]
0x1800159b7  mov     ecx, [rbp+48h]
0x1800159ba  call    _XcptFilter_0
0x1800159bf  mov     [rbp+50h], eax
0x1800159c2  jmp     short loc_1800159CB
0x1800159c4  mov     dword ptr [rbp+50h], 0
0x1800159cb  mov     eax, [rbp+50h]
0x1800159ce  add     rsp, 20h
0x1800159d2  pop     rbp
0x1800159d3  retn
0x1800159d5  push    rbp
0x1800159d7  sub     rsp, 20h
0x1800159db  mov     rbp, rdx
0x1800159de  mov     rax, [rcx]
0x1800159e1  mov     edx, [rax]
0x1800159e3  mov     [rbp+0C0h], rcx
0x1800159ea  mov     [rbp+58h], edx
0x1800159ed  mov     eax, [rbp+58h]
0x1800159f0  cmp     eax, 0E06D7363h
0x1800159f5  jnz     short loc_180015A0B
0x1800159f7  mov     rdx, [rbp+0C0h]
0x1800159fe  mov     ecx, [rbp+58h]
0x180015a01  call    _XcptFilter_0
0x180015a06  mov     [rbp+60h], eax
0x180015a09  jmp     short loc_180015A12
0x180015a0b  mov     dword ptr [rbp+60h], 0
0x180015a12  mov     eax, [rbp+60h]
0x180015a15  add     rsp, 20h
0x180015a19  pop     rbp
0x180015a1a  retn
0x180015a1c  push    rbp
0x180015a1e  sub     rsp, 20h
0x180015a22  mov     rbp, rdx
0x180015a25  mov     rax, [rcx]
0x180015a28  mov     edx, [rax]
0x180015a2a  mov     [rbp+0C8h], rcx
0x180015a31  mov     [rbp+68h], edx
0x180015a34  mov     eax, [rbp+68h]
0x180015a37  cmp     eax, 0E06D7363h
0x180015a3c  jnz     short loc_180015A52
0x180015a3e  mov     rdx, [rbp+0C8h]
0x180015a45  mov     ecx, [rbp+68h]
0x180015a48  call    _XcptFilter_0
0x180015a4d  mov     [rbp+70h], eax
0x180015a50  jmp     short loc_180015A59
0x180015a52  mov     dword ptr [rbp+70h], 0
0x180015a59  mov     eax, [rbp+70h]
0x180015a5c  add     rsp, 20h
0x180015a60  pop     rbp
0x180015a61  retn
0x180015a63  push    rbp
0x180015a65  sub     rsp, 20h
0x180015a69  mov     rbp, rdx
0x180015a6c  mov     rax, [rcx]
0x180015a6f  mov     edx, [rax]
0x180015a71  mov     [rbp+0D0h], rcx
0x180015a78  mov     [rbp+78h], edx
0x180015a7b  mov     eax, [rbp+78h]
0x180015a7e  cmp     eax, 0E06D7363h
0x180015a83  jnz     short loc_180015A9C
0x180015a85  mov     rdx, [rbp+0D0h]
0x180015a8c  mov     ecx, [rbp+78h]
0x180015a8f  call    _XcptFilter_0
0x180015a94  mov     [rbp+80h], eax
0x180015a9a  jmp     short loc_180015AA6
0x180015a9c  mov     dword ptr [rbp+80h], 0
0x180015aa6  mov     eax, [rbp+80h]
0x180015aac  add     rsp, 20h
0x180015ab0  pop     rbp
0x180015ab1  retn
0x180015ab3  push    rbp
0x180015ab5  sub     rsp, 20h
0x180015ab9  mov     rbp, rdx
0x180015abc  mov     rax, [rcx]
0x180015abf  mov     edx, [rax]
0x180015ac1  mov     [rbp+0D8h], rcx
0x180015ac8  mov     [rbp+88h], edx
0x180015ace  mov     eax, [rbp+88h]
0x180015ad4  cmp     eax, 0E06D7363h
0x180015ad9  jnz     short loc_180015AF5
0x180015adb  mov     rdx, [rbp+0D8h]
0x180015ae2  mov     ecx, [rbp+88h]
0x180015ae8  call    _XcptFilter_0
0x180015aed  mov     [rbp+90h], eax
0x180015af3  jmp     short loc_180015AFF
0x180015af5  mov     dword ptr [rbp+90h], 0
0x180015aff  mov     eax, [rbp+90h]
0x180015b05  add     rsp, 20h
0x180015b09  pop     rbp
0x180015b0a  retn
0x180015b0c  push    rbp
0x180015b0e  sub     rsp, 20h
0x180015b12  mov     rbp, rdx
0x180015b15  mov     rax, [rcx]
0x180015b18  mov     edx, [rax]
0x180015b1a  mov     [rbp+0E0h], rcx
0x180015b21  mov     [rbp+98h], edx
0x180015b27  mov     eax, [rbp+98h]
0x180015b2d  cmp     eax, 0E06D7363h
0x180015b32  jnz     short loc_180015B4E
0x180015b34  mov     rdx, [rbp+0E0h]
0x180015b3b  mov     ecx, [rbp+98h]
0x180015b41  call    _XcptFilter_0
0x180015b46  mov     [rbp+0A0h], eax
0x180015b4c  jmp     short loc_180015B58
0x180015b4e  mov     dword ptr [rbp+0A0h], 0
0x180015b58  mov     eax, [rbp+0A0h]
0x180015b5e  add     rsp, 20h
0x180015b62  pop     rbp
0x180015b63  retn
0x180015b65  push    rbp
0x180015b67  sub     rsp, 20h
0x180015b6b  mov     rbp, rdx
0x180015b6e  cmp     dword ptr [rbp+118h], 1
0x180015b75  ja      short loc_180015B81
0x180015b77  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
