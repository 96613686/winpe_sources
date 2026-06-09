# ATL::CRegParser::RegisterBuffer(ushort *,int)

- ea: `0x180004b10`
- end: `0x180004c95`
- name: `?RegisterBuffer@CRegParser@ATL@@QEAAJPEAGH@Z`
- size: `389`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task`

## callers

- `0x180004c9c`

## callees

- `0x180004594`
- `0x1800047b0`
- `0x180004b10`
- `0x180004f1c`
- `0x180005614`
- `0x18001e9f0`
- `0x18001eab0`

## import_xrefs

- `KERNEL32!lstrcmpiW` at `0x180004bae`
- `KERNEL32!lstrcmpiW` at `0x180004bae`
- `ole32!CoTaskMemFree` at `0x180004c5b`
- `ole32!CoTaskMemFree` at `0x180004c5b`

## pseudocode

```c
__int64 __fastcall ATL::CRegParser::RegisterBuffer(ATL::CRegParser *this, unsigned __int16 *a2, int a3)
{
  __int64 result; // rax
  int Token; // ebx
  void *v7; // rbp
  unsigned int v8; // esi
  __int64 v9; // rbx
  LPCWSTR *i; // r14
  HKEY v11; // rsi
  __int64 v12; // r14
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
      v8 = 0;
      v9 = 0;
      for ( i = (LPCWSTR *)&`ATL::CRegParser::HKeyFromString'::`2'::map; ; i += 2 )
      {
        if ( v8 >= 0xE )
          goto LABEL_17;
        if ( !lstrcmpiW(String1, *i) )
          break;
        ++v8;
        ++v9;
      }
      v11 = (HKEY)*(&`ATL::CRegParser::HKeyFromString'::`2'::map + 2 * v9 + 1);
      if ( !v11 )
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
        v12 = *(_QWORD *)this;
        Token = ATL::CRegParser::RegisterSubkeys(this, String1, v11, a3, 0);
        if ( Token < 0 )
        {
          *(_QWORD *)this = v12;
          ATL::CRegParser::RegisterSubkeys(this, String1, v11, 0, 0);
          break;
        }
      }
      else
      {
        Token = ATL::CRegParser::RegisterSubkeys(this, String1, v11, 0, 0);
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
0x180004b10  mov     [rsp+arg_18], rbx
0x180004b15  push    rbp
0x180004b16  push    rsi
0x180004b17  push    rdi
0x180004b18  push    r12
0x180004b1a  push    r13
0x180004b1c  push    r14
0x180004b1e  push    r15
0x180004b20  mov     eax, 2050h
0x180004b25  call    _alloca_probe
0x180004b2a  sub     rsp, rax
0x180004b2d  mov     rax, cs:__security_cookie
0x180004b34  xor     rax, rsp
0x180004b37  mov     [rsp+2088h+var_48], rax
0x180004b3f  mov     r15d, r8d
0x180004b42  xor     r12d, r12d
0x180004b45  lea     r8, [rsp+2088h+pv]; unsigned __int16 **
0x180004b4a  mov     [rsp+2088h+pv], r12
0x180004b4f  mov     rdi, rcx
0x180004b52  call    ?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z; ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)
0x180004b57  mov     ebx, eax
0x180004b59  test    eax, eax
0x180004b5b  js      loc_180004C69
0x180004b61  mov     rbp, [rsp+2088h+pv]
0x180004b66  lea     r13, ?map@?1??HKeyFromString@CRegParser@ATL@@KAPEAUHKEY__@@PEAG@Z@4QBUkeymap@?1??123@KAPEAU4@0@Z@B; `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::keymap const near * const `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::map
0x180004b6d  mov     [rdi], rbp
0x180004b70  mov     rax, [rdi]
0x180004b73  cmp     r12w, [rax]
0x180004b77  jz      loc_180004C58
0x180004b7d  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x180004b82  mov     rcx, rdi; this
0x180004b85  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180004b8a  mov     ebx, eax
0x180004b8c  test    eax, eax
0x180004b8e  js      loc_180004C58
0x180004b94  mov     esi, r12d
0x180004b97  mov     rbx, r12
0x180004b9a  mov     r14, r13
0x180004b9d  cmp     esi, 0Eh
0x180004ba0  jnb     loc_180004C53
0x180004ba6  mov     rdx, [r14]; lpString2
0x180004ba9  lea     rcx, [rsp+2088h+String1]; lpString1
0x180004bae  call    cs:__imp_lstrcmpiW
0x180004bb5  nop     dword ptr [rax+rax+00h]
0x180004bba  test    eax, eax
0x180004bbc  jz      short loc_180004BC9
0x180004bbe  inc     esi
0x180004bc0  inc     rbx
0x180004bc3  add     r14, 10h
0x180004bc7  jmp     short loc_180004B9D
0x180004bc9  add     rbx, rbx
0x180004bcc  mov     rsi, [r13+rbx*8+8]
0x180004bd1  test    rsi, rsi
0x180004bd4  jz      short loc_180004C53
0x180004bd6  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x180004bdb  mov     rcx, rdi; this
0x180004bde  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180004be3  mov     ebx, eax
0x180004be5  test    eax, eax
0x180004be7  js      short loc_180004C58
0x180004be9  mov     eax, 7Bh ; '{'
0x180004bee  cmp     ax, [rsp+2088h+String1]
0x180004bf3  jnz     short loc_180004C53
0x180004bf5  mov     [rsp+2088h+var_2068], r12d; int
0x180004bfa  mov     r8, rsi; HKEY
0x180004bfd  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x180004c02  mov     rcx, rdi; this
0x180004c05  test    r15d, r15d
0x180004c08  jz      short loc_180004C38
0x180004c0a  mov     r14, [rdi]
0x180004c0d  mov     r9d, r15d; int
0x180004c10  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x180004c15  mov     ebx, eax
0x180004c17  test    eax, eax
0x180004c19  jns     short loc_180004C46
0x180004c1b  xor     r9d, r9d; int
0x180004c1e  mov     [rdi], r14
0x180004c21  mov     r8, rsi; HKEY
0x180004c24  mov     [rsp+2088h+var_2068], r12d; int
0x180004c29  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x180004c2e  mov     rcx, rdi; this
0x180004c31  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x180004c36  jmp     short loc_180004C58
0x180004c38  xor     r9d, r9d; int
0x180004c3b  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x180004c40  mov     ebx, eax
0x180004c42  test    eax, eax
0x180004c44  js      short loc_180004C58
0x180004c46  mov     rcx, rdi; this
0x180004c49  call    ?SkipWhiteSpace@CRegParser@ATL@@IEAAXXZ; ATL::CRegParser::SkipWhiteSpace(void)
0x180004c4e  jmp     loc_180004B70
0x180004c53  mov     ebx, 80020009h
0x180004c58  mov     rcx, rbp; pv
0x180004c5b  call    cs:__imp_CoTaskMemFree
0x180004c62  nop     dword ptr [rax+rax+00h]
0x180004c67  mov     eax, ebx
0x180004c69  mov     rcx, [rsp+2088h+var_48]
0x180004c71  xor     rcx, rsp; StackCookie
0x180004c74  call    __security_check_cookie
0x180004c79  mov     rbx, [rsp+2088h+arg_18]
0x180004c81  add     rsp, 2050h
0x180004c88  pop     r15
0x180004c8a  pop     r14
0x180004c8c  pop     r13
0x180004c8e  pop     r12
0x180004c90  pop     rdi
0x180004c91  pop     rsi
0x180004c92  pop     rbp
0x180004c93  retn
```
