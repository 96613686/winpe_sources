# SIPolicyQuerySubVerBlock

- ea: `0x18001e010`
- end: `0x18001e1ce`
- name: `SIPolicyQuerySubVerBlock`
- size: `446`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180013a24`

## callees

- `0x180006d30`
- `0x18001e010`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x18001e0ee`
- `ntdll!RtlInitUnicodeString` at `0x18001e0ee`
- `ntdll!RtlCompareUnicodeString` at `0x18001e117`
- `ntdll!RtlCompareUnicodeString` at `0x18001e117`

## pseudocode

```c
__int64 __fastcall SIPolicyQuerySubVerBlock(unsigned __int16 *a1, WCHAR *a2, _QWORD *a3, _QWORD *a4)
{
  bool v4; // zf
  unsigned __int16 *v8; // rsi
  unsigned __int16 v9; // cx
  unsigned __int16 *v10; // rdi
  WCHAR *v11; // r14
  int v12; // ebp
  __int64 v13; // rax
  unsigned __int16 v14; // cx
  __int64 v15; // rax
  UNICODE_STRING String1; // [rsp+20h] [rbp-38h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-28h] BYREF

  v4 = a1[2] == 0;
  String1 = 0;
  DestinationString = 0;
  v8 = a1;
  if ( !v4 )
    return 3221226021LL;
  v9 = *a1;
  if ( (unsigned __int16)(v9 - 8) > 0x7FF8u || (v9 & 1) != 0 )
    return 3221226021LL;
LABEL_4:
  while ( *a2 == 92 )
    ++a2;
  v10 = (unsigned __int16 *)SIPolicyCheckVerBlock(v8, *v8);
  if ( !v10 )
    return 3221226021LL;
  if ( *a2 )
  {
    v11 = a2;
    do
    {
      if ( *a2 == 92 )
        break;
      ++a2;
    }
    while ( *a2 );
    v12 = (_DWORD)v8 + *v8;
    while ( SIPolicyCheckVerBlock(v10, (unsigned int)(v12 - (_DWORD)v10)) )
    {
      RtlInitUnicodeString(&DestinationString, v10 + 3);
      String1.Buffer = v11;
      String1.Length = (_WORD)a2 - (_WORD)v11;
      String1.MaximumLength = (_WORD)a2 - (_WORD)v11;
      if ( !RtlCompareUnicodeString(&String1, &DestinationString, 1u) )
      {
        v8 = v10;
        goto LABEL_4;
      }
      v10 = (unsigned __int16 *)((char *)v10 + ((*v10 + 3LL) & 0xFFFFFFFFFFFFFFFCuLL));
    }
    return 3221226021LL;
  }
  *a4 = v8[1];
  v13 = -1;
  do
    ++v13;
  while ( v8[v13 + 3] );
  v14 = v8[1];
  if ( v14 && (v8[2] || v14 >= 2u) )
    v15 = (2 * (_DWORD)v13 + 11) & 0xFFFFFFFC;
  else
    v15 = 2LL * (unsigned int)v13 + 6;
  *a3 = (char *)v8 + v15;
  return 0;
}

```

## disassembly

```asm
0x18001e010  mov     [rsp+arg_18], rbx
0x18001e015  push    rsi
0x18001e016  push    r12
0x18001e018  push    r15
0x18001e01a  sub     rsp, 40h
0x18001e01e  cmp     word ptr [rcx+4], 0
0x18001e023  xorps   xmm0, xmm0
0x18001e026  xorps   xmm1, xmm1
0x18001e029  mov     r15, r9
0x18001e02c  movups  xmmword ptr [rsp+58h+String1.Length], xmm0
0x18001e031  mov     r12, r8
0x18001e034  mov     rbx, rdx
0x18001e037  movups  xmmword ptr [rsp+58h+DestinationString.Length], xmm1
0x18001e03c  mov     rsi, rcx
0x18001e03f  jnz     loc_18001E1BA
0x18001e045  movzx   ecx, word ptr [rcx]
0x18001e048  mov     edx, 7FF8h
0x18001e04d  lea     eax, [rcx-8]
0x18001e050  cmp     ax, dx
0x18001e053  ja      loc_18001E1BA
0x18001e059  test    cl, 1
0x18001e05c  jnz     loc_18001E1BA
0x18001e062  mov     [rsp+58h+arg_0], rbp
0x18001e067  mov     [rsp+58h+arg_8], rdi
0x18001e06c  mov     [rsp+58h+arg_10], r14
0x18001e071  cmp     word ptr [rbx], 5Ch ; '\'
0x18001e075  jnz     short loc_18001E08A
0x18001e077  nop     word ptr [rax+rax+00000000h]
0x18001e080  add     rbx, 2
0x18001e084  cmp     word ptr [rbx], 5Ch ; '\'
0x18001e088  jz      short loc_18001E080
0x18001e08a  movzx   edx, word ptr [rsi]
0x18001e08d  mov     rcx, rsi
0x18001e090  call    SIPolicyCheckVerBlock
0x18001e095  mov     rdi, rax
0x18001e098  test    rax, rax
0x18001e09b  jz      loc_18001E1B3
0x18001e0a1  cmp     word ptr [rbx], 0
0x18001e0a5  jz      loc_18001E139
0x18001e0ab  mov     r14, rbx
0x18001e0ae  xchg    ax, ax
0x18001e0b0  cmp     word ptr [rbx], 5Ch ; '\'
0x18001e0b4  jz      short loc_18001E0C0
0x18001e0b6  add     rbx, 2
0x18001e0ba  cmp     word ptr [rbx], 0
0x18001e0be  jnz     short loc_18001E0B0
0x18001e0c0  movzx   ebp, word ptr [rsi]
0x18001e0c3  add     ebp, esi
0x18001e0c5  nop     word ptr [rax+rax+00000000h]
0x18001e0d0  mov     edx, ebp
0x18001e0d2  mov     rcx, rdi
0x18001e0d5  sub     edx, edi
0x18001e0d7  call    SIPolicyCheckVerBlock
0x18001e0dc  test    rax, rax
0x18001e0df  jz      loc_18001E1B3
0x18001e0e5  lea     rdx, [rdi+6]; SourceString
0x18001e0e9  lea     rcx, [rsp+58h+DestinationString]; DestinationString
0x18001e0ee  call    cs:__imp_RtlInitUnicodeString
0x18001e0f4  movzx   eax, bx
0x18001e0f7  mov     [rsp+58h+String1.Buffer], r14
0x18001e0fc  sub     ax, r14w
0x18001e100  lea     rdx, [rsp+58h+DestinationString]; String2
0x18001e105  mov     r8b, 1; CaseInsensitive
0x18001e108  mov     [rsp+58h+String1.Length], ax
0x18001e10d  lea     rcx, [rsp+58h+String1]; String1
0x18001e112  mov     [rsp+58h+String1.MaximumLength], ax
0x18001e117  call    cs:__imp_RtlCompareUnicodeString
0x18001e11d  test    eax, eax
0x18001e11f  jz      short loc_18001E131
0x18001e121  movzx   eax, word ptr [rdi]
0x18001e124  add     rax, 3
0x18001e128  and     rax, 0FFFFFFFFFFFFFFFCh
0x18001e12c  add     rdi, rax
0x18001e12f  jmp     short loc_18001E0D0
0x18001e131  mov     rsi, rdi
0x18001e134  jmp     loc_18001E071
0x18001e139  movzx   eax, word ptr [rsi+2]
0x18001e13d  mov     [r15], rax
0x18001e140  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18001e147  nop     word ptr [rax+rax+00000000h]
0x18001e150  inc     rax
0x18001e153  cmp     word ptr [rsi+rax*2+6], 0
0x18001e159  jnz     short loc_18001E150
0x18001e15b  movzx   ecx, word ptr [rsi+2]
0x18001e15f  test    cx, cx
0x18001e162  jz      short loc_18001E182
0x18001e164  cmp     word ptr [rsi+4], 0
0x18001e169  jnz     short loc_18001E171
0x18001e16b  cmp     cx, 2
0x18001e16f  jb      short loc_18001E182
0x18001e171  lea     eax, ds:0Bh[rax*2]
0x18001e178  mov     ecx, 0FFFFFFFCh
0x18001e17d  and     rax, rcx
0x18001e180  jmp     short loc_18001E18C
0x18001e182  mov     eax, eax
0x18001e184  lea     rax, ds:6[rax*2]
0x18001e18c  add     rax, rsi
0x18001e18f  mov     [r12], rax
0x18001e193  xor     eax, eax
0x18001e195  mov     rdi, [rsp+58h+arg_8]
0x18001e19a  mov     rbp, [rsp+58h+arg_0]
0x18001e19f  mov     r14, [rsp+58h+arg_10]
0x18001e1a4  mov     rbx, [rsp+58h+arg_18]
0x18001e1a9  add     rsp, 40h
0x18001e1ad  pop     r15
0x18001e1af  pop     r12
0x18001e1b1  pop     rsi
0x18001e1b2  retn
0x18001e1b3  mov     eax, 0C0000225h
0x18001e1b8  jmp     short loc_18001E195
0x18001e1ba  mov     rbx, [rsp+58h+arg_18]
0x18001e1bf  mov     eax, 0C0000225h
0x18001e1c4  add     rsp, 40h
0x18001e1c8  pop     r15
0x18001e1ca  pop     r12
0x18001e1cc  pop     rsi
0x18001e1cd  retn
```
