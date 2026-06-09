# HTTP_WRAPPER::CreateConfigGroup(unsigned __int64 *)

- ea: `0x1800132cc`
- end: `0x18001332f`
- name: `?CreateConfigGroup@HTTP_WRAPPER@@QEAAKPEA_K@Z`
- size: `99`
- prototype: `unsigned int __fastcall(HTTP_WRAPPER *__hidden this, unsigned __int64 *)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180012530`
- `0x1800143dc`

## callees

- `0x1800132cc`
- `0x180013338`

## import_xrefs

- `HTTPAPI!HttpCreateUrlGroup` at `0x1800132e8`
- `HTTPAPI!HttpCreateUrlGroup` at `0x1800132e8`
- `HTTPAPI!HttpCloseUrlGroup` at `0x180013310`
- `HTTPAPI!HttpCloseUrlGroup` at `0x180013310`

## pseudocode

```c
__int64 __fastcall HTTP_WRAPPER::CreateConfigGroup(HTTP_WRAPPER *this, unsigned __int64 *a2)
{
  ULONG UrlGroup; // edi

  UrlGroup = HttpCreateUrlGroup(*((_QWORD *)this + 2), a2, 0);
  if ( UrlGroup || (UrlGroup = HTTP_WRAPPER::SetConfigGroupState(this, *a2, 0)) != 0 )
  {
    if ( *a2 )
    {
      HttpCloseUrlGroup(*a2);
      *a2 = 0;
    }
  }
  return UrlGroup;
}

```

## disassembly

```asm
0x1800132cc  mov     [rsp+arg_0], rbx
0x1800132d1  mov     [rsp+arg_8], rsi
0x1800132d6  push    rdi
0x1800132d7  sub     rsp, 20h
0x1800132db  mov     rsi, rcx
0x1800132de  xor     r8d, r8d; Reserved
0x1800132e1  mov     rcx, [rcx+10h]; ServerSessionId
0x1800132e5  mov     rbx, rdx
0x1800132e8  call    cs:__imp_HttpCreateUrlGroup
0x1800132ee  mov     edi, eax
0x1800132f0  test    eax, eax
0x1800132f2  jnz     short loc_180013308
0x1800132f4  mov     rdx, [rbx]; unsigned __int64
0x1800132f7  xor     r8d, r8d; int
0x1800132fa  mov     rcx, rsi; this
0x1800132fd  call    ?SetConfigGroupState@HTTP_WRAPPER@@QEAAK_KH@Z; HTTP_WRAPPER::SetConfigGroupState(unsigned __int64,int)
0x180013302  mov     edi, eax
0x180013304  test    eax, eax
0x180013306  jz      short loc_18001331D
0x180013308  mov     rcx, [rbx]; UrlGroupId
0x18001330b  test    rcx, rcx
0x18001330e  jz      short loc_18001331D
0x180013310  call    cs:__imp_HttpCloseUrlGroup
0x180013316  mov     qword ptr [rbx], 0
0x18001331d  mov     rbx, [rsp+28h+arg_0]
0x180013322  mov     eax, edi
0x180013324  mov     rsi, [rsp+28h+arg_8]
0x180013329  add     rsp, 20h
0x18001332d  pop     rdi
0x18001332e  retn
```
