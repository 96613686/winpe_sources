# Windows::Internal::Flighting::OneSettings::OneSettingsPayload::GetPayloadUniqueId(HSTRING__ * *)

- ea: `0x180017410`
- end: `0x18001748a`
- name: `?GetPayloadUniqueId@OneSettingsPayload@OneSettings@Flighting@Internal@Windows@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `122`
- prototype: `int(Windows::Internal::Flighting::OneSettings::OneSettingsPayload *__hidden this, HSTRING *)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x18000e5ac`
- `0x180017410`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180017451`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180017451`

## string_xrefs

- `0x180017465`: `onecore\base\flighting\onesettings\libs\configurationsmanager\onesettingspayload.cpp`

## pseudocode

```c
__int64 __fastcall Windows::Internal::Flighting::OneSettings::OneSettingsPayload::GetPayloadUniqueId(
        Windows::Internal::Flighting::OneSettings::OneSettingsPayload *this,
        HSTRING *a2)
{
  const WCHAR *v3; // rcx
  __int64 v4; // rdx
  HRESULT String; // eax
  unsigned int v6; // ebx
  int v8; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v3 = *(const WCHAR **)((*((_BYTE *)this + 97) != 0 ? 0x28 : 0) + *((_QWORD *)this + 6) + 72LL);
  if ( v3 )
  {
    v4 = -1;
    do
      ++v4;
    while ( v3[v4] );
  }
  else
  {
    LODWORD(v4) = 0;
  }
  *a2 = 0;
  String = WindowsCreateString(v3, v4, a2);
  v6 = String;
  if ( String < 0 )
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1A5,
      (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\configurationsmanager\\onesettingspayload.cpp",
      (const char *)(unsigned int)String,
      v8);
  return v6;
}

```

## disassembly

```asm
0x180017410  mov     [rsp+arg_8], rbx
0x180017415  push    rdi; int
0x180017416  sub     rsp, 20h
0x18001741a  mov     r9, rdx
0x18001741d  mov     al, [rcx+61h]
0x180017420  neg     al
0x180017422  sbb     r8, r8
0x180017425  and     r8d, 28h
0x180017429  mov     rax, [rcx+30h]
0x18001742d  mov     rcx, [r8+rax+48h]; sourceString
0x180017432  xor     edi, edi
0x180017434  test    rcx, rcx
0x180017437  jz      short loc_180017448
0x180017439  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18001743d  inc     rdx
0x180017440  cmp     [rcx+rdx*2], di
0x180017444  jnz     short loc_18001743D
0x180017446  jmp     short loc_18001744B
0x180017448  mov     rdx, rdi; length
0x18001744b  mov     [r9], rdi
0x18001744e  mov     r8, r9; string
0x180017451  call    cs:__imp_WindowsCreateString
0x180017457  mov     ebx, eax
0x180017459  test    eax, eax
0x18001745b  jns     short loc_180017476
0x18001745d  mov     rcx, [rsp+28h]; this
0x180017462  mov     r9d, eax; char *
0x180017465  lea     r8, aOnecoreBaseFli_30; "onecore\\base\\flighting\\onesettings\\"...
0x18001746c  mov     edx, 1A5h; void *
0x180017471  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017476  mov     eax, ebx
0x180017478  jmp     short loc_18001747E
0x18001747a  mov     eax, [rsp+28h+arg_0]
0x18001747e  mov     rbx, [rsp+28h+arg_8]
0x180017483  add     rsp, 20h
0x180017487  pop     rdi
0x180017488  retn
```
