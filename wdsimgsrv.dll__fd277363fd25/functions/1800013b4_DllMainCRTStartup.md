# __DllMainCRTStartup

- ea: `0x1800013b4`
- end: `0x1800015c1`
- name: `__DllMainCRTStartup`
- size: `525`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180001370`

## callees

- `0x18000112c`
- `0x1800013b4`
- `0x1800016c3`
- `0x1800018a4`
- `0x180017010`

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
  if ( (_DWORD)fdwReason || dword_1800226A0 )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_1800226A4 = 1;
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
            if ( dword_1800226A4 )
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
0x1800013b4  mov     [rsp+lpvReserved], r8
0x1800013b9  mov     [rsp+arg_8], edx
0x1800013bd  mov     [rsp+arg_0], rcx
0x1800013c2  push    rbx
0x1800013c3  push    rsi
0x1800013c4  push    rdi
0x1800013c5  sub     rsp, 150h
0x1800013cc  mov     edi, edx
0x1800013ce  mov     rsi, rcx
0x1800013d1  mov     ebx, 1
0x1800013d6  mov     [rsp+168h+var_148], ebx
0x1800013da  cmp     edx, ebx
0x1800013dc  ja      short loc_1800013E4
0x1800013de  mov     cs:__native_dllmain_reason, edx
0x1800013e4  test    edx, edx
0x1800013e6  jnz     short loc_1800013FB
0x1800013e8  cmp     cs:dword_1800226A0, edx
0x1800013ee  jnz     short loc_1800013FB
0x1800013f0  xor     ebx, ebx
0x1800013f2  mov     [rsp+168h+var_148], ebx
0x1800013f6  jmp     loc_1800015A5
0x1800013fb  lea     eax, [rdx-1]
0x1800013fe  cmp     eax, 1
0x180001401  ja      loc_180001487
0x180001407  mov     rax, cs:_pRawDllMain
0x18000140e  test    rax, rax
0x180001411  jz      short loc_180001448
0x180001413  cmp     edx, 1
0x180001416  jnz     short loc_18000141E
0x180001418  mov     cs:dword_1800226A4, edx
0x18000141e  mov     r8, [rsp+168h+lpvReserved]
0x180001426  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000142b  mov     ebx, eax
0x18000142d  mov     [rsp+168h+var_148], eax
0x180001431  jmp     short loc_180001448
0x180001433  xor     ebx, ebx
0x180001435  mov     [rsp+168h+var_148], ebx
0x180001439  mov     edi, [rsp+168h+arg_8]
0x180001440  mov     rsi, [rsp+168h+arg_0]
0x180001448  test    ebx, ebx
0x18000144a  jz      loc_1800015A5
0x180001450  mov     r8, [rsp+168h+lpvReserved]
0x180001458  mov     edx, edi
0x18000145a  mov     rcx, rsi
0x18000145d  call    _CRT_INIT
0x180001462  mov     ebx, eax
0x180001464  mov     [rsp+168h+var_148], eax
0x180001468  jmp     short loc_18000147F
0x18000146a  xor     ebx, ebx
0x18000146c  mov     [rsp+168h+var_148], ebx
0x180001470  mov     edi, [rsp+168h+arg_8]
0x180001477  mov     rsi, [rsp+168h+arg_0]
0x18000147f  test    ebx, ebx
0x180001481  jz      loc_1800015A5
0x180001487  mov     r8, [rsp+168h+lpvReserved]; lpvReserved
0x18000148f  mov     edx, edi; fdwReason
0x180001491  mov     rcx, rsi; hinstDLL
0x180001494  call    DllMain
0x180001499  mov     ebx, eax
0x18000149b  mov     [rsp+168h+var_148], eax
0x18000149f  jmp     short loc_1800014B6
0x1800014a1  xor     ebx, ebx
0x1800014a3  mov     [rsp+168h+var_148], ebx
0x1800014a7  mov     edi, [rsp+168h+arg_8]
0x1800014ae  mov     rsi, [rsp+168h+arg_0]
0x1800014b6  cmp     edi, 1
0x1800014b9  jnz     short loc_180001531
0x1800014bb  test    ebx, ebx
0x1800014bd  jnz     short loc_180001531
0x1800014bf  xor     r8d, r8d; lpvReserved
0x1800014c2  xor     edx, edx; fdwReason
0x1800014c4  mov     rcx, rsi; hinstDLL
0x1800014c7  call    DllMain
0x1800014cc  jmp     short loc_1800014E1
0x1800014ce  mov     edi, [rsp+168h+arg_8]
0x1800014d5  mov     rsi, [rsp+168h+arg_0]
0x1800014dd  mov     ebx, [rsp+168h+var_148]
0x1800014e1  xor     r8d, r8d
0x1800014e4  xor     edx, edx
0x1800014e6  mov     rcx, rsi
0x1800014e9  call    _CRT_INIT
0x1800014ee  jmp     short loc_180001503
0x1800014f0  mov     edi, [rsp+168h+arg_8]
0x1800014f7  mov     rsi, [rsp+168h+arg_0]
0x1800014ff  mov     ebx, [rsp+168h+var_148]
0x180001503  mov     rax, cs:_pRawDllMain
0x18000150a  test    rax, rax
0x18000150d  jz      short loc_180001531
0x18000150f  xor     r8d, r8d
0x180001512  xor     edx, edx
0x180001514  mov     rcx, rsi
0x180001517  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000151c  jmp     short loc_180001531
0x18000151e  mov     edi, [rsp+168h+arg_8]
0x180001525  mov     rsi, [rsp+168h+arg_0]
0x18000152d  mov     ebx, [rsp+168h+var_148]
0x180001531  test    edi, edi
0x180001533  jz      short loc_18000153A
0x180001535  cmp     edi, 3
0x180001538  jnz     short loc_1800015A5
0x18000153a  mov     r8, [rsp+168h+lpvReserved]
0x180001542  mov     edx, edi
0x180001544  mov     rcx, rsi
0x180001547  call    _CRT_INIT
0x18000154c  mov     ebx, eax
0x18000154e  mov     [rsp+168h+var_148], eax
0x180001552  jmp     short loc_180001569
0x180001554  xor     ebx, ebx
0x180001556  mov     [rsp+168h+var_148], ebx
0x18000155a  mov     edi, [rsp+168h+arg_8]
0x180001561  mov     rsi, [rsp+168h+arg_0]
0x180001569  mov     rax, cs:_pRawDllMain
0x180001570  test    rax, rax
0x180001573  jz      short loc_1800015A5
0x180001575  cmp     cs:dword_1800226A4, 0
0x18000157c  jz      short loc_1800015A5
0x18000157e  mov     r8, [rsp+168h+lpvReserved]
0x180001586  mov     edx, edi
0x180001588  mov     rcx, rsi
0x18000158b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001590  mov     ebx, eax
0x180001592  mov     [rsp+168h+var_148], eax
0x180001596  jmp     short loc_1800015A5
0x180001598  xor     ebx, ebx
0x18000159a  mov     [rsp+168h+var_148], ebx
0x18000159e  mov     edi, [rsp+168h+arg_8]
0x1800015a5  cmp     edi, 1
0x1800015a8  ja      short loc_1800015B4
0x1800015aa  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x1800015b4  mov     eax, ebx
0x1800015b6  add     rsp, 150h
0x1800015bd  pop     rdi
0x1800015be  pop     rsi
0x1800015bf  pop     rbx
0x1800015c0  retn
0x1800160d0  push    rbp
0x1800160d2  sub     rsp, 20h
0x1800160d6  mov     rbp, rdx
0x1800160d9  mov     [rbp+108h], rcx
0x1800160e0  mov     rax, [rcx]
0x1800160e3  mov     edx, [rax]
0x1800160e5  mov     [rbp+0A4h], edx
0x1800160eb  mov     [rbp+0C8h], rcx
0x1800160f2  mov     [rbp+28h], edx
0x1800160f5  mov     eax, [rbp+28h]
0x1800160f8  cmp     eax, 0E06D7363h
0x1800160fd  jnz     short loc_180016113
0x1800160ff  mov     rdx, [rbp+0C8h]
0x180016106  mov     ecx, [rbp+28h]
0x180016109  call    _XcptFilter_0
0x18001610e  mov     [rbp+30h], eax
0x180016111  jmp     short loc_18001611A
0x180016113  mov     dword ptr [rbp+30h], 0
0x18001611a  mov     eax, [rbp+30h]
0x18001611d  add     rsp, 20h
0x180016121  pop     rbp
0x180016122  retn
0x180016124  push    rbp
0x180016126  sub     rsp, 20h
0x18001612a  mov     rbp, rdx
0x18001612d  mov     [rbp+110h], rcx
0x180016134  mov     rax, [rcx]
0x180016137  mov     edx, [rax]
0x180016139  mov     [rbp+0A8h], edx
0x18001613f  mov     [rbp+0D0h], rcx
0x180016146  mov     [rbp+38h], edx
0x180016149  mov     eax, [rbp+38h]
0x18001614c  cmp     eax, 0E06D7363h
0x180016151  jnz     short loc_180016167
0x180016153  mov     rdx, [rbp+0D0h]
0x18001615a  mov     ecx, [rbp+38h]
0x18001615d  call    _XcptFilter_0
0x180016162  mov     [rbp+40h], eax
0x180016165  jmp     short loc_18001616E
0x180016167  mov     dword ptr [rbp+40h], 0
0x18001616e  mov     eax, [rbp+40h]
0x180016171  add     rsp, 20h
0x180016175  pop     rbp
0x180016176  retn
0x180016178  push    rbp
0x18001617a  sub     rsp, 20h
0x18001617e  mov     rbp, rdx
0x180016181  mov     [rbp+118h], rcx
0x180016188  mov     rax, [rcx]
0x18001618b  mov     edx, [rax]
0x18001618d  mov     [rbp+0ACh], edx
0x180016193  mov     [rbp+0D8h], rcx
0x18001619a  mov     [rbp+48h], edx
0x18001619d  mov     eax, [rbp+48h]
0x1800161a0  cmp     eax, 0E06D7363h
0x1800161a5  jnz     short loc_1800161BB
0x1800161a7  mov     rdx, [rbp+0D8h]
0x1800161ae  mov     ecx, [rbp+48h]
0x1800161b1  call    _XcptFilter_0
0x1800161b6  mov     [rbp+50h], eax
0x1800161b9  jmp     short loc_1800161C2
0x1800161bb  mov     dword ptr [rbp+50h], 0
0x1800161c2  mov     eax, [rbp+50h]
0x1800161c5  add     rsp, 20h
0x1800161c9  pop     rbp
0x1800161ca  retn
0x1800161cc  push    rbp
0x1800161ce  sub     rsp, 20h
0x1800161d2  mov     rbp, rdx
0x1800161d5  mov     [rbp+120h], rcx
0x1800161dc  mov     rax, [rcx]
0x1800161df  mov     edx, [rax]
0x1800161e1  mov     [rbp+0B0h], edx
0x1800161e7  mov     [rbp+0E0h], rcx
0x1800161ee  mov     [rbp+58h], edx
0x1800161f1  mov     eax, [rbp+58h]
0x1800161f4  cmp     eax, 0E06D7363h
0x1800161f9  jnz     short loc_18001620F
0x1800161fb  mov     rdx, [rbp+0E0h]
0x180016202  mov     ecx, [rbp+58h]
0x180016205  call    _XcptFilter_0
0x18001620a  mov     [rbp+60h], eax
0x18001620d  jmp     short loc_180016216
0x18001620f  mov     dword ptr [rbp+60h], 0
0x180016216  mov     eax, [rbp+60h]
0x180016219  add     rsp, 20h
0x18001621d  pop     rbp
0x18001621e  retn
0x180016220  push    rbp
0x180016222  sub     rsp, 20h
0x180016226  mov     rbp, rdx
0x180016229  mov     [rbp+128h], rcx
0x180016230  mov     rax, [rcx]
0x180016233  mov     edx, [rax]
0x180016235  mov     [rbp+0B4h], edx
0x18001623b  mov     [rbp+0E8h], rcx
0x180016242  mov     [rbp+68h], edx
0x180016245  mov     eax, [rbp+68h]
0x180016248  cmp     eax, 0E06D7363h
0x18001624d  jnz     short loc_180016263
0x18001624f  mov     rdx, [rbp+0E8h]
0x180016256  mov     ecx, [rbp+68h]
0x180016259  call    _XcptFilter_0
0x18001625e  mov     [rbp+70h], eax
0x180016261  jmp     short loc_18001626A
0x180016263  mov     dword ptr [rbp+70h], 0
0x18001626a  mov     eax, [rbp+70h]
0x18001626d  add     rsp, 20h
0x180016271  pop     rbp
0x180016272  retn
0x180016274  push    rbp
0x180016276  sub     rsp, 20h
0x18001627a  mov     rbp, rdx
0x18001627d  mov     [rbp+130h], rcx
0x180016284  mov     rax, [rcx]
0x180016287  mov     edx, [rax]
0x180016289  mov     [rbp+0B8h], edx
0x18001628f  mov     [rbp+0F0h], rcx
0x180016296  mov     [rbp+78h], edx
0x180016299  mov     eax, [rbp+78h]
0x18001629c  cmp     eax, 0E06D7363h
0x1800162a1  jnz     short loc_1800162BA
0x1800162a3  mov     rdx, [rbp+0F0h]
0x1800162aa  mov     ecx, [rbp+78h]
0x1800162ad  call    _XcptFilter_0
0x1800162b2  mov     [rbp+80h], eax
0x1800162b8  jmp     short loc_1800162C4
0x1800162ba  mov     dword ptr [rbp+80h], 0
0x1800162c4  mov     eax, [rbp+80h]
0x1800162ca  add     rsp, 20h
0x1800162ce  pop     rbp
0x1800162cf  retn
0x1800162d1  push    rbp
0x1800162d3  sub     rsp, 20h
0x1800162d7  mov     rbp, rdx
0x1800162da  mov     [rbp+138h], rcx
0x1800162e1  mov     rax, [rcx]
0x1800162e4  mov     edx, [rax]
0x1800162e6  mov     [rbp+0BCh], edx
0x1800162ec  mov     [rbp+0F8h], rcx
0x1800162f3  mov     [rbp+88h], edx
0x1800162f9  mov     eax, [rbp+88h]
0x1800162ff  cmp     eax, 0E06D7363h
0x180016304  jnz     short loc_180016320
0x180016306  mov     rdx, [rbp+0F8h]
0x18001630d  mov     ecx, [rbp+88h]
0x180016313  call    _XcptFilter_0
0x180016318  mov     [rbp+90h], eax
0x18001631e  jmp     short loc_18001632A
0x180016320  mov     dword ptr [rbp+90h], 0
0x18001632a  mov     eax, [rbp+90h]
0x180016330  add     rsp, 20h
0x180016334  pop     rbp
0x180016335  retn
0x180016337  push    rbp
0x180016339  sub     rsp, 20h
0x18001633d  mov     rbp, rdx
0x180016340  mov     [rbp+140h], rcx
0x180016347  mov     rax, [rcx]
0x18001634a  mov     edx, [rax]
0x18001634c  mov     [rbp+0C0h], edx
0x180016352  mov     [rbp+100h], rcx
0x180016359  mov     [rbp+98h], edx
0x18001635f  mov     eax, [rbp+98h]
0x180016365  cmp     eax, 0E06D7363h
  ... truncated ...
```
