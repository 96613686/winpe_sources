# __DllMainCRTStartup

- ea: `0x1800015d4`
- end: `0x1800017e0`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, __int64 fdwReason, void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180001590`

## callees

- `0x180001360`
- `0x1800015d4`
- `0x18000198e`
- `0x180003230`
- `0x18001fec0`

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
  if ( (_DWORD)fdwReason || dword_18002F1BC )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_18002F1C0 = 1;
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
            if ( dword_18002F1C0 )
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
0x1800015d4  mov     [rsp+lpvReserved], r8
0x1800015d9  mov     [rsp+arg_8], edx
0x1800015dd  mov     [rsp+arg_0], rcx
0x1800015e2  push    rbx
0x1800015e3  push    rsi
0x1800015e4  push    rdi
0x1800015e5  sub     rsp, 0F0h
0x1800015ec  mov     edi, edx
0x1800015ee  mov     rsi, rcx
0x1800015f1  mov     ebx, 1
0x1800015f6  cmp     edx, ebx
0x1800015f8  ja      short loc_180001600
0x1800015fa  mov     cs:__native_dllmain_reason, edx
0x180001600  test    edx, edx
0x180001602  jnz     short loc_180001617
0x180001604  cmp     cs:dword_18002F1BC, edx
0x18000160a  jnz     short loc_180001617
0x18000160c  xor     ebx, ebx
0x18000160e  mov     [rsp+108h+var_E8], ebx
0x180001612  jmp     loc_1800017C4
0x180001617  lea     eax, [rdx-1]
0x18000161a  cmp     eax, 1
0x18000161d  ja      loc_1800016A4
0x180001623  mov     rax, cs:_pRawDllMain
0x18000162a  test    rax, rax
0x18000162d  jz      short loc_180001665
0x18000162f  cmp     edx, 1
0x180001632  jnz     short loc_18000163A
0x180001634  mov     cs:dword_18002F1C0, edx
0x18000163a  mov     r8, [rsp+108h+lpvReserved]
0x180001642  call    cs:__guard_dispatch_icall_fptr
0x180001648  mov     ebx, eax
0x18000164a  mov     [rsp+108h+var_E8], eax
0x18000164e  jmp     short loc_180001665
0x180001650  xor     ebx, ebx
0x180001652  mov     [rsp+108h+var_E8], ebx
0x180001656  mov     edi, [rsp+108h+arg_8]
0x18000165d  mov     rsi, [rsp+108h+arg_0]
0x180001665  test    ebx, ebx
0x180001667  jz      loc_1800017C4
0x18000166d  mov     r8, [rsp+108h+lpvReserved]
0x180001675  mov     edx, edi
0x180001677  mov     rcx, rsi
0x18000167a  call    _CRT_INIT
0x18000167f  mov     ebx, eax
0x180001681  mov     [rsp+108h+var_E8], eax
0x180001685  jmp     short loc_18000169C
0x180001687  xor     ebx, ebx
0x180001689  mov     [rsp+108h+var_E8], ebx
0x18000168d  mov     edi, [rsp+108h+arg_8]
0x180001694  mov     rsi, [rsp+108h+arg_0]
0x18000169c  test    ebx, ebx
0x18000169e  jz      loc_1800017C4
0x1800016a4  mov     r8, [rsp+108h+lpvReserved]; lpvReserved
0x1800016ac  mov     edx, edi; fdwReason
0x1800016ae  mov     rcx, rsi; hinstDLL
0x1800016b1  call    DllMain
0x1800016b6  mov     ebx, eax
0x1800016b8  mov     [rsp+108h+var_E8], eax
0x1800016bc  jmp     short loc_1800016D3
0x1800016be  xor     ebx, ebx
0x1800016c0  mov     [rsp+108h+var_E8], ebx
0x1800016c4  mov     edi, [rsp+108h+arg_8]
0x1800016cb  mov     rsi, [rsp+108h+arg_0]
0x1800016d3  cmp     edi, 1
0x1800016d6  jnz     short loc_18000174F
0x1800016d8  test    ebx, ebx
0x1800016da  jnz     short loc_18000174F
0x1800016dc  xor     r8d, r8d; lpvReserved
0x1800016df  xor     edx, edx; fdwReason
0x1800016e1  mov     rcx, rsi; hinstDLL
0x1800016e4  call    DllMain
0x1800016e9  jmp     short loc_1800016FE
0x1800016eb  mov     edi, [rsp+108h+arg_8]
0x1800016f2  mov     rsi, [rsp+108h+arg_0]
0x1800016fa  mov     ebx, [rsp+108h+var_E8]
0x1800016fe  xor     r8d, r8d
0x180001701  xor     edx, edx
0x180001703  mov     rcx, rsi
0x180001706  call    _CRT_INIT
0x18000170b  jmp     short loc_180001720
0x18000170d  mov     edi, [rsp+108h+arg_8]
0x180001714  mov     rsi, [rsp+108h+arg_0]
0x18000171c  mov     ebx, [rsp+108h+var_E8]
0x180001720  mov     rax, cs:_pRawDllMain
0x180001727  test    rax, rax
0x18000172a  jz      short loc_18000174F
0x18000172c  xor     r8d, r8d
0x18000172f  xor     edx, edx
0x180001731  mov     rcx, rsi
0x180001734  call    cs:__guard_dispatch_icall_fptr
0x18000173a  jmp     short loc_18000174F
0x18000173c  mov     edi, [rsp+108h+arg_8]
0x180001743  mov     rsi, [rsp+108h+arg_0]
0x18000174b  mov     ebx, [rsp+108h+var_E8]
0x18000174f  test    edi, edi
0x180001751  jz      short loc_180001758
0x180001753  cmp     edi, 3
0x180001756  jnz     short loc_1800017C4
0x180001758  mov     r8, [rsp+108h+lpvReserved]
0x180001760  mov     edx, edi
0x180001762  mov     rcx, rsi
0x180001765  call    _CRT_INIT
0x18000176a  mov     ebx, eax
0x18000176c  mov     [rsp+108h+var_E8], eax
0x180001770  jmp     short loc_180001787
0x180001772  xor     ebx, ebx
0x180001774  mov     [rsp+108h+var_E8], ebx
0x180001778  mov     edi, [rsp+108h+arg_8]
0x18000177f  mov     rsi, [rsp+108h+arg_0]
0x180001787  mov     rax, cs:_pRawDllMain
0x18000178e  test    rax, rax
0x180001791  jz      short loc_1800017C4
0x180001793  cmp     cs:dword_18002F1C0, 0
0x18000179a  jz      short loc_1800017C4
0x18000179c  mov     r8, [rsp+108h+lpvReserved]
0x1800017a4  mov     edx, edi
0x1800017a6  mov     rcx, rsi
0x1800017a9  call    cs:__guard_dispatch_icall_fptr
0x1800017af  mov     ebx, eax
0x1800017b1  mov     [rsp+108h+var_E8], eax
0x1800017b5  jmp     short loc_1800017C4
0x1800017b7  xor     ebx, ebx
0x1800017b9  mov     [rsp+108h+var_E8], ebx
0x1800017bd  mov     edi, [rsp+108h+arg_8]
0x1800017c4  cmp     edi, 1
0x1800017c7  ja      short loc_1800017D3
0x1800017c9  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x1800017d3  mov     eax, ebx
0x1800017d5  add     rsp, 0F0h
0x1800017dc  pop     rdi
0x1800017dd  pop     rsi
0x1800017de  pop     rbx
0x1800017df  retn
0x18001ff00  push    rbp
0x18001ff02  sub     rsp, 20h
0x18001ff06  mov     rbp, rdx
0x18001ff09  mov     rax, [rcx]
0x18001ff0c  mov     edx, [rax]
0x18001ff0e  mov     [rbp+0A8h], rcx
0x18001ff15  mov     [rbp+28h], edx
0x18001ff18  mov     eax, [rbp+28h]
0x18001ff1b  cmp     eax, 0E06D7363h
0x18001ff20  jnz     short loc_18001FF36
0x18001ff22  mov     rdx, [rbp+0A8h]
0x18001ff29  mov     ecx, [rbp+28h]
0x18001ff2c  call    _XcptFilter_0
0x18001ff31  mov     [rbp+30h], eax
0x18001ff34  jmp     short loc_18001FF3D
0x18001ff36  mov     dword ptr [rbp+30h], 0
0x18001ff3d  mov     eax, [rbp+30h]
0x18001ff40  add     rsp, 20h
0x18001ff44  pop     rbp
0x18001ff45  retn
0x18001ff47  push    rbp
0x18001ff49  sub     rsp, 20h
0x18001ff4d  mov     rbp, rdx
0x18001ff50  mov     rax, [rcx]
0x18001ff53  mov     edx, [rax]
0x18001ff55  mov     [rbp+0B0h], rcx
0x18001ff5c  mov     [rbp+38h], edx
0x18001ff5f  mov     eax, [rbp+38h]
0x18001ff62  cmp     eax, 0E06D7363h
0x18001ff67  jnz     short loc_18001FF7D
0x18001ff69  mov     rdx, [rbp+0B0h]
0x18001ff70  mov     ecx, [rbp+38h]
0x18001ff73  call    _XcptFilter_0
0x18001ff78  mov     [rbp+40h], eax
0x18001ff7b  jmp     short loc_18001FF84
0x18001ff7d  mov     dword ptr [rbp+40h], 0
0x18001ff84  mov     eax, [rbp+40h]
0x18001ff87  add     rsp, 20h
0x18001ff8b  pop     rbp
0x18001ff8c  retn
0x18001ff8e  push    rbp
0x18001ff90  sub     rsp, 20h
0x18001ff94  mov     rbp, rdx
0x18001ff97  mov     rax, [rcx]
0x18001ff9a  mov     edx, [rax]
0x18001ff9c  mov     [rbp+0B8h], rcx
0x18001ffa3  mov     [rbp+48h], edx
0x18001ffa6  mov     eax, [rbp+48h]
0x18001ffa9  cmp     eax, 0E06D7363h
0x18001ffae  jnz     short loc_18001FFC4
0x18001ffb0  mov     rdx, [rbp+0B8h]
0x18001ffb7  mov     ecx, [rbp+48h]
0x18001ffba  call    _XcptFilter_0
0x18001ffbf  mov     [rbp+50h], eax
0x18001ffc2  jmp     short loc_18001FFCB
0x18001ffc4  mov     dword ptr [rbp+50h], 0
0x18001ffcb  mov     eax, [rbp+50h]
0x18001ffce  add     rsp, 20h
0x18001ffd2  pop     rbp
0x18001ffd3  retn
0x18001ffd5  push    rbp
0x18001ffd7  sub     rsp, 20h
0x18001ffdb  mov     rbp, rdx
0x18001ffde  mov     rax, [rcx]
0x18001ffe1  mov     edx, [rax]
0x18001ffe3  mov     [rbp+0C0h], rcx
0x18001ffea  mov     [rbp+58h], edx
0x18001ffed  mov     eax, [rbp+58h]
0x18001fff0  cmp     eax, 0E06D7363h
0x18001fff5  jnz     short loc_18002000B
0x18001fff7  mov     rdx, [rbp+0C0h]
0x18001fffe  mov     ecx, [rbp+58h]
0x180020001  call    _XcptFilter_0
0x180020006  mov     [rbp+60h], eax
0x180020009  jmp     short loc_180020012
0x18002000b  mov     dword ptr [rbp+60h], 0
0x180020012  mov     eax, [rbp+60h]
0x180020015  add     rsp, 20h
0x180020019  pop     rbp
0x18002001a  retn
0x18002001c  push    rbp
0x18002001e  sub     rsp, 20h
0x180020022  mov     rbp, rdx
0x180020025  mov     rax, [rcx]
0x180020028  mov     edx, [rax]
0x18002002a  mov     [rbp+0C8h], rcx
0x180020031  mov     [rbp+68h], edx
0x180020034  mov     eax, [rbp+68h]
0x180020037  cmp     eax, 0E06D7363h
0x18002003c  jnz     short loc_180020052
0x18002003e  mov     rdx, [rbp+0C8h]
0x180020045  mov     ecx, [rbp+68h]
0x180020048  call    _XcptFilter_0
0x18002004d  mov     [rbp+70h], eax
0x180020050  jmp     short loc_180020059
0x180020052  mov     dword ptr [rbp+70h], 0
0x180020059  mov     eax, [rbp+70h]
0x18002005c  add     rsp, 20h
0x180020060  pop     rbp
0x180020061  retn
0x180020063  push    rbp
0x180020065  sub     rsp, 20h
0x180020069  mov     rbp, rdx
0x18002006c  mov     rax, [rcx]
0x18002006f  mov     edx, [rax]
0x180020071  mov     [rbp+0D0h], rcx
0x180020078  mov     [rbp+78h], edx
0x18002007b  mov     eax, [rbp+78h]
0x18002007e  cmp     eax, 0E06D7363h
0x180020083  jnz     short loc_18002009C
0x180020085  mov     rdx, [rbp+0D0h]
0x18002008c  mov     ecx, [rbp+78h]
0x18002008f  call    _XcptFilter_0
0x180020094  mov     [rbp+80h], eax
0x18002009a  jmp     short loc_1800200A6
0x18002009c  mov     dword ptr [rbp+80h], 0
0x1800200a6  mov     eax, [rbp+80h]
0x1800200ac  add     rsp, 20h
0x1800200b0  pop     rbp
0x1800200b1  retn
0x1800200b3  push    rbp
0x1800200b5  sub     rsp, 20h
0x1800200b9  mov     rbp, rdx
0x1800200bc  mov     rax, [rcx]
0x1800200bf  mov     edx, [rax]
0x1800200c1  mov     [rbp+0D8h], rcx
0x1800200c8  mov     [rbp+88h], edx
0x1800200ce  mov     eax, [rbp+88h]
0x1800200d4  cmp     eax, 0E06D7363h
0x1800200d9  jnz     short loc_1800200F5
0x1800200db  mov     rdx, [rbp+0D8h]
0x1800200e2  mov     ecx, [rbp+88h]
0x1800200e8  call    _XcptFilter_0
0x1800200ed  mov     [rbp+90h], eax
0x1800200f3  jmp     short loc_1800200FF
0x1800200f5  mov     dword ptr [rbp+90h], 0
0x1800200ff  mov     eax, [rbp+90h]
0x180020105  add     rsp, 20h
0x180020109  pop     rbp
0x18002010a  retn
0x18002010c  push    rbp
0x18002010e  sub     rsp, 20h
0x180020112  mov     rbp, rdx
0x180020115  mov     rax, [rcx]
0x180020118  mov     edx, [rax]
0x18002011a  mov     [rbp+0E0h], rcx
0x180020121  mov     [rbp+98h], edx
0x180020127  mov     eax, [rbp+98h]
0x18002012d  cmp     eax, 0E06D7363h
0x180020132  jnz     short loc_18002014E
0x180020134  mov     rdx, [rbp+0E0h]
0x18002013b  mov     ecx, [rbp+98h]
0x180020141  call    _XcptFilter_0
0x180020146  mov     [rbp+0A0h], eax
0x18002014c  jmp     short loc_180020158
0x18002014e  mov     dword ptr [rbp+0A0h], 0
0x180020158  mov     eax, [rbp+0A0h]
0x18002015e  add     rsp, 20h
0x180020162  pop     rbp
0x180020163  retn
0x180020165  push    rbp
0x180020167  sub     rsp, 20h
0x18002016b  mov     rbp, rdx
0x18002016e  cmp     dword ptr [rbp+118h], 1
0x180020175  ja      short loc_180020181
0x180020177  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
