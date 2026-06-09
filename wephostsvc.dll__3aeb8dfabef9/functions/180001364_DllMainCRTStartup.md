# __DllMainCRTStartup

- ea: `0x180001364`
- end: `0x180001570`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, __int64 fdwReason, void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180001320`

## callees

- `0x1800010f0`
- `0x180001364`
- `0x180001576`
- `0x180001748`
- `0x180003c20`

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
  if ( (_DWORD)fdwReason || dword_180008140 )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_180008144 = 1;
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
            if ( dword_180008144 )
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
0x180001375  sub     rsp, 0F0h
0x18000137c  mov     edi, edx
0x18000137e  mov     rsi, rcx
0x180001381  mov     ebx, 1
0x180001386  cmp     edx, ebx
0x180001388  ja      short loc_180001390
0x18000138a  mov     cs:__native_dllmain_reason, edx
0x180001390  test    edx, edx
0x180001392  jnz     short loc_1800013A7
0x180001394  cmp     cs:dword_180008140, edx
0x18000139a  jnz     short loc_1800013A7
0x18000139c  xor     ebx, ebx
0x18000139e  mov     [rsp+108h+var_E8], ebx
0x1800013a2  jmp     loc_180001554
0x1800013a7  lea     eax, [rdx-1]
0x1800013aa  cmp     eax, 1
0x1800013ad  ja      loc_180001434
0x1800013b3  mov     rax, cs:_pRawDllMain
0x1800013ba  test    rax, rax
0x1800013bd  jz      short loc_1800013F5
0x1800013bf  cmp     edx, 1
0x1800013c2  jnz     short loc_1800013CA
0x1800013c4  mov     cs:dword_180008144, edx
0x1800013ca  mov     r8, [rsp+108h+lpvReserved]
0x1800013d2  call    cs:__guard_dispatch_icall_fptr
0x1800013d8  mov     ebx, eax
0x1800013da  mov     [rsp+108h+var_E8], eax
0x1800013de  jmp     short loc_1800013F5
0x1800013e0  xor     ebx, ebx
0x1800013e2  mov     [rsp+108h+var_E8], ebx
0x1800013e6  mov     edi, [rsp+108h+arg_8]
0x1800013ed  mov     rsi, [rsp+108h+arg_0]
0x1800013f5  test    ebx, ebx
0x1800013f7  jz      loc_180001554
0x1800013fd  mov     r8, [rsp+108h+lpvReserved]
0x180001405  mov     edx, edi
0x180001407  mov     rcx, rsi
0x18000140a  call    _CRT_INIT
0x18000140f  mov     ebx, eax
0x180001411  mov     [rsp+108h+var_E8], eax
0x180001415  jmp     short loc_18000142C
0x180001417  xor     ebx, ebx
0x180001419  mov     [rsp+108h+var_E8], ebx
0x18000141d  mov     edi, [rsp+108h+arg_8]
0x180001424  mov     rsi, [rsp+108h+arg_0]
0x18000142c  test    ebx, ebx
0x18000142e  jz      loc_180001554
0x180001434  mov     r8, [rsp+108h+lpvReserved]; lpvReserved
0x18000143c  mov     edx, edi; fdwReason
0x18000143e  mov     rcx, rsi; hinstDLL
0x180001441  call    DllMain
0x180001446  mov     ebx, eax
0x180001448  mov     [rsp+108h+var_E8], eax
0x18000144c  jmp     short loc_180001463
0x18000144e  xor     ebx, ebx
0x180001450  mov     [rsp+108h+var_E8], ebx
0x180001454  mov     edi, [rsp+108h+arg_8]
0x18000145b  mov     rsi, [rsp+108h+arg_0]
0x180001463  cmp     edi, 1
0x180001466  jnz     short loc_1800014DF
0x180001468  test    ebx, ebx
0x18000146a  jnz     short loc_1800014DF
0x18000146c  xor     r8d, r8d; lpvReserved
0x18000146f  xor     edx, edx; fdwReason
0x180001471  mov     rcx, rsi; hinstDLL
0x180001474  call    DllMain
0x180001479  jmp     short loc_18000148E
0x18000147b  mov     edi, [rsp+108h+arg_8]
0x180001482  mov     rsi, [rsp+108h+arg_0]
0x18000148a  mov     ebx, [rsp+108h+var_E8]
0x18000148e  xor     r8d, r8d
0x180001491  xor     edx, edx
0x180001493  mov     rcx, rsi
0x180001496  call    _CRT_INIT
0x18000149b  jmp     short loc_1800014B0
0x18000149d  mov     edi, [rsp+108h+arg_8]
0x1800014a4  mov     rsi, [rsp+108h+arg_0]
0x1800014ac  mov     ebx, [rsp+108h+var_E8]
0x1800014b0  mov     rax, cs:_pRawDllMain
0x1800014b7  test    rax, rax
0x1800014ba  jz      short loc_1800014DF
0x1800014bc  xor     r8d, r8d
0x1800014bf  xor     edx, edx
0x1800014c1  mov     rcx, rsi
0x1800014c4  call    cs:__guard_dispatch_icall_fptr
0x1800014ca  jmp     short loc_1800014DF
0x1800014cc  mov     edi, [rsp+108h+arg_8]
0x1800014d3  mov     rsi, [rsp+108h+arg_0]
0x1800014db  mov     ebx, [rsp+108h+var_E8]
0x1800014df  test    edi, edi
0x1800014e1  jz      short loc_1800014E8
0x1800014e3  cmp     edi, 3
0x1800014e6  jnz     short loc_180001554
0x1800014e8  mov     r8, [rsp+108h+lpvReserved]
0x1800014f0  mov     edx, edi
0x1800014f2  mov     rcx, rsi
0x1800014f5  call    _CRT_INIT
0x1800014fa  mov     ebx, eax
0x1800014fc  mov     [rsp+108h+var_E8], eax
0x180001500  jmp     short loc_180001517
0x180001502  xor     ebx, ebx
0x180001504  mov     [rsp+108h+var_E8], ebx
0x180001508  mov     edi, [rsp+108h+arg_8]
0x18000150f  mov     rsi, [rsp+108h+arg_0]
0x180001517  mov     rax, cs:_pRawDllMain
0x18000151e  test    rax, rax
0x180001521  jz      short loc_180001554
0x180001523  cmp     cs:dword_180008144, 0
0x18000152a  jz      short loc_180001554
0x18000152c  mov     r8, [rsp+108h+lpvReserved]
0x180001534  mov     edx, edi
0x180001536  mov     rcx, rsi
0x180001539  call    cs:__guard_dispatch_icall_fptr
0x18000153f  mov     ebx, eax
0x180001541  mov     [rsp+108h+var_E8], eax
0x180001545  jmp     short loc_180001554
0x180001547  xor     ebx, ebx
0x180001549  mov     [rsp+108h+var_E8], ebx
0x18000154d  mov     edi, [rsp+108h+arg_8]
0x180001554  cmp     edi, 1
0x180001557  ja      short loc_180001563
0x180001559  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x180001563  mov     eax, ebx
0x180001565  add     rsp, 0F0h
0x18000156c  pop     rdi
0x18000156d  pop     rsi
0x18000156e  pop     rbx
0x18000156f  retn
0x180003cf0  push    rbp
0x180003cf2  sub     rsp, 20h
0x180003cf6  mov     rbp, rdx
0x180003cf9  mov     rax, [rcx]
0x180003cfc  mov     edx, [rax]
0x180003cfe  mov     [rbp+0A8h], rcx
0x180003d05  mov     [rbp+28h], edx
0x180003d08  mov     eax, [rbp+28h]
0x180003d0b  cmp     eax, 0E06D7363h
0x180003d10  jnz     short loc_180003D26
0x180003d12  mov     rdx, [rbp+0A8h]
0x180003d19  mov     ecx, [rbp+28h]
0x180003d1c  call    _XcptFilter_0
0x180003d21  mov     [rbp+30h], eax
0x180003d24  jmp     short loc_180003D2D
0x180003d26  mov     dword ptr [rbp+30h], 0
0x180003d2d  mov     eax, [rbp+30h]
0x180003d30  add     rsp, 20h
0x180003d34  pop     rbp
0x180003d35  retn
0x180003d37  push    rbp
0x180003d39  sub     rsp, 20h
0x180003d3d  mov     rbp, rdx
0x180003d40  mov     rax, [rcx]
0x180003d43  mov     edx, [rax]
0x180003d45  mov     [rbp+0B0h], rcx
0x180003d4c  mov     [rbp+38h], edx
0x180003d4f  mov     eax, [rbp+38h]
0x180003d52  cmp     eax, 0E06D7363h
0x180003d57  jnz     short loc_180003D6D
0x180003d59  mov     rdx, [rbp+0B0h]
0x180003d60  mov     ecx, [rbp+38h]
0x180003d63  call    _XcptFilter_0
0x180003d68  mov     [rbp+40h], eax
0x180003d6b  jmp     short loc_180003D74
0x180003d6d  mov     dword ptr [rbp+40h], 0
0x180003d74  mov     eax, [rbp+40h]
0x180003d77  add     rsp, 20h
0x180003d7b  pop     rbp
0x180003d7c  retn
0x180003d7e  push    rbp
0x180003d80  sub     rsp, 20h
0x180003d84  mov     rbp, rdx
0x180003d87  mov     rax, [rcx]
0x180003d8a  mov     edx, [rax]
0x180003d8c  mov     [rbp+0B8h], rcx
0x180003d93  mov     [rbp+48h], edx
0x180003d96  mov     eax, [rbp+48h]
0x180003d99  cmp     eax, 0E06D7363h
0x180003d9e  jnz     short loc_180003DB4
0x180003da0  mov     rdx, [rbp+0B8h]
0x180003da7  mov     ecx, [rbp+48h]
0x180003daa  call    _XcptFilter_0
0x180003daf  mov     [rbp+50h], eax
0x180003db2  jmp     short loc_180003DBB
0x180003db4  mov     dword ptr [rbp+50h], 0
0x180003dbb  mov     eax, [rbp+50h]
0x180003dbe  add     rsp, 20h
0x180003dc2  pop     rbp
0x180003dc3  retn
0x180003dc5  push    rbp
0x180003dc7  sub     rsp, 20h
0x180003dcb  mov     rbp, rdx
0x180003dce  mov     rax, [rcx]
0x180003dd1  mov     edx, [rax]
0x180003dd3  mov     [rbp+0C0h], rcx
0x180003dda  mov     [rbp+58h], edx
0x180003ddd  mov     eax, [rbp+58h]
0x180003de0  cmp     eax, 0E06D7363h
0x180003de5  jnz     short loc_180003DFB
0x180003de7  mov     rdx, [rbp+0C0h]
0x180003dee  mov     ecx, [rbp+58h]
0x180003df1  call    _XcptFilter_0
0x180003df6  mov     [rbp+60h], eax
0x180003df9  jmp     short loc_180003E02
0x180003dfb  mov     dword ptr [rbp+60h], 0
0x180003e02  mov     eax, [rbp+60h]
0x180003e05  add     rsp, 20h
0x180003e09  pop     rbp
0x180003e0a  retn
0x180003e0c  push    rbp
0x180003e0e  sub     rsp, 20h
0x180003e12  mov     rbp, rdx
0x180003e15  mov     rax, [rcx]
0x180003e18  mov     edx, [rax]
0x180003e1a  mov     [rbp+0C8h], rcx
0x180003e21  mov     [rbp+68h], edx
0x180003e24  mov     eax, [rbp+68h]
0x180003e27  cmp     eax, 0E06D7363h
0x180003e2c  jnz     short loc_180003E42
0x180003e2e  mov     rdx, [rbp+0C8h]
0x180003e35  mov     ecx, [rbp+68h]
0x180003e38  call    _XcptFilter_0
0x180003e3d  mov     [rbp+70h], eax
0x180003e40  jmp     short loc_180003E49
0x180003e42  mov     dword ptr [rbp+70h], 0
0x180003e49  mov     eax, [rbp+70h]
0x180003e4c  add     rsp, 20h
0x180003e50  pop     rbp
0x180003e51  retn
0x180003e53  push    rbp
0x180003e55  sub     rsp, 20h
0x180003e59  mov     rbp, rdx
0x180003e5c  mov     rax, [rcx]
0x180003e5f  mov     edx, [rax]
0x180003e61  mov     [rbp+0D0h], rcx
0x180003e68  mov     [rbp+78h], edx
0x180003e6b  mov     eax, [rbp+78h]
0x180003e6e  cmp     eax, 0E06D7363h
0x180003e73  jnz     short loc_180003E8C
0x180003e75  mov     rdx, [rbp+0D0h]
0x180003e7c  mov     ecx, [rbp+78h]
0x180003e7f  call    _XcptFilter_0
0x180003e84  mov     [rbp+80h], eax
0x180003e8a  jmp     short loc_180003E96
0x180003e8c  mov     dword ptr [rbp+80h], 0
0x180003e96  mov     eax, [rbp+80h]
0x180003e9c  add     rsp, 20h
0x180003ea0  pop     rbp
0x180003ea1  retn
0x180003ea3  push    rbp
0x180003ea5  sub     rsp, 20h
0x180003ea9  mov     rbp, rdx
0x180003eac  mov     rax, [rcx]
0x180003eaf  mov     edx, [rax]
0x180003eb1  mov     [rbp+0D8h], rcx
0x180003eb8  mov     [rbp+88h], edx
0x180003ebe  mov     eax, [rbp+88h]
0x180003ec4  cmp     eax, 0E06D7363h
0x180003ec9  jnz     short loc_180003EE5
0x180003ecb  mov     rdx, [rbp+0D8h]
0x180003ed2  mov     ecx, [rbp+88h]
0x180003ed8  call    _XcptFilter_0
0x180003edd  mov     [rbp+90h], eax
0x180003ee3  jmp     short loc_180003EEF
0x180003ee5  mov     dword ptr [rbp+90h], 0
0x180003eef  mov     eax, [rbp+90h]
0x180003ef5  add     rsp, 20h
0x180003ef9  pop     rbp
0x180003efa  retn
0x180003efc  push    rbp
0x180003efe  sub     rsp, 20h
0x180003f02  mov     rbp, rdx
0x180003f05  mov     rax, [rcx]
0x180003f08  mov     edx, [rax]
0x180003f0a  mov     [rbp+0E0h], rcx
0x180003f11  mov     [rbp+98h], edx
0x180003f17  mov     eax, [rbp+98h]
0x180003f1d  cmp     eax, 0E06D7363h
0x180003f22  jnz     short loc_180003F3E
0x180003f24  mov     rdx, [rbp+0E0h]
0x180003f2b  mov     ecx, [rbp+98h]
0x180003f31  call    _XcptFilter_0
0x180003f36  mov     [rbp+0A0h], eax
0x180003f3c  jmp     short loc_180003F48
0x180003f3e  mov     dword ptr [rbp+0A0h], 0
0x180003f48  mov     eax, [rbp+0A0h]
0x180003f4e  add     rsp, 20h
0x180003f52  pop     rbp
0x180003f53  retn
0x180003f55  push    rbp
0x180003f57  sub     rsp, 20h
0x180003f5b  mov     rbp, rdx
0x180003f5e  cmp     dword ptr [rbp+118h], 1
0x180003f65  ja      short loc_180003F71
0x180003f67  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
