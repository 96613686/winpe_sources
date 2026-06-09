# __DllMainCRTStartup

- ea: `0x180002274`
- end: `0x180002480`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(PRELOAD_MANAGER *this)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180002230`

## callees

- `0x180002000`
- `0x180002274`
- `0x1800024c0`
- `0x18000b500`
- `0x18000c410`

## pseudocode

```c
__int64 __fastcall _DllMainCRTStartup(PRELOAD_MANAGER *this, __int64 a2, __int64 a3)
{
  unsigned int v3; // edi
  unsigned int IsGranularModeListener; // ebx

  v3 = a2;
  IsGranularModeListener = 1;
  if ( (unsigned int)a2 <= 1 )
    _native_dllmain_reason = a2;
  if ( (_DWORD)a2 || dword_180014100 )
  {
    if ( (unsigned int)(a2 - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)a2 == 1 )
        dword_180014104 = 1;
      IsGranularModeListener = pRawDllMain(this, a2, a3);
    }
    if ( IsGranularModeListener )
    {
      IsGranularModeListener = CRT_INIT(this, v3, a3);
      if ( IsGranularModeListener )
      {
LABEL_13:
        IsGranularModeListener = PRELOAD_MANAGER::IsGranularModeListener(this);
        if ( v3 == 1 && !IsGranularModeListener )
        {
          PRELOAD_MANAGER::IsGranularModeListener(this);
          CRT_INIT(this, 0, 0);
          if ( pRawDllMain )
            pRawDllMain(this, 0, 0);
        }
        if ( !v3 || v3 == 3 )
        {
          IsGranularModeListener = CRT_INIT(this, v3, a3);
          if ( pRawDllMain )
          {
            if ( dword_180014104 )
              IsGranularModeListener = pRawDllMain(this, v3, a3);
          }
        }
      }
    }
  }
  else
  {
    IsGranularModeListener = 0;
  }
  if ( v3 <= 1 )
    _native_dllmain_reason = -1;
  return IsGranularModeListener;
}

```

## disassembly

```asm
0x180002274  mov     [rsp+arg_10], r8
0x180002279  mov     [rsp+arg_8], edx
0x18000227d  mov     [rsp+arg_0], rcx
0x180002282  push    rbx
0x180002283  push    rsi
0x180002284  push    rdi
0x180002285  sub     rsp, 0F0h
0x18000228c  mov     edi, edx
0x18000228e  mov     rsi, rcx
0x180002291  mov     ebx, 1
0x180002296  cmp     edx, ebx
0x180002298  ja      short loc_1800022A0
0x18000229a  mov     cs:__native_dllmain_reason, edx
0x1800022a0  test    edx, edx
0x1800022a2  jnz     short loc_1800022B7
0x1800022a4  cmp     cs:dword_180014100, edx
0x1800022aa  jnz     short loc_1800022B7
0x1800022ac  xor     ebx, ebx
0x1800022ae  mov     [rsp+108h+var_E8], ebx
0x1800022b2  jmp     loc_180002464
0x1800022b7  lea     eax, [rdx-1]
0x1800022ba  cmp     eax, 1
0x1800022bd  ja      loc_180002344
0x1800022c3  mov     rax, cs:_pRawDllMain
0x1800022ca  test    rax, rax
0x1800022cd  jz      short loc_180002305
0x1800022cf  cmp     edx, 1
0x1800022d2  jnz     short loc_1800022DA
0x1800022d4  mov     cs:dword_180014104, edx
0x1800022da  mov     r8, [rsp+108h+arg_10]
0x1800022e2  call    cs:__guard_dispatch_icall_fptr
0x1800022e8  mov     ebx, eax
0x1800022ea  mov     [rsp+108h+var_E8], eax
0x1800022ee  jmp     short loc_180002305
0x1800022f0  xor     ebx, ebx
0x1800022f2  mov     [rsp+108h+var_E8], ebx
0x1800022f6  mov     edi, [rsp+108h+arg_8]
0x1800022fd  mov     rsi, [rsp+108h+arg_0]
0x180002305  test    ebx, ebx
0x180002307  jz      loc_180002464
0x18000230d  mov     r8, [rsp+108h+arg_10]
0x180002315  mov     edx, edi
0x180002317  mov     rcx, rsi
0x18000231a  call    _CRT_INIT
0x18000231f  mov     ebx, eax
0x180002321  mov     [rsp+108h+var_E8], eax
0x180002325  jmp     short loc_18000233C
0x180002327  xor     ebx, ebx
0x180002329  mov     [rsp+108h+var_E8], ebx
0x18000232d  mov     edi, [rsp+108h+arg_8]
0x180002334  mov     rsi, [rsp+108h+arg_0]
0x18000233c  test    ebx, ebx
0x18000233e  jz      loc_180002464
0x180002344  mov     r8, [rsp+108h+arg_10]
0x18000234c  mov     edx, edi
0x18000234e  mov     rcx, rsi; this
0x180002351  call    ?IsGranularModeListener@PRELOAD_MANAGER@@UEAAHXZ; PRELOAD_MANAGER::IsGranularModeListener(void)
0x180002356  mov     ebx, eax
0x180002358  mov     [rsp+108h+var_E8], eax
0x18000235c  jmp     short loc_180002373
0x18000235e  xor     ebx, ebx
0x180002360  mov     [rsp+108h+var_E8], ebx
0x180002364  mov     edi, [rsp+108h+arg_8]
0x18000236b  mov     rsi, [rsp+108h+arg_0]
0x180002373  cmp     edi, 1
0x180002376  jnz     short loc_1800023EF
0x180002378  test    ebx, ebx
0x18000237a  jnz     short loc_1800023EF
0x18000237c  xor     r8d, r8d
0x18000237f  xor     edx, edx
0x180002381  mov     rcx, rsi; this
0x180002384  call    ?IsGranularModeListener@PRELOAD_MANAGER@@UEAAHXZ; PRELOAD_MANAGER::IsGranularModeListener(void)
0x180002389  jmp     short loc_18000239E
0x18000238b  mov     edi, [rsp+108h+arg_8]
0x180002392  mov     rsi, [rsp+108h+arg_0]
0x18000239a  mov     ebx, [rsp+108h+var_E8]
0x18000239e  xor     r8d, r8d
0x1800023a1  xor     edx, edx
0x1800023a3  mov     rcx, rsi
0x1800023a6  call    _CRT_INIT
0x1800023ab  jmp     short loc_1800023C0
0x1800023ad  mov     edi, [rsp+108h+arg_8]
0x1800023b4  mov     rsi, [rsp+108h+arg_0]
0x1800023bc  mov     ebx, [rsp+108h+var_E8]
0x1800023c0  mov     rax, cs:_pRawDllMain
0x1800023c7  test    rax, rax
0x1800023ca  jz      short loc_1800023EF
0x1800023cc  xor     r8d, r8d
0x1800023cf  xor     edx, edx
0x1800023d1  mov     rcx, rsi
0x1800023d4  call    cs:__guard_dispatch_icall_fptr
0x1800023da  jmp     short loc_1800023EF
0x1800023dc  mov     edi, [rsp+108h+arg_8]
0x1800023e3  mov     rsi, [rsp+108h+arg_0]
0x1800023eb  mov     ebx, [rsp+108h+var_E8]
0x1800023ef  test    edi, edi
0x1800023f1  jz      short loc_1800023F8
0x1800023f3  cmp     edi, 3
0x1800023f6  jnz     short loc_180002464
0x1800023f8  mov     r8, [rsp+108h+arg_10]
0x180002400  mov     edx, edi
0x180002402  mov     rcx, rsi
0x180002405  call    _CRT_INIT
0x18000240a  mov     ebx, eax
0x18000240c  mov     [rsp+108h+var_E8], eax
0x180002410  jmp     short loc_180002427
0x180002412  xor     ebx, ebx
0x180002414  mov     [rsp+108h+var_E8], ebx
0x180002418  mov     edi, [rsp+108h+arg_8]
0x18000241f  mov     rsi, [rsp+108h+arg_0]
0x180002427  mov     rax, cs:_pRawDllMain
0x18000242e  test    rax, rax
0x180002431  jz      short loc_180002464
0x180002433  cmp     cs:dword_180014104, 0
0x18000243a  jz      short loc_180002464
0x18000243c  mov     r8, [rsp+108h+arg_10]
0x180002444  mov     edx, edi
0x180002446  mov     rcx, rsi
0x180002449  call    cs:__guard_dispatch_icall_fptr
0x18000244f  mov     ebx, eax
0x180002451  mov     [rsp+108h+var_E8], eax
0x180002455  jmp     short loc_180002464
0x180002457  xor     ebx, ebx
0x180002459  mov     [rsp+108h+var_E8], ebx
0x18000245d  mov     edi, [rsp+108h+arg_8]
0x180002464  cmp     edi, 1
0x180002467  ja      short loc_180002473
0x180002469  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x180002473  mov     eax, ebx
0x180002475  add     rsp, 0F0h
0x18000247c  pop     rdi
0x18000247d  pop     rsi
0x18000247e  pop     rbx
0x18000247f  retn
0x18000c480  push    rbp
0x18000c482  sub     rsp, 20h
0x18000c486  mov     rbp, rdx
0x18000c489  mov     rax, [rcx]
0x18000c48c  mov     edx, [rax]
0x18000c48e  mov     [rbp+0A8h], rcx
0x18000c495  mov     [rbp+28h], edx
0x18000c498  mov     eax, [rbp+28h]
0x18000c49b  cmp     eax, 0E06D7363h
0x18000c4a0  jnz     short loc_18000C4B6
0x18000c4a2  mov     rdx, [rbp+0A8h]
0x18000c4a9  mov     ecx, [rbp+28h]
0x18000c4ac  call    _XcptFilter_0
0x18000c4b1  mov     [rbp+30h], eax
0x18000c4b4  jmp     short loc_18000C4BD
0x18000c4b6  mov     dword ptr [rbp+30h], 0
0x18000c4bd  mov     eax, [rbp+30h]
0x18000c4c0  add     rsp, 20h
0x18000c4c4  pop     rbp
0x18000c4c5  retn
0x18000c4c7  push    rbp
0x18000c4c9  sub     rsp, 20h
0x18000c4cd  mov     rbp, rdx
0x18000c4d0  mov     rax, [rcx]
0x18000c4d3  mov     edx, [rax]
0x18000c4d5  mov     [rbp+0B0h], rcx
0x18000c4dc  mov     [rbp+38h], edx
0x18000c4df  mov     eax, [rbp+38h]
0x18000c4e2  cmp     eax, 0E06D7363h
0x18000c4e7  jnz     short loc_18000C4FD
0x18000c4e9  mov     rdx, [rbp+0B0h]
0x18000c4f0  mov     ecx, [rbp+38h]
0x18000c4f3  call    _XcptFilter_0
0x18000c4f8  mov     [rbp+40h], eax
0x18000c4fb  jmp     short loc_18000C504
0x18000c4fd  mov     dword ptr [rbp+40h], 0
0x18000c504  mov     eax, [rbp+40h]
0x18000c507  add     rsp, 20h
0x18000c50b  pop     rbp
0x18000c50c  retn
0x18000c50e  push    rbp
0x18000c510  sub     rsp, 20h
0x18000c514  mov     rbp, rdx
0x18000c517  mov     rax, [rcx]
0x18000c51a  mov     edx, [rax]
0x18000c51c  mov     [rbp+0B8h], rcx
0x18000c523  mov     [rbp+48h], edx
0x18000c526  mov     eax, [rbp+48h]
0x18000c529  cmp     eax, 0E06D7363h
0x18000c52e  jnz     short loc_18000C544
0x18000c530  mov     rdx, [rbp+0B8h]
0x18000c537  mov     ecx, [rbp+48h]
0x18000c53a  call    _XcptFilter_0
0x18000c53f  mov     [rbp+50h], eax
0x18000c542  jmp     short loc_18000C54B
0x18000c544  mov     dword ptr [rbp+50h], 0
0x18000c54b  mov     eax, [rbp+50h]
0x18000c54e  add     rsp, 20h
0x18000c552  pop     rbp
0x18000c553  retn
0x18000c555  push    rbp
0x18000c557  sub     rsp, 20h
0x18000c55b  mov     rbp, rdx
0x18000c55e  mov     rax, [rcx]
0x18000c561  mov     edx, [rax]
0x18000c563  mov     [rbp+0C0h], rcx
0x18000c56a  mov     [rbp+58h], edx
0x18000c56d  mov     eax, [rbp+58h]
0x18000c570  cmp     eax, 0E06D7363h
0x18000c575  jnz     short loc_18000C58B
0x18000c577  mov     rdx, [rbp+0C0h]
0x18000c57e  mov     ecx, [rbp+58h]
0x18000c581  call    _XcptFilter_0
0x18000c586  mov     [rbp+60h], eax
0x18000c589  jmp     short loc_18000C592
0x18000c58b  mov     dword ptr [rbp+60h], 0
0x18000c592  mov     eax, [rbp+60h]
0x18000c595  add     rsp, 20h
0x18000c599  pop     rbp
0x18000c59a  retn
0x18000c59c  push    rbp
0x18000c59e  sub     rsp, 20h
0x18000c5a2  mov     rbp, rdx
0x18000c5a5  mov     rax, [rcx]
0x18000c5a8  mov     edx, [rax]
0x18000c5aa  mov     [rbp+0C8h], rcx
0x18000c5b1  mov     [rbp+68h], edx
0x18000c5b4  mov     eax, [rbp+68h]
0x18000c5b7  cmp     eax, 0E06D7363h
0x18000c5bc  jnz     short loc_18000C5D2
0x18000c5be  mov     rdx, [rbp+0C8h]
0x18000c5c5  mov     ecx, [rbp+68h]
0x18000c5c8  call    _XcptFilter_0
0x18000c5cd  mov     [rbp+70h], eax
0x18000c5d0  jmp     short loc_18000C5D9
0x18000c5d2  mov     dword ptr [rbp+70h], 0
0x18000c5d9  mov     eax, [rbp+70h]
0x18000c5dc  add     rsp, 20h
0x18000c5e0  pop     rbp
0x18000c5e1  retn
0x18000c5e3  push    rbp
0x18000c5e5  sub     rsp, 20h
0x18000c5e9  mov     rbp, rdx
0x18000c5ec  mov     rax, [rcx]
0x18000c5ef  mov     edx, [rax]
0x18000c5f1  mov     [rbp+0D0h], rcx
0x18000c5f8  mov     [rbp+78h], edx
0x18000c5fb  mov     eax, [rbp+78h]
0x18000c5fe  cmp     eax, 0E06D7363h
0x18000c603  jnz     short loc_18000C61C
0x18000c605  mov     rdx, [rbp+0D0h]
0x18000c60c  mov     ecx, [rbp+78h]
0x18000c60f  call    _XcptFilter_0
0x18000c614  mov     [rbp+80h], eax
0x18000c61a  jmp     short loc_18000C626
0x18000c61c  mov     dword ptr [rbp+80h], 0
0x18000c626  mov     eax, [rbp+80h]
0x18000c62c  add     rsp, 20h
0x18000c630  pop     rbp
0x18000c631  retn
0x18000c633  push    rbp
0x18000c635  sub     rsp, 20h
0x18000c639  mov     rbp, rdx
0x18000c63c  mov     rax, [rcx]
0x18000c63f  mov     edx, [rax]
0x18000c641  mov     [rbp+0D8h], rcx
0x18000c648  mov     [rbp+88h], edx
0x18000c64e  mov     eax, [rbp+88h]
0x18000c654  cmp     eax, 0E06D7363h
0x18000c659  jnz     short loc_18000C675
0x18000c65b  mov     rdx, [rbp+0D8h]
0x18000c662  mov     ecx, [rbp+88h]
0x18000c668  call    _XcptFilter_0
0x18000c66d  mov     [rbp+90h], eax
0x18000c673  jmp     short loc_18000C67F
0x18000c675  mov     dword ptr [rbp+90h], 0
0x18000c67f  mov     eax, [rbp+90h]
0x18000c685  add     rsp, 20h
0x18000c689  pop     rbp
0x18000c68a  retn
0x18000c68c  push    rbp
0x18000c68e  sub     rsp, 20h
0x18000c692  mov     rbp, rdx
0x18000c695  mov     rax, [rcx]
0x18000c698  mov     edx, [rax]
0x18000c69a  mov     [rbp+0E0h], rcx
0x18000c6a1  mov     [rbp+98h], edx
0x18000c6a7  mov     eax, [rbp+98h]
0x18000c6ad  cmp     eax, 0E06D7363h
0x18000c6b2  jnz     short loc_18000C6CE
0x18000c6b4  mov     rdx, [rbp+0E0h]
0x18000c6bb  mov     ecx, [rbp+98h]
0x18000c6c1  call    _XcptFilter_0
0x18000c6c6  mov     [rbp+0A0h], eax
0x18000c6cc  jmp     short loc_18000C6D8
0x18000c6ce  mov     dword ptr [rbp+0A0h], 0
0x18000c6d8  mov     eax, [rbp+0A0h]
0x18000c6de  add     rsp, 20h
0x18000c6e2  pop     rbp
0x18000c6e3  retn
0x18000c6e5  push    rbp
0x18000c6e7  sub     rsp, 20h
0x18000c6eb  mov     rbp, rdx
0x18000c6ee  cmp     dword ptr [rbp+118h], 1
0x18000c6f5  ja      short loc_18000C701
0x18000c6f7  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
