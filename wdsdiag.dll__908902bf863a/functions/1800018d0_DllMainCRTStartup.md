# __DllMainCRTStartup

- ea: `0x1800018d0`
- end: `0x180001b1c`
- name: `__DllMainCRTStartup`
- size: `588`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180001890`

## callees

- `0x180001654`
- `0x1800018d0`
- `0x180001bf8`
- `0x180001db0`
- `0x180002220`

## pseudocode

```c
__int64 __fastcall _DllMainCRTStartup(HINSTANCE hinstDLL, __int64 fdwReason, void *a3)
{
  DWORD v3; // edi
  unsigned int v5; // ebx
  int v6; // eax

  v3 = fdwReason;
  v5 = 1;
  if ( (unsigned int)fdwReason <= 1 )
    _native_dllmain_reason = fdwReason;
  if ( (_DWORD)fdwReason || dword_180005080 )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      v6 = dword_180005084;
      if ( (_DWORD)fdwReason == 1 )
        v6 = 1;
      dword_180005084 = v6;
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
            if ( dword_180005084 )
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
0x1800018d0  mov     rax, rsp
0x1800018d3  mov     [rax+20h], rbx
0x1800018d7  mov     [rax+18h], r8
0x1800018db  mov     [rax+10h], edx
0x1800018de  mov     [rax+8], rcx
0x1800018e2  push    rsi
0x1800018e3  push    rdi
0x1800018e4  push    r14
0x1800018e6  sub     rsp, 150h
0x1800018ed  mov     edi, edx
0x1800018ef  mov     r14, rcx
0x1800018f2  mov     esi, 1
0x1800018f7  mov     ebx, esi
0x1800018f9  mov     [rsp+168h+var_148], ebx
0x1800018fd  cmp     edx, esi
0x1800018ff  ja      short loc_180001907
0x180001901  mov     cs:__native_dllmain_reason, edx
0x180001907  test    edx, edx
0x180001909  jnz     short loc_18000191E
0x18000190b  cmp     cs:dword_180005080, edx
0x180001911  jnz     short loc_18000191E
0x180001913  xor     ebx, ebx
0x180001915  mov     [rsp+168h+var_148], ebx
0x180001919  jmp     loc_180001AF8
0x18000191e  lea     eax, [rdx-1]
0x180001921  cmp     eax, esi
0x180001923  ja      loc_1800019B9
0x180001929  mov     r9, cs:_pRawDllMain
0x180001930  test    r9, r9
0x180001933  jz      short loc_180001977
0x180001935  mov     eax, cs:dword_180005084
0x18000193b  cmp     edx, esi
0x18000193d  cmovz   eax, esi
0x180001940  mov     cs:dword_180005084, eax
0x180001946  mov     r8, [rsp+168h+lpvReserved]
0x18000194e  mov     rax, r9
0x180001951  call    cs:__guard_dispatch_icall_fptr
0x180001957  mov     ebx, eax
0x180001959  mov     [rsp+168h+var_148], eax
0x18000195d  jmp     short loc_180001977
0x18000195f  xor     ebx, ebx
0x180001961  mov     [rsp+168h+var_148], ebx
0x180001965  lea     esi, [rbx+1]
0x180001968  mov     edi, [rsp+168h+arg_8]
0x18000196f  mov     r14, [rsp+168h+arg_0]
0x180001977  test    ebx, ebx
0x180001979  jz      loc_180001AF8
0x18000197f  mov     r8, [rsp+168h+lpvReserved]
0x180001987  mov     edx, edi
0x180001989  mov     rcx, r14
0x18000198c  call    _CRT_INIT
0x180001991  mov     ebx, eax
0x180001993  mov     [rsp+168h+var_148], eax
0x180001997  jmp     short loc_1800019B1
0x180001999  xor     ebx, ebx
0x18000199b  mov     [rsp+168h+var_148], ebx
0x18000199f  lea     esi, [rbx+1]
0x1800019a2  mov     edi, [rsp+168h+arg_8]
0x1800019a9  mov     r14, [rsp+168h+arg_0]
0x1800019b1  test    ebx, ebx
0x1800019b3  jz      loc_180001AF8
0x1800019b9  mov     r8, [rsp+168h+lpvReserved]; lpvReserved
0x1800019c1  mov     edx, edi; fdwReason
0x1800019c3  mov     rcx, r14; hinstDLL
0x1800019c6  call    DllMain
0x1800019cb  mov     ebx, eax
0x1800019cd  mov     [rsp+168h+var_148], eax
0x1800019d1  jmp     short loc_1800019EB
0x1800019d3  xor     ebx, ebx
0x1800019d5  mov     [rsp+168h+var_148], ebx
0x1800019d9  lea     esi, [rbx+1]
0x1800019dc  mov     edi, [rsp+168h+arg_8]
0x1800019e3  mov     r14, [rsp+168h+arg_0]
0x1800019eb  cmp     edi, esi
0x1800019ed  jnz     loc_180001A7D
0x1800019f3  test    ebx, ebx
0x1800019f5  jnz     loc_180001A7D
0x1800019fb  xor     r8d, r8d; lpvReserved
0x1800019fe  xor     edx, edx; fdwReason
0x180001a00  mov     rcx, r14; hinstDLL
0x180001a03  call    DllMain
0x180001a08  jmp     short loc_180001A22
0x180001a0a  mov     esi, 1
0x180001a0f  mov     edi, [rsp+168h+arg_8]
0x180001a16  mov     r14, [rsp+168h+arg_0]
0x180001a1e  mov     ebx, [rsp+168h+var_148]
0x180001a22  xor     r8d, r8d
0x180001a25  xor     edx, edx
0x180001a27  mov     rcx, r14
0x180001a2a  call    _CRT_INIT
0x180001a2f  jmp     short loc_180001A49
0x180001a31  mov     esi, 1
0x180001a36  mov     edi, [rsp+168h+arg_8]
0x180001a3d  mov     r14, [rsp+168h+arg_0]
0x180001a45  mov     ebx, [rsp+168h+var_148]
0x180001a49  mov     rax, cs:_pRawDllMain
0x180001a50  test    rax, rax
0x180001a53  jz      short loc_180001A7D
0x180001a55  xor     r8d, r8d
0x180001a58  xor     edx, edx
0x180001a5a  mov     rcx, r14
0x180001a5d  call    cs:__guard_dispatch_icall_fptr
0x180001a63  jmp     short loc_180001A7D
0x180001a65  mov     esi, 1
0x180001a6a  mov     edi, [rsp+168h+arg_8]
0x180001a71  mov     r14, [rsp+168h+arg_0]
0x180001a79  mov     ebx, [rsp+168h+var_148]
0x180001a7d  test    edi, edi
0x180001a7f  jz      short loc_180001A86
0x180001a81  cmp     edi, 3
0x180001a84  jnz     short loc_180001AF8
0x180001a86  mov     r8, [rsp+168h+lpvReserved]
0x180001a8e  mov     edx, edi
0x180001a90  mov     rcx, r14
0x180001a93  call    _CRT_INIT
0x180001a98  mov     ebx, eax
0x180001a9a  mov     [rsp+168h+var_148], eax
0x180001a9e  jmp     short loc_180001AB8
0x180001aa0  xor     ebx, ebx
0x180001aa2  mov     [rsp+168h+var_148], ebx
0x180001aa6  lea     esi, [rbx+1]
0x180001aa9  mov     edi, [rsp+168h+arg_8]
0x180001ab0  mov     r14, [rsp+168h+arg_0]
0x180001ab8  mov     rax, cs:_pRawDllMain
0x180001abf  test    rax, rax
0x180001ac2  jz      short loc_180001AF8
0x180001ac4  cmp     cs:dword_180005084, 0
0x180001acb  jz      short loc_180001AF8
0x180001acd  mov     r8, [rsp+168h+lpvReserved]
0x180001ad5  mov     edx, edi
0x180001ad7  mov     rcx, r14
0x180001ada  call    cs:__guard_dispatch_icall_fptr
0x180001ae0  mov     ebx, eax
0x180001ae2  mov     [rsp+168h+var_148], eax
0x180001ae6  jmp     short loc_180001AF8
0x180001ae8  xor     ebx, ebx
0x180001aea  mov     [rsp+168h+var_148], ebx
0x180001aee  lea     esi, [rbx+1]
0x180001af1  mov     edi, [rsp+168h+arg_8]
0x180001af8  cmp     edi, esi
0x180001afa  ja      short loc_180001B06
0x180001afc  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x180001b06  mov     eax, ebx
0x180001b08  mov     rbx, [rsp+168h+arg_18]
0x180001b10  add     rsp, 150h
0x180001b17  pop     r14
0x180001b19  pop     rdi
0x180001b1a  pop     rsi
0x180001b1b  retn
0x1800022e0  push    rbp
0x1800022e2  sub     rsp, 20h
0x1800022e6  mov     rbp, rdx
0x1800022e9  mov     [rbp+108h], rcx
0x1800022f0  mov     rax, [rcx]
0x1800022f3  mov     edx, [rax]
0x1800022f5  mov     [rbp+0A4h], edx
0x1800022fb  mov     [rbp+0C8h], rcx
0x180002302  mov     [rbp+28h], edx
0x180002305  mov     eax, [rbp+28h]
0x180002308  cmp     eax, 0E06D7363h
0x18000230d  jnz     short loc_180002323
0x18000230f  mov     rdx, [rbp+0C8h]
0x180002316  mov     ecx, [rbp+28h]
0x180002319  call    _XcptFilter_0
0x18000231e  mov     [rbp+30h], eax
0x180002321  jmp     short loc_18000232A
0x180002323  mov     dword ptr [rbp+30h], 0
0x18000232a  mov     eax, [rbp+30h]
0x18000232d  add     rsp, 20h
0x180002331  pop     rbp
0x180002332  retn
0x180002334  push    rbp
0x180002336  sub     rsp, 20h
0x18000233a  mov     rbp, rdx
0x18000233d  mov     [rbp+110h], rcx
0x180002344  mov     rax, [rcx]
0x180002347  mov     edx, [rax]
0x180002349  mov     [rbp+0A8h], edx
0x18000234f  mov     [rbp+0D0h], rcx
0x180002356  mov     [rbp+38h], edx
0x180002359  mov     eax, [rbp+38h]
0x18000235c  cmp     eax, 0E06D7363h
0x180002361  jnz     short loc_180002377
0x180002363  mov     rdx, [rbp+0D0h]
0x18000236a  mov     ecx, [rbp+38h]
0x18000236d  call    _XcptFilter_0
0x180002372  mov     [rbp+40h], eax
0x180002375  jmp     short loc_18000237E
0x180002377  mov     dword ptr [rbp+40h], 0
0x18000237e  mov     eax, [rbp+40h]
0x180002381  add     rsp, 20h
0x180002385  pop     rbp
0x180002386  retn
0x180002388  push    rbp
0x18000238a  sub     rsp, 20h
0x18000238e  mov     rbp, rdx
0x180002391  mov     [rbp+118h], rcx
0x180002398  mov     rax, [rcx]
0x18000239b  mov     edx, [rax]
0x18000239d  mov     [rbp+0ACh], edx
0x1800023a3  mov     [rbp+0D8h], rcx
0x1800023aa  mov     [rbp+48h], edx
0x1800023ad  mov     eax, [rbp+48h]
0x1800023b0  cmp     eax, 0E06D7363h
0x1800023b5  jnz     short loc_1800023CB
0x1800023b7  mov     rdx, [rbp+0D8h]
0x1800023be  mov     ecx, [rbp+48h]
0x1800023c1  call    _XcptFilter_0
0x1800023c6  mov     [rbp+50h], eax
0x1800023c9  jmp     short loc_1800023D2
0x1800023cb  mov     dword ptr [rbp+50h], 0
0x1800023d2  mov     eax, [rbp+50h]
0x1800023d5  add     rsp, 20h
0x1800023d9  pop     rbp
0x1800023da  retn
0x1800023dc  push    rbp
0x1800023de  sub     rsp, 20h
0x1800023e2  mov     rbp, rdx
0x1800023e5  mov     [rbp+120h], rcx
0x1800023ec  mov     rax, [rcx]
0x1800023ef  mov     edx, [rax]
0x1800023f1  mov     [rbp+0B0h], edx
0x1800023f7  mov     [rbp+0E0h], rcx
0x1800023fe  mov     [rbp+58h], edx
0x180002401  mov     eax, [rbp+58h]
0x180002404  cmp     eax, 0E06D7363h
0x180002409  jnz     short loc_18000241F
0x18000240b  mov     rdx, [rbp+0E0h]
0x180002412  mov     ecx, [rbp+58h]
0x180002415  call    _XcptFilter_0
0x18000241a  mov     [rbp+60h], eax
0x18000241d  jmp     short loc_180002426
0x18000241f  mov     dword ptr [rbp+60h], 0
0x180002426  mov     eax, [rbp+60h]
0x180002429  add     rsp, 20h
0x18000242d  pop     rbp
0x18000242e  retn
0x180002430  push    rbp
0x180002432  sub     rsp, 20h
0x180002436  mov     rbp, rdx
0x180002439  mov     [rbp+128h], rcx
0x180002440  mov     rax, [rcx]
0x180002443  mov     edx, [rax]
0x180002445  mov     [rbp+0B4h], edx
0x18000244b  mov     [rbp+0E8h], rcx
0x180002452  mov     [rbp+68h], edx
0x180002455  mov     eax, [rbp+68h]
0x180002458  cmp     eax, 0E06D7363h
0x18000245d  jnz     short loc_180002473
0x18000245f  mov     rdx, [rbp+0E8h]
0x180002466  mov     ecx, [rbp+68h]
0x180002469  call    _XcptFilter_0
0x18000246e  mov     [rbp+70h], eax
0x180002471  jmp     short loc_18000247A
0x180002473  mov     dword ptr [rbp+70h], 0
0x18000247a  mov     eax, [rbp+70h]
0x18000247d  add     rsp, 20h
0x180002481  pop     rbp
0x180002482  retn
0x180002484  push    rbp
0x180002486  sub     rsp, 20h
0x18000248a  mov     rbp, rdx
0x18000248d  mov     [rbp+130h], rcx
0x180002494  mov     rax, [rcx]
0x180002497  mov     edx, [rax]
0x180002499  mov     [rbp+0B8h], edx
0x18000249f  mov     [rbp+0F0h], rcx
0x1800024a6  mov     [rbp+78h], edx
0x1800024a9  mov     eax, [rbp+78h]
0x1800024ac  cmp     eax, 0E06D7363h
0x1800024b1  jnz     short loc_1800024CA
0x1800024b3  mov     rdx, [rbp+0F0h]
0x1800024ba  mov     ecx, [rbp+78h]
0x1800024bd  call    _XcptFilter_0
0x1800024c2  mov     [rbp+80h], eax
0x1800024c8  jmp     short loc_1800024D4
0x1800024ca  mov     dword ptr [rbp+80h], 0
0x1800024d4  mov     eax, [rbp+80h]
0x1800024da  add     rsp, 20h
0x1800024de  pop     rbp
0x1800024df  retn
0x1800024e1  push    rbp
0x1800024e3  sub     rsp, 20h
0x1800024e7  mov     rbp, rdx
0x1800024ea  mov     [rbp+138h], rcx
0x1800024f1  mov     rax, [rcx]
0x1800024f4  mov     edx, [rax]
0x1800024f6  mov     [rbp+0BCh], edx
0x1800024fc  mov     [rbp+0F8h], rcx
0x180002503  mov     [rbp+88h], edx
0x180002509  mov     eax, [rbp+88h]
0x18000250f  cmp     eax, 0E06D7363h
0x180002514  jnz     short loc_180002530
0x180002516  mov     rdx, [rbp+0F8h]
0x18000251d  mov     ecx, [rbp+88h]
0x180002523  call    _XcptFilter_0
0x180002528  mov     [rbp+90h], eax
0x18000252e  jmp     short loc_18000253A
0x180002530  mov     dword ptr [rbp+90h], 0
0x18000253a  mov     eax, [rbp+90h]
  ... truncated ...
```
