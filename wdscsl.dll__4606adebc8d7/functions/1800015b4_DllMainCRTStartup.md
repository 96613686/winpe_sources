# __DllMainCRTStartup

- ea: `0x1800015b4`
- end: `0x1800017c1`
- name: `__DllMainCRTStartup`
- size: `525`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180001570`

## callees

- `0x18000132c`
- `0x1800015b4`
- `0x1800018e7`
- `0x18000ce9c`
- `0x18000e010`

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
  if ( (_DWORD)fdwReason || dword_180015300 )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_180015304 = 1;
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
            if ( dword_180015304 )
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
0x1800015b4  mov     [rsp+lpvReserved], r8
0x1800015b9  mov     [rsp+arg_8], edx
0x1800015bd  mov     [rsp+arg_0], rcx
0x1800015c2  push    rbx
0x1800015c3  push    rsi
0x1800015c4  push    rdi
0x1800015c5  sub     rsp, 150h
0x1800015cc  mov     edi, edx
0x1800015ce  mov     rsi, rcx
0x1800015d1  mov     ebx, 1
0x1800015d6  mov     [rsp+168h+var_148], ebx
0x1800015da  cmp     edx, ebx
0x1800015dc  ja      short loc_1800015E4
0x1800015de  mov     cs:__native_dllmain_reason, edx
0x1800015e4  test    edx, edx
0x1800015e6  jnz     short loc_1800015FB
0x1800015e8  cmp     cs:dword_180015300, edx
0x1800015ee  jnz     short loc_1800015FB
0x1800015f0  xor     ebx, ebx
0x1800015f2  mov     [rsp+168h+var_148], ebx
0x1800015f6  jmp     loc_1800017A5
0x1800015fb  lea     eax, [rdx-1]
0x1800015fe  cmp     eax, 1
0x180001601  ja      loc_180001687
0x180001607  mov     rax, cs:_pRawDllMain
0x18000160e  test    rax, rax
0x180001611  jz      short loc_180001648
0x180001613  cmp     edx, 1
0x180001616  jnz     short loc_18000161E
0x180001618  mov     cs:dword_180015304, edx
0x18000161e  mov     r8, [rsp+168h+lpvReserved]
0x180001626  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000162b  mov     ebx, eax
0x18000162d  mov     [rsp+168h+var_148], eax
0x180001631  jmp     short loc_180001648
0x180001633  xor     ebx, ebx
0x180001635  mov     [rsp+168h+var_148], ebx
0x180001639  mov     edi, [rsp+168h+arg_8]
0x180001640  mov     rsi, [rsp+168h+arg_0]
0x180001648  test    ebx, ebx
0x18000164a  jz      loc_1800017A5
0x180001650  mov     r8, [rsp+168h+lpvReserved]
0x180001658  mov     edx, edi
0x18000165a  mov     rcx, rsi
0x18000165d  call    _CRT_INIT
0x180001662  mov     ebx, eax
0x180001664  mov     [rsp+168h+var_148], eax
0x180001668  jmp     short loc_18000167F
0x18000166a  xor     ebx, ebx
0x18000166c  mov     [rsp+168h+var_148], ebx
0x180001670  mov     edi, [rsp+168h+arg_8]
0x180001677  mov     rsi, [rsp+168h+arg_0]
0x18000167f  test    ebx, ebx
0x180001681  jz      loc_1800017A5
0x180001687  mov     r8, [rsp+168h+lpvReserved]; lpvReserved
0x18000168f  mov     edx, edi; fdwReason
0x180001691  mov     rcx, rsi; hinstDLL
0x180001694  call    DllMain
0x180001699  mov     ebx, eax
0x18000169b  mov     [rsp+168h+var_148], eax
0x18000169f  jmp     short loc_1800016B6
0x1800016a1  xor     ebx, ebx
0x1800016a3  mov     [rsp+168h+var_148], ebx
0x1800016a7  mov     edi, [rsp+168h+arg_8]
0x1800016ae  mov     rsi, [rsp+168h+arg_0]
0x1800016b6  cmp     edi, 1
0x1800016b9  jnz     short loc_180001731
0x1800016bb  test    ebx, ebx
0x1800016bd  jnz     short loc_180001731
0x1800016bf  xor     r8d, r8d; lpvReserved
0x1800016c2  xor     edx, edx; fdwReason
0x1800016c4  mov     rcx, rsi; hinstDLL
0x1800016c7  call    DllMain
0x1800016cc  jmp     short loc_1800016E1
0x1800016ce  mov     edi, [rsp+168h+arg_8]
0x1800016d5  mov     rsi, [rsp+168h+arg_0]
0x1800016dd  mov     ebx, [rsp+168h+var_148]
0x1800016e1  xor     r8d, r8d
0x1800016e4  xor     edx, edx
0x1800016e6  mov     rcx, rsi
0x1800016e9  call    _CRT_INIT
0x1800016ee  jmp     short loc_180001703
0x1800016f0  mov     edi, [rsp+168h+arg_8]
0x1800016f7  mov     rsi, [rsp+168h+arg_0]
0x1800016ff  mov     ebx, [rsp+168h+var_148]
0x180001703  mov     rax, cs:_pRawDllMain
0x18000170a  test    rax, rax
0x18000170d  jz      short loc_180001731
0x18000170f  xor     r8d, r8d
0x180001712  xor     edx, edx
0x180001714  mov     rcx, rsi
0x180001717  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000171c  jmp     short loc_180001731
0x18000171e  mov     edi, [rsp+168h+arg_8]
0x180001725  mov     rsi, [rsp+168h+arg_0]
0x18000172d  mov     ebx, [rsp+168h+var_148]
0x180001731  test    edi, edi
0x180001733  jz      short loc_18000173A
0x180001735  cmp     edi, 3
0x180001738  jnz     short loc_1800017A5
0x18000173a  mov     r8, [rsp+168h+lpvReserved]
0x180001742  mov     edx, edi
0x180001744  mov     rcx, rsi
0x180001747  call    _CRT_INIT
0x18000174c  mov     ebx, eax
0x18000174e  mov     [rsp+168h+var_148], eax
0x180001752  jmp     short loc_180001769
0x180001754  xor     ebx, ebx
0x180001756  mov     [rsp+168h+var_148], ebx
0x18000175a  mov     edi, [rsp+168h+arg_8]
0x180001761  mov     rsi, [rsp+168h+arg_0]
0x180001769  mov     rax, cs:_pRawDllMain
0x180001770  test    rax, rax
0x180001773  jz      short loc_1800017A5
0x180001775  cmp     cs:dword_180015304, 0
0x18000177c  jz      short loc_1800017A5
0x18000177e  mov     r8, [rsp+168h+lpvReserved]
0x180001786  mov     edx, edi
0x180001788  mov     rcx, rsi
0x18000178b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001790  mov     ebx, eax
0x180001792  mov     [rsp+168h+var_148], eax
0x180001796  jmp     short loc_1800017A5
0x180001798  xor     ebx, ebx
0x18000179a  mov     [rsp+168h+var_148], ebx
0x18000179e  mov     edi, [rsp+168h+arg_8]
0x1800017a5  cmp     edi, 1
0x1800017a8  ja      short loc_1800017B4
0x1800017aa  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x1800017b4  mov     eax, ebx
0x1800017b6  add     rsp, 150h
0x1800017bd  pop     rdi
0x1800017be  pop     rsi
0x1800017bf  pop     rbx
0x1800017c0  retn
0x18000d813  push    rbp
0x18000d815  sub     rsp, 20h
0x18000d819  mov     rbp, rdx
0x18000d81c  mov     [rbp+108h], rcx
0x18000d823  mov     rax, [rcx]
0x18000d826  mov     edx, [rax]
0x18000d828  mov     [rbp+0A4h], edx
0x18000d82e  mov     [rbp+0C8h], rcx
0x18000d835  mov     [rbp+28h], edx
0x18000d838  mov     eax, [rbp+28h]
0x18000d83b  cmp     eax, 0E06D7363h
0x18000d840  jnz     short loc_18000D856
0x18000d842  mov     rdx, [rbp+0C8h]
0x18000d849  mov     ecx, [rbp+28h]
0x18000d84c  call    _XcptFilter_0
0x18000d851  mov     [rbp+30h], eax
0x18000d854  jmp     short loc_18000D85D
0x18000d856  mov     dword ptr [rbp+30h], 0
0x18000d85d  mov     eax, [rbp+30h]
0x18000d860  add     rsp, 20h
0x18000d864  pop     rbp
0x18000d865  retn
0x18000d867  push    rbp
0x18000d869  sub     rsp, 20h
0x18000d86d  mov     rbp, rdx
0x18000d870  mov     [rbp+110h], rcx
0x18000d877  mov     rax, [rcx]
0x18000d87a  mov     edx, [rax]
0x18000d87c  mov     [rbp+0A8h], edx
0x18000d882  mov     [rbp+0D0h], rcx
0x18000d889  mov     [rbp+38h], edx
0x18000d88c  mov     eax, [rbp+38h]
0x18000d88f  cmp     eax, 0E06D7363h
0x18000d894  jnz     short loc_18000D8AA
0x18000d896  mov     rdx, [rbp+0D0h]
0x18000d89d  mov     ecx, [rbp+38h]
0x18000d8a0  call    _XcptFilter_0
0x18000d8a5  mov     [rbp+40h], eax
0x18000d8a8  jmp     short loc_18000D8B1
0x18000d8aa  mov     dword ptr [rbp+40h], 0
0x18000d8b1  mov     eax, [rbp+40h]
0x18000d8b4  add     rsp, 20h
0x18000d8b8  pop     rbp
0x18000d8b9  retn
0x18000d8bb  push    rbp
0x18000d8bd  sub     rsp, 20h
0x18000d8c1  mov     rbp, rdx
0x18000d8c4  mov     [rbp+118h], rcx
0x18000d8cb  mov     rax, [rcx]
0x18000d8ce  mov     edx, [rax]
0x18000d8d0  mov     [rbp+0ACh], edx
0x18000d8d6  mov     [rbp+0D8h], rcx
0x18000d8dd  mov     [rbp+48h], edx
0x18000d8e0  mov     eax, [rbp+48h]
0x18000d8e3  cmp     eax, 0E06D7363h
0x18000d8e8  jnz     short loc_18000D8FE
0x18000d8ea  mov     rdx, [rbp+0D8h]
0x18000d8f1  mov     ecx, [rbp+48h]
0x18000d8f4  call    _XcptFilter_0
0x18000d8f9  mov     [rbp+50h], eax
0x18000d8fc  jmp     short loc_18000D905
0x18000d8fe  mov     dword ptr [rbp+50h], 0
0x18000d905  mov     eax, [rbp+50h]
0x18000d908  add     rsp, 20h
0x18000d90c  pop     rbp
0x18000d90d  retn
0x18000d90f  push    rbp
0x18000d911  sub     rsp, 20h
0x18000d915  mov     rbp, rdx
0x18000d918  mov     [rbp+120h], rcx
0x18000d91f  mov     rax, [rcx]
0x18000d922  mov     edx, [rax]
0x18000d924  mov     [rbp+0B0h], edx
0x18000d92a  mov     [rbp+0E0h], rcx
0x18000d931  mov     [rbp+58h], edx
0x18000d934  mov     eax, [rbp+58h]
0x18000d937  cmp     eax, 0E06D7363h
0x18000d93c  jnz     short loc_18000D952
0x18000d93e  mov     rdx, [rbp+0E0h]
0x18000d945  mov     ecx, [rbp+58h]
0x18000d948  call    _XcptFilter_0
0x18000d94d  mov     [rbp+60h], eax
0x18000d950  jmp     short loc_18000D959
0x18000d952  mov     dword ptr [rbp+60h], 0
0x18000d959  mov     eax, [rbp+60h]
0x18000d95c  add     rsp, 20h
0x18000d960  pop     rbp
0x18000d961  retn
0x18000d963  push    rbp
0x18000d965  sub     rsp, 20h
0x18000d969  mov     rbp, rdx
0x18000d96c  mov     [rbp+128h], rcx
0x18000d973  mov     rax, [rcx]
0x18000d976  mov     edx, [rax]
0x18000d978  mov     [rbp+0B4h], edx
0x18000d97e  mov     [rbp+0E8h], rcx
0x18000d985  mov     [rbp+68h], edx
0x18000d988  mov     eax, [rbp+68h]
0x18000d98b  cmp     eax, 0E06D7363h
0x18000d990  jnz     short loc_18000D9A6
0x18000d992  mov     rdx, [rbp+0E8h]
0x18000d999  mov     ecx, [rbp+68h]
0x18000d99c  call    _XcptFilter_0
0x18000d9a1  mov     [rbp+70h], eax
0x18000d9a4  jmp     short loc_18000D9AD
0x18000d9a6  mov     dword ptr [rbp+70h], 0
0x18000d9ad  mov     eax, [rbp+70h]
0x18000d9b0  add     rsp, 20h
0x18000d9b4  pop     rbp
0x18000d9b5  retn
0x18000d9b7  push    rbp
0x18000d9b9  sub     rsp, 20h
0x18000d9bd  mov     rbp, rdx
0x18000d9c0  mov     [rbp+130h], rcx
0x18000d9c7  mov     rax, [rcx]
0x18000d9ca  mov     edx, [rax]
0x18000d9cc  mov     [rbp+0B8h], edx
0x18000d9d2  mov     [rbp+0F0h], rcx
0x18000d9d9  mov     [rbp+78h], edx
0x18000d9dc  mov     eax, [rbp+78h]
0x18000d9df  cmp     eax, 0E06D7363h
0x18000d9e4  jnz     short loc_18000D9FD
0x18000d9e6  mov     rdx, [rbp+0F0h]
0x18000d9ed  mov     ecx, [rbp+78h]
0x18000d9f0  call    _XcptFilter_0
0x18000d9f5  mov     [rbp+80h], eax
0x18000d9fb  jmp     short loc_18000DA07
0x18000d9fd  mov     dword ptr [rbp+80h], 0
0x18000da07  mov     eax, [rbp+80h]
0x18000da0d  add     rsp, 20h
0x18000da11  pop     rbp
0x18000da12  retn
0x18000da14  push    rbp
0x18000da16  sub     rsp, 20h
0x18000da1a  mov     rbp, rdx
0x18000da1d  mov     [rbp+138h], rcx
0x18000da24  mov     rax, [rcx]
0x18000da27  mov     edx, [rax]
0x18000da29  mov     [rbp+0BCh], edx
0x18000da2f  mov     [rbp+0F8h], rcx
0x18000da36  mov     [rbp+88h], edx
0x18000da3c  mov     eax, [rbp+88h]
0x18000da42  cmp     eax, 0E06D7363h
0x18000da47  jnz     short loc_18000DA63
0x18000da49  mov     rdx, [rbp+0F8h]
0x18000da50  mov     ecx, [rbp+88h]
0x18000da56  call    _XcptFilter_0
0x18000da5b  mov     [rbp+90h], eax
0x18000da61  jmp     short loc_18000DA6D
0x18000da63  mov     dword ptr [rbp+90h], 0
0x18000da6d  mov     eax, [rbp+90h]
0x18000da73  add     rsp, 20h
0x18000da77  pop     rbp
0x18000da78  retn
0x18000da7a  push    rbp
0x18000da7c  sub     rsp, 20h
0x18000da80  mov     rbp, rdx
0x18000da83  mov     [rbp+140h], rcx
0x18000da8a  mov     rax, [rcx]
0x18000da8d  mov     edx, [rax]
0x18000da8f  mov     [rbp+0C0h], edx
0x18000da95  mov     [rbp+100h], rcx
0x18000da9c  mov     [rbp+98h], edx
0x18000daa2  mov     eax, [rbp+98h]
0x18000daa8  cmp     eax, 0E06D7363h
  ... truncated ...
```
