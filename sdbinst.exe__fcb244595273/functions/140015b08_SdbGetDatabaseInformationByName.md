# SdbGetDatabaseInformationByName

- ea: `0x140015b08`
- end: `0x140015cb3`
- name: `SdbGetDatabaseInformationByName`
- size: `427`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x140017ef8`

## callees

- `0x140002212`
- `0x14001008c`
- `0x140015934`
- `0x140015b08`
- `0x140015cbc`
- `0x140016198`
- `0x14002e420`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x140015bf8`
- `ntdll!RtlAllocateHeap` at `0x140015bf8`
- `ntdll!RtlFreeHeap` at `0x140015c85`
- `ntdll!RtlFreeHeap` at `0x140015c85`

## string_xrefs

- `0x140015b58`: `Error opening database file "%ws"`

## pseudocode

```c
__int64 __fastcall SdbGetDatabaseInformationByName(__int64 a1, _QWORD *a2)
{
  __int64 v4; // rax
  _QWORD *v5; // rbp
  unsigned int v7; // esi
  void *v8; // rbx
  const void *v9; // rdi
  unsigned int v10; // eax
  __int64 v11; // rax
  size_t v12; // r14
  _OWORD *Heap; // rax
  __int128 v14; // xmm1
  __int128 v15; // xmm0
  __int128 v16; // [rsp+30h] [rbp-68h] BYREF
  void *Src[2]; // [rsp+40h] [rbp-58h]
  __int128 v18; // [rsp+50h] [rbp-48h]

  v16 = 0;
  *(_OWORD *)Src = 0;
  v18 = 0;
  v4 = SdbOpenDatabaseEx(a1, a2, 0);
  v5 = (_QWORD *)v4;
  if ( v4 )
  {
    v7 = 0;
    if ( (unsigned int)SdbGetDatabaseInformationEx(v4, &v16) )
    {
      v9 = Src[0];
      v10 = 0;
      if ( Src[0] )
      {
        v11 = -1;
        do
          ++v11;
        while ( *((_WORD *)Src[0] + v11) );
        v10 = 2 * v11 + 2;
      }
      v12 = v10;
      Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, v10 + 48LL);
      v8 = Heap;
      if ( Heap )
      {
        v14 = *(_OWORD *)Src;
        *Heap = v16;
        v15 = v18;
        Heap[1] = v14;
        Heap[2] = v15;
        *(_DWORD *)Heap |= 0x10000000u;
        if ( v9 )
        {
          *((_QWORD *)Heap + 2) = Heap + 3;
          memmove_0(Heap + 3, v9, v12);
        }
        *a2 = v8;
        v7 = 1;
      }
      else
      {
        AslLogCallPrintf(1, "SdbGetDatabaseInformationByName", 701, "Error allocating database information");
      }
    }
    else
    {
      v8 = 0;
      AslLogCallPrintf(
        1,
        "SdbGetDatabaseInformationByName",
        691,
        "Error Retrieving Database information for \"%ws\"",
        a1);
    }
    SdbCloseDatabaseRead(v5);
    if ( !v7 )
    {
      if ( v8 )
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v8);
    }
    return v7;
  }
  else
  {
    AslLogCallPrintf(1, "SdbGetDatabaseInformationByName", 683, "Error opening database file \"%ws\"", a1);
    return 0;
  }
}

```

## disassembly

```asm
0x140015b08  mov     [rsp+arg_10], rbx
0x140015b0d  mov     [rsp+arg_18], rbp
0x140015b12  push    rsi
0x140015b13  push    rdi
0x140015b14  push    r12
0x140015b16  push    r14
0x140015b18  push    r15
0x140015b1a  sub     rsp, 70h
0x140015b1e  mov     rax, cs:__security_cookie
0x140015b25  xor     rax, rsp
0x140015b28  mov     [rsp+98h+var_38], rax
0x140015b2d  xorps   xmm0, xmm0
0x140015b30  xor     r8d, r8d
0x140015b33  movups  [rsp+98h+var_68], xmm0
0x140015b38  mov     r15, rdx
0x140015b3b  mov     rdi, rcx
0x140015b3e  movups  xmmword ptr [rsp+98h+Src], xmm0
0x140015b43  movups  [rsp+98h+var_48], xmm0
0x140015b48  call    SdbOpenDatabaseEx
0x140015b4d  xor     r12d, r12d
0x140015b50  mov     rbp, rax
0x140015b53  test    rax, rax
0x140015b56  jnz     short loc_140015B80
0x140015b58  lea     r9, aErrorOpeningDa_0; "Error opening database file \"%ws\""
0x140015b5f  mov     [rsp+98h+var_78], rdi
0x140015b64  mov     r8d, 2ABh
0x140015b6a  lea     rdx, aSdbgetdatabase; "SdbGetDatabaseInformationByName"
0x140015b71  lea     ecx, [rax+1]
0x140015b74  call    AslLogCallPrintf
0x140015b79  xor     eax, eax
0x140015b7b  jmp     loc_140015C8D
0x140015b80  lea     rdx, [rsp+98h+var_68]
0x140015b85  mov     rcx, rbp
0x140015b88  mov     esi, r12d
0x140015b8b  call    SdbGetDatabaseInformationEx
0x140015b90  test    eax, eax
0x140015b92  jnz     short loc_140015BBD
0x140015b94  lea     r9, aErrorRetrievin; "Error Retrieving Database information f"...
0x140015b9b  mov     [rsp+98h+var_78], rdi
0x140015ba0  mov     r8d, 2B3h
0x140015ba6  lea     rdx, aSdbgetdatabase; "SdbGetDatabaseInformationByName"
0x140015bad  lea     ecx, [rax+1]
0x140015bb0  mov     rbx, r12
0x140015bb3  call    AslLogCallPrintf
0x140015bb8  jmp     loc_140015C62
0x140015bbd  mov     rdi, [rsp+98h+Src]
0x140015bc2  mov     eax, r12d
0x140015bc5  test    rdi, rdi
0x140015bc8  jz      short loc_140015BDF
0x140015bca  or      rax, 0FFFFFFFFFFFFFFFFh
0x140015bce  inc     rax
0x140015bd1  cmp     [rdi+rax*2], r12w
0x140015bd6  jnz     short loc_140015BCE
0x140015bd8  lea     eax, ds:2[rax*2]
0x140015bdf  mov     rcx, gs:60h
0x140015be8  mov     edx, 8; Flags
0x140015bed  mov     r14d, eax
0x140015bf0  mov     rcx, [rcx+30h]; HeapHandle
0x140015bf4  lea     r8, [r14+30h]; Size
0x140015bf8  call    cs:__imp_RtlAllocateHeap
0x140015bfe  mov     rbx, rax
0x140015c01  test    rax, rax
0x140015c04  jnz     short loc_140015C24
0x140015c06  lea     r9, aErrorAllocatin; "Error allocating database information"
0x140015c0d  mov     r8d, 2BDh
0x140015c13  lea     rdx, aSdbgetdatabase; "SdbGetDatabaseInformationByName"
0x140015c1a  lea     ecx, [rax+1]
0x140015c1d  call    AslLogCallPrintf
0x140015c22  jmp     short loc_140015C62
0x140015c24  movups  xmm0, [rsp+98h+var_68]
0x140015c29  movups  xmm1, xmmword ptr [rsp+98h+Src]
0x140015c2e  movups  xmmword ptr [rax], xmm0
0x140015c31  movups  xmm0, [rsp+98h+var_48]
0x140015c36  movups  xmmword ptr [rax+10h], xmm1
0x140015c3a  movups  xmmword ptr [rax+20h], xmm0
0x140015c3e  bts     dword ptr [rax], 1Ch
0x140015c42  test    rdi, rdi
0x140015c45  jz      short loc_140015C5A
0x140015c47  lea     rcx, [rax+30h]; void *
0x140015c4b  mov     r8, r14; Size
0x140015c4e  mov     rdx, rdi; Src
0x140015c51  mov     [rax+10h], rcx
0x140015c55  call    memmove_0
0x140015c5a  mov     [r15], rbx
0x140015c5d  mov     esi, 1
0x140015c62  mov     rcx, rbp
0x140015c65  call    SdbCloseDatabaseRead
0x140015c6a  test    esi, esi
0x140015c6c  jnz     short loc_140015C8B
0x140015c6e  test    rbx, rbx
0x140015c71  jz      short loc_140015C8B
0x140015c73  mov     rcx, gs:60h
0x140015c7c  mov     r8, rbx; P
0x140015c7f  xor     edx, edx; Flags
0x140015c81  mov     rcx, [rcx+30h]; HeapHandle
0x140015c85  call    cs:__imp_RtlFreeHeap
0x140015c8b  mov     eax, esi
0x140015c8d  mov     rcx, [rsp+98h+var_38]
0x140015c92  xor     rcx, rsp; StackCookie
0x140015c95  call    __security_check_cookie
0x140015c9a  lea     r11, [rsp+98h+var_28]
0x140015c9f  mov     rbx, [r11+40h]
0x140015ca3  mov     rbp, [r11+48h]
0x140015ca7  mov     rsp, r11
0x140015caa  pop     r15
0x140015cac  pop     r14
0x140015cae  pop     r12
0x140015cb0  pop     rdi
0x140015cb1  pop     rsi
0x140015cb2  retn
```
