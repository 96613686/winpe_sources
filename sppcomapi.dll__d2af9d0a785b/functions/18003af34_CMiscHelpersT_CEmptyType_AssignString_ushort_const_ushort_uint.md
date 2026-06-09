# CMiscHelpersT<CEmptyType>::AssignString(ushort const *,ushort * *,uint)

- ea: `0x18003af34`
- end: `0x18003b0e2`
- name: `?AssignString@?$CMiscHelpersT@VCEmptyType@@@@SAJPEBGPEAPEAGI@Z`
- size: `430`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x180005810`
- `0x18003b714`
- `0x18003b878`

## callees

- `0x180003520`
- `0x180004288`
- `0x18003af34`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003b0c2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003b0c2`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003b028`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003b028`

## pseudocode

```c
__int64 __fastcall CMiscHelpersT<CEmptyType>::AssignString(_WORD *a1, _QWORD *a2, unsigned int a3)
{
  _WORD *v4; // r14
  unsigned int v5; // r15d
  _WORD *v6; // rax
  unsigned __int64 i; // rcx
  int v8; // ebp
  int v9; // ebx
  unsigned __int64 v10; // rdx
  unsigned __int64 v11; // rdx
  unsigned __int64 v12; // rdi
  unsigned __int64 v13; // rdx
  unsigned int v14; // esi
  _WORD *v15; // rdi
  int v16; // ecx
  _WORD *v17; // rax
  unsigned __int64 v18; // rsi
  __int64 v19; // rcx
  _WORD *v20; // rdx

  v4 = a1;
  v5 = 0;
  if ( a1 )
  {
    v6 = a1;
    for ( i = (unsigned __int64)a3 >> 1; i; --i )
    {
      if ( !*v6 )
        break;
      ++v6;
    }
    v8 = -2147024809;
    v9 = i == 0 ? 0x80070057 : 0;
    if ( i )
      v10 = ((unsigned __int64)a3 >> 1) - i;
    else
      v10 = 0;
    if ( i )
    {
      v11 = 2 * v10;
      v12 = v11 + 2;
      if ( v11 + 2 < v11 )
      {
        v9 = -2147024362;
        CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(-2147024362);
        v12 = v13;
      }
      else
      {
        v9 = 0;
      }
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v9);
      if ( v9 >= 0 )
      {
        v14 = v12;
        if ( v12 == (unsigned int)v12 )
        {
          CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
          v9 = 0;
        }
        else
        {
          v14 = 0;
          v9 = -2147024362;
          CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(-2147024362);
        }
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v9);
        if ( v9 >= 0 )
        {
          v5 = v14;
          goto LABEL_20;
        }
      }
    }
  }
  else
  {
    v8 = -2147024809;
    v9 = -2147024809;
  }
  CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v9);
LABEL_20:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v9);
  if ( v9 >= 0 )
  {
    v17 = LocalAlloc(0x40u, v5);
    v15 = v17;
    if ( !v17 )
    {
      v9 = -2147024882;
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(-2147024882);
      v15 = 0;
      goto LABEL_37;
    }
    v18 = (unsigned __int64)v5 >> 1;
    if ( v18 )
    {
      v19 = 2147483646;
      do
      {
        if ( !v19 )
          break;
        if ( !*v4 )
          break;
        *v15++ = *v4++;
        --v19;
        --v18;
      }
      while ( v18 );
      v20 = v15 - 1;
      if ( v18 )
        v20 = v15;
      *v20 = 0;
      v9 = v18 == 0 ? 0x8007007A : 0;
      if ( v18 )
      {
        v15 = 0;
        *a2 = v17;
        goto LABEL_37;
      }
      v15 = v17;
      v8 = -2147024774;
    }
    else
    {
      v9 = -2147024809;
    }
    v16 = v8;
  }
  else
  {
    v15 = 0;
    v16 = v9;
  }
  CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v16);
LABEL_37:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v9);
  if ( v15 )
    LocalFree(v15);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18003af34  push    rbx
0x18003af36  push    rbp
0x18003af37  push    rsi
0x18003af38  push    rdi
0x18003af39  push    r12
0x18003af3b  push    r13
0x18003af3d  push    r14
0x18003af3f  push    r15
0x18003af41  sub     rsp, 28h
0x18003af45  xor     r13d, r13d
0x18003af48  mov     r12, rdx
0x18003af4b  mov     r14, rcx
0x18003af4e  mov     r15d, r13d
0x18003af51  test    rcx, rcx
0x18003af54  jz      loc_18003AFFA
0x18003af5a  mov     ecx, r8d
0x18003af5d  mov     rax, r14
0x18003af60  shr     rcx, 1
0x18003af63  mov     rdx, rcx
0x18003af66  jz      short loc_18003AF78
0x18003af68  cmp     [rax], r13w
0x18003af6c  jz      short loc_18003AF78
0x18003af6e  add     rax, 2
0x18003af72  sub     rcx, 1
0x18003af76  jnz     short loc_18003AF68
0x18003af78  mov     rax, rcx
0x18003af7b  mov     ebp, 80070057h
0x18003af80  neg     rax
0x18003af83  sbb     ebx, ebx
0x18003af85  not     ebx
0x18003af87  and     ebx, ebp
0x18003af89  test    rcx, rcx
0x18003af8c  jz      short loc_18003AF93
0x18003af8e  sub     rdx, rcx
0x18003af91  jmp     short loc_18003AF96
0x18003af93  mov     rdx, r13
0x18003af96  test    rcx, rcx
0x18003af99  jz      short loc_18003B001
0x18003af9b  add     rdx, rdx
0x18003af9e  mov     eax, 80070216h
0x18003afa3  lea     rdi, [rdx+2]
0x18003afa7  cmp     rdi, rdx
0x18003afaa  jb      short loc_18003AFB1
0x18003afac  mov     ebx, r13d
0x18003afaf  jmp     short loc_18003AFBD
0x18003afb1  mov     ecx, eax
0x18003afb3  mov     ebx, eax
0x18003afb5  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18003afba  mov     rdi, rdx
0x18003afbd  mov     ecx, ebx
0x18003afbf  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18003afc4  test    ebx, ebx
0x18003afc6  js      short loc_18003B001
0x18003afc8  mov     esi, edi
0x18003afca  cmp     rdi, rsi
0x18003afcd  jz      short loc_18003AFE0
0x18003afcf  mov     ecx, 80070216h
0x18003afd4  mov     esi, r13d
0x18003afd7  mov     ebx, ecx
0x18003afd9  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18003afde  jmp     short loc_18003AFEA
0x18003afe0  xor     ecx, ecx
0x18003afe2  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18003afe7  mov     ebx, r13d
0x18003afea  mov     ecx, ebx
0x18003afec  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18003aff1  test    ebx, ebx
0x18003aff3  js      short loc_18003B001
0x18003aff5  mov     r15d, esi
0x18003aff8  jmp     short loc_18003B008
0x18003affa  mov     ebp, 80070057h
0x18003afff  mov     ebx, ebp
0x18003b001  mov     ecx, ebx
0x18003b003  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18003b008  mov     ecx, ebx
0x18003b00a  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18003b00f  test    ebx, ebx
0x18003b011  jns     short loc_18003B01D
0x18003b013  mov     rdi, r13
0x18003b016  mov     ecx, ebx
0x18003b018  jmp     loc_18003B0AE
0x18003b01d  mov     edx, r15d; uBytes
0x18003b020  mov     ecx, 40h ; '@'; uFlags
0x18003b025  mov     esi, r15d
0x18003b028  call    cs:__imp_LocalAlloc
0x18003b02f  nop     dword ptr [rax+rax+00h]
0x18003b034  mov     rdi, rax
0x18003b037  test    rax, rax
0x18003b03a  jnz     short loc_18003B04D
0x18003b03c  mov     ebx, 8007000Eh
0x18003b041  mov     ecx, ebx
0x18003b043  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18003b048  mov     rdi, r13
0x18003b04b  jmp     short loc_18003B0B3
0x18003b04d  shr     rsi, 1
0x18003b050  jz      short loc_18003B0AA
0x18003b052  mov     ecx, 7FFFFFFEh
0x18003b057  test    rcx, rcx
0x18003b05a  jz      short loc_18003B079
0x18003b05c  movzx   edx, word ptr [r14]
0x18003b060  test    dx, dx
0x18003b063  jz      short loc_18003B079
0x18003b065  mov     [rdi], dx
0x18003b068  add     r14, 2
0x18003b06c  add     rdi, 2
0x18003b070  dec     rcx
0x18003b073  sub     rsi, 1
0x18003b077  jnz     short loc_18003B057
0x18003b079  mov     rcx, rsi
0x18003b07c  lea     rdx, [rdi-2]
0x18003b080  neg     rcx
0x18003b083  sbb     ebx, ebx
0x18003b085  test    rsi, rsi
0x18003b088  not     ebx
0x18003b08a  cmovnz  rdx, rdi
0x18003b08e  mov     [rdx], r13w
0x18003b092  and     ebx, 8007007Ah
0x18003b098  jns     short loc_18003B0A1
0x18003b09a  mov     rdi, rax
0x18003b09d  mov     ebp, ebx
0x18003b09f  jmp     short loc_18003B0AC
0x18003b0a1  mov     rdi, r13
0x18003b0a4  mov     [r12], rax
0x18003b0a8  jmp     short loc_18003B0B3
0x18003b0aa  mov     ebx, ebp
0x18003b0ac  mov     ecx, ebp
0x18003b0ae  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18003b0b3  mov     ecx, ebx
0x18003b0b5  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18003b0ba  test    rdi, rdi
0x18003b0bd  jz      short loc_18003B0CE
0x18003b0bf  mov     rcx, rdi; hMem
0x18003b0c2  call    cs:__imp_LocalFree
0x18003b0c9  nop     dword ptr [rax+rax+00h]
0x18003b0ce  mov     eax, ebx
0x18003b0d0  add     rsp, 28h
0x18003b0d4  pop     r15
0x18003b0d6  pop     r14
0x18003b0d8  pop     r13
0x18003b0da  pop     r12
0x18003b0dc  pop     rdi
0x18003b0dd  pop     rsi
0x18003b0de  pop     rbp
0x18003b0df  pop     rbx
0x18003b0e0  retn
```
