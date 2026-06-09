# CSsdpNotifyRequest::FIsMatchingEvent(_SSDP_REQUEST const *)

- ea: `0x180021d84`
- end: `0x180021e5b`
- name: `?FIsMatchingEvent@CSsdpNotifyRequest@@QEAAHPEBU_SSDP_REQUEST@@@Z`
- size: `215`
- prototype: `__int64 __fastcall(CSsdpNotifyRequest *__hidden this, const struct _SSDP_REQUEST *)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18001ce24`
- `0x18002e12c`

## callees

- `0x180013e70`
- `0x180014ea0`
- `0x180021d84`
- `0x180035274`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x180021e3a`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x180021e3a`
- `api-ms-win-crt-private-l1-1-0!_o__strnicmp` at `0x180021df3`
- `api-ms-win-crt-private-l1-1-0!_o__strnicmp` at `0x180021df3`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180021e4a`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180021e4a`

## string_xrefs

- `0x180021dec`: `text/xml`

## pseudocode

```c
__int64 __fastcall CSsdpNotifyRequest::FIsMatchingEvent(CSsdpNotifyRequest *this, const struct _SSDP_REQUEST *a2)
{
  __int64 v2; // rbp
  unsigned int v4; // ebx
  const char *v6; // rcx
  unsigned __int8 *v7; // rax
  int v8; // r9d
  int v9; // edx
  const char *v10; // rcx
  CUString *v11; // rcx
  void *Block; // [rsp+58h] [rbp+10h] BYREF

  v2 = *((_QWORD *)a2 + 10);
  v4 = 0;
  v6 = *(const char **)(v2 + 16);
  if ( v6 )
  {
    v7 = *(unsigned __int8 **)(v2 + 16);
    do
    {
      v8 = v7["upnp:dead" - v6];
      v9 = *v7 - v8;
      if ( v9 )
        break;
      ++v7;
    }
    while ( v8 );
    if ( !v9
      || !strcmp_0(v6, "upnp:propchange")
      && (v10 = *(const char **)(v2 + 128)) != 0
      && !_strnicmp(v10, "text/xml", 8u)
      && *(_DWORD *)this == 1 )
    {
      if ( CUString::GetLength((CSsdpNotifyRequest *)((char *)this + 72)) )
      {
        if ( *(_QWORD *)(*((_QWORD *)a2 + 10) + 104LL) )
        {
          Block = 0;
          if ( (int)CUString::HrGetMultiByteWithAlloc(v11, (char **)&Block) >= 0 )
          {
            LOBYTE(v4) = (unsigned int)_o__stricmp(*(_QWORD *)(*((_QWORD *)a2 + 10) + 104LL), Block) == 0;
            free(Block);
          }
        }
      }
    }
  }
  return v4;
}

```

## disassembly

```asm
0x180021d84  push    rbx
0x180021d86  push    rbp
0x180021d87  push    rsi
0x180021d88  push    rdi
0x180021d89  sub     rsp, 28h
0x180021d8d  mov     rbp, [rdx+50h]
0x180021d91  mov     rsi, rcx
0x180021d94  xor     ebx, ebx
0x180021d96  mov     rdi, rdx
0x180021d99  mov     rcx, [rbp+10h]; Str1
0x180021d9d  test    rcx, rcx
0x180021da0  jz      loc_180021E50
0x180021da6  lea     r8, aUpnpDead; "upnp:dead"
0x180021dad  mov     rax, rcx
0x180021db0  sub     r8, rcx
0x180021db3  movzx   edx, byte ptr [rax]
0x180021db6  movzx   r9d, byte ptr [rax+r8]
0x180021dbb  sub     edx, r9d
0x180021dbe  jnz     short loc_180021DC8
0x180021dc0  inc     rax
0x180021dc3  test    r9d, r9d
0x180021dc6  jnz     short loc_180021DB3
0x180021dc8  test    edx, edx
0x180021dca  jz      short loc_180021E02
0x180021dcc  lea     rdx, aUpnpPropchange; "upnp:propchange"
0x180021dd3  call    strcmp_0
0x180021dd8  test    eax, eax
0x180021dda  jnz     short loc_180021E50
0x180021ddc  mov     rcx, [rbp+80h]; String1
0x180021de3  test    rcx, rcx
0x180021de6  jz      short loc_180021E50
0x180021de8  lea     r8d, [rax+8]; MaxCount
0x180021dec  lea     rdx, aTextXml; "text/xml"
0x180021df3  call    cs:__imp__strnicmp
0x180021df9  test    eax, eax
0x180021dfb  jnz     short loc_180021E50
0x180021dfd  cmp     dword ptr [rsi], 1
0x180021e00  jnz     short loc_180021E50
0x180021e02  lea     rcx, [rsi+48h]; this
0x180021e06  call    ?GetLength@CUString@@QEBA_KXZ; CUString::GetLength(void)
0x180021e0b  test    rax, rax
0x180021e0e  jz      short loc_180021E50
0x180021e10  mov     rax, [rdi+50h]
0x180021e14  cmp     [rax+68h], rbx
0x180021e18  jz      short loc_180021E50
0x180021e1a  lea     rdx, [rsp+48h+Block]; char **
0x180021e1f  mov     [rsp+48h+Block], rbx
0x180021e24  call    ?HrGetMultiByteWithAlloc@CUString@@QEBAJPEAPEAD@Z; CUString::HrGetMultiByteWithAlloc(char * *)
0x180021e29  test    eax, eax
0x180021e2b  js      short loc_180021E50
0x180021e2d  mov     rcx, [rdi+50h]
0x180021e31  mov     rdx, [rsp+48h+Block]
0x180021e36  mov     rcx, [rcx+68h]
0x180021e3a  call    cs:__imp__o__stricmp
0x180021e40  mov     rcx, [rsp+48h+Block]; Block
0x180021e45  test    eax, eax
0x180021e47  setz    bl
0x180021e4a  call    cs:__imp_free
0x180021e50  mov     eax, ebx
0x180021e52  add     rsp, 28h
0x180021e56  pop     rdi
0x180021e57  pop     rsi
0x180021e58  pop     rbp
0x180021e59  pop     rbx
0x180021e5a  retn
```
