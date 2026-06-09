# YReader::ParseDeclAttlistType(DeclAttDef *)

- ea: `0x100405a00`
- end: `0x100405c6c`
- name: `?ParseDeclAttlistType@YReader@@AEAAXPEAVDeclAttDef@@@Z`
- size: `620`
- prototype: `void __fastcall(YReader *__hidden this, struct DeclAttDef *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x100405110`

## callees

- `0x100401780`
- `0x1004018f0`
- `0x100401ab0`
- `0x1004058d0`
- `0x100405a00`
- `0x10040a020`
- `0x100415490`
- `0x100439df0`

## pseudocode

```c
void __fastcall YReader::ParseDeclAttlistType(YReader *this, struct DeclAttDef *a2)
{
  __int128 v4; // xmm0
  int v5; // ebp
  signed int v6; // ebp
  char *v7; // rax
  __int64 v8; // rcx
  char *v9; // rax
  __int64 v10; // rcx
  char *v11; // [rsp+20h] [rbp-18h] BYREF
  int v12; // [rsp+28h] [rbp-10h]

  v11 = 0;
  v12 = 0;
  switch ( (unsigned int)YReader::GetTokenDeclInner(this) )
  {
    case 0x1Du:
      *((_DWORD *)a2 + 43) = 0;
      v4 = CodeStringPtr::CDATA;
      goto LABEL_3;
    case 0x1Eu:
      *((_DWORD *)a2 + 43) = 1;
      v4 = CodeStringPtr::ID;
      goto LABEL_3;
    case 0x1Fu:
      *((_DWORD *)a2 + 43) = 2;
      v4 = CodeStringPtr::IDREF;
      goto LABEL_3;
    case 0x20u:
      *((_DWORD *)a2 + 43) = 3;
      v4 = CodeStringPtr::IDREFS;
      goto LABEL_3;
    case 0x21u:
      *((_DWORD *)a2 + 43) = 4;
      v4 = CodeStringPtr::ENTITY;
      goto LABEL_3;
    case 0x22u:
      *((_DWORD *)a2 + 43) = 5;
      v4 = CodeStringPtr::ENTITIES;
      goto LABEL_3;
    case 0x23u:
      *((_DWORD *)a2 + 43) = 6;
      v4 = CodeStringPtr::NMTOKEN;
      goto LABEL_3;
    case 0x24u:
      *((_DWORD *)a2 + 43) = 7;
      v4 = CodeStringPtr::NMTOKENS;
LABEL_3:
      *((_OWORD *)a2 + 6) = v4;
      break;
    case 0x25u:
      *((_DWORD *)a2 + 43) = 8;
      if ( *((_QWORD *)a2 + 12) )
      {
        if ( *((_DWORD *)a2 + 26) > 0x3FFFFFFFu
          || (_mm_lfence(),
              v5 = 2 * *((_DWORD *)a2 + 26),
              v6 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 13) + 96LL))(*((_QWORD *)this + 13)) + v5,
              v6 < 0) )
        {
          MXRRaiseException(-2147024882);
          __debugbreak();
        }
        _mm_lfence();
        v7 = BlockAlloc::ReallocData((YReader *)((char *)this + 416), *((char **)a2 + 12), v6);
        v8 = *((unsigned int *)a2 + 26);
        *((_QWORD *)a2 + 12) = v7;
        v9 = &v7[2 * v8];
        v10 = *((_QWORD *)this + 13);
        v11 = v9;
        (*(void (__fastcall **)(__int64, char **))(*(_QWORD *)v10 + 104LL))(v10, &v11);
        *((_DWORD *)a2 + 26) += v12;
      }
      else
      {
        _mm_lfence();
        YReader::GetTokenData(this, (struct DeclAttDef *)((char *)a2 + 96));
      }
      _mm_lfence();
      YReader::SetTokenData3(this, 0x4Eu, (struct DeclAttDef *)((char *)a2 + 96));
      YReader::SetTokenData3(this, 0x20u, (struct DeclAttDef *)((char *)a2 + 96));
      if ( (unsigned int)YReader::GetTokenDeclInner(this) != 50 )
      {
        MXRRaiseException(-1072894422);
        __debugbreak();
      }
      _mm_lfence();
      YReader::ParseDeclAttlistEnumeratedType(this, a2);
      break;
    case 0x32u:
      _mm_lfence();
      *((_DWORD *)a2 + 43) = 9;
      YReader::ParseDeclAttlistEnumeratedType(this, a2);
      break;
    default:
      MXRRaiseException(-1072894419);
      __debugbreak();
  }
}

```

## disassembly

```asm
0x100405a00  mov     [rsp+arg_0], rbx
0x100405a05  mov     [rsp+arg_8], rbp
0x100405a0a  mov     [rsp+arg_10], rsi
0x100405a0f  push    rdi
0x100405a10  sub     rsp, 30h
0x100405a14  xor     ebp, ebp
0x100405a16  mov     rdi, rdx
0x100405a19  mov     [rsp+38h+var_18], rbp
0x100405a1e  mov     rsi, rcx
0x100405a21  mov     [rsp+38h+var_10], ebp
0x100405a25  call    ?GetTokenDeclInner@YReader@@AEAAHXZ; YReader::GetTokenDeclInner(void)
0x100405a2a  add     eax, 0FFFFFFE3h; switch 22 cases
0x100405a2d  cmp     eax, 15h
0x100405a30  ja      def_100405A49; jumptable 0000000100405A49 default case, cases 38-49
0x100405a36  lea     rdx, __ImageBase
0x100405a3d  cdqe
0x100405a3f  mov     ecx, ds:(jpt_100405A49 - 100400000h)[rdx+rax*4]
0x100405a46  add     rcx, rdx
0x100405a49  jmp     rcx; switch jump
0x100405a4b  mov     [rdi+0ACh], ebp; jumptable 0000000100405A49 case 29
0x100405a51  movups  xmm0, xmmword ptr cs:?CDATA@CodeStringPtr@@2UStringPtr@@A; StringPtr CodeStringPtr::CDATA
0x100405a58  movups  xmmword ptr [rdi+60h], xmm0
0x100405a5c  mov     rbx, [rsp+38h+arg_0]
0x100405a61  mov     rbp, [rsp+38h+arg_8]
0x100405a66  mov     rsi, [rsp+38h+arg_10]
0x100405a6b  add     rsp, 30h
0x100405a6f  pop     rdi
0x100405a70  retn
0x100405a71  mov     dword ptr [rdi+0ACh], 1; jumptable 0000000100405A49 case 30
0x100405a7b  movups  xmm0, xmmword ptr cs:?ID@CodeStringPtr@@2UStringPtr@@A; StringPtr CodeStringPtr::ID
0x100405a82  jmp     short loc_100405A58
0x100405a84  mov     dword ptr [rdi+0ACh], 2; jumptable 0000000100405A49 case 31
0x100405a8e  movups  xmm0, xmmword ptr cs:?IDREF@CodeStringPtr@@2UStringPtr@@A; StringPtr CodeStringPtr::IDREF
0x100405a95  jmp     short loc_100405A58
0x100405a97  mov     dword ptr [rdi+0ACh], 3; jumptable 0000000100405A49 case 32
0x100405aa1  movups  xmm0, xmmword ptr cs:?IDREFS@CodeStringPtr@@2UStringPtr@@A; StringPtr CodeStringPtr::IDREFS
0x100405aa8  jmp     short loc_100405A58
0x100405aaa  mov     dword ptr [rdi+0ACh], 4; jumptable 0000000100405A49 case 33
0x100405ab4  movups  xmm0, xmmword ptr cs:?ENTITY@CodeStringPtr@@2UStringPtr@@A; StringPtr CodeStringPtr::ENTITY
0x100405abb  jmp     short loc_100405A58
0x100405abd  mov     dword ptr [rdi+0ACh], 5; jumptable 0000000100405A49 case 34
0x100405ac7  movups  xmm0, xmmword ptr cs:?ENTITIES@CodeStringPtr@@2UStringPtr@@A; StringPtr CodeStringPtr::ENTITIES
0x100405ace  jmp     short loc_100405A58
0x100405ad0  mov     dword ptr [rdi+0ACh], 6; jumptable 0000000100405A49 case 35
0x100405ada  movups  xmm0, xmmword ptr cs:?NMTOKEN@CodeStringPtr@@2UStringPtr@@A; StringPtr CodeStringPtr::NMTOKEN
0x100405ae1  jmp     loc_100405A58
0x100405ae6  mov     dword ptr [rdi+0ACh], 7; jumptable 0000000100405A49 case 36
0x100405af0  movups  xmm0, xmmword ptr cs:?NMTOKENS@CodeStringPtr@@2UStringPtr@@A; StringPtr CodeStringPtr::NMTOKENS
0x100405af7  jmp     loc_100405A58
0x100405afc  mov     dword ptr [rdi+0ACh], 8; jumptable 0000000100405A49 case 37
0x100405b06  cmp     [rdi+60h], rbp
0x100405b0a  jnz     short loc_100405B1D
0x100405b0c  lfence
0x100405b0f  lea     rdx, [rdi+60h]; struct StringPtr *
0x100405b13  mov     rcx, rsi; this
0x100405b16  call    ?GetTokenData@YReader@@AEAAXPEAUStringPtr@@@Z; YReader::GetTokenData(StringPtr *)
0x100405b1b  jmp     short loc_100405B8E
0x100405b1d  cmp     dword ptr [rdi+68h], 3FFFFFFFh
0x100405b24  ja      loc_100405C06
0x100405b2a  lfence
0x100405b2d  mov     rcx, [rsi+68h]
0x100405b31  mov     ebp, [rdi+68h]
0x100405b34  add     ebp, ebp
0x100405b36  mov     rax, [rcx]
0x100405b39  mov     rax, [rax+60h]
0x100405b3d  call    cs:__guard_dispatch_icall_fptr
0x100405b43  add     ebp, eax
0x100405b45  js      loc_100405C06
0x100405b4b  lfence
0x100405b4e  mov     rdx, [rdi+60h]; void *
0x100405b52  lea     rcx, [rsi+1A0h]; this
0x100405b59  mov     r8d, ebp; unsigned int
0x100405b5c  call    ?ReallocData@BlockAlloc@@QEAAPEAXPEAXK@Z; BlockAlloc::ReallocData(void *,ulong)
0x100405b61  mov     ecx, [rdi+68h]
0x100405b64  lea     rdx, [rsp+38h+var_18]
0x100405b69  mov     [rdi+60h], rax
0x100405b6d  lea     rax, [rax+rcx*2]
0x100405b71  mov     rcx, [rsi+68h]
0x100405b75  mov     [rsp+38h+var_18], rax
0x100405b7a  mov     rax, [rcx]
0x100405b7d  mov     rax, [rax+68h]
0x100405b81  call    cs:__guard_dispatch_icall_fptr
0x100405b87  mov     eax, [rsp+38h+var_10]
0x100405b8b  add     [rdi+68h], eax
0x100405b8e  lfence
0x100405b91  mov     edx, 4Eh ; 'N'; wchar_t
0x100405b96  lea     r8, [rdi+60h]; struct StringPtr *
0x100405b9a  mov     rcx, rsi; this
0x100405b9d  call    ?SetTokenData3@YReader@@AEAAX_WPEAUStringPtr@@@Z; YReader::SetTokenData3(wchar_t,StringPtr *)
0x100405ba2  mov     edx, 20h ; ' '; wchar_t
0x100405ba7  lea     r8, [rdi+60h]; struct StringPtr *
0x100405bab  mov     rcx, rsi; this
0x100405bae  call    ?SetTokenData3@YReader@@AEAAX_WPEAUStringPtr@@@Z; YReader::SetTokenData3(wchar_t,StringPtr *)
0x100405bb3  mov     rcx, rsi; this
0x100405bb6  call    ?GetTokenDeclInner@YReader@@AEAAHXZ; YReader::GetTokenDeclInner(void)
0x100405bbb  cmp     eax, 32h ; '2'
0x100405bbe  jnz     short loc_100405BFB
0x100405bc0  lfence
0x100405bc3  mov     rdx, rdi; struct DeclAttDef *
0x100405bc6  mov     rcx, rsi; this
0x100405bc9  call    ?ParseDeclAttlistEnumeratedType@YReader@@AEAAXPEAVDeclAttDef@@@Z; YReader::ParseDeclAttlistEnumeratedType(DeclAttDef *)
0x100405bce  jmp     loc_100405A5C
0x100405bd3  lfence; jumptable 0000000100405A49 case 50
0x100405bd6  mov     rdx, rdi; struct DeclAttDef *
0x100405bd9  mov     dword ptr [rdi+0ACh], 9
0x100405be3  mov     rcx, rsi; this
0x100405be6  call    ?ParseDeclAttlistEnumeratedType@YReader@@AEAAXPEAVDeclAttDef@@@Z; YReader::ParseDeclAttlistEnumeratedType(DeclAttDef *)
0x100405beb  jmp     loc_100405A5C
0x100405bf0  mov     ecx, 0C00CEE2Dh; jumptable 0000000100405A49 default case, cases 38-49
0x100405bf5  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
0x100405bfa  int     3; Trap to Debugger
0x100405bfb  mov     ecx, 0C00CEE2Ah; int
0x100405c00  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
0x100405c05  int     3; Trap to Debugger
0x100405c06  mov     ecx, 8007000Eh; int
0x100405c0b  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
0x100405c10  int     3; Trap to Debugger
```
