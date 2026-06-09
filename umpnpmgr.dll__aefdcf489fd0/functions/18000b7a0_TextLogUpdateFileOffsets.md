# TextLogUpdateFileOffsets

- ea: `0x18000b7a0`
- end: `0x18000b87f`
- name: `TextLogUpdateFileOffsets`
- size: `223`
- prototype: `__int64 __fastcall(__int64, unsigned int, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x18000c9d0`

## callees

- `0x18000b7a0`
- `0x18000b890`
- `0x18000b900`

## pseudocode

```c
__int64 __fastcall TextLogUpdateFileOffsets(__int64 a1, unsigned int a2, int a3)
{
  __int64 result; // rax
  unsigned int i; // ebp
  __int128 v8; // [rsp+20h] [rbp-28h] BYREF
  int v9; // [rsp+30h] [rbp-18h]

  result = 0;
  v9 = 0;
  v8 = 0;
  if ( a3 )
  {
    *(_DWORD *)(a1 + 40) += a3;
    for ( i = 0; (unsigned int)TextLogEnumerateOpenSections(a1, i, (__int64)&v8); ++i )
    {
      if ( a3 <= 0 )
      {
        if ( DWORD2(v8) > a2 )
        {
          if ( DWORD2(v8) <= a2 - a3 )
            DWORD2(v8) = a2;
          else
            DWORD2(v8) += a3;
        }
        if ( HIDWORD(v8) > a2 )
        {
          if ( HIDWORD(v8) <= a2 - a3 )
            HIDWORD(v8) = a2;
          else
            HIDWORD(v8) += a3;
        }
      }
      else
      {
        if ( DWORD2(v8) >= a2 )
          DWORD2(v8) += a3;
        if ( HIDWORD(v8) >= a2 )
          HIDWORD(v8) += a3;
      }
      TextLogUpdateSectionTag(a1, &v8, i);
    }
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x18000b7a0  mov     [rsp+arg_8], rbx
0x18000b7a5  mov     [rsp+arg_10], rsi
0x18000b7aa  push    rdi
0x18000b7ab  sub     rsp, 40h
0x18000b7af  xor     eax, eax
0x18000b7b1  xorps   xmm0, xmm0
0x18000b7b4  mov     [rsp+48h+var_18], eax
0x18000b7b8  mov     edi, r8d
0x18000b7bb  mov     ebx, edx
0x18000b7bd  mov     rsi, rcx
0x18000b7c0  movups  [rsp+48h+var_28], xmm0
0x18000b7c5  test    r8d, r8d
0x18000b7c8  jz      loc_18000B86F
0x18000b7ce  add     [rcx+28h], r8d
0x18000b7d2  xor     edx, edx
0x18000b7d4  lea     r8, [rsp+48h+var_28]
0x18000b7d9  mov     [rsp+48h+arg_0], rbp
0x18000b7de  xor     ebp, ebp
0x18000b7e0  call    TextLogEnumerateOpenSections
0x18000b7e5  test    eax, eax
0x18000b7e7  jz      short loc_18000B868
0x18000b7e9  test    edi, edi
0x18000b7eb  jle     short loc_18000B80B
0x18000b7ed  mov     eax, dword ptr [rsp+48h+var_28+8]
0x18000b7f1  cmp     eax, ebx
0x18000b7f3  jb      short loc_18000B7FB
0x18000b7f5  add     eax, edi
0x18000b7f7  mov     dword ptr [rsp+48h+var_28+8], eax
0x18000b7fb  mov     eax, dword ptr [rsp+48h+var_28+0Ch]
0x18000b7ff  cmp     eax, ebx
0x18000b801  jb      short loc_18000B843
0x18000b803  add     eax, edi
0x18000b805  mov     dword ptr [rsp+48h+var_28+0Ch], eax
0x18000b809  jmp     short loc_18000B843
0x18000b80b  mov     ecx, dword ptr [rsp+48h+var_28+8]
0x18000b80f  cmp     ecx, ebx
0x18000b811  jbe     short loc_18000B827
0x18000b813  mov     eax, ebx
0x18000b815  sub     eax, edi
0x18000b817  cmp     ecx, eax
0x18000b819  jbe     short loc_18000B823
0x18000b81b  add     ecx, edi
0x18000b81d  mov     dword ptr [rsp+48h+var_28+8], ecx
0x18000b821  jmp     short loc_18000B827
0x18000b823  mov     dword ptr [rsp+48h+var_28+8], ebx
0x18000b827  mov     ecx, dword ptr [rsp+48h+var_28+0Ch]
0x18000b82b  cmp     ecx, ebx
0x18000b82d  jbe     short loc_18000B843
0x18000b82f  mov     eax, ebx
0x18000b831  sub     eax, edi
0x18000b833  cmp     ecx, eax
0x18000b835  jbe     short loc_18000B83F
0x18000b837  add     ecx, edi
0x18000b839  mov     dword ptr [rsp+48h+var_28+0Ch], ecx
0x18000b83d  jmp     short loc_18000B843
0x18000b83f  mov     dword ptr [rsp+48h+var_28+0Ch], ebx
0x18000b843  mov     r8d, ebp
0x18000b846  lea     rdx, [rsp+48h+var_28]
0x18000b84b  mov     rcx, rsi
0x18000b84e  call    TextLogUpdateSectionTag
0x18000b853  inc     ebp
0x18000b855  lea     r8, [rsp+48h+var_28]
0x18000b85a  mov     edx, ebp
0x18000b85c  mov     rcx, rsi
0x18000b85f  call    TextLogEnumerateOpenSections
0x18000b864  test    eax, eax
0x18000b866  jnz     short loc_18000B7E9
0x18000b868  mov     rbp, [rsp+48h+arg_0]
0x18000b86d  xor     eax, eax
0x18000b86f  mov     rbx, [rsp+48h+arg_8]
0x18000b874  mov     rsi, [rsp+48h+arg_10]
0x18000b879  add     rsp, 40h
0x18000b87d  pop     rdi
0x18000b87e  retn
```
