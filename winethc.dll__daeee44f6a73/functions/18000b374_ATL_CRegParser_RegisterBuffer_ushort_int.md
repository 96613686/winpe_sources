# ATL::CRegParser::RegisterBuffer(ushort *,int)

- ea: `0x18000b374`
- end: `0x18000b511`
- name: `?RegisterBuffer@CRegParser@ATL@@QEAAJPEAGH@Z`
- size: `413`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000b518`

## callees

- `0x18000a924`
- `0x18000ab0c`
- `0x18000b374`
- `0x18000b6fc`
- `0x180012db0`
- `0x180012e40`

## import_xrefs

- `KERNEL32!lstrcmpiW` at `0x18000b3f9`
- `KERNEL32!lstrcmpiW` at `0x18000b3f9`
- `USER32!CharNextW` at `0x18000b4f0`
- `USER32!CharNextW` at `0x18000b4f0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b418`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b418`

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
0x18000b374  push    rbx
0x18000b376  push    rbp
0x18000b377  push    rsi
0x18000b378  push    rdi
0x18000b379  push    r13
0x18000b37b  push    r14
0x18000b37d  push    r15
0x18000b37f  mov     eax, 2050h
0x18000b384  call    _alloca_probe
0x18000b389  sub     rsp, rax
0x18000b38c  mov     rax, cs:__security_cookie
0x18000b393  xor     rax, rsp
0x18000b396  mov     [rsp+2088h+var_48], rax
0x18000b39e  mov     r15d, r8d
0x18000b3a1  mov     [rsp+2088h+pv], 0
0x18000b3aa  lea     r8, [rsp+2088h+pv]; unsigned __int16 **
0x18000b3af  mov     rdi, rcx
0x18000b3b2  call    ?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z; ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)
0x18000b3b7  mov     ebx, eax
0x18000b3b9  test    eax, eax
0x18000b3bb  js      short loc_18000B426
0x18000b3bd  mov     rbp, [rsp+2088h+pv]
0x18000b3c2  xor     eax, eax
0x18000b3c4  mov     [rdi], rbp
0x18000b3c7  cmp     ax, [rbp+0]
0x18000b3cb  jz      short loc_18000B415
0x18000b3cd  lea     r13, ?map@?1??HKeyFromString@CRegParser@ATL@@KAPEAUHKEY__@@PEAG@Z@4QBUkeymap@?1??123@KAPEAU4@0@Z@B; `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::keymap const near * const `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::map
0x18000b3d4  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x18000b3d9  mov     rcx, rdi; this
0x18000b3dc  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000b3e1  mov     ebx, eax
0x18000b3e3  test    eax, eax
0x18000b3e5  js      short loc_18000B415
0x18000b3e7  xor     ebx, ebx
0x18000b3e9  movsxd  rsi, ebx
0x18000b3ec  lea     rcx, [rsp+2088h+String1]; lpString1
0x18000b3f1  add     rsi, rsi
0x18000b3f4  mov     rdx, [r13+rsi*8+0]; lpString2
0x18000b3f9  call    cs:__imp_lstrcmpiW
0x18000b400  nop     dword ptr [rax+rax+00h]
0x18000b405  test    eax, eax
0x18000b407  jz      short loc_18000B449
0x18000b409  inc     ebx
0x18000b40b  cmp     ebx, 0Eh
0x18000b40e  jb      short loc_18000B3E9
0x18000b410  mov     ebx, 80020009h
0x18000b415  mov     rcx, rbp; pv
0x18000b418  call    cs:__imp_CoTaskMemFree
0x18000b41f  nop     dword ptr [rax+rax+00h]
0x18000b424  mov     eax, ebx
0x18000b426  mov     rcx, [rsp+2088h+var_48]
0x18000b42e  xor     rcx, rsp; StackCookie
0x18000b431  call    __security_check_cookie
0x18000b436  add     rsp, 2050h
0x18000b43d  pop     r15
0x18000b43f  pop     r14
0x18000b441  pop     r13
0x18000b443  pop     rdi
0x18000b444  pop     rsi
0x18000b445  pop     rbp
0x18000b446  pop     rbx
0x18000b447  retn
0x18000b449  mov     rsi, [r13+rsi*8+8]
0x18000b44e  test    rsi, rsi
0x18000b451  jz      short loc_18000B410
0x18000b453  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x18000b458  mov     rcx, rdi; this
0x18000b45b  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000b460  mov     ebx, eax
0x18000b462  test    eax, eax
0x18000b464  js      short loc_18000B415
0x18000b466  mov     eax, 7Bh ; '{'
0x18000b46b  cmp     ax, [rsp+2088h+String1]
0x18000b470  jnz     short loc_18000B410
0x18000b472  mov     [rsp+2088h+var_2068], 0; int
0x18000b47a  mov     r8, rsi; HKEY
0x18000b47d  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x18000b482  mov     rcx, rdi; this
0x18000b485  test    r15d, r15d
0x18000b488  jz      short loc_18000B4BE
0x18000b48a  mov     r14, [rdi]
0x18000b48d  mov     r9d, r15d; int
0x18000b490  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x18000b495  mov     ebx, eax
0x18000b497  test    eax, eax
0x18000b499  jns     short loc_18000B4D0
0x18000b49b  xor     r9d, r9d; int
0x18000b49e  mov     [rdi], r14
0x18000b4a1  mov     r8, rsi; HKEY
0x18000b4a4  mov     [rsp+2088h+var_2068], 0; int
0x18000b4ac  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x18000b4b1  mov     rcx, rdi; this
0x18000b4b4  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x18000b4b9  jmp     loc_18000B415
0x18000b4be  xor     r9d, r9d; int
0x18000b4c1  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x18000b4c6  mov     ebx, eax
0x18000b4c8  test    eax, eax
0x18000b4ca  js      loc_18000B415
0x18000b4d0  mov     r8, [rdi]
0x18000b4d3  movzx   edx, word ptr [r8]
0x18000b4d7  mov     ecx, edx
0x18000b4d9  sub     ecx, 9
0x18000b4dc  jz      short loc_18000B4ED
0x18000b4de  sub     ecx, 1
0x18000b4e1  jz      short loc_18000B4ED
0x18000b4e3  sub     ecx, 3
0x18000b4e6  jz      short loc_18000B4ED
0x18000b4e8  cmp     ecx, 13h
0x18000b4eb  jnz     short loc_18000B501
0x18000b4ed  mov     rcx, r8; lpsz
0x18000b4f0  call    cs:__imp_CharNextW
0x18000b4f7  nop     dword ptr [rax+rax+00h]
0x18000b4fc  mov     [rdi], rax
0x18000b4ff  jmp     short loc_18000B4D0
0x18000b501  xor     eax, eax
0x18000b503  cmp     ax, dx
0x18000b506  jnz     loc_18000B3D4
0x18000b50c  jmp     loc_18000B415
```
