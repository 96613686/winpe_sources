# __DllMainCRTStartup

- ea: `0x180001f54`
- end: `0x180002160`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180001f10`

## callees

- `0x180001ce0`
- `0x180001f54`
- `0x180002336`
- `0x180002508`
- `0x18000af10`

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
  if ( (_DWORD)fdwReason || dword_18001320C )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_180013210 = 1;
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
            if ( dword_180013210 )
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
0x180001f54  mov     [rsp+lpvReserved], r8
0x180001f59  mov     [rsp+arg_8], edx
0x180001f5d  mov     [rsp+arg_0], rcx
0x180001f62  push    rbx
0x180001f63  push    rsi
0x180001f64  push    rdi
0x180001f65  sub     rsp, 0F0h
0x180001f6c  mov     edi, edx
0x180001f6e  mov     rsi, rcx
0x180001f71  mov     ebx, 1
0x180001f76  cmp     edx, ebx
0x180001f78  ja      short loc_180001F80
0x180001f7a  mov     cs:__native_dllmain_reason, edx
0x180001f80  test    edx, edx
0x180001f82  jnz     short loc_180001F97
0x180001f84  cmp     cs:dword_18001320C, edx
0x180001f8a  jnz     short loc_180001F97
0x180001f8c  xor     ebx, ebx
0x180001f8e  mov     [rsp+108h+var_E8], ebx
0x180001f92  jmp     loc_180002144
0x180001f97  lea     eax, [rdx-1]
0x180001f9a  cmp     eax, 1
0x180001f9d  ja      loc_180002024
0x180001fa3  mov     rax, cs:_pRawDllMain
0x180001faa  test    rax, rax
0x180001fad  jz      short loc_180001FE5
0x180001faf  cmp     edx, 1
0x180001fb2  jnz     short loc_180001FBA
0x180001fb4  mov     cs:dword_180013210, edx
0x180001fba  mov     r8, [rsp+108h+lpvReserved]
0x180001fc2  call    cs:__guard_dispatch_icall_fptr
0x180001fc8  mov     ebx, eax
0x180001fca  mov     [rsp+108h+var_E8], eax
0x180001fce  jmp     short loc_180001FE5
0x180001fd0  xor     ebx, ebx
0x180001fd2  mov     [rsp+108h+var_E8], ebx
0x180001fd6  mov     edi, [rsp+108h+arg_8]
0x180001fdd  mov     rsi, [rsp+108h+arg_0]
0x180001fe5  test    ebx, ebx
0x180001fe7  jz      loc_180002144
0x180001fed  mov     r8, [rsp+108h+lpvReserved]
0x180001ff5  mov     edx, edi
0x180001ff7  mov     rcx, rsi
0x180001ffa  call    _CRT_INIT
0x180001fff  mov     ebx, eax
0x180002001  mov     [rsp+108h+var_E8], eax
0x180002005  jmp     short loc_18000201C
0x180002007  xor     ebx, ebx
0x180002009  mov     [rsp+108h+var_E8], ebx
0x18000200d  mov     edi, [rsp+108h+arg_8]
0x180002014  mov     rsi, [rsp+108h+arg_0]
0x18000201c  test    ebx, ebx
0x18000201e  jz      loc_180002144
0x180002024  mov     r8, [rsp+108h+lpvReserved]; lpvReserved
0x18000202c  mov     edx, edi; fdwReason
0x18000202e  mov     rcx, rsi; hinstDLL
0x180002031  call    DllMain
0x180002036  mov     ebx, eax
0x180002038  mov     [rsp+108h+var_E8], eax
0x18000203c  jmp     short loc_180002053
0x18000203e  xor     ebx, ebx
0x180002040  mov     [rsp+108h+var_E8], ebx
0x180002044  mov     edi, [rsp+108h+arg_8]
0x18000204b  mov     rsi, [rsp+108h+arg_0]
0x180002053  cmp     edi, 1
0x180002056  jnz     short loc_1800020CF
0x180002058  test    ebx, ebx
0x18000205a  jnz     short loc_1800020CF
0x18000205c  xor     r8d, r8d; lpvReserved
0x18000205f  xor     edx, edx; fdwReason
0x180002061  mov     rcx, rsi; hinstDLL
0x180002064  call    DllMain
0x180002069  jmp     short loc_18000207E
0x18000206b  mov     edi, [rsp+108h+arg_8]
0x180002072  mov     rsi, [rsp+108h+arg_0]
0x18000207a  mov     ebx, [rsp+108h+var_E8]
0x18000207e  xor     r8d, r8d
0x180002081  xor     edx, edx
0x180002083  mov     rcx, rsi
0x180002086  call    _CRT_INIT
0x18000208b  jmp     short loc_1800020A0
0x18000208d  mov     edi, [rsp+108h+arg_8]
0x180002094  mov     rsi, [rsp+108h+arg_0]
0x18000209c  mov     ebx, [rsp+108h+var_E8]
0x1800020a0  mov     rax, cs:_pRawDllMain
0x1800020a7  test    rax, rax
0x1800020aa  jz      short loc_1800020CF
0x1800020ac  xor     r8d, r8d
0x1800020af  xor     edx, edx
0x1800020b1  mov     rcx, rsi
0x1800020b4  call    cs:__guard_dispatch_icall_fptr
0x1800020ba  jmp     short loc_1800020CF
0x1800020bc  mov     edi, [rsp+108h+arg_8]
0x1800020c3  mov     rsi, [rsp+108h+arg_0]
0x1800020cb  mov     ebx, [rsp+108h+var_E8]
0x1800020cf  test    edi, edi
0x1800020d1  jz      short loc_1800020D8
0x1800020d3  cmp     edi, 3
0x1800020d6  jnz     short loc_180002144
0x1800020d8  mov     r8, [rsp+108h+lpvReserved]
0x1800020e0  mov     edx, edi
0x1800020e2  mov     rcx, rsi
0x1800020e5  call    _CRT_INIT
0x1800020ea  mov     ebx, eax
0x1800020ec  mov     [rsp+108h+var_E8], eax
0x1800020f0  jmp     short loc_180002107
0x1800020f2  xor     ebx, ebx
0x1800020f4  mov     [rsp+108h+var_E8], ebx
0x1800020f8  mov     edi, [rsp+108h+arg_8]
0x1800020ff  mov     rsi, [rsp+108h+arg_0]
0x180002107  mov     rax, cs:_pRawDllMain
0x18000210e  test    rax, rax
0x180002111  jz      short loc_180002144
0x180002113  cmp     cs:dword_180013210, 0
0x18000211a  jz      short loc_180002144
0x18000211c  mov     r8, [rsp+108h+lpvReserved]
0x180002124  mov     edx, edi
0x180002126  mov     rcx, rsi
0x180002129  call    cs:__guard_dispatch_icall_fptr
0x18000212f  mov     ebx, eax
0x180002131  mov     [rsp+108h+var_E8], eax
0x180002135  jmp     short loc_180002144
0x180002137  xor     ebx, ebx
0x180002139  mov     [rsp+108h+var_E8], ebx
0x18000213d  mov     edi, [rsp+108h+arg_8]
0x180002144  cmp     edi, 1
0x180002147  ja      short loc_180002153
0x180002149  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x180002153  mov     eax, ebx
0x180002155  add     rsp, 0F0h
0x18000215c  pop     rdi
0x18000215d  pop     rsi
0x18000215e  pop     rbx
0x18000215f  retn
0x18000afbf  push    rbp
0x18000afc1  sub     rsp, 20h
0x18000afc5  mov     rbp, rdx
0x18000afc8  mov     rax, [rcx]
0x18000afcb  mov     edx, [rax]
0x18000afcd  mov     [rbp+0A8h], rcx
0x18000afd4  mov     [rbp+28h], edx
0x18000afd7  mov     eax, [rbp+28h]
0x18000afda  cmp     eax, 0E06D7363h
0x18000afdf  jnz     short loc_18000AFF5
0x18000afe1  mov     rdx, [rbp+0A8h]
0x18000afe8  mov     ecx, [rbp+28h]
0x18000afeb  call    _XcptFilter_0
0x18000aff0  mov     [rbp+30h], eax
0x18000aff3  jmp     short loc_18000AFFC
0x18000aff5  mov     dword ptr [rbp+30h], 0
0x18000affc  mov     eax, [rbp+30h]
0x18000afff  add     rsp, 20h
0x18000b003  pop     rbp
0x18000b004  retn
0x18000b006  push    rbp
0x18000b008  sub     rsp, 20h
0x18000b00c  mov     rbp, rdx
0x18000b00f  mov     rax, [rcx]
0x18000b012  mov     edx, [rax]
0x18000b014  mov     [rbp+0B0h], rcx
0x18000b01b  mov     [rbp+38h], edx
0x18000b01e  mov     eax, [rbp+38h]
0x18000b021  cmp     eax, 0E06D7363h
0x18000b026  jnz     short loc_18000B03C
0x18000b028  mov     rdx, [rbp+0B0h]
0x18000b02f  mov     ecx, [rbp+38h]
0x18000b032  call    _XcptFilter_0
0x18000b037  mov     [rbp+40h], eax
0x18000b03a  jmp     short loc_18000B043
0x18000b03c  mov     dword ptr [rbp+40h], 0
0x18000b043  mov     eax, [rbp+40h]
0x18000b046  add     rsp, 20h
0x18000b04a  pop     rbp
0x18000b04b  retn
0x18000b04d  push    rbp
0x18000b04f  sub     rsp, 20h
0x18000b053  mov     rbp, rdx
0x18000b056  mov     rax, [rcx]
0x18000b059  mov     edx, [rax]
0x18000b05b  mov     [rbp+0B8h], rcx
0x18000b062  mov     [rbp+48h], edx
0x18000b065  mov     eax, [rbp+48h]
0x18000b068  cmp     eax, 0E06D7363h
0x18000b06d  jnz     short loc_18000B083
0x18000b06f  mov     rdx, [rbp+0B8h]
0x18000b076  mov     ecx, [rbp+48h]
0x18000b079  call    _XcptFilter_0
0x18000b07e  mov     [rbp+50h], eax
0x18000b081  jmp     short loc_18000B08A
0x18000b083  mov     dword ptr [rbp+50h], 0
0x18000b08a  mov     eax, [rbp+50h]
0x18000b08d  add     rsp, 20h
0x18000b091  pop     rbp
0x18000b092  retn
0x18000b094  push    rbp
0x18000b096  sub     rsp, 20h
0x18000b09a  mov     rbp, rdx
0x18000b09d  mov     rax, [rcx]
0x18000b0a0  mov     edx, [rax]
0x18000b0a2  mov     [rbp+0C0h], rcx
0x18000b0a9  mov     [rbp+58h], edx
0x18000b0ac  mov     eax, [rbp+58h]
0x18000b0af  cmp     eax, 0E06D7363h
0x18000b0b4  jnz     short loc_18000B0CA
0x18000b0b6  mov     rdx, [rbp+0C0h]
0x18000b0bd  mov     ecx, [rbp+58h]
0x18000b0c0  call    _XcptFilter_0
0x18000b0c5  mov     [rbp+60h], eax
0x18000b0c8  jmp     short loc_18000B0D1
0x18000b0ca  mov     dword ptr [rbp+60h], 0
0x18000b0d1  mov     eax, [rbp+60h]
0x18000b0d4  add     rsp, 20h
0x18000b0d8  pop     rbp
0x18000b0d9  retn
0x18000b0db  push    rbp
0x18000b0dd  sub     rsp, 20h
0x18000b0e1  mov     rbp, rdx
0x18000b0e4  mov     rax, [rcx]
0x18000b0e7  mov     edx, [rax]
0x18000b0e9  mov     [rbp+0C8h], rcx
0x18000b0f0  mov     [rbp+68h], edx
0x18000b0f3  mov     eax, [rbp+68h]
0x18000b0f6  cmp     eax, 0E06D7363h
0x18000b0fb  jnz     short loc_18000B111
0x18000b0fd  mov     rdx, [rbp+0C8h]
0x18000b104  mov     ecx, [rbp+68h]
0x18000b107  call    _XcptFilter_0
0x18000b10c  mov     [rbp+70h], eax
0x18000b10f  jmp     short loc_18000B118
0x18000b111  mov     dword ptr [rbp+70h], 0
0x18000b118  mov     eax, [rbp+70h]
0x18000b11b  add     rsp, 20h
0x18000b11f  pop     rbp
0x18000b120  retn
0x18000b122  push    rbp
0x18000b124  sub     rsp, 20h
0x18000b128  mov     rbp, rdx
0x18000b12b  mov     rax, [rcx]
0x18000b12e  mov     edx, [rax]
0x18000b130  mov     [rbp+0D0h], rcx
0x18000b137  mov     [rbp+78h], edx
0x18000b13a  mov     eax, [rbp+78h]
0x18000b13d  cmp     eax, 0E06D7363h
0x18000b142  jnz     short loc_18000B15B
0x18000b144  mov     rdx, [rbp+0D0h]
0x18000b14b  mov     ecx, [rbp+78h]
0x18000b14e  call    _XcptFilter_0
0x18000b153  mov     [rbp+80h], eax
0x18000b159  jmp     short loc_18000B165
0x18000b15b  mov     dword ptr [rbp+80h], 0
0x18000b165  mov     eax, [rbp+80h]
0x18000b16b  add     rsp, 20h
0x18000b16f  pop     rbp
0x18000b170  retn
0x18000b172  push    rbp
0x18000b174  sub     rsp, 20h
0x18000b178  mov     rbp, rdx
0x18000b17b  mov     rax, [rcx]
0x18000b17e  mov     edx, [rax]
0x18000b180  mov     [rbp+0D8h], rcx
0x18000b187  mov     [rbp+88h], edx
0x18000b18d  mov     eax, [rbp+88h]
0x18000b193  cmp     eax, 0E06D7363h
0x18000b198  jnz     short loc_18000B1B4
0x18000b19a  mov     rdx, [rbp+0D8h]
0x18000b1a1  mov     ecx, [rbp+88h]
0x18000b1a7  call    _XcptFilter_0
0x18000b1ac  mov     [rbp+90h], eax
0x18000b1b2  jmp     short loc_18000B1BE
0x18000b1b4  mov     dword ptr [rbp+90h], 0
0x18000b1be  mov     eax, [rbp+90h]
0x18000b1c4  add     rsp, 20h
0x18000b1c8  pop     rbp
0x18000b1c9  retn
0x18000b1cb  push    rbp
0x18000b1cd  sub     rsp, 20h
0x18000b1d1  mov     rbp, rdx
0x18000b1d4  mov     rax, [rcx]
0x18000b1d7  mov     edx, [rax]
0x18000b1d9  mov     [rbp+0E0h], rcx
0x18000b1e0  mov     [rbp+98h], edx
0x18000b1e6  mov     eax, [rbp+98h]
0x18000b1ec  cmp     eax, 0E06D7363h
0x18000b1f1  jnz     short loc_18000B20D
0x18000b1f3  mov     rdx, [rbp+0E0h]
0x18000b1fa  mov     ecx, [rbp+98h]
0x18000b200  call    _XcptFilter_0
0x18000b205  mov     [rbp+0A0h], eax
0x18000b20b  jmp     short loc_18000B217
0x18000b20d  mov     dword ptr [rbp+0A0h], 0
0x18000b217  mov     eax, [rbp+0A0h]
0x18000b21d  add     rsp, 20h
0x18000b221  pop     rbp
0x18000b222  retn
0x18000b224  push    rbp
0x18000b226  sub     rsp, 20h
0x18000b22a  mov     rbp, rdx
0x18000b22d  cmp     dword ptr [rbp+118h], 1
0x18000b234  ja      short loc_18000B240
0x18000b236  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
