# ATL::CRegParser::RegisterBuffer(ushort *,int)

- ea: `0x140003e1c`
- end: `0x140003fa6`
- name: `?RegisterBuffer@CRegParser@ATL@@QEAAJPEAGH@Z`
- size: `394`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x140003fac`

## callees

- `0x1400014f0`
- `0x140003784`
- `0x140003924`
- `0x140003e1c`
- `0x140004190`
- `0x140007570`

## import_xrefs

- `KERNEL32!lstrcmpiW` at `0x140003ea1`
- `KERNEL32!lstrcmpiW` at `0x140003ea1`
- `USER32!CharNextW` at `0x140003f8b`
- `USER32!CharNextW` at `0x140003f8b`
- `ole32!CoTaskMemFree` at `0x140003eba`
- `ole32!CoTaskMemFree` at `0x140003eba`

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
        Token = ATL::CRegParser::NextToken((ATL::CRegParser *)this, String1);
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
        Token = ATL::CRegParser::NextToken((ATL::CRegParser *)this, String1);
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
0x140003e1c  push    rbx
0x140003e1e  push    rbp
0x140003e1f  push    rsi
0x140003e20  push    rdi
0x140003e21  push    r13
0x140003e23  push    r14
0x140003e25  push    r15
0x140003e27  mov     eax, 2050h
0x140003e2c  call    _alloca_probe
0x140003e31  sub     rsp, rax
0x140003e34  mov     rax, cs:__security_cookie
0x140003e3b  xor     rax, rsp
0x140003e3e  mov     [rsp+2088h+var_48], rax
0x140003e46  mov     r15d, r8d
0x140003e49  mov     [rsp+2088h+pv], 0
0x140003e52  lea     r8, [rsp+2088h+pv]; unsigned __int16 **
0x140003e57  mov     rdi, rcx
0x140003e5a  call    ?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z; ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)
0x140003e5f  mov     ebx, eax
0x140003e61  test    eax, eax
0x140003e63  js      short loc_140003EC2
0x140003e65  mov     rbp, [rsp+2088h+pv]
0x140003e6a  xor     eax, eax
0x140003e6c  mov     [rdi], rbp
0x140003e6f  cmp     ax, [rbp+0]
0x140003e73  jz      short loc_140003EB7
0x140003e75  lea     r13, ?map@?1??HKeyFromString@CRegParser@ATL@@KAPEAUHKEY__@@PEAG@Z@4QBUkeymap@?1??123@KAPEAU4@0@Z@B; `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::keymap const near * const `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::map
0x140003e7c  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x140003e81  mov     rcx, rdi; this
0x140003e84  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x140003e89  mov     ebx, eax
0x140003e8b  test    eax, eax
0x140003e8d  js      short loc_140003EB7
0x140003e8f  xor     ebx, ebx
0x140003e91  movsxd  rsi, ebx
0x140003e94  lea     rcx, [rsp+2088h+String1]; lpString1
0x140003e99  add     rsi, rsi
0x140003e9c  mov     rdx, [r13+rsi*8+0]; lpString2
0x140003ea1  call    cs:__imp_lstrcmpiW
0x140003ea7  test    eax, eax
0x140003ea9  jz      short loc_140003EE4
0x140003eab  inc     ebx
0x140003ead  cmp     ebx, 0Eh
0x140003eb0  jb      short loc_140003E91
0x140003eb2  mov     ebx, 80020009h
0x140003eb7  mov     rcx, rbp; pv
0x140003eba  call    cs:__imp_CoTaskMemFree
0x140003ec0  mov     eax, ebx
0x140003ec2  mov     rcx, [rsp+2088h+var_48]
0x140003eca  xor     rcx, rsp; StackCookie
0x140003ecd  call    __security_check_cookie
0x140003ed2  add     rsp, 2050h
0x140003ed9  pop     r15
0x140003edb  pop     r14
0x140003edd  pop     r13
0x140003edf  pop     rdi
0x140003ee0  pop     rsi
0x140003ee1  pop     rbp
0x140003ee2  pop     rbx
0x140003ee3  retn
0x140003ee4  mov     rsi, [r13+rsi*8+8]
0x140003ee9  test    rsi, rsi
0x140003eec  jz      short loc_140003EB2
0x140003eee  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x140003ef3  mov     rcx, rdi; this
0x140003ef6  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x140003efb  mov     ebx, eax
0x140003efd  test    eax, eax
0x140003eff  js      short loc_140003EB7
0x140003f01  mov     eax, 7Bh ; '{'
0x140003f06  cmp     ax, [rsp+2088h+String1]
0x140003f0b  jnz     short loc_140003EB2
0x140003f0d  mov     [rsp+2088h+var_2068], 0; int
0x140003f15  mov     r8, rsi; HKEY
0x140003f18  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x140003f1d  mov     rcx, rdi; this
0x140003f20  test    r15d, r15d
0x140003f23  jz      short loc_140003F59
0x140003f25  mov     r14, [rdi]
0x140003f28  mov     r9d, r15d; int
0x140003f2b  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x140003f30  mov     ebx, eax
0x140003f32  test    eax, eax
0x140003f34  jns     short loc_140003F6B
0x140003f36  xor     r9d, r9d; int
0x140003f39  mov     [rdi], r14
0x140003f3c  mov     r8, rsi; HKEY
0x140003f3f  mov     [rsp+2088h+var_2068], 0; int
0x140003f47  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x140003f4c  mov     rcx, rdi; this
0x140003f4f  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x140003f54  jmp     loc_140003EB7
0x140003f59  xor     r9d, r9d; int
0x140003f5c  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x140003f61  mov     ebx, eax
0x140003f63  test    eax, eax
0x140003f65  js      loc_140003EB7
0x140003f6b  mov     r8, [rdi]
0x140003f6e  movzx   edx, word ptr [r8]
0x140003f72  mov     ecx, edx
0x140003f74  sub     ecx, 9
0x140003f77  jz      short loc_140003F88
0x140003f79  sub     ecx, 1
0x140003f7c  jz      short loc_140003F88
0x140003f7e  sub     ecx, 3
0x140003f81  jz      short loc_140003F88
0x140003f83  cmp     ecx, 13h
0x140003f86  jnz     short loc_140003F96
0x140003f88  mov     rcx, r8; lpsz
0x140003f8b  call    cs:__imp_CharNextW
0x140003f91  mov     [rdi], rax
0x140003f94  jmp     short loc_140003F6B
0x140003f96  xor     eax, eax
0x140003f98  cmp     ax, dx
0x140003f9b  jnz     loc_140003E7C
0x140003fa1  jmp     loc_140003EB7
```
