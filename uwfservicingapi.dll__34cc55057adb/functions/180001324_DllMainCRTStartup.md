# __DllMainCRTStartup

- ea: `0x180001324`
- end: `0x180001530`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, __int64 fdwReason, void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1800012e0`

## callees

- `0x1800010b0`
- `0x180001324`
- `0x18000155c`
- `0x180001738`
- `0x1800051e0`

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
  if ( (_DWORD)fdwReason || dword_18000C1A0 )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_18000C1A4 = 1;
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
            if ( dword_18000C1A4 )
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
0x180001324  mov     [rsp+lpvReserved], r8
0x180001329  mov     [rsp+arg_8], edx
0x18000132d  mov     [rsp+arg_0], rcx
0x180001332  push    rbx
0x180001333  push    rsi
0x180001334  push    rdi
0x180001335  sub     rsp, 0F0h
0x18000133c  mov     edi, edx
0x18000133e  mov     rsi, rcx
0x180001341  mov     ebx, 1
0x180001346  cmp     edx, ebx
0x180001348  ja      short loc_180001350
0x18000134a  mov     cs:__native_dllmain_reason, edx
0x180001350  test    edx, edx
0x180001352  jnz     short loc_180001367
0x180001354  cmp     cs:dword_18000C1A0, edx
0x18000135a  jnz     short loc_180001367
0x18000135c  xor     ebx, ebx
0x18000135e  mov     [rsp+108h+var_E8], ebx
0x180001362  jmp     loc_180001514
0x180001367  lea     eax, [rdx-1]
0x18000136a  cmp     eax, 1
0x18000136d  ja      loc_1800013F4
0x180001373  mov     rax, cs:_pRawDllMain
0x18000137a  test    rax, rax
0x18000137d  jz      short loc_1800013B5
0x18000137f  cmp     edx, 1
0x180001382  jnz     short loc_18000138A
0x180001384  mov     cs:dword_18000C1A4, edx
0x18000138a  mov     r8, [rsp+108h+lpvReserved]
0x180001392  call    cs:__guard_dispatch_icall_fptr
0x180001398  mov     ebx, eax
0x18000139a  mov     [rsp+108h+var_E8], eax
0x18000139e  jmp     short loc_1800013B5
0x1800013a0  xor     ebx, ebx
0x1800013a2  mov     [rsp+108h+var_E8], ebx
0x1800013a6  mov     edi, [rsp+108h+arg_8]
0x1800013ad  mov     rsi, [rsp+108h+arg_0]
0x1800013b5  test    ebx, ebx
0x1800013b7  jz      loc_180001514
0x1800013bd  mov     r8, [rsp+108h+lpvReserved]
0x1800013c5  mov     edx, edi
0x1800013c7  mov     rcx, rsi
0x1800013ca  call    _CRT_INIT
0x1800013cf  mov     ebx, eax
0x1800013d1  mov     [rsp+108h+var_E8], eax
0x1800013d5  jmp     short loc_1800013EC
0x1800013d7  xor     ebx, ebx
0x1800013d9  mov     [rsp+108h+var_E8], ebx
0x1800013dd  mov     edi, [rsp+108h+arg_8]
0x1800013e4  mov     rsi, [rsp+108h+arg_0]
0x1800013ec  test    ebx, ebx
0x1800013ee  jz      loc_180001514
0x1800013f4  mov     r8, [rsp+108h+lpvReserved]; lpvReserved
0x1800013fc  mov     edx, edi; fdwReason
0x1800013fe  mov     rcx, rsi; hinstDLL
0x180001401  call    DllMain
0x180001406  mov     ebx, eax
0x180001408  mov     [rsp+108h+var_E8], eax
0x18000140c  jmp     short loc_180001423
0x18000140e  xor     ebx, ebx
0x180001410  mov     [rsp+108h+var_E8], ebx
0x180001414  mov     edi, [rsp+108h+arg_8]
0x18000141b  mov     rsi, [rsp+108h+arg_0]
0x180001423  cmp     edi, 1
0x180001426  jnz     short loc_18000149F
0x180001428  test    ebx, ebx
0x18000142a  jnz     short loc_18000149F
0x18000142c  xor     r8d, r8d; lpvReserved
0x18000142f  xor     edx, edx; fdwReason
0x180001431  mov     rcx, rsi; hinstDLL
0x180001434  call    DllMain
0x180001439  jmp     short loc_18000144E
0x18000143b  mov     edi, [rsp+108h+arg_8]
0x180001442  mov     rsi, [rsp+108h+arg_0]
0x18000144a  mov     ebx, [rsp+108h+var_E8]
0x18000144e  xor     r8d, r8d
0x180001451  xor     edx, edx
0x180001453  mov     rcx, rsi
0x180001456  call    _CRT_INIT
0x18000145b  jmp     short loc_180001470
0x18000145d  mov     edi, [rsp+108h+arg_8]
0x180001464  mov     rsi, [rsp+108h+arg_0]
0x18000146c  mov     ebx, [rsp+108h+var_E8]
0x180001470  mov     rax, cs:_pRawDllMain
0x180001477  test    rax, rax
0x18000147a  jz      short loc_18000149F
0x18000147c  xor     r8d, r8d
0x18000147f  xor     edx, edx
0x180001481  mov     rcx, rsi
0x180001484  call    cs:__guard_dispatch_icall_fptr
0x18000148a  jmp     short loc_18000149F
0x18000148c  mov     edi, [rsp+108h+arg_8]
0x180001493  mov     rsi, [rsp+108h+arg_0]
0x18000149b  mov     ebx, [rsp+108h+var_E8]
0x18000149f  test    edi, edi
0x1800014a1  jz      short loc_1800014A8
0x1800014a3  cmp     edi, 3
0x1800014a6  jnz     short loc_180001514
0x1800014a8  mov     r8, [rsp+108h+lpvReserved]
0x1800014b0  mov     edx, edi
0x1800014b2  mov     rcx, rsi
0x1800014b5  call    _CRT_INIT
0x1800014ba  mov     ebx, eax
0x1800014bc  mov     [rsp+108h+var_E8], eax
0x1800014c0  jmp     short loc_1800014D7
0x1800014c2  xor     ebx, ebx
0x1800014c4  mov     [rsp+108h+var_E8], ebx
0x1800014c8  mov     edi, [rsp+108h+arg_8]
0x1800014cf  mov     rsi, [rsp+108h+arg_0]
0x1800014d7  mov     rax, cs:_pRawDllMain
0x1800014de  test    rax, rax
0x1800014e1  jz      short loc_180001514
0x1800014e3  cmp     cs:dword_18000C1A4, 0
0x1800014ea  jz      short loc_180001514
0x1800014ec  mov     r8, [rsp+108h+lpvReserved]
0x1800014f4  mov     edx, edi
0x1800014f6  mov     rcx, rsi
0x1800014f9  call    cs:__guard_dispatch_icall_fptr
0x1800014ff  mov     ebx, eax
0x180001501  mov     [rsp+108h+var_E8], eax
0x180001505  jmp     short loc_180001514
0x180001507  xor     ebx, ebx
0x180001509  mov     [rsp+108h+var_E8], ebx
0x18000150d  mov     edi, [rsp+108h+arg_8]
0x180001514  cmp     edi, 1
0x180001517  ja      short loc_180001523
0x180001519  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x180001523  mov     eax, ebx
0x180001525  add     rsp, 0F0h
0x18000152c  pop     rdi
0x18000152d  pop     rsi
0x18000152e  pop     rbx
0x18000152f  retn
0x180005250  push    rbp
0x180005252  sub     rsp, 20h
0x180005256  mov     rbp, rdx
0x180005259  mov     rax, [rcx]
0x18000525c  mov     edx, [rax]
0x18000525e  mov     [rbp+0A8h], rcx
0x180005265  mov     [rbp+28h], edx
0x180005268  mov     eax, [rbp+28h]
0x18000526b  cmp     eax, 0E06D7363h
0x180005270  jnz     short loc_180005286
0x180005272  mov     rdx, [rbp+0A8h]
0x180005279  mov     ecx, [rbp+28h]
0x18000527c  call    _XcptFilter_0
0x180005281  mov     [rbp+30h], eax
0x180005284  jmp     short loc_18000528D
0x180005286  mov     dword ptr [rbp+30h], 0
0x18000528d  mov     eax, [rbp+30h]
0x180005290  add     rsp, 20h
0x180005294  pop     rbp
0x180005295  retn
0x180005297  push    rbp
0x180005299  sub     rsp, 20h
0x18000529d  mov     rbp, rdx
0x1800052a0  mov     rax, [rcx]
0x1800052a3  mov     edx, [rax]
0x1800052a5  mov     [rbp+0B0h], rcx
0x1800052ac  mov     [rbp+38h], edx
0x1800052af  mov     eax, [rbp+38h]
0x1800052b2  cmp     eax, 0E06D7363h
0x1800052b7  jnz     short loc_1800052CD
0x1800052b9  mov     rdx, [rbp+0B0h]
0x1800052c0  mov     ecx, [rbp+38h]
0x1800052c3  call    _XcptFilter_0
0x1800052c8  mov     [rbp+40h], eax
0x1800052cb  jmp     short loc_1800052D4
0x1800052cd  mov     dword ptr [rbp+40h], 0
0x1800052d4  mov     eax, [rbp+40h]
0x1800052d7  add     rsp, 20h
0x1800052db  pop     rbp
0x1800052dc  retn
0x1800052de  push    rbp
0x1800052e0  sub     rsp, 20h
0x1800052e4  mov     rbp, rdx
0x1800052e7  mov     rax, [rcx]
0x1800052ea  mov     edx, [rax]
0x1800052ec  mov     [rbp+0B8h], rcx
0x1800052f3  mov     [rbp+48h], edx
0x1800052f6  mov     eax, [rbp+48h]
0x1800052f9  cmp     eax, 0E06D7363h
0x1800052fe  jnz     short loc_180005314
0x180005300  mov     rdx, [rbp+0B8h]
0x180005307  mov     ecx, [rbp+48h]
0x18000530a  call    _XcptFilter_0
0x18000530f  mov     [rbp+50h], eax
0x180005312  jmp     short loc_18000531B
0x180005314  mov     dword ptr [rbp+50h], 0
0x18000531b  mov     eax, [rbp+50h]
0x18000531e  add     rsp, 20h
0x180005322  pop     rbp
0x180005323  retn
0x180005325  push    rbp
0x180005327  sub     rsp, 20h
0x18000532b  mov     rbp, rdx
0x18000532e  mov     rax, [rcx]
0x180005331  mov     edx, [rax]
0x180005333  mov     [rbp+0C0h], rcx
0x18000533a  mov     [rbp+58h], edx
0x18000533d  mov     eax, [rbp+58h]
0x180005340  cmp     eax, 0E06D7363h
0x180005345  jnz     short loc_18000535B
0x180005347  mov     rdx, [rbp+0C0h]
0x18000534e  mov     ecx, [rbp+58h]
0x180005351  call    _XcptFilter_0
0x180005356  mov     [rbp+60h], eax
0x180005359  jmp     short loc_180005362
0x18000535b  mov     dword ptr [rbp+60h], 0
0x180005362  mov     eax, [rbp+60h]
0x180005365  add     rsp, 20h
0x180005369  pop     rbp
0x18000536a  retn
0x18000536c  push    rbp
0x18000536e  sub     rsp, 20h
0x180005372  mov     rbp, rdx
0x180005375  mov     rax, [rcx]
0x180005378  mov     edx, [rax]
0x18000537a  mov     [rbp+0C8h], rcx
0x180005381  mov     [rbp+68h], edx
0x180005384  mov     eax, [rbp+68h]
0x180005387  cmp     eax, 0E06D7363h
0x18000538c  jnz     short loc_1800053A2
0x18000538e  mov     rdx, [rbp+0C8h]
0x180005395  mov     ecx, [rbp+68h]
0x180005398  call    _XcptFilter_0
0x18000539d  mov     [rbp+70h], eax
0x1800053a0  jmp     short loc_1800053A9
0x1800053a2  mov     dword ptr [rbp+70h], 0
0x1800053a9  mov     eax, [rbp+70h]
0x1800053ac  add     rsp, 20h
0x1800053b0  pop     rbp
0x1800053b1  retn
0x1800053b3  push    rbp
0x1800053b5  sub     rsp, 20h
0x1800053b9  mov     rbp, rdx
0x1800053bc  mov     rax, [rcx]
0x1800053bf  mov     edx, [rax]
0x1800053c1  mov     [rbp+0D0h], rcx
0x1800053c8  mov     [rbp+78h], edx
0x1800053cb  mov     eax, [rbp+78h]
0x1800053ce  cmp     eax, 0E06D7363h
0x1800053d3  jnz     short loc_1800053EC
0x1800053d5  mov     rdx, [rbp+0D0h]
0x1800053dc  mov     ecx, [rbp+78h]
0x1800053df  call    _XcptFilter_0
0x1800053e4  mov     [rbp+80h], eax
0x1800053ea  jmp     short loc_1800053F6
0x1800053ec  mov     dword ptr [rbp+80h], 0
0x1800053f6  mov     eax, [rbp+80h]
0x1800053fc  add     rsp, 20h
0x180005400  pop     rbp
0x180005401  retn
0x180005403  push    rbp
0x180005405  sub     rsp, 20h
0x180005409  mov     rbp, rdx
0x18000540c  mov     rax, [rcx]
0x18000540f  mov     edx, [rax]
0x180005411  mov     [rbp+0D8h], rcx
0x180005418  mov     [rbp+88h], edx
0x18000541e  mov     eax, [rbp+88h]
0x180005424  cmp     eax, 0E06D7363h
0x180005429  jnz     short loc_180005445
0x18000542b  mov     rdx, [rbp+0D8h]
0x180005432  mov     ecx, [rbp+88h]
0x180005438  call    _XcptFilter_0
0x18000543d  mov     [rbp+90h], eax
0x180005443  jmp     short loc_18000544F
0x180005445  mov     dword ptr [rbp+90h], 0
0x18000544f  mov     eax, [rbp+90h]
0x180005455  add     rsp, 20h
0x180005459  pop     rbp
0x18000545a  retn
0x18000545c  push    rbp
0x18000545e  sub     rsp, 20h
0x180005462  mov     rbp, rdx
0x180005465  mov     rax, [rcx]
0x180005468  mov     edx, [rax]
0x18000546a  mov     [rbp+0E0h], rcx
0x180005471  mov     [rbp+98h], edx
0x180005477  mov     eax, [rbp+98h]
0x18000547d  cmp     eax, 0E06D7363h
0x180005482  jnz     short loc_18000549E
0x180005484  mov     rdx, [rbp+0E0h]
0x18000548b  mov     ecx, [rbp+98h]
0x180005491  call    _XcptFilter_0
0x180005496  mov     [rbp+0A0h], eax
0x18000549c  jmp     short loc_1800054A8
0x18000549e  mov     dword ptr [rbp+0A0h], 0
0x1800054a8  mov     eax, [rbp+0A0h]
0x1800054ae  add     rsp, 20h
0x1800054b2  pop     rbp
0x1800054b3  retn
0x1800054b5  push    rbp
0x1800054b7  sub     rsp, 20h
0x1800054bb  mov     rbp, rdx
0x1800054be  cmp     dword ptr [rbp+118h], 1
0x1800054c5  ja      short loc_1800054D1
0x1800054c7  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
