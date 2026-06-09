# __DllMainCRTStartup

- ea: `0x1800012c4`
- end: `0x1800014d0`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180001280`

## callees

- `0x180001050`
- `0x1800012c4`
- `0x1800016c6`
- `0x180001898`
- `0x180002220`

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
  if ( (_DWORD)fdwReason || dword_1800060A0 )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_1800060A4 = 1;
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
            if ( dword_1800060A4 )
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
0x1800012c4  mov     [rsp+lpvReserved], r8
0x1800012c9  mov     [rsp+arg_8], edx
0x1800012cd  mov     [rsp+arg_0], rcx
0x1800012d2  push    rbx
0x1800012d3  push    rsi
0x1800012d4  push    rdi
0x1800012d5  sub     rsp, 0F0h
0x1800012dc  mov     edi, edx
0x1800012de  mov     rsi, rcx
0x1800012e1  mov     ebx, 1
0x1800012e6  cmp     edx, ebx
0x1800012e8  ja      short loc_1800012F0
0x1800012ea  mov     cs:__native_dllmain_reason, edx
0x1800012f0  test    edx, edx
0x1800012f2  jnz     short loc_180001307
0x1800012f4  cmp     cs:dword_1800060A0, edx
0x1800012fa  jnz     short loc_180001307
0x1800012fc  xor     ebx, ebx
0x1800012fe  mov     [rsp+108h+var_E8], ebx
0x180001302  jmp     loc_1800014B4
0x180001307  lea     eax, [rdx-1]
0x18000130a  cmp     eax, 1
0x18000130d  ja      loc_180001394
0x180001313  mov     rax, cs:_pRawDllMain
0x18000131a  test    rax, rax
0x18000131d  jz      short loc_180001355
0x18000131f  cmp     edx, 1
0x180001322  jnz     short loc_18000132A
0x180001324  mov     cs:dword_1800060A4, edx
0x18000132a  mov     r8, [rsp+108h+lpvReserved]
0x180001332  call    cs:__guard_dispatch_icall_fptr
0x180001338  mov     ebx, eax
0x18000133a  mov     [rsp+108h+var_E8], eax
0x18000133e  jmp     short loc_180001355
0x180001340  xor     ebx, ebx
0x180001342  mov     [rsp+108h+var_E8], ebx
0x180001346  mov     edi, [rsp+108h+arg_8]
0x18000134d  mov     rsi, [rsp+108h+arg_0]
0x180001355  test    ebx, ebx
0x180001357  jz      loc_1800014B4
0x18000135d  mov     r8, [rsp+108h+lpvReserved]
0x180001365  mov     edx, edi
0x180001367  mov     rcx, rsi
0x18000136a  call    _CRT_INIT
0x18000136f  mov     ebx, eax
0x180001371  mov     [rsp+108h+var_E8], eax
0x180001375  jmp     short loc_18000138C
0x180001377  xor     ebx, ebx
0x180001379  mov     [rsp+108h+var_E8], ebx
0x18000137d  mov     edi, [rsp+108h+arg_8]
0x180001384  mov     rsi, [rsp+108h+arg_0]
0x18000138c  test    ebx, ebx
0x18000138e  jz      loc_1800014B4
0x180001394  mov     r8, [rsp+108h+lpvReserved]; lpvReserved
0x18000139c  mov     edx, edi; fdwReason
0x18000139e  mov     rcx, rsi; hinstDLL
0x1800013a1  call    DllMain
0x1800013a6  mov     ebx, eax
0x1800013a8  mov     [rsp+108h+var_E8], eax
0x1800013ac  jmp     short loc_1800013C3
0x1800013ae  xor     ebx, ebx
0x1800013b0  mov     [rsp+108h+var_E8], ebx
0x1800013b4  mov     edi, [rsp+108h+arg_8]
0x1800013bb  mov     rsi, [rsp+108h+arg_0]
0x1800013c3  cmp     edi, 1
0x1800013c6  jnz     short loc_18000143F
0x1800013c8  test    ebx, ebx
0x1800013ca  jnz     short loc_18000143F
0x1800013cc  xor     r8d, r8d; lpvReserved
0x1800013cf  xor     edx, edx; fdwReason
0x1800013d1  mov     rcx, rsi; hinstDLL
0x1800013d4  call    DllMain
0x1800013d9  jmp     short loc_1800013EE
0x1800013db  mov     edi, [rsp+108h+arg_8]
0x1800013e2  mov     rsi, [rsp+108h+arg_0]
0x1800013ea  mov     ebx, [rsp+108h+var_E8]
0x1800013ee  xor     r8d, r8d
0x1800013f1  xor     edx, edx
0x1800013f3  mov     rcx, rsi
0x1800013f6  call    _CRT_INIT
0x1800013fb  jmp     short loc_180001410
0x1800013fd  mov     edi, [rsp+108h+arg_8]
0x180001404  mov     rsi, [rsp+108h+arg_0]
0x18000140c  mov     ebx, [rsp+108h+var_E8]
0x180001410  mov     rax, cs:_pRawDllMain
0x180001417  test    rax, rax
0x18000141a  jz      short loc_18000143F
0x18000141c  xor     r8d, r8d
0x18000141f  xor     edx, edx
0x180001421  mov     rcx, rsi
0x180001424  call    cs:__guard_dispatch_icall_fptr
0x18000142a  jmp     short loc_18000143F
0x18000142c  mov     edi, [rsp+108h+arg_8]
0x180001433  mov     rsi, [rsp+108h+arg_0]
0x18000143b  mov     ebx, [rsp+108h+var_E8]
0x18000143f  test    edi, edi
0x180001441  jz      short loc_180001448
0x180001443  cmp     edi, 3
0x180001446  jnz     short loc_1800014B4
0x180001448  mov     r8, [rsp+108h+lpvReserved]
0x180001450  mov     edx, edi
0x180001452  mov     rcx, rsi
0x180001455  call    _CRT_INIT
0x18000145a  mov     ebx, eax
0x18000145c  mov     [rsp+108h+var_E8], eax
0x180001460  jmp     short loc_180001477
0x180001462  xor     ebx, ebx
0x180001464  mov     [rsp+108h+var_E8], ebx
0x180001468  mov     edi, [rsp+108h+arg_8]
0x18000146f  mov     rsi, [rsp+108h+arg_0]
0x180001477  mov     rax, cs:_pRawDllMain
0x18000147e  test    rax, rax
0x180001481  jz      short loc_1800014B4
0x180001483  cmp     cs:dword_1800060A4, 0
0x18000148a  jz      short loc_1800014B4
0x18000148c  mov     r8, [rsp+108h+lpvReserved]
0x180001494  mov     edx, edi
0x180001496  mov     rcx, rsi
0x180001499  call    cs:__guard_dispatch_icall_fptr
0x18000149f  mov     ebx, eax
0x1800014a1  mov     [rsp+108h+var_E8], eax
0x1800014a5  jmp     short loc_1800014B4
0x1800014a7  xor     ebx, ebx
0x1800014a9  mov     [rsp+108h+var_E8], ebx
0x1800014ad  mov     edi, [rsp+108h+arg_8]
0x1800014b4  cmp     edi, 1
0x1800014b7  ja      short loc_1800014C3
0x1800014b9  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x1800014c3  mov     eax, ebx
0x1800014c5  add     rsp, 0F0h
0x1800014cc  pop     rdi
0x1800014cd  pop     rsi
0x1800014ce  pop     rbx
0x1800014cf  retn
0x180002290  push    rbp
0x180002292  sub     rsp, 20h
0x180002296  mov     rbp, rdx
0x180002299  mov     rax, [rcx]
0x18000229c  mov     edx, [rax]
0x18000229e  mov     [rbp+0A8h], rcx
0x1800022a5  mov     [rbp+28h], edx
0x1800022a8  mov     eax, [rbp+28h]
0x1800022ab  cmp     eax, 0E06D7363h
0x1800022b0  jnz     short loc_1800022C6
0x1800022b2  mov     rdx, [rbp+0A8h]
0x1800022b9  mov     ecx, [rbp+28h]
0x1800022bc  call    _XcptFilter_0
0x1800022c1  mov     [rbp+30h], eax
0x1800022c4  jmp     short loc_1800022CD
0x1800022c6  mov     dword ptr [rbp+30h], 0
0x1800022cd  mov     eax, [rbp+30h]
0x1800022d0  add     rsp, 20h
0x1800022d4  pop     rbp
0x1800022d5  retn
0x1800022d7  push    rbp
0x1800022d9  sub     rsp, 20h
0x1800022dd  mov     rbp, rdx
0x1800022e0  mov     rax, [rcx]
0x1800022e3  mov     edx, [rax]
0x1800022e5  mov     [rbp+0B0h], rcx
0x1800022ec  mov     [rbp+38h], edx
0x1800022ef  mov     eax, [rbp+38h]
0x1800022f2  cmp     eax, 0E06D7363h
0x1800022f7  jnz     short loc_18000230D
0x1800022f9  mov     rdx, [rbp+0B0h]
0x180002300  mov     ecx, [rbp+38h]
0x180002303  call    _XcptFilter_0
0x180002308  mov     [rbp+40h], eax
0x18000230b  jmp     short loc_180002314
0x18000230d  mov     dword ptr [rbp+40h], 0
0x180002314  mov     eax, [rbp+40h]
0x180002317  add     rsp, 20h
0x18000231b  pop     rbp
0x18000231c  retn
0x18000231e  push    rbp
0x180002320  sub     rsp, 20h
0x180002324  mov     rbp, rdx
0x180002327  mov     rax, [rcx]
0x18000232a  mov     edx, [rax]
0x18000232c  mov     [rbp+0B8h], rcx
0x180002333  mov     [rbp+48h], edx
0x180002336  mov     eax, [rbp+48h]
0x180002339  cmp     eax, 0E06D7363h
0x18000233e  jnz     short loc_180002354
0x180002340  mov     rdx, [rbp+0B8h]
0x180002347  mov     ecx, [rbp+48h]
0x18000234a  call    _XcptFilter_0
0x18000234f  mov     [rbp+50h], eax
0x180002352  jmp     short loc_18000235B
0x180002354  mov     dword ptr [rbp+50h], 0
0x18000235b  mov     eax, [rbp+50h]
0x18000235e  add     rsp, 20h
0x180002362  pop     rbp
0x180002363  retn
0x180002365  push    rbp
0x180002367  sub     rsp, 20h
0x18000236b  mov     rbp, rdx
0x18000236e  mov     rax, [rcx]
0x180002371  mov     edx, [rax]
0x180002373  mov     [rbp+0C0h], rcx
0x18000237a  mov     [rbp+58h], edx
0x18000237d  mov     eax, [rbp+58h]
0x180002380  cmp     eax, 0E06D7363h
0x180002385  jnz     short loc_18000239B
0x180002387  mov     rdx, [rbp+0C0h]
0x18000238e  mov     ecx, [rbp+58h]
0x180002391  call    _XcptFilter_0
0x180002396  mov     [rbp+60h], eax
0x180002399  jmp     short loc_1800023A2
0x18000239b  mov     dword ptr [rbp+60h], 0
0x1800023a2  mov     eax, [rbp+60h]
0x1800023a5  add     rsp, 20h
0x1800023a9  pop     rbp
0x1800023aa  retn
0x1800023ac  push    rbp
0x1800023ae  sub     rsp, 20h
0x1800023b2  mov     rbp, rdx
0x1800023b5  mov     rax, [rcx]
0x1800023b8  mov     edx, [rax]
0x1800023ba  mov     [rbp+0C8h], rcx
0x1800023c1  mov     [rbp+68h], edx
0x1800023c4  mov     eax, [rbp+68h]
0x1800023c7  cmp     eax, 0E06D7363h
0x1800023cc  jnz     short loc_1800023E2
0x1800023ce  mov     rdx, [rbp+0C8h]
0x1800023d5  mov     ecx, [rbp+68h]
0x1800023d8  call    _XcptFilter_0
0x1800023dd  mov     [rbp+70h], eax
0x1800023e0  jmp     short loc_1800023E9
0x1800023e2  mov     dword ptr [rbp+70h], 0
0x1800023e9  mov     eax, [rbp+70h]
0x1800023ec  add     rsp, 20h
0x1800023f0  pop     rbp
0x1800023f1  retn
0x1800023f3  push    rbp
0x1800023f5  sub     rsp, 20h
0x1800023f9  mov     rbp, rdx
0x1800023fc  mov     rax, [rcx]
0x1800023ff  mov     edx, [rax]
0x180002401  mov     [rbp+0D0h], rcx
0x180002408  mov     [rbp+78h], edx
0x18000240b  mov     eax, [rbp+78h]
0x18000240e  cmp     eax, 0E06D7363h
0x180002413  jnz     short loc_18000242C
0x180002415  mov     rdx, [rbp+0D0h]
0x18000241c  mov     ecx, [rbp+78h]
0x18000241f  call    _XcptFilter_0
0x180002424  mov     [rbp+80h], eax
0x18000242a  jmp     short loc_180002436
0x18000242c  mov     dword ptr [rbp+80h], 0
0x180002436  mov     eax, [rbp+80h]
0x18000243c  add     rsp, 20h
0x180002440  pop     rbp
0x180002441  retn
0x180002443  push    rbp
0x180002445  sub     rsp, 20h
0x180002449  mov     rbp, rdx
0x18000244c  mov     rax, [rcx]
0x18000244f  mov     edx, [rax]
0x180002451  mov     [rbp+0D8h], rcx
0x180002458  mov     [rbp+88h], edx
0x18000245e  mov     eax, [rbp+88h]
0x180002464  cmp     eax, 0E06D7363h
0x180002469  jnz     short loc_180002485
0x18000246b  mov     rdx, [rbp+0D8h]
0x180002472  mov     ecx, [rbp+88h]
0x180002478  call    _XcptFilter_0
0x18000247d  mov     [rbp+90h], eax
0x180002483  jmp     short loc_18000248F
0x180002485  mov     dword ptr [rbp+90h], 0
0x18000248f  mov     eax, [rbp+90h]
0x180002495  add     rsp, 20h
0x180002499  pop     rbp
0x18000249a  retn
0x18000249c  push    rbp
0x18000249e  sub     rsp, 20h
0x1800024a2  mov     rbp, rdx
0x1800024a5  mov     rax, [rcx]
0x1800024a8  mov     edx, [rax]
0x1800024aa  mov     [rbp+0E0h], rcx
0x1800024b1  mov     [rbp+98h], edx
0x1800024b7  mov     eax, [rbp+98h]
0x1800024bd  cmp     eax, 0E06D7363h
0x1800024c2  jnz     short loc_1800024DE
0x1800024c4  mov     rdx, [rbp+0E0h]
0x1800024cb  mov     ecx, [rbp+98h]
0x1800024d1  call    _XcptFilter_0
0x1800024d6  mov     [rbp+0A0h], eax
0x1800024dc  jmp     short loc_1800024E8
0x1800024de  mov     dword ptr [rbp+0A0h], 0
0x1800024e8  mov     eax, [rbp+0A0h]
0x1800024ee  add     rsp, 20h
0x1800024f2  pop     rbp
0x1800024f3  retn
0x1800024f5  push    rbp
0x1800024f7  sub     rsp, 20h
0x1800024fb  mov     rbp, rdx
0x1800024fe  cmp     dword ptr [rbp+118h], 1
0x180002505  ja      short loc_180002511
0x180002507  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
