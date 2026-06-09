# ATL::CRegParser::RegisterBuffer(ushort *,int)

- ea: `0x18001ec2c`
- end: `0x18001ed99`
- name: `?RegisterBuffer@CRegParser@ATL@@QEAAJPEAGH@Z`
- size: `365`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001eda0`

## callees

- `0x18001a0d0`
- `0x18001e500`
- `0x18001e660`
- `0x18001ec2c`
- `0x18001ef4c`
- `0x18001f99c`
- `0x180053560`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001ed6f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001ed6f`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18001ecc8`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18001ecc8`

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
0x18001ec2c  push    rbx
0x18001ec2e  push    rbp
0x18001ec2f  push    rsi
0x18001ec30  push    rdi
0x18001ec31  push    r13
0x18001ec33  push    r14
0x18001ec35  push    r15
0x18001ec37  mov     eax, 2050h
0x18001ec3c  call    _alloca_probe
0x18001ec41  sub     rsp, rax
0x18001ec44  mov     rax, cs:__security_cookie
0x18001ec4b  xor     rax, rsp
0x18001ec4e  mov     [rsp+2088h+var_48], rax
0x18001ec56  mov     r15d, r8d
0x18001ec59  mov     [rsp+2088h+pv], 0
0x18001ec62  lea     r8, [rsp+2088h+pv]; unsigned __int16 **
0x18001ec67  mov     rdi, rcx
0x18001ec6a  call    ?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z; ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)
0x18001ec6f  mov     ebx, eax
0x18001ec71  test    eax, eax
0x18001ec73  js      loc_18001ED77
0x18001ec79  mov     rbp, [rsp+2088h+pv]
0x18001ec7e  lea     r13, ?map@?1??HKeyFromString@CRegParser@ATL@@KAPEAUHKEY__@@PEAG@Z@4QBUkeymap@?1??123@KAPEAU4@0@Z@B; `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::keymap const near * const `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::map
0x18001ec85  mov     [rdi], rbp
0x18001ec88  mov     rcx, [rdi]
0x18001ec8b  xor     eax, eax
0x18001ec8d  cmp     ax, [rcx]
0x18001ec90  jz      loc_18001ED6C
0x18001ec96  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x18001ec9b  mov     rcx, rdi; this
0x18001ec9e  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18001eca3  mov     ebx, eax
0x18001eca5  test    eax, eax
0x18001eca7  js      loc_18001ED6C
0x18001ecad  xor     ebx, ebx
0x18001ecaf  cmp     ebx, 0Eh
0x18001ecb2  jnb     loc_18001ED67
0x18001ecb8  movsxd  rsi, ebx
0x18001ecbb  lea     rcx, [rsp+2088h+String1]; lpString1
0x18001ecc0  add     rsi, rsi
0x18001ecc3  mov     rdx, [r13+rsi*8+0]; lpString2
0x18001ecc8  call    cs:__imp_lstrcmpiW
0x18001ecce  test    eax, eax
0x18001ecd0  jz      short loc_18001ECD6
0x18001ecd2  inc     ebx
0x18001ecd4  jmp     short loc_18001ECAF
0x18001ecd6  mov     rsi, [r13+rsi*8+8]
0x18001ecdb  test    rsi, rsi
0x18001ecde  jz      loc_18001ED67
0x18001ece4  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x18001ece9  mov     rcx, rdi; this
0x18001ecec  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18001ecf1  mov     ebx, eax
0x18001ecf3  test    eax, eax
0x18001ecf5  js      short loc_18001ED6C
0x18001ecf7  mov     eax, 7Bh ; '{'
0x18001ecfc  cmp     ax, [rsp+2088h+String1]
0x18001ed01  jnz     short loc_18001ED67
0x18001ed03  mov     [rsp+2088h+var_2068], 0; int
0x18001ed0b  mov     r8, rsi; HKEY
0x18001ed0e  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x18001ed13  mov     rcx, rdi; this
0x18001ed16  test    r15d, r15d
0x18001ed19  jz      short loc_18001ED4C
0x18001ed1b  mov     r14, [rdi]
0x18001ed1e  mov     r9d, r15d; int
0x18001ed21  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x18001ed26  mov     ebx, eax
0x18001ed28  test    eax, eax
0x18001ed2a  jns     short loc_18001ED5A
0x18001ed2c  xor     r9d, r9d; int
0x18001ed2f  mov     [rdi], r14
0x18001ed32  mov     r8, rsi; HKEY
0x18001ed35  mov     [rsp+2088h+var_2068], 0; int
0x18001ed3d  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x18001ed42  mov     rcx, rdi; this
0x18001ed45  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x18001ed4a  jmp     short loc_18001ED6C
0x18001ed4c  xor     r9d, r9d; int
0x18001ed4f  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x18001ed54  mov     ebx, eax
0x18001ed56  test    eax, eax
0x18001ed58  js      short loc_18001ED6C
0x18001ed5a  mov     rcx, rdi; this
0x18001ed5d  call    ?SkipWhiteSpace@CRegParser@ATL@@IEAAXXZ; ATL::CRegParser::SkipWhiteSpace(void)
0x18001ed62  jmp     loc_18001EC88
0x18001ed67  mov     ebx, 80020009h
0x18001ed6c  mov     rcx, rbp; pv
0x18001ed6f  call    cs:__imp_CoTaskMemFree
0x18001ed75  mov     eax, ebx
0x18001ed77  mov     rcx, [rsp+2088h+var_48]
0x18001ed7f  xor     rcx, rsp; StackCookie
0x18001ed82  call    __security_check_cookie
0x18001ed87  add     rsp, 2050h
0x18001ed8e  pop     r15
0x18001ed90  pop     r14
0x18001ed92  pop     r13
0x18001ed94  pop     rdi
0x18001ed95  pop     rsi
0x18001ed96  pop     rbp
0x18001ed97  pop     rbx
0x18001ed98  retn
```
