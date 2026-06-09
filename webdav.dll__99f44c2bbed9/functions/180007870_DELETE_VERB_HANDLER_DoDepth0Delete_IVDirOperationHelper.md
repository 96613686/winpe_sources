# DELETE_VERB_HANDLER::DoDepth0Delete(IVDirOperationHelper *)

- ea: `0x180007870`
- end: `0x180007951`
- name: `?DoDepth0Delete@DELETE_VERB_HANDLER@@AEAAJPEAVIVDirOperationHelper@@@Z`
- size: `225`
- prototype: `__int64 __fastcall(DELETE_VERB_HANDLER *__hidden this, struct IVDirOperationHelper *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180007710`

## callees

- `0x180007870`
- `0x180007bb0`
- `0x180023010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800078c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800078c3`

## string_xrefs

- `0x1800078fd`: `Error Deleting File or Directory`

## pseudocode

```c
__int64 __fastcall DELETE_VERB_HANDLER::DoDepth0Delete(DELETE_VERB_HANDLER *this, struct IVDirOperationHelper *a2)
{
  signed int v3; // edi
  signed int LastError; // eax
  __int64 v5; // rbx
  __int64 v6; // rax
  char v8; // [rsp+20h] [rbp-18h]

  v3 = (*(__int64 (__fastcall **)(struct IVDirOperationHelper *, _QWORD, _QWORD))(*(_QWORD *)a2 + 16LL))(
         a2,
         *((_QWORD *)this + 9),
         *((_QWORD *)this + 23));
  if ( v3 >= 0 )
  {
    if ( (*(unsigned int (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 30) + 104LL))(
           *((_QWORD *)this + 30),
           *((_QWORD *)this + 23)) )
    {
      return (unsigned int)v3;
    }
    LastError = GetLastError();
    v3 = LastError;
    if ( LastError > 0 )
      v3 = (unsigned __int16)LastError | 0x80070000;
    v5 = *((_QWORD *)this + 23);
    v6 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 1) + 272LL))(*((_QWORD *)this + 1));
    v8 = 3;
    (*(void (__fastcall **)(__int64, const wchar_t *, __int64, _QWORD, char))(*(_QWORD *)v6 + 32LL))(
      v6,
      L"Error Deleting File or Directory",
      v5,
      (unsigned int)v3,
      v8);
  }
  if ( (unsigned int)(v3 + 2147024894) > 1 )
  {
    if ( v3 < 0 )
      DAV_TRACE::TracePropertyDeleteError(
        *((struct IHttpContext **)this + 1),
        v3,
        *((const unsigned __int16 **)this + 9),
        *((const unsigned __int16 **)this + 23));
  }
  else
  {
    return 0;
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180007870  mov     [rsp+arg_0], rbx
0x180007875  mov     [rsp+arg_8], rsi
0x18000787a  push    rdi
0x18000787b  sub     rsp, 30h
0x18000787f  mov     rax, [rdx]
0x180007882  mov     r9, rdx
0x180007885  mov     r8, [rcx+0B8h]
0x18000788c  mov     rsi, rcx
0x18000788f  mov     rdx, [rcx+48h]
0x180007893  mov     rcx, r9
0x180007896  mov     rax, [rax+10h]
0x18000789a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000789f  mov     edi, eax
0x1800078a1  test    eax, eax
0x1800078a3  js      short loc_180007916
0x1800078a5  mov     rcx, [rsi+0F0h]
0x1800078ac  mov     rdx, [rcx]
0x1800078af  mov     rax, [rdx+68h]
0x1800078b3  mov     rdx, [rsi+0B8h]
0x1800078ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800078bf  test    eax, eax
0x1800078c1  jnz     short loc_18000793F
0x1800078c3  call    cs:__imp_GetLastError
0x1800078c9  mov     edi, eax
0x1800078cb  test    eax, eax
0x1800078cd  jle     short loc_1800078D8
0x1800078cf  movzx   edi, ax
0x1800078d2  or      edi, 80070000h
0x1800078d8  mov     rcx, [rsi+8]
0x1800078dc  mov     rbx, [rsi+0B8h]
0x1800078e3  mov     rax, [rcx]
0x1800078e6  mov     rax, [rax+110h]
0x1800078ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800078f2  mov     r10, rax
0x1800078f5  mov     [rsp+38h+var_18], 3
0x1800078fa  mov     r9d, edi
0x1800078fd  lea     rdx, aErrorDeletingF; "Error Deleting File or Directory"
0x180007904  mov     r8, rbx
0x180007907  mov     rcx, [rax]
0x18000790a  mov     rax, [rcx+20h]
0x18000790e  mov     rcx, r10
0x180007911  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007916  lea     eax, [rdi+7FF8FFFEh]
0x18000791c  cmp     eax, 1
0x18000791f  ja      short loc_180007925
0x180007921  xor     edi, edi
0x180007923  jmp     short loc_18000793F
0x180007925  test    edi, edi
0x180007927  jns     short loc_18000793F
0x180007929  mov     r9, [rsi+0B8h]; unsigned __int16 *
0x180007930  mov     edx, edi; int
0x180007932  mov     r8, [rsi+48h]; unsigned __int16 *
0x180007936  mov     rcx, [rsi+8]; struct IHttpContext *
0x18000793a  call    ?TracePropertyDeleteError@DAV_TRACE@@SAXPEAVIHttpContext@@JPEBG1@Z; DAV_TRACE::TracePropertyDeleteError(IHttpContext *,long,ushort const *,ushort const *)
0x18000793f  mov     rbx, [rsp+38h+arg_0]
0x180007944  mov     eax, edi
0x180007946  mov     rsi, [rsp+38h+arg_8]
0x18000794b  add     rsp, 30h
0x18000794f  pop     rdi
0x180007950  retn
```
