# __DllMainCRTStartup

- ea: `0x1800017e4`
- end: `0x1800019f1`
- name: `__DllMainCRTStartup`
- size: `525`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1800017a0`

## callees

- `0x18000155c`
- `0x1800017e4`
- `0x180001d04`
- `0x180001ee4`
- `0x180013010`

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
  if ( (_DWORD)fdwReason || dword_18001C4C0 )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_18001C4C4 = 1;
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
            if ( dword_18001C4C4 )
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
0x1800017e4  mov     [rsp+lpvReserved], r8
0x1800017e9  mov     [rsp+arg_8], edx
0x1800017ed  mov     [rsp+arg_0], rcx
0x1800017f2  push    rbx
0x1800017f3  push    rsi
0x1800017f4  push    rdi
0x1800017f5  sub     rsp, 150h
0x1800017fc  mov     edi, edx
0x1800017fe  mov     rsi, rcx
0x180001801  mov     ebx, 1
0x180001806  mov     [rsp+168h+var_148], ebx
0x18000180a  cmp     edx, ebx
0x18000180c  ja      short loc_180001814
0x18000180e  mov     cs:__native_dllmain_reason, edx
0x180001814  test    edx, edx
0x180001816  jnz     short loc_18000182B
0x180001818  cmp     cs:dword_18001C4C0, edx
0x18000181e  jnz     short loc_18000182B
0x180001820  xor     ebx, ebx
0x180001822  mov     [rsp+168h+var_148], ebx
0x180001826  jmp     loc_1800019D5
0x18000182b  lea     eax, [rdx-1]
0x18000182e  cmp     eax, 1
0x180001831  ja      loc_1800018B7
0x180001837  mov     rax, cs:_pRawDllMain
0x18000183e  test    rax, rax
0x180001841  jz      short loc_180001878
0x180001843  cmp     edx, 1
0x180001846  jnz     short loc_18000184E
0x180001848  mov     cs:dword_18001C4C4, edx
0x18000184e  mov     r8, [rsp+168h+lpvReserved]
0x180001856  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000185b  mov     ebx, eax
0x18000185d  mov     [rsp+168h+var_148], eax
0x180001861  jmp     short loc_180001878
0x180001863  xor     ebx, ebx
0x180001865  mov     [rsp+168h+var_148], ebx
0x180001869  mov     edi, [rsp+168h+arg_8]
0x180001870  mov     rsi, [rsp+168h+arg_0]
0x180001878  test    ebx, ebx
0x18000187a  jz      loc_1800019D5
0x180001880  mov     r8, [rsp+168h+lpvReserved]
0x180001888  mov     edx, edi
0x18000188a  mov     rcx, rsi
0x18000188d  call    _CRT_INIT
0x180001892  mov     ebx, eax
0x180001894  mov     [rsp+168h+var_148], eax
0x180001898  jmp     short loc_1800018AF
0x18000189a  xor     ebx, ebx
0x18000189c  mov     [rsp+168h+var_148], ebx
0x1800018a0  mov     edi, [rsp+168h+arg_8]
0x1800018a7  mov     rsi, [rsp+168h+arg_0]
0x1800018af  test    ebx, ebx
0x1800018b1  jz      loc_1800019D5
0x1800018b7  mov     r8, [rsp+168h+lpvReserved]; lpvReserved
0x1800018bf  mov     edx, edi; fdwReason
0x1800018c1  mov     rcx, rsi; hinstDLL
0x1800018c4  call    DllMain
0x1800018c9  mov     ebx, eax
0x1800018cb  mov     [rsp+168h+var_148], eax
0x1800018cf  jmp     short loc_1800018E6
0x1800018d1  xor     ebx, ebx
0x1800018d3  mov     [rsp+168h+var_148], ebx
0x1800018d7  mov     edi, [rsp+168h+arg_8]
0x1800018de  mov     rsi, [rsp+168h+arg_0]
0x1800018e6  cmp     edi, 1
0x1800018e9  jnz     short loc_180001961
0x1800018eb  test    ebx, ebx
0x1800018ed  jnz     short loc_180001961
0x1800018ef  xor     r8d, r8d; lpvReserved
0x1800018f2  xor     edx, edx; fdwReason
0x1800018f4  mov     rcx, rsi; hinstDLL
0x1800018f7  call    DllMain
0x1800018fc  jmp     short loc_180001911
0x1800018fe  mov     edi, [rsp+168h+arg_8]
0x180001905  mov     rsi, [rsp+168h+arg_0]
0x18000190d  mov     ebx, [rsp+168h+var_148]
0x180001911  xor     r8d, r8d
0x180001914  xor     edx, edx
0x180001916  mov     rcx, rsi
0x180001919  call    _CRT_INIT
0x18000191e  jmp     short loc_180001933
0x180001920  mov     edi, [rsp+168h+arg_8]
0x180001927  mov     rsi, [rsp+168h+arg_0]
0x18000192f  mov     ebx, [rsp+168h+var_148]
0x180001933  mov     rax, cs:_pRawDllMain
0x18000193a  test    rax, rax
0x18000193d  jz      short loc_180001961
0x18000193f  xor     r8d, r8d
0x180001942  xor     edx, edx
0x180001944  mov     rcx, rsi
0x180001947  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000194c  jmp     short loc_180001961
0x18000194e  mov     edi, [rsp+168h+arg_8]
0x180001955  mov     rsi, [rsp+168h+arg_0]
0x18000195d  mov     ebx, [rsp+168h+var_148]
0x180001961  test    edi, edi
0x180001963  jz      short loc_18000196A
0x180001965  cmp     edi, 3
0x180001968  jnz     short loc_1800019D5
0x18000196a  mov     r8, [rsp+168h+lpvReserved]
0x180001972  mov     edx, edi
0x180001974  mov     rcx, rsi
0x180001977  call    _CRT_INIT
0x18000197c  mov     ebx, eax
0x18000197e  mov     [rsp+168h+var_148], eax
0x180001982  jmp     short loc_180001999
0x180001984  xor     ebx, ebx
0x180001986  mov     [rsp+168h+var_148], ebx
0x18000198a  mov     edi, [rsp+168h+arg_8]
0x180001991  mov     rsi, [rsp+168h+arg_0]
0x180001999  mov     rax, cs:_pRawDllMain
0x1800019a0  test    rax, rax
0x1800019a3  jz      short loc_1800019D5
0x1800019a5  cmp     cs:dword_18001C4C4, 0
0x1800019ac  jz      short loc_1800019D5
0x1800019ae  mov     r8, [rsp+168h+lpvReserved]
0x1800019b6  mov     edx, edi
0x1800019b8  mov     rcx, rsi
0x1800019bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800019c0  mov     ebx, eax
0x1800019c2  mov     [rsp+168h+var_148], eax
0x1800019c6  jmp     short loc_1800019D5
0x1800019c8  xor     ebx, ebx
0x1800019ca  mov     [rsp+168h+var_148], ebx
0x1800019ce  mov     edi, [rsp+168h+arg_8]
0x1800019d5  cmp     edi, 1
0x1800019d8  ja      short loc_1800019E4
0x1800019da  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x1800019e4  mov     eax, ebx
0x1800019e6  add     rsp, 150h
0x1800019ed  pop     rdi
0x1800019ee  pop     rsi
0x1800019ef  pop     rbx
0x1800019f0  retn
0x180011ba3  push    rbp
0x180011ba5  sub     rsp, 20h
0x180011ba9  mov     rbp, rdx
0x180011bac  mov     [rbp+108h], rcx
0x180011bb3  mov     rax, [rcx]
0x180011bb6  mov     edx, [rax]
0x180011bb8  mov     [rbp+0A4h], edx
0x180011bbe  mov     [rbp+0C8h], rcx
0x180011bc5  mov     [rbp+28h], edx
0x180011bc8  mov     eax, [rbp+28h]
0x180011bcb  cmp     eax, 0E06D7363h
0x180011bd0  jnz     short loc_180011BE6
0x180011bd2  mov     rdx, [rbp+0C8h]
0x180011bd9  mov     ecx, [rbp+28h]
0x180011bdc  call    _XcptFilter_0
0x180011be1  mov     [rbp+30h], eax
0x180011be4  jmp     short loc_180011BED
0x180011be6  mov     dword ptr [rbp+30h], 0
0x180011bed  mov     eax, [rbp+30h]
0x180011bf0  add     rsp, 20h
0x180011bf4  pop     rbp
0x180011bf5  retn
0x180011bf7  push    rbp
0x180011bf9  sub     rsp, 20h
0x180011bfd  mov     rbp, rdx
0x180011c00  mov     [rbp+110h], rcx
0x180011c07  mov     rax, [rcx]
0x180011c0a  mov     edx, [rax]
0x180011c0c  mov     [rbp+0A8h], edx
0x180011c12  mov     [rbp+0D0h], rcx
0x180011c19  mov     [rbp+38h], edx
0x180011c1c  mov     eax, [rbp+38h]
0x180011c1f  cmp     eax, 0E06D7363h
0x180011c24  jnz     short loc_180011C3A
0x180011c26  mov     rdx, [rbp+0D0h]
0x180011c2d  mov     ecx, [rbp+38h]
0x180011c30  call    _XcptFilter_0
0x180011c35  mov     [rbp+40h], eax
0x180011c38  jmp     short loc_180011C41
0x180011c3a  mov     dword ptr [rbp+40h], 0
0x180011c41  mov     eax, [rbp+40h]
0x180011c44  add     rsp, 20h
0x180011c48  pop     rbp
0x180011c49  retn
0x180011c4b  push    rbp
0x180011c4d  sub     rsp, 20h
0x180011c51  mov     rbp, rdx
0x180011c54  mov     [rbp+118h], rcx
0x180011c5b  mov     rax, [rcx]
0x180011c5e  mov     edx, [rax]
0x180011c60  mov     [rbp+0ACh], edx
0x180011c66  mov     [rbp+0D8h], rcx
0x180011c6d  mov     [rbp+48h], edx
0x180011c70  mov     eax, [rbp+48h]
0x180011c73  cmp     eax, 0E06D7363h
0x180011c78  jnz     short loc_180011C8E
0x180011c7a  mov     rdx, [rbp+0D8h]
0x180011c81  mov     ecx, [rbp+48h]
0x180011c84  call    _XcptFilter_0
0x180011c89  mov     [rbp+50h], eax
0x180011c8c  jmp     short loc_180011C95
0x180011c8e  mov     dword ptr [rbp+50h], 0
0x180011c95  mov     eax, [rbp+50h]
0x180011c98  add     rsp, 20h
0x180011c9c  pop     rbp
0x180011c9d  retn
0x180011c9f  push    rbp
0x180011ca1  sub     rsp, 20h
0x180011ca5  mov     rbp, rdx
0x180011ca8  mov     [rbp+120h], rcx
0x180011caf  mov     rax, [rcx]
0x180011cb2  mov     edx, [rax]
0x180011cb4  mov     [rbp+0B0h], edx
0x180011cba  mov     [rbp+0E0h], rcx
0x180011cc1  mov     [rbp+58h], edx
0x180011cc4  mov     eax, [rbp+58h]
0x180011cc7  cmp     eax, 0E06D7363h
0x180011ccc  jnz     short loc_180011CE2
0x180011cce  mov     rdx, [rbp+0E0h]
0x180011cd5  mov     ecx, [rbp+58h]
0x180011cd8  call    _XcptFilter_0
0x180011cdd  mov     [rbp+60h], eax
0x180011ce0  jmp     short loc_180011CE9
0x180011ce2  mov     dword ptr [rbp+60h], 0
0x180011ce9  mov     eax, [rbp+60h]
0x180011cec  add     rsp, 20h
0x180011cf0  pop     rbp
0x180011cf1  retn
0x180011cf3  push    rbp
0x180011cf5  sub     rsp, 20h
0x180011cf9  mov     rbp, rdx
0x180011cfc  mov     [rbp+128h], rcx
0x180011d03  mov     rax, [rcx]
0x180011d06  mov     edx, [rax]
0x180011d08  mov     [rbp+0B4h], edx
0x180011d0e  mov     [rbp+0E8h], rcx
0x180011d15  mov     [rbp+68h], edx
0x180011d18  mov     eax, [rbp+68h]
0x180011d1b  cmp     eax, 0E06D7363h
0x180011d20  jnz     short loc_180011D36
0x180011d22  mov     rdx, [rbp+0E8h]
0x180011d29  mov     ecx, [rbp+68h]
0x180011d2c  call    _XcptFilter_0
0x180011d31  mov     [rbp+70h], eax
0x180011d34  jmp     short loc_180011D3D
0x180011d36  mov     dword ptr [rbp+70h], 0
0x180011d3d  mov     eax, [rbp+70h]
0x180011d40  add     rsp, 20h
0x180011d44  pop     rbp
0x180011d45  retn
0x180011d47  push    rbp
0x180011d49  sub     rsp, 20h
0x180011d4d  mov     rbp, rdx
0x180011d50  mov     [rbp+130h], rcx
0x180011d57  mov     rax, [rcx]
0x180011d5a  mov     edx, [rax]
0x180011d5c  mov     [rbp+0B8h], edx
0x180011d62  mov     [rbp+0F0h], rcx
0x180011d69  mov     [rbp+78h], edx
0x180011d6c  mov     eax, [rbp+78h]
0x180011d6f  cmp     eax, 0E06D7363h
0x180011d74  jnz     short loc_180011D8D
0x180011d76  mov     rdx, [rbp+0F0h]
0x180011d7d  mov     ecx, [rbp+78h]
0x180011d80  call    _XcptFilter_0
0x180011d85  mov     [rbp+80h], eax
0x180011d8b  jmp     short loc_180011D97
0x180011d8d  mov     dword ptr [rbp+80h], 0
0x180011d97  mov     eax, [rbp+80h]
0x180011d9d  add     rsp, 20h
0x180011da1  pop     rbp
0x180011da2  retn
0x180011da4  push    rbp
0x180011da6  sub     rsp, 20h
0x180011daa  mov     rbp, rdx
0x180011dad  mov     [rbp+138h], rcx
0x180011db4  mov     rax, [rcx]
0x180011db7  mov     edx, [rax]
0x180011db9  mov     [rbp+0BCh], edx
0x180011dbf  mov     [rbp+0F8h], rcx
0x180011dc6  mov     [rbp+88h], edx
0x180011dcc  mov     eax, [rbp+88h]
0x180011dd2  cmp     eax, 0E06D7363h
0x180011dd7  jnz     short loc_180011DF3
0x180011dd9  mov     rdx, [rbp+0F8h]
0x180011de0  mov     ecx, [rbp+88h]
0x180011de6  call    _XcptFilter_0
0x180011deb  mov     [rbp+90h], eax
0x180011df1  jmp     short loc_180011DFD
0x180011df3  mov     dword ptr [rbp+90h], 0
0x180011dfd  mov     eax, [rbp+90h]
0x180011e03  add     rsp, 20h
0x180011e07  pop     rbp
0x180011e08  retn
0x180011e0a  push    rbp
0x180011e0c  sub     rsp, 20h
0x180011e10  mov     rbp, rdx
0x180011e13  mov     [rbp+140h], rcx
0x180011e1a  mov     rax, [rcx]
0x180011e1d  mov     edx, [rax]
0x180011e1f  mov     [rbp+0C0h], edx
0x180011e25  mov     [rbp+100h], rcx
0x180011e2c  mov     [rbp+98h], edx
0x180011e32  mov     eax, [rbp+98h]
0x180011e38  cmp     eax, 0E06D7363h
  ... truncated ...
```
