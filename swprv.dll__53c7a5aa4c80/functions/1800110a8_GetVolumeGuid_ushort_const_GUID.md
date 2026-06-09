# GetVolumeGuid(ushort const *,_GUID &)

- ea: `0x1800110a8`
- end: `0x180011172`
- name: `?GetVolumeGuid@@YA_NPEBGAEAU_GUID@@@Z`
- size: `202`
- prototype: `bool __fastcall(const unsigned __int16 *, struct _GUID *)`
- caller_count: `3`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180012254`
- `0x18002e7ec`
- `0x18002f070`

## callees

- `0x180001580`
- `0x180007650`
- `0x1800110a8`
- `0x1800419e4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18001113e`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18001113e`

## pseudocode

```c
bool __fastcall GetVolumeGuid(const unsigned __int16 *a1, struct _GUID *a2)
{
  __int64 v2; // rax
  size_t *v5; // r8
  wchar_t pszDest[40]; // [rsp+30h] [rbp-68h] BYREF

  v2 = -1;
  do
    ++v2;
  while ( a1[v2] );
  if ( v2 != 49
    || wcsncmp_0(a1, L"\\\\?\\Volume", 0xAu)
    || wcsncmp_0(a1 + 48, L"\\", 2u)
    || StringCopyWorkerW(pszDest, 0x27u, v5, a1 + 10, 0x26u) < 0 )
  {
    return 0;
  }
  pszDest[38] = 0;
  return CLSIDFromString(pszDest, a2) == 0;
}

```

## disassembly

```asm
0x1800110a8  mov     [rsp+arg_10], rbx
0x1800110ad  mov     [rsp+arg_18], rsi
0x1800110b2  push    rdi
0x1800110b3  sub     rsp, 90h
0x1800110ba  mov     rax, cs:__security_cookie
0x1800110c1  xor     rax, rsp
0x1800110c4  mov     [rsp+98h+var_18], rax
0x1800110cc  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800110d0  mov     rdi, rdx
0x1800110d3  xor     esi, esi
0x1800110d5  mov     rbx, rcx
0x1800110d8  inc     rax
0x1800110db  cmp     [rcx+rax*2], si
0x1800110df  jnz     short loc_1800110D8
0x1800110e1  cmp     rax, 31h ; '1'
0x1800110e5  jnz     short loc_18001114B
0x1800110e7  lea     r8d, [rax-27h]; MaxCount
0x1800110eb  lea     rdx, aVolume; "\\\\?\\Volume"
0x1800110f2  call    wcsncmp_0
0x1800110f7  test    eax, eax
0x1800110f9  jnz     short loc_18001114B
0x1800110fb  lea     rcx, [rbx+60h]; String1
0x1800110ff  lea     r8d, [rax+2]; MaxCount
0x180011103  lea     rdx, asc_180053DF0; "\\"
0x18001110a  call    wcsncmp_0
0x18001110f  test    eax, eax
0x180011111  jnz     short loc_18001114B
0x180011113  lea     r9, [rbx+14h]; pszSrc
0x180011117  mov     [rsp+98h+cchToCopy], 26h ; '&'; cchToCopy
0x180011120  lea     edx, [rax+27h]; cchDest
0x180011123  lea     rcx, [rsp+98h+pszDest]; pszDest
0x180011128  call    StringCopyWorkerW
0x18001112d  test    eax, eax
0x18001112f  js      short loc_18001114B
0x180011131  mov     rdx, rdi; pclsid
0x180011134  mov     [rsp+98h+var_1C], si
0x180011139  lea     rcx, [rsp+98h+pszDest]; lpsz
0x18001113e  call    cs:__imp_CLSIDFromString
0x180011144  test    eax, eax
0x180011146  setz    al
0x180011149  jmp     short loc_18001114D
0x18001114b  xor     al, al
0x18001114d  mov     rcx, [rsp+98h+var_18]
0x180011155  xor     rcx, rsp; StackCookie
0x180011158  call    __security_check_cookie
0x18001115d  lea     r11, [rsp+98h+var_8]
0x180011165  mov     rbx, [r11+20h]
0x180011169  mov     rsi, [r11+28h]
0x18001116d  mov     rsp, r11
0x180011170  pop     rdi
0x180011171  retn
```
