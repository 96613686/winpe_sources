# __DllMainCRTStartup

- ea: `0x180001364`
- end: `0x180001571`
- name: `__DllMainCRTStartup`
- size: `525`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180001320`

## callees

- `0x1800010dc`
- `0x180001364`
- `0x1800016a5`
- `0x18000e32c`
- `0x180011010`

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
  if ( (_DWORD)fdwReason || dword_1800181A0 )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_1800181A4 = 1;
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
            if ( dword_1800181A4 )
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
0x180001364  mov     [rsp+lpvReserved], r8
0x180001369  mov     [rsp+arg_8], edx
0x18000136d  mov     [rsp+arg_0], rcx
0x180001372  push    rbx
0x180001373  push    rsi
0x180001374  push    rdi
0x180001375  sub     rsp, 150h
0x18000137c  mov     edi, edx
0x18000137e  mov     rsi, rcx
0x180001381  mov     ebx, 1
0x180001386  mov     [rsp+168h+var_148], ebx
0x18000138a  cmp     edx, ebx
0x18000138c  ja      short loc_180001394
0x18000138e  mov     cs:__native_dllmain_reason, edx
0x180001394  test    edx, edx
0x180001396  jnz     short loc_1800013AB
0x180001398  cmp     cs:dword_1800181A0, edx
0x18000139e  jnz     short loc_1800013AB
0x1800013a0  xor     ebx, ebx
0x1800013a2  mov     [rsp+168h+var_148], ebx
0x1800013a6  jmp     loc_180001555
0x1800013ab  lea     eax, [rdx-1]
0x1800013ae  cmp     eax, 1
0x1800013b1  ja      loc_180001437
0x1800013b7  mov     rax, cs:_pRawDllMain
0x1800013be  test    rax, rax
0x1800013c1  jz      short loc_1800013F8
0x1800013c3  cmp     edx, 1
0x1800013c6  jnz     short loc_1800013CE
0x1800013c8  mov     cs:dword_1800181A4, edx
0x1800013ce  mov     r8, [rsp+168h+lpvReserved]
0x1800013d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800013db  mov     ebx, eax
0x1800013dd  mov     [rsp+168h+var_148], eax
0x1800013e1  jmp     short loc_1800013F8
0x1800013e3  xor     ebx, ebx
0x1800013e5  mov     [rsp+168h+var_148], ebx
0x1800013e9  mov     edi, [rsp+168h+arg_8]
0x1800013f0  mov     rsi, [rsp+168h+arg_0]
0x1800013f8  test    ebx, ebx
0x1800013fa  jz      loc_180001555
0x180001400  mov     r8, [rsp+168h+lpvReserved]
0x180001408  mov     edx, edi
0x18000140a  mov     rcx, rsi
0x18000140d  call    _CRT_INIT
0x180001412  mov     ebx, eax
0x180001414  mov     [rsp+168h+var_148], eax
0x180001418  jmp     short loc_18000142F
0x18000141a  xor     ebx, ebx
0x18000141c  mov     [rsp+168h+var_148], ebx
0x180001420  mov     edi, [rsp+168h+arg_8]
0x180001427  mov     rsi, [rsp+168h+arg_0]
0x18000142f  test    ebx, ebx
0x180001431  jz      loc_180001555
0x180001437  mov     r8, [rsp+168h+lpvReserved]; lpvReserved
0x18000143f  mov     edx, edi; fdwReason
0x180001441  mov     rcx, rsi; hinstDLL
0x180001444  call    DllMain
0x180001449  mov     ebx, eax
0x18000144b  mov     [rsp+168h+var_148], eax
0x18000144f  jmp     short loc_180001466
0x180001451  xor     ebx, ebx
0x180001453  mov     [rsp+168h+var_148], ebx
0x180001457  mov     edi, [rsp+168h+arg_8]
0x18000145e  mov     rsi, [rsp+168h+arg_0]
0x180001466  cmp     edi, 1
0x180001469  jnz     short loc_1800014E1
0x18000146b  test    ebx, ebx
0x18000146d  jnz     short loc_1800014E1
0x18000146f  xor     r8d, r8d; lpvReserved
0x180001472  xor     edx, edx; fdwReason
0x180001474  mov     rcx, rsi; hinstDLL
0x180001477  call    DllMain
0x18000147c  jmp     short loc_180001491
0x18000147e  mov     edi, [rsp+168h+arg_8]
0x180001485  mov     rsi, [rsp+168h+arg_0]
0x18000148d  mov     ebx, [rsp+168h+var_148]
0x180001491  xor     r8d, r8d
0x180001494  xor     edx, edx
0x180001496  mov     rcx, rsi
0x180001499  call    _CRT_INIT
0x18000149e  jmp     short loc_1800014B3
0x1800014a0  mov     edi, [rsp+168h+arg_8]
0x1800014a7  mov     rsi, [rsp+168h+arg_0]
0x1800014af  mov     ebx, [rsp+168h+var_148]
0x1800014b3  mov     rax, cs:_pRawDllMain
0x1800014ba  test    rax, rax
0x1800014bd  jz      short loc_1800014E1
0x1800014bf  xor     r8d, r8d
0x1800014c2  xor     edx, edx
0x1800014c4  mov     rcx, rsi
0x1800014c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800014cc  jmp     short loc_1800014E1
0x1800014ce  mov     edi, [rsp+168h+arg_8]
0x1800014d5  mov     rsi, [rsp+168h+arg_0]
0x1800014dd  mov     ebx, [rsp+168h+var_148]
0x1800014e1  test    edi, edi
0x1800014e3  jz      short loc_1800014EA
0x1800014e5  cmp     edi, 3
0x1800014e8  jnz     short loc_180001555
0x1800014ea  mov     r8, [rsp+168h+lpvReserved]
0x1800014f2  mov     edx, edi
0x1800014f4  mov     rcx, rsi
0x1800014f7  call    _CRT_INIT
0x1800014fc  mov     ebx, eax
0x1800014fe  mov     [rsp+168h+var_148], eax
0x180001502  jmp     short loc_180001519
0x180001504  xor     ebx, ebx
0x180001506  mov     [rsp+168h+var_148], ebx
0x18000150a  mov     edi, [rsp+168h+arg_8]
0x180001511  mov     rsi, [rsp+168h+arg_0]
0x180001519  mov     rax, cs:_pRawDllMain
0x180001520  test    rax, rax
0x180001523  jz      short loc_180001555
0x180001525  cmp     cs:dword_1800181A4, 0
0x18000152c  jz      short loc_180001555
0x18000152e  mov     r8, [rsp+168h+lpvReserved]
0x180001536  mov     edx, edi
0x180001538  mov     rcx, rsi
0x18000153b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001540  mov     ebx, eax
0x180001542  mov     [rsp+168h+var_148], eax
0x180001546  jmp     short loc_180001555
0x180001548  xor     ebx, ebx
0x18000154a  mov     [rsp+168h+var_148], ebx
0x18000154e  mov     edi, [rsp+168h+arg_8]
0x180001555  cmp     edi, 1
0x180001558  ja      short loc_180001564
0x18000155a  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x180001564  mov     eax, ebx
0x180001566  add     rsp, 150h
0x18000156d  pop     rdi
0x18000156e  pop     rsi
0x18000156f  pop     rbx
0x180001570  retn
0x18000ffc0  push    rbp
0x18000ffc2  sub     rsp, 20h
0x18000ffc6  mov     rbp, rdx
0x18000ffc9  mov     [rbp+108h], rcx
0x18000ffd0  mov     rax, [rcx]
0x18000ffd3  mov     edx, [rax]
0x18000ffd5  mov     [rbp+0A4h], edx
0x18000ffdb  mov     [rbp+0C8h], rcx
0x18000ffe2  mov     [rbp+28h], edx
0x18000ffe5  mov     eax, [rbp+28h]
0x18000ffe8  cmp     eax, 0E06D7363h
0x18000ffed  jnz     short loc_180010003
0x18000ffef  mov     rdx, [rbp+0C8h]
0x18000fff6  mov     ecx, [rbp+28h]
0x18000fff9  call    _XcptFilter_0
0x18000fffe  mov     [rbp+30h], eax
0x180010001  jmp     short loc_18001000A
0x180010003  mov     dword ptr [rbp+30h], 0
0x18001000a  mov     eax, [rbp+30h]
0x18001000d  add     rsp, 20h
0x180010011  pop     rbp
0x180010012  retn
0x180010014  push    rbp
0x180010016  sub     rsp, 20h
0x18001001a  mov     rbp, rdx
0x18001001d  mov     [rbp+110h], rcx
0x180010024  mov     rax, [rcx]
0x180010027  mov     edx, [rax]
0x180010029  mov     [rbp+0A8h], edx
0x18001002f  mov     [rbp+0D0h], rcx
0x180010036  mov     [rbp+38h], edx
0x180010039  mov     eax, [rbp+38h]
0x18001003c  cmp     eax, 0E06D7363h
0x180010041  jnz     short loc_180010057
0x180010043  mov     rdx, [rbp+0D0h]
0x18001004a  mov     ecx, [rbp+38h]
0x18001004d  call    _XcptFilter_0
0x180010052  mov     [rbp+40h], eax
0x180010055  jmp     short loc_18001005E
0x180010057  mov     dword ptr [rbp+40h], 0
0x18001005e  mov     eax, [rbp+40h]
0x180010061  add     rsp, 20h
0x180010065  pop     rbp
0x180010066  retn
0x180010068  push    rbp
0x18001006a  sub     rsp, 20h
0x18001006e  mov     rbp, rdx
0x180010071  mov     [rbp+118h], rcx
0x180010078  mov     rax, [rcx]
0x18001007b  mov     edx, [rax]
0x18001007d  mov     [rbp+0ACh], edx
0x180010083  mov     [rbp+0D8h], rcx
0x18001008a  mov     [rbp+48h], edx
0x18001008d  mov     eax, [rbp+48h]
0x180010090  cmp     eax, 0E06D7363h
0x180010095  jnz     short loc_1800100AB
0x180010097  mov     rdx, [rbp+0D8h]
0x18001009e  mov     ecx, [rbp+48h]
0x1800100a1  call    _XcptFilter_0
0x1800100a6  mov     [rbp+50h], eax
0x1800100a9  jmp     short loc_1800100B2
0x1800100ab  mov     dword ptr [rbp+50h], 0
0x1800100b2  mov     eax, [rbp+50h]
0x1800100b5  add     rsp, 20h
0x1800100b9  pop     rbp
0x1800100ba  retn
0x1800100bc  push    rbp
0x1800100be  sub     rsp, 20h
0x1800100c2  mov     rbp, rdx
0x1800100c5  mov     [rbp+120h], rcx
0x1800100cc  mov     rax, [rcx]
0x1800100cf  mov     edx, [rax]
0x1800100d1  mov     [rbp+0B0h], edx
0x1800100d7  mov     [rbp+0E0h], rcx
0x1800100de  mov     [rbp+58h], edx
0x1800100e1  mov     eax, [rbp+58h]
0x1800100e4  cmp     eax, 0E06D7363h
0x1800100e9  jnz     short loc_1800100FF
0x1800100eb  mov     rdx, [rbp+0E0h]
0x1800100f2  mov     ecx, [rbp+58h]
0x1800100f5  call    _XcptFilter_0
0x1800100fa  mov     [rbp+60h], eax
0x1800100fd  jmp     short loc_180010106
0x1800100ff  mov     dword ptr [rbp+60h], 0
0x180010106  mov     eax, [rbp+60h]
0x180010109  add     rsp, 20h
0x18001010d  pop     rbp
0x18001010e  retn
0x180010110  push    rbp
0x180010112  sub     rsp, 20h
0x180010116  mov     rbp, rdx
0x180010119  mov     [rbp+128h], rcx
0x180010120  mov     rax, [rcx]
0x180010123  mov     edx, [rax]
0x180010125  mov     [rbp+0B4h], edx
0x18001012b  mov     [rbp+0E8h], rcx
0x180010132  mov     [rbp+68h], edx
0x180010135  mov     eax, [rbp+68h]
0x180010138  cmp     eax, 0E06D7363h
0x18001013d  jnz     short loc_180010153
0x18001013f  mov     rdx, [rbp+0E8h]
0x180010146  mov     ecx, [rbp+68h]
0x180010149  call    _XcptFilter_0
0x18001014e  mov     [rbp+70h], eax
0x180010151  jmp     short loc_18001015A
0x180010153  mov     dword ptr [rbp+70h], 0
0x18001015a  mov     eax, [rbp+70h]
0x18001015d  add     rsp, 20h
0x180010161  pop     rbp
0x180010162  retn
0x180010164  push    rbp
0x180010166  sub     rsp, 20h
0x18001016a  mov     rbp, rdx
0x18001016d  mov     [rbp+130h], rcx
0x180010174  mov     rax, [rcx]
0x180010177  mov     edx, [rax]
0x180010179  mov     [rbp+0B8h], edx
0x18001017f  mov     [rbp+0F0h], rcx
0x180010186  mov     [rbp+78h], edx
0x180010189  mov     eax, [rbp+78h]
0x18001018c  cmp     eax, 0E06D7363h
0x180010191  jnz     short loc_1800101AA
0x180010193  mov     rdx, [rbp+0F0h]
0x18001019a  mov     ecx, [rbp+78h]
0x18001019d  call    _XcptFilter_0
0x1800101a2  mov     [rbp+80h], eax
0x1800101a8  jmp     short loc_1800101B4
0x1800101aa  mov     dword ptr [rbp+80h], 0
0x1800101b4  mov     eax, [rbp+80h]
0x1800101ba  add     rsp, 20h
0x1800101be  pop     rbp
0x1800101bf  retn
0x1800101c1  push    rbp
0x1800101c3  sub     rsp, 20h
0x1800101c7  mov     rbp, rdx
0x1800101ca  mov     [rbp+138h], rcx
0x1800101d1  mov     rax, [rcx]
0x1800101d4  mov     edx, [rax]
0x1800101d6  mov     [rbp+0BCh], edx
0x1800101dc  mov     [rbp+0F8h], rcx
0x1800101e3  mov     [rbp+88h], edx
0x1800101e9  mov     eax, [rbp+88h]
0x1800101ef  cmp     eax, 0E06D7363h
0x1800101f4  jnz     short loc_180010210
0x1800101f6  mov     rdx, [rbp+0F8h]
0x1800101fd  mov     ecx, [rbp+88h]
0x180010203  call    _XcptFilter_0
0x180010208  mov     [rbp+90h], eax
0x18001020e  jmp     short loc_18001021A
0x180010210  mov     dword ptr [rbp+90h], 0
0x18001021a  mov     eax, [rbp+90h]
0x180010220  add     rsp, 20h
0x180010224  pop     rbp
0x180010225  retn
0x180010227  push    rbp
0x180010229  sub     rsp, 20h
0x18001022d  mov     rbp, rdx
0x180010230  mov     [rbp+140h], rcx
0x180010237  mov     rax, [rcx]
0x18001023a  mov     edx, [rax]
0x18001023c  mov     [rbp+0C0h], edx
0x180010242  mov     [rbp+100h], rcx
0x180010249  mov     [rbp+98h], edx
0x18001024f  mov     eax, [rbp+98h]
0x180010255  cmp     eax, 0E06D7363h
  ... truncated ...
```
