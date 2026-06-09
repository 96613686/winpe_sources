# TextLogDeleteString

- ea: `0x18000b5f0`
- end: `0x18000b78c`
- name: `TextLogDeleteString`
- size: `412`
- prototype: `__int64 __fastcall(__int64, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, installer_update`

## callers

- `0x1800104d8`

## callees

- `0x18000b5f0`
- `0x18000b890`
- `0x18000b900`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b705`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b705`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18000b662`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18000b662`

## pseudocode

```c
__int64 __fastcall TextLogDeleteString(__int64 a1, unsigned int a2)
{
  _BYTE *v4; // rbx
  _BYTE *v5; // r9
  _BYTE *v6; // r10
  unsigned __int64 v7; // rax
  unsigned int v8; // eax
  __int64 i; // r8
  DWORD LastError; // edi
  int v11; // ebx
  __int128 v14; // [rsp+38h] [rbp-40h] BYREF
  int v15; // [rsp+48h] [rbp-30h]

  if ( a2 >= *(_DWORD *)(a1 + 40) )
    return 87;
  v4 = (_BYTE *)(*(_QWORD *)(a1 + 16) + a2);
  v5 = v4;
  v6 = v4;
  do
  {
    v7 = *(_QWORD *)(a1 + 24);
    if ( (unsigned __int64)v6 >= v7 )
      break;
    v6 = v5 + 1;
  }
  while ( *v5++ != 10 );
  v8 = v7 - (_DWORD)v6;
  for ( i = 0; (unsigned int)i < v8; i = (unsigned int)(i + 1) )
    v4[i] = v5[i];
  LastError = 0;
  v11 = (_DWORD)v4 - (_DWORD)v6;
  *(_QWORD *)(a1 + 24) += v11;
  if ( SetFilePointer(*(HANDLE *)a1, *(_QWORD *)(a1 + 24) - *(_DWORD *)(a1 + 16), 0, 0) == -1 )
    LastError = GetLastError();
  if ( !LastError )
  {
    v14 = 0;
    v15 = 0;
    if ( v11 )
    {
      *(_DWORD *)(a1 + 40) += v11;
      while ( (unsigned int)TextLogEnumerateOpenSections(a1, LastError, &v14) )
      {
        if ( v11 > 0 )
        {
          if ( DWORD2(v14) >= a2 )
            DWORD2(v14) += v11;
          if ( HIDWORD(v14) >= a2 )
            HIDWORD(v14) += v11;
        }
        else
        {
          if ( DWORD2(v14) > a2 )
          {
            if ( DWORD2(v14) <= a2 - v11 )
              DWORD2(v14) = a2;
            else
              DWORD2(v14) += v11;
          }
          if ( HIDWORD(v14) > a2 )
          {
            if ( HIDWORD(v14) <= a2 - v11 )
              HIDWORD(v14) = a2;
            else
              HIDWORD(v14) += v11;
          }
        }
        TextLogUpdateSectionTag(a1, &v14, LastError++);
      }
    }
    return 0;
  }
  return LastError;
}

```

## disassembly

```asm
0x18000b5f0  push    rbx
0x18000b5f2  push    rsi
0x18000b5f3  push    rdi
0x18000b5f4  push    r14
0x18000b5f6  sub     rsp, 58h
0x18000b5fa  mov     r14d, edx
0x18000b5fd  mov     rsi, rcx
0x18000b600  cmp     edx, [rcx+28h]
0x18000b603  jnb     loc_18000B785
0x18000b609  mov     ebx, r14d
0x18000b60c  add     rbx, [rcx+10h]
0x18000b610  mov     r9, rbx
0x18000b613  mov     [rsp+78h+var_48], rbx
0x18000b618  mov     r10, rbx
0x18000b61b  mov     rax, [rcx+18h]
0x18000b61f  cmp     r10, rax
0x18000b622  jb      loc_18000B6EA
0x18000b628  sub     eax, r10d
0x18000b62b  xor     r8d, r8d
0x18000b62e  mov     [rsp+78h+var_50], r8d
0x18000b633  cmp     r8d, eax
0x18000b636  jnb     short loc_18000B646
0x18000b638  movzx   ecx, byte ptr [r8+r9]
0x18000b63d  mov     [r8+rbx], cl
0x18000b641  inc     r8d
0x18000b644  jmp     short loc_18000B62E
0x18000b646  xor     edi, edi
0x18000b648  sub     ebx, r10d
0x18000b64b  movsxd  rax, ebx
0x18000b64e  add     [rsi+18h], rax
0x18000b652  mov     rdx, [rsi+18h]
0x18000b656  sub     edx, [rsi+10h]; lDistanceToMove
0x18000b659  xor     r9d, r9d; dwMoveMethod
0x18000b65c  xor     r8d, r8d; lpDistanceToMoveHigh
0x18000b65f  mov     rcx, [rsi]; hFile
0x18000b662  call    cs:__imp_SetFilePointer
0x18000b668  cmp     eax, 0FFFFFFFFh
0x18000b66b  jz      loc_18000B705
0x18000b671  mov     [rsp+78h+var_54], edi
0x18000b675  test    edi, edi
0x18000b677  jnz     loc_18000B76E
0x18000b67d  xorps   xmm0, xmm0
0x18000b680  xor     eax, eax
0x18000b682  movups  [rsp+78h+var_40], xmm0
0x18000b687  mov     [rsp+78h+var_30], eax
0x18000b68b  mov     [rsp+78h+var_58], eax
0x18000b68f  test    ebx, ebx
0x18000b691  jz      short loc_18000B6DF
0x18000b693  add     [rsi+28h], ebx
0x18000b696  mov     [rsp+78h+var_58], edi
0x18000b69a  lea     r8, [rsp+78h+var_40]
0x18000b69f  mov     edx, edi
0x18000b6a1  mov     rcx, rsi
0x18000b6a4  call    TextLogEnumerateOpenSections
0x18000b6a9  test    eax, eax
0x18000b6ab  jz      short loc_18000B6DF
0x18000b6ad  test    ebx, ebx
0x18000b6af  jg      short loc_18000B712
0x18000b6b1  mov     ecx, dword ptr [rsp+78h+var_40+8]
0x18000b6b5  cmp     ecx, r14d
0x18000b6b8  ja      short loc_18000B732
0x18000b6ba  mov     ecx, dword ptr [rsp+78h+var_40+0Ch]
0x18000b6be  cmp     ecx, r14d
0x18000b6c1  ja      loc_18000B750
0x18000b6c7  mov     r8d, edi
0x18000b6ca  lea     rdx, [rsp+78h+var_40]
0x18000b6cf  mov     rcx, rsi
0x18000b6d2  call    TextLogUpdateSectionTag
0x18000b6d7  inc     edi
0x18000b6d9  mov     [rsp+78h+var_58], edi
0x18000b6dd  jmp     short loc_18000B69A
0x18000b6df  xor     edi, edi
0x18000b6e1  mov     [rsp+78h+var_54], edi
0x18000b6e5  jmp     loc_18000B76E
0x18000b6ea  lea     r10, [r9+1]
0x18000b6ee  mov     [rsp+78h+var_48], r10
0x18000b6f3  cmp     byte ptr [r9], 0Ah
0x18000b6f7  mov     r9, r10
0x18000b6fa  jz      loc_18000B628
0x18000b700  jmp     loc_18000B61B
0x18000b705  call    cs:__imp_GetLastError
0x18000b70b  mov     edi, eax
0x18000b70d  jmp     loc_18000B671
0x18000b712  mov     eax, dword ptr [rsp+78h+var_40+8]
0x18000b716  cmp     eax, r14d
0x18000b719  jb      short loc_18000B721
0x18000b71b  add     eax, ebx
0x18000b71d  mov     dword ptr [rsp+78h+var_40+8], eax
0x18000b721  mov     eax, dword ptr [rsp+78h+var_40+0Ch]
0x18000b725  cmp     eax, r14d
0x18000b728  jb      short loc_18000B6C7
0x18000b72a  add     eax, ebx
0x18000b72c  mov     dword ptr [rsp+78h+var_40+0Ch], eax
0x18000b730  jmp     short loc_18000B6C7
0x18000b732  mov     eax, r14d
0x18000b735  sub     eax, ebx
0x18000b737  cmp     ecx, eax
0x18000b739  jbe     short loc_18000B746
0x18000b73b  add     ecx, ebx
0x18000b73d  mov     dword ptr [rsp+78h+var_40+8], ecx
0x18000b741  jmp     loc_18000B6BA
0x18000b746  mov     dword ptr [rsp+78h+var_40+8], r14d
0x18000b74b  jmp     loc_18000B6BA
0x18000b750  mov     eax, r14d
0x18000b753  sub     eax, ebx
0x18000b755  cmp     ecx, eax
0x18000b757  jbe     short loc_18000B764
0x18000b759  add     ecx, ebx
0x18000b75b  mov     dword ptr [rsp+78h+var_40+0Ch], ecx
0x18000b75f  jmp     loc_18000B6C7
0x18000b764  mov     dword ptr [rsp+78h+var_40+0Ch], r14d
0x18000b769  jmp     loc_18000B6C7
0x18000b76e  jmp     short loc_18000B779
0x18000b770  mov     edi, 0Dh
0x18000b775  mov     [rsp+78h+var_54], edi
0x18000b779  mov     eax, edi
0x18000b77b  add     rsp, 58h
0x18000b77f  pop     r14
0x18000b781  pop     rdi
0x18000b782  pop     rsi
0x18000b783  pop     rbx
0x18000b784  retn
0x18000b785  mov     eax, 57h ; 'W'
0x18000b78a  jmp     short loc_18000B77B
```
