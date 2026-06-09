# _StpGetRegistryRoot

- ea: `0x18007018c`
- end: `0x18007030a`
- name: `_StpGetRegistryRoot`
- size: `382`
- prototype: ``
- caller_count: `7`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18006ff3c`
- `0x1801ff77c`
- `0x1802003b0`
- `0x18020077c`
- `0x18020135c`
- `0x180202114`
- `0x18020234c`

## callees

- `0x18000aa0c`
- `0x18007018c`
- `0x180108234`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18007025e`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18007026d`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x1800702cf`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x1800702de`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18007025e`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18007026d`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x1800702cf`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x1800702de`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x1800701db`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x1800701db`
- `ext-ms-win-networking-wlanstorage-l1-1-0!GetCustomRegRootPath` at `0x1800702f7`
- `ext-ms-win-networking-wlanstorage-l1-1-0!GetCustomRegRootPath` at `0x1800702f7`
- `ext-ms-win-networking-wlanstorage-l1-1-0!GetCustomWfdSettingsRegPath` at `0x180070290`
- `ext-ms-win-networking-wlanstorage-l1-1-0!GetCustomWfdSettingsRegPath` at `0x180070290`

## pseudocode

```c
__int64 __fastcall StpGetRegistryRoot(__int64 a1, __int64 a2, __int64 a3, __int64 a4, int a5)
{
  unsigned int v9; // ebx
  __int64 v11; // rax
  __int64 v12; // rax

  if ( a5 && IsGetCustomWfdSettingsRegPathPresent() && (int)GetCustomWfdSettingsRegPath(a1, a2, a3) >= 0 )
  {
    v9 = 0;
    if ( a4 )
    {
      v12 = -1;
      do
        ++v12;
      while ( *(_WORD *)(a4 + 2 * v12) );
      if ( v12 )
      {
        _o_wcscat_s(a1, a2, L"\\");
        return (unsigned int)_o_wcscat_s(a1, a2, a4);
      }
    }
    return v9;
  }
  if ( !a1 || !a3 || !a2 )
  {
    v9 = 87;
LABEL_11:
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 105)
      && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 10, &WPP_d35b4e0e825b3126173a8f9fbc52d996_Traceguids, v9);
    }
    return v9;
  }
  if ( IsGetCustomWfdSettingsRegPathPresent() && (v9 = 0, (int)GetCustomRegRootPath(a1, a2, a3) >= 0)
    || (v9 = _o_wcscpy_s(a1, a2, a3)) == 0 )
  {
    if ( a4 )
    {
      v11 = -1;
      do
        ++v11;
      while ( *(_WORD *)(a4 + 2 * v11) );
      if ( v11 )
      {
        _o_wcscat_s(a1, a2, L"\\");
        v9 = _o_wcscat_s(a1, a2, a4);
      }
    }
  }
  if ( v9 )
    goto LABEL_11;
  return v9;
}

```

## disassembly

```asm
0x18007018c  push    rbx
0x18007018e  push    rbp
0x18007018f  push    rsi
0x180070190  push    rdi
0x180070191  push    r14
0x180070193  push    r15
0x180070195  sub     rsp, 28h
0x180070199  xor     r15d, r15d
0x18007019c  mov     rbp, r9
0x18007019f  mov     r14, r8
0x1800701a2  mov     rdi, rdx
0x1800701a5  mov     rsi, rcx
0x1800701a8  cmp     [rsp+58h+arg_20], r15d
0x1800701b0  jnz     loc_18007027A
0x1800701b6  test    rsi, rsi
0x1800701b9  jz      short loc_1800701FF
0x1800701bb  test    r14, r14
0x1800701be  jz      short loc_1800701FF
0x1800701c0  test    rdi, rdi
0x1800701c3  jz      short loc_1800701FF
0x1800701c5  call    IsGetCustomWfdSettingsRegPathPresent
0x1800701ca  test    al, al
0x1800701cc  jnz     loc_1800702EB
0x1800701d2  mov     r8, r14
0x1800701d5  mov     rdx, rdi
0x1800701d8  mov     rcx, rsi
0x1800701db  call    cs:__imp__o_wcscpy_s
0x1800701e1  mov     ebx, eax
0x1800701e3  test    eax, eax
0x1800701e5  jnz     short loc_1800701EC
0x1800701e7  test    rbp, rbp
0x1800701ea  jnz     short loc_18007023D
0x1800701ec  test    ebx, ebx
0x1800701ee  jnz     short loc_180070204
0x1800701f0  mov     eax, ebx
0x1800701f2  add     rsp, 28h
0x1800701f6  pop     r15
0x1800701f8  pop     r14
0x1800701fa  pop     rdi
0x1800701fb  pop     rsi
0x1800701fc  pop     rbp
0x1800701fd  pop     rbx
0x1800701fe  retn
0x1800701ff  mov     ebx, 57h ; 'W'
0x180070204  mov     r9d, ebx
0x180070207  mov     rcx, cs:WPP_GLOBAL_Control
0x18007020e  lea     rax, WPP_GLOBAL_Control
0x180070215  cmp     rcx, rax
0x180070218  jz      short loc_1800701F0
0x18007021a  cmp     byte ptr [rcx+69h], 1
0x18007021e  jb      short loc_1800701F0
0x180070220  test    byte ptr [rcx+6Ch], 1
0x180070224  jz      short loc_1800701F0
0x180070226  mov     rcx, [rcx+60h]
0x18007022a  lea     r8, WPP_d35b4e0e825b3126173a8f9fbc52d996_Traceguids
0x180070231  mov     edx, 0Ah
0x180070236  call    WPP_SF_d
0x18007023b  jmp     short loc_1800701F0
0x18007023d  or      rax, 0FFFFFFFFFFFFFFFFh
0x180070241  inc     rax
0x180070244  cmp     [rbp+rax*2+0], r15w
0x18007024a  jnz     short loc_180070241
0x18007024c  test    rax, rax
0x18007024f  jz      short loc_1800701EC
0x180070251  lea     r8, SubBlock; "\\"
0x180070258  mov     rdx, rdi
0x18007025b  mov     rcx, rsi
0x18007025e  call    cs:__imp__o_wcscat_s
0x180070264  mov     r8, rbp
0x180070267  mov     rdx, rdi
0x18007026a  mov     rcx, rsi
0x18007026d  call    cs:__imp__o_wcscat_s
0x180070273  mov     ebx, eax
0x180070275  jmp     loc_1800701EC
0x18007027a  call    IsGetCustomWfdSettingsRegPathPresent
0x18007027f  test    al, al
0x180070281  jz      loc_1800701B6
0x180070287  mov     r8, r14
0x18007028a  mov     rdx, rdi
0x18007028d  mov     rcx, rsi
0x180070290  call    cs:__imp_GetCustomWfdSettingsRegPath
0x180070296  test    eax, eax
0x180070298  js      loc_1800701B6
0x18007029e  mov     ebx, r15d
0x1800702a1  test    rbp, rbp
0x1800702a4  jz      loc_1800701F0
0x1800702aa  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800702ae  inc     rax
0x1800702b1  cmp     [rbp+rax*2+0], r15w
0x1800702b7  jnz     short loc_1800702AE
0x1800702b9  test    rax, rax
0x1800702bc  jz      loc_1800701F0
0x1800702c2  lea     r8, SubBlock; "\\"
0x1800702c9  mov     rdx, rdi
0x1800702cc  mov     rcx, rsi
0x1800702cf  call    cs:__imp__o_wcscat_s
0x1800702d5  mov     r8, rbp
0x1800702d8  mov     rdx, rdi
0x1800702db  mov     rcx, rsi
0x1800702de  call    cs:__imp__o_wcscat_s
0x1800702e4  mov     ebx, eax
0x1800702e6  jmp     loc_1800701F0
0x1800702eb  mov     r8, r14
0x1800702ee  mov     rdx, rdi
0x1800702f1  mov     rcx, rsi
0x1800702f4  mov     ebx, r15d
0x1800702f7  call    cs:__imp_GetCustomRegRootPath
0x1800702fd  test    eax, eax
0x1800702ff  jns     loc_1800701E7
0x180070305  jmp     loc_1800701D2
```
