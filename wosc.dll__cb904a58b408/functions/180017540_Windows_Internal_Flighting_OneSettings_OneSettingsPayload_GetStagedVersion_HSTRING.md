# Windows::Internal::Flighting::OneSettings::OneSettingsPayload::GetStagedVersion(HSTRING__ * *)

- ea: `0x180017540`
- end: `0x1800175b5`
- name: `?GetStagedVersion@OneSettingsPayload@OneSettings@Flighting@Internal@Windows@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `117`
- prototype: `int(Windows::Internal::Flighting::OneSettings::OneSettingsPayload *__hidden this, HSTRING *)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x1800101fc`
- `0x180017540`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18001757c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18001757c`

## string_xrefs

- `0x18001758e`: `onecore\base\flighting\onesettings\libs\configurationsmanager\onesettingspayload.cpp`

## pseudocode

```c
__int64 __fastcall Windows::Internal::Flighting::OneSettings::OneSettingsPayload::GetStagedVersion(
        Windows::Internal::Flighting::OneSettings::OneSettingsPayload *this,
        HSTRING *a2)
{
  const WCHAR *v3; // rcx
  const WCHAR *v4; // rax
  __int64 v5; // rdx
  HRESULT String; // eax
  const char *v8; // r9
  __int64 v9; // rdx
  int v10; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  unsigned int v12; // [rsp+30h] [rbp+8h]

  *a2 = 0;
  v3 = *(const WCHAR **)(*((_QWORD *)this + 4) + 344LL);
  v4 = &String1;
  if ( v3 )
    v4 = v3;
  if ( !*v4 )
    return 2147943568LL;
  v5 = -1;
  do
    ++v5;
  while ( v4[v5] );
  String = WindowsCreateString(v4, v5, a2);
  if ( String < 0 )
  {
    try
    {
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x179,
        (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\configurationsmanager\\onesettingspayload.cpp",
        (const char *)(unsigned int)String,
        v10);
    }
    catch ( ... )
    {
      *(_DWORD *)(v9 + 48) = wil::details::in1diag3::Return_CaughtException(
                               retaddr,
                               (void *)0x17B,
                               (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\configurationsmanager\\onesettingspayload.cpp",
                               v8);
      return v12;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180017540  push    rbx; int
0x180017542  sub     rsp, 20h
0x180017546  mov     r8, rdx; string
0x180017549  xor     ebx, ebx
0x18001754b  mov     [rdx], rbx
0x18001754e  mov     rax, [rcx+20h]
0x180017552  mov     rcx, [rax+158h]
0x180017559  lea     rax, String1
0x180017560  test    rcx, rcx
0x180017563  cmovnz  rax, rcx
0x180017567  cmp     [rax], bx
0x18001756a  jz      short loc_1800175A3
0x18001756c  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180017570  inc     rdx; length
0x180017573  cmp     [rax+rdx*2], bx
0x180017577  jnz     short loc_180017570
0x180017579  mov     rcx, rax; sourceString
0x18001757c  call    cs:__imp_WindowsCreateString
0x180017582  mov     rcx, [rsp+28h]; this
0x180017587  test    eax, eax
0x180017589  jns     short loc_18001759F
0x18001758b  mov     r9d, eax; char *
0x18001758e  lea     r8, aOnecoreBaseFli_30; "onecore\\base\\flighting\\onesettings\\"...
0x180017595  mov     edx, 179h; void *
0x18001759a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001759f  xor     eax, eax
0x1800175a1  jmp     short loc_1800175AE
0x1800175a3  mov     eax, 80070490h
0x1800175a8  jmp     short loc_1800175AE
0x1800175aa  mov     eax, [rsp+28h+arg_0]
0x1800175ae  add     rsp, 20h
0x1800175b2  pop     rbx
0x1800175b3  retn
```
