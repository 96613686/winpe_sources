# WcCopySourceList

- ea: `0x140029504`
- end: `0x140029651`
- name: `WcCopySourceList`
- size: `333`
- prototype: `__int64 __fastcall(_QWORD *, __int64, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x140014c90`

## callees

- `0x1400020c4`
- `0x140029504`
- `0x14002ad54`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14002962c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002962c`
- `ntoskrnl!ExAllocatePool2` at `0x140029553`
- `ntoskrnl!ExAllocatePool2` at `0x140029553`

## pseudocode

```c
__int64 __fastcall WcCopySourceList(_QWORD *a1, __int64 a2, __int64 a3)
{
  _QWORD *v3; // rsi
  int v4; // edi
  __int64 Pool2; // rax
  _QWORD *v9; // rbx
  int v10; // edx
  _QWORD *v11; // rax
  _QWORD v13[9]; // [rsp+40h] [rbp-48h] BYREF

  v3 = (_QWORD *)*a1;
  v4 = 0;
  v13[0] = 917504;
  v13[1] = L"::$DATA";
  while ( v3 != a1 )
  {
    Pool2 = ExAllocatePool2(256, 40, 1702052695);
    v9 = (_QWORD *)Pool2;
    if ( !Pool2 )
      return (unsigned int)-1073741670;
    *(_QWORD *)(Pool2 + 16) = 0;
    v4 = WcOpenSourceFile(
           a2,
           *(_QWORD *)(v3[3] + 32LL),
           *(_QWORD *)v3[3],
           *(_QWORD *)(v3[3] + 8LL),
           v13,
           33,
           Pool2 + 24);
    if ( v4 < 0 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v10) = 2;
        WPP_RECORDER_SF_sDd(
          wil_details_featureDescriptors_a->DeviceExtension,
          v10,
          10,
          14,
          (__int64)WPP_950001495d7d34274b0ab8b7fcc7b560_Traceguids,
          (__int64)"onecore\\base\\fs\\wci\\wcifs\\context.c",
          17,
          v4);
      }
      ExFreePoolWithTag(v9, 0x65734357u);
      return (unsigned int)v4;
    }
    *((_DWORD *)v9 + 8) |= 1u;
    v11 = *(_QWORD **)(a3 + 8);
    if ( *v11 != a3 )
      __fastfail(3u);
    *v9 = a3;
    v9[1] = v11;
    *v11 = v9;
    *(_QWORD *)(a3 + 8) = v9;
    v3 = (_QWORD *)*v3;
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x140029504  push    rbx
0x140029506  push    rbp
0x140029507  push    rsi
0x140029508  push    rdi
0x140029509  push    r13
0x14002950b  push    r14
0x14002950d  push    r15
0x14002950f  sub     rsp, 50h
0x140029513  mov     rsi, [rcx]
0x140029516  lea     rax, aData; "::$DATA"
0x14002951d  xor     edi, edi
0x14002951f  mov     [rsp+88h+var_48], 0E0000h
0x140029528  mov     rbp, r8
0x14002952b  mov     [rsp+88h+var_40], rax
0x140029530  mov     r15, rdx
0x140029533  mov     r14, rcx
0x140029536  lea     r13d, [rdi+0Eh]
0x14002953a  cmp     rsi, r14
0x14002953d  jz      loc_14002963F
0x140029543  mov     edx, 28h ; '('
0x140029548  mov     ecx, 100h
0x14002954d  mov     r8d, 65734357h
0x140029553  call    cs:__imp_ExAllocatePool2
0x14002955a  nop     dword ptr [rax+rax+00h]
0x14002955f  mov     rbx, rax
0x140029562  test    rax, rax
0x140029565  jz      loc_14002963A
0x14002956b  mov     qword ptr [rax+10h], 0
0x140029573  mov     rcx, r15
0x140029576  mov     rdx, [rsi+18h]
0x14002957a  add     rax, 18h
0x14002957e  mov     [rsp+88h+var_58], rax
0x140029583  lea     rax, [rsp+88h+var_48]
0x140029588  mov     dword ptr [rsp+88h+var_60], 21h ; '!'
0x140029590  mov     [rsp+88h+var_68], rax
0x140029595  mov     r9, [rdx+8]
0x140029599  mov     r8, [rdx]
0x14002959c  mov     rdx, [rdx+20h]
0x1400295a0  call    WcOpenSourceFile
0x1400295a5  mov     edi, eax
0x1400295a7  test    eax, eax
0x1400295a9  js      short loc_1400295D5
0x1400295ab  or      dword ptr [rbx+20h], 1
0x1400295af  mov     rax, [rbp+8]
0x1400295b3  cmp     [rax], rbp
0x1400295b6  jnz     short loc_1400295CE
0x1400295b8  mov     [rbx], rbp
0x1400295bb  mov     [rbx+8], rax
0x1400295bf  mov     [rax], rbx
0x1400295c2  mov     [rbp+8], rbx
0x1400295c6  mov     rsi, [rsi]
0x1400295c9  jmp     loc_14002953A
0x1400295ce  mov     ecx, 3
0x1400295d3  int     29h; Win8: RtlFailFast(ecx)
0x1400295d5  lea     rax, WPP_RECORDER_INITIALIZED
0x1400295dc  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400295e3  jz      short loc_140029624
0x1400295e5  mov     rcx, cs:wil_details_featureDescriptors_a
0x1400295ec  lea     rax, aOnecoreBaseFsW_6; "onecore\\base\\fs\\wci\\wcifs\\context."...
0x1400295f3  mov     [rsp+88h+var_50], edi
0x1400295f7  mov     r9d, r13d
0x1400295fa  mov     dword ptr [rsp+88h+var_58], 311h
0x140029602  mov     r8d, 0Ah
0x140029608  mov     [rsp+88h+var_60], rax
0x14002960d  mov     dl, 2
0x14002960f  mov     rcx, [rcx+40h]
0x140029613  lea     rax, WPP_950001495d7d34274b0ab8b7fcc7b560_Traceguids
0x14002961a  mov     [rsp+88h+var_68], rax
0x14002961f  call    WPP_RECORDER_SF_sDd
0x140029624  mov     edx, 65734357h; Tag
0x140029629  mov     rcx, rbx; P
0x14002962c  call    cs:__imp_ExFreePoolWithTag
0x140029633  nop     dword ptr [rax+rax+00h]
0x140029638  jmp     short loc_14002963F
0x14002963a  mov     edi, 0C000009Ah
0x14002963f  mov     eax, edi
0x140029641  add     rsp, 50h
0x140029645  pop     r15
0x140029647  pop     r14
0x140029649  pop     r13
0x14002964b  pop     rdi
0x14002964c  pop     rsi
0x14002964d  pop     rbp
0x14002964e  pop     rbx
0x14002964f  retn
```
