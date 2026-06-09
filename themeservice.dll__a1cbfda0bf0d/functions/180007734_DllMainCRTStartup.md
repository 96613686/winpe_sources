# __DllMainCRTStartup

- ea: `0x180007734`
- end: `0x180007940`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, __int64 fdwReason, void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1800076f0`

## callees

- `0x1800074c0`
- `0x180007734`
- `0x180007a1c`
- `0x18000a48c`
- `0x18000fa40`

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
  if ( (_DWORD)fdwReason || dword_1800161C0 )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_1800161C4 = 1;
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
            if ( dword_1800161C4 )
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
0x180007734  mov     [rsp+lpvReserved], r8
0x180007739  mov     [rsp+arg_8], edx
0x18000773d  mov     [rsp+arg_0], rcx
0x180007742  push    rbx
0x180007743  push    rsi
0x180007744  push    rdi
0x180007745  sub     rsp, 0F0h
0x18000774c  mov     edi, edx
0x18000774e  mov     rsi, rcx
0x180007751  mov     ebx, 1
0x180007756  cmp     edx, ebx
0x180007758  ja      short loc_180007760
0x18000775a  mov     cs:__native_dllmain_reason, edx
0x180007760  test    edx, edx
0x180007762  jnz     short loc_180007777
0x180007764  cmp     cs:dword_1800161C0, edx
0x18000776a  jnz     short loc_180007777
0x18000776c  xor     ebx, ebx
0x18000776e  mov     [rsp+108h+var_E8], ebx
0x180007772  jmp     loc_180007924
0x180007777  lea     eax, [rdx-1]
0x18000777a  cmp     eax, 1
0x18000777d  ja      loc_180007804
0x180007783  mov     rax, cs:_pRawDllMain
0x18000778a  test    rax, rax
0x18000778d  jz      short loc_1800077C5
0x18000778f  cmp     edx, 1
0x180007792  jnz     short loc_18000779A
0x180007794  mov     cs:dword_1800161C4, edx
0x18000779a  mov     r8, [rsp+108h+lpvReserved]
0x1800077a2  call    cs:__guard_dispatch_icall_fptr
0x1800077a8  mov     ebx, eax
0x1800077aa  mov     [rsp+108h+var_E8], eax
0x1800077ae  jmp     short loc_1800077C5
0x1800077b0  xor     ebx, ebx
0x1800077b2  mov     [rsp+108h+var_E8], ebx
0x1800077b6  mov     edi, [rsp+108h+arg_8]
0x1800077bd  mov     rsi, [rsp+108h+arg_0]
0x1800077c5  test    ebx, ebx
0x1800077c7  jz      loc_180007924
0x1800077cd  mov     r8, [rsp+108h+lpvReserved]
0x1800077d5  mov     edx, edi
0x1800077d7  mov     rcx, rsi
0x1800077da  call    _CRT_INIT
0x1800077df  mov     ebx, eax
0x1800077e1  mov     [rsp+108h+var_E8], eax
0x1800077e5  jmp     short loc_1800077FC
0x1800077e7  xor     ebx, ebx
0x1800077e9  mov     [rsp+108h+var_E8], ebx
0x1800077ed  mov     edi, [rsp+108h+arg_8]
0x1800077f4  mov     rsi, [rsp+108h+arg_0]
0x1800077fc  test    ebx, ebx
0x1800077fe  jz      loc_180007924
0x180007804  mov     r8, [rsp+108h+lpvReserved]; lpvReserved
0x18000780c  mov     edx, edi; fdwReason
0x18000780e  mov     rcx, rsi; hinstDLL
0x180007811  call    DllMain
0x180007816  mov     ebx, eax
0x180007818  mov     [rsp+108h+var_E8], eax
0x18000781c  jmp     short loc_180007833
0x18000781e  xor     ebx, ebx
0x180007820  mov     [rsp+108h+var_E8], ebx
0x180007824  mov     edi, [rsp+108h+arg_8]
0x18000782b  mov     rsi, [rsp+108h+arg_0]
0x180007833  cmp     edi, 1
0x180007836  jnz     short loc_1800078AF
0x180007838  test    ebx, ebx
0x18000783a  jnz     short loc_1800078AF
0x18000783c  xor     r8d, r8d; lpvReserved
0x18000783f  xor     edx, edx; fdwReason
0x180007841  mov     rcx, rsi; hinstDLL
0x180007844  call    DllMain
0x180007849  jmp     short loc_18000785E
0x18000784b  mov     edi, [rsp+108h+arg_8]
0x180007852  mov     rsi, [rsp+108h+arg_0]
0x18000785a  mov     ebx, [rsp+108h+var_E8]
0x18000785e  xor     r8d, r8d
0x180007861  xor     edx, edx
0x180007863  mov     rcx, rsi
0x180007866  call    _CRT_INIT
0x18000786b  jmp     short loc_180007880
0x18000786d  mov     edi, [rsp+108h+arg_8]
0x180007874  mov     rsi, [rsp+108h+arg_0]
0x18000787c  mov     ebx, [rsp+108h+var_E8]
0x180007880  mov     rax, cs:_pRawDllMain
0x180007887  test    rax, rax
0x18000788a  jz      short loc_1800078AF
0x18000788c  xor     r8d, r8d
0x18000788f  xor     edx, edx
0x180007891  mov     rcx, rsi
0x180007894  call    cs:__guard_dispatch_icall_fptr
0x18000789a  jmp     short loc_1800078AF
0x18000789c  mov     edi, [rsp+108h+arg_8]
0x1800078a3  mov     rsi, [rsp+108h+arg_0]
0x1800078ab  mov     ebx, [rsp+108h+var_E8]
0x1800078af  test    edi, edi
0x1800078b1  jz      short loc_1800078B8
0x1800078b3  cmp     edi, 3
0x1800078b6  jnz     short loc_180007924
0x1800078b8  mov     r8, [rsp+108h+lpvReserved]
0x1800078c0  mov     edx, edi
0x1800078c2  mov     rcx, rsi
0x1800078c5  call    _CRT_INIT
0x1800078ca  mov     ebx, eax
0x1800078cc  mov     [rsp+108h+var_E8], eax
0x1800078d0  jmp     short loc_1800078E7
0x1800078d2  xor     ebx, ebx
0x1800078d4  mov     [rsp+108h+var_E8], ebx
0x1800078d8  mov     edi, [rsp+108h+arg_8]
0x1800078df  mov     rsi, [rsp+108h+arg_0]
0x1800078e7  mov     rax, cs:_pRawDllMain
0x1800078ee  test    rax, rax
0x1800078f1  jz      short loc_180007924
0x1800078f3  cmp     cs:dword_1800161C4, 0
0x1800078fa  jz      short loc_180007924
0x1800078fc  mov     r8, [rsp+108h+lpvReserved]
0x180007904  mov     edx, edi
0x180007906  mov     rcx, rsi
0x180007909  call    cs:__guard_dispatch_icall_fptr
0x18000790f  mov     ebx, eax
0x180007911  mov     [rsp+108h+var_E8], eax
0x180007915  jmp     short loc_180007924
0x180007917  xor     ebx, ebx
0x180007919  mov     [rsp+108h+var_E8], ebx
0x18000791d  mov     edi, [rsp+108h+arg_8]
0x180007924  cmp     edi, 1
0x180007927  ja      short loc_180007933
0x180007929  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x180007933  mov     eax, ebx
0x180007935  add     rsp, 0F0h
0x18000793c  pop     rdi
0x18000793d  pop     rsi
0x18000793e  pop     rbx
0x18000793f  retn
0x18000fb3e  push    rbp
0x18000fb40  sub     rsp, 20h
0x18000fb44  mov     rbp, rdx
0x18000fb47  mov     rax, [rcx]
0x18000fb4a  mov     edx, [rax]
0x18000fb4c  mov     [rbp+0A8h], rcx
0x18000fb53  mov     [rbp+28h], edx
0x18000fb56  mov     eax, [rbp+28h]
0x18000fb59  cmp     eax, 0E06D7363h
0x18000fb5e  jnz     short loc_18000FB74
0x18000fb60  mov     rdx, [rbp+0A8h]
0x18000fb67  mov     ecx, [rbp+28h]
0x18000fb6a  call    _XcptFilter_0
0x18000fb6f  mov     [rbp+30h], eax
0x18000fb72  jmp     short loc_18000FB7B
0x18000fb74  mov     dword ptr [rbp+30h], 0
0x18000fb7b  mov     eax, [rbp+30h]
0x18000fb7e  add     rsp, 20h
0x18000fb82  pop     rbp
0x18000fb83  retn
0x18000fb85  push    rbp
0x18000fb87  sub     rsp, 20h
0x18000fb8b  mov     rbp, rdx
0x18000fb8e  mov     rax, [rcx]
0x18000fb91  mov     edx, [rax]
0x18000fb93  mov     [rbp+0B0h], rcx
0x18000fb9a  mov     [rbp+38h], edx
0x18000fb9d  mov     eax, [rbp+38h]
0x18000fba0  cmp     eax, 0E06D7363h
0x18000fba5  jnz     short loc_18000FBBB
0x18000fba7  mov     rdx, [rbp+0B0h]
0x18000fbae  mov     ecx, [rbp+38h]
0x18000fbb1  call    _XcptFilter_0
0x18000fbb6  mov     [rbp+40h], eax
0x18000fbb9  jmp     short loc_18000FBC2
0x18000fbbb  mov     dword ptr [rbp+40h], 0
0x18000fbc2  mov     eax, [rbp+40h]
0x18000fbc5  add     rsp, 20h
0x18000fbc9  pop     rbp
0x18000fbca  retn
0x18000fbcc  push    rbp
0x18000fbce  sub     rsp, 20h
0x18000fbd2  mov     rbp, rdx
0x18000fbd5  mov     rax, [rcx]
0x18000fbd8  mov     edx, [rax]
0x18000fbda  mov     [rbp+0B8h], rcx
0x18000fbe1  mov     [rbp+48h], edx
0x18000fbe4  mov     eax, [rbp+48h]
0x18000fbe7  cmp     eax, 0E06D7363h
0x18000fbec  jnz     short loc_18000FC02
0x18000fbee  mov     rdx, [rbp+0B8h]
0x18000fbf5  mov     ecx, [rbp+48h]
0x18000fbf8  call    _XcptFilter_0
0x18000fbfd  mov     [rbp+50h], eax
0x18000fc00  jmp     short loc_18000FC09
0x18000fc02  mov     dword ptr [rbp+50h], 0
0x18000fc09  mov     eax, [rbp+50h]
0x18000fc0c  add     rsp, 20h
0x18000fc10  pop     rbp
0x18000fc11  retn
0x18000fc13  push    rbp
0x18000fc15  sub     rsp, 20h
0x18000fc19  mov     rbp, rdx
0x18000fc1c  mov     rax, [rcx]
0x18000fc1f  mov     edx, [rax]
0x18000fc21  mov     [rbp+0C0h], rcx
0x18000fc28  mov     [rbp+58h], edx
0x18000fc2b  mov     eax, [rbp+58h]
0x18000fc2e  cmp     eax, 0E06D7363h
0x18000fc33  jnz     short loc_18000FC49
0x18000fc35  mov     rdx, [rbp+0C0h]
0x18000fc3c  mov     ecx, [rbp+58h]
0x18000fc3f  call    _XcptFilter_0
0x18000fc44  mov     [rbp+60h], eax
0x18000fc47  jmp     short loc_18000FC50
0x18000fc49  mov     dword ptr [rbp+60h], 0
0x18000fc50  mov     eax, [rbp+60h]
0x18000fc53  add     rsp, 20h
0x18000fc57  pop     rbp
0x18000fc58  retn
0x18000fc5a  push    rbp
0x18000fc5c  sub     rsp, 20h
0x18000fc60  mov     rbp, rdx
0x18000fc63  mov     rax, [rcx]
0x18000fc66  mov     edx, [rax]
0x18000fc68  mov     [rbp+0C8h], rcx
0x18000fc6f  mov     [rbp+68h], edx
0x18000fc72  mov     eax, [rbp+68h]
0x18000fc75  cmp     eax, 0E06D7363h
0x18000fc7a  jnz     short loc_18000FC90
0x18000fc7c  mov     rdx, [rbp+0C8h]
0x18000fc83  mov     ecx, [rbp+68h]
0x18000fc86  call    _XcptFilter_0
0x18000fc8b  mov     [rbp+70h], eax
0x18000fc8e  jmp     short loc_18000FC97
0x18000fc90  mov     dword ptr [rbp+70h], 0
0x18000fc97  mov     eax, [rbp+70h]
0x18000fc9a  add     rsp, 20h
0x18000fc9e  pop     rbp
0x18000fc9f  retn
0x18000fca1  push    rbp
0x18000fca3  sub     rsp, 20h
0x18000fca7  mov     rbp, rdx
0x18000fcaa  mov     rax, [rcx]
0x18000fcad  mov     edx, [rax]
0x18000fcaf  mov     [rbp+0D0h], rcx
0x18000fcb6  mov     [rbp+78h], edx
0x18000fcb9  mov     eax, [rbp+78h]
0x18000fcbc  cmp     eax, 0E06D7363h
0x18000fcc1  jnz     short loc_18000FCDA
0x18000fcc3  mov     rdx, [rbp+0D0h]
0x18000fcca  mov     ecx, [rbp+78h]
0x18000fccd  call    _XcptFilter_0
0x18000fcd2  mov     [rbp+80h], eax
0x18000fcd8  jmp     short loc_18000FCE4
0x18000fcda  mov     dword ptr [rbp+80h], 0
0x18000fce4  mov     eax, [rbp+80h]
0x18000fcea  add     rsp, 20h
0x18000fcee  pop     rbp
0x18000fcef  retn
0x18000fcf1  push    rbp
0x18000fcf3  sub     rsp, 20h
0x18000fcf7  mov     rbp, rdx
0x18000fcfa  mov     rax, [rcx]
0x18000fcfd  mov     edx, [rax]
0x18000fcff  mov     [rbp+0D8h], rcx
0x18000fd06  mov     [rbp+88h], edx
0x18000fd0c  mov     eax, [rbp+88h]
0x18000fd12  cmp     eax, 0E06D7363h
0x18000fd17  jnz     short loc_18000FD33
0x18000fd19  mov     rdx, [rbp+0D8h]
0x18000fd20  mov     ecx, [rbp+88h]
0x18000fd26  call    _XcptFilter_0
0x18000fd2b  mov     [rbp+90h], eax
0x18000fd31  jmp     short loc_18000FD3D
0x18000fd33  mov     dword ptr [rbp+90h], 0
0x18000fd3d  mov     eax, [rbp+90h]
0x18000fd43  add     rsp, 20h
0x18000fd47  pop     rbp
0x18000fd48  retn
0x18000fd4a  push    rbp
0x18000fd4c  sub     rsp, 20h
0x18000fd50  mov     rbp, rdx
0x18000fd53  mov     rax, [rcx]
0x18000fd56  mov     edx, [rax]
0x18000fd58  mov     [rbp+0E0h], rcx
0x18000fd5f  mov     [rbp+98h], edx
0x18000fd65  mov     eax, [rbp+98h]
0x18000fd6b  cmp     eax, 0E06D7363h
0x18000fd70  jnz     short loc_18000FD8C
0x18000fd72  mov     rdx, [rbp+0E0h]
0x18000fd79  mov     ecx, [rbp+98h]
0x18000fd7f  call    _XcptFilter_0
0x18000fd84  mov     [rbp+0A0h], eax
0x18000fd8a  jmp     short loc_18000FD96
0x18000fd8c  mov     dword ptr [rbp+0A0h], 0
0x18000fd96  mov     eax, [rbp+0A0h]
0x18000fd9c  add     rsp, 20h
0x18000fda0  pop     rbp
0x18000fda1  retn
0x18000fda3  push    rbp
0x18000fda5  sub     rsp, 20h
0x18000fda9  mov     rbp, rdx
0x18000fdac  cmp     dword ptr [rbp+118h], 1
0x18000fdb3  ja      short loc_18000FDBF
0x18000fdb5  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
