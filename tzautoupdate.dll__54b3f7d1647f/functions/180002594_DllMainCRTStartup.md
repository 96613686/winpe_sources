# __DllMainCRTStartup

- ea: `0x180002594`
- end: `0x1800027a0`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, __int64 fdwReason, void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180002550`

## callees

- `0x180002320`
- `0x180002594`
- `0x18000299e`
- `0x180002b78`
- `0x18001b1c0`

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
  if ( (_DWORD)fdwReason || dword_180030B34 )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_180030B38 = 1;
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
            if ( dword_180030B38 )
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
0x180002594  mov     [rsp+lpvReserved], r8
0x180002599  mov     [rsp+arg_8], edx
0x18000259d  mov     [rsp+arg_0], rcx
0x1800025a2  push    rbx
0x1800025a3  push    rsi
0x1800025a4  push    rdi
0x1800025a5  sub     rsp, 0F0h
0x1800025ac  mov     edi, edx
0x1800025ae  mov     rsi, rcx
0x1800025b1  mov     ebx, 1
0x1800025b6  cmp     edx, ebx
0x1800025b8  ja      short loc_1800025C0
0x1800025ba  mov     cs:__native_dllmain_reason, edx
0x1800025c0  test    edx, edx
0x1800025c2  jnz     short loc_1800025D7
0x1800025c4  cmp     cs:dword_180030B34, edx
0x1800025ca  jnz     short loc_1800025D7
0x1800025cc  xor     ebx, ebx
0x1800025ce  mov     [rsp+108h+var_E8], ebx
0x1800025d2  jmp     loc_180002784
0x1800025d7  lea     eax, [rdx-1]
0x1800025da  cmp     eax, 1
0x1800025dd  ja      loc_180002664
0x1800025e3  mov     rax, cs:_pRawDllMain
0x1800025ea  test    rax, rax
0x1800025ed  jz      short loc_180002625
0x1800025ef  cmp     edx, 1
0x1800025f2  jnz     short loc_1800025FA
0x1800025f4  mov     cs:dword_180030B38, edx
0x1800025fa  mov     r8, [rsp+108h+lpvReserved]
0x180002602  call    cs:__guard_dispatch_icall_fptr
0x180002608  mov     ebx, eax
0x18000260a  mov     [rsp+108h+var_E8], eax
0x18000260e  jmp     short loc_180002625
0x180002610  xor     ebx, ebx
0x180002612  mov     [rsp+108h+var_E8], ebx
0x180002616  mov     edi, [rsp+108h+arg_8]
0x18000261d  mov     rsi, [rsp+108h+arg_0]
0x180002625  test    ebx, ebx
0x180002627  jz      loc_180002784
0x18000262d  mov     r8, [rsp+108h+lpvReserved]
0x180002635  mov     edx, edi
0x180002637  mov     rcx, rsi
0x18000263a  call    _CRT_INIT
0x18000263f  mov     ebx, eax
0x180002641  mov     [rsp+108h+var_E8], eax
0x180002645  jmp     short loc_18000265C
0x180002647  xor     ebx, ebx
0x180002649  mov     [rsp+108h+var_E8], ebx
0x18000264d  mov     edi, [rsp+108h+arg_8]
0x180002654  mov     rsi, [rsp+108h+arg_0]
0x18000265c  test    ebx, ebx
0x18000265e  jz      loc_180002784
0x180002664  mov     r8, [rsp+108h+lpvReserved]; lpvReserved
0x18000266c  mov     edx, edi; fdwReason
0x18000266e  mov     rcx, rsi; hinstDLL
0x180002671  call    DllMain
0x180002676  mov     ebx, eax
0x180002678  mov     [rsp+108h+var_E8], eax
0x18000267c  jmp     short loc_180002693
0x18000267e  xor     ebx, ebx
0x180002680  mov     [rsp+108h+var_E8], ebx
0x180002684  mov     edi, [rsp+108h+arg_8]
0x18000268b  mov     rsi, [rsp+108h+arg_0]
0x180002693  cmp     edi, 1
0x180002696  jnz     short loc_18000270F
0x180002698  test    ebx, ebx
0x18000269a  jnz     short loc_18000270F
0x18000269c  xor     r8d, r8d; lpvReserved
0x18000269f  xor     edx, edx; fdwReason
0x1800026a1  mov     rcx, rsi; hinstDLL
0x1800026a4  call    DllMain
0x1800026a9  jmp     short loc_1800026BE
0x1800026ab  mov     edi, [rsp+108h+arg_8]
0x1800026b2  mov     rsi, [rsp+108h+arg_0]
0x1800026ba  mov     ebx, [rsp+108h+var_E8]
0x1800026be  xor     r8d, r8d
0x1800026c1  xor     edx, edx
0x1800026c3  mov     rcx, rsi
0x1800026c6  call    _CRT_INIT
0x1800026cb  jmp     short loc_1800026E0
0x1800026cd  mov     edi, [rsp+108h+arg_8]
0x1800026d4  mov     rsi, [rsp+108h+arg_0]
0x1800026dc  mov     ebx, [rsp+108h+var_E8]
0x1800026e0  mov     rax, cs:_pRawDllMain
0x1800026e7  test    rax, rax
0x1800026ea  jz      short loc_18000270F
0x1800026ec  xor     r8d, r8d
0x1800026ef  xor     edx, edx
0x1800026f1  mov     rcx, rsi
0x1800026f4  call    cs:__guard_dispatch_icall_fptr
0x1800026fa  jmp     short loc_18000270F
0x1800026fc  mov     edi, [rsp+108h+arg_8]
0x180002703  mov     rsi, [rsp+108h+arg_0]
0x18000270b  mov     ebx, [rsp+108h+var_E8]
0x18000270f  test    edi, edi
0x180002711  jz      short loc_180002718
0x180002713  cmp     edi, 3
0x180002716  jnz     short loc_180002784
0x180002718  mov     r8, [rsp+108h+lpvReserved]
0x180002720  mov     edx, edi
0x180002722  mov     rcx, rsi
0x180002725  call    _CRT_INIT
0x18000272a  mov     ebx, eax
0x18000272c  mov     [rsp+108h+var_E8], eax
0x180002730  jmp     short loc_180002747
0x180002732  xor     ebx, ebx
0x180002734  mov     [rsp+108h+var_E8], ebx
0x180002738  mov     edi, [rsp+108h+arg_8]
0x18000273f  mov     rsi, [rsp+108h+arg_0]
0x180002747  mov     rax, cs:_pRawDllMain
0x18000274e  test    rax, rax
0x180002751  jz      short loc_180002784
0x180002753  cmp     cs:dword_180030B38, 0
0x18000275a  jz      short loc_180002784
0x18000275c  mov     r8, [rsp+108h+lpvReserved]
0x180002764  mov     edx, edi
0x180002766  mov     rcx, rsi
0x180002769  call    cs:__guard_dispatch_icall_fptr
0x18000276f  mov     ebx, eax
0x180002771  mov     [rsp+108h+var_E8], eax
0x180002775  jmp     short loc_180002784
0x180002777  xor     ebx, ebx
0x180002779  mov     [rsp+108h+var_E8], ebx
0x18000277d  mov     edi, [rsp+108h+arg_8]
0x180002784  cmp     edi, 1
0x180002787  ja      short loc_180002793
0x180002789  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x180002793  mov     eax, ebx
0x180002795  add     rsp, 0F0h
0x18000279c  pop     rdi
0x18000279d  pop     rsi
0x18000279e  pop     rbx
0x18000279f  retn
0x18001b263  push    rbp
0x18001b265  sub     rsp, 20h
0x18001b269  mov     rbp, rdx
0x18001b26c  mov     rax, [rcx]
0x18001b26f  mov     edx, [rax]
0x18001b271  mov     [rbp+0A8h], rcx
0x18001b278  mov     [rbp+28h], edx
0x18001b27b  mov     eax, [rbp+28h]
0x18001b27e  cmp     eax, 0E06D7363h
0x18001b283  jnz     short loc_18001B299
0x18001b285  mov     rdx, [rbp+0A8h]
0x18001b28c  mov     ecx, [rbp+28h]
0x18001b28f  call    _XcptFilter_0
0x18001b294  mov     [rbp+30h], eax
0x18001b297  jmp     short loc_18001B2A0
0x18001b299  mov     dword ptr [rbp+30h], 0
0x18001b2a0  mov     eax, [rbp+30h]
0x18001b2a3  add     rsp, 20h
0x18001b2a7  pop     rbp
0x18001b2a8  retn
0x18001b2aa  push    rbp
0x18001b2ac  sub     rsp, 20h
0x18001b2b0  mov     rbp, rdx
0x18001b2b3  mov     rax, [rcx]
0x18001b2b6  mov     edx, [rax]
0x18001b2b8  mov     [rbp+0B0h], rcx
0x18001b2bf  mov     [rbp+38h], edx
0x18001b2c2  mov     eax, [rbp+38h]
0x18001b2c5  cmp     eax, 0E06D7363h
0x18001b2ca  jnz     short loc_18001B2E0
0x18001b2cc  mov     rdx, [rbp+0B0h]
0x18001b2d3  mov     ecx, [rbp+38h]
0x18001b2d6  call    _XcptFilter_0
0x18001b2db  mov     [rbp+40h], eax
0x18001b2de  jmp     short loc_18001B2E7
0x18001b2e0  mov     dword ptr [rbp+40h], 0
0x18001b2e7  mov     eax, [rbp+40h]
0x18001b2ea  add     rsp, 20h
0x18001b2ee  pop     rbp
0x18001b2ef  retn
0x18001b2f1  push    rbp
0x18001b2f3  sub     rsp, 20h
0x18001b2f7  mov     rbp, rdx
0x18001b2fa  mov     rax, [rcx]
0x18001b2fd  mov     edx, [rax]
0x18001b2ff  mov     [rbp+0B8h], rcx
0x18001b306  mov     [rbp+48h], edx
0x18001b309  mov     eax, [rbp+48h]
0x18001b30c  cmp     eax, 0E06D7363h
0x18001b311  jnz     short loc_18001B327
0x18001b313  mov     rdx, [rbp+0B8h]
0x18001b31a  mov     ecx, [rbp+48h]
0x18001b31d  call    _XcptFilter_0
0x18001b322  mov     [rbp+50h], eax
0x18001b325  jmp     short loc_18001B32E
0x18001b327  mov     dword ptr [rbp+50h], 0
0x18001b32e  mov     eax, [rbp+50h]
0x18001b331  add     rsp, 20h
0x18001b335  pop     rbp
0x18001b336  retn
0x18001b338  push    rbp
0x18001b33a  sub     rsp, 20h
0x18001b33e  mov     rbp, rdx
0x18001b341  mov     rax, [rcx]
0x18001b344  mov     edx, [rax]
0x18001b346  mov     [rbp+0C0h], rcx
0x18001b34d  mov     [rbp+58h], edx
0x18001b350  mov     eax, [rbp+58h]
0x18001b353  cmp     eax, 0E06D7363h
0x18001b358  jnz     short loc_18001B36E
0x18001b35a  mov     rdx, [rbp+0C0h]
0x18001b361  mov     ecx, [rbp+58h]
0x18001b364  call    _XcptFilter_0
0x18001b369  mov     [rbp+60h], eax
0x18001b36c  jmp     short loc_18001B375
0x18001b36e  mov     dword ptr [rbp+60h], 0
0x18001b375  mov     eax, [rbp+60h]
0x18001b378  add     rsp, 20h
0x18001b37c  pop     rbp
0x18001b37d  retn
0x18001b37f  push    rbp
0x18001b381  sub     rsp, 20h
0x18001b385  mov     rbp, rdx
0x18001b388  mov     rax, [rcx]
0x18001b38b  mov     edx, [rax]
0x18001b38d  mov     [rbp+0C8h], rcx
0x18001b394  mov     [rbp+68h], edx
0x18001b397  mov     eax, [rbp+68h]
0x18001b39a  cmp     eax, 0E06D7363h
0x18001b39f  jnz     short loc_18001B3B5
0x18001b3a1  mov     rdx, [rbp+0C8h]
0x18001b3a8  mov     ecx, [rbp+68h]
0x18001b3ab  call    _XcptFilter_0
0x18001b3b0  mov     [rbp+70h], eax
0x18001b3b3  jmp     short loc_18001B3BC
0x18001b3b5  mov     dword ptr [rbp+70h], 0
0x18001b3bc  mov     eax, [rbp+70h]
0x18001b3bf  add     rsp, 20h
0x18001b3c3  pop     rbp
0x18001b3c4  retn
0x18001b3c6  push    rbp
0x18001b3c8  sub     rsp, 20h
0x18001b3cc  mov     rbp, rdx
0x18001b3cf  mov     rax, [rcx]
0x18001b3d2  mov     edx, [rax]
0x18001b3d4  mov     [rbp+0D0h], rcx
0x18001b3db  mov     [rbp+78h], edx
0x18001b3de  mov     eax, [rbp+78h]
0x18001b3e1  cmp     eax, 0E06D7363h
0x18001b3e6  jnz     short loc_18001B3FF
0x18001b3e8  mov     rdx, [rbp+0D0h]
0x18001b3ef  mov     ecx, [rbp+78h]
0x18001b3f2  call    _XcptFilter_0
0x18001b3f7  mov     [rbp+80h], eax
0x18001b3fd  jmp     short loc_18001B409
0x18001b3ff  mov     dword ptr [rbp+80h], 0
0x18001b409  mov     eax, [rbp+80h]
0x18001b40f  add     rsp, 20h
0x18001b413  pop     rbp
0x18001b414  retn
0x18001b416  push    rbp
0x18001b418  sub     rsp, 20h
0x18001b41c  mov     rbp, rdx
0x18001b41f  mov     rax, [rcx]
0x18001b422  mov     edx, [rax]
0x18001b424  mov     [rbp+0D8h], rcx
0x18001b42b  mov     [rbp+88h], edx
0x18001b431  mov     eax, [rbp+88h]
0x18001b437  cmp     eax, 0E06D7363h
0x18001b43c  jnz     short loc_18001B458
0x18001b43e  mov     rdx, [rbp+0D8h]
0x18001b445  mov     ecx, [rbp+88h]
0x18001b44b  call    _XcptFilter_0
0x18001b450  mov     [rbp+90h], eax
0x18001b456  jmp     short loc_18001B462
0x18001b458  mov     dword ptr [rbp+90h], 0
0x18001b462  mov     eax, [rbp+90h]
0x18001b468  add     rsp, 20h
0x18001b46c  pop     rbp
0x18001b46d  retn
0x18001b46f  push    rbp
0x18001b471  sub     rsp, 20h
0x18001b475  mov     rbp, rdx
0x18001b478  mov     rax, [rcx]
0x18001b47b  mov     edx, [rax]
0x18001b47d  mov     [rbp+0E0h], rcx
0x18001b484  mov     [rbp+98h], edx
0x18001b48a  mov     eax, [rbp+98h]
0x18001b490  cmp     eax, 0E06D7363h
0x18001b495  jnz     short loc_18001B4B1
0x18001b497  mov     rdx, [rbp+0E0h]
0x18001b49e  mov     ecx, [rbp+98h]
0x18001b4a4  call    _XcptFilter_0
0x18001b4a9  mov     [rbp+0A0h], eax
0x18001b4af  jmp     short loc_18001B4BB
0x18001b4b1  mov     dword ptr [rbp+0A0h], 0
0x18001b4bb  mov     eax, [rbp+0A0h]
0x18001b4c1  add     rsp, 20h
0x18001b4c5  pop     rbp
0x18001b4c6  retn
0x18001b4c8  push    rbp
0x18001b4ca  sub     rsp, 20h
0x18001b4ce  mov     rbp, rdx
0x18001b4d1  cmp     dword ptr [rbp+118h], 1
0x18001b4d8  ja      short loc_18001B4E4
0x18001b4da  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
