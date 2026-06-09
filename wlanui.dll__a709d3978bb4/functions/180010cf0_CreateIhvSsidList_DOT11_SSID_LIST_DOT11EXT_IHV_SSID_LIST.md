# CreateIhvSsidList(DOT11_SSID_LIST *,_DOT11EXT_IHV_SSID_LIST * *)

- ea: `0x180010cf0`
- end: `0x180010d84`
- name: `?CreateIhvSsidList@@YAKPEAUDOT11_SSID_LIST@@PEAPEAU_DOT11EXT_IHV_SSID_LIST@@@Z`
- size: `148`
- prototype: `unsigned int __fastcall(struct DOT11_SSID_LIST *, struct _DOT11EXT_IHV_SSID_LIST **)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x180008498`
- `0x18000dc38`

## callees

- `0x180001d8c`
- `0x180001e26`
- `0x180010cf0`

## pseudocode

```c
__int64 __fastcall CreateIhvSsidList(struct DOT11_SSID_LIST *a1, struct _DOT11EXT_IHV_SSID_LIST **a2)
{
  unsigned int v2; // ebx
  __int64 uTotalNumOfEntries; // rcx
  unsigned int v6; // r8d
  size_t v7; // rbp
  struct _DOT11EXT_IHV_SSID_LIST *v8; // rax

  v2 = 0;
  if ( !*a2 )
  {
    if ( a1 )
    {
      uTotalNumOfEntries = a1->uTotalNumOfEntries;
      if ( (_DWORD)uTotalNumOfEntries )
      {
        v6 = 36 * uTotalNumOfEntries;
        v7 = (unsigned int)(36 * uTotalNumOfEntries);
        if ( v7 / 0x24 == uTotalNumOfEntries && v6 + 4 >= v6 )
        {
          v8 = (struct _DOT11EXT_IHV_SSID_LIST *)operator new[](v6 + 4, (const struct std::nothrow_t *)&std::nothrow);
          *a2 = v8;
          if ( v8 )
          {
            v8->ulCount = a1->uTotalNumOfEntries;
            memcpy_0((*a2)->SSIDs, a1->SSIDs, v7);
          }
          else
          {
            return 14;
          }
        }
        else
        {
          return 534;
        }
      }
    }
  }
  return v2;
}

```

## disassembly

```asm
0x180010cf0  push    rbx
0x180010cf2  push    rbp
0x180010cf3  push    rsi
0x180010cf4  push    rdi
0x180010cf5  sub     rsp, 28h
0x180010cf9  xor     ebx, ebx
0x180010cfb  mov     rsi, rdx
0x180010cfe  mov     rdi, rcx
0x180010d01  cmp     [rdx], rbx
0x180010d04  jnz     short loc_180010D79
0x180010d06  test    rcx, rcx
0x180010d09  jz      short loc_180010D79
0x180010d0b  mov     ecx, [rcx+8]
0x180010d0e  test    ecx, ecx
0x180010d10  jz      short loc_180010D79
0x180010d12  lea     eax, [rcx+rcx*8]
0x180010d15  lea     r8d, ds:0[rax*4]
0x180010d1d  mov     rax, 0E38E38E38E38E38Fh
0x180010d27  mov     ebp, r8d
0x180010d2a  mul     rbp
0x180010d2d  shr     rdx, 5
0x180010d31  cmp     rdx, rcx
0x180010d34  jz      short loc_180010D3D
0x180010d36  mov     ebx, 216h
0x180010d3b  jmp     short loc_180010D79
0x180010d3d  lea     eax, [r8+4]
0x180010d41  cmp     eax, r8d
0x180010d44  jb      short loc_180010D36
0x180010d46  mov     ecx, eax; unsigned __int64
0x180010d48  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180010d4f  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180010d54  mov     [rsi], rax
0x180010d57  test    rax, rax
0x180010d5a  jnz     short loc_180010D61
0x180010d5c  lea     ebx, [rax+0Eh]
0x180010d5f  jmp     short loc_180010D79
0x180010d61  mov     ecx, [rdi+8]
0x180010d64  lea     rdx, [rdi+0Ch]; Src
0x180010d68  mov     [rax], ecx
0x180010d6a  mov     r8, rbp; Size
0x180010d6d  mov     rcx, [rsi]
0x180010d70  add     rcx, 4; void *
0x180010d74  call    memcpy_0
0x180010d79  mov     eax, ebx
0x180010d7b  add     rsp, 28h
0x180010d7f  pop     rdi
0x180010d80  pop     rsi
0x180010d81  pop     rbp
0x180010d82  pop     rbx
0x180010d83  retn
```
