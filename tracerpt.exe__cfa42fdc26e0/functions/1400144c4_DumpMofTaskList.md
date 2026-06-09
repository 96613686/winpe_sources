# DumpMofTaskList

- ea: `0x1400144c4`
- end: `0x140014598`
- name: `DumpMofTaskList`
- size: `212`
- prototype: `__int64 __fastcall(struct _iobuf **)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x1400145a0`

## callees

- `0x1400144c4`
- `0x140016360`
- `0x1400164c4`
- `0x140032488`
- `0x140040130`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140014556`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140014556`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140014548`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140014548`

## string_xrefs

- `0x1400144ee`: `		<tasks>\n`
- `0x140014530`: `			<task value="%d" eventGUID="%ws" name="task%d" message="$(string.string%d)" />\n`
- `0x140014567`: `		</tasks>\n`

## pseudocode

```c
__int64 __fastcall DumpMofTaskList(struct _iobuf **a1)
{
  void **v2; // rsi
  __int64 v3; // rcx
  _QWORD *v4; // rax
  HANDLE ProcessHeap; // rax
  struct _GUID *v6; // rdi
  __int64 v8; // [rsp+20h] [rbp-128h]
  __int64 v9; // [rsp+28h] [rbp-120h]
  unsigned __int16 v10[128]; // [rsp+30h] [rbp-118h] BYREF

  TracerptFPutws((wchar_t *)L"\t\t<tasks>\r\n", *a1);
  v2 = (void **)(a1 + 22);
  while ( 1 )
  {
    v6 = (struct _GUID *)*v2;
    if ( *v2 == v2 )
      break;
    v3 = *(_QWORD *)&v6->Data1;
    v4 = *(_QWORD **)v6->Data4;
    *v4 = *(_QWORD *)&v6->Data1;
    *(_QWORD *)(v3 + 8) = v4;
    CpdiGuidToString(v10, 0x80u, v6 + 1);
    LODWORD(v9) = v6[2].Data1;
    LODWORD(v8) = *(_DWORD *)&v6[2].Data2;
    TracerptFWPrintf(
      *a1,
      (wchar_t *)L"\t\t\t<task value=\"%d\" eventGUID=\"%ws\" name=\"task%d\" message=\"$(string.string%d)\" />\r\n",
      (unsigned int)v8,
      v10,
      v8,
      v9);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v6);
  }
  return TracerptFPutws((wchar_t *)L"\t\t</tasks>\r\n", *a1);
}

```

## disassembly

```asm
0x1400144c4  mov     [rsp+arg_8], rbx
0x1400144c9  mov     [rsp+arg_10], rsi
0x1400144ce  push    rdi
0x1400144cf  sub     rsp, 140h
0x1400144d6  mov     rax, cs:__security_cookie
0x1400144dd  xor     rax, rsp
0x1400144e0  mov     [rsp+148h+var_18], rax
0x1400144e8  mov     rdx, [rcx]; struct _iobuf *
0x1400144eb  mov     rbx, rcx
0x1400144ee  lea     rcx, aTasks; "\t\t<tasks>\r\n"
0x1400144f5  call    ?TracerptFPutws@@YAKPEBGPEAU_iobuf@@@Z; TracerptFPutws(ushort const *,_iobuf *)
0x1400144fa  lea     rsi, [rbx+0B0h]
0x140014501  jmp     short loc_14001455C
0x140014503  mov     rcx, [rdi]
0x140014506  lea     r8, [rdi+10h]; struct _GUID *
0x14001450a  mov     rax, [rdi+8]
0x14001450e  mov     edx, 80h; unsigned int
0x140014513  mov     [rax], rcx
0x140014516  mov     [rcx+8], rax
0x14001451a  lea     rcx, [rsp+148h+var_118]; unsigned __int16 *
0x14001451f  call    ?CpdiGuidToString@@YAPEAGPEAGKPEAU_GUID@@@Z; CpdiGuidToString(ushort *,ulong,_GUID *)
0x140014524  mov     eax, [rdi+20h]
0x140014527  lea     r9, [rsp+148h+var_118]
0x14001452c  mov     r8d, [rdi+24h]
0x140014530  lea     rdx, aTaskValueDEven; "\t\t\t<task value=\"%d\" eventGUID=\"%w"...
0x140014537  mov     rcx, [rbx]; struct _iobuf *
0x14001453a  mov     dword ptr [rsp+148h+var_120], eax
0x14001453e  mov     dword ptr [rsp+148h+var_128], r8d
0x140014543  call    ?TracerptFWPrintf@@YAKPEAU_iobuf@@PEBGZZ; TracerptFWPrintf(_iobuf *,ushort const *,...)
0x140014548  call    cs:__imp_GetProcessHeap
0x14001454e  mov     r8, rdi; lpMem
0x140014551  xor     edx, edx; dwFlags
0x140014553  mov     rcx, rax; hHeap
0x140014556  call    cs:__imp_HeapFree
0x14001455c  mov     rdi, [rsi]
0x14001455f  cmp     rdi, rsi
0x140014562  jnz     short loc_140014503
0x140014564  mov     rdx, [rbx]; struct _iobuf *
0x140014567  lea     rcx, aTasks_0; "\t\t</tasks>\r\n"
0x14001456e  call    ?TracerptFPutws@@YAKPEBGPEAU_iobuf@@@Z; TracerptFPutws(ushort const *,_iobuf *)
0x140014573  mov     rcx, [rsp+148h+var_18]
0x14001457b  xor     rcx, rsp; StackCookie
0x14001457e  call    __security_check_cookie
0x140014583  lea     r11, [rsp+148h+var_8]
0x14001458b  mov     rbx, [r11+18h]
0x14001458f  mov     rsi, [r11+20h]
0x140014593  mov     rsp, r11
0x140014596  pop     rdi
0x140014597  retn
```
