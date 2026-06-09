# __DllMainCRTStartup

- ea: `0x180001724`
- end: `0x180001931`
- name: `__DllMainCRTStartup`
- size: `525`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1800016e0`

## callees

- `0x18000149c`
- `0x180001724`
- `0x180001a45`
- `0x180001c24`
- `0x18001d010`

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
  if ( (_DWORD)fdwReason || dword_1800283C0 )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_1800283C4 = 1;
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
            if ( dword_1800283C4 )
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
0x180001724  mov     [rsp+lpvReserved], r8
0x180001729  mov     [rsp+arg_8], edx
0x18000172d  mov     [rsp+arg_0], rcx
0x180001732  push    rbx
0x180001733  push    rsi
0x180001734  push    rdi
0x180001735  sub     rsp, 150h
0x18000173c  mov     edi, edx
0x18000173e  mov     rsi, rcx
0x180001741  mov     ebx, 1
0x180001746  mov     [rsp+168h+var_148], ebx
0x18000174a  cmp     edx, ebx
0x18000174c  ja      short loc_180001754
0x18000174e  mov     cs:__native_dllmain_reason, edx
0x180001754  test    edx, edx
0x180001756  jnz     short loc_18000176B
0x180001758  cmp     cs:dword_1800283C0, edx
0x18000175e  jnz     short loc_18000176B
0x180001760  xor     ebx, ebx
0x180001762  mov     [rsp+168h+var_148], ebx
0x180001766  jmp     loc_180001915
0x18000176b  lea     eax, [rdx-1]
0x18000176e  cmp     eax, 1
0x180001771  ja      loc_1800017F7
0x180001777  mov     rax, cs:_pRawDllMain
0x18000177e  test    rax, rax
0x180001781  jz      short loc_1800017B8
0x180001783  cmp     edx, 1
0x180001786  jnz     short loc_18000178E
0x180001788  mov     cs:dword_1800283C4, edx
0x18000178e  mov     r8, [rsp+168h+lpvReserved]
0x180001796  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000179b  mov     ebx, eax
0x18000179d  mov     [rsp+168h+var_148], eax
0x1800017a1  jmp     short loc_1800017B8
0x1800017a3  xor     ebx, ebx
0x1800017a5  mov     [rsp+168h+var_148], ebx
0x1800017a9  mov     edi, [rsp+168h+arg_8]
0x1800017b0  mov     rsi, [rsp+168h+arg_0]
0x1800017b8  test    ebx, ebx
0x1800017ba  jz      loc_180001915
0x1800017c0  mov     r8, [rsp+168h+lpvReserved]
0x1800017c8  mov     edx, edi
0x1800017ca  mov     rcx, rsi
0x1800017cd  call    _CRT_INIT
0x1800017d2  mov     ebx, eax
0x1800017d4  mov     [rsp+168h+var_148], eax
0x1800017d8  jmp     short loc_1800017EF
0x1800017da  xor     ebx, ebx
0x1800017dc  mov     [rsp+168h+var_148], ebx
0x1800017e0  mov     edi, [rsp+168h+arg_8]
0x1800017e7  mov     rsi, [rsp+168h+arg_0]
0x1800017ef  test    ebx, ebx
0x1800017f1  jz      loc_180001915
0x1800017f7  mov     r8, [rsp+168h+lpvReserved]; lpvReserved
0x1800017ff  mov     edx, edi; fdwReason
0x180001801  mov     rcx, rsi; hinstDLL
0x180001804  call    DllMain
0x180001809  mov     ebx, eax
0x18000180b  mov     [rsp+168h+var_148], eax
0x18000180f  jmp     short loc_180001826
0x180001811  xor     ebx, ebx
0x180001813  mov     [rsp+168h+var_148], ebx
0x180001817  mov     edi, [rsp+168h+arg_8]
0x18000181e  mov     rsi, [rsp+168h+arg_0]
0x180001826  cmp     edi, 1
0x180001829  jnz     short loc_1800018A1
0x18000182b  test    ebx, ebx
0x18000182d  jnz     short loc_1800018A1
0x18000182f  xor     r8d, r8d; lpvReserved
0x180001832  xor     edx, edx; fdwReason
0x180001834  mov     rcx, rsi; hinstDLL
0x180001837  call    DllMain
0x18000183c  jmp     short loc_180001851
0x18000183e  mov     edi, [rsp+168h+arg_8]
0x180001845  mov     rsi, [rsp+168h+arg_0]
0x18000184d  mov     ebx, [rsp+168h+var_148]
0x180001851  xor     r8d, r8d
0x180001854  xor     edx, edx
0x180001856  mov     rcx, rsi
0x180001859  call    _CRT_INIT
0x18000185e  jmp     short loc_180001873
0x180001860  mov     edi, [rsp+168h+arg_8]
0x180001867  mov     rsi, [rsp+168h+arg_0]
0x18000186f  mov     ebx, [rsp+168h+var_148]
0x180001873  mov     rax, cs:_pRawDllMain
0x18000187a  test    rax, rax
0x18000187d  jz      short loc_1800018A1
0x18000187f  xor     r8d, r8d
0x180001882  xor     edx, edx
0x180001884  mov     rcx, rsi
0x180001887  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000188c  jmp     short loc_1800018A1
0x18000188e  mov     edi, [rsp+168h+arg_8]
0x180001895  mov     rsi, [rsp+168h+arg_0]
0x18000189d  mov     ebx, [rsp+168h+var_148]
0x1800018a1  test    edi, edi
0x1800018a3  jz      short loc_1800018AA
0x1800018a5  cmp     edi, 3
0x1800018a8  jnz     short loc_180001915
0x1800018aa  mov     r8, [rsp+168h+lpvReserved]
0x1800018b2  mov     edx, edi
0x1800018b4  mov     rcx, rsi
0x1800018b7  call    _CRT_INIT
0x1800018bc  mov     ebx, eax
0x1800018be  mov     [rsp+168h+var_148], eax
0x1800018c2  jmp     short loc_1800018D9
0x1800018c4  xor     ebx, ebx
0x1800018c6  mov     [rsp+168h+var_148], ebx
0x1800018ca  mov     edi, [rsp+168h+arg_8]
0x1800018d1  mov     rsi, [rsp+168h+arg_0]
0x1800018d9  mov     rax, cs:_pRawDllMain
0x1800018e0  test    rax, rax
0x1800018e3  jz      short loc_180001915
0x1800018e5  cmp     cs:dword_1800283C4, 0
0x1800018ec  jz      short loc_180001915
0x1800018ee  mov     r8, [rsp+168h+lpvReserved]
0x1800018f6  mov     edx, edi
0x1800018f8  mov     rcx, rsi
0x1800018fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001900  mov     ebx, eax
0x180001902  mov     [rsp+168h+var_148], eax
0x180001906  jmp     short loc_180001915
0x180001908  xor     ebx, ebx
0x18000190a  mov     [rsp+168h+var_148], ebx
0x18000190e  mov     edi, [rsp+168h+arg_8]
0x180001915  cmp     edi, 1
0x180001918  ja      short loc_180001924
0x18000191a  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x180001924  mov     eax, ebx
0x180001926  add     rsp, 150h
0x18000192d  pop     rdi
0x18000192e  pop     rsi
0x18000192f  pop     rbx
0x180001930  retn
0x18001c263  push    rbp
0x18001c265  sub     rsp, 20h
0x18001c269  mov     rbp, rdx
0x18001c26c  mov     [rbp+108h], rcx
0x18001c273  mov     rax, [rcx]
0x18001c276  mov     edx, [rax]
0x18001c278  mov     [rbp+0A4h], edx
0x18001c27e  mov     [rbp+0C8h], rcx
0x18001c285  mov     [rbp+28h], edx
0x18001c288  mov     eax, [rbp+28h]
0x18001c28b  cmp     eax, 0E06D7363h
0x18001c290  jnz     short loc_18001C2A6
0x18001c292  mov     rdx, [rbp+0C8h]
0x18001c299  mov     ecx, [rbp+28h]
0x18001c29c  call    _XcptFilter_0
0x18001c2a1  mov     [rbp+30h], eax
0x18001c2a4  jmp     short loc_18001C2AD
0x18001c2a6  mov     dword ptr [rbp+30h], 0
0x18001c2ad  mov     eax, [rbp+30h]
0x18001c2b0  add     rsp, 20h
0x18001c2b4  pop     rbp
0x18001c2b5  retn
0x18001c2b7  push    rbp
0x18001c2b9  sub     rsp, 20h
0x18001c2bd  mov     rbp, rdx
0x18001c2c0  mov     [rbp+110h], rcx
0x18001c2c7  mov     rax, [rcx]
0x18001c2ca  mov     edx, [rax]
0x18001c2cc  mov     [rbp+0A8h], edx
0x18001c2d2  mov     [rbp+0D0h], rcx
0x18001c2d9  mov     [rbp+38h], edx
0x18001c2dc  mov     eax, [rbp+38h]
0x18001c2df  cmp     eax, 0E06D7363h
0x18001c2e4  jnz     short loc_18001C2FA
0x18001c2e6  mov     rdx, [rbp+0D0h]
0x18001c2ed  mov     ecx, [rbp+38h]
0x18001c2f0  call    _XcptFilter_0
0x18001c2f5  mov     [rbp+40h], eax
0x18001c2f8  jmp     short loc_18001C301
0x18001c2fa  mov     dword ptr [rbp+40h], 0
0x18001c301  mov     eax, [rbp+40h]
0x18001c304  add     rsp, 20h
0x18001c308  pop     rbp
0x18001c309  retn
0x18001c30b  push    rbp
0x18001c30d  sub     rsp, 20h
0x18001c311  mov     rbp, rdx
0x18001c314  mov     [rbp+118h], rcx
0x18001c31b  mov     rax, [rcx]
0x18001c31e  mov     edx, [rax]
0x18001c320  mov     [rbp+0ACh], edx
0x18001c326  mov     [rbp+0D8h], rcx
0x18001c32d  mov     [rbp+48h], edx
0x18001c330  mov     eax, [rbp+48h]
0x18001c333  cmp     eax, 0E06D7363h
0x18001c338  jnz     short loc_18001C34E
0x18001c33a  mov     rdx, [rbp+0D8h]
0x18001c341  mov     ecx, [rbp+48h]
0x18001c344  call    _XcptFilter_0
0x18001c349  mov     [rbp+50h], eax
0x18001c34c  jmp     short loc_18001C355
0x18001c34e  mov     dword ptr [rbp+50h], 0
0x18001c355  mov     eax, [rbp+50h]
0x18001c358  add     rsp, 20h
0x18001c35c  pop     rbp
0x18001c35d  retn
0x18001c35f  push    rbp
0x18001c361  sub     rsp, 20h
0x18001c365  mov     rbp, rdx
0x18001c368  mov     [rbp+120h], rcx
0x18001c36f  mov     rax, [rcx]
0x18001c372  mov     edx, [rax]
0x18001c374  mov     [rbp+0B0h], edx
0x18001c37a  mov     [rbp+0E0h], rcx
0x18001c381  mov     [rbp+58h], edx
0x18001c384  mov     eax, [rbp+58h]
0x18001c387  cmp     eax, 0E06D7363h
0x18001c38c  jnz     short loc_18001C3A2
0x18001c38e  mov     rdx, [rbp+0E0h]
0x18001c395  mov     ecx, [rbp+58h]
0x18001c398  call    _XcptFilter_0
0x18001c39d  mov     [rbp+60h], eax
0x18001c3a0  jmp     short loc_18001C3A9
0x18001c3a2  mov     dword ptr [rbp+60h], 0
0x18001c3a9  mov     eax, [rbp+60h]
0x18001c3ac  add     rsp, 20h
0x18001c3b0  pop     rbp
0x18001c3b1  retn
0x18001c3b3  push    rbp
0x18001c3b5  sub     rsp, 20h
0x18001c3b9  mov     rbp, rdx
0x18001c3bc  mov     [rbp+128h], rcx
0x18001c3c3  mov     rax, [rcx]
0x18001c3c6  mov     edx, [rax]
0x18001c3c8  mov     [rbp+0B4h], edx
0x18001c3ce  mov     [rbp+0E8h], rcx
0x18001c3d5  mov     [rbp+68h], edx
0x18001c3d8  mov     eax, [rbp+68h]
0x18001c3db  cmp     eax, 0E06D7363h
0x18001c3e0  jnz     short loc_18001C3F6
0x18001c3e2  mov     rdx, [rbp+0E8h]
0x18001c3e9  mov     ecx, [rbp+68h]
0x18001c3ec  call    _XcptFilter_0
0x18001c3f1  mov     [rbp+70h], eax
0x18001c3f4  jmp     short loc_18001C3FD
0x18001c3f6  mov     dword ptr [rbp+70h], 0
0x18001c3fd  mov     eax, [rbp+70h]
0x18001c400  add     rsp, 20h
0x18001c404  pop     rbp
0x18001c405  retn
0x18001c407  push    rbp
0x18001c409  sub     rsp, 20h
0x18001c40d  mov     rbp, rdx
0x18001c410  mov     [rbp+130h], rcx
0x18001c417  mov     rax, [rcx]
0x18001c41a  mov     edx, [rax]
0x18001c41c  mov     [rbp+0B8h], edx
0x18001c422  mov     [rbp+0F0h], rcx
0x18001c429  mov     [rbp+78h], edx
0x18001c42c  mov     eax, [rbp+78h]
0x18001c42f  cmp     eax, 0E06D7363h
0x18001c434  jnz     short loc_18001C44D
0x18001c436  mov     rdx, [rbp+0F0h]
0x18001c43d  mov     ecx, [rbp+78h]
0x18001c440  call    _XcptFilter_0
0x18001c445  mov     [rbp+80h], eax
0x18001c44b  jmp     short loc_18001C457
0x18001c44d  mov     dword ptr [rbp+80h], 0
0x18001c457  mov     eax, [rbp+80h]
0x18001c45d  add     rsp, 20h
0x18001c461  pop     rbp
0x18001c462  retn
0x18001c464  push    rbp
0x18001c466  sub     rsp, 20h
0x18001c46a  mov     rbp, rdx
0x18001c46d  mov     [rbp+138h], rcx
0x18001c474  mov     rax, [rcx]
0x18001c477  mov     edx, [rax]
0x18001c479  mov     [rbp+0BCh], edx
0x18001c47f  mov     [rbp+0F8h], rcx
0x18001c486  mov     [rbp+88h], edx
0x18001c48c  mov     eax, [rbp+88h]
0x18001c492  cmp     eax, 0E06D7363h
0x18001c497  jnz     short loc_18001C4B3
0x18001c499  mov     rdx, [rbp+0F8h]
0x18001c4a0  mov     ecx, [rbp+88h]
0x18001c4a6  call    _XcptFilter_0
0x18001c4ab  mov     [rbp+90h], eax
0x18001c4b1  jmp     short loc_18001C4BD
0x18001c4b3  mov     dword ptr [rbp+90h], 0
0x18001c4bd  mov     eax, [rbp+90h]
0x18001c4c3  add     rsp, 20h
0x18001c4c7  pop     rbp
0x18001c4c8  retn
0x18001c4ca  push    rbp
0x18001c4cc  sub     rsp, 20h
0x18001c4d0  mov     rbp, rdx
0x18001c4d3  mov     [rbp+140h], rcx
0x18001c4da  mov     rax, [rcx]
0x18001c4dd  mov     edx, [rax]
0x18001c4df  mov     [rbp+0C0h], edx
0x18001c4e5  mov     [rbp+100h], rcx
0x18001c4ec  mov     [rbp+98h], edx
0x18001c4f2  mov     eax, [rbp+98h]
0x18001c4f8  cmp     eax, 0E06D7363h
  ... truncated ...
```
