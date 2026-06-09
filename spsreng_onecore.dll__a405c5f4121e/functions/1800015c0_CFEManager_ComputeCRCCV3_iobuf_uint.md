# CFEManager::ComputeCRCCV3(_iobuf *,uint *)

- ea: `0x1800015c0`
- end: `0x180001719`
- name: `?ComputeCRCCV3@CFEManager@@AEAAJPEAU_iobuf@@PEAI@Z`
- size: `345`
- prototype: `__int64 __fastcall(CFEManager *__hidden this, struct _iobuf *, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180021188`

## callees

- `0x1800015c0`
- `0x1800034b0`
- `0x1800ff490`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_ferror` at `0x18000169a`
- `api-ms-win-crt-private-l1-1-0!_o_ferror` at `0x1800016f7`
- `api-ms-win-crt-private-l1-1-0!_o_ferror` at `0x18000169a`
- `api-ms-win-crt-private-l1-1-0!_o_ferror` at `0x1800016f7`
- `api-ms-win-crt-private-l1-1-0!_o_fread` at `0x180001636`
- `api-ms-win-crt-private-l1-1-0!_o_fread` at `0x18000168c`
- `api-ms-win-crt-private-l1-1-0!_o_fread` at `0x180001636`
- `api-ms-win-crt-private-l1-1-0!_o_fread` at `0x18000168c`
- `api-ms-win-crt-private-l1-1-0!_o_fseek` at `0x180001609`
- `api-ms-win-crt-private-l1-1-0!_o_fseek` at `0x180001709`
- `api-ms-win-crt-private-l1-1-0!_o_fseek` at `0x180001609`
- `api-ms-win-crt-private-l1-1-0!_o_fseek` at `0x180001709`
- `api-ms-win-crt-private-l1-1-0!_o_ftell` at `0x1800015f6`
- `api-ms-win-crt-private-l1-1-0!_o_ftell` at `0x1800015f6`

## pseudocode

```c
int __fastcall CFEManager::ComputeCRCCV3(CFEManager *this, struct _iobuf *a2, unsigned int *a3)
{
  int v5; // ebp
  unsigned int v6; // ebx
  size_t v7; // rax
  char v8; // r9
  __int64 v9; // rdx
  __int16 v10; // cx
  int result; // eax
  _WORD Buffer[2048]; // [rsp+20h] [rbp-1028h] BYREF

  v5 = _o_ftell(a2);
  if ( fseek(a2, 32, 0) )
    return -2147418113;
  v6 = -1;
  do
  {
    v7 = fread(Buffer, 2u, 0x800u, a2);
    if ( v7 < 0x800 )
    {
      v9 = 0;
      v8 = 1;
      if ( !v7 )
        break;
    }
    else
    {
      v8 = 0;
      v9 = 0;
    }
    do
    {
      v10 = v6 ^ Buffer[v9];
      v9 = (unsigned int)(v9 + 1);
      v6 = *((_DWORD *)&CFEManager::s_CRCTable + (unsigned __int8)v10) ^ (v6 >> 8);
    }
    while ( (unsigned int)v9 < v7 );
  }
  while ( !v8 );
  Buffer[0] = 0;
  if ( fread(Buffer, 1u, 2u, a2) )
  {
    if ( (unsigned int)_o_ferror(a2) )
      return -2147418113;
    v6 = *((_DWORD *)&CFEManager::s_CRCTable + (unsigned __int8)(v6 ^ LOBYTE(Buffer[0]))) ^ (v6 >> 8);
  }
  if ( (unsigned int)_o_ferror(a2) )
    return -2147418113;
  result = fseek(a2, v5, 0);
  if ( result )
    return -2147418113;
  *a3 = ~v6;
  return result;
}

```

## disassembly

```asm
0x1800015c0  mov     [rsp+arg_0], rbx
0x1800015c5  mov     [rsp+arg_18], rbp
0x1800015ca  push    rsi
0x1800015cb  push    rdi
0x1800015cc  push    r14
0x1800015ce  mov     eax, 1030h
0x1800015d3  call    _alloca_probe
0x1800015d8  sub     rsp, rax
0x1800015db  mov     rax, cs:__security_cookie
0x1800015e2  xor     rax, rsp
0x1800015e5  mov     [rsp+1048h+var_28], rax
0x1800015ed  mov     rcx, rdx
0x1800015f0  mov     rsi, r8
0x1800015f3  mov     rdi, rdx
0x1800015f6  call    cs:__imp__o_ftell
0x1800015fc  xor     r8d, r8d; Origin
0x1800015ff  mov     edx, 20h ; ' '; Offset
0x180001604  mov     rcx, rdi; Stream
0x180001607  mov     ebp, eax
0x180001609  call    cs:__imp_fseek
0x18000160f  test    eax, eax
0x180001611  jnz     loc_1800016A4
0x180001617  mov     ebx, 0FFFFFFFFh
0x18000161c  lea     r14, ?s_CRCTable@CFEManager@@0QBHB; int const near * const CFEManager::s_CRCTable
0x180001623  mov     r9, rdi; Stream
0x180001626  lea     rcx, [rsp+1048h+Buffer]; Buffer
0x18000162b  mov     edx, 2; ElementSize
0x180001630  mov     r8d, 800h; ElementCount
0x180001636  call    cs:__imp_fread
0x18000163c  mov     r8, rax
0x18000163f  cmp     rax, 800h
0x180001645  jb      loc_1800016D1
0x18000164b  xor     r9b, r9b
0x18000164e  xor     edx, edx
0x180001650  movsx   ecx, [rsp+rdx*2+1048h+Buffer]
0x180001655  mov     eax, ebx
0x180001657  xor     rcx, rax
0x18000165a  shr     ebx, 8
0x18000165d  movzx   eax, cl
0x180001660  inc     edx
0x180001662  xor     ebx, [r14+rax*4]
0x180001666  mov     eax, edx
0x180001668  cmp     rax, r8
0x18000166b  jb      short loc_180001650
0x18000166d  test    r9b, r9b
0x180001670  jz      short loc_180001623
0x180001672  xor     eax, eax
0x180001674  lea     rcx, [rsp+1048h+Buffer]; Buffer
0x180001679  mov     r9, rdi; Stream
0x18000167c  mov     [rsp+1048h+Buffer], ax
0x180001681  mov     edx, 1; ElementSize
0x180001686  mov     r8d, 2; ElementCount
0x18000168c  call    cs:__imp_fread
0x180001692  test    rax, rax
0x180001695  jz      short loc_1800016F4
0x180001697  mov     rcx, rdi
0x18000169a  call    cs:__imp__o_ferror
0x1800016a0  test    eax, eax
0x1800016a2  jz      short loc_1800016E1
0x1800016a4  mov     eax, 8000FFFFh
0x1800016a9  mov     rcx, [rsp+1048h+var_28]
0x1800016b1  xor     rcx, rsp; StackCookie
0x1800016b4  call    __security_check_cookie
0x1800016b9  lea     r11, [rsp+1048h+var_18]
0x1800016c1  mov     rbx, [r11+20h]
0x1800016c5  mov     rbp, [r11+38h]
0x1800016c9  mov     rsp, r11
0x1800016cc  pop     r14
0x1800016ce  pop     rdi
0x1800016cf  pop     rsi
0x1800016d0  retn
0x1800016d1  xor     edx, edx
0x1800016d3  mov     r9b, 1
0x1800016d6  test    r8, r8
0x1800016d9  jnz     loc_180001650
0x1800016df  jmp     short loc_180001672
0x1800016e1  mov     ecx, dword ptr [rsp+1048h+Buffer]
0x1800016e5  mov     eax, ebx
0x1800016e7  xor     rcx, rax
0x1800016ea  shr     ebx, 8
0x1800016ed  movzx   eax, cl
0x1800016f0  xor     ebx, [r14+rax*4]
0x1800016f4  mov     rcx, rdi
0x1800016f7  call    cs:__imp__o_ferror
0x1800016fd  test    eax, eax
0x1800016ff  jnz     short loc_1800016A4
0x180001701  xor     r8d, r8d; Origin
0x180001704  mov     edx, ebp; Offset
0x180001706  mov     rcx, rdi; Stream
0x180001709  call    cs:__imp_fseek
0x18000170f  test    eax, eax
0x180001711  jnz     short loc_1800016A4
0x180001713  not     ebx
0x180001715  mov     [rsi], ebx
0x180001717  jmp     short loc_1800016A9
```
