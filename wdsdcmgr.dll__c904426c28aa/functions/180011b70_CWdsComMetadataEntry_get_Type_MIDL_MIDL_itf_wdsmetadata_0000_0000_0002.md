# CWdsComMetadataEntry::get_Type(__MIDL___MIDL_itf_wdsmetadata_0000_0000_0002 *)

- ea: `0x180011b70`
- end: `0x180011c2f`
- name: `?get_Type@CWdsComMetadataEntry@@UEAAJPEAW4__MIDL___MIDL_itf_wdsmetadata_0000_0000_0002@@@Z`
- size: `191`
- prototype: `__int64 __fastcall(CWdsComMetadataEntry *__hidden this, enum __MIDL___MIDL_itf_wdsmetadata_0000_0000_0002 *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180011b70`
- `0x180014ee0`

## string_xrefs

- `0x180011b91`: `base\eco\wds\lib\metadata\com\wdscommetadataentry.cpp`
- `0x180011bd4`: `base\eco\wds\lib\metadata\com\wdscommetadataentry.cpp`

## pseudocode

```c
__int64 __fastcall CWdsComMetadataEntry::get_Type(
        CWdsComMetadataEntry *this,
        enum __MIDL___MIDL_itf_wdsmetadata_0000_0000_0002 *a2)
{
  unsigned int v2; // edi

  v2 = 0;
  if ( a2
    || (v2 = -2147024809,
        (int)ElValidateHr(-2147024809, 0, "base\\eco\\wds\\lib\\metadata\\com\\wdscommetadataentry.cpp", 0x14Au) >= 0) )
  {
    switch ( *((_DWORD *)this + 26) )
    {
      case 1:
        *(_DWORD *)a2 = 0;
        break;
      case 2:
        *(_DWORD *)a2 = 1;
        break;
      case 3:
        *(_DWORD *)a2 = 2;
        break;
      case 4:
        *(_DWORD *)a2 = 3;
        break;
      case 5:
        *(_DWORD *)a2 = 4;
        break;
      case 6:
        *(_DWORD *)a2 = 5;
        break;
      case 7:
        *(_DWORD *)a2 = 6;
        break;
      default:
        v2 = -2147418113;
        ElValidateHr(
          -2147418113,
          (const char *)a2,
          "base\\eco\\wds\\lib\\metadata\\com\\wdscommetadataentry.cpp",
          0x16Du);
        break;
    }
  }
  return v2;
}

```

## disassembly

```asm
0x180011b70  mov     [rsp+arg_0], rbx
0x180011b75  mov     [rsp+arg_8], rsi
0x180011b7a  push    rdi
0x180011b7b  sub     rsp, 20h
0x180011b7f  xor     edi, edi
0x180011b81  mov     rbx, rdx
0x180011b84  mov     rsi, rcx
0x180011b87  test    rdx, rdx
0x180011b8a  jnz     short loc_180011BA9
0x180011b8c  mov     edi, 80070057h
0x180011b91  lea     r8, aBaseEcoWdsLibM_2; "base\\eco\\wds\\lib\\metadata\\com\\wds"...
0x180011b98  mov     ecx, edi; int
0x180011b9a  mov     r9d, 14Ah; unsigned int
0x180011ba0  call    ?ElValidateHr@@YAJJPEBD0K@Z; ElValidateHr(long,char const *,char const *,ulong)
0x180011ba5  test    eax, eax
0x180011ba7  js      short loc_180011C1D
0x180011ba9  mov     ecx, [rsi+68h]
0x180011bac  sub     ecx, 1
0x180011baf  jz      short loc_180011C1A
0x180011bb1  sub     ecx, 1
0x180011bb4  jz      short loc_180011C12
0x180011bb6  sub     ecx, 1
0x180011bb9  jz      short loc_180011C0A
0x180011bbb  sub     ecx, 1
0x180011bbe  jz      short loc_180011C02
0x180011bc0  sub     ecx, 1
0x180011bc3  jz      short loc_180011BFA
0x180011bc5  sub     ecx, 1
0x180011bc8  jz      short loc_180011BF2
0x180011bca  cmp     ecx, 1
0x180011bcd  jz      short loc_180011BEA
0x180011bcf  mov     edi, 8000FFFFh
0x180011bd4  lea     r8, aBaseEcoWdsLibM_2; "base\\eco\\wds\\lib\\metadata\\com\\wds"...
0x180011bdb  mov     ecx, edi; int
0x180011bdd  mov     r9d, 16Dh; unsigned int
0x180011be3  call    ?ElValidateHr@@YAJJPEBD0K@Z; ElValidateHr(long,char const *,char const *,ulong)
0x180011be8  jmp     short loc_180011C1D
0x180011bea  mov     dword ptr [rbx], 6
0x180011bf0  jmp     short loc_180011C1D
0x180011bf2  mov     dword ptr [rbx], 5
0x180011bf8  jmp     short loc_180011C1D
0x180011bfa  mov     dword ptr [rbx], 4
0x180011c00  jmp     short loc_180011C1D
0x180011c02  mov     dword ptr [rbx], 3
0x180011c08  jmp     short loc_180011C1D
0x180011c0a  mov     dword ptr [rbx], 2
0x180011c10  jmp     short loc_180011C1D
0x180011c12  mov     dword ptr [rbx], 1
0x180011c18  jmp     short loc_180011C1D
0x180011c1a  and     dword ptr [rbx], 0
0x180011c1d  mov     rbx, [rsp+28h+arg_0]
0x180011c22  mov     eax, edi
0x180011c24  mov     rsi, [rsp+28h+arg_8]
0x180011c29  add     rsp, 20h
0x180011c2d  pop     rdi
0x180011c2e  retn
```
