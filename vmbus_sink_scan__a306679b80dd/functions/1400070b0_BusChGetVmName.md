# BusChGetVmName

- ea: `0x1400070b0`
- end: `0x140007139`
- name: `BusChGetVmName`
- size: `137`
- prototype: `void __fastcall(__int64 *, struct _UNICODE_STRING *, unsigned __int16 *, _OWORD *)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1400070b0`

## import_xrefs

- `ntoskrnl!RtlCopyUnicodeString` at `0x140007106`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140007106`

## pseudocode

```c
void __fastcall BusChGetVmName(__int64 *a1, struct _UNICODE_STRING *a2, unsigned __int16 *a3, _OWORD *a4)
{
  __int64 v4; // rax
  __int64 v7; // rcx
  __int128 v8; // xmm6
  UNICODE_STRING SourceString; // [rsp+20h] [rbp-28h] BYREF

  v4 = *a1;
  SourceString = 0;
  v7 = *(_QWORD *)(v4 + 216);
  SourceString = *(UNICODE_STRING *)(v7 + 144);
  v8 = *(_OWORD *)(v7 + 128);
  if ( a2 && a2->MaximumLength >= SourceString.Length )
    RtlCopyUnicodeString(a2, &SourceString);
  if ( a3 )
    *a3 = SourceString.Length;
  if ( a4 )
    *a4 = v8;
}

```

## disassembly

```asm
0x1400070b0  mov     [rsp+arg_0], rbx
0x1400070b5  push    rdi
0x1400070b6  sub     rsp, 40h
0x1400070ba  mov     rax, [rcx]
0x1400070bd  xorps   xmm0, xmm0
0x1400070c0  movaps  [rsp+48h+var_18], xmm6
0x1400070c5  mov     rbx, r9
0x1400070c8  mov     rdi, r8
0x1400070cb  mov     r9, rdx
0x1400070ce  movups  xmmword ptr [rsp+48h+SourceString.Length], xmm0
0x1400070d3  mov     rcx, [rax+0D8h]
0x1400070da  movups  xmm0, xmmword ptr [rcx+90h]
0x1400070e1  movdqu  xmmword ptr [rsp+48h+SourceString.Length], xmm0
0x1400070e7  movups  xmm6, xmmword ptr [rcx+80h]
0x1400070ee  test    rdx, rdx
0x1400070f1  jz      short loc_140007112
0x1400070f3  movzx   eax, [rsp+48h+SourceString.Length]
0x1400070f8  cmp     [rdx+2], ax
0x1400070fc  jb      short loc_140007112
0x1400070fe  lea     rdx, [rsp+48h+SourceString]; SourceString
0x140007103  mov     rcx, r9; DestinationString
0x140007106  call    cs:__imp_RtlCopyUnicodeString
0x14000710d  nop     dword ptr [rax+rax+00h]
0x140007112  test    rdi, rdi
0x140007115  jz      short loc_14000711F
0x140007117  movzx   eax, [rsp+48h+SourceString.Length]
0x14000711c  mov     [rdi], ax
0x14000711f  test    rbx, rbx
0x140007122  jz      short loc_140007128
0x140007124  movdqu  xmmword ptr [rbx], xmm6
0x140007128  mov     rbx, [rsp+48h+arg_0]
0x14000712d  movaps  xmm6, [rsp+48h+var_18]
0x140007132  add     rsp, 40h
0x140007136  pop     rdi
0x140007137  retn
```
