# UdfValidateAndRemoveStreamSuffix

- ea: `0x14002fac4`
- end: `0x14002fbd2`
- name: `UdfValidateAndRemoveStreamSuffix`
- size: `270`
- prototype: `SIZE_T __fastcall(__int64, _WORD *, UNICODE_STRING *)`
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140034450`
- `0x140042c40`
- `0x140044950`

## callees

- `0x14000cad4`
- `0x140013688`
- `0x14002fac4`

## import_xrefs

- `ntoskrnl!ExRaiseStatus` at `0x14002fbc5`
- `ntoskrnl!ExRaiseStatus` at `0x14002fbc5`
- `ntoskrnl!RtlUpcaseUnicodeString` at `0x14002fb3e`
- `ntoskrnl!RtlUpcaseUnicodeString` at `0x14002fb3e`
- `ntoskrnl!RtlCompareMemory` at `0x14002fb67`
- `ntoskrnl!RtlCompareMemory` at `0x14002fb67`

## pseudocode

```c
SIZE_T __fastcall UdfValidateAndRemoveStreamSuffix(__int64 a1, _WORD *a2, UNICODE_STRING *a3)
{
  SIZE_T result; // rax
  int v6; // esi
  int v7; // edx
  int v8; // r8d
  SIZE_T Length; // rbx

  result = *(_QWORD *)(a1 + 16);
  v6 = (int)a2;
  if ( *(_WORD *)(result + 2136) != 10 )
  {
    if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x4000) != 0 )
    {
      WPP_SF_(*(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL), 14, WPP_9347fa571a1230f8ec97dda486d24b3c_Traceguids);
    }
    goto LABEL_14;
  }
  if ( a3->Length )
  {
    RtlUpcaseUnicodeString(a3, a3, 0);
    if ( UdfStreamTypeNames != a3->Length
      || (Length = a3->Length, result = RtlCompareMemory(Source1, a3->Buffer, Length), Length != result) )
    {
      if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x4000) != 0 )
      {
        WPP_SF_ZZ(*(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL), v7, v8, v6, (__int64)a3);
      }
LABEL_14:
      *(_DWORD *)(a1 + 24) = -1073741773;
      ExRaiseStatus(-1073741773);
    }
    a3->Length = 0;
  }
  else if ( !*a2 )
  {
    goto LABEL_14;
  }
  return result;
}

```

## disassembly

```asm
0x14002fac4  push    rbx
0x14002fac6  push    rbp
0x14002fac7  push    rsi
0x14002fac8  push    rdi
0x14002fac9  push    r14
0x14002facb  sub     rsp, 30h
0x14002facf  mov     rax, [rcx+10h]
0x14002fad3  mov     rbp, rcx
0x14002fad6  mov     ecx, 0Ah
0x14002fadb  mov     rdi, r8
0x14002fade  mov     rsi, rdx
0x14002fae1  cmp     cx, [rax+858h]
0x14002fae8  jz      short loc_14002FB28
0x14002faea  mov     rcx, cs:WPP_GLOBAL_Control
0x14002faf1  lea     rax, WPP_GLOBAL_Control
0x14002faf8  cmp     rcx, rax
0x14002fafb  jz      loc_14002FBBD
0x14002fb01  test    dword ptr [rcx+2Ch], 4000h
0x14002fb08  jz      loc_14002FBBD
0x14002fb0e  mov     rcx, [rcx+18h]
0x14002fb12  lea     r8, WPP_9347fa571a1230f8ec97dda486d24b3c_Traceguids
0x14002fb19  mov     edx, 0Eh
0x14002fb1e  call    WPP_SF_
0x14002fb23  jmp     loc_14002FBBD
0x14002fb28  xor     r14d, r14d
0x14002fb2b  cmp     [r8], r14w
0x14002fb2f  jz      loc_14002FBB7
0x14002fb35  xor     r8d, r8d; AllocateDestinationString
0x14002fb38  mov     rdx, rdi; SourceString
0x14002fb3b  mov     rcx, rdi; DestinationString
0x14002fb3e  call    cs:__imp_RtlUpcaseUnicodeString
0x14002fb45  nop     dword ptr [rax+rax+00h]
0x14002fb4a  movzx   eax, word ptr [rdi]
0x14002fb4d  cmp     cs:UdfStreamTypeNames, ax
0x14002fb54  jnz     short loc_14002FB88
0x14002fb56  mov     rdx, [rdi+8]; Source2
0x14002fb5a  mov     r8d, eax; Length
0x14002fb5d  mov     rcx, cs:Source1; Source1
0x14002fb64  movzx   ebx, word ptr [rdi]
0x14002fb67  call    cs:__imp_RtlCompareMemory
0x14002fb6e  nop     dword ptr [rax+rax+00h]
0x14002fb73  cmp     rbx, rax
0x14002fb76  jnz     short loc_14002FB88
0x14002fb78  mov     [rdi], r14w
0x14002fb7c  add     rsp, 30h
0x14002fb80  pop     r14
0x14002fb82  pop     rdi
0x14002fb83  pop     rsi
0x14002fb84  pop     rbp
0x14002fb85  pop     rbx
0x14002fb86  retn
0x14002fb88  mov     rcx, cs:WPP_GLOBAL_Control
0x14002fb8f  lea     rax, WPP_GLOBAL_Control
0x14002fb96  cmp     rcx, rax
0x14002fb99  jz      short loc_14002FBBD
0x14002fb9b  test    dword ptr [rcx+2Ch], 4000h
0x14002fba2  jz      short loc_14002FBBD
0x14002fba4  mov     rcx, [rcx+18h]
0x14002fba8  mov     r9, rsi
0x14002fbab  mov     [rsp+58h+var_38], rdi
0x14002fbb0  call    WPP_SF_ZZ
0x14002fbb5  jmp     short loc_14002FBBD
0x14002fbb7  cmp     [rdx], r14w
0x14002fbbb  jnz     short loc_14002FB7C
0x14002fbbd  mov     ecx, 0C0000033h; Status
0x14002fbc2  mov     [rbp+18h], ecx
0x14002fbc5  call    cs:__imp_ExRaiseStatus
```
