# __DllMainCRTStartup

- ea: `0x180001594`
- end: `0x1800017a0`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, __int64 fdwReason, void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180001550`

## callees

- `0x180001320`
- `0x180001594`
- `0x1800017b6`
- `0x180001988`
- `0x1800028d0`

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
  if ( (_DWORD)fdwReason || dword_180006240 )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_180006244 = 1;
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
            if ( dword_180006244 )
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
0x180001594  mov     [rsp+lpvReserved], r8
0x180001599  mov     [rsp+arg_8], edx
0x18000159d  mov     [rsp+arg_0], rcx
0x1800015a2  push    rbx
0x1800015a3  push    rsi
0x1800015a4  push    rdi
0x1800015a5  sub     rsp, 0F0h
0x1800015ac  mov     edi, edx
0x1800015ae  mov     rsi, rcx
0x1800015b1  mov     ebx, 1
0x1800015b6  cmp     edx, ebx
0x1800015b8  ja      short loc_1800015C0
0x1800015ba  mov     cs:__native_dllmain_reason, edx
0x1800015c0  test    edx, edx
0x1800015c2  jnz     short loc_1800015D7
0x1800015c4  cmp     cs:dword_180006240, edx
0x1800015ca  jnz     short loc_1800015D7
0x1800015cc  xor     ebx, ebx
0x1800015ce  mov     [rsp+108h+var_E8], ebx
0x1800015d2  jmp     loc_180001784
0x1800015d7  lea     eax, [rdx-1]
0x1800015da  cmp     eax, 1
0x1800015dd  ja      loc_180001664
0x1800015e3  mov     rax, cs:_pRawDllMain
0x1800015ea  test    rax, rax
0x1800015ed  jz      short loc_180001625
0x1800015ef  cmp     edx, 1
0x1800015f2  jnz     short loc_1800015FA
0x1800015f4  mov     cs:dword_180006244, edx
0x1800015fa  mov     r8, [rsp+108h+lpvReserved]
0x180001602  call    cs:__guard_dispatch_icall_fptr
0x180001608  mov     ebx, eax
0x18000160a  mov     [rsp+108h+var_E8], eax
0x18000160e  jmp     short loc_180001625
0x180001610  xor     ebx, ebx
0x180001612  mov     [rsp+108h+var_E8], ebx
0x180001616  mov     edi, [rsp+108h+arg_8]
0x18000161d  mov     rsi, [rsp+108h+arg_0]
0x180001625  test    ebx, ebx
0x180001627  jz      loc_180001784
0x18000162d  mov     r8, [rsp+108h+lpvReserved]
0x180001635  mov     edx, edi
0x180001637  mov     rcx, rsi
0x18000163a  call    _CRT_INIT
0x18000163f  mov     ebx, eax
0x180001641  mov     [rsp+108h+var_E8], eax
0x180001645  jmp     short loc_18000165C
0x180001647  xor     ebx, ebx
0x180001649  mov     [rsp+108h+var_E8], ebx
0x18000164d  mov     edi, [rsp+108h+arg_8]
0x180001654  mov     rsi, [rsp+108h+arg_0]
0x18000165c  test    ebx, ebx
0x18000165e  jz      loc_180001784
0x180001664  mov     r8, [rsp+108h+lpvReserved]; lpvReserved
0x18000166c  mov     edx, edi; fdwReason
0x18000166e  mov     rcx, rsi; hinstDLL
0x180001671  call    DllMain
0x180001676  mov     ebx, eax
0x180001678  mov     [rsp+108h+var_E8], eax
0x18000167c  jmp     short loc_180001693
0x18000167e  xor     ebx, ebx
0x180001680  mov     [rsp+108h+var_E8], ebx
0x180001684  mov     edi, [rsp+108h+arg_8]
0x18000168b  mov     rsi, [rsp+108h+arg_0]
0x180001693  cmp     edi, 1
0x180001696  jnz     short loc_18000170F
0x180001698  test    ebx, ebx
0x18000169a  jnz     short loc_18000170F
0x18000169c  xor     r8d, r8d; lpvReserved
0x18000169f  xor     edx, edx; fdwReason
0x1800016a1  mov     rcx, rsi; hinstDLL
0x1800016a4  call    DllMain
0x1800016a9  jmp     short loc_1800016BE
0x1800016ab  mov     edi, [rsp+108h+arg_8]
0x1800016b2  mov     rsi, [rsp+108h+arg_0]
0x1800016ba  mov     ebx, [rsp+108h+var_E8]
0x1800016be  xor     r8d, r8d
0x1800016c1  xor     edx, edx
0x1800016c3  mov     rcx, rsi
0x1800016c6  call    _CRT_INIT
0x1800016cb  jmp     short loc_1800016E0
0x1800016cd  mov     edi, [rsp+108h+arg_8]
0x1800016d4  mov     rsi, [rsp+108h+arg_0]
0x1800016dc  mov     ebx, [rsp+108h+var_E8]
0x1800016e0  mov     rax, cs:_pRawDllMain
0x1800016e7  test    rax, rax
0x1800016ea  jz      short loc_18000170F
0x1800016ec  xor     r8d, r8d
0x1800016ef  xor     edx, edx
0x1800016f1  mov     rcx, rsi
0x1800016f4  call    cs:__guard_dispatch_icall_fptr
0x1800016fa  jmp     short loc_18000170F
0x1800016fc  mov     edi, [rsp+108h+arg_8]
0x180001703  mov     rsi, [rsp+108h+arg_0]
0x18000170b  mov     ebx, [rsp+108h+var_E8]
0x18000170f  test    edi, edi
0x180001711  jz      short loc_180001718
0x180001713  cmp     edi, 3
0x180001716  jnz     short loc_180001784
0x180001718  mov     r8, [rsp+108h+lpvReserved]
0x180001720  mov     edx, edi
0x180001722  mov     rcx, rsi
0x180001725  call    _CRT_INIT
0x18000172a  mov     ebx, eax
0x18000172c  mov     [rsp+108h+var_E8], eax
0x180001730  jmp     short loc_180001747
0x180001732  xor     ebx, ebx
0x180001734  mov     [rsp+108h+var_E8], ebx
0x180001738  mov     edi, [rsp+108h+arg_8]
0x18000173f  mov     rsi, [rsp+108h+arg_0]
0x180001747  mov     rax, cs:_pRawDllMain
0x18000174e  test    rax, rax
0x180001751  jz      short loc_180001784
0x180001753  cmp     cs:dword_180006244, 0
0x18000175a  jz      short loc_180001784
0x18000175c  mov     r8, [rsp+108h+lpvReserved]
0x180001764  mov     edx, edi
0x180001766  mov     rcx, rsi
0x180001769  call    cs:__guard_dispatch_icall_fptr
0x18000176f  mov     ebx, eax
0x180001771  mov     [rsp+108h+var_E8], eax
0x180001775  jmp     short loc_180001784
0x180001777  xor     ebx, ebx
0x180001779  mov     [rsp+108h+var_E8], ebx
0x18000177d  mov     edi, [rsp+108h+arg_8]
0x180001784  cmp     edi, 1
0x180001787  ja      short loc_180001793
0x180001789  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x180001793  mov     eax, ebx
0x180001795  add     rsp, 0F0h
0x18000179c  pop     rdi
0x18000179d  pop     rsi
0x18000179e  pop     rbx
0x18000179f  retn
0x180002940  push    rbp
0x180002942  sub     rsp, 20h
0x180002946  mov     rbp, rdx
0x180002949  mov     rax, [rcx]
0x18000294c  mov     edx, [rax]
0x18000294e  mov     [rbp+0A8h], rcx
0x180002955  mov     [rbp+28h], edx
0x180002958  mov     eax, [rbp+28h]
0x18000295b  cmp     eax, 0E06D7363h
0x180002960  jnz     short loc_180002976
0x180002962  mov     rdx, [rbp+0A8h]
0x180002969  mov     ecx, [rbp+28h]
0x18000296c  call    _XcptFilter_0
0x180002971  mov     [rbp+30h], eax
0x180002974  jmp     short loc_18000297D
0x180002976  mov     dword ptr [rbp+30h], 0
0x18000297d  mov     eax, [rbp+30h]
0x180002980  add     rsp, 20h
0x180002984  pop     rbp
0x180002985  retn
0x180002987  push    rbp
0x180002989  sub     rsp, 20h
0x18000298d  mov     rbp, rdx
0x180002990  mov     rax, [rcx]
0x180002993  mov     edx, [rax]
0x180002995  mov     [rbp+0B0h], rcx
0x18000299c  mov     [rbp+38h], edx
0x18000299f  mov     eax, [rbp+38h]
0x1800029a2  cmp     eax, 0E06D7363h
0x1800029a7  jnz     short loc_1800029BD
0x1800029a9  mov     rdx, [rbp+0B0h]
0x1800029b0  mov     ecx, [rbp+38h]
0x1800029b3  call    _XcptFilter_0
0x1800029b8  mov     [rbp+40h], eax
0x1800029bb  jmp     short loc_1800029C4
0x1800029bd  mov     dword ptr [rbp+40h], 0
0x1800029c4  mov     eax, [rbp+40h]
0x1800029c7  add     rsp, 20h
0x1800029cb  pop     rbp
0x1800029cc  retn
0x1800029ce  push    rbp
0x1800029d0  sub     rsp, 20h
0x1800029d4  mov     rbp, rdx
0x1800029d7  mov     rax, [rcx]
0x1800029da  mov     edx, [rax]
0x1800029dc  mov     [rbp+0B8h], rcx
0x1800029e3  mov     [rbp+48h], edx
0x1800029e6  mov     eax, [rbp+48h]
0x1800029e9  cmp     eax, 0E06D7363h
0x1800029ee  jnz     short loc_180002A04
0x1800029f0  mov     rdx, [rbp+0B8h]
0x1800029f7  mov     ecx, [rbp+48h]
0x1800029fa  call    _XcptFilter_0
0x1800029ff  mov     [rbp+50h], eax
0x180002a02  jmp     short loc_180002A0B
0x180002a04  mov     dword ptr [rbp+50h], 0
0x180002a0b  mov     eax, [rbp+50h]
0x180002a0e  add     rsp, 20h
0x180002a12  pop     rbp
0x180002a13  retn
0x180002a15  push    rbp
0x180002a17  sub     rsp, 20h
0x180002a1b  mov     rbp, rdx
0x180002a1e  mov     rax, [rcx]
0x180002a21  mov     edx, [rax]
0x180002a23  mov     [rbp+0C0h], rcx
0x180002a2a  mov     [rbp+58h], edx
0x180002a2d  mov     eax, [rbp+58h]
0x180002a30  cmp     eax, 0E06D7363h
0x180002a35  jnz     short loc_180002A4B
0x180002a37  mov     rdx, [rbp+0C0h]
0x180002a3e  mov     ecx, [rbp+58h]
0x180002a41  call    _XcptFilter_0
0x180002a46  mov     [rbp+60h], eax
0x180002a49  jmp     short loc_180002A52
0x180002a4b  mov     dword ptr [rbp+60h], 0
0x180002a52  mov     eax, [rbp+60h]
0x180002a55  add     rsp, 20h
0x180002a59  pop     rbp
0x180002a5a  retn
0x180002a5c  push    rbp
0x180002a5e  sub     rsp, 20h
0x180002a62  mov     rbp, rdx
0x180002a65  mov     rax, [rcx]
0x180002a68  mov     edx, [rax]
0x180002a6a  mov     [rbp+0C8h], rcx
0x180002a71  mov     [rbp+68h], edx
0x180002a74  mov     eax, [rbp+68h]
0x180002a77  cmp     eax, 0E06D7363h
0x180002a7c  jnz     short loc_180002A92
0x180002a7e  mov     rdx, [rbp+0C8h]
0x180002a85  mov     ecx, [rbp+68h]
0x180002a88  call    _XcptFilter_0
0x180002a8d  mov     [rbp+70h], eax
0x180002a90  jmp     short loc_180002A99
0x180002a92  mov     dword ptr [rbp+70h], 0
0x180002a99  mov     eax, [rbp+70h]
0x180002a9c  add     rsp, 20h
0x180002aa0  pop     rbp
0x180002aa1  retn
0x180002aa3  push    rbp
0x180002aa5  sub     rsp, 20h
0x180002aa9  mov     rbp, rdx
0x180002aac  mov     rax, [rcx]
0x180002aaf  mov     edx, [rax]
0x180002ab1  mov     [rbp+0D0h], rcx
0x180002ab8  mov     [rbp+78h], edx
0x180002abb  mov     eax, [rbp+78h]
0x180002abe  cmp     eax, 0E06D7363h
0x180002ac3  jnz     short loc_180002ADC
0x180002ac5  mov     rdx, [rbp+0D0h]
0x180002acc  mov     ecx, [rbp+78h]
0x180002acf  call    _XcptFilter_0
0x180002ad4  mov     [rbp+80h], eax
0x180002ada  jmp     short loc_180002AE6
0x180002adc  mov     dword ptr [rbp+80h], 0
0x180002ae6  mov     eax, [rbp+80h]
0x180002aec  add     rsp, 20h
0x180002af0  pop     rbp
0x180002af1  retn
0x180002af3  push    rbp
0x180002af5  sub     rsp, 20h
0x180002af9  mov     rbp, rdx
0x180002afc  mov     rax, [rcx]
0x180002aff  mov     edx, [rax]
0x180002b01  mov     [rbp+0D8h], rcx
0x180002b08  mov     [rbp+88h], edx
0x180002b0e  mov     eax, [rbp+88h]
0x180002b14  cmp     eax, 0E06D7363h
0x180002b19  jnz     short loc_180002B35
0x180002b1b  mov     rdx, [rbp+0D8h]
0x180002b22  mov     ecx, [rbp+88h]
0x180002b28  call    _XcptFilter_0
0x180002b2d  mov     [rbp+90h], eax
0x180002b33  jmp     short loc_180002B3F
0x180002b35  mov     dword ptr [rbp+90h], 0
0x180002b3f  mov     eax, [rbp+90h]
0x180002b45  add     rsp, 20h
0x180002b49  pop     rbp
0x180002b4a  retn
0x180002b4c  push    rbp
0x180002b4e  sub     rsp, 20h
0x180002b52  mov     rbp, rdx
0x180002b55  mov     rax, [rcx]
0x180002b58  mov     edx, [rax]
0x180002b5a  mov     [rbp+0E0h], rcx
0x180002b61  mov     [rbp+98h], edx
0x180002b67  mov     eax, [rbp+98h]
0x180002b6d  cmp     eax, 0E06D7363h
0x180002b72  jnz     short loc_180002B8E
0x180002b74  mov     rdx, [rbp+0E0h]
0x180002b7b  mov     ecx, [rbp+98h]
0x180002b81  call    _XcptFilter_0
0x180002b86  mov     [rbp+0A0h], eax
0x180002b8c  jmp     short loc_180002B98
0x180002b8e  mov     dword ptr [rbp+0A0h], 0
0x180002b98  mov     eax, [rbp+0A0h]
0x180002b9e  add     rsp, 20h
0x180002ba2  pop     rbp
0x180002ba3  retn
0x180002ba5  push    rbp
0x180002ba7  sub     rsp, 20h
0x180002bab  mov     rbp, rdx
0x180002bae  cmp     dword ptr [rbp+118h], 1
0x180002bb5  ja      short loc_180002BC1
0x180002bb7  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
