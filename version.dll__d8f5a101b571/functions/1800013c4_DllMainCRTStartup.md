# __DllMainCRTStartup

- ea: `0x1800013c4`
- end: `0x1800015d0`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180001380`

## callees

- `0x1800010a0`
- `0x180001150`
- `0x1800013c4`
- `0x1800015d6`
- `0x1800031f0`

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
  if ( (_DWORD)fdwReason || dword_1800070A0 )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_1800070A4 = 1;
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
            if ( dword_1800070A4 )
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
0x1800013c4  mov     [rsp+lpvReserved], r8
0x1800013c9  mov     [rsp+arg_8], edx
0x1800013cd  mov     [rsp+arg_0], rcx
0x1800013d2  push    rbx
0x1800013d3  push    rsi
0x1800013d4  push    rdi
0x1800013d5  sub     rsp, 0F0h
0x1800013dc  mov     edi, edx
0x1800013de  mov     rsi, rcx
0x1800013e1  mov     ebx, 1
0x1800013e6  cmp     edx, ebx
0x1800013e8  ja      short loc_1800013F0
0x1800013ea  mov     cs:__native_dllmain_reason, edx
0x1800013f0  test    edx, edx
0x1800013f2  jnz     short loc_180001407
0x1800013f4  cmp     cs:dword_1800070A0, edx
0x1800013fa  jnz     short loc_180001407
0x1800013fc  xor     ebx, ebx
0x1800013fe  mov     [rsp+108h+var_E8], ebx
0x180001402  jmp     loc_1800015B4
0x180001407  lea     eax, [rdx-1]
0x18000140a  cmp     eax, 1
0x18000140d  ja      loc_180001494
0x180001413  mov     rax, cs:_pRawDllMain
0x18000141a  test    rax, rax
0x18000141d  jz      short loc_180001455
0x18000141f  cmp     edx, 1
0x180001422  jnz     short loc_18000142A
0x180001424  mov     cs:dword_1800070A4, edx
0x18000142a  mov     r8, [rsp+108h+lpvReserved]
0x180001432  call    cs:__guard_dispatch_icall_fptr
0x180001438  mov     ebx, eax
0x18000143a  mov     [rsp+108h+var_E8], eax
0x18000143e  jmp     short loc_180001455
0x180001440  xor     ebx, ebx
0x180001442  mov     [rsp+108h+var_E8], ebx
0x180001446  mov     edi, [rsp+108h+arg_8]
0x18000144d  mov     rsi, [rsp+108h+arg_0]
0x180001455  test    ebx, ebx
0x180001457  jz      loc_1800015B4
0x18000145d  mov     r8, [rsp+108h+lpvReserved]
0x180001465  mov     edx, edi
0x180001467  mov     rcx, rsi
0x18000146a  call    _CRT_INIT
0x18000146f  mov     ebx, eax
0x180001471  mov     [rsp+108h+var_E8], eax
0x180001475  jmp     short loc_18000148C
0x180001477  xor     ebx, ebx
0x180001479  mov     [rsp+108h+var_E8], ebx
0x18000147d  mov     edi, [rsp+108h+arg_8]
0x180001484  mov     rsi, [rsp+108h+arg_0]
0x18000148c  test    ebx, ebx
0x18000148e  jz      loc_1800015B4
0x180001494  mov     r8, [rsp+108h+lpvReserved]; lpvReserved
0x18000149c  mov     edx, edi; fdwReason
0x18000149e  mov     rcx, rsi; hinstDLL
0x1800014a1  call    DllMain
0x1800014a6  mov     ebx, eax
0x1800014a8  mov     [rsp+108h+var_E8], eax
0x1800014ac  jmp     short loc_1800014C3
0x1800014ae  xor     ebx, ebx
0x1800014b0  mov     [rsp+108h+var_E8], ebx
0x1800014b4  mov     edi, [rsp+108h+arg_8]
0x1800014bb  mov     rsi, [rsp+108h+arg_0]
0x1800014c3  cmp     edi, 1
0x1800014c6  jnz     short loc_18000153F
0x1800014c8  test    ebx, ebx
0x1800014ca  jnz     short loc_18000153F
0x1800014cc  xor     r8d, r8d; lpvReserved
0x1800014cf  xor     edx, edx; fdwReason
0x1800014d1  mov     rcx, rsi; hinstDLL
0x1800014d4  call    DllMain
0x1800014d9  jmp     short loc_1800014EE
0x1800014db  mov     edi, [rsp+108h+arg_8]
0x1800014e2  mov     rsi, [rsp+108h+arg_0]
0x1800014ea  mov     ebx, [rsp+108h+var_E8]
0x1800014ee  xor     r8d, r8d
0x1800014f1  xor     edx, edx
0x1800014f3  mov     rcx, rsi
0x1800014f6  call    _CRT_INIT
0x1800014fb  jmp     short loc_180001510
0x1800014fd  mov     edi, [rsp+108h+arg_8]
0x180001504  mov     rsi, [rsp+108h+arg_0]
0x18000150c  mov     ebx, [rsp+108h+var_E8]
0x180001510  mov     rax, cs:_pRawDllMain
0x180001517  test    rax, rax
0x18000151a  jz      short loc_18000153F
0x18000151c  xor     r8d, r8d
0x18000151f  xor     edx, edx
0x180001521  mov     rcx, rsi
0x180001524  call    cs:__guard_dispatch_icall_fptr
0x18000152a  jmp     short loc_18000153F
0x18000152c  mov     edi, [rsp+108h+arg_8]
0x180001533  mov     rsi, [rsp+108h+arg_0]
0x18000153b  mov     ebx, [rsp+108h+var_E8]
0x18000153f  test    edi, edi
0x180001541  jz      short loc_180001548
0x180001543  cmp     edi, 3
0x180001546  jnz     short loc_1800015B4
0x180001548  mov     r8, [rsp+108h+lpvReserved]
0x180001550  mov     edx, edi
0x180001552  mov     rcx, rsi
0x180001555  call    _CRT_INIT
0x18000155a  mov     ebx, eax
0x18000155c  mov     [rsp+108h+var_E8], eax
0x180001560  jmp     short loc_180001577
0x180001562  xor     ebx, ebx
0x180001564  mov     [rsp+108h+var_E8], ebx
0x180001568  mov     edi, [rsp+108h+arg_8]
0x18000156f  mov     rsi, [rsp+108h+arg_0]
0x180001577  mov     rax, cs:_pRawDllMain
0x18000157e  test    rax, rax
0x180001581  jz      short loc_1800015B4
0x180001583  cmp     cs:dword_1800070A4, 0
0x18000158a  jz      short loc_1800015B4
0x18000158c  mov     r8, [rsp+108h+lpvReserved]
0x180001594  mov     edx, edi
0x180001596  mov     rcx, rsi
0x180001599  call    cs:__guard_dispatch_icall_fptr
0x18000159f  mov     ebx, eax
0x1800015a1  mov     [rsp+108h+var_E8], eax
0x1800015a5  jmp     short loc_1800015B4
0x1800015a7  xor     ebx, ebx
0x1800015a9  mov     [rsp+108h+var_E8], ebx
0x1800015ad  mov     edi, [rsp+108h+arg_8]
0x1800015b4  cmp     edi, 1
0x1800015b7  ja      short loc_1800015C3
0x1800015b9  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x1800015c3  mov     eax, ebx
0x1800015c5  add     rsp, 0F0h
0x1800015cc  pop     rdi
0x1800015cd  pop     rsi
0x1800015ce  pop     rbx
0x1800015cf  retn
0x180003260  push    rbp
0x180003262  sub     rsp, 20h
0x180003266  mov     rbp, rdx
0x180003269  mov     rax, [rcx]
0x18000326c  mov     edx, [rax]
0x18000326e  mov     [rbp+0A8h], rcx
0x180003275  mov     [rbp+28h], edx
0x180003278  mov     eax, [rbp+28h]
0x18000327b  cmp     eax, 0E06D7363h
0x180003280  jnz     short loc_180003296
0x180003282  mov     rdx, [rbp+0A8h]
0x180003289  mov     ecx, [rbp+28h]
0x18000328c  call    _XcptFilter_0
0x180003291  mov     [rbp+30h], eax
0x180003294  jmp     short loc_18000329D
0x180003296  mov     dword ptr [rbp+30h], 0
0x18000329d  mov     eax, [rbp+30h]
0x1800032a0  add     rsp, 20h
0x1800032a4  pop     rbp
0x1800032a5  retn
0x1800032a7  push    rbp
0x1800032a9  sub     rsp, 20h
0x1800032ad  mov     rbp, rdx
0x1800032b0  mov     rax, [rcx]
0x1800032b3  mov     edx, [rax]
0x1800032b5  mov     [rbp+0B0h], rcx
0x1800032bc  mov     [rbp+38h], edx
0x1800032bf  mov     eax, [rbp+38h]
0x1800032c2  cmp     eax, 0E06D7363h
0x1800032c7  jnz     short loc_1800032DD
0x1800032c9  mov     rdx, [rbp+0B0h]
0x1800032d0  mov     ecx, [rbp+38h]
0x1800032d3  call    _XcptFilter_0
0x1800032d8  mov     [rbp+40h], eax
0x1800032db  jmp     short loc_1800032E4
0x1800032dd  mov     dword ptr [rbp+40h], 0
0x1800032e4  mov     eax, [rbp+40h]
0x1800032e7  add     rsp, 20h
0x1800032eb  pop     rbp
0x1800032ec  retn
0x1800032ee  push    rbp
0x1800032f0  sub     rsp, 20h
0x1800032f4  mov     rbp, rdx
0x1800032f7  mov     rax, [rcx]
0x1800032fa  mov     edx, [rax]
0x1800032fc  mov     [rbp+0B8h], rcx
0x180003303  mov     [rbp+48h], edx
0x180003306  mov     eax, [rbp+48h]
0x180003309  cmp     eax, 0E06D7363h
0x18000330e  jnz     short loc_180003324
0x180003310  mov     rdx, [rbp+0B8h]
0x180003317  mov     ecx, [rbp+48h]
0x18000331a  call    _XcptFilter_0
0x18000331f  mov     [rbp+50h], eax
0x180003322  jmp     short loc_18000332B
0x180003324  mov     dword ptr [rbp+50h], 0
0x18000332b  mov     eax, [rbp+50h]
0x18000332e  add     rsp, 20h
0x180003332  pop     rbp
0x180003333  retn
0x180003335  push    rbp
0x180003337  sub     rsp, 20h
0x18000333b  mov     rbp, rdx
0x18000333e  mov     rax, [rcx]
0x180003341  mov     edx, [rax]
0x180003343  mov     [rbp+0C0h], rcx
0x18000334a  mov     [rbp+58h], edx
0x18000334d  mov     eax, [rbp+58h]
0x180003350  cmp     eax, 0E06D7363h
0x180003355  jnz     short loc_18000336B
0x180003357  mov     rdx, [rbp+0C0h]
0x18000335e  mov     ecx, [rbp+58h]
0x180003361  call    _XcptFilter_0
0x180003366  mov     [rbp+60h], eax
0x180003369  jmp     short loc_180003372
0x18000336b  mov     dword ptr [rbp+60h], 0
0x180003372  mov     eax, [rbp+60h]
0x180003375  add     rsp, 20h
0x180003379  pop     rbp
0x18000337a  retn
0x18000337c  push    rbp
0x18000337e  sub     rsp, 20h
0x180003382  mov     rbp, rdx
0x180003385  mov     rax, [rcx]
0x180003388  mov     edx, [rax]
0x18000338a  mov     [rbp+0C8h], rcx
0x180003391  mov     [rbp+68h], edx
0x180003394  mov     eax, [rbp+68h]
0x180003397  cmp     eax, 0E06D7363h
0x18000339c  jnz     short loc_1800033B2
0x18000339e  mov     rdx, [rbp+0C8h]
0x1800033a5  mov     ecx, [rbp+68h]
0x1800033a8  call    _XcptFilter_0
0x1800033ad  mov     [rbp+70h], eax
0x1800033b0  jmp     short loc_1800033B9
0x1800033b2  mov     dword ptr [rbp+70h], 0
0x1800033b9  mov     eax, [rbp+70h]
0x1800033bc  add     rsp, 20h
0x1800033c0  pop     rbp
0x1800033c1  retn
0x1800033c3  push    rbp
0x1800033c5  sub     rsp, 20h
0x1800033c9  mov     rbp, rdx
0x1800033cc  mov     rax, [rcx]
0x1800033cf  mov     edx, [rax]
0x1800033d1  mov     [rbp+0D0h], rcx
0x1800033d8  mov     [rbp+78h], edx
0x1800033db  mov     eax, [rbp+78h]
0x1800033de  cmp     eax, 0E06D7363h
0x1800033e3  jnz     short loc_1800033FC
0x1800033e5  mov     rdx, [rbp+0D0h]
0x1800033ec  mov     ecx, [rbp+78h]
0x1800033ef  call    _XcptFilter_0
0x1800033f4  mov     [rbp+80h], eax
0x1800033fa  jmp     short loc_180003406
0x1800033fc  mov     dword ptr [rbp+80h], 0
0x180003406  mov     eax, [rbp+80h]
0x18000340c  add     rsp, 20h
0x180003410  pop     rbp
0x180003411  retn
0x180003413  push    rbp
0x180003415  sub     rsp, 20h
0x180003419  mov     rbp, rdx
0x18000341c  mov     rax, [rcx]
0x18000341f  mov     edx, [rax]
0x180003421  mov     [rbp+0D8h], rcx
0x180003428  mov     [rbp+88h], edx
0x18000342e  mov     eax, [rbp+88h]
0x180003434  cmp     eax, 0E06D7363h
0x180003439  jnz     short loc_180003455
0x18000343b  mov     rdx, [rbp+0D8h]
0x180003442  mov     ecx, [rbp+88h]
0x180003448  call    _XcptFilter_0
0x18000344d  mov     [rbp+90h], eax
0x180003453  jmp     short loc_18000345F
0x180003455  mov     dword ptr [rbp+90h], 0
0x18000345f  mov     eax, [rbp+90h]
0x180003465  add     rsp, 20h
0x180003469  pop     rbp
0x18000346a  retn
0x18000346c  push    rbp
0x18000346e  sub     rsp, 20h
0x180003472  mov     rbp, rdx
0x180003475  mov     rax, [rcx]
0x180003478  mov     edx, [rax]
0x18000347a  mov     [rbp+0E0h], rcx
0x180003481  mov     [rbp+98h], edx
0x180003487  mov     eax, [rbp+98h]
0x18000348d  cmp     eax, 0E06D7363h
0x180003492  jnz     short loc_1800034AE
0x180003494  mov     rdx, [rbp+0E0h]
0x18000349b  mov     ecx, [rbp+98h]
0x1800034a1  call    _XcptFilter_0
0x1800034a6  mov     [rbp+0A0h], eax
0x1800034ac  jmp     short loc_1800034B8
0x1800034ae  mov     dword ptr [rbp+0A0h], 0
0x1800034b8  mov     eax, [rbp+0A0h]
0x1800034be  add     rsp, 20h
0x1800034c2  pop     rbp
0x1800034c3  retn
0x1800034c5  push    rbp
0x1800034c7  sub     rsp, 20h
0x1800034cb  mov     rbp, rdx
0x1800034ce  cmp     dword ptr [rbp+118h], 1
0x1800034d5  ja      short loc_1800034E1
0x1800034d7  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
