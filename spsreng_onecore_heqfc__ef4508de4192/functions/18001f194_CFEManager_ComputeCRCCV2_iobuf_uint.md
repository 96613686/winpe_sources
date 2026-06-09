# CFEManager::ComputeCRCCV2(_iobuf *,uint *)

- ea: `0x18001f194`
- end: `0x18001f2d2`
- name: `?ComputeCRCCV2@CFEManager@@AEAAJPEAU_iobuf@@PEAI@Z`
- size: `318`
- prototype: `__int64 __fastcall(CFEManager *__hidden this, struct _iobuf *, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180021188`

## callees

- `0x1800034b0`
- `0x18001f194`
- `0x1800ff490`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_ferror` at `0x18001f261`
- `api-ms-win-crt-private-l1-1-0!_o_ferror` at `0x18001f28a`
- `api-ms-win-crt-private-l1-1-0!_o_ferror` at `0x18001f261`
- `api-ms-win-crt-private-l1-1-0!_o_ferror` at `0x18001f28a`
- `api-ms-win-crt-private-l1-1-0!_o_fread` at `0x18001f1f9`
- `api-ms-win-crt-private-l1-1-0!_o_fread` at `0x18001f253`
- `api-ms-win-crt-private-l1-1-0!_o_fread` at `0x18001f1f9`
- `api-ms-win-crt-private-l1-1-0!_o_fread` at `0x18001f253`
- `api-ms-win-crt-private-l1-1-0!_o_fseek` at `0x18001f1d6`
- `api-ms-win-crt-private-l1-1-0!_o_fseek` at `0x18001f29c`
- `api-ms-win-crt-private-l1-1-0!_o_fseek` at `0x18001f1d6`
- `api-ms-win-crt-private-l1-1-0!_o_fseek` at `0x18001f29c`
- `api-ms-win-crt-private-l1-1-0!_o_ftell` at `0x18001f1c4`
- `api-ms-win-crt-private-l1-1-0!_o_ftell` at `0x18001f1c4`

## pseudocode

```c
int __fastcall CFEManager::ComputeCRCCV2(CFEManager *this, struct _iobuf *a2, unsigned int *a3)
{
  int v5; // ebp
  unsigned int v6; // ebx
  size_t v7; // rax
  __int64 i; // r10
  int v9; // edx
  int result; // eax
  _WORD Buffer[2048]; // [rsp+20h] [rbp-1028h] BYREF

  v5 = _o_ftell(a2);
  if ( fseek(a2, 32, 0) )
    return -2147418113;
  v6 = 0;
  do
  {
    v7 = fread(Buffer, 2u, 0x800u, a2);
    for ( i = 0; (unsigned int)i < v7; v6 = ((v6 << 16) + v9) % 0xFFF1 )
    {
      v9 = (__int16)Buffer[i];
      i = (unsigned int)(i + 1);
    }
  }
  while ( v7 >= 0x800 );
  Buffer[0] = 0;
  if ( fread(Buffer, 1u, 2u, a2) )
  {
    if ( (unsigned int)_o_ferror(a2) )
      return -2147418113;
    v6 = (Buffer[0] + (v6 << 16)) % 0xFFF1;
  }
  if ( !(unsigned int)_o_ferror(a2) )
  {
    result = fseek(a2, v5, 0);
    if ( !result )
    {
      *a3 = v6;
      return result;
    }
  }
  return -2147418113;
}

```

## disassembly

```asm
0x18001f194  mov     [rsp+arg_0], rbx
0x18001f199  push    rbp
0x18001f19a  push    rsi
0x18001f19b  push    rdi
0x18001f19c  mov     eax, 1030h
0x18001f1a1  call    _alloca_probe
0x18001f1a6  sub     rsp, rax
0x18001f1a9  mov     rax, cs:__security_cookie
0x18001f1b0  xor     rax, rsp
0x18001f1b3  mov     [rsp+1048h+var_28], rax
0x18001f1bb  mov     rcx, rdx
0x18001f1be  mov     rsi, r8
0x18001f1c1  mov     rdi, rdx
0x18001f1c4  call    cs:__imp__o_ftell
0x18001f1ca  xor     r8d, r8d; Origin
0x18001f1cd  mov     rcx, rdi; Stream
0x18001f1d0  mov     ebp, eax
0x18001f1d2  lea     edx, [r8+20h]; Offset
0x18001f1d6  call    cs:__imp_fseek
0x18001f1dc  test    eax, eax
0x18001f1de  jnz     loc_18001F2AA
0x18001f1e4  xor     ebx, ebx
0x18001f1e6  mov     r9, rdi; Stream
0x18001f1e9  lea     rcx, [rsp+1048h+Buffer]; Buffer
0x18001f1ee  mov     edx, 2; ElementSize
0x18001f1f3  mov     r8d, 800h; ElementCount
0x18001f1f9  call    cs:__imp_fread
0x18001f1ff  xor     r10d, r10d
0x18001f202  mov     r9, rax
0x18001f205  test    rax, rax
0x18001f208  jz      short loc_18001F234
0x18001f20a  movsx   edx, [rsp+r10*2+1048h+Buffer]
0x18001f210  mov     eax, 80078071h
0x18001f215  shl     ebx, 10h
0x18001f218  inc     r10d
0x18001f21b  add     edx, ebx
0x18001f21d  mov     ebx, edx
0x18001f21f  mul     edx
0x18001f221  shr     edx, 0Fh
0x18001f224  imul    eax, edx, 0FFF1h
0x18001f22a  sub     ebx, eax
0x18001f22c  mov     eax, r10d
0x18001f22f  cmp     rax, r9
0x18001f232  jb      short loc_18001F20A
0x18001f234  cmp     r9, 800h
0x18001f23b  jnb     short loc_18001F1E6
0x18001f23d  xor     eax, eax
0x18001f23f  lea     rcx, [rsp+1048h+Buffer]; Buffer
0x18001f244  mov     r9, rdi; Stream
0x18001f247  mov     [rsp+1048h+Buffer], ax
0x18001f24c  lea     edx, [rax+1]; ElementSize
0x18001f24f  lea     r8d, [rax+2]; ElementCount
0x18001f253  call    cs:__imp_fread
0x18001f259  test    rax, rax
0x18001f25c  jz      short loc_18001F287
0x18001f25e  mov     rcx, rdi
0x18001f261  call    cs:__imp__o_ferror
0x18001f267  test    eax, eax
0x18001f269  jnz     short loc_18001F2AA
0x18001f26b  movsx   ecx, [rsp+1048h+Buffer]
0x18001f270  mov     eax, 80078071h
0x18001f275  shl     ebx, 10h
0x18001f278  add     ebx, ecx
0x18001f27a  mul     ebx
0x18001f27c  shr     edx, 0Fh
0x18001f27f  imul    eax, edx, 0FFF1h
0x18001f285  sub     ebx, eax
0x18001f287  mov     rcx, rdi
0x18001f28a  call    cs:__imp__o_ferror
0x18001f290  test    eax, eax
0x18001f292  jnz     short loc_18001F2AA
0x18001f294  xor     r8d, r8d; Origin
0x18001f297  mov     edx, ebp; Offset
0x18001f299  mov     rcx, rdi; Stream
0x18001f29c  call    cs:__imp_fseek
0x18001f2a2  test    eax, eax
0x18001f2a4  jnz     short loc_18001F2AA
0x18001f2a6  mov     [rsi], ebx
0x18001f2a8  jmp     short loc_18001F2AF
0x18001f2aa  mov     eax, 8000FFFFh
0x18001f2af  mov     rcx, [rsp+1048h+var_28]
0x18001f2b7  xor     rcx, rsp; StackCookie
0x18001f2ba  call    __security_check_cookie
0x18001f2bf  mov     rbx, [rsp+1048h+arg_0]
0x18001f2c7  add     rsp, 1030h
0x18001f2ce  pop     rdi
0x18001f2cf  pop     rsi
0x18001f2d0  pop     rbp
0x18001f2d1  retn
```
