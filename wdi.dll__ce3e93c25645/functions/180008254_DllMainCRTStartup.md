# __DllMainCRTStartup

- ea: `0x180008254`
- end: `0x180008460`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, __int64 fdwReason, void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180008210`

## callees

- `0x1800030c0`
- `0x180007fe0`
- `0x180008254`
- `0x18000848a`
- `0x18000f230`

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
  if ( (_DWORD)fdwReason || dword_1800170A0 )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_1800170A4 = 1;
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
            if ( dword_1800170A4 )
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
0x180008254  mov     [rsp+lpvReserved], r8
0x180008259  mov     [rsp+arg_8], edx
0x18000825d  mov     [rsp+arg_0], rcx
0x180008262  push    rbx
0x180008263  push    rsi
0x180008264  push    rdi
0x180008265  sub     rsp, 0F0h
0x18000826c  mov     edi, edx
0x18000826e  mov     rsi, rcx
0x180008271  mov     ebx, 1
0x180008276  cmp     edx, ebx
0x180008278  ja      short loc_180008280
0x18000827a  mov     cs:__native_dllmain_reason, edx
0x180008280  test    edx, edx
0x180008282  jnz     short loc_180008297
0x180008284  cmp     cs:dword_1800170A0, edx
0x18000828a  jnz     short loc_180008297
0x18000828c  xor     ebx, ebx
0x18000828e  mov     [rsp+108h+var_E8], ebx
0x180008292  jmp     loc_180008444
0x180008297  lea     eax, [rdx-1]
0x18000829a  cmp     eax, 1
0x18000829d  ja      loc_180008324
0x1800082a3  mov     rax, cs:_pRawDllMain
0x1800082aa  test    rax, rax
0x1800082ad  jz      short loc_1800082E5
0x1800082af  cmp     edx, 1
0x1800082b2  jnz     short loc_1800082BA
0x1800082b4  mov     cs:dword_1800170A4, edx
0x1800082ba  mov     r8, [rsp+108h+lpvReserved]
0x1800082c2  call    cs:__guard_dispatch_icall_fptr
0x1800082c8  mov     ebx, eax
0x1800082ca  mov     [rsp+108h+var_E8], eax
0x1800082ce  jmp     short loc_1800082E5
0x1800082d0  xor     ebx, ebx
0x1800082d2  mov     [rsp+108h+var_E8], ebx
0x1800082d6  mov     edi, [rsp+108h+arg_8]
0x1800082dd  mov     rsi, [rsp+108h+arg_0]
0x1800082e5  test    ebx, ebx
0x1800082e7  jz      loc_180008444
0x1800082ed  mov     r8, [rsp+108h+lpvReserved]
0x1800082f5  mov     edx, edi
0x1800082f7  mov     rcx, rsi
0x1800082fa  call    _CRT_INIT
0x1800082ff  mov     ebx, eax
0x180008301  mov     [rsp+108h+var_E8], eax
0x180008305  jmp     short loc_18000831C
0x180008307  xor     ebx, ebx
0x180008309  mov     [rsp+108h+var_E8], ebx
0x18000830d  mov     edi, [rsp+108h+arg_8]
0x180008314  mov     rsi, [rsp+108h+arg_0]
0x18000831c  test    ebx, ebx
0x18000831e  jz      loc_180008444
0x180008324  mov     r8, [rsp+108h+lpvReserved]; lpvReserved
0x18000832c  mov     edx, edi; fdwReason
0x18000832e  mov     rcx, rsi; hinstDLL
0x180008331  call    DllMain
0x180008336  mov     ebx, eax
0x180008338  mov     [rsp+108h+var_E8], eax
0x18000833c  jmp     short loc_180008353
0x18000833e  xor     ebx, ebx
0x180008340  mov     [rsp+108h+var_E8], ebx
0x180008344  mov     edi, [rsp+108h+arg_8]
0x18000834b  mov     rsi, [rsp+108h+arg_0]
0x180008353  cmp     edi, 1
0x180008356  jnz     short loc_1800083CF
0x180008358  test    ebx, ebx
0x18000835a  jnz     short loc_1800083CF
0x18000835c  xor     r8d, r8d; lpvReserved
0x18000835f  xor     edx, edx; fdwReason
0x180008361  mov     rcx, rsi; hinstDLL
0x180008364  call    DllMain
0x180008369  jmp     short loc_18000837E
0x18000836b  mov     edi, [rsp+108h+arg_8]
0x180008372  mov     rsi, [rsp+108h+arg_0]
0x18000837a  mov     ebx, [rsp+108h+var_E8]
0x18000837e  xor     r8d, r8d
0x180008381  xor     edx, edx
0x180008383  mov     rcx, rsi
0x180008386  call    _CRT_INIT
0x18000838b  jmp     short loc_1800083A0
0x18000838d  mov     edi, [rsp+108h+arg_8]
0x180008394  mov     rsi, [rsp+108h+arg_0]
0x18000839c  mov     ebx, [rsp+108h+var_E8]
0x1800083a0  mov     rax, cs:_pRawDllMain
0x1800083a7  test    rax, rax
0x1800083aa  jz      short loc_1800083CF
0x1800083ac  xor     r8d, r8d
0x1800083af  xor     edx, edx
0x1800083b1  mov     rcx, rsi
0x1800083b4  call    cs:__guard_dispatch_icall_fptr
0x1800083ba  jmp     short loc_1800083CF
0x1800083bc  mov     edi, [rsp+108h+arg_8]
0x1800083c3  mov     rsi, [rsp+108h+arg_0]
0x1800083cb  mov     ebx, [rsp+108h+var_E8]
0x1800083cf  test    edi, edi
0x1800083d1  jz      short loc_1800083D8
0x1800083d3  cmp     edi, 3
0x1800083d6  jnz     short loc_180008444
0x1800083d8  mov     r8, [rsp+108h+lpvReserved]
0x1800083e0  mov     edx, edi
0x1800083e2  mov     rcx, rsi
0x1800083e5  call    _CRT_INIT
0x1800083ea  mov     ebx, eax
0x1800083ec  mov     [rsp+108h+var_E8], eax
0x1800083f0  jmp     short loc_180008407
0x1800083f2  xor     ebx, ebx
0x1800083f4  mov     [rsp+108h+var_E8], ebx
0x1800083f8  mov     edi, [rsp+108h+arg_8]
0x1800083ff  mov     rsi, [rsp+108h+arg_0]
0x180008407  mov     rax, cs:_pRawDllMain
0x18000840e  test    rax, rax
0x180008411  jz      short loc_180008444
0x180008413  cmp     cs:dword_1800170A4, 0
0x18000841a  jz      short loc_180008444
0x18000841c  mov     r8, [rsp+108h+lpvReserved]
0x180008424  mov     edx, edi
0x180008426  mov     rcx, rsi
0x180008429  call    cs:__guard_dispatch_icall_fptr
0x18000842f  mov     ebx, eax
0x180008431  mov     [rsp+108h+var_E8], eax
0x180008435  jmp     short loc_180008444
0x180008437  xor     ebx, ebx
0x180008439  mov     [rsp+108h+var_E8], ebx
0x18000843d  mov     edi, [rsp+108h+arg_8]
0x180008444  cmp     edi, 1
0x180008447  ja      short loc_180008453
0x180008449  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x180008453  mov     eax, ebx
0x180008455  add     rsp, 0F0h
0x18000845c  pop     rdi
0x18000845d  pop     rsi
0x18000845e  pop     rbx
0x18000845f  retn
0x18000f2a0  push    rbp
0x18000f2a2  sub     rsp, 20h
0x18000f2a6  mov     rbp, rdx
0x18000f2a9  mov     rax, [rcx]
0x18000f2ac  mov     edx, [rax]
0x18000f2ae  mov     [rbp+0A8h], rcx
0x18000f2b5  mov     [rbp+28h], edx
0x18000f2b8  mov     eax, [rbp+28h]
0x18000f2bb  cmp     eax, 0E06D7363h
0x18000f2c0  jnz     short loc_18000F2D6
0x18000f2c2  mov     rdx, [rbp+0A8h]
0x18000f2c9  mov     ecx, [rbp+28h]
0x18000f2cc  call    _XcptFilter_0
0x18000f2d1  mov     [rbp+30h], eax
0x18000f2d4  jmp     short loc_18000F2DD
0x18000f2d6  mov     dword ptr [rbp+30h], 0
0x18000f2dd  mov     eax, [rbp+30h]
0x18000f2e0  add     rsp, 20h
0x18000f2e4  pop     rbp
0x18000f2e5  retn
0x18000f2e7  push    rbp
0x18000f2e9  sub     rsp, 20h
0x18000f2ed  mov     rbp, rdx
0x18000f2f0  mov     rax, [rcx]
0x18000f2f3  mov     edx, [rax]
0x18000f2f5  mov     [rbp+0B0h], rcx
0x18000f2fc  mov     [rbp+38h], edx
0x18000f2ff  mov     eax, [rbp+38h]
0x18000f302  cmp     eax, 0E06D7363h
0x18000f307  jnz     short loc_18000F31D
0x18000f309  mov     rdx, [rbp+0B0h]
0x18000f310  mov     ecx, [rbp+38h]
0x18000f313  call    _XcptFilter_0
0x18000f318  mov     [rbp+40h], eax
0x18000f31b  jmp     short loc_18000F324
0x18000f31d  mov     dword ptr [rbp+40h], 0
0x18000f324  mov     eax, [rbp+40h]
0x18000f327  add     rsp, 20h
0x18000f32b  pop     rbp
0x18000f32c  retn
0x18000f32e  push    rbp
0x18000f330  sub     rsp, 20h
0x18000f334  mov     rbp, rdx
0x18000f337  mov     rax, [rcx]
0x18000f33a  mov     edx, [rax]
0x18000f33c  mov     [rbp+0B8h], rcx
0x18000f343  mov     [rbp+48h], edx
0x18000f346  mov     eax, [rbp+48h]
0x18000f349  cmp     eax, 0E06D7363h
0x18000f34e  jnz     short loc_18000F364
0x18000f350  mov     rdx, [rbp+0B8h]
0x18000f357  mov     ecx, [rbp+48h]
0x18000f35a  call    _XcptFilter_0
0x18000f35f  mov     [rbp+50h], eax
0x18000f362  jmp     short loc_18000F36B
0x18000f364  mov     dword ptr [rbp+50h], 0
0x18000f36b  mov     eax, [rbp+50h]
0x18000f36e  add     rsp, 20h
0x18000f372  pop     rbp
0x18000f373  retn
0x18000f375  push    rbp
0x18000f377  sub     rsp, 20h
0x18000f37b  mov     rbp, rdx
0x18000f37e  mov     rax, [rcx]
0x18000f381  mov     edx, [rax]
0x18000f383  mov     [rbp+0C0h], rcx
0x18000f38a  mov     [rbp+58h], edx
0x18000f38d  mov     eax, [rbp+58h]
0x18000f390  cmp     eax, 0E06D7363h
0x18000f395  jnz     short loc_18000F3AB
0x18000f397  mov     rdx, [rbp+0C0h]
0x18000f39e  mov     ecx, [rbp+58h]
0x18000f3a1  call    _XcptFilter_0
0x18000f3a6  mov     [rbp+60h], eax
0x18000f3a9  jmp     short loc_18000F3B2
0x18000f3ab  mov     dword ptr [rbp+60h], 0
0x18000f3b2  mov     eax, [rbp+60h]
0x18000f3b5  add     rsp, 20h
0x18000f3b9  pop     rbp
0x18000f3ba  retn
0x18000f3bc  push    rbp
0x18000f3be  sub     rsp, 20h
0x18000f3c2  mov     rbp, rdx
0x18000f3c5  mov     rax, [rcx]
0x18000f3c8  mov     edx, [rax]
0x18000f3ca  mov     [rbp+0C8h], rcx
0x18000f3d1  mov     [rbp+68h], edx
0x18000f3d4  mov     eax, [rbp+68h]
0x18000f3d7  cmp     eax, 0E06D7363h
0x18000f3dc  jnz     short loc_18000F3F2
0x18000f3de  mov     rdx, [rbp+0C8h]
0x18000f3e5  mov     ecx, [rbp+68h]
0x18000f3e8  call    _XcptFilter_0
0x18000f3ed  mov     [rbp+70h], eax
0x18000f3f0  jmp     short loc_18000F3F9
0x18000f3f2  mov     dword ptr [rbp+70h], 0
0x18000f3f9  mov     eax, [rbp+70h]
0x18000f3fc  add     rsp, 20h
0x18000f400  pop     rbp
0x18000f401  retn
0x18000f403  push    rbp
0x18000f405  sub     rsp, 20h
0x18000f409  mov     rbp, rdx
0x18000f40c  mov     rax, [rcx]
0x18000f40f  mov     edx, [rax]
0x18000f411  mov     [rbp+0D0h], rcx
0x18000f418  mov     [rbp+78h], edx
0x18000f41b  mov     eax, [rbp+78h]
0x18000f41e  cmp     eax, 0E06D7363h
0x18000f423  jnz     short loc_18000F43C
0x18000f425  mov     rdx, [rbp+0D0h]
0x18000f42c  mov     ecx, [rbp+78h]
0x18000f42f  call    _XcptFilter_0
0x18000f434  mov     [rbp+80h], eax
0x18000f43a  jmp     short loc_18000F446
0x18000f43c  mov     dword ptr [rbp+80h], 0
0x18000f446  mov     eax, [rbp+80h]
0x18000f44c  add     rsp, 20h
0x18000f450  pop     rbp
0x18000f451  retn
0x18000f453  push    rbp
0x18000f455  sub     rsp, 20h
0x18000f459  mov     rbp, rdx
0x18000f45c  mov     rax, [rcx]
0x18000f45f  mov     edx, [rax]
0x18000f461  mov     [rbp+0D8h], rcx
0x18000f468  mov     [rbp+88h], edx
0x18000f46e  mov     eax, [rbp+88h]
0x18000f474  cmp     eax, 0E06D7363h
0x18000f479  jnz     short loc_18000F495
0x18000f47b  mov     rdx, [rbp+0D8h]
0x18000f482  mov     ecx, [rbp+88h]
0x18000f488  call    _XcptFilter_0
0x18000f48d  mov     [rbp+90h], eax
0x18000f493  jmp     short loc_18000F49F
0x18000f495  mov     dword ptr [rbp+90h], 0
0x18000f49f  mov     eax, [rbp+90h]
0x18000f4a5  add     rsp, 20h
0x18000f4a9  pop     rbp
0x18000f4aa  retn
0x18000f4ac  push    rbp
0x18000f4ae  sub     rsp, 20h
0x18000f4b2  mov     rbp, rdx
0x18000f4b5  mov     rax, [rcx]
0x18000f4b8  mov     edx, [rax]
0x18000f4ba  mov     [rbp+0E0h], rcx
0x18000f4c1  mov     [rbp+98h], edx
0x18000f4c7  mov     eax, [rbp+98h]
0x18000f4cd  cmp     eax, 0E06D7363h
0x18000f4d2  jnz     short loc_18000F4EE
0x18000f4d4  mov     rdx, [rbp+0E0h]
0x18000f4db  mov     ecx, [rbp+98h]
0x18000f4e1  call    _XcptFilter_0
0x18000f4e6  mov     [rbp+0A0h], eax
0x18000f4ec  jmp     short loc_18000F4F8
0x18000f4ee  mov     dword ptr [rbp+0A0h], 0
0x18000f4f8  mov     eax, [rbp+0A0h]
0x18000f4fe  add     rsp, 20h
0x18000f502  pop     rbp
0x18000f503  retn
0x18000f505  push    rbp
0x18000f507  sub     rsp, 20h
0x18000f50b  mov     rbp, rdx
0x18000f50e  cmp     dword ptr [rbp+118h], 1
0x18000f515  ja      short loc_18000F521
0x18000f517  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
