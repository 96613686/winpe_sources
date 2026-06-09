# WcCopySourceList

- ea: `0x1400294b4`
- end: `0x140029601`
- name: `WcCopySourceList`
- size: `333`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x140014c90`

## callees

- `0x1400020c4`
- `0x1400294b4`
- `0x14002ad04`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400295dc`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400295dc`
- `ntoskrnl!ExAllocatePool2` at `0x140029503`
- `ntoskrnl!ExAllocatePool2` at `0x140029503`

## pseudocode

```c
__int64 __fastcall WcCopySourceList(__int64 ***a1, __int64 a2, __int64 a3)
{
  __int64 **v3; // rsi
  int v4; // edi
  __int64 Pool2; // rax
  _QWORD *v9; // rbx
  int v10; // edx
  _QWORD *v11; // rax
  UNICODE_STRING v13; // [rsp+40h] [rbp-48h] BYREF

  v3 = *a1;
  v4 = 0;
  *(_QWORD *)&v13.Length = 917504;
  v13.Buffer = L"::$DATA";
  while ( v3 != (__int64 **)a1 )
  {
    Pool2 = ExAllocatePool2(256, 40, 1702052695);
    v9 = (_QWORD *)Pool2;
    if ( !Pool2 )
      return (unsigned int)-1073741670;
    *(_QWORD *)(Pool2 + 16) = 0;
    v4 = WcOpenSourceFile(
           a2,
           v3[3][4],
           (struct _FLT_INSTANCE *)*v3[3],
           (void *)v3[3][1],
           &v13,
           0x21u,
           (_QWORD *)(Pool2 + 24));
    if ( v4 < 0 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v10) = 2;
        WPP_RECORDER_SF_sDd(
          WPP_GLOBAL_Control->DeviceExtension,
          v10,
          10,
          14,
          (__int64)WPP_950001495d7d34274b0ab8b7fcc7b560_Traceguids,
          (__int64)"onecore\\base\\fs\\wci\\wcifs\\context.c",
          17,
          v4,
          *(_QWORD *)&v13.Length,
          v13.Buffer);
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
    v3 = (__int64 **)*v3;
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1400294b4  push    rbx
0x1400294b6  push    rbp
0x1400294b7  push    rsi
0x1400294b8  push    rdi
0x1400294b9  push    r13
0x1400294bb  push    r14
0x1400294bd  push    r15
0x1400294bf  sub     rsp, 50h
0x1400294c3  mov     rsi, [rcx]
0x1400294c6  lea     rax, aData; "::$DATA"
0x1400294cd  xor     edi, edi
0x1400294cf  mov     [rsp+88h+var_48], 0E0000h
0x1400294d8  mov     rbp, r8
0x1400294db  mov     [rsp+88h+var_40], rax
0x1400294e0  mov     r15, rdx
0x1400294e3  mov     r14, rcx
0x1400294e6  lea     r13d, [rdi+0Eh]
0x1400294ea  cmp     rsi, r14
0x1400294ed  jz      loc_1400295EF
0x1400294f3  mov     edx, 28h ; '('
0x1400294f8  mov     ecx, 100h
0x1400294fd  mov     r8d, 65734357h
0x140029503  call    cs:__imp_ExAllocatePool2
0x14002950a  nop     dword ptr [rax+rax+00h]
0x14002950f  mov     rbx, rax
0x140029512  test    rax, rax
0x140029515  jz      loc_1400295EA
0x14002951b  mov     qword ptr [rax+10h], 0
0x140029523  mov     rcx, r15
0x140029526  mov     rdx, [rsi+18h]
0x14002952a  add     rax, 18h
0x14002952e  mov     [rsp+88h+var_58], rax
0x140029533  lea     rax, [rsp+88h+var_48]
0x140029538  mov     dword ptr [rsp+88h+var_60], 21h ; '!'
0x140029540  mov     [rsp+88h+var_68], rax
0x140029545  mov     r9, [rdx+8]
0x140029549  mov     r8, [rdx]
0x14002954c  mov     rdx, [rdx+20h]
0x140029550  call    WcOpenSourceFile
0x140029555  mov     edi, eax
0x140029557  test    eax, eax
0x140029559  js      short loc_140029585
0x14002955b  or      dword ptr [rbx+20h], 1
0x14002955f  mov     rax, [rbp+8]
0x140029563  cmp     [rax], rbp
0x140029566  jnz     short loc_14002957E
0x140029568  mov     [rbx], rbp
0x14002956b  mov     [rbx+8], rax
0x14002956f  mov     [rax], rbx
0x140029572  mov     [rbp+8], rbx
0x140029576  mov     rsi, [rsi]
0x140029579  jmp     loc_1400294EA
0x14002957e  mov     ecx, 3
0x140029583  int     29h; Win8: RtlFailFast(ecx)
0x140029585  lea     rax, WPP_RECORDER_INITIALIZED
0x14002958c  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140029593  jz      short loc_1400295D4
0x140029595  mov     rcx, cs:WPP_GLOBAL_Control
0x14002959c  lea     rax, aOnecoreBaseFsW_6; "onecore\\base\\fs\\wci\\wcifs\\context."...
0x1400295a3  mov     [rsp+88h+var_50], edi
0x1400295a7  mov     r9d, r13d
0x1400295aa  mov     dword ptr [rsp+88h+var_58], 311h
0x1400295b2  mov     r8d, 0Ah
0x1400295b8  mov     [rsp+88h+var_60], rax
0x1400295bd  mov     dl, 2
0x1400295bf  mov     rcx, [rcx+40h]
0x1400295c3  lea     rax, WPP_950001495d7d34274b0ab8b7fcc7b560_Traceguids
0x1400295ca  mov     [rsp+88h+var_68], rax
0x1400295cf  call    WPP_RECORDER_SF_sDd
0x1400295d4  mov     edx, 65734357h; Tag
0x1400295d9  mov     rcx, rbx; P
0x1400295dc  call    cs:__imp_ExFreePoolWithTag
0x1400295e3  nop     dword ptr [rax+rax+00h]
0x1400295e8  jmp     short loc_1400295EF
0x1400295ea  mov     edi, 0C000009Ah
0x1400295ef  mov     eax, edi
0x1400295f1  add     rsp, 50h
0x1400295f5  pop     r15
0x1400295f7  pop     r14
0x1400295f9  pop     r13
0x1400295fb  pop     rdi
0x1400295fc  pop     rsi
0x1400295fd  pop     rbp
0x1400295fe  pop     rbx
0x1400295ff  retn
```
