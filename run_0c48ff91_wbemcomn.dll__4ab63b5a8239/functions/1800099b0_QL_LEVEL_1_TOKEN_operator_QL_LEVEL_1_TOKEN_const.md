# QL_LEVEL_1_TOKEN::operator=(QL_LEVEL_1_TOKEN const &)

- ea: `0x1800099b0`
- end: `0x180009c36`
- name: `??4QL_LEVEL_1_TOKEN@@QEAAAEAU0@AEBU0@@Z`
- size: `646`
- prototype: ``
- caller_count: `5`
- callee_count: `8`
- tags: ``

## callers

- `0x180008730`
- `0x180023ec0`
- `0x180024030`
- `0x180036850`
- `0x1800370b0`

## callees

- `0x1800099b0`
- `0x180009c40`
- `0x180009e20`
- `0x180009f40`
- `0x18000ab30`
- `0x180014120`
- `0x18002ca74`
- `0x18002ee7c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180009a1b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180009a1b`
- `OLEAUT32!__imp_VariantCopy` at `0x1800099cb`
- `OLEAUT32!__imp_VariantCopy` at `0x1800099cb`

## pseudocode

```c
__int64 __fastcall QL_LEVEL_1_TOKEN::operator=(__int64 a1, __int64 a2)
{
  _DWORD *v4; // rbx
  SIZE_T v5; // rax
  LPVOID v6; // rax
  int v7; // ebp
  __int64 v8; // rax
  __int64 v9; // rdi
  void *v11; // rcx
  char pExceptionObject; // [rsp+60h] [rbp+8h] BYREF

  if ( VariantCopy((VARIANTARG *)(a1 + 48), (const VARIANTARG *)(a2 + 48)) < 0 )
  {
    CMemoryLog::Write((CMemoryLog *)&unk_18006A9C0, 0xFFFFFFFE);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        27,
        &WPP_2122daa7e8023666a1921e333e1159b1_Traceguids,
        "CX_MemoryException()");
    }
    throw (CX_MemoryException *)&pExceptionObject;
  }
  v4 = (_DWORD *)(a1 + 8);
  *(_DWORD *)a1 = *(_DWORD *)a2;
  CPropertyName::Empty((CPropertyName *)(a1 + 8));
  if ( *(int *)(a2 + 8) > 0 )
  {
    v5 = 16LL * *(int *)(a2 + 8);
    if ( !is_mul_ok(*(int *)(a2 + 8), 0x10u) )
      v5 = -1;
    if ( hHeap )
      v6 = HeapAlloc(hHeap, 0, v5);
    else
      v6 = 0;
    *(_QWORD *)(a1 + 16) = v6;
    if ( !v6 )
    {
      CMemoryLog::Write((CMemoryLog *)&unk_18006A9C0, 0xFFFFFFFE);
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_s(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          11,
          &WPP_2122daa7e8023666a1921e333e1159b1_Traceguids,
          "CX_MemoryException()");
      }
      throw (CX_MemoryException *)&pExceptionObject;
    }
  }
  v7 = 0;
  for ( *(_DWORD *)(a1 + 24) = *(_DWORD *)(a2 + 8);
        v7 < *(_DWORD *)(a2 + 8);
        *(_WORD *)(*(_QWORD *)(a1 + 16) + 8 * v9) = *(_WORD *)(*(_QWORD *)(a2 + 16) + 8 * v9) )
  {
    v8 = *(_QWORD *)(a2 + 16);
    v9 = 2LL * v7;
    if ( *(_WORD *)(v8 + 16LL * v7) )
    {
      *(_DWORD *)(*(_QWORD *)(a1 + 16) + 16LL * v7 + 8) = *(_DWORD *)(v8 + 16LL * v7 + 8);
    }
    else
    {
      *(_QWORD *)(*(_QWORD *)(a1 + 16) + 16LL * v7 + 8) = WbemStringCopy(*(const unsigned __int16 **)(v8 + 16LL * v7 + 8));
      if ( !*(_QWORD *)(*(_QWORD *)(a1 + 16) + 16LL * v7 + 8) )
        break;
    }
    ++v7;
  }
  *v4 = v7;
  if ( v7 != *(_DWORD *)(a2 + 8) )
  {
    v11 = *(void **)(a1 + 16);
    if ( v11 )
    {
      CMUILocale::_Free(v11);
      *v4 = 0;
      *(_DWORD *)(a1 + 24) = 0;
      *(_QWORD *)(a1 + 16) = 0;
    }
    CMemoryLog::Write((CMemoryLog *)&unk_18006A9C0, 0xFFFFFFFE);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        12,
        &WPP_2122daa7e8023666a1921e333e1159b1_Traceguids,
        "CX_MemoryException()");
    }
    throw (CX_MemoryException *)&pExceptionObject;
  }
  *(_QWORD *)(a1 + 32) = *(_QWORD *)(a2 + 32);
  if ( *(_DWORD *)(a2 + 112) )
  {
    CPropertyName::operator=(a1 + 80, a2 + 80);
    *(_QWORD *)(a1 + 104) = *(_QWORD *)(a2 + 104);
  }
  *(_DWORD *)(a1 + 40) = *(_DWORD *)(a2 + 40);
  *(_DWORD *)(a1 + 116) = *(_DWORD *)(a2 + 116);
  *(_DWORD *)(a1 + 120) = *(_DWORD *)(a2 + 120);
  *(_DWORD *)(a1 + 72) = *(_DWORD *)(a2 + 72);
  *(_DWORD *)(a1 + 112) = *(_DWORD *)(a2 + 112);
  return a1;
}

```

## disassembly

```asm
0x1800099b0  push    rbx
0x1800099b2  push    rbp
0x1800099b3  push    rsi
0x1800099b4  push    rdi
0x1800099b5  push    r14
0x1800099b7  push    r15
0x1800099b9  sub     rsp, 28h
0x1800099bd  mov     rsi, rdx
0x1800099c0  mov     r14, rcx
0x1800099c3  add     rdx, 30h ; '0'; pvargSrc
0x1800099c7  add     rcx, 30h ; '0'; pvargDest
0x1800099cb  call    cs:__imp_VariantCopy
0x1800099d1  xor     r15d, r15d
0x1800099d4  test    eax, eax
0x1800099d6  js      loc_180009AEA
0x1800099dc  mov     eax, [rsi]
0x1800099de  lea     rbx, [r14+8]
0x1800099e2  mov     rcx, rbx; this
0x1800099e5  mov     [r14], eax
0x1800099e8  call    ?Empty@CPropertyName@@QEAAXXZ; CPropertyName::Empty(void)
0x1800099ed  cmp     [rsi+8], r15d
0x1800099f1  jle     short loc_180009A2E
0x1800099f3  movsxd  rcx, dword ptr [rsi+8]
0x1800099f7  lea     eax, [r15+10h]
0x1800099fb  mul     rcx
0x1800099fe  lea     rcx, [r15-1]
0x180009a02  cmovb   rax, rcx
0x180009a06  mov     rcx, cs:hHeap; hHeap
0x180009a0d  test    rcx, rcx
0x180009a10  jz      loc_180009B48
0x180009a16  mov     r8, rax; dwBytes
0x180009a19  xor     edx, edx; dwFlags
0x180009a1b  call    cs:__imp_HeapAlloc
0x180009a21  mov     [rbx+8], rax
0x180009a25  test    rax, rax
0x180009a28  jz      loc_180009B50
0x180009a2e  mov     eax, [rsi+8]
0x180009a31  mov     ebp, r15d
0x180009a34  mov     [rbx+10h], eax
0x180009a37  cmp     [rsi+8], r15d
0x180009a3b  jle     short loc_180009A87
0x180009a3d  mov     rax, [rsi+10h]
0x180009a41  movsxd  rdi, ebp
0x180009a44  add     rdi, rdi
0x180009a47  cmp     [rax+rdi*8], r15w
0x180009a4c  jnz     loc_180009BAE
0x180009a52  mov     rcx, [rax+rdi*8+8]; unsigned __int16 *
0x180009a57  call    ?WbemStringCopy@@YAPEAGPEBG@Z; WbemStringCopy(ushort const *)
0x180009a5c  mov     rcx, [rbx+8]
0x180009a60  mov     [rcx+rdi*8+8], rax
0x180009a65  mov     rax, [rbx+8]
0x180009a69  cmp     [rax+rdi*8+8], r15
0x180009a6e  jz      short loc_180009A87
0x180009a70  mov     rax, [rsi+10h]
0x180009a74  inc     ebp
0x180009a76  mov     rcx, [rbx+8]
0x180009a7a  movzx   eax, word ptr [rax+rdi*8]
0x180009a7e  mov     [rcx+rdi*8], ax
0x180009a82  cmp     ebp, [rsi+8]
0x180009a85  jl      short loc_180009A3D
0x180009a87  mov     [rbx], ebp
0x180009a89  cmp     ebp, [rsi+8]
0x180009a8c  jnz     loc_180009BBF
0x180009a92  mov     rax, [rsi+20h]
0x180009a96  mov     [rbx+18h], rax
0x180009a9a  cmp     [rsi+70h], r15d
0x180009a9e  jnz     short loc_180009AD3
0x180009aa0  mov     eax, [rsi+28h]
0x180009aa3  mov     [r14+28h], eax
0x180009aa7  mov     eax, [rsi+74h]
0x180009aaa  mov     [r14+74h], eax
0x180009aae  mov     eax, [rsi+78h]
0x180009ab1  mov     [r14+78h], eax
0x180009ab5  mov     eax, [rsi+48h]
0x180009ab8  mov     [r14+48h], eax
0x180009abc  mov     eax, [rsi+70h]
0x180009abf  mov     [r14+70h], eax
0x180009ac3  mov     rax, r14
0x180009ac6  add     rsp, 28h
0x180009aca  pop     r15
0x180009acc  pop     r14
0x180009ace  pop     rdi
0x180009acf  pop     rsi
0x180009ad0  pop     rbp
0x180009ad1  pop     rbx
0x180009ad2  retn
0x180009ad3  lea     rdx, [rsi+50h]
0x180009ad7  lea     rcx, [r14+50h]
0x180009adb  call    ??4CPropertyName@@QEAAXAEBU_tag_WbemPropertyName@@@Z; CPropertyName::operator=(_tag_WbemPropertyName const &)
0x180009ae0  mov     rax, [rsi+68h]
0x180009ae4  mov     [r14+68h], rax
0x180009ae8  jmp     short loc_180009AA0
0x180009aea  mov     edx, 0FFFFFFFEh; int
0x180009aef  lea     rcx, unk_18006A9C0; this
0x180009af6  call    ?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180009afb  mov     rcx, cs:WPP_GLOBAL_Control
0x180009b02  lea     rax, WPP_GLOBAL_Control
0x180009b09  cmp     rcx, rax
0x180009b0c  jz      short loc_180009B36
0x180009b0e  test    byte ptr [rcx+1Ch], 1
0x180009b12  jz      short loc_180009B36
0x180009b14  cmp     byte ptr [rcx+19h], 2
0x180009b18  jb      short loc_180009B36
0x180009b1a  mov     rcx, [rcx+10h]
0x180009b1e  lea     r9, aCxMemoryexcept; "CX_MemoryException()"
0x180009b25  mov     edx, 1Bh
0x180009b2a  lea     r8, WPP_2122daa7e8023666a1921e333e1159b1_Traceguids
0x180009b31  call    WPP_SF_s
0x180009b36  lea     rdx, _TI2?AVCX_MemoryException@@; pThrowInfo
0x180009b3d  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x180009b42  call    _CxxThrowException_0
0x180009b48  mov     rax, r15
0x180009b4b  jmp     loc_180009A21
0x180009b50  mov     edx, 0FFFFFFFEh; int
0x180009b55  lea     rcx, unk_18006A9C0; this
0x180009b5c  call    ?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180009b61  mov     rcx, cs:WPP_GLOBAL_Control
0x180009b68  lea     rax, WPP_GLOBAL_Control
0x180009b6f  cmp     rcx, rax
0x180009b72  jz      short loc_180009B9C
0x180009b74  test    byte ptr [rcx+1Ch], 1
0x180009b78  jz      short loc_180009B9C
0x180009b7a  cmp     byte ptr [rcx+19h], 2
0x180009b7e  jb      short loc_180009B9C
0x180009b80  mov     rcx, [rcx+10h]
0x180009b84  lea     r9, aCxMemoryexcept; "CX_MemoryException()"
0x180009b8b  mov     edx, 0Bh
0x180009b90  lea     r8, WPP_2122daa7e8023666a1921e333e1159b1_Traceguids
0x180009b97  call    WPP_SF_s
0x180009b9c  lea     rdx, _TI2?AVCX_MemoryException@@; pThrowInfo
0x180009ba3  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x180009ba8  call    _CxxThrowException_0
0x180009bae  mov     rcx, [rbx+8]
0x180009bb2  mov     eax, [rax+rdi*8+8]
0x180009bb6  mov     [rcx+rdi*8+8], eax
0x180009bba  jmp     loc_180009A70
0x180009bbf  mov     rcx, [rbx+8]; void *
0x180009bc3  test    rcx, rcx
0x180009bc6  jz      short loc_180009BD8
0x180009bc8  call    ?_Free@CMUILocale@@SAHPEAX@Z; CMUILocale::_Free(void *)
0x180009bcd  mov     [rbx], r15d
0x180009bd0  mov     [rbx+10h], r15d
0x180009bd4  mov     [rbx+8], r15
0x180009bd8  mov     edx, 0FFFFFFFEh; int
0x180009bdd  lea     rcx, unk_18006A9C0; this
0x180009be4  call    ?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180009be9  mov     rcx, cs:WPP_GLOBAL_Control
0x180009bf0  lea     rax, WPP_GLOBAL_Control
0x180009bf7  cmp     rcx, rax
0x180009bfa  jz      short loc_180009C24
0x180009bfc  test    byte ptr [rcx+1Ch], 1
0x180009c00  jz      short loc_180009C24
0x180009c02  cmp     byte ptr [rcx+19h], 2
0x180009c06  jb      short loc_180009C24
0x180009c08  mov     rcx, [rcx+10h]
0x180009c0c  lea     r9, aCxMemoryexcept; "CX_MemoryException()"
0x180009c13  mov     edx, 0Ch
0x180009c18  lea     r8, WPP_2122daa7e8023666a1921e333e1159b1_Traceguids
0x180009c1f  call    WPP_SF_s
0x180009c24  lea     rdx, _TI2?AVCX_MemoryException@@; pThrowInfo
0x180009c2b  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x180009c30  call    _CxxThrowException_0
```
