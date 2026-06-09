# XmlPrinter::Start(void *,bool)

- ea: `0x14000e8c4`
- end: `0x14000e91d`
- name: `?Start@XmlPrinter@@QEAAXPEAX_N@Z`
- size: `89`
- prototype: `void(XmlPrinter *__hidden this, void *, bool)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x14000db10`
- `0x14000e550`
- `0x140026680`

## callees

- `0x14000d144`
- `0x14000e8c4`

## string_xrefs

- `0x14000e8e9`: `<?xml version="1.0" encoding="UTF-8"?>\n`
- `0x14000e8fb`: `<?xml version="1.0" encoding="UTF-16"?>\n`

## pseudocode

```c
void __fastcall XmlPrinter::Start(XmlPrinter *this, void *a2, char a3)
{
  const wchar_t *v3; // rcx
  const wchar_t *v4; // [rsp+20h] [rbp-18h] BYREF
  __int64 v5; // [rsp+28h] [rbp-10h]

  *(_QWORD *)this = a2;
  *((_BYTE *)this + 32) = a3;
  *((_BYTE *)this + 33) = 0;
  if ( a3 )
  {
    if ( g_outputUnicode )
    {
      v3 = L"<?xml version=\"1.0\" encoding=\"UTF-16\"?>\r\n";
      v5 = 41;
    }
    else
    {
      v3 = L"<?xml version=\"1.0\" encoding=\"UTF-8\"?>\r\n";
      v5 = 40;
    }
    v4 = v3;
    FilePuts(a2, &v4);
  }
}

```

## disassembly

```asm
0x14000e8c4  sub     rsp, 38h
0x14000e8c8  mov     [rcx], rdx
0x14000e8cb  mov     rax, rdx
0x14000e8ce  mov     [rcx+20h], r8b
0x14000e8d2  mov     byte ptr [rcx+21h], 0
0x14000e8d6  test    r8b, r8b
0x14000e8d9  jz      short loc_14000E918
0x14000e8db  cmp     cs:?g_outputUnicode@@3_NA, 0; bool g_outputUnicode
0x14000e8e2  lea     rdx, [rsp+38h+var_18]
0x14000e8e7  jnz     short loc_14000E8FB
0x14000e8e9  lea     rcx, aXmlVersion10En_0; "<?xml version=\"1.0\" encoding=\"UTF-8"...
0x14000e8f0  mov     [rsp+38h+var_10], 28h ; '('
0x14000e8f9  jmp     short loc_14000E90B
0x14000e8fb  lea     rcx, aXmlVersion10En; "<?xml version=\"1.0\" encoding=\"UTF-16"...
0x14000e902  mov     [rsp+38h+var_10], 29h ; ')'
0x14000e90b  mov     [rsp+38h+var_18], rcx
0x14000e910  mov     rcx, rax; hFile
0x14000e913  call    ?FilePuts@@YAJPEAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; FilePuts(void *,std::wstring_view)
0x14000e918  add     rsp, 38h
0x14000e91c  retn
```
