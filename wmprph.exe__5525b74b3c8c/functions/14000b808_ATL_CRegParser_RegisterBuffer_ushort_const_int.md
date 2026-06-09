# ATL::CRegParser::RegisterBuffer(ushort const *,int)

- ea: `0x14000b808`
- end: `0x14000b99a`
- name: `?RegisterBuffer@CRegParser@ATL@@QEAAJPEBGH@Z`
- size: `402`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x14000b9a0`

## callees

- `0x14000b134`
- `0x14000b2c4`
- `0x14000b808`
- `0x14000bbf0`

## import_xrefs

- `KERNEL32!lstrcmpiW` at `0x14000b897`
- `KERNEL32!lstrcmpiW` at `0x14000b897`
- `USER32!CharNextW` at `0x14000b95d`
- `USER32!CharNextW` at `0x14000b95d`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14000b8b9`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14000b8b9`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x14000b835`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x14000b835`
- `ole32!CoTaskMemFree` at `0x14000b8b0`
- `ole32!CoTaskMemFree` at `0x14000b8b0`

## pseudocode

```c
__int64 __fastcall ATL::CRegParser::RegisterBuffer(LPCWSTR *this, WCHAR *a2, int a3)
{
  unsigned __int16 *v6; // rdi
  int Token; // ebx
  _WORD *v9; // r14
  int v10; // ebx
  HKEY v11; // rbp
  LPCWSTR v12; // r15
  LPVOID pv; // [rsp+78h] [rbp+20h] BYREF

  pv = 0;
  v6 = (unsigned __int16 *)malloc(0x2000u);
  if ( !v6 )
    return 2147942414LL;
  Token = ATL::CRegParser::PreProcessBuffer(this, a2, (unsigned __int16 **)&pv);
  if ( Token >= 0 )
  {
    v9 = pv;
    *this = (LPCWSTR)pv;
    if ( *v9 )
    {
      do
      {
        Token = ATL::CRegParser::NextToken((ATL::CRegParser *)this, v6);
        if ( Token < 0 )
          break;
        v10 = 0;
        while ( lstrcmpiW(v6, (&`ATL::CRegParser::HKeyFromString'::`2'::map)[2 * v10]) )
        {
          if ( (unsigned int)++v10 >= 0xE )
            goto LABEL_9;
        }
        v11 = (HKEY)*(&`ATL::CRegParser::HKeyFromString'::`2'::map + 2 * v10 + 1);
        if ( !v11 )
          goto LABEL_9;
        Token = ATL::CRegParser::NextToken((ATL::CRegParser *)this, v6);
        if ( Token < 0 )
          break;
        if ( *v6 != 123 )
        {
LABEL_9:
          Token = -2147352567;
          break;
        }
        if ( a3 )
        {
          v12 = *this;
          Token = ATL::CRegParser::RegisterSubkeys((ATL::CRegParser *)this, v6, v11, a3, 0);
          if ( Token < 0 )
          {
            *this = v12;
            ATL::CRegParser::RegisterSubkeys((ATL::CRegParser *)this, v6, v11, 0, 0);
            break;
          }
        }
        else
        {
          Token = ATL::CRegParser::RegisterSubkeys((ATL::CRegParser *)this, v6, v11, 0, 0);
          if ( Token < 0 )
            break;
        }
        while ( **this == 9 || **this == 10 || **this == 13 || **this == 32 )
          *this = CharNextW(*this);
      }
      while ( **this );
    }
    CoTaskMemFree(v9);
  }
  free(v6);
  return (unsigned int)Token;
}

```

## disassembly

```asm
0x14000b808  mov     [rsp+arg_0], rbx
0x14000b80d  mov     [rsp+arg_8], rbp
0x14000b812  push    rsi
0x14000b813  push    rdi
0x14000b814  push    r12
0x14000b816  push    r14
0x14000b818  push    r15
0x14000b81a  sub     rsp, 30h
0x14000b81e  mov     rsi, rcx
0x14000b821  mov     [rsp+58h+pv], 0
0x14000b82a  mov     ecx, 2000h; Size
0x14000b82f  mov     r12d, r8d
0x14000b832  mov     rbx, rdx
0x14000b835  call    cs:__imp_malloc
0x14000b83b  mov     rdi, rax
0x14000b83e  test    rax, rax
0x14000b841  jnz     short loc_14000B84A
0x14000b843  mov     eax, 8007000Eh
0x14000b848  jmp     short loc_14000B8C1
0x14000b84a  lea     r8, [rsp+58h+pv]; unsigned __int16 **
0x14000b84f  mov     rdx, rbx; unsigned __int16 *
0x14000b852  mov     rcx, rsi; this
0x14000b855  call    ?PreProcessBuffer@CRegParser@ATL@@QEAAJPEBGPEAPEAG@Z; ATL::CRegParser::PreProcessBuffer(ushort const *,ushort * *)
0x14000b85a  mov     ebx, eax
0x14000b85c  test    eax, eax
0x14000b85e  js      short loc_14000B8B6
0x14000b860  mov     r14, [rsp+58h+pv]
0x14000b865  xor     eax, eax
0x14000b867  mov     [rsi], r14
0x14000b86a  cmp     ax, [r14]
0x14000b86e  jz      short loc_14000B8AD
0x14000b870  lea     r15, ?map@?1??HKeyFromString@CRegParser@ATL@@KAPEAUHKEY__@@PEAG@Z@4QBUkeymap@?1??123@KAPEAU4@0@Z@B; `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::keymap const near * const `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::map
0x14000b877  mov     rdx, rdi; unsigned __int16 *
0x14000b87a  mov     rcx, rsi; this
0x14000b87d  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x14000b882  mov     ebx, eax
0x14000b884  test    eax, eax
0x14000b886  js      short loc_14000B8AD
0x14000b888  xor     ebx, ebx
0x14000b88a  movsxd  rbp, ebx
0x14000b88d  mov     rcx, rdi; lpString1
0x14000b890  add     rbp, rbp
0x14000b893  mov     rdx, [r15+rbp*8]; lpString2
0x14000b897  call    cs:__imp_lstrcmpiW
0x14000b89d  test    eax, eax
0x14000b89f  jz      short loc_14000B8D8
0x14000b8a1  inc     ebx
0x14000b8a3  cmp     ebx, 0Eh
0x14000b8a6  jb      short loc_14000B88A
0x14000b8a8  mov     ebx, 80020009h
0x14000b8ad  mov     rcx, r14; pv
0x14000b8b0  call    cs:__imp_CoTaskMemFree
0x14000b8b6  mov     rcx, rdi; Block
0x14000b8b9  call    cs:__imp_free
0x14000b8bf  mov     eax, ebx
0x14000b8c1  mov     rbx, [rsp+58h+arg_0]
0x14000b8c6  mov     rbp, [rsp+58h+arg_8]
0x14000b8cb  add     rsp, 30h
0x14000b8cf  pop     r15
0x14000b8d1  pop     r14
0x14000b8d3  pop     r12
0x14000b8d5  pop     rdi
0x14000b8d6  pop     rsi
0x14000b8d7  retn
0x14000b8d8  mov     rbp, [r15+rbp*8+8]
0x14000b8dd  test    rbp, rbp
0x14000b8e0  jz      short loc_14000B8A8
0x14000b8e2  mov     rdx, rdi; unsigned __int16 *
0x14000b8e5  mov     rcx, rsi; this
0x14000b8e8  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x14000b8ed  mov     ebx, eax
0x14000b8ef  test    eax, eax
0x14000b8f1  js      short loc_14000B8AD
0x14000b8f3  mov     eax, 7Bh ; '{'
0x14000b8f8  cmp     ax, [rdi]
0x14000b8fb  jnz     short loc_14000B8A8
0x14000b8fd  mov     [rsp+58h+var_38], 0; int
0x14000b905  mov     r8, rbp; HKEY
0x14000b908  mov     rdx, rdi; unsigned __int16 *
0x14000b90b  mov     rcx, rsi; this
0x14000b90e  test    r12d, r12d
0x14000b911  jz      short loc_14000B92D
0x14000b913  mov     r15, [rsi]
0x14000b916  mov     r9d, r12d; int
0x14000b919  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x14000b91e  mov     ebx, eax
0x14000b920  test    eax, eax
0x14000b922  js      short loc_14000B979
0x14000b924  lea     r15, ?map@?1??HKeyFromString@CRegParser@ATL@@KAPEAUHKEY__@@PEAG@Z@4QBUkeymap@?1??123@KAPEAU4@0@Z@B; `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::keymap const near * const `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::map
0x14000b92b  jmp     short loc_14000B93F
0x14000b92d  xor     r9d, r9d; int
0x14000b930  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x14000b935  mov     ebx, eax
0x14000b937  test    eax, eax
0x14000b939  js      loc_14000B8AD
0x14000b93f  mov     rcx, [rsi]; lpsz
0x14000b942  movzx   r8d, word ptr [rcx]
0x14000b946  mov     edx, r8d
0x14000b949  sub     edx, 9
0x14000b94c  jz      short loc_14000B95D
0x14000b94e  sub     edx, 1
0x14000b951  jz      short loc_14000B95D
0x14000b953  sub     edx, 3
0x14000b956  jz      short loc_14000B95D
0x14000b958  cmp     edx, 13h
0x14000b95b  jnz     short loc_14000B968
0x14000b95d  call    cs:__imp_CharNextW
0x14000b963  mov     [rsi], rax
0x14000b966  jmp     short loc_14000B93F
0x14000b968  xor     eax, eax
0x14000b96a  cmp     ax, r8w
0x14000b96e  jnz     loc_14000B877
0x14000b974  jmp     loc_14000B8AD
0x14000b979  xor     r9d, r9d; int
0x14000b97c  mov     [rsi], r15
0x14000b97f  mov     r8, rbp; HKEY
0x14000b982  mov     [rsp+58h+var_38], 0; int
0x14000b98a  mov     rdx, rdi; unsigned __int16 *
0x14000b98d  mov     rcx, rsi; this
0x14000b990  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x14000b995  jmp     loc_14000B8AD
```
