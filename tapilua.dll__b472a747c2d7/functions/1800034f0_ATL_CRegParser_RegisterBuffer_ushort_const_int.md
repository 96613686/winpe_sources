# ATL::CRegParser::RegisterBuffer(ushort const *,int)

- ea: `0x1800034f0`
- end: `0x180003682`
- name: `?RegisterBuffer@CRegParser@ATL@@QEAAJPEBGH@Z`
- size: `402`
- prototype: `__int64 __fastcall(LPCWSTR *this, WCHAR *, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x180003688`

## callees

- `0x180002f30`
- `0x1800030cc`
- `0x1800034f0`
- `0x1800038f0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800035a1`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800035a1`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000351d`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000351d`
- `KERNEL32!lstrcmpiW` at `0x18000357f`
- `KERNEL32!lstrcmpiW` at `0x18000357f`
- `ole32!CoTaskMemFree` at `0x180003598`
- `ole32!CoTaskMemFree` at `0x180003598`
- `USER32!CharNextW` at `0x180003645`
- `USER32!CharNextW` at `0x180003645`

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
        Token = ATL::CRegParser::NextToken(this, v6);
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
        Token = ATL::CRegParser::NextToken(this, v6);
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
0x1800034f0  mov     [rsp+arg_0], rbx
0x1800034f5  mov     [rsp+arg_8], rbp
0x1800034fa  push    rsi
0x1800034fb  push    rdi
0x1800034fc  push    r12
0x1800034fe  push    r14
0x180003500  push    r15
0x180003502  sub     rsp, 30h
0x180003506  mov     rsi, rcx
0x180003509  mov     [rsp+58h+pv], 0
0x180003512  mov     ecx, 2000h; Size
0x180003517  mov     r12d, r8d
0x18000351a  mov     rbx, rdx
0x18000351d  call    cs:__imp_malloc
0x180003523  mov     rdi, rax
0x180003526  test    rax, rax
0x180003529  jnz     short loc_180003532
0x18000352b  mov     eax, 8007000Eh
0x180003530  jmp     short loc_1800035A9
0x180003532  lea     r8, [rsp+58h+pv]; unsigned __int16 **
0x180003537  mov     rdx, rbx; unsigned __int16 *
0x18000353a  mov     rcx, rsi; this
0x18000353d  call    ?PreProcessBuffer@CRegParser@ATL@@QEAAJPEBGPEAPEAG@Z; ATL::CRegParser::PreProcessBuffer(ushort const *,ushort * *)
0x180003542  mov     ebx, eax
0x180003544  test    eax, eax
0x180003546  js      short loc_18000359E
0x180003548  mov     r14, [rsp+58h+pv]
0x18000354d  xor     eax, eax
0x18000354f  mov     [rsi], r14
0x180003552  cmp     ax, [r14]
0x180003556  jz      short loc_180003595
0x180003558  lea     r15, ?map@?1??HKeyFromString@CRegParser@ATL@@KAPEAUHKEY__@@PEAG@Z@4QBUkeymap@?1??123@KAPEAU4@0@Z@B; `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::keymap const near * const `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::map
0x18000355f  mov     rdx, rdi; unsigned __int16 *
0x180003562  mov     rcx, rsi; this
0x180003565  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000356a  mov     ebx, eax
0x18000356c  test    eax, eax
0x18000356e  js      short loc_180003595
0x180003570  xor     ebx, ebx
0x180003572  movsxd  rbp, ebx
0x180003575  mov     rcx, rdi; lpString1
0x180003578  add     rbp, rbp
0x18000357b  mov     rdx, [r15+rbp*8]; lpString2
0x18000357f  call    cs:__imp_lstrcmpiW
0x180003585  test    eax, eax
0x180003587  jz      short loc_1800035C0
0x180003589  inc     ebx
0x18000358b  cmp     ebx, 0Eh
0x18000358e  jb      short loc_180003572
0x180003590  mov     ebx, 80020009h
0x180003595  mov     rcx, r14; pv
0x180003598  call    cs:__imp_CoTaskMemFree
0x18000359e  mov     rcx, rdi; Block
0x1800035a1  call    cs:__imp_free
0x1800035a7  mov     eax, ebx
0x1800035a9  mov     rbx, [rsp+58h+arg_0]
0x1800035ae  mov     rbp, [rsp+58h+arg_8]
0x1800035b3  add     rsp, 30h
0x1800035b7  pop     r15
0x1800035b9  pop     r14
0x1800035bb  pop     r12
0x1800035bd  pop     rdi
0x1800035be  pop     rsi
0x1800035bf  retn
0x1800035c0  mov     rbp, [r15+rbp*8+8]
0x1800035c5  test    rbp, rbp
0x1800035c8  jz      short loc_180003590
0x1800035ca  mov     rdx, rdi; unsigned __int16 *
0x1800035cd  mov     rcx, rsi; this
0x1800035d0  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800035d5  mov     ebx, eax
0x1800035d7  test    eax, eax
0x1800035d9  js      short loc_180003595
0x1800035db  mov     eax, 7Bh ; '{'
0x1800035e0  cmp     ax, [rdi]
0x1800035e3  jnz     short loc_180003590
0x1800035e5  mov     [rsp+58h+var_38], 0; int
0x1800035ed  mov     r8, rbp; HKEY
0x1800035f0  mov     rdx, rdi; unsigned __int16 *
0x1800035f3  mov     rcx, rsi; this
0x1800035f6  test    r12d, r12d
0x1800035f9  jz      short loc_180003615
0x1800035fb  mov     r15, [rsi]
0x1800035fe  mov     r9d, r12d; int
0x180003601  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x180003606  mov     ebx, eax
0x180003608  test    eax, eax
0x18000360a  js      short loc_180003661
0x18000360c  lea     r15, ?map@?1??HKeyFromString@CRegParser@ATL@@KAPEAUHKEY__@@PEAG@Z@4QBUkeymap@?1??123@KAPEAU4@0@Z@B; `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::keymap const near * const `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::map
0x180003613  jmp     short loc_180003627
0x180003615  xor     r9d, r9d; int
0x180003618  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x18000361d  mov     ebx, eax
0x18000361f  test    eax, eax
0x180003621  js      loc_180003595
0x180003627  mov     rcx, [rsi]; lpsz
0x18000362a  movzx   r8d, word ptr [rcx]
0x18000362e  mov     edx, r8d
0x180003631  sub     edx, 9
0x180003634  jz      short loc_180003645
0x180003636  sub     edx, 1
0x180003639  jz      short loc_180003645
0x18000363b  sub     edx, 3
0x18000363e  jz      short loc_180003645
0x180003640  cmp     edx, 13h
0x180003643  jnz     short loc_180003650
0x180003645  call    cs:__imp_CharNextW
0x18000364b  mov     [rsi], rax
0x18000364e  jmp     short loc_180003627
0x180003650  xor     eax, eax
0x180003652  cmp     ax, r8w
0x180003656  jnz     loc_18000355F
0x18000365c  jmp     loc_180003595
0x180003661  xor     r9d, r9d; int
0x180003664  mov     [rsi], r15
0x180003667  mov     r8, rbp; HKEY
0x18000366a  mov     [rsp+58h+var_38], 0; int
0x180003672  mov     rdx, rdi; unsigned __int16 *
0x180003675  mov     rcx, rsi; this
0x180003678  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x18000367d  jmp     loc_180003595
```
