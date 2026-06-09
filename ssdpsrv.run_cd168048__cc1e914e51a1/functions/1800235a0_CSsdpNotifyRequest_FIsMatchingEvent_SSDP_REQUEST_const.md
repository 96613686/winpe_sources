# CSsdpNotifyRequest::FIsMatchingEvent(_SSDP_REQUEST const *)

- ea: `0x1800235a0`
- end: `0x18002368e`
- name: `?FIsMatchingEvent@CSsdpNotifyRequest@@QEAAHPEBU_SSDP_REQUEST@@@Z`
- size: `238`
- prototype: `__int64 __fastcall(CSsdpNotifyRequest *__hidden this, const struct _SSDP_REQUEST *)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18001e2c4`
- `0x180030274`

## callees

- `0x180014f80`
- `0x1800174b0`
- `0x1800235a0`
- `0x180037db4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x180023660`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x180023660`
- `api-ms-win-crt-private-l1-1-0!_o__strnicmp` at `0x180023613`
- `api-ms-win-crt-private-l1-1-0!_o__strnicmp` at `0x180023613`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180023676`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180023676`

## string_xrefs

- `0x18002360c`: `text/xml`

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
0x1800235a0  push    rbx
0x1800235a2  push    rbp
0x1800235a3  push    rsi
0x1800235a4  push    rdi
0x1800235a5  sub     rsp, 28h
0x1800235a9  mov     rbp, [rdx+50h]
0x1800235ad  mov     rsi, rcx
0x1800235b0  xor     ebx, ebx
0x1800235b2  mov     rdi, rdx
0x1800235b5  mov     rcx, [rbp+10h]; Str1
0x1800235b9  test    rcx, rcx
0x1800235bc  jz      loc_180023682
0x1800235c2  lea     r8, aUpnpDead; "upnp:dead"
0x1800235c9  mov     rax, rcx
0x1800235cc  sub     r8, rcx
0x1800235cf  movzx   edx, byte ptr [rax]
0x1800235d2  movzx   r9d, byte ptr [rax+r8]
0x1800235d7  sub     edx, r9d
0x1800235da  jnz     short loc_1800235E4
0x1800235dc  inc     rax
0x1800235df  test    r9d, r9d
0x1800235e2  jnz     short loc_1800235CF
0x1800235e4  test    edx, edx
0x1800235e6  jz      short loc_180023628
0x1800235e8  lea     rdx, aUpnpPropchange; "upnp:propchange"
0x1800235ef  call    strcmp_0
0x1800235f4  test    eax, eax
0x1800235f6  jnz     loc_180023682
0x1800235fc  mov     rcx, [rbp+80h]; String1
0x180023603  test    rcx, rcx
0x180023606  jz      short loc_180023682
0x180023608  lea     r8d, [rax+8]; MaxCount
0x18002360c  lea     rdx, aTextXml; "text/xml"
0x180023613  call    cs:__imp__strnicmp
0x18002361a  nop     dword ptr [rax+rax+00h]
0x18002361f  test    eax, eax
0x180023621  jnz     short loc_180023682
0x180023623  cmp     dword ptr [rsi], 1
0x180023626  jnz     short loc_180023682
0x180023628  lea     rcx, [rsi+48h]; this
0x18002362c  call    ?GetLength@CUString@@QEBA_KXZ; CUString::GetLength(void)
0x180023631  test    rax, rax
0x180023634  jz      short loc_180023682
0x180023636  mov     rax, [rdi+50h]
0x18002363a  cmp     [rax+68h], rbx
0x18002363e  jz      short loc_180023682
0x180023640  lea     rdx, [rsp+48h+Block]; char **
0x180023645  mov     [rsp+48h+Block], rbx
0x18002364a  call    ?HrGetMultiByteWithAlloc@CUString@@QEBAJPEAPEAD@Z; CUString::HrGetMultiByteWithAlloc(char * *)
0x18002364f  test    eax, eax
0x180023651  js      short loc_180023682
0x180023653  mov     rcx, [rdi+50h]
0x180023657  mov     rdx, [rsp+48h+Block]
0x18002365c  mov     rcx, [rcx+68h]
0x180023660  call    cs:__imp__o__stricmp
0x180023667  nop     dword ptr [rax+rax+00h]
0x18002366c  mov     rcx, [rsp+48h+Block]; Block
0x180023671  test    eax, eax
0x180023673  setz    bl
0x180023676  call    cs:__imp_free
0x18002367d  nop     dword ptr [rax+rax+00h]
0x180023682  mov     eax, ebx
0x180023684  add     rsp, 28h
0x180023688  pop     rdi
0x180023689  pop     rsi
0x18002368a  pop     rbp
0x18002368b  pop     rbx
0x18002368c  retn
```
