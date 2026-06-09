# __DllMainCRTStartup

- ea: `0x1800014b4`
- end: `0x1800016c0`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180001470`

## callees

- `0x180001240`
- `0x1800014b4`
- `0x180001c31`
- `0x180013670`
- `0x1800142b0`

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
  if ( (_DWORD)fdwReason || dword_18001B780 )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_18001B784 = 1;
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
            if ( dword_18001B784 )
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
0x1800014b4  mov     [rsp+lpvReserved], r8
0x1800014b9  mov     [rsp+arg_8], edx
0x1800014bd  mov     [rsp+arg_0], rcx
0x1800014c2  push    rbx
0x1800014c3  push    rsi
0x1800014c4  push    rdi
0x1800014c5  sub     rsp, 0F0h
0x1800014cc  mov     edi, edx
0x1800014ce  mov     rsi, rcx
0x1800014d1  mov     ebx, 1
0x1800014d6  cmp     edx, ebx
0x1800014d8  ja      short loc_1800014E0
0x1800014da  mov     cs:__native_dllmain_reason, edx
0x1800014e0  test    edx, edx
0x1800014e2  jnz     short loc_1800014F7
0x1800014e4  cmp     cs:dword_18001B780, edx
0x1800014ea  jnz     short loc_1800014F7
0x1800014ec  xor     ebx, ebx
0x1800014ee  mov     [rsp+108h+var_E8], ebx
0x1800014f2  jmp     loc_1800016A4
0x1800014f7  lea     eax, [rdx-1]
0x1800014fa  cmp     eax, 1
0x1800014fd  ja      loc_180001584
0x180001503  mov     rax, cs:_pRawDllMain
0x18000150a  test    rax, rax
0x18000150d  jz      short loc_180001545
0x18000150f  cmp     edx, 1
0x180001512  jnz     short loc_18000151A
0x180001514  mov     cs:dword_18001B784, edx
0x18000151a  mov     r8, [rsp+108h+lpvReserved]
0x180001522  call    cs:__guard_dispatch_icall_fptr
0x180001528  mov     ebx, eax
0x18000152a  mov     [rsp+108h+var_E8], eax
0x18000152e  jmp     short loc_180001545
0x180001530  xor     ebx, ebx
0x180001532  mov     [rsp+108h+var_E8], ebx
0x180001536  mov     edi, [rsp+108h+arg_8]
0x18000153d  mov     rsi, [rsp+108h+arg_0]
0x180001545  test    ebx, ebx
0x180001547  jz      loc_1800016A4
0x18000154d  mov     r8, [rsp+108h+lpvReserved]
0x180001555  mov     edx, edi
0x180001557  mov     rcx, rsi
0x18000155a  call    _CRT_INIT
0x18000155f  mov     ebx, eax
0x180001561  mov     [rsp+108h+var_E8], eax
0x180001565  jmp     short loc_18000157C
0x180001567  xor     ebx, ebx
0x180001569  mov     [rsp+108h+var_E8], ebx
0x18000156d  mov     edi, [rsp+108h+arg_8]
0x180001574  mov     rsi, [rsp+108h+arg_0]
0x18000157c  test    ebx, ebx
0x18000157e  jz      loc_1800016A4
0x180001584  mov     r8, [rsp+108h+lpvReserved]; lpvReserved
0x18000158c  mov     edx, edi; fdwReason
0x18000158e  mov     rcx, rsi; hinstDLL
0x180001591  call    DllMain
0x180001596  mov     ebx, eax
0x180001598  mov     [rsp+108h+var_E8], eax
0x18000159c  jmp     short loc_1800015B3
0x18000159e  xor     ebx, ebx
0x1800015a0  mov     [rsp+108h+var_E8], ebx
0x1800015a4  mov     edi, [rsp+108h+arg_8]
0x1800015ab  mov     rsi, [rsp+108h+arg_0]
0x1800015b3  cmp     edi, 1
0x1800015b6  jnz     short loc_18000162F
0x1800015b8  test    ebx, ebx
0x1800015ba  jnz     short loc_18000162F
0x1800015bc  xor     r8d, r8d; lpvReserved
0x1800015bf  xor     edx, edx; fdwReason
0x1800015c1  mov     rcx, rsi; hinstDLL
0x1800015c4  call    DllMain
0x1800015c9  jmp     short loc_1800015DE
0x1800015cb  mov     edi, [rsp+108h+arg_8]
0x1800015d2  mov     rsi, [rsp+108h+arg_0]
0x1800015da  mov     ebx, [rsp+108h+var_E8]
0x1800015de  xor     r8d, r8d
0x1800015e1  xor     edx, edx
0x1800015e3  mov     rcx, rsi
0x1800015e6  call    _CRT_INIT
0x1800015eb  jmp     short loc_180001600
0x1800015ed  mov     edi, [rsp+108h+arg_8]
0x1800015f4  mov     rsi, [rsp+108h+arg_0]
0x1800015fc  mov     ebx, [rsp+108h+var_E8]
0x180001600  mov     rax, cs:_pRawDllMain
0x180001607  test    rax, rax
0x18000160a  jz      short loc_18000162F
0x18000160c  xor     r8d, r8d
0x18000160f  xor     edx, edx
0x180001611  mov     rcx, rsi
0x180001614  call    cs:__guard_dispatch_icall_fptr
0x18000161a  jmp     short loc_18000162F
0x18000161c  mov     edi, [rsp+108h+arg_8]
0x180001623  mov     rsi, [rsp+108h+arg_0]
0x18000162b  mov     ebx, [rsp+108h+var_E8]
0x18000162f  test    edi, edi
0x180001631  jz      short loc_180001638
0x180001633  cmp     edi, 3
0x180001636  jnz     short loc_1800016A4
0x180001638  mov     r8, [rsp+108h+lpvReserved]
0x180001640  mov     edx, edi
0x180001642  mov     rcx, rsi
0x180001645  call    _CRT_INIT
0x18000164a  mov     ebx, eax
0x18000164c  mov     [rsp+108h+var_E8], eax
0x180001650  jmp     short loc_180001667
0x180001652  xor     ebx, ebx
0x180001654  mov     [rsp+108h+var_E8], ebx
0x180001658  mov     edi, [rsp+108h+arg_8]
0x18000165f  mov     rsi, [rsp+108h+arg_0]
0x180001667  mov     rax, cs:_pRawDllMain
0x18000166e  test    rax, rax
0x180001671  jz      short loc_1800016A4
0x180001673  cmp     cs:dword_18001B784, 0
0x18000167a  jz      short loc_1800016A4
0x18000167c  mov     r8, [rsp+108h+lpvReserved]
0x180001684  mov     edx, edi
0x180001686  mov     rcx, rsi
0x180001689  call    cs:__guard_dispatch_icall_fptr
0x18000168f  mov     ebx, eax
0x180001691  mov     [rsp+108h+var_E8], eax
0x180001695  jmp     short loc_1800016A4
0x180001697  xor     ebx, ebx
0x180001699  mov     [rsp+108h+var_E8], ebx
0x18000169d  mov     edi, [rsp+108h+arg_8]
0x1800016a4  cmp     edi, 1
0x1800016a7  ja      short loc_1800016B3
0x1800016a9  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x1800016b3  mov     eax, ebx
0x1800016b5  add     rsp, 0F0h
0x1800016bc  pop     rdi
0x1800016bd  pop     rsi
0x1800016be  pop     rbx
0x1800016bf  retn
0x180014380  push    rbp
0x180014382  sub     rsp, 20h
0x180014386  mov     rbp, rdx
0x180014389  mov     rax, [rcx]
0x18001438c  mov     edx, [rax]
0x18001438e  mov     [rbp+0A8h], rcx
0x180014395  mov     [rbp+28h], edx
0x180014398  mov     eax, [rbp+28h]
0x18001439b  cmp     eax, 0E06D7363h
0x1800143a0  jnz     short loc_1800143B6
0x1800143a2  mov     rdx, [rbp+0A8h]
0x1800143a9  mov     ecx, [rbp+28h]
0x1800143ac  call    _XcptFilter_0
0x1800143b1  mov     [rbp+30h], eax
0x1800143b4  jmp     short loc_1800143BD
0x1800143b6  mov     dword ptr [rbp+30h], 0
0x1800143bd  mov     eax, [rbp+30h]
0x1800143c0  add     rsp, 20h
0x1800143c4  pop     rbp
0x1800143c5  retn
0x1800143c7  push    rbp
0x1800143c9  sub     rsp, 20h
0x1800143cd  mov     rbp, rdx
0x1800143d0  mov     rax, [rcx]
0x1800143d3  mov     edx, [rax]
0x1800143d5  mov     [rbp+0B0h], rcx
0x1800143dc  mov     [rbp+38h], edx
0x1800143df  mov     eax, [rbp+38h]
0x1800143e2  cmp     eax, 0E06D7363h
0x1800143e7  jnz     short loc_1800143FD
0x1800143e9  mov     rdx, [rbp+0B0h]
0x1800143f0  mov     ecx, [rbp+38h]
0x1800143f3  call    _XcptFilter_0
0x1800143f8  mov     [rbp+40h], eax
0x1800143fb  jmp     short loc_180014404
0x1800143fd  mov     dword ptr [rbp+40h], 0
0x180014404  mov     eax, [rbp+40h]
0x180014407  add     rsp, 20h
0x18001440b  pop     rbp
0x18001440c  retn
0x18001440e  push    rbp
0x180014410  sub     rsp, 20h
0x180014414  mov     rbp, rdx
0x180014417  mov     rax, [rcx]
0x18001441a  mov     edx, [rax]
0x18001441c  mov     [rbp+0B8h], rcx
0x180014423  mov     [rbp+48h], edx
0x180014426  mov     eax, [rbp+48h]
0x180014429  cmp     eax, 0E06D7363h
0x18001442e  jnz     short loc_180014444
0x180014430  mov     rdx, [rbp+0B8h]
0x180014437  mov     ecx, [rbp+48h]
0x18001443a  call    _XcptFilter_0
0x18001443f  mov     [rbp+50h], eax
0x180014442  jmp     short loc_18001444B
0x180014444  mov     dword ptr [rbp+50h], 0
0x18001444b  mov     eax, [rbp+50h]
0x18001444e  add     rsp, 20h
0x180014452  pop     rbp
0x180014453  retn
0x180014455  push    rbp
0x180014457  sub     rsp, 20h
0x18001445b  mov     rbp, rdx
0x18001445e  mov     rax, [rcx]
0x180014461  mov     edx, [rax]
0x180014463  mov     [rbp+0C0h], rcx
0x18001446a  mov     [rbp+58h], edx
0x18001446d  mov     eax, [rbp+58h]
0x180014470  cmp     eax, 0E06D7363h
0x180014475  jnz     short loc_18001448B
0x180014477  mov     rdx, [rbp+0C0h]
0x18001447e  mov     ecx, [rbp+58h]
0x180014481  call    _XcptFilter_0
0x180014486  mov     [rbp+60h], eax
0x180014489  jmp     short loc_180014492
0x18001448b  mov     dword ptr [rbp+60h], 0
0x180014492  mov     eax, [rbp+60h]
0x180014495  add     rsp, 20h
0x180014499  pop     rbp
0x18001449a  retn
0x18001449c  push    rbp
0x18001449e  sub     rsp, 20h
0x1800144a2  mov     rbp, rdx
0x1800144a5  mov     rax, [rcx]
0x1800144a8  mov     edx, [rax]
0x1800144aa  mov     [rbp+0C8h], rcx
0x1800144b1  mov     [rbp+68h], edx
0x1800144b4  mov     eax, [rbp+68h]
0x1800144b7  cmp     eax, 0E06D7363h
0x1800144bc  jnz     short loc_1800144D2
0x1800144be  mov     rdx, [rbp+0C8h]
0x1800144c5  mov     ecx, [rbp+68h]
0x1800144c8  call    _XcptFilter_0
0x1800144cd  mov     [rbp+70h], eax
0x1800144d0  jmp     short loc_1800144D9
0x1800144d2  mov     dword ptr [rbp+70h], 0
0x1800144d9  mov     eax, [rbp+70h]
0x1800144dc  add     rsp, 20h
0x1800144e0  pop     rbp
0x1800144e1  retn
0x1800144e3  push    rbp
0x1800144e5  sub     rsp, 20h
0x1800144e9  mov     rbp, rdx
0x1800144ec  mov     rax, [rcx]
0x1800144ef  mov     edx, [rax]
0x1800144f1  mov     [rbp+0D0h], rcx
0x1800144f8  mov     [rbp+78h], edx
0x1800144fb  mov     eax, [rbp+78h]
0x1800144fe  cmp     eax, 0E06D7363h
0x180014503  jnz     short loc_18001451C
0x180014505  mov     rdx, [rbp+0D0h]
0x18001450c  mov     ecx, [rbp+78h]
0x18001450f  call    _XcptFilter_0
0x180014514  mov     [rbp+80h], eax
0x18001451a  jmp     short loc_180014526
0x18001451c  mov     dword ptr [rbp+80h], 0
0x180014526  mov     eax, [rbp+80h]
0x18001452c  add     rsp, 20h
0x180014530  pop     rbp
0x180014531  retn
0x180014533  push    rbp
0x180014535  sub     rsp, 20h
0x180014539  mov     rbp, rdx
0x18001453c  mov     rax, [rcx]
0x18001453f  mov     edx, [rax]
0x180014541  mov     [rbp+0D8h], rcx
0x180014548  mov     [rbp+88h], edx
0x18001454e  mov     eax, [rbp+88h]
0x180014554  cmp     eax, 0E06D7363h
0x180014559  jnz     short loc_180014575
0x18001455b  mov     rdx, [rbp+0D8h]
0x180014562  mov     ecx, [rbp+88h]
0x180014568  call    _XcptFilter_0
0x18001456d  mov     [rbp+90h], eax
0x180014573  jmp     short loc_18001457F
0x180014575  mov     dword ptr [rbp+90h], 0
0x18001457f  mov     eax, [rbp+90h]
0x180014585  add     rsp, 20h
0x180014589  pop     rbp
0x18001458a  retn
0x18001458c  push    rbp
0x18001458e  sub     rsp, 20h
0x180014592  mov     rbp, rdx
0x180014595  mov     rax, [rcx]
0x180014598  mov     edx, [rax]
0x18001459a  mov     [rbp+0E0h], rcx
0x1800145a1  mov     [rbp+98h], edx
0x1800145a7  mov     eax, [rbp+98h]
0x1800145ad  cmp     eax, 0E06D7363h
0x1800145b2  jnz     short loc_1800145CE
0x1800145b4  mov     rdx, [rbp+0E0h]
0x1800145bb  mov     ecx, [rbp+98h]
0x1800145c1  call    _XcptFilter_0
0x1800145c6  mov     [rbp+0A0h], eax
0x1800145cc  jmp     short loc_1800145D8
0x1800145ce  mov     dword ptr [rbp+0A0h], 0
0x1800145d8  mov     eax, [rbp+0A0h]
0x1800145de  add     rsp, 20h
0x1800145e2  pop     rbp
0x1800145e3  retn
0x1800145e5  push    rbp
0x1800145e7  sub     rsp, 20h
0x1800145eb  mov     rbp, rdx
0x1800145ee  cmp     dword ptr [rbp+118h], 1
0x1800145f5  ja      short loc_180014601
0x1800145f7  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
