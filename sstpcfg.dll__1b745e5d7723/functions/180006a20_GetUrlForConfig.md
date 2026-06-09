# GetUrlForConfig

- ea: `0x180006a20`
- end: `0x180006b63`
- name: `GetUrlForConfig`
- size: `323`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180002518`

## callees

- `0x180006a20`
- `0x180009e58`
- `0x18000a044`
- `0x18000acbc`
- `0x18000ae4e`
- `0x18000ae80`
- `0x18000c010`

## string_xrefs

- `0x180006b10`: `Error during prefix construction: 0x%x`

## pseudocode

```c
int __fastcall GetUrlForConfig(__int64 a1, int *a2, wchar_t *a3)
{
  int *v6; // rdx
  int v7; // ecx
  const wchar_t *v8; // r9
  _UNKNOWN **v9; // rax
  __int64 v10; // r8
  unsigned int v11; // ebx
  int v13; // [rsp+20h] [rbp-848h]
  int v14; // [rsp+40h] [rbp-828h] BYREF
  _BYTE v15[2044]; // [rsp+44h] [rbp-824h] BYREF

  v14 = 0;
  memset_0(v15, 0, sizeof(v15));
  v6 = &dword_18000D51C;
  if ( a2 )
    v6 = a2;
  if ( *(_WORD *)(a1 + 2) )
    v7 = *(unsigned __int16 *)(a1 + 2);
  else
    v7 = *(_BYTE *)a1 != 0 ? 443 : 80;
  v8 = L"https";
  if ( !*(_BYTE *)a1 )
    v8 = L"http";
  v13 = v7;
  LODWORD(v9) = StringCchPrintfW(
                  a3,
                  0x104u,
                  L"%s://+:%hd%s%s",
                  v8,
                  v13,
                  v6,
                  L"/sra_{BA195980-CD49-458b-9E23-C84EE0ADCD75}/");
  v11 = (unsigned int)v9;
  if ( (int)v9 < 0 )
  {
    v9 = &WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      LODWORD(v9) = WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, v10, v11);
    }
    if ( (_QWORD)xmmword_1800146E0 )
    {
      LOWORD(v14) = 0;
      FormatRRASErrorString(&v14, L"Error during prefix construction: 0x%x", v11);
      LODWORD(v9) = ((__int64 (__fastcall *)(__int64, _QWORD, int *))gSstpCfgTemplateFunc)(
                      gSstpCfgEtwContext,
                      xmmword_1800146E0,
                      &v14);
    }
  }
  return (int)v9;
}

```

## disassembly

```asm
0x180006a20  mov     [rsp+arg_18], rbx
0x180006a25  push    rbp
0x180006a26  push    rsi
0x180006a27  push    rdi
0x180006a28  sub     rsp, 850h
0x180006a2f  mov     rax, cs:__security_cookie
0x180006a36  xor     rax, rsp
0x180006a39  mov     [rsp+868h+var_28], rax
0x180006a41  mov     rsi, r8
0x180006a44  mov     rbx, rdx
0x180006a47  mov     rdi, rcx
0x180006a4a  xor     ebp, ebp
0x180006a4c  xor     edx, edx; Val
0x180006a4e  mov     [rsp+868h+var_828], ebp
0x180006a52  mov     r8d, 7FCh; Size
0x180006a58  lea     rcx, [rsp+868h+var_824]; void *
0x180006a5d  call    memset_0
0x180006a62  test    rbx, rbx
0x180006a65  lea     rdx, dword_18000D51C
0x180006a6c  cmovnz  rdx, rbx
0x180006a70  cmp     [rdi+2], bp
0x180006a74  jnz     short loc_180006A87
0x180006a76  mov     al, [rdi]
0x180006a78  neg     al
0x180006a7a  sbb     ecx, ecx
0x180006a7c  and     ecx, 16Bh
0x180006a82  add     ecx, 50h ; 'P'
0x180006a85  jmp     short loc_180006A8B
0x180006a87  movzx   ecx, word ptr [rdi+2]
0x180006a8b  cmp     [rdi], bpl
0x180006a8e  lea     rax, aHttp; "http"
0x180006a95  lea     r9, aHttps; "https"
0x180006a9c  cmovz   r9, rax
0x180006aa0  lea     r8, aSHdSS; "%s://+:%hd%s%s"
0x180006aa7  lea     rax, aSraBa195980Cd4; "/sra_{BA195980-CD49-458b-9E23-C84EE0ADC"...
0x180006aae  mov     [rsp+868h+var_838], rax
0x180006ab3  mov     [rsp+868h+var_840], rdx
0x180006ab8  mov     edx, 104h; cchDest
0x180006abd  mov     [rsp+868h+var_848], ecx
0x180006ac1  mov     rcx, rsi; pszDest
0x180006ac4  call    StringCchPrintfW
0x180006ac9  mov     ebx, eax
0x180006acb  test    eax, eax
0x180006acd  jns     short loc_180006B40
0x180006acf  mov     rcx, cs:WPP_GLOBAL_Control
0x180006ad6  lea     rax, WPP_GLOBAL_Control
0x180006add  cmp     rcx, rax
0x180006ae0  jz      short loc_180006AFF
0x180006ae2  test    byte ptr [rcx+1Ch], 40h
0x180006ae6  jz      short loc_180006AFF
0x180006ae8  cmp     byte ptr [rcx+19h], 1
0x180006aec  jb      short loc_180006AFF
0x180006aee  mov     rcx, [rcx+10h]
0x180006af2  mov     edx, 1Dh
0x180006af7  mov     r9d, ebx
0x180006afa  call    WPP_SF_d
0x180006aff  cmp     qword ptr cs:xmmword_1800146E0, rbp
0x180006b06  jz      short loc_180006B40
0x180006b08  mov     r8d, ebx
0x180006b0b  mov     word ptr [rsp+868h+var_828], bp
0x180006b10  lea     rdx, aErrorDuringPre; "Error during prefix construction: 0x%x"
0x180006b17  lea     rcx, [rsp+868h+var_828]
0x180006b1c  call    FormatRRASErrorString
0x180006b21  mov     rdx, qword ptr cs:xmmword_1800146E0
0x180006b28  lea     r8, [rsp+868h+var_828]
0x180006b2d  mov     rcx, cs:gSstpCfgEtwContext
0x180006b34  mov     rax, cs:gSstpCfgTemplateFunc
0x180006b3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006b40  mov     rcx, [rsp+868h+var_28]
0x180006b48  xor     rcx, rsp; StackCookie
0x180006b4b  call    __security_check_cookie
0x180006b50  mov     rbx, [rsp+868h+arg_18]
0x180006b58  add     rsp, 850h
0x180006b5f  pop     rdi
0x180006b60  pop     rsi
0x180006b61  pop     rbp
0x180006b62  retn
```
