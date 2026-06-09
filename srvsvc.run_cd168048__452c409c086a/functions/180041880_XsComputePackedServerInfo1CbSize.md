# XsComputePackedServerInfo1CbSize

- ea: `0x180041880`
- end: `0x1800418fc`
- name: `XsComputePackedServerInfo1CbSize`
- size: `124`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x180041c94`

## callees

- `0x180041838`
- `0x180041880`

## import_xrefs

- `ntdll!RtlxUnicodeStringToOemSize` at `0x1800418da`
- `ntdll!RtlxUnicodeStringToOemSize` at `0x1800418da`

## pseudocode

```c
__int64 __fastcall XsComputePackedServerInfo1CbSize(__int64 a1)
{
  _WORD *v1; // r11
  ULONG v2; // edx
  WCHAR *v3; // r11
  ULONG v4; // eax
  UNICODE_STRING UnicodeString; // [rsp+20h] [rbp-18h] BYREF
  __int64 v7; // [rsp+40h] [rbp+8h] BYREF

  v1 = *(_WORD **)(a1 + 32);
  v2 = 0;
  if ( v1 && *v1 )
  {
    v7 = 0;
    UnicodeString = 0;
    if ( (int)RtlStringLengthWorkerW(v1, 0x7FFF, &v7) < 0 )
    {
      v4 = 256;
    }
    else
    {
      UnicodeString.Buffer = v3;
      UnicodeString.Length = 2 * v7;
      UnicodeString.MaximumLength = 2 * v7 + 2;
      v4 = RtlxUnicodeStringToOemSize(&UnicodeString);
      if ( v4 > 0x100 )
        v4 = 256;
    }
    v2 = v4 - 1;
  }
  return v2 + 27;
}

```

## disassembly

```asm
0x180041880  sub     rsp, 38h
0x180041884  mov     r11, [rcx+20h]
0x180041888  xor     edx, edx
0x18004188a  test    r11, r11
0x18004188d  jz      short loc_1800418F4
0x18004188f  xor     eax, eax
0x180041891  cmp     ax, [r11]
0x180041895  jz      short loc_1800418F4
0x180041897  xorps   xmm0, xmm0
0x18004189a  mov     [rsp+38h+arg_0], rax
0x18004189f  lea     r8, [rsp+38h+arg_0]
0x1800418a4  mov     edx, 7FFFh
0x1800418a9  mov     rcx, r11
0x1800418ac  movups  xmmword ptr [rsp+38h+UnicodeString.Length], xmm0
0x1800418b1  call    RtlStringLengthWorkerW
0x1800418b6  test    eax, eax
0x1800418b8  js      short loc_1800418EC
0x1800418ba  movzx   eax, word ptr [rsp+38h+arg_0]
0x1800418bf  lea     rcx, [rsp+38h+UnicodeString]; UnicodeString
0x1800418c4  add     ax, ax
0x1800418c7  mov     [rsp+38h+UnicodeString.Buffer], r11
0x1800418cc  mov     [rsp+38h+UnicodeString.Length], ax
0x1800418d1  add     ax, 2
0x1800418d5  mov     [rsp+38h+UnicodeString.MaximumLength], ax
0x1800418da  call    cs:__imp_RtlxUnicodeStringToOemSize
0x1800418e0  mov     ecx, 100h
0x1800418e5  cmp     eax, ecx
0x1800418e7  cmova   eax, ecx
0x1800418ea  jmp     short loc_1800418F1
0x1800418ec  mov     eax, 100h
0x1800418f1  lea     edx, [rax-1]
0x1800418f4  lea     eax, [rdx+1Bh]
0x1800418f7  add     rsp, 38h
0x1800418fb  retn
```
