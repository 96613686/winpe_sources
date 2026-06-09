# __DllMainCRTStartup

- ea: `0x180013894`
- end: `0x180013aa0`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180013850`

## callees

- `0x180013620`
- `0x180013894`
- `0x180013aca`
- `0x180013ca8`
- `0x1800160e0`

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
  if ( (_DWORD)fdwReason || dword_180020380 )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_180020384 = 1;
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
            if ( dword_180020384 )
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
0x180013894  mov     [rsp+lpvReserved], r8
0x180013899  mov     [rsp+arg_8], edx
0x18001389d  mov     [rsp+arg_0], rcx
0x1800138a2  push    rbx
0x1800138a3  push    rsi
0x1800138a4  push    rdi
0x1800138a5  sub     rsp, 0F0h
0x1800138ac  mov     edi, edx
0x1800138ae  mov     rsi, rcx
0x1800138b1  mov     ebx, 1
0x1800138b6  cmp     edx, ebx
0x1800138b8  ja      short loc_1800138C0
0x1800138ba  mov     cs:__native_dllmain_reason, edx
0x1800138c0  test    edx, edx
0x1800138c2  jnz     short loc_1800138D7
0x1800138c4  cmp     cs:dword_180020380, edx
0x1800138ca  jnz     short loc_1800138D7
0x1800138cc  xor     ebx, ebx
0x1800138ce  mov     [rsp+108h+var_E8], ebx
0x1800138d2  jmp     loc_180013A84
0x1800138d7  lea     eax, [rdx-1]
0x1800138da  cmp     eax, 1
0x1800138dd  ja      loc_180013964
0x1800138e3  mov     rax, cs:_pRawDllMain
0x1800138ea  test    rax, rax
0x1800138ed  jz      short loc_180013925
0x1800138ef  cmp     edx, 1
0x1800138f2  jnz     short loc_1800138FA
0x1800138f4  mov     cs:dword_180020384, edx
0x1800138fa  mov     r8, [rsp+108h+lpvReserved]
0x180013902  call    cs:__guard_dispatch_icall_fptr
0x180013908  mov     ebx, eax
0x18001390a  mov     [rsp+108h+var_E8], eax
0x18001390e  jmp     short loc_180013925
0x180013910  xor     ebx, ebx
0x180013912  mov     [rsp+108h+var_E8], ebx
0x180013916  mov     edi, [rsp+108h+arg_8]
0x18001391d  mov     rsi, [rsp+108h+arg_0]
0x180013925  test    ebx, ebx
0x180013927  jz      loc_180013A84
0x18001392d  mov     r8, [rsp+108h+lpvReserved]
0x180013935  mov     edx, edi
0x180013937  mov     rcx, rsi
0x18001393a  call    _CRT_INIT
0x18001393f  mov     ebx, eax
0x180013941  mov     [rsp+108h+var_E8], eax
0x180013945  jmp     short loc_18001395C
0x180013947  xor     ebx, ebx
0x180013949  mov     [rsp+108h+var_E8], ebx
0x18001394d  mov     edi, [rsp+108h+arg_8]
0x180013954  mov     rsi, [rsp+108h+arg_0]
0x18001395c  test    ebx, ebx
0x18001395e  jz      loc_180013A84
0x180013964  mov     r8, [rsp+108h+lpvReserved]; lpvReserved
0x18001396c  mov     edx, edi; fdwReason
0x18001396e  mov     rcx, rsi; hinstDLL
0x180013971  call    DllMain
0x180013976  mov     ebx, eax
0x180013978  mov     [rsp+108h+var_E8], eax
0x18001397c  jmp     short loc_180013993
0x18001397e  xor     ebx, ebx
0x180013980  mov     [rsp+108h+var_E8], ebx
0x180013984  mov     edi, [rsp+108h+arg_8]
0x18001398b  mov     rsi, [rsp+108h+arg_0]
0x180013993  cmp     edi, 1
0x180013996  jnz     short loc_180013A0F
0x180013998  test    ebx, ebx
0x18001399a  jnz     short loc_180013A0F
0x18001399c  xor     r8d, r8d; lpvReserved
0x18001399f  xor     edx, edx; fdwReason
0x1800139a1  mov     rcx, rsi; hinstDLL
0x1800139a4  call    DllMain
0x1800139a9  jmp     short loc_1800139BE
0x1800139ab  mov     edi, [rsp+108h+arg_8]
0x1800139b2  mov     rsi, [rsp+108h+arg_0]
0x1800139ba  mov     ebx, [rsp+108h+var_E8]
0x1800139be  xor     r8d, r8d
0x1800139c1  xor     edx, edx
0x1800139c3  mov     rcx, rsi
0x1800139c6  call    _CRT_INIT
0x1800139cb  jmp     short loc_1800139E0
0x1800139cd  mov     edi, [rsp+108h+arg_8]
0x1800139d4  mov     rsi, [rsp+108h+arg_0]
0x1800139dc  mov     ebx, [rsp+108h+var_E8]
0x1800139e0  mov     rax, cs:_pRawDllMain
0x1800139e7  test    rax, rax
0x1800139ea  jz      short loc_180013A0F
0x1800139ec  xor     r8d, r8d
0x1800139ef  xor     edx, edx
0x1800139f1  mov     rcx, rsi
0x1800139f4  call    cs:__guard_dispatch_icall_fptr
0x1800139fa  jmp     short loc_180013A0F
0x1800139fc  mov     edi, [rsp+108h+arg_8]
0x180013a03  mov     rsi, [rsp+108h+arg_0]
0x180013a0b  mov     ebx, [rsp+108h+var_E8]
0x180013a0f  test    edi, edi
0x180013a11  jz      short loc_180013A18
0x180013a13  cmp     edi, 3
0x180013a16  jnz     short loc_180013A84
0x180013a18  mov     r8, [rsp+108h+lpvReserved]
0x180013a20  mov     edx, edi
0x180013a22  mov     rcx, rsi
0x180013a25  call    _CRT_INIT
0x180013a2a  mov     ebx, eax
0x180013a2c  mov     [rsp+108h+var_E8], eax
0x180013a30  jmp     short loc_180013A47
0x180013a32  xor     ebx, ebx
0x180013a34  mov     [rsp+108h+var_E8], ebx
0x180013a38  mov     edi, [rsp+108h+arg_8]
0x180013a3f  mov     rsi, [rsp+108h+arg_0]
0x180013a47  mov     rax, cs:_pRawDllMain
0x180013a4e  test    rax, rax
0x180013a51  jz      short loc_180013A84
0x180013a53  cmp     cs:dword_180020384, 0
0x180013a5a  jz      short loc_180013A84
0x180013a5c  mov     r8, [rsp+108h+lpvReserved]
0x180013a64  mov     edx, edi
0x180013a66  mov     rcx, rsi
0x180013a69  call    cs:__guard_dispatch_icall_fptr
0x180013a6f  mov     ebx, eax
0x180013a71  mov     [rsp+108h+var_E8], eax
0x180013a75  jmp     short loc_180013A84
0x180013a77  xor     ebx, ebx
0x180013a79  mov     [rsp+108h+var_E8], ebx
0x180013a7d  mov     edi, [rsp+108h+arg_8]
0x180013a84  cmp     edi, 1
0x180013a87  ja      short loc_180013A93
0x180013a89  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x180013a93  mov     eax, ebx
0x180013a95  add     rsp, 0F0h
0x180013a9c  pop     rdi
0x180013a9d  pop     rsi
0x180013a9e  pop     rbx
0x180013a9f  retn
0x1800161b0  push    rbp
0x1800161b2  sub     rsp, 20h
0x1800161b6  mov     rbp, rdx
0x1800161b9  mov     rax, [rcx]
0x1800161bc  mov     edx, [rax]
0x1800161be  mov     [rbp+0A8h], rcx
0x1800161c5  mov     [rbp+28h], edx
0x1800161c8  mov     eax, [rbp+28h]
0x1800161cb  cmp     eax, 0E06D7363h
0x1800161d0  jnz     short loc_1800161E6
0x1800161d2  mov     rdx, [rbp+0A8h]
0x1800161d9  mov     ecx, [rbp+28h]
0x1800161dc  call    _XcptFilter_0
0x1800161e1  mov     [rbp+30h], eax
0x1800161e4  jmp     short loc_1800161ED
0x1800161e6  mov     dword ptr [rbp+30h], 0
0x1800161ed  mov     eax, [rbp+30h]
0x1800161f0  add     rsp, 20h
0x1800161f4  pop     rbp
0x1800161f5  retn
0x1800161f7  push    rbp
0x1800161f9  sub     rsp, 20h
0x1800161fd  mov     rbp, rdx
0x180016200  mov     rax, [rcx]
0x180016203  mov     edx, [rax]
0x180016205  mov     [rbp+0B0h], rcx
0x18001620c  mov     [rbp+38h], edx
0x18001620f  mov     eax, [rbp+38h]
0x180016212  cmp     eax, 0E06D7363h
0x180016217  jnz     short loc_18001622D
0x180016219  mov     rdx, [rbp+0B0h]
0x180016220  mov     ecx, [rbp+38h]
0x180016223  call    _XcptFilter_0
0x180016228  mov     [rbp+40h], eax
0x18001622b  jmp     short loc_180016234
0x18001622d  mov     dword ptr [rbp+40h], 0
0x180016234  mov     eax, [rbp+40h]
0x180016237  add     rsp, 20h
0x18001623b  pop     rbp
0x18001623c  retn
0x18001623e  push    rbp
0x180016240  sub     rsp, 20h
0x180016244  mov     rbp, rdx
0x180016247  mov     rax, [rcx]
0x18001624a  mov     edx, [rax]
0x18001624c  mov     [rbp+0B8h], rcx
0x180016253  mov     [rbp+48h], edx
0x180016256  mov     eax, [rbp+48h]
0x180016259  cmp     eax, 0E06D7363h
0x18001625e  jnz     short loc_180016274
0x180016260  mov     rdx, [rbp+0B8h]
0x180016267  mov     ecx, [rbp+48h]
0x18001626a  call    _XcptFilter_0
0x18001626f  mov     [rbp+50h], eax
0x180016272  jmp     short loc_18001627B
0x180016274  mov     dword ptr [rbp+50h], 0
0x18001627b  mov     eax, [rbp+50h]
0x18001627e  add     rsp, 20h
0x180016282  pop     rbp
0x180016283  retn
0x180016285  push    rbp
0x180016287  sub     rsp, 20h
0x18001628b  mov     rbp, rdx
0x18001628e  mov     rax, [rcx]
0x180016291  mov     edx, [rax]
0x180016293  mov     [rbp+0C0h], rcx
0x18001629a  mov     [rbp+58h], edx
0x18001629d  mov     eax, [rbp+58h]
0x1800162a0  cmp     eax, 0E06D7363h
0x1800162a5  jnz     short loc_1800162BB
0x1800162a7  mov     rdx, [rbp+0C0h]
0x1800162ae  mov     ecx, [rbp+58h]
0x1800162b1  call    _XcptFilter_0
0x1800162b6  mov     [rbp+60h], eax
0x1800162b9  jmp     short loc_1800162C2
0x1800162bb  mov     dword ptr [rbp+60h], 0
0x1800162c2  mov     eax, [rbp+60h]
0x1800162c5  add     rsp, 20h
0x1800162c9  pop     rbp
0x1800162ca  retn
0x1800162cc  push    rbp
0x1800162ce  sub     rsp, 20h
0x1800162d2  mov     rbp, rdx
0x1800162d5  mov     rax, [rcx]
0x1800162d8  mov     edx, [rax]
0x1800162da  mov     [rbp+0C8h], rcx
0x1800162e1  mov     [rbp+68h], edx
0x1800162e4  mov     eax, [rbp+68h]
0x1800162e7  cmp     eax, 0E06D7363h
0x1800162ec  jnz     short loc_180016302
0x1800162ee  mov     rdx, [rbp+0C8h]
0x1800162f5  mov     ecx, [rbp+68h]
0x1800162f8  call    _XcptFilter_0
0x1800162fd  mov     [rbp+70h], eax
0x180016300  jmp     short loc_180016309
0x180016302  mov     dword ptr [rbp+70h], 0
0x180016309  mov     eax, [rbp+70h]
0x18001630c  add     rsp, 20h
0x180016310  pop     rbp
0x180016311  retn
0x180016313  push    rbp
0x180016315  sub     rsp, 20h
0x180016319  mov     rbp, rdx
0x18001631c  mov     rax, [rcx]
0x18001631f  mov     edx, [rax]
0x180016321  mov     [rbp+0D0h], rcx
0x180016328  mov     [rbp+78h], edx
0x18001632b  mov     eax, [rbp+78h]
0x18001632e  cmp     eax, 0E06D7363h
0x180016333  jnz     short loc_18001634C
0x180016335  mov     rdx, [rbp+0D0h]
0x18001633c  mov     ecx, [rbp+78h]
0x18001633f  call    _XcptFilter_0
0x180016344  mov     [rbp+80h], eax
0x18001634a  jmp     short loc_180016356
0x18001634c  mov     dword ptr [rbp+80h], 0
0x180016356  mov     eax, [rbp+80h]
0x18001635c  add     rsp, 20h
0x180016360  pop     rbp
0x180016361  retn
0x180016363  push    rbp
0x180016365  sub     rsp, 20h
0x180016369  mov     rbp, rdx
0x18001636c  mov     rax, [rcx]
0x18001636f  mov     edx, [rax]
0x180016371  mov     [rbp+0D8h], rcx
0x180016378  mov     [rbp+88h], edx
0x18001637e  mov     eax, [rbp+88h]
0x180016384  cmp     eax, 0E06D7363h
0x180016389  jnz     short loc_1800163A5
0x18001638b  mov     rdx, [rbp+0D8h]
0x180016392  mov     ecx, [rbp+88h]
0x180016398  call    _XcptFilter_0
0x18001639d  mov     [rbp+90h], eax
0x1800163a3  jmp     short loc_1800163AF
0x1800163a5  mov     dword ptr [rbp+90h], 0
0x1800163af  mov     eax, [rbp+90h]
0x1800163b5  add     rsp, 20h
0x1800163b9  pop     rbp
0x1800163ba  retn
0x1800163bc  push    rbp
0x1800163be  sub     rsp, 20h
0x1800163c2  mov     rbp, rdx
0x1800163c5  mov     rax, [rcx]
0x1800163c8  mov     edx, [rax]
0x1800163ca  mov     [rbp+0E0h], rcx
0x1800163d1  mov     [rbp+98h], edx
0x1800163d7  mov     eax, [rbp+98h]
0x1800163dd  cmp     eax, 0E06D7363h
0x1800163e2  jnz     short loc_1800163FE
0x1800163e4  mov     rdx, [rbp+0E0h]
0x1800163eb  mov     ecx, [rbp+98h]
0x1800163f1  call    _XcptFilter_0
0x1800163f6  mov     [rbp+0A0h], eax
0x1800163fc  jmp     short loc_180016408
0x1800163fe  mov     dword ptr [rbp+0A0h], 0
0x180016408  mov     eax, [rbp+0A0h]
0x18001640e  add     rsp, 20h
0x180016412  pop     rbp
0x180016413  retn
0x180016415  push    rbp
0x180016417  sub     rsp, 20h
0x18001641b  mov     rbp, rdx
0x18001641e  cmp     dword ptr [rbp+118h], 1
0x180016425  ja      short loc_180016431
0x180016427  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
