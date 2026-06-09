# windows::rt::create_hstring(ushort const *)

- ea: `0x1400051b0`
- end: `0x140005258`
- name: `?create_hstring@rt@windows@@YA?AVHString@Wrappers@WRL@Microsoft@@PEBG@Z`
- size: `168`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140004b54`
- `0x140005000`
- `0x140040514`

## callees

- `0x1400051b0`
- `0x140005260`
- `0x140010304`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x14000520b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x14000520b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1400051fa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1400051fa`

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
    String = Microsoft::WRL::Wrappers::HString::Set((Microsoft::WRL::Wrappers::HString *)a1, &qword_140072110, 0);
  }
  if ( String < 0 )
    goto LABEL_7;
  return a1;
}

```

## disassembly

```asm
0x1400051b0  mov     [rsp+arg_10], rbx
0x1400051b5  push    rbp
0x1400051b6  push    rsi
0x1400051b7  push    rdi
0x1400051b8  sub     rsp, 30h
0x1400051bc  mov     rdi, rdx
0x1400051bf  mov     rsi, rcx
0x1400051c2  mov     [rsp+48h+var_20], rcx
0x1400051c7  xor     ebp, ebp
0x1400051c9  mov     [rsp+48h+var_28], ebp
0x1400051cd  mov     [rcx], rbp
0x1400051d0  mov     [rsp+48h+var_28], 1; int
0x1400051d8  test    rdx, rdx
0x1400051db  jz      short loc_140005246
0x1400051dd  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x1400051e4  inc     rbx
0x1400051e7  cmp     word ptr [rdx+rbx*2], 0
0x1400051ec  jnz     short loc_1400051E4
0x1400051ee  mov     eax, 0FFFFFFFFh
0x1400051f3  cmp     rbx, rax
0x1400051f6  ja      short loc_14000522F
0x1400051f8  xor     ecx, ecx; string
0x1400051fa  call    cs:__imp_WindowsDeleteString
0x140005200  mov     [rsi], rbp
0x140005203  mov     edx, ebx; length
0x140005205  mov     r8, rsi; string
0x140005208  mov     rcx, rdi; sourceString
0x14000520b  call    cs:__imp_WindowsCreateString
0x140005211  test    eax, eax
0x140005213  jns     short loc_140005236
0x140005215  mov     rcx, [rsp+48h]; this
0x14000521a  mov     r9d, eax; char *
0x14000521d  lea     r8, aOnecoreAmcoreS_6; "onecore\\amcore\\smartscreen\\src\\clie"...
0x140005224  mov     edx, 174h; void *
0x140005229  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14000522f  mov     eax, 80070216h
0x140005234  jmp     short loc_140005215
0x140005236  mov     rax, rsi
0x140005239  mov     rbx, [rsp+48h+arg_10]
0x14000523e  add     rsp, 30h
0x140005242  pop     rdi
0x140005243  pop     rsi
0x140005244  pop     rbp
0x140005245  retn
0x140005246  xor     r8d, r8d; unsigned int
0x140005249  lea     rdx, qword_140072110; unsigned __int16 *
0x140005250  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJPEBGI@Z; Microsoft::WRL::Wrappers::HString::Set(ushort const *,uint)
0x140005255  jmp     short loc_140005211
```
