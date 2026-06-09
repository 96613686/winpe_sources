# __DllMainCRTStartup

- ea: `0x1800015a4`
- end: `0x1800017b0`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180001560`

## callees

- `0x180001330`
- `0x1800015a4`
- `0x1800017c6`
- `0x180001998`
- `0x180002990`

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
  if ( (_DWORD)fdwReason || dword_180006240 )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_180006244 = 1;
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
            if ( dword_180006244 )
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
0x1800015a4  mov     [rsp+lpvReserved], r8
0x1800015a9  mov     [rsp+arg_8], edx
0x1800015ad  mov     [rsp+arg_0], rcx
0x1800015b2  push    rbx
0x1800015b3  push    rsi
0x1800015b4  push    rdi
0x1800015b5  sub     rsp, 0F0h
0x1800015bc  mov     edi, edx
0x1800015be  mov     rsi, rcx
0x1800015c1  mov     ebx, 1
0x1800015c6  cmp     edx, ebx
0x1800015c8  ja      short loc_1800015D0
0x1800015ca  mov     cs:__native_dllmain_reason, edx
0x1800015d0  test    edx, edx
0x1800015d2  jnz     short loc_1800015E7
0x1800015d4  cmp     cs:dword_180006240, edx
0x1800015da  jnz     short loc_1800015E7
0x1800015dc  xor     ebx, ebx
0x1800015de  mov     [rsp+108h+var_E8], ebx
0x1800015e2  jmp     loc_180001794
0x1800015e7  lea     eax, [rdx-1]
0x1800015ea  cmp     eax, 1
0x1800015ed  ja      loc_180001674
0x1800015f3  mov     rax, cs:_pRawDllMain
0x1800015fa  test    rax, rax
0x1800015fd  jz      short loc_180001635
0x1800015ff  cmp     edx, 1
0x180001602  jnz     short loc_18000160A
0x180001604  mov     cs:dword_180006244, edx
0x18000160a  mov     r8, [rsp+108h+lpvReserved]
0x180001612  call    cs:__guard_dispatch_icall_fptr
0x180001618  mov     ebx, eax
0x18000161a  mov     [rsp+108h+var_E8], eax
0x18000161e  jmp     short loc_180001635
0x180001620  xor     ebx, ebx
0x180001622  mov     [rsp+108h+var_E8], ebx
0x180001626  mov     edi, [rsp+108h+arg_8]
0x18000162d  mov     rsi, [rsp+108h+arg_0]
0x180001635  test    ebx, ebx
0x180001637  jz      loc_180001794
0x18000163d  mov     r8, [rsp+108h+lpvReserved]
0x180001645  mov     edx, edi
0x180001647  mov     rcx, rsi
0x18000164a  call    _CRT_INIT
0x18000164f  mov     ebx, eax
0x180001651  mov     [rsp+108h+var_E8], eax
0x180001655  jmp     short loc_18000166C
0x180001657  xor     ebx, ebx
0x180001659  mov     [rsp+108h+var_E8], ebx
0x18000165d  mov     edi, [rsp+108h+arg_8]
0x180001664  mov     rsi, [rsp+108h+arg_0]
0x18000166c  test    ebx, ebx
0x18000166e  jz      loc_180001794
0x180001674  mov     r8, [rsp+108h+lpvReserved]; lpvReserved
0x18000167c  mov     edx, edi; fdwReason
0x18000167e  mov     rcx, rsi; hinstDLL
0x180001681  call    DllMain
0x180001686  mov     ebx, eax
0x180001688  mov     [rsp+108h+var_E8], eax
0x18000168c  jmp     short loc_1800016A3
0x18000168e  xor     ebx, ebx
0x180001690  mov     [rsp+108h+var_E8], ebx
0x180001694  mov     edi, [rsp+108h+arg_8]
0x18000169b  mov     rsi, [rsp+108h+arg_0]
0x1800016a3  cmp     edi, 1
0x1800016a6  jnz     short loc_18000171F
0x1800016a8  test    ebx, ebx
0x1800016aa  jnz     short loc_18000171F
0x1800016ac  xor     r8d, r8d; lpvReserved
0x1800016af  xor     edx, edx; fdwReason
0x1800016b1  mov     rcx, rsi; hinstDLL
0x1800016b4  call    DllMain
0x1800016b9  jmp     short loc_1800016CE
0x1800016bb  mov     edi, [rsp+108h+arg_8]
0x1800016c2  mov     rsi, [rsp+108h+arg_0]
0x1800016ca  mov     ebx, [rsp+108h+var_E8]
0x1800016ce  xor     r8d, r8d
0x1800016d1  xor     edx, edx
0x1800016d3  mov     rcx, rsi
0x1800016d6  call    _CRT_INIT
0x1800016db  jmp     short loc_1800016F0
0x1800016dd  mov     edi, [rsp+108h+arg_8]
0x1800016e4  mov     rsi, [rsp+108h+arg_0]
0x1800016ec  mov     ebx, [rsp+108h+var_E8]
0x1800016f0  mov     rax, cs:_pRawDllMain
0x1800016f7  test    rax, rax
0x1800016fa  jz      short loc_18000171F
0x1800016fc  xor     r8d, r8d
0x1800016ff  xor     edx, edx
0x180001701  mov     rcx, rsi
0x180001704  call    cs:__guard_dispatch_icall_fptr
0x18000170a  jmp     short loc_18000171F
0x18000170c  mov     edi, [rsp+108h+arg_8]
0x180001713  mov     rsi, [rsp+108h+arg_0]
0x18000171b  mov     ebx, [rsp+108h+var_E8]
0x18000171f  test    edi, edi
0x180001721  jz      short loc_180001728
0x180001723  cmp     edi, 3
0x180001726  jnz     short loc_180001794
0x180001728  mov     r8, [rsp+108h+lpvReserved]
0x180001730  mov     edx, edi
0x180001732  mov     rcx, rsi
0x180001735  call    _CRT_INIT
0x18000173a  mov     ebx, eax
0x18000173c  mov     [rsp+108h+var_E8], eax
0x180001740  jmp     short loc_180001757
0x180001742  xor     ebx, ebx
0x180001744  mov     [rsp+108h+var_E8], ebx
0x180001748  mov     edi, [rsp+108h+arg_8]
0x18000174f  mov     rsi, [rsp+108h+arg_0]
0x180001757  mov     rax, cs:_pRawDllMain
0x18000175e  test    rax, rax
0x180001761  jz      short loc_180001794
0x180001763  cmp     cs:dword_180006244, 0
0x18000176a  jz      short loc_180001794
0x18000176c  mov     r8, [rsp+108h+lpvReserved]
0x180001774  mov     edx, edi
0x180001776  mov     rcx, rsi
0x180001779  call    cs:__guard_dispatch_icall_fptr
0x18000177f  mov     ebx, eax
0x180001781  mov     [rsp+108h+var_E8], eax
0x180001785  jmp     short loc_180001794
0x180001787  xor     ebx, ebx
0x180001789  mov     [rsp+108h+var_E8], ebx
0x18000178d  mov     edi, [rsp+108h+arg_8]
0x180001794  cmp     edi, 1
0x180001797  ja      short loc_1800017A3
0x180001799  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x1800017a3  mov     eax, ebx
0x1800017a5  add     rsp, 0F0h
0x1800017ac  pop     rdi
0x1800017ad  pop     rsi
0x1800017ae  pop     rbx
0x1800017af  retn
0x180002a00  push    rbp
0x180002a02  sub     rsp, 20h
0x180002a06  mov     rbp, rdx
0x180002a09  mov     rax, [rcx]
0x180002a0c  mov     edx, [rax]
0x180002a0e  mov     [rbp+0A8h], rcx
0x180002a15  mov     [rbp+28h], edx
0x180002a18  mov     eax, [rbp+28h]
0x180002a1b  cmp     eax, 0E06D7363h
0x180002a20  jnz     short loc_180002A36
0x180002a22  mov     rdx, [rbp+0A8h]
0x180002a29  mov     ecx, [rbp+28h]
0x180002a2c  call    _XcptFilter_0
0x180002a31  mov     [rbp+30h], eax
0x180002a34  jmp     short loc_180002A3D
0x180002a36  mov     dword ptr [rbp+30h], 0
0x180002a3d  mov     eax, [rbp+30h]
0x180002a40  add     rsp, 20h
0x180002a44  pop     rbp
0x180002a45  retn
0x180002a47  push    rbp
0x180002a49  sub     rsp, 20h
0x180002a4d  mov     rbp, rdx
0x180002a50  mov     rax, [rcx]
0x180002a53  mov     edx, [rax]
0x180002a55  mov     [rbp+0B0h], rcx
0x180002a5c  mov     [rbp+38h], edx
0x180002a5f  mov     eax, [rbp+38h]
0x180002a62  cmp     eax, 0E06D7363h
0x180002a67  jnz     short loc_180002A7D
0x180002a69  mov     rdx, [rbp+0B0h]
0x180002a70  mov     ecx, [rbp+38h]
0x180002a73  call    _XcptFilter_0
0x180002a78  mov     [rbp+40h], eax
0x180002a7b  jmp     short loc_180002A84
0x180002a7d  mov     dword ptr [rbp+40h], 0
0x180002a84  mov     eax, [rbp+40h]
0x180002a87  add     rsp, 20h
0x180002a8b  pop     rbp
0x180002a8c  retn
0x180002a8e  push    rbp
0x180002a90  sub     rsp, 20h
0x180002a94  mov     rbp, rdx
0x180002a97  mov     rax, [rcx]
0x180002a9a  mov     edx, [rax]
0x180002a9c  mov     [rbp+0B8h], rcx
0x180002aa3  mov     [rbp+48h], edx
0x180002aa6  mov     eax, [rbp+48h]
0x180002aa9  cmp     eax, 0E06D7363h
0x180002aae  jnz     short loc_180002AC4
0x180002ab0  mov     rdx, [rbp+0B8h]
0x180002ab7  mov     ecx, [rbp+48h]
0x180002aba  call    _XcptFilter_0
0x180002abf  mov     [rbp+50h], eax
0x180002ac2  jmp     short loc_180002ACB
0x180002ac4  mov     dword ptr [rbp+50h], 0
0x180002acb  mov     eax, [rbp+50h]
0x180002ace  add     rsp, 20h
0x180002ad2  pop     rbp
0x180002ad3  retn
0x180002ad5  push    rbp
0x180002ad7  sub     rsp, 20h
0x180002adb  mov     rbp, rdx
0x180002ade  mov     rax, [rcx]
0x180002ae1  mov     edx, [rax]
0x180002ae3  mov     [rbp+0C0h], rcx
0x180002aea  mov     [rbp+58h], edx
0x180002aed  mov     eax, [rbp+58h]
0x180002af0  cmp     eax, 0E06D7363h
0x180002af5  jnz     short loc_180002B0B
0x180002af7  mov     rdx, [rbp+0C0h]
0x180002afe  mov     ecx, [rbp+58h]
0x180002b01  call    _XcptFilter_0
0x180002b06  mov     [rbp+60h], eax
0x180002b09  jmp     short loc_180002B12
0x180002b0b  mov     dword ptr [rbp+60h], 0
0x180002b12  mov     eax, [rbp+60h]
0x180002b15  add     rsp, 20h
0x180002b19  pop     rbp
0x180002b1a  retn
0x180002b1c  push    rbp
0x180002b1e  sub     rsp, 20h
0x180002b22  mov     rbp, rdx
0x180002b25  mov     rax, [rcx]
0x180002b28  mov     edx, [rax]
0x180002b2a  mov     [rbp+0C8h], rcx
0x180002b31  mov     [rbp+68h], edx
0x180002b34  mov     eax, [rbp+68h]
0x180002b37  cmp     eax, 0E06D7363h
0x180002b3c  jnz     short loc_180002B52
0x180002b3e  mov     rdx, [rbp+0C8h]
0x180002b45  mov     ecx, [rbp+68h]
0x180002b48  call    _XcptFilter_0
0x180002b4d  mov     [rbp+70h], eax
0x180002b50  jmp     short loc_180002B59
0x180002b52  mov     dword ptr [rbp+70h], 0
0x180002b59  mov     eax, [rbp+70h]
0x180002b5c  add     rsp, 20h
0x180002b60  pop     rbp
0x180002b61  retn
0x180002b63  push    rbp
0x180002b65  sub     rsp, 20h
0x180002b69  mov     rbp, rdx
0x180002b6c  mov     rax, [rcx]
0x180002b6f  mov     edx, [rax]
0x180002b71  mov     [rbp+0D0h], rcx
0x180002b78  mov     [rbp+78h], edx
0x180002b7b  mov     eax, [rbp+78h]
0x180002b7e  cmp     eax, 0E06D7363h
0x180002b83  jnz     short loc_180002B9C
0x180002b85  mov     rdx, [rbp+0D0h]
0x180002b8c  mov     ecx, [rbp+78h]
0x180002b8f  call    _XcptFilter_0
0x180002b94  mov     [rbp+80h], eax
0x180002b9a  jmp     short loc_180002BA6
0x180002b9c  mov     dword ptr [rbp+80h], 0
0x180002ba6  mov     eax, [rbp+80h]
0x180002bac  add     rsp, 20h
0x180002bb0  pop     rbp
0x180002bb1  retn
0x180002bb3  push    rbp
0x180002bb5  sub     rsp, 20h
0x180002bb9  mov     rbp, rdx
0x180002bbc  mov     rax, [rcx]
0x180002bbf  mov     edx, [rax]
0x180002bc1  mov     [rbp+0D8h], rcx
0x180002bc8  mov     [rbp+88h], edx
0x180002bce  mov     eax, [rbp+88h]
0x180002bd4  cmp     eax, 0E06D7363h
0x180002bd9  jnz     short loc_180002BF5
0x180002bdb  mov     rdx, [rbp+0D8h]
0x180002be2  mov     ecx, [rbp+88h]
0x180002be8  call    _XcptFilter_0
0x180002bed  mov     [rbp+90h], eax
0x180002bf3  jmp     short loc_180002BFF
0x180002bf5  mov     dword ptr [rbp+90h], 0
0x180002bff  mov     eax, [rbp+90h]
0x180002c05  add     rsp, 20h
0x180002c09  pop     rbp
0x180002c0a  retn
0x180002c0c  push    rbp
0x180002c0e  sub     rsp, 20h
0x180002c12  mov     rbp, rdx
0x180002c15  mov     rax, [rcx]
0x180002c18  mov     edx, [rax]
0x180002c1a  mov     [rbp+0E0h], rcx
0x180002c21  mov     [rbp+98h], edx
0x180002c27  mov     eax, [rbp+98h]
0x180002c2d  cmp     eax, 0E06D7363h
0x180002c32  jnz     short loc_180002C4E
0x180002c34  mov     rdx, [rbp+0E0h]
0x180002c3b  mov     ecx, [rbp+98h]
0x180002c41  call    _XcptFilter_0
0x180002c46  mov     [rbp+0A0h], eax
0x180002c4c  jmp     short loc_180002C58
0x180002c4e  mov     dword ptr [rbp+0A0h], 0
0x180002c58  mov     eax, [rbp+0A0h]
0x180002c5e  add     rsp, 20h
0x180002c62  pop     rbp
0x180002c63  retn
0x180002c65  push    rbp
0x180002c67  sub     rsp, 20h
0x180002c6b  mov     rbp, rdx
0x180002c6e  cmp     dword ptr [rbp+118h], 1
0x180002c75  ja      short loc_180002C81
0x180002c77  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
