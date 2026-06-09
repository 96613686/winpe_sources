# ParseBinaryData

- ea: `0x18000a980`
- end: `0x18000ab1b`
- name: `ParseBinaryData`
- size: `411`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180009ba8`

## callees

- `0x1800015d4`
- `0x18000a980`
- `0x18000c274`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18000a9fc`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18000aa1b`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18000a9fc`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18000aa1b`
- `WdsCommonLib!?StrRemoveChar@@YAXPEAGG@Z` at `0x18000aabe`
- `WdsCommonLib!?StrRemoveChar@@YAXPEAGG@Z` at `0x18000aad2`
- `WdsCommonLib!?StrRemoveChar@@YAXPEAGG@Z` at `0x18000aabe`
- `WdsCommonLib!?StrRemoveChar@@YAXPEAGG@Z` at `0x18000aad2`
- `WdsCommonLib!?StringToHex@@YAKPEBGPEAPEAEPEA_K@Z` at `0x18000aaeb`
- `WdsCommonLib!?StringToHex@@YAKPEBGPEAPEAEPEA_K@Z` at `0x18000aaeb`
- `WdsCommonLib!?DuplicateStringW@@YAKPEBGPEAPEAG@Z` at `0x18000aa97`
- `WdsCommonLib!?DuplicateStringW@@YAKPEBGPEAPEAG@Z` at `0x18000aa97`

## pseudocode

```c
__int64 __fastcall ParseBinaryData(__int64 a1, unsigned __int8 **a2, _QWORD *a3)
{
  unsigned __int64 v4; // rbx
  unsigned int v7; // esi
  __int64 v8; // rax
  __int64 v9; // rcx
  unsigned int v10; // ebx
  __int64 v12; // rdx
  __int64 v13; // r8
  __int64 v14; // rdx
  __int64 v15; // r8
  unsigned __int64 v16[7]; // [rsp+20h] [rbp-38h] BYREF
  void *Block; // [rsp+78h] [rbp+20h] BYREF

  v16[0] = 0;
  v4 = -1;
  Block = 0;
  do
    ++v4;
  while ( *(_WORD *)(a1 + 2 * v4) );
  if ( v4 )
  {
    if ( *(_WORD *)a1 == 91 && *(_WORD *)(a1 + 2 * v4 - 2) == 93 )
    {
      v7 = 1;
      if ( v4 > 2 )
      {
        while ( wcsrchr(L"0123456789abcdefABCDEF", *(_WORD *)(a1 + 2LL * v7))
             && wcsrchr(L"0123456789abcdefABCDEF", *(_WORD *)(a1 + 2LL * (v7 + 1))) )
        {
          v8 = v7 + 2;
          v7 += 3;
          v9 = 2 * v8;
          if ( v7 == v4 && *(_WORD *)(v9 + a1) == 93 )
          {
            v10 = DuplicateStringW((const unsigned __int16 *)(a1 + 2), (unsigned __int16 **)&Block);
            if ( !(unsigned int)ElValidateWin32_1(v10, v12, v13, 1080) )
            {
              StrRemoveChar((unsigned __int16 *)Block, 0x2Du);
              StrRemoveChar((unsigned __int16 *)Block, 0x5Du);
              v10 = StringToHex((const unsigned __int16 *)Block, a2, v16);
              if ( !(unsigned int)ElValidateWin32_1(v10, v14, v15, 1086) )
                *a3 = v16[0];
            }
            goto LABEL_15;
          }
          if ( (unsigned int)v8 == v4 || *(_WORD *)(v9 + a1) != 45 || v7 + 1 >= v4 )
            break;
        }
      }
    }
  }
  v10 = 13;
LABEL_15:
  if ( Block )
    operator delete(Block);
  return v10;
}

```

## disassembly

```asm
0x18000a980  mov     rax, rsp
0x18000a983  mov     [rax+8], rbx
0x18000a987  mov     [rax+10h], rbp
0x18000a98b  mov     [rax+18h], rsi
0x18000a98f  push    rdi
0x18000a990  push    r12
0x18000a992  push    r13
0x18000a994  push    r14
0x18000a996  push    r15
0x18000a998  sub     rsp, 30h
0x18000a99c  xor     r15d, r15d
0x18000a99f  mov     r14, r8
0x18000a9a2  mov     [rax-38h], r15
0x18000a9a6  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000a9aa  mov     [rax+20h], r15
0x18000a9ae  mov     rbp, rdx
0x18000a9b1  mov     rdi, rcx
0x18000a9b4  inc     rbx
0x18000a9b7  cmp     [rcx+rbx*2], r15w
0x18000a9bc  jnz     short loc_18000A9B4
0x18000a9be  test    rbx, rbx
0x18000a9c1  jz      loc_18000AA5A
0x18000a9c7  cmp     word ptr [rcx], 5Bh ; '['
0x18000a9cb  jnz     loc_18000AA5A
0x18000a9d1  mov     r12d, 5Dh ; ']'
0x18000a9d7  cmp     [rcx+rbx*2-2], r12w
0x18000a9dd  jnz     short loc_18000AA5A
0x18000a9df  lea     esi, [r12-5Ch]
0x18000a9e4  cmp     rbx, 2
0x18000a9e8  jbe     short loc_18000AA5A
0x18000a9ea  lea     r13d, [r12-30h]
0x18000a9ef  mov     edx, esi
0x18000a9f1  lea     rcx, a0123456789abcd; "0123456789abcdefABCDEF"
0x18000a9f8  movzx   edx, word ptr [rdi+rdx*2]; Ch
0x18000a9fc  call    cs:__imp_wcsrchr
0x18000aa03  nop     dword ptr [rax+rax+00h]
0x18000aa08  test    rax, rax
0x18000aa0b  jz      short loc_18000AA5A
0x18000aa0d  lea     eax, [rsi+1]
0x18000aa10  movzx   edx, word ptr [rdi+rax*2]; Ch
0x18000aa14  lea     rcx, a0123456789abcd; "0123456789abcdefABCDEF"
0x18000aa1b  call    cs:__imp_wcsrchr
0x18000aa22  nop     dword ptr [rax+rax+00h]
0x18000aa27  test    rax, rax
0x18000aa2a  jz      short loc_18000AA5A
0x18000aa2c  lea     eax, [rsi+2]
0x18000aa2f  lea     esi, [rax+1]
0x18000aa32  mov     edx, eax
0x18000aa34  lea     rcx, [rax+rax]
0x18000aa38  mov     eax, esi
0x18000aa3a  cmp     rax, rbx
0x18000aa3d  jnz     short loc_18000AA46
0x18000aa3f  cmp     [rcx+rdi], r12w
0x18000aa44  jz      short loc_18000AA8E
0x18000aa46  cmp     rdx, rbx
0x18000aa49  jz      short loc_18000AA5A
0x18000aa4b  cmp     [rcx+rdi], r13w
0x18000aa50  jnz     short loc_18000AA5A
0x18000aa52  lea     ecx, [rsi+1]
0x18000aa55  cmp     rcx, rbx
0x18000aa58  jb      short loc_18000A9EF
0x18000aa5a  mov     ebx, 0Dh
0x18000aa5f  mov     rcx, [rsp+58h+Block]; Block
0x18000aa64  test    rcx, rcx
0x18000aa67  jz      short loc_18000AA6E
0x18000aa69  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000aa6e  mov     rbp, [rsp+58h+arg_8]
0x18000aa73  mov     eax, ebx
0x18000aa75  mov     rbx, [rsp+58h+arg_0]
0x18000aa7a  mov     rsi, [rsp+58h+arg_10]
0x18000aa7f  add     rsp, 30h
0x18000aa83  pop     r15
0x18000aa85  pop     r14
0x18000aa87  pop     r13
0x18000aa89  pop     r12
0x18000aa8b  pop     rdi
0x18000aa8c  retn
0x18000aa8e  lea     rcx, [rdi+2]
0x18000aa92  lea     rdx, [rsp+58h+Block]
0x18000aa97  call    cs:__imp_?DuplicateStringW@@YAKPEBGPEAPEAG@Z; DuplicateStringW(ushort const *,ushort * *)
0x18000aa9e  nop     dword ptr [rax+rax+00h]
0x18000aaa3  mov     ecx, eax
0x18000aaa5  mov     r9d, 438h
0x18000aaab  mov     ebx, eax
0x18000aaad  call    ElValidateWin32_1
0x18000aab2  test    eax, eax
0x18000aab4  jnz     short loc_18000AA5F
0x18000aab6  mov     rcx, [rsp+58h+Block]
0x18000aabb  mov     edx, r13d
0x18000aabe  call    cs:__imp_?StrRemoveChar@@YAXPEAGG@Z; StrRemoveChar(ushort *,ushort)
0x18000aac5  nop     dword ptr [rax+rax+00h]
0x18000aaca  mov     rcx, [rsp+58h+Block]
0x18000aacf  mov     edx, r12d
0x18000aad2  call    cs:__imp_?StrRemoveChar@@YAXPEAGG@Z; StrRemoveChar(ushort *,ushort)
0x18000aad9  nop     dword ptr [rax+rax+00h]
0x18000aade  mov     rcx, [rsp+58h+Block]
0x18000aae3  lea     r8, [rsp+58h+var_38]
0x18000aae8  mov     rdx, rbp
0x18000aaeb  call    cs:__imp_?StringToHex@@YAKPEBGPEAPEAEPEA_K@Z; StringToHex(ushort const *,uchar * *,unsigned __int64 *)
0x18000aaf2  nop     dword ptr [rax+rax+00h]
0x18000aaf7  mov     ecx, eax
0x18000aaf9  mov     r9d, 43Eh
0x18000aaff  mov     ebx, eax
0x18000ab01  call    ElValidateWin32_1
0x18000ab06  test    eax, eax
0x18000ab08  jnz     loc_18000AA5F
0x18000ab0e  mov     rax, [rsp+58h+var_38]
0x18000ab13  mov     [r14], rax
0x18000ab16  jmp     loc_18000AA5F
```
