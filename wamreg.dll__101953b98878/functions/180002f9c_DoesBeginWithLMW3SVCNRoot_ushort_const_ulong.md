# DoesBeginWithLMW3SVCNRoot(ushort const *,ulong *)

- ea: `0x180002f9c`
- end: `0x1800030a7`
- name: `?DoesBeginWithLMW3SVCNRoot@@YAHPEBGPEAK@Z`
- size: `267`
- prototype: `__int64 __fastcall(wchar_t *String2, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800030b0`

## callees

- `0x180002f9c`
- `0x180006822`
- `0x180006850`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x180003009`
- `msvcrt!_wcsnicmp` at `0x18000305c`
- `msvcrt!_wcsnicmp` at `0x180003009`
- `msvcrt!_wcsnicmp` at `0x18000305c`
- `msvcrt!_itow` at `0x180003031`
- `msvcrt!_itow` at `0x180003031`
- `msvcrt!_wtoi` at `0x18000301a`
- `msvcrt!_wtoi` at `0x18000301a`

## pseudocode

```c
__int64 __fastcall DoesBeginWithLMW3SVCNRoot(wchar_t *String2, unsigned int *a2)
{
  unsigned int v4; // esi
  __int64 v5; // rbx
  unsigned __int64 v6; // rax
  const wchar_t *v7; // rdi
  int v8; // eax
  __int64 v9; // rax
  const wchar_t *v10; // rdi
  wchar_t Buffer[256]; // [rsp+20h] [rbp-228h] BYREF

  v4 = 0;
  memset_0(Buffer, 0, sizeof(Buffer));
  v5 = -1;
  v6 = -1;
  do
    ++v6;
  while ( String2[v6] );
  if ( v6 >= 0x10 && !_wcsnicmp(L"/lm/w3svc/", String2, 0xAu) )
  {
    v7 = String2 + 10;
    v8 = _wtoi(v7);
    if ( v8 )
    {
      _itow(v8, Buffer, 10);
      v9 = -1;
      do
        ++v9;
      while ( Buffer[v9] );
      v10 = &v7[v9];
      if ( !_wcsnicmp(v10, L"/Root", 5u) )
      {
        if ( a2 )
        {
          do
            ++v5;
          while ( v10[v5 + 5] );
          *a2 = v5;
        }
        return 1;
      }
    }
  }
  return v4;
}

```

## disassembly

```asm
0x180002f9c  mov     [rsp+arg_10], rbx
0x180002fa1  mov     [rsp+arg_18], rbp
0x180002fa6  push    rsi
0x180002fa7  push    rdi
0x180002fa8  push    r14
0x180002faa  sub     rsp, 230h
0x180002fb1  mov     rax, cs:__security_cookie
0x180002fb8  xor     rax, rsp
0x180002fbb  mov     [rsp+248h+var_28], rax
0x180002fc3  mov     r14, rdx
0x180002fc6  mov     rdi, rcx
0x180002fc9  xor     ebp, ebp
0x180002fcb  lea     rcx, [rsp+248h+Buffer]; void *
0x180002fd0  xor     edx, edx; Val
0x180002fd2  mov     r8d, 200h; Size
0x180002fd8  mov     esi, ebp
0x180002fda  call    memset_0
0x180002fdf  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180002fe3  mov     rax, rbx
0x180002fe6  inc     rax
0x180002fe9  cmp     [rdi+rax*2], bp
0x180002fed  jnz     short loc_180002FE6
0x180002fef  cmp     rax, 10h
0x180002ff3  jb      loc_18000307D
0x180002ff9  mov     r8d, 0Ah; MaxCount
0x180002fff  lea     rcx, aLmW3svc_2; "/lm/w3svc/"
0x180003006  mov     rdx, rdi; String2
0x180003009  call    cs:__imp__wcsnicmp
0x18000300f  test    eax, eax
0x180003011  jnz     short loc_18000307D
0x180003013  add     rdi, 14h
0x180003017  mov     rcx, rdi; String
0x18000301a  call    cs:__imp__wtoi
0x180003020  test    eax, eax
0x180003022  jz      short loc_18000307D
0x180003024  mov     r8d, 0Ah; Radix
0x18000302a  lea     rdx, [rsp+248h+Buffer]; Buffer
0x18000302f  mov     ecx, eax; Value
0x180003031  call    cs:__imp__itow
0x180003037  lea     rcx, [rsp+248h+Buffer]
0x18000303c  mov     rax, rbx
0x18000303f  inc     rax
0x180003042  cmp     [rcx+rax*2], bp
0x180003046  jnz     short loc_18000303F
0x180003048  lea     rdi, [rdi+rax*2]
0x18000304c  mov     r8d, 5; MaxCount
0x180003052  mov     rcx, rdi; String1
0x180003055  lea     rdx, aRoot_0; "/Root"
0x18000305c  call    cs:__imp__wcsnicmp
0x180003062  test    eax, eax
0x180003064  jnz     short loc_18000307D
0x180003066  test    r14, r14
0x180003069  jz      short loc_180003078
0x18000306b  inc     rbx
0x18000306e  cmp     [rdi+rbx*2+0Ah], bp
0x180003073  jnz     short loc_18000306B
0x180003075  mov     [r14], ebx
0x180003078  mov     esi, 1
0x18000307d  mov     eax, esi
0x18000307f  mov     rcx, [rsp+248h+var_28]
0x180003087  xor     rcx, rsp; StackCookie
0x18000308a  call    __security_check_cookie
0x18000308f  lea     r11, [rsp+248h+var_18]
0x180003097  mov     rbx, [r11+30h]
0x18000309b  mov     rbp, [r11+38h]
0x18000309f  mov     rsp, r11
0x1800030a2  pop     r14
0x1800030a4  pop     rdi
0x1800030a5  pop     rsi
0x1800030a6  retn
```
