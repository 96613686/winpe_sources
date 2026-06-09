# __DllMainCRTStartup

- ea: `0x1800085f4`
- end: `0x180008800`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, __int64 fdwReason, void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1800085b0`

## callees

- `0x180006a8c`
- `0x180008380`
- `0x1800085f4`
- `0x1800089f6`
- `0x18000a7e0`

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
  if ( (_DWORD)fdwReason || dword_1800110E0 )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_1800110E4 = 1;
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
            if ( dword_1800110E4 )
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
0x1800085f4  mov     [rsp+lpvReserved], r8
0x1800085f9  mov     [rsp+arg_8], edx
0x1800085fd  mov     [rsp+arg_0], rcx
0x180008602  push    rbx
0x180008603  push    rsi
0x180008604  push    rdi
0x180008605  sub     rsp, 0F0h
0x18000860c  mov     edi, edx
0x18000860e  mov     rsi, rcx
0x180008611  mov     ebx, 1
0x180008616  cmp     edx, ebx
0x180008618  ja      short loc_180008620
0x18000861a  mov     cs:__native_dllmain_reason, edx
0x180008620  test    edx, edx
0x180008622  jnz     short loc_180008637
0x180008624  cmp     cs:dword_1800110E0, edx
0x18000862a  jnz     short loc_180008637
0x18000862c  xor     ebx, ebx
0x18000862e  mov     [rsp+108h+var_E8], ebx
0x180008632  jmp     loc_1800087E4
0x180008637  lea     eax, [rdx-1]
0x18000863a  cmp     eax, 1
0x18000863d  ja      loc_1800086C4
0x180008643  mov     rax, cs:_pRawDllMain
0x18000864a  test    rax, rax
0x18000864d  jz      short loc_180008685
0x18000864f  cmp     edx, 1
0x180008652  jnz     short loc_18000865A
0x180008654  mov     cs:dword_1800110E4, edx
0x18000865a  mov     r8, [rsp+108h+lpvReserved]
0x180008662  call    cs:__guard_dispatch_icall_fptr
0x180008668  mov     ebx, eax
0x18000866a  mov     [rsp+108h+var_E8], eax
0x18000866e  jmp     short loc_180008685
0x180008670  xor     ebx, ebx
0x180008672  mov     [rsp+108h+var_E8], ebx
0x180008676  mov     edi, [rsp+108h+arg_8]
0x18000867d  mov     rsi, [rsp+108h+arg_0]
0x180008685  test    ebx, ebx
0x180008687  jz      loc_1800087E4
0x18000868d  mov     r8, [rsp+108h+lpvReserved]
0x180008695  mov     edx, edi
0x180008697  mov     rcx, rsi
0x18000869a  call    _CRT_INIT
0x18000869f  mov     ebx, eax
0x1800086a1  mov     [rsp+108h+var_E8], eax
0x1800086a5  jmp     short loc_1800086BC
0x1800086a7  xor     ebx, ebx
0x1800086a9  mov     [rsp+108h+var_E8], ebx
0x1800086ad  mov     edi, [rsp+108h+arg_8]
0x1800086b4  mov     rsi, [rsp+108h+arg_0]
0x1800086bc  test    ebx, ebx
0x1800086be  jz      loc_1800087E4
0x1800086c4  mov     r8, [rsp+108h+lpvReserved]; lpvReserved
0x1800086cc  mov     edx, edi; fdwReason
0x1800086ce  mov     rcx, rsi; hinstDLL
0x1800086d1  call    DllMain
0x1800086d6  mov     ebx, eax
0x1800086d8  mov     [rsp+108h+var_E8], eax
0x1800086dc  jmp     short loc_1800086F3
0x1800086de  xor     ebx, ebx
0x1800086e0  mov     [rsp+108h+var_E8], ebx
0x1800086e4  mov     edi, [rsp+108h+arg_8]
0x1800086eb  mov     rsi, [rsp+108h+arg_0]
0x1800086f3  cmp     edi, 1
0x1800086f6  jnz     short loc_18000876F
0x1800086f8  test    ebx, ebx
0x1800086fa  jnz     short loc_18000876F
0x1800086fc  xor     r8d, r8d; lpvReserved
0x1800086ff  xor     edx, edx; fdwReason
0x180008701  mov     rcx, rsi; hinstDLL
0x180008704  call    DllMain
0x180008709  jmp     short loc_18000871E
0x18000870b  mov     edi, [rsp+108h+arg_8]
0x180008712  mov     rsi, [rsp+108h+arg_0]
0x18000871a  mov     ebx, [rsp+108h+var_E8]
0x18000871e  xor     r8d, r8d
0x180008721  xor     edx, edx
0x180008723  mov     rcx, rsi
0x180008726  call    _CRT_INIT
0x18000872b  jmp     short loc_180008740
0x18000872d  mov     edi, [rsp+108h+arg_8]
0x180008734  mov     rsi, [rsp+108h+arg_0]
0x18000873c  mov     ebx, [rsp+108h+var_E8]
0x180008740  mov     rax, cs:_pRawDllMain
0x180008747  test    rax, rax
0x18000874a  jz      short loc_18000876F
0x18000874c  xor     r8d, r8d
0x18000874f  xor     edx, edx
0x180008751  mov     rcx, rsi
0x180008754  call    cs:__guard_dispatch_icall_fptr
0x18000875a  jmp     short loc_18000876F
0x18000875c  mov     edi, [rsp+108h+arg_8]
0x180008763  mov     rsi, [rsp+108h+arg_0]
0x18000876b  mov     ebx, [rsp+108h+var_E8]
0x18000876f  test    edi, edi
0x180008771  jz      short loc_180008778
0x180008773  cmp     edi, 3
0x180008776  jnz     short loc_1800087E4
0x180008778  mov     r8, [rsp+108h+lpvReserved]
0x180008780  mov     edx, edi
0x180008782  mov     rcx, rsi
0x180008785  call    _CRT_INIT
0x18000878a  mov     ebx, eax
0x18000878c  mov     [rsp+108h+var_E8], eax
0x180008790  jmp     short loc_1800087A7
0x180008792  xor     ebx, ebx
0x180008794  mov     [rsp+108h+var_E8], ebx
0x180008798  mov     edi, [rsp+108h+arg_8]
0x18000879f  mov     rsi, [rsp+108h+arg_0]
0x1800087a7  mov     rax, cs:_pRawDllMain
0x1800087ae  test    rax, rax
0x1800087b1  jz      short loc_1800087E4
0x1800087b3  cmp     cs:dword_1800110E4, 0
0x1800087ba  jz      short loc_1800087E4
0x1800087bc  mov     r8, [rsp+108h+lpvReserved]
0x1800087c4  mov     edx, edi
0x1800087c6  mov     rcx, rsi
0x1800087c9  call    cs:__guard_dispatch_icall_fptr
0x1800087cf  mov     ebx, eax
0x1800087d1  mov     [rsp+108h+var_E8], eax
0x1800087d5  jmp     short loc_1800087E4
0x1800087d7  xor     ebx, ebx
0x1800087d9  mov     [rsp+108h+var_E8], ebx
0x1800087dd  mov     edi, [rsp+108h+arg_8]
0x1800087e4  cmp     edi, 1
0x1800087e7  ja      short loc_1800087F3
0x1800087e9  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x1800087f3  mov     eax, ebx
0x1800087f5  add     rsp, 0F0h
0x1800087fc  pop     rdi
0x1800087fd  pop     rsi
0x1800087fe  pop     rbx
0x1800087ff  retn
0x18000a850  push    rbp
0x18000a852  sub     rsp, 20h
0x18000a856  mov     rbp, rdx
0x18000a859  mov     rax, [rcx]
0x18000a85c  mov     edx, [rax]
0x18000a85e  mov     [rbp+0A8h], rcx
0x18000a865  mov     [rbp+28h], edx
0x18000a868  mov     eax, [rbp+28h]
0x18000a86b  cmp     eax, 0E06D7363h
0x18000a870  jnz     short loc_18000A886
0x18000a872  mov     rdx, [rbp+0A8h]
0x18000a879  mov     ecx, [rbp+28h]
0x18000a87c  call    _XcptFilter_0
0x18000a881  mov     [rbp+30h], eax
0x18000a884  jmp     short loc_18000A88D
0x18000a886  mov     dword ptr [rbp+30h], 0
0x18000a88d  mov     eax, [rbp+30h]
0x18000a890  add     rsp, 20h
0x18000a894  pop     rbp
0x18000a895  retn
0x18000a897  push    rbp
0x18000a899  sub     rsp, 20h
0x18000a89d  mov     rbp, rdx
0x18000a8a0  mov     rax, [rcx]
0x18000a8a3  mov     edx, [rax]
0x18000a8a5  mov     [rbp+0B0h], rcx
0x18000a8ac  mov     [rbp+38h], edx
0x18000a8af  mov     eax, [rbp+38h]
0x18000a8b2  cmp     eax, 0E06D7363h
0x18000a8b7  jnz     short loc_18000A8CD
0x18000a8b9  mov     rdx, [rbp+0B0h]
0x18000a8c0  mov     ecx, [rbp+38h]
0x18000a8c3  call    _XcptFilter_0
0x18000a8c8  mov     [rbp+40h], eax
0x18000a8cb  jmp     short loc_18000A8D4
0x18000a8cd  mov     dword ptr [rbp+40h], 0
0x18000a8d4  mov     eax, [rbp+40h]
0x18000a8d7  add     rsp, 20h
0x18000a8db  pop     rbp
0x18000a8dc  retn
0x18000a8de  push    rbp
0x18000a8e0  sub     rsp, 20h
0x18000a8e4  mov     rbp, rdx
0x18000a8e7  mov     rax, [rcx]
0x18000a8ea  mov     edx, [rax]
0x18000a8ec  mov     [rbp+0B8h], rcx
0x18000a8f3  mov     [rbp+48h], edx
0x18000a8f6  mov     eax, [rbp+48h]
0x18000a8f9  cmp     eax, 0E06D7363h
0x18000a8fe  jnz     short loc_18000A914
0x18000a900  mov     rdx, [rbp+0B8h]
0x18000a907  mov     ecx, [rbp+48h]
0x18000a90a  call    _XcptFilter_0
0x18000a90f  mov     [rbp+50h], eax
0x18000a912  jmp     short loc_18000A91B
0x18000a914  mov     dword ptr [rbp+50h], 0
0x18000a91b  mov     eax, [rbp+50h]
0x18000a91e  add     rsp, 20h
0x18000a922  pop     rbp
0x18000a923  retn
0x18000a925  push    rbp
0x18000a927  sub     rsp, 20h
0x18000a92b  mov     rbp, rdx
0x18000a92e  mov     rax, [rcx]
0x18000a931  mov     edx, [rax]
0x18000a933  mov     [rbp+0C0h], rcx
0x18000a93a  mov     [rbp+58h], edx
0x18000a93d  mov     eax, [rbp+58h]
0x18000a940  cmp     eax, 0E06D7363h
0x18000a945  jnz     short loc_18000A95B
0x18000a947  mov     rdx, [rbp+0C0h]
0x18000a94e  mov     ecx, [rbp+58h]
0x18000a951  call    _XcptFilter_0
0x18000a956  mov     [rbp+60h], eax
0x18000a959  jmp     short loc_18000A962
0x18000a95b  mov     dword ptr [rbp+60h], 0
0x18000a962  mov     eax, [rbp+60h]
0x18000a965  add     rsp, 20h
0x18000a969  pop     rbp
0x18000a96a  retn
0x18000a96c  push    rbp
0x18000a96e  sub     rsp, 20h
0x18000a972  mov     rbp, rdx
0x18000a975  mov     rax, [rcx]
0x18000a978  mov     edx, [rax]
0x18000a97a  mov     [rbp+0C8h], rcx
0x18000a981  mov     [rbp+68h], edx
0x18000a984  mov     eax, [rbp+68h]
0x18000a987  cmp     eax, 0E06D7363h
0x18000a98c  jnz     short loc_18000A9A2
0x18000a98e  mov     rdx, [rbp+0C8h]
0x18000a995  mov     ecx, [rbp+68h]
0x18000a998  call    _XcptFilter_0
0x18000a99d  mov     [rbp+70h], eax
0x18000a9a0  jmp     short loc_18000A9A9
0x18000a9a2  mov     dword ptr [rbp+70h], 0
0x18000a9a9  mov     eax, [rbp+70h]
0x18000a9ac  add     rsp, 20h
0x18000a9b0  pop     rbp
0x18000a9b1  retn
0x18000a9b3  push    rbp
0x18000a9b5  sub     rsp, 20h
0x18000a9b9  mov     rbp, rdx
0x18000a9bc  mov     rax, [rcx]
0x18000a9bf  mov     edx, [rax]
0x18000a9c1  mov     [rbp+0D0h], rcx
0x18000a9c8  mov     [rbp+78h], edx
0x18000a9cb  mov     eax, [rbp+78h]
0x18000a9ce  cmp     eax, 0E06D7363h
0x18000a9d3  jnz     short loc_18000A9EC
0x18000a9d5  mov     rdx, [rbp+0D0h]
0x18000a9dc  mov     ecx, [rbp+78h]
0x18000a9df  call    _XcptFilter_0
0x18000a9e4  mov     [rbp+80h], eax
0x18000a9ea  jmp     short loc_18000A9F6
0x18000a9ec  mov     dword ptr [rbp+80h], 0
0x18000a9f6  mov     eax, [rbp+80h]
0x18000a9fc  add     rsp, 20h
0x18000aa00  pop     rbp
0x18000aa01  retn
0x18000aa03  push    rbp
0x18000aa05  sub     rsp, 20h
0x18000aa09  mov     rbp, rdx
0x18000aa0c  mov     rax, [rcx]
0x18000aa0f  mov     edx, [rax]
0x18000aa11  mov     [rbp+0D8h], rcx
0x18000aa18  mov     [rbp+88h], edx
0x18000aa1e  mov     eax, [rbp+88h]
0x18000aa24  cmp     eax, 0E06D7363h
0x18000aa29  jnz     short loc_18000AA45
0x18000aa2b  mov     rdx, [rbp+0D8h]
0x18000aa32  mov     ecx, [rbp+88h]
0x18000aa38  call    _XcptFilter_0
0x18000aa3d  mov     [rbp+90h], eax
0x18000aa43  jmp     short loc_18000AA4F
0x18000aa45  mov     dword ptr [rbp+90h], 0
0x18000aa4f  mov     eax, [rbp+90h]
0x18000aa55  add     rsp, 20h
0x18000aa59  pop     rbp
0x18000aa5a  retn
0x18000aa5c  push    rbp
0x18000aa5e  sub     rsp, 20h
0x18000aa62  mov     rbp, rdx
0x18000aa65  mov     rax, [rcx]
0x18000aa68  mov     edx, [rax]
0x18000aa6a  mov     [rbp+0E0h], rcx
0x18000aa71  mov     [rbp+98h], edx
0x18000aa77  mov     eax, [rbp+98h]
0x18000aa7d  cmp     eax, 0E06D7363h
0x18000aa82  jnz     short loc_18000AA9E
0x18000aa84  mov     rdx, [rbp+0E0h]
0x18000aa8b  mov     ecx, [rbp+98h]
0x18000aa91  call    _XcptFilter_0
0x18000aa96  mov     [rbp+0A0h], eax
0x18000aa9c  jmp     short loc_18000AAA8
0x18000aa9e  mov     dword ptr [rbp+0A0h], 0
0x18000aaa8  mov     eax, [rbp+0A0h]
0x18000aaae  add     rsp, 20h
0x18000aab2  pop     rbp
0x18000aab3  retn
0x18000aab5  push    rbp
0x18000aab7  sub     rsp, 20h
0x18000aabb  mov     rbp, rdx
0x18000aabe  cmp     dword ptr [rbp+118h], 1
0x18000aac5  ja      short loc_18000AAD1
0x18000aac7  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
