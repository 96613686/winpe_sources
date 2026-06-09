# DumpTemplateList

- ea: `0x140014ccc`
- end: `0x140014e8f`
- name: `DumpTemplateList`
- size: `451`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1400145a0`

## callees

- `0x140014ccc`
- `0x140014e98`
- `0x1400155e0`
- `0x140016360`
- `0x1400164c4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140014e5d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140014e5d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140014e4f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140014e4f`

## string_xrefs

- `0x140014ce3`: `		<templates>\n`
- `0x140014d0c`: `			<template tid="tid_%d">\n`
- `0x140014e43`: `			</template>\n`
- `0x140014e73`: `		</templates>\n`

## pseudocode

```c
__int64 __fastcall DumpTemplateList(__int64 a1)
{
  void **v2; // r12
  __int64 *v3; // rdi
  __int64 v4; // rcx
  __int64 *v5; // rax
  unsigned int v6; // r13d
  __int64 v7; // rbp
  __int64 v8; // rsi
  __int64 v9; // rax
  __int64 v10; // rax
  __int64 v11; // r9
  unsigned int v12; // r15d
  unsigned int v13; // esi
  HANDLE ProcessHeap; // rax

  TracerptFPutws((wchar_t *)L"\t\t<templates>\r\n", *(struct _iobuf **)a1);
  v2 = (void **)(a1 + 152);
  v3 = *(__int64 **)(a1 + 152);
  if ( v3 != (__int64 *)(a1 + 152) )
  {
    do
    {
      v4 = *v3;
      v5 = (__int64 *)v3[1];
      *v5 = *v3;
      *(_QWORD *)(v4 + 8) = v5;
      TracerptFWPrintf(
        *(struct _iobuf **)a1,
        (wchar_t *)L"\t\t\t<template tid=\"tid_%d\">\r\n",
        *((unsigned int *)v3 + 4));
      v6 = *(_DWORD *)(v3[3] + 104);
      if ( v6 )
      {
        v7 = 0;
        do
        {
          v8 = v3[3];
          v9 = *(unsigned int *)(v8 + 24 * v7 + 116);
          if ( (_DWORD)v9 )
          {
            if ( (*(_BYTE *)(v8 + 24 * v7 + 112) & 1) != 0 )
            {
              TracerptFWPrintf(*(struct _iobuf **)a1, (wchar_t *)L"\t\t\t\t<struct name=\"%ws\"", v8 + v9);
              v10 = *(unsigned __int16 *)(v8 + 24 * v7 + 128);
              if ( (*(_BYTE *)(v8 + 24 * v7 + 112) & 4) != 0 )
              {
                TracerptFWPrintf(
                  *(struct _iobuf **)a1,
                  (wchar_t *)L" count=\"%ws\"",
                  v3[3] + *(unsigned int *)(v3[3] + 24 * v10 + 116));
              }
              else if ( (unsigned __int16)v10 > 1u )
              {
                TracerptFWPrintf(
                  *(struct _iobuf **)a1,
                  (wchar_t *)L" count=\"%d\"",
                  *(unsigned __int16 *)(v8 + 24 * v7 + 128));
              }
              TracerptFPutws((wchar_t *)L">\r\n", *(struct _iobuf **)a1);
              v12 = *(unsigned __int16 *)(v8 + 24 * v7 + 120);
              v13 = v12 + *(unsigned __int16 *)(v8 + 24 * v7 + 122);
              while ( v12 < v13 )
              {
                LOBYTE(v11) = 1;
                OutputProperty(a1, v3[3], v12++, v11);
              }
              TracerptFPutws((wchar_t *)L"\t\t\t\t</struct>\r\n", *(struct _iobuf **)a1);
            }
            else
            {
              OutputProperty(a1, v3[3], (unsigned int)v7, 0);
            }
          }
          v7 = (unsigned int)(v7 + 1);
        }
        while ( (unsigned int)v7 < v6 );
      }
      if ( (*(_BYTE *)(v3[3] + 108) & 2) != 0 )
        DumpUserData(a1);
      TracerptFPutws((wchar_t *)L"\t\t\t</template>\r\n", *(struct _iobuf **)a1);
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v3);
      v3 = (__int64 *)*v2;
    }
    while ( *v2 != v2 );
  }
  return TracerptFPutws((wchar_t *)L"\t\t</templates>\r\n", *(struct _iobuf **)a1);
}

```

## disassembly

```asm
0x140014ccc  push    rbx
0x140014cce  push    rbp
0x140014ccf  push    rsi
0x140014cd0  push    rdi
0x140014cd1  push    r12
0x140014cd3  push    r13
0x140014cd5  push    r14
0x140014cd7  push    r15
0x140014cd9  sub     rsp, 28h
0x140014cdd  mov     rdx, [rcx]; struct _iobuf *
0x140014ce0  mov     rbx, rcx
0x140014ce3  lea     rcx, aTemplates; "\t\t<templates>\r\n"
0x140014cea  call    ?TracerptFPutws@@YAKPEBGPEAU_iobuf@@@Z; TracerptFPutws(ushort const *,_iobuf *)
0x140014cef  lea     r12, [rbx+98h]
0x140014cf6  mov     rdi, [r12]
0x140014cfa  cmp     rdi, r12
0x140014cfd  jz      loc_140014E70
0x140014d03  mov     r15d, 1
0x140014d09  mov     rcx, [rdi]
0x140014d0c  lea     rdx, aTemplateTidTid; "\t\t\t<template tid=\"tid_%d\">\r\n"
0x140014d13  mov     rax, [rdi+8]
0x140014d17  mov     [rax], rcx
0x140014d1a  mov     [rcx+8], rax
0x140014d1e  mov     r8d, [rdi+10h]
0x140014d22  mov     rcx, [rbx]; struct _iobuf *
0x140014d25  call    ?TracerptFWPrintf@@YAKPEAU_iobuf@@PEBGZZ; TracerptFWPrintf(_iobuf *,ushort const *,...)
0x140014d2a  mov     rax, [rdi+18h]
0x140014d2e  mov     r13d, [rax+68h]
0x140014d32  test    r13d, r13d
0x140014d35  jz      loc_140014E2E
0x140014d3b  xor     ebp, ebp
0x140014d3d  mov     rsi, [rdi+18h]
0x140014d41  lea     r14, ds:0[rbp*2]
0x140014d49  add     r14, rbp
0x140014d4c  mov     eax, [rsi+r14*8+74h]
0x140014d51  test    eax, eax
0x140014d53  jz      loc_140014E22
0x140014d59  test    [rsi+r14*8+70h], r15b
0x140014d5e  jnz     short loc_140014D76
0x140014d60  xor     r9d, r9d
0x140014d63  mov     r8d, ebp
0x140014d66  mov     rdx, rsi
0x140014d69  mov     rcx, rbx
0x140014d6c  call    OutputProperty
0x140014d71  jmp     loc_140014E22
0x140014d76  mov     rcx, [rbx]; struct _iobuf *
0x140014d79  lea     r8, [rsi+rax]
0x140014d7d  lea     rdx, aStructNameWs; "\t\t\t\t<struct name=\"%ws\""
0x140014d84  call    ?TracerptFWPrintf@@YAKPEAU_iobuf@@PEBGZZ; TracerptFWPrintf(_iobuf *,ushort const *,...)
0x140014d89  test    byte ptr [rsi+r14*8+70h], 4
0x140014d8f  movzx   eax, word ptr [rsi+r14*8+80h]
0x140014d98  jz      short loc_140014DBB
0x140014d9a  mov     rdx, [rdi+18h]
0x140014d9e  lea     rcx, [rax+rax*2]
0x140014da2  mov     r8d, [rdx+rcx*8+74h]
0x140014da7  mov     rcx, [rbx]; struct _iobuf *
0x140014daa  add     r8, rdx
0x140014dad  lea     rdx, aCountWs; " count=\"%ws\""
0x140014db4  call    ?TracerptFWPrintf@@YAKPEAU_iobuf@@PEBGZZ; TracerptFWPrintf(_iobuf *,ushort const *,...)
0x140014db9  jmp     short loc_140014DD3
0x140014dbb  cmp     ax, r15w
0x140014dbf  jbe     short loc_140014DD3
0x140014dc1  mov     rcx, [rbx]; struct _iobuf *
0x140014dc4  lea     rdx, aCountD; " count=\"%d\""
0x140014dcb  mov     r8d, eax
0x140014dce  call    ?TracerptFWPrintf@@YAKPEAU_iobuf@@PEBGZZ; TracerptFWPrintf(_iobuf *,ushort const *,...)
0x140014dd3  mov     rdx, [rbx]; struct _iobuf *
0x140014dd6  lea     rcx, asc_140047FF0; ">\r\n"
0x140014ddd  call    ?TracerptFPutws@@YAKPEBGPEAU_iobuf@@@Z; TracerptFPutws(ushort const *,_iobuf *)
0x140014de2  movzx   r15d, word ptr [rsi+r14*8+78h]
0x140014de8  movzx   esi, word ptr [rsi+r14*8+7Ah]
0x140014dee  add     esi, r15d
0x140014df1  jmp     short loc_140014E08
0x140014df3  mov     rdx, [rdi+18h]
0x140014df7  mov     r9b, 1
0x140014dfa  mov     r8d, r15d
0x140014dfd  mov     rcx, rbx
0x140014e00  call    OutputProperty
0x140014e05  inc     r15d
0x140014e08  cmp     r15d, esi
0x140014e0b  jb      short loc_140014DF3
0x140014e0d  mov     rdx, [rbx]; struct _iobuf *
0x140014e10  lea     rcx, aStruct; "\t\t\t\t</struct>\r\n"
0x140014e17  call    ?TracerptFPutws@@YAKPEBGPEAU_iobuf@@@Z; TracerptFPutws(ushort const *,_iobuf *)
0x140014e1c  mov     r15d, 1
0x140014e22  add     ebp, r15d
0x140014e25  cmp     ebp, r13d
0x140014e28  jb      loc_140014D3D
0x140014e2e  mov     rdx, [rdi+18h]
0x140014e32  test    byte ptr [rdx+6Ch], 2
0x140014e36  jz      short loc_140014E40
0x140014e38  mov     rcx, rbx
0x140014e3b  call    DumpUserData
0x140014e40  mov     rdx, [rbx]; struct _iobuf *
0x140014e43  lea     rcx, aTemplate; "\t\t\t</template>\r\n"
0x140014e4a  call    ?TracerptFPutws@@YAKPEBGPEAU_iobuf@@@Z; TracerptFPutws(ushort const *,_iobuf *)
0x140014e4f  call    cs:__imp_GetProcessHeap
0x140014e55  mov     r8, rdi; lpMem
0x140014e58  xor     edx, edx; dwFlags
0x140014e5a  mov     rcx, rax; hHeap
0x140014e5d  call    cs:__imp_HeapFree
0x140014e63  mov     rdi, [r12]
0x140014e67  cmp     rdi, r12
0x140014e6a  jnz     loc_140014D09
0x140014e70  mov     rdx, [rbx]; struct _iobuf *
0x140014e73  lea     rcx, aTemplates_0; "\t\t</templates>\r\n"
0x140014e7a  add     rsp, 28h
0x140014e7e  pop     r15
0x140014e80  pop     r14
0x140014e82  pop     r13
0x140014e84  pop     r12
0x140014e86  pop     rdi
0x140014e87  pop     rsi
0x140014e88  pop     rbp
0x140014e89  pop     rbx
0x140014e8a  jmp     ?TracerptFPutws@@YAKPEBGPEAU_iobuf@@@Z; TracerptFPutws(ushort const *,_iobuf *)
```
