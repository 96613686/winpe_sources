# ATL::CRegParser::RegisterBuffer(ushort *,int)

- ea: `0x18000bb2c`
- end: `0x18000bc99`
- name: `?RegisterBuffer@CRegParser@ATL@@QEAAJPEAGH@Z`
- size: `365`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000bd28`

## callees

- `0x180001580`
- `0x18000a8f0`
- `0x18000b670`
- `0x18000bb2c`
- `0x18000bf80`
- `0x18000ca34`
- `0x180041990`

## import_xrefs

- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000bbc8`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000bbc8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000bc6f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000bc6f`

## pseudocode

```c
__int64 __fastcall ATL::CRegParser::RegisterBuffer(ATL::CRegParser *this, unsigned __int16 *a2, int a3)
{
  __int64 result; // rax
  int Token; // ebx
  void *v7; // rbp
  unsigned int i; // ebx
  HKEY v9; // rsi
  __int64 v10; // r14
  LPVOID pv; // [rsp+30h] [rbp-2058h] BYREF
  WCHAR String1[4096]; // [rsp+40h] [rbp-2048h] BYREF

  pv = 0;
  result = ATL::CRegParser::PreProcessBuffer(this, a2, (unsigned __int16 **)&pv);
  Token = result;
  if ( (int)result >= 0 )
  {
    v7 = pv;
    *(_QWORD *)this = pv;
    while ( **(_WORD **)this )
    {
      Token = ATL::CRegParser::NextToken(this, String1);
      if ( Token < 0 )
        break;
      for ( i = 0; ; ++i )
      {
        if ( i >= 0xE )
          goto LABEL_17;
        if ( !lstrcmpiW(String1, (&`ATL::CRegParser::HKeyFromString'::`2'::map)[2 * (int)i]) )
          break;
      }
      v9 = (HKEY)*(&`ATL::CRegParser::HKeyFromString'::`2'::map + 2 * (int)i + 1);
      if ( !v9 )
        goto LABEL_17;
      Token = ATL::CRegParser::NextToken(this, String1);
      if ( Token < 0 )
        break;
      if ( String1[0] != 123 )
      {
LABEL_17:
        Token = -2147352567;
        break;
      }
      if ( a3 )
      {
        v10 = *(_QWORD *)this;
        Token = ATL::CRegParser::RegisterSubkeys(this, String1, v9, a3, 0);
        if ( Token < 0 )
        {
          *(_QWORD *)this = v10;
          ATL::CRegParser::RegisterSubkeys(this, String1, v9, 0, 0);
          break;
        }
      }
      else
      {
        Token = ATL::CRegParser::RegisterSubkeys(this, String1, v9, 0, 0);
        if ( Token < 0 )
          break;
      }
      ATL::CRegParser::SkipWhiteSpace(this);
    }
    CoTaskMemFree(v7);
    return (unsigned int)Token;
  }
  return result;
}

```

## disassembly

```asm
0x18000bb2c  push    rbx
0x18000bb2e  push    rbp
0x18000bb2f  push    rsi
0x18000bb30  push    rdi
0x18000bb31  push    r13
0x18000bb33  push    r14
0x18000bb35  push    r15
0x18000bb37  mov     eax, 2050h
0x18000bb3c  call    _alloca_probe
0x18000bb41  sub     rsp, rax
0x18000bb44  mov     rax, cs:__security_cookie
0x18000bb4b  xor     rax, rsp
0x18000bb4e  mov     [rsp+2088h+var_48], rax
0x18000bb56  mov     r15d, r8d
0x18000bb59  mov     [rsp+2088h+pv], 0
0x18000bb62  lea     r8, [rsp+2088h+pv]; unsigned __int16 **
0x18000bb67  mov     rdi, rcx
0x18000bb6a  call    ?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z; ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)
0x18000bb6f  mov     ebx, eax
0x18000bb71  test    eax, eax
0x18000bb73  js      loc_18000BC77
0x18000bb79  mov     rbp, [rsp+2088h+pv]
0x18000bb7e  lea     r13, ?map@?1??HKeyFromString@CRegParser@ATL@@KAPEAUHKEY__@@PEAG@Z@4QBUkeymap@?1??123@KAPEAU4@0@Z@B; `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::keymap const near * const `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::map
0x18000bb85  mov     [rdi], rbp
0x18000bb88  mov     rcx, [rdi]
0x18000bb8b  xor     eax, eax
0x18000bb8d  cmp     ax, [rcx]
0x18000bb90  jz      loc_18000BC6C
0x18000bb96  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x18000bb9b  mov     rcx, rdi; this
0x18000bb9e  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000bba3  mov     ebx, eax
0x18000bba5  test    eax, eax
0x18000bba7  js      loc_18000BC6C
0x18000bbad  xor     ebx, ebx
0x18000bbaf  cmp     ebx, 0Eh
0x18000bbb2  jnb     loc_18000BC67
0x18000bbb8  movsxd  rsi, ebx
0x18000bbbb  lea     rcx, [rsp+2088h+String1]; lpString1
0x18000bbc0  add     rsi, rsi
0x18000bbc3  mov     rdx, [r13+rsi*8+0]; lpString2
0x18000bbc8  call    cs:__imp_lstrcmpiW
0x18000bbce  test    eax, eax
0x18000bbd0  jz      short loc_18000BBD6
0x18000bbd2  inc     ebx
0x18000bbd4  jmp     short loc_18000BBAF
0x18000bbd6  mov     rsi, [r13+rsi*8+8]
0x18000bbdb  test    rsi, rsi
0x18000bbde  jz      loc_18000BC67
0x18000bbe4  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x18000bbe9  mov     rcx, rdi; this
0x18000bbec  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000bbf1  mov     ebx, eax
0x18000bbf3  test    eax, eax
0x18000bbf5  js      short loc_18000BC6C
0x18000bbf7  mov     eax, 7Bh ; '{'
0x18000bbfc  cmp     ax, [rsp+2088h+String1]
0x18000bc01  jnz     short loc_18000BC67
0x18000bc03  mov     [rsp+2088h+var_2068], 0; int
0x18000bc0b  mov     r8, rsi; HKEY
0x18000bc0e  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x18000bc13  mov     rcx, rdi; this
0x18000bc16  test    r15d, r15d
0x18000bc19  jz      short loc_18000BC4C
0x18000bc1b  mov     r14, [rdi]
0x18000bc1e  mov     r9d, r15d; int
0x18000bc21  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x18000bc26  mov     ebx, eax
0x18000bc28  test    eax, eax
0x18000bc2a  jns     short loc_18000BC5A
0x18000bc2c  xor     r9d, r9d; int
0x18000bc2f  mov     [rdi], r14
0x18000bc32  mov     r8, rsi; HKEY
0x18000bc35  mov     [rsp+2088h+var_2068], 0; int
0x18000bc3d  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x18000bc42  mov     rcx, rdi; this
0x18000bc45  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x18000bc4a  jmp     short loc_18000BC6C
0x18000bc4c  xor     r9d, r9d; int
0x18000bc4f  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x18000bc54  mov     ebx, eax
0x18000bc56  test    eax, eax
0x18000bc58  js      short loc_18000BC6C
0x18000bc5a  mov     rcx, rdi; this
0x18000bc5d  call    ?SkipWhiteSpace@CRegParser@ATL@@IEAAXXZ; ATL::CRegParser::SkipWhiteSpace(void)
0x18000bc62  jmp     loc_18000BB88
0x18000bc67  mov     ebx, 80020009h
0x18000bc6c  mov     rcx, rbp; pv
0x18000bc6f  call    cs:__imp_CoTaskMemFree
0x18000bc75  mov     eax, ebx
0x18000bc77  mov     rcx, [rsp+2088h+var_48]
0x18000bc7f  xor     rcx, rsp; StackCookie
0x18000bc82  call    __security_check_cookie
0x18000bc87  add     rsp, 2050h
0x18000bc8e  pop     r15
0x18000bc90  pop     r14
0x18000bc92  pop     r13
0x18000bc94  pop     rdi
0x18000bc95  pop     rsi
0x18000bc96  pop     rbp
0x18000bc97  pop     rbx
0x18000bc98  retn
```
