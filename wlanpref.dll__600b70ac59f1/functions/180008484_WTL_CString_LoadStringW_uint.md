# WTL::CString::LoadStringW(uint)

- ea: `0x180008484`
- end: `0x180008559`
- name: `?LoadStringW@CString@WTL@@QEAAHI@Z`
- size: `213`
- prototype: `__int64 __fastcall(WTL::CString *__hidden this, UINT uID)`
- caller_count: `25`
- callee_count: `6`
- tags: ``

## callers

- `0x18000b96c`
- `0x18000cf1c`
- `0x18000e164`
- `0x18000ea60`
- `0x18000eb50`
- `0x18000eea0`
- `0x18000f28c`
- `0x18000f630`
- `0x1800105cc`
- `0x180011a40`
- `0x180011c5c`
- `0x1800126b8`
- `0x1800150bc`
- `0x1800202f8`
- `0x180021194`
- `0x1800216ac`
- `0x180022524`
- `0x18002276c`
- `0x180022b40`
- `0x1800232b4`
- `0x180023308`
- `0x180026518`
- `0x18002780c`
- `0x180027ad4`
- `0x18002c8a8`

## callees

- `0x1800036fc`
- `0x1800077dc`
- `0x180008484`
- `0x18000b888`
- `0x18000c4dc`
- `0x18002d840`

## pseudocode

```c
__int64 __fastcall WTL::CString::LoadStringW(WTL::CString *this, UINT uID)
{
  int String; // edi
  unsigned int v5; // ebx
  bool v6; // zf
  bool v7; // sf
  unsigned int v8; // edi
  WCHAR *v9; // rax
  int v10; // edx
  int v11; // esi
  WCHAR Buffer[256]; // [rsp+20h] [rbp-228h] BYREF

  String = WTL::CString::_LoadString(uID, Buffer, 0x100u);
  if ( 256 - String <= 1 )
  {
    v8 = 256;
    v5 = 0;
    while ( 1 )
    {
      v8 += 256;
      v9 = WTL::CString::GetBuffer(this, v8 - 1);
      if ( !v9 )
        break;
      v11 = WTL::CString::_LoadString(uID, v9, v8);
      if ( (int)(v8 - v11) > 1 )
        goto LABEL_8;
    }
    v11 = 0;
LABEL_8:
    WTL::CString::ReleaseBuffer(this, v10);
    v6 = v11 == 0;
    v7 = v11 < 0;
  }
  else
  {
    WTL::CString::operator=(this, Buffer);
    v5 = 0;
    v6 = String == 0;
    v7 = String < 0;
  }
  LOBYTE(v5) = !v7 && !v6;
  return v5;
}

```

## disassembly

```asm
0x180008484  mov     [rsp+arg_10], rbx
0x180008489  mov     [rsp+arg_18], rbp
0x18000848e  push    rsi
0x18000848f  push    rdi
0x180008490  push    r14
0x180008492  sub     rsp, 230h
0x180008499  mov     rax, cs:__security_cookie
0x1800084a0  xor     rax, rsp
0x1800084a3  mov     [rsp+248h+var_28], rax
0x1800084ab  mov     r14d, edx
0x1800084ae  mov     rbp, rcx
0x1800084b1  mov     ecx, r14d; uID
0x1800084b4  lea     rdx, [rsp+248h+Buffer]; lpBuffer
0x1800084b9  mov     r8d, 100h; cchBufferMax
0x1800084bf  call    ?_LoadString@CString@WTL@@KAHIPEAGI@Z; WTL::CString::_LoadString(uint,ushort *,uint)
0x1800084c4  mov     r8d, 100h
0x1800084ca  mov     edi, eax
0x1800084cc  sub     r8d, eax
0x1800084cf  cmp     r8d, 1
0x1800084d3  jle     short loc_1800084E8
0x1800084d5  lea     rdx, [rsp+248h+Buffer]; unsigned __int16 *
0x1800084da  mov     rcx, rbp; this
0x1800084dd  call    ??4CString@WTL@@QEAAAEAV01@PEBG@Z; WTL::CString::operator=(ushort const *)
0x1800084e2  xor     ebx, ebx
0x1800084e4  test    edi, edi
0x1800084e6  jmp     short loc_18000852C
0x1800084e8  mov     edi, 100h
0x1800084ed  xor     ebx, ebx
0x1800084ef  add     edi, 100h
0x1800084f5  mov     rcx, rbp; this
0x1800084f8  lea     edx, [rdi-1]; int
0x1800084fb  call    ?GetBuffer@CString@WTL@@QEAAPEAGH@Z; WTL::CString::GetBuffer(int)
0x180008500  test    rax, rax
0x180008503  jz      short loc_180008520
0x180008505  mov     r8d, edi; cchBufferMax
0x180008508  mov     rdx, rax; lpBuffer
0x18000850b  mov     ecx, r14d; uID
0x18000850e  call    ?_LoadString@CString@WTL@@KAHIPEAGI@Z; WTL::CString::_LoadString(uint,ushort *,uint)
0x180008513  mov     ecx, edi
0x180008515  mov     esi, eax
0x180008517  sub     ecx, eax
0x180008519  cmp     ecx, 1
0x18000851c  jle     short loc_1800084EF
0x18000851e  jmp     short loc_180008522
0x180008520  mov     esi, ebx
0x180008522  mov     rcx, rbp; this
0x180008525  call    ?ReleaseBuffer@CString@WTL@@QEAAXH@Z; WTL::CString::ReleaseBuffer(int)
0x18000852a  test    esi, esi
0x18000852c  setnle  bl
0x18000852f  mov     eax, ebx
0x180008531  mov     rcx, [rsp+248h+var_28]
0x180008539  xor     rcx, rsp; StackCookie
0x18000853c  call    __security_check_cookie
0x180008541  lea     r11, [rsp+248h+var_18]
0x180008549  mov     rbx, [r11+30h]
0x18000854d  mov     rbp, [r11+38h]
0x180008551  mov     rsp, r11
0x180008554  pop     r14
0x180008556  pop     rdi
0x180008557  pop     rsi
0x180008558  retn
```
