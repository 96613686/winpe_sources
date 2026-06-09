# GetInstanceIdFromDevName

- ea: `0x1800049fc`
- end: `0x180004ad4`
- name: `GetInstanceIdFromDevName`
- size: `216`
- prototype: `__int64 __fastcall(wchar_t *String2, LPIID lpiid)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800048b0`

## callees

- `0x1800049fc`
- `0x180005d94`
- `0x180005db8`
- `0x180007984`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180004a4f`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180004a4f`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x180004a8c`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x180004a8c`

## string_xrefs

- `0x180004a30`: `onecore\vm\dv\vmbus\pipes\dll\client.cpp`
- `0x180004aab`: `onecore\vm\dv\vmbus\pipes\dll\client.cpp`

## pseudocode

```c
int __fastcall GetInstanceIdFromDevName(wchar_t *String2, LPIID lpiid)
{
  __int64 v4; // rdx
  wchar_t *v6; // rdi
  unsigned __int64 v7; // rax
  wchar_t v8; // bx
  HRESULT v9; // eax
  unsigned int v10; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  if ( wcsncmp_0(L"VMBUS\\", String2, 6u) )
  {
    v4 = 413;
    return wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)v4,
             (unsigned int)"onecore\\vm\\dv\\vmbus\\pipes\\dll\\client.cpp",
             (const char *)0xD,
             v10);
  }
  v6 = wcsrchr(String2, 0x7Bu);
  if ( !v6 )
  {
    v4 = 422;
    return wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)v4,
             (unsigned int)"onecore\\vm\\dv\\vmbus\\pipes\\dll\\client.cpp",
             (const char *)0xD,
             v10);
  }
  v7 = -1;
  do
    ++v7;
  while ( v6[v7] );
  if ( v7 < 0x26 )
  {
    v4 = 427;
    return wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)v4,
             (unsigned int)"onecore\\vm\\dv\\vmbus\\pipes\\dll\\client.cpp",
             (const char *)0xD,
             v10);
  }
  v8 = v6[38];
  v6[38] = 0;
  v9 = IIDFromString(v6, lpiid);
  v6[38] = v8;
  if ( v9 >= 0 )
    return 0;
  else
    return wil::details::in1diag3::Return_Win32Msg(
             retaddr,
             (void *)0x1B9,
             (unsigned int)"onecore\\vm\\dv\\vmbus\\pipes\\dll\\client.cpp",
             (const char *)0xD,
             (unsigned int)"%ls",
             (const char *)v6);
}

```

## disassembly

```asm
0x1800049fc  push    rbx
0x1800049fe  push    rbp
0x1800049ff  push    rsi
0x180004a00  push    rdi
0x180004a01  sub     rsp, 38h
0x180004a05  mov     rsi, rdx
0x180004a08  mov     rbx, rcx
0x180004a0b  mov     rdx, rcx; String2
0x180004a0e  mov     r8d, 6; MaxCount
0x180004a14  lea     rcx, aVmbus; "VMBUS\\"
0x180004a1b  call    wcsncmp_0
0x180004a20  xor     ebp, ebp
0x180004a22  test    eax, eax
0x180004a24  jz      short loc_180004A47
0x180004a26  mov     edx, 19Dh; void *
0x180004a2b  mov     rcx, [rsp+58h]; this
0x180004a30  lea     r8, aOnecoreVmDvVmb; "onecore\\vm\\dv\\vmbus\\pipes\\dll\\cli"...
0x180004a37  mov     r9d, 0Dh; char *
0x180004a3d  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180004a42  jmp     loc_180004ACB
0x180004a47  mov     edx, 7Bh ; '{'; Ch
0x180004a4c  mov     rcx, rbx; Str
0x180004a4f  call    cs:__imp_wcsrchr
0x180004a55  mov     rdi, rax
0x180004a58  test    rax, rax
0x180004a5b  jnz     short loc_180004A64
0x180004a5d  mov     edx, 1A6h
0x180004a62  jmp     short loc_180004A2B
0x180004a64  or      rax, 0FFFFFFFFFFFFFFFFh
0x180004a68  inc     rax
0x180004a6b  cmp     [rdi+rax*2], bp
0x180004a6f  jnz     short loc_180004A68
0x180004a71  cmp     rax, 26h ; '&'
0x180004a75  jnb     short loc_180004A7E
0x180004a77  mov     edx, 1ABh
0x180004a7c  jmp     short loc_180004A2B
0x180004a7e  movzx   ebx, word ptr [rdi+4Ch]
0x180004a82  mov     rdx, rsi; lpiid
0x180004a85  mov     rcx, rdi; lpsz
0x180004a88  mov     [rdi+4Ch], bp
0x180004a8c  call    cs:__imp_IIDFromString
0x180004a92  mov     [rdi+4Ch], bx
0x180004a96  test    eax, eax
0x180004a98  jns     short loc_180004AC9
0x180004a9a  mov     rcx, [rsp+58h]; this
0x180004a9f  lea     rax, aLs; "%ls"
0x180004aa6  mov     [rsp+58h+var_30], rdi; char *
0x180004aab  lea     r8, aOnecoreVmDvVmb; "onecore\\vm\\dv\\vmbus\\pipes\\dll\\cli"...
0x180004ab2  mov     r9d, 0Dh; char *
0x180004ab8  mov     qword ptr [rsp+58h+var_38], rax; unsigned int
0x180004abd  mov     edx, 1B9h; void *
0x180004ac2  call    ?Return_Win32Msg@in1diag3@details@wil@@YAJPEAXIPEBDK1ZZ; wil::details::in1diag3::Return_Win32Msg(void *,uint,char const *,ulong,char const *,...)
0x180004ac7  jmp     short loc_180004ACB
0x180004ac9  xor     eax, eax
0x180004acb  add     rsp, 38h
0x180004acf  pop     rdi
0x180004ad0  pop     rsi
0x180004ad1  pop     rbp
0x180004ad2  pop     rbx
0x180004ad3  retn
```
