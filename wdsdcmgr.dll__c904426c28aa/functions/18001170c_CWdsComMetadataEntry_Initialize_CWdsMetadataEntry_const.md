# CWdsComMetadataEntry::Initialize(CWdsMetadataEntry const *)

- ea: `0x18001170c`
- end: `0x18001184b`
- name: `?Initialize@CWdsComMetadataEntry@@AEAAJPEBVCWdsMetadataEntry@@@Z`
- size: `319`
- prototype: `__int64 __fastcall(CWdsComMetadataEntry *__hidden this, const struct CWdsMetadataEntry *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180011854`

## callees

- `0x180009894`
- `0x18000a380`
- `0x18001170c`
- `0x180013dcc`
- `0x180014d58`

## string_xrefs

- `0x18001180e`: `base\eco\wds\lib\metadata\com\wdscommetadataentry.cpp`

## pseudocode

```c
__int64 __fastcall CWdsComMetadataEntry::Initialize(unsigned __int16 **this, const unsigned __int16 **a2)
{
  unsigned __int16 **v3; // rbp
  unsigned int v4; // ebx
  signed int v5; // edi
  const char *v6; // rdx
  const char *v7; // rdx
  const char *v8; // rdx
  const unsigned __int16 *v9; // rcx
  const char *v10; // rdx
  const unsigned __int16 *v11; // rcx
  const char *v12; // rdx
  const char *v13; // rdx

  v3 = this + 8;
  v4 = 0;
  v5 = DuplicateStringW(*a2, this + 8);
  if ( !ElValidateWin32(v5, v6, "base\\eco\\wds\\lib\\metadata\\core\\metadata.cpp", 0x912u) )
  {
    v5 = DuplicateStringW(a2[1], v3 + 1);
    if ( !ElValidateWin32(v5, v8, "base\\eco\\wds\\lib\\metadata\\core\\metadata.cpp", 0x915u) )
    {
      v9 = a2[2];
      if ( !v9
        || (v5 = DuplicateStringW(v9, v3 + 2),
            !ElValidateWin32(v5, v10, "base\\eco\\wds\\lib\\metadata\\core\\metadata.cpp", 0x91Au)) )
      {
        v11 = a2[3];
        if ( !v11
          || (v5 = DuplicateStringW(v11, v3 + 3),
              !ElValidateWin32(v5, v12, "base\\eco\\wds\\lib\\metadata\\core\\metadata.cpp", 0x920u)) )
        {
          v5 = CWdsMetadataValue::Initialize((CWdsMetadataValue *)(v3 + 5), (wchar_t *)a2[1]);
          if ( !ElValidateWin32(v5, v13, "base\\eco\\wds\\lib\\metadata\\core\\metadata.cpp", 0x924u) )
          {
            *((_DWORD *)v3 + 8) = *((_DWORD *)a2 + 8);
            *((_DWORD *)v3 + 9) = *((_DWORD *)a2 + 9);
          }
        }
      }
    }
  }
  if ( v5 )
    CWdsMetadataEntry::Shutdown((CWdsMetadataEntry *)v3);
  if ( ElValidateWin32(v5, v7, "base\\eco\\wds\\lib\\metadata\\com\\wdscommetadataentry.cpp", 0x61u) )
  {
    v4 = (unsigned __int16)v5 | 0x80070000;
    if ( v5 <= 0 )
      return (unsigned int)v5;
  }
  return v4;
}

```

## disassembly

```asm
0x18001170c  mov     rax, rsp
0x18001170f  mov     [rax+8], rbx
0x180011713  mov     [rax+10h], rbp
0x180011717  mov     [rax+18h], rsi
0x18001171b  mov     [rax+20h], rdi
0x18001171f  push    r14
0x180011721  sub     rsp, 20h
0x180011725  mov     rsi, rdx
0x180011728  lea     rbp, [rcx+40h]
0x18001172c  mov     rdx, rbp; unsigned __int16 **
0x18001172f  xor     ebx, ebx
0x180011731  mov     rcx, [rsi]; unsigned __int16 *
0x180011734  call    ?DuplicateStringW@@YAKPEBGPEAPEAG@Z; DuplicateStringW(ushort const *,ushort * *)
0x180011739  lea     r14, aBaseEcoWdsLibM; "base\\eco\\wds\\lib\\metadata\\core\\me"...
0x180011740  mov     r9d, 912h; unsigned int
0x180011746  mov     r8, r14; char *
0x180011749  mov     ecx, eax; unsigned int
0x18001174b  mov     edi, eax
0x18001174d  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180011752  test    eax, eax
0x180011754  jnz     loc_1800117FC
0x18001175a  mov     rcx, [rsi+8]; unsigned __int16 *
0x18001175e  lea     rdx, [rbp+8]; unsigned __int16 **
0x180011762  call    ?DuplicateStringW@@YAKPEBGPEAPEAG@Z; DuplicateStringW(ushort const *,ushort * *)
0x180011767  mov     r9d, 915h; unsigned int
0x18001176d  mov     r8, r14; char *
0x180011770  mov     ecx, eax; unsigned int
0x180011772  mov     edi, eax
0x180011774  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180011779  test    eax, eax
0x18001177b  jnz     short loc_1800117FC
0x18001177d  mov     rcx, [rsi+10h]; unsigned __int16 *
0x180011781  test    rcx, rcx
0x180011784  jz      short loc_1800117A5
0x180011786  lea     rdx, [rbp+10h]; unsigned __int16 **
0x18001178a  call    ?DuplicateStringW@@YAKPEBGPEAPEAG@Z; DuplicateStringW(ushort const *,ushort * *)
0x18001178f  mov     r9d, 91Ah; unsigned int
0x180011795  mov     r8, r14; char *
0x180011798  mov     ecx, eax; unsigned int
0x18001179a  mov     edi, eax
0x18001179c  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x1800117a1  test    eax, eax
0x1800117a3  jnz     short loc_1800117FC
0x1800117a5  mov     rcx, [rsi+18h]; unsigned __int16 *
0x1800117a9  test    rcx, rcx
0x1800117ac  jz      short loc_1800117CD
0x1800117ae  lea     rdx, [rbp+18h]; unsigned __int16 **
0x1800117b2  call    ?DuplicateStringW@@YAKPEBGPEAPEAG@Z; DuplicateStringW(ushort const *,ushort * *)
0x1800117b7  mov     r9d, 920h; unsigned int
0x1800117bd  mov     r8, r14; char *
0x1800117c0  mov     ecx, eax; unsigned int
0x1800117c2  mov     edi, eax
0x1800117c4  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x1800117c9  test    eax, eax
0x1800117cb  jnz     short loc_1800117FC
0x1800117cd  mov     rdx, [rsi+8]; unsigned __int16 *
0x1800117d1  lea     rcx, [rbp+28h]; this
0x1800117d5  call    ?Initialize@CWdsMetadataValue@@QEAAKPEBG@Z; CWdsMetadataValue::Initialize(ushort const *)
0x1800117da  mov     r9d, 924h; unsigned int
0x1800117e0  mov     r8, r14; char *
0x1800117e3  mov     ecx, eax; unsigned int
0x1800117e5  mov     edi, eax
0x1800117e7  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x1800117ec  test    eax, eax
0x1800117ee  jnz     short loc_1800117FC
0x1800117f0  mov     eax, [rsi+20h]
0x1800117f3  mov     [rbp+20h], eax
0x1800117f6  mov     eax, [rsi+24h]
0x1800117f9  mov     [rbp+24h], eax
0x1800117fc  test    edi, edi
0x1800117fe  jz      short loc_180011808
0x180011800  mov     rcx, rbp; this
0x180011803  call    ?Shutdown@CWdsMetadataEntry@@QEAAXXZ; CWdsMetadataEntry::Shutdown(void)
0x180011808  mov     r9d, 61h ; 'a'; unsigned int
0x18001180e  lea     r8, aBaseEcoWdsLibM_2; "base\\eco\\wds\\lib\\metadata\\com\\wds"...
0x180011815  mov     ecx, edi; unsigned int
0x180011817  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18001181c  test    eax, eax
0x18001181e  jz      short loc_18001182E
0x180011820  movzx   ebx, di
0x180011823  or      ebx, 80070000h
0x180011829  test    edi, edi
0x18001182b  cmovle  ebx, edi
0x18001182e  mov     rbp, [rsp+28h+arg_8]
0x180011833  mov     eax, ebx
0x180011835  mov     rbx, [rsp+28h+arg_0]
0x18001183a  mov     rsi, [rsp+28h+arg_10]
0x18001183f  mov     rdi, [rsp+28h+arg_18]
0x180011844  add     rsp, 20h
0x180011848  pop     r14
0x18001184a  retn
```
