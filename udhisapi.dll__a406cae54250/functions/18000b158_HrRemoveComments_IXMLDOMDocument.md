# HrRemoveComments(IXMLDOMDocument *)

- ea: `0x18000b158`
- end: `0x18000b22e`
- name: `?HrRemoveComments@@YAJPEAUIXMLDOMDocument@@@Z`
- size: `214`
- prototype: `__int64 __fastcall(struct IXMLDOMDocument *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180005e60`

## callees

- `0x1800038ec`
- `0x18000b158`
- `0x18000c010`

## string_xrefs

- `0x18000b166`: `//comment()`
- `0x18000b20a`: `HrRemoveComments(): Exiting`

## pseudocode

```c
__int64 __fastcall HrRemoveComments(struct IXMLDOMDocument *a1)
{
  struct IXMLDOMDocumentVtbl *lpVtbl; // rax
  int v2; // ebx
  __int64 v4; // [rsp+40h] [rbp+8h] BYREF
  __int64 v5; // [rsp+48h] [rbp+10h] BYREF

  lpVtbl = a1->lpVtbl;
  v5 = 0;
  v4 = 0;
  v2 = ((__int64 (__fastcall *)(struct IXMLDOMDocument *, const wchar_t *, __int64 *))lpVtbl->selectNodes)(
         a1,
         L"//comment()",
         &v5);
  if ( v2 >= 0 )
  {
    v2 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v5)(v5, &IID_IXMLDOMSelection, &v4);
    if ( v2 >= 0 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 152LL))(v4);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
    }
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
  }
  if ( v2 && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      66,
      (unsigned int)WPP_1663e5dd4df63ad0f4f5db840799a00c_Traceguids,
      (unsigned int)"HrRemoveComments(): Exiting",
      v2);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x18000b158  push    rbx
0x18000b15a  sub     rsp, 30h
0x18000b15e  mov     rax, [rcx]
0x18000b161  lea     r8, [rsp+38h+arg_8]
0x18000b166  lea     rdx, aComment; "//comment()"
0x18000b16d  mov     [rsp+38h+arg_8], 0
0x18000b176  mov     [rsp+38h+arg_0], 0
0x18000b17f  mov     rax, [rax+120h]
0x18000b186  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b18b  mov     ebx, eax
0x18000b18d  test    eax, eax
0x18000b18f  js      short loc_18000B1E9
0x18000b191  mov     rcx, [rsp+38h+arg_8]
0x18000b196  lea     r8, [rsp+38h+arg_0]
0x18000b19b  lea     rdx, IID_IXMLDOMSelection
0x18000b1a2  mov     rax, [rcx]
0x18000b1a5  mov     rax, [rax]
0x18000b1a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b1ad  mov     ebx, eax
0x18000b1af  test    eax, eax
0x18000b1b1  js      short loc_18000B1D8
0x18000b1b3  mov     rcx, [rsp+38h+arg_0]
0x18000b1b8  mov     rax, [rcx]
0x18000b1bb  mov     rax, [rax+98h]
0x18000b1c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b1c7  mov     rcx, [rsp+38h+arg_0]
0x18000b1cc  mov     rax, [rcx]
0x18000b1cf  mov     rax, [rax+10h]
0x18000b1d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b1d8  mov     rcx, [rsp+38h+arg_8]
0x18000b1dd  mov     rax, [rcx]
0x18000b1e0  mov     rax, [rax+10h]
0x18000b1e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b1e9  test    ebx, ebx
0x18000b1eb  jz      short loc_18000B226
0x18000b1ed  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b1f4  lea     rax, WPP_GLOBAL_Control
0x18000b1fb  cmp     rcx, rax
0x18000b1fe  jz      short loc_18000B226
0x18000b200  test    byte ptr [rcx+1Ch], 1
0x18000b204  jz      short loc_18000B226
0x18000b206  mov     rcx, [rcx+10h]
0x18000b20a  lea     r9, aHrremovecommen; "HrRemoveComments(): Exiting"
0x18000b211  mov     edx, 42h ; 'B'
0x18000b216  mov     [rsp+38h+var_18], ebx
0x18000b21a  lea     r8, WPP_1663e5dd4df63ad0f4f5db840799a00c_Traceguids
0x18000b221  call    WPP_SF_sd
0x18000b226  mov     eax, ebx
0x18000b228  add     rsp, 30h
0x18000b22c  pop     rbx
0x18000b22d  retn
```
