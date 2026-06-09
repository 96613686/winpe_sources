# __DllMainCRTStartup

- ea: `0x180003744`
- end: `0x180003845`
- name: `__DllMainCRTStartup`
- size: `257`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, __int64 fdwReason, void *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180003700`

## callees

- `0x18000361c`
- `0x180003744`
- `0x180003974`

## pseudocode

```c
__int64 __fastcall _DllMainCRTStartup(HINSTANCE hinstDLL, __int64 fdwReason, void *a3)
{
  DWORD v3; // edi
  unsigned int v5; // ebx

  v3 = fdwReason;
  if ( (_DWORD)fdwReason || dword_180009060 )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 || (v5 = CRT_INIT(hinstDLL, fdwReason, a3)) != 0 )
    {
      v5 = DllMain(hinstDLL, v3, a3);
      if ( v3 == 1 && !v5 )
      {
        DllMain(hinstDLL, 0, 0);
        CRT_INIT(hinstDLL, 0, 0);
      }
      if ( !v3 || v3 == 3 )
        return (unsigned int)CRT_INIT(hinstDLL, v3, a3);
    }
  }
  else
  {
    return 0;
  }
  return v5;
}

```

## disassembly

```asm
0x180003744  mov     rax, rsp
0x180003747  mov     [rax+18h], r8
0x18000374b  mov     [rax+10h], edx
0x18000374e  mov     [rax+8], rcx
0x180003752  push    rbx
0x180003753  push    rsi
0x180003754  push    rdi
0x180003755  sub     rsp, 50h
0x180003759  mov     edi, edx
0x18000375b  mov     rsi, rcx
0x18000375e  test    edx, edx
0x180003760  jnz     short loc_180003774
0x180003762  cmp     cs:dword_180009060, edx
0x180003768  jnz     short loc_180003774
0x18000376a  xor     ebx, ebx
0x18000376c  mov     [rax-48h], ebx
0x18000376f  jmp     loc_18000383B
0x180003774  lea     eax, [rdx-1]
0x180003777  cmp     eax, 1
0x18000377a  ja      short loc_1800037A8
0x18000377c  mov     r8, [rsp+68h+lpvReserved]
0x180003784  call    _CRT_INIT
0x180003789  mov     ebx, eax
0x18000378b  mov     [rsp+68h+var_48], eax
0x18000378f  jmp     short loc_1800037A0
0x180003791  xor     ebx, ebx
0x180003793  mov     [rsp+68h+var_48], ebx
0x180003797  mov     edi, [rsp+68h+arg_8]
0x18000379b  mov     rsi, [rsp+68h+arg_0]
0x1800037a0  test    ebx, ebx
0x1800037a2  jz      loc_18000383B
0x1800037a8  mov     r8, [rsp+68h+lpvReserved]; lpvReserved
0x1800037b0  mov     edx, edi; fdwReason
0x1800037b2  mov     rcx, rsi; hinstDLL
0x1800037b5  call    DllMain
0x1800037ba  mov     ebx, eax
0x1800037bc  mov     [rsp+68h+var_48], eax
0x1800037c0  jmp     short loc_1800037D1
0x1800037c2  xor     ebx, ebx
0x1800037c4  mov     [rsp+68h+var_48], ebx
0x1800037c8  mov     edi, [rsp+68h+arg_8]
0x1800037cc  mov     rsi, [rsp+68h+arg_0]
0x1800037d1  cmp     edi, 1
0x1800037d4  jnz     short loc_180003812
0x1800037d6  test    ebx, ebx
0x1800037d8  jnz     short loc_180003812
0x1800037da  xor     r8d, r8d; lpvReserved
0x1800037dd  xor     edx, edx; fdwReason
0x1800037df  mov     rcx, rsi; hinstDLL
0x1800037e2  call    DllMain
0x1800037e7  jmp     short loc_1800037F6
0x1800037e9  mov     edi, [rsp+68h+arg_8]
0x1800037ed  mov     rsi, [rsp+68h+arg_0]
0x1800037f2  mov     ebx, [rsp+68h+var_48]
0x1800037f6  xor     r8d, r8d
0x1800037f9  xor     edx, edx
0x1800037fb  mov     rcx, rsi
0x1800037fe  call    _CRT_INIT
0x180003803  jmp     short loc_180003812
0x180003805  mov     edi, [rsp+68h+arg_8]
0x180003809  mov     rsi, [rsp+68h+arg_0]
0x18000380e  mov     ebx, [rsp+68h+var_48]
0x180003812  test    edi, edi
0x180003814  jz      short loc_18000381B
0x180003816  cmp     edi, 3
0x180003819  jnz     short loc_18000383B
0x18000381b  mov     r8, [rsp+68h+lpvReserved]
0x180003823  mov     edx, edi
0x180003825  mov     rcx, rsi
0x180003828  call    _CRT_INIT
0x18000382d  mov     ebx, eax
0x18000382f  mov     [rsp+68h+var_48], eax
0x180003833  jmp     short loc_18000383B
0x180003835  xor     ebx, ebx
0x180003837  mov     [rsp+68h+var_48], ebx
0x18000383b  mov     eax, ebx
0x18000383d  add     rsp, 50h
0x180003841  pop     rdi
0x180003842  pop     rsi
0x180003843  pop     rbx
0x180003844  retn
0x1800049a6  push    rbp
0x1800049a8  sub     rsp, 20h
0x1800049ac  mov     rbp, rdx
0x1800049af  xor     eax, eax
0x1800049b1  add     rsp, 20h
0x1800049b5  pop     rbp
0x1800049b6  retn
0x1800049b8  push    rbp
0x1800049ba  sub     rsp, 20h
0x1800049be  mov     rbp, rdx
0x1800049c1  xor     eax, eax
0x1800049c3  add     rsp, 20h
0x1800049c7  pop     rbp
0x1800049c8  retn
0x1800049ca  push    rbp
0x1800049cc  sub     rsp, 20h
0x1800049d0  mov     rbp, rdx
0x1800049d3  xor     eax, eax
0x1800049d5  add     rsp, 20h
0x1800049d9  pop     rbp
0x1800049da  retn
0x1800049dc  push    rbp
0x1800049de  sub     rsp, 20h
0x1800049e2  mov     rbp, rdx
0x1800049e5  xor     eax, eax
0x1800049e7  add     rsp, 20h
0x1800049eb  pop     rbp
0x1800049ec  retn
0x1800049ee  push    rbp
0x1800049f0  sub     rsp, 20h
0x1800049f4  mov     rbp, rdx
0x1800049f7  xor     eax, eax
0x1800049f9  add     rsp, 20h
0x1800049fd  pop     rbp
0x1800049fe  retn
0x180004a00  push    rbp
0x180004a02  sub     rsp, 20h
0x180004a06  mov     rbp, rdx
0x180004a09  add     rsp, 20h
0x180004a0d  pop     rbp
0x180004a0e  retn
```
