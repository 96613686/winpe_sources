# WsFindLocal

- ea: `0x180008b50`
- end: `0x180008c33`
- name: `WsFindLocal`
- size: `227`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180001750`
- `0x1800089ac`
- `0x18002be90`

## callees

- `0x180008b50`

## import_xrefs

- `ntdll!RtlCompareUnicodeString` at `0x180008bfc`
- `ntdll!RtlCompareUnicodeString` at `0x180008bfc`

## pseudocode

```c
LONG __fastcall WsFindLocal(_QWORD *a1, WCHAR *a2, _QWORD *a3, _QWORD *a4)
{
  _QWORD *i; // rdi
  WCHAR *v8; // r10
  __int64 v9; // rax
  __int64 v10; // rax
  LONG result; // eax
  UNICODE_STRING String2; // [rsp+20h] [rbp-48h] BYREF
  UNICODE_STRING String1; // [rsp+30h] [rbp-38h] BYREF

  *a4 = a1;
  for ( i = a1; i; i = (_QWORD *)*i )
  {
    v8 = (WCHAR *)i[2];
    if ( v8 )
    {
      String1 = 0;
      v9 = -1;
      String2 = 0;
      do
        ++v9;
      while ( v8[v9] );
      String1.Buffer = v8;
      String1.MaximumLength = 2 * (v9 + 1);
      String1.Length = String1.MaximumLength;
      v10 = -1;
      do
        ++v10;
      while ( a2[v10] );
      String2.Buffer = a2;
      String2.MaximumLength = 2 * (v10 + 1);
      String2.Length = String2.MaximumLength;
      result = RtlCompareUnicodeString(&String1, &String2, 1u);
      if ( !result )
      {
        *a3 = i;
        return result;
      }
    }
    *a4 = i;
  }
  result = 0;
  *a4 = 0;
  *a3 = 0;
  return result;
}

```

## disassembly

```asm
0x180008b50  push    rbx
0x180008b52  push    rsi
0x180008b53  push    rdi
0x180008b54  push    r14
0x180008b56  sub     rsp, 48h
0x180008b5a  mov     rsi, r9
0x180008b5d  mov     [r9], rcx
0x180008b60  mov     r14, r8
0x180008b63  mov     rbx, rdx
0x180008b66  mov     rdi, rcx
0x180008b69  nop     dword ptr [rax+00000000h]
0x180008b70  test    rdi, rdi
0x180008b73  jz      loc_180008C25
0x180008b79  mov     r10, [rdi+10h]
0x180008b7d  test    r10, r10
0x180008b80  jz      loc_180008C0C
0x180008b86  xorps   xmm0, xmm0
0x180008b89  xorps   xmm1, xmm1
0x180008b8c  movups  xmmword ptr [rsp+68h+String1.Length], xmm0
0x180008b91  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180008b98  movups  xmmword ptr [rsp+68h+String2.Length], xmm1
0x180008b9d  nop     dword ptr [rax]
0x180008ba0  inc     rax
0x180008ba3  cmp     word ptr [r10+rax*2], 0
0x180008ba9  jnz     short loc_180008BA0
0x180008bab  inc     ax
0x180008bae  mov     [rsp+68h+String1.Buffer], r10
0x180008bb3  add     ax, ax
0x180008bb6  mov     [rsp+68h+String1.MaximumLength], ax
0x180008bbb  mov     [rsp+68h+String1.Length], ax
0x180008bc0  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180008bc7  nop     word ptr [rax+rax+00000000h]
0x180008bd0  inc     rax
0x180008bd3  cmp     word ptr [rbx+rax*2], 0
0x180008bd8  jnz     short loc_180008BD0
0x180008bda  inc     ax
0x180008bdd  mov     [rsp+68h+String2.Buffer], rbx
0x180008be2  add     ax, ax
0x180008be5  lea     rdx, [rsp+68h+String2]; String2
0x180008bea  mov     r8b, 1; CaseInsensitive
0x180008bed  mov     [rsp+68h+String2.MaximumLength], ax
0x180008bf2  lea     rcx, [rsp+68h+String1]; String1
0x180008bf7  mov     [rsp+68h+String2.Length], ax
0x180008bfc  call    cs:__imp_RtlCompareUnicodeString
0x180008c03  nop     dword ptr [rax+rax+00h]
0x180008c08  test    eax, eax
0x180008c0a  jz      short loc_180008C17
0x180008c0c  mov     [rsi], rdi
0x180008c0f  mov     rdi, [rdi]
0x180008c12  jmp     loc_180008B70
0x180008c17  mov     [r14], rdi
0x180008c1a  add     rsp, 48h
0x180008c1e  pop     r14
0x180008c20  pop     rdi
0x180008c21  pop     rsi
0x180008c22  pop     rbx
0x180008c23  retn
0x180008c25  xor     eax, eax
0x180008c27  mov     qword ptr [rsi], 0
0x180008c2e  mov     [r14], rax
0x180008c31  jmp     short loc_180008C1A
```
