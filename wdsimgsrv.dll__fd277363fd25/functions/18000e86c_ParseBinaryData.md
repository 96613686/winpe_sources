# ParseBinaryData

- ea: `0x18000e86c`
- end: `0x18000ea14`
- name: `ParseBinaryData`
- size: `424`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000e330`

## callees

- `0x18000e86c`
- `0x18000fd28`

## import_xrefs

- `msvcrt!wcsrchr` at `0x18000e8ec`
- `msvcrt!wcsrchr` at `0x18000e90c`
- `msvcrt!wcsrchr` at `0x18000e8ec`
- `msvcrt!wcsrchr` at `0x18000e90c`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000e9e8`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000e9e8`
- `WdsCommonLib!?StringToHex@@YAKPEBGPEAPEAEPEA_K@Z` at `0x18000e9b0`
- `WdsCommonLib!?StringToHex@@YAKPEBGPEAPEAEPEA_K@Z` at `0x18000e9b0`
- `WdsCommonLib!?StrRemoveChar@@YAXPEAGG@Z` at `0x18000e983`
- `WdsCommonLib!?StrRemoveChar@@YAXPEAGG@Z` at `0x18000e997`
- `WdsCommonLib!?StrRemoveChar@@YAXPEAGG@Z` at `0x18000e983`
- `WdsCommonLib!?StrRemoveChar@@YAXPEAGG@Z` at `0x18000e997`
- `WdsCommonLib!?DuplicateStringW@@YAKPEBGPEAPEAG@Z` at `0x18000e95c`
- `WdsCommonLib!?DuplicateStringW@@YAKPEBGPEAPEAG@Z` at `0x18000e95c`

## pseudocode

```c
__int64 __fastcall ParseBinaryData(__int64 a1, unsigned __int8 **a2, _QWORD *a3)
{
  unsigned __int64 v4; // rbx
  unsigned int i; // esi
  unsigned __int64 v8; // rbp
  __int64 v9; // rsi
  unsigned int v10; // ebx
  __int64 v11; // rdx
  __int64 v12; // r8
  __int64 v13; // rdx
  __int64 v14; // r8
  unsigned __int64 v16[7]; // [rsp+20h] [rbp-38h] BYREF
  unsigned __int16 *v17; // [rsp+78h] [rbp+20h] BYREF

  v16[0] = 0;
  v4 = -1;
  v17 = 0;
  do
    ++v4;
  while ( *(_WORD *)(a1 + 2 * v4) );
  if ( v4 && *(_WORD *)a1 == 91 && *(_WORD *)(a1 + 2 * v4 - 2) == 93 )
  {
    for ( i = 1; ; i = v9 + 1 )
    {
      v8 = i + 1;
      if ( v8 >= v4
        || !wcsrchr(L"0123456789abcdefABCDEF", *(_WORD *)(a1 + 2LL * i))
        || !wcsrchr(L"0123456789abcdefABCDEF", *(_WORD *)(a1 + 2 * v8)) )
      {
        break;
      }
      v9 = i + 2;
      if ( (_DWORD)v9 + 1 == v4 && *(_WORD *)(a1 + 2 * v9) == 93 )
      {
        v10 = DuplicateStringW((const unsigned __int16 *)(a1 + 2), &v17);
        if ( !(unsigned int)ElValidateWin32_2(v10, v11, v12, 1080) )
        {
          StrRemoveChar(v17, 0x2Du);
          StrRemoveChar(v17, 0x5Du);
          v10 = StringToHex(v17, a2, v16);
          if ( !(unsigned int)ElValidateWin32_2(v10, v13, v14, 1086) )
            *a3 = v16[0];
        }
        goto LABEL_19;
      }
      if ( (unsigned int)v9 == v4 || *(_WORD *)(a1 + 2 * v9) != 45 )
        break;
    }
  }
  v10 = 13;
LABEL_19:
  if ( v17 )
    operator delete(v17);
  return v10;
}

```

## disassembly

```asm
0x18000e86c  mov     rax, rsp
0x18000e86f  mov     [rax+8], rbx
0x18000e873  mov     [rax+10h], rbp
0x18000e877  mov     [rax+18h], rsi
0x18000e87b  push    rdi
0x18000e87c  push    r12
0x18000e87e  push    r13
0x18000e880  push    r14
0x18000e882  push    r15
0x18000e884  sub     rsp, 30h
0x18000e888  xor     r12d, r12d
0x18000e88b  mov     r14, r8
0x18000e88e  mov     [rax-38h], r12
0x18000e892  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000e896  mov     [rax+20h], r12
0x18000e89a  mov     r15, rdx
0x18000e89d  mov     rdi, rcx
0x18000e8a0  inc     rbx
0x18000e8a3  cmp     [rcx+rbx*2], r12w
0x18000e8a8  jnz     short loc_18000E8A0
0x18000e8aa  test    rbx, rbx
0x18000e8ad  jz      loc_18000E9D9
0x18000e8b3  cmp     word ptr [rcx], 5Bh ; '['
0x18000e8b7  jnz     loc_18000E9D9
0x18000e8bd  mov     r13d, 5Dh ; ']'
0x18000e8c3  cmp     [rcx+rbx*2-2], r13w
0x18000e8c9  jnz     loc_18000E9D9
0x18000e8cf  lea     esi, [r13-5Ch]
0x18000e8d3  lea     ebp, [rsi+1]
0x18000e8d6  cmp     rbp, rbx
0x18000e8d9  jnb     loc_18000E9D9
0x18000e8df  mov     edx, esi
0x18000e8e1  lea     rcx, a0123456789abcd_0; "0123456789abcdefABCDEF"
0x18000e8e8  movzx   edx, word ptr [rdi+rdx*2]; Ch
0x18000e8ec  call    cs:__imp_wcsrchr
0x18000e8f3  nop     dword ptr [rax+rax+00h]
0x18000e8f8  test    rax, rax
0x18000e8fb  jz      loc_18000E9D9
0x18000e901  movzx   edx, word ptr [rdi+rbp*2]; Ch
0x18000e905  lea     rcx, a0123456789abcd_0; "0123456789abcdefABCDEF"
0x18000e90c  call    cs:__imp_wcsrchr
0x18000e913  nop     dword ptr [rax+rax+00h]
0x18000e918  test    rax, rax
0x18000e91b  jz      loc_18000E9D9
0x18000e921  add     esi, 2
0x18000e924  mov     ecx, esi
0x18000e926  lea     edx, [rsi+1]
0x18000e929  mov     eax, edx
0x18000e92b  cmp     rax, rbx
0x18000e92e  jnz     short loc_18000E937
0x18000e930  cmp     [rdi+rsi*2], r13w
0x18000e935  jz      short loc_18000E953
0x18000e937  cmp     rcx, rbx
0x18000e93a  jz      loc_18000E9D9
0x18000e940  mov     eax, 2Dh ; '-'
0x18000e945  cmp     [rdi+rsi*2], ax
0x18000e949  jnz     loc_18000E9D9
0x18000e94f  mov     esi, edx
0x18000e951  jmp     short loc_18000E8D3
0x18000e953  lea     rcx, [rdi+2]
0x18000e957  lea     rdx, [rsp+58h+arg_18]
0x18000e95c  call    cs:__imp_?DuplicateStringW@@YAKPEBGPEAPEAG@Z; DuplicateStringW(ushort const *,ushort * *)
0x18000e963  nop     dword ptr [rax+rax+00h]
0x18000e968  mov     ecx, eax
0x18000e96a  mov     r9d, 438h
0x18000e970  mov     ebx, eax
0x18000e972  call    ElValidateWin32_2
0x18000e977  test    eax, eax
0x18000e979  jnz     short loc_18000E9DE
0x18000e97b  mov     rcx, [rsp+58h+arg_18]
0x18000e980  lea     edx, [rax+2Dh]
0x18000e983  call    cs:__imp_?StrRemoveChar@@YAXPEAGG@Z; StrRemoveChar(ushort *,ushort)
0x18000e98a  nop     dword ptr [rax+rax+00h]
0x18000e98f  mov     rcx, [rsp+58h+arg_18]
0x18000e994  mov     edx, r13d
0x18000e997  call    cs:__imp_?StrRemoveChar@@YAXPEAGG@Z; StrRemoveChar(ushort *,ushort)
0x18000e99e  nop     dword ptr [rax+rax+00h]
0x18000e9a3  mov     rcx, [rsp+58h+arg_18]
0x18000e9a8  lea     r8, [rsp+58h+var_38]
0x18000e9ad  mov     rdx, r15
0x18000e9b0  call    cs:__imp_?StringToHex@@YAKPEBGPEAPEAEPEA_K@Z; StringToHex(ushort const *,uchar * *,unsigned __int64 *)
0x18000e9b7  nop     dword ptr [rax+rax+00h]
0x18000e9bc  mov     ecx, eax
0x18000e9be  mov     r9d, 43Eh
0x18000e9c4  mov     ebx, eax
0x18000e9c6  call    ElValidateWin32_2
0x18000e9cb  test    eax, eax
0x18000e9cd  jnz     short loc_18000E9DE
0x18000e9cf  mov     rax, [rsp+58h+var_38]
0x18000e9d4  mov     [r14], rax
0x18000e9d7  jmp     short loc_18000E9DE
0x18000e9d9  mov     ebx, 0Dh
0x18000e9de  mov     rcx, [rsp+58h+arg_18]
0x18000e9e3  test    rcx, rcx
0x18000e9e6  jz      short loc_18000E9F4
0x18000e9e8  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000e9ef  nop     dword ptr [rax+rax+00h]
0x18000e9f4  mov     rbp, [rsp+58h+arg_8]
0x18000e9f9  mov     eax, ebx
0x18000e9fb  mov     rbx, [rsp+58h+arg_0]
0x18000ea00  mov     rsi, [rsp+58h+arg_10]
0x18000ea05  add     rsp, 30h
0x18000ea09  pop     r15
0x18000ea0b  pop     r14
0x18000ea0d  pop     r13
0x18000ea0f  pop     r12
0x18000ea11  pop     rdi
0x18000ea12  retn
```
