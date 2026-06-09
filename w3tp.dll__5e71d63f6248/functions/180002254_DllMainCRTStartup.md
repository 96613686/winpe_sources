# __DllMainCRTStartup

- ea: `0x180002254`
- end: `0x180002460`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180002210`

## callees

- `0x180001fe0`
- `0x180002254`
- `0x18000248a`
- `0x1800040a0`
- `0x180004210`

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
  if ( (_DWORD)fdwReason || dword_1800090C0 )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_1800090C4 = 1;
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
            if ( dword_1800090C4 )
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
0x180002254  mov     [rsp+lpvReserved], r8
0x180002259  mov     [rsp+arg_8], edx
0x18000225d  mov     [rsp+arg_0], rcx
0x180002262  push    rbx
0x180002263  push    rsi
0x180002264  push    rdi
0x180002265  sub     rsp, 0F0h
0x18000226c  mov     edi, edx
0x18000226e  mov     rsi, rcx
0x180002271  mov     ebx, 1
0x180002276  cmp     edx, ebx
0x180002278  ja      short loc_180002280
0x18000227a  mov     cs:__native_dllmain_reason, edx
0x180002280  test    edx, edx
0x180002282  jnz     short loc_180002297
0x180002284  cmp     cs:dword_1800090C0, edx
0x18000228a  jnz     short loc_180002297
0x18000228c  xor     ebx, ebx
0x18000228e  mov     [rsp+108h+var_E8], ebx
0x180002292  jmp     loc_180002444
0x180002297  lea     eax, [rdx-1]
0x18000229a  cmp     eax, 1
0x18000229d  ja      loc_180002324
0x1800022a3  mov     rax, cs:_pRawDllMain
0x1800022aa  test    rax, rax
0x1800022ad  jz      short loc_1800022E5
0x1800022af  cmp     edx, 1
0x1800022b2  jnz     short loc_1800022BA
0x1800022b4  mov     cs:dword_1800090C4, edx
0x1800022ba  mov     r8, [rsp+108h+lpvReserved]
0x1800022c2  call    cs:__guard_dispatch_icall_fptr
0x1800022c8  mov     ebx, eax
0x1800022ca  mov     [rsp+108h+var_E8], eax
0x1800022ce  jmp     short loc_1800022E5
0x1800022d0  xor     ebx, ebx
0x1800022d2  mov     [rsp+108h+var_E8], ebx
0x1800022d6  mov     edi, [rsp+108h+arg_8]
0x1800022dd  mov     rsi, [rsp+108h+arg_0]
0x1800022e5  test    ebx, ebx
0x1800022e7  jz      loc_180002444
0x1800022ed  mov     r8, [rsp+108h+lpvReserved]
0x1800022f5  mov     edx, edi
0x1800022f7  mov     rcx, rsi
0x1800022fa  call    _CRT_INIT
0x1800022ff  mov     ebx, eax
0x180002301  mov     [rsp+108h+var_E8], eax
0x180002305  jmp     short loc_18000231C
0x180002307  xor     ebx, ebx
0x180002309  mov     [rsp+108h+var_E8], ebx
0x18000230d  mov     edi, [rsp+108h+arg_8]
0x180002314  mov     rsi, [rsp+108h+arg_0]
0x18000231c  test    ebx, ebx
0x18000231e  jz      loc_180002444
0x180002324  mov     r8, [rsp+108h+lpvReserved]; lpvReserved
0x18000232c  mov     edx, edi; fdwReason
0x18000232e  mov     rcx, rsi; hinstDLL
0x180002331  call    DllMain
0x180002336  mov     ebx, eax
0x180002338  mov     [rsp+108h+var_E8], eax
0x18000233c  jmp     short loc_180002353
0x18000233e  xor     ebx, ebx
0x180002340  mov     [rsp+108h+var_E8], ebx
0x180002344  mov     edi, [rsp+108h+arg_8]
0x18000234b  mov     rsi, [rsp+108h+arg_0]
0x180002353  cmp     edi, 1
0x180002356  jnz     short loc_1800023CF
0x180002358  test    ebx, ebx
0x18000235a  jnz     short loc_1800023CF
0x18000235c  xor     r8d, r8d; lpvReserved
0x18000235f  xor     edx, edx; fdwReason
0x180002361  mov     rcx, rsi; hinstDLL
0x180002364  call    DllMain
0x180002369  jmp     short loc_18000237E
0x18000236b  mov     edi, [rsp+108h+arg_8]
0x180002372  mov     rsi, [rsp+108h+arg_0]
0x18000237a  mov     ebx, [rsp+108h+var_E8]
0x18000237e  xor     r8d, r8d
0x180002381  xor     edx, edx
0x180002383  mov     rcx, rsi
0x180002386  call    _CRT_INIT
0x18000238b  jmp     short loc_1800023A0
0x18000238d  mov     edi, [rsp+108h+arg_8]
0x180002394  mov     rsi, [rsp+108h+arg_0]
0x18000239c  mov     ebx, [rsp+108h+var_E8]
0x1800023a0  mov     rax, cs:_pRawDllMain
0x1800023a7  test    rax, rax
0x1800023aa  jz      short loc_1800023CF
0x1800023ac  xor     r8d, r8d
0x1800023af  xor     edx, edx
0x1800023b1  mov     rcx, rsi
0x1800023b4  call    cs:__guard_dispatch_icall_fptr
0x1800023ba  jmp     short loc_1800023CF
0x1800023bc  mov     edi, [rsp+108h+arg_8]
0x1800023c3  mov     rsi, [rsp+108h+arg_0]
0x1800023cb  mov     ebx, [rsp+108h+var_E8]
0x1800023cf  test    edi, edi
0x1800023d1  jz      short loc_1800023D8
0x1800023d3  cmp     edi, 3
0x1800023d6  jnz     short loc_180002444
0x1800023d8  mov     r8, [rsp+108h+lpvReserved]
0x1800023e0  mov     edx, edi
0x1800023e2  mov     rcx, rsi
0x1800023e5  call    _CRT_INIT
0x1800023ea  mov     ebx, eax
0x1800023ec  mov     [rsp+108h+var_E8], eax
0x1800023f0  jmp     short loc_180002407
0x1800023f2  xor     ebx, ebx
0x1800023f4  mov     [rsp+108h+var_E8], ebx
0x1800023f8  mov     edi, [rsp+108h+arg_8]
0x1800023ff  mov     rsi, [rsp+108h+arg_0]
0x180002407  mov     rax, cs:_pRawDllMain
0x18000240e  test    rax, rax
0x180002411  jz      short loc_180002444
0x180002413  cmp     cs:dword_1800090C4, 0
0x18000241a  jz      short loc_180002444
0x18000241c  mov     r8, [rsp+108h+lpvReserved]
0x180002424  mov     edx, edi
0x180002426  mov     rcx, rsi
0x180002429  call    cs:__guard_dispatch_icall_fptr
0x18000242f  mov     ebx, eax
0x180002431  mov     [rsp+108h+var_E8], eax
0x180002435  jmp     short loc_180002444
0x180002437  xor     ebx, ebx
0x180002439  mov     [rsp+108h+var_E8], ebx
0x18000243d  mov     edi, [rsp+108h+arg_8]
0x180002444  cmp     edi, 1
0x180002447  ja      short loc_180002453
0x180002449  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x180002453  mov     eax, ebx
0x180002455  add     rsp, 0F0h
0x18000245c  pop     rdi
0x18000245d  pop     rsi
0x18000245e  pop     rbx
0x18000245f  retn
0x180004280  push    rbp
0x180004282  sub     rsp, 20h
0x180004286  mov     rbp, rdx
0x180004289  mov     rax, [rcx]
0x18000428c  mov     edx, [rax]
0x18000428e  mov     [rbp+0A8h], rcx
0x180004295  mov     [rbp+28h], edx
0x180004298  mov     eax, [rbp+28h]
0x18000429b  cmp     eax, 0E06D7363h
0x1800042a0  jnz     short loc_1800042B6
0x1800042a2  mov     rdx, [rbp+0A8h]
0x1800042a9  mov     ecx, [rbp+28h]
0x1800042ac  call    _XcptFilter_0
0x1800042b1  mov     [rbp+30h], eax
0x1800042b4  jmp     short loc_1800042BD
0x1800042b6  mov     dword ptr [rbp+30h], 0
0x1800042bd  mov     eax, [rbp+30h]
0x1800042c0  add     rsp, 20h
0x1800042c4  pop     rbp
0x1800042c5  retn
0x1800042c7  push    rbp
0x1800042c9  sub     rsp, 20h
0x1800042cd  mov     rbp, rdx
0x1800042d0  mov     rax, [rcx]
0x1800042d3  mov     edx, [rax]
0x1800042d5  mov     [rbp+0B0h], rcx
0x1800042dc  mov     [rbp+38h], edx
0x1800042df  mov     eax, [rbp+38h]
0x1800042e2  cmp     eax, 0E06D7363h
0x1800042e7  jnz     short loc_1800042FD
0x1800042e9  mov     rdx, [rbp+0B0h]
0x1800042f0  mov     ecx, [rbp+38h]
0x1800042f3  call    _XcptFilter_0
0x1800042f8  mov     [rbp+40h], eax
0x1800042fb  jmp     short loc_180004304
0x1800042fd  mov     dword ptr [rbp+40h], 0
0x180004304  mov     eax, [rbp+40h]
0x180004307  add     rsp, 20h
0x18000430b  pop     rbp
0x18000430c  retn
0x18000430e  push    rbp
0x180004310  sub     rsp, 20h
0x180004314  mov     rbp, rdx
0x180004317  mov     rax, [rcx]
0x18000431a  mov     edx, [rax]
0x18000431c  mov     [rbp+0B8h], rcx
0x180004323  mov     [rbp+48h], edx
0x180004326  mov     eax, [rbp+48h]
0x180004329  cmp     eax, 0E06D7363h
0x18000432e  jnz     short loc_180004344
0x180004330  mov     rdx, [rbp+0B8h]
0x180004337  mov     ecx, [rbp+48h]
0x18000433a  call    _XcptFilter_0
0x18000433f  mov     [rbp+50h], eax
0x180004342  jmp     short loc_18000434B
0x180004344  mov     dword ptr [rbp+50h], 0
0x18000434b  mov     eax, [rbp+50h]
0x18000434e  add     rsp, 20h
0x180004352  pop     rbp
0x180004353  retn
0x180004355  push    rbp
0x180004357  sub     rsp, 20h
0x18000435b  mov     rbp, rdx
0x18000435e  mov     rax, [rcx]
0x180004361  mov     edx, [rax]
0x180004363  mov     [rbp+0C0h], rcx
0x18000436a  mov     [rbp+58h], edx
0x18000436d  mov     eax, [rbp+58h]
0x180004370  cmp     eax, 0E06D7363h
0x180004375  jnz     short loc_18000438B
0x180004377  mov     rdx, [rbp+0C0h]
0x18000437e  mov     ecx, [rbp+58h]
0x180004381  call    _XcptFilter_0
0x180004386  mov     [rbp+60h], eax
0x180004389  jmp     short loc_180004392
0x18000438b  mov     dword ptr [rbp+60h], 0
0x180004392  mov     eax, [rbp+60h]
0x180004395  add     rsp, 20h
0x180004399  pop     rbp
0x18000439a  retn
0x18000439c  push    rbp
0x18000439e  sub     rsp, 20h
0x1800043a2  mov     rbp, rdx
0x1800043a5  mov     rax, [rcx]
0x1800043a8  mov     edx, [rax]
0x1800043aa  mov     [rbp+0C8h], rcx
0x1800043b1  mov     [rbp+68h], edx
0x1800043b4  mov     eax, [rbp+68h]
0x1800043b7  cmp     eax, 0E06D7363h
0x1800043bc  jnz     short loc_1800043D2
0x1800043be  mov     rdx, [rbp+0C8h]
0x1800043c5  mov     ecx, [rbp+68h]
0x1800043c8  call    _XcptFilter_0
0x1800043cd  mov     [rbp+70h], eax
0x1800043d0  jmp     short loc_1800043D9
0x1800043d2  mov     dword ptr [rbp+70h], 0
0x1800043d9  mov     eax, [rbp+70h]
0x1800043dc  add     rsp, 20h
0x1800043e0  pop     rbp
0x1800043e1  retn
0x1800043e3  push    rbp
0x1800043e5  sub     rsp, 20h
0x1800043e9  mov     rbp, rdx
0x1800043ec  mov     rax, [rcx]
0x1800043ef  mov     edx, [rax]
0x1800043f1  mov     [rbp+0D0h], rcx
0x1800043f8  mov     [rbp+78h], edx
0x1800043fb  mov     eax, [rbp+78h]
0x1800043fe  cmp     eax, 0E06D7363h
0x180004403  jnz     short loc_18000441C
0x180004405  mov     rdx, [rbp+0D0h]
0x18000440c  mov     ecx, [rbp+78h]
0x18000440f  call    _XcptFilter_0
0x180004414  mov     [rbp+80h], eax
0x18000441a  jmp     short loc_180004426
0x18000441c  mov     dword ptr [rbp+80h], 0
0x180004426  mov     eax, [rbp+80h]
0x18000442c  add     rsp, 20h
0x180004430  pop     rbp
0x180004431  retn
0x180004433  push    rbp
0x180004435  sub     rsp, 20h
0x180004439  mov     rbp, rdx
0x18000443c  mov     rax, [rcx]
0x18000443f  mov     edx, [rax]
0x180004441  mov     [rbp+0D8h], rcx
0x180004448  mov     [rbp+88h], edx
0x18000444e  mov     eax, [rbp+88h]
0x180004454  cmp     eax, 0E06D7363h
0x180004459  jnz     short loc_180004475
0x18000445b  mov     rdx, [rbp+0D8h]
0x180004462  mov     ecx, [rbp+88h]
0x180004468  call    _XcptFilter_0
0x18000446d  mov     [rbp+90h], eax
0x180004473  jmp     short loc_18000447F
0x180004475  mov     dword ptr [rbp+90h], 0
0x18000447f  mov     eax, [rbp+90h]
0x180004485  add     rsp, 20h
0x180004489  pop     rbp
0x18000448a  retn
0x18000448c  push    rbp
0x18000448e  sub     rsp, 20h
0x180004492  mov     rbp, rdx
0x180004495  mov     rax, [rcx]
0x180004498  mov     edx, [rax]
0x18000449a  mov     [rbp+0E0h], rcx
0x1800044a1  mov     [rbp+98h], edx
0x1800044a7  mov     eax, [rbp+98h]
0x1800044ad  cmp     eax, 0E06D7363h
0x1800044b2  jnz     short loc_1800044CE
0x1800044b4  mov     rdx, [rbp+0E0h]
0x1800044bb  mov     ecx, [rbp+98h]
0x1800044c1  call    _XcptFilter_0
0x1800044c6  mov     [rbp+0A0h], eax
0x1800044cc  jmp     short loc_1800044D8
0x1800044ce  mov     dword ptr [rbp+0A0h], 0
0x1800044d8  mov     eax, [rbp+0A0h]
0x1800044de  add     rsp, 20h
0x1800044e2  pop     rbp
0x1800044e3  retn
0x1800044e5  push    rbp
0x1800044e7  sub     rsp, 20h
0x1800044eb  mov     rbp, rdx
0x1800044ee  cmp     dword ptr [rbp+118h], 1
0x1800044f5  ja      short loc_180004501
0x1800044f7  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
