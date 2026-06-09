# ClusApi::Resource::Delete(int,wchar_t const *)

- ea: `0x18002d330`
- end: `0x18002d35d`
- name: `?Delete@Resource@ClusApi@@UEAAJHPEB_W@Z`
- size: `45`
- prototype: `__int64 __fastcall(ClusApi::Resource *__hidden this, int, const wchar_t *)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x18002d330`

## import_xrefs

- `CLUSAPI!DeleteClusterResourceEx` at `0x18002d346`
- `CLUSAPI!DeleteClusterResourceEx` at `0x18002d346`

## string_xrefs

- `0x18002d338`: `cluswmiext!ClusApi::Resource::Delete`

## pseudocode

```c
__int64 __fastcall ClusApi::Resource::Delete(ClusApi::Resource *this, __int64 a2, const wchar_t *a3)
{
  __int64 v3; // rcx
  const wchar_t *v4; // rdx
  __int64 result; // rax

  v3 = *((_QWORD *)this + 7);
  v4 = L"cluswmiext!ClusApi::Resource::Delete";
  if ( a3 )
    v4 = a3;
  result = DeleteClusterResourceEx(v3, v4);
  if ( (int)result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x18002d330  sub     rsp, 28h
0x18002d334  mov     rcx, [rcx+38h]
0x18002d338  lea     rdx, aCluswmiextClus_54; "cluswmiext!ClusApi::Resource::Delete"
0x18002d33f  test    r8, r8
0x18002d342  cmovnz  rdx, r8
0x18002d346  call    cs:__imp_DeleteClusterResourceEx
0x18002d34c  test    eax, eax
0x18002d34e  jle     short loc_18002D358
0x18002d350  movzx   eax, ax
0x18002d353  or      eax, 80070000h
0x18002d358  add     rsp, 28h
0x18002d35c  retn
```
