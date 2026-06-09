# __DllMainCRTStartup

- ea: `0x1800034f4`
- end: `0x180003700`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1800034b0`

## callees

- `0x180002760`
- `0x180003280`
- `0x1800034f4`
- `0x180003a48`
- `0x18000d200`

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
  if ( (_DWORD)fdwReason || dword_1800142C0 )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_1800142C4 = 1;
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
            if ( dword_1800142C4 )
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
0x1800034f4  mov     [rsp+lpvReserved], r8
0x1800034f9  mov     [rsp+arg_8], edx
0x1800034fd  mov     [rsp+arg_0], rcx
0x180003502  push    rbx
0x180003503  push    rsi
0x180003504  push    rdi
0x180003505  sub     rsp, 0F0h
0x18000350c  mov     edi, edx
0x18000350e  mov     rsi, rcx
0x180003511  mov     ebx, 1
0x180003516  cmp     edx, ebx
0x180003518  ja      short loc_180003520
0x18000351a  mov     cs:__native_dllmain_reason, edx
0x180003520  test    edx, edx
0x180003522  jnz     short loc_180003537
0x180003524  cmp     cs:dword_1800142C0, edx
0x18000352a  jnz     short loc_180003537
0x18000352c  xor     ebx, ebx
0x18000352e  mov     [rsp+108h+var_E8], ebx
0x180003532  jmp     loc_1800036E4
0x180003537  lea     eax, [rdx-1]
0x18000353a  cmp     eax, 1
0x18000353d  ja      loc_1800035C4
0x180003543  mov     rax, cs:_pRawDllMain
0x18000354a  test    rax, rax
0x18000354d  jz      short loc_180003585
0x18000354f  cmp     edx, 1
0x180003552  jnz     short loc_18000355A
0x180003554  mov     cs:dword_1800142C4, edx
0x18000355a  mov     r8, [rsp+108h+lpvReserved]
0x180003562  call    cs:__guard_dispatch_icall_fptr
0x180003568  mov     ebx, eax
0x18000356a  mov     [rsp+108h+var_E8], eax
0x18000356e  jmp     short loc_180003585
0x180003570  xor     ebx, ebx
0x180003572  mov     [rsp+108h+var_E8], ebx
0x180003576  mov     edi, [rsp+108h+arg_8]
0x18000357d  mov     rsi, [rsp+108h+arg_0]
0x180003585  test    ebx, ebx
0x180003587  jz      loc_1800036E4
0x18000358d  mov     r8, [rsp+108h+lpvReserved]
0x180003595  mov     edx, edi
0x180003597  mov     rcx, rsi
0x18000359a  call    _CRT_INIT
0x18000359f  mov     ebx, eax
0x1800035a1  mov     [rsp+108h+var_E8], eax
0x1800035a5  jmp     short loc_1800035BC
0x1800035a7  xor     ebx, ebx
0x1800035a9  mov     [rsp+108h+var_E8], ebx
0x1800035ad  mov     edi, [rsp+108h+arg_8]
0x1800035b4  mov     rsi, [rsp+108h+arg_0]
0x1800035bc  test    ebx, ebx
0x1800035be  jz      loc_1800036E4
0x1800035c4  mov     r8, [rsp+108h+lpvReserved]; lpvReserved
0x1800035cc  mov     edx, edi; fdwReason
0x1800035ce  mov     rcx, rsi; hinstDLL
0x1800035d1  call    DllMain
0x1800035d6  mov     ebx, eax
0x1800035d8  mov     [rsp+108h+var_E8], eax
0x1800035dc  jmp     short loc_1800035F3
0x1800035de  xor     ebx, ebx
0x1800035e0  mov     [rsp+108h+var_E8], ebx
0x1800035e4  mov     edi, [rsp+108h+arg_8]
0x1800035eb  mov     rsi, [rsp+108h+arg_0]
0x1800035f3  cmp     edi, 1
0x1800035f6  jnz     short loc_18000366F
0x1800035f8  test    ebx, ebx
0x1800035fa  jnz     short loc_18000366F
0x1800035fc  xor     r8d, r8d; lpvReserved
0x1800035ff  xor     edx, edx; fdwReason
0x180003601  mov     rcx, rsi; hinstDLL
0x180003604  call    DllMain
0x180003609  jmp     short loc_18000361E
0x18000360b  mov     edi, [rsp+108h+arg_8]
0x180003612  mov     rsi, [rsp+108h+arg_0]
0x18000361a  mov     ebx, [rsp+108h+var_E8]
0x18000361e  xor     r8d, r8d
0x180003621  xor     edx, edx
0x180003623  mov     rcx, rsi
0x180003626  call    _CRT_INIT
0x18000362b  jmp     short loc_180003640
0x18000362d  mov     edi, [rsp+108h+arg_8]
0x180003634  mov     rsi, [rsp+108h+arg_0]
0x18000363c  mov     ebx, [rsp+108h+var_E8]
0x180003640  mov     rax, cs:_pRawDllMain
0x180003647  test    rax, rax
0x18000364a  jz      short loc_18000366F
0x18000364c  xor     r8d, r8d
0x18000364f  xor     edx, edx
0x180003651  mov     rcx, rsi
0x180003654  call    cs:__guard_dispatch_icall_fptr
0x18000365a  jmp     short loc_18000366F
0x18000365c  mov     edi, [rsp+108h+arg_8]
0x180003663  mov     rsi, [rsp+108h+arg_0]
0x18000366b  mov     ebx, [rsp+108h+var_E8]
0x18000366f  test    edi, edi
0x180003671  jz      short loc_180003678
0x180003673  cmp     edi, 3
0x180003676  jnz     short loc_1800036E4
0x180003678  mov     r8, [rsp+108h+lpvReserved]
0x180003680  mov     edx, edi
0x180003682  mov     rcx, rsi
0x180003685  call    _CRT_INIT
0x18000368a  mov     ebx, eax
0x18000368c  mov     [rsp+108h+var_E8], eax
0x180003690  jmp     short loc_1800036A7
0x180003692  xor     ebx, ebx
0x180003694  mov     [rsp+108h+var_E8], ebx
0x180003698  mov     edi, [rsp+108h+arg_8]
0x18000369f  mov     rsi, [rsp+108h+arg_0]
0x1800036a7  mov     rax, cs:_pRawDllMain
0x1800036ae  test    rax, rax
0x1800036b1  jz      short loc_1800036E4
0x1800036b3  cmp     cs:dword_1800142C4, 0
0x1800036ba  jz      short loc_1800036E4
0x1800036bc  mov     r8, [rsp+108h+lpvReserved]
0x1800036c4  mov     edx, edi
0x1800036c6  mov     rcx, rsi
0x1800036c9  call    cs:__guard_dispatch_icall_fptr
0x1800036cf  mov     ebx, eax
0x1800036d1  mov     [rsp+108h+var_E8], eax
0x1800036d5  jmp     short loc_1800036E4
0x1800036d7  xor     ebx, ebx
0x1800036d9  mov     [rsp+108h+var_E8], ebx
0x1800036dd  mov     edi, [rsp+108h+arg_8]
0x1800036e4  cmp     edi, 1
0x1800036e7  ja      short loc_1800036F3
0x1800036e9  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x1800036f3  mov     eax, ebx
0x1800036f5  add     rsp, 0F0h
0x1800036fc  pop     rdi
0x1800036fd  pop     rsi
0x1800036fe  pop     rbx
0x1800036ff  retn
0x18000d2d0  push    rbp
0x18000d2d2  sub     rsp, 20h
0x18000d2d6  mov     rbp, rdx
0x18000d2d9  mov     rax, [rcx]
0x18000d2dc  mov     edx, [rax]
0x18000d2de  mov     [rbp+0A8h], rcx
0x18000d2e5  mov     [rbp+28h], edx
0x18000d2e8  mov     eax, [rbp+28h]
0x18000d2eb  cmp     eax, 0E06D7363h
0x18000d2f0  jnz     short loc_18000D306
0x18000d2f2  mov     rdx, [rbp+0A8h]
0x18000d2f9  mov     ecx, [rbp+28h]
0x18000d2fc  call    _XcptFilter_0
0x18000d301  mov     [rbp+30h], eax
0x18000d304  jmp     short loc_18000D30D
0x18000d306  mov     dword ptr [rbp+30h], 0
0x18000d30d  mov     eax, [rbp+30h]
0x18000d310  add     rsp, 20h
0x18000d314  pop     rbp
0x18000d315  retn
0x18000d317  push    rbp
0x18000d319  sub     rsp, 20h
0x18000d31d  mov     rbp, rdx
0x18000d320  mov     rax, [rcx]
0x18000d323  mov     edx, [rax]
0x18000d325  mov     [rbp+0B0h], rcx
0x18000d32c  mov     [rbp+38h], edx
0x18000d32f  mov     eax, [rbp+38h]
0x18000d332  cmp     eax, 0E06D7363h
0x18000d337  jnz     short loc_18000D34D
0x18000d339  mov     rdx, [rbp+0B0h]
0x18000d340  mov     ecx, [rbp+38h]
0x18000d343  call    _XcptFilter_0
0x18000d348  mov     [rbp+40h], eax
0x18000d34b  jmp     short loc_18000D354
0x18000d34d  mov     dword ptr [rbp+40h], 0
0x18000d354  mov     eax, [rbp+40h]
0x18000d357  add     rsp, 20h
0x18000d35b  pop     rbp
0x18000d35c  retn
0x18000d35e  push    rbp
0x18000d360  sub     rsp, 20h
0x18000d364  mov     rbp, rdx
0x18000d367  mov     rax, [rcx]
0x18000d36a  mov     edx, [rax]
0x18000d36c  mov     [rbp+0B8h], rcx
0x18000d373  mov     [rbp+48h], edx
0x18000d376  mov     eax, [rbp+48h]
0x18000d379  cmp     eax, 0E06D7363h
0x18000d37e  jnz     short loc_18000D394
0x18000d380  mov     rdx, [rbp+0B8h]
0x18000d387  mov     ecx, [rbp+48h]
0x18000d38a  call    _XcptFilter_0
0x18000d38f  mov     [rbp+50h], eax
0x18000d392  jmp     short loc_18000D39B
0x18000d394  mov     dword ptr [rbp+50h], 0
0x18000d39b  mov     eax, [rbp+50h]
0x18000d39e  add     rsp, 20h
0x18000d3a2  pop     rbp
0x18000d3a3  retn
0x18000d3a5  push    rbp
0x18000d3a7  sub     rsp, 20h
0x18000d3ab  mov     rbp, rdx
0x18000d3ae  mov     rax, [rcx]
0x18000d3b1  mov     edx, [rax]
0x18000d3b3  mov     [rbp+0C0h], rcx
0x18000d3ba  mov     [rbp+58h], edx
0x18000d3bd  mov     eax, [rbp+58h]
0x18000d3c0  cmp     eax, 0E06D7363h
0x18000d3c5  jnz     short loc_18000D3DB
0x18000d3c7  mov     rdx, [rbp+0C0h]
0x18000d3ce  mov     ecx, [rbp+58h]
0x18000d3d1  call    _XcptFilter_0
0x18000d3d6  mov     [rbp+60h], eax
0x18000d3d9  jmp     short loc_18000D3E2
0x18000d3db  mov     dword ptr [rbp+60h], 0
0x18000d3e2  mov     eax, [rbp+60h]
0x18000d3e5  add     rsp, 20h
0x18000d3e9  pop     rbp
0x18000d3ea  retn
0x18000d3ec  push    rbp
0x18000d3ee  sub     rsp, 20h
0x18000d3f2  mov     rbp, rdx
0x18000d3f5  mov     rax, [rcx]
0x18000d3f8  mov     edx, [rax]
0x18000d3fa  mov     [rbp+0C8h], rcx
0x18000d401  mov     [rbp+68h], edx
0x18000d404  mov     eax, [rbp+68h]
0x18000d407  cmp     eax, 0E06D7363h
0x18000d40c  jnz     short loc_18000D422
0x18000d40e  mov     rdx, [rbp+0C8h]
0x18000d415  mov     ecx, [rbp+68h]
0x18000d418  call    _XcptFilter_0
0x18000d41d  mov     [rbp+70h], eax
0x18000d420  jmp     short loc_18000D429
0x18000d422  mov     dword ptr [rbp+70h], 0
0x18000d429  mov     eax, [rbp+70h]
0x18000d42c  add     rsp, 20h
0x18000d430  pop     rbp
0x18000d431  retn
0x18000d433  push    rbp
0x18000d435  sub     rsp, 20h
0x18000d439  mov     rbp, rdx
0x18000d43c  mov     rax, [rcx]
0x18000d43f  mov     edx, [rax]
0x18000d441  mov     [rbp+0D0h], rcx
0x18000d448  mov     [rbp+78h], edx
0x18000d44b  mov     eax, [rbp+78h]
0x18000d44e  cmp     eax, 0E06D7363h
0x18000d453  jnz     short loc_18000D46C
0x18000d455  mov     rdx, [rbp+0D0h]
0x18000d45c  mov     ecx, [rbp+78h]
0x18000d45f  call    _XcptFilter_0
0x18000d464  mov     [rbp+80h], eax
0x18000d46a  jmp     short loc_18000D476
0x18000d46c  mov     dword ptr [rbp+80h], 0
0x18000d476  mov     eax, [rbp+80h]
0x18000d47c  add     rsp, 20h
0x18000d480  pop     rbp
0x18000d481  retn
0x18000d483  push    rbp
0x18000d485  sub     rsp, 20h
0x18000d489  mov     rbp, rdx
0x18000d48c  mov     rax, [rcx]
0x18000d48f  mov     edx, [rax]
0x18000d491  mov     [rbp+0D8h], rcx
0x18000d498  mov     [rbp+88h], edx
0x18000d49e  mov     eax, [rbp+88h]
0x18000d4a4  cmp     eax, 0E06D7363h
0x18000d4a9  jnz     short loc_18000D4C5
0x18000d4ab  mov     rdx, [rbp+0D8h]
0x18000d4b2  mov     ecx, [rbp+88h]
0x18000d4b8  call    _XcptFilter_0
0x18000d4bd  mov     [rbp+90h], eax
0x18000d4c3  jmp     short loc_18000D4CF
0x18000d4c5  mov     dword ptr [rbp+90h], 0
0x18000d4cf  mov     eax, [rbp+90h]
0x18000d4d5  add     rsp, 20h
0x18000d4d9  pop     rbp
0x18000d4da  retn
0x18000d4dc  push    rbp
0x18000d4de  sub     rsp, 20h
0x18000d4e2  mov     rbp, rdx
0x18000d4e5  mov     rax, [rcx]
0x18000d4e8  mov     edx, [rax]
0x18000d4ea  mov     [rbp+0E0h], rcx
0x18000d4f1  mov     [rbp+98h], edx
0x18000d4f7  mov     eax, [rbp+98h]
0x18000d4fd  cmp     eax, 0E06D7363h
0x18000d502  jnz     short loc_18000D51E
0x18000d504  mov     rdx, [rbp+0E0h]
0x18000d50b  mov     ecx, [rbp+98h]
0x18000d511  call    _XcptFilter_0
0x18000d516  mov     [rbp+0A0h], eax
0x18000d51c  jmp     short loc_18000D528
0x18000d51e  mov     dword ptr [rbp+0A0h], 0
0x18000d528  mov     eax, [rbp+0A0h]
0x18000d52e  add     rsp, 20h
0x18000d532  pop     rbp
0x18000d533  retn
0x18000d535  push    rbp
0x18000d537  sub     rsp, 20h
0x18000d53b  mov     rbp, rdx
0x18000d53e  cmp     dword ptr [rbp+118h], 1
0x18000d545  ja      short loc_18000D551
0x18000d547  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
