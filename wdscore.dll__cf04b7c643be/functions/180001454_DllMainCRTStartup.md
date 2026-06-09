# __DllMainCRTStartup

- ea: `0x180001454`
- end: `0x180001660`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180001410`

## callees

- `0x1800011e0`
- `0x180001454`
- `0x180001c26`
- `0x18000b610`
- `0x180027580`

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
  if ( (_DWORD)fdwReason || dword_18003A7C0 )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_18003A7C4 = 1;
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
            if ( dword_18003A7C4 )
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
0x180001454  mov     [rsp+lpvReserved], r8
0x180001459  mov     [rsp+arg_8], edx
0x18000145d  mov     [rsp+arg_0], rcx
0x180001462  push    rbx
0x180001463  push    rsi
0x180001464  push    rdi
0x180001465  sub     rsp, 0F0h
0x18000146c  mov     edi, edx
0x18000146e  mov     rsi, rcx
0x180001471  mov     ebx, 1
0x180001476  cmp     edx, ebx
0x180001478  ja      short loc_180001480
0x18000147a  mov     cs:__native_dllmain_reason, edx
0x180001480  test    edx, edx
0x180001482  jnz     short loc_180001497
0x180001484  cmp     cs:dword_18003A7C0, edx
0x18000148a  jnz     short loc_180001497
0x18000148c  xor     ebx, ebx
0x18000148e  mov     [rsp+108h+var_E8], ebx
0x180001492  jmp     loc_180001644
0x180001497  lea     eax, [rdx-1]
0x18000149a  cmp     eax, 1
0x18000149d  ja      loc_180001524
0x1800014a3  mov     rax, cs:_pRawDllMain
0x1800014aa  test    rax, rax
0x1800014ad  jz      short loc_1800014E5
0x1800014af  cmp     edx, 1
0x1800014b2  jnz     short loc_1800014BA
0x1800014b4  mov     cs:dword_18003A7C4, edx
0x1800014ba  mov     r8, [rsp+108h+lpvReserved]
0x1800014c2  call    cs:__guard_dispatch_icall_fptr
0x1800014c8  mov     ebx, eax
0x1800014ca  mov     [rsp+108h+var_E8], eax
0x1800014ce  jmp     short loc_1800014E5
0x1800014d0  xor     ebx, ebx
0x1800014d2  mov     [rsp+108h+var_E8], ebx
0x1800014d6  mov     edi, [rsp+108h+arg_8]
0x1800014dd  mov     rsi, [rsp+108h+arg_0]
0x1800014e5  test    ebx, ebx
0x1800014e7  jz      loc_180001644
0x1800014ed  mov     r8, [rsp+108h+lpvReserved]
0x1800014f5  mov     edx, edi
0x1800014f7  mov     rcx, rsi
0x1800014fa  call    _CRT_INIT
0x1800014ff  mov     ebx, eax
0x180001501  mov     [rsp+108h+var_E8], eax
0x180001505  jmp     short loc_18000151C
0x180001507  xor     ebx, ebx
0x180001509  mov     [rsp+108h+var_E8], ebx
0x18000150d  mov     edi, [rsp+108h+arg_8]
0x180001514  mov     rsi, [rsp+108h+arg_0]
0x18000151c  test    ebx, ebx
0x18000151e  jz      loc_180001644
0x180001524  mov     r8, [rsp+108h+lpvReserved]; lpvReserved
0x18000152c  mov     edx, edi; fdwReason
0x18000152e  mov     rcx, rsi; hinstDLL
0x180001531  call    DllMain
0x180001536  mov     ebx, eax
0x180001538  mov     [rsp+108h+var_E8], eax
0x18000153c  jmp     short loc_180001553
0x18000153e  xor     ebx, ebx
0x180001540  mov     [rsp+108h+var_E8], ebx
0x180001544  mov     edi, [rsp+108h+arg_8]
0x18000154b  mov     rsi, [rsp+108h+arg_0]
0x180001553  cmp     edi, 1
0x180001556  jnz     short loc_1800015CF
0x180001558  test    ebx, ebx
0x18000155a  jnz     short loc_1800015CF
0x18000155c  xor     r8d, r8d; lpvReserved
0x18000155f  xor     edx, edx; fdwReason
0x180001561  mov     rcx, rsi; hinstDLL
0x180001564  call    DllMain
0x180001569  jmp     short loc_18000157E
0x18000156b  mov     edi, [rsp+108h+arg_8]
0x180001572  mov     rsi, [rsp+108h+arg_0]
0x18000157a  mov     ebx, [rsp+108h+var_E8]
0x18000157e  xor     r8d, r8d
0x180001581  xor     edx, edx
0x180001583  mov     rcx, rsi
0x180001586  call    _CRT_INIT
0x18000158b  jmp     short loc_1800015A0
0x18000158d  mov     edi, [rsp+108h+arg_8]
0x180001594  mov     rsi, [rsp+108h+arg_0]
0x18000159c  mov     ebx, [rsp+108h+var_E8]
0x1800015a0  mov     rax, cs:_pRawDllMain
0x1800015a7  test    rax, rax
0x1800015aa  jz      short loc_1800015CF
0x1800015ac  xor     r8d, r8d
0x1800015af  xor     edx, edx
0x1800015b1  mov     rcx, rsi
0x1800015b4  call    cs:__guard_dispatch_icall_fptr
0x1800015ba  jmp     short loc_1800015CF
0x1800015bc  mov     edi, [rsp+108h+arg_8]
0x1800015c3  mov     rsi, [rsp+108h+arg_0]
0x1800015cb  mov     ebx, [rsp+108h+var_E8]
0x1800015cf  test    edi, edi
0x1800015d1  jz      short loc_1800015D8
0x1800015d3  cmp     edi, 3
0x1800015d6  jnz     short loc_180001644
0x1800015d8  mov     r8, [rsp+108h+lpvReserved]
0x1800015e0  mov     edx, edi
0x1800015e2  mov     rcx, rsi
0x1800015e5  call    _CRT_INIT
0x1800015ea  mov     ebx, eax
0x1800015ec  mov     [rsp+108h+var_E8], eax
0x1800015f0  jmp     short loc_180001607
0x1800015f2  xor     ebx, ebx
0x1800015f4  mov     [rsp+108h+var_E8], ebx
0x1800015f8  mov     edi, [rsp+108h+arg_8]
0x1800015ff  mov     rsi, [rsp+108h+arg_0]
0x180001607  mov     rax, cs:_pRawDllMain
0x18000160e  test    rax, rax
0x180001611  jz      short loc_180001644
0x180001613  cmp     cs:dword_18003A7C4, 0
0x18000161a  jz      short loc_180001644
0x18000161c  mov     r8, [rsp+108h+lpvReserved]
0x180001624  mov     edx, edi
0x180001626  mov     rcx, rsi
0x180001629  call    cs:__guard_dispatch_icall_fptr
0x18000162f  mov     ebx, eax
0x180001631  mov     [rsp+108h+var_E8], eax
0x180001635  jmp     short loc_180001644
0x180001637  xor     ebx, ebx
0x180001639  mov     [rsp+108h+var_E8], ebx
0x18000163d  mov     edi, [rsp+108h+arg_8]
0x180001644  cmp     edi, 1
0x180001647  ja      short loc_180001653
0x180001649  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x180001653  mov     eax, ebx
0x180001655  add     rsp, 0F0h
0x18000165c  pop     rdi
0x18000165d  pop     rsi
0x18000165e  pop     rbx
0x18000165f  retn
0x180027623  push    rbp
0x180027625  sub     rsp, 20h
0x180027629  mov     rbp, rdx
0x18002762c  mov     rax, [rcx]
0x18002762f  mov     edx, [rax]
0x180027631  mov     [rbp+0A8h], rcx
0x180027638  mov     [rbp+28h], edx
0x18002763b  mov     eax, [rbp+28h]
0x18002763e  cmp     eax, 0E06D7363h
0x180027643  jnz     short loc_180027659
0x180027645  mov     rdx, [rbp+0A8h]
0x18002764c  mov     ecx, [rbp+28h]
0x18002764f  call    _XcptFilter_0
0x180027654  mov     [rbp+30h], eax
0x180027657  jmp     short loc_180027660
0x180027659  mov     dword ptr [rbp+30h], 0
0x180027660  mov     eax, [rbp+30h]
0x180027663  add     rsp, 20h
0x180027667  pop     rbp
0x180027668  retn
0x18002766a  push    rbp
0x18002766c  sub     rsp, 20h
0x180027670  mov     rbp, rdx
0x180027673  mov     rax, [rcx]
0x180027676  mov     edx, [rax]
0x180027678  mov     [rbp+0B0h], rcx
0x18002767f  mov     [rbp+38h], edx
0x180027682  mov     eax, [rbp+38h]
0x180027685  cmp     eax, 0E06D7363h
0x18002768a  jnz     short loc_1800276A0
0x18002768c  mov     rdx, [rbp+0B0h]
0x180027693  mov     ecx, [rbp+38h]
0x180027696  call    _XcptFilter_0
0x18002769b  mov     [rbp+40h], eax
0x18002769e  jmp     short loc_1800276A7
0x1800276a0  mov     dword ptr [rbp+40h], 0
0x1800276a7  mov     eax, [rbp+40h]
0x1800276aa  add     rsp, 20h
0x1800276ae  pop     rbp
0x1800276af  retn
0x1800276b1  push    rbp
0x1800276b3  sub     rsp, 20h
0x1800276b7  mov     rbp, rdx
0x1800276ba  mov     rax, [rcx]
0x1800276bd  mov     edx, [rax]
0x1800276bf  mov     [rbp+0B8h], rcx
0x1800276c6  mov     [rbp+48h], edx
0x1800276c9  mov     eax, [rbp+48h]
0x1800276cc  cmp     eax, 0E06D7363h
0x1800276d1  jnz     short loc_1800276E7
0x1800276d3  mov     rdx, [rbp+0B8h]
0x1800276da  mov     ecx, [rbp+48h]
0x1800276dd  call    _XcptFilter_0
0x1800276e2  mov     [rbp+50h], eax
0x1800276e5  jmp     short loc_1800276EE
0x1800276e7  mov     dword ptr [rbp+50h], 0
0x1800276ee  mov     eax, [rbp+50h]
0x1800276f1  add     rsp, 20h
0x1800276f5  pop     rbp
0x1800276f6  retn
0x1800276f8  push    rbp
0x1800276fa  sub     rsp, 20h
0x1800276fe  mov     rbp, rdx
0x180027701  mov     rax, [rcx]
0x180027704  mov     edx, [rax]
0x180027706  mov     [rbp+0C0h], rcx
0x18002770d  mov     [rbp+58h], edx
0x180027710  mov     eax, [rbp+58h]
0x180027713  cmp     eax, 0E06D7363h
0x180027718  jnz     short loc_18002772E
0x18002771a  mov     rdx, [rbp+0C0h]
0x180027721  mov     ecx, [rbp+58h]
0x180027724  call    _XcptFilter_0
0x180027729  mov     [rbp+60h], eax
0x18002772c  jmp     short loc_180027735
0x18002772e  mov     dword ptr [rbp+60h], 0
0x180027735  mov     eax, [rbp+60h]
0x180027738  add     rsp, 20h
0x18002773c  pop     rbp
0x18002773d  retn
0x18002773f  push    rbp
0x180027741  sub     rsp, 20h
0x180027745  mov     rbp, rdx
0x180027748  mov     rax, [rcx]
0x18002774b  mov     edx, [rax]
0x18002774d  mov     [rbp+0C8h], rcx
0x180027754  mov     [rbp+68h], edx
0x180027757  mov     eax, [rbp+68h]
0x18002775a  cmp     eax, 0E06D7363h
0x18002775f  jnz     short loc_180027775
0x180027761  mov     rdx, [rbp+0C8h]
0x180027768  mov     ecx, [rbp+68h]
0x18002776b  call    _XcptFilter_0
0x180027770  mov     [rbp+70h], eax
0x180027773  jmp     short loc_18002777C
0x180027775  mov     dword ptr [rbp+70h], 0
0x18002777c  mov     eax, [rbp+70h]
0x18002777f  add     rsp, 20h
0x180027783  pop     rbp
0x180027784  retn
0x180027786  push    rbp
0x180027788  sub     rsp, 20h
0x18002778c  mov     rbp, rdx
0x18002778f  mov     rax, [rcx]
0x180027792  mov     edx, [rax]
0x180027794  mov     [rbp+0D0h], rcx
0x18002779b  mov     [rbp+78h], edx
0x18002779e  mov     eax, [rbp+78h]
0x1800277a1  cmp     eax, 0E06D7363h
0x1800277a6  jnz     short loc_1800277BF
0x1800277a8  mov     rdx, [rbp+0D0h]
0x1800277af  mov     ecx, [rbp+78h]
0x1800277b2  call    _XcptFilter_0
0x1800277b7  mov     [rbp+80h], eax
0x1800277bd  jmp     short loc_1800277C9
0x1800277bf  mov     dword ptr [rbp+80h], 0
0x1800277c9  mov     eax, [rbp+80h]
0x1800277cf  add     rsp, 20h
0x1800277d3  pop     rbp
0x1800277d4  retn
0x1800277d6  push    rbp
0x1800277d8  sub     rsp, 20h
0x1800277dc  mov     rbp, rdx
0x1800277df  mov     rax, [rcx]
0x1800277e2  mov     edx, [rax]
0x1800277e4  mov     [rbp+0D8h], rcx
0x1800277eb  mov     [rbp+88h], edx
0x1800277f1  mov     eax, [rbp+88h]
0x1800277f7  cmp     eax, 0E06D7363h
0x1800277fc  jnz     short loc_180027818
0x1800277fe  mov     rdx, [rbp+0D8h]
0x180027805  mov     ecx, [rbp+88h]
0x18002780b  call    _XcptFilter_0
0x180027810  mov     [rbp+90h], eax
0x180027816  jmp     short loc_180027822
0x180027818  mov     dword ptr [rbp+90h], 0
0x180027822  mov     eax, [rbp+90h]
0x180027828  add     rsp, 20h
0x18002782c  pop     rbp
0x18002782d  retn
0x18002782f  push    rbp
0x180027831  sub     rsp, 20h
0x180027835  mov     rbp, rdx
0x180027838  mov     rax, [rcx]
0x18002783b  mov     edx, [rax]
0x18002783d  mov     [rbp+0E0h], rcx
0x180027844  mov     [rbp+98h], edx
0x18002784a  mov     eax, [rbp+98h]
0x180027850  cmp     eax, 0E06D7363h
0x180027855  jnz     short loc_180027871
0x180027857  mov     rdx, [rbp+0E0h]
0x18002785e  mov     ecx, [rbp+98h]
0x180027864  call    _XcptFilter_0
0x180027869  mov     [rbp+0A0h], eax
0x18002786f  jmp     short loc_18002787B
0x180027871  mov     dword ptr [rbp+0A0h], 0
0x18002787b  mov     eax, [rbp+0A0h]
0x180027881  add     rsp, 20h
0x180027885  pop     rbp
0x180027886  retn
0x180027888  push    rbp
0x18002788a  sub     rsp, 20h
0x18002788e  mov     rbp, rdx
0x180027891  cmp     dword ptr [rbp+118h], 1
0x180027898  ja      short loc_1800278A4
0x18002789a  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
