# VMX_TOC_ENTRY::Unformat(uchar * *,ulong)

- ea: `0x140046ac4`
- end: `0x140046c7a`
- name: `?Unformat@VMX_TOC_ENTRY@@QEAAJPEAPEAEK@Z`
- size: `438`
- prototype: `__int64 __fastcall(VMX_TOC_ENTRY *__hidden this, unsigned __int8 **, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x140032930`

## callees

- `0x14001b896`
- `0x140046ac4`

## string_xrefs

- `0x140046bda`: `config`

## pseudocode

```c
__int64 __fastcall VMX_TOC_ENTRY::Unformat(VMX_TOC_ENTRY *this, unsigned __int8 **a2, unsigned int a3)
{
  __int64 v5; // rbx
  __int16 v6; // dx
  unsigned __int64 v7; // rsi
  __int64 v8; // r15
  unsigned __int8 *v9; // rbp
  char v10; // al
  unsigned __int16 v11; // cx
  char Str1[8]; // [rsp+20h] [rbp-38h] BYREF
  char v14; // [rsp+28h] [rbp-30h]

  if ( a3 >= 0x1C )
  {
    v5 = (__int64)*a2;
    v14 = 0;
    v6 = *(unsigned __int8 *)(v5 + 9);
    *(_QWORD *)Str1 = *(_QWORD *)v5;
    *((_WORD *)this + 17) = (*(unsigned __int8 *)(v5 + 8) << 8) | v6;
    *((_QWORD *)this + 5) = *(unsigned __int8 *)(v5 + 17)
                          | ((*(unsigned __int8 *)(v5 + 16)
                            | ((*(unsigned __int8 *)(v5 + 15)
                              | ((*(unsigned __int8 *)(v5 + 14)
                                | ((*(unsigned __int8 *)(v5 + 13)
                                  | ((*(unsigned __int8 *)(v5 + 12)
                                    | ((*(unsigned __int8 *)(v5 + 11)
                                      | ((unsigned __int64)*(unsigned __int8 *)(v5 + 10) << 8)) << 8)) << 8)) << 8)) << 8)) << 8)) << 8);
    v7 = *(unsigned __int8 *)(v5 + 25)
       | ((*(unsigned __int8 *)(v5 + 24)
         | ((*(unsigned __int8 *)(v5 + 23)
           | ((*(unsigned __int8 *)(v5 + 22)
             | ((*(unsigned __int8 *)(v5 + 21)
               | ((*(unsigned __int8 *)(v5 + 20)
                 | ((*(unsigned __int8 *)(v5 + 19) | ((unsigned __int64)*(unsigned __int8 *)(v5 + 18) << 8)) << 8)) << 8)) << 8)) << 8)) << 8)) << 8);
    *((_QWORD *)this + 6) = v7;
    v8 = _byteswap_ushort(*(_WORD *)(v5 + 26));
    v9 = (unsigned __int8 *)(v8 + v5 + 28);
    if ( (unsigned __int64)v9 <= v5 + (unsigned __int64)a3 )
    {
      if ( !strcmp_0(Str1, "config") )
      {
        v10 = 1;
      }
      else
      {
        if ( strcmp_0(Str1, "log") )
        {
          *((_BYTE *)this + 32) = 0;
          *a2 = v9;
          return 0;
        }
        v10 = 2;
      }
      *((_BYTE *)this + 32) = v10;
      if ( (_DWORD)v8 == 6 )
      {
        if ( v7 )
        {
          v11 = _byteswap_ushort(*(_WORD *)(v5 + 28));
          *((_WORD *)this + 28) = v11;
          if ( v11 )
          {
            *((_DWORD *)this + 15) = *(unsigned __int8 *)(v5 + 33)
                                   | ((*(unsigned __int8 *)(v5 + 32)
                                     | ((*(unsigned __int8 *)(v5 + 31) | (*(unsigned __int8 *)(v5 + 30) << 8)) << 8)) << 8);
            *a2 = (unsigned __int8 *)(v5 + 34);
            return 0;
          }
        }
      }
    }
  }
  return 3221225485LL;
}

```

## disassembly

```asm
0x140046ac4  mov     [rsp+arg_10], rbx
0x140046ac9  push    rbp
0x140046aca  push    rsi
0x140046acb  push    rdi
0x140046acc  push    r14
0x140046ace  push    r15
0x140046ad0  sub     rsp, 30h
0x140046ad4  mov     r14, rdx
0x140046ad7  mov     rdi, rcx
0x140046ada  cmp     r8d, 1Ch
0x140046ade  jb      loc_140046C63
0x140046ae4  mov     rbx, [rdx]
0x140046ae7  mov     [rsp+58h+var_30], 0
0x140046aec  mov     rax, [rbx]
0x140046aef  lea     rbp, [rbx+1Ch]
0x140046af3  movzx   edx, byte ptr [rbx+9]
0x140046af7  mov     qword ptr [rsp+58h+Str1], rax
0x140046afc  movzx   eax, byte ptr [rbx+8]
0x140046b00  shl     ax, 8
0x140046b04  or      dx, ax
0x140046b07  mov     [rcx+22h], dx
0x140046b0b  movzx   eax, byte ptr [rbx+0Bh]
0x140046b0f  movzx   ecx, byte ptr [rbx+0Ah]
0x140046b13  shl     rcx, 8
0x140046b17  or      rcx, rax
0x140046b1a  movzx   eax, byte ptr [rbx+0Ch]
0x140046b1e  shl     rcx, 8
0x140046b22  or      rcx, rax
0x140046b25  movzx   eax, byte ptr [rbx+0Dh]
0x140046b29  shl     rcx, 8
0x140046b2d  or      rcx, rax
0x140046b30  movzx   eax, byte ptr [rbx+0Eh]
0x140046b34  shl     rcx, 8
0x140046b38  or      rcx, rax
0x140046b3b  movzx   eax, byte ptr [rbx+0Fh]
0x140046b3f  shl     rcx, 8
0x140046b43  or      rcx, rax
0x140046b46  movzx   eax, byte ptr [rbx+10h]
0x140046b4a  shl     rcx, 8
0x140046b4e  or      rcx, rax
0x140046b51  movzx   eax, byte ptr [rbx+11h]
0x140046b55  shl     rcx, 8
0x140046b59  or      rcx, rax
0x140046b5c  mov     [rdi+28h], rcx
0x140046b60  movzx   eax, byte ptr [rbx+13h]
0x140046b64  movzx   esi, byte ptr [rbx+12h]
0x140046b68  shl     rsi, 8
0x140046b6c  or      rsi, rax
0x140046b6f  movzx   eax, byte ptr [rbx+14h]
0x140046b73  shl     rsi, 8
0x140046b77  or      rsi, rax
0x140046b7a  movzx   eax, byte ptr [rbx+15h]
0x140046b7e  shl     rsi, 8
0x140046b82  or      rsi, rax
0x140046b85  movzx   eax, byte ptr [rbx+16h]
0x140046b89  shl     rsi, 8
0x140046b8d  or      rsi, rax
0x140046b90  movzx   eax, byte ptr [rbx+17h]
0x140046b94  shl     rsi, 8
0x140046b98  or      rsi, rax
0x140046b9b  movzx   eax, byte ptr [rbx+18h]
0x140046b9f  shl     rsi, 8
0x140046ba3  or      rsi, rax
0x140046ba6  movzx   eax, byte ptr [rbx+19h]
0x140046baa  shl     rsi, 8
0x140046bae  or      rsi, rax
0x140046bb1  mov     [rdi+30h], rsi
0x140046bb5  movzx   eax, byte ptr [rbx+1Ah]
0x140046bb9  movzx   ecx, byte ptr [rbx+1Bh]
0x140046bbd  shl     ax, 8
0x140046bc1  or      cx, ax
0x140046bc4  mov     eax, r8d
0x140046bc7  movzx   r15d, cx
0x140046bcb  add     rax, rbx
0x140046bce  add     rbp, r15
0x140046bd1  cmp     rbp, rax
0x140046bd4  ja      loc_140046C63
0x140046bda  lea     rdx, aConfig; "config"
0x140046be1  lea     rcx, [rsp+58h+Str1]; Str1
0x140046be6  call    strcmp_0
0x140046beb  test    eax, eax
0x140046bed  jnz     short loc_140046BF3
0x140046bef  mov     al, 1
0x140046bf1  jmp     short loc_140046C0A
0x140046bf3  lea     rdx, aLog; "log"
0x140046bfa  lea     rcx, [rsp+58h+Str1]; Str1
0x140046bff  call    strcmp_0
0x140046c04  test    eax, eax
0x140046c06  jnz     short loc_140046C5A
0x140046c08  mov     al, 2
0x140046c0a  mov     [rdi+20h], al
0x140046c0d  cmp     r15d, 6
0x140046c11  jnz     short loc_140046C63
0x140046c13  test    rsi, rsi
0x140046c16  jz      short loc_140046C63
0x140046c18  movzx   ecx, byte ptr [rbx+1Ch]
0x140046c1c  movzx   eax, byte ptr [rbx+1Dh]
0x140046c20  shl     cx, 8
0x140046c24  or      cx, ax
0x140046c27  mov     [rdi+38h], cx
0x140046c2b  jz      short loc_140046C63
0x140046c2d  movzx   eax, byte ptr [rbx+1Fh]
0x140046c31  movzx   ecx, byte ptr [rbx+1Eh]
0x140046c35  shl     ecx, 8
0x140046c38  or      ecx, eax
0x140046c3a  movzx   eax, byte ptr [rbx+20h]
0x140046c3e  shl     ecx, 8
0x140046c41  or      ecx, eax
0x140046c43  movzx   eax, byte ptr [rbx+21h]
0x140046c47  shl     ecx, 8
0x140046c4a  or      ecx, eax
0x140046c4c  lea     rax, [rbx+22h]
0x140046c50  mov     [rdi+3Ch], ecx
0x140046c53  mov     [r14], rax
0x140046c56  xor     eax, eax
0x140046c58  jmp     short loc_140046C68
0x140046c5a  mov     byte ptr [rdi+20h], 0
0x140046c5e  mov     [r14], rbp
0x140046c61  jmp     short loc_140046C56
0x140046c63  mov     eax, 0C000000Dh
0x140046c68  mov     rbx, [rsp+58h+arg_10]
0x140046c6d  add     rsp, 30h
0x140046c71  pop     r15
0x140046c73  pop     r14
0x140046c75  pop     rdi
0x140046c76  pop     rsi
0x140046c77  pop     rbp
0x140046c78  retn
```
