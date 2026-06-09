# p9fs::Handler::MessageResponse::EnsureSize(p9fs::MessageType,uint,uint)

- ea: `0x180010020`
- end: `0x180010133`
- name: `?EnsureSize@MessageResponse@Handler@p9fs@@QEAAXW4MessageType@3@II@Z`
- size: `275`
- prototype: `void __high(enum p9fs::MessageType, unsigned int, unsigned int)`
- caller_count: `18`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x18001085c`
- `0x180011728`
- `0x1800119dc`
- `0x180011dac`
- `0x18001206c`
- `0x18001238c`
- `0x180012ea8`
- `0x1800130f0`
- `0x1800133e0`
- `0x1800138b0`
- `0x180013b88`
- `0x180014384`
- `0x180014698`
- `0x1800149fc`
- `0x18001572c`
- `0x180015ad0`
- `0x180016310`
- `0x18001bd28`

## callees

- `0x180004c80`
- `0x18000ae8c`
- `0x18000d498`
- `0x180010020`
- `0x1800104ec`
- `0x180016760`
- `0x18001c93c`

## string_xrefs

- `0x1800100fa`: `onecore\vm\dv\storage\plan9\dll\p9handler.cpp`
- `0x18001011c`: `onecore\vm\dv\storage\plan9\dll\p9handler.cpp`

## pseudocode

```c
unsigned __int64 __fastcall p9fs::Handler::MessageResponse::EnsureSize(__int64 a1, char a2)
{
  __int64 v2; // rsi
  __int64 MessageSize; // rbx
  unsigned int v4; // r8d
  unsigned __int64 result; // rax
  unsigned __int64 v6; // rbx
  unsigned __int64 v7; // r10
  __int64 v8; // rbp
  __int64 v9; // rdx
  unsigned __int64 v10; // rcx
  size_t v11; // rax
  size_t v12; // rbx
  gsl::details *v13; // rcx
  unsigned int v14; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  v2 = a1;
  LOBYTE(a1) = a2;
  MessageSize = (unsigned int)p9fs::GetMessageSize(a1);
  result = v4;
  v6 = v4 + MessageSize;
  if ( v6 > v7 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x45,
      (unsigned int)"onecore\\vm\\dv\\storage\\plan9\\dll\\p9handler.cpp",
      (const char *)0xD,
      v14);
  if ( v6 > *(_QWORD *)v2 )
  {
    if ( !*(_BYTE *)(v2 + 48) )
    {
      Plan9TraceLoggingProvider::InvalidResponseBufferSize();
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x50,
        (unsigned int)"onecore\\vm\\dv\\storage\\plan9\\dll\\p9handler.cpp",
        (const char *)0xD,
        v14);
    }
    v8 = *(_QWORD *)(v2 + 32);
    v9 = *(_QWORD *)(v2 + 24);
    v10 = v8 - v9;
    if ( v6 < v8 - v9 )
    {
      v11 = v9 + v6;
LABEL_10:
      *(_QWORD *)(v2 + 32) = v11;
      goto LABEL_11;
    }
    if ( v6 > v10 )
    {
      if ( v6 <= *(_QWORD *)(v2 + 40) - v9 )
      {
        v12 = v6 - v10;
        memset_0(*(void **)(v2 + 32), 0, v12);
        v11 = v12 + v8;
        goto LABEL_10;
      }
      std::vector<unsigned char>::_Resize_reallocate<std::_Value_init_tag>(v2 + 24, v6);
    }
LABEL_11:
    v13 = *(gsl::details **)(v2 + 24);
    result = *(_QWORD *)(v2 + 32) - (_QWORD)v13;
    if ( result == -1
      || !v13 && result
      || (*(_QWORD *)v2 = result, *(_QWORD *)(v2 + 8) = v13, *(_QWORD *)(v2 + 16) = 0, result < 7) )
    {
      gsl::details::terminate(v13);
    }
    *(_QWORD *)(v2 + 16) = 7;
  }
  return result;
}

```

## disassembly

```asm
0x180010020  mov     [rsp+arg_18], rbx
0x180010025  push    rbp
0x180010026  push    rsi
0x180010027  push    rdi; unsigned int
0x180010028  sub     rsp, 20h
0x18001002c  mov     rsi, rcx
0x18001002f  mov     r10d, r9d
0x180010032  mov     cl, dl
0x180010034  call    ?GetMessageSize@p9fs@@YAIW4MessageType@1@@Z; p9fs::GetMessageSize(p9fs::MessageType)
0x180010039  mov     ebx, eax
0x18001003b  mov     eax, r8d
0x18001003e  add     rbx, rax
0x180010041  cmp     rbx, r10
0x180010044  ja      loc_180010117
0x18001004a  cmp     rbx, [rsi]
0x18001004d  jbe     loc_1800100E3
0x180010053  cmp     byte ptr [rsi+30h], 0
0x180010057  jz      loc_1800100F0
0x18001005d  lea     rdi, [rsi+18h]
0x180010061  mov     rbp, [rdi+8]
0x180010065  mov     rdx, [rdi]
0x180010068  mov     rcx, rbp
0x18001006b  sub     rcx, rdx
0x18001006e  cmp     rbx, rcx
0x180010071  jnb     short loc_180010079
0x180010073  lea     rax, [rdx+rbx]
0x180010077  jmp     short loc_1800100A8
0x180010079  jbe     short loc_1800100AC
0x18001007b  mov     rax, [rdi+10h]
0x18001007f  sub     rax, rdx
0x180010082  cmp     rbx, rax
0x180010085  jbe     short loc_180010094
0x180010087  mov     rdx, rbx
0x18001008a  mov     rcx, rdi
0x18001008d  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@EV?$allocator@E@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<uchar>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x180010092  jmp     short loc_1800100AC
0x180010094  sub     rbx, rcx
0x180010097  xor     edx, edx; Val
0x180010099  mov     r8, rbx; Size
0x18001009c  mov     rcx, rbp; void *
0x18001009f  call    memset_0
0x1800100a4  lea     rax, [rbx+rbp]
0x1800100a8  mov     [rdi+8], rax
0x1800100ac  mov     rcx, [rdi]; this
0x1800100af  mov     rax, [rdi+8]
0x1800100b3  sub     rax, rcx
0x1800100b6  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800100ba  jz      short loc_180010111
0x1800100bc  test    rcx, rcx
0x1800100bf  jnz     short loc_1800100C6
0x1800100c1  test    rax, rax
0x1800100c4  jnz     short loc_180010111
0x1800100c6  mov     [rsi], rax
0x1800100c9  mov     [rsi+8], rcx
0x1800100cd  mov     qword ptr [rsi+10h], 0
0x1800100d5  cmp     rax, 7
0x1800100d9  jb      short loc_180010111
0x1800100db  mov     qword ptr [rsi+10h], 7
0x1800100e3  mov     rbx, [rsp+38h+arg_18]
0x1800100e8  add     rsp, 20h
0x1800100ec  pop     rdi
0x1800100ed  pop     rsi
0x1800100ee  pop     rbp
0x1800100ef  retn
0x1800100f0  call    ?InvalidResponseBufferSize@Plan9TraceLoggingProvider@@SAXXZ; Plan9TraceLoggingProvider::InvalidResponseBufferSize(void)
0x1800100f5  mov     rcx, [rsp+38h]; this
0x1800100fa  lea     r8, aOnecoreVmDvSto_6; "onecore\\vm\\dv\\storage\\plan9\\dll\\p"...
0x180010101  mov     r9d, 0Dh; char *
0x180010107  lea     edx, [r9+43h]; void *
0x18001010b  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x180010111  call    ?terminate@details@gsl@@YAXXZ; gsl::details::terminate(void)
0x180010117  mov     rcx, [rsp+38h]; this
0x18001011c  lea     r8, aOnecoreVmDvSto_6; "onecore\\vm\\dv\\storage\\plan9\\dll\\p"...
0x180010123  mov     r9d, 0Dh; char *
0x180010129  lea     edx, [r9+38h]; void *
0x18001012d  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
```
