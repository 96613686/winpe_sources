# SIPolicyQuerySubVerBlock

- ea: `0x18004c07c`
- end: `0x18004c1ee`
- name: `SIPolicyQuerySubVerBlock`
- size: `370`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18002737c`

## callees

- `0x18004beb0`
- `0x18004c07c`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x18004c13f`
- `ntdll!RtlInitUnicodeString` at `0x18004c13f`
- `ntdll!RtlCompareUnicodeString` at `0x18004c168`
- `ntdll!RtlCompareUnicodeString` at `0x18004c168`

## pseudocode

```c
__int64 __fastcall SIPolicyQuerySubVerBlock(unsigned __int16 *a1, WCHAR *a2, _QWORD *a3, _QWORD *a4)
{
  unsigned __int16 *v7; // rbx
  unsigned int v8; // r14d
  unsigned __int16 *v9; // rsi
  WCHAR *v10; // r15
  int v11; // ebp
  __int64 v12; // rax
  __int64 v13; // rax
  UNICODE_STRING String1; // [rsp+20h] [rbp-68h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-58h] BYREF

  v7 = a1;
  v8 = -1073741275;
  String1 = 0;
  DestinationString = 0;
  if ( !a1[2] && (unsigned __int16)(*a1 - 8) <= 0x7FF8u && (*(_BYTE *)a1 & 1) == 0 )
  {
LABEL_6:
    while ( *a2 == 92 )
      ++a2;
    v9 = (unsigned __int16 *)SIPolicyCheckVerBlock(v7, *v7);
    if ( v9 )
    {
      if ( *a2 )
      {
        v10 = a2;
        do
        {
          if ( *a2 == 92 )
            break;
          ++a2;
        }
        while ( *a2 );
        v11 = (_DWORD)v7 + *v7;
        while ( SIPolicyCheckVerBlock(v9, (unsigned int)(v11 - (_DWORD)v9)) )
        {
          RtlInitUnicodeString(&DestinationString, v9 + 3);
          String1.Buffer = v10;
          String1.Length = (_WORD)a2 - (_WORD)v10;
          String1.MaximumLength = (_WORD)a2 - (_WORD)v10;
          if ( !RtlCompareUnicodeString(&String1, &DestinationString, 1u) )
          {
            v7 = v9;
            goto LABEL_6;
          }
          v9 = (unsigned __int16 *)((char *)v9 + ((*v9 + 3LL) & 0xFFFFFFFFFFFFFFFCuLL));
        }
      }
      else
      {
        *a4 = v7[1];
        v12 = -1;
        do
          ++v12;
        while ( v7[v12 + 3] );
        if ( v7[1] && *(_DWORD *)(v7 + 1) >= 2u )
          v13 = (2 * (_DWORD)v12 + 11) & 0xFFFFFFFC;
        else
          v13 = 2LL * (unsigned int)v12 + 6;
        v8 = 0;
        *a3 = (char *)v7 + v13;
      }
    }
  }
  return v8;
}

```

## disassembly

```asm
0x18004c07c  push    rbx
0x18004c07e  push    rbp
0x18004c07f  push    rsi
0x18004c080  push    rdi
0x18004c081  push    r12
0x18004c083  push    r13
0x18004c085  push    r14
0x18004c087  push    r15
0x18004c089  sub     rsp, 48h
0x18004c08d  xor     ebp, ebp
0x18004c08f  xorps   xmm0, xmm0
0x18004c092  xorps   xmm1, xmm1
0x18004c095  mov     r12, r9
0x18004c098  mov     r13, r8
0x18004c09b  mov     rdi, rdx
0x18004c09e  mov     rbx, rcx
0x18004c0a1  mov     r14d, 0C0000225h
0x18004c0a7  movups  xmmword ptr [rsp+88h+String1.Length], xmm0
0x18004c0ac  movups  xmmword ptr [rsp+88h+DestinationString.Length], xmm1
0x18004c0b1  cmp     [rcx+4], bp
0x18004c0b5  jnz     loc_18004C1DA
0x18004c0bb  movzx   eax, word ptr [rcx]
0x18004c0be  mov     ecx, 7FF8h
0x18004c0c3  sub     ax, 8
0x18004c0c7  cmp     ax, cx
0x18004c0ca  ja      loc_18004C1DA
0x18004c0d0  test    byte ptr [rbx], 1
0x18004c0d3  jnz     loc_18004C1DA
0x18004c0d9  mov     r15d, 2
0x18004c0df  jmp     short loc_18004C0E4
0x18004c0e1  add     rdi, r15
0x18004c0e4  cmp     word ptr [rdi], 5Ch ; '\'
0x18004c0e8  jz      short loc_18004C0E1
0x18004c0ea  movzx   edx, word ptr [rbx]
0x18004c0ed  mov     rcx, rbx
0x18004c0f0  call    SIPolicyCheckVerBlock
0x18004c0f5  mov     rsi, rax
0x18004c0f8  test    rax, rax
0x18004c0fb  jz      loc_18004C1DA
0x18004c101  cmp     [rdi], bp
0x18004c104  jz      loc_18004C18C
0x18004c10a  mov     r15, rdi
0x18004c10d  cmp     word ptr [rdi], 5Ch ; '\'
0x18004c111  jz      short loc_18004C11C
0x18004c113  add     rdi, 2
0x18004c117  cmp     [rdi], bp
0x18004c11a  jnz     short loc_18004C10D
0x18004c11c  movzx   ebp, word ptr [rbx]
0x18004c11f  add     ebp, ebx
0x18004c121  mov     edx, ebp
0x18004c123  mov     rcx, rsi
0x18004c126  sub     edx, esi
0x18004c128  call    SIPolicyCheckVerBlock
0x18004c12d  test    rax, rax
0x18004c130  jz      loc_18004C1DA
0x18004c136  lea     rdx, [rsi+6]; SourceString
0x18004c13a  lea     rcx, [rsp+88h+DestinationString]; DestinationString
0x18004c13f  call    cs:__imp_RtlInitUnicodeString
0x18004c145  movzx   eax, di
0x18004c148  mov     [rsp+88h+String1.Buffer], r15
0x18004c14d  sub     ax, r15w
0x18004c151  lea     rdx, [rsp+88h+DestinationString]; String2
0x18004c156  mov     r8b, 1; CaseInsensitive
0x18004c159  mov     [rsp+88h+String1.Length], ax
0x18004c15e  lea     rcx, [rsp+88h+String1]; String1
0x18004c163  mov     [rsp+88h+String1.MaximumLength], ax
0x18004c168  call    cs:__imp_RtlCompareUnicodeString
0x18004c16e  test    eax, eax
0x18004c170  jz      short loc_18004C182
0x18004c172  movzx   eax, word ptr [rsi]
0x18004c175  add     rax, 3
0x18004c179  and     rax, 0FFFFFFFFFFFFFFFCh
0x18004c17d  add     rsi, rax
0x18004c180  jmp     short loc_18004C121
0x18004c182  mov     rbx, rsi
0x18004c185  xor     ebp, ebp
0x18004c187  jmp     loc_18004C0D9
0x18004c18c  movzx   eax, word ptr [rbx+2]
0x18004c190  mov     [r12], rax
0x18004c194  or      rax, 0FFFFFFFFFFFFFFFFh
0x18004c198  inc     rax
0x18004c19b  cmp     [rbx+rax*2+6], bp
0x18004c1a0  jnz     short loc_18004C198
0x18004c1a2  cmp     [rbx+2], bp
0x18004c1a6  jz      short loc_18004C1C6
0x18004c1a8  cmp     [rbx+4], bp
0x18004c1ac  jnz     short loc_18004C1B5
0x18004c1ae  cmp     [rbx+2], r15w
0x18004c1b3  jb      short loc_18004C1C6
0x18004c1b5  lea     eax, ds:0Bh[rax*2]
0x18004c1bc  mov     ecx, 0FFFFFFFCh
0x18004c1c1  and     rax, rcx
0x18004c1c4  jmp     short loc_18004C1D0
0x18004c1c6  mov     eax, eax
0x18004c1c8  lea     rax, ds:6[rax*2]
0x18004c1d0  add     rax, rbx
0x18004c1d3  mov     r14d, ebp
0x18004c1d6  mov     [r13+0], rax
0x18004c1da  mov     eax, r14d
0x18004c1dd  add     rsp, 48h
0x18004c1e1  pop     r15
0x18004c1e3  pop     r14
0x18004c1e5  pop     r13
0x18004c1e7  pop     r12
0x18004c1e9  pop     rdi
0x18004c1ea  pop     rsi
0x18004c1eb  pop     rbp
0x18004c1ec  pop     rbx
0x18004c1ed  retn
```
