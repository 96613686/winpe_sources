# __DllMainCRTStartup

- ea: `0x180001714`
- end: `0x180001920`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1800016d0`

## callees

- `0x1800014a0`
- `0x180001714`
- `0x180001e76`
- `0x180005ca0`
- `0x18001bfb0`

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
  if ( (_DWORD)fdwReason || dword_18002E37C )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_18002E380 = 1;
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
            if ( dword_18002E380 )
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
0x180001714  mov     [rsp+lpvReserved], r8
0x180001719  mov     [rsp+arg_8], edx
0x18000171d  mov     [rsp+arg_0], rcx
0x180001722  push    rbx
0x180001723  push    rsi
0x180001724  push    rdi
0x180001725  sub     rsp, 0F0h
0x18000172c  mov     edi, edx
0x18000172e  mov     rsi, rcx
0x180001731  mov     ebx, 1
0x180001736  cmp     edx, ebx
0x180001738  ja      short loc_180001740
0x18000173a  mov     cs:__native_dllmain_reason, edx
0x180001740  test    edx, edx
0x180001742  jnz     short loc_180001757
0x180001744  cmp     cs:dword_18002E37C, edx
0x18000174a  jnz     short loc_180001757
0x18000174c  xor     ebx, ebx
0x18000174e  mov     [rsp+108h+var_E8], ebx
0x180001752  jmp     loc_180001904
0x180001757  lea     eax, [rdx-1]
0x18000175a  cmp     eax, 1
0x18000175d  ja      loc_1800017E4
0x180001763  mov     rax, cs:_pRawDllMain
0x18000176a  test    rax, rax
0x18000176d  jz      short loc_1800017A5
0x18000176f  cmp     edx, 1
0x180001772  jnz     short loc_18000177A
0x180001774  mov     cs:dword_18002E380, edx
0x18000177a  mov     r8, [rsp+108h+lpvReserved]
0x180001782  call    cs:__guard_dispatch_icall_fptr
0x180001788  mov     ebx, eax
0x18000178a  mov     [rsp+108h+var_E8], eax
0x18000178e  jmp     short loc_1800017A5
0x180001790  xor     ebx, ebx
0x180001792  mov     [rsp+108h+var_E8], ebx
0x180001796  mov     edi, [rsp+108h+arg_8]
0x18000179d  mov     rsi, [rsp+108h+arg_0]
0x1800017a5  test    ebx, ebx
0x1800017a7  jz      loc_180001904
0x1800017ad  mov     r8, [rsp+108h+lpvReserved]
0x1800017b5  mov     edx, edi
0x1800017b7  mov     rcx, rsi
0x1800017ba  call    _CRT_INIT
0x1800017bf  mov     ebx, eax
0x1800017c1  mov     [rsp+108h+var_E8], eax
0x1800017c5  jmp     short loc_1800017DC
0x1800017c7  xor     ebx, ebx
0x1800017c9  mov     [rsp+108h+var_E8], ebx
0x1800017cd  mov     edi, [rsp+108h+arg_8]
0x1800017d4  mov     rsi, [rsp+108h+arg_0]
0x1800017dc  test    ebx, ebx
0x1800017de  jz      loc_180001904
0x1800017e4  mov     r8, [rsp+108h+lpvReserved]; lpvReserved
0x1800017ec  mov     edx, edi; fdwReason
0x1800017ee  mov     rcx, rsi; hinstDLL
0x1800017f1  call    DllMain
0x1800017f6  mov     ebx, eax
0x1800017f8  mov     [rsp+108h+var_E8], eax
0x1800017fc  jmp     short loc_180001813
0x1800017fe  xor     ebx, ebx
0x180001800  mov     [rsp+108h+var_E8], ebx
0x180001804  mov     edi, [rsp+108h+arg_8]
0x18000180b  mov     rsi, [rsp+108h+arg_0]
0x180001813  cmp     edi, 1
0x180001816  jnz     short loc_18000188F
0x180001818  test    ebx, ebx
0x18000181a  jnz     short loc_18000188F
0x18000181c  xor     r8d, r8d; lpvReserved
0x18000181f  xor     edx, edx; fdwReason
0x180001821  mov     rcx, rsi; hinstDLL
0x180001824  call    DllMain
0x180001829  jmp     short loc_18000183E
0x18000182b  mov     edi, [rsp+108h+arg_8]
0x180001832  mov     rsi, [rsp+108h+arg_0]
0x18000183a  mov     ebx, [rsp+108h+var_E8]
0x18000183e  xor     r8d, r8d
0x180001841  xor     edx, edx
0x180001843  mov     rcx, rsi
0x180001846  call    _CRT_INIT
0x18000184b  jmp     short loc_180001860
0x18000184d  mov     edi, [rsp+108h+arg_8]
0x180001854  mov     rsi, [rsp+108h+arg_0]
0x18000185c  mov     ebx, [rsp+108h+var_E8]
0x180001860  mov     rax, cs:_pRawDllMain
0x180001867  test    rax, rax
0x18000186a  jz      short loc_18000188F
0x18000186c  xor     r8d, r8d
0x18000186f  xor     edx, edx
0x180001871  mov     rcx, rsi
0x180001874  call    cs:__guard_dispatch_icall_fptr
0x18000187a  jmp     short loc_18000188F
0x18000187c  mov     edi, [rsp+108h+arg_8]
0x180001883  mov     rsi, [rsp+108h+arg_0]
0x18000188b  mov     ebx, [rsp+108h+var_E8]
0x18000188f  test    edi, edi
0x180001891  jz      short loc_180001898
0x180001893  cmp     edi, 3
0x180001896  jnz     short loc_180001904
0x180001898  mov     r8, [rsp+108h+lpvReserved]
0x1800018a0  mov     edx, edi
0x1800018a2  mov     rcx, rsi
0x1800018a5  call    _CRT_INIT
0x1800018aa  mov     ebx, eax
0x1800018ac  mov     [rsp+108h+var_E8], eax
0x1800018b0  jmp     short loc_1800018C7
0x1800018b2  xor     ebx, ebx
0x1800018b4  mov     [rsp+108h+var_E8], ebx
0x1800018b8  mov     edi, [rsp+108h+arg_8]
0x1800018bf  mov     rsi, [rsp+108h+arg_0]
0x1800018c7  mov     rax, cs:_pRawDllMain
0x1800018ce  test    rax, rax
0x1800018d1  jz      short loc_180001904
0x1800018d3  cmp     cs:dword_18002E380, 0
0x1800018da  jz      short loc_180001904
0x1800018dc  mov     r8, [rsp+108h+lpvReserved]
0x1800018e4  mov     edx, edi
0x1800018e6  mov     rcx, rsi
0x1800018e9  call    cs:__guard_dispatch_icall_fptr
0x1800018ef  mov     ebx, eax
0x1800018f1  mov     [rsp+108h+var_E8], eax
0x1800018f5  jmp     short loc_180001904
0x1800018f7  xor     ebx, ebx
0x1800018f9  mov     [rsp+108h+var_E8], ebx
0x1800018fd  mov     edi, [rsp+108h+arg_8]
0x180001904  cmp     edi, 1
0x180001907  ja      short loc_180001913
0x180001909  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x180001913  mov     eax, ebx
0x180001915  add     rsp, 0F0h
0x18000191c  pop     rdi
0x18000191d  pop     rsi
0x18000191e  pop     rbx
0x18000191f  retn
0x18001c053  push    rbp
0x18001c055  sub     rsp, 20h
0x18001c059  mov     rbp, rdx
0x18001c05c  mov     rax, [rcx]
0x18001c05f  mov     edx, [rax]
0x18001c061  mov     [rbp+0A8h], rcx
0x18001c068  mov     [rbp+28h], edx
0x18001c06b  mov     eax, [rbp+28h]
0x18001c06e  cmp     eax, 0E06D7363h
0x18001c073  jnz     short loc_18001C089
0x18001c075  mov     rdx, [rbp+0A8h]
0x18001c07c  mov     ecx, [rbp+28h]
0x18001c07f  call    _XcptFilter_0
0x18001c084  mov     [rbp+30h], eax
0x18001c087  jmp     short loc_18001C090
0x18001c089  mov     dword ptr [rbp+30h], 0
0x18001c090  mov     eax, [rbp+30h]
0x18001c093  add     rsp, 20h
0x18001c097  pop     rbp
0x18001c098  retn
0x18001c09a  push    rbp
0x18001c09c  sub     rsp, 20h
0x18001c0a0  mov     rbp, rdx
0x18001c0a3  mov     rax, [rcx]
0x18001c0a6  mov     edx, [rax]
0x18001c0a8  mov     [rbp+0B0h], rcx
0x18001c0af  mov     [rbp+38h], edx
0x18001c0b2  mov     eax, [rbp+38h]
0x18001c0b5  cmp     eax, 0E06D7363h
0x18001c0ba  jnz     short loc_18001C0D0
0x18001c0bc  mov     rdx, [rbp+0B0h]
0x18001c0c3  mov     ecx, [rbp+38h]
0x18001c0c6  call    _XcptFilter_0
0x18001c0cb  mov     [rbp+40h], eax
0x18001c0ce  jmp     short loc_18001C0D7
0x18001c0d0  mov     dword ptr [rbp+40h], 0
0x18001c0d7  mov     eax, [rbp+40h]
0x18001c0da  add     rsp, 20h
0x18001c0de  pop     rbp
0x18001c0df  retn
0x18001c0e1  push    rbp
0x18001c0e3  sub     rsp, 20h
0x18001c0e7  mov     rbp, rdx
0x18001c0ea  mov     rax, [rcx]
0x18001c0ed  mov     edx, [rax]
0x18001c0ef  mov     [rbp+0B8h], rcx
0x18001c0f6  mov     [rbp+48h], edx
0x18001c0f9  mov     eax, [rbp+48h]
0x18001c0fc  cmp     eax, 0E06D7363h
0x18001c101  jnz     short loc_18001C117
0x18001c103  mov     rdx, [rbp+0B8h]
0x18001c10a  mov     ecx, [rbp+48h]
0x18001c10d  call    _XcptFilter_0
0x18001c112  mov     [rbp+50h], eax
0x18001c115  jmp     short loc_18001C11E
0x18001c117  mov     dword ptr [rbp+50h], 0
0x18001c11e  mov     eax, [rbp+50h]
0x18001c121  add     rsp, 20h
0x18001c125  pop     rbp
0x18001c126  retn
0x18001c128  push    rbp
0x18001c12a  sub     rsp, 20h
0x18001c12e  mov     rbp, rdx
0x18001c131  mov     rax, [rcx]
0x18001c134  mov     edx, [rax]
0x18001c136  mov     [rbp+0C0h], rcx
0x18001c13d  mov     [rbp+58h], edx
0x18001c140  mov     eax, [rbp+58h]
0x18001c143  cmp     eax, 0E06D7363h
0x18001c148  jnz     short loc_18001C15E
0x18001c14a  mov     rdx, [rbp+0C0h]
0x18001c151  mov     ecx, [rbp+58h]
0x18001c154  call    _XcptFilter_0
0x18001c159  mov     [rbp+60h], eax
0x18001c15c  jmp     short loc_18001C165
0x18001c15e  mov     dword ptr [rbp+60h], 0
0x18001c165  mov     eax, [rbp+60h]
0x18001c168  add     rsp, 20h
0x18001c16c  pop     rbp
0x18001c16d  retn
0x18001c16f  push    rbp
0x18001c171  sub     rsp, 20h
0x18001c175  mov     rbp, rdx
0x18001c178  mov     rax, [rcx]
0x18001c17b  mov     edx, [rax]
0x18001c17d  mov     [rbp+0C8h], rcx
0x18001c184  mov     [rbp+68h], edx
0x18001c187  mov     eax, [rbp+68h]
0x18001c18a  cmp     eax, 0E06D7363h
0x18001c18f  jnz     short loc_18001C1A5
0x18001c191  mov     rdx, [rbp+0C8h]
0x18001c198  mov     ecx, [rbp+68h]
0x18001c19b  call    _XcptFilter_0
0x18001c1a0  mov     [rbp+70h], eax
0x18001c1a3  jmp     short loc_18001C1AC
0x18001c1a5  mov     dword ptr [rbp+70h], 0
0x18001c1ac  mov     eax, [rbp+70h]
0x18001c1af  add     rsp, 20h
0x18001c1b3  pop     rbp
0x18001c1b4  retn
0x18001c1b6  push    rbp
0x18001c1b8  sub     rsp, 20h
0x18001c1bc  mov     rbp, rdx
0x18001c1bf  mov     rax, [rcx]
0x18001c1c2  mov     edx, [rax]
0x18001c1c4  mov     [rbp+0D0h], rcx
0x18001c1cb  mov     [rbp+78h], edx
0x18001c1ce  mov     eax, [rbp+78h]
0x18001c1d1  cmp     eax, 0E06D7363h
0x18001c1d6  jnz     short loc_18001C1EF
0x18001c1d8  mov     rdx, [rbp+0D0h]
0x18001c1df  mov     ecx, [rbp+78h]
0x18001c1e2  call    _XcptFilter_0
0x18001c1e7  mov     [rbp+80h], eax
0x18001c1ed  jmp     short loc_18001C1F9
0x18001c1ef  mov     dword ptr [rbp+80h], 0
0x18001c1f9  mov     eax, [rbp+80h]
0x18001c1ff  add     rsp, 20h
0x18001c203  pop     rbp
0x18001c204  retn
0x18001c206  push    rbp
0x18001c208  sub     rsp, 20h
0x18001c20c  mov     rbp, rdx
0x18001c20f  mov     rax, [rcx]
0x18001c212  mov     edx, [rax]
0x18001c214  mov     [rbp+0D8h], rcx
0x18001c21b  mov     [rbp+88h], edx
0x18001c221  mov     eax, [rbp+88h]
0x18001c227  cmp     eax, 0E06D7363h
0x18001c22c  jnz     short loc_18001C248
0x18001c22e  mov     rdx, [rbp+0D8h]
0x18001c235  mov     ecx, [rbp+88h]
0x18001c23b  call    _XcptFilter_0
0x18001c240  mov     [rbp+90h], eax
0x18001c246  jmp     short loc_18001C252
0x18001c248  mov     dword ptr [rbp+90h], 0
0x18001c252  mov     eax, [rbp+90h]
0x18001c258  add     rsp, 20h
0x18001c25c  pop     rbp
0x18001c25d  retn
0x18001c25f  push    rbp
0x18001c261  sub     rsp, 20h
0x18001c265  mov     rbp, rdx
0x18001c268  mov     rax, [rcx]
0x18001c26b  mov     edx, [rax]
0x18001c26d  mov     [rbp+0E0h], rcx
0x18001c274  mov     [rbp+98h], edx
0x18001c27a  mov     eax, [rbp+98h]
0x18001c280  cmp     eax, 0E06D7363h
0x18001c285  jnz     short loc_18001C2A1
0x18001c287  mov     rdx, [rbp+0E0h]
0x18001c28e  mov     ecx, [rbp+98h]
0x18001c294  call    _XcptFilter_0
0x18001c299  mov     [rbp+0A0h], eax
0x18001c29f  jmp     short loc_18001C2AB
0x18001c2a1  mov     dword ptr [rbp+0A0h], 0
0x18001c2ab  mov     eax, [rbp+0A0h]
0x18001c2b1  add     rsp, 20h
0x18001c2b5  pop     rbp
0x18001c2b6  retn
0x18001c2b8  push    rbp
0x18001c2ba  sub     rsp, 20h
0x18001c2be  mov     rbp, rdx
0x18001c2c1  cmp     dword ptr [rbp+118h], 1
0x18001c2c8  ja      short loc_18001C2D4
0x18001c2ca  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
