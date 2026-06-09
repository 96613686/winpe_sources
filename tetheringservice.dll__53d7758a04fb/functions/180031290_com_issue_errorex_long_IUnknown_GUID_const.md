# _com_issue_errorex(long,IUnknown *,_GUID const &)

- ea: `0x180031290`
- end: `0x180031322`
- name: `?_com_issue_errorex@@YAXJPEAUIUnknown@@AEBU_GUID@@@Z`
- size: `146`
- prototype: `void __fastcall __noreturn(int, struct IUnknown *, const struct _GUID *)`
- caller_count: `8`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180023974`
- `0x180028998`
- `0x180029048`
- `0x1800293e8`
- `0x180029600`
- `0x180029680`
- `0x180029740`
- `0x180029a5c`

## callees

- `0x180031290`
- `0x180031448`
- `0x180033010`

## import_xrefs

- `OLEAUT32!__imp_GetErrorInfo` at `0x180031302`
- `OLEAUT32!__imp_GetErrorInfo` at `0x180031302`

## pseudocode

```c
void __fastcall __noreturn _com_issue_errorex(int a1, struct IUnknown *a2, const struct _GUID *a3)
{
  struct IErrorInfo *v5; // rdx
  struct IUnknownVtbl *lpVtbl; // rax
  int v8; // ebx
  __int64 v9; // [rsp+38h] [rbp+10h] BYREF
  IErrorInfo *pperrinfo; // [rsp+48h] [rbp+20h] BYREF

  v5 = 0;
  pperrinfo = 0;
  if ( a2 )
  {
    lpVtbl = a2->lpVtbl;
    v9 = 0;
    if ( ((__int64 (__fastcall *)(struct IUnknown *, GUID *, __int64 *))lpVtbl->QueryInterface)(
           a2,
           &GUID_df0b3d60_548f_101b_8e65_08002b2bd119,
           &v9) < 0
      || (v8 = (*(__int64 (__fastcall **)(__int64, const struct _GUID *))(*(_QWORD *)v9 + 24LL))(v9, a3),
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9),
          v8)
      || !GetErrorInfo(0, &pperrinfo) )
    {
      v5 = pperrinfo;
    }
    else
    {
      v5 = 0;
      pperrinfo = 0;
    }
  }
  _com_raise_error(a1, v5);
}

```

## disassembly

```asm
0x180031290  mov     r11, rsp
0x180031293  mov     [r11+8], rbx
0x180031297  push    rdi
0x180031298  sub     rsp, 20h
0x18003129c  mov     r9, rdx
0x18003129f  mov     rbx, r8
0x1800312a2  xor     edx, edx
0x1800312a4  mov     edi, ecx
0x1800312a6  mov     [r11+20h], rdx
0x1800312aa  test    r9, r9
0x1800312ad  jz      short loc_18003131A
0x1800312af  mov     rax, [r9]
0x1800312b2  lea     r8, [r11+10h]
0x1800312b6  mov     [r11+10h], rdx
0x1800312ba  mov     rcx, r9
0x1800312bd  lea     rdx, _GUID_df0b3d60_548f_101b_8e65_08002b2bd119
0x1800312c4  mov     rax, [rax]
0x1800312c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800312cc  test    eax, eax
0x1800312ce  js      short loc_180031315
0x1800312d0  mov     rcx, [rsp+28h+arg_8]
0x1800312d5  mov     rdx, rbx
0x1800312d8  mov     rax, [rcx]
0x1800312db  mov     rax, [rax+18h]
0x1800312df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800312e4  mov     rcx, [rsp+28h+arg_8]
0x1800312e9  mov     ebx, eax
0x1800312eb  mov     rdx, [rcx]
0x1800312ee  mov     rax, [rdx+10h]
0x1800312f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800312f7  test    ebx, ebx
0x1800312f9  jnz     short loc_180031315
0x1800312fb  lea     rdx, [rsp+28h+pperrinfo]; pperrinfo
0x180031300  xor     ecx, ecx; dwReserved
0x180031302  call    cs:__imp_GetErrorInfo
0x180031308  test    eax, eax
0x18003130a  jz      short loc_180031315
0x18003130c  xor     edx, edx
0x18003130e  mov     [rsp+28h+pperrinfo], rdx
0x180031313  jmp     short loc_18003131A
0x180031315  mov     rdx, [rsp+28h+pperrinfo]; struct IErrorInfo *
0x18003131a  mov     ecx, edi; int
0x18003131c  call    ?_com_raise_error@@YAXJPEAUIErrorInfo@@@Z; _com_raise_error(long,IErrorInfo *)
```
