# windows::rt::create_hstring(ushort const *)

- ea: `0x1400054f0`
- end: `0x1400055a5`
- name: `?create_hstring@rt@windows@@YA?AVHString@Wrappers@WRL@Microsoft@@PEBG@Z`
- size: `181`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140004dcc`
- `0x140005310`
- `0x140041c5c`

## callees

- `0x1400054f0`
- `0x1400055ac`
- `0x140010d44`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x140005551`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x140005551`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14000553a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14000553a`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
HSTRING *__fastcall windows::rt::create_hstring(HSTRING *a1, const WCHAR *a2)
{
  unsigned __int64 v4; // rbx
  HRESULT String; // eax
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  *a1 = 0;
  if ( a2 )
  {
    v4 = -1;
    do
      ++v4;
    while ( a2[v4] );
    if ( v4 > 0xFFFFFFFF )
    {
      String = -2147024362;
LABEL_7:
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x174,
        (unsigned int)"onecore\\amcore\\smartscreen\\src\\client\\helpers\\rt.h",
        (const char *)(unsigned int)String,
        1);
    }
    WindowsDeleteString(0);
    *a1 = 0;
    String = WindowsCreateString(a2, v4, a1);
  }
  else
  {
    String = Microsoft::WRL::Wrappers::HString::Set((Microsoft::WRL::Wrappers::HString *)a1, &qword_140074140, 0);
  }
  if ( String < 0 )
    goto LABEL_7;
  return a1;
}

```

## disassembly

```asm
0x1400054f0  mov     [rsp+arg_10], rbx
0x1400054f5  push    rbp
0x1400054f6  push    rsi
0x1400054f7  push    rdi
0x1400054f8  sub     rsp, 30h
0x1400054fc  mov     rdi, rdx
0x1400054ff  mov     rsi, rcx
0x140005502  mov     [rsp+48h+var_20], rcx
0x140005507  xor     ebp, ebp
0x140005509  mov     [rsp+48h+var_28], ebp
0x14000550d  mov     [rcx], rbp
0x140005510  mov     [rsp+48h+var_28], 1; int
0x140005518  test    rdx, rdx
0x14000551b  jz      short loc_140005593
0x14000551d  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x140005524  inc     rbx
0x140005527  cmp     word ptr [rdx+rbx*2], 0
0x14000552c  jnz     short loc_140005524
0x14000552e  mov     eax, 0FFFFFFFFh
0x140005533  cmp     rbx, rax
0x140005536  ja      short loc_14000557B
0x140005538  xor     ecx, ecx; string
0x14000553a  call    cs:__imp_WindowsDeleteString
0x140005541  nop     dword ptr [rax+rax+00h]
0x140005546  mov     [rsi], rbp
0x140005549  mov     edx, ebx; length
0x14000554b  mov     r8, rsi; string
0x14000554e  mov     rcx, rdi; sourceString
0x140005551  call    cs:__imp_WindowsCreateString
0x140005558  nop     dword ptr [rax+rax+00h]
0x14000555d  test    eax, eax
0x14000555f  jns     short loc_140005582
0x140005561  mov     rcx, [rsp+48h]; this
0x140005566  mov     r9d, eax; char *
0x140005569  lea     r8, aOnecoreAmcoreS_6; "onecore\\amcore\\smartscreen\\src\\clie"...
0x140005570  mov     edx, 174h; void *
0x140005575  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14000557b  mov     eax, 80070216h
0x140005580  jmp     short loc_140005561
0x140005582  mov     rax, rsi
0x140005585  mov     rbx, [rsp+48h+arg_10]
0x14000558a  add     rsp, 30h
0x14000558e  pop     rdi
0x14000558f  pop     rsi
0x140005590  pop     rbp
0x140005591  retn
0x140005593  xor     r8d, r8d; unsigned int
0x140005596  lea     rdx, qword_140074140; unsigned __int16 *
0x14000559d  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJPEBGI@Z; Microsoft::WRL::Wrappers::HString::Set(ushort const *,uint)
0x1400055a2  jmp     short loc_14000555D
```
