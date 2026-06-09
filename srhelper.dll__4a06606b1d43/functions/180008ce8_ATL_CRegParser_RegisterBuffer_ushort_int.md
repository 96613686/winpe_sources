# ATL::CRegParser::RegisterBuffer(ushort *,int)

- ea: `0x180008ce8`
- end: `0x180008e72`
- name: `?RegisterBuffer@CRegParser@ATL@@QEAAJPEAGH@Z`
- size: `394`
- prototype: `__int64 __fastcall(LPCWSTR *this, unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x180008e78`

## callees

- `0x180008700`
- `0x1800088ac`
- `0x180008ce8`
- `0x18000902c`
- `0x1800157f0`
- `0x180015880`

## import_xrefs

- `KERNEL32!lstrcmpiW` at `0x180008d6d`
- `KERNEL32!lstrcmpiW` at `0x180008d6d`
- `USER32!CharNextW` at `0x180008e57`
- `USER32!CharNextW` at `0x180008e57`
- `ole32!CoTaskMemFree` at `0x180008d86`
- `ole32!CoTaskMemFree` at `0x180008d86`

## pseudocode

```c
__int64 __fastcall ATL::CRegParser::RegisterBuffer(LPCWSTR *this, unsigned __int16 *a2, int a3)
{
  __int64 result; // rax
  int Token; // ebx
  _WORD *v7; // rbp
  int v8; // ebx
  HKEY v9; // rsi
  LPCWSTR v10; // r14
  LPVOID pv; // [rsp+30h] [rbp-2058h] BYREF
  WCHAR String1[4096]; // [rsp+40h] [rbp-2048h] BYREF

  pv = 0;
  result = ATL::CRegParser::PreProcessBuffer(this, a2, (unsigned __int16 **)&pv);
  Token = result;
  if ( (int)result >= 0 )
  {
    v7 = pv;
    *this = (LPCWSTR)pv;
    if ( *v7 )
    {
      do
      {
        Token = ATL::CRegParser::NextToken(this, String1);
        if ( Token < 0 )
          break;
        v8 = 0;
        while ( lstrcmpiW(String1, (&`ATL::CRegParser::HKeyFromString'::`2'::map)[2 * v8]) )
        {
          if ( (unsigned int)++v8 >= 0xE )
            goto LABEL_7;
        }
        v9 = (HKEY)*(&`ATL::CRegParser::HKeyFromString'::`2'::map + 2 * v8 + 1);
        if ( !v9 )
          goto LABEL_7;
        Token = ATL::CRegParser::NextToken(this, String1);
        if ( Token < 0 )
          break;
        if ( String1[0] != 123 )
        {
LABEL_7:
          Token = -2147352567;
          break;
        }
        if ( a3 )
        {
          v10 = *this;
          Token = ATL::CRegParser::RegisterSubkeys((ATL::CRegParser *)this, String1, v9, a3, 0);
          if ( Token < 0 )
          {
            *this = v10;
            ATL::CRegParser::RegisterSubkeys((ATL::CRegParser *)this, String1, v9, 0, 0);
            break;
          }
        }
        else
        {
          Token = ATL::CRegParser::RegisterSubkeys((ATL::CRegParser *)this, String1, v9, 0, 0);
          if ( Token < 0 )
            break;
        }
        while ( **this == 9 || **this == 10 || **this == 13 || **this == 32 )
          *this = CharNextW(*this);
      }
      while ( **this );
    }
    CoTaskMemFree(v7);
    return (unsigned int)Token;
  }
  return result;
}

```

## disassembly

```asm
0x180008ce8  push    rbx
0x180008cea  push    rbp
0x180008ceb  push    rsi
0x180008cec  push    rdi
0x180008ced  push    r13
0x180008cef  push    r14
0x180008cf1  push    r15
0x180008cf3  mov     eax, 2050h
0x180008cf8  call    _alloca_probe
0x180008cfd  sub     rsp, rax
0x180008d00  mov     rax, cs:__security_cookie
0x180008d07  xor     rax, rsp
0x180008d0a  mov     [rsp+2088h+var_48], rax
0x180008d12  mov     r15d, r8d
0x180008d15  mov     [rsp+2088h+pv], 0
0x180008d1e  lea     r8, [rsp+2088h+pv]; unsigned __int16 **
0x180008d23  mov     rdi, rcx
0x180008d26  call    ?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z; ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)
0x180008d2b  mov     ebx, eax
0x180008d2d  test    eax, eax
0x180008d2f  js      short loc_180008D8E
0x180008d31  mov     rbp, [rsp+2088h+pv]
0x180008d36  xor     eax, eax
0x180008d38  mov     [rdi], rbp
0x180008d3b  cmp     ax, [rbp+0]
0x180008d3f  jz      short loc_180008D83
0x180008d41  lea     r13, ?map@?1??HKeyFromString@CRegParser@ATL@@KAPEAUHKEY__@@PEAG@Z@4QBUkeymap@?1??123@KAPEAU4@0@Z@B; `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::keymap const near * const `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::map
0x180008d48  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x180008d4d  mov     rcx, rdi; this
0x180008d50  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180008d55  mov     ebx, eax
0x180008d57  test    eax, eax
0x180008d59  js      short loc_180008D83
0x180008d5b  xor     ebx, ebx
0x180008d5d  movsxd  rsi, ebx
0x180008d60  lea     rcx, [rsp+2088h+String1]; lpString1
0x180008d65  add     rsi, rsi
0x180008d68  mov     rdx, [r13+rsi*8+0]; lpString2
0x180008d6d  call    cs:__imp_lstrcmpiW
0x180008d73  test    eax, eax
0x180008d75  jz      short loc_180008DB0
0x180008d77  inc     ebx
0x180008d79  cmp     ebx, 0Eh
0x180008d7c  jb      short loc_180008D5D
0x180008d7e  mov     ebx, 80020009h
0x180008d83  mov     rcx, rbp; pv
0x180008d86  call    cs:__imp_CoTaskMemFree
0x180008d8c  mov     eax, ebx
0x180008d8e  mov     rcx, [rsp+2088h+var_48]
0x180008d96  xor     rcx, rsp; StackCookie
0x180008d99  call    __security_check_cookie
0x180008d9e  add     rsp, 2050h
0x180008da5  pop     r15
0x180008da7  pop     r14
0x180008da9  pop     r13
0x180008dab  pop     rdi
0x180008dac  pop     rsi
0x180008dad  pop     rbp
0x180008dae  pop     rbx
0x180008daf  retn
0x180008db0  mov     rsi, [r13+rsi*8+8]
0x180008db5  test    rsi, rsi
0x180008db8  jz      short loc_180008D7E
0x180008dba  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x180008dbf  mov     rcx, rdi; this
0x180008dc2  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180008dc7  mov     ebx, eax
0x180008dc9  test    eax, eax
0x180008dcb  js      short loc_180008D83
0x180008dcd  mov     eax, 7Bh ; '{'
0x180008dd2  cmp     ax, [rsp+2088h+String1]
0x180008dd7  jnz     short loc_180008D7E
0x180008dd9  mov     [rsp+2088h+var_2068], 0; int
0x180008de1  mov     r8, rsi; HKEY
0x180008de4  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x180008de9  mov     rcx, rdi; this
0x180008dec  test    r15d, r15d
0x180008def  jz      short loc_180008E25
0x180008df1  mov     r14, [rdi]
0x180008df4  mov     r9d, r15d; int
0x180008df7  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x180008dfc  mov     ebx, eax
0x180008dfe  test    eax, eax
0x180008e00  jns     short loc_180008E37
0x180008e02  xor     r9d, r9d; int
0x180008e05  mov     [rdi], r14
0x180008e08  mov     r8, rsi; HKEY
0x180008e0b  mov     [rsp+2088h+var_2068], 0; int
0x180008e13  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x180008e18  mov     rcx, rdi; this
0x180008e1b  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x180008e20  jmp     loc_180008D83
0x180008e25  xor     r9d, r9d; int
0x180008e28  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x180008e2d  mov     ebx, eax
0x180008e2f  test    eax, eax
0x180008e31  js      loc_180008D83
0x180008e37  mov     r8, [rdi]
0x180008e3a  movzx   edx, word ptr [r8]
0x180008e3e  mov     ecx, edx
0x180008e40  sub     ecx, 9
0x180008e43  jz      short loc_180008E54
0x180008e45  sub     ecx, 1
0x180008e48  jz      short loc_180008E54
0x180008e4a  sub     ecx, 3
0x180008e4d  jz      short loc_180008E54
0x180008e4f  cmp     ecx, 13h
0x180008e52  jnz     short loc_180008E62
0x180008e54  mov     rcx, r8; lpsz
0x180008e57  call    cs:__imp_CharNextW
0x180008e5d  mov     [rdi], rax
0x180008e60  jmp     short loc_180008E37
0x180008e62  xor     eax, eax
0x180008e64  cmp     ax, dx
0x180008e67  jnz     loc_180008D48
0x180008e6d  jmp     loc_180008D83
```
