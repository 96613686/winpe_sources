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
- `0x1800014d6`
- `0x1800028cc`
- `0x180003700`

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
  if ( (_DWORD)fdwReason || dword_1800070E0 )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_1800070E4 = 1;
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
            if ( dword_1800070E4 )
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
0x1800012f4  cmp     cs:dword_1800070E0, edx
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
0x180001324  mov     cs:dword_1800070E4, edx
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
0x180001483  cmp     cs:dword_1800070E4, 0
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
0x180003770  push    rbp
0x180003772  sub     rsp, 20h
0x180003776  mov     rbp, rdx
0x180003779  mov     rax, [rcx]
0x18000377c  mov     edx, [rax]
0x18000377e  mov     [rbp+0A8h], rcx
0x180003785  mov     [rbp+28h], edx
0x180003788  mov     eax, [rbp+28h]
0x18000378b  cmp     eax, 0E06D7363h
0x180003790  jnz     short loc_1800037A6
0x180003792  mov     rdx, [rbp+0A8h]
0x180003799  mov     ecx, [rbp+28h]
0x18000379c  call    _XcptFilter_0
0x1800037a1  mov     [rbp+30h], eax
0x1800037a4  jmp     short loc_1800037AD
0x1800037a6  mov     dword ptr [rbp+30h], 0
0x1800037ad  mov     eax, [rbp+30h]
0x1800037b0  add     rsp, 20h
0x1800037b4  pop     rbp
0x1800037b5  retn
0x1800037b7  push    rbp
0x1800037b9  sub     rsp, 20h
0x1800037bd  mov     rbp, rdx
0x1800037c0  mov     rax, [rcx]
0x1800037c3  mov     edx, [rax]
0x1800037c5  mov     [rbp+0B0h], rcx
0x1800037cc  mov     [rbp+38h], edx
0x1800037cf  mov     eax, [rbp+38h]
0x1800037d2  cmp     eax, 0E06D7363h
0x1800037d7  jnz     short loc_1800037ED
0x1800037d9  mov     rdx, [rbp+0B0h]
0x1800037e0  mov     ecx, [rbp+38h]
0x1800037e3  call    _XcptFilter_0
0x1800037e8  mov     [rbp+40h], eax
0x1800037eb  jmp     short loc_1800037F4
0x1800037ed  mov     dword ptr [rbp+40h], 0
0x1800037f4  mov     eax, [rbp+40h]
0x1800037f7  add     rsp, 20h
0x1800037fb  pop     rbp
0x1800037fc  retn
0x1800037fe  push    rbp
0x180003800  sub     rsp, 20h
0x180003804  mov     rbp, rdx
0x180003807  mov     rax, [rcx]
0x18000380a  mov     edx, [rax]
0x18000380c  mov     [rbp+0B8h], rcx
0x180003813  mov     [rbp+48h], edx
0x180003816  mov     eax, [rbp+48h]
0x180003819  cmp     eax, 0E06D7363h
0x18000381e  jnz     short loc_180003834
0x180003820  mov     rdx, [rbp+0B8h]
0x180003827  mov     ecx, [rbp+48h]
0x18000382a  call    _XcptFilter_0
0x18000382f  mov     [rbp+50h], eax
0x180003832  jmp     short loc_18000383B
0x180003834  mov     dword ptr [rbp+50h], 0
0x18000383b  mov     eax, [rbp+50h]
0x18000383e  add     rsp, 20h
0x180003842  pop     rbp
0x180003843  retn
0x180003845  push    rbp
0x180003847  sub     rsp, 20h
0x18000384b  mov     rbp, rdx
0x18000384e  mov     rax, [rcx]
0x180003851  mov     edx, [rax]
0x180003853  mov     [rbp+0C0h], rcx
0x18000385a  mov     [rbp+58h], edx
0x18000385d  mov     eax, [rbp+58h]
0x180003860  cmp     eax, 0E06D7363h
0x180003865  jnz     short loc_18000387B
0x180003867  mov     rdx, [rbp+0C0h]
0x18000386e  mov     ecx, [rbp+58h]
0x180003871  call    _XcptFilter_0
0x180003876  mov     [rbp+60h], eax
0x180003879  jmp     short loc_180003882
0x18000387b  mov     dword ptr [rbp+60h], 0
0x180003882  mov     eax, [rbp+60h]
0x180003885  add     rsp, 20h
0x180003889  pop     rbp
0x18000388a  retn
0x18000388c  push    rbp
0x18000388e  sub     rsp, 20h
0x180003892  mov     rbp, rdx
0x180003895  mov     rax, [rcx]
0x180003898  mov     edx, [rax]
0x18000389a  mov     [rbp+0C8h], rcx
0x1800038a1  mov     [rbp+68h], edx
0x1800038a4  mov     eax, [rbp+68h]
0x1800038a7  cmp     eax, 0E06D7363h
0x1800038ac  jnz     short loc_1800038C2
0x1800038ae  mov     rdx, [rbp+0C8h]
0x1800038b5  mov     ecx, [rbp+68h]
0x1800038b8  call    _XcptFilter_0
0x1800038bd  mov     [rbp+70h], eax
0x1800038c0  jmp     short loc_1800038C9
0x1800038c2  mov     dword ptr [rbp+70h], 0
0x1800038c9  mov     eax, [rbp+70h]
0x1800038cc  add     rsp, 20h
0x1800038d0  pop     rbp
0x1800038d1  retn
0x1800038d3  push    rbp
0x1800038d5  sub     rsp, 20h
0x1800038d9  mov     rbp, rdx
0x1800038dc  mov     rax, [rcx]
0x1800038df  mov     edx, [rax]
0x1800038e1  mov     [rbp+0D0h], rcx
0x1800038e8  mov     [rbp+78h], edx
0x1800038eb  mov     eax, [rbp+78h]
0x1800038ee  cmp     eax, 0E06D7363h
0x1800038f3  jnz     short loc_18000390C
0x1800038f5  mov     rdx, [rbp+0D0h]
0x1800038fc  mov     ecx, [rbp+78h]
0x1800038ff  call    _XcptFilter_0
0x180003904  mov     [rbp+80h], eax
0x18000390a  jmp     short loc_180003916
0x18000390c  mov     dword ptr [rbp+80h], 0
0x180003916  mov     eax, [rbp+80h]
0x18000391c  add     rsp, 20h
0x180003920  pop     rbp
0x180003921  retn
0x180003923  push    rbp
0x180003925  sub     rsp, 20h
0x180003929  mov     rbp, rdx
0x18000392c  mov     rax, [rcx]
0x18000392f  mov     edx, [rax]
0x180003931  mov     [rbp+0D8h], rcx
0x180003938  mov     [rbp+88h], edx
0x18000393e  mov     eax, [rbp+88h]
0x180003944  cmp     eax, 0E06D7363h
0x180003949  jnz     short loc_180003965
0x18000394b  mov     rdx, [rbp+0D8h]
0x180003952  mov     ecx, [rbp+88h]
0x180003958  call    _XcptFilter_0
0x18000395d  mov     [rbp+90h], eax
0x180003963  jmp     short loc_18000396F
0x180003965  mov     dword ptr [rbp+90h], 0
0x18000396f  mov     eax, [rbp+90h]
0x180003975  add     rsp, 20h
0x180003979  pop     rbp
0x18000397a  retn
0x18000397c  push    rbp
0x18000397e  sub     rsp, 20h
0x180003982  mov     rbp, rdx
0x180003985  mov     rax, [rcx]
0x180003988  mov     edx, [rax]
0x18000398a  mov     [rbp+0E0h], rcx
0x180003991  mov     [rbp+98h], edx
0x180003997  mov     eax, [rbp+98h]
0x18000399d  cmp     eax, 0E06D7363h
0x1800039a2  jnz     short loc_1800039BE
0x1800039a4  mov     rdx, [rbp+0E0h]
0x1800039ab  mov     ecx, [rbp+98h]
0x1800039b1  call    _XcptFilter_0
0x1800039b6  mov     [rbp+0A0h], eax
0x1800039bc  jmp     short loc_1800039C8
0x1800039be  mov     dword ptr [rbp+0A0h], 0
0x1800039c8  mov     eax, [rbp+0A0h]
0x1800039ce  add     rsp, 20h
0x1800039d2  pop     rbp
0x1800039d3  retn
0x1800039d5  push    rbp
0x1800039d7  sub     rsp, 20h
0x1800039db  mov     rbp, rdx
0x1800039de  cmp     dword ptr [rbp+118h], 1
0x1800039e5  ja      short loc_1800039F1
0x1800039e7  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
